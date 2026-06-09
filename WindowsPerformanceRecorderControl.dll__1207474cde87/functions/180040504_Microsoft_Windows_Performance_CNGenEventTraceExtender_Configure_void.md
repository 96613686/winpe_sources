# Microsoft::Windows::Performance::CNGenEventTraceExtender::Configure(void)

- ea: `0x180040504`
- end: `0x1800409ef`
- name: `?Configure@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEAAJXZ`
- size: `1259`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CNGenEventTraceExtender *__hidden this)`
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18007a3a4`

## callees

- `0x180008330`
- `0x180009b40`
- `0x1800103c0`
- `0x1800131a0`
- `0x180016480`
- `0x18001c458`
- `0x18001c820`
- `0x180040504`
- `0x180040a04`
- `0x1800419e8`
- `0x18004b39c`
- `0x18004ece0`
- `0x18005a604`
- `0x1800772f0`
- `0x1800774cc`
- `0x1800774ec`
- `0x180078048`
- `0x180078280`
- `0x180078c40`
- `0x180079ed4`
- `0x18007b6b8`
- `0x18007bdb0`
- `0x18008c010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x18004090a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x18004090a`

## string_xrefs

- `0x18004096a`: `XPERF_NGenPdbsCachePath`
- `0x1800407b5`: `XPERF_NGenPdbsPath`
- `0x1800407e0`: `_NT_SYMBOL_PATH`
- `0x18004054e`: `mscoree.dll`
- `0x18004056a`: `CLRCreateInstance`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Performance::CNGenEventTraceExtender::Configure(
        Microsoft::Windows::Performance::CNGenEventTraceExtender *this)
{
  int Error; // ebx
  __int64 (__fastcall *v3)(GUID *, GUID *, __int64 *); // rax
  unsigned __int16 v4; // di
  void (__fastcall ***v5)(_QWORD, GUID *, __int64 *); // r9
  __int64 v6; // rcx
  unsigned __int16 v7; // bx
  WindowsPerformanceRecorder::Status::CSessionInfo *v8; // rcx
  _QWORD *v10; // rsi
  int v11; // eax
  __int64 v12; // rdx
  void (__fastcall ***v13)(_QWORD, GUID *, _QWORD *); // rbx
  int v14; // edi
  __int64 v15; // rdx
  unsigned __int64 v16; // rax
  _QWORD *v17; // rbx
  int v18; // edx
  int v19; // ecx
  __int64 v20; // [rsp+30h] [rbp-D0h] BYREF
  void (__fastcall ***v21)(_QWORD, GUID *, __int64 *); // [rsp+38h] [rbp-C8h] BYREF
  int v22; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v23; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v24; // [rsp+50h] [rbp-B0h] BYREF
  int v25; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v26; // [rsp+5Ch] [rbp-A4h] BYREF
  __int64 v27; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v28; // [rsp+68h] [rbp-98h] BYREF
  __int64 v29; // [rsp+78h] [rbp-88h]
  char v30; // [rsp+80h] [rbp-80h]
  __int64 v31; // [rsp+88h] [rbp-78h] BYREF
  __int128 v32; // [rsp+90h] [rbp-70h] BYREF
  __int64 v33; // [rsp+A0h] [rbp-60h]
  int v34; // [rsp+A8h] [rbp-58h]
  __int64 v35; // [rsp+B0h] [rbp-50h]
  int v36; // [rsp+B8h] [rbp-48h]
  __int64 v37; // [rsp+C0h] [rbp-40h]
  __int16 v38; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 v39; // [rsp+D2h] [rbp-2Eh]
  __int16 v40; // [rsp+D4h] [rbp-2Ch]
  WCHAR Buffer[264]; // [rsp+120h] [rbp+20h] BYREF

  v37 = -2;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v24);
  v31 = 0;
  *(_QWORD *)&v32 = L"mscoree.dll";
  *((_QWORD *)&v32 + 1) = 0;
  LOBYTE(v33) = 0;
  *(_QWORD *)&v28 = &v31;
  *((_QWORD *)&v28 + 1) = "CLRCreateInstance";
  v29 = 0;
  v30 = 0;
  if ( !Performance::DelayLoad::CDelayLoadedImport<void * (*)(void *,unsigned short const *,unsigned long),Performance::DelayLoad::CFakeSRWLock>::operator void * (*)(void *,unsigned short const *,unsigned long)(&v28) )
  {
    Error = -2147467259;
LABEL_7:
    Performance::DelayLoad::CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>::~CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>(&v31);
LABEL_25:
    v8 = (WindowsPerformanceRecorder::Status::CSessionInfo *)&v24;
LABEL_26:
    WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(v8);
    return (unsigned int)Error;
  }
  v27 = 0;
  v3 = (__int64 (__fastcall *)(GUID *, GUID *, __int64 *))Performance::DelayLoad::CDelayLoadedImport<void * (*)(void *,unsigned short const *,unsigned long),Performance::DelayLoad::CFakeSRWLock>::operator void * (*)(void *,unsigned short const *,unsigned long)(&v28);
  Error = v3(&CLSID_CLRMetaHost, &IID_ICLRMetaHost, &v27);
  if ( Error < 0 )
  {
LABEL_6:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v27);
    goto LABEL_7;
  }
  v20 = 0;
  Error = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v27 + 40LL))(v27, &v20);
  if ( Error < 0 )
  {
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v20);
    goto LABEL_6;
  }
  v21 = 0;
  v25 = 0;
  v4 = 0;
  while ( (*(int (__fastcall **)(__int64, __int64, void (__fastcall ****)(_QWORD, GUID *, __int64 *), int *))(*(_QWORD *)v20 + 24LL))(
            v20,
            1,
            &v21,
            &v25) >= 0
       && v25 == 1 )
  {
    v5 = v21;
    v21 = 0;
    *(_QWORD *)&v28 = v5;
    v6 = 0;
    v23 = 0;
    if ( v5 )
    {
      (**v5)(v5, &GUID_bd39d1d2_ba2f_486a_89b0_b4b0cb466891, &v23);
      v6 = v23;
    }
    if ( v6 )
    {
      v26 = 30;
      if ( (*(int (__fastcall **)(__int64, __int16 *, unsigned int *))(*(_QWORD *)v6 + 24LL))(v6, &v38, &v26) >= 0
        && v26 >= 3
        && ((v38 - 86) & 0xFFDF) == 0 )
      {
        v7 = v39;
        if ( (unsigned __int16)(v39 - 52) <= 5u && v40 == 46 && v39 > v4 )
        {
          v22 = 260;
          if ( (*(int (__fastcall **)(__int64, WCHAR *, int *))(*(_QWORD *)v23 + 32LL))(v23, Buffer, &v22) >= 0 )
          {
            ATL::CSimpleStringT<unsigned short,0>::SetString(&v24, Buffer);
            v4 = v7;
          }
        }
      }
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v23);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v28);
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v21);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v20);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v27);
  Performance::DelayLoad::CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>::~CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>(&v31);
  if ( !*(_DWORD *)(v24 - 16) )
  {
    Error = -2147467259;
    goto LABEL_25;
  }
  ATL::CSimpleStringT<unsigned short,0>::operator=((char *)this + 40, &v24);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Replace((char *)this + 40);
  ATL::CSimpleStringT<unsigned short,0>::operator=((char *)this + 48, &v24);
  WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&v24);
  v10 = (_QWORD *)((char *)this + 56);
  if ( !(unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::GetEnvironmentVariableW(
                        (char *)this + 56,
                        L"XPERF_NGenPdbsPath")
    || !*(_DWORD *)(*v10 - 16LL) )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v20);
    if ( (unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::GetEnvironmentVariableW(
                         &v20,
                         L"_NT_SYMBOL_PATH") )
    {
      v32 = 0;
      v33 = 0;
      v34 = 0;
      v35 = 0;
      v36 = 1;
      LODWORD(v31) = 0;
      v11 = ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::Parse(&v31);
      if ( v11 )
      {
        Error = -2147418113;
        if ( v11 == 1 )
          Error = -2147024882;
        ATL::CAtlArray<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION,ATL::CElementTraits<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION>>::~CAtlArray<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION,ATL::CElementTraits<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION>>(&v32);
        goto LABEL_55;
      }
      ATL::CAtlREMatchContext<ATL::CAtlRECharTraitsW>::CAtlREMatchContext<ATL::CAtlRECharTraitsW>(&v38);
      v22 = 0;
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v21);
      while ( 1 )
      {
        v12 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Tokenize(
                &v20,
                &v28);
        ATL::CSimpleStringT<unsigned short,0>::operator=(&v21, v12);
        v13 = v21;
        v14 = *((_DWORD *)v21 - 4);
        WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&v28);
        if ( !v14 )
          break;
        if ( (unsigned int)ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::Match(&v31, v13, &v38, 0) )
        {
          v28 = 0;
          ATL::CAtlREMatchContext<ATL::CAtlRECharTraitsW>::GetMatch(&v38, v15, &v28);
          ATL::CSimpleStringT<unsigned short,0>::SetString(
            (__int64 *)this + 7,
            (const void *)v28,
            (__int64)(*((_QWORD *)&v28 + 1) - v28) >> 1);
          break;
        }
      }
      WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&v21);
      ATL::CAtlREMatchContext<ATL::CAtlRECharTraitsW>::~CAtlREMatchContext<ATL::CAtlRECharTraitsW>(&v38);
      ATL::CAtlArray<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION,ATL::CElementTraits<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION>>::~CAtlArray<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION,ATL::CElementTraits<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION>>(&v32);
    }
    if ( !*(_DWORD *)(*v10 - 16LL) )
    {
      if ( !GetSystemWindowsDirectoryW(Buffer, 0x105u) )
      {
        Error = ATL::AtlHresultFromLastError();
LABEL_55:
        v8 = (WindowsPerformanceRecorder::Status::CSessionInfo *)&v20;
        goto LABEL_26;
      }
      v16 = -1;
      do
        ++v16;
      while ( Buffer[v16] );
      if ( v16 < 2 || Buffer[1] != 58 )
      {
        Error = -2147418113;
        goto LABEL_55;
      }
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
        (char *)this + 56,
        L"%wc:\\Symbols",
        Buffer[0]);
    }
    WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&v20);
  }
  v17 = (_QWORD *)((char *)this + 64);
  if ( !(unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::GetEnvironmentVariableW(
                        (char *)this + 64,
                        L"XPERF_NGenPdbsCachePath")
    || !*(_DWORD *)(*v17 - 16LL) )
  {
    ATL::CSimpleStringT<unsigned short,0>::operator=((char *)this + 64, (char *)this + 56);
  }
  *((_BYTE *)this + 32) = 1;
  if ( (Microsoft_Windows_XPerfCoreEnableBits & 1) != 0 )
    McTemplateU0zzzz_EventWriteTransfer(v19, v18, *v10, *v17, *((_QWORD *)this + 5), *((_QWORD *)this + 6));
  return 0;
}

```

## disassembly

```asm
0x180040504  push    rbp
0x180040506  push    rbx
0x180040507  push    rsi
0x180040508  push    rdi
0x180040509  push    r12
0x18004050b  push    r13
0x18004050d  push    r14
0x18004050f  push    r15
0x180040511  lea     rbp, [rsp-248h]
0x180040519  sub     rsp, 348h
0x180040520  mov     [rbp+280h+var_2C0], 0FFFFFFFFFFFFFFFEh
0x180040528  mov     rax, cs:__security_cookie
0x18004052f  xor     rax, rsp
0x180040532  mov     [rbp+280h+var_50], rax
0x180040539  mov     r14, rcx
0x18004053c  lea     rcx, [rsp+380h+var_330]; void *
0x180040541  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180040546  nop
0x180040547  xor     r13d, r13d
0x18004054a  mov     [rbp+280h+var_2F8], r13
0x18004054e  lea     rax, aMscoreeDll; "mscoree.dll"
0x180040555  mov     qword ptr [rbp+280h+var_2F0], rax
0x180040559  mov     qword ptr [rbp+280h+var_2F0+8], r13
0x18004055d  mov     byte ptr [rbp+280h+var_2E0], r13b
0x180040561  lea     rax, [rbp+280h+var_2F8]
0x180040565  mov     qword ptr [rsp+380h+var_318], rax
0x18004056a  lea     rax, aClrcreateinsta; "CLRCreateInstance"
0x180040571  mov     qword ptr [rsp+380h+var_318+8], rax
0x180040576  mov     [rsp+380h+var_308], r13
0x18004057b  mov     [rbp+280h+var_300], r13b
0x18004057f  lea     rcx, [rsp+380h+var_318]
0x180040584  call    ??B?$CDelayLoadedImport@P6APEAXPEAXPEBGK@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6APEAXPEAXPEBGK@ZXZ; Performance::DelayLoad::CDelayLoadedImport<void * (*)(void *,ushort const *,ulong),Performance::DelayLoad::CFakeSRWLock>::operator void * (*)(void *,ushort const *,ulong)(void)
0x180040589  test    rax, rax
0x18004058c  jnz     short loc_180040595
0x18004058e  mov     ebx, 80004005h
0x180040593  jmp     short loc_1800405F9
0x180040595  mov     [rsp+380h+var_320], r13
0x18004059a  lea     rcx, [rsp+380h+var_318]
0x18004059f  call    ??B?$CDelayLoadedImport@P6APEAXPEAXPEBGK@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6APEAXPEAXPEBGK@ZXZ; Performance::DelayLoad::CDelayLoadedImport<void * (*)(void *,ushort const *,ulong),Performance::DelayLoad::CFakeSRWLock>::operator void * (*)(void *,ushort const *,ulong)(void)
0x1800405a4  lea     r8, [rsp+380h+var_320]
0x1800405a9  lea     rdx, IID_ICLRMetaHost
0x1800405b0  lea     rcx, CLSID_CLRMetaHost
0x1800405b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800405bc  mov     ebx, eax
0x1800405be  test    eax, eax
0x1800405c0  js      short loc_1800405EE
0x1800405c2  mov     [rsp+380h+var_350], r13
0x1800405c7  mov     rcx, [rsp+380h+var_320]
0x1800405cc  mov     rax, [rcx]
0x1800405cf  lea     rdx, [rsp+380h+var_350]
0x1800405d4  mov     rax, [rax+28h]
0x1800405d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800405dd  mov     ebx, eax
0x1800405df  test    eax, eax
0x1800405e1  jns     short loc_180040607
0x1800405e3  lea     rcx, [rsp+380h+var_350]
0x1800405e8  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800405ed  nop
0x1800405ee  lea     rcx, [rsp+380h+var_320]
0x1800405f3  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800405f8  nop
0x1800405f9  lea     rcx, [rbp+280h+var_2F8]
0x1800405fd  call    ??1?$CDelayLoadedModule@VCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAA@XZ; Performance::DelayLoad::CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>::~CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>(void)
0x180040602  jmp     loc_18004076E
0x180040607  mov     [rsp+380h+var_348], r13
0x18004060c  mov     [rsp+380h+var_328], r13d
0x180040611  mov     edi, r13d
0x180040614  mov     rcx, [rsp+380h+var_350]
0x180040619  mov     rax, [rcx]
0x18004061c  lea     r9, [rsp+380h+var_328]
0x180040621  lea     r8, [rsp+380h+var_348]
0x180040626  mov     edx, 1
0x18004062b  mov     rax, [rax+18h]
0x18004062f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040634  test    eax, eax
0x180040636  js      loc_180040734
0x18004063c  cmp     [rsp+380h+var_328], 1
0x180040641  jnz     loc_180040734
0x180040647  mov     r9, [rsp+380h+var_348]
0x18004064c  mov     [rsp+380h+var_348], r13
0x180040651  mov     qword ptr [rsp+380h+var_318], r9
0x180040656  mov     rcx, r13
0x180040659  mov     [rsp+380h+var_338], rcx
0x18004065e  test    r9, r9
0x180040661  jz      short loc_180040682
0x180040663  mov     rax, [r9]
0x180040666  lea     r8, [rsp+380h+var_338]
0x18004066b  lea     rdx, _GUID_bd39d1d2_ba2f_486a_89b0_b4b0cb466891
0x180040672  mov     rcx, r9
0x180040675  mov     rax, [rax]
0x180040678  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004067d  mov     rcx, [rsp+380h+var_338]
0x180040682  test    rcx, rcx
0x180040685  jnz     short loc_1800406A1
0x180040687  lea     rcx, [rsp+380h+var_338]
0x18004068c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180040691  nop
0x180040692  lea     rcx, [rsp+380h+var_318]
0x180040697  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004069c  jmp     loc_180040614
0x1800406a1  mov     [rsp+380h+var_324], 1Eh
0x1800406a9  mov     rax, [rcx]
0x1800406ac  lea     r8, [rsp+380h+var_324]
0x1800406b1  lea     rdx, [rbp+280h+var_2B0]
0x1800406b5  mov     rax, [rax+18h]
0x1800406b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800406be  test    eax, eax
0x1800406c0  js      short loc_180040687
0x1800406c2  cmp     [rsp+380h+var_324], 3
0x1800406c7  jb      short loc_180040687
0x1800406c9  movzx   eax, [rbp+280h+var_2B0]
0x1800406cd  sub     ax, 56h ; 'V'
0x1800406d1  mov     ecx, 0FFDFh
0x1800406d6  test    cx, ax
0x1800406d9  jnz     short loc_180040687
0x1800406db  movzx   ebx, [rbp+280h+var_2AE]
0x1800406df  lea     eax, [rbx-34h]
0x1800406e2  cmp     ax, 5
0x1800406e6  ja      short loc_180040687
0x1800406e8  cmp     [rbp+280h+var_2AC], 2Eh ; '.'
0x1800406ed  jnz     short loc_180040687
0x1800406ef  cmp     bx, di
0x1800406f2  jbe     short loc_180040687
0x1800406f4  mov     [rsp+380h+var_340], 104h
0x1800406fc  mov     rcx, [rsp+380h+var_338]
0x180040701  mov     rax, [rcx]
0x180040704  lea     r8, [rsp+380h+var_340]
0x180040709  lea     rdx, [rbp+280h+Buffer]
0x18004070d  mov     rax, [rax+20h]
0x180040711  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040716  test    eax, eax
0x180040718  js      loc_180040687
0x18004071e  lea     rdx, [rbp+280h+Buffer]
0x180040722  lea     rcx, [rsp+380h+var_330]
0x180040727  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x18004072c  movzx   edi, bx
0x18004072f  jmp     loc_180040687
0x180040734  lea     rcx, [rsp+380h+var_348]
0x180040739  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004073e  nop
0x18004073f  lea     rcx, [rsp+380h+var_350]
0x180040744  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180040749  nop
0x18004074a  lea     rcx, [rsp+380h+var_320]
0x18004074f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180040754  nop
0x180040755  lea     rcx, [rbp+280h+var_2F8]
0x180040759  call    ??1?$CDelayLoadedModule@VCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAA@XZ; Performance::DelayLoad::CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>::~CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>(void)
0x18004075e  mov     rax, [rsp+380h+var_330]
0x180040763  cmp     [rax-10h], r13d
0x180040767  jnz     short loc_18004077F
0x180040769  mov     ebx, 80004005h
0x18004076e  lea     rcx, [rsp+380h+var_330]; this
0x180040773  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x180040778  mov     eax, ebx
0x18004077a  jmp     loc_1800409BD
0x18004077f  lea     r15, [r14+28h]
0x180040783  lea     rdx, [rsp+380h+var_330]
0x180040788  mov     rcx, r15
0x18004078b  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x180040790  mov     rcx, r15
0x180040793  call    ?Replace@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEBG0@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Replace(ushort const *,ushort const *)
0x180040798  lea     rdx, [rsp+380h+var_330]
0x18004079d  lea     rcx, [r14+30h]
0x1800407a1  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x1800407a6  nop
0x1800407a7  lea     rcx, [rsp+380h+var_330]; this
0x1800407ac  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x1800407b1  lea     rsi, [r14+38h]
0x1800407b5  lea     rdx, aXperfNgenpdbsp; "XPERF_NGenPdbsPath"
0x1800407bc  mov     rcx, rsi
0x1800407bf  call    ?GetEnvironmentVariableW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::GetEnvironmentVariableW(ushort const *)
0x1800407c4  test    eax, eax
0x1800407c6  jz      short loc_1800407D5
0x1800407c8  mov     rax, [rsi]
0x1800407cb  cmp     [rax-10h], r13d
0x1800407cf  jnz     loc_180040966
0x1800407d5  lea     rcx, [rsp+380h+var_350]; void *
0x1800407da  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800407df  nop
0x1800407e0  lea     rdx, aNtSymbolPath; "_NT_SYMBOL_PATH"
0x1800407e7  lea     rcx, [rsp+380h+var_350]
0x1800407ec  call    ?GetEnvironmentVariableW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::GetEnvironmentVariableW(ushort const *)
0x1800407f1  test    eax, eax
0x1800407f3  jz      loc_1800408F8
0x1800407f9  xorps   xmm0, xmm0
0x1800407fc  movdqu  [rbp+280h+var_2F0], xmm0
0x180040801  mov     [rbp+280h+var_2E0], r13
0x180040805  mov     [rbp+280h+var_2D8], r13d
0x180040809  mov     [rbp+280h+var_2D0], r13
0x18004080d  mov     [rbp+280h+var_2C8], 1
0x180040814  mov     dword ptr [rbp+280h+var_2F8], r13d
0x180040818  lea     rcx, [rbp+280h+var_2F8]
0x18004081c  call    ?Parse@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@QEAA?AW4REParseError@2@PEBGH@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::Parse(ushort const *,int)
0x180040821  test    eax, eax
0x180040823  jz      short loc_180040842
0x180040825  cmp     eax, 1
0x180040828  mov     ebx, 8000FFFFh
0x18004082d  jnz     short loc_180040834
0x18004082f  mov     ebx, 8007000Eh
0x180040834  lea     rcx, [rbp+280h+var_2F0]
0x180040838  call    ??1?$CAtlArray@UINSTRUCTION@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@V?$CElementTraits@UINSTRUCTION@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@@3@@ATL@@QEAA@XZ; ATL::CAtlArray<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION,ATL::CElementTraits<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION>>::~CAtlArray<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION,ATL::CElementTraits<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION>>(void)
0x18004083d  jmp     loc_1800409E5
0x180040842  lea     rcx, [rbp+280h+var_2B0]
0x180040846  call    ??0?$CAtlREMatchContext@VCAtlRECharTraitsW@ATL@@@ATL@@QEAA@_K@Z; ATL::CAtlREMatchContext<ATL::CAtlRECharTraitsW>::CAtlREMatchContext<ATL::CAtlRECharTraitsW>(unsigned __int64)
0x18004084b  nop
0x18004084c  mov     [rsp+380h+var_340], r13d
0x180040851  lea     rcx, [rsp+380h+var_348]; void *
0x180040856  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18004085b  nop
0x18004085c  lea     r9, [rsp+380h+var_340]
0x180040861  lea     rdx, [rsp+380h+var_318]; void *
0x180040866  lea     rcx, [rsp+380h+var_350]; void *
0x18004086b  call    ?Tokenize@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@PEBGAEAH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Tokenize(ushort const *,int &)
0x180040870  nop
0x180040871  mov     rdx, rax
0x180040874  lea     rcx, [rsp+380h+var_348]
0x180040879  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x18004087e  mov     rbx, [rsp+380h+var_348]
0x180040883  mov     edi, [rbx-10h]
0x180040886  lea     rcx, [rsp+380h+var_318]; this
0x18004088b  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x180040890  test    edi, edi
0x180040892  jz      short loc_1800408DA
0x180040894  xor     r9d, r9d
0x180040897  lea     r8, [rbp+280h+var_2B0]
0x18004089b  mov     rdx, rbx
0x18004089e  lea     rcx, [rbp+280h+var_2F8]
0x1800408a2  call    ?Match@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@QEAAHPEBGPEAV?$CAtlREMatchContext@VCAtlRECharTraitsW@ATL@@@2@PEAPEBG@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::Match(ushort const *,ATL::CAtlREMatchContext<ATL::CAtlRECharTraitsW> *,ushort const * *)
0x1800408a7  test    eax, eax
0x1800408a9  jz      short loc_18004085C
0x1800408ab  xorps   xmm0, xmm0
0x1800408ae  movups  [rsp+380h+var_318], xmm0
0x1800408b3  lea     r8, [rsp+380h+var_318]
0x1800408b8  lea     rcx, [rbp+280h+var_2B0]
0x1800408bc  call    ?GetMatch@?$CAtlREMatchContext@VCAtlRECharTraitsW@ATL@@@ATL@@QEAAXIPEAUMatchGroup@12@@Z; ATL::CAtlREMatchContext<ATL::CAtlRECharTraitsW>::GetMatch(uint,ATL::CAtlREMatchContext<ATL::CAtlRECharTraitsW>::MatchGroup *)
0x1800408c1  mov     r8, qword ptr [rsp+380h+var_318+8]
0x1800408c6  mov     rdx, qword ptr [rsp+380h+var_318]
0x1800408cb  sub     r8, rdx
0x1800408ce  sar     r8, 1
0x1800408d1  mov     rcx, rsi
0x1800408d4  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1800408d9  nop
0x1800408da  lea     rcx, [rsp+380h+var_348]; this
0x1800408df  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x1800408e4  nop
0x1800408e5  lea     rcx, [rbp+280h+var_2B0]
0x1800408e9  call    ??1?$CAtlREMatchContext@VCAtlRECharTraitsW@ATL@@@ATL@@QEAA@XZ; ATL::CAtlREMatchContext<ATL::CAtlRECharTraitsW>::~CAtlREMatchContext<ATL::CAtlRECharTraitsW>(void)
0x1800408ee  nop
0x1800408ef  lea     rcx, [rbp+280h+var_2F0]
0x1800408f3  call    ??1?$CAtlArray@UINSTRUCTION@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@V?$CElementTraits@UINSTRUCTION@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@@3@@ATL@@QEAA@XZ; ATL::CAtlArray<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION,ATL::CElementTraits<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION>>::~CAtlArray<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION,ATL::CElementTraits<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION>>(void)
0x1800408f8  mov     rax, [rsi]
0x1800408fb  cmp     [rax-10h], r13d
0x1800408ff  jnz     short loc_18004095C
0x180040901  mov     edx, 105h; uSize
0x180040906  lea     rcx, [rbp+280h+Buffer]; lpBuffer
0x18004090a  call    cs:__imp_GetSystemWindowsDirectoryW
0x180040910  test    eax, eax
0x180040912  jnz     short loc_180040920
0x180040914  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180040919  mov     ebx, eax
0x18004091b  jmp     loc_1800409E5
0x180040920  lea     rcx, [rbp+280h+Buffer]
0x180040924  or      rax, 0FFFFFFFFFFFFFFFFh
0x180040928  inc     rax
0x18004092b  cmp     [rcx+rax*2], r13w
0x180040930  jnz     short loc_180040928
0x180040932  cmp     rax, 2
0x180040936  jb      loc_1800409E0
0x18004093c  cmp     [rbp+280h+var_25E], 3Ah ; ':'
0x180040941  jnz     loc_1800409E0
0x180040947  movzx   r8d, [rbp+280h+Buffer]
0x18004094c  lea     rdx, aWcSymbols; "%wc:\\Symbols"
0x180040953  mov     rcx, rsi
0x180040956  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18004095b  nop
0x18004095c  lea     rcx, [rsp+380h+var_350]; this
0x180040961  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x180040966  lea     rbx, [r14+40h]
0x18004096a  lea     rdx, aXperfNgenpdbsc; "XPERF_NGenPdbsCachePath"
0x180040971  mov     rcx, rbx
0x180040974  call    ?GetEnvironmentVariableW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::GetEnvironmentVariableW(ushort const *)
0x180040979  test    eax, eax
0x18004097b  jz      short loc_180040986
0x18004097d  mov     rax, [rbx]
0x180040980  cmp     [rax-10h], r13d
0x180040984  jnz     short loc_180040991
0x180040986  mov     rdx, rsi
0x180040989  mov     rcx, rbx
0x18004098c  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x180040991  mov     byte ptr [r14+20h], 1
0x180040996  test    cs:Microsoft_Windows_XPerfCoreEnableBits, 1
0x18004099d  jz      short loc_1800409BB
0x18004099f  mov     rax, [r14+30h]
0x1800409a3  mov     [rsp+380h+var_358], rax
0x1800409a8  mov     rax, [r15]
0x1800409ab  mov     [rsp+380h+var_360], rax
0x1800409b0  mov     r9, [rbx]
0x1800409b3  mov     r8, [rsi]
0x1800409b6  call    McTemplateU0zzzz_EventWriteTransfer
  ... truncated ...
```
