# GetExtensibleContainersList(ushort const *,HKEY__ *,_URLCACHE_EXTENSIBLE_CONTAINER * *,ulong *)

- ea: `0x180026820`
- end: `0x180027b0d`
- name: `?GetExtensibleContainersList@@YAJPEBGPEAUHKEY__@@PEAPEAU_URLCACHE_EXTENSIBLE_CONTAINER@@PEAK@Z`
- size: `4845`
- prototype: `__int64 __fastcall(const unsigned __int16 *, HKEY, struct _URLCACHE_EXTENSIBLE_CONTAINER **, unsigned int *)`
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180117300`

## callees

- `0x18001bbbc`
- `0x180020468`
- `0x18002086c`
- `0x180025910`
- `0x180025980`
- `0x180026820`
- `0x180027ec0`
- `0x180044a44`
- `0x180046a1c`
- `0x1801003fc`
- `0x180110154`
- `0x180127544`
- `0x180132988`
- `0x180148b48`
- `0x18014a7a0`
- `0x18014b3b4`
- `0x180154882`
- `0x1801dd240`
- `0x1801e1790`
- `0x1801e3348`
- `0x1801ee010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800279b5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800279b5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800275df`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800275df`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180026942`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180026942`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180026a50`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180026c73`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180026df9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800276fa`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180026a50`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180026c73`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180026df9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800276fa`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x180027655`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x180027655`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180026bd2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180026d57`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180026eda`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180027044`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180027084`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800270c4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180027104`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180026bd2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180026d57`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180026eda`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180027044`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180027084`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800270c4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180027104`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800269ab`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800269ab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026b00`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026b7b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800275bf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026b00`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026b7b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800275bf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026b3d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026b3d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180027902`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180027998`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180027902`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180027998`
- `RPCRT4!RpcRevertToSelf` at `0x1800275cd`
- `RPCRT4!RpcRevertToSelf` at `0x180027709`
- `RPCRT4!RpcRevertToSelf` at `0x1800275cd`
- `RPCRT4!RpcRevertToSelf` at `0x180027709`

## string_xrefs

- `0x180026d30`: `CachePath`
- `0x180027a20`: `CachePath`
- `0x180026bab`: `CachePrefix`
- `0x180027062`: `CacheOptions`
- `0x180026eb3`: `CacheRelativePath`
- `0x1800279f5`: `CacheRelativePath`
- `0x180027018`: `CacheLimit`
- `0x180027982`: `CacheLimit`
- `0x1800270e2`: `CacheRepair`
- `0x1800278ec`: `CacheRepair`

## pseudocode

```c
__int64 __fastcall GetExtensibleContainersList(
        const unsigned __int16 *a1,
        HKEY a2,
        struct _URLCACHE_EXTENSIBLE_CONTAINER **a3,
        unsigned int *a4)
{
  int v6; // r15d
  const WCHAR *v8; // r13
  __int64 v9; // rax
  signed int v10; // esi
  int v11; // ebx
  unsigned int v12; // r12d
  __int64 v13; // r14
  DWORD v14; // ecx
  int v15; // r13d
  LSTATUS v16; // eax
  int v17; // edx
  int v18; // r8d
  __int64 v19; // r12
  unsigned int v20; // r13d
  unsigned int v21; // ecx
  int v22; // eax
  int v23; // ecx
  int v24; // r15d
  __int64 v25; // rcx
  WCHAR *v26; // rax
  WCHAR *v27; // rsi
  HKEY v28; // r14
  size_t v29; // rdi
  const WCHAR *v30; // r15
  WCHAR *v31; // rsi
  int v32; // ecx
  LSTATUS v33; // eax
  HKEY v34; // rcx
  int v35; // r15d
  const WCHAR *v36; // rdi
  LSTATUS ValueW; // eax
  __int64 v38; // r12
  unsigned int v39; // r13d
  unsigned int v40; // ecx
  int v41; // eax
  int v42; // ecx
  int v43; // r15d
  __int64 v44; // rcx
  WCHAR *v45; // rax
  WCHAR *v46; // rsi
  const WCHAR *v47; // r14
  const WCHAR *v48; // rdx
  size_t v49; // rdi
  WCHAR *v50; // rsi
  __int64 v51; // rax
  unsigned int v52; // edi
  BYTE *v53; // r14
  LSTATUS v54; // eax
  __int64 v55; // r12
  int v56; // r13d
  unsigned int v57; // ecx
  int v58; // eax
  int v59; // ecx
  int v60; // r15d
  __int64 v61; // rcx
  BYTE *v62; // rax
  BYTE *v63; // rsi
  size_t v64; // rdi
  BYTE *v65; // rdi
  BYTE *v66; // rsi
  unsigned int v67; // edi
  BYTE *v68; // r15
  LSTATUS v69; // eax
  __int64 v70; // r12
  unsigned int v71; // r13d
  __int64 v72; // rcx
  int v73; // eax
  int v74; // edx
  int v75; // r15d
  BYTE *Heap; // rax
  BYTE *v77; // rsi
  BYTE *v78; // r14
  size_t v79; // rdi
  BYTE *v80; // rsi
  LSTATUS v81; // eax
  LSTATUS v82; // eax
  LSTATUS v83; // eax
  LSTATUS v84; // eax
  const unsigned __int16 *v85; // rcx
  BYTE *v86; // r14
  BOOL v87; // r10d
  __int64 i; // rcx
  __int64 v89; // rdx
  __int64 v90; // rax
  unsigned int v91; // r12d
  __int64 v92; // r8
  __int64 v93; // r9
  _WORD *v94; // rdx
  int v95; // ecx
  __int64 v96; // rax
  unsigned int v97; // ecx
  __int64 v98; // rax
  __int64 v99; // rcx
  int v100; // eax
  __int64 v101; // rcx
  int v102; // r11d
  int v103; // edi
  BYTE *v104; // rax
  const WCHAR *v105; // rcx
  unsigned int j; // r15d
  size_t v107; // rdi
  BYTE *v108; // rsi
  BYTE *v109; // rdi
  int v110; // esi
  char *v111; // rdx
  void *v112; // rax
  void *v113; // rax
  BYTE *v114; // rax
  __int64 v115; // rax
  LPVOID v116; // rdi
  unsigned int v118; // edi
  void *v119; // rax
  struct _URLCACHE_EXTENSIBLE_CONTAINER *v120; // rax
  LSTATUS v121; // eax
  __int64 v122; // rdi
  unsigned __int16 v123; // dx
  int v124; // r9d
  unsigned int v125; // edi
  char *v126; // rbx
  unsigned int v127; // [rsp+40h] [rbp-C0h]
  DWORD v128; // [rsp+48h] [rbp-B8h]
  void *v129; // [rsp+58h] [rbp-A8h] BYREF
  BYTE *v130; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v131; // [rsp+68h] [rbp-98h]
  LPVOID lpMem; // [rsp+70h] [rbp-90h] BYREF
  __int64 v133; // [rsp+78h] [rbp-88h]
  int v134; // [rsp+80h] [rbp-80h] BYREF
  BYTE *lpData; // [rsp+88h] [rbp-78h] BYREF
  __int64 v136; // [rsp+90h] [rbp-70h]
  __int64 v137; // [rsp+98h] [rbp-68h]
  void *Src; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v139; // [rsp+A8h] [rbp-58h]
  void *v140; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v141; // [rsp+B8h] [rbp-48h]
  int v142; // [rsp+C0h] [rbp-40h]
  HKEY hKey; // [rsp+C8h] [rbp-38h]
  const unsigned __int16 *v144; // [rsp+D0h] [rbp-30h]
  __int64 v145; // [rsp+D8h] [rbp-28h]
  struct _URLCACHE_EXTENSIBLE_CONTAINER **v146; // [rsp+E0h] [rbp-20h]
  unsigned int *v147; // [rsp+E8h] [rbp-18h]
  _QWORD v148[2]; // [rsp+F0h] [rbp-10h]
  __int128 v149; // [rsp+100h] [rbp+0h]
  __int128 v150; // [rsp+110h] [rbp+10h]
  __int128 v151; // [rsp+120h] [rbp+20h]
  __int128 v152; // [rsp+130h] [rbp+30h]
  DWORD cchName; // [rsp+140h] [rbp+40h] BYREF
  HKEY hkey; // [rsp+148h] [rbp+48h] BYREF
  unsigned int pvData; // [rsp+150h] [rbp+50h] BYREF
  BYTE Data[4]; // [rsp+154h] [rbp+54h] BYREF
  int v157; // [rsp+158h] [rbp+58h] BYREF
  HKEY phkResult; // [rsp+160h] [rbp+60h] BYREF
  int v159; // [rsp+168h] [rbp+68h] BYREF
  int v160; // [rsp+16Ch] [rbp+6Ch] BYREF
  _OWORD v161[2]; // [rsp+170h] [rbp+70h] BYREF
  __int64 v162; // [rsp+190h] [rbp+90h]
  _DWORD v163[20]; // [rsp+1A0h] [rbp+A0h] BYREF
  void *v164[20]; // [rsp+1F0h] [rbp+F0h] BYREF
  WCHAR Name[264]; // [rsp+290h] [rbp+190h] BYREF

  v146 = a3;
  hKey = a2;
  v144 = a1;
  hkey = 0;
  v147 = a4;
  v6 = 0;
  memset_0(Name, 0, 0x208u);
  cchName = 0;
  v8 = &::Data;
  Src = (void *)&::Data;
  v140 = (void *)&::Data;
  v130 = (BYTE *)&::Data;
  lpData = (BYTE *)&::Data;
  v139 = 0;
  v141 = 0;
  v131 = 0;
  v136 = 0;
  pvData = 0;
  *(_DWORD *)Data = 0;
  v157 = 0;
  v159 = 0;
  lpMem = 0;
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_Sqq(
      1036,
      14,
      (unsigned int)&WPP_1af76d9ad7163b4b1c76b77142f1718e_Traceguids,
      (_DWORD)a1,
      (__int64)a3,
      (__int64)a4);
  if ( a3 )
    *a3 = 0;
  if ( a4 )
    *a4 = 0;
  v9 = -1;
  do
    ++v9;
  while ( a1[v9] );
  v145 = v9;
  HIDWORD(v137) = 0;
  v134 = 0;
  v10 = WxRpcImpersonateNonElevatedCaller(&v134);
  if ( v10 < 0 )
  {
    HIDWORD(v137) = 1117;
    v11 = 0;
    goto LABEL_215;
  }
  v11 = v134;
  v12 = 0;
  v127 = 0;
  v142 = 0;
  AcquireSRWLockShared(&g_srwExtensibleContainerConfig);
  v6 = 1;
  LODWORD(v13) = v139;
  v14 = 0;
  v137 = (unsigned int)v141;
  v133 = (unsigned int)v139;
  while ( 1 )
  {
    v128 = v14;
    if ( (_DWORD)v13 )
    {
      LODWORD(v13) = 0;
      LODWORD(v139) = 0;
      v133 = 0;
      *v8 = 0;
    }
    v15 = 0;
    cchName = 260;
    v16 = RegEnumKeyExW(hKey, v14, Name, &cchName, 0, 0, 0, 0);
    v10 = v16;
    if ( v16 == 259 )
    {
      if ( v11 )
      {
        RpcRevertToSelf();
        v11 = 0;
      }
      v120 = (struct _URLCACHE_EXTENSIBLE_CONTAINER *)lpMem;
      v10 = 0;
      lpMem = 0;
      *v146 = v120;
      *v147 = v12;
      goto LABEL_215;
    }
    if ( v16 > 0 )
      v10 = (unsigned __int16)v16 | 0x80070000;
    if ( v10 < 0 )
      goto LABEL_178;
    v19 = -1;
    do
      ++v19;
    while ( Name[v19] );
    if ( (_DWORD)v19 )
    {
      v20 = v19 + v13;
      if ( HIDWORD(v139) >= (unsigned int)(v19 + v13 + 1) )
      {
        v30 = (const WCHAR *)Src;
      }
      else
      {
        v21 = v19 + v13 + 3;
        v22 = 256;
        if ( v21 > 0x100 )
        {
          if ( v21 > 0x400 )
          {
            v22 = 4096;
            if ( v21 <= 0x1000 )
              v22 = 1024;
          }
        }
        else
        {
          v22 = 64;
        }
        v23 = -v22 & (v22 + v19 + v13 + 2);
        v24 = v23 - 1;
        if ( (unsigned int)(v23 - 1) > 0xFFFFFFE )
        {
          v10 = -2147024809;
          goto LABEL_176;
        }
        v25 = (unsigned int)(2 * v23);
        HIDWORD(v129) = 0;
        if ( g_fWxHeapExtensionInitialized )
          v26 = (WCHAR *)((__int64 (__fastcall *)(__int64))qword_180268420)(v25);
        else
          v26 = (WCHAR *)HeapAlloc(g_hWxProcessHeap, 0, (unsigned int)v25);
        v27 = v26;
        if ( !v26 )
        {
          HIDWORD(v129) = 52;
          v10 = -2147024882;
          goto LABEL_176;
        }
        v28 = (HKEY)Src;
        *v26 = 0;
        v29 = (unsigned int)v133;
        memcpy_0(v26, v28, v29 * 2);
        HIDWORD(v139) = v24;
        v27[v29] = 0;
        v30 = v27;
        Src = v27;
        if ( v28 )
        {
          phkResult = v28;
          if ( v28 != (HKEY)&::Data )
            WxFreeHeapEx(&phkResult);
        }
      }
      v31 = (WCHAR *)&v30[(unsigned int)v133];
      memcpy_0(v31, Name, 2LL * (unsigned int)v19);
      LODWORD(v139) = v20;
      v13 = v20;
      v31[(unsigned int)v19] = 0;
      v15 = 0;
      v133 = v13;
    }
    else
    {
      v30 = (const WCHAR *)Src;
    }
    v32 = (int)hkey;
    if ( hkey )
    {
      RegCloseKey(hkey);
      hkey = 0;
    }
    HIDWORD(v129) = 0;
    phkResult = 0;
    if ( (BYTE3(xmmword_180266B60) & 0x20) != 0 )
      WPP_SF_qSDlq(v32, v17, v18, (_DWORD)hKey, (__int64)v30, 15, 0, (__int64)&hkey);
    hkey = 0;
    v33 = RegOpenKeyExW(hKey, v30, 0, 0xFu, &phkResult);
    v10 = v33;
    if ( v33 > 0 )
      v10 = (unsigned __int16)v33 | 0x80070000;
    if ( v10 < 0 )
    {
      v34 = phkResult;
      HIDWORD(v129) = 680;
    }
    else
    {
      v34 = 0;
      hkey = phkResult;
      phkResult = 0;
    }
    if ( (BYTE3(xmmword_180266B60) & 0x20) != 0 )
    {
      WPP_SF_d(1053, 11, &WPP_b64a873b5a0a3123360afb44b8058dda_Traceguids, (unsigned int)v10);
      v34 = phkResult;
    }
    if ( v34 )
    {
      RegCloseKey(v34);
      phkResult = 0;
    }
    if ( v10 < 0 )
      goto LABEL_176;
    v35 = v137;
    v36 = (const WCHAR *)v140;
    if ( (_DWORD)v137 )
    {
      v35 = 0;
      LODWORD(v141) = 0;
      v137 = 0;
      *(_WORD *)v140 = 0;
    }
    cchName = 520;
    ValueW = RegGetValueW(hkey, 0, L"CachePrefix", 2u, 0, Name, &cchName);
    v10 = ValueW;
    if ( ValueW == 2 )
      goto LABEL_256;
    if ( ValueW > 0 )
      v10 = (unsigned __int16)ValueW | 0x80070000;
    if ( v10 < 0 )
      goto LABEL_176;
    v38 = -1;
    do
      ++v38;
    while ( Name[v38] );
    if ( (_DWORD)v38 )
    {
      v39 = v38 + v35;
      if ( HIDWORD(v141) < (unsigned int)(v38 + v35 + 1) )
      {
        v40 = v38 + v35 + 3;
        v41 = 256;
        if ( v40 > 0x100 )
        {
          if ( v40 > 0x400 )
          {
            v41 = 4096;
            if ( v40 <= 0x1000 )
              v41 = 1024;
          }
        }
        else
        {
          v41 = 64;
        }
        v42 = -v41 & (v41 + v38 + v35 + 2);
        v43 = v42 - 1;
        if ( (unsigned int)(v42 - 1) > 0xFFFFFFE )
        {
          v10 = -2147024809;
          goto LABEL_176;
        }
        v44 = (unsigned int)(2 * v42);
        HIDWORD(v129) = 0;
        if ( g_fWxHeapExtensionInitialized )
          v45 = (WCHAR *)((__int64 (__fastcall *)(__int64))qword_180268420)(v44);
        else
          v45 = (WCHAR *)HeapAlloc(g_hWxProcessHeap, 0, (unsigned int)v44);
        v46 = v45;
        if ( !v45 )
        {
          HIDWORD(v129) = 52;
          v10 = -2147024882;
          goto LABEL_176;
        }
        *v45 = 0;
        v47 = v36;
        v48 = v36;
        v49 = (unsigned int)v137;
        memcpy_0(v45, v48, v49 * 2);
        HIDWORD(v141) = v43;
        v46[v49] = 0;
        v36 = v46;
        v140 = v46;
        if ( v47 )
        {
          v129 = (void *)v47;
          if ( v47 != &::Data )
            WxFreeHeapEx(&v129);
        }
      }
      v50 = (WCHAR *)&v36[(unsigned int)v137];
      memcpy_0(v50, Name, 2LL * (unsigned int)v38);
      v51 = v39;
      v50[(unsigned int)v38] = 0;
      v15 = 0;
      v137 = v51;
      LODWORD(v141) = v51;
    }
    v52 = v131;
    v53 = v130;
    if ( (_DWORD)v131 )
    {
      v52 = 0;
      LODWORD(v131) = 0;
      *(_WORD *)v130 = 0;
    }
    cchName = 520;
    v54 = RegGetValueW(hkey, 0, L"CachePath", 2u, 0, Name, &cchName);
    v10 = v54;
    if ( v54 == 2 )
    {
      LODWORD(v13) = v133;
LABEL_256:
      v6 = 1;
LABEL_165:
      v12 = v127;
      goto LABEL_157;
    }
    if ( v54 > 0 )
      v10 = (unsigned __int16)v54 | 0x80070000;
    if ( v10 < 0 )
      goto LABEL_176;
    v55 = -1;
    do
      ++v55;
    while ( Name[v55] );
    if ( (_DWORD)v55 )
    {
      v56 = v55 + v52;
      if ( HIDWORD(v131) >= (unsigned int)v55 + v52 + 1 )
      {
        v65 = v130;
      }
      else
      {
        v57 = v55 + v52 + 3;
        v58 = 256;
        if ( v57 > 0x100 )
        {
          if ( v57 > 0x400 )
          {
            v58 = 4096;
            if ( v57 <= 0x1000 )
              v58 = 1024;
          }
        }
        else
        {
          v58 = 64;
        }
        v59 = -v58 & (v58 + v55 + v52 + 2);
        v60 = v59 - 1;
        if ( (unsigned int)(v59 - 1) > 0xFFFFFFE )
        {
          v10 = -2147024809;
          goto LABEL_176;
        }
        v61 = (unsigned int)(2 * v59);
        HIDWORD(v129) = 0;
        if ( g_fWxHeapExtensionInitialized )
          v62 = (BYTE *)((__int64 (__fastcall *)(__int64))qword_180268420)(v61);
        else
          v62 = (BYTE *)HeapAlloc(g_hWxProcessHeap, 0, (unsigned int)v61);
        v63 = v62;
        if ( !v62 )
        {
          HIDWORD(v129) = 52;
          v10 = -2147024882;
          goto LABEL_176;
        }
        *(_WORD *)v62 = 0;
        v64 = 2LL * v52;
        memcpy_0(v62, v53, v64);
        HIDWORD(v131) = v60;
        *(_WORD *)&v63[v64] = 0;
        v65 = v63;
        v130 = v63;
        if ( v53 )
        {
          v129 = v53;
          if ( v53 != (BYTE *)&::Data )
            WxFreeHeapEx(&v129);
        }
      }
      v66 = &v65[2 * (unsigned int)v131];
      memcpy_0(v66, Name, 2LL * (unsigned int)v55);
      LODWORD(v131) = v56;
      *(_WORD *)&v66[2 * (unsigned int)v55] = 0;
      v15 = 0;
    }
    v67 = v136;
    v68 = lpData;
    if ( (_DWORD)v136 )
    {
      v67 = 0;
      LODWORD(v136) = 0;
      *(_WORD *)lpData = 0;
    }
    cchName = 520;
    v69 = RegGetValueW(hkey, 0, L"CacheRelativePath", 2u, 0, Name, &cchName);
    v10 = v69;
    if ( v69 != 2 )
    {
      if ( v69 > 0 )
        v10 = (unsigned __int16)v69 | 0x80070000;
      if ( v10 < 0 )
        goto LABEL_176;
      v70 = -1;
      do
        ++v70;
      while ( Name[v70] );
      if ( (_DWORD)v70 )
      {
        v71 = v70 + v67;
        if ( HIDWORD(v136) < (unsigned int)v70 + v67 + 1 )
        {
          v72 = (unsigned int)v70 + v67 + 3;
          v73 = 256;
          if ( (unsigned int)v72 > 0x100 )
          {
            if ( (unsigned int)v72 > 0x400 )
            {
              v73 = 4096;
              if ( (unsigned int)v72 <= 0x1000 )
                v73 = 1024;
            }
          }
          else
          {
            v73 = 64;
          }
          v74 = -v73 & (v72 + v73 - 1);
          v75 = v74 - 1;
          if ( (unsigned int)(v74 - 1) > 0xFFFFFFE )
          {
            v10 = -2147024809;
            goto LABEL_176;
          }
          HIDWORD(v129) = 0;
          Heap = (BYTE *)WxAllocateHeapEx(v72, (unsigned int)(2 * v74));
          v77 = Heap;
          if ( !Heap )
          {
            HIDWORD(v129) = 52;
            v10 = -2147024882;
LABEL_176:
            v6 = 1;
LABEL_177:
            v12 = v127;
            goto LABEL_178;
          }
          v78 = lpData;
          *(_WORD *)Heap = 0;
          v79 = 2LL * v67;
          memcpy_0(Heap, v78, v79);
          HIDWORD(v136) = v75;
          *(_WORD *)&v77[v79] = 0;
          v68 = v77;
          lpData = v77;
          if ( v78 )
          {
            v129 = v78;
            if ( v78 != (BYTE *)&::Data )
              WxFreeHeapEx(&v129);
          }
        }
        v80 = &v68[2 * (unsigned int)v136];
        memcpy_0(v80, Name, 2LL * (unsigned int)v70);
        LODWORD(v136) = v71;
        *(_WORD *)&v80[2 * (unsigned int)v70] = 0;
        v67 = v71;
        v15 = 0;
      }
    }
    pvData = 0;
    cchName = 4;
    v81 = RegGetValueW(hkey, 0, L"CacheLimit", 0x18u, 0, &pvData, &cchName);
    v10 = v81;
    if ( v81 != 2 )
    {
      if ( v81 > 0 )
        v10 = (unsigned __int16)v81 | 0x80070000;
      if ( v10 < 0 )
        goto LABEL_176;
    }
    v157 = 0;
    cchName = 4;
    v82 = RegGetValueW(hkey, 0, L"CacheOptions", 0x18u, 0, &v157, &cchName);
    v10 = v82;
    if ( v82 != 2 )
    {
      if ( v82 > 0 )
        v10 = (unsigned __int16)v82 | 0x80070000;
      if ( v10 < 0 )
        goto LABEL_176;
    }
    v159 = 0;
    cchName = 4;
    v83 = RegGetValueW(hkey, 0, L"EntryMaxAge", 0x18u, 0, &v159, &cchName);
    v10 = v83;
    if ( v83 != 2 )
    {
      if ( v83 > 0 )
        v10 = (unsigned __int16)v83 | 0x80070000;
      if ( v10 < 0 )
        goto LABEL_176;
    }
    *(_DWORD *)Data = 0;
    cchName = 4;
    v84 = RegGetValueW(hkey, 0, L"CacheRepair", 0x18u, 0, Data, &cchName);
    v10 = v84;
    if ( v84 != 2 )
    {
      if ( v84 > 0 )
        v10 = (unsigned __int16)v84 | 0x80070000;
      if ( v10 < 0 )
        goto LABEL_176;
    }
    v6 = 1;
    if ( (v157 & 0x10) != 0 )
    {
LABEL_164:
      LODWORD(v13) = v133;
      goto LABEL_165;
    }
    if ( !pvData )
    {
      pvData = 1;
      RegSetValueExW(hkey, L"CacheLimit", 0, 4u, (const BYTE *)&pvData, 4u);
    }
    if ( v67 )
    {
      v85 = v144;
      if ( !v144 || !*v144 )
      {
        v10 = -2147024809;
        goto LABEL_177;
      }
      v86 = v130;
      if ( (_DWORD)v131 )
      {
        LODWORD(v131) = 0;
        *(_WORD *)v130 = 0;
      }
      v148[1] = lpData;
      v148[0] = v85;
      v162 = 0;
      v149 = 0;
      v150 = 0;
      v151 = 0;
      v152 = 0;
      memset(v161, 0, sizeof(v161));
      memset_0(v164, 0, sizeof(v164));
      memset_0(v163, 0, sizeof(v163));
      v87 = 0;
      v160 = 92;
      for ( i = 0; i != 10; ++i )
      {
        v89 = v148[i];
        if ( v89 )
        {
          v90 = -1;
          do
            ++v90;
          while ( *(_WORD *)(v89 + 2 * v90) );
        }
        else
        {
          LODWORD(v90) = 0;
        }
        *((_DWORD *)v161 + i) = v90;
      }
      v91 = 0;
      LODWORD(v92) = 0;
      v93 = 1;
      do
      {
        v94 = (_WORD *)v148[(unsigned int)v92];
        if ( v87 && *v94 == 92 )
        {
          ++v94;
          --*((_DWORD *)v161 + (unsigned int)v92);
        }
        else if ( !(_DWORD)v93 && !v87 && *v94 != 92 )
        {
          v115 = v91;
          v93 = (__int64)&v160;
          ++v91;
          v164[v115] = &v160;
          v163[v115] = 1;
        }
        v95 = *((_DWORD *)v161 + (unsigned int)v92);
        v96 = v91++;
        v164[v96] = v94;
        v163[v96] = v95;
        v87 = v94[v95 - 1] == 92;
        v92 = (unsigned int)(v92 + 1);
        if ( (unsigned int)v92 >= 0xA )
          break;
        v93 = 0;
      }
      while ( *((_DWORD *)v161 + v92) );
      v97 = 0;
      if ( v91 )
      {
        do
        {
          v98 = v97++;
          v15 += v163[v98];
        }
        while ( v97 < v91 );
        v10 = 0;
        if ( !v15 )
        {
LABEL_138:
          if ( v10 < 0 )
            goto LABEL_177;
LABEL_139:
          v108 = v130;
          goto LABEL_140;
        }
        v99 = (unsigned int)(v15 + 1);
        if ( HIDWORD(v131) >= (unsigned int)v99 )
        {
LABEL_135:
          for ( j = 0; j < v91; ++j )
          {
            v107 = 2LL * (unsigned int)v163[j];
            memcpy_0(v86, v164[j], v107);
            v86 += v107;
          }
          v11 = v134;
          v6 = 1;
          *(_WORD *)v86 = 0;
          LODWORD(v131) = v15;
          goto LABEL_138;
        }
        v100 = CalculateRoundedUpBufferSize(v99, v94, v92, v93);
        v103 = v100 - 1;
        if ( (unsigned int)(v100 - 1) <= 0xFFFFFFE )
        {
          HIDWORD(v129) = v102;
          v104 = (BYTE *)WxAllocateHeapEx(v101, (unsigned int)(2 * v100));
          if ( !v104 )
          {
            HIDWORD(v129) = 52;
            v10 = -2147024882;
            goto LABEL_138;
          }
          v105 = (const WCHAR *)v86;
          *(_WORD *)v104 = 0;
          v86 = v104;
          HIDWORD(v131) = v103;
          v130 = v104;
          if ( v105 )
          {
            v129 = (void *)v105;
            if ( v105 != &::Data )
              WxFreeHeapEx(&v129);
          }
          goto LABEL_135;
        }
      }
      v10 = -2147024809;
      goto LABEL_138;
    }
    v122 = (unsigned int)v145;
    v108 = v130;
    if ( !(unsigned int)_o__wcsnicmp(v130, v144, (unsigned int)v145) )
    {
      v10 = CWxString::Set((CWxString *)&lpData, (const unsigned __int16 *)&v108[2 * v122]);
      if ( v10 < 0 )
        goto LABEL_177;
      CWxString::UnLeading((CWxString *)&lpData, v123);
      CWxString::UnTrailing((CWxString *)&lpData, 0x5Cu);
      v10 = WxSetRegistryString(hkey, L"CacheRelativePath", lpData, v124);
      if ( v10 < 0 )
        goto LABEL_177;
      goto LABEL_139;
    }
LABEL_140:
    if ( *(_DWORD *)Data )
    {
      v10 = WxSetRegistryString(hkey, L"CachePath", v108, v93);
      if ( v10 < 0 )
        goto LABEL_177;
      *(_DWORD *)Data = 0;
      v121 = RegSetValueExW(hkey, L"CacheRepair", 0, 4u, Data, 4u);
      v10 = v121;
      if ( v121 > 0 )
        v10 = (unsigned __int16)v121 | 0x80070000;
      if ( v10 < 0 )
        goto LABEL_177;
    }
    v10 = CWxString::Trailing((CWxString *)&v130, (unsigned __int16)v94);
    if ( v10 < 0 )
      goto LABEL_177;
    v109 = v130;
    if ( (int)WxValidateCacheDirectory((const unsigned __int16 *)v130) < 0 )
      goto LABEL_164;
    v12 = v127;
    v110 = v142;
    if ( v142 == v127 )
      break;
LABEL_144:
    v111 = (char *)lpMem + 40 * v127;
    if ( v111 )
    {
      v112 = 0;
      LODWORD(v13) = 0;
      v133 = 0;
      if ( Src != &::Data )
        v112 = Src;
      *(_QWORD *)v111 = v112;
      Src = (void *)&::Data;
      v139 = 0;
    }
    else
    {
      LODWORD(v13) = v133;
    }
    if ( v111 != (char *)-8LL )
    {
      v113 = 0;
      if ( v140 != &::Data )
        v113 = v140;
      *((_QWORD *)v111 + 1) = v113;
      v137 = 0;
      v141 = 0;
      v140 = (void *)&::Data;
    }
    if ( v111 != (char *)-16LL )
    {
      v130 = (BYTE *)&::Data;
      v114 = 0;
      v131 = 0;
      if ( v109 != (BYTE *)&::Data )
        v114 = v109;
      *((_QWORD *)v111 + 2) = v114;
    }
    *((_QWORD *)v111 + 3) = (unsigned __int64)pvData << 10;
    v12 = v127 + 1;
    *((_DWORD *)v111 + 8) = v157;
    *((_DWORD *)v111 + 9) = v159;
    ++v127;
LABEL_157:
    v8 = (const WCHAR *)Src;
    v14 = v128 + 1;
  }
  v118 = 40 * (v142 + 5);
  if ( g_fWxHeapExtensionInitialized )
    WxFatalHResult(-2147467263);
  if ( lpMem )
    v119 = HeapReAlloc(g_hWxProcessHeap, 8u, lpMem, v118);
  else
    v119 = HeapAlloc(g_hWxProcessHeap, 8u, v118);
  if ( v119 )
  {
    v109 = v130;
    v142 = v110 + 5;
    lpMem = v119;
    goto LABEL_144;
  }
  v10 = -2147024882;
LABEL_178:
  v116 = lpMem;
  if ( !lpMem )
    goto LABEL_179;
  v125 = 0;
  if ( v12 )
  {
    v126 = (char *)lpMem;
    do
      Free_URLCACHE_EXTENSIBLE_CONTAINER((struct _URLCACHE_EXTENSIBLE_CONTAINER *)&v126[40 * v125++]);
    while ( v125 < v12 );
    v11 = v134;
  }
LABEL_215:
  v116 = lpMem;
LABEL_179:
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_d(1036, 15, &WPP_1af76d9ad7163b4b1c76b77142f1718e_Traceguids, (unsigned int)v10);
  if ( v116 )
    WxFreeHeapEx(&lpMem);
  CWxString::_Release((CWxString *)&lpData);
  CWxString::_Release((CWxString *)&v130);
  CWxString::_Release((CWxString *)&v140);
  CWxString::_Release((CWxString *)&Src);
  if ( hkey )
  {
    RegCloseKey(hkey);
    hkey = 0;
  }
  if ( v11 )
    RpcRevertToSelf();
  if ( v6 )
    ReleaseSRWLockShared(&g_srwExtensibleContainerConfig);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180026820  push    rbp
0x180026822  push    rbx
0x180026823  push    rsi
0x180026824  push    rdi
0x180026825  push    r12
0x180026827  push    r13
0x180026829  push    r14
0x18002682b  push    r15
0x18002682d  lea     rbp, [rsp-3B8h]
0x180026835  sub     rsp, 4B8h
0x18002683c  mov     rax, cs:__security_cookie
0x180026843  xor     rax, rsp
0x180026846  mov     [rbp+3F0h+var_50], rax
0x18002684d  xor     esi, esi
0x18002684f  mov     [rbp+3F0h+var_410], r8
0x180026853  mov     r14, r8
0x180026856  mov     [rbp+3F0h+hKey], rdx
0x18002685a  mov     rbx, rcx
0x18002685d  mov     [rbp+3F0h+var_420], rcx
0x180026861  xor     edx, edx; Val
0x180026863  mov     [rsp+4F0h+var_4A4], esi
0x180026867  mov     r8d, 208h; Size
0x18002686d  mov     [rbp+3F0h+hkey], rsi
0x180026871  lea     rcx, [rbp+3F0h+Name]; void *
0x180026878  mov     [rbp+3F0h+var_408], r9
0x18002687c  mov     r15d, esi
0x18002687f  mov     r12, r9
0x180026882  call    memset_0
0x180026887  lea     rax, Data
0x18002688e  mov     [rbp+3F0h+cchName], esi
0x180026891  mov     r13, rax
0x180026894  mov     [rbp+3F0h+Src], rax
0x180026898  mov     [rbp+3F0h+var_440], rax
0x18002689c  mov     [rsp+4F0h+var_490], rax
0x1800268a1  mov     [rbp+3F0h+lpData], rax
0x1800268a5  mov     [rbp+3F0h+var_448], rsi
0x1800268a9  mov     [rbp+3F0h+var_438], rsi
0x1800268ad  mov     [rsp+4F0h+var_488], rsi
0x1800268b2  mov     [rbp+3F0h+var_460], rsi
0x1800268b6  mov     [rbp+3F0h+pvData], esi
0x1800268b9  mov     dword ptr [rbp+3F0h+Data], esi
0x1800268bc  mov     [rbp+3F0h+var_398], esi
0x1800268bf  mov     [rbp+3F0h+var_388], esi
0x1800268c2  mov     [rsp+4F0h+lpMem], rsi
0x1800268c7  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800268ce  jz      short loc_1800268F1
0x1800268d0  lea     edx, [rsi+0Eh]
0x1800268d3  mov     [rsp+4F0h+lpClass], r12
0x1800268d8  mov     ecx, 40Ch
0x1800268dd  mov     [rsp+4F0h+lpReserved], r14
0x1800268e2  mov     r9, rbx
0x1800268e5  lea     r8, WPP_1af76d9ad7163b4b1c76b77142f1718e_Traceguids
0x1800268ec  call    WPP_SF_Sqq
0x1800268f1  test    r14, r14
0x1800268f4  jz      short loc_1800268F9
0x1800268f6  mov     [r14], rsi
0x1800268f9  test    r12, r12
0x1800268fc  jz      short loc_180026902
0x1800268fe  mov     [r12], esi
0x180026902  or      rax, 0FFFFFFFFFFFFFFFFh
0x180026906  inc     rax
0x180026909  cmp     [rbx+rax*2], si
0x18002690d  jnz     short loc_180026906
0x18002690f  lea     rcx, [rbp+3F0h+var_470]; int *
0x180026913  mov     [rbp+3F0h+var_418], rax
0x180026917  mov     dword ptr [rbp+3F0h+var_458+4], esi
0x18002691a  mov     [rbp+3F0h+var_470], esi
0x18002691d  call    ?WxRpcImpersonateNonElevatedCaller@@YAJPEAH@Z; WxRpcImpersonateNonElevatedCaller(int *)
0x180026922  xor     edi, edi
0x180026924  mov     esi, eax
0x180026926  test    eax, eax
0x180026928  js      loc_18002772F
0x18002692e  mov     ebx, [rbp+3F0h+var_470]
0x180026931  lea     rcx, ?g_srwExtensibleContainerConfig@@3VWxSrw@@A; SRWLock
0x180026938  mov     r12d, edi
0x18002693b  mov     [rsp+4F0h+var_4B0], edi
0x18002693f  mov     [rbp+3F0h+var_430], edi
0x180026942  call    cs:__imp_AcquireSRWLockShared
0x180026948  mov     eax, dword ptr [rbp+3F0h+var_438]
0x18002694b  lea     r15d, [rdi+1]
0x18002694f  mov     r14d, dword ptr [rbp+3F0h+var_448]
0x180026953  mov     ecx, edi
0x180026955  mov     [rsp+4F0h+var_4A0], r15
0x18002695a  mov     [rbp-68h], rax
0x18002695e  mov     [rsp+4F0h+var_478], r14
0x180026963  mov     [rsp+4F0h+var_4A8], ecx
0x180026967  test    r14d, r14d
0x18002696a  jz      short loc_18002697C
0x18002696c  mov     r14d, edi
0x18002696f  mov     dword ptr [rbp+3F0h+var_448], edi
0x180026972  mov     [rsp+4F0h+var_478], r14
0x180026977  mov     [r13+0], di
0x18002697c  xor     r13d, r13d
0x18002697f  mov     [rbp+3F0h+cchName], 104h
0x180026986  mov     [rsp+4F0h+lpftLastWriteTime], r13; lpftLastWriteTime
0x18002698b  lea     r9, [rbp+3F0h+cchName]; lpcchName
0x18002698f  mov     [rsp+4F0h+lpcchClass], r13; lpcchClass
0x180026994  lea     r8, [rbp+3F0h+Name]; lpName
0x18002699b  mov     edx, ecx; dwIndex
0x18002699d  mov     [rsp+4F0h+lpClass], r13; lpClass
0x1800269a2  mov     rcx, [rbp+3F0h+hKey]; hKey
0x1800269a6  mov     [rsp+4F0h+lpReserved], r13; lpReserved
0x1800269ab  call    cs:__imp_RegEnumKeyExW
0x1800269b1  mov     esi, eax
0x1800269b3  cmp     eax, 103h
0x1800269b8  jz      loc_180027705
0x1800269be  test    eax, eax
0x1800269c0  jle     short loc_1800269CB
0x1800269c2  movzx   esi, ax
0x1800269c5  or      esi, 80070000h
0x1800269cb  test    esi, esi
0x1800269cd  js      loc_180027AC1
0x1800269d3  lea     rax, [rbp+3F0h+Name]
0x1800269da  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800269de  inc     r12
0x1800269e1  cmp     [rax+r12*2], r13w
0x1800269e6  jnz     short loc_1800269DE
0x1800269e8  test    r12d, r12d
0x1800269eb  jz      loc_18002792C
0x1800269f1  xor     edi, edi
0x1800269f3  lea     r13d, [r12+r14]
0x1800269f7  lea     ecx, [r13+1]
0x1800269fb  mov     esi, edi
0x1800269fd  cmp     dword ptr [rbp+3F0h+var_448+4], ecx
0x180026a00  jnb     loc_18002781B
0x180026a06  add     ecx, 2
0x180026a09  mov     eax, 100h
0x180026a0e  cmp     ecx, eax
0x180026a10  ja      loc_18002768E
0x180026a16  lea     eax, [rdi+40h]
0x180026a19  dec     ecx
0x180026a1b  add     ecx, eax
0x180026a1d  neg     eax
0x180026a1f  and     ecx, eax
0x180026a21  lea     r15d, [rcx-1]
0x180026a25  cmp     r15d, 0FFFFFFEh
0x180026a2c  ja      loc_18002752C
0x180026a32  add     ecx, ecx
0x180026a34  mov     dword ptr [rsp+4F0h+var_498+4], edi
0x180026a38  cmp     cs:?g_fWxHeapExtensionInitialized@@3HA, edi; int g_fWxHeapExtensionInitialized
0x180026a3e  jnz     loc_180027858
0x180026a44  mov     r8d, ecx; dwBytes
0x180026a47  xor     edx, edx; dwFlags
0x180026a49  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x180026a50  call    cs:__imp_HeapAlloc
0x180026a56  mov     rsi, rax
0x180026a59  test    rax, rax
0x180026a5c  jz      loc_180027791
0x180026a62  mov     r14, [rbp+3F0h+Src]
0x180026a66  mov     rcx, rsi; void *
0x180026a69  mov     [rax], di
0x180026a6c  mov     rdx, r14; Src
0x180026a6f  mov     eax, dword ptr [rsp+4F0h+var_478]
0x180026a73  lea     rdi, [rax+rax]
0x180026a77  mov     r8, rdi; Size
0x180026a7a  call    memcpy_0
0x180026a7f  xor     ecx, ecx
0x180026a81  mov     dword ptr [rbp+3F0h+var_448+4], r15d
0x180026a85  mov     [rdi+rsi], cx
0x180026a89  mov     r15, rsi
0x180026a8c  mov     [rbp+3F0h+Src], rsi
0x180026a90  xor     edi, edi
0x180026a92  mov     esi, edi
0x180026a94  test    r14, r14
0x180026a97  jz      short loc_180026AB4
0x180026a99  lea     rax, Data
0x180026aa0  mov     [rbp+3F0h+phkResult], r14
0x180026aa4  cmp     r14, rax
0x180026aa7  jz      short loc_180026AB4
0x180026aa9  lea     rcx, [rbp+3F0h+phkResult]
0x180026aad  call    WxFreeHeapEx
0x180026ab2  jmp     short loc_180026AC1
0x180026ab4  mov     r14, [rsp+4F0h+var_478]
0x180026ab9  test    esi, esi
0x180026abb  js      loc_180027824
0x180026ac1  mov     eax, dword ptr [rsp+4F0h+var_478]
0x180026ac5  lea     rdx, [rbp+3F0h+Name]; Src
0x180026acc  lea     rsi, [r15+rax*2]
0x180026ad0  mov     eax, r12d
0x180026ad3  mov     rcx, rsi; void *
0x180026ad6  lea     rdi, [rax+rax]
0x180026ada  mov     r8, rdi; Size
0x180026add  call    memcpy_0
0x180026ae2  xor     ecx, ecx
0x180026ae4  mov     dword ptr [rbp+3F0h+var_448], r13d
0x180026ae8  mov     r14d, r13d
0x180026aeb  mov     [rdi+rsi], cx
0x180026aef  xor     r13d, r13d
0x180026af2  mov     [rsp+4F0h+var_478], r14
0x180026af7  mov     rcx, [rbp+3F0h+hkey]; hKey
0x180026afb  test    rcx, rcx
0x180026afe  jz      short loc_180026B0A
0x180026b00  call    cs:__imp_RegCloseKey
0x180026b06  mov     [rbp+3F0h+hkey], r13
0x180026b0a  mov     dword ptr [rsp+4F0h+var_498+4], r13d
0x180026b0f  mov     [rbp+3F0h+phkResult], r13
0x180026b13  test    byte ptr cs:xmmword_180266B60+3, 20h
0x180026b1a  jnz     loc_180027934
0x180026b20  mov     rcx, [rbp+3F0h+hKey]; hKey
0x180026b24  lea     rax, [rbp+3F0h+phkResult]
0x180026b28  mov     r9d, 0Fh; samDesired
0x180026b2e  mov     [rsp+4F0h+lpReserved], rax; phkResult
0x180026b33  xor     r8d, r8d; ulOptions
0x180026b36  mov     [rbp+3F0h+hkey], r13
0x180026b3a  mov     rdx, r15; lpSubKey
0x180026b3d  call    cs:__imp_RegOpenKeyExW
0x180026b43  mov     esi, eax
0x180026b45  test    eax, eax
0x180026b47  jle     short loc_180026B52
0x180026b49  movzx   esi, ax
0x180026b4c  or      esi, 80070000h
0x180026b52  test    esi, esi
0x180026b54  js      loc_1800277F8
0x180026b5a  mov     rax, [rbp+3F0h+phkResult]
0x180026b5e  mov     rcx, r13; hKey
0x180026b61  mov     [rbp+3F0h+hkey], rax
0x180026b65  mov     [rbp+3F0h+phkResult], rcx
0x180026b69  test    byte ptr cs:xmmword_180266B60+3, 20h
0x180026b70  jnz     loc_18002789B
0x180026b76  test    rcx, rcx
0x180026b79  jz      short loc_180026B85
0x180026b7b  call    cs:__imp_RegCloseKey
0x180026b81  mov     [rbp+3F0h+phkResult], r13
0x180026b85  test    esi, esi
0x180026b87  js      loc_1800277D9
0x180026b8d  mov     r15, [rbp-68h]
0x180026b91  mov     rdi, [rbp+3F0h+var_440]
0x180026b95  test    r15d, r15d
0x180026b98  jnz     loc_18002747C
0x180026b9e  mov     rcx, [rbp+3F0h+hkey]; hkey
0x180026ba2  lea     rax, [rbp+3F0h+cchName]
0x180026ba6  mov     [rsp+4F0h+lpcchClass], rax; pcbData
0x180026bab  lea     r8, Value; "CachePrefix"
0x180026bb2  lea     rax, [rbp+3F0h+Name]
0x180026bb9  mov     [rbp+3F0h+cchName], 208h
0x180026bc0  mov     [rsp+4F0h+lpClass], rax; pvData
0x180026bc5  mov     r9d, 2; dwFlags
0x180026bcb  xor     edx, edx; lpSubKey
0x180026bcd  mov     [rsp+4F0h+lpReserved], r13; pdwType
0x180026bd2  call    cs:__imp_RegGetValueW
0x180026bd8  mov     esi, eax
0x180026bda  cmp     eax, 2
0x180026bdd  jz      loc_180027A64
0x180026be3  test    eax, eax
0x180026be5  jle     short loc_180026BF0
0x180026be7  movzx   esi, ax
0x180026bea  or      esi, 80070000h
0x180026bf0  test    esi, esi
0x180026bf2  js      loc_180027AB4
0x180026bf8  lea     rax, [rbp+3F0h+Name]
0x180026bff  or      r12, 0FFFFFFFFFFFFFFFFh
0x180026c03  inc     r12
0x180026c06  cmp     [rax+r12*2], r13w
0x180026c0b  jnz     short loc_180026C03
0x180026c0d  test    r12d, r12d
0x180026c10  jz      loc_18002795D
0x180026c16  xor     edx, edx; dwFlags
0x180026c18  lea     r13d, [r12+r15]
0x180026c1c  lea     ecx, [r13+1]
0x180026c20  mov     esi, edx
0x180026c22  cmp     dword ptr [rbp+3F0h+var_438+4], ecx
0x180026c25  jnb     loc_180026CD7
0x180026c2b  add     ecx, 2
0x180026c2e  mov     eax, 100h
0x180026c33  cmp     ecx, eax
0x180026c35  ja      loc_1800276AF
0x180026c3b  lea     eax, [rdx+40h]
0x180026c3e  dec     ecx
0x180026c40  add     ecx, eax
0x180026c42  neg     eax
0x180026c44  and     ecx, eax
0x180026c46  lea     r15d, [rcx-1]
0x180026c4a  cmp     r15d, 0FFFFFFEh
0x180026c51  ja      loc_18002760A
0x180026c57  add     ecx, ecx
0x180026c59  mov     dword ptr [rsp+4F0h+var_498+4], edx
0x180026c5d  cmp     cs:?g_fWxHeapExtensionInitialized@@3HA, edx; int g_fWxHeapExtensionInitialized
0x180026c63  jnz     loc_180027869
0x180026c69  mov     r8d, ecx; dwBytes
0x180026c6c  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x180026c73  call    cs:__imp_HeapAlloc
0x180026c79  xor     ecx, ecx
0x180026c7b  mov     rsi, rax
0x180026c7e  test    rax, rax
0x180026c81  jz      loc_1800277A3
0x180026c87  mov     [rax], cx
0x180026c8a  mov     r14, rdi
0x180026c8d  mov     eax, dword ptr [rbp+3F0h+var_458]
0x180026c90  mov     rdx, r14; Src
0x180026c93  mov     rcx, rsi; void *
0x180026c96  lea     rdi, [rax+rax]
0x180026c9a  mov     r8, rdi; Size
0x180026c9d  call    memcpy_0
0x180026ca2  xor     edx, edx
0x180026ca4  mov     dword ptr [rbp+3F0h+var_438+4], r15d
0x180026ca8  mov     [rdi+rsi], dx
0x180026cac  mov     rdi, rsi
0x180026caf  mov     [rbp+3F0h+var_440], rsi
0x180026cb3  mov     esi, edx
0x180026cb5  test    r14, r14
  ... truncated ...
```
