# FlowEndpointBase::InvokeMessage(StandardMessage,winrt::Windows::Foundation::Collections::ValueSet)

- ea: `0x180044e9c`
- end: `0x180044fe2`
- name: `?InvokeMessage@FlowEndpointBase@@QEAAXW4StandardMessage@@UValueSet@Collections@Foundation@Windows@winrt@@@Z`
- size: `326`
- prototype: `void __high(enum StandardMessage, struct winrt::Windows::Foundation::Collections::ValueSet)`
- caller_count: `4`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180041960`
- `0x1800444f4`
- `0x18004d0b8`
- `0x18004d874`

## callees

- `0x180002b20`
- `0x1800041c4`
- `0x18000e2a0`
- `0x18001049c`
- `0x1800398d8`
- `0x180044e9c`
- `0x180044fe8`
- `0x18004eb14`

## import_xrefs

- `USER32!GetWindowThreadProcessId` at `0x180044f7f`
- `USER32!GetWindowThreadProcessId` at `0x180044f7f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180044f8b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180044f8b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180044ee5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180044ee5`

## string_xrefs

- `0x180044f95`: `ShellCommon\Internal\Shell\Inc\ValueSetChannel.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall FlowEndpointBase::InvokeMessage(
        __int64 a1,
        unsigned int a2,
        winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *a3)
{
  __int64 v6; // rax
  HWND v7; // rcx
  DWORD WindowThreadProcessId; // ebx
  const char *v9; // r9
  __int64 v10; // rax
  unsigned int v11; // [rsp+20h] [rbp-30h] BYREF
  __int64 v12; // [rsp+28h] [rbp-28h] BYREF
  _QWORD v13[2]; // [rsp+30h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]

  v13[1] = a3;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OobeShellHostWin32App>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_OobeShellHostWin32App>::GetImpl'::`2'::impl) )
  {
    v7 = *(HWND *)(a1 + 8);
    if ( v7 )
    {
      WindowThreadProcessId = GetWindowThreadProcessId(v7, 0);
      if ( WindowThreadProcessId != GetCurrentThreadId() )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x9C,
          (unsigned int)"ShellCommon\\Internal\\Shell\\Inc\\ValueSetChannel.h",
          v9);
    }
    if ( *(_DWORD *)(a1 + 112) != 2 )
    {
      v11 = a2;
      v10 = *(_QWORD *)a3;
      *(_QWORD *)a3 = 0;
      v12 = v10;
      std::list<std::pair<enum StandardMessage,winrt::Windows::Foundation::Collections::ValueSet>>::_Emplace<std::pair<enum StandardMessage,winrt::Windows::Foundation::Collections::ValueSet>>(
        a1 + 96,
        *(_QWORD *)(a1 + 96),
        &v11);
      winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v12);
      goto LABEL_6;
    }
    goto LABEL_5;
  }
  AcquireSRWLockExclusive((PSRWLOCK)(a1 + 120));
  v13[0] = a1 + 120;
  if ( *(_BYTE *)(a1 + 128) )
  {
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v13);
LABEL_5:
    FlowEndpointBase::InvokeMessageToEndpoint(a1, *(_QWORD *)(a1 + 40), a2, a3);
    goto LABEL_6;
  }
  v11 = a2;
  v6 = *(_QWORD *)a3;
  *(_QWORD *)a3 = 0;
  v12 = v6;
  std::list<std::pair<enum StandardMessage,winrt::Windows::Foundation::Collections::ValueSet>>::_Emplace<std::pair<enum StandardMessage,winrt::Windows::Foundation::Collections::ValueSet>>(
    a1 + 96,
    *(_QWORD *)(a1 + 96),
    &v11);
  winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v12);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v13);
LABEL_6:
  winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(a3);
}

```

## disassembly

```asm
0x180044e9c  mov     [rsp-28h+arg_18], rbx
0x180044ea1  push    rbp
0x180044ea2  push    rsi
0x180044ea3  push    rdi
0x180044ea4  push    r14
0x180044ea6  push    r15
0x180044ea8  mov     rbp, rsp
0x180044eab  sub     rsp, 50h
0x180044eaf  mov     rax, cs:__security_cookie
0x180044eb6  xor     rax, rsp
0x180044eb9  mov     [rbp+var_10], rax
0x180044ebd  mov     rsi, r8
0x180044ec0  mov     r14d, edx
0x180044ec3  mov     rdi, rcx
0x180044ec6  mov     [rbp+var_18], r8
0x180044eca  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OobeShellHostWin32App@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OobeShellHostWin32App@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OobeShellHostWin32App> `wil::Feature<__WilFeatureTraits_Feature_OobeShellHostWin32App>::GetImpl(void)'::`2'::impl
0x180044ed1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OobeShellHostWin32App@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OobeShellHostWin32App>::__private_IsEnabled(void)
0x180044ed6  test    al, al
0x180044ed8  jz      loc_180044F74
0x180044ede  lea     rbx, [rdi+78h]
0x180044ee2  mov     rcx, rbx; SRWLock
0x180044ee5  call    cs:__imp_AcquireSRWLockExclusive
0x180044eeb  mov     [rbp+var_20], rbx
0x180044eef  cmp     byte ptr [rdi+80h], 0
0x180044ef6  jnz     short loc_180044F30
0x180044ef8  lea     rcx, [rdi+60h]
0x180044efc  mov     [rbp+var_30], r14d
0x180044f00  mov     rax, [rsi]
0x180044f03  mov     qword ptr [rsi], 0
0x180044f0a  mov     [rbp+var_28], rax
0x180044f0e  lea     r8, [rbp+var_30]
0x180044f12  mov     rdx, [rcx]
0x180044f15  call    ??$_Emplace@U?$pair@W4StandardMessage@@UValueSet@Collections@Foundation@Windows@winrt@@@std@@@?$list@U?$pair@W4StandardMessage@@UValueSet@Collections@Foundation@Windows@winrt@@@std@@V?$allocator@U?$pair@W4StandardMessage@@UValueSet@Collections@Foundation@Windows@winrt@@@std@@@2@@std@@QEAAPEAU?$_List_node@U?$pair@W4StandardMessage@@UValueSet@Collections@Foundation@Windows@winrt@@@std@@PEAX@1@QEAU21@$$QEAU?$pair@W4StandardMessage@@UValueSet@Collections@Foundation@Windows@winrt@@@1@@Z; std::list<std::pair<StandardMessage,winrt::Windows::Foundation::Collections::ValueSet>>::_Emplace<std::pair<StandardMessage,winrt::Windows::Foundation::Collections::ValueSet>>(std::_List_node<std::pair<StandardMessage,winrt::Windows::Foundation::Collections::ValueSet>,void *> * const,std::pair<StandardMessage,winrt::Windows::Foundation::Collections::ValueSet> &&)
0x180044f1a  nop
0x180044f1b  lea     rcx, [rbp+var_28]; this
0x180044f1f  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x180044f24  nop
0x180044f25  lea     rcx, [rbp+var_20]
0x180044f29  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180044f2e  jmp     short loc_180044F4C
0x180044f30  lea     rcx, [rbp+var_20]
0x180044f34  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180044f39  mov     r9, rsi
0x180044f3c  mov     r8d, r14d
0x180044f3f  mov     rdx, [rdi+28h]
0x180044f43  mov     rcx, rdi
0x180044f46  call    ?InvokeMessageToEndpoint@FlowEndpointBase@@QEAAXPEAUHWND__@@W4StandardMessage@@AEBUValueSet@Collections@Foundation@Windows@winrt@@@Z; FlowEndpointBase::InvokeMessageToEndpoint(HWND__ *,StandardMessage,winrt::Windows::Foundation::Collections::ValueSet const &)
0x180044f4b  nop
0x180044f4c  mov     rcx, rsi; this
0x180044f4f  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x180044f54  mov     rcx, [rbp+var_10]
0x180044f58  xor     rcx, rsp; StackCookie
0x180044f5b  call    __security_check_cookie
0x180044f60  mov     rbx, [rsp+50h+arg_18]
0x180044f68  add     rsp, 50h
0x180044f6c  pop     r15
0x180044f6e  pop     r14
0x180044f70  pop     rdi
0x180044f71  pop     rsi
0x180044f72  pop     rbp
0x180044f73  retn
0x180044f74  mov     rcx, [rdi+8]; hWnd
0x180044f78  test    rcx, rcx
0x180044f7b  jz      short loc_180044FAA
0x180044f7d  xor     edx, edx; lpdwProcessId
0x180044f7f  call    cs:__imp_GetWindowThreadProcessId
0x180044f85  mov     ebx, eax
0x180044f87  mov     r15, [rbp+28h]
0x180044f8b  call    cs:__imp_GetCurrentThreadId
0x180044f91  cmp     ebx, eax
0x180044f93  jz      short loc_180044FAA
0x180044f95  lea     r8, aShellcommonInt_0; "ShellCommon\\Internal\\Shell\\Inc\\Valu"...
0x180044f9c  mov     edx, 9Ch; void *
0x180044fa1  mov     rcx, r15; this
0x180044fa4  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180044faa  cmp     dword ptr [rdi+70h], 2
0x180044fae  jz      short loc_180044F39
0x180044fb0  lea     rcx, [rdi+60h]
0x180044fb4  mov     [rbp+var_30], r14d
0x180044fb8  mov     rax, [rsi]
0x180044fbb  mov     qword ptr [rsi], 0
0x180044fc2  mov     [rbp+var_28], rax
0x180044fc6  lea     r8, [rbp+var_30]
0x180044fca  mov     rdx, [rcx]
0x180044fcd  call    ??$_Emplace@U?$pair@W4StandardMessage@@UValueSet@Collections@Foundation@Windows@winrt@@@std@@@?$list@U?$pair@W4StandardMessage@@UValueSet@Collections@Foundation@Windows@winrt@@@std@@V?$allocator@U?$pair@W4StandardMessage@@UValueSet@Collections@Foundation@Windows@winrt@@@std@@@2@@std@@QEAAPEAU?$_List_node@U?$pair@W4StandardMessage@@UValueSet@Collections@Foundation@Windows@winrt@@@std@@PEAX@1@QEAU21@$$QEAU?$pair@W4StandardMessage@@UValueSet@Collections@Foundation@Windows@winrt@@@1@@Z; std::list<std::pair<StandardMessage,winrt::Windows::Foundation::Collections::ValueSet>>::_Emplace<std::pair<StandardMessage,winrt::Windows::Foundation::Collections::ValueSet>>(std::_List_node<std::pair<StandardMessage,winrt::Windows::Foundation::Collections::ValueSet>,void *> * const,std::pair<StandardMessage,winrt::Windows::Foundation::Collections::ValueSet> &&)
0x180044fd2  nop
0x180044fd3  lea     rcx, [rbp+var_28]; this
0x180044fd7  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x180044fdc  jmp     loc_180044F4C
```
