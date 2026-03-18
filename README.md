# PAC3

El quadern jupyter s'ha executat de forma remota a [Colab](https://colab.research.google.com/)
amb VS Code, ja que requereix l'ús de GPU per accelerar el processament. Els
primers exercicis es poden executar en local, mentre que els altres no es
recomana far-ho per l'elevat temps d'execució necessari a menys que es disposi
d'una GPU.

## Execucio remota amb Colab des de VS Code

Una vegada instal·lades les extensions de VS Code, només cal establir una
connexió a Colab en un host amb GPU. Per a fer-ho, després d'obrir el quadern
cliquem a "Select kernel", "Select Another kernel", "Colab", "New Colab Server
CPU, GPU or TPU", Seleccionem la variant "GPU", seleccionem la GPU, per exemple
"T4", seleccionem una versió de les eines "Latest" i finalment donem un nom al
kernel d'iPython.

## Execució local amb un entorn virtual creat amb conda

L'avantatge d'utilitzar un entorn virtual és que permet aïllar les
dependències del projecte de les del sistema operatiu, evitant conflictes
entre diferents projectes i versions de biblioteques.

Per utilitzar el codi, primer cal preparar l'entorn virtual i instal·lar les
dependències.

Un cop creat i activat l'entorn virtual, ja es pot executar el codi.

> [!NOTE]
> Podeu utilitzar l'extensió de Visual Studio Code
> [Python](https://marketplace.visualstudio.com/items?itemName=ms-python.python)
> per gestionar entorns virtuals i executar codi Python dins de l'editor.
> Per crear un entorn virtual amb venv o conda, accediu a la paleta d'ordres
> (`Ctrl+Shift+P` o `Cmd+Shift+P` a macOS) i escriviu "Python: Create Environment".

> [!IMPORTANT]
> Si voleu canviar l'intèrpret de Python utilitzat per Visual Studio Code,
> podeu fer-ho des de la paleta d'ordres (`Ctrl+Shift+P` o `Cmd+Shift+P` a macOS)
> escrivint "Python: Select Interpreter" i seleccionant l'intèrpret de l'entorn
> virtual que heu creat. Cal tenir en compte que l'intèrpret se seleccionarà
> automàticament amb l'entorn virtual quant aquest s'hagi creat amb l'extensió
> comentada en la nota anterior.

### Entorn virtual amb conda

#### Creació de l'entorn virtual amb conda

Per crear un entorn virtual amb conda, executeu la següent ordre al directori
arrel del projecte:

```sh
conda env create --prefix=./.conda --file=environment.yml
```

Per tal d'assegurar que l'entorn virtual s'ha creat correctament, podeu
comprovar que el directori `.conda/` s'ha creat al directori arrel del projecte.

> [!TIP]
> Miniconda requereix menys espai i és més lleuger que Anaconda. Per a
> instal·lar Miniconda en sistemes macOS, podeu utilitzar Homebrew:

```sh
brew install --cask miniconda
conda init
conda config --set auto_activate_base False
source ~/.bash_profile
conda tos accept --override-channels --channel https://repo.anaconda.com/pkgs/main
conda tos accept --override-channels --channel https://repo.anaconda.com/pkgs/r
```

#### Activació i desactivació de l'entorn virtual amb conda

Per activar l'entorn virtual, executeu la següent ordre:

```sh
conda activate ./.conda
```

Per a desactivar l'entorn virtual, executeu la següent ordre:

```sh
conda deactivate
```

> [!TIP]
> Per canviar el prompt de l'entorn virtual i que mostri el nom de l'entorn,
> un cop activat, podeu executar la següent ordre per escurçar-lo:

```sh
conda config --set env_prompt '({name}) '
```
