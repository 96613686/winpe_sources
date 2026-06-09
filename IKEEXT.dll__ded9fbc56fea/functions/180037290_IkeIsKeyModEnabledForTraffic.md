# IkeIsKeyModEnabledForTraffic

- ea: `0x180037290`
- end: `0x180037e82`
- name: `IkeIsKeyModEnabledForTraffic`
- size: `3058`
- prototype: ``
- caller_count: `5`
- callee_count: `10`
- tags: `registry_config, loader_planting`

## callers

- `0x180025110`
- `0x180040d70`
- `0x180046ab0`
- `0x18007660c`
- `0x1800e29fc`

## callees

- `0x1800145f8`
- `0x180014860`
- `0x18001c2d0`
- `0x180035234`
- `0x1800356c0`
- `0x180037290`
- `0x18004890c`
- `0x180050850`
- `0x18005bfa0`
- `0x18005c3d0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180037347`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003738e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800374b6`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180037534`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003757b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800376bc`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180037703`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800378a2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800378e9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180037a1d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180037a54`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180037abb`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180037b02`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180037c61`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180037c98`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180037cff`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180037d46`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180037347`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003738e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800374b6`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180037534`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003757b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800376bc`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180037703`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800378a2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800378e9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180037a1d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180037a54`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180037abb`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180037b02`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180037c61`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180037c98`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180037cff`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180037d46`
- `ntdll!EtwEventWriteTransfer` at `0x180037468`
- `ntdll!EtwEventWriteTransfer` at `0x180037662`
- `ntdll!EtwEventWriteTransfer` at `0x1800379c1`
- `ntdll!EtwEventWriteTransfer` at `0x180037c10`
- `ntdll!EtwEventWriteTransfer` at `0x180037e50`
- `ntdll!EtwEventWriteTransfer` at `0x180037468`
- `ntdll!EtwEventWriteTransfer` at `0x180037662`
- `ntdll!EtwEventWriteTransfer` at `0x1800379c1`
- `ntdll!EtwEventWriteTransfer` at `0x180037c10`
- `ntdll!EtwEventWriteTransfer` at `0x180037e50`

## pseudocode

```c
__int64 __fastcall IkeIsKeyModEnabledForTraffic(unsigned int a1, _BYTE *a2, __int64 a3, __int64 a4)
{
  __int64 v7; // rsi
  LPCRITICAL_SECTION v8; // rax
  DWORD LockSemaphore; // ecx
  __int64 *Value; // rax
  __int64 v11; // rcx
  DWORD v12; // ecx
  char *v13; // rax
  const WCHAR *v14; // rdx
  __int64 v15; // rax
  bool v16; // zf
  int v17; // eax
  _QWORD *v18; // rdi
  DWORD v19; // ecx
  __int64 *v20; // rax
  __int64 v21; // r14
  __int64 v22; // rdi
  __int64 KeyModString; // rbx
  __int64 v24; // rcx
  __int64 TlsPeerAddr; // rax
  LPCRITICAL_SECTION v26; // rax
  DWORD v27; // ecx
  __int64 *v28; // rax
  __int64 v29; // rcx
  DWORD v30; // ecx
  char *v31; // rax
  const WCHAR *v32; // rdx
  __int64 v33; // rax
  int v34; // eax
  LPCRITICAL_SECTION v35; // rax
  DWORD v36; // ecx
  __int64 *v37; // rax
  __int64 v38; // rcx
  DWORD v39; // ecx
  char *v40; // rax
  const WCHAR *v41; // rdx
  int v42; // esi
  __int64 MMPolicy; // rbx
  __int64 v44; // r8
  LPCRITICAL_SECTION v45; // rax
  DWORD v46; // ecx
  __int64 *v47; // rax
  __int64 v48; // rcx
  DWORD v49; // ecx
  char *v50; // rax
  const WCHAR *v51; // rdx
  __int64 v52; // rax
  int v53; // eax
  LPCRITICAL_SECTION v54; // rdx
  DWORD v55; // ecx
  LPVOID v56; // rax
  LPVOID v57; // rcx
  __int64 v58; // rbx
  DWORD v59; // ecx
  __int64 *v60; // rax
  __int64 v61; // r9
  __int64 v62; // rax
  __int64 v63; // r10
  int v64; // r9d
  LPCRITICAL_SECTION v65; // rax
  DWORD v66; // ecx
  __int64 *v67; // rax
  __int64 v68; // rcx
  DWORD v69; // ecx
  char *v70; // rax
  const WCHAR *v71; // rdx
  __int64 v72; // rax
  int v73; // eax
  const char *v74; // rax
  LPCRITICAL_SECTION v76; // rdx
  DWORD v77; // ecx
  LPVOID v78; // rax
  LPVOID v79; // rcx
  __int64 v80; // rbx
  DWORD v81; // ecx
  __int64 *v82; // rax
  __int64 v83; // r9
  __int64 v84; // rax
  __int64 v85; // r10
  int v86; // r9d
  LPCRITICAL_SECTION v87; // rax
  DWORD v88; // ecx
  __int64 *v89; // rax
  __int64 v90; // rcx
  DWORD v91; // ecx
  char *v92; // rax
  const WCHAR *v93; // rdx
  __int64 v94; // rax
  int v95; // eax
  const char *v96; // rax
  LPVOID lpMem; // [rsp+58h] [rbp-A8h] BYREF
  LPVOID v98; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID v99; // [rsp+68h] [rbp-98h] BYREF
  __int64 v100; // [rsp+70h] [rbp-90h] BYREF
  _OWORD v101[2]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v102; // [rsp+98h] [rbp-68h]
  int v103; // [rsp+A0h] [rbp-60h] BYREF
  int v104; // [rsp+A4h] [rbp-5Ch]
  __int64 v105; // [rsp+A8h] [rbp-58h]
  char *v106; // [rsp+B0h] [rbp-50h] BYREF
  int v107; // [rsp+B8h] [rbp-48h]
  int v108; // [rsp+BCh] [rbp-44h]
  char *v109; // [rsp+C0h] [rbp-40h]
  int v110; // [rsp+C8h] [rbp-38h]
  int v111; // [rsp+CCh] [rbp-34h]
  __int64 *v112; // [rsp+D0h] [rbp-30h]
  __int64 v113; // [rsp+D8h] [rbp-28h]
  const WCHAR *v114; // [rsp+E0h] [rbp-20h]
  int v115; // [rsp+E8h] [rbp-18h]
  int v116; // [rsp+ECh] [rbp-14h]
  const char *v117; // [rsp+F0h] [rbp-10h]
  __int64 v118; // [rsp+F8h] [rbp-8h]
  const char *v119; // [rsp+100h] [rbp+0h]
  __int64 v120; // [rsp+108h] [rbp+8h]

  lpMem = 0;
  v102 = 0;
  v98 = 0;
  v99 = 0;
  v7 = -1;
  memset(v101, 0, sizeof(v101));
  if ( (unsigned int)dword_180173278 <= 5 || (qword_180173288 & 1) == 0 || (qword_180173290 & 1) != qword_180173290 )
    goto LABEL_20;
  v8 = gIkeExtGlobals;
  if ( !gIkeExtGlobals )
    goto LABEL_9;
  LockSemaphore = (DWORD)gIkeExtGlobals[86].LockSemaphore;
  if ( LockSemaphore == -1 )
    goto LABEL_9;
  Value = (__int64 *)TlsGetValue(LockSemaphore);
  if ( !Value )
  {
    v8 = gIkeExtGlobals;
LABEL_9:
    v11 = 0;
    goto LABEL_10;
  }
  v11 = *Value;
  v8 = gIkeExtGlobals;
LABEL_10:
  v100 = v11;
  v112 = &v100;
  v113 = 8;
  if ( !v8 )
    goto LABEL_18;
  v12 = (DWORD)v8[86].LockSemaphore;
  if ( v12 == -1 )
    goto LABEL_18;
  v13 = (char *)TlsGetValue(v12);
  v14 = (const WCHAR *)(v13 + 8);
  if ( !v13 )
    v14 = 0;
  if ( v14 )
  {
    v15 = -1;
    do
      v16 = v14[++v15] == 0;
    while ( !v16 );
    v17 = 2 * v15 + 2;
  }
  else
  {
LABEL_18:
    v14 = &LocaleName;
    v17 = 2;
  }
  v115 = v17;
  v104 = 5;
  v106 = off_180173280;
  v114 = v14;
  v116 = 0;
  v117 = "IkeIsKeyModEnabledForTraffic";
  v118 = 29;
  v103 = 184549376;
  v105 = 1;
  v107 = *(unsigned __int16 *)off_180173280;
  v109 = (char *)&dword_180166EA4;
  v108 = 2;
  v110 = 45;
  v111 = 1;
  EtwEventWriteTransfer(qword_180173298, &v103, 0, 0, 5, &v106);
LABEL_20:
  if ( a1 == 1 && ((__int64)gIkeExtGlobals[50].LockSemaphore & 0x40) != 0 )
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v19 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
      if ( v19 == -1 || (v20 = (__int64 *)TlsGetValue(v19), v18 = WPP_GLOBAL_Control, !v20) )
        LODWORD(v21) = 0;
      else
        v21 = *v20;
      v22 = v18[2];
      KeyModString = IkeGetKeyModString(1, a2, a3, a4);
      TlsPeerAddr = IkeGetTlsPeerAddr(v24);
      WPP_SF_iSs(v22, 50, (unsigned int)WPP_15c4be3b741d37db00cbf381bc2eea53_Traceguids, v21, TlsPeerAddr, KeyModString);
    }
    if ( (unsigned int)dword_180173278 <= 4 )
    {
LABEL_47:
      if ( (unsigned int)dword_180173278 <= 5 || (qword_180173288 & 1) == 0 || (qword_180173290 & 1) != qword_180173290 )
        return 0;
      v35 = gIkeExtGlobals;
      if ( gIkeExtGlobals )
      {
        v36 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
        if ( v36 != -1 )
        {
          v37 = (__int64 *)TlsGetValue(v36);
          if ( v37 )
          {
            v38 = *v37;
            v35 = gIkeExtGlobals;
LABEL_56:
            v100 = v38;
            v112 = &v100;
            v113 = 8;
            if ( !v35 )
              goto LABEL_63;
            v39 = (DWORD)v35[86].LockSemaphore;
            if ( v39 == -1 )
              goto LABEL_63;
            v40 = (char *)TlsGetValue(v39);
            v41 = (const WCHAR *)(v40 + 8);
            if ( !v40 )
              v41 = 0;
            if ( v41 )
            {
              do
                v16 = v41[++v7] == 0;
              while ( !v16 );
              v42 = 2 * v7 + 2;
            }
            else
            {
LABEL_63:
              v41 = &LocaleName;
              v42 = 2;
            }
            v104 = 5;
            v106 = off_180173280;
            v114 = v41;
            v115 = v42;
            v116 = 0;
            v117 = "IkeIsKeyModEnabledForTraffic";
            v118 = 29;
            v103 = 184549376;
            v105 = 1;
            v107 = *(unsigned __int16 *)off_180173280;
            v109 = byte_180166E6B;
            v108 = 2;
            v110 = 45;
            v111 = 1;
            EtwEventWriteTransfer(qword_180173298, &v103, 0, 0, 5, &v106);
            return 0;
          }
          v35 = gIkeExtGlobals;
        }
      }
      v38 = 0;
      goto LABEL_56;
    }
    v26 = gIkeExtGlobals;
    if ( gIkeExtGlobals )
    {
      v27 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
      if ( v27 != -1 )
      {
        v28 = (__int64 *)TlsGetValue(v27);
        if ( v28 )
        {
          v29 = *v28;
          v26 = gIkeExtGlobals;
LABEL_37:
          v100 = v29;
          v112 = &v100;
          v113 = 8;
          if ( !v26 )
            goto LABEL_45;
          v30 = (DWORD)v26[86].LockSemaphore;
          if ( v30 == -1 )
            goto LABEL_45;
          v31 = (char *)TlsGetValue(v30);
          v32 = (const WCHAR *)(v31 + 8);
          if ( !v31 )
            v32 = 0;
          if ( v32 )
          {
            v33 = -1;
            do
              v16 = v32[++v33] == 0;
            while ( !v16 );
            v34 = 2 * v33 + 2;
          }
          else
          {
LABEL_45:
            v32 = &LocaleName;
            v34 = 2;
          }
          v115 = v34;
          v114 = v32;
          v117 = "keying module is not enabled for traffic";
          v104 = 4;
          v106 = off_180173280;
          v119 = "AUTHIP";
          v116 = 0;
          v118 = 41;
          v120 = 7;
          v103 = 184549376;
          v105 = 0;
          v107 = *(unsigned __int16 *)off_180173280;
          v109 = &byte_180159BFF;
          v108 = 2;
          v110 = 76;
          v111 = 1;
          EtwEventWriteTransfer(qword_180173298, &v103, 0, 0, 6, &v106);
          goto LABEL_47;
        }
        v26 = gIkeExtGlobals;
      }
    }
    v29 = 0;
    goto LABEL_37;
  }
  LODWORD(v101[0]) = a1;
  MMPolicy = IkeFindMMPolicy((_DWORD)a2, (unsigned int)v101, 1, 0, (__int64)&lpMem);
  if ( !MMPolicy && a3 )
    MMPolicy = IkeFindQMPolicy(0, a2, a3, 0, (__int64)v101, 0, 0, 1, &v98, &v99);
  IkeFreeMMPolicy(lpMem);
  IkeFreeQMExtPolicy(v98);
  IkeFreeUMPolicy(v99);
  if ( (unsigned int)dword_180173278 > 5 && (qword_180173288 & 1) != 0 && (qword_180173290 & 1) == qword_180173290 )
  {
    v45 = gIkeExtGlobals;
    if ( gIkeExtGlobals )
    {
      v46 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
      if ( v46 != -1 )
      {
        v47 = (__int64 *)TlsGetValue(v46);
        if ( v47 )
        {
          v48 = *v47;
          v45 = gIkeExtGlobals;
LABEL_77:
          v100 = v48;
          v112 = &v100;
          v113 = 8;
          if ( !v45 )
            goto LABEL_85;
          v49 = (DWORD)v45[86].LockSemaphore;
          if ( v49 == -1 )
            goto LABEL_85;
          v50 = (char *)TlsGetValue(v49);
          v51 = (const WCHAR *)(v50 + 8);
          if ( !v50 )
            v51 = 0;
          if ( v51 )
          {
            v52 = -1;
            do
              v16 = v51[++v52] == 0;
            while ( !v16 );
            v53 = 2 * v52 + 2;
          }
          else
          {
LABEL_85:
            v51 = &LocaleName;
            v53 = 2;
          }
          v115 = v53;
          v114 = v51;
          v117 = "IkeIsKeyModEnabledForTraffic";
          v104 = 5;
          v106 = off_180173280;
          v116 = 0;
          v118 = 29;
          v103 = 184549376;
          v105 = 1;
          v107 = *(unsigned __int16 *)off_180173280;
          v109 = byte_180166E6B;
          v108 = 2;
          v110 = 45;
          v111 = 1;
          EtwEventWriteTransfer(qword_180173298, &v103, 0, 0, 5, &v106);
          goto LABEL_87;
        }
        v45 = gIkeExtGlobals;
      }
    }
    v48 = 0;
    goto LABEL_77;
  }
LABEL_87:
  if ( MMPolicy )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v54 = gIkeExtGlobals;
      if ( !gIkeExtGlobals || (v55 = (DWORD)gIkeExtGlobals[86].LockSemaphore, v55 == -1) )
      {
        v57 = 0;
      }
      else
      {
        v56 = TlsGetValue(v55);
        v54 = gIkeExtGlobals;
        v57 = v56;
      }
      v58 = (__int64)v57 + 8;
      if ( !v57 )
        v58 = 0;
      if ( v54 && (v59 = (DWORD)v54[86].LockSemaphore, v59 != -1) && (v60 = (__int64 *)TlsGetValue(v59)) != 0 )
        v61 = *v60;
      else
        v61 = 0;
      v62 = IkeGetKeyModString(a1, v54, v44, v61);
      WPP_SF_iSs(
        *(_QWORD *)(v63 + 16),
        51,
        (unsigned int)WPP_15c4be3b741d37db00cbf381bc2eea53_Traceguids,
        v64,
        v58,
        v62);
    }
    if ( (unsigned int)dword_180173278 <= 4 )
      return 0;
    v65 = gIkeExtGlobals;
    if ( gIkeExtGlobals )
    {
      v66 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
      if ( v66 != -1 )
      {
        v67 = (__int64 *)TlsGetValue(v66);
        if ( v67 )
        {
          v68 = *v67;
          v65 = gIkeExtGlobals;
LABEL_110:
          v100 = v68;
          v112 = &v100;
          v113 = 8;
          if ( !v65 )
            goto LABEL_118;
          v69 = (DWORD)v65[86].LockSemaphore;
          if ( v69 == -1 )
            goto LABEL_118;
          v70 = (char *)TlsGetValue(v69);
          v71 = (const WCHAR *)(v70 + 8);
          if ( !v70 )
            v71 = 0;
          if ( v71 )
          {
            v72 = -1;
            do
              v16 = v71[++v72] == 0;
            while ( !v16 );
            v73 = 2 * v72 + 2;
          }
          else
          {
LABEL_118:
            v71 = &LocaleName;
            v73 = 2;
          }
          v115 = v73;
          v117 = "keying module is not enabled for traffic";
          v114 = v71;
          v116 = 0;
          v118 = 41;
          if ( a1 )
          {
            v74 = "IKEv2";
            if ( a1 != 2 )
              v74 = "AUTHIP";
          }
          else
          {
            v74 = "IKE";
          }
          do
            v16 = v74[++v7] == 0;
          while ( !v16 );
          v119 = v74;
          v120 = (unsigned int)(v7 + 1);
          v104 = 4;
          v106 = off_180173280;
          v103 = 184549376;
          v105 = 0;
          v107 = *(unsigned __int16 *)off_180173280;
          v109 = &byte_180159BA7;
          v108 = 2;
          v110 = 76;
          v111 = 1;
          EtwEventWriteTransfer(qword_180173298, &v103, 0, 0, 6, &v106);
          return 0;
        }
        v65 = gIkeExtGlobals;
      }
    }
    v68 = 0;
    goto LABEL_110;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v76 = gIkeExtGlobals;
    if ( !gIkeExtGlobals || (v77 = (DWORD)gIkeExtGlobals[86].LockSemaphore, v77 == -1) )
    {
      v79 = 0;
    }
    else
    {
      v78 = TlsGetValue(v77);
      v76 = gIkeExtGlobals;
      v79 = v78;
    }
    v80 = (__int64)v79 + 8;
    if ( !v79 )
      v80 = 0;
    if ( v76 && (v81 = (DWORD)v76[86].LockSemaphore, v81 != -1) && (v82 = (__int64 *)TlsGetValue(v81)) != 0 )
      v83 = *v82;
    else
      v83 = 0;
    v84 = IkeGetKeyModString(a1, v76, v44, v83);
    WPP_SF_iSs(*(_QWORD *)(v85 + 16), 52, (unsigned int)WPP_15c4be3b741d37db00cbf381bc2eea53_Traceguids, v86, v80, v84);
  }
  if ( (unsigned int)dword_180173278 > 4 )
  {
    v87 = gIkeExtGlobals;
    if ( gIkeExtGlobals )
    {
      v88 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
      if ( v88 != -1 )
      {
        v89 = (__int64 *)TlsGetValue(v88);
        if ( v89 )
        {
          v90 = *v89;
          v87 = gIkeExtGlobals;
LABEL_148:
          v100 = v90;
          v112 = &v100;
          v113 = 8;
          if ( !v87 )
            goto LABEL_156;
          v91 = (DWORD)v87[86].LockSemaphore;
          if ( v91 == -1 )
            goto LABEL_156;
          v92 = (char *)TlsGetValue(v91);
          v93 = (const WCHAR *)(v92 + 8);
          if ( !v92 )
            v93 = 0;
          if ( v93 )
          {
            v94 = -1;
            do
              v16 = v93[++v94] == 0;
            while ( !v16 );
            v95 = 2 * v94 + 2;
          }
          else
          {
LABEL_156:
            v93 = &LocaleName;
            v95 = 2;
          }
          v115 = v95;
          v117 = "keying module is enabled for traffic";
          v114 = v93;
          v116 = 0;
          v118 = 37;
          if ( a1 )
          {
            v96 = "IKEv2";
            if ( a1 != 2 )
              v96 = "AUTHIP";
          }
          else
          {
            v96 = "IKE";
          }
          do
            v16 = v96[++v7] == 0;
          while ( !v16 );
          v119 = v96;
          v120 = (unsigned int)(v7 + 1);
          v104 = 4;
          v106 = off_180173280;
          v103 = 184549376;
          v105 = 0;
          v107 = *(unsigned __int16 *)off_180173280;
          v109 = &byte_180159B07;
          v108 = 2;
          v110 = 75;
          v111 = 1;
          EtwEventWriteTransfer(qword_180173298, &v103, 0, 0, 6, &v106);
          return 1;
        }
        v87 = gIkeExtGlobals;
      }
    }
    v90 = 0;
    goto LABEL_148;
  }
  return 1;
}

```

## disassembly

```asm
0x180037290  mov     [rsp-8+arg_18], rbx
0x180037295  push    rbp
0x180037296  push    rsi
0x180037297  push    rdi
0x180037298  push    r12
0x18003729a  push    r13
0x18003729c  push    r14
0x18003729e  push    r15
0x1800372a0  lea     rbp, [rsp-20h]
0x1800372a5  sub     rsp, 120h
0x1800372ac  mov     rax, cs:__security_cookie
0x1800372b3  xor     rax, rsp
0x1800372b6  mov     [rbp+50h+var_40], rax
0x1800372ba  xor     r13d, r13d
0x1800372bd  lea     rbx, aIkeiskeymodena; "IkeIsKeyModEnabledForTraffic"
0x1800372c4  xor     eax, eax
0x1800372c6  mov     [rsp+150h+lpMem], r13
0x1800372cb  xorps   xmm0, xmm0
0x1800372ce  mov     [rbp+50h+var_B8], rax
0x1800372d2  mov     eax, cs:dword_180173278
0x1800372d8  lea     r12, _TraceLoggingMetadataEnd
0x1800372df  mov     [rsp+150h+var_F0], r13
0x1800372e4  mov     rdi, r8
0x1800372e7  mov     [rsp+150h+var_E8], r13
0x1800372ec  mov     r14, rdx
0x1800372ef  mov     r15d, ecx
0x1800372f2  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x1800372f9  movups  [rsp+150h+var_D8], xmm0
0x1800372fe  movups  [rbp+50h+var_C8], xmm0
0x180037302  cmp     eax, 5
0x180037305  jbe     loc_18003746E
0x18003730b  mov     rcx, cs:qword_180173290
0x180037312  mov     rax, cs:qword_180173288
0x180037319  test    al, 1
0x18003731b  jz      loc_18003746E
0x180037321  mov     rax, rcx
0x180037324  and     eax, 1
0x180037327  cmp     rax, rcx
0x18003732a  jnz     loc_18003746E
0x180037330  mov     rax, cs:gIkeExtGlobals
0x180037337  test    rax, rax
0x18003733a  jz      short loc_180037365
0x18003733c  mov     ecx, [rax+0D88h]; dwTlsIndex
0x180037342  cmp     ecx, 0FFFFFFFFh
0x180037345  jz      short loc_180037365
0x180037347  call    cs:__imp_TlsGetValue
0x18003734d  test    rax, rax
0x180037350  jz      short loc_18003735E
0x180037352  mov     rcx, [rax]
0x180037355  mov     rax, cs:gIkeExtGlobals
0x18003735c  jmp     short loc_180037368
0x18003735e  mov     rax, cs:gIkeExtGlobals
0x180037365  mov     rcx, r13
0x180037368  mov     [rsp+150h+var_E0], rcx
0x18003736d  lea     rcx, [rsp+150h+var_E0]
0x180037372  mov     [rbp+50h+var_80], rcx
0x180037376  mov     [rbp+50h+var_78], 8
0x18003737e  test    rax, rax
0x180037381  jz      short loc_1800373C5
0x180037383  mov     ecx, [rax+0D88h]; dwTlsIndex
0x180037389  cmp     ecx, 0FFFFFFFFh
0x18003738c  jz      short loc_1800373C5
0x18003738e  call    cs:__imp_TlsGetValue
0x180037394  test    rax, rax
0x180037397  lea     rdx, [rax+8]
0x18003739b  cmovz   rdx, r13
0x18003739f  test    rdx, rdx
0x1800373a2  jz      short loc_1800373C5
0x1800373a4  mov     rax, rsi
0x1800373a7  nop     word ptr [rax+rax+00000000h]
0x1800373b0  cmp     [rdx+rax*2+2], r13w
0x1800373b6  lea     rax, [rax+1]
0x1800373ba  jnz     short loc_1800373B0
0x1800373bc  lea     eax, ds:2[rax*2]
0x1800373c3  jmp     short loc_1800373D1
0x1800373c5  lea     rdx, LocaleName
0x1800373cc  mov     eax, 2
0x1800373d1  mov     [rbp+50h+var_68], eax
0x1800373d4  lea     rcx, _TraceLoggingMetadata
0x1800373db  movzx   eax, cs:word_180166E9A
0x1800373e2  xor     r9d, r9d
0x1800373e5  mov     [rbp+50h+var_AC], eax
0x1800373e8  xor     r8d, r8d
0x1800373eb  mov     rax, cs:off_180173280
0x1800373f2  mov     [rbp+50h+var_A0], rax
0x1800373f6  mov     [rbp+50h+var_70], rdx
0x1800373fa  lea     rdx, [rbp+50h+var_B0]
0x1800373fe  mov     [rbp+50h+var_64], r13d
0x180037402  mov     [rbp+50h+var_60], rbx
0x180037406  mov     [rbp+50h+var_58], 1Dh
0x18003740e  mov     [rbp+50h+var_B0], 0B000000h
0x180037415  mov     [rbp+50h+var_A8], 1
0x18003741d  movzx   eax, word ptr [rax]
0x180037420  mov     [rbp+50h+var_98], eax
0x180037423  lea     rax, dword_180166EA4
0x18003742a  mov     [rbp+50h+var_90], rax
0x18003742e  mov     rax, r12
0x180037431  sub     eax, ecx
0x180037433  mov     [rbp+50h+var_94], 2
0x18003743a  mov     [rbp+50h+var_88], 2Dh ; '-'
0x180037441  mov     [rbp+50h+var_84], 1
0x180037448  mov     [rsp+150h+var_100], eax
0x18003744c  mov     eax, [rsp+150h+var_100]
0x180037450  mov     rcx, cs:qword_180173298
0x180037457  lea     rax, [rbp+50h+var_A0]
0x18003745b  mov     [rsp+150h+var_128], rax
0x180037460  mov     dword ptr [rsp+150h+var_130], 5
0x180037468  call    cs:__imp_EtwEventWriteTransfer
0x18003746e  cmp     r15d, 1
0x180037472  jnz     loc_1800377C4
0x180037478  mov     rcx, cs:gIkeExtGlobals
0x18003747f  test    byte ptr [rcx+7E8h], 40h
0x180037486  jz      loc_1800377C4
0x18003748c  mov     rdi, cs:WPP_GLOBAL_Control
0x180037493  lea     rax, WPP_GLOBAL_Control
0x18003749a  cmp     rdi, rax
0x18003749d  jz      short loc_18003750E
0x18003749f  cmp     byte ptr [rdi+19h], 4
0x1800374a3  jb      short loc_18003750E
0x1800374a5  test    byte ptr [rdi+1Ch], 10h
0x1800374a9  jz      short loc_18003750E
0x1800374ab  mov     ecx, [rcx+0D88h]; dwTlsIndex
0x1800374b1  cmp     ecx, 0FFFFFFFFh
0x1800374b4  jz      short loc_1800374CD
0x1800374b6  call    cs:__imp_TlsGetValue
0x1800374bc  mov     rdi, cs:WPP_GLOBAL_Control
0x1800374c3  test    rax, rax
0x1800374c6  jz      short loc_1800374CD
0x1800374c8  mov     r14, [rax]
0x1800374cb  jmp     short loc_1800374D0
0x1800374cd  mov     r14, r13
0x1800374d0  mov     rdi, [rdi+10h]
0x1800374d4  mov     ecx, 1
0x1800374d9  call    IkeGetKeyModString
0x1800374de  mov     rbx, rax
0x1800374e1  call    IkeGetTlsPeerAddr
0x1800374e6  mov     edx, 32h ; '2'
0x1800374eb  mov     [rsp+150h+var_128], rbx
0x1800374f0  mov     r9, r14
0x1800374f3  mov     [rsp+150h+var_130], rax
0x1800374f8  lea     r8, WPP_15c4be3b741d37db00cbf381bc2eea53_Traceguids
0x1800374ff  mov     rcx, rdi
0x180037502  call    WPP_SF_iSs
0x180037507  lea     rbx, aIkeiskeymodena; "IkeIsKeyModEnabledForTraffic"
0x18003750e  mov     eax, cs:dword_180173278
0x180037514  cmp     eax, 4
0x180037517  jbe     loc_18003766A
0x18003751d  mov     rax, cs:gIkeExtGlobals
0x180037524  test    rax, rax
0x180037527  jz      short loc_180037552
0x180037529  mov     ecx, [rax+0D88h]; dwTlsIndex
0x18003752f  cmp     ecx, 0FFFFFFFFh
0x180037532  jz      short loc_180037552
0x180037534  call    cs:__imp_TlsGetValue
0x18003753a  test    rax, rax
0x18003753d  jz      short loc_18003754B
0x18003753f  mov     rcx, [rax]
0x180037542  mov     rax, cs:gIkeExtGlobals
0x180037549  jmp     short loc_180037555
0x18003754b  mov     rax, cs:gIkeExtGlobals
0x180037552  mov     rcx, r13
0x180037555  mov     [rsp+150h+var_E0], rcx
0x18003755a  lea     rcx, [rsp+150h+var_E0]
0x18003755f  mov     [rbp+50h+var_80], rcx
0x180037563  mov     [rbp+50h+var_78], 8
0x18003756b  test    rax, rax
0x18003756e  jz      short loc_1800375A9
0x180037570  mov     ecx, [rax+0D88h]; dwTlsIndex
0x180037576  cmp     ecx, 0FFFFFFFFh
0x180037579  jz      short loc_1800375A9
0x18003757b  call    cs:__imp_TlsGetValue
0x180037581  test    rax, rax
0x180037584  lea     rdx, [rax+8]
0x180037588  cmovz   rdx, r13
0x18003758c  test    rdx, rdx
0x18003758f  jz      short loc_1800375A9
0x180037591  mov     rax, rsi
0x180037594  cmp     [rdx+rax*2+2], r13w
0x18003759a  lea     rax, [rax+1]
0x18003759e  jnz     short loc_180037594
0x1800375a0  lea     eax, ds:2[rax*2]
0x1800375a7  jmp     short loc_1800375B5
0x1800375a9  lea     rdx, LocaleName
0x1800375b0  mov     eax, 2
0x1800375b5  mov     [rbp+50h+var_68], eax
0x1800375b8  lea     rcx, aAuthip_0; "AUTHIP"
0x1800375bf  mov     [rbp+50h+var_70], rdx
0x1800375c3  lea     rax, aKeyingModuleIs; "keying module is not enabled for traffi"...
0x1800375ca  mov     [rbp+50h+var_60], rax
0x1800375ce  lea     rdi, _TraceLoggingMetadata
0x1800375d5  movzx   eax, cs:word_180159BF5
0x1800375dc  lea     rdx, [rbp+50h+var_B0]
0x1800375e0  mov     [rbp+50h+var_AC], eax
0x1800375e3  xor     r9d, r9d
0x1800375e6  mov     rax, cs:off_180173280
0x1800375ed  xor     r8d, r8d
0x1800375f0  mov     [rbp+50h+var_A0], rax
0x1800375f4  mov     [rbp+50h+var_50], rcx
0x1800375f8  mov     [rbp+50h+var_64], r13d
0x1800375fc  mov     [rbp+50h+var_58], 29h ; ')'
0x180037604  mov     [rbp+50h+var_48], 7
0x18003760c  mov     [rbp+50h+var_B0], 0B000000h
0x180037613  mov     [rbp+50h+var_A8], r13
0x180037617  movzx   eax, word ptr [rax]
0x18003761a  mov     [rbp+50h+var_98], eax
0x18003761d  lea     rax, byte_180159BFF
0x180037624  mov     [rbp+50h+var_90], rax
0x180037628  mov     rax, r12
0x18003762b  sub     eax, edi
0x18003762d  mov     [rbp+50h+var_94], 2
0x180037634  mov     [rbp+50h+var_88], 4Ch ; 'L'
0x18003763b  mov     [rbp+50h+var_84], 1
0x180037642  mov     [rsp+150h+var_100], eax
0x180037646  mov     eax, [rsp+150h+var_100]
0x18003764a  mov     rcx, cs:qword_180173298
0x180037651  lea     rax, [rbp+50h+var_A0]
0x180037655  mov     [rsp+150h+var_128], rax
0x18003765a  mov     dword ptr [rsp+150h+var_130], 6
0x180037662  call    cs:__imp_EtwEventWriteTransfer
0x180037668  jmp     short loc_180037671
0x18003766a  lea     rdi, _TraceLoggingMetadata
0x180037671  mov     eax, cs:dword_180173278
0x180037677  cmp     eax, 5
0x18003767a  jbe     loc_180037C16
0x180037680  mov     rcx, cs:qword_180173290
0x180037687  mov     rax, cs:qword_180173288
0x18003768e  test    al, 1
0x180037690  jz      loc_180037C16
0x180037696  mov     rax, rcx
0x180037699  and     eax, 1
0x18003769c  cmp     rax, rcx
0x18003769f  jnz     loc_180037C16
0x1800376a5  mov     rax, cs:gIkeExtGlobals
0x1800376ac  test    rax, rax
0x1800376af  jz      short loc_1800376DA
0x1800376b1  mov     ecx, [rax+0D88h]; dwTlsIndex
0x1800376b7  cmp     ecx, 0FFFFFFFFh
0x1800376ba  jz      short loc_1800376DA
0x1800376bc  call    cs:__imp_TlsGetValue
0x1800376c2  test    rax, rax
0x1800376c5  jz      short loc_1800376D3
0x1800376c7  mov     rcx, [rax]
0x1800376ca  mov     rax, cs:gIkeExtGlobals
0x1800376d1  jmp     short loc_1800376DD
0x1800376d3  mov     rax, cs:gIkeExtGlobals
0x1800376da  mov     rcx, r13
0x1800376dd  mov     [rsp+150h+var_E0], rcx
0x1800376e2  lea     rcx, [rsp+150h+var_E0]
0x1800376e7  mov     [rbp+50h+var_80], rcx
0x1800376eb  mov     [rbp+50h+var_78], 8
0x1800376f3  test    rax, rax
0x1800376f6  jz      short loc_180037735
0x1800376f8  mov     ecx, [rax+0D88h]; dwTlsIndex
0x1800376fe  cmp     ecx, 0FFFFFFFFh
0x180037701  jz      short loc_180037735
0x180037703  call    cs:__imp_TlsGetValue
0x180037709  test    rax, rax
0x18003770c  lea     rdx, [rax+8]
0x180037710  cmovz   rdx, r13
0x180037714  test    rdx, rdx
0x180037717  jz      short loc_180037735
0x180037719  nop     dword ptr [rax+00000000h]
0x180037720  cmp     [rdx+rsi*2+2], r13w
0x180037726  lea     rsi, [rsi+1]
0x18003772a  jnz     short loc_180037720
0x18003772c  lea     esi, ds:2[rsi*2]
0x180037733  jmp     short loc_180037741
0x180037735  lea     rdx, LocaleName
0x18003773c  mov     esi, 2
0x180037741  movzx   eax, cs:word_180166E61
0x180037748  sub     r12d, edi
0x18003774b  mov     [rbp+50h+var_AC], eax
0x18003774e  mov     rax, cs:off_180173280
0x180037755  mov     [rbp+50h+var_A0], rax
0x180037759  mov     [rbp+50h+var_70], rdx
0x18003775d  mov     [rbp+50h+var_68], esi
0x180037760  mov     [rbp+50h+var_64], r13d
0x180037764  mov     [rbp+50h+var_60], rbx
0x180037768  mov     [rbp+50h+var_58], 1Dh
0x180037770  mov     [rbp+50h+var_B0], 0B000000h
0x180037777  mov     [rbp+50h+var_A8], 1
0x18003777f  movzx   eax, word ptr [rax]
0x180037782  mov     [rbp+50h+var_98], eax
0x180037785  lea     rax, byte_180166E6B
0x18003778c  mov     [rbp+50h+var_90], rax
0x180037790  mov     [rbp+50h+var_94], 2
0x180037797  mov     [rbp+50h+var_88], 2Dh ; '-'
0x18003779e  mov     [rbp+50h+var_84], 1
0x1800377a5  mov     [rsp+150h+var_100], r12d
0x1800377aa  mov     eax, [rsp+150h+var_100]
0x1800377ae  lea     rax, [rbp+50h+var_A0]
0x1800377b2  mov     [rsp+150h+var_128], rax
0x1800377b7  mov     dword ptr [rsp+150h+var_130], 5
0x1800377bf  jmp     loc_180037BFF
0x1800377c4  lea     rax, [rsp+150h+lpMem]
0x1800377c9  mov     dword ptr [rsp+150h+var_D8], r15d
0x1800377ce  xor     r9d, r9d
0x1800377d1  mov     [rsp+150h+var_130], rax
0x1800377d6  mov     r8d, 1
0x1800377dc  lea     rdx, [rsp+150h+var_D8]
  ... truncated ...
```
