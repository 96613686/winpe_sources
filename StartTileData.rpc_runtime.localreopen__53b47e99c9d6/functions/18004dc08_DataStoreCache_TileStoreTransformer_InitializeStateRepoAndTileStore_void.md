# DataStoreCache::TileStoreTransformer::InitializeStateRepoAndTileStore(void)

- ea: `0x18004dc08`
- end: `0x18004e140`
- name: `?InitializeStateRepoAndTileStore@TileStoreTransformer@DataStoreCache@@AEAAXXZ`
- size: `1336`
- prototype: `void __fastcall(DataStoreCache::TileStoreTransformer *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004dbc8`

## callees

- `0x18000ce94`
- `0x18001dac0`
- `0x180020aac`
- `0x180021dd8`
- `0x180021f7c`
- `0x18003d71c`
- `0x18004dc08`
- `0x18004e72c`
- `0x18004e7e4`
- `0x18004e884`
- `0x18004f218`
- `0x18004ffc0`
- `0x180201e50`
- `0x18035e220`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004dc87`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004dc87`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004dfdd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004dfdd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004e03c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004e04e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004e060`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004e072`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004e03c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004e04e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004e060`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004e072`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004dcb4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004ddeb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004de4d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004dee8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004dcb4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004ddeb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004de4d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004dee8`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18004dce0`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18004de1a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18004de7c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18004df17`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18004dce0`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18004de1a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18004de7c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18004df17`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18004deaa`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18004df45`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18004deaa`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18004df45`
- `ntdll!RtlIsMultiSessionSku` at `0x18004e112`
- `ntdll!RtlIsMultiSessionSku` at `0x18004e112`

## string_xrefs

- `0x18004e07c`: `shellcommon\shell\datastorecache\transformers\tilestore\lib\tilestoretransformer.cpp`
- `0x18004e091`: `shellcommon\shell\datastorecache\transformers\tilestore\lib\tilestoretransformer.cpp`
- `0x18004e0a6`: `shellcommon\shell\datastorecache\transformers\tilestore\lib\tilestoretransformer.cpp`
- `0x18004e0bb`: `shellcommon\shell\datastorecache\transformers\tilestore\lib\tilestoretransformer.cpp`
- `0x18004e0d0`: `shellcommon\shell\datastorecache\transformers\tilestore\lib\tilestoretransformer.cpp`
- `0x18004e0e5`: `shellcommon\shell\datastorecache\transformers\tilestore\lib\tilestoretransformer.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall DataStoreCache::TileStoreTransformer::InitializeStateRepoAndTileStore(
        DataStoreCache::TileStoreTransformer *this)
{
  unsigned int v2; // ebx
  HRESULT v3; // eax
  HSTRING v4; // rbx
  int ActivationFactory; // eax
  wil::details::in1diag3 *v6; // rcx
  __int64 v7; // rsi
  __int64 (__fastcall *v8)(__int64, _QWORD, char *); // rdi
  int v9; // eax
  char *StateRepositoryUser; // rax
  __int64 v11; // rcx
  __int64 v12; // rdx
  wil *v13; // rcx
  HRESULT v14; // eax
  HSTRING v15; // rdi
  int v16; // eax
  HRESULT v17; // eax
  HSTRING v18; // rdi
  int v19; // eax
  wil::details::in1diag3 *v20; // rcx
  HRESULT v21; // eax
  HSTRING v22; // rdi
  int v23; // eax
  int v24; // eax
  __int64 v25; // rcx
  char v26; // al
  int v27[2]; // [rsp+20h] [rbp-1C8h] BYREF
  _QWORD v28[2]; // [rsp+28h] [rbp-1C0h] BYREF
  char v29; // [rsp+38h] [rbp-1B0h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-1A8h] BYREF
  HSTRING string; // [rsp+58h] [rbp-190h] BYREF
  _QWORD v32[42]; // [rsp+60h] [rbp-188h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+0h]

  v2 = _InterlockedIncrement((volatile signed __int32 *)this + 100);
  wil::ActivityBase<DataStoreTransformerLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DataStoreTransformerLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v32,
    "TileStoreTransformerInitializeStateRepoAndTileStore");
  v32[0] = &DataStoreTransformerTelemetry::TileStoreTransformerInitializeStateRepoAndTileStore::`vftable';
  DataStoreTransformerTelemetry::TileStoreTransformerInitializeStateRepoAndTileStore::StartActivity(
    (DataStoreTransformerTelemetry::TileStoreTransformerInitializeStateRepoAndTileStore *)v32,
    v2);
  DataStoreCache::TileStoreTransformer::UnregisterForTileStoreEvents(this);
  AcquireSRWLockExclusive((PSRWLOCK)this + 19);
  v28[1] = (char *)this + 152;
  v28[0] = 0;
  string = 0;
  v3 = WindowsCreateStringReference(L"Windows.Internal.Tiles.TileStore", 0x20u, &hstringHeader, &string);
  if ( v3 < 0 )
  {
    RaiseException(v3, 1u, 0, 0);
    __debugbreak();
  }
  v4 = string;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v28);
  ActivationFactory = RoGetActivationFactory(v4, &GUID_3a1f4546_cb54_4968_a3f8_fa93f2fe6b40, v28);
  v6 = retaddr;
  if ( ActivationFactory < 0 )
    goto LABEL_33;
  v7 = v28[0];
  v8 = *(__int64 (__fastcall **)(__int64, _QWORD, char *))(*(_QWORD *)v28[0] + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 344);
  v9 = v8(v7, *((_QWORD *)this + 54), (char *)this + 344);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x54A,
      (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\tilestore\\lib\\tilestoretransformer.cpp",
      (const char *)(unsigned int)v9,
      v27[0]);
  try
  {
    StateRepositoryUser = (char *)UserHelpers::GetStateRepositoryUser();
    v11 = 0;
    if ( &v29 != StateRepositoryUser )
    {
      v11 = *(_QWORD *)StateRepositoryUser;
      *(_QWORD *)StateRepositoryUser = 0;
    }
    v12 = *((_QWORD *)this + 42);
    *((_QWORD *)this + 42) = v11;
    if ( v12 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    v13 = *(wil **)v27;
    if ( *(_QWORD *)v27 )
    {
      *(_QWORD *)v27 = 0;
      (*(void (__fastcall **)(wil *))(*(_QWORD *)v13 + 16LL))(v13);
    }
  }
  catch ( ... )
  {
    v27[0] = wil::ResultFromCaughtException(v13);
    DataStoreTransformerTelemetry::TileStoreTransformerInitializeStateRepoAndTileStore::StateRepoUserNotFound<long>(
      v32,
      v27);
    throw;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 360);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 352);
  DataStoreCache::TileStoreTransformer::CreateTileStoreQueryFilters(
    *((unsigned int *)this + 104),
    *((unsigned int *)this + 105),
    (char *)this + 352,
    (char *)this + 360);
  string = 0;
  v14 = WindowsCreateStringReference(L"Windows.Internal.StateRepository.TileView", 0x29u, &hstringHeader, &string);
  if ( v14 < 0 )
  {
    RaiseException(v14, 1u, 0, 0);
    __debugbreak();
  }
  v15 = string;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 296);
  v16 = RoGetActivationFactory(v15, &GUID_61424521_07b6_40d2_9323_b78cdae5eb61, (char *)this + 296);
  if ( v16 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x560,
      (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\tilestore\\lib\\tilestoretransformer.cpp",
      (const char *)(unsigned int)v16,
      v27[0]);
  string = 0;
  v17 = WindowsCreateStringReference(L"Windows.Internal.StateRepository.PackageUser", 0x2Cu, &hstringHeader, &string);
  if ( v17 < 0 )
  {
    RaiseException(v17, 1u, 0, 0);
    __debugbreak();
  }
  v18 = string;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 312);
  v19 = RoGetActivationFactory(v18, &GUID_bd9205c6_e02a_4ad3_8174_8b4c3a7e0ef6, (char *)this + 312);
  v20 = retaddr;
  if ( v19 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x561,
      (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\tilestore\\lib\\tilestoretransformer.cpp",
      (const char *)(unsigned int)v19,
      v27[0]);
  if ( !`Details::GetDeviceFamily'::`2'::s_hasChecked )
  {
    v27[0] = 0;
    RtlGetDeviceFamilyInfoEnum(0, v27, 0);
    `Details::GetDeviceFamily'::`2'::s_platform = v27[0];
    `Details::GetDeviceFamily'::`2'::s_hasChecked = 1;
  }
  if ( `Details::GetDeviceFamily'::`2'::s_platform == 3
    || `Details::GetDeviceFamily'::`2'::s_platform == 9
    || `Details::GetDeviceFamily'::`2'::s_platform == 6
    && (`Details::GetIsMultiSessionSku'::`2'::s_hasChecked
      ? (v26 = `Details::GetIsMultiSessionSku'::`2'::s_isMultiSession)
      : (v26 = (unsigned __int8)RtlIsMultiSessionSku(v20) != 0,
         `Details::GetIsMultiSessionSku'::`2'::s_isMultiSession = v26,
         `Details::GetIsMultiSessionSku'::`2'::s_hasChecked = 1),
        v26) )
  {
    string = 0;
    v21 = WindowsCreateStringReference(L"Windows.Internal.StateRepository.HostRuntime", 0x2Cu, &hstringHeader, &string);
    if ( v21 >= 0 )
    {
      v22 = string;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 320);
      v23 = RoGetActivationFactory(v22, &GUID_1493f40f_2e38_4bbc_a161_93f5bdf6d056, (char *)this + 320);
      if ( v23 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x566,
          (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\tilestore\\lib\\tilestoretransformer.cpp",
          (const char *)(unsigned int)v23,
          v27[0]);
      goto LABEL_20;
    }
    RaiseException(v21, 1u, 0, 0);
LABEL_33:
    wil::details::in1diag3::Throw_Hr(
      v6,
      (void *)0x546,
      (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\tilestore\\lib\\tilestoretransformer.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v27[0]);
  }
LABEL_20:
  if ( !`Details::GetDeviceFamily'::`2'::s_hasChecked )
  {
    v27[0] = 0;
    RtlGetDeviceFamilyInfoEnum(0, v27, 0);
    `Details::GetDeviceFamily'::`2'::s_platform = v27[0];
    `Details::GetDeviceFamily'::`2'::s_hasChecked = 1;
  }
  if ( ((`Details::GetDeviceFamily'::`2'::s_platform - 14) & 0xFFFFFFFD) == 0 )
  {
    string = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Internal.StateRepository.Package",
      0x29u,
      0x28u);
    v24 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageStatics>>(
            string,
            (char *)this + 304);
    if ( v24 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x56C,
        (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\tilestore\\lib\\tilestoretransformer.cpp",
        (const char *)(unsigned int)v24,
        v27[0]);
  }
  wil::ActivityBase<DataStoreTransformerLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v32);
  v25 = v28[0];
  if ( v28[0] )
  {
    v28[0] = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  }
  if ( this != (DataStoreCache::TileStoreTransformer *)-152LL )
    ReleaseSRWLockExclusive((PSRWLOCK)this + 19);
  v32[0] = &DataStoreTransformerTelemetry::TileStoreTransformerInitializeStateRepoAndTileStore::`vftable';
  wil::ActivityBase<DataStoreTransformerLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v32);
  wil::ActivityBase<DataStoreTransformerLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DataStoreTransformerLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v32);
}

```

## disassembly

```asm
0x18004dc08  mov     [rsp+arg_8], rbx
0x18004dc0d  mov     [rsp+arg_10], rsi
0x18004dc12  push    rdi
0x18004dc13  push    r12
0x18004dc15  push    r13
0x18004dc17  push    r14
0x18004dc19  push    r15
0x18004dc1b  sub     rsp, 1C0h
0x18004dc22  mov     rax, cs:__security_cookie
0x18004dc29  xor     rax, rsp
0x18004dc2c  mov     [rsp+1E8h+var_38], rax
0x18004dc34  mov     r14, rcx
0x18004dc37  mov     r13d, 1
0x18004dc3d  mov     ebx, r13d
0x18004dc40  lock xadd [rcx+190h], ebx
0x18004dc48  add     ebx, r13d
0x18004dc4b  lea     rdx, aTilestoretrans_10; "TileStoreTransformerInitializeStateRepo"...
0x18004dc52  lea     rcx, [rsp+1E8h+var_188]
0x18004dc57  call    ??0?$ActivityBase@VDataStoreTransformerLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<DataStoreTransformerLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DataStoreTransformerLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18004dc5c  lea     rax, ??_7TileStoreTransformerInitializeStateRepoAndTileStore@DataStoreTransformerTelemetry@@6B@; const DataStoreTransformerTelemetry::TileStoreTransformerInitializeStateRepoAndTileStore::`vftable'
0x18004dc63  mov     [rsp+1E8h+var_188], rax
0x18004dc68  mov     edx, ebx; unsigned int
0x18004dc6a  lea     rcx, [rsp+1E8h+var_188]; this
0x18004dc6f  call    ?StartActivity@TileStoreTransformerInitializeStateRepoAndTileStore@DataStoreTransformerTelemetry@@QEAAXI@Z; DataStoreTransformerTelemetry::TileStoreTransformerInitializeStateRepoAndTileStore::StartActivity(uint)
0x18004dc74  nop
0x18004dc75  mov     rcx, r14; this
0x18004dc78  call    ?UnregisterForTileStoreEvents@TileStoreTransformer@DataStoreCache@@AEAAXXZ; DataStoreCache::TileStoreTransformer::UnregisterForTileStoreEvents(void)
0x18004dc7d  lea     r15, [r14+98h]
0x18004dc84  mov     rcx, r15; SRWLock
0x18004dc87  call    cs:__imp_AcquireSRWLockExclusive
0x18004dc8d  mov     [rsp+1E8h+var_1B8], r15
0x18004dc92  xor     r12d, r12d
0x18004dc95  mov     [rsp+1E8h+var_1C0], r12
0x18004dc9a  mov     [rsp+1E8h+string], r12
0x18004dc9f  lea     r9, [rsp+1E8h+string]; string
0x18004dca4  lea     r8, [rsp+1E8h+hstringHeader]; hstringHeader
0x18004dca9  lea     edx, [r13+1Fh]; length
0x18004dcad  lea     rcx, ?RuntimeClass_Windows_Internal_Tiles_TileStore@@3QBGB; "Windows.Internal.Tiles.TileStore"
0x18004dcb4  call    cs:__imp_WindowsCreateStringReference
0x18004dcba  test    eax, eax
0x18004dcbc  js      loc_18004E031
0x18004dcc2  mov     rbx, [rsp+1E8h+string]
0x18004dcc7  lea     rcx, [rsp+1E8h+var_1C0]
0x18004dccc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004dcd1  lea     r8, [rsp+1E8h+var_1C0]
0x18004dcd6  lea     rdx, _GUID_3a1f4546_cb54_4968_a3f8_fa93f2fe6b40
0x18004dcdd  mov     rcx, rbx
0x18004dce0  call    cs:__imp_RoGetActivationFactory
0x18004dce6  mov     rcx, [rsp+1E8h]
0x18004dcee  test    eax, eax
0x18004dcf0  js      loc_18004E079
0x18004dcf6  mov     rsi, [rsp+1E8h+var_1C0]
0x18004dcfb  mov     rax, [rsi]
0x18004dcfe  mov     rdi, [rax+30h]
0x18004dd02  lea     rbx, [r14+158h]
0x18004dd09  mov     rcx, rbx
0x18004dd0c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004dd11  mov     r8, rbx
0x18004dd14  mov     rdx, [r14+1B0h]
0x18004dd1b  mov     rcx, rsi
0x18004dd1e  mov     rax, rdi
0x18004dd21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dd26  mov     rcx, [rsp+1E8h]; this
0x18004dd2e  test    eax, eax
0x18004dd30  js      loc_18004E08E
0x18004dd36  mov     rdx, [r14+1B0h]
0x18004dd3d  lea     rcx, [rsp+1E8h+var_1C8]
0x18004dd42  call    ?GetStateRepositoryUser@UserHelpers@@YA?AV?$ComPtr@UIUser@StateRepository@Internal@Windows@@@WRL@Microsoft@@PEAUIUser@System@Windows@@@Z; UserHelpers::GetStateRepositoryUser(Windows::System::IUser *)
0x18004dd47  mov     ecx, r12d
0x18004dd4a  lea     rdx, [rsp+1E8h+var_1B0]
0x18004dd4f  cmp     rdx, rax
0x18004dd52  jz      short loc_18004DD5A
0x18004dd54  mov     rcx, [rax]
0x18004dd57  mov     [rax], r12
0x18004dd5a  mov     rdx, [r14+150h]
0x18004dd61  mov     [r14+150h], rcx
0x18004dd68  test    rdx, rdx
0x18004dd6b  jz      short loc_18004DD7D
0x18004dd6d  mov     rax, [rdx]
0x18004dd70  mov     rcx, rdx
0x18004dd73  mov     rax, [rax+10h]
0x18004dd77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dd7c  nop
0x18004dd7d  mov     rcx, qword ptr [rsp+1E8h+var_1C8]
0x18004dd82  test    rcx, rcx
0x18004dd85  jz      short loc_18004DD99
0x18004dd87  mov     qword ptr [rsp+1E8h+var_1C8], r12; int
0x18004dd8c  mov     rax, [rcx]
0x18004dd8f  mov     rax, [rax+10h]
0x18004dd93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dd98  nop
0x18004dd99  lea     rdi, [r14+168h]
0x18004dda0  mov     rcx, rdi
0x18004dda3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004dda8  lea     rbx, [r14+160h]
0x18004ddaf  mov     rcx, rbx
0x18004ddb2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004ddb7  mov     r9, rdi
0x18004ddba  mov     r8, rbx
0x18004ddbd  mov     edx, [r14+1A4h]
0x18004ddc4  mov     ecx, [r14+1A0h]
0x18004ddcb  call    ?CreateTileStoreQueryFilters@TileStoreTransformer@DataStoreCache@@CAXW4PackagedTileEnumerationFilters@UnifiedTile@Shell@WindowsInternal@@0PEAPEAUITileQueryFilter@Tiles@Internal@Windows@@1@Z; DataStoreCache::TileStoreTransformer::CreateTileStoreQueryFilters(WindowsInternal::Shell::UnifiedTile::PackagedTileEnumerationFilters,WindowsInternal::Shell::UnifiedTile::PackagedTileEnumerationFilters,Windows::Internal::Tiles::ITileQueryFilter * *,Windows::Internal::Tiles::ITileQueryFilter * *)
0x18004ddd0  mov     [rsp+1E8h+string], r12
0x18004ddd5  lea     r9, [rsp+1E8h+string]; string
0x18004ddda  lea     r8, [rsp+1E8h+hstringHeader]; hstringHeader
0x18004dddf  mov     edx, 29h ; ')'; length
0x18004dde4  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_TileView@@3QBGB; "Windows.Internal.StateRepository.TileVi"...
0x18004ddeb  call    cs:__imp_WindowsCreateStringReference
0x18004ddf1  test    eax, eax
0x18004ddf3  js      loc_18004E043
0x18004ddf9  lea     rbx, [r14+128h]
0x18004de00  mov     rdi, [rsp+1E8h+string]
0x18004de05  mov     rcx, rbx
0x18004de08  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004de0d  mov     r8, rbx
0x18004de10  lea     rdx, _GUID_61424521_07b6_40d2_9323_b78cdae5eb61
0x18004de17  mov     rcx, rdi
0x18004de1a  call    cs:__imp_RoGetActivationFactory
0x18004de20  mov     rcx, [rsp+1E8h]; this
0x18004de28  test    eax, eax
0x18004de2a  js      loc_18004E0A3
0x18004de30  mov     [rsp+1E8h+string], r12
0x18004de35  lea     r9, [rsp+1E8h+string]; string
0x18004de3a  lea     r8, [rsp+1E8h+hstringHeader]; hstringHeader
0x18004de3f  mov     esi, 2Ch ; ','
0x18004de44  mov     edx, esi; length
0x18004de46  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_PackageUser@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x18004de4d  call    cs:__imp_WindowsCreateStringReference
0x18004de53  test    eax, eax
0x18004de55  js      loc_18004E055
0x18004de5b  lea     rbx, [r14+138h]
0x18004de62  mov     rdi, [rsp+1E8h+string]
0x18004de67  mov     rcx, rbx
0x18004de6a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004de6f  mov     r8, rbx
0x18004de72  lea     rdx, _GUID_bd9205c6_e02a_4ad3_8174_8b4c3a7e0ef6
0x18004de79  mov     rcx, rdi
0x18004de7c  call    cs:__imp_RoGetActivationFactory
0x18004de82  mov     rcx, [rsp+1E8h]; this
0x18004de8a  test    eax, eax
0x18004de8c  js      loc_18004E0B8
0x18004de92  cmp     cs:?s_hasChecked@?1??GetDeviceFamily@Details@@YAKXZ@4_NA, r12b; bool `Details::GetDeviceFamily(void)'::`2'::s_hasChecked
0x18004de99  jnz     short loc_18004DEC1
0x18004de9b  mov     [rsp+1E8h+var_1C8], r12d; int
0x18004dea0  xor     r8d, r8d
0x18004dea3  lea     rdx, [rsp+1E8h+var_1C8]
0x18004dea8  xor     ecx, ecx
0x18004deaa  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x18004deb0  mov     eax, [rsp+1E8h+var_1C8]
0x18004deb4  mov     cs:?s_platform@?1??GetDeviceFamily@Details@@YAKXZ@4KA, eax; ulong `Details::GetDeviceFamily(void)'::`2'::s_platform
0x18004deba  mov     cs:?s_hasChecked@?1??GetDeviceFamily@Details@@YAKXZ@4_NA, r13b; bool `Details::GetDeviceFamily(void)'::`2'::s_hasChecked
0x18004dec1  mov     eax, cs:?s_platform@?1??GetDeviceFamily@Details@@YAKXZ@4KA; ulong `Details::GetDeviceFamily(void)'::`2'::s_platform
0x18004dec7  cmp     eax, 3
0x18004deca  jnz     loc_18004E0F7
0x18004ded0  mov     [rsp+1E8h+string], r12
0x18004ded5  lea     r9, [rsp+1E8h+string]; string
0x18004deda  lea     r8, [rsp+1E8h+hstringHeader]; hstringHeader
0x18004dedf  mov     edx, esi; length
0x18004dee1  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_HostRuntime@@3QBGB; "Windows.Internal.StateRepository.HostRu"...
0x18004dee8  call    cs:__imp_WindowsCreateStringReference
0x18004deee  test    eax, eax
0x18004def0  js      loc_18004E067
0x18004def6  lea     rbx, [r14+140h]
0x18004defd  mov     rdi, [rsp+1E8h+string]
0x18004df02  mov     rcx, rbx
0x18004df05  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004df0a  mov     r8, rbx
0x18004df0d  lea     rdx, _GUID_1493f40f_2e38_4bbc_a161_93f5bdf6d056
0x18004df14  mov     rcx, rdi
0x18004df17  call    cs:__imp_RoGetActivationFactory
0x18004df1d  mov     rcx, [rsp+1E8h]; this
0x18004df25  test    eax, eax
0x18004df27  js      loc_18004E0CD
0x18004df2d  cmp     cs:?s_hasChecked@?1??GetDeviceFamily@Details@@YAKXZ@4_NA, r12b; bool `Details::GetDeviceFamily(void)'::`2'::s_hasChecked
0x18004df34  jnz     short loc_18004DF5C
0x18004df36  mov     [rsp+1E8h+var_1C8], r12d; int
0x18004df3b  xor     r8d, r8d
0x18004df3e  lea     rdx, [rsp+1E8h+var_1C8]
0x18004df43  xor     ecx, ecx
0x18004df45  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x18004df4b  mov     eax, [rsp+1E8h+var_1C8]
0x18004df4f  mov     cs:?s_platform@?1??GetDeviceFamily@Details@@YAKXZ@4KA, eax; ulong `Details::GetDeviceFamily(void)'::`2'::s_platform
0x18004df55  mov     cs:?s_hasChecked@?1??GetDeviceFamily@Details@@YAKXZ@4_NA, r13b; bool `Details::GetDeviceFamily(void)'::`2'::s_hasChecked
0x18004df5c  mov     eax, cs:?s_platform@?1??GetDeviceFamily@Details@@YAKXZ@4KA; ulong `Details::GetDeviceFamily(void)'::`2'::s_platform
0x18004df62  add     eax, 0FFFFFFF2h
0x18004df65  test    eax, 0FFFFFFFDh
0x18004df6a  jnz     short loc_18004DFAE
0x18004df6c  mov     [rsp+1E8h+string], r12
0x18004df71  mov     r9d, 28h ; '('; unsigned int
0x18004df77  lea     r8d, [r9+1]; unsigned int
0x18004df7b  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_Package@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x18004df82  lea     rcx, [rsp+1E8h+hstringHeader]; hstringHeader
0x18004df87  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18004df8c  nop
0x18004df8d  lea     rdx, [r14+130h]
0x18004df94  mov     rcx, [rsp+1E8h+string]
0x18004df99  call    ??$GetActivationFactory@V?$ComPtr@UIPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageStatics>>)
0x18004df9e  mov     rcx, [rsp+1E8h]; this
0x18004dfa6  test    eax, eax
0x18004dfa8  js      loc_18004E0E2
0x18004dfae  lea     rcx, [rsp+1E8h+var_188]
0x18004dfb3  call    ?Stop@?$ActivityBase@VDataStoreTransformerLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<DataStoreTransformerLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18004dfb8  nop
0x18004dfb9  mov     rcx, [rsp+1E8h+var_1C0]
0x18004dfbe  test    rcx, rcx
0x18004dfc1  jz      short loc_18004DFD5
0x18004dfc3  mov     [rsp+1E8h+var_1C0], r12
0x18004dfc8  mov     rax, [rcx]
0x18004dfcb  mov     rax, [rax+10h]
0x18004dfcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dfd4  nop
0x18004dfd5  test    r15, r15
0x18004dfd8  jz      short loc_18004DFE4
0x18004dfda  mov     rcx, r15; SRWLock
0x18004dfdd  call    cs:__imp_ReleaseSRWLockExclusive
0x18004dfe3  nop
0x18004dfe4  lea     rax, ??_7TileStoreTransformerInitializeStateRepoAndTileStore@DataStoreTransformerTelemetry@@6B@; const DataStoreTransformerTelemetry::TileStoreTransformerInitializeStateRepoAndTileStore::`vftable'
0x18004dfeb  mov     [rsp+1E8h+var_188], rax
0x18004dff0  lea     rcx, [rsp+1E8h+var_188]
0x18004dff5  call    ?Destroy@?$ActivityBase@VDataStoreTransformerLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<DataStoreTransformerLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18004dffa  lea     rcx, [rsp+1E8h+var_188]
0x18004dfff  call    ??1?$ActivityBase@VDataStoreTransformerLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<DataStoreTransformerLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DataStoreTransformerLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18004e004  mov     rcx, [rsp+1E8h+var_38]
0x18004e00c  xor     rcx, rsp; StackCookie
0x18004e00f  call    __security_check_cookie
0x18004e014  lea     r11, [rsp+1E8h+var_28]
0x18004e01c  mov     rbx, [r11+38h]
0x18004e020  mov     rsi, [r11+40h]
0x18004e024  mov     rsp, r11
0x18004e027  pop     r15
0x18004e029  pop     r14
0x18004e02b  pop     r13
0x18004e02d  pop     r12
0x18004e02f  pop     rdi
0x18004e030  retn
0x18004e031  xor     r9d, r9d; lpArguments
0x18004e034  xor     r8d, r8d; nNumberOfArguments
0x18004e037  mov     edx, r13d; dwExceptionFlags
0x18004e03a  mov     ecx, eax; dwExceptionCode
0x18004e03c  call    cs:__imp_RaiseException
0x18004e042  int     3; Trap to Debugger
0x18004e043  xor     r9d, r9d; lpArguments
0x18004e046  xor     r8d, r8d; nNumberOfArguments
0x18004e049  mov     edx, r13d; dwExceptionFlags
0x18004e04c  mov     ecx, eax; dwExceptionCode
0x18004e04e  call    cs:__imp_RaiseException
0x18004e054  int     3; Trap to Debugger
0x18004e055  xor     r9d, r9d; lpArguments
0x18004e058  xor     r8d, r8d; nNumberOfArguments
0x18004e05b  mov     edx, r13d; dwExceptionFlags
0x18004e05e  mov     ecx, eax; dwExceptionCode
0x18004e060  call    cs:__imp_RaiseException
0x18004e066  int     3; Trap to Debugger
0x18004e067  xor     r9d, r9d; lpArguments
0x18004e06a  xor     r8d, r8d; nNumberOfArguments
0x18004e06d  mov     edx, r13d; dwExceptionFlags
0x18004e070  mov     ecx, eax; dwExceptionCode
0x18004e072  call    cs:__imp_RaiseException
0x18004e078  nop
0x18004e079  mov     r9d, eax; char *
0x18004e07c  lea     r8, aShellcommonShe_151; "shellcommon\\shell\\datastorecache\\tra"...
0x18004e083  mov     edx, 546h; void *
0x18004e088  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004e08e  mov     r9d, eax; char *
0x18004e091  lea     r8, aShellcommonShe_151; "shellcommon\\shell\\datastorecache\\tra"...
0x18004e098  mov     edx, 54Ah; void *
0x18004e09d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004e0a3  mov     r9d, eax; char *
0x18004e0a6  lea     r8, aShellcommonShe_151; "shellcommon\\shell\\datastorecache\\tra"...
0x18004e0ad  mov     edx, 560h; void *
0x18004e0b2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004e0b8  mov     r9d, eax; char *
0x18004e0bb  lea     r8, aShellcommonShe_151; "shellcommon\\shell\\datastorecache\\tra"...
0x18004e0c2  mov     edx, 561h; void *
0x18004e0c7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004e0cd  mov     r9d, eax; char *
0x18004e0d0  lea     r8, aShellcommonShe_151; "shellcommon\\shell\\datastorecache\\tra"...
0x18004e0d7  mov     edx, 566h; void *
0x18004e0dc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004e0e2  mov     r9d, eax; char *
0x18004e0e5  lea     r8, aShellcommonShe_151; "shellcommon\\shell\\datastorecache\\tra"...
0x18004e0ec  mov     edx, 56Ch; void *
0x18004e0f1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004e0f7  cmp     eax, 9
0x18004e0fa  jz      loc_18004DED0
0x18004e100  cmp     eax, 6
0x18004e103  jnz     loc_18004DF2D
0x18004e109  cmp     cs:?s_hasChecked@?1??GetIsMultiSessionSku@Details@@YAKXZ@4_NA, r12b; bool `Details::GetIsMultiSessionSku(void)'::`2'::s_hasChecked
0x18004e110  jnz     short loc_18004E12C
0x18004e112  call    cs:__imp_RtlIsMultiSessionSku
0x18004e118  test    al, al
0x18004e11a  setnz   al
0x18004e11d  mov     cs:?s_isMultiSession@?1??GetIsMultiSessionSku@Details@@YAKXZ@4_NA, al; bool `Details::GetIsMultiSessionSku(void)'::`2'::s_isMultiSession
0x18004e123  mov     cs:?s_hasChecked@?1??GetIsMultiSessionSku@Details@@YAKXZ@4_NA, r13b; bool `Details::GetIsMultiSessionSku(void)'::`2'::s_hasChecked
0x18004e12a  jmp     short loc_18004E132
0x18004e12c  mov     al, cs:?s_isMultiSession@?1??GetIsMultiSessionSku@Details@@YAKXZ@4_NA; bool `Details::GetIsMultiSessionSku(void)'::`2'::s_isMultiSession
0x18004e132  test    al, al
0x18004e134  jz      loc_18004DF2D
0x18004e13a  jmp     loc_18004DED0
```
