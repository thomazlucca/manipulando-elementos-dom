
// MÓDULO 1

//exercício 1

document.querySelector('html')
document.querySelector('#timer')
document.querySelector('.app__image')
document.querySelector('.app__title')

//exercício 2

const html = document.querySelector('html')
const displayTempo = document.querySelector('#timer')
const banner = document.querySelector('.app__image')
const titulo = document.querySelector('.app__title')

//exercício 3

const iniciarBt = document.querySelector('.app__card-primary-button')
const focoBt = document.querySelector('.app__card-button--foco');
const curtoBt = document.querySelector('.app__card-button--curto');
const longoBt = document.querySelector('.app__card-button--longo');

const temporizadorFoco = 1500;
const temporizadorDescansoCurto = 300;
const temporizadorDescansoLongo = 900;

// MÓDULO 2

//exercicio 1

function alterarContexto(contexto,imagem) {
    html.setAttribute('data-contexto', contexto);
    banner.setAttribute('src', `/imagens/${imagem}.png`);
}

//exercicio 2

  const focoBt = document.querySelector('.app__card-button--foco');
  focoBt.addEventListener('click', () => {
    alterarContexto('foco', 'foco.png');
  });
  
  const curtoBt = document.querySelector('.app__card-button--curto');
  curtoBt.addEventListener('click', () => {
    alterarContexto('descanso-curto', 'descanso-curto.png');
  });
  
  const longoBt = document.querySelector('.app__card-button--longo');
  longoBt.addEventListener('click', () => {
    alterarContexto('descanso-longo', 'descanso-longo.png');
  });

  //exercicio 3

  focoBt.addEventListener('click', () => {
    alterarContexto('foco')
})

curtoBt.addEventListener('click', () => {
    alterarContexto('descanso-curto')
})

longoBt.addEventListener('click', () => {
    alterarContexto('descanso-longo')
})

function alterarContexto(contexto) {
    html.setAttribute('data-contexto', contexto)
    banner.setAttribute('src', `/imagens/${contexto}.png`)
    switch (contexto) {
        case "foco":
            titulo.innerHTML = `
            Otimize sua produtividade,<br>
                <strong class="app__title-strong">mergulhe no que importa.</strong>
            `
            break;
        case "descanso-curto":
            titulo.innerHTML = `
            Que tal dar uma respirada? <strong class="app__title-strong">Faça uma pausa curta!</strong>
            ` 
            break;
        case "descanso-longo":
            titulo.innerHTML = `
            Hora de voltar à superfície.<strong class="app__title-strong"> Faça uma pausa longa.</strong>
            `
        default:
            break;
    }
}