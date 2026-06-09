# Windows::Internal::StateRepository::PrimaryTileUserNotifierServer::add_Changed(Windows::Foundation::ITypedEventHandler<Windows::Internal::StateRepository::PrimaryTileUserNotifier *,Windows::Internal::StateRepository::PrimaryTileUserChangedEventArgs *> *,EventRegistrationToken *)

- ea: `0x180020ec0`
- end: `0x180021297`
- name: `?add_Changed@PrimaryTileUserNotifierServer@StateRepository@Internal@Windows@@UEAAJPEAU?$ITypedEventHandler@PEAVPrimaryTileUserNotifier@StateRepository@Internal@Windows@@PEAVPrimaryTileUserChangedEventArgs@234@@Foundation@4@PEAUEventRegistrationToken@@@Z`
- size: `983`
- prototype: `__int64 __fastcall(_QWORD *, __int64, __int64)`
- caller_count: `0`
- callee_count: `19`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180002980`
- `0x180005340`
- `0x1800075e4`
- `0x18000b348`
- `0x180019f40`
- `0x18001b7d4`
- `0x18001e2e8`
- `0x18001e660`
- `0x18001e834`
- `0x18001eab0`
- `0x18001ef04`
- `0x18001f030`
- `0x18001ff58`
- `0x180020644`
- `0x1800207e4`
- `0x180020ec0`
- `0x180025ecc`
- `0x180026498`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180020f37`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180020f37`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180021039`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180021039`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180020f1f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180020f1f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180021007`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180021007`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180020f5b`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180020f5b`

## pseudocode

```c
__int64 __fastcall Windows::Internal::StateRepository::PrimaryTileUserNotifierServer::add_Changed(
        _QWORD *a1,
        __int64 a2,
        __int64 a3)
{
  HSTRING v6; // rbx
  int ActivationFactory; // eax
  int v8; // ebx
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, _QWORD, _QWORD); // rbx
  int v11; // eax
  __int64 v12; // rdx
  __int64 (__fastcall ***v13)(_QWORD, _QWORD, _QWORD); // rdi
  HSTRING *v14; // r14
  __int64 (__fastcall *v15)(_QWORD, GUID *, HSTRING *); // rbx
  HSTRING v16; // rcx
  PCWSTR StringRawBuffer; // rax
  int v18; // eax
  void *v19; // rdx
  _QWORD *v20; // rax
  unsigned int v21; // edx
  __int64 (__fastcall ***v22)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v23)(_QWORD, GUID *, HSTRING *); // rdi
  int v24; // eax
  unsigned __int8 *v25; // r9
  __int64 v26; // rdx
  StateRepository::WinRT::CoreApplication *v27; // rcx
  void *v29; // rdx
  struct IInspectable v30; // [rsp+20h] [rbp-B9h] BYREF
  __int64 (__fastcall ***v31)(_QWORD, GUID *, HSTRING *); // [rsp+28h] [rbp-B1h] BYREF
  __int64 v32; // [rsp+30h] [rbp-A9h] BYREF
  wil::details *v33; // [rsp+38h] [rbp-A1h] BYREF
  HSTRING v34; // [rsp+40h] [rbp-99h] BYREF
  _QWORD *v35; // [rsp+48h] [rbp-91h] BYREF
  wil::details::event_watcher_state *v36; // [rsp+50h] [rbp-89h] BYREF
  HSTRING string; // [rsp+58h] [rbp-81h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp-79h] BYREF
  char v39[8]; // [rsp+78h] [rbp-61h] BYREF
  char v40[104]; // [rsp+80h] [rbp-59h] BYREF
  __int64 v41; // [rsp+E8h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+5Fh]

  if ( !Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::Internal::StateRepository::SecondaryTileUserNotifier *,Windows::Internal::StateRepository::SecondaryTileUserChangedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::GetSize(a1 + 11) )
  {
    v32 = 0;
    if ( WindowsCreateStringReference(
           L"Windows.Internal.StateRepository.PrimaryTileUserNotificationChannel",
           0x43u,
           &hstringHeader,
           &string) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    v6 = string;
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v32);
    ActivationFactory = RoGetActivationFactory(v6, &GUID_b17fc34b_d906_4cd1_ad70_c16d125d1686, &v32);
    v8 = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3F,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\windows.internal.staterepository.pri"
                      "marytileusernotifier.cpp",
        (const char *)(unsigned int)ActivationFactory,
        (int)v30.lpVtbl);
LABEL_27:
      Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v32);
      return (unsigned int)v8;
    }
    v31 = 0;
    v9 = v32;
    v10 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v32 + 56LL);
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v31);
    v11 = v10(v9, a1[9], &v31);
    v8 = v11;
    if ( v11 < 0 )
    {
      v12 = 65;
LABEL_8:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v12,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\windows.internal.staterepository.pri"
                      "marytileusernotifier.cpp",
        (const char *)(unsigned int)v11,
        (int)v30.lpVtbl);
LABEL_26:
      Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v31);
      goto LABEL_27;
    }
    v11 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, HSTRING *)))(*v31)[6])(v31);
    v8 = v11;
    if ( v11 < 0 )
    {
      v12 = 68;
      goto LABEL_8;
    }
    v13 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v31;
    v14 = (HSTRING *)(a1 + 8);
    v15 = (*v31)[9];
    WindowsDeleteString((HSTRING)a1[8]);
    a1[8] = 0;
    v11 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD), _QWORD *))v15)(v13, a1 + 8);
    v8 = v11;
    if ( v11 < 0 )
    {
      v12 = 71;
      goto LABEL_8;
    }
    v16 = *v14;
    v33 = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(v16, 0);
    v18 = _open___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJPEBGK_N_Z(
            &v33,
            StringRawBuffer);
    v8 = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x49,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\windows.internal.staterepository.pri"
                      "marytileusernotifier.cpp",
        (const char *)(unsigned int)v18,
        (int)v30.lpVtbl);
LABEL_25:
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
        &v33,
        v19);
      goto LABEL_26;
    }
    v35 = a1;
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::SecondaryTileUserNotifierServer>::InternalAddRef(&v35);
    v35 = a1;
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::SecondaryTileUserNotifierServer>::InternalAddRef(&v35);
    v41 = 0;
    v41 = wistd::__function::__func__lambda_ea0836fc14460d04a7929eb0dff71c21__void___cdecl_void__::__func__lambda_ea0836fc14460d04a7929eb0dff71c21__void___cdecl_void__(
            v40,
            &v35);
    if ( v35 )
      ((void (*)(void))Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::StateRepository::ISecondaryTileUserNotifier,Microsoft::WRL::FtmBase>::Release)();
    v20 = wil::make_event_watcher_nothrow<wil::err_returncode_policy>(&v36, (__int64 *)&v33, (__int64)v39);
    wil::unique_any_t<wil::event_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&void wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>>::operator=(
      a1 + 10,
      v20);
    wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&void wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&void wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>(
      &v36,
      v21);
    wistd::function<void (void)>::~function<void (void)>(v39);
    if ( !a1[10] )
    {
      v8 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x51,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\windows.internal.staterepository.pri"
                      "marytileusernotifier.cpp",
        (const char *)0x8007000ELL,
        (int)v30.lpVtbl);
LABEL_24:
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::StateRepository::ISecondaryTileUserNotifier,Microsoft::WRL::FtmBase>::Release(a1);
      goto LABEL_25;
    }
    v22 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v31;
    v34 = 0;
    v23 = **v31;
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v34);
    v24 = v23(v22, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, &v34);
    v8 = v24;
    if ( v24 < 0 )
    {
      v26 = 85;
LABEL_23:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v26,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\windows.internal.staterepository.pri"
                      "marytileusernotifier.cpp",
        (const char *)(unsigned int)v24,
        (int)v30.lpVtbl);
      Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v34);
      goto LABEL_24;
    }
    v27 = (StateRepository::WinRT::CoreApplication *)*v14;
    LOBYTE(v30.lpVtbl) = 0;
    v24 = StateRepository::WinRT::CoreApplication::SetPrivateProperty(v27, v34, &v30, v25);
    v8 = v24;
    if ( v24 < 0 )
    {
      v26 = 87;
      goto LABEL_23;
    }
    if ( LOBYTE(v30.lpVtbl) )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v34);
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::StateRepository::ISecondaryTileUserNotifier,Microsoft::WRL::FtmBase>::Release(a1);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
      &v33,
      v29);
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v31);
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v32);
  }
  if ( !a2 )
  {
    v8 = -2147024809;
LABEL_39:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5C,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\windows.internal.staterepository.prima"
                    "rytileusernotifier.cpp",
      (const char *)(unsigned int)v8,
      (int)v30.lpVtbl);
    return (unsigned int)v8;
  }
  v32 = 0;
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v32);
  v8 = Microsoft::WRL::Details::CreateAgileHelper<Windows::Foundation::ITypedEventHandler<Windows::Internal::StateRepository::PrimaryTileUserNotifier *,Windows::Internal::StateRepository::PrimaryTileUserChangedEventArgs *>>(
         a2,
         &v32);
  if ( v8 >= 0 )
  {
    if ( v32 )
      v8 = Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::Internal::StateRepository::SecondaryTileUserNotifier *,Windows::Internal::StateRepository::SecondaryTileUserChangedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::AddInternal(
             a1 + 11,
             v32,
             *(_QWORD *)(*(_QWORD *)a2 + 24LL),
             a3);
    else
      v8 = -2147024809;
  }
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v32);
  if ( v8 < 0 )
    goto LABEL_39;
  return 0;
}

```

## disassembly

```asm
0x180020ec0  mov     [rsp-8+arg_18], rbx
0x180020ec5  push    rbp
0x180020ec6  push    rsi
0x180020ec7  push    rdi
0x180020ec8  push    r12
0x180020eca  push    r13
0x180020ecc  push    r14
0x180020ece  push    r15
0x180020ed0  lea     rbp, [rsp-27h]
0x180020ed5  sub     rsp, 100h
0x180020edc  mov     rax, cs:__security_cookie
0x180020ee3  xor     rax, rsp
0x180020ee6  mov     [rbp+57h+var_40], rax
0x180020eea  mov     rsi, rcx
0x180020eed  mov     r13, r8
0x180020ef0  add     rcx, 58h ; 'X'
0x180020ef4  mov     r15, rdx
0x180020ef7  call    ?GetSize@?$EventSource@U?$ITypedEventHandler@PEAVSecondaryTileUserNotifier@StateRepository@Internal@Windows@@PEAVSecondaryTileUserChangedEventArgs@234@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEBA_KXZ; Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::Internal::StateRepository::SecondaryTileUserNotifier *,Windows::Internal::StateRepository::SecondaryTileUserChangedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::GetSize(void)
0x180020efc  xor     edi, edi
0x180020efe  test    rax, rax
0x180020f01  jnz     loc_1800211EF
0x180020f07  lea     r9, [rsp+130h+string]; string
0x180020f0c  mov     [rsp+130h+var_100], rdi
0x180020f11  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180020f15  lea     edx, [rdi+43h]; length
0x180020f18  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_PrimaryTileUserNotificationChannel@@3QBGB; "Windows.Internal.StateRepository.Primar"...
0x180020f1f  call    cs:__imp_WindowsCreateStringReference
0x180020f25  test    eax, eax
0x180020f27  jns     short loc_180020F3D
0x180020f29  xor     r9d, r9d; lpArguments
0x180020f2c  lea     edx, [rdi+1]; dwExceptionFlags
0x180020f2f  xor     r8d, r8d; nNumberOfArguments
0x180020f32  mov     ecx, 0C000000Dh; dwExceptionCode
0x180020f37  call    cs:__imp_RaiseException
0x180020f3d  mov     rbx, [rsp+130h+string]
0x180020f42  lea     rcx, [rsp+130h+var_100]
0x180020f47  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x180020f4c  lea     r8, [rsp+130h+var_100]
0x180020f51  mov     rcx, rbx
0x180020f54  lea     rdx, _GUID_b17fc34b_d906_4cd1_ad70_c16d125d1686
0x180020f5b  call    cs:__imp_RoGetActivationFactory
0x180020f61  mov     ebx, eax
0x180020f63  test    eax, eax
0x180020f65  jns     short loc_180020F84
0x180020f67  mov     rcx, [rbp+5Fh]; this
0x180020f6b  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\staterepositor"...
0x180020f72  mov     r9d, eax; char *
0x180020f75  mov     edx, 3Fh ; '?'; void *
0x180020f7a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020f7f  jmp     loc_1800211A2
0x180020f84  mov     [rsp+130h+var_108], rdi
0x180020f89  lea     rcx, [rsp+130h+var_108]
0x180020f8e  mov     rdi, [rsp+130h+var_100]
0x180020f93  mov     rax, [rdi]
0x180020f96  mov     rbx, [rax+38h]
0x180020f9a  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x180020f9f  mov     rdx, [rsi+48h]
0x180020fa3  lea     r8, [rsp+130h+var_108]
0x180020fa8  mov     rcx, rdi
0x180020fab  mov     rax, rbx
0x180020fae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020fb3  mov     ebx, eax
0x180020fb5  test    eax, eax
0x180020fb7  jns     short loc_180020FD6
0x180020fb9  mov     edx, 41h ; 'A'; void *
0x180020fbe  mov     rcx, [rbp+5Fh]; this
0x180020fc2  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\staterepositor"...
0x180020fc9  mov     r9d, eax; char *
0x180020fcc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020fd1  jmp     loc_180021198
0x180020fd6  mov     rcx, [rsp+130h+var_108]
0x180020fdb  mov     rax, [rcx]
0x180020fde  mov     rax, [rax+30h]
0x180020fe2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020fe7  mov     ebx, eax
0x180020fe9  test    eax, eax
0x180020feb  jns     short loc_180020FF4
0x180020fed  mov     edx, 44h ; 'D'
0x180020ff2  jmp     short loc_180020FBE
0x180020ff4  mov     rdi, [rsp+130h+var_108]
0x180020ff9  lea     r14, [rsi+40h]
0x180020ffd  mov     rcx, [r14]; string
0x180021000  mov     rax, [rdi]
0x180021003  mov     rbx, [rax+48h]
0x180021007  call    cs:__imp_WindowsDeleteString
0x18002100d  mov     rdx, r14
0x180021010  mov     qword ptr [r14], 0
0x180021017  mov     rcx, rdi
0x18002101a  mov     rax, rbx
0x18002101d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021022  xor     edi, edi
0x180021024  mov     ebx, eax
0x180021026  test    eax, eax
0x180021028  jns     short loc_18002102F
0x18002102a  lea     edx, [rdi+47h]
0x18002102d  jmp     short loc_180020FBE
0x18002102f  mov     rcx, [r14]; string
0x180021032  xor     edx, edx; length
0x180021034  mov     [rsp+130h+var_F8], rdi
0x180021039  call    cs:__imp_WindowsGetStringRawBuffer
0x18002103f  mov     rdx, rax
0x180021042  lea     rcx, [rsp+130h+var_F8]
0x180021047  call    ?open@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJPEBGK_N@Z
0x18002104c  mov     ebx, eax
0x18002104e  test    eax, eax
0x180021050  jns     short loc_18002106F
0x180021052  mov     rcx, [rbp+5Fh]; this
0x180021056  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\staterepositor"...
0x18002105d  mov     r9d, eax; char *
0x180021060  mov     edx, 49h ; 'I'; void *
0x180021065  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002106a  jmp     loc_18002118E
0x18002106f  lea     rcx, [rsp+130h+var_E8]
0x180021074  mov     [rsp+130h+var_E8], rsi
0x180021079  call    ?InternalAddRef@?$ComPtr@VSecondaryTileUserNotifierServer@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::SecondaryTileUserNotifierServer>::InternalAddRef(void)
0x18002107e  lea     rcx, [rsp+130h+var_E8]
0x180021083  mov     [rsp+130h+var_E8], rsi
0x180021088  call    ?InternalAddRef@?$ComPtr@VSecondaryTileUserNotifierServer@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::SecondaryTileUserNotifierServer>::InternalAddRef(void)
0x18002108d  lea     rdx, [rsp+130h+var_E8]
0x180021092  mov     [rbp+57h+var_48], rdi
0x180021096  lea     rcx, [rbp+57h+var_B0]
0x18002109a  call    wistd____function____func__lambda_ea0836fc14460d04a7929eb0dff71c21__void___cdecl_void______func__lambda_ea0836fc14460d04a7929eb0dff71c21__void___cdecl_void__
0x18002109f  mov     rcx, [rsp+130h+var_E8]
0x1800210a4  mov     [rbp+57h+var_48], rax
0x1800210a8  test    rcx, rcx
0x1800210ab  jz      short loc_1800210B2
0x1800210ad  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UISecondaryTileUserNotifier@StateRepository@Internal@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::StateRepository::ISecondaryTileUserNotifier,Microsoft::WRL::FtmBase>::Release(void)
0x1800210b2  lea     r8, [rbp+57h+var_B8]
0x1800210b6  lea     rdx, [rsp+130h+var_F8]
0x1800210bb  lea     rcx, [rsp+130h+var_E0]
0x1800210c0  call    ??$make_event_watcher_nothrow@Uerr_returncode_policy@wil@@@wil@@YA?AV?$unique_any_t@V?$event_watcher_t@V?$unique_storage@U?$resource_policy@PEAUevent_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_event_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@0@$$QEAV?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@0@$$QEAV?$function@$$A6AXXZ@wistd@@@Z
0x1800210c5  mov     rdx, rax
0x1800210c8  lea     rcx, [rsi+50h]
0x1800210cc  call    ??4?$unique_any_t@V?$event_watcher_t@V?$unique_storage@U?$resource_policy@PEAUevent_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_event_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::event_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>>::operator=(wil::unique_any_t<wil::event_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>> &&)
0x1800210d1  lea     rcx, [rsp+130h+var_E0]
0x1800210d6  call    ??1?$unique_storage@U?$resource_policy@PEAUevent_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_event_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>(void)
0x1800210db  lea     rcx, [rbp+57h+var_B8]
0x1800210df  call    ??1?$function@$$A6AXXZ@wistd@@QEAA@XZ; wistd::function<void (void)>::~function<void (void)>(void)
0x1800210e4  cmp     [rsi+50h], rdi
0x1800210e8  jnz     short loc_180021109
0x1800210ea  mov     rcx, [rbp+5Fh]; this
0x1800210ee  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\staterepositor"...
0x1800210f5  mov     ebx, 8007000Eh
0x1800210fa  mov     edx, 51h ; 'Q'; void *
0x1800210ff  mov     r9d, ebx; char *
0x180021102  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021107  jmp     short loc_180021186
0x180021109  mov     rbx, [rsp+130h+var_108]
0x18002110e  lea     rcx, [rsp+130h+var_F0]
0x180021113  mov     [rsp+130h+var_F0], rdi
0x180021118  mov     rax, [rbx]
0x18002111b  mov     rdi, [rax]
0x18002111e  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x180021123  lea     r8, [rsp+130h+var_F0]
0x180021128  mov     rcx, rbx
0x18002112b  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90
0x180021132  mov     rax, rdi
0x180021135  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002113a  xor     edi, edi
0x18002113c  mov     ebx, eax
0x18002113e  test    eax, eax
0x180021140  jns     short loc_180021147
0x180021142  lea     edx, [rdi+55h]
0x180021145  jmp     short loc_180021169
0x180021147  mov     rdx, [rsp+130h+var_F0]; HSTRING
0x18002114c  lea     r8, [rsp+130h+var_110]; struct IInspectable *
0x180021151  mov     rcx, [r14]; this
0x180021154  mov     byte ptr [rsp+130h+var_110.lpVtbl], dil; int
0x180021159  call    ?SetPrivateProperty@CoreApplication@WinRT@StateRepository@@YAJPEAUHSTRING__@@PEAUIInspectable@@PEAE@Z; StateRepository::WinRT::CoreApplication::SetPrivateProperty(HSTRING__ *,IInspectable *,uchar *)
0x18002115e  mov     ebx, eax
0x180021160  test    eax, eax
0x180021162  jns     short loc_1800211B3
0x180021164  mov     edx, 57h ; 'W'; void *
0x180021169  mov     rcx, [rbp+5Fh]; this
0x18002116d  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\staterepositor"...
0x180021174  mov     r9d, eax; char *
0x180021177  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002117c  lea     rcx, [rsp+130h+var_F0]
0x180021181  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x180021186  mov     rcx, rsi
0x180021189  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UISecondaryTileUserNotifier@StateRepository@Internal@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::StateRepository::ISecondaryTileUserNotifier,Microsoft::WRL::FtmBase>::Release(void)
0x18002118e  lea     rcx, [rsp+130h+var_F8]
0x180021193  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180021198  lea     rcx, [rsp+130h+var_108]
0x18002119d  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x1800211a2  lea     rcx, [rsp+130h+var_100]
0x1800211a7  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x1800211ac  mov     eax, ebx
0x1800211ae  jmp     loc_180021270
0x1800211b3  cmp     byte ptr [rsp+130h+var_110.lpVtbl], dil
0x1800211b8  jz      short loc_1800211BF
0x1800211ba  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800211bf  lea     rcx, [rsp+130h+var_F0]
0x1800211c4  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x1800211c9  mov     rcx, rsi
0x1800211cc  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UISecondaryTileUserNotifier@StateRepository@Internal@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::StateRepository::ISecondaryTileUserNotifier,Microsoft::WRL::FtmBase>::Release(void)
0x1800211d1  lea     rcx, [rsp+130h+var_F8]
0x1800211d6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800211db  lea     rcx, [rsp+130h+var_108]
0x1800211e0  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x1800211e5  lea     rcx, [rsp+130h+var_100]
0x1800211ea  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x1800211ef  test    r15, r15
0x1800211f2  jnz     short loc_1800211FB
0x1800211f4  mov     ebx, 80070057h
0x1800211f9  jmp     short loc_180021251
0x1800211fb  lea     rcx, [rsp+130h+var_100]
0x180021200  mov     [rsp+130h+var_100], rdi
0x180021205  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x18002120a  lea     rdx, [rsp+130h+var_100]
0x18002120f  mov     rcx, r15
0x180021212  call    ??$CreateAgileHelper@U?$ITypedEventHandler@PEAVPrimaryTileUserNotifier@StateRepository@Internal@Windows@@PEAVPrimaryTileUserChangedEventArgs@234@@Foundation@Windows@@@Details@WRL@Microsoft@@YAJPEAU?$ITypedEventHandler@PEAVPrimaryTileUserNotifier@StateRepository@Internal@Windows@@PEAVPrimaryTileUserChangedEventArgs@234@@Foundation@Windows@@PEAPEAU345@@Z; Microsoft::WRL::Details::CreateAgileHelper<Windows::Foundation::ITypedEventHandler<Windows::Internal::StateRepository::PrimaryTileUserNotifier *,Windows::Internal::StateRepository::PrimaryTileUserChangedEventArgs *>>(Windows::Foundation::ITypedEventHandler<Windows::Internal::StateRepository::PrimaryTileUserNotifier *,Windows::Internal::StateRepository::PrimaryTileUserChangedEventArgs *> *,Windows::Foundation::ITypedEventHandler<Windows::Internal::StateRepository::PrimaryTileUserNotifier *,Windows::Internal::StateRepository::PrimaryTileUserChangedEventArgs *> * *)
0x180021217  mov     ebx, eax
0x180021219  test    eax, eax
0x18002121b  js      short loc_180021243
0x18002121d  mov     rdx, [rsp+130h+var_100]
0x180021222  test    rdx, rdx
0x180021225  jnz     short loc_18002122E
0x180021227  mov     ebx, 80070057h
0x18002122c  jmp     short loc_180021243
0x18002122e  mov     r8, [r15]
0x180021231  lea     rcx, [rsi+58h]
0x180021235  mov     r9, r13
0x180021238  mov     r8, [r8+18h]
0x18002123c  call    ?AddInternal@?$EventSource@U?$ITypedEventHandler@PEAVSecondaryTileUserNotifier@StateRepository@Internal@Windows@@PEAVSecondaryTileUserChangedEventArgs@234@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@AEAAJPEAU?$ITypedEventHandler@PEAVSecondaryTileUserNotifier@StateRepository@Internal@Windows@@PEAVSecondaryTileUserChangedEventArgs@234@@Foundation@Windows@@PEAXPEAUEventRegistrationToken@@@Z; Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::Internal::StateRepository::SecondaryTileUserNotifier *,Windows::Internal::StateRepository::SecondaryTileUserChangedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::AddInternal(Windows::Foundation::ITypedEventHandler<Windows::Internal::StateRepository::SecondaryTileUserNotifier *,Windows::Internal::StateRepository::SecondaryTileUserChangedEventArgs *> *,void *,EventRegistrationToken *)
0x180021241  mov     ebx, eax
0x180021243  lea     rcx, [rsp+130h+var_100]
0x180021248  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x18002124d  test    ebx, ebx
0x18002124f  jns     short loc_18002126E
0x180021251  mov     rcx, [rbp+5Fh]; this
0x180021255  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\staterepositor"...
0x18002125c  mov     r9d, ebx; char *
0x18002125f  mov     edx, 5Ch ; '\'; void *
0x180021264  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021269  jmp     loc_1800211AC
0x18002126e  xor     eax, eax
0x180021270  mov     rcx, [rbp+57h+var_40]
0x180021274  xor     rcx, rsp; StackCookie
0x180021277  call    __security_check_cookie
0x18002127c  mov     rbx, [rsp+130h+arg_18]
0x180021284  add     rsp, 100h
0x18002128b  pop     r15
0x18002128d  pop     r14
0x18002128f  pop     r13
0x180021291  pop     r12
0x180021293  pop     rdi
0x180021294  pop     rsi
0x180021295  pop     rbp
0x180021296  retn
```
