# CAvEndpointBuilder::Initialize(void)

- ea: `0x18003984c`
- end: `0x180039d33`
- name: `?Initialize@CAvEndpointBuilder@@QEAAJXZ`
- size: `1255`
- prototype: `__int64 __fastcall(CAvEndpointBuilder *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180047854`

## callees

- `0x180005358`
- `0x180006b0c`
- `0x180007580`
- `0x180010da8`
- `0x180023fbc`
- `0x1800274dc`
- `0x180033444`
- `0x18003984c`
- `0x180039d3c`
- `0x180039d64`
- `0x18003e920`
- `0x18003edfc`
- `0x18003f7a4`
- `0x18004d818`
- `0x1800586e4`
- `0x18005c44c`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800399e3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800399e3`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800399b2`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800399b2`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800398d9`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800398d9`
- `ntdll!RtlPublishWnfStateData` at `0x180039cb5`
- `ntdll!RtlPublishWnfStateData` at `0x180039cb5`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180039b1b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180039b1b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003991c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003996c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180039af2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003991c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003996c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180039af2`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180039985`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180039985`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoSizeW` at `0x180039a02`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoSizeW` at `0x180039a02`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoW` at `0x180039a54`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoW` at `0x180039a54`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180039a90`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180039a90`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180039b97`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180039b97`

## string_xrefs

- `0x180039a63`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x180039bb2`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x180039cf4`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CAvEndpointBuilder::Initialize(CAvEndpointBuilder *this)
{
  LPCRITICAL_SECTION v1; // rdi
  int AEBBindingHandle; // eax
  void *v3; // rcx
  unsigned int LastError; // ebx
  unsigned __int64 v5; // r9
  __int64 v6; // rdx
  int v7; // eax
  char *v8; // rax
  __int64 v9; // rcx
  char *v10; // rbx
  DWORD FileVersionInfoSizeW; // eax
  DWORD v12; // ebx
  struct _RTL_CRITICAL_SECTION_DEBUG *v13; // rax
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rcx
  PRTL_CRITICAL_SECTION_DEBUG v15; // r9
  const char *v16; // r9
  __int64 v17; // rdx
  PTP_TIMER ThreadpoolTimer; // rax
  int Instance; // eax
  int v20; // eax
  HRESULT v21; // eax
  __int64 v22; // rdx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbx
  unsigned int i; // ebx
  __int64 v25; // rax
  int pdwType; // [rsp+20h] [rbp-E0h]
  int pdwTypea; // [rsp+20h] [rbp-E0h]
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD dwMilliseconds; // [rsp+44h] [rbp-BCh] BYREF
  __int64 *v31; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v32; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID ppv; // [rsp+58h] [rbp-A8h] BYREF
  char *v34; // [rsp+60h] [rbp-A0h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+68h] [rbp-98h] BYREF
  int v36[4]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Filename[264]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+1D8h]

  v1 = AvEndpointBuilder;
  memset_0(Filename, 0, 0x208u);
  Binding = 0;
  AEBBindingHandle = GetAEBBindingHandle(&Binding);
  LastError = AEBBindingHandle;
  if ( AEBBindingHandle < 0 )
  {
    v5 = (unsigned int)AEBBindingHandle;
    v6 = 1307;
LABEL_56:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)v5,
      pdwType);
    goto LABEL_57;
  }
  v7 = InitializeAEBSvc(v3);
  LastError = v7;
  if ( v7 < 0 )
  {
    v5 = (unsigned int)v7;
    v6 = 1308;
    goto LABEL_56;
  }
  dwMilliseconds = 0;
  pcbData = 4;
  BYTE4(v1[1].SpinCount) = (unsigned __int8)RtlIsStateSeparationEnabled() == 0;
  if ( !RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Audio",
          L"SkipAEBVersionCheck",
          0x18u,
          0,
          &dwMilliseconds,
          &pcbData)
    && pcbData == 4 )
  {
    BYTE4(v1[1].SpinCount) = dwMilliseconds != 0;
  }
  pcbData = 4;
  if ( !RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Audio",
          L"AEBSlowStart",
          0x18u,
          0,
          &dwMilliseconds,
          &pcbData)
    && pcbData == 4
    && dwMilliseconds )
  {
    Sleep(dwMilliseconds);
  }
  v8 = (char *)operator new(0x38u);
  v10 = v8;
  v34 = v8;
  if ( v8 )
  {
    *(_QWORD *)v8 = 0;
    *((_WORD *)v8 + 4) = 0;
    InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v8 + 16), 0, 0);
  }
  else
  {
    v10 = 0;
  }
  std::unique_ptr<CUpgradeDiagnostics>::reset(v9, v10);
  if ( !g_UpgradeDiagnostics )
  {
    v6 = 1351;
    goto LABEL_54;
  }
  if ( !GetModuleFileNameW(g_hInstance, Filename, 0x104u) )
  {
    LastError = -2147467259;
    v6 = 1356;
LABEL_55:
    v5 = LastError;
    goto LABEL_56;
  }
  FileVersionInfoSizeW = GetFileVersionInfoSizeW(Filename, 0);
  v12 = FileVersionInfoSizeW;
  if ( !FileVersionInfoSizeW )
  {
    LastError = -2147467259;
    v6 = 1359;
    goto LABEL_55;
  }
  v13 = (struct _RTL_CRITICAL_SECTION_DEBUG *)operator new[](
                                                FileVersionInfoSizeW,
                                                (const struct std::nothrow_t *)&std::nothrow);
  DebugInfo = v1[2].DebugInfo;
  v1[2].DebugInfo = v13;
  if ( DebugInfo )
    operator delete(DebugInfo);
  v15 = v1[2].DebugInfo;
  if ( !v15 )
  {
    v6 = 1362;
LABEL_54:
    LastError = -2147024882;
    goto LABEL_55;
  }
  if ( !GetFileVersionInfoW(Filename, 0, v12, v15) )
  {
    v17 = 1363;
LABEL_25:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v17,
                  (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
                  v16);
LABEL_57:
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&Binding);
    return LastError;
  }
  if ( !VerQueryValueW(v1[2].DebugInfo, L"\\", (LPVOID *)&v1[2].LockCount, (PUINT)&v1[2].OwningThread) )
  {
    LastError = -2147467259;
    v6 = 1364;
    goto LABEL_55;
  }
  if ( !LODWORD(v1[2].OwningThread) )
  {
    LastError = -2147467259;
    v6 = 1365;
    goto LABEL_55;
  }
  pcbData = 4;
  if ( !RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Audio",
          L"BluetoothEndpointUnificationTimeoutInSecond",
          0x18u,
          0,
          &dwMilliseconds,
          &pcbData)
    && pcbData == 4
    && dwMilliseconds )
  {
    LODWORD(v1[1].SpinCount) = dwMilliseconds;
  }
  ThreadpoolTimer = CreateThreadpoolTimer(CAvEndpointBuilder::BluetoothEndpointUnificationCallback, v1, 0);
  v1[1].LockSemaphore = ThreadpoolTimer;
  if ( !ThreadpoolTimer )
  {
    v17 = 1379;
    goto LABEL_25;
  }
  Instance = CAudioDeviceManager::CreateInstance((struct CAudioDeviceManager **)&v1[2].LockSemaphore);
  LastError = Instance;
  if ( Instance < 0 )
  {
    v5 = (unsigned int)Instance;
    v6 = 1383;
    goto LABEL_56;
  }
  v20 = CAvEndpointBuilder::QueryAndSubscribePostureChangeNotification(v1);
  LastError = v20;
  if ( v20 < 0 )
  {
    v5 = (unsigned int)v20;
    v6 = 1385;
    goto LABEL_56;
  }
  v32 = 0;
  v31 = 0;
  ppv = 0;
  v21 = CoCreateInstance(
          &GUID_06cca63e_9941_441b_b004_39f999ada412,
          0,
          0x17u,
          &GUID_6ca19947_8747_46ab_879e_349c4dbb88fb,
          &ppv);
  LastError = v21;
  if ( v21 < 0 )
  {
    v22 = 1398;
LABEL_42:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v22,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)(unsigned int)v21,
      pdwTypea);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v31);
    goto LABEL_57;
  }
  QueryInterface = g_DeviceEnumerator->lpVtbl[1].QueryInterface;
  wil::com_ptr_t<IMMDeviceCollection,wil::err_returncode_policy>::reset(&v31);
  v21 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, __int64, __int64 **))QueryInterface)(
          g_DeviceEnumerator,
          2,
          9,
          &v31);
  LastError = v21;
  if ( v21 < 0 )
  {
    v22 = 1399;
    goto LABEL_42;
  }
  v21 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*v31 + 24))(v31, &v32);
  LastError = v21;
  if ( v21 < 0 )
  {
    v22 = 1400;
    goto LABEL_42;
  }
  for ( i = 0; i < v32; ++i )
  {
    v34 = 0;
    v25 = *v31;
    v34 = 0;
    if ( (*(int (__fastcall **)(__int64 *, _QWORD, char **))(v25 + 32))(v31, i, &v34) >= 0 )
      (*(void (__fastcall **)(LPVOID, char *, __int64))(*(_QWORD *)ppv + 40LL))(ppv, v34, 4);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v34);
  }
  v36[0] = 0;
  RtlPublishWnfStateData(WNF_AUDC_AEB_INITIALSYNC_COMPLETE, 0, v36, 4);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v31);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&Binding);
  return 0;
}

```

## disassembly

```asm
0x18003984c  push    rbp
0x18003984e  push    rbx
0x18003984f  push    rsi
0x180039850  push    rdi
0x180039851  push    r13
0x180039853  push    r14
0x180039855  lea     rbp, [rsp-1A8h]
0x18003985d  sub     rsp, 2A8h
0x180039864  mov     rax, cs:__security_cookie
0x18003986b  xor     rax, rsp
0x18003986e  mov     [rbp+1D0h+var_40], rax
0x180039875  mov     rdi, cs:?AvEndpointBuilder@@3PEAVCAvEndpointBuilder@@EA; CAvEndpointBuilder * AvEndpointBuilder
0x18003987c  xor     edx, edx; Val
0x18003987e  mov     r8d, 208h; Size
0x180039884  lea     rcx, [rbp+1D0h+Filename]; void *
0x180039888  call    memset_0
0x18003988d  nop
0x18003988e  xor     esi, esi
0x180039890  mov     [rsp+2D0h+Binding], rsi
0x180039895  lea     rcx, [rsp+2D0h+Binding]; Binding
0x18003989a  call    ?GetAEBBindingHandle@@YAJPEAPEAX@Z; GetAEBBindingHandle(void * *)
0x18003989f  mov     ebx, eax
0x1800398a1  test    eax, eax
0x1800398a3  jns     short loc_1800398B2
0x1800398a5  mov     r9d, eax
0x1800398a8  mov     edx, 51Bh
0x1800398ad  jmp     loc_180039CF4
0x1800398b2  call    ?InitializeAEBSvc@@YAJPEAX@Z; InitializeAEBSvc(void *)
0x1800398b7  mov     ebx, eax
0x1800398b9  test    eax, eax
0x1800398bb  jns     short loc_1800398CA
0x1800398bd  mov     r9d, eax
0x1800398c0  mov     edx, 51Ch
0x1800398c5  jmp     loc_180039CF4
0x1800398ca  mov     [rsp+2D0h+dwMilliseconds], esi
0x1800398ce  mov     r14d, 4
0x1800398d4  mov     [rsp+2D0h+var_290], r14d
0x1800398d9  call    cs:__imp_RtlIsStateSeparationEnabled
0x1800398df  test    al, al
0x1800398e1  setz    al
0x1800398e4  mov     [rdi+4Ch], al
0x1800398e7  lea     rax, [rsp+2D0h+var_290]
0x1800398ec  mov     [rsp+2D0h+pcbData], rax; pcbData
0x1800398f1  lea     rax, [rsp+2D0h+dwMilliseconds]
0x1800398f6  mov     [rsp+2D0h+pvData], rax; pvData
0x1800398fb  mov     [rsp+2D0h+pdwType], rsi; pdwType
0x180039900  lea     r9d, [r14+14h]; dwFlags
0x180039904  lea     r8, aSkipaebversion; "SkipAEBVersionCheck"
0x18003990b  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180039912  mov     r13, 0FFFFFFFF80000002h
0x180039919  mov     rcx, r13; hkey
0x18003991c  call    cs:__imp_RegGetValueW
0x180039922  test    eax, eax
0x180039924  jnz     short loc_180039937
0x180039926  cmp     [rsp+2D0h+var_290], r14d
0x18003992b  jnz     short loc_180039937
0x18003992d  cmp     [rsp+2D0h+dwMilliseconds], esi
0x180039931  setnz   al
0x180039934  mov     [rdi+4Ch], al
0x180039937  mov     [rsp+2D0h+var_290], r14d
0x18003993c  lea     rax, [rsp+2D0h+var_290]
0x180039941  mov     [rsp+2D0h+pcbData], rax; pcbData
0x180039946  lea     rax, [rsp+2D0h+dwMilliseconds]
0x18003994b  mov     [rsp+2D0h+pvData], rax; pvData
0x180039950  mov     [rsp+2D0h+pdwType], rsi; int
0x180039955  mov     r9d, 18h; dwFlags
0x18003995b  lea     r8, aAebslowstart; "AEBSlowStart"
0x180039962  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180039969  mov     rcx, r13; hkey
0x18003996c  call    cs:__imp_RegGetValueW
0x180039972  test    eax, eax
0x180039974  jnz     short loc_18003998B
0x180039976  cmp     [rsp+2D0h+var_290], r14d
0x18003997b  jnz     short loc_18003998B
0x18003997d  mov     ecx, [rsp+2D0h+dwMilliseconds]; dwMilliseconds
0x180039981  test    ecx, ecx
0x180039983  jz      short loc_18003998B
0x180039985  call    cs:__imp_Sleep
0x18003998b  mov     ecx, 38h ; '8'; unsigned __int64
0x180039990  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180039995  mov     rbx, rax
0x180039998  mov     [rsp+2D0h+var_270], rax
0x18003999d  test    rax, rax
0x1800399a0  jz      short loc_1800399BA
0x1800399a2  mov     [rax], rsi
0x1800399a5  mov     [rax+8], si
0x1800399a9  lea     rcx, [rax+10h]; lpCriticalSection
0x1800399ad  xor     r8d, r8d; Flags
0x1800399b0  xor     edx, edx; dwSpinCount
0x1800399b2  call    cs:__imp_InitializeCriticalSectionEx
0x1800399b8  jmp     short loc_1800399BD
0x1800399ba  mov     rbx, rsi
0x1800399bd  mov     rdx, rbx
0x1800399c0  call    ?reset@?$unique_ptr@VCUpgradeDiagnostics@@U?$default_delete@VCUpgradeDiagnostics@@@std@@@std@@QEAAXPEAVCUpgradeDiagnostics@@@Z; std::unique_ptr<CUpgradeDiagnostics>::reset(CUpgradeDiagnostics *)
0x1800399c5  cmp     cs:?g_UpgradeDiagnostics@@3V?$unique_ptr@VCUpgradeDiagnostics@@U?$default_delete@VCUpgradeDiagnostics@@@std@@@std@@A, rsi; std::unique_ptr<CUpgradeDiagnostics> g_UpgradeDiagnostics
0x1800399cc  jz      loc_180039CE7
0x1800399d2  mov     r8d, 104h; nSize
0x1800399d8  lea     rdx, [rbp+1D0h+Filename]; lpFilename
0x1800399dc  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hModule
0x1800399e3  call    cs:__imp_GetModuleFileNameW
0x1800399e9  test    eax, eax
0x1800399eb  jnz     short loc_1800399FC
0x1800399ed  mov     ebx, 80004005h
0x1800399f2  mov     edx, 54Ch
0x1800399f7  jmp     loc_180039CF1
0x1800399fc  xor     edx, edx; lpdwHandle
0x1800399fe  lea     rcx, [rbp+1D0h+Filename]; lptstrFilename
0x180039a02  call    cs:__imp_GetFileVersionInfoSizeW
0x180039a08  mov     ebx, eax
0x180039a0a  test    eax, eax
0x180039a0c  jnz     short loc_180039A1D
0x180039a0e  mov     ebx, 80004005h
0x180039a13  mov     edx, 54Fh
0x180039a18  jmp     loc_180039CF1
0x180039a1d  mov     rcx, rbx; unsigned __int64
0x180039a20  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180039a27  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180039a2c  mov     rcx, [rdi+50h]; void *
0x180039a30  mov     [rdi+50h], rax
0x180039a34  test    rcx, rcx
0x180039a37  jz      short loc_180039A3E
0x180039a39  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180039a3e  mov     r9, [rdi+50h]; lpData
0x180039a42  test    r9, r9
0x180039a45  jz      loc_180039CE0
0x180039a4b  mov     r8d, ebx; dwLen
0x180039a4e  xor     edx, edx; dwHandle
0x180039a50  lea     rcx, [rbp+1D0h+Filename]; lptstrFilename
0x180039a54  call    cs:__imp_GetFileVersionInfoW
0x180039a5a  test    eax, eax
0x180039a5c  jnz     short loc_180039A7D
0x180039a5e  mov     edx, 553h; void *
0x180039a63  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x180039a6a  mov     rcx, [rbp+1D8h]; this
0x180039a71  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180039a76  mov     ebx, eax
0x180039a78  jmp     loc_180039D08
0x180039a7d  lea     r8, [rdi+58h]; lplpBuffer
0x180039a81  lea     r9, [rdi+60h]; puLen
0x180039a85  lea     rdx, SubBlock; "\\"
0x180039a8c  mov     rcx, [rdi+50h]; pBlock
0x180039a90  call    cs:__imp_VerQueryValueW
0x180039a96  test    eax, eax
0x180039a98  jnz     short loc_180039AA9
0x180039a9a  mov     ebx, 80004005h
0x180039a9f  mov     edx, 554h
0x180039aa4  jmp     loc_180039CF1
0x180039aa9  cmp     [rdi+60h], esi
0x180039aac  jnz     short loc_180039ABD
0x180039aae  mov     ebx, 80004005h
0x180039ab3  mov     edx, 555h
0x180039ab8  jmp     loc_180039CF1
0x180039abd  mov     [rsp+2D0h+var_290], r14d
0x180039ac2  lea     rax, [rsp+2D0h+var_290]
0x180039ac7  mov     [rsp+2D0h+pcbData], rax; pcbData
0x180039acc  lea     rax, [rsp+2D0h+dwMilliseconds]
0x180039ad1  mov     [rsp+2D0h+pvData], rax; pvData
0x180039ad6  mov     [rsp+2D0h+pdwType], rsi; pdwType
0x180039adb  mov     r9d, 18h; dwFlags
0x180039ae1  lea     r8, aBluetoothendpo; "BluetoothEndpointUnificationTimeoutInSe"...
0x180039ae8  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180039aef  mov     rcx, r13; hkey
0x180039af2  call    cs:__imp_RegGetValueW
0x180039af8  test    eax, eax
0x180039afa  jnz     short loc_180039B0E
0x180039afc  cmp     [rsp+2D0h+var_290], r14d
0x180039b01  jnz     short loc_180039B0E
0x180039b03  mov     eax, [rsp+2D0h+dwMilliseconds]
0x180039b07  test    eax, eax
0x180039b09  jz      short loc_180039B0E
0x180039b0b  mov     [rdi+48h], eax
0x180039b0e  xor     r8d, r8d; pcbe
0x180039b11  mov     rdx, rdi; pv
0x180039b14  lea     rcx, ?BluetoothEndpointUnificationCallback@CAvEndpointBuilder@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180039b1b  call    cs:__imp_CreateThreadpoolTimer
0x180039b21  mov     [rdi+40h], rax
0x180039b25  test    rax, rax
0x180039b28  jnz     short loc_180039B34
0x180039b2a  mov     edx, 563h
0x180039b2f  jmp     loc_180039A63
0x180039b34  lea     rcx, [rdi+68h]; struct CAudioDeviceManager **
0x180039b38  call    ?CreateInstance@CAudioDeviceManager@@SAJPEAPEAV1@@Z; CAudioDeviceManager::CreateInstance(CAudioDeviceManager * *)
0x180039b3d  mov     ebx, eax
0x180039b3f  test    eax, eax
0x180039b41  jns     short loc_180039B50
0x180039b43  mov     r9d, eax
0x180039b46  mov     edx, 567h
0x180039b4b  jmp     loc_180039CF4
0x180039b50  mov     rcx, rdi; lpCriticalSection
0x180039b53  call    ?QueryAndSubscribePostureChangeNotification@CAvEndpointBuilder@@AEAAJXZ; CAvEndpointBuilder::QueryAndSubscribePostureChangeNotification(void)
0x180039b58  mov     ebx, eax
0x180039b5a  test    eax, eax
0x180039b5c  jns     short loc_180039B6B
0x180039b5e  mov     r9d, eax
0x180039b61  mov     edx, 569h
0x180039b66  jmp     loc_180039CF4
0x180039b6b  mov     [rsp+2D0h+var_280], esi
0x180039b6f  mov     [rsp+2D0h+var_288], rsi
0x180039b74  mov     [rsp+2D0h+ppv], rsi
0x180039b79  lea     rax, [rsp+2D0h+ppv]
0x180039b7e  mov     [rsp+2D0h+pdwType], rax; int
0x180039b83  lea     r9, _GUID_6ca19947_8747_46ab_879e_349c4dbb88fb; riid
0x180039b8a  xor     edx, edx; pUnkOuter
0x180039b8c  lea     r8d, [rdx+17h]; dwClsContext
0x180039b90  lea     rcx, _GUID_06cca63e_9941_441b_b004_39f999ada412; rclsid
0x180039b97  call    cs:__imp_CoCreateInstance
0x180039b9d  mov     ebx, eax
0x180039b9f  test    eax, eax
0x180039ba1  jns     short loc_180039BD9
0x180039ba3  mov     edx, 576h; void *
0x180039ba8  mov     rcx, [rbp+1D8h]; this
0x180039baf  mov     r9d, eax; char *
0x180039bb2  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x180039bb9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039bbe  nop
0x180039bbf  lea     rcx, [rsp+2D0h+ppv]
0x180039bc4  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180039bc9  nop
0x180039bca  lea     rcx, [rsp+2D0h+var_288]
0x180039bcf  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180039bd4  jmp     loc_180039D08
0x180039bd9  mov     rax, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x180039be0  mov     rcx, [rax]
0x180039be3  mov     rbx, [rcx+18h]
0x180039be7  lea     rcx, [rsp+2D0h+var_288]
0x180039bec  call    ?reset@?$com_ptr_t@UIMMDeviceCollection@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMMDeviceCollection,wil::err_returncode_policy>::reset(void)
0x180039bf1  lea     r9, [rsp+2D0h+var_288]
0x180039bf6  mov     edx, 2
0x180039bfb  lea     r8d, [rdx+7]
0x180039bff  mov     rcx, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x180039c06  mov     rax, rbx
0x180039c09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039c0e  mov     ebx, eax
0x180039c10  test    eax, eax
0x180039c12  jns     short loc_180039C1B
0x180039c14  mov     edx, 577h
0x180039c19  jmp     short loc_180039BA8
0x180039c1b  mov     rcx, [rsp+2D0h+var_288]
0x180039c20  mov     rax, [rcx]
0x180039c23  lea     rdx, [rsp+2D0h+var_280]
0x180039c28  mov     rax, [rax+18h]
0x180039c2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039c31  mov     ebx, eax
0x180039c33  test    eax, eax
0x180039c35  jns     short loc_180039C41
0x180039c37  mov     edx, 578h
0x180039c3c  jmp     loc_180039BA8
0x180039c41  mov     ebx, esi
0x180039c43  cmp     [rsp+2D0h+var_280], esi
0x180039c47  jbe     short loc_180039C9B
0x180039c49  mov     [rsp+2D0h+var_270], rsi
0x180039c4e  mov     rcx, [rsp+2D0h+var_288]
0x180039c53  mov     rax, [rcx]
0x180039c56  mov     [rsp+2D0h+var_270], rsi
0x180039c5b  lea     r8, [rsp+2D0h+var_270]
0x180039c60  mov     edx, ebx
0x180039c62  mov     rax, [rax+20h]
0x180039c66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039c6b  test    eax, eax
0x180039c6d  js      short loc_180039C89
0x180039c6f  mov     rcx, [rsp+2D0h+ppv]
0x180039c74  mov     rax, [rcx]
0x180039c77  mov     r8d, r14d
0x180039c7a  mov     rdx, [rsp+2D0h+var_270]
0x180039c7f  mov     rax, [rax+28h]
0x180039c83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039c88  nop
0x180039c89  lea     rcx, [rsp+2D0h+var_270]
0x180039c8e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180039c93  inc     ebx
0x180039c95  cmp     ebx, [rsp+2D0h+var_280]
0x180039c99  jb      short loc_180039C49
0x180039c9b  mov     [rsp+2D0h+var_260], esi
0x180039c9f  mov     [rsp+2D0h+pdwType], rsi
0x180039ca4  mov     r9d, r14d
0x180039ca7  lea     r8, [rsp+2D0h+var_260]
0x180039cac  xor     edx, edx
0x180039cae  mov     rcx, cs:WNF_AUDC_AEB_INITIALSYNC_COMPLETE
0x180039cb5  call    cs:__imp_RtlPublishWnfStateData
0x180039cbb  nop
0x180039cbc  lea     rcx, [rsp+2D0h+ppv]
0x180039cc1  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180039cc6  nop
0x180039cc7  lea     rcx, [rsp+2D0h+var_288]
0x180039ccc  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180039cd1  nop
0x180039cd2  lea     rcx, [rsp+2D0h+Binding]
0x180039cd7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?WpRpcBindingFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180039cdc  xor     eax, eax
0x180039cde  jmp     short loc_180039D14
0x180039ce0  mov     edx, 552h
0x180039ce5  jmp     short loc_180039CEC
0x180039ce7  mov     edx, 547h; void *
0x180039cec  mov     ebx, 8007000Eh
0x180039cf1  mov     r9d, ebx; char *
0x180039cf4  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x180039cfb  mov     rcx, [rbp+1D8h]; this
0x180039d02  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039d07  nop
0x180039d08  lea     rcx, [rsp+2D0h+Binding]
  ... truncated ...
```
