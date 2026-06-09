# Container::Manager::Agent::Core::WaitForSystemQuiesce(ulong &)

- ea: `0x180020308`
- end: `0x180020586`
- name: `?WaitForSystemQuiesce@Core@Agent@Manager@Container@@YAJAEAK@Z`
- size: `638`
- prototype: `__int64 __fastcall(Container::Manager::Agent::Core *__hidden this, unsigned int *)`
- caller_count: `3`
- callee_count: `12`
- tags: `service_task, installer_update`

## callers

- `0x180004f40`
- `0x180005400`
- `0x180023090`

## callees

- `0x180002140`
- `0x180002ea4`
- `0x1800045e4`
- `0x180005934`
- `0x1800059f8`
- `0x1800063e8`
- `0x180007b4c`
- `0x18000892c`
- `0x18000a768`
- `0x180011ea4`
- `0x18001c9dc`
- `0x180020308`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180020394`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180020394`
- `ext-ms-win-resourcemanager-crm-l1-2-0!CrmActivityWindowClosedReasonSubscribe` at `0x1800204b1`
- `ext-ms-win-resourcemanager-crm-l1-2-0!CrmActivityWindowClosedReasonSubscribe` at `0x1800204b1`
- `ext-ms-win-resourcemanager-crm-l1-2-0!CrmRegister` at `0x1800203c5`
- `ext-ms-win-resourcemanager-crm-l1-2-0!CrmRegister` at `0x1800203c5`
- `ext-ms-win-resourcemanager-crm-l1-2-0!CrmUnregister` at `0x180020400`
- `ext-ms-win-resourcemanager-crm-l1-2-0!CrmUnregister` at `0x18002052c`
- `ext-ms-win-resourcemanager-crm-l1-2-0!CrmUnregister` at `0x180020400`
- `ext-ms-win-resourcemanager-crm-l1-2-0!CrmUnregister` at `0x18002052c`
- `ext-ms-win-resourcemanager-crm-l1-2-0!CrmActivityFree` at `0x18002048f`
- `ext-ms-win-resourcemanager-crm-l1-2-0!CrmActivityFree` at `0x180020516`
- `ext-ms-win-resourcemanager-crm-l1-2-0!CrmActivityFree` at `0x18002048f`
- `ext-ms-win-resourcemanager-crm-l1-2-0!CrmActivityFree` at `0x180020516`
- `ext-ms-win-resourcemanager-crm-l1-2-0!CrmActivityAllocate` at `0x180020454`
- `ext-ms-win-resourcemanager-crm-l1-2-0!CrmActivityAllocate` at `0x180020454`
- `ext-ms-win-resourcemanager-crm-l1-2-0!CrmActivityWindowClosedReasonUnsubscribe` at `0x1800204dc`
- `ext-ms-win-resourcemanager-crm-l1-2-0!CrmActivityWindowClosedReasonUnsubscribe` at `0x1800204dc`

## string_xrefs

- `0x18002037c`: `onecore\base\gendrv\silos\clem\agent\core\lib\core.cpp`
- `0x1800203df`: `onecore\base\gendrv\silos\clem\agent\core\lib\core.cpp`
- `0x180020469`: `onecore\base\gendrv\silos\clem\agent\core\lib\core.cpp`
- `0x1800204f6`: `onecore\base\gendrv\silos\clem\agent\core\lib\core.cpp`

## pseudocode

```c
__int64 __fastcall Container::Manager::Agent::Core::WaitForSystemQuiesce(
        Container::Manager::Agent::Core *this,
        unsigned int *a2)
{
  int v3; // ebx
  int v4; // eax
  int v5; // eax
  __int64 v6; // rdx
  __int64 v8; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v9; // [rsp+48h] [rbp-B8h] BYREF
  _DWORD Address[4]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v11[42]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+C8h]

  wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    (__int64)v11,
    (__int64)"WaitForSystemQuiesce");
  v11[0] = &CmAgentTraceProvider::WaitForSystemQuiesce::`vftable';
  CmAgentTraceProvider::WaitForSystemQuiesce::StartActivity((CmAgentTraceProvider::WaitForSystemQuiesce *)v11);
  if ( !(unsigned __int8)IsCrmRegisterPresent() )
  {
    if ( *(_DWORD *)this < 0x1388u )
    {
      v3 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x4E0,
             (int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\core.cpp",
             (const char *)0x5B4);
      goto LABEL_23;
    }
    Sleep(0x1388u);
    *(_DWORD *)this -= 5000;
LABEL_22:
    wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
      (__int64)v11,
      0);
    v3 = 0;
    goto LABEL_23;
  }
  v9 = 0;
  v4 = CrmRegister(&v9, 306, L"CrmClient_ContainerManager");
  if ( v4 >= 0 )
  {
    Address[0] = 0;
    v8 = 0;
    v5 = CrmActivityAllocate(&v8, v9, 1201, L"CrmClientActivity_ContainerManagerCpuDiskLowUsage", 0, 0, 0);
    if ( v5 >= 0 )
    {
      v5 = CrmActivityWindowClosedReasonSubscribe(
             v8,
             &Container::Manager::Agent::Core::_anonymous_namespace_::CrmSystemLowUsageWindowClosedReasonCallback,
             Address);
      if ( v5 >= 0 )
      {
        v3 = Container::Manager::Agent::Core::Details::WaitOnEventAndUpdateTimeout<wil::slim_event_t<1>>(
               Address,
               (unsigned int *)this);
        CrmActivityWindowClosedReasonUnsubscribe(v8);
        if ( v3 >= 0 )
        {
          if ( v8 )
            CrmActivityFree();
          if ( v9 )
            CrmUnregister();
          goto LABEL_22;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x509,
          (int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\core.cpp",
          (const char *)(unsigned int)v3);
        goto LABEL_12;
      }
      v6 = 1279;
    }
    else
    {
      v6 = 1270;
    }
    v3 = wil::details::in1diag3::Return_NtStatus(
           retaddr,
           (void *)v6,
           (int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\core.cpp",
           (const char *)(unsigned int)v5);
LABEL_12:
    if ( v8 )
      CrmActivityFree();
    goto LABEL_7;
  }
  v3 = wil::details::in1diag3::Return_NtStatus(
         retaddr,
         (void *)0x4EB,
         (int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\core.cpp",
         (const char *)(unsigned int)v4);
LABEL_7:
  if ( v9 )
    CrmUnregister();
LABEL_23:
  v11[0] = &CmAgentTraceProvider::WaitForSystemQuiesce::`vftable';
  wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v11);
  wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>((__int64)v11);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180020308  mov     [rsp-8+arg_8], rbx
0x18002030d  mov     [rsp-8+arg_10], rsi
0x180020312  push    rbp
0x180020313  lea     rbp, [rsp-0C0h]
0x18002031b  sub     rsp, 1C0h
0x180020322  mov     rax, cs:__security_cookie
0x180020329  xor     rax, rsp
0x18002032c  mov     [rbp+0C0h+var_10], rax
0x180020333  mov     rbx, rcx
0x180020336  lea     rdx, aWaitforsystemq; "WaitForSystemQuiesce"
0x18002033d  lea     rcx, [rsp+1C0h+var_160]
0x180020342  call    ??0?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180020347  lea     rsi, ??_7WaitForSystemQuiesce@CmAgentTraceProvider@@6B@; const CmAgentTraceProvider::WaitForSystemQuiesce::`vftable'
0x18002034e  mov     [rsp+1C0h+var_160], rsi
0x180020353  lea     rcx, [rsp+1C0h+var_160]; this
0x180020358  call    ?StartActivity@WaitForSystemQuiesce@CmAgentTraceProvider@@QEAAXXZ; CmAgentTraceProvider::WaitForSystemQuiesce::StartActivity(void)
0x18002035d  call    IsCrmRegisterPresent
0x180020362  test    al, al
0x180020364  jnz     short loc_1800203AB
0x180020366  mov     ecx, 1388h; dwMilliseconds
0x18002036b  cmp     [rbx], ecx
0x18002036d  jnb     short loc_180020394
0x18002036f  mov     rcx, [rbp+0C8h]; this
0x180020376  mov     r9d, 5B4h; char *
0x18002037c  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x180020383  mov     edx, 4E0h; void *
0x180020388  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002038d  mov     ebx, eax
0x18002038f  jmp     loc_180020546
0x180020394  call    cs:__imp_Sleep
0x18002039b  nop     dword ptr [rax+rax+00h]
0x1800203a0  add     dword ptr [rbx], 0FFFFEC78h
0x1800203a6  jmp     loc_180020538
0x1800203ab  mov     [rsp+1C0h+var_178], 0
0x1800203b4  lea     r8, aCrmclientConta; "CrmClient_ContainerManager"
0x1800203bb  mov     edx, 132h
0x1800203c0  lea     rcx, [rsp+1C0h+var_178]
0x1800203c5  call    cs:__imp_CrmRegister
0x1800203cc  nop     dword ptr [rax+rax+00h]
0x1800203d1  test    eax, eax
0x1800203d3  jns     short loc_180020411
0x1800203d5  mov     rcx, [rbp+0C8h]; this
0x1800203dc  mov     r9d, eax; char *
0x1800203df  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x1800203e6  mov     edx, 4EBh; void *
0x1800203eb  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800203f0  mov     ebx, eax
0x1800203f2  mov     rcx, [rsp+1C0h+var_178]
0x1800203f7  test    rcx, rcx
0x1800203fa  jz      loc_180020546
0x180020400  call    cs:__imp_CrmUnregister
0x180020407  nop     dword ptr [rax+rax+00h]
0x18002040c  jmp     loc_180020546
0x180020411  mov     [rsp+1C0h+Address], 0
0x180020419  mov     [rsp+1C0h+var_180], 0
0x180020422  mov     [rsp+1C0h+var_190], 0
0x18002042b  mov     [rsp+1C0h+var_198], 0
0x180020434  mov     qword ptr [rsp+1C0h+var_1A0], 0; int
0x18002043d  lea     r9, aCrmclientactiv; "CrmClientActivity_ContainerManagerCpuDi"...
0x180020444  mov     r8d, 4B1h
0x18002044a  mov     rdx, [rsp+1C0h+var_178]
0x18002044f  lea     rcx, [rsp+1C0h+var_180]
0x180020454  call    cs:__imp_CrmActivityAllocate
0x18002045b  nop     dword ptr [rax+rax+00h]
0x180020460  test    eax, eax
0x180020462  jns     short loc_1800204A0
0x180020464  mov     edx, 4F6h; void *
0x180020469  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x180020470  mov     r9d, eax; char *
0x180020473  mov     rcx, [rbp+0C8h]; this
0x18002047a  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18002047f  mov     ebx, eax
0x180020481  mov     rcx, [rsp+1C0h+var_180]
0x180020486  test    rcx, rcx
0x180020489  jz      loc_1800203F2
0x18002048f  call    cs:__imp_CrmActivityFree
0x180020496  nop     dword ptr [rax+rax+00h]
0x18002049b  jmp     loc_1800203F2
0x1800204a0  lea     r8, [rsp+1C0h+Address]
0x1800204a5  lea     rdx, Container__Manager__Agent__Core___anonymous_namespace___CrmSystemLowUsageWindowClosedReasonCallback
0x1800204ac  mov     rcx, [rsp+1C0h+var_180]
0x1800204b1  call    cs:__imp_CrmActivityWindowClosedReasonSubscribe
0x1800204b8  nop     dword ptr [rax+rax+00h]
0x1800204bd  test    eax, eax
0x1800204bf  jns     short loc_1800204C8
0x1800204c1  mov     edx, 4FFh
0x1800204c6  jmp     short loc_180020469
0x1800204c8  mov     rdx, rbx
0x1800204cb  lea     rcx, [rsp+1C0h+Address]; Address
0x1800204d0  call    ??$WaitOnEventAndUpdateTimeout@V?$slim_event_t@$00@wil@@@Details@Core@Agent@Manager@Container@@YAJAEAV?$slim_event_t@$00@wil@@AEAK@Z; Container::Manager::Agent::Core::Details::WaitOnEventAndUpdateTimeout<wil::slim_event_t<1>>(wil::slim_event_t<1> &,ulong &)
0x1800204d5  mov     ebx, eax
0x1800204d7  mov     rcx, [rsp+1C0h+var_180]
0x1800204dc  call    cs:__imp_CrmActivityWindowClosedReasonUnsubscribe
0x1800204e3  nop     dword ptr [rax+rax+00h]
0x1800204e8  test    ebx, ebx
0x1800204ea  jns     short loc_18002050C
0x1800204ec  mov     rcx, [rbp+0C8h]; this
0x1800204f3  mov     r9d, ebx; char *
0x1800204f6  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x1800204fd  mov     edx, 509h; void *
0x180020502  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020507  jmp     loc_180020481
0x18002050c  mov     rcx, [rsp+1C0h+var_180]
0x180020511  test    rcx, rcx
0x180020514  jz      short loc_180020522
0x180020516  call    cs:__imp_CrmActivityFree
0x18002051d  nop     dword ptr [rax+rax+00h]
0x180020522  mov     rcx, [rsp+1C0h+var_178]
0x180020527  test    rcx, rcx
0x18002052a  jz      short loc_180020538
0x18002052c  call    cs:__imp_CrmUnregister
0x180020533  nop     dword ptr [rax+rax+00h]
0x180020538  xor     edx, edx
0x18002053a  lea     rcx, [rsp+1C0h+var_160]
0x18002053f  call    ?Stop@?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180020544  xor     ebx, ebx
0x180020546  mov     [rsp+1C0h+var_160], rsi
0x18002054b  lea     rcx, [rsp+1C0h+var_160]
0x180020550  call    ?Destroy@?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180020555  lea     rcx, [rsp+1C0h+var_160]
0x18002055a  call    ??1?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x18002055f  mov     eax, ebx
0x180020561  mov     rcx, [rbp+0C0h+var_10]
0x180020568  xor     rcx, rsp; StackCookie
0x18002056b  call    __security_check_cookie
0x180020570  lea     r11, [rsp+1C0h+var_s0]
0x180020578  mov     rbx, [r11+18h]
0x18002057c  mov     rsi, [r11+20h]
0x180020580  mov     rsp, r11
0x180020583  pop     rbp
0x180020584  retn
```
