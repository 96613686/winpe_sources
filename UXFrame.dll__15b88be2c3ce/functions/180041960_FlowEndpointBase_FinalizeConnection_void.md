# FlowEndpointBase::FinalizeConnection(void)

- ea: `0x180041960`
- end: `0x180041bbd`
- name: `?FinalizeConnection@FlowEndpointBase@@IEAAXXZ`
- size: `605`
- prototype: `void __fastcall(FlowEndpointBase *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800447bc`

## callees

- `0x180002b20`
- `0x1800041c4`
- `0x1800050b4`
- `0x1800089c0`
- `0x18000e2a0`
- `0x18001049c`
- `0x18003d424`
- `0x180041960`
- `0x180044e9c`
- `0x180044fe8`
- `0x18004eb14`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800419b1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800419b1`

## string_xrefs

- `0x180041bab`: `ShellCommon\Internal\Shell\Inc\ValueSetChannel.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall FlowEndpointBase::FinalizeConnection(FlowEndpointBase *this)
{
  char IsEnabled; // al
  int v3; // r12d
  const char *v4; // r9
  _QWORD **v5; // rbx
  _QWORD *i; // rdi
  _QWORD *v7; // r14
  _QWORD *v8; // rdi
  void (__fastcall ***v9)(_QWORD, _QWORD, char **); // rcx
  void (__fastcall **v10)(_QWORD, _QWORD, char **); // rax
  _QWORD **v11; // rbx
  _QWORD *j; // rdi
  unsigned int v13; // r14d
  char *v14; // rsi
  void (__fastcall ***v15)(_QWORD, _QWORD, char **); // rcx
  void (__fastcall **v16)(_QWORD, _QWORD, char **); // rax
  _QWORD *v17; // r14
  _QWORD *v18; // rdi
  char *v19; // [rsp+20h] [rbp-30h] BYREF
  unsigned int v20; // [rsp+28h] [rbp-28h]
  char *v21; // [rsp+30h] [rbp-20h] BYREF
  __int128 v22; // [rsp+38h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]

  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_OobeShellHostWin32App>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_OobeShellHostWin32App>::GetImpl'::`2'::impl);
  v3 = *((_DWORD *)this + 28);
  *((_DWORD *)this + 28) = 2;
  if ( IsEnabled )
  {
    AcquireSRWLockExclusive((PSRWLOCK)this + 15);
    v19 = (char *)this + 120;
    if ( *((_BYTE *)this + 128) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x184,
        (unsigned int)"ShellCommon\\Internal\\Shell\\Inc\\ValueSetChannel.h",
        v4);
    *((_BYTE *)this + 128) = 1;
    v22 = 0;
    std::list<std::pair<enum StandardMessage,winrt::Windows::Foundation::Collections::ValueSet>>::list<std::pair<enum StandardMessage,winrt::Windows::Foundation::Collections::ValueSet>>(
      &v22,
      (char *)this + 96);
    v5 = (_QWORD **)v22;
    for ( i = *(_QWORD **)v22; i != v5; i = (_QWORD *)*i )
    {
      v20 = *((_DWORD *)i + 4);
      v21 = (char *)i[3];
      winrt::Windows::Foundation::IUnknown::add_ref((winrt::Windows::Foundation::IUnknown *)&v21);
      FlowEndpointBase::InvokeMessageToEndpoint(this, *((_QWORD *)this + 5), v20, &v21);
      winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v21);
    }
    *v5[1] = 0;
    v7 = *v5;
    if ( *v5 )
    {
      do
      {
        v8 = (_QWORD *)*v7;
        winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)(v7 + 3));
        std::_Deallocate<16>(v7, 32);
        v7 = v8;
      }
      while ( v8 );
    }
    std::_Deallocate<16>(v5, 32);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v19);
    if ( v3 )
    {
      v9 = (void (__fastcall ***)(_QWORD, _QWORD, char **))*((_QWORD *)this + 10);
      v10 = *v9;
      v19 = 0;
      (*v10)(v9, 0, &v19);
      winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v19);
    }
  }
  else
  {
    v22 = 0;
    std::list<std::pair<enum StandardMessage,winrt::Windows::Foundation::Collections::ValueSet>>::list<std::pair<enum StandardMessage,winrt::Windows::Foundation::Collections::ValueSet>>(
      &v22,
      (char *)this + 96);
    v11 = (_QWORD **)v22;
    for ( j = *(_QWORD **)v22; j != v11; j = (_QWORD *)*j )
    {
      v20 = *((_DWORD *)j + 4);
      v13 = v20;
      v21 = (char *)j[3];
      v14 = v21;
      winrt::Windows::Foundation::IUnknown::add_ref((winrt::Windows::Foundation::IUnknown *)&v21);
      v19 = v14;
      winrt::Windows::Foundation::IUnknown::add_ref((winrt::Windows::Foundation::IUnknown *)&v19);
      FlowEndpointBase::InvokeMessage((__int64)this, v13, (winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v19);
      winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v21);
    }
    if ( v3 )
    {
      v15 = (void (__fastcall ***)(_QWORD, _QWORD, char **))*((_QWORD *)this + 10);
      v16 = *v15;
      v19 = 0;
      (*v16)(v15, 0, &v19);
      winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v19);
    }
    *v11[1] = 0;
    v17 = *v11;
    if ( *v11 )
    {
      do
      {
        v18 = (_QWORD *)*v17;
        winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)(v17 + 3));
        std::_Deallocate<16>(v17, 32);
        v17 = v18;
      }
      while ( v18 );
    }
    std::_Deallocate<16>(v11, 32);
  }
}

```

## disassembly

```asm
0x180041960  mov     [rsp-28h+arg_8], rbx
0x180041965  mov     [rsp-28h+arg_10], rsi
0x18004196a  push    rbp
0x18004196b  push    rdi
0x18004196c  push    r12
0x18004196e  push    r14
0x180041970  push    r15
0x180041972  mov     rbp, rsp
0x180041975  sub     rsp, 50h
0x180041979  mov     rax, cs:__security_cookie
0x180041980  xor     rax, rsp
0x180041983  mov     [rbp+var_8], rax
0x180041987  mov     r15, rcx
0x18004198a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OobeShellHostWin32App@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OobeShellHostWin32App@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OobeShellHostWin32App> `wil::Feature<__WilFeatureTraits_Feature_OobeShellHostWin32App>::GetImpl(void)'::`2'::impl
0x180041991  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OobeShellHostWin32App@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OobeShellHostWin32App>::__private_IsEnabled(void)
0x180041996  mov     r12d, [r15+70h]
0x18004199a  mov     dword ptr [r15+70h], 2
0x1800419a2  test    al, al
0x1800419a4  jz      loc_180041AB1
0x1800419aa  lea     rbx, [r15+78h]
0x1800419ae  mov     rcx, rbx; SRWLock
0x1800419b1  call    cs:__imp_AcquireSRWLockExclusive
0x1800419b7  mov     [rbp+var_30], rbx
0x1800419bb  mov     rcx, [rbp+28h]; this
0x1800419bf  cmp     byte ptr [r15+80h], 0
0x1800419c7  jnz     loc_180041BAB
0x1800419cd  mov     byte ptr [r15+80h], 1
0x1800419d5  xorps   xmm0, xmm0
0x1800419d8  movups  [rbp+var_18], xmm0
0x1800419dc  lea     rdx, [r15+60h]
0x1800419e0  lea     rcx, [rbp+var_18]
0x1800419e4  call    ??0?$list@U?$pair@W4StandardMessage@@UValueSet@Collections@Foundation@Windows@winrt@@@std@@V?$allocator@U?$pair@W4StandardMessage@@UValueSet@Collections@Foundation@Windows@winrt@@@std@@@2@@std@@QEAA@$$QEAV01@@Z; std::list<std::pair<StandardMessage,winrt::Windows::Foundation::Collections::ValueSet>>::list<std::pair<StandardMessage,winrt::Windows::Foundation::Collections::ValueSet>>(std::list<std::pair<StandardMessage,winrt::Windows::Foundation::Collections::ValueSet>> &&)
0x1800419e9  nop
0x1800419ea  mov     rbx, qword ptr [rbp+var_18]
0x1800419ee  mov     rdi, [rbx]
0x1800419f1  cmp     rdi, rbx
0x1800419f4  jz      short loc_180041A30
0x1800419f6  mov     esi, [rdi+10h]
0x1800419f9  mov     [rbp+var_28], esi
0x1800419fc  mov     rax, [rdi+18h]
0x180041a00  mov     [rbp+var_20], rax
0x180041a04  lea     rcx, [rbp+var_20]; this
0x180041a08  call    ?add_ref@IUnknown@Foundation@Windows@winrt@@AEBAXXZ; winrt::Windows::Foundation::IUnknown::add_ref(void)
0x180041a0d  nop
0x180041a0e  lea     r9, [rbp+var_20]
0x180041a12  mov     r8d, esi
0x180041a15  mov     rdx, [r15+28h]
0x180041a19  mov     rcx, r15
0x180041a1c  call    ?InvokeMessageToEndpoint@FlowEndpointBase@@QEAAXPEAUHWND__@@W4StandardMessage@@AEBUValueSet@Collections@Foundation@Windows@winrt@@@Z; FlowEndpointBase::InvokeMessageToEndpoint(HWND__ *,StandardMessage,winrt::Windows::Foundation::Collections::ValueSet const &)
0x180041a21  nop
0x180041a22  lea     rcx, [rbp+var_20]; this
0x180041a26  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x180041a2b  mov     rdi, [rdi]
0x180041a2e  jmp     short loc_1800419F1
0x180041a30  mov     rax, [rbx+8]
0x180041a34  mov     qword ptr [rax], 0
0x180041a3b  mov     r14, [rbx]
0x180041a3e  mov     esi, 20h ; ' '
0x180041a43  test    r14, r14
0x180041a46  jz      short loc_180041A67
0x180041a48  mov     rdi, [r14]
0x180041a4b  lea     rcx, [r14+18h]; this
0x180041a4f  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x180041a54  mov     rdx, rsi
0x180041a57  mov     rcx, r14
0x180041a5a  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180041a5f  mov     r14, rdi
0x180041a62  test    rdi, rdi
0x180041a65  jnz     short loc_180041A48
0x180041a67  mov     rdx, rsi
0x180041a6a  mov     rcx, rbx
0x180041a6d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180041a72  nop
0x180041a73  lea     rcx, [rbp+var_30]
0x180041a77  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180041a7c  test    r12d, r12d
0x180041a7f  jz      loc_180041B86
0x180041a85  mov     rcx, [r15+50h]
0x180041a89  mov     rax, [rcx]
0x180041a8c  mov     [rbp+var_30], 0
0x180041a94  lea     r8, [rbp+var_30]
0x180041a98  xor     edx, edx
0x180041a9a  mov     rax, [rax]
0x180041a9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041aa2  nop
0x180041aa3  lea     rcx, [rbp+var_30]; this
0x180041aa7  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x180041aac  jmp     loc_180041B86
0x180041ab1  xorps   xmm0, xmm0
0x180041ab4  movups  [rbp+var_18], xmm0
0x180041ab8  lea     rdx, [r15+60h]
0x180041abc  lea     rcx, [rbp+var_18]
0x180041ac0  call    ??0?$list@U?$pair@W4StandardMessage@@UValueSet@Collections@Foundation@Windows@winrt@@@std@@V?$allocator@U?$pair@W4StandardMessage@@UValueSet@Collections@Foundation@Windows@winrt@@@std@@@2@@std@@QEAA@$$QEAV01@@Z; std::list<std::pair<StandardMessage,winrt::Windows::Foundation::Collections::ValueSet>>::list<std::pair<StandardMessage,winrt::Windows::Foundation::Collections::ValueSet>>(std::list<std::pair<StandardMessage,winrt::Windows::Foundation::Collections::ValueSet>> &&)
0x180041ac5  nop
0x180041ac6  mov     rbx, qword ptr [rbp+var_18]
0x180041aca  mov     rdi, [rbx]
0x180041acd  cmp     rdi, rbx
0x180041ad0  jz      short loc_180041B17
0x180041ad2  mov     r14d, [rdi+10h]
0x180041ad6  mov     [rbp+var_28], r14d
0x180041ada  mov     rsi, [rdi+18h]
0x180041ade  mov     [rbp+var_20], rsi
0x180041ae2  lea     rcx, [rbp+var_20]; this
0x180041ae6  call    ?add_ref@IUnknown@Foundation@Windows@winrt@@AEBAXXZ; winrt::Windows::Foundation::IUnknown::add_ref(void)
0x180041aeb  nop
0x180041aec  mov     [rbp+var_30], rsi
0x180041af0  lea     rcx, [rbp+var_30]; this
0x180041af4  call    ?add_ref@IUnknown@Foundation@Windows@winrt@@AEBAXXZ; winrt::Windows::Foundation::IUnknown::add_ref(void)
0x180041af9  lea     r8, [rbp+var_30]
0x180041afd  mov     edx, r14d
0x180041b00  mov     rcx, r15
0x180041b03  call    ?InvokeMessage@FlowEndpointBase@@QEAAXW4StandardMessage@@UValueSet@Collections@Foundation@Windows@winrt@@@Z; FlowEndpointBase::InvokeMessage(StandardMessage,winrt::Windows::Foundation::Collections::ValueSet)
0x180041b08  nop
0x180041b09  lea     rcx, [rbp+var_20]; this
0x180041b0d  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x180041b12  mov     rdi, [rdi]
0x180041b15  jmp     short loc_180041ACD
0x180041b17  test    r12d, r12d
0x180041b1a  jz      short loc_180041B44
0x180041b1c  mov     rcx, [r15+50h]
0x180041b20  mov     rax, [rcx]
0x180041b23  mov     [rbp+var_30], 0
0x180041b2b  lea     r8, [rbp+var_30]
0x180041b2f  xor     edx, edx
0x180041b31  mov     rax, [rax]
0x180041b34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041b39  nop
0x180041b3a  lea     rcx, [rbp+var_30]; this
0x180041b3e  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x180041b43  nop
0x180041b44  mov     rax, [rbx+8]
0x180041b48  mov     qword ptr [rax], 0
0x180041b4f  mov     r14, [rbx]
0x180041b52  mov     esi, 20h ; ' '
0x180041b57  test    r14, r14
0x180041b5a  jz      short loc_180041B7B
0x180041b5c  mov     rdi, [r14]
0x180041b5f  lea     rcx, [r14+18h]; this
0x180041b63  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x180041b68  mov     rdx, rsi
0x180041b6b  mov     rcx, r14
0x180041b6e  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180041b73  mov     r14, rdi
0x180041b76  test    rdi, rdi
0x180041b79  jnz     short loc_180041B5C
0x180041b7b  mov     rdx, rsi
0x180041b7e  mov     rcx, rbx
0x180041b81  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180041b86  mov     rcx, [rbp+var_8]
0x180041b8a  xor     rcx, rsp; StackCookie
0x180041b8d  call    __security_check_cookie
0x180041b92  lea     r11, [rsp+50h+var_s0]
0x180041b97  mov     rbx, [r11+38h]
0x180041b9b  mov     rsi, [r11+40h]
0x180041b9f  mov     rsp, r11
0x180041ba2  pop     r15
0x180041ba4  pop     r14
0x180041ba6  pop     r12
0x180041ba8  pop     rdi
0x180041ba9  pop     rbp
0x180041baa  retn
0x180041bab  lea     r8, aShellcommonInt_0; "ShellCommon\\Internal\\Shell\\Inc\\Valu"...
0x180041bb2  mov     edx, 184h; void *
0x180041bb7  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
