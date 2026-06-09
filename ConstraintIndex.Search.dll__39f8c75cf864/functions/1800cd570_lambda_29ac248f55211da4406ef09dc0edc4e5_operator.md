# _lambda_29ac248f55211da4406ef09dc0edc4e5_::operator()

- ea: `0x1800cd570`
- end: `0x1800cda10`
- name: `_lambda_29ac248f55211da4406ef09dc0edc4e5_::operator()`
- size: `1184`
- prototype: ``
- caller_count: `1`
- callee_count: `34`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800d02b0`

## callees

- `0x1800049e0`
- `0x180005e44`
- `0x180005e50`
- `0x18000616e`
- `0x18000617a`
- `0x1800061aa`
- `0x18003b2f4`
- `0x18003fd04`
- `0x18003feb4`
- `0x18003fee0`
- `0x18003ff00`
- `0x18003ff8c`
- `0x18004086c`
- `0x180081870`
- `0x180081a5c`
- `0x1800827f8`
- `0x180086b84`
- `0x18008e508`
- `0x18008fa58`
- `0x180093118`
- `0x1800940f8`
- `0x18009af90`
- `0x1800a457c`
- `0x1800a5428`
- `0x1800a6a94`
- `0x1800a6b24`
- `0x1800a6bb4`
- `0x1800a6c44`
- `0x1800cc8d8`
- `0x1800cd418`
- `0x1800cd570`
- `0x1800ce76c`
- `0x1800ce9b0`
- `0x1800cf6e8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800cd732`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800cd732`
- `wincorlib!?ToString@Guid@Platform@@QEAAPE$AAVString@2@XZ` at `0x1800cd755`
- `wincorlib!?ToString@Guid@Platform@@QEAAPE$AAVString@2@XZ` at `0x1800cd755`
- `wincorlib!?ToString@uint32@default@@QEAAPE$AAVString@Platform@@XZ` at `0x1800cd853`
- `wincorlib!?ToString@uint32@default@@QEAAPE$AAVString@Platform@@XZ` at `0x1800cd8a1`
- `wincorlib!?ToString@uint32@default@@QEAAPE$AAVString@Platform@@XZ` at `0x1800cd853`
- `wincorlib!?ToString@uint32@default@@QEAAPE$AAVString@Platform@@XZ` at `0x1800cd8a1`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
__int64 __fastcall lambda_29ac248f55211da4406ef09dc0edc4e5_::operator()(_QWORD *a1, _QWORD *a2)
{
  _QWORD *v3; // rbx
  __int64 v4; // rdx
  __int64 v5; // rdx
  HSTRING NamespaceSettingsRevision; // rsi
  HSTRING v7; // rdi
  __int64 v8; // rcx
  HSTRING v9; // rdi
  HSTRING v10; // rdi
  HRESULT v11; // eax
  __int64 v12; // rdx
  HSTRING v13; // rsi
  int v14; // esi
  HSTRING v15; // r13
  HRESULT v16; // eax
  HSTRING v17; // r12
  HSTRING v18; // r15
  HSTRING v19; // rsi
  HSTRING v20; // r14
  void *v21; // rsi
  _QWORD *v22; // rdi
  __int64 v23; // rbx
  unsigned int v25; // [rsp+20h] [rbp-288h]
  HSTRING v26; // [rsp+28h] [rbp-280h] BYREF
  __int64 v27; // [rsp+30h] [rbp-278h] BYREF
  _QWORD *v28; // [rsp+38h] [rbp-270h]
  _QWORD *v29; // [rsp+40h] [rbp-268h]
  _QWORD *v30; // [rsp+48h] [rbp-260h]
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-258h] BYREF
  HSTRING v32; // [rsp+68h] [rbp-240h]
  __int64 v33; // [rsp+70h] [rbp-238h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+78h] [rbp-230h] BYREF
  HSTRING_HEADER v35; // [rsp+90h] [rbp-218h] BYREF
  HSTRING CurrentVersion; // [rsp+A8h] [rbp-200h] BYREF
  HSTRING string; // [rsp+B0h] [rbp-1F8h] BYREF
  GUID pguid; // [rsp+B8h] [rbp-1F0h] BYREF
  _BYTE v39[80]; // [rsp+D0h] [rbp-1D8h] BYREF
  _QWORD v40[42]; // [rsp+120h] [rbp-188h] BYREF

  v28 = a2;
  v3 = a1;
  v30 = a1;
  v29 = a2;
  memset_0(v40, 0, sizeof(v40));
  wil::ActivityBase<CortanaSearchTelemetryLogging,1,70368744177664,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CortanaSearchTelemetryLogging,1,70368744177664,4,0,_TlgReflectorTag_Param0IsProviderType>(
    v40,
    v3 + 1);
  v40[0] = &ConstraintIndexTelemetry::SettingsJsonGenerator_UpdateSettingsCacheOnDiskAsync::`vftable';
  memset_0(v39, 0, sizeof(v39));
  wil::ActivityBase<CortanaSearchTelemetryLogging,1,70368744177664,4,0,_TlgReflectorTag_Param0IsProviderType>::ContinueOnCurrentThread(
    (struct wil::details::IFailureCallback *)v40,
    (wil::ActivityThreadWatcher *)v39);
  try
  {
    v25 = 0;
    if ( !*a2 )
      Concurrency::details::_DefaultTaskHelper::_NoCallOnDefaultTask_ErrorImpl();
    if ( (unsigned int)Concurrency::details::_Task_impl_base::_Wait(*a2) == 2 )
    {
      Concurrency::task_canceled::task_canceled((Concurrency::task_canceled *)pExceptionObject);
      throw (Concurrency::task_canceled *)pExceptionObject;
    }
    CurrentVersion = (HSTRING)Cortana::ConstraintIndex::Search::SettingsJsonGenerator::GetCurrentVersion(*(_QWORD *)(*v3 + 48LL));
    v26 = (HSTRING)__abi_winrt_ptr_ctor(*(_QWORD *)(*(_QWORD *)(*v3 + 32LL) + 32LL));
    Cortana::ConstraintIndex::Search::DEUtilities::SetIndexedVersion(v26, v4, CurrentVersion);
    __abi_winrt_ptr_dtor(v26);
    WindowsDeleteString_0(CurrentVersion);
    CurrentVersion = (HSTRING)Cortana::ConstraintIndex::Search::GetUserSettingsDirectoryLanguage();
    v26 = (HSTRING)__abi_winrt_ptr_ctor(*(_QWORD *)(*(_QWORD *)(*v3 + 32LL) + 32LL));
    Cortana::ConstraintIndex::Search::DEUtilities::SetIndexedLanguage(v26, v5, CurrentVersion);
    __abi_winrt_ptr_dtor(v26);
    WindowsDeleteString_0(CurrentVersion);
    CurrentVersion = (HSTRING)__abi_winrt_ptr_ctor(*(_QWORD *)(*(_QWORD *)(*v3 + 32LL) + 32LL));
    NamespaceSettingsRevision = (HSTRING)Cortana::ConstraintIndex::Search::SettingsJsonGenerator::GetNamespaceSettingsRevision(CurrentVersion);
    v7 = (HSTRING)__abi_winrt_ptrto_string_ctor(NamespaceSettingsRevision);
    v26 = v7;
    WindowsDeleteString_0(NamespaceSettingsRevision);
    __abi_winrt_ptr_dtor(CurrentVersion);
    if ( WindowsIsStringEmpty_0(v7) )
    {
      pguid = 0;
      if ( CoCreateGuid(&pguid) >= 0 )
      {
        v8 = Platform::Guid::Guid((Platform::Guid *)&hstringHeader, &pguid);
        v9 = (HSTRING)Platform::Guid::ToString(v8);
        CurrentVersion = v9;
        __abi_winrt_ptrto_string_assign(&v26, v9);
        WindowsDeleteString_0(v9);
        v10 = (HSTRING)__abi_winrt_ptr_ctor(*(_QWORD *)(*(_QWORD *)(*v3 + 32LL) + 32LL));
        CurrentVersion = v10;
        Cortana::ConstraintIndex::Search::DEUtilities::GetConstraintIndexContainer(&v27, v10);
        __abi_winrt_ptr_dtor(v10);
        string = 0;
        v11 = WindowsCreateStringReference_0(L"NamespaceSettingsRevision", 0x19u, &hstringHeader, &string);
        if ( v11 < 0 )
          __abi_WinRTraiseException(v11);
        v7 = v26;
        Cortana::ConstraintIndex::Search::ConstraintIndexRegistryContainer::WriteStringValue(&v27, v12, string, v26);
        __abi_winrt_ptr_dtor(v27);
      }
    }
    v13 = (HSTRING)__abi_winrt_ptr_ctor(*(_QWORD *)(*(_QWORD *)(*v3 + 32LL) + 32LL));
    CurrentVersion = v13;
    Cortana::ConstraintIndex::Search::DEUtilities::SetCachedNamespaceSettingsRevision(v13, v7);
    __abi_winrt_ptr_dtor(v13);
    v14 = Windows::Storage::Streams::IDataReader::UnconsumedBufferLength::get(*(_QWORD *)(*v3 + 48LL));
    LODWORD(v27) = Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue __gc *>::Size::get(*(_QWORD *)(*v3 + 48LL));
    v15 = (HSTRING)default::uint32::ToString(&v27);
    v32 = v15;
    CurrentVersion = 0;
    v16 = WindowsCreateStringReference_0(L".", 1u, &v35, &CurrentVersion);
    if ( v16 < 0 )
      __abi_WinRTraiseException(v16);
    LODWORD(string) = v14;
    v17 = (HSTRING)default::uint32::ToString(&string);
    hstringHeader.Reserved.Reserved1 = v17;
    v18 = (HSTRING)Platform::String::Concat(v17, CurrentVersion);
    CurrentVersion = v18;
    v19 = (HSTRING)Platform::String::Concat(v18, v15);
    *(_QWORD *)&pguid.Data1 = v19;
    v20 = (HSTRING)__abi_winrt_ptrto_string_ctor(v19);
    *(_QWORD *)&pguid.Data1 = v20;
    WindowsDeleteString_0(v19);
    WindowsDeleteString_0(v18);
    WindowsDeleteString_0(v17);
    WindowsDeleteString_0(v15);
    v21 = (void *)__abi_winrt_ptr_ctor(*(_QWORD *)(*(_QWORD *)(*v3 + 32LL) + 32LL));
    hstringHeader.Reserved.Reserved1 = v21;
    Cortana::ConstraintIndex::Search::DEUtilities::SetCachedNamespaceSettingsFeatureState(v21, v20);
    __abi_winrt_ptr_dtor(v21);
    WindowsDeleteString_0(v20);
    WindowsDeleteString_0(v7);
    v22 = v28;
  }
  catch ( Platform::Exception *v33 )
  {
    v25 = *(_DWORD *)(v33 + 64);
    v22 = v29;
    v3 = v30;
  }
  wil::ActivityBase<CortanaSearchTelemetryLogging,1,70368744177664,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
    v40,
    v25);
  v23 = __abi_winrt_ptrto_string_ctor(v3[43]);
  wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v39);
  ConstraintIndexTelemetry::SettingsJsonGenerator_UpdateSettingsCacheOnDiskAsync::~SettingsJsonGenerator_UpdateSettingsCacheOnDiskAsync((ConstraintIndexTelemetry::SettingsJsonGenerator_UpdateSettingsCacheOnDiskAsync *)v40);
  std::shared_ptr<Concurrency::details::_Task_impl<Windows::Foundation::Collections::IVectorView<Cortana::ConstraintIndex::Search::ISettingResultItem __gc *> __gc *>>::~shared_ptr<Concurrency::details::_Task_impl<Windows::Foundation::Collections::IVectorView<Cortana::ConstraintIndex::Search::ISettingResultItem __gc *> __gc *>>(v22);
  return v23;
}

```

## disassembly

```asm
0x1800cd570  mov     [rsp+arg_10], rbx
0x1800cd575  mov     [rsp+arg_18], rsi
0x1800cd57a  push    rdi
0x1800cd57b  push    r12
0x1800cd57d  push    r13
0x1800cd57f  push    r14
0x1800cd581  push    r15
0x1800cd583  sub     rsp, 280h
0x1800cd58a  mov     rax, cs:__security_cookie
0x1800cd591  xor     rax, rsp
0x1800cd594  mov     [rsp+2A8h+var_38], rax
0x1800cd59c  mov     rdi, rdx
0x1800cd59f  mov     [rsp+2A8h+var_270], rdx
0x1800cd5a4  mov     rbx, rcx
0x1800cd5a7  mov     [rsp+2A8h+var_260], rcx
0x1800cd5ac  mov     [rsp+2A8h+var_268], rdx
0x1800cd5b1  xor     edx, edx; Val
0x1800cd5b3  mov     r8d, 150h; Size
0x1800cd5b9  lea     rcx, [rsp+2A8h+var_188]; void *
0x1800cd5c1  call    memset_0
0x1800cd5c6  lea     rdx, [rbx+8]
0x1800cd5ca  lea     rcx, [rsp+2A8h+var_188]
0x1800cd5d2  call    ??0?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$0EAAAAAAAAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@AEBV01@@Z; wil::ActivityBase<CortanaSearchTelemetryLogging,1,70368744177664,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CortanaSearchTelemetryLogging,1,70368744177664,4,0,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<CortanaSearchTelemetryLogging,1,70368744177664,4,0,_TlgReflectorTag_Param0IsProviderType> const &)
0x1800cd5d7  lea     rax, ??_7SettingsJsonGenerator_UpdateSettingsCacheOnDiskAsync@ConstraintIndexTelemetry@@6B@; const ConstraintIndexTelemetry::SettingsJsonGenerator_UpdateSettingsCacheOnDiskAsync::`vftable'
0x1800cd5de  mov     [rsp+2A8h+var_188], rax
0x1800cd5e6  xor     edx, edx; Val
0x1800cd5e8  lea     r8d, [rdx+50h]; Size
0x1800cd5ec  lea     rcx, [rsp+2A8h+var_1D8]; void *
0x1800cd5f4  call    memset_0
0x1800cd5f9  lea     rdx, [rsp+2A8h+var_1D8]; this
0x1800cd601  lea     rcx, [rsp+2A8h+var_188]; struct wil::details::IFailureCallback *
0x1800cd609  call    ?ContinueOnCurrentThread@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$0EAAAAAAAAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA?AVActivityThreadWatcher@2@XZ; wil::ActivityBase<CortanaSearchTelemetryLogging,1,70368744177664,4,0,_TlgReflectorTag_Param0IsProviderType>::ContinueOnCurrentThread(void)
0x1800cd60e  nop
0x1800cd60f  xor     r15d, r15d
0x1800cd612  mov     [rsp+2A8h+var_288], r15d
0x1800cd617  mov     rcx, [rdi]
0x1800cd61a  test    rcx, rcx
0x1800cd61d  jz      loc_1800CD9DD
0x1800cd623  call    ?_Wait@_Task_impl_base@details@Concurrency@@QEAA?AW4task_group_status@3@XZ; Concurrency::details::_Task_impl_base::_Wait(void)
0x1800cd628  cmp     eax, 2
0x1800cd62b  jz      loc_1800CD9E3
0x1800cd631  mov     rcx, [rbx]
0x1800cd634  mov     rcx, [rcx+30h]
0x1800cd638  call    ?GetCurrentVersion@SettingsJsonGenerator@Search@ConstraintIndex@Cortana@@SAPE$AAVString@Platform@@PE$AAVSettingsSearchContentManager@DataModel@SystemSettings@@@Z; Cortana::ConstraintIndex::Search::SettingsJsonGenerator::GetCurrentVersion(SystemSettings::DataModel::SettingsSearchContentManager *)
0x1800cd63d  mov     rsi, rax
0x1800cd640  mov     [rsp+2A8h+var_200], rax
0x1800cd648  mov     rcx, [rbx]
0x1800cd64b  mov     rcx, [rcx+20h]
0x1800cd64f  mov     rcx, [rcx+20h]
0x1800cd653  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x1800cd658  mov     rdi, rax
0x1800cd65b  mov     [rsp+2A8h+var_280], rax
0x1800cd660  mov     r8, rsi
0x1800cd663  mov     rcx, rax
0x1800cd666  call    ?SetIndexedVersion@DEUtilities@Search@ConstraintIndex@Cortana@@SAXPE$AAUIConstraintIndexOptions@234@PE$AAVString@Platform@@1@Z; Cortana::ConstraintIndex::Search::DEUtilities::SetIndexedVersion(Cortana::ConstraintIndex::Search::IConstraintIndexOptions *,Platform::String *,Platform::String *)
0x1800cd66b  nop
0x1800cd66c  mov     rcx, rdi
0x1800cd66f  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x1800cd674  nop
0x1800cd675  mov     rcx, rsi; string
0x1800cd678  call    WindowsDeleteString_0
0x1800cd67d  call    ?GetUserSettingsDirectoryLanguage@Search@ConstraintIndex@Cortana@@YAPE$AAVString@Platform@@XZ; Cortana::ConstraintIndex::Search::GetUserSettingsDirectoryLanguage(void)
0x1800cd682  mov     rsi, rax
0x1800cd685  mov     [rsp+2A8h+var_200], rax
0x1800cd68d  mov     rcx, [rbx]
0x1800cd690  mov     rcx, [rcx+20h]
0x1800cd694  mov     rcx, [rcx+20h]
0x1800cd698  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x1800cd69d  mov     rdi, rax
0x1800cd6a0  mov     [rsp+2A8h+var_280], rax
0x1800cd6a5  mov     r8, rsi
0x1800cd6a8  mov     rcx, rax
0x1800cd6ab  call    ?SetIndexedLanguage@DEUtilities@Search@ConstraintIndex@Cortana@@SAXPE$AAUIConstraintIndexOptions@234@PE$AAVString@Platform@@1@Z; Cortana::ConstraintIndex::Search::DEUtilities::SetIndexedLanguage(Cortana::ConstraintIndex::Search::IConstraintIndexOptions *,Platform::String *,Platform::String *)
0x1800cd6b0  nop
0x1800cd6b1  mov     rcx, rdi
0x1800cd6b4  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x1800cd6b9  nop
0x1800cd6ba  mov     rcx, rsi; string
0x1800cd6bd  call    WindowsDeleteString_0
0x1800cd6c2  mov     rax, [rbx]
0x1800cd6c5  mov     rcx, [rax+20h]
0x1800cd6c9  mov     rcx, [rcx+20h]
0x1800cd6cd  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x1800cd6d2  mov     r14, rax
0x1800cd6d5  mov     [rsp+2A8h+var_200], rax
0x1800cd6dd  mov     rcx, rax
0x1800cd6e0  call    ?GetNamespaceSettingsRevision@SettingsJsonGenerator@Search@ConstraintIndex@Cortana@@SAPE$AAVString@Platform@@PE$AAUIConstraintIndexOptions@234@@Z; Cortana::ConstraintIndex::Search::SettingsJsonGenerator::GetNamespaceSettingsRevision(Cortana::ConstraintIndex::Search::IConstraintIndexOptions *)
0x1800cd6e5  mov     rsi, rax
0x1800cd6e8  mov     [rsp+2A8h+var_280], rax
0x1800cd6ed  mov     rcx, rax
0x1800cd6f0  call    ?__abi_winrt_ptrto_string_ctor@@YAPEAXPE$ADVString@Platform@@@Z; __abi_winrt_ptrto_string_ctor(Platform::String const volatile *)
0x1800cd6f5  mov     rdi, rax
0x1800cd6f8  mov     [rsp+2A8h+var_280], rax
0x1800cd6fd  mov     rcx, rsi; string
0x1800cd700  call    WindowsDeleteString_0
0x1800cd705  nop
0x1800cd706  mov     rcx, r14
0x1800cd709  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x1800cd70e  nop
0x1800cd70f  mov     rcx, rdi; string
0x1800cd712  call    WindowsIsStringEmpty_0
0x1800cd717  test    eax, eax
0x1800cd719  jz      loc_1800CD801
0x1800cd71f  xorps   xmm0, xmm0
0x1800cd722  movups  xmmword ptr [rsp+2A8h+pguid.Data1], xmm0
0x1800cd72a  lea     rcx, [rsp+2A8h+pguid]; pguid
0x1800cd732  call    cs:__imp_CoCreateGuid
0x1800cd738  test    eax, eax
0x1800cd73a  js      loc_1800CD801
0x1800cd740  lea     rdx, [rsp+2A8h+pguid]; struct _GUID *
0x1800cd748  lea     rcx, [rsp+2A8h+hstringHeader]; this
0x1800cd74d  call    ??0Guid@Platform@@QEAA@AEBU_GUID@@@Z; Platform::Guid::Guid(_GUID const &)
0x1800cd752  mov     rcx, rax
0x1800cd755  call    cs:__imp_?ToString@Guid@Platform@@QEAAPE$AAVString@2@XZ; Platform::Guid::ToString(void)
0x1800cd75b  mov     rdi, rax
0x1800cd75e  mov     [rsp+2A8h+var_200], rax
0x1800cd766  mov     rdx, rax
0x1800cd769  lea     rcx, [rsp+2A8h+var_280]
0x1800cd76e  call    ?__abi_winrt_ptrto_string_assign@@YAPEAXPEAPEAXPE$ADVString@Platform@@@Z; __abi_winrt_ptrto_string_assign(void * *,Platform::String const volatile *)
0x1800cd773  nop
0x1800cd774  mov     rcx, rdi; string
0x1800cd777  call    WindowsDeleteString_0
0x1800cd77c  mov     rax, [rbx]
0x1800cd77f  mov     rcx, [rax+20h]
0x1800cd783  mov     rcx, [rcx+20h]
0x1800cd787  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x1800cd78c  mov     rdi, rax
0x1800cd78f  mov     [rsp+2A8h+var_200], rax
0x1800cd797  mov     rdx, rax
0x1800cd79a  lea     rcx, [rsp+2A8h+var_278]
0x1800cd79f  call    ?GetConstraintIndexContainer@DEUtilities@Search@ConstraintIndex@Cortana@@SA?AUConstraintIndexRegistryContainer@234@PE$AAUIConstraintIndexOptions@234@@Z; Cortana::ConstraintIndex::Search::DEUtilities::GetConstraintIndexContainer(Cortana::ConstraintIndex::Search::IConstraintIndexOptions *)
0x1800cd7a4  nop
0x1800cd7a5  mov     rcx, rdi
0x1800cd7a8  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x1800cd7ad  mov     [rsp+2A8h+string], r15
0x1800cd7b5  lea     r9, [rsp+2A8h+string]; string
0x1800cd7bd  lea     r8, [rsp+2A8h+hstringHeader]; hstringHeader
0x1800cd7c2  mov     edx, 19h; length
0x1800cd7c7  lea     rcx, aNamespacesetti; "NamespaceSettingsRevision"
0x1800cd7ce  call    WindowsCreateStringReference_0
0x1800cd7d3  test    eax, eax
0x1800cd7d5  js      loc_1800CD9FF
0x1800cd7db  mov     rdi, [rsp+2A8h+var_280]
0x1800cd7e0  mov     r9, rdi
0x1800cd7e3  mov     r8, [rsp+2A8h+string]
0x1800cd7eb  lea     rcx, [rsp+2A8h+var_278]
0x1800cd7f0  call    ?WriteStringValue@ConstraintIndexRegistryContainer@Search@ConstraintIndex@Cortana@@QEBAXPE$AAVString@Platform@@00@Z; Cortana::ConstraintIndex::Search::ConstraintIndexRegistryContainer::WriteStringValue(Platform::String *,Platform::String *,Platform::String *)
0x1800cd7f5  nop
0x1800cd7f6  mov     rcx, [rsp+2A8h+var_278]
0x1800cd7fb  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x1800cd800  nop
0x1800cd801  mov     rax, [rbx]
0x1800cd804  mov     rcx, [rax+20h]
0x1800cd808  mov     rcx, [rcx+20h]
0x1800cd80c  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x1800cd811  mov     rsi, rax
0x1800cd814  mov     [rsp+2A8h+var_200], rax
0x1800cd81c  mov     rdx, rdi
0x1800cd81f  mov     rcx, rax
0x1800cd822  call    ?SetCachedNamespaceSettingsRevision@DEUtilities@Search@ConstraintIndex@Cortana@@SAXPE$AAUIConstraintIndexOptions@234@PE$AAVString@Platform@@@Z; Cortana::ConstraintIndex::Search::DEUtilities::SetCachedNamespaceSettingsRevision(Cortana::ConstraintIndex::Search::IConstraintIndexOptions *,Platform::String *)
0x1800cd827  nop
0x1800cd828  mov     rcx, rsi
0x1800cd82b  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x1800cd830  mov     rcx, [rbx]
0x1800cd833  mov     rcx, [rcx+30h]
0x1800cd837  call    ?get@UnconsumedBufferLength@IDataReader@Streams@Storage@Windows@@UE$AAAIXZ; Windows::Storage::Streams::IDataReader::UnconsumedBufferLength::get(void)
0x1800cd83c  mov     esi, eax
0x1800cd83e  mov     rcx, [rbx]
0x1800cd841  mov     rcx, [rcx+30h]
0x1800cd845  call    ?get@Size@?$IVector@PE$AAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@UE$AAAIXZ; Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>::Size::get(void)
0x1800cd84a  mov     dword ptr [rsp+2A8h+var_278], eax
0x1800cd84e  lea     rcx, [rsp+2A8h+var_278]
0x1800cd853  call    cs:__imp_?ToString@uint32@default@@QEAAPE$AAVString@Platform@@XZ; default::uint32::ToString(void)
0x1800cd859  mov     r13, rax
0x1800cd85c  mov     [rsp+2A8h+var_240], rax
0x1800cd861  mov     [rsp+2A8h+var_200], r15
0x1800cd869  lea     r9, [rsp+2A8h+var_200]; string
0x1800cd871  lea     r8, [rsp+2A8h+var_218]; hstringHeader
0x1800cd879  mov     edx, 1; length
0x1800cd87e  lea     rcx, asc_18010A4F0; "."
0x1800cd885  call    WindowsCreateStringReference_0
0x1800cd88a  test    eax, eax
0x1800cd88c  js      loc_1800CDA07
0x1800cd892  mov     dword ptr [rsp+2A8h+string], esi
0x1800cd899  lea     rcx, [rsp+2A8h+string]
0x1800cd8a1  call    cs:__imp_?ToString@uint32@default@@QEAAPE$AAVString@Platform@@XZ; default::uint32::ToString(void)
0x1800cd8a7  mov     r12, rax
0x1800cd8aa  mov     qword ptr [rsp+2A8h+hstringHeader.Reserved], rax
0x1800cd8af  mov     rdx, [rsp+2A8h+var_200]
0x1800cd8b7  mov     rcx, rax
0x1800cd8ba  call    ?Concat@String@Platform@@SAPE$AAV12@PE$AAV12@0@Z; Platform::String::Concat(Platform::String *,Platform::String *)
0x1800cd8bf  mov     r15, rax
0x1800cd8c2  mov     [rsp+2A8h+var_200], rax
0x1800cd8ca  mov     rdx, r13
0x1800cd8cd  mov     rcx, rax
0x1800cd8d0  call    ?Concat@String@Platform@@SAPE$AAV12@PE$AAV12@0@Z; Platform::String::Concat(Platform::String *,Platform::String *)
0x1800cd8d5  mov     rsi, rax
0x1800cd8d8  mov     qword ptr [rsp+2A8h+pguid.Data1], rax
0x1800cd8e0  mov     rcx, rax
0x1800cd8e3  call    ?__abi_winrt_ptrto_string_ctor@@YAPEAXPE$ADVString@Platform@@@Z; __abi_winrt_ptrto_string_ctor(Platform::String const volatile *)
0x1800cd8e8  mov     r14, rax
0x1800cd8eb  mov     qword ptr [rsp+2A8h+pguid.Data1], rax
0x1800cd8f3  mov     rcx, rsi; string
0x1800cd8f6  call    WindowsDeleteString_0
0x1800cd8fb  nop
0x1800cd8fc  mov     rcx, r15; string
0x1800cd8ff  call    WindowsDeleteString_0
0x1800cd904  nop
0x1800cd905  mov     rcx, r12; string
0x1800cd908  call    WindowsDeleteString_0
0x1800cd90d  nop
0x1800cd90e  mov     rcx, r13; string
0x1800cd911  call    WindowsDeleteString_0
0x1800cd916  nop
0x1800cd917  mov     rax, [rbx]
0x1800cd91a  mov     rcx, [rax+20h]
0x1800cd91e  mov     rcx, [rcx+20h]
0x1800cd922  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x1800cd927  mov     rsi, rax
0x1800cd92a  mov     qword ptr [rsp+2A8h+hstringHeader.Reserved], rax
0x1800cd92f  mov     rdx, r14
0x1800cd932  mov     rcx, rax
0x1800cd935  call    ?SetCachedNamespaceSettingsFeatureState@DEUtilities@Search@ConstraintIndex@Cortana@@SAXPE$AAUIConstraintIndexOptions@234@PE$AAVString@Platform@@@Z; Cortana::ConstraintIndex::Search::DEUtilities::SetCachedNamespaceSettingsFeatureState(Cortana::ConstraintIndex::Search::IConstraintIndexOptions *,Platform::String *)
0x1800cd93a  nop
0x1800cd93b  mov     rcx, rsi
0x1800cd93e  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x1800cd943  nop
0x1800cd944  mov     rcx, r14; string
0x1800cd947  call    WindowsDeleteString_0
0x1800cd94c  nop
0x1800cd94d  mov     rcx, rdi; string
0x1800cd950  call    WindowsDeleteString_0
0x1800cd955  nop
0x1800cd956  mov     rdi, [rsp+2A8h+var_270]
0x1800cd95b  jmp     short loc_1800CD967
0x1800cd95d  mov     rdi, [rsp+2A8h+var_268]
0x1800cd962  mov     rbx, [rsp+2A8h+var_260]
0x1800cd967  mov     eax, [rsp+2A8h+var_288]
0x1800cd96b  mov     edx, eax
0x1800cd96d  lea     rcx, [rsp+2A8h+var_188]
0x1800cd975  call    ?Stop@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$0EAAAAAAAAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<CortanaSearchTelemetryLogging,1,70368744177664,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800cd97a  mov     rcx, [rbx+158h]
0x1800cd981  call    ?__abi_winrt_ptrto_string_ctor@@YAPEAXPE$ADVString@Platform@@@Z; __abi_winrt_ptrto_string_ctor(Platform::String const volatile *)
0x1800cd986  mov     rbx, rax
0x1800cd989  lea     rcx, [rsp+2A8h+var_1D8]; this
0x1800cd991  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x1800cd996  nop
0x1800cd997  lea     rcx, [rsp+2A8h+var_188]; this
0x1800cd99f  call    ??1SettingsJsonGenerator_UpdateSettingsCacheOnDiskAsync@ConstraintIndexTelemetry@@QEAA@XZ; ConstraintIndexTelemetry::SettingsJsonGenerator_UpdateSettingsCacheOnDiskAsync::~SettingsJsonGenerator_UpdateSettingsCacheOnDiskAsync(void)
0x1800cd9a4  nop
0x1800cd9a5  mov     rcx, rdi
0x1800cd9a8  call    ??1?$shared_ptr@U?$_Task_impl@PE$AAU?$IVectorView@PE$AAUISettingResultItem@Search@ConstraintIndex@Cortana@@@Collections@Foundation@Windows@@@details@Concurrency@@@std@@QEAA@XZ; std::shared_ptr<Concurrency::details::_Task_impl<Windows::Foundation::Collections::IVectorView<Cortana::ConstraintIndex::Search::ISettingResultItem *> *>>::~shared_ptr<Concurrency::details::_Task_impl<Windows::Foundation::Collections::IVectorView<Cortana::ConstraintIndex::Search::ISettingResultItem *> *>>(void)
0x1800cd9ad  mov     rax, rbx
0x1800cd9b0  mov     rcx, [rsp+2A8h+var_38]
0x1800cd9b8  xor     rcx, rsp; StackCookie
0x1800cd9bb  call    __security_check_cookie
0x1800cd9c0  lea     r11, [rsp+2A8h+var_28]
0x1800cd9c8  mov     rbx, [r11+40h]
0x1800cd9cc  mov     rsi, [r11+48h]
0x1800cd9d0  mov     rsp, r11
0x1800cd9d3  pop     r15
0x1800cd9d5  pop     r14
0x1800cd9d7  pop     r13
0x1800cd9d9  pop     r12
0x1800cd9db  pop     rdi
0x1800cd9dc  retn
0x1800cd9dd  call    ?_NoCallOnDefaultTask_ErrorImpl@_DefaultTaskHelper@details@Concurrency@@SAXXZ; Concurrency::details::_DefaultTaskHelper::_NoCallOnDefaultTask_ErrorImpl(void)
0x1800cd9e3  lea     rcx, [rsp+2A8h+pExceptionObject]; this
0x1800cd9e8  call    ??0task_canceled@Concurrency@@QEAA@XZ; Concurrency::task_canceled::task_canceled(void)
0x1800cd9ed  lea     rdx, _TI2?AVtask_canceled@Concurrency@@; pThrowInfo
0x1800cd9f4  lea     rcx, [rsp+2A8h+pExceptionObject]; pExceptionObject
0x1800cd9f9  call    _CxxThrowException_0
0x1800cd9ff  mov     ecx, eax; int
0x1800cda01  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
0x1800cda07  mov     ecx, eax; int
0x1800cda09  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
```
