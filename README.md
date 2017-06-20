<html>
	<meta charset = "UTF-8">
	<style>
		/*Button Tag Enabled*/
		p.btge {
			font-family: Trebuchet MS;
			font-size: 16px;
			font-weight: bold;
			height: 50px;
			/*width: 50px;*/
			display: table-cell;
			vertical-align: middle;
			text-align: center;
			color: #d9d9d9;
			cursor: pointer;
            -webkit-touch-callout: none;
            -webkit-user-select: none;
            -khtml-user-select: none;
            -moz-user-select: none;
            -ms-user-select: none;
            -o-user-select: none;
            user-select: none;
		}
		/*Name Tag ×1*/
		p.ntg {
			font-family: Trebuchet MS;
			font-size: 16px;
			font-weight: bold;
			height: 50px;
			width: 100px;
			display: table-cell;
			vertical-align: middle;
			text-align: center;
            -webkit-touch-callout: none;
            -webkit-user-select: none;
            -khtml-user-select: none;
            -moz-user-select: none;
            -ms-user-select: none;
            -o-user-select: none;
            user-select: none;
		}
		/*Value Tag*/
		p.vtg {
			font-family: Trebuchet MS;
			font-size: 16px;
			font-weight: bold;
			height: 50px;
			/*width: 70px;*/
			display: table-cell;
			vertical-align: middle;
			text-align: center;
			color: #d9d9d9;
            -webkit-touch-callout: none;
            -webkit-user-select: none;
            -khtml-user-select: none;
            -moz-user-select: none;
            -ms-user-select: none;
            -o-user-select: none;
            user-select: none;
		}
	</style>
	<body style='margin:0; padding:0' onload='init ()'>
	</body>
	<script>
//                      0(Nc)            1(Rc)            2(lb)                3(Rb)             4(la)                5(Ra)             6(lP)                7(Rp)              8(Uc)                
		var prmAct = [ [1, 0, 0, 0, 0], [0, 0, 0, 0, 0], [1000, 10, 0, 0, 0], [70, 0, 0, 0, 0], [1000, 10, 0, 0, 0], [70, 0, 0, 0, 0], [1000, 10, 0, 0, 0], [150, 0, 0, 0, 0], [21.6, 0, 0, 0, 0] ];
		var cfg = 1;
        var fr0 = 1;
        var fr1 = 1;
        function calc (cfg) {
            switch (fr0) {
                case 1:
//                  Uc1 = Ur * Rc1 / (Rba + Ra1 + Rp1 + Rc1)
                    break;
                case 2:
//                  Uc1 = Ujba * Rc1 / (Ra1 + Rp1 + Rc1);
                    break;
                case 3:
//                  Uc2 = Ujba * Rc2 / (Ra2 + Rp2 + Rc2);
                    break;
                case 4:
//                  Uc2 = Ur * Rc2 / (Rbb + Ra2 + Rp2 + Rc2);
                    break;
                case 5:
//                  Uc2 = Ujbb * Rc2 / (Ra2 + Rp2 + Rc2);
                    break;
                case 6:
//                  Uc3 = Ujba * Rc3 / (Ra3 + Rp3 + Rc3);
                    break;
                case 7:
//                  Uc3 = Ujbb * Rc3 / (Ra3 + Rp3 + Rc3);
                    break;
                case 8:
//                  Uc1 = Ujbb * Rc1 / (Rba + Ra1 + Rp1 + Rc1);
                    break;
                case 9:
//                  Uc3 = Ur * Rc3 / (Rbc + Ra3 + Rp3 + Rc3);
                    break;
                case 10:
//                  Uc3 = Ujbb * Rc3 / (Rbc + Ra3 + Rp3 + Rc3);
                    break;
                case 11:
//                  Uc4 = Ujba * Rc4 / (Ra4 + Rp4 + Rc4);
                    break;
                case 12:
//                  Uc4 = Ujbb * Rc4 / (Ra4 + Rp4 + Rc4);
                    break;
                case 13:
//                  Uc3 = Ujbc * Rc3 / (Ra3 + Rp3 + Rc3);
                    break;
                case 14:
//                  Uc4 = Ujbc * Rc4 / (Ra4 + Rp4 + Rc4);
                    break;
                case 15:
//                  Uc4 = Ur * Rc4 / (Rbc + Ra4 + Rp4 + Rc4);
                    break;
                case 16:
//                  Uc2 = Ujba * Rc2 / (Rbb + Ra2 + Rp2 + Rc2);
                    break;
                case 17:
//                  Uc4 = Ujbc * Rc4 / (Rbd + Ra4 + Rp4 + Rc4);
                    break;
            }
            switch (fr1) {
                case 1:
//                  Uc
                    break;
            }
            for (i = 1; i <= prmAct [0] [0]; i ++) {
                prmAct [1] [i] = 1 / (1 / (prmAct [8] [0] / .08) + prmAct [0] [i] / (prmAct [8] [0] / .022) );
                prmAct [3] [i] = 2 * prmAct [2] [i] * prmAct [3] [0] / prmAct [2] [0];
                prmAct [5] [i] = 2 * prmAct [4] [i] * prmAct [5] [0] / prmAct [4] [0];
                prmAct [7] [i] = 2 * prmAct [6] [i] * prmAct [7] [0] / prmAct [6] [0];
            }
            switch (cfg) {
                case 1:
//                  Uc1 = Uc0 * Rc1 / (Rb1 + Ra1 + Rp1 + Rc1)
                    prmAct [8] [1] = prmAct [8] [0] * prmAct [1] [1] / (prmAct [3] [1] + prmAct [5] [1] + prmAct [7] [1] + prmAct [1] [1]);
                    break;
                case 2:
//                  Uc1 = Uc0 * (1 / (1 / (Ra1 + Rp1 + Rc1) + 1 / (Ra2 + Rp2 + Rc2) ) ) / (Rb1 + 1 / (1 / (Ra1 + Rp1 + Rc1) + 1 / (Ra2 + Rp2 + Rc2) ) ) * Rc1 / (Ra1 + Rp1 + Rc1)
                    prmAct [8] [1] = prmAct [8] [0] * (1 / (1 / (prmAct [5] [1] + prmAct [7] [1] + prmAct [1] [1]) + 1 / (prmAct [5] [2] + prmAct [7] [2] + prmAct [1] [2]) ) ) / (prmAct [3] [1] + 1 / (1 / (prmAct [5] [1] + prmAct [7] [1] + prmAct [1] [1]) + 1 / (prmAct [5] [2] + prmAct [7] [2] + prmAct [1] [2]) ) ) * prmAct [1] [1] / (prmAct [5] [1] + prmAct [7] [1] + prmAct [1] [1]);
//                  Uc2 = Uc0 * (1 / (1 / (Ra1 + Rp1 + Rc1) + 1 / (Ra2 + Rp2 + Rc2) ) ) / (Rb1 + 1 / (1 / (Ra1 + Rp1 + Rc1) + 1 / (Ra2 + Rp2 + Rc2) ) ) * Rc2 / (Ra2 + Rp2 + Rc2)
                    prmAct [8] [2] = prmAct [8] [0] * (1 / (1 / (prmAct [5] [1] + prmAct [7] [1] + prmAct [1] [1]) + 1 / (prmAct [5] [2] + prmAct [7] [2] + prmAct [1] [2]) ) ) / (prmAct [3] [1] + 1 / (1 / (prmAct [5] [1] + prmAct [7] [1] + prmAct [1] [1]) + 1 / (prmAct [5] [2] + prmAct [7] [2] + prmAct [1] [2]) ) ) * prmAct [1] [2] / (prmAct [5] [2] + prmAct [7] [2] + prmAct [1] [2]);
                    break;
                case 3:
//                  Uc1 = Uc0 * Rc1 / (Rb1 + Ra1 + Rp1 + Rc1)
                    prmAct [8] [1] = prmAct [8] [0] * prmAct [1] [1] / (prmAct [3] [1] + prmAct [5] [1] + prmAct [7] [1] + prmAct [1] [1]);
//                  Uc2 = Uc0 * Rc2 / (Rb2 + Ra2 + Rp2 + Rc2)
                    prmAct [8] [2] = prmAct [8] [0] * prmAct [1] [2] / (prmAct [3] [2] + prmAct [5] [2] + prmAct [7] [2] + prmAct [1] [2]);
                    break;
                case 4:
                    break;
                default:
//                  Uci = 0
                    prmAct [8] [i] = 0;
            }
        }
        
		var xmlns = 'http://www.w3.org/2000/svg';
        var svgCanvas = document.createElementNS (xmlns,'svg');
        svgCanvas.setAttributeNS (null,'height',960);
        svgCanvas.setAttributeNS (null,'width',1200);
        document.body.appendChild (svgCanvas);
        
		function init () {
	// PARAMETER SNAPSHOT
			prmTmp = prmAct;
	// CALCULATE
			calc (1);
	// RACK NODE
			tNode ('RN', 140, 20, 100, 100, 'fill:#d9d9d9');
			var pRN = document.getElementById ('RN').getBoundingClientRect ();
			nTag ('', pRN.left, pRN.top + 25, 'RACK', 'ntg');
	// BUS CABLES NODE
            tNode ('BCN', 260, 20, 100, 100, 'fill:#933a32');
			var pBCN = document.getElementById ('BCN').getBoundingClientRect ();
			nTag ('', pBCN.left, pBCN.top, 'BUS<br>CABLES', 'ntg', 'color:#d9d9d9');
			vTag (3, 0, pBCN.left, pBCN.top + 50, 0, String (prmAct [3] [0] ).concat (' &Omega;/km'), true, false, 'vtg', 100, 'toNum (this)', 'toStr (this, " &Omega;/km")', 'idBlur (event, this)');
	// JUNCTION BOXES NODE
			tNode ('JBN', 380, 20, 100, 100, 'fill:#d9d9d9');
			var pJBN = document.getElementById ('JBN').getBoundingClientRect ();
			nTag ('', pJBN.left, pJBN.top + 25, 'JUNCTION<br>BOXES', 'ntg');
	// ACCESS CABLES NODE
			tNode ('ACN', 500, 20, 100, 100, 'fill:#7f659f');
			var pACN = document.getElementById ('ACN').getBoundingClientRect ();
			nTag ('', pACN.left, pACN.top, 'ACCESS<br>CABLES', 'ntg', 'color:#d9d9d9');
			vTag (5, 0, pACN.left, pACN.top + 50, 0, String (prmAct [5] [0] ).concat (' &Omega;/km'), true, false, 'vtg', 100, 'toNum (this)', 'toStr (this, " &Omega;/km")', 'idBlur (event, this)');
	// WALL SOCKETS NODE
			tNode ('WSN', 620, 20, 100, 100, 'fill:#d9d9d9');
			var pWSN = document.getElementById ('WSN').getBoundingClientRect ();
			nTag ('', pWSN.left, pWSN.top + 25, 'WALL<br>SOCKETS', 'ntg');
	// PATCH CABLES NODE
			tNode ('PCN', 740, 20, 100, 100, 'fill:#799540');
			var pPCN = document.getElementById ('PCN').getBoundingClientRect ();
			nTag ('', pPCN.left, pPCN.top, 'PATCH<br>CABLES', 'ntg', 'color:#d9d9d9');
			vTag (7, 0, pPCN.left, pPCN.top + 50, 0, String (prmAct [7] [0] ).concat (' &Omega;/km'), true, false, 'vtg', 100, 'toNum (this)', 'toStr (this, " &Omega;/km")', 'idBlur (event, this)');
	// CALL STATIONS NODE
			tNode ('CSN', 860, 20, 200, 100, 'fill:#d9d9d9');
			var pCSN = document.getElementById ('CSN').getBoundingClientRect ();
			nTag ('', pCSN.left, pCSN.top + 25, 'CALL<br>STATIONS', 'ntg');
			nTag ('', pCSN.left + 100, pCSN.top + 25, 'EXTENTIONS', 'ntg');
	// SOURCE VOLTAGE
			tNode ('SV', 20, 140, 100, 100, 'fill:#31859b');
			var pSV = document.getElementById ('SV').getBoundingClientRect ();
			vTag (8, 0, pSV.left, pSV.top, 0, String (prmAct [8] [0] ).concat (' V'), false, false, 'vtg', 100);
			bTag ('SVt', pSV.left, pSV.top + 50, 100, '21.6&#8651;24 V', 'btge', 'svpSrc ()');
	// RACK
			tNode ('R', 140, 140, 100, 100, 'fill:#7f7f7f');
			var pR = document.getElementById ('R').getBoundingClientRect ();
			nTag ('', pR.left, pR.top + (pR.height - 50) / 2, 'R', 'ntg', 'color:#d9d9d9');
	// BUS CABLE 1
			tLink ('BC1', 240, 165, 140, 50, 'fill:#933a32');
			var pBC1 = document.getElementById ('BC1').getBoundingClientRect ();
			vTag (2, 1, pBC1.left, pBC1.top, 0, String (prmAct [2] [1] ).concat (' m'), true, false, 'vtg', 70, 'toNum (this)', 'toStr (this, " m")', 'idBlur (event, this)');
			vTag (3, 1, pBC1.left + 70, pBC1.top, 0, String (prmAct [3] [1].toFixed (1) ).concat (' &Omega;'), false, false, 'vtg', 70);
            /*tLink ('BC1', 405, 240, 50, 140, 'fill:#933a32');
            var pBC1 = document.getElementById ('BC1').getBoundingClientRect ();
            vTag (2, 0, -380, 405, -90, String (prmAct [2] [1] ).concat (' m'), true, false, 'vtg', 70, 'toNum (this)', 'toStr (this, " m")', 'idBlur (event, this)');
            vTag (3, 0, -310, 405, -90, String (prmAct [3] [1].toFixed (1) ).concat (' &Omega;'), false, false, 'vtg', 70);*/
	// JUNCTION BOX 1
			tNode ('JB1', 380, 140, 100, 100, 'fill:#7f7f7f');
			var pJB1 = document.getElementById ('JB1').getBoundingClientRect ();
			nTag ('', pJB1.left + (pJB1.width - 100) / 2, pJB1.top + (pJB1.height - 50) / 2 - 25, 'JB1', 'ntg', 'color:#d9d9d9');
			bTag ('JB-1', pJB1.left, pJB1.top + pJB1.height - 50, 50, '-', 'btge');
			bTag ('JB+1', pJB1.left + pJB1.width - 50, pJB1.top + pJB1.height - 50, 50, '+', 'btge');
	// ACCESS CABLE 1
			tLink ('AC1', pJB1.left + pJB1.width, 165, 140, 50, 'fill:#7f659f');
			var pAC1 = document.getElementById ('AC1').getBoundingClientRect ();
			vTag (4, 1, pAC1.left, pAC1.top, 0, String (prmAct [4] [1] ).concat (' m'), true, false, 'vtg', 70, 'toNum (this)', 'toStr (this, " m")', 'idBlur (event, this)');
			vTag (5, 1, pAC1.left + 70, pAC1.top, 0, String (prmAct [5] [1].toFixed (1) ).concat (' &Omega;'), false, false, 'vtg', 70);
	// WALL SOCKET 1
			tNode ('WS1', 620, 140, 100, 100, 'fill:#7f7f7f');
			var pWS1 = document.getElementById ('WS1').getBoundingClientRect ();
			nTag ('ws1', pWS1.left, pWS1.top + 25, 'WS1', 'ntg', 'color:#d9d9d9');
//			bTag (pWS1.left, pWS1.top + 50, 50, '-', 'btge');
//			bTag (pWS1.left + 50, pWS1.top + 50, 50, '+', 'btge');
	// PATCH CABLE 1
			tLink ('PC1', pWS1.left + pWS1.width, 165, 140, 50, 'fill:#799540');
			var pPC1 = document.getElementById ('PC1').getBoundingClientRect ();
			vTag (6, 1, pPC1.left, pPC1.top, 0, String (prmAct [6] [1] ).concat (' m'), true, false, 'vtg', 70, 'toNum (this)', 'toStr (this, " m")', 'idBlur (event, this)');
			vTag (7, 1, pPC1.left + 70, pPC1.top, 0, String (prmAct [7] [1].toFixed (1) ).concat (' &Omega;'), false, false, 'vtg', 70);
	// CALL STATION 1
			tNode ('CS1', 860, 140, 200, 100, 'fill:#7f7f7f');
			var pCS1 = document.getElementById ('CS1').getBoundingClientRect ();
			nTag ('cs1', pCS1.left, pCS1.top, 'CS1', 'ntg', 'color:#d9d9d9');
            vTag (0, 1, pCS1.left + 100, pCS1.top, 0, 'E&times;'.concat (prmAct [0] [1] ), false, false, 'vtg', 100);
            bTag ('CS-1', pCS1.left, pCS1.top + 50, 50, '-', 'btge', 'subCST ()');
			bTag ('CS+1', pCS1.left + 50, pCS1.top + 50, 50, '+', 'btge', 'addCST ()');
			bTag ('cs-1', pCS1.left + 100, pCS1.top + 50, 50, '-', 'btge', 'subExt (this)');
			bTag ('cs+1', pCS1.left + 150, pCS1.top + 50, 50, '+', 'btge', 'addExt (this)');
	// EFFECTIVE VOLTAGE 1
			tNode ('EV1', 1080, 140, 100, 100, 'fill:#31859b');
			var pEV1 = document.getElementById ('EV1').getBoundingClientRect ();
			vTag (8, 1, pEV1.left, pEV1.top + 25, 0, String (prmAct [8] [1].toFixed (1) ).concat (' V'), false, false, 'vtg', 100);
		}
        
		function updt (cfg) {
			if (prmTmp != prmAct) {
				calc (cfg);
				prmTmp = prmAct;
			}
		}
        
		function tNode (id, x, y, width, height, style) {
			var svgRect = document.createElementNS (xmlns, 'rect');
			svgRect.setAttributeNS (null, 'style', style);
			svgRect.setAttributeNS (null, 'height', height);
			svgRect.setAttributeNS (null, 'width', width);
			svgRect.setAttributeNS (null, 'ry', 5);
			svgRect.setAttributeNS (null, 'rx', 5);
			svgRect.setAttributeNS (null, 'y', y);
			svgRect.setAttributeNS (null, 'x', x);
			svgRect.setAttributeNS (null, 'id', id);
			svgCanvas.appendChild (svgRect);
		}
        
		function nTag (id, x, y, text, clss, style) {
			var svgFoObj = document.createElementNS (xmlns, 'foreignObject');
			svgFoObj.setAttributeNS (null, 'height', 50);
			svgFoObj.setAttributeNS (null, 'width', 100);
			svgFoObj.setAttributeNS (null, 'y', y);
			svgFoObj.setAttributeNS (null, 'x', x);
            svgFoObj.setAttributeNS (null, 'id', id);
			var svgP = document.createElement ('p');
			svgP.setAttributeNS (null, 'class', clss);
			svgP.setAttributeNS (null, 'style', style);
			svgP.innerHTML = text;
			svgFoObj.appendChild (svgP);
			svgCanvas.appendChild (svgFoObj);
		}
        
		function vTag (a, b, x, y, rotate, text, editable, spellcheck, clss, width, onfocus, onblur, onkeypress) {
			var svgFoObj = document.createElementNS (xmlns, 'foreignObject');
            svgFoObj.setAttributeNS (null, 'style', '-moz-transform: rotate('.concat (rotate).concat ('deg)') );
			svgFoObj.setAttributeNS (null, 'height', 50);
			svgFoObj.setAttributeNS (null, 'width', width);
			svgFoObj.setAttributeNS (null, 'y', y);
			svgFoObj.setAttributeNS (null, 'x', x);
            svgFoObj.setAttributeNS (null, 'id', 'p'.concat (String (a) ).concat (String (b) ) );
			var svgP = document.createElement ('p');
			svgP.setAttributeNS (null, 'class', clss);
			svgP.setAttributeNS (null, 'contenteditable', editable);
			svgP.setAttributeNS (null, 'spellcheck', spellcheck);
			svgP.setAttributeNS (null, 'onfocus', onfocus);
			svgP.setAttributeNS (null, 'onblur', onblur);
			svgP.setAttributeNS (null, 'onkeypress', onkeypress);
			svgP.setAttributeNS (null, 'style', 'width: '.concat (width).concat ('px') );
			svgP.setAttributeNS (null, 'id', String (a).concat (String (b) ) );
			svgP.innerHTML = text;
			svgFoObj.appendChild (svgP);
			svgCanvas.appendChild (svgFoObj);
		}
        
		function tLink (id, x, y, width, height, style) {
			var svgRect = document.createElementNS (xmlns, 'rect');
			svgRect.setAttributeNS (null, 'style', style);
			svgRect.setAttributeNS (null, 'height', height);
			svgRect.setAttributeNS (null, 'width', width);
			svgRect.setAttributeNS (null, 'y', y);
			svgRect.setAttributeNS (null, 'x', x);
			svgRect.setAttributeNS (null, 'id', id);
			svgCanvas.appendChild (svgRect);
		}
        
		function bTag (id, x, y, width, text, clss, onclick) {
			var svgFoObj = document.createElementNS (xmlns, 'foreignObject');
			svgFoObj.setAttributeNS (null, 'height', 50);
			svgFoObj.setAttributeNS (null, 'width', width);
			svgFoObj.setAttributeNS (null, 'y', y);
			svgFoObj.setAttributeNS (null, 'x', x);
            svgFoObj.setAttributeNS (null, 'id', id);
			var svgP = document.createElement ('p');
			svgP.setAttributeNS (null, 'class', clss);
			svgP.setAttributeNS (null, 'onclick', onclick);
			svgP.setAttributeNS (null, 'style', 'width: '.concat (width).concat ('px') );
			svgP.innerHTML = text;
			svgFoObj.appendChild (svgP);
			svgCanvas.appendChild (svgFoObj);
		}

        function addExt (id) {
            n = (id.parentElement.id).replace (/^\D+/g, '');
            if (prmAct [0] [n] < 5) {
                prmAct [0] [n] ++;
                calc (cfg);
                document.getElementById (String (0).concat (n) ).innerHTML = 'E&times;'.concat (prmAct [0] [n] );
                document.getElementById (String (8).concat (n) ).innerHTML = prmAct [8] [n].toFixed (1).concat (' V');
            }
        }

        function subExt (id) {
            n = (id.parentElement.id).replace (/^\D+/g, '');
            if (prmAct [0] [n] > 0) {
                prmAct [0] [n] --;
                calc (cfg);
                document.getElementById (String (0).concat (n) ).innerHTML = 'E&times;'.concat (prmAct [0] [n] );
                document.getElementById (String (8).concat (n) ).innerHTML = prmAct [8] [n].toFixed (1).concat (' V');                
            }
        }
        
        function addCST () {
            if (prmAct [0] [0] < 4) {
    // UPDATE COUNT
                prmAct [0] [0] ++;
                var n = prmAct [0] [0];
    // WALL SOCKET n
                tNode ('WS'.concat (n), 620, 240 * n - 120, 100, 100, 'fill:#7f7f7f');
                var pWSn = document.getElementById ('WS'.concat (n) ).getBoundingClientRect ();
                nTag ('ws'.concat (n), pWSn.left, pWSn.top + 25, 'WS'.concat (n), 'ntg', 'color:#d9d9d9');
	// PATCH CABLE n
                tLink ('PC'.concat (n), pWSn.left + pWSn.width, pWSn.top + 25, 140, 50, 'fill:#799540');
                var pPCn = document.getElementById ('PC'.concat (n) ).getBoundingClientRect ();
                prmAct [6] [n] = 10;
                vTag (6, n, pPCn.left, pPCn.top, 0, String (prmAct [6] [n] ).concat (' m'), true, false, 'vtg', 70, 'toNum (this)', 'toStr (this, " m")', 'idBlur (event, this)');
                prmAct [7] [n] = 3;
                vTag (7, n, pPCn.left + 70, pPCn.top, 0, String (prmAct [7] [n].toFixed (1) ).concat (' &Omega;'), false, false, 'vtg', 70);
    // CALL STATION n
                tNode ('CS'.concat (n), 860, 240 * n - 120, 200, 100, 'fill:#7f7f7f');
                var pCSn = document.getElementById ('CS'.concat (n) ).getBoundingClientRect ();
                nTag ('cs'.concat (n), pCSn.left, pWSn.top + 25, 'CS'.concat (n), 'ntg', 'color:#d9d9d9');
                vTag (0, (n), pCSn.left + 100, pCSn.top, 0, 'E&times;'.concat (prmAct [0] [n] ), false, false, 'vtg', 100);
                bTag ('cs-'.concat (n), pCSn.left + 100, pCSn.top + 50, 50, '-', 'btge', 'subExt (this)');
                bTag ('cs+'.concat (n), pCSn.left + 150, pCSn.top + 50, 50, '+', 'btge', 'addExt (this)');
    // EFFECTIVE VOLTAGE n
                tNode ('EV'.concat (n), 1080, 240 * n - 120, 100, 100, 'fill:#31859b');
                var pEVn = document.getElementById ('EV'.concat (n) ).getBoundingClientRect ();
                vTag (8, n, pEVn.left, pEVn.top + 25, 0, String (prmAct [8] [n].toFixed (1) ).concat (' V'), false, false, 'vtg', 100);
            }
        }
        
        function subCST () {
            if (prmAct [0] [0] > 1) {
                var n = prmAct [0] [0];
    // WALL SOCKET n
                document.getElementById ('WS'.concat (n) ).parentNode.removeChild (document.getElementById ('WS'.concat (n) ) );
                document.getElementById ('ws'.concat (n) ).parentNode.removeChild (document.getElementById ('ws'.concat (n) ) );
	// PATCH CABLE n
                document.getElementById ('PC'.concat (n) ).parentNode.removeChild (document.getElementById ('PC'.concat (n) ) );
                prmAct [6] [n] = 0;
                document.getElementById ('p6'.concat (n) ).parentNode.removeChild (document.getElementById ('p6'.concat (n) ) );
                prmAct [7] [n] = 0;
                document.getElementById ('p7'.concat (n) ).parentNode.removeChild (document.getElementById ('p7'.concat (n) ) );
    // CALL STATION n
                document.getElementById ('CS'.concat (n) ).parentNode.removeChild (document.getElementById ('CS'.concat (n) ) );
                document.getElementById ('cs'.concat (n) ).parentNode.removeChild (document.getElementById ('cs'.concat (n) ) );
                document.getElementById ('p0'.concat (n) ).parentNode.removeChild (document.getElementById ('p0'.concat (n) ) );
                document.getElementById ('cs-'.concat (n) ).parentNode.removeChild (document.getElementById ('cs-'.concat (n) ) );
                document.getElementById ('cs+'.concat (n) ).parentNode.removeChild (document.getElementById ('cs+'.concat (n) ) );
    // EFFECTIVE VOLTAGE n
                document.getElementById ('EV'.concat (n) ).parentNode.removeChild (document.getElementById ('EV'.concat (n) ) );
                document.getElementById ('p8'.concat (n) ).parentNode.removeChild (document.getElementById ('p8'.concat (n) ) );
    // UPDATE COUNT
                prmAct [0] [0] --;
            }
        }

        function idBlur (event, id) {
			var x = event.which || event.keyCode;
			if (x == 13) {
				id.blur ();
			}
		}
        
		function toNum (id) {
			id.innerHTML = id.innerHTML.replace (/\D+[^\.]*/g, '');
			selectText (id);
		}
        
		function toStr (id, format) {
			n = id.innerHTML.replace (/\D+[^\.]*/g, '');
			n = Number (n);
            a = Number (String (id.id).slice (0, 1) );
            b = Number (String (id.id).slice (1) );
			prmAct [a] [b] = n;
			n = n.toFixed (0);
			id.innerHTML = n.concat (format);
			calc (cfg);
            if (b == 0) {
                for (i = 1; i < 5; i ++) {
                    n = prmAct [a] [i];
                    if (document.getElementById (String (8).concat (i) ) != null) {
                        document.getElementById (String (a).concat (i) ).innerHTML = prmAct [a] [i].toFixed (1).concat (' &Omega;');
                        document.getElementById (String (8).concat (i) ).innerHTML = prmAct [8] [i].toFixed (1).concat (' V');
                    }
                }
            }
            else {
                a = Math.floor (Number (a) / 2) * 2 + 1;
                n = prmAct [a] [b];
                document.getElementById (String (a).concat (b) ).innerHTML = prmAct [a] [b].toFixed (1).concat (' &Omega;');
                document.getElementById (String (8).concat (b) ).innerHTML = prmAct [8] [b].toFixed (1).concat (' V');
            }
		}
        
		function selectText (id) {
			if (document.selection) {
				var range = document.body.createTextRange ();
				range.moveToElementText (id);
				range.select ();
			} else if (window.getSelection) {
				var range = document.createRange ();
				range.selectNodeContents (id);
				window.getSelection ().removeAllRanges ();
				window.getSelection ().addRange (range);
			}
		}
        
		function svpSrc () {
			if (prmAct [8] [0] == 21.6) prmAct [8] [0] = 24;
            else prmAct [8] [0] = 21.6;
            document.getElementById ('80').innerHTML = prmAct [8] [0].toFixed (1).concat (' V');
            calc (cfg);
            for (i = 1; i < 5; i ++) {
                if (document.getElementById (String (8).concat (i) ) != null) document.getElementById (String (8).concat (i) ).innerHTML = prmAct [8] [i].toFixed (1).concat (' V');
            }
		}
        
	</script>
</html>
