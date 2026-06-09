# CRdpIdSwapchain::Terminate(void)

- ea: `0x18002ce70`
- end: `0x18002cff5`
- name: `?Terminate@CRdpIdSwapchain@@QEAAXXZ`
- size: `389`
- prototype: `void __fastcall(CRdpIdSwapchain *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180024e68`

## callees

- `0x180001bc4`
- `0x18000d614`
- `0x180015398`
- `0x18001d7bc`
- `0x18002ce70`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18002ce97`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18002ce97`

## pseudocode

```c
void __fastcall CRdpIdSwapchain::Terminate(CRdpIdSwapchain *this)
{
  __int64 v2; // rcx
  int v3; // edi
  _DWORD *v4; // r8
  int v5; // r9d
  __int64 v6; // rax
  int v7; // ecx
  __int64 v8; // rdx
  _DWORD *v9; // r8
  int v10; // r9d
  __int64 v11; // rax
  int v12; // ecx
  const char *v13; // [rsp+50h] [rbp-10h] BYREF
  const char *v14; // [rsp+58h] [rbp-8h] BYREF
  int v15; // [rsp+90h] [rbp+30h] BYREF
  int v16; // [rsp+98h] [rbp+38h] BYREF
  int v17; // [rsp+A0h] [rbp+40h] BYREF
  const char *v18; // [rsp+A8h] [rbp+48h] BYREF

  v2 = *(_QWORD *)(*(_QWORD *)this + 24LL);
  if ( v2 )
    WaitForThreadpoolWaitCallbacks(*(PTP_WAIT *)(*(_QWORD *)(v2 + 24) + 8LL), 0);
  if ( *((_QWORD *)this + 2) )
  {
    v3 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)this + 232LL) + 516LL);
    v4 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
    if ( *v4 > 4u )
    {
      v6 = *(_QWORD *)this;
      v15 = v3;
      v13 = "CRdpIdSwapchain::Terminate";
      v14 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\swapchain.cpp";
      v7 = *(_DWORD *)(v6 + 280);
      v18 = "Swapchain processing stop requested";
      v16 = v7;
      v17 = 284;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v4,
        (unsigned int)byte_18004F693,
        (_DWORD)v4,
        v5,
        (__int64)&v14,
        (__int64)&v17,
        (__int64)&v13,
        (__int64)&v18,
        (__int64)&v16,
        (__int64)&v15);
    }
    Rdp::Utils::TP::details::CThreadPoolWait<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&void Rdp::Utils::TP::details::DestroyThreadpoolWait(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>>>::Shutdown(*((_QWORD *)this + 2));
    v8 = *((_QWORD *)this + 2);
    *((_QWORD *)this + 2) = 0;
    if ( v8 )
      std::default_delete<Rdp::Utils::TP::details::CThreadPoolWait<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&void Rdp::Utils::TP::details::DestroyThreadpoolWait(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>>>>::operator()();
    v9 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
    if ( *v9 > 4u )
    {
      v11 = *(_QWORD *)this;
      v15 = v3;
      v14 = "CRdpIdSwapchain::Terminate";
      v13 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\swapchain.cpp";
      v12 = *(_DWORD *)(v11 + 280);
      v18 = "Swapchain processing stopped";
      v16 = v12;
      v17 = 295;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v9,
        (unsigned int)byte_18004F643,
        (_DWORD)v9,
        v10,
        (__int64)&v13,
        (__int64)&v17,
        (__int64)&v14,
        (__int64)&v18,
        (__int64)&v16,
        (__int64)&v15);
    }
  }
}

```

## disassembly

```asm
0x18002ce70  push    rbp
0x18002ce72  push    rbx
0x18002ce73  push    rsi
0x18002ce74  push    rdi
0x18002ce75  push    r14
0x18002ce77  mov     rbp, rsp
0x18002ce7a  sub     rsp, 60h
0x18002ce7e  mov     rax, [rcx]
0x18002ce81  mov     rbx, rcx
0x18002ce84  mov     rcx, [rax+18h]
0x18002ce88  test    rcx, rcx
0x18002ce8b  jz      short loc_18002CEA3
0x18002ce8d  mov     rcx, [rcx+18h]
0x18002ce91  xor     edx, edx; fCancelPendingCallbacks
0x18002ce93  mov     rcx, [rcx+8]; pwa
0x18002ce97  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x18002ce9e  nop     dword ptr [rax+rax+00h]
0x18002cea3  cmp     qword ptr [rbx+10h], 0
0x18002cea8  jz      loc_18002CFE9
0x18002ceae  mov     rax, [rbx]
0x18002ceb1  mov     rcx, [rax+0E8h]
0x18002ceb8  mov     edi, [rcx+204h]
0x18002cebe  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x18002cec3  lea     rsi, aCrdpidswapchai; "CRdpIdSwapchain::Terminate"
0x18002ceca  lea     r14, aOnecoreuapTerm_8; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18002ced1  mov     r8, [rax+8]
0x18002ced5  mov     eax, [r8]
0x18002ced8  cmp     eax, 4
0x18002cedb  jbe     short loc_18002CF4B
0x18002cedd  mov     rax, [rbx]
0x18002cee0  lea     rdx, byte_18004F693
0x18002cee7  mov     [rbp+arg_0], edi
0x18002ceea  mov     [rbp+var_10], rsi
0x18002ceee  mov     [rbp+var_8], r14
0x18002cef2  mov     ecx, [rax+118h]
0x18002cef8  lea     rax, aSwapchainProce; "Swapchain processing stop requested"
0x18002ceff  mov     [rbp+arg_18], rax
0x18002cf03  lea     rax, [rbp+arg_0]
0x18002cf07  mov     [rsp+60h+var_18], rax
0x18002cf0c  lea     rax, [rbp+arg_8]
0x18002cf10  mov     [rsp+60h+var_20], rax
0x18002cf15  lea     rax, [rbp+arg_18]
0x18002cf19  mov     [rsp+60h+var_28], rax
0x18002cf1e  lea     rax, [rbp+var_10]
0x18002cf22  mov     [rsp+60h+var_30], rax
0x18002cf27  lea     rax, [rbp+arg_10]
0x18002cf2b  mov     [rsp+60h+var_38], rax
0x18002cf30  lea     rax, [rbp+var_8]
0x18002cf34  mov     [rbp+arg_8], ecx
0x18002cf37  mov     rcx, r8
0x18002cf3a  mov     [rsp+60h+var_40], rax
0x18002cf3f  mov     [rbp+arg_10], 11Ch
0x18002cf46  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18002cf4b  mov     rcx, [rbx+10h]
0x18002cf4f  call    ?Shutdown@?$CThreadPoolWait@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?DestroyThreadpoolWait@details@TP@Utils@Rdp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@TP@Utils@Rdp@@QEAAXXZ; Rdp::Utils::TP::details::CThreadPoolWait<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&Rdp::Utils::TP::details::DestroyThreadpoolWait(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>>>::Shutdown(void)
0x18002cf54  mov     rdx, [rbx+10h]
0x18002cf58  mov     qword ptr [rbx+10h], 0
0x18002cf60  test    rdx, rdx
0x18002cf63  jz      short loc_18002CF6A
0x18002cf65  call    ??R?$default_delete@V?$CThreadPoolWait@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?DestroyThreadpoolWait@details@TP@Utils@Rdp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@TP@Utils@Rdp@@@std@@QEBAXPEAV?$CThreadPoolWait@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?DestroyThreadpoolWait@details@TP@Utils@Rdp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@TP@Utils@Rdp@@@Z; std::default_delete<Rdp::Utils::TP::details::CThreadPoolWait<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&Rdp::Utils::TP::details::DestroyThreadpoolWait(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>>>>::operator()(Rdp::Utils::TP::details::CThreadPoolWait<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&Rdp::Utils::TP::details::DestroyThreadpoolWait(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>>> *)
0x18002cf6a  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x18002cf6f  mov     r8, [rax+8]
0x18002cf73  mov     eax, [r8]
0x18002cf76  cmp     eax, 4
0x18002cf79  jbe     short loc_18002CFE9
0x18002cf7b  mov     rax, [rbx]
0x18002cf7e  lea     rdx, byte_18004F643
0x18002cf85  mov     [rbp+arg_0], edi
0x18002cf88  mov     [rbp+var_8], rsi
0x18002cf8c  mov     [rbp+var_10], r14
0x18002cf90  mov     ecx, [rax+118h]
0x18002cf96  lea     rax, aSwapchainProce_0; "Swapchain processing stopped"
0x18002cf9d  mov     [rbp+arg_18], rax
0x18002cfa1  lea     rax, [rbp+arg_0]
0x18002cfa5  mov     [rsp+60h+var_18], rax
0x18002cfaa  lea     rax, [rbp+arg_8]
0x18002cfae  mov     [rsp+60h+var_20], rax
0x18002cfb3  lea     rax, [rbp+arg_18]
0x18002cfb7  mov     [rsp+60h+var_28], rax
0x18002cfbc  lea     rax, [rbp+var_8]
0x18002cfc0  mov     [rsp+60h+var_30], rax
0x18002cfc5  lea     rax, [rbp+arg_10]
0x18002cfc9  mov     [rsp+60h+var_38], rax
0x18002cfce  lea     rax, [rbp+var_10]
0x18002cfd2  mov     [rbp+arg_8], ecx
0x18002cfd5  mov     rcx, r8
0x18002cfd8  mov     [rsp+60h+var_40], rax
0x18002cfdd  mov     [rbp+arg_10], 127h
0x18002cfe4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18002cfe9  add     rsp, 60h
0x18002cfed  pop     r14
0x18002cfef  pop     rdi
0x18002cff0  pop     rsi
0x18002cff1  pop     rbx
0x18002cff2  pop     rbp
0x18002cff3  retn
```
