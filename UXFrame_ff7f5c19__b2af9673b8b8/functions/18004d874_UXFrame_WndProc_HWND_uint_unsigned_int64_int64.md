# UXFrame::WndProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x18004d874`
- end: `0x18004db61`
- name: `?WndProc@UXFrame@@AEAA_JPEAUHWND__@@I_K_J@Z`
- size: `749`
- prototype: `__int64(UXFrame *__hidden this, HWND, unsigned int, unsigned __int64, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180050020`

## callees

- `0x180002b20`
- `0x1800041c4`
- `0x180004240`
- `0x1800049ac`
- `0x1800089c0`
- `0x18001049c`
- `0x18001600c`
- `0x180017164`
- `0x180038940`
- `0x18003c63c`
- `0x180044e9c`
- `0x18004d874`
- `0x18005a010`

## import_xrefs

- `USER32!DefWindowProcW` at `0x18004db0e`
- `USER32!DefWindowProcW` at `0x18004db0e`
- `ext-ms-win-uiacore-l1-1-0!UiaReturnRawElementProvider` at `0x18004d9a5`
- `ext-ms-win-uiacore-l1-1-0!UiaReturnRawElementProvider` at `0x18004da0d`
- `ext-ms-win-uiacore-l1-1-0!UiaReturnRawElementProvider` at `0x18004d9a5`
- `ext-ms-win-uiacore-l1-1-0!UiaReturnRawElementProvider` at `0x18004da0d`

## string_xrefs

- `0x18004db39`: `pcshell\shell\uxframe\dll\UXFrame.cpp`
- `0x18004db4f`: `pcshell\shell\uxframe\dll\UXFrame.cpp`

## pseudocode

```c
LRESULT __fastcall UXFrame::WndProc(UXFrame *this, HWND a2, UINT a3, WPARAM a4, LPARAM lParam)
{
  HWND v7; // rsi
  bool v9; // r15
  _QWORD *v10; // rdi
  __int64 v11; // rcx
  __int64 v12; // rax
  const char *v14; // r9
  __int64 v15; // rcx
  const char *v16; // r9
  void *v17; // rdx
  __int64 v18; // rcx
  char v19; // [rsp+30h] [rbp-38h]
  __int64 v20; // [rsp+38h] [rbp-30h] BYREF
  UXFrame *v21; // [rsp+40h] [rbp-28h] BYREF
  HWND v22; // [rsp+48h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+40h]

  v7 = a2;
  v22 = a2;
  v9 = 1;
  v19 = 1;
  v10 = (_QWORD *)((char *)this + 192);
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_5>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SWT_5>::GetImpl'::`2'::impl) )
  {
    if ( *v10 )
      v9 = (*(unsigned int (__fastcall **)(_QWORD, _QWORD, WPARAM, LPARAM))(*(_QWORD *)*v10 + 32LL))(
             *v10,
             a3,
             a4,
             lParam) != 1;
    v11 = *((_QWORD *)this + 26);
    if ( v11
      && (*(unsigned int (__fastcall **)(__int64, _QWORD, WPARAM, LPARAM))(*(_QWORD *)v11 + 112LL))(v11, a3, a4, lParam) == 1 )
    {
      v9 = 0;
    }
  }
  if ( a3 == 2 )
  {
    UiaReturnRawElementProvider(v7, 0, 0, 0);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_5>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SWT_5>::GetImpl'::`2'::impl) )
    {
      if ( *((_DWORD *)this + 64) != 5 )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x397,
          (unsigned int)"pcshell\\shell\\uxframe\\dll\\UXFrame.cpp",
          v14);
      v15 = *((_QWORD *)this + 24);
      if ( v15 && (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v15 + 56LL))(v15) )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x39C,
          (unsigned int)"pcshell\\shell\\uxframe\\dll\\UXFrame.cpp",
          v16);
    }
    else
    {
      v20 = *((_QWORD *)this + 23);
      winrt::Windows::Foundation::IUnknown::add_ref((winrt::Windows::Foundation::IUnknown *)&v20);
      FlowEndpointBase::InvokeMessage(
        (__int64)this + 312,
        3u,
        (winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v20);
    }
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_5>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SWT_5>::GetImpl'::`2'::impl) )
      wil::details::SetEvent(*((wil::details **)this + 33), v17);
    goto LABEL_28;
  }
  if ( a3 == 16 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_5>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SWT_5>::GetImpl'::`2'::impl) )
    {
      v21 = this;
      UXFrameTelemetry::OnWindowMessage_WM_CLOSE<UXFrame *>(&v21);
      v19 = 0;
      v9 = 0;
      v20 = 0;
      (*(void (__fastcall **)(char *, __int64 *))(*((_QWORD *)this + 2) + 32LL))((char *)this + 16, &v20);
      winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v20);
    }
    goto LABEL_28;
  }
  if ( a3 != 61 )
  {
    if ( a3 == 130 )
      *((_QWORD *)this + 37) = 0;
    goto LABEL_28;
  }
  if ( (_DWORD)lParam != -25 )
  {
LABEL_28:
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_5>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SWT_5>::GetImpl'::`2'::impl) )
    {
      if ( *v10
        && (*(unsigned int (__fastcall **)(_QWORD, _QWORD, WPARAM, LPARAM))(*(_QWORD *)*v10 + 32LL))(
             *v10,
             a3,
             a4,
             lParam) == 1 )
      {
        v9 = 0;
      }
      if ( v19 )
      {
        v18 = *((_QWORD *)this + 26);
        if ( v18 )
        {
          if ( (*(unsigned int (__fastcall **)(__int64, _QWORD, WPARAM, LPARAM))(*(_QWORD *)v18 + 112LL))(
                 v18,
                 a3,
                 a4,
                 lParam) == 1 )
            return 0;
        }
      }
    }
    if ( !v9 )
      return 0;
    else
      return DefWindowProcW(v7, a3, a4, lParam);
  }
  if ( !*((_QWORD *)this + 35) )
  {
    v21 = this;
    v12 = winrt::make_self<WindowUIAProvider,HWND__ * &,UXFrame *>(&v20, &v22, &v21);
    winrt::Windows::Foundation::IUnknown::operator=((char *)this + 280, v12);
    if ( v20 )
      winrt::com_ptr<WindowUIAProvider>::unconditional_release_ref(&v20);
    v7 = v22;
  }
  return UiaReturnRawElementProvider(v7, a4, lParam, *((IRawElementProviderSimple **)this + 35));
}

```

## disassembly

```asm
0x18004d874  push    rbp
0x18004d876  push    rbx
0x18004d877  push    rsi
0x18004d878  push    rdi
0x18004d879  push    r12
0x18004d87b  push    r13
0x18004d87d  push    r14
0x18004d87f  push    r15
0x18004d881  mov     rbp, rsp
0x18004d884  sub     rsp, 68h
0x18004d888  mov     rax, cs:__security_cookie
0x18004d88f  xor     rax, rsp
0x18004d892  mov     [rbp+var_18], rax
0x18004d896  mov     r13, r9
0x18004d899  mov     r12d, r8d
0x18004d89c  mov     rsi, rdx
0x18004d89f  mov     rbx, rcx
0x18004d8a2  mov     [rbp+var_20], rdx
0x18004d8a6  mov     r15b, 1
0x18004d8a9  mov     [rbp+var_38], r15b
0x18004d8ad  lea     rdi, [rcx+0C0h]
0x18004d8b4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SWT_5@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_5@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_5> `wil::Feature<__WilFeatureTraits_Feature_SWT_5>::GetImpl(void)'::`2'::impl
0x18004d8bb  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_5@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_5>::__private_IsEnabled(void)
0x18004d8c0  mov     r14, [rbp+lParam]
0x18004d8c4  test    al, al
0x18004d8c6  jnz     short loc_18004D91B
0x18004d8c8  mov     rcx, [rdi]
0x18004d8cb  test    rcx, rcx
0x18004d8ce  jz      short loc_18004D8F2
0x18004d8d0  mov     rax, [rcx]
0x18004d8d3  mov     r9, r14
0x18004d8d6  mov     r8, r13
0x18004d8d9  mov     edx, r12d
0x18004d8dc  mov     rax, [rax+20h]
0x18004d8e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d8e5  movzx   r15d, r15b
0x18004d8e9  xor     ecx, ecx
0x18004d8eb  cmp     eax, 1
0x18004d8ee  cmovz   r15d, ecx
0x18004d8f2  mov     rcx, [rbx+0D0h]
0x18004d8f9  test    rcx, rcx
0x18004d8fc  jz      short loc_18004D91B
0x18004d8fe  mov     rax, [rcx]
0x18004d901  mov     r9, r14
0x18004d904  mov     r8, r13
0x18004d907  mov     edx, r12d
0x18004d90a  mov     rax, [rax+70h]
0x18004d90e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d913  cmp     eax, 1
0x18004d916  jnz     short loc_18004D91B
0x18004d918  xor     r15b, r15b
0x18004d91b  mov     eax, r12d
0x18004d91e  sub     eax, 2
0x18004d921  jz      loc_18004DA02
0x18004d927  sub     eax, 0Eh
0x18004d92a  jz      loc_18004D9B0
0x18004d930  sub     eax, 2Dh ; '-'
0x18004d933  jz      short loc_18004D94E
0x18004d935  cmp     eax, 45h ; 'E'
0x18004d938  jnz     loc_18004DA97
0x18004d93e  mov     qword ptr [rbx+128h], 0
0x18004d949  jmp     loc_18004DA97
0x18004d94e  cmp     r14d, 0FFFFFFE7h
0x18004d952  jnz     loc_18004DA97
0x18004d958  lea     rdi, [rbx+118h]
0x18004d95f  cmp     qword ptr [rdi], 0
0x18004d963  jnz     short loc_18004D999
0x18004d965  mov     [rbp+var_28], rbx
0x18004d969  lea     r8, [rbp+var_28]
0x18004d96d  lea     rdx, [rbp+var_20]
0x18004d971  lea     rcx, [rbp+var_30]
0x18004d975  call    ??$make_self@VWindowUIAProvider@@AEAPEAUHWND__@@PEAVUXFrame@@@winrt@@YA?AU?$com_ptr@VWindowUIAProvider@@@0@AEAPEAUHWND__@@$$QEAPEAVUXFrame@@@Z; winrt::make_self<WindowUIAProvider,HWND__ * &,UXFrame *>(HWND__ * &,UXFrame * &&)
0x18004d97a  mov     rdx, rax
0x18004d97d  mov     rcx, rdi
0x18004d980  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@$$QEAU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown &&)
0x18004d985  cmp     [rbp+var_30], 0
0x18004d98a  jz      short loc_18004D995
0x18004d98c  lea     rcx, [rbp+var_30]
0x18004d990  call    ?unconditional_release_ref@?$com_ptr@VWindowUIAProvider@@@winrt@@AEAAXXZ; winrt::com_ptr<WindowUIAProvider>::unconditional_release_ref(void)
0x18004d995  mov     rsi, [rbp+var_20]
0x18004d999  mov     r9, [rdi]; el
0x18004d99c  mov     r8, r14; lParam
0x18004d99f  mov     rdx, r13; wParam
0x18004d9a2  mov     rcx, rsi; hwnd
0x18004d9a5  call    cs:__imp_UiaReturnRawElementProvider
0x18004d9ab  jmp     loc_18004DB18
0x18004d9b0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SWT_5@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_5@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_5> `wil::Feature<__WilFeatureTraits_Feature_SWT_5>::GetImpl(void)'::`2'::impl
0x18004d9b7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_5@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_5>::__private_IsEnabled(void)
0x18004d9bc  test    al, al
0x18004d9be  jz      loc_18004DA97
0x18004d9c4  mov     [rbp+var_28], rbx
0x18004d9c8  lea     rcx, [rbp+var_28]
0x18004d9cc  call    ??$OnWindowMessage_WM_CLOSE@PEAVUXFrame@@@UXFrameTelemetry@@SAX$$QEAPEAVUXFrame@@@Z; UXFrameTelemetry::OnWindowMessage_WM_CLOSE<UXFrame *>(UXFrame * &&)
0x18004d9d1  mov     [rbp+var_38], 0
0x18004d9d5  xor     r15b, r15b
0x18004d9d8  mov     [rbp+var_30], 0
0x18004d9e0  lea     rcx, [rbx+10h]
0x18004d9e4  mov     rax, [rcx]
0x18004d9e7  lea     rdx, [rbp+var_30]
0x18004d9eb  mov     rax, [rax+20h]
0x18004d9ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d9f4  lea     rcx, [rbp+var_30]; this
0x18004d9f8  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x18004d9fd  jmp     loc_18004DA97
0x18004da02  xor     r9d, r9d; el
0x18004da05  xor     r8d, r8d; lParam
0x18004da08  xor     edx, edx; wParam
0x18004da0a  mov     rcx, rsi; hwnd
0x18004da0d  call    cs:__imp_UiaReturnRawElementProvider
0x18004da13  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SWT_5@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_5@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_5> `wil::Feature<__WilFeatureTraits_Feature_SWT_5>::GetImpl(void)'::`2'::impl
0x18004da1a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_5@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_5>::__private_IsEnabled(void)
0x18004da1f  test    al, al
0x18004da21  jz      short loc_18004DA52
0x18004da23  cmp     dword ptr [rbx+100h], 5
0x18004da2a  jnz     loc_18004DB35
0x18004da30  mov     rcx, [rbx+0C0h]
0x18004da37  test    rcx, rcx
0x18004da3a  jz      short loc_18004DA7B
0x18004da3c  mov     rax, [rcx]
0x18004da3f  mov     rax, [rax+38h]
0x18004da43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004da48  test    eax, eax
0x18004da4a  jnz     loc_18004DB4B
0x18004da50  jmp     short loc_18004DA7B
0x18004da52  mov     rax, [rbx+0B8h]
0x18004da59  mov     [rbp+var_30], rax
0x18004da5d  lea     rcx, [rbp+var_30]; this
0x18004da61  call    ?add_ref@IUnknown@Foundation@Windows@winrt@@AEBAXXZ; winrt::Windows::Foundation::IUnknown::add_ref(void)
0x18004da66  lea     rcx, [rbx+138h]
0x18004da6d  lea     r8, [rbp+var_30]
0x18004da71  mov     edx, 3
0x18004da76  call    ?InvokeMessage@FlowEndpointBase@@QEAAXW4StandardMessage@@UValueSet@Collections@Foundation@Windows@winrt@@@Z; FlowEndpointBase::InvokeMessage(StandardMessage,winrt::Windows::Foundation::Collections::ValueSet)
0x18004da7b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SWT_5@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_5@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_5> `wil::Feature<__WilFeatureTraits_Feature_SWT_5>::GetImpl(void)'::`2'::impl
0x18004da82  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_5@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_5>::__private_IsEnabled(void)
0x18004da87  test    al, al
0x18004da89  jnz     short loc_18004DA97
0x18004da8b  mov     rcx, [rbx+108h]; this
0x18004da92  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x18004da97  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SWT_5@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_5@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_5> `wil::Feature<__WilFeatureTraits_Feature_SWT_5>::GetImpl(void)'::`2'::impl
0x18004da9e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_5@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_5>::__private_IsEnabled(void)
0x18004daa3  test    al, al
0x18004daa5  jz      short loc_18004DAFD
0x18004daa7  mov     rcx, [rdi]
0x18004daaa  test    rcx, rcx
0x18004daad  jz      short loc_18004DAD1
0x18004daaf  mov     rax, [rcx]
0x18004dab2  mov     r9, r14
0x18004dab5  mov     r8, r13
0x18004dab8  mov     edx, r12d
0x18004dabb  mov     rax, [rax+20h]
0x18004dabf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dac4  movzx   r15d, r15b
0x18004dac8  xor     ecx, ecx
0x18004daca  cmp     eax, 1
0x18004dacd  cmovz   r15d, ecx
0x18004dad1  cmp     [rbp+var_38], 0
0x18004dad5  jz      short loc_18004DAFD
0x18004dad7  mov     rcx, [rbx+0D0h]
0x18004dade  test    rcx, rcx
0x18004dae1  jz      short loc_18004DAFD
0x18004dae3  mov     rax, [rcx]
0x18004dae6  mov     r9, r14
0x18004dae9  mov     r8, r13
0x18004daec  mov     edx, r12d
0x18004daef  mov     rax, [rax+70h]
0x18004daf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004daf8  cmp     eax, 1
0x18004dafb  jz      short loc_18004DB16
0x18004dafd  test    r15b, r15b
0x18004db00  jz      short loc_18004DB16
0x18004db02  mov     r9, r14; lParam
0x18004db05  mov     r8, r13; wParam
0x18004db08  mov     edx, r12d; Msg
0x18004db0b  mov     rcx, rsi; hWnd
0x18004db0e  call    cs:__imp_DefWindowProcW
0x18004db14  jmp     short loc_18004DB18
0x18004db16  xor     eax, eax
0x18004db18  mov     rcx, [rbp+var_18]
0x18004db1c  xor     rcx, rsp; StackCookie
0x18004db1f  call    __security_check_cookie
0x18004db24  add     rsp, 68h
0x18004db28  pop     r15
0x18004db2a  pop     r14
0x18004db2c  pop     r13
0x18004db2e  pop     r12
0x18004db30  pop     rdi
0x18004db31  pop     rsi
0x18004db32  pop     rbx
0x18004db33  pop     rbp
0x18004db34  retn
0x18004db35  mov     rcx, [rbp+40h]; this
0x18004db39  lea     r8, aPcshellShellUx_2; "pcshell\\shell\\uxframe\\dll\\UXFrame.c"...
0x18004db40  mov     edx, 397h; void *
0x18004db45  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18004db4b  mov     rcx, [rbp+40h]; this
0x18004db4f  lea     r8, aPcshellShellUx_2; "pcshell\\shell\\uxframe\\dll\\UXFrame.c"...
0x18004db56  mov     edx, 39Ch; void *
0x18004db5b  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
