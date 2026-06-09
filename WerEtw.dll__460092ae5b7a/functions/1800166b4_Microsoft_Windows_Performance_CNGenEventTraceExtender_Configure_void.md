# Microsoft::Windows::Performance::CNGenEventTraceExtender::Configure(void)

- ea: `0x1800166b4`
- end: `0x180016e7b`
- name: `?Configure@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEAAJXZ`
- size: `1991`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CNGenEventTraceExtender *__hidden this)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180015e40`

## callees

- `0x180001870`
- `0x180001894`
- `0x180003bb8`
- `0x180004670`
- `0x1800053a8`
- `0x180007da8`
- `0x18000ea38`
- `0x180011764`
- `0x180012058`
- `0x1800125f8`
- `0x180013088`
- `0x180013e40`
- `0x18001578c`
- `0x1800163cc`
- `0x1800166b4`
- `0x180018228`
- `0x180018968`
- `0x18002a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180016b7d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180016bb8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180016d14`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180016d3d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180016b7d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180016bb8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180016d14`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180016d3d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180016d59`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180016d59`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180016754`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800167b1`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180016a63`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180016754`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800167b1`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180016a63`

## string_xrefs

- `0x180016b2a`: `_NT_SYMBOL_PATH`
- `0x18001670c`: `mscoree.dll`
- `0x180016729`: `CLRCreateInstance`
- `0x180016aea`: `XPERF_NGenPdbsPath`
- `0x180016dfa`: `XPERF_NGenPdbsCachePath`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Performance::CNGenEventTraceExtender::Configure(
        Microsoft::Windows::Performance::CNGenEventTraceExtender *this)
{
  __int64 v2; // rbx
  __int64 (__fastcall *v3)(GUID *, GUID *, __int64 *); // rax
  int v4; // esi
  unsigned __int16 v6; // r14
  __int64 v7; // rbx
  __int64 v8; // rcx
  unsigned __int16 v9; // si
  __int64 v10; // r8
  _QWORD *v11; // rsi
  int v12; // eax
  _QWORD *v13; // rdx
  _QWORD *v14; // rdx
  __int64 v15; // r8
  __int64 v16; // rax
  int v17; // ebx
  _QWORD *v18; // rdx
  _QWORD *v19; // rdx
  unsigned int Error; // ebx
  _QWORD *v21; // rdx
  unsigned __int64 v22; // rax
  _QWORD *v23; // rdx
  _QWORD *v24; // rbx
  int v25; // edx
  int v26; // ecx
  __int64 v27; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v28; // [rsp+38h] [rbp-C8h] BYREF
  int v29; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v30; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v31; // [rsp+50h] [rbp-B0h] BYREF
  int v32; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v33; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v34; // [rsp+68h] [rbp-98h] BYREF
  HMODULE hLibModule[3]; // [rsp+70h] [rbp-90h] BYREF
  char v36; // [rsp+88h] [rbp-78h]
  int v37; // [rsp+90h] [rbp-70h] BYREF
  __int64 v38; // [rsp+98h] [rbp-68h]
  __int64 v39; // [rsp+A0h] [rbp-60h]
  void *v40; // [rsp+A8h] [rbp-58h]
  void *v41; // [rsp+B0h] [rbp-50h]
  void *v42; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v43; // [rsp+C0h] [rbp-40h]
  int v44; // [rsp+D0h] [rbp-30h]
  __int64 v45; // [rsp+D8h] [rbp-28h]
  __int64 v46; // [rsp+E0h] [rbp-20h]
  HMODULE *v47; // [rsp+E8h] [rbp-18h] BYREF
  void *Block[2]; // [rsp+F0h] [rbp-10h]
  __int64 v49; // [rsp+100h] [rbp+0h]
  int v50; // [rsp+108h] [rbp+8h]
  __int64 v51; // [rsp+110h] [rbp+10h]
  int v52; // [rsp+118h] [rbp+18h]
  WCHAR Buffer[264]; // [rsp+130h] [rbp+30h] BYREF

  v2 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v28 = v2;
  hLibModule[0] = 0;
  hLibModule[1] = (HMODULE)L"mscoree.dll";
  hLibModule[2] = 0;
  v36 = 0;
  v47 = hLibModule;
  Block[0] = "CLRCreateInstance";
  Block[1] = 0;
  LOBYTE(v49) = 0;
  if ( !Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)(&v47) )
  {
    if ( hLibModule[0] )
      FreeLibrary(hLibModule[0]);
    goto LABEL_62;
  }
  v33 = 0;
  v3 = (__int64 (__fastcall *)(GUID *, GUID *, __int64 *))Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)(&v47);
  v4 = v3(&CLSID_CLRMetaHost, &IID_ICLRMetaHost, &v33);
  if ( v4 < 0 )
  {
    if ( v33 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
LABEL_8:
    if ( hLibModule[0] )
      FreeLibrary(hLibModule[0]);
    if ( _InterlockedDecrement((volatile signed __int32 *)(v2 - 24 + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v2 - 24) + 8LL))(*(_QWORD *)(v2 - 24));
    return (unsigned int)v4;
  }
  v31 = 0;
  v4 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v33 + 40LL))(v33, &v31);
  if ( v4 < 0 )
  {
    if ( v31 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    if ( v33 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    goto LABEL_8;
  }
  v34 = 0;
  v32 = 0;
  v6 = 0;
  while ( (*(int (__fastcall **)(__int64, __int64, __int64 *, int *))(*(_QWORD *)v31 + 24LL))(v31, 1, &v34, &v32) >= 0
       && v32 == 1 )
  {
    v7 = v34;
    v34 = 0;
    v46 = v7;
    v8 = 0;
    v30 = 0;
    if ( v7 )
    {
      (**(void (__fastcall ***)(__int64, GUID *, __int64 *))v7)(v7, &GUID_bd39d1d2_ba2f_486a_89b0_b4b0cb466891, &v30);
      v8 = v30;
    }
    if ( v8 )
    {
      LODWORD(v27) = 30;
      if ( (*(int (__fastcall **)(__int64, HMODULE **, __int64 *))(*(_QWORD *)v8 + 24LL))(v8, &v47, &v27) >= 0 )
      {
        if ( (unsigned int)v27 < 3
          || (((_WORD)v47 - 86) & 0xFFDF) != 0
          || (v9 = WORD1(v47), (unsigned __int16)(WORD1(v47) - 52) > 5u)
          || WORD2(v47) != 46
          || WORD1(v47) <= v6 )
        {
LABEL_48:
          if ( v30 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
          if ( v7 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
        }
        else
        {
          v29 = 260;
          if ( (*(int (__fastcall **)(__int64, WCHAR *, int *))(*(_QWORD *)v30 + 32LL))(v30, Buffer, &v29) >= 0 )
          {
            v10 = -1;
            do
              ++v10;
            while ( Buffer[v10] );
            ATL::CSimpleStringT<unsigned short,0>::SetString(&v28, Buffer, v10);
            v6 = v9;
            goto LABEL_48;
          }
          if ( v30 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
          if ( v7 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
        }
      }
      else
      {
        if ( v30 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
        if ( v7 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
      }
    }
    else if ( v7 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    }
  }
  if ( v34 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
  if ( v31 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
  if ( v33 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
  if ( hLibModule[0] )
    FreeLibrary(hLibModule[0]);
  v2 = v28;
  if ( !*(_DWORD *)(v28 - 16) )
  {
LABEL_62:
    if ( _InterlockedDecrement((volatile signed __int32 *)(v2 - 24 + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v2 - 24) + 8LL))(*(_QWORD *)(v2 - 24));
    return 2147500037LL;
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
    (char *)this + 40,
    &v28);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Replace((char *)this + 40);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
    (char *)this + 48,
    &v28);
  if ( _InterlockedDecrement((volatile signed __int32 *)(v2 - 24 + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v2 - 24) + 8LL))(*(_QWORD *)(v2 - 24));
  v11 = (_QWORD *)((char *)this + 56);
  if ( (unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::GetEnvironmentVariableW(
                       (char *)this + 56,
                       L"XPERF_NGenPdbsPath")
    && *(_DWORD *)(*v11 - 16LL) )
  {
LABEL_109:
    v24 = (_QWORD *)((char *)this + 64);
    if ( !(unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::GetEnvironmentVariableW(
                          (char *)this + 64,
                          L"XPERF_NGenPdbsCachePath")
      || !*(_DWORD *)(*v24 - 16LL) )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
        (char *)this + 64,
        (char *)this + 56);
    }
    *((_BYTE *)this + 32) = 1;
    if ( (Microsoft_Windows_XPerfCoreEnableBits & 1) != 0 )
      McTemplateU0zzzz_EventWriteTransfer(v26, v25, *v11, *v24, *((_QWORD *)this + 5), *((_QWORD *)this + 6));
    return 0;
  }
  v27 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  if ( !(unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::GetEnvironmentVariableW(
                        &v27,
                        L"_NT_SYMBOL_PATH") )
  {
LABEL_97:
    if ( !*(_DWORD *)(*v11 - 16LL) )
    {
      if ( !GetSystemWindowsDirectoryW(Buffer, 0x105u) )
      {
        Error = ATL::AtlHresultFromLastError();
        v21 = (_QWORD *)(v27 - 24);
        if ( _InterlockedDecrement((volatile signed __int32 *)(v27 - 24 + 16)) <= 0 )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v21 + 8LL))(*v21);
        return Error;
      }
      v22 = -1;
      do
        ++v22;
      while ( Buffer[v22] );
      if ( v22 < 2 || Buffer[1] != 58 )
        goto LABEL_74;
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
        (char *)this + 56,
        L"%wc:\\Symbols",
        Buffer[0]);
    }
    v23 = (_QWORD *)(v27 - 24);
    if ( _InterlockedDecrement((volatile signed __int32 *)(v27 - 24 + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v23 + 8LL))(*v23);
    goto LABEL_109;
  }
  *(_OWORD *)Block = 0;
  v49 = 0;
  v50 = 0;
  v51 = 0;
  v52 = 1;
  LODWORD(v47) = 0;
  v12 = ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::Parse(&v47);
  if ( !v12 )
  {
    v40 = 0;
    v41 = 0;
    v42 = 0;
    v43 = 0;
    v44 = 0;
    v37 = 0;
    v45 = 0;
    if ( (unsigned __int8)ATL::CAtlArray<void *,ATL::CElementTraits<void *>>::GrowBuffer(&v42, 256) )
    {
      ATL::CAtlArray<void *,ATL::CElementTraits<void *>>::CallConstructors();
      *(_QWORD *)&v43 = 256;
    }
    v38 = 0;
    v39 = 0;
    v29 = 0;
    v28 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
    while ( 1 )
    {
      v16 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Tokenize(
              &v27,
              &v31,
              v15,
              &v29);
      v17 = *(_DWORD *)(*(_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
                                     &v28,
                                     v16)
                      - 16LL);
      v18 = (_QWORD *)(v31 - 24);
      if ( _InterlockedDecrement((volatile signed __int32 *)(v31 - 24 + 16)) <= 0 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v18 + 8LL))(*v18);
      if ( !v17 )
        break;
      if ( (unsigned int)ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::Match(&v47, v28, &v37, 0) )
      {
        if ( !v37 )
          ATL::AtlThrowImpl(-2147467259);
        ATL::CSimpleStringT<unsigned short,0>::SetString(
          (char *)this + 56,
          *(_QWORD *)v41,
          (__int64)(*((_QWORD *)v41 + 1) - *(_QWORD *)v41) >> 1);
        break;
      }
    }
    v19 = (_QWORD *)(v28 - 24);
    if ( _InterlockedDecrement((volatile signed __int32 *)(v28 - 24 + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v19 + 8LL))(*v19);
    if ( v42 )
      free(v42);
    operator delete(v41);
    v41 = 0;
    operator delete(v40);
    v40 = 0;
    if ( Block[0] )
      free(Block[0]);
    goto LABEL_97;
  }
  if ( v12 == 1 )
  {
    if ( Block[0] )
      free(Block[0]);
    v14 = (_QWORD *)(v27 - 24);
    if ( _InterlockedDecrement((volatile signed __int32 *)(v27 - 24 + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v14 + 8LL))(*v14);
    return 2147942414LL;
  }
  else
  {
    if ( Block[0] )
      free(Block[0]);
LABEL_74:
    v13 = (_QWORD *)(v27 - 24);
    if ( _InterlockedDecrement((volatile signed __int32 *)(v27 - 24 + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v13 + 8LL))(*v13);
    return 2147549183LL;
  }
}

```

## disassembly

```asm
0x1800166b4  push    rbp
0x1800166b6  push    rbx
0x1800166b7  push    rsi
0x1800166b8  push    rdi
0x1800166b9  push    r12
0x1800166bb  push    r13
0x1800166bd  push    r14
0x1800166bf  push    r15
0x1800166c1  lea     rbp, [rsp-258h]
0x1800166c9  sub     rsp, 358h
0x1800166d0  mov     rax, cs:__security_cookie
0x1800166d7  xor     rax, rsp
0x1800166da  mov     [rbp+290h+var_50], rax
0x1800166e1  mov     r13, rcx
0x1800166e4  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800166eb  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800166f2  mov     rax, [rax+18h]
0x1800166f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800166fb  lea     rbx, [rax+18h]
0x1800166ff  mov     [rsp+390h+var_358], rbx
0x180016704  xor     r12d, r12d
0x180016707  mov     [rsp+390h+hLibModule], r12
0x18001670c  lea     rax, aMscoreeDll; "mscoree.dll"
0x180016713  mov     [rsp+390h+var_318], rax
0x180016718  mov     [rbp+290h+var_310], r12
0x18001671c  mov     [rbp+290h+var_308], r12b
0x180016720  lea     rax, [rsp+390h+hLibModule]
0x180016725  mov     [rbp+290h+var_2A8], rax
0x180016729  lea     rax, aClrcreateinsta; "CLRCreateInstance"
0x180016730  mov     [rbp+290h+Block], rax
0x180016734  mov     [rbp+290h+Block+8], r12
0x180016738  mov     byte ptr [rbp+290h+var_290], r12b
0x18001673c  lea     rcx, [rbp+290h+var_2A8]
0x180016740  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x180016745  test    rax, rax
0x180016748  jnz     short loc_180016764
0x18001674a  mov     rcx, [rsp+390h+hLibModule]; hLibModule
0x18001674f  test    rcx, rcx
0x180016752  jz      short loc_18001675B
0x180016754  call    cs:__imp_FreeLibrary
0x18001675a  nop
0x18001675b  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001675f  jmp     loc_180016A74
0x180016764  mov     [rsp+390h+var_330], r12
0x180016769  lea     rcx, [rbp+290h+var_2A8]
0x18001676d  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x180016772  lea     r8, [rsp+390h+var_330]
0x180016777  lea     rdx, IID_ICLRMetaHost
0x18001677e  lea     rcx, CLSID_CLRMetaHost
0x180016785  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001678a  mov     esi, eax
0x18001678c  test    eax, eax
0x18001678e  jns     short loc_1800167E3
0x180016790  mov     rcx, [rsp+390h+var_330]
0x180016795  test    rcx, rcx
0x180016798  jz      short loc_1800167A7
0x18001679a  mov     rdx, [rcx]
0x18001679d  mov     rax, [rdx+10h]
0x1800167a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800167a6  nop
0x1800167a7  mov     rcx, [rsp+390h+hLibModule]; hLibModule
0x1800167ac  test    rcx, rcx
0x1800167af  jz      short loc_1800167B8
0x1800167b1  call    cs:__imp_FreeLibrary
0x1800167b7  nop
0x1800167b8  lea     rdx, [rbx-18h]
0x1800167bc  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800167c0  mov     eax, edi
0x1800167c2  lock xadd [rdx+10h], eax
0x1800167c7  add     eax, edi
0x1800167c9  test    eax, eax
0x1800167cb  jg      short loc_1800167DC
0x1800167cd  mov     rcx, [rdx]
0x1800167d0  mov     rax, [rcx]
0x1800167d3  mov     rax, [rax+8]
0x1800167d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800167dc  mov     eax, esi
0x1800167de  jmp     loc_180016E4D
0x1800167e3  mov     [rsp+390h+var_340], r12
0x1800167e8  mov     rcx, [rsp+390h+var_330]
0x1800167ed  mov     rax, [rcx]
0x1800167f0  lea     rdx, [rsp+390h+var_340]
0x1800167f5  mov     rax, [rax+28h]
0x1800167f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800167fe  mov     esi, eax
0x180016800  test    eax, eax
0x180016802  jns     short loc_180016837
0x180016804  mov     rcx, [rsp+390h+var_340]
0x180016809  test    rcx, rcx
0x18001680c  jz      short loc_18001681B
0x18001680e  mov     rdx, [rcx]
0x180016811  mov     rax, [rdx+10h]
0x180016815  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001681a  nop
0x18001681b  mov     rcx, [rsp+390h+var_330]
0x180016820  test    rcx, rcx
0x180016823  jz      short loc_180016832
0x180016825  mov     rax, [rcx]
0x180016828  mov     rax, [rax+10h]
0x18001682c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016831  nop
0x180016832  jmp     loc_1800167A7
0x180016837  mov     [rsp+390h+var_328], r12
0x18001683c  mov     [rsp+390h+var_338], r12d
0x180016841  mov     r14d, r12d
0x180016844  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180016848  mov     rcx, [rsp+390h+var_340]
0x18001684d  mov     rax, [rcx]
0x180016850  lea     r9, [rsp+390h+var_338]
0x180016855  lea     r8, [rsp+390h+var_328]
0x18001685a  mov     edx, 1
0x18001685f  mov     rax, [rax+18h]
0x180016863  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016868  test    eax, eax
0x18001686a  js      loc_180016A14
0x180016870  cmp     [rsp+390h+var_338], 1
0x180016875  jnz     loc_180016A14
0x18001687b  mov     rbx, [rsp+390h+var_328]
0x180016880  mov     [rsp+390h+var_328], r12
0x180016885  mov     [rbp+290h+var_2B0], rbx
0x180016889  mov     rcx, r12
0x18001688c  mov     [rsp+390h+var_348], rcx
0x180016891  test    rbx, rbx
0x180016894  jz      short loc_1800168B5
0x180016896  mov     rax, [rbx]
0x180016899  lea     r8, [rsp+390h+var_348]
0x18001689e  lea     rdx, _GUID_bd39d1d2_ba2f_486a_89b0_b4b0cb466891
0x1800168a5  mov     rcx, rbx
0x1800168a8  mov     rax, [rax]
0x1800168ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800168b0  mov     rcx, [rsp+390h+var_348]
0x1800168b5  test    rcx, rcx
0x1800168b8  jnz     short loc_1800168D4
0x1800168ba  test    rbx, rbx
0x1800168bd  jz      short loc_1800168CF
0x1800168bf  mov     rax, [rbx]
0x1800168c2  mov     rcx, rbx
0x1800168c5  mov     rax, [rax+10h]
0x1800168c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800168ce  nop
0x1800168cf  jmp     loc_180016848
0x1800168d4  mov     dword ptr [rsp+390h+var_360], 1Eh
0x1800168dc  mov     rax, [rcx]
0x1800168df  lea     r8, [rsp+390h+var_360]
0x1800168e4  lea     rdx, [rbp+290h+var_2A8]
0x1800168e8  mov     rax, [rax+18h]
0x1800168ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800168f1  test    eax, eax
0x1800168f3  jns     short loc_180016926
0x1800168f5  mov     rcx, [rsp+390h+var_348]
0x1800168fa  test    rcx, rcx
0x1800168fd  jz      short loc_18001690C
0x1800168ff  mov     rax, [rcx]
0x180016902  mov     rax, [rax+10h]
0x180016906  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001690b  nop
0x18001690c  test    rbx, rbx
0x18001690f  jz      short loc_180016921
0x180016911  mov     rax, [rbx]
0x180016914  mov     rcx, rbx
0x180016917  mov     rax, [rax+10h]
0x18001691b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016920  nop
0x180016921  jmp     loc_180016848
0x180016926  cmp     dword ptr [rsp+390h+var_360], 3
0x18001692b  jb      loc_1800169E3
0x180016931  movzx   eax, word ptr [rbp+290h+var_2A8]
0x180016935  sub     ax, 56h ; 'V'
0x180016939  mov     ecx, 0FFDFh
0x18001693e  test    cx, ax
0x180016941  jnz     loc_1800169E3
0x180016947  movzx   esi, word ptr [rbp+290h+var_2A8+2]
0x18001694b  lea     eax, [rsi-34h]
0x18001694e  cmp     ax, 5
0x180016952  ja      loc_1800169E3
0x180016958  cmp     word ptr [rbp+290h+var_2A8+4], 2Eh ; '.'
0x18001695d  jnz     loc_1800169E3
0x180016963  cmp     si, r14w
0x180016967  jbe     short loc_1800169E3
0x180016969  mov     [rsp+390h+var_350], 104h
0x180016971  mov     rcx, [rsp+390h+var_348]
0x180016976  mov     rax, [rcx]
0x180016979  lea     r8, [rsp+390h+var_350]
0x18001697e  lea     rdx, [rbp+290h+Buffer]
0x180016982  mov     rax, [rax+20h]
0x180016986  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001698b  test    eax, eax
0x18001698d  jns     short loc_1800169C0
0x18001698f  mov     rcx, [rsp+390h+var_348]
0x180016994  test    rcx, rcx
0x180016997  jz      short loc_1800169A6
0x180016999  mov     rax, [rcx]
0x18001699c  mov     rax, [rax+10h]
0x1800169a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800169a5  nop
0x1800169a6  test    rbx, rbx
0x1800169a9  jz      short loc_1800169BB
0x1800169ab  mov     rax, [rbx]
0x1800169ae  mov     rcx, rbx
0x1800169b1  mov     rax, [rax+10h]
0x1800169b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800169ba  nop
0x1800169bb  jmp     loc_180016848
0x1800169c0  lea     rax, [rbp+290h+Buffer]
0x1800169c4  mov     r8, rdi
0x1800169c7  inc     r8
0x1800169ca  cmp     [rax+r8*2], r12w
0x1800169cf  jnz     short loc_1800169C7
0x1800169d1  lea     rdx, [rbp+290h+Buffer]
0x1800169d5  lea     rcx, [rsp+390h+var_358]
0x1800169da  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1800169df  movzx   r14d, si
0x1800169e3  mov     rcx, [rsp+390h+var_348]
0x1800169e8  test    rcx, rcx
0x1800169eb  jz      short loc_1800169FA
0x1800169ed  mov     rax, [rcx]
0x1800169f0  mov     rax, [rax+10h]
0x1800169f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800169f9  nop
0x1800169fa  test    rbx, rbx
0x1800169fd  jz      short loc_180016A0F
0x1800169ff  mov     rax, [rbx]
0x180016a02  mov     rcx, rbx
0x180016a05  mov     rax, [rax+10h]
0x180016a09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a0e  nop
0x180016a0f  jmp     loc_180016848
0x180016a14  mov     rcx, [rsp+390h+var_328]
0x180016a19  test    rcx, rcx
0x180016a1c  jz      short loc_180016A2B
0x180016a1e  mov     rax, [rcx]
0x180016a21  mov     rax, [rax+10h]
0x180016a25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a2a  nop
0x180016a2b  mov     rcx, [rsp+390h+var_340]
0x180016a30  test    rcx, rcx
0x180016a33  jz      short loc_180016A42
0x180016a35  mov     rax, [rcx]
0x180016a38  mov     rax, [rax+10h]
0x180016a3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a41  nop
0x180016a42  mov     rcx, [rsp+390h+var_330]
0x180016a47  test    rcx, rcx
0x180016a4a  jz      short loc_180016A59
0x180016a4c  mov     rax, [rcx]
0x180016a4f  mov     rax, [rax+10h]
0x180016a53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a58  nop
0x180016a59  mov     rcx, [rsp+390h+hLibModule]; hLibModule
0x180016a5e  test    rcx, rcx
0x180016a61  jz      short loc_180016A69
0x180016a63  call    cs:__imp_FreeLibrary
0x180016a69  mov     rbx, [rsp+390h+var_358]
0x180016a6e  cmp     [rbx-10h], r12d
0x180016a72  jnz     short loc_180016A9E
0x180016a74  lea     rdx, [rbx-18h]
0x180016a78  mov     eax, edi
0x180016a7a  lock xadd [rdx+10h], eax
0x180016a7f  add     eax, edi
0x180016a81  test    eax, eax
0x180016a83  jg      short loc_180016A94
0x180016a85  mov     rcx, [rdx]
0x180016a88  mov     rax, [rcx]
0x180016a8b  mov     rax, [rax+8]
0x180016a8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a94  mov     eax, 80004005h
0x180016a99  jmp     loc_180016E4D
0x180016a9e  lea     r14, [r13+28h]
0x180016aa2  lea     rdx, [rsp+390h+var_358]
0x180016aa7  mov     rcx, r14
0x180016aaa  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180016aaf  mov     rcx, r14
0x180016ab2  call    ?Replace@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEBG0@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Replace(ushort const *,ushort const *)
0x180016ab7  lea     rdx, [rsp+390h+var_358]
0x180016abc  lea     rcx, [r13+30h]
0x180016ac0  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180016ac5  nop
0x180016ac6  lea     rdx, [rbx-18h]
0x180016aca  mov     eax, edi
0x180016acc  lock xadd [rdx+10h], eax
0x180016ad1  add     eax, edi
0x180016ad3  test    eax, eax
0x180016ad5  jg      short loc_180016AE6
0x180016ad7  mov     rcx, [rdx]
0x180016ada  mov     rax, [rcx]
0x180016add  mov     rax, [rax+8]
0x180016ae1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ae6  lea     rsi, [r13+38h]
0x180016aea  lea     rdx, aXperfNgenpdbsp; "XPERF_NGenPdbsPath"
0x180016af1  mov     rcx, rsi
0x180016af4  call    ?GetEnvironmentVariableW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::GetEnvironmentVariableW(ushort const *)
0x180016af9  test    eax, eax
0x180016afb  jz      short loc_180016B0A
0x180016afd  mov     rax, [rsi]
0x180016b00  cmp     [rax-10h], r12d
0x180016b04  jnz     loc_180016DF6
0x180016b0a  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180016b11  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180016b18  mov     rax, [rax+18h]
0x180016b1c  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
