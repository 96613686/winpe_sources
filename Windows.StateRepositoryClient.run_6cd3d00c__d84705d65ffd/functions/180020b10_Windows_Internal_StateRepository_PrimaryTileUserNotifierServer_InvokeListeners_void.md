# Windows::Internal::StateRepository::PrimaryTileUserNotifierServer::InvokeListeners(void)

- ea: `0x180020b10`
- end: `0x180020ce9`
- name: `?InvokeListeners@PrimaryTileUserNotifierServer@StateRepository@Internal@Windows@@UEAAJXZ`
- size: `473`
- prototype: `__int64 __fastcall(Windows::Internal::StateRepository::PrimaryTileUserNotifierServer *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180020970`

## callees

- `0x180002980`
- `0x180006ab8`
- `0x1800075e4`
- `0x18000b348`
- `0x18001def8`
- `0x18001e7b4`
- `0x18001f500`
- `0x180020b10`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180020c48`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180020c48`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180020b6e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180020b6e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180020b55`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180020b55`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180020b8f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180020b8f`

## pseudocode

```c
__int64 __fastcall Windows::Internal::StateRepository::PrimaryTileUserNotifierServer::InvokeListeners(
        Windows::Internal::StateRepository::PrimaryTileUserNotifierServer *this)
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
  Windows::Internal::StateRepository::PrimaryTileUserNotifierServer *v14; // [rsp+38h] [rbp-48h] BYREF
  __int64 v15; // [rsp+40h] [rbp-40h] BYREF
  HSTRING string; // [rsp+50h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  v12 = 0;
  if ( WindowsCreateStringReference(
         L"Windows.Internal.StateRepository.PrimaryTileUserChangedEventArgs",
         0x40u,
         &hstringHeader,
         &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v2 = string;
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v12);
  ActivationFactory = RoGetActivationFactory(v2, &GUID_f7ec1a17_b666_4ca9_9d57_a64a22502210, &v12);
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
      Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::operator=(&v13, (char *)this + 88);
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
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\windows.internal.staterepository.p"
                        "rimarytileusernotifier.cpp",
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
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\windows.internal.staterepository.pri"
                      "marytileusernotifier.cpp",
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
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\windows.internal.staterepository.prima"
                    "rytileusernotifier.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v11);
  }
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v12);
  return v4;
}

```

## disassembly

```asm
0x180020b10  mov     [rsp-18h+arg_8], rbx
0x180020b15  mov     [rsp-18h+arg_10], rsi
0x180020b1a  push    rbp
0x180020b1b  push    rdi
0x180020b1c  push    r14
0x180020b1e  mov     rbp, rsp
0x180020b21  sub     rsp, 80h
0x180020b28  mov     rax, cs:__security_cookie
0x180020b2f  xor     rax, rsp
0x180020b32  mov     [rbp+var_10], rax
0x180020b36  mov     r14, rcx
0x180020b39  mov     [rbp+var_58], 0
0x180020b41  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_PrimaryTileUserChangedEventArgs@@3QBGB; "Windows.Internal.StateRepository.Primar"...
0x180020b48  mov     edx, 40h ; '@'; length
0x180020b4d  lea     r9, [rbp+string]; string
0x180020b51  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180020b55  call    cs:__imp_WindowsCreateStringReference
0x180020b5b  test    eax, eax
0x180020b5d  jns     short loc_180020B74
0x180020b5f  xor     r9d, r9d; lpArguments
0x180020b62  xor     r8d, r8d; nNumberOfArguments
0x180020b65  mov     ecx, 0C000000Dh; dwExceptionCode
0x180020b6a  lea     edx, [r9+1]; dwExceptionFlags
0x180020b6e  call    cs:__imp_RaiseException
0x180020b74  mov     rbx, [rbp+string]
0x180020b78  lea     rcx, [rbp+var_58]
0x180020b7c  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x180020b81  lea     r8, [rbp+var_58]
0x180020b85  mov     rcx, rbx
0x180020b88  lea     rdx, _GUID_f7ec1a17_b666_4ca9_9d57_a64a22502210
0x180020b8f  call    cs:__imp_RoGetActivationFactory
0x180020b95  mov     ebx, eax
0x180020b97  test    eax, eax
0x180020b99  jns     short loc_180020BB8
0x180020b9b  mov     rcx, [rbp+18h]; this
0x180020b9f  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\staterepositor"...
0x180020ba6  mov     r9d, eax; char *
0x180020ba9  mov     edx, 77h ; 'w'; void *
0x180020bae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020bb3  jmp     loc_180020CBA
0x180020bb8  mov     rdi, [rbp+var_58]
0x180020bbc  lea     rcx, [rbp+var_60]
0x180020bc0  mov     [rbp+var_60], 0
0x180020bc8  mov     rax, [rdi]
0x180020bcb  mov     rbx, [rax+30h]
0x180020bcf  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x180020bd4  mov     rdx, [r14+48h]
0x180020bd8  lea     r8, [rbp+var_60]
0x180020bdc  mov     rcx, rdi
0x180020bdf  mov     rax, rbx
0x180020be2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020be7  mov     ebx, eax
0x180020be9  test    eax, eax
0x180020beb  jns     short loc_180020C13
0x180020bed  mov     rcx, [rbp+18h]; this
0x180020bf1  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\staterepositor"...
0x180020bf8  mov     r9d, eax; char *
0x180020bfb  mov     edx, 79h ; 'y'; void *
0x180020c00  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020c05  lea     rcx, [rbp+var_60]
0x180020c09  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x180020c0e  jmp     loc_180020CBA
0x180020c13  mov     rax, [rbp+var_60]
0x180020c17  lea     rdx, [r14+60h]
0x180020c1b  xor     edi, edi
0x180020c1d  mov     [rbp+var_40], rax
0x180020c21  lea     rcx, [rbp+string]
0x180020c25  mov     [rbp+var_50], rdi
0x180020c29  mov     [rbp+var_48], r14
0x180020c2d  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x180020c32  lea     rdx, [r14+58h]
0x180020c36  lea     rcx, [rbp+var_50]
0x180020c3a  call    ??4?$ComPtr@VEventTargetArray@Details@WRL@Microsoft@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::operator=(Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray> const &)
0x180020c3f  mov     rcx, [rbp+string]; SRWLock
0x180020c43  test    rcx, rcx
0x180020c46  jz      short loc_180020C4E
0x180020c48  call    cs:__imp_ReleaseSRWLockExclusive
0x180020c4e  mov     rbx, [rbp+var_50]
0x180020c52  test    rbx, rbx
0x180020c55  jz      short loc_180020C86
0x180020c57  lea     rax, [rbp+var_48]
0x180020c5b  mov     rdx, rbx
0x180020c5e  mov     [rbp+string], rax
0x180020c62  lea     r8, [r14+58h]
0x180020c66  lea     rax, [rbp+var_40]
0x180020c6a  lea     rcx, [rbp+string]
0x180020c6e  mov     qword ptr [rbp+hstringHeader.Reserved], rax
0x180020c72  call    ??$InvokeDelegates@V_lambda_14da6de372024dce4ca8d5cf352a7641_@@U?$ITypedEventHandler@PEAVSecondaryTileUserNotifier@StateRepository@Internal@Windows@@PEAVSecondaryTileUserChangedEventArgs@234@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@?$InvokeTraits@$0?1@WRL@Microsoft@@SAJV_lambda_14da6de372024dce4ca8d5cf352a7641_@@PEAVEventTargetArray@Details@12@PEAV?$EventSource@U?$ITypedEventHandler@PEAVSecondaryTileUserNotifier@StateRepository@Internal@Windows@@PEAVSecondaryTileUserChangedEventArgs@234@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@12@@Z; Microsoft::WRL::InvokeTraits<-2>::InvokeDelegates<_lambda_14da6de372024dce4ca8d5cf352a7641_,Windows::Foundation::ITypedEventHandler<Windows::Internal::StateRepository::SecondaryTileUserNotifier *,Windows::Internal::StateRepository::SecondaryTileUserChangedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>(_lambda_14da6de372024dce4ca8d5cf352a7641_,Microsoft::WRL::Details::EventTargetArray *,Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::Internal::StateRepository::SecondaryTileUserNotifier *,Windows::Internal::StateRepository::SecondaryTileUserChangedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>> *)
0x180020c77  mov     edi, eax
0x180020c79  test    rbx, rbx
0x180020c7c  jz      short loc_180020C86
0x180020c7e  mov     rcx, rbx
0x180020c81  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x180020c86  test    edi, edi
0x180020c88  jns     short loc_180020CAF
0x180020c8a  mov     rcx, [rbp+18h]; this
0x180020c8e  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\staterepositor"...
0x180020c95  mov     r9d, edi; char *
0x180020c98  mov     edx, 7Bh ; '{'; void *
0x180020c9d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020ca2  lea     rcx, [rbp+var_60]
0x180020ca6  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x180020cab  mov     ebx, edi
0x180020cad  jmp     short loc_180020CBA
0x180020caf  lea     rcx, [rbp+var_60]
0x180020cb3  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x180020cb8  xor     ebx, ebx
0x180020cba  lea     rcx, [rbp+var_58]
0x180020cbe  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x180020cc3  mov     eax, ebx
0x180020cc5  mov     rcx, [rbp+var_10]
0x180020cc9  xor     rcx, rsp; StackCookie
0x180020ccc  call    __security_check_cookie
0x180020cd1  lea     r11, [rsp+80h+var_s0]
0x180020cd9  mov     rbx, [r11+28h]
0x180020cdd  mov     rsi, [r11+30h]
0x180020ce1  mov     rsp, r11
0x180020ce4  pop     r14
0x180020ce6  pop     rdi
0x180020ce7  pop     rbp
0x180020ce8  retn
```
