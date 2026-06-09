# Windows::Internal::StateRepository::SecondaryTileUserNotifierServer::add_Changed(Windows::Foundation::ITypedEventHandler<Windows::Internal::StateRepository::SecondaryTileUserNotifier *,Windows::Internal::StateRepository::SecondaryTileUserChangedEventArgs *> *,EventRegistrationToken *)

- ea: `0x18001f9f0`
- end: `0x18001fdc7`
- name: `?add_Changed@SecondaryTileUserNotifierServer@StateRepository@Internal@Windows@@UEAAJPEAU?$ITypedEventHandler@PEAVSecondaryTileUserNotifier@StateRepository@Internal@Windows@@PEAVSecondaryTileUserChangedEventArgs@234@@Foundation@4@PEAUEventRegistrationToken@@@Z`
- size: `983`
- prototype: ``
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
- `0x18001de00`
- `0x18001e2e8`
- `0x18001e40c`
- `0x18001e660`
- `0x18001e834`
- `0x18001eab0`
- `0x18001ef04`
- `0x18001f030`
- `0x18001f9f0`
- `0x18001ff58`
- `0x180025ecc`
- `0x180026498`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001fa67`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001fa67`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001fb69`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001fb69`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001fa4f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001fa4f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001fb37`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001fb37`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001fa8b`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001fa8b`

## pseudocode

```c
__int64 __fastcall Windows::Internal::StateRepository::SecondaryTileUserNotifierServer::add_Changed(
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
  __int64 v19; // rax
  __int64 (__fastcall ***v20)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v21)(_QWORD, GUID *, HSTRING *); // rdi
  int v22; // eax
  unsigned __int8 *v23; // r9
  __int64 v24; // rdx
  StateRepository::WinRT::CoreApplication *v25; // rcx
  IInspectable v27; // [rsp+20h] [rbp-B9h] BYREF
  __int64 (__fastcall ***v28)(_QWORD, GUID *, HSTRING *); // [rsp+28h] [rbp-B1h] BYREF
  __int64 v29; // [rsp+30h] [rbp-A9h] BYREF
  __int64 v30; // [rsp+38h] [rbp-A1h] BYREF
  HSTRING v31; // [rsp+40h] [rbp-99h] BYREF
  _QWORD *v32; // [rsp+48h] [rbp-91h] BYREF
  char v33[8]; // [rsp+50h] [rbp-89h] BYREF
  HSTRING string; // [rsp+58h] [rbp-81h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp-79h] BYREF
  char v36[8]; // [rsp+78h] [rbp-61h] BYREF
  char v37[104]; // [rsp+80h] [rbp-59h] BYREF
  __int64 v38; // [rsp+E8h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+5Fh]

  if ( !Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::Internal::StateRepository::SecondaryTileUserNotifier *,Windows::Internal::StateRepository::SecondaryTileUserChangedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::GetSize(a1 + 11) )
  {
    v29 = 0;
    if ( WindowsCreateStringReference(
           L"Windows.Internal.StateRepository.SecondaryTileUserNotificationChannel",
           0x45u,
           &hstringHeader,
           &string) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    v6 = string;
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v29);
    ActivationFactory = RoGetActivationFactory(v6, &GUID_fe39030f_8455_4bf4_af4a_a34c336e4c13, &v29);
    v8 = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3F,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\windows.internal.staterepository.sec"
                      "ondarytileusernotifier.cpp",
        (const char *)(unsigned int)ActivationFactory,
        (int)v27.lpVtbl);
LABEL_27:
      Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v29);
      return (unsigned int)v8;
    }
    v28 = 0;
    v9 = v29;
    v10 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v29 + 56LL);
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v28);
    v11 = v10(v9, a1[9], &v28);
    v8 = v11;
    if ( v11 < 0 )
    {
      v12 = 65;
LABEL_8:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v12,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\windows.internal.staterepository.sec"
                      "ondarytileusernotifier.cpp",
        (const char *)(unsigned int)v11,
        (int)v27.lpVtbl);
LABEL_26:
      Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v28);
      goto LABEL_27;
    }
    v11 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, HSTRING *)))(*v28)[6])(v28);
    v8 = v11;
    if ( v11 < 0 )
    {
      v12 = 68;
      goto LABEL_8;
    }
    v13 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v28;
    v14 = (HSTRING *)(a1 + 8);
    v15 = (*v28)[9];
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
    v30 = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(v16, 0);
    v18 = _open___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJPEBGK_N_Z(
            &v30,
            StringRawBuffer);
    v8 = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x49,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\windows.internal.staterepository.sec"
                      "ondarytileusernotifier.cpp",
        (const char *)(unsigned int)v18,
        (int)v27.lpVtbl);
LABEL_25:
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v30);
      goto LABEL_26;
    }
    v32 = a1;
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::SecondaryTileUserNotifierServer>::InternalAddRef(&v32);
    v32 = a1;
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::SecondaryTileUserNotifierServer>::InternalAddRef(&v32);
    v38 = 0;
    v38 = wistd::__function::__func__lambda_7d16cdb3ae8eb95b227734d7328a4093__void___cdecl_void__::__func__lambda_7d16cdb3ae8eb95b227734d7328a4093__void___cdecl_void__(
            v37,
            &v32);
    if ( v32 )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::StateRepository::ISecondaryTileUserNotifier,Microsoft::WRL::FtmBase>::Release(v32);
    v19 = wil::make_event_watcher_nothrow<wil::err_returncode_policy>(v33, &v30, v36);
    wil::unique_any_t<wil::event_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&void wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>>::operator=(
      a1 + 10,
      v19);
    wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&void wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&void wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>(v33);
    wistd::function<void (void)>::~function<void (void)>(v36);
    if ( !a1[10] )
    {
      v8 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x51,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\windows.internal.staterepository.sec"
                      "ondarytileusernotifier.cpp",
        (const char *)0x8007000ELL,
        (int)v27.lpVtbl);
LABEL_24:
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::StateRepository::ISecondaryTileUserNotifier,Microsoft::WRL::FtmBase>::Release(a1);
      goto LABEL_25;
    }
    v20 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v28;
    v31 = 0;
    v21 = **v28;
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v31);
    v22 = v21(v20, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, &v31);
    v8 = v22;
    if ( v22 < 0 )
    {
      v24 = 85;
LABEL_23:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v24,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\windows.internal.staterepository.sec"
                      "ondarytileusernotifier.cpp",
        (const char *)(unsigned int)v22,
        (int)v27.lpVtbl);
      Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v31);
      goto LABEL_24;
    }
    v25 = (StateRepository::WinRT::CoreApplication *)*v14;
    LOBYTE(v27.lpVtbl) = 0;
    v22 = StateRepository::WinRT::CoreApplication::SetPrivateProperty(v25, v31, &v27, v23);
    v8 = v22;
    if ( v22 < 0 )
    {
      v24 = 87;
      goto LABEL_23;
    }
    if ( LOBYTE(v27.lpVtbl) )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v31);
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::StateRepository::ISecondaryTileUserNotifier,Microsoft::WRL::FtmBase>::Release(a1);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v30);
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v28);
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v29);
  }
  if ( !a2 )
  {
    v8 = -2147024809;
LABEL_39:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5C,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\windows.internal.staterepository.secon"
                    "darytileusernotifier.cpp",
      (const char *)(unsigned int)v8,
      (int)v27.lpVtbl);
    return (unsigned int)v8;
  }
  v29 = 0;
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v29);
  v8 = Microsoft::WRL::Details::CreateAgileHelper<Windows::Foundation::ITypedEventHandler<Windows::Internal::StateRepository::SecondaryTileUserNotifier *,Windows::Internal::StateRepository::SecondaryTileUserChangedEventArgs *>>(
         a2,
         &v29);
  if ( v8 >= 0 )
  {
    if ( v29 )
      v8 = Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::Internal::StateRepository::SecondaryTileUserNotifier *,Windows::Internal::StateRepository::SecondaryTileUserChangedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::AddInternal(
             a1 + 11,
             v29,
             *(_QWORD *)(*(_QWORD *)a2 + 24LL),
             a3);
    else
      v8 = -2147024809;
  }
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v29);
  if ( v8 < 0 )
    goto LABEL_39;
  return 0;
}

```

## disassembly

```asm
0x18001f9f0  mov     [rsp-8+arg_18], rbx
0x18001f9f5  push    rbp
0x18001f9f6  push    rsi
0x18001f9f7  push    rdi
0x18001f9f8  push    r12
0x18001f9fa  push    r13
0x18001f9fc  push    r14
0x18001f9fe  push    r15
0x18001fa00  lea     rbp, [rsp-27h]
0x18001fa05  sub     rsp, 100h
0x18001fa0c  mov     rax, cs:__security_cookie
0x18001fa13  xor     rax, rsp
0x18001fa16  mov     [rbp+57h+var_40], rax
0x18001fa1a  mov     rsi, rcx
0x18001fa1d  mov     r13, r8
0x18001fa20  add     rcx, 58h ; 'X'
0x18001fa24  mov     r15, rdx
0x18001fa27  call    ?GetSize@?$EventSource@U?$ITypedEventHandler@PEAVSecondaryTileUserNotifier@StateRepository@Internal@Windows@@PEAVSecondaryTileUserChangedEventArgs@234@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEBA_KXZ; Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::Internal::StateRepository::SecondaryTileUserNotifier *,Windows::Internal::StateRepository::SecondaryTileUserChangedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::GetSize(void)
0x18001fa2c  xor     edi, edi
0x18001fa2e  test    rax, rax
0x18001fa31  jnz     loc_18001FD1F
0x18001fa37  lea     r9, [rsp+130h+string]; string
0x18001fa3c  mov     [rsp+130h+var_100], rdi
0x18001fa41  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18001fa45  lea     edx, [rdi+45h]; length
0x18001fa48  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_SecondaryTileUserNotificationChannel@@3QBGB; "Windows.Internal.StateRepository.Second"...
0x18001fa4f  call    cs:__imp_WindowsCreateStringReference
0x18001fa55  test    eax, eax
0x18001fa57  jns     short loc_18001FA6D
0x18001fa59  xor     r9d, r9d; lpArguments
0x18001fa5c  lea     edx, [rdi+1]; dwExceptionFlags
0x18001fa5f  xor     r8d, r8d; nNumberOfArguments
0x18001fa62  mov     ecx, 0C000000Dh; dwExceptionCode
0x18001fa67  call    cs:__imp_RaiseException
0x18001fa6d  mov     rbx, [rsp+130h+string]
0x18001fa72  lea     rcx, [rsp+130h+var_100]
0x18001fa77  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x18001fa7c  lea     r8, [rsp+130h+var_100]
0x18001fa81  mov     rcx, rbx
0x18001fa84  lea     rdx, _GUID_fe39030f_8455_4bf4_af4a_a34c336e4c13
0x18001fa8b  call    cs:__imp_RoGetActivationFactory
0x18001fa91  mov     ebx, eax
0x18001fa93  test    eax, eax
0x18001fa95  jns     short loc_18001FAB4
0x18001fa97  mov     rcx, [rbp+5Fh]; this
0x18001fa9b  lea     r8, aOnecoreBaseApp_3; "onecore\\base\\appmodel\\staterepositor"...
0x18001faa2  mov     r9d, eax; char *
0x18001faa5  mov     edx, 3Fh ; '?'; void *
0x18001faaa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001faaf  jmp     loc_18001FCD2
0x18001fab4  mov     [rsp+130h+var_108], rdi
0x18001fab9  lea     rcx, [rsp+130h+var_108]
0x18001fabe  mov     rdi, [rsp+130h+var_100]
0x18001fac3  mov     rax, [rdi]
0x18001fac6  mov     rbx, [rax+38h]
0x18001faca  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x18001facf  mov     rdx, [rsi+48h]
0x18001fad3  lea     r8, [rsp+130h+var_108]
0x18001fad8  mov     rcx, rdi
0x18001fadb  mov     rax, rbx
0x18001fade  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fae3  mov     ebx, eax
0x18001fae5  test    eax, eax
0x18001fae7  jns     short loc_18001FB06
0x18001fae9  mov     edx, 41h ; 'A'; void *
0x18001faee  mov     rcx, [rbp+5Fh]; this
0x18001faf2  lea     r8, aOnecoreBaseApp_3; "onecore\\base\\appmodel\\staterepositor"...
0x18001faf9  mov     r9d, eax; char *
0x18001fafc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fb01  jmp     loc_18001FCC8
0x18001fb06  mov     rcx, [rsp+130h+var_108]
0x18001fb0b  mov     rax, [rcx]
0x18001fb0e  mov     rax, [rax+30h]
0x18001fb12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fb17  mov     ebx, eax
0x18001fb19  test    eax, eax
0x18001fb1b  jns     short loc_18001FB24
0x18001fb1d  mov     edx, 44h ; 'D'
0x18001fb22  jmp     short loc_18001FAEE
0x18001fb24  mov     rdi, [rsp+130h+var_108]
0x18001fb29  lea     r14, [rsi+40h]
0x18001fb2d  mov     rcx, [r14]; string
0x18001fb30  mov     rax, [rdi]
0x18001fb33  mov     rbx, [rax+48h]
0x18001fb37  call    cs:__imp_WindowsDeleteString
0x18001fb3d  mov     rdx, r14
0x18001fb40  mov     qword ptr [r14], 0
0x18001fb47  mov     rcx, rdi
0x18001fb4a  mov     rax, rbx
0x18001fb4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fb52  xor     edi, edi
0x18001fb54  mov     ebx, eax
0x18001fb56  test    eax, eax
0x18001fb58  jns     short loc_18001FB5F
0x18001fb5a  lea     edx, [rdi+47h]
0x18001fb5d  jmp     short loc_18001FAEE
0x18001fb5f  mov     rcx, [r14]; string
0x18001fb62  xor     edx, edx; length
0x18001fb64  mov     [rsp+130h+var_F8], rdi
0x18001fb69  call    cs:__imp_WindowsGetStringRawBuffer
0x18001fb6f  mov     rdx, rax
0x18001fb72  lea     rcx, [rsp+130h+var_F8]
0x18001fb77  call    ?open@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJPEBGK_N@Z
0x18001fb7c  mov     ebx, eax
0x18001fb7e  test    eax, eax
0x18001fb80  jns     short loc_18001FB9F
0x18001fb82  mov     rcx, [rbp+5Fh]; this
0x18001fb86  lea     r8, aOnecoreBaseApp_3; "onecore\\base\\appmodel\\staterepositor"...
0x18001fb8d  mov     r9d, eax; char *
0x18001fb90  mov     edx, 49h ; 'I'; void *
0x18001fb95  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fb9a  jmp     loc_18001FCBE
0x18001fb9f  lea     rcx, [rsp+130h+var_E8]
0x18001fba4  mov     [rsp+130h+var_E8], rsi
0x18001fba9  call    ?InternalAddRef@?$ComPtr@VSecondaryTileUserNotifierServer@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::SecondaryTileUserNotifierServer>::InternalAddRef(void)
0x18001fbae  lea     rcx, [rsp+130h+var_E8]
0x18001fbb3  mov     [rsp+130h+var_E8], rsi
0x18001fbb8  call    ?InternalAddRef@?$ComPtr@VSecondaryTileUserNotifierServer@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::SecondaryTileUserNotifierServer>::InternalAddRef(void)
0x18001fbbd  lea     rdx, [rsp+130h+var_E8]
0x18001fbc2  mov     [rbp+57h+var_48], rdi
0x18001fbc6  lea     rcx, [rbp+57h+var_B0]
0x18001fbca  call    wistd____function____func__lambda_7d16cdb3ae8eb95b227734d7328a4093__void___cdecl_void______func__lambda_7d16cdb3ae8eb95b227734d7328a4093__void___cdecl_void__
0x18001fbcf  mov     rcx, [rsp+130h+var_E8]
0x18001fbd4  mov     [rbp+57h+var_48], rax
0x18001fbd8  test    rcx, rcx
0x18001fbdb  jz      short loc_18001FBE2
0x18001fbdd  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UISecondaryTileUserNotifier@StateRepository@Internal@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::StateRepository::ISecondaryTileUserNotifier,Microsoft::WRL::FtmBase>::Release(void)
0x18001fbe2  lea     r8, [rbp+57h+var_B8]
0x18001fbe6  lea     rdx, [rsp+130h+var_F8]
0x18001fbeb  lea     rcx, [rsp+130h+var_E0]
0x18001fbf0  call    ??$make_event_watcher_nothrow@Uerr_returncode_policy@wil@@@wil@@YA?AV?$unique_any_t@V?$event_watcher_t@V?$unique_storage@U?$resource_policy@PEAUevent_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_event_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@0@$$QEAV?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@0@$$QEAV?$function@$$A6AXXZ@wistd@@@Z
0x18001fbf5  mov     rdx, rax
0x18001fbf8  lea     rcx, [rsi+50h]
0x18001fbfc  call    ??4?$unique_any_t@V?$event_watcher_t@V?$unique_storage@U?$resource_policy@PEAUevent_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_event_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::event_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>>::operator=(wil::unique_any_t<wil::event_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>> &&)
0x18001fc01  lea     rcx, [rsp+130h+var_E0]
0x18001fc06  call    ??1?$unique_storage@U?$resource_policy@PEAUevent_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_event_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>(void)
0x18001fc0b  lea     rcx, [rbp+57h+var_B8]
0x18001fc0f  call    ??1?$function@$$A6AXXZ@wistd@@QEAA@XZ; wistd::function<void (void)>::~function<void (void)>(void)
0x18001fc14  cmp     [rsi+50h], rdi
0x18001fc18  jnz     short loc_18001FC39
0x18001fc1a  mov     rcx, [rbp+5Fh]; this
0x18001fc1e  lea     r8, aOnecoreBaseApp_3; "onecore\\base\\appmodel\\staterepositor"...
0x18001fc25  mov     ebx, 8007000Eh
0x18001fc2a  mov     edx, 51h ; 'Q'; void *
0x18001fc2f  mov     r9d, ebx; char *
0x18001fc32  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fc37  jmp     short loc_18001FCB6
0x18001fc39  mov     rbx, [rsp+130h+var_108]
0x18001fc3e  lea     rcx, [rsp+130h+var_F0]
0x18001fc43  mov     [rsp+130h+var_F0], rdi
0x18001fc48  mov     rax, [rbx]
0x18001fc4b  mov     rdi, [rax]
0x18001fc4e  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x18001fc53  lea     r8, [rsp+130h+var_F0]
0x18001fc58  mov     rcx, rbx
0x18001fc5b  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90
0x18001fc62  mov     rax, rdi
0x18001fc65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fc6a  xor     edi, edi
0x18001fc6c  mov     ebx, eax
0x18001fc6e  test    eax, eax
0x18001fc70  jns     short loc_18001FC77
0x18001fc72  lea     edx, [rdi+55h]
0x18001fc75  jmp     short loc_18001FC99
0x18001fc77  mov     rdx, [rsp+130h+var_F0]; HSTRING
0x18001fc7c  lea     r8, [rsp+130h+var_110]; struct IInspectable *
0x18001fc81  mov     rcx, [r14]; this
0x18001fc84  mov     byte ptr [rsp+130h+var_110.lpVtbl], dil; int
0x18001fc89  call    ?SetPrivateProperty@CoreApplication@WinRT@StateRepository@@YAJPEAUHSTRING__@@PEAUIInspectable@@PEAE@Z; StateRepository::WinRT::CoreApplication::SetPrivateProperty(HSTRING__ *,IInspectable *,uchar *)
0x18001fc8e  mov     ebx, eax
0x18001fc90  test    eax, eax
0x18001fc92  jns     short loc_18001FCE3
0x18001fc94  mov     edx, 57h ; 'W'; void *
0x18001fc99  mov     rcx, [rbp+5Fh]; this
0x18001fc9d  lea     r8, aOnecoreBaseApp_3; "onecore\\base\\appmodel\\staterepositor"...
0x18001fca4  mov     r9d, eax; char *
0x18001fca7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fcac  lea     rcx, [rsp+130h+var_F0]
0x18001fcb1  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x18001fcb6  mov     rcx, rsi
0x18001fcb9  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UISecondaryTileUserNotifier@StateRepository@Internal@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::StateRepository::ISecondaryTileUserNotifier,Microsoft::WRL::FtmBase>::Release(void)
0x18001fcbe  lea     rcx, [rsp+130h+var_F8]
0x18001fcc3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001fcc8  lea     rcx, [rsp+130h+var_108]
0x18001fccd  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x18001fcd2  lea     rcx, [rsp+130h+var_100]
0x18001fcd7  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x18001fcdc  mov     eax, ebx
0x18001fcde  jmp     loc_18001FDA0
0x18001fce3  cmp     byte ptr [rsp+130h+var_110.lpVtbl], dil
0x18001fce8  jz      short loc_18001FCEF
0x18001fcea  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001fcef  lea     rcx, [rsp+130h+var_F0]
0x18001fcf4  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x18001fcf9  mov     rcx, rsi
0x18001fcfc  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UISecondaryTileUserNotifier@StateRepository@Internal@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::StateRepository::ISecondaryTileUserNotifier,Microsoft::WRL::FtmBase>::Release(void)
0x18001fd01  lea     rcx, [rsp+130h+var_F8]
0x18001fd06  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001fd0b  lea     rcx, [rsp+130h+var_108]
0x18001fd10  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x18001fd15  lea     rcx, [rsp+130h+var_100]
0x18001fd1a  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x18001fd1f  test    r15, r15
0x18001fd22  jnz     short loc_18001FD2B
0x18001fd24  mov     ebx, 80070057h
0x18001fd29  jmp     short loc_18001FD81
0x18001fd2b  lea     rcx, [rsp+130h+var_100]
0x18001fd30  mov     [rsp+130h+var_100], rdi
0x18001fd35  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x18001fd3a  lea     rdx, [rsp+130h+var_100]
0x18001fd3f  mov     rcx, r15
0x18001fd42  call    ??$CreateAgileHelper@U?$ITypedEventHandler@PEAVSecondaryTileUserNotifier@StateRepository@Internal@Windows@@PEAVSecondaryTileUserChangedEventArgs@234@@Foundation@Windows@@@Details@WRL@Microsoft@@YAJPEAU?$ITypedEventHandler@PEAVSecondaryTileUserNotifier@StateRepository@Internal@Windows@@PEAVSecondaryTileUserChangedEventArgs@234@@Foundation@Windows@@PEAPEAU345@@Z; Microsoft::WRL::Details::CreateAgileHelper<Windows::Foundation::ITypedEventHandler<Windows::Internal::StateRepository::SecondaryTileUserNotifier *,Windows::Internal::StateRepository::SecondaryTileUserChangedEventArgs *>>(Windows::Foundation::ITypedEventHandler<Windows::Internal::StateRepository::SecondaryTileUserNotifier *,Windows::Internal::StateRepository::SecondaryTileUserChangedEventArgs *> *,Windows::Foundation::ITypedEventHandler<Windows::Internal::StateRepository::SecondaryTileUserNotifier *,Windows::Internal::StateRepository::SecondaryTileUserChangedEventArgs *> * *)
0x18001fd47  mov     ebx, eax
0x18001fd49  test    eax, eax
0x18001fd4b  js      short loc_18001FD73
0x18001fd4d  mov     rdx, [rsp+130h+var_100]
0x18001fd52  test    rdx, rdx
0x18001fd55  jnz     short loc_18001FD5E
0x18001fd57  mov     ebx, 80070057h
0x18001fd5c  jmp     short loc_18001FD73
0x18001fd5e  mov     r8, [r15]
0x18001fd61  lea     rcx, [rsi+58h]
0x18001fd65  mov     r9, r13
0x18001fd68  mov     r8, [r8+18h]
0x18001fd6c  call    ?AddInternal@?$EventSource@U?$ITypedEventHandler@PEAVSecondaryTileUserNotifier@StateRepository@Internal@Windows@@PEAVSecondaryTileUserChangedEventArgs@234@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@AEAAJPEAU?$ITypedEventHandler@PEAVSecondaryTileUserNotifier@StateRepository@Internal@Windows@@PEAVSecondaryTileUserChangedEventArgs@234@@Foundation@Windows@@PEAXPEAUEventRegistrationToken@@@Z; Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::Internal::StateRepository::SecondaryTileUserNotifier *,Windows::Internal::StateRepository::SecondaryTileUserChangedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::AddInternal(Windows::Foundation::ITypedEventHandler<Windows::Internal::StateRepository::SecondaryTileUserNotifier *,Windows::Internal::StateRepository::SecondaryTileUserChangedEventArgs *> *,void *,EventRegistrationToken *)
0x18001fd71  mov     ebx, eax
0x18001fd73  lea     rcx, [rsp+130h+var_100]
0x18001fd78  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x18001fd7d  test    ebx, ebx
0x18001fd7f  jns     short loc_18001FD9E
0x18001fd81  mov     rcx, [rbp+5Fh]; this
0x18001fd85  lea     r8, aOnecoreBaseApp_3; "onecore\\base\\appmodel\\staterepositor"...
0x18001fd8c  mov     r9d, ebx; char *
0x18001fd8f  mov     edx, 5Ch ; '\'; void *
0x18001fd94  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fd99  jmp     loc_18001FCDC
0x18001fd9e  xor     eax, eax
0x18001fda0  mov     rcx, [rbp+57h+var_40]
0x18001fda4  xor     rcx, rsp; StackCookie
0x18001fda7  call    __security_check_cookie
0x18001fdac  mov     rbx, [rsp+130h+arg_18]
0x18001fdb4  add     rsp, 100h
0x18001fdbb  pop     r15
0x18001fdbd  pop     r14
0x18001fdbf  pop     r13
0x18001fdc1  pop     r12
0x18001fdc3  pop     rdi
0x18001fdc4  pop     rsi
0x18001fdc5  pop     rbp
0x18001fdc6  retn
```
