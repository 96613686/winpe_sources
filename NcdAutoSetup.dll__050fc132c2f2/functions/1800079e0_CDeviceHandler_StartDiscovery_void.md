# CDeviceHandler::StartDiscovery(void)

- ea: `0x1800079e0`
- end: `0x18000802e`
- name: `?StartDiscovery@CDeviceHandler@@QEAAJXZ`
- size: `1614`
- prototype: `__int64 __fastcall(CDeviceHandler *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800074f0`
- `0x18000aa58`
- `0x180011b70`

## callees

- `0x1800079e0`
- `0x180008034`
- `0x18000a644`
- `0x18000a778`
- `0x180013840`

## import_xrefs

- `api-ms-win-devices-query-l1-1-0!DevCreateObjectQuery` at `0x180007f9e`
- `api-ms-win-devices-query-l1-1-0!DevCreateObjectQuery` at `0x180007f9e`

## pseudocode

```c
__int64 __fastcall CDeviceHandler::StartDiscovery(CDeviceHandler *this)
{
  _QWORD *v2; // r9
  __int64 v3; // rdx
  int v4; // eax
  _DWORD *v5; // rdx
  int v6; // edi
  char v8; // [rsp+50h] [rbp-B0h] BYREF
  char v9; // [rsp+51h] [rbp-AFh] BYREF
  _DWORD v10[3]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v11; // [rsp+6Ch] [rbp-94h]
  _BYTE v12[28]; // [rsp+7Ch] [rbp-84h] BYREF
  int v13; // [rsp+98h] [rbp-68h]
  __int128 v14; // [rsp+A0h] [rbp-60h]
  int v15; // [rsp+B0h] [rbp-50h]
  int v16; // [rsp+B4h] [rbp-4Ch]
  __int64 v17; // [rsp+B8h] [rbp-48h]
  int v18; // [rsp+C0h] [rbp-40h]
  int v19; // [rsp+C4h] [rbp-3Ch]
  char *v20; // [rsp+C8h] [rbp-38h]
  int v21; // [rsp+D0h] [rbp-30h]
  __int128 v22; // [rsp+D8h] [rbp-28h]
  int v23; // [rsp+E8h] [rbp-18h]
  int v24; // [rsp+ECh] [rbp-14h]
  __int64 v25; // [rsp+F0h] [rbp-10h]
  int v26; // [rsp+F8h] [rbp-8h]
  int v27; // [rsp+FCh] [rbp-4h]
  char *v28; // [rsp+100h] [rbp+0h]
  int v29; // [rsp+108h] [rbp+8h]
  __int128 v30; // [rsp+110h] [rbp+10h]
  int v31; // [rsp+120h] [rbp+20h]
  int v32; // [rsp+124h] [rbp+24h]
  __int64 v33; // [rsp+128h] [rbp+28h]
  int v34; // [rsp+130h] [rbp+30h]
  int v35; // [rsp+134h] [rbp+34h]
  const wchar_t *v36; // [rsp+138h] [rbp+38h]
  int v37; // [rsp+140h] [rbp+40h]
  __int128 v38; // [rsp+148h] [rbp+48h]
  int v39; // [rsp+158h] [rbp+58h]
  int v40; // [rsp+15Ch] [rbp+5Ch]
  __int64 v41; // [rsp+160h] [rbp+60h]
  int v42; // [rsp+168h] [rbp+68h]
  int v43; // [rsp+16Ch] [rbp+6Ch]
  const wchar_t *v44; // [rsp+170h] [rbp+70h]
  int v45; // [rsp+178h] [rbp+78h]
  __int128 v46; // [rsp+180h] [rbp+80h]
  int v47; // [rsp+190h] [rbp+90h]
  int v48; // [rsp+194h] [rbp+94h]
  __int64 v49; // [rsp+198h] [rbp+98h]
  int v50; // [rsp+1A0h] [rbp+A0h]
  int v51; // [rsp+1A4h] [rbp+A4h]
  const wchar_t *v52; // [rsp+1A8h] [rbp+A8h]
  int v53; // [rsp+1B0h] [rbp+B0h]
  __int128 v54; // [rsp+1B8h] [rbp+B8h]
  int v55; // [rsp+1C8h] [rbp+C8h]
  int v56; // [rsp+1CCh] [rbp+CCh]
  __int64 v57; // [rsp+1D0h] [rbp+D0h]
  int v58; // [rsp+1D8h] [rbp+D8h]
  int v59; // [rsp+1DCh] [rbp+DCh]
  __int64 *v60; // [rsp+1E0h] [rbp+E0h]
  int v61; // [rsp+1E8h] [rbp+E8h]
  int v62; // [rsp+1F0h] [rbp+F0h]
  __int128 v63; // [rsp+1F4h] [rbp+F4h]
  _BYTE v64[28]; // [rsp+204h] [rbp+104h] BYREF
  _DWORD v65[3]; // [rsp+220h] [rbp+120h] BYREF
  __int128 v66; // [rsp+22Ch] [rbp+12Ch]
  _BYTE v67[28]; // [rsp+23Ch] [rbp+13Ch] BYREF
  int v68; // [rsp+258h] [rbp+158h]
  __int128 v69; // [rsp+260h] [rbp+160h]
  int v70; // [rsp+270h] [rbp+170h]
  int v71; // [rsp+274h] [rbp+174h]
  __int64 v72; // [rsp+278h] [rbp+178h]
  int v73; // [rsp+280h] [rbp+180h]
  int v74; // [rsp+284h] [rbp+184h]
  const wchar_t *v75; // [rsp+288h] [rbp+188h]
  int v76; // [rsp+290h] [rbp+190h]
  __int128 v77; // [rsp+298h] [rbp+198h]
  int v78; // [rsp+2A8h] [rbp+1A8h]
  int v79; // [rsp+2ACh] [rbp+1ACh]
  __int64 v80; // [rsp+2B0h] [rbp+1B0h]
  int v81; // [rsp+2B8h] [rbp+1B8h]
  int v82; // [rsp+2BCh] [rbp+1BCh]
  const wchar_t *v83; // [rsp+2C0h] [rbp+1C0h]
  int v84; // [rsp+2C8h] [rbp+1C8h]
  __int128 v85; // [rsp+2D0h] [rbp+1D0h]
  int v86; // [rsp+2E0h] [rbp+1E0h]
  int v87; // [rsp+2E4h] [rbp+1E4h]
  __int64 v88; // [rsp+2E8h] [rbp+1E8h]
  int v89; // [rsp+2F0h] [rbp+1F0h]
  int v90; // [rsp+2F4h] [rbp+1F4h]
  const wchar_t *v91; // [rsp+2F8h] [rbp+1F8h]
  int v92; // [rsp+300h] [rbp+200h]
  __int128 v93; // [rsp+308h] [rbp+208h]
  int v94; // [rsp+318h] [rbp+218h]
  int v95; // [rsp+31Ch] [rbp+21Ch]
  __int64 v96; // [rsp+320h] [rbp+220h]
  int v97; // [rsp+328h] [rbp+228h]
  int v98; // [rsp+32Ch] [rbp+22Ch]
  __int64 *v99; // [rsp+330h] [rbp+230h]
  int v100; // [rsp+338h] [rbp+238h]
  int v101; // [rsp+340h] [rbp+240h]
  __int128 v102; // [rsp+344h] [rbp+244h]
  _BYTE v103[28]; // [rsp+354h] [rbp+254h] BYREF
  __int128 v104; // [rsp+370h] [rbp+270h] BYREF
  int v105; // [rsp+380h] [rbp+280h]
  int v106; // [rsp+384h] [rbp+284h]
  __int64 v107; // [rsp+388h] [rbp+288h]
  __int128 v108; // [rsp+390h] [rbp+290h]
  int v109; // [rsp+3A0h] [rbp+2A0h]
  int v110; // [rsp+3A4h] [rbp+2A4h]
  __int64 v111; // [rsp+3A8h] [rbp+2A8h]
  __int128 v112; // [rsp+3B0h] [rbp+2B0h]
  int v113; // [rsp+3C0h] [rbp+2C0h]
  int v114; // [rsp+3C4h] [rbp+2C4h]
  __int64 v115; // [rsp+3C8h] [rbp+2C8h]
  __int128 v116; // [rsp+3D0h] [rbp+2D0h]
  int v117; // [rsp+3E0h] [rbp+2E0h]
  int v118; // [rsp+3E4h] [rbp+2E4h]
  __int64 v119; // [rsp+3E8h] [rbp+2E8h]
  __int128 v120; // [rsp+3F0h] [rbp+2F0h]
  int v121; // [rsp+400h] [rbp+300h]
  int v122; // [rsp+404h] [rbp+304h]
  __int64 v123; // [rsp+408h] [rbp+308h]
  __int128 v124; // [rsp+410h] [rbp+310h]
  int v125; // [rsp+420h] [rbp+320h]
  int v126; // [rsp+424h] [rbp+324h]
  __int64 v127; // [rsp+428h] [rbp+328h]
  __int128 v128; // [rsp+430h] [rbp+330h]
  int v129; // [rsp+440h] [rbp+340h]
  int v130; // [rsp+444h] [rbp+344h]
  __int64 v131; // [rsp+448h] [rbp+348h]
  __int128 v132; // [rsp+450h] [rbp+350h]
  int v133; // [rsp+460h] [rbp+360h]
  int v134; // [rsp+464h] [rbp+364h]
  __int64 v135; // [rsp+468h] [rbp+368h]
  DEVPROPKEY v136; // [rsp+470h] [rbp+370h]
  int v137; // [rsp+484h] [rbp+384h]
  __int64 v138; // [rsp+488h] [rbp+388h]
  __int128 v139; // [rsp+490h] [rbp+390h]
  int v140; // [rsp+4A0h] [rbp+3A0h]
  int v141; // [rsp+4A4h] [rbp+3A4h]
  __int64 v142; // [rsp+4A8h] [rbp+3A8h]
  __int128 v143; // [rsp+4B0h] [rbp+3B0h]
  int v144; // [rsp+4C0h] [rbp+3C0h]
  int v145; // [rsp+4C4h] [rbp+3C4h]
  __int64 v146; // [rsp+4C8h] [rbp+3C8h]
  __int128 v147; // [rsp+4D0h] [rbp+3D0h]
  int v148; // [rsp+4E0h] [rbp+3E0h]
  int v149; // [rsp+4E4h] [rbp+3E4h]
  __int64 v150; // [rsp+4E8h] [rbp+3E8h]

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_7fef1fa79ee3391c6a163bc1b1bc3ea3_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  v20 = &v8;
  v9 = 0;
  v18 = 17;
  v19 = 1;
  v27 = 1;
  v26 = 17;
  v10[2] = 0;
  v13 = 2;
  v16 = 0;
  v17 = 0;
  v21 = 2;
  v24 = 0;
  v25 = 0;
  v32 = 0;
  v33 = 0;
  v40 = 0;
  v41 = 0;
  v48 = 0;
  v49 = 0;
  v53 = 2;
  v56 = 0;
  v57 = 0;
  v34 = 18;
  v42 = 18;
  v50 = 18;
  v28 = &v9;
  memset(v12, 0, sizeof(v12));
  v29 = 196610;
  v37 = 196610;
  v45 = 196610;
  v55 = 5;
  v8 = -1;
  v10[0] = 0x100000;
  v11 = 0;
  v15 = 3;
  v23 = 16;
  v14 = DEVPKEY_Aep_IsAssociatable;
  v22 = DEVPKEY_Aep_IsAssociated;
  v31 = 12;
  v30 = DEVPKEY_Aep_DeviceAddress;
  v35 = 20;
  v36 = L"127.0.0.1";
  v38 = DEVPKEY_Aep_DeviceAddress;
  v39 = 12;
  v43 = 8;
  v44 = L"::1";
  v46 = DEVPKEY_Aep_DeviceAddress;
  v47 = 12;
  v51 = 32;
  v52 = L"0:0:0:0:0:0:0:1";
  v54 = DEVPKEY_Aep_ProtocolId;
  v58 = 13;
  v59 = 16;
  v60 = DAF_ProtocolId_UPnP;
  v61 = 0x200000;
  v62 = 0;
  memset(v64, 0, sizeof(v64));
  v70 = 12;
  memset(v67, 0, sizeof(v67));
  v78 = 12;
  memset(v103, 0, sizeof(v103));
  v86 = 12;
  v75 = L"127.0.0.1";
  v117 = 2;
  v65[2] = 0;
  v63 = 0;
  v71 = 0;
  v66 = 0;
  v72 = 0;
  v102 = 0;
  v76 = 196610;
  v83 = L"::1";
  v84 = 196610;
  v116 = DEVPKEY_Aep_ContainerId;
  v121 = 4;
  v120 = DEVPKEY_Aep_FriendlyName;
  v65[0] = 0x100000;
  v68 = 196610;
  v124 = DEVPKEY_PNPX_ModelName;
  v73 = 18;
  v69 = DEVPKEY_Aep_DeviceAddress;
  v128 = DEVPKEY_PNPX_Manufacturer;
  v74 = 20;
  v77 = DEVPKEY_Aep_DeviceAddress;
  v79 = 0;
  v80 = 0;
  v81 = 18;
  v82 = 8;
  v85 = DEVPKEY_Aep_DeviceAddress;
  v87 = 0;
  v88 = 0;
  v89 = 18;
  v90 = 32;
  v91 = L"0:0:0:0:0:0:0:1";
  v92 = 2;
  v93 = DEVPKEY_Aep_ProtocolId;
  v94 = 5;
  v95 = 0;
  v96 = 0;
  v97 = 13;
  v98 = 16;
  v99 = DAF_ProtocolId_UPnP;
  v100 = 0x200000;
  v101 = 0;
  v104 = DEVPKEY_Aep_IsAssociatable;
  v105 = 3;
  v106 = 0;
  v107 = 0;
  v108 = DEVPKEY_Aep_IsAssociated;
  v109 = 16;
  v110 = 0;
  v111 = 0;
  v112 = DEVPKEY_Aep_ProtocolId;
  v113 = 5;
  v114 = 0;
  v115 = 0;
  v118 = 0;
  v119 = 0;
  v122 = 0;
  v123 = 0;
  v125 = 8194;
  v126 = 0;
  v127 = 0;
  v129 = 0x2000;
  v132 = DEVPKEY_PNPX_DeviceCategory;
  v133 = 12292;
  v136 = DEVPKEY_DeviceContainer_Category;
  v139 = DEVPKEY_PNPX_IpAddress;
  v140 = 12297;
  v143 = DEVPKEY_PNPX_ID;
  v144 = 4101;
  v147 = DEVPKEY_PNPX_Types;
  v130 = 0;
  v131 = 0;
  v134 = 0;
  v135 = 0;
  v137 = 0;
  v138 = 0;
  v141 = 0;
  v142 = 0;
  v145 = 0;
  v146 = 0;
  v148 = 4097;
  v149 = 0;
  v150 = 0;
  if ( *((_DWORD *)this + 2) )
  {
    if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 8) != 0 )
    {
      v3 = 30;
LABEL_11:
      WPP_SF_(v2[2], v3, WPP_7fef1fa79ee3391c6a163bc1b1bc3ea3_Traceguids);
    }
  }
  else if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 8) != 0 )
  {
    v3 = 31;
    goto LABEL_11;
  }
  v4 = *((_DWORD *)this + 2);
  v5 = v10;
  if ( v4 )
    v5 = v65;
  v6 = DevCreateObjectQuery(5, 5, 12, &v104, v4 != 0 ? 6 : 8, v5, CDeviceHandler::s_DevQueryCallback, this, this);
  if ( v6 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_7fef1fa79ee3391c6a163bc1b1bc3ea3_Traceguids);
    CDeviceHandler::StopDiscovery(this);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_7fef1fa79ee3391c6a163bc1b1bc3ea3_Traceguids);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800079e0  mov     [rsp-8+arg_8], rbx
0x1800079e5  mov     [rsp-8+arg_10], rsi
0x1800079ea  push    rbp
0x1800079eb  push    rdi
0x1800079ec  push    r12
0x1800079ee  push    r13
0x1800079f0  push    r15
0x1800079f2  lea     rbp, [rsp-400h]
0x1800079fa  sub     rsp, 500h
0x180007a01  mov     rax, cs:__security_cookie
0x180007a08  xor     rax, rsp
0x180007a0b  mov     [rbp+420h+var_30], rax
0x180007a12  mov     rbx, rcx
0x180007a15  mov     r9, cs:WPP_GLOBAL_Control
0x180007a1c  lea     rax, WPP_GLOBAL_Control
0x180007a23  cmp     r9, rax
0x180007a26  jz      short loc_180007A4B
0x180007a28  test    byte ptr [r9+1Ch], 20h
0x180007a2d  jz      short loc_180007A4B
0x180007a2f  mov     rcx, [r9+10h]
0x180007a33  lea     r8, WPP_7fef1fa79ee3391c6a163bc1b1bc3ea3_Traceguids
0x180007a3a  mov     edx, 1Dh
0x180007a3f  call    WPP_SF_
0x180007a44  mov     r9, cs:WPP_GLOBAL_Control
0x180007a4b  movups  xmm1, cs:DEVPKEY_Aep_DeviceAddress
0x180007a52  mov     r8d, cs:dword_180015C68
0x180007a59  xor     r11d, r11d
0x180007a5c  movups  xmm4, cs:DEVPKEY_Aep_IsAssociatable
0x180007a63  mov     edx, cs:dword_180015BE0
0x180007a69  lea     rax, [rsp+520h+var_4D0]
0x180007a6e  movups  xmm3, cs:DEVPKEY_Aep_IsAssociated
0x180007a75  lea     edi, [r11+2]
0x180007a79  mov     [rbp+420h+var_458], rax
0x180007a7d  movups  xmm2, cs:DEVPKEY_Aep_ProtocolId
0x180007a84  lea     r10d, [r11+11h]
0x180007a88  mov     [rsp+520h+var_4CF], r11b
0x180007a8d  lea     ecx, [rdi-1]
0x180007a90  mov     [rbp+420h+var_460], r10d
0x180007a94  xorps   xmm0, xmm0
0x180007a97  mov     [rbp+420h+var_45C], ecx
0x180007a9a  mov     [rbp+420h+var_424], ecx
0x180007a9d  lea     rax, [rsp+520h+var_4CF]
0x180007aa2  lea     ecx, [rdi+10h]
0x180007aa5  mov     [rbp+420h+var_428], r10d
0x180007aa9  mov     r10d, 30002h
0x180007aaf  mov     [rsp+520h+var_4B8], r11d
0x180007ab4  lea     esi, [rdi+0Eh]
0x180007ab7  mov     [rbp+420h+var_488], edi
0x180007aba  mov     [rbp+420h+var_46C], r11d
0x180007abe  lea     r13, a127001; "127.0.0.1"
0x180007ac5  mov     [rbp+420h+var_468], r11
0x180007ac9  lea     r12, a1; "::1"
0x180007ad0  mov     [rbp+420h+var_450], edi
0x180007ad3  lea     r15, a00000001; "0:0:0:0:0:0:0:1"
0x180007ada  mov     [rbp+420h+var_434], r11d
0x180007ade  mov     [rbp+420h+var_430], r11
0x180007ae2  mov     [rbp+420h+var_3FC], r11d
0x180007ae6  mov     [rbp+420h+var_3F8], r11
0x180007aea  mov     [rbp+420h+var_3C4], r11d
0x180007aee  mov     [rbp+420h+var_3C0], r11
0x180007af2  mov     [rbp+420h+var_38C], r11d
0x180007af9  mov     [rbp+420h+var_388], r11
0x180007b00  mov     [rbp+420h+var_370], edi
0x180007b06  lea     rdi, DAF_ProtocolId_UPnP
0x180007b0d  mov     [rbp+420h+var_354], r11d
0x180007b14  mov     [rbp+420h+var_350], r11
0x180007b1b  mov     r11d, 200000h
0x180007b21  mov     [rbp+420h+var_3F0], ecx
0x180007b24  mov     [rbp+420h+var_3B8], ecx
0x180007b27  mov     [rbp+420h+var_380], ecx
0x180007b2d  mov     ecx, cs:dword_180015B38
0x180007b33  mov     [rbp+420h+var_420], rax
0x180007b37  mov     eax, cs:dword_180015B98
0x180007b3d  movups  xmmword ptr [rsp+520h+var_4A4], xmm0
0x180007b42  mov     [rbp+420h+var_418], r10d
0x180007b46  mov     [rbp+420h+var_3E0], r10d
0x180007b4a  mov     [rbp+420h+var_3A8], r10d
0x180007b4e  xor     r10d, r10d
0x180007b51  mov     [rbp+420h+var_358], ecx
0x180007b57  mov     [rsp+520h+var_4D0], 0FFh
0x180007b5c  mov     [rsp+520h+var_4C0], 100000h
0x180007b64  movups  [rsp+520h+var_4B4], xmm0
0x180007b69  mov     [rbp+420h+var_470], r8d
0x180007b6d  movups  xmmword ptr [rbp+420h+var_4A4+0Ch], xmm0
0x180007b71  mov     [rbp+420h+var_438], edx
0x180007b74  movaps  [rbp+420h+var_480], xmm4
0x180007b78  movups  [rbp+420h+var_448], xmm3
0x180007b7c  mov     [rbp+420h+var_400], eax
0x180007b7f  movaps  [rbp+420h+var_410], xmm1
0x180007b83  mov     [rbp+420h+var_3EC], 14h
0x180007b8a  mov     [rbp+420h+var_3E8], r13
0x180007b8e  movups  [rbp+420h+var_3D8], xmm1
0x180007b92  mov     [rbp+420h+var_3C8], eax
0x180007b95  mov     [rbp+420h+var_3B4], 8
0x180007b9c  mov     [rbp+420h+var_3B0], r12
0x180007ba0  movaps  [rbp+420h+var_3A0], xmm1
0x180007ba7  mov     [rbp+420h+var_390], eax
0x180007bad  mov     [rbp+420h+var_37C], 20h ; ' '
0x180007bb7  mov     [rbp+420h+var_378], r15
0x180007bbe  movups  [rbp+420h+var_368], xmm2
0x180007bc5  mov     [rbp+420h+var_348], 0Dh
0x180007bcf  mov     [rbp+420h+var_344], esi
0x180007bd5  mov     [rbp+420h+var_340], rdi
0x180007bdc  mov     [rbp+420h+var_338], r11d
0x180007be3  mov     [rbp+420h+var_330], 0
0x180007bed  movups  xmmword ptr [rbp+420h+var_31C], xmm0
0x180007bf4  mov     [rbp+420h+var_2B0], eax
0x180007bfa  movups  xmmword ptr [rbp+420h+var_2E4], xmm0
0x180007c01  mov     [rbp+420h+var_278], eax
0x180007c07  movups  xmmword ptr [rbp+420h+var_1CC], xmm0
0x180007c0e  mov     [rbp+420h+var_240], eax
0x180007c14  mov     eax, cs:dword_180015C90
0x180007c1a  movups  xmmword ptr [rbp+420h+var_31C+0Ch], xmm0
0x180007c21  mov     [rbp+420h+var_298], r13
0x180007c28  mov     r13d, 30002h
0x180007c2e  movups  xmmword ptr [rbp+420h+var_2E4+0Ch], xmm0
0x180007c35  mov     [rbp+420h+var_140], eax
0x180007c3b  mov     eax, cs:dword_180015CE0
0x180007c41  movups  xmmword ptr [rbp+420h+var_1CC+0Ch], xmm0
0x180007c48  mov     [rbp+420h+var_2F8], r10d
0x180007c4f  movups  [rbp+420h+var_32C], xmm0
0x180007c56  mov     [rbp+420h+var_2AC], r10d
0x180007c5d  movups  [rbp+420h+var_2F4], xmm0
0x180007c64  mov     [rbp+420h+var_2A8], r10
0x180007c6b  lea     r10d, [rsi+2]
0x180007c6f  movups  [rbp+420h+var_1DC], xmm0
0x180007c76  mov     [rbp+420h+var_290], r13d
0x180007c7d  movups  xmm0, cs:DEVPKEY_Aep_ContainerId
0x180007c84  mov     [rbp+420h+var_260], r12
0x180007c8b  lea     r12d, [rsi+10h]
0x180007c8f  mov     [rbp+420h+var_258], r13d
0x180007c96  xor     r13d, r13d
0x180007c99  movaps  [rbp+420h+var_150], xmm0
0x180007ca0  movups  xmm0, cs:DEVPKEY_Aep_FriendlyName
0x180007ca7  mov     [rbp+420h+var_120], eax
0x180007cad  mov     eax, cs:dword_180016290
0x180007cb3  movaps  [rbp+420h+var_130], xmm0
0x180007cba  movups  xmm0, cs:DEVPKEY_PNPX_ModelName
0x180007cc1  mov     [rbp+420h+var_300], 100000h
0x180007ccb  mov     [rbp+420h+var_2C8], 30002h
0x180007cd5  movaps  [rbp+420h+var_110], xmm0
0x180007cdc  movups  xmm0, cs:DEVPKEY_PNPX_Manufacturer
0x180007ce3  mov     [rbp+420h+var_2A0], r10d
0x180007cea  movaps  [rbp+420h+var_2C0], xmm1
0x180007cf1  movaps  [rbp+420h+var_F0], xmm0
0x180007cf8  mov     [rbp+420h+var_29C], 14h
0x180007d02  movups  [rbp+420h+var_288], xmm1
0x180007d09  mov     [rbp+420h+var_274], 0
0x180007d13  mov     [rbp+420h+var_270], 0
0x180007d1e  mov     [rbp+420h+var_268], r10d
0x180007d25  mov     [rbp+420h+var_264], 8
0x180007d2f  movaps  [rbp+420h+var_250], xmm1
0x180007d36  mov     [rbp+420h+var_23C], r13d
0x180007d3d  mov     [rbp+420h+var_238], r13
0x180007d44  mov     [rbp+420h+var_230], r10d
0x180007d4b  mov     [rbp+420h+var_22C], r12d
0x180007d52  mov     [rbp+420h+var_228], r15
0x180007d59  mov     [rbp+420h+var_220], 2
0x180007d63  movups  [rbp+420h+var_218], xmm2
0x180007d6a  mov     [rbp+420h+var_208], ecx
0x180007d70  mov     [rbp+420h+var_204], r13d
0x180007d77  mov     [rbp+420h+var_200], r13
0x180007d7e  mov     [rbp+420h+var_1F8], 0Dh
0x180007d88  mov     [rbp+420h+var_1F4], esi
0x180007d8e  mov     [rbp+420h+var_1F0], rdi
0x180007d95  mov     [rbp+420h+var_1E8], r11d
0x180007d9c  mov     [rbp+420h+var_1E0], r13d
0x180007da3  movaps  [rbp+420h+var_1B0], xmm4
0x180007daa  mov     [rbp+420h+var_1A0], r8d
0x180007db1  mov     [rbp+420h+var_19C], r13d
0x180007db8  mov     [rbp+420h+var_198], r13
0x180007dbf  movaps  [rbp+420h+var_190], xmm3
0x180007dc6  mov     [rbp+420h+var_180], edx
0x180007dcc  mov     [rbp+420h+var_17C], r13d
0x180007dd3  mov     [rbp+420h+var_178], r13
0x180007dda  movaps  [rbp+420h+var_170], xmm2
0x180007de1  mov     [rbp+420h+var_160], ecx
0x180007de7  mov     [rbp+420h+var_15C], r13d
0x180007dee  mov     [rbp+420h+var_158], r13
0x180007df5  mov     [rbp+420h+var_13C], r13d
0x180007dfc  mov     [rbp+420h+var_138], r13
0x180007e03  mov     [rbp+420h+var_11C], r13d
0x180007e0a  mov     [rbp+420h+var_118], r13
0x180007e11  mov     [rbp+420h+var_100], eax
0x180007e17  mov     [rbp+420h+var_FC], r13d
0x180007e1e  mov     [rbp+420h+var_F8], r13
0x180007e25  movups  xmm0, cs:DEVPKEY_PNPX_DeviceCategory
0x180007e2c  mov     eax, cs:dword_1800162A8
0x180007e32  mov     [rbp+420h+var_E0], eax
0x180007e38  mov     eax, cs:dword_180016278
0x180007e3e  movaps  [rbp+420h+var_D0], xmm0
0x180007e45  movups  xmm0, xmmword ptr cs:DEVPKEY_DeviceContainer_Category.fmtid.Data1
0x180007e4c  mov     [rbp+420h+var_C0], eax
0x180007e52  mov     eax, cs:DEVPKEY_DeviceContainer_Category.pid
0x180007e58  movaps  [rbp+420h+var_B0], xmm0
0x180007e5f  movups  xmm0, cs:DEVPKEY_PNPX_IpAddress
0x180007e66  mov     [rbp+420h+var_A0], eax
0x180007e6c  mov     eax, cs:dword_180016260
0x180007e72  movaps  [rbp+420h+var_90], xmm0
0x180007e79  movups  xmm0, cs:DEVPKEY_PNPX_ID
0x180007e80  mov     [rbp+420h+var_80], eax
0x180007e86  mov     eax, cs:dword_1800162C0
0x180007e8c  movaps  [rbp+420h+var_70], xmm0
0x180007e93  movups  xmm0, cs:DEVPKEY_PNPX_Types
0x180007e9a  mov     [rbp+420h+var_60], eax
0x180007ea0  mov     eax, cs:dword_1800162D8
0x180007ea6  movaps  [rbp+420h+var_50], xmm0
0x180007ead  mov     [rbp+420h+var_DC], r13d
0x180007eb4  mov     [rbp+420h+var_D8], r13
0x180007ebb  mov     [rbp+420h+var_BC], r13d
0x180007ec2  mov     [rbp+420h+var_B8], r13
0x180007ec9  mov     [rbp+420h+var_9C], r13d
0x180007ed0  mov     [rbp+420h+var_98], r13
0x180007ed7  mov     [rbp+420h+var_7C], r13d
0x180007ede  mov     [rbp+420h+var_78], r13
0x180007ee5  mov     [rbp+420h+var_5C], r13d
0x180007eec  mov     [rbp+420h+var_58], r13
0x180007ef3  mov     [rbp+420h+var_40], eax
0x180007ef9  mov     [rbp+420h+var_3C], r13d
0x180007f00  mov     [rbp+420h+var_38], r13
0x180007f07  cmp     [rbx+8], r13d
0x180007f0b  jz      short loc_180007F26
0x180007f0d  lea     rsi, WPP_GLOBAL_Control
0x180007f14  cmp     r9, rsi
0x180007f17  jz      short loc_180007F4E
0x180007f19  test    byte ptr [r9+1Ch], 8
0x180007f1e  jz      short loc_180007F4E
0x180007f20  lea     edx, [r10+0Ch]
0x180007f24  jmp     short loc_180007F3E
0x180007f26  lea     rsi, WPP_GLOBAL_Control
0x180007f2d  cmp     r9, rsi
0x180007f30  jz      short loc_180007F4E
0x180007f32  test    byte ptr [r9+1Ch], 8
0x180007f37  jz      short loc_180007F4E
0x180007f39  mov     edx, 1Fh
0x180007f3e  mov     rcx, [r9+10h]
0x180007f42  lea     r8, WPP_7fef1fa79ee3391c6a163bc1b1bc3ea3_Traceguids
0x180007f49  call    WPP_SF_
0x180007f4e  mov     eax, [rbx+8]
0x180007f51  lea     rcx, [rbp+420h+var_300]
0x180007f58  test    eax, eax
0x180007f5a  mov     [rsp+520h+var_4E0], rbx
0x180007f5f  mov     [rsp+520h+var_4E8], rbx
0x180007f64  lea     rdx, [rsp+520h+var_4C0]
0x180007f69  cmovnz  rdx, rcx
0x180007f6d  lea     r9, [rbp+420h+var_1B0]
0x180007f74  neg     eax
0x180007f76  lea     rax, ?s_DevQueryCallback@CDeviceHandler@@CAXPEAUHDEVQUERY__@@PEAXPEBU_DEV_QUERY_RESULT_ACTION_DATA@@@Z; CDeviceHandler::s_DevQueryCallback(HDEVQUERY__ *,void *,_DEV_QUERY_RESULT_ACTION_DATA const *)
0x180007f7d  sbb     ecx, ecx
0x180007f7f  mov     [rsp+520h+var_4F0], rax
0x180007f84  and     ecx, 0FFFFFFFEh
0x180007f87  mov     [rsp+520h+var_4F8], rdx
0x180007f8c  add     ecx, 8
0x180007f8f  mov     [rsp+520h+var_500], ecx
0x180007f93  mov     ecx, 5
0x180007f98  mov     edx, ecx
0x180007f9a  lea     r8d, [rcx+7]
0x180007f9e  call    cs:__imp_DevCreateObjectQuery
0x180007fa4  mov     edi, eax
0x180007fa6  test    eax, eax
0x180007fa8  jns     short loc_180007FDA
0x180007faa  mov     rcx, cs:WPP_GLOBAL_Control
0x180007fb1  cmp     rcx, rsi
0x180007fb4  jz      short loc_180007FD2
0x180007fb6  test    byte ptr [rcx+1Ch], 2
0x180007fba  jz      short loc_180007FD2
0x180007fbc  mov     rcx, [rcx+10h]
0x180007fc0  lea     r8, WPP_7fef1fa79ee3391c6a163bc1b1bc3ea3_Traceguids
0x180007fc7  mov     edx, r12d
0x180007fca  mov     r9d, eax
0x180007fcd  call    WPP_SF_d
0x180007fd2  mov     rcx, rbx; this
0x180007fd5  call    ?StopDiscovery@CDeviceHandler@@QEAAXXZ; CDeviceHandler::StopDiscovery(void)
0x180007fda  mov     rcx, cs:WPP_GLOBAL_Control
0x180007fe1  cmp     rcx, rsi
0x180007fe4  jz      short loc_180008001
0x180007fe6  test    [rcx+1Ch], r12b
0x180007fea  jz      short loc_180008001
0x180007fec  mov     rcx, [rcx+10h]
0x180007ff0  lea     r8, WPP_7fef1fa79ee3391c6a163bc1b1bc3ea3_Traceguids
0x180007ff7  mov     edx, 21h ; '!'
0x180007ffc  call    WPP_SF_
0x180008001  mov     eax, edi
0x180008003  mov     rcx, [rbp+420h+var_30]
0x18000800a  xor     rcx, rsp; StackCookie
0x18000800d  call    __security_check_cookie
0x180008012  lea     r11, [rsp+520h+var_20]
0x18000801a  mov     rbx, [r11+38h]
0x18000801e  mov     rsi, [r11+40h]
0x180008022  mov     rsp, r11
0x180008025  pop     r15
0x180008027  pop     r13
0x180008029  pop     r12
0x18000802b  pop     rdi
0x18000802c  pop     rbp
0x18000802d  retn
```
