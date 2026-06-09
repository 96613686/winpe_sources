# Windows::Networking::UX::Internal::WlanInterface::_ProcessUIRequest(_GUID const &,_L2_UI_REQUEST *)

- ea: `0x18004b650`
- end: `0x18004b88f`
- name: `?_ProcessUIRequest@WlanInterface@Internal@UX@Networking@Windows@@IEAAXAEBU_GUID@@PEAU_L2_UI_REQUEST@@@Z`
- size: `575`
- prototype: `void __fastcall(Windows::Networking::UX::Internal::WlanInterface *__hidden this, const struct _GUID *, struct _L2_UI_REQUEST *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800508d0`

## callees

- `0x180003ed0`
- `0x1800043bc`
- `0x18000de4c`
- `0x180012178`
- `0x1800121e8`
- `0x1800141a0`
- `0x18001d4d4`
- `0x18002f0dc`
- `0x180039acc`
- `0x18003a600`
- `0x18003ad84`
- `0x180040eb0`
- `0x18004591c`
- `0x180047680`
- `0x1800476bc`
- `0x18004b650`
- `0x180066ec0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b7d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b7d4`

## pseudocode

```c
void __fastcall Windows::Networking::UX::Internal::WlanInterface::_ProcessUIRequest(
        Windows::Networking::UX::Internal::WlanInterface *this,
        struct _GUID *a2,
        struct _L2_UI_REQUEST *a3)
{
  char *v6; // r14
  __int64 v7; // r8
  void *v8; // r9
  __int64 v9; // rax
  __int64 v10; // r9
  __int64 v11; // rax
  __int64 v12; // rcx
  unsigned int v13; // eax
  unsigned int v14; // ebx
  __int64 v15; // rax
  int v16[2]; // [rsp+20h] [rbp-E0h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v18; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v19[8]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v20[16]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v21[336]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v22[336]; // [rsp+1A0h] [rbp+A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+338h] [rbp+238h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 253, &WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids);
  wil::EnterCriticalSection(v20, (char *)this + 1304);
  wil::EnterCriticalSection(v19, (char *)this + 752);
  v6 = (char *)this + 832;
  NetworkUxTelemetry::WlanConnectionFlow::TransferToCurrentThread((char *)this + 832, v21);
  if ( *((_QWORD *)this + 99) )
  {
    pv = a3;
    v8 = operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v8 )
    {
      v9 = wistd::unique_ptr<_L2_UI_REQUEST,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::unique_ptr<_L2_UI_REQUEST,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>(
             &v18,
             &pv,
             v7,
             v8);
      v11 = Windows::Networking::UX::Internal::WlanUIRequestEvent::WlanUIRequestEvent(v10, a2, v9);
      *(_QWORD *)v16 = v11;
      if ( v11 )
      {
        v12 = *((_QWORD *)this + 99);
        *(_QWORD *)v16 = 0;
        v18 = v11;
        v13 = Windows::Networking::UX::Internal::WlanStateMachine::PostMediaEvent(v12, &v18);
        v14 = v13;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 254, &WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids, v13);
        NetworkUxTelemetry::WlanConnectionFlow::SetUserInputState(v21, 0, v14);
        goto LABEL_13;
      }
    }
    else
    {
      *(_QWORD *)v16 = 0;
    }
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0xD5D,
      (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\wlaninterface.cpp",
      (const char *)0x8007000ELL,
      v16[0]);
LABEL_13:
    std::unique_ptr<std::_Facet_base>::~unique_ptr<std::_Facet_base>(v16);
    if ( pv )
      CoTaskMemFree(pv);
    goto LABEL_18;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 255, &WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids);
LABEL_18:
  v15 = NetworkUxTelemetry::WlanConnectionFlow::TransferToMember(v21, v22);
  NetworkUxTelemetry::WlanConnectionFlow::operator=(v6, v15);
  NetworkUxTelemetry::WlanConnectionFlow::~WlanConnectionFlow((NetworkUxTelemetry::WlanConnectionFlow *)v22);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 256, &WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids);
  NetworkUxTelemetry::WlanConnectionFlow::~WlanConnectionFlow((NetworkUxTelemetry::WlanConnectionFlow *)v21);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(v19);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(v20);
}

```

## disassembly

```asm
0x18004b650  push    rbp
0x18004b652  push    rbx
0x18004b653  push    rsi
0x18004b654  push    rdi
0x18004b655  push    r13
0x18004b657  push    r14
0x18004b659  lea     rbp, [rsp-208h]
0x18004b661  sub     rsp, 308h
0x18004b668  mov     rax, cs:__security_cookie
0x18004b66f  xor     rax, rsp
0x18004b672  mov     [rbp+230h+var_40], rax
0x18004b679  mov     rdi, r8
0x18004b67c  mov     rsi, rdx
0x18004b67f  mov     rbx, rcx
0x18004b682  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b689  lea     r13, WPP_GLOBAL_Control
0x18004b690  cmp     rcx, r13
0x18004b693  jz      short loc_18004B6B0
0x18004b695  test    byte ptr [rcx+1Ch], 40h
0x18004b699  jz      short loc_18004B6B0
0x18004b69b  mov     rcx, [rcx+10h]
0x18004b69f  lea     r8, WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids
0x18004b6a6  mov     edx, 0FDh
0x18004b6ab  call    WPP_SF_
0x18004b6b0  lea     rdx, [rbx+518h]
0x18004b6b7  lea     rcx, [rsp+330h+var_2F0]
0x18004b6bc  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18004b6c1  lea     rdx, [rbx+2F0h]
0x18004b6c8  lea     rcx, [rsp+330h+var_2F8]
0x18004b6cd  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18004b6d2  lea     r14, [rbx+340h]
0x18004b6d9  mov     rcx, r14
0x18004b6dc  lea     rdx, [rsp+330h+var_2E0]
0x18004b6e1  call    ?TransferToCurrentThread@WlanConnectionFlow@NetworkUxTelemetry@@QEAA?AV12@XZ; NetworkUxTelemetry::WlanConnectionFlow::TransferToCurrentThread(void)
0x18004b6e6  cmp     qword ptr [rbx+318h], 0
0x18004b6ee  jz      loc_18004B7DC
0x18004b6f4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18004b6fb  mov     [rsp+330h+pv], rdi
0x18004b700  mov     ecx, 28h ; '('; unsigned __int64
0x18004b705  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18004b70a  mov     r9, rax
0x18004b70d  test    rax, rax
0x18004b710  jz      loc_18004B799
0x18004b716  lea     rdx, [rsp+330h+pv]
0x18004b71b  lea     rcx, [rsp+330h+var_300]
0x18004b720  call    ??0?$unique_ptr@U_L2_UI_REQUEST@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAA@$$QEAV01@@Z; wistd::unique_ptr<_L2_UI_REQUEST,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::unique_ptr<_L2_UI_REQUEST,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>(wistd::unique_ptr<_L2_UI_REQUEST,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> &&)
0x18004b725  mov     r8, rax
0x18004b728  mov     rdx, rsi
0x18004b72b  mov     rcx, r9
0x18004b72e  call    ??0WlanUIRequestEvent@Internal@UX@Networking@Windows@@QEAA@AEBU_GUID@@V?$unique_ptr@U_L2_UI_REQUEST@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@Z; Windows::Networking::UX::Internal::WlanUIRequestEvent::WlanUIRequestEvent(_GUID const &,wistd::unique_ptr<_L2_UI_REQUEST,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>)
0x18004b733  mov     qword ptr [rsp+330h+var_310], rax
0x18004b738  test    rax, rax
0x18004b73b  jz      short loc_18004B7A2
0x18004b73d  mov     rcx, [rbx+318h]
0x18004b744  lea     rdx, [rsp+330h+var_300]
0x18004b749  mov     qword ptr [rsp+330h+var_310], 0
0x18004b752  mov     [rsp+330h+var_300], rax
0x18004b757  call    ?PostMediaEvent@WlanStateMachine@Internal@UX@Networking@Windows@@UEAAJV?$unique_ptr@UWlanStateMachineEvent@Internal@UX@Networking@Windows@@U?$default_delete@UWlanStateMachineEvent@Internal@UX@Networking@Windows@@@std@@@std@@@Z; Windows::Networking::UX::Internal::WlanStateMachine::PostMediaEvent(std::unique_ptr<Windows::Networking::UX::Internal::WlanStateMachineEvent>)
0x18004b75c  mov     ebx, eax
0x18004b75e  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b765  cmp     rcx, r13
0x18004b768  jz      short loc_18004B788
0x18004b76a  test    byte ptr [rcx+1Ch], 8
0x18004b76e  jz      short loc_18004B788
0x18004b770  mov     rcx, [rcx+10h]
0x18004b774  lea     r8, WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids
0x18004b77b  mov     edx, 0FEh
0x18004b780  mov     r9d, eax
0x18004b783  call    WPP_SF_d
0x18004b788  mov     r8d, ebx
0x18004b78b  lea     rcx, [rsp+330h+var_2E0]
0x18004b790  xor     edx, edx
0x18004b792  call    ?SetUserInputState@WlanConnectionFlow@NetworkUxTelemetry@@QEAAXW4UserInputState@@J@Z; NetworkUxTelemetry::WlanConnectionFlow::SetUserInputState(UserInputState,long)
0x18004b797  jmp     short loc_18004B7C0
0x18004b799  mov     qword ptr [rsp+330h+var_310], 0; int
0x18004b7a2  mov     rcx, [rbp+238h]; this
0x18004b7a9  lea     r8, aOnecoreuapNetU_20; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x18004b7b0  mov     r9d, 8007000Eh; char *
0x18004b7b6  mov     edx, 0D5Dh; void *
0x18004b7bb  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18004b7c0  lea     rcx, [rsp+330h+var_310]
0x18004b7c5  call    ??1?$unique_ptr@V_Facet_base@std@@U?$default_delete@V_Facet_base@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::_Facet_base>::~unique_ptr<std::_Facet_base>(void)
0x18004b7ca  mov     rcx, [rsp+330h+pv]; pv
0x18004b7cf  test    rcx, rcx
0x18004b7d2  jz      short loc_18004B803
0x18004b7d4  call    cs:__imp_CoTaskMemFree
0x18004b7da  jmp     short loc_18004B803
0x18004b7dc  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b7e3  cmp     rcx, r13
0x18004b7e6  jz      short loc_18004B803
0x18004b7e8  test    byte ptr [rcx+1Ch], 4
0x18004b7ec  jz      short loc_18004B803
0x18004b7ee  mov     rcx, [rcx+10h]
0x18004b7f2  lea     r8, WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids
0x18004b7f9  mov     edx, 0FFh
0x18004b7fe  call    WPP_SF_
0x18004b803  lea     rdx, [rbp+230h+var_190]
0x18004b80a  lea     rcx, [rsp+330h+var_2E0]
0x18004b80f  call    ?TransferToMember@WlanConnectionFlow@NetworkUxTelemetry@@QEAA?AV12@XZ; NetworkUxTelemetry::WlanConnectionFlow::TransferToMember(void)
0x18004b814  mov     rdx, rax
0x18004b817  mov     rcx, r14
0x18004b81a  call    ??4WlanConnectionFlow@NetworkUxTelemetry@@QEAAAEAV01@$$QEAV01@@Z; NetworkUxTelemetry::WlanConnectionFlow::operator=(NetworkUxTelemetry::WlanConnectionFlow &&)
0x18004b81f  lea     rcx, [rbp+230h+var_190]; this
0x18004b826  call    ??1WlanConnectionFlow@NetworkUxTelemetry@@QEAA@XZ; NetworkUxTelemetry::WlanConnectionFlow::~WlanConnectionFlow(void)
0x18004b82b  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b832  cmp     rcx, r13
0x18004b835  jz      short loc_18004B852
0x18004b837  test    byte ptr [rcx+1Ch], 40h
0x18004b83b  jz      short loc_18004B852
0x18004b83d  mov     rcx, [rcx+10h]
0x18004b841  lea     r8, WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids
0x18004b848  mov     edx, 100h
0x18004b84d  call    WPP_SF_
0x18004b852  lea     rcx, [rsp+330h+var_2E0]; this
0x18004b857  call    ??1WlanConnectionFlow@NetworkUxTelemetry@@QEAA@XZ; NetworkUxTelemetry::WlanConnectionFlow::~WlanConnectionFlow(void)
0x18004b85c  lea     rcx, [rsp+330h+var_2F8]
0x18004b861  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18004b866  lea     rcx, [rsp+330h+var_2F0]
0x18004b86b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18004b870  mov     rcx, [rbp+230h+var_40]
0x18004b877  xor     rcx, rsp; StackCookie
0x18004b87a  call    __security_check_cookie
0x18004b87f  add     rsp, 308h
0x18004b886  pop     r14
0x18004b888  pop     r13
0x18004b88a  pop     rdi
0x18004b88b  pop     rsi
0x18004b88c  pop     rbx
0x18004b88d  pop     rbp
0x18004b88e  retn
```
