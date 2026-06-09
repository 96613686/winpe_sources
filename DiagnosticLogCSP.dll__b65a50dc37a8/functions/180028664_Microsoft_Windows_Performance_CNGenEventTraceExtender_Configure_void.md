# Microsoft::Windows::Performance::CNGenEventTraceExtender::Configure(void)

- ea: `0x180028664`
- end: `0x180028e61`
- name: `?Configure@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEAAJXZ`
- size: `2045`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CNGenEventTraceExtender *__hidden this)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180027db4`

## callees

- `0x180001b90`
- `0x180001bf8`
- `0x180011648`
- `0x180016274`
- `0x180017000`
- `0x18001a030`
- `0x180020678`
- `0x1800232e0`
- `0x180023c9c`
- `0x18002428c`
- `0x180024e18`
- `0x180025e80`
- `0x1800279b0`
- `0x18002834c`
- `0x180028664`
- `0x18002a1a8`
- `0x18002a9e8`
- `0x180039010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180028b43`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180028b84`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180028ce7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180028d16`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180028b43`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180028b84`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180028ce7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180028d16`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180028704`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180028767`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180028a1f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180028704`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180028767`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180028a1f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180028d38`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180028d38`

## string_xrefs

- `0x180028aec`: `_NT_SYMBOL_PATH`
- `0x1800286bc`: `mscoree.dll`
- `0x1800286d9`: `CLRCreateInstance`
- `0x180028aac`: `XPERF_NGenPdbsPath`
- `0x180028ddf`: `XPERF_NGenPdbsCachePath`

## pseudocode

```c
// Hidden C++ exception states: #wind=22
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
  unsigned __int64 v20; // rdx
  unsigned int Error; // ebx
  _QWORD *v22; // rdx
  unsigned __int64 v23; // rax
  _QWORD *v24; // rdx
  _QWORD *v25; // rbx
  int v26; // edx
  int v27; // ecx
  __int64 v28; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v29; // [rsp+38h] [rbp-C8h] BYREF
  int v30; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v31; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v32; // [rsp+50h] [rbp-B0h] BYREF
  int v33; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v34; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v35; // [rsp+68h] [rbp-98h] BYREF
  HMODULE hLibModule[3]; // [rsp+70h] [rbp-90h] BYREF
  char v37; // [rsp+88h] [rbp-78h]
  int v38; // [rsp+90h] [rbp-70h] BYREF
  __int64 v39; // [rsp+98h] [rbp-68h]
  __int64 v40; // [rsp+A0h] [rbp-60h]
  void *v41; // [rsp+A8h] [rbp-58h]
  void *v42; // [rsp+B0h] [rbp-50h]
  void *v43; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v44; // [rsp+C0h] [rbp-40h]
  int v45; // [rsp+D0h] [rbp-30h]
  __int64 v46; // [rsp+D8h] [rbp-28h]
  __int64 v47; // [rsp+E0h] [rbp-20h]
  HMODULE *v48; // [rsp+E8h] [rbp-18h] BYREF
  void *Block[2]; // [rsp+F0h] [rbp-10h]
  __int64 v50; // [rsp+100h] [rbp+0h]
  int v51; // [rsp+108h] [rbp+8h]
  __int64 v52; // [rsp+110h] [rbp+10h]
  int v53; // [rsp+118h] [rbp+18h]
  WCHAR Buffer[264]; // [rsp+130h] [rbp+30h] BYREF

  v2 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v29 = v2;
  hLibModule[0] = 0;
  hLibModule[1] = (HMODULE)L"mscoree.dll";
  hLibModule[2] = 0;
  v37 = 0;
  v48 = hLibModule;
  Block[0] = "CLRCreateInstance";
  Block[1] = 0;
  LOBYTE(v50) = 0;
  if ( !Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)(&v48) )
  {
    if ( hLibModule[0] )
      FreeLibrary(hLibModule[0]);
    goto LABEL_62;
  }
  v34 = 0;
  v3 = (__int64 (__fastcall *)(GUID *, GUID *, __int64 *))Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)(&v48);
  v4 = v3(&CLSID_CLRMetaHost, &IID_ICLRMetaHost, &v34);
  if ( v4 < 0 )
  {
    if ( v34 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
LABEL_8:
    if ( hLibModule[0] )
      FreeLibrary(hLibModule[0]);
    if ( _InterlockedDecrement((volatile signed __int32 *)(v2 - 24 + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v2 - 24) + 8LL))(*(_QWORD *)(v2 - 24));
    return (unsigned int)v4;
  }
  v32 = 0;
  v4 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v34 + 40LL))(v34, &v32);
  if ( v4 < 0 )
  {
    if ( v32 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    if ( v34 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    goto LABEL_8;
  }
  v35 = 0;
  v33 = 0;
  v6 = 0;
  while ( (*(int (__fastcall **)(__int64, __int64, __int64 *, int *))(*(_QWORD *)v32 + 24LL))(v32, 1, &v35, &v33) >= 0
       && v33 == 1 )
  {
    v7 = v35;
    v35 = 0;
    v47 = v7;
    v8 = 0;
    v31 = 0;
    if ( v7 )
    {
      (**(void (__fastcall ***)(__int64, GUID *, __int64 *))v7)(v7, &GUID_bd39d1d2_ba2f_486a_89b0_b4b0cb466891, &v31);
      v8 = v31;
    }
    if ( v8 )
    {
      LODWORD(v28) = 30;
      if ( (*(int (__fastcall **)(__int64, HMODULE **, __int64 *))(*(_QWORD *)v8 + 24LL))(v8, &v48, &v28) >= 0 )
      {
        if ( (unsigned int)v28 < 3
          || (((_WORD)v48 - 86) & 0xFFDF) != 0
          || (v9 = WORD1(v48), (unsigned __int16)(WORD1(v48) - 52) > 5u)
          || WORD2(v48) != 46
          || WORD1(v48) <= v6 )
        {
LABEL_48:
          if ( v31 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
          if ( v7 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
        }
        else
        {
          v30 = 260;
          if ( (*(int (__fastcall **)(__int64, WCHAR *, int *))(*(_QWORD *)v31 + 32LL))(v31, Buffer, &v30) >= 0 )
          {
            v10 = -1;
            do
              ++v10;
            while ( Buffer[v10] );
            ATL::CSimpleStringT<unsigned short,0>::SetString(&v29, Buffer, v10);
            v6 = v9;
            goto LABEL_48;
          }
          if ( v31 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
          if ( v7 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
        }
      }
      else
      {
        if ( v31 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
        if ( v7 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
      }
    }
    else if ( v7 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    }
  }
  if ( v35 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
  if ( v32 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
  if ( v34 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
  if ( hLibModule[0] )
    FreeLibrary(hLibModule[0]);
  v2 = v29;
  if ( !*(_DWORD *)(v29 - 16) )
  {
LABEL_62:
    if ( _InterlockedDecrement((volatile signed __int32 *)(v2 - 24 + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v2 - 24) + 8LL))(*(_QWORD *)(v2 - 24));
    return 2147500037LL;
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
    (char *)this + 40,
    &v29);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Replace((char *)this + 40);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
    (char *)this + 48,
    &v29);
  if ( _InterlockedDecrement((volatile signed __int32 *)(v2 - 24 + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v2 - 24) + 8LL))(*(_QWORD *)(v2 - 24));
  v11 = (_QWORD *)((char *)this + 56);
  if ( (unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::GetEnvironmentVariableW(
                       (char *)this + 56,
                       L"XPERF_NGenPdbsPath")
    && *(_DWORD *)(*v11 - 16LL) )
  {
LABEL_109:
    v25 = (_QWORD *)((char *)this + 64);
    if ( !(unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::GetEnvironmentVariableW(
                          (char *)this + 64,
                          L"XPERF_NGenPdbsCachePath")
      || !*(_DWORD *)(*v25 - 16LL) )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
        (char *)this + 64,
        (char *)this + 56);
    }
    *((_BYTE *)this + 32) = 1;
    if ( (Microsoft_Windows_XPerfCoreEnableBits & 1) != 0 )
      McTemplateU0zzzz_EventWriteTransfer(v27, v26, *v11, *v25, *((_QWORD *)this + 5), *((_QWORD *)this + 6));
    return 0;
  }
  v28 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  if ( !(unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::GetEnvironmentVariableW(
                        &v28,
                        L"_NT_SYMBOL_PATH") )
  {
LABEL_97:
    if ( !*(_DWORD *)(*v11 - 16LL) )
    {
      if ( !GetSystemWindowsDirectoryW(Buffer, 0x105u) )
      {
        Error = ATL::AtlHresultFromLastError();
        v22 = (_QWORD *)(v28 - 24);
        if ( _InterlockedDecrement((volatile signed __int32 *)(v28 - 24 + 16)) <= 0 )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v22 + 8LL))(*v22);
        return Error;
      }
      v23 = -1;
      do
        ++v23;
      while ( Buffer[v23] );
      if ( v23 < 2 || Buffer[1] != 58 )
        goto LABEL_74;
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
        (char *)this + 56,
        L"%wc:\\Symbols",
        Buffer[0]);
    }
    v24 = (_QWORD *)(v28 - 24);
    if ( _InterlockedDecrement((volatile signed __int32 *)(v28 - 24 + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v24 + 8LL))(*v24);
    goto LABEL_109;
  }
  *(_OWORD *)Block = 0;
  v50 = 0;
  v51 = 0;
  v52 = 0;
  v53 = 1;
  LODWORD(v48) = 0;
  v12 = ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::Parse(&v48);
  if ( !v12 )
  {
    v41 = 0;
    v42 = 0;
    v43 = 0;
    v44 = 0;
    v45 = 0;
    v38 = 0;
    v46 = 0;
    if ( (unsigned __int8)ATL::CAtlArray<void *,ATL::CElementTraits<void *>>::GrowBuffer(&v43, 256) )
    {
      ATL::CAtlArray<void *,ATL::CElementTraits<void *>>::CallConstructors();
      *(_QWORD *)&v44 = 256;
    }
    v39 = 0;
    v40 = 0;
    v30 = 0;
    v29 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
    while ( 1 )
    {
      v16 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Tokenize(
              &v28,
              &v32,
              v15,
              &v30);
      v17 = *(_DWORD *)(*(_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
                                     &v29,
                                     v16)
                      - 16LL);
      v18 = (_QWORD *)(v32 - 24);
      if ( _InterlockedDecrement((volatile signed __int32 *)(v32 - 24 + 16)) <= 0 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v18 + 8LL))(*v18);
      if ( !v17 )
        break;
      if ( (unsigned int)ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::Match(&v48, v29, &v38, 0) )
      {
        if ( !v38 )
          ATL::AtlThrowImpl(-2147467259);
        ATL::CSimpleStringT<unsigned short,0>::SetString(
          (char *)this + 56,
          *(_QWORD *)v42,
          (__int64)(*((_QWORD *)v42 + 1) - *(_QWORD *)v42) >> 1);
        break;
      }
    }
    v19 = (_QWORD *)(v29 - 24);
    if ( _InterlockedDecrement((volatile signed __int32 *)(v29 - 24 + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v19 + 8LL))(*v19);
    if ( v43 )
      free(v43);
    operator delete(v42, (unsigned __int64)v19);
    v42 = 0;
    operator delete(v41, v20);
    v41 = 0;
    if ( Block[0] )
      free(Block[0]);
    goto LABEL_97;
  }
  if ( v12 == 1 )
  {
    if ( Block[0] )
      free(Block[0]);
    v14 = (_QWORD *)(v28 - 24);
    if ( _InterlockedDecrement((volatile signed __int32 *)(v28 - 24 + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v14 + 8LL))(*v14);
    return 2147942414LL;
  }
  else
  {
    if ( Block[0] )
      free(Block[0]);
LABEL_74:
    v13 = (_QWORD *)(v28 - 24);
    if ( _InterlockedDecrement((volatile signed __int32 *)(v28 - 24 + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v13 + 8LL))(*v13);
    return 2147549183LL;
  }
}

```

## disassembly

```asm
0x180028664  push    rbp
0x180028666  push    rbx
0x180028667  push    rsi
0x180028668  push    rdi
0x180028669  push    r12
0x18002866b  push    r13
0x18002866d  push    r14
0x18002866f  push    r15
0x180028671  lea     rbp, [rsp-258h]
0x180028679  sub     rsp, 358h
0x180028680  mov     rax, cs:__security_cookie
0x180028687  xor     rax, rsp
0x18002868a  mov     [rbp+290h+var_50], rax
0x180028691  mov     r13, rcx
0x180028694  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18002869b  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800286a2  mov     rax, [rax+18h]
0x1800286a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800286ab  lea     rbx, [rax+18h]
0x1800286af  mov     [rsp+390h+var_358], rbx
0x1800286b4  xor     r12d, r12d
0x1800286b7  mov     [rsp+390h+hLibModule], r12
0x1800286bc  lea     rax, aMscoreeDll; "mscoree.dll"
0x1800286c3  mov     [rsp+390h+var_318], rax
0x1800286c8  mov     [rbp+290h+var_310], r12
0x1800286cc  mov     [rbp+290h+var_308], r12b
0x1800286d0  lea     rax, [rsp+390h+hLibModule]
0x1800286d5  mov     [rbp+290h+var_2A8], rax
0x1800286d9  lea     rax, aClrcreateinsta; "CLRCreateInstance"
0x1800286e0  mov     [rbp+290h+Block], rax
0x1800286e4  mov     [rbp+290h+Block+8], r12
0x1800286e8  mov     byte ptr [rbp+290h+var_290], r12b
0x1800286ec  lea     rcx, [rbp+290h+var_2A8]
0x1800286f0  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x1800286f5  test    rax, rax
0x1800286f8  jnz     short loc_18002871A
0x1800286fa  mov     rcx, [rsp+390h+hLibModule]; hLibModule
0x1800286ff  test    rcx, rcx
0x180028702  jz      short loc_180028711
0x180028704  call    cs:__imp_FreeLibrary
0x18002870b  nop     dword ptr [rax+rax+00h]
0x180028710  nop
0x180028711  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180028715  jmp     loc_180028A36
0x18002871a  mov     [rsp+390h+var_330], r12
0x18002871f  lea     rcx, [rbp+290h+var_2A8]
0x180028723  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x180028728  lea     r8, [rsp+390h+var_330]
0x18002872d  lea     rdx, IID_ICLRMetaHost
0x180028734  lea     rcx, CLSID_CLRMetaHost
0x18002873b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028740  mov     esi, eax
0x180028742  test    eax, eax
0x180028744  jns     short loc_18002879F
0x180028746  mov     rcx, [rsp+390h+var_330]
0x18002874b  test    rcx, rcx
0x18002874e  jz      short loc_18002875D
0x180028750  mov     rdx, [rcx]
0x180028753  mov     rax, [rdx+10h]
0x180028757  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002875c  nop
0x18002875d  mov     rcx, [rsp+390h+hLibModule]; hLibModule
0x180028762  test    rcx, rcx
0x180028765  jz      short loc_180028774
0x180028767  call    cs:__imp_FreeLibrary
0x18002876e  nop     dword ptr [rax+rax+00h]
0x180028773  nop
0x180028774  lea     rdx, [rbx-18h]
0x180028778  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18002877c  mov     eax, edi
0x18002877e  lock xadd [rdx+10h], eax
0x180028783  add     eax, edi
0x180028785  test    eax, eax
0x180028787  jg      short loc_180028798
0x180028789  mov     rcx, [rdx]
0x18002878c  mov     rax, [rcx]
0x18002878f  mov     rax, [rax+8]
0x180028793  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028798  mov     eax, esi
0x18002879a  jmp     loc_180028E32
0x18002879f  mov     [rsp+390h+var_340], r12
0x1800287a4  mov     rcx, [rsp+390h+var_330]
0x1800287a9  mov     rax, [rcx]
0x1800287ac  lea     rdx, [rsp+390h+var_340]
0x1800287b1  mov     rax, [rax+28h]
0x1800287b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800287ba  mov     esi, eax
0x1800287bc  test    eax, eax
0x1800287be  jns     short loc_1800287F3
0x1800287c0  mov     rcx, [rsp+390h+var_340]
0x1800287c5  test    rcx, rcx
0x1800287c8  jz      short loc_1800287D7
0x1800287ca  mov     rdx, [rcx]
0x1800287cd  mov     rax, [rdx+10h]
0x1800287d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800287d6  nop
0x1800287d7  mov     rcx, [rsp+390h+var_330]
0x1800287dc  test    rcx, rcx
0x1800287df  jz      short loc_1800287EE
0x1800287e1  mov     rax, [rcx]
0x1800287e4  mov     rax, [rax+10h]
0x1800287e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800287ed  nop
0x1800287ee  jmp     loc_18002875D
0x1800287f3  mov     [rsp+390h+var_328], r12
0x1800287f8  mov     [rsp+390h+var_338], r12d
0x1800287fd  mov     r14d, r12d
0x180028800  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180028804  mov     rcx, [rsp+390h+var_340]
0x180028809  mov     rax, [rcx]
0x18002880c  lea     r9, [rsp+390h+var_338]
0x180028811  lea     r8, [rsp+390h+var_328]
0x180028816  mov     edx, 1
0x18002881b  mov     rax, [rax+18h]
0x18002881f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028824  test    eax, eax
0x180028826  js      loc_1800289D0
0x18002882c  cmp     [rsp+390h+var_338], 1
0x180028831  jnz     loc_1800289D0
0x180028837  mov     rbx, [rsp+390h+var_328]
0x18002883c  mov     [rsp+390h+var_328], r12
0x180028841  mov     [rbp+290h+var_2B0], rbx
0x180028845  mov     rcx, r12
0x180028848  mov     [rsp+390h+var_348], rcx
0x18002884d  test    rbx, rbx
0x180028850  jz      short loc_180028871
0x180028852  mov     rax, [rbx]
0x180028855  lea     r8, [rsp+390h+var_348]
0x18002885a  lea     rdx, _GUID_bd39d1d2_ba2f_486a_89b0_b4b0cb466891
0x180028861  mov     rcx, rbx
0x180028864  mov     rax, [rax]
0x180028867  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002886c  mov     rcx, [rsp+390h+var_348]
0x180028871  test    rcx, rcx
0x180028874  jnz     short loc_180028890
0x180028876  test    rbx, rbx
0x180028879  jz      short loc_18002888B
0x18002887b  mov     rax, [rbx]
0x18002887e  mov     rcx, rbx
0x180028881  mov     rax, [rax+10h]
0x180028885  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002888a  nop
0x18002888b  jmp     loc_180028804
0x180028890  mov     dword ptr [rsp+390h+var_360], 1Eh
0x180028898  mov     rax, [rcx]
0x18002889b  lea     r8, [rsp+390h+var_360]
0x1800288a0  lea     rdx, [rbp+290h+var_2A8]
0x1800288a4  mov     rax, [rax+18h]
0x1800288a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800288ad  test    eax, eax
0x1800288af  jns     short loc_1800288E2
0x1800288b1  mov     rcx, [rsp+390h+var_348]
0x1800288b6  test    rcx, rcx
0x1800288b9  jz      short loc_1800288C8
0x1800288bb  mov     rax, [rcx]
0x1800288be  mov     rax, [rax+10h]
0x1800288c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800288c7  nop
0x1800288c8  test    rbx, rbx
0x1800288cb  jz      short loc_1800288DD
0x1800288cd  mov     rax, [rbx]
0x1800288d0  mov     rcx, rbx
0x1800288d3  mov     rax, [rax+10h]
0x1800288d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800288dc  nop
0x1800288dd  jmp     loc_180028804
0x1800288e2  cmp     dword ptr [rsp+390h+var_360], 3
0x1800288e7  jb      loc_18002899F
0x1800288ed  movzx   eax, word ptr [rbp+290h+var_2A8]
0x1800288f1  sub     ax, 56h ; 'V'
0x1800288f5  mov     ecx, 0FFDFh
0x1800288fa  test    cx, ax
0x1800288fd  jnz     loc_18002899F
0x180028903  movzx   esi, word ptr [rbp+290h+var_2A8+2]
0x180028907  lea     eax, [rsi-34h]
0x18002890a  cmp     ax, 5
0x18002890e  ja      loc_18002899F
0x180028914  cmp     word ptr [rbp+290h+var_2A8+4], 2Eh ; '.'
0x180028919  jnz     loc_18002899F
0x18002891f  cmp     si, r14w
0x180028923  jbe     short loc_18002899F
0x180028925  mov     [rsp+390h+var_350], 104h
0x18002892d  mov     rcx, [rsp+390h+var_348]
0x180028932  mov     rax, [rcx]
0x180028935  lea     r8, [rsp+390h+var_350]
0x18002893a  lea     rdx, [rbp+290h+Buffer]
0x18002893e  mov     rax, [rax+20h]
0x180028942  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028947  test    eax, eax
0x180028949  jns     short loc_18002897C
0x18002894b  mov     rcx, [rsp+390h+var_348]
0x180028950  test    rcx, rcx
0x180028953  jz      short loc_180028962
0x180028955  mov     rax, [rcx]
0x180028958  mov     rax, [rax+10h]
0x18002895c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028961  nop
0x180028962  test    rbx, rbx
0x180028965  jz      short loc_180028977
0x180028967  mov     rax, [rbx]
0x18002896a  mov     rcx, rbx
0x18002896d  mov     rax, [rax+10h]
0x180028971  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028976  nop
0x180028977  jmp     loc_180028804
0x18002897c  lea     rax, [rbp+290h+Buffer]
0x180028980  mov     r8, rdi
0x180028983  inc     r8
0x180028986  cmp     [rax+r8*2], r12w
0x18002898b  jnz     short loc_180028983
0x18002898d  lea     rdx, [rbp+290h+Buffer]
0x180028991  lea     rcx, [rsp+390h+var_358]
0x180028996  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18002899b  movzx   r14d, si
0x18002899f  mov     rcx, [rsp+390h+var_348]
0x1800289a4  test    rcx, rcx
0x1800289a7  jz      short loc_1800289B6
0x1800289a9  mov     rax, [rcx]
0x1800289ac  mov     rax, [rax+10h]
0x1800289b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800289b5  nop
0x1800289b6  test    rbx, rbx
0x1800289b9  jz      short loc_1800289CB
0x1800289bb  mov     rax, [rbx]
0x1800289be  mov     rcx, rbx
0x1800289c1  mov     rax, [rax+10h]
0x1800289c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800289ca  nop
0x1800289cb  jmp     loc_180028804
0x1800289d0  mov     rcx, [rsp+390h+var_328]
0x1800289d5  test    rcx, rcx
0x1800289d8  jz      short loc_1800289E7
0x1800289da  mov     rax, [rcx]
0x1800289dd  mov     rax, [rax+10h]
0x1800289e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800289e6  nop
0x1800289e7  mov     rcx, [rsp+390h+var_340]
0x1800289ec  test    rcx, rcx
0x1800289ef  jz      short loc_1800289FE
0x1800289f1  mov     rax, [rcx]
0x1800289f4  mov     rax, [rax+10h]
0x1800289f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800289fd  nop
0x1800289fe  mov     rcx, [rsp+390h+var_330]
0x180028a03  test    rcx, rcx
0x180028a06  jz      short loc_180028A15
0x180028a08  mov     rax, [rcx]
0x180028a0b  mov     rax, [rax+10h]
0x180028a0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028a14  nop
0x180028a15  mov     rcx, [rsp+390h+hLibModule]; hLibModule
0x180028a1a  test    rcx, rcx
0x180028a1d  jz      short loc_180028A2B
0x180028a1f  call    cs:__imp_FreeLibrary
0x180028a26  nop     dword ptr [rax+rax+00h]
0x180028a2b  mov     rbx, [rsp+390h+var_358]
0x180028a30  cmp     [rbx-10h], r12d
0x180028a34  jnz     short loc_180028A60
0x180028a36  lea     rdx, [rbx-18h]
0x180028a3a  mov     eax, edi
0x180028a3c  lock xadd [rdx+10h], eax
0x180028a41  add     eax, edi
0x180028a43  test    eax, eax
0x180028a45  jg      short loc_180028A56
0x180028a47  mov     rcx, [rdx]
0x180028a4a  mov     rax, [rcx]
0x180028a4d  mov     rax, [rax+8]
0x180028a51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028a56  mov     eax, 80004005h
0x180028a5b  jmp     loc_180028E32
0x180028a60  lea     r14, [r13+28h]
0x180028a64  lea     rdx, [rsp+390h+var_358]
0x180028a69  mov     rcx, r14
0x180028a6c  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180028a71  mov     rcx, r14
0x180028a74  call    ?Replace@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEBG0@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Replace(ushort const *,ushort const *)
0x180028a79  lea     rdx, [rsp+390h+var_358]
0x180028a7e  lea     rcx, [r13+30h]
0x180028a82  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180028a87  nop
0x180028a88  lea     rdx, [rbx-18h]
0x180028a8c  mov     eax, edi
0x180028a8e  lock xadd [rdx+10h], eax
0x180028a93  add     eax, edi
0x180028a95  test    eax, eax
0x180028a97  jg      short loc_180028AA8
0x180028a99  mov     rcx, [rdx]
0x180028a9c  mov     rax, [rcx]
0x180028a9f  mov     rax, [rax+8]
0x180028aa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028aa8  lea     rsi, [r13+38h]
0x180028aac  lea     rdx, aXperfNgenpdbsp; "XPERF_NGenPdbsPath"
0x180028ab3  mov     rcx, rsi
0x180028ab6  call    ?GetEnvironmentVariableW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::GetEnvironmentVariableW(ushort const *)
0x180028abb  test    eax, eax
0x180028abd  jz      short loc_180028ACC
0x180028abf  mov     rax, [rsi]
0x180028ac2  cmp     [rax-10h], r12d
0x180028ac6  jnz     loc_180028DDB
0x180028acc  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
  ... truncated ...
```
