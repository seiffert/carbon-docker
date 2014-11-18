(Docker) Container that runs Carbon 
=====================================

Use together with pseiffert/graphite-data ([github](https://github.com/seiffert/graphite-data-docker)/[hub](https://registry.hub.docker.com/u/pseiffert/graphite-data/)) and pseiffert/graphite ([github](https://github.com/seiffert/graphite-docker)/[hub](https://registry.hub.docker.com/u/pseiffert/graphite/))

1) Run the data volume container:

	docker run --name=graphite-data pseiffert/graphite-data

2) Run carbon

	docker run --volumes-from=graphite-data -p 2003:2003 pseiffert/carbon

3) Run graphite

	docker run -d --volumes-from=graphite-data -p 8080:80 pseiffert/graphite

4) Access `http://localhost:8080` in your web browser.
