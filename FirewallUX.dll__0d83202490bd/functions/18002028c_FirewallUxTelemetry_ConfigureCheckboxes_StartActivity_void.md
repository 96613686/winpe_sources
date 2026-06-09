# FirewallUxTelemetry::ConfigureCheckboxes::StartActivity(void)

- ea: `0x18002028c`
- end: `0x1800203c8`
- name: `?StartActivity@ConfigureCheckboxes@FirewallUxTelemetry@@QEAAXXZ`
- size: `316`
- prototype: `void __fastcall(FirewallUxTelemetry::ConfigureCheckboxes *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800209d4`

## callees

- `0x1800019dc`
- `0x1800021c0`
- `0x18000812c`
- `0x180008820`
- `0x180009fc8`
- `0x18002028c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800202f9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800202f9`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800202db`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800202db`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020312`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020312`

## pseudocode

```c
void __fastcall FirewallUxTelemetry::ConfigureCheckboxes::StartActivity(FirewallUxTelemetry::ConfigureCheckboxes *this)
{
  __int64 v2; // rdi
  const struct _tlgProvider_t *v3; // rdi
  __int64 v4; // r8
  const GUID *v5; // r9
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-9h] BYREF
  __int64 v7; // [rsp+38h] [rbp-1h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v8; // [rsp+40h] [rbp+7h] BYREF
  __int64 *v9; // [rsp+60h] [rbp+27h]
  __int64 v10; // [rsp+68h] [rbp+2Fh]
  PSRWLOCK *p_SRWLock; // [rsp+70h] [rbp+37h]
  __int64 v12; // [rsp+78h] [rbp+3Fh]

  wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &SRWLock);
  v2 = *((_QWORD *)this + 34);
  if ( *(_DWORD *)FirewallUxTraceLoggingProvider::Provider() <= 5u )
    *(_OWORD *)(v2 + 8) = 0;
  else
    EventActivityIdControl(3u, (LPGUID)(v2 + 8));
  *(_DWORD *)v2 = 1;
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  v3 = FirewallUxTraceLoggingProvider::Provider();
  if ( *(_DWORD *)v3 > 5u )
  {
    LODWORD(SRWLock) = GetCurrentThreadId();
    v7 = 0;
    v4 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v4 + 4)
      || (v5 = (const GUID *)(v4 + 24), !*(_DWORD *)(v4 + 24))
      && !*(_DWORD *)(v4 + 28)
      && !*(_DWORD *)(v4 + 32)
      && !*(_DWORD *)(v4 + 36) )
    {
      v5 = 0;
    }
    p_SRWLock = &SRWLock;
    v12 = 4;
    v9 = &v7;
    v10 = 8;
    tlgWriteTransfer_EventWriteTransfer((__int64)v3, byte_1800331F1, (const GUID *)(v4 + 8), v5, 4u, &v8);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((FirewallUxTelemetry::ConfigureCheckboxes *)((char *)this + 288));
}

```

## disassembly

```asm
0x18002028c  mov     [rsp-8+arg_8], rbx
0x180020291  mov     [rsp-8+arg_10], rdi
0x180020296  push    rbp
0x180020297  lea     rbp, [rsp-57h]
0x18002029c  sub     rsp, 90h
0x1800202a3  mov     rax, cs:__security_cookie
0x1800202aa  xor     rax, rsp
0x1800202ad  mov     [rbp+57h+var_10], rax
0x1800202b1  mov     rbx, rcx
0x1800202b4  lea     rdx, [rbp+57h+SRWLock]
0x1800202b8  call    ?LockExclusive@?$ActivityBase@VFirewallUxTraceLoggingProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800202bd  mov     rdi, [rbx+110h]
0x1800202c4  call    ?Provider@FirewallUxTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; FirewallUxTraceLoggingProvider::Provider(void)
0x1800202c9  mov     r8d, [rax]
0x1800202cc  cmp     r8d, 5
0x1800202d0  jbe     short loc_1800202E3
0x1800202d2  lea     rdx, [rdi+8]; ActivityId
0x1800202d6  mov     ecx, 3; ControlCode
0x1800202db  call    cs:__imp_EventActivityIdControl
0x1800202e1  jmp     short loc_1800202EA
0x1800202e3  xorps   xmm0, xmm0
0x1800202e6  movups  xmmword ptr [rdi+8], xmm0
0x1800202ea  mov     dword ptr [rdi], 1
0x1800202f0  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x1800202f4  test    rcx, rcx
0x1800202f7  jz      short loc_1800202FF
0x1800202f9  call    cs:__imp_ReleaseSRWLockExclusive
0x1800202ff  call    ?Provider@FirewallUxTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; FirewallUxTraceLoggingProvider::Provider(void)
0x180020304  mov     rdi, rax
0x180020307  mov     ecx, [rax]
0x180020309  cmp     ecx, 5
0x18002030c  jbe     loc_180020394
0x180020312  call    cs:__imp_GetCurrentThreadId
0x180020318  mov     dword ptr [rbp+57h+SRWLock], eax
0x18002031b  mov     [rbp+57h+var_58], 0
0x180020323  mov     r8, [rbx+110h]
0x18002032a  cmp     byte ptr [r8+4], 0
0x18002032f  jz      short loc_180020350
0x180020331  lea     r9, [r8+18h]
0x180020335  cmp     dword ptr [r9], 0
0x180020339  jnz     short loc_180020353
0x18002033b  cmp     dword ptr [r9+4], 0
0x180020340  jnz     short loc_180020353
0x180020342  cmp     dword ptr [r9+8], 0
0x180020347  jnz     short loc_180020353
0x180020349  cmp     dword ptr [r9+0Ch], 0
0x18002034e  jnz     short loc_180020353
0x180020350  xor     r9d, r9d
0x180020353  lea     rax, [rbp+57h+SRWLock]
0x180020357  mov     [rbp+57h+var_20], rax
0x18002035b  mov     ecx, 4
0x180020360  mov     [rbp+57h+var_18], rcx
0x180020364  lea     rax, [rbp+57h+var_58]
0x180020368  mov     [rbp+57h+var_30], rax
0x18002036c  mov     [rbp+57h+var_28], 8
0x180020374  add     r8, 8
0x180020378  lea     rax, [rbp+57h+var_50]
0x18002037c  mov     [rsp+90h+var_68], rax
0x180020381  mov     [rsp+90h+var_70], ecx
0x180020385  lea     rdx, byte_1800331F1
0x18002038c  mov     rcx, rdi
0x18002038f  call    _tlgWriteTransfer_EventWriteTransfer
0x180020394  lea     rcx, [rbx+120h]; this
0x18002039b  cmp     dword ptr [rcx+18h], 0
0x18002039f  jnz     short loc_1800203A7
0x1800203a1  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x1800203a6  nop
0x1800203a7  mov     rcx, [rbp+57h+var_10]
0x1800203ab  xor     rcx, rsp; StackCookie
0x1800203ae  call    __security_check_cookie
0x1800203b3  lea     r11, [rsp+90h+var_s0]
0x1800203bb  mov     rbx, [r11+18h]
0x1800203bf  mov     rdi, [r11+20h]
0x1800203c3  mov     rsp, r11
0x1800203c6  pop     rbp
0x1800203c7  retn
```
