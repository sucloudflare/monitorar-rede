<h1>README: Monitoramento de Rede com tcpdump, iftop e nethogs</h1>
<p>Este README fornece uma visão geral de como usar <code>tcpdump</code>, <code>iftop</code> e <code>nethogs</code> para monitoramento de rede em sistemas Linux, com base em sua configuração e interações.</p>

<h2>Pré-requisitos</h2>
<ul>
 <li>Sistema operacional Linux (comandos demonstrados no Kali Linux)</li>
<li><code>tcpdump</code>, <code>iftop</code> e <code>nethogs</code> instalados (<code>tcpdump</code> normalmente vem pré-instalado em muitas distribuições)</li>
</ul>

<h2>Verificando interfaces de rede</h2>
<p>Para começar, identifique as interfaces de rede disponíveis em seu sistema usando os seguintes comandos:</p>
<pre class="command">
ip link show
ifconfig -a
</pre>
<p>Esses comandos listarão todas as interfaces de rede (<code>eth0</code>, <code>wlan0</code>, etc.) e seu status atual (<code>UP</code>, <code>DOWN</code>, <code>NO-CARRIER</code>, etc.).</p>

<h2>Usando tcpdump</h2>
<p><code>tcpdump</code> é um poderoso analisador de pacotes de linha de comando que permite capturar pacotes de rede. Ele pode ser usado para diversas tarefas de análise de rede, como monitoramento de endereços IP ou protocolos específicos.</p>
    
<h3>Uso Básico</h3>
<p>Para capturar pacotes em uma interface específica (<code>eth0</code> neste exemplo) e filtrar por um endereço IP específico (<code>192.168.10.107</code>):</p>
<pre class="command">
sudo tcpdump -i eth0 host 192.168.10.107
</pre>

<h3>Saída detalhada</h3>
<p>Para informações mais detalhadas sobre pacotes, use as flags <code>-v</code> ou <code>-vv</code>:</p>
<pre class="command">
sudo tcpdump -i eth0 -v
 </pre>

<h3>Filtragem de Pacotes</h3>
<p>Você pode filtrar pacotes por protocolo, porta ou outros critérios:</p>
<pre class="command">
sudo tcpdump -i eth0 tcp port 80
</pre>

<h2>Usando iftop</h2>
 <p><code>iftop</code> é uma ferramenta de monitoramento de largura de banda de rede baseada em console em tempo real que mostra uma lista de conexões de rede classificadas por uso de largura de banda.</p>
    
<h3>Uso Básico</h3>
<p>Para monitorar o uso de largura de banda em uma interface específica (<code>eth0</code>):</p>
 <pre class="command">
sudo iftop -i eth0
  </pre>

<h2>Usando nethogs</h2>
<p><code>nethogs</code> monitora o tráfego de rede por processos em vez de conexões. Mostra quais processos estão usando a rede e quanta largura de banda eles ocupam.</p>
    
<h3>Uso Básico</h3>
<p>Para monitorar o uso da rede por processos em <code>eth0</code>:</p>
<pre class="command">
sudo nethogs eth0
 </pre>

<h2>Notas Adicionais</h2>
<ul>
<li>Certifique-se de ter as permissões apropriadas (<code>sudo</code>) para executar esses comandos, pois eles exigem privilégios administrativos para capturar e monitorar o tráfego de rede.</li>
<li>Se <code>tcpdump</code>, <code>iftop</code> ou <code>nethogs</code> não relatarem nenhum dispositivo ou interface, verifique se você está usando o nome correto da interface (<code>eth0</code>, <code>wlan0</code>, etc.) e se a interface está ativa (status <code>UP</code>).</li>
<li>Use <code>Ctrl + C</code> para parar o <code>tcpdump</code>, <code>iftop</code> ou <code>nethogs</code> quando você terminar de monitorar.</li>
</ul>

<h2>Conclusão</h2>
<p>Essas ferramentas (<code>tcpdump</code>, <code>iftop</code> e <code>nethogs</code>) fornecem informações valiosas sobre o tráfego de rede, uso de largura de banda e atividades de rede específicas de processos. Para obter informações mais detalhadas e opções adicionais, consulte as respectivas páginas de manual (<code>man tcpdump</code>, <code>man iftop</code>, <code>man nethogs</code>) ou sua documentação online.</p>
