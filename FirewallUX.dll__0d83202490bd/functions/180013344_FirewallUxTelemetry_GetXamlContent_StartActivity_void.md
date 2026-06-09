# FirewallUxTelemetry::GetXamlContent::StartActivity(void)

- ea: `0x180013344`
- end: `0x180013480`
- name: `?StartActivity@GetXamlContent@FirewallUxTelemetry@@QEAAXXZ`
- size: `316`
- prototype: `void __fastcall(FirewallUxTelemetry::GetXamlContent *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800123e0`

## callees

- `0x1800019dc`
- `0x1800021c0`
- `0x18000812c`
- `0x180008820`
- `0x180009fc8`
- `0x180013344`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800133b1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800133b1`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180013393`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180013393`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800133ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800133ca`

## pseudocode

```c
void __fastcall FirewallUxTelemetry::GetXamlContent::StartActivity(FirewallUxTelemetry::GetXamlContent *this)
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
    tlgWriteTransfer_EventWriteTransfer((__int64)v3, byte_180032BB2, (const GUID *)(v4 + 8), v5, 4u, &v8);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((FirewallUxTelemetry::GetXamlContent *)((char *)this + 288));
}

```

## disassembly

```asm
0x180013344  mov     [rsp-8+arg_8], rbx
0x180013349  mov     [rsp-8+arg_10], rdi
0x18001334e  push    rbp
0x18001334f  lea     rbp, [rsp-57h]
0x180013354  sub     rsp, 90h
0x18001335b  mov     rax, cs:__security_cookie
0x180013362  xor     rax, rsp
0x180013365  mov     [rbp+57h+var_10], rax
0x180013369  mov     rbx, rcx
0x18001336c  lea     rdx, [rbp+57h+SRWLock]
0x180013370  call    ?LockExclusive@?$ActivityBase@VFirewallUxTraceLoggingProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180013375  mov     rdi, [rbx+110h]
0x18001337c  call    ?Provider@FirewallUxTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; FirewallUxTraceLoggingProvider::Provider(void)
0x180013381  mov     r8d, [rax]
0x180013384  cmp     r8d, 5
0x180013388  jbe     short loc_18001339B
0x18001338a  lea     rdx, [rdi+8]; ActivityId
0x18001338e  mov     ecx, 3; ControlCode
0x180013393  call    cs:__imp_EventActivityIdControl
0x180013399  jmp     short loc_1800133A2
0x18001339b  xorps   xmm0, xmm0
0x18001339e  movups  xmmword ptr [rdi+8], xmm0
0x1800133a2  mov     dword ptr [rdi], 1
0x1800133a8  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x1800133ac  test    rcx, rcx
0x1800133af  jz      short loc_1800133B7
0x1800133b1  call    cs:__imp_ReleaseSRWLockExclusive
0x1800133b7  call    ?Provider@FirewallUxTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; FirewallUxTraceLoggingProvider::Provider(void)
0x1800133bc  mov     rdi, rax
0x1800133bf  mov     ecx, [rax]
0x1800133c1  cmp     ecx, 5
0x1800133c4  jbe     loc_18001344C
0x1800133ca  call    cs:__imp_GetCurrentThreadId
0x1800133d0  mov     dword ptr [rbp+57h+SRWLock], eax
0x1800133d3  mov     [rbp+57h+var_58], 0
0x1800133db  mov     r8, [rbx+110h]
0x1800133e2  cmp     byte ptr [r8+4], 0
0x1800133e7  jz      short loc_180013408
0x1800133e9  lea     r9, [r8+18h]
0x1800133ed  cmp     dword ptr [r9], 0
0x1800133f1  jnz     short loc_18001340B
0x1800133f3  cmp     dword ptr [r9+4], 0
0x1800133f8  jnz     short loc_18001340B
0x1800133fa  cmp     dword ptr [r9+8], 0
0x1800133ff  jnz     short loc_18001340B
0x180013401  cmp     dword ptr [r9+0Ch], 0
0x180013406  jnz     short loc_18001340B
0x180013408  xor     r9d, r9d
0x18001340b  lea     rax, [rbp+57h+SRWLock]
0x18001340f  mov     [rbp+57h+var_20], rax
0x180013413  mov     ecx, 4
0x180013418  mov     [rbp+57h+var_18], rcx
0x18001341c  lea     rax, [rbp+57h+var_58]
0x180013420  mov     [rbp+57h+var_30], rax
0x180013424  mov     [rbp+57h+var_28], 8
0x18001342c  add     r8, 8
0x180013430  lea     rax, [rbp+57h+var_50]
0x180013434  mov     [rsp+90h+var_68], rax
0x180013439  mov     [rsp+90h+var_70], ecx
0x18001343d  lea     rdx, byte_180032BB2
0x180013444  mov     rcx, rdi
0x180013447  call    _tlgWriteTransfer_EventWriteTransfer
0x18001344c  lea     rcx, [rbx+120h]; this
0x180013453  cmp     dword ptr [rcx+18h], 0
0x180013457  jnz     short loc_18001345F
0x180013459  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x18001345e  nop
0x18001345f  mov     rcx, [rbp+57h+var_10]
0x180013463  xor     rcx, rsp; StackCookie
0x180013466  call    __security_check_cookie
0x18001346b  lea     r11, [rsp+90h+var_s0]
0x180013473  mov     rbx, [r11+18h]
0x180013477  mov     rdi, [r11+20h]
0x18001347b  mov     rsp, r11
0x18001347e  pop     rbp
0x18001347f  retn
```
