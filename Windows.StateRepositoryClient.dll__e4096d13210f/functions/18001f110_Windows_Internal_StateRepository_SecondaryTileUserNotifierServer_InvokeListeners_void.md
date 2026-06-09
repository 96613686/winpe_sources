# Windows::Internal::StateRepository::SecondaryTileUserNotifierServer::InvokeListeners(void)

- ea: `0x18001f110`
- end: `0x18001f2e9`
- name: `?InvokeListeners@SecondaryTileUserNotifierServer@StateRepository@Internal@Windows@@UEAAJXZ`
- size: `473`
- prototype: `__int64 __fastcall(Windows::Internal::StateRepository::SecondaryTileUserNotifierServer *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001e8c0`

## callees

- `0x180002980`
- `0x180006ab8`
- `0x1800075e4`
- `0x18000b348`
- `0x18001def8`
- `0x18001e7b4`
- `0x18001f110`
- `0x18001f500`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001f248`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001f248`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001f16e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001f16e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001f155`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001f155`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001f18f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001f18f`

## pseudocode

```c
__int64 __fastcall Windows::Internal::StateRepository::SecondaryTileUserNotifierServer::InvokeListeners(
        Windows::Internal::StateRepository::SecondaryTileUserNotifierServer *this)
{
  HSTRING v2; // rbx
  int ActivationFactory; // eax
  unsigned int v4; // ebx
  __int64 v5; // rdi
  __int64 (__fastcall *v6)(__int64, _QWORD, __int64 *); // rbx
  int v7; // eax
  int v8; // edi
  __int64 v9; // rbx
  __int64 v11; // [rsp+20h] [rbp-60h] BYREF
  __int64 v12; // [rsp+28h] [rbp-58h] BYREF
  __int64 v13; // [rsp+30h] [rbp-50h] BYREF
  Windows::Internal::StateRepository::SecondaryTileUserNotifierServer *v14; // [rsp+38h] [rbp-48h] BYREF
  __int64 v15; // [rsp+40h] [rbp-40h] BYREF
  HSTRING string; // [rsp+50h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  v12 = 0;
  if ( WindowsCreateStringReference(
         L"Windows.Internal.StateRepository.SecondaryTileUserChangedEventArgs",
         0x42u,
         &hstringHeader,
         &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v2 = string;
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v12);
  ActivationFactory = RoGetActivationFactory(v2, &GUID_3940ce31_f32f_4fba_b877_1a1beea68f77, &v12);
  v4 = ActivationFactory;
  if ( ActivationFactory >= 0 )
  {
    v5 = v12;
    v11 = 0;
    v6 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v12 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v11);
    v7 = v6(v5, *((_QWORD *)this + 9), &v11);
    v4 = v7;
    if ( v7 >= 0 )
    {
      v8 = 0;
      v15 = v11;
      v13 = 0;
      v14 = this;
      Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&string, (char *)this + 96);
      Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::operator=(&v13, (__int64 *)this + 11);
      if ( string )
        ReleaseSRWLockExclusive((PSRWLOCK)string);
      v9 = v13;
      if ( v13 )
      {
        string = (HSTRING)&v14;
        hstringHeader.Reserved.Reserved1 = &v15;
        v8 = Microsoft::WRL::InvokeTraits<-2>::InvokeDelegates<_lambda_14da6de372024dce4ca8d5cf352a7641_,Windows::Foundation::ITypedEventHandler<Windows::Internal::StateRepository::SecondaryTileUserNotifier *,Windows::Internal::StateRepository::SecondaryTileUserChangedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>(
               &string,
               v13,
               (char *)this + 88);
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v9);
      }
      if ( v8 >= 0 )
      {
        Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v11);
        v4 = 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x7B,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\windows.internal.staterepository.s"
                        "econdarytileusernotifier.cpp",
          (const char *)(unsigned int)v8,
          v11);
        Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v11);
        v4 = v8;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x79,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\windows.internal.staterepository.sec"
                      "ondarytileusernotifier.cpp",
        (const char *)(unsigned int)v7,
        v11);
      Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v11);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x77,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\windows.internal.staterepository.secon"
                    "darytileusernotifier.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v11);
  }
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v12);
  return v4;
}

```

## disassembly

```asm
0x18001f110  mov     [rsp-18h+arg_8], rbx
0x18001f115  mov     [rsp-18h+arg_10], rsi
0x18001f11a  push    rbp
0x18001f11b  push    rdi
0x18001f11c  push    r14
0x18001f11e  mov     rbp, rsp
0x18001f121  sub     rsp, 80h
0x18001f128  mov     rax, cs:__security_cookie
0x18001f12f  xor     rax, rsp
0x18001f132  mov     [rbp+var_10], rax
0x18001f136  mov     r14, rcx
0x18001f139  mov     [rbp+var_58], 0
0x18001f141  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_SecondaryTileUserChangedEventArgs@@3QBGB; "Windows.Internal.StateRepository.Second"...
0x18001f148  mov     edx, 42h ; 'B'; length
0x18001f14d  lea     r9, [rbp+string]; string
0x18001f151  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18001f155  call    cs:__imp_WindowsCreateStringReference
0x18001f15b  test    eax, eax
0x18001f15d  jns     short loc_18001F174
0x18001f15f  xor     r9d, r9d; lpArguments
0x18001f162  xor     r8d, r8d; nNumberOfArguments
0x18001f165  mov     ecx, 0C000000Dh; dwExceptionCode
0x18001f16a  lea     edx, [r9+1]; dwExceptionFlags
0x18001f16e  call    cs:__imp_RaiseException
0x18001f174  mov     rbx, [rbp+string]
0x18001f178  lea     rcx, [rbp+var_58]
0x18001f17c  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x18001f181  lea     r8, [rbp+var_58]
0x18001f185  mov     rcx, rbx
0x18001f188  lea     rdx, _GUID_3940ce31_f32f_4fba_b877_1a1beea68f77
0x18001f18f  call    cs:__imp_RoGetActivationFactory
0x18001f195  mov     ebx, eax
0x18001f197  test    eax, eax
0x18001f199  jns     short loc_18001F1B8
0x18001f19b  mov     rcx, [rbp+18h]; this
0x18001f19f  lea     r8, aOnecoreBaseApp_3; "onecore\\base\\appmodel\\staterepositor"...
0x18001f1a6  mov     r9d, eax; char *
0x18001f1a9  mov     edx, 77h ; 'w'; void *
0x18001f1ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f1b3  jmp     loc_18001F2BA
0x18001f1b8  mov     rdi, [rbp+var_58]
0x18001f1bc  lea     rcx, [rbp+var_60]
0x18001f1c0  mov     [rbp+var_60], 0
0x18001f1c8  mov     rax, [rdi]
0x18001f1cb  mov     rbx, [rax+30h]
0x18001f1cf  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x18001f1d4  mov     rdx, [r14+48h]
0x18001f1d8  lea     r8, [rbp+var_60]
0x18001f1dc  mov     rcx, rdi
0x18001f1df  mov     rax, rbx
0x18001f1e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f1e7  mov     ebx, eax
0x18001f1e9  test    eax, eax
0x18001f1eb  jns     short loc_18001F213
0x18001f1ed  mov     rcx, [rbp+18h]; this
0x18001f1f1  lea     r8, aOnecoreBaseApp_3; "onecore\\base\\appmodel\\staterepositor"...
0x18001f1f8  mov     r9d, eax; char *
0x18001f1fb  mov     edx, 79h ; 'y'; void *
0x18001f200  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f205  lea     rcx, [rbp+var_60]
0x18001f209  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x18001f20e  jmp     loc_18001F2BA
0x18001f213  mov     rax, [rbp+var_60]
0x18001f217  lea     rdx, [r14+60h]
0x18001f21b  xor     edi, edi
0x18001f21d  mov     [rbp+var_40], rax
0x18001f221  lea     rcx, [rbp+string]
0x18001f225  mov     [rbp+var_50], rdi
0x18001f229  mov     [rbp+var_48], r14
0x18001f22d  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x18001f232  lea     rdx, [r14+58h]
0x18001f236  lea     rcx, [rbp+var_50]
0x18001f23a  call    ??4?$ComPtr@VEventTargetArray@Details@WRL@Microsoft@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::operator=(Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray> const &)
0x18001f23f  mov     rcx, [rbp+string]; SRWLock
0x18001f243  test    rcx, rcx
0x18001f246  jz      short loc_18001F24E
0x18001f248  call    cs:__imp_ReleaseSRWLockExclusive
0x18001f24e  mov     rbx, [rbp+var_50]
0x18001f252  test    rbx, rbx
0x18001f255  jz      short loc_18001F286
0x18001f257  lea     rax, [rbp+var_48]
0x18001f25b  mov     rdx, rbx
0x18001f25e  mov     [rbp+string], rax
0x18001f262  lea     r8, [r14+58h]
0x18001f266  lea     rax, [rbp+var_40]
0x18001f26a  lea     rcx, [rbp+string]
0x18001f26e  mov     qword ptr [rbp+hstringHeader.Reserved], rax
0x18001f272  call    ??$InvokeDelegates@V_lambda_14da6de372024dce4ca8d5cf352a7641_@@U?$ITypedEventHandler@PEAVSecondaryTileUserNotifier@StateRepository@Internal@Windows@@PEAVSecondaryTileUserChangedEventArgs@234@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@?$InvokeTraits@$0?1@WRL@Microsoft@@SAJV_lambda_14da6de372024dce4ca8d5cf352a7641_@@PEAVEventTargetArray@Details@12@PEAV?$EventSource@U?$ITypedEventHandler@PEAVSecondaryTileUserNotifier@StateRepository@Internal@Windows@@PEAVSecondaryTileUserChangedEventArgs@234@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@12@@Z; Microsoft::WRL::InvokeTraits<-2>::InvokeDelegates<_lambda_14da6de372024dce4ca8d5cf352a7641_,Windows::Foundation::ITypedEventHandler<Windows::Internal::StateRepository::SecondaryTileUserNotifier *,Windows::Internal::StateRepository::SecondaryTileUserChangedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>(_lambda_14da6de372024dce4ca8d5cf352a7641_,Microsoft::WRL::Details::EventTargetArray *,Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::Internal::StateRepository::SecondaryTileUserNotifier *,Windows::Internal::StateRepository::SecondaryTileUserChangedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>> *)
0x18001f277  mov     edi, eax
0x18001f279  test    rbx, rbx
0x18001f27c  jz      short loc_18001F286
0x18001f27e  mov     rcx, rbx
0x18001f281  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18001f286  test    edi, edi
0x18001f288  jns     short loc_18001F2AF
0x18001f28a  mov     rcx, [rbp+18h]; this
0x18001f28e  lea     r8, aOnecoreBaseApp_3; "onecore\\base\\appmodel\\staterepositor"...
0x18001f295  mov     r9d, edi; char *
0x18001f298  mov     edx, 7Bh ; '{'; void *
0x18001f29d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f2a2  lea     rcx, [rbp+var_60]
0x18001f2a6  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x18001f2ab  mov     ebx, edi
0x18001f2ad  jmp     short loc_18001F2BA
0x18001f2af  lea     rcx, [rbp+var_60]
0x18001f2b3  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x18001f2b8  xor     ebx, ebx
0x18001f2ba  lea     rcx, [rbp+var_58]
0x18001f2be  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x18001f2c3  mov     eax, ebx
0x18001f2c5  mov     rcx, [rbp+var_10]
0x18001f2c9  xor     rcx, rsp; StackCookie
0x18001f2cc  call    __security_check_cookie
0x18001f2d1  lea     r11, [rsp+80h+var_s0]
0x18001f2d9  mov     rbx, [r11+28h]
0x18001f2dd  mov     rsi, [r11+30h]
0x18001f2e1  mov     rsp, r11
0x18001f2e4  pop     r14
0x18001f2e6  pop     rdi
0x18001f2e7  pop     rbp
0x18001f2e8  retn
```
