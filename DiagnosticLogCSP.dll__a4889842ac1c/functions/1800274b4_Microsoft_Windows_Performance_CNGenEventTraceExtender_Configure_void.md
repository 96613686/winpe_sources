# Microsoft::Windows::Performance::CNGenEventTraceExtender::Configure(void)

- ea: `0x1800274b4`
- end: `0x180027c7c`
- name: `?Configure@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEAAJXZ`
- size: `1992`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CNGenEventTraceExtender *__hidden this)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180026c3c`

## callees

- `0x180001b60`
- `0x180001bc8`
- `0x180010db8`
- `0x180015710`
- `0x180016440`
- `0x180019260`
- `0x18001f65c`
- `0x180022394`
- `0x180022c40`
- `0x1800231dc`
- `0x180023c6c`
- `0x180024d20`
- `0x1800267d0`
- `0x1800271c8`
- `0x1800274b4`
- `0x180029028`
- `0x180029768`
- `0x180037010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002797d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800279b8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180027b15`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180027b3e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002797d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800279b8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180027b15`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180027b3e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180027554`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800275b1`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180027863`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180027554`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800275b1`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180027863`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180027b5a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180027b5a`

## string_xrefs

- `0x18002792a`: `_NT_SYMBOL_PATH`
- `0x18002750c`: `mscoree.dll`
- `0x180027529`: `CLRCreateInstance`
- `0x1800278ea`: `XPERF_NGenPdbsPath`
- `0x180027bfb`: `XPERF_NGenPdbsCachePath`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Performance::CNGenEventTraceExtender::Configure(
        Microsoft::Windows::Performance::CNGenEventTraceExtender *this)
{
  __int64 v2; // rbx
  FARPROC v3; // rax
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
  if ( !Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)((__int64 *)&v47) )
  {
    if ( hLibModule[0] )
      FreeLibrary(hLibModule[0]);
    goto LABEL_62;
  }
  v33 = 0;
  v3 = Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)((__int64 *)&v47);
  v4 = ((__int64 (__fastcall *)(GUID *, GUID *, __int64 *))v3)(&CLSID_CLRMetaHost, &IID_ICLRMetaHost, &v33);
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
0x1800274b4  push    rbp
0x1800274b6  push    rbx
0x1800274b7  push    rsi
0x1800274b8  push    rdi
0x1800274b9  push    r12
0x1800274bb  push    r13
0x1800274bd  push    r14
0x1800274bf  push    r15
0x1800274c1  lea     rbp, [rsp-258h]
0x1800274c9  sub     rsp, 358h
0x1800274d0  mov     rax, cs:__security_cookie
0x1800274d7  xor     rax, rsp
0x1800274da  mov     [rbp+290h+var_50], rax
0x1800274e1  mov     r13, rcx
0x1800274e4  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800274eb  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800274f2  mov     rax, [rax+18h]
0x1800274f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800274fb  lea     rbx, [rax+18h]
0x1800274ff  mov     [rsp+390h+var_358], rbx
0x180027504  xor     r12d, r12d
0x180027507  mov     [rsp+390h+hLibModule], r12
0x18002750c  lea     rax, aMscoreeDll; "mscoree.dll"
0x180027513  mov     [rsp+390h+var_318], rax
0x180027518  mov     [rbp+290h+var_310], r12
0x18002751c  mov     [rbp+290h+var_308], r12b
0x180027520  lea     rax, [rsp+390h+hLibModule]
0x180027525  mov     [rbp+290h+var_2A8], rax
0x180027529  lea     rax, aClrcreateinsta; "CLRCreateInstance"
0x180027530  mov     [rbp+290h+Block], rax
0x180027534  mov     [rbp+290h+Block+8], r12
0x180027538  mov     byte ptr [rbp+290h+var_290], r12b
0x18002753c  lea     rcx, [rbp+290h+var_2A8]
0x180027540  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x180027545  test    rax, rax
0x180027548  jnz     short loc_180027564
0x18002754a  mov     rcx, [rsp+390h+hLibModule]; hLibModule
0x18002754f  test    rcx, rcx
0x180027552  jz      short loc_18002755B
0x180027554  call    cs:__imp_FreeLibrary
0x18002755a  nop
0x18002755b  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18002755f  jmp     loc_180027874
0x180027564  mov     [rsp+390h+var_330], r12
0x180027569  lea     rcx, [rbp+290h+var_2A8]
0x18002756d  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x180027572  lea     r8, [rsp+390h+var_330]
0x180027577  lea     rdx, IID_ICLRMetaHost
0x18002757e  lea     rcx, CLSID_CLRMetaHost
0x180027585  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002758a  mov     esi, eax
0x18002758c  test    eax, eax
0x18002758e  jns     short loc_1800275E3
0x180027590  mov     rcx, [rsp+390h+var_330]
0x180027595  test    rcx, rcx
0x180027598  jz      short loc_1800275A7
0x18002759a  mov     rdx, [rcx]
0x18002759d  mov     rax, [rdx+10h]
0x1800275a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800275a6  nop
0x1800275a7  mov     rcx, [rsp+390h+hLibModule]; hLibModule
0x1800275ac  test    rcx, rcx
0x1800275af  jz      short loc_1800275B8
0x1800275b1  call    cs:__imp_FreeLibrary
0x1800275b7  nop
0x1800275b8  lea     rdx, [rbx-18h]
0x1800275bc  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800275c0  mov     eax, edi
0x1800275c2  lock xadd [rdx+10h], eax
0x1800275c7  add     eax, edi
0x1800275c9  test    eax, eax
0x1800275cb  jg      short loc_1800275DC
0x1800275cd  mov     rcx, [rdx]
0x1800275d0  mov     rax, [rcx]
0x1800275d3  mov     rax, [rax+8]
0x1800275d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800275dc  mov     eax, esi
0x1800275de  jmp     loc_180027C4E
0x1800275e3  mov     [rsp+390h+var_340], r12
0x1800275e8  mov     rcx, [rsp+390h+var_330]
0x1800275ed  mov     rax, [rcx]
0x1800275f0  lea     rdx, [rsp+390h+var_340]
0x1800275f5  mov     rax, [rax+28h]
0x1800275f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800275fe  mov     esi, eax
0x180027600  test    eax, eax
0x180027602  jns     short loc_180027637
0x180027604  mov     rcx, [rsp+390h+var_340]
0x180027609  test    rcx, rcx
0x18002760c  jz      short loc_18002761B
0x18002760e  mov     rdx, [rcx]
0x180027611  mov     rax, [rdx+10h]
0x180027615  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002761a  nop
0x18002761b  mov     rcx, [rsp+390h+var_330]
0x180027620  test    rcx, rcx
0x180027623  jz      short loc_180027632
0x180027625  mov     rax, [rcx]
0x180027628  mov     rax, [rax+10h]
0x18002762c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027631  nop
0x180027632  jmp     loc_1800275A7
0x180027637  mov     [rsp+390h+var_328], r12
0x18002763c  mov     [rsp+390h+var_338], r12d
0x180027641  mov     r14d, r12d
0x180027644  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180027648  mov     rcx, [rsp+390h+var_340]
0x18002764d  mov     rax, [rcx]
0x180027650  lea     r9, [rsp+390h+var_338]
0x180027655  lea     r8, [rsp+390h+var_328]
0x18002765a  mov     edx, 1
0x18002765f  mov     rax, [rax+18h]
0x180027663  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027668  test    eax, eax
0x18002766a  js      loc_180027814
0x180027670  cmp     [rsp+390h+var_338], 1
0x180027675  jnz     loc_180027814
0x18002767b  mov     rbx, [rsp+390h+var_328]
0x180027680  mov     [rsp+390h+var_328], r12
0x180027685  mov     [rbp+290h+var_2B0], rbx
0x180027689  mov     rcx, r12
0x18002768c  mov     [rsp+390h+var_348], rcx
0x180027691  test    rbx, rbx
0x180027694  jz      short loc_1800276B5
0x180027696  mov     rax, [rbx]
0x180027699  lea     r8, [rsp+390h+var_348]
0x18002769e  lea     rdx, _GUID_bd39d1d2_ba2f_486a_89b0_b4b0cb466891
0x1800276a5  mov     rcx, rbx
0x1800276a8  mov     rax, [rax]
0x1800276ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800276b0  mov     rcx, [rsp+390h+var_348]
0x1800276b5  test    rcx, rcx
0x1800276b8  jnz     short loc_1800276D4
0x1800276ba  test    rbx, rbx
0x1800276bd  jz      short loc_1800276CF
0x1800276bf  mov     rax, [rbx]
0x1800276c2  mov     rcx, rbx
0x1800276c5  mov     rax, [rax+10h]
0x1800276c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800276ce  nop
0x1800276cf  jmp     loc_180027648
0x1800276d4  mov     dword ptr [rsp+390h+var_360], 1Eh
0x1800276dc  mov     rax, [rcx]
0x1800276df  lea     r8, [rsp+390h+var_360]
0x1800276e4  lea     rdx, [rbp+290h+var_2A8]
0x1800276e8  mov     rax, [rax+18h]
0x1800276ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800276f1  test    eax, eax
0x1800276f3  jns     short loc_180027726
0x1800276f5  mov     rcx, [rsp+390h+var_348]
0x1800276fa  test    rcx, rcx
0x1800276fd  jz      short loc_18002770C
0x1800276ff  mov     rax, [rcx]
0x180027702  mov     rax, [rax+10h]
0x180027706  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002770b  nop
0x18002770c  test    rbx, rbx
0x18002770f  jz      short loc_180027721
0x180027711  mov     rax, [rbx]
0x180027714  mov     rcx, rbx
0x180027717  mov     rax, [rax+10h]
0x18002771b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027720  nop
0x180027721  jmp     loc_180027648
0x180027726  cmp     dword ptr [rsp+390h+var_360], 3
0x18002772b  jb      loc_1800277E3
0x180027731  movzx   eax, word ptr [rbp+290h+var_2A8]
0x180027735  sub     ax, 56h ; 'V'
0x180027739  mov     ecx, 0FFDFh
0x18002773e  test    cx, ax
0x180027741  jnz     loc_1800277E3
0x180027747  movzx   esi, word ptr [rbp+290h+var_2A8+2]
0x18002774b  lea     eax, [rsi-34h]
0x18002774e  cmp     ax, 5
0x180027752  ja      loc_1800277E3
0x180027758  cmp     word ptr [rbp+290h+var_2A8+4], 2Eh ; '.'
0x18002775d  jnz     loc_1800277E3
0x180027763  cmp     si, r14w
0x180027767  jbe     short loc_1800277E3
0x180027769  mov     [rsp+390h+var_350], 104h
0x180027771  mov     rcx, [rsp+390h+var_348]
0x180027776  mov     rax, [rcx]
0x180027779  lea     r8, [rsp+390h+var_350]
0x18002777e  lea     rdx, [rbp+290h+Buffer]
0x180027782  mov     rax, [rax+20h]
0x180027786  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002778b  test    eax, eax
0x18002778d  jns     short loc_1800277C0
0x18002778f  mov     rcx, [rsp+390h+var_348]
0x180027794  test    rcx, rcx
0x180027797  jz      short loc_1800277A6
0x180027799  mov     rax, [rcx]
0x18002779c  mov     rax, [rax+10h]
0x1800277a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800277a5  nop
0x1800277a6  test    rbx, rbx
0x1800277a9  jz      short loc_1800277BB
0x1800277ab  mov     rax, [rbx]
0x1800277ae  mov     rcx, rbx
0x1800277b1  mov     rax, [rax+10h]
0x1800277b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800277ba  nop
0x1800277bb  jmp     loc_180027648
0x1800277c0  lea     rax, [rbp+290h+Buffer]
0x1800277c4  mov     r8, rdi
0x1800277c7  inc     r8
0x1800277ca  cmp     [rax+r8*2], r12w
0x1800277cf  jnz     short loc_1800277C7
0x1800277d1  lea     rdx, [rbp+290h+Buffer]
0x1800277d5  lea     rcx, [rsp+390h+var_358]
0x1800277da  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1800277df  movzx   r14d, si
0x1800277e3  mov     rcx, [rsp+390h+var_348]
0x1800277e8  test    rcx, rcx
0x1800277eb  jz      short loc_1800277FA
0x1800277ed  mov     rax, [rcx]
0x1800277f0  mov     rax, [rax+10h]
0x1800277f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800277f9  nop
0x1800277fa  test    rbx, rbx
0x1800277fd  jz      short loc_18002780F
0x1800277ff  mov     rax, [rbx]
0x180027802  mov     rcx, rbx
0x180027805  mov     rax, [rax+10h]
0x180027809  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002780e  nop
0x18002780f  jmp     loc_180027648
0x180027814  mov     rcx, [rsp+390h+var_328]
0x180027819  test    rcx, rcx
0x18002781c  jz      short loc_18002782B
0x18002781e  mov     rax, [rcx]
0x180027821  mov     rax, [rax+10h]
0x180027825  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002782a  nop
0x18002782b  mov     rcx, [rsp+390h+var_340]
0x180027830  test    rcx, rcx
0x180027833  jz      short loc_180027842
0x180027835  mov     rax, [rcx]
0x180027838  mov     rax, [rax+10h]
0x18002783c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027841  nop
0x180027842  mov     rcx, [rsp+390h+var_330]
0x180027847  test    rcx, rcx
0x18002784a  jz      short loc_180027859
0x18002784c  mov     rax, [rcx]
0x18002784f  mov     rax, [rax+10h]
0x180027853  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027858  nop
0x180027859  mov     rcx, [rsp+390h+hLibModule]; hLibModule
0x18002785e  test    rcx, rcx
0x180027861  jz      short loc_180027869
0x180027863  call    cs:__imp_FreeLibrary
0x180027869  mov     rbx, [rsp+390h+var_358]
0x18002786e  cmp     [rbx-10h], r12d
0x180027872  jnz     short loc_18002789E
0x180027874  lea     rdx, [rbx-18h]
0x180027878  mov     eax, edi
0x18002787a  lock xadd [rdx+10h], eax
0x18002787f  add     eax, edi
0x180027881  test    eax, eax
0x180027883  jg      short loc_180027894
0x180027885  mov     rcx, [rdx]
0x180027888  mov     rax, [rcx]
0x18002788b  mov     rax, [rax+8]
0x18002788f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027894  mov     eax, 80004005h
0x180027899  jmp     loc_180027C4E
0x18002789e  lea     r14, [r13+28h]
0x1800278a2  lea     rdx, [rsp+390h+var_358]
0x1800278a7  mov     rcx, r14
0x1800278aa  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1800278af  mov     rcx, r14
0x1800278b2  call    ?Replace@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEBG0@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Replace(ushort const *,ushort const *)
0x1800278b7  lea     rdx, [rsp+390h+var_358]
0x1800278bc  lea     rcx, [r13+30h]
0x1800278c0  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1800278c5  nop
0x1800278c6  lea     rdx, [rbx-18h]
0x1800278ca  mov     eax, edi
0x1800278cc  lock xadd [rdx+10h], eax
0x1800278d1  add     eax, edi
0x1800278d3  test    eax, eax
0x1800278d5  jg      short loc_1800278E6
0x1800278d7  mov     rcx, [rdx]
0x1800278da  mov     rax, [rcx]
0x1800278dd  mov     rax, [rax+8]
0x1800278e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800278e6  lea     rsi, [r13+38h]
0x1800278ea  lea     rdx, aXperfNgenpdbsp; "XPERF_NGenPdbsPath"
0x1800278f1  mov     rcx, rsi
0x1800278f4  call    ?GetEnvironmentVariableW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::GetEnvironmentVariableW(ushort const *)
0x1800278f9  test    eax, eax
0x1800278fb  jz      short loc_18002790A
0x1800278fd  mov     rax, [rsi]
0x180027900  cmp     [rax-10h], r12d
0x180027904  jnz     loc_180027BF7
0x18002790a  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180027911  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180027918  mov     rax, [rax+18h]
0x18002791c  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
