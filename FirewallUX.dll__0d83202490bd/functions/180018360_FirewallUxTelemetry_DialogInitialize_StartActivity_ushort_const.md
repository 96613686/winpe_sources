# FirewallUxTelemetry::DialogInitialize::StartActivity(ushort const *)

- ea: `0x180018360`
- end: `0x1800184d4`
- name: `?StartActivity@DialogInitialize@FirewallUxTelemetry@@QEAAXPEBG@Z`
- size: `372`
- prototype: `void __fastcall(FirewallUxTelemetry::DialogInitialize *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x18001815c`
- `0x18001fd60`

## callees

- `0x1800019dc`
- `0x1800021c0`
- `0x18000812c`
- `0x180008820`
- `0x180009fc8`
- `0x180018360`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800183d6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800183d6`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800183b5`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800183b5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800183ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800183ef`

## pseudocode

```c
void __fastcall FirewallUxTelemetry::DialogInitialize::StartActivity(
        FirewallUxTelemetry::DialogInitialize *this,
        const unsigned __int16 *a2)
{
  __int64 v4; // rsi
  RTL_SRWLOCK *v5; // rcx
  const struct _tlgProvider_t *v6; // rsi
  DWORD CurrentThreadId; // eax
  __int64 v8; // r8
  const GUID *v9; // r9
  __int64 v10; // rax
  int v11; // eax
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-29h] BYREF
  __int64 v13; // [rsp+38h] [rbp-21h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v14; // [rsp+40h] [rbp-19h] BYREF
  __int64 *v15; // [rsp+60h] [rbp+7h]
  __int64 v16; // [rsp+68h] [rbp+Fh]
  PSRWLOCK *p_SRWLock; // [rsp+70h] [rbp+17h]
  __int64 v18; // [rsp+78h] [rbp+1Fh]
  const unsigned __int16 *v19; // [rsp+80h] [rbp+27h]
  int v20; // [rsp+88h] [rbp+2Fh]
  int v21; // [rsp+8Ch] [rbp+33h]

  wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &SRWLock);
  v4 = *((_QWORD *)this + 34);
  if ( *(_DWORD *)FirewallUxTraceLoggingProvider::Provider() <= 5u )
    *(_OWORD *)(v4 + 8) = 0;
  else
    EventActivityIdControl(3u, (LPGUID)(v4 + 8));
  v5 = SRWLock;
  *(_DWORD *)v4 = 1;
  if ( v5 )
    ReleaseSRWLockExclusive(v5);
  v6 = FirewallUxTraceLoggingProvider::Provider();
  if ( *(_DWORD *)v6 > 5u )
  {
    CurrentThreadId = GetCurrentThreadId();
    v8 = *((_QWORD *)this + 34);
    LODWORD(SRWLock) = CurrentThreadId;
    v13 = 0;
    if ( !*(_BYTE *)(v8 + 4)
      || (v9 = (const GUID *)(v8 + 24), !*(_DWORD *)(v8 + 24))
      && !*(_DWORD *)(v8 + 28)
      && !*(_DWORD *)(v8 + 32)
      && !*(_DWORD *)(v8 + 36) )
    {
      v9 = 0;
    }
    if ( a2 )
    {
      v10 = -1;
      do
        ++v10;
      while ( a2[v10] );
      v11 = 2 * v10 + 2;
    }
    else
    {
      a2 = &szFile;
      v11 = 2;
    }
    v20 = v11;
    v19 = a2;
    p_SRWLock = &SRWLock;
    v21 = 0;
    v15 = &v13;
    v18 = 4;
    v16 = 8;
    tlgWriteTransfer_EventWriteTransfer((__int64)v6, byte_180032F3F, (const GUID *)(v8 + 8), v9, 5u, &v14);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((FirewallUxTelemetry::DialogInitialize *)((char *)this + 288));
}

```

## disassembly

```asm
0x180018360  mov     [rsp-8+arg_8], rbx
0x180018365  mov     [rsp-8+arg_10], rsi
0x18001836a  push    rbp
0x18001836b  push    rdi
0x18001836c  push    r14
0x18001836e  lea     rbp, [rsp-47h]
0x180018373  sub     rsp, 0A0h
0x18001837a  mov     rax, cs:__security_cookie
0x180018381  xor     rax, rsp
0x180018384  mov     [rbp+57h+var_20], rax
0x180018388  mov     rbx, rdx
0x18001838b  mov     rdi, rcx
0x18001838e  lea     rdx, [rbp+57h+SRWLock]
0x180018392  call    ?LockExclusive@?$ActivityBase@VFirewallUxTraceLoggingProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<FirewallUxTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180018397  mov     rsi, [rdi+110h]
0x18001839e  call    ?Provider@FirewallUxTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; FirewallUxTraceLoggingProvider::Provider(void)
0x1800183a3  mov     r8d, [rax]
0x1800183a6  cmp     r8d, 5
0x1800183aa  jbe     short loc_1800183BD
0x1800183ac  lea     rdx, [rsi+8]; ActivityId
0x1800183b0  mov     ecx, 3; ControlCode
0x1800183b5  call    cs:__imp_EventActivityIdControl
0x1800183bb  jmp     short loc_1800183C4
0x1800183bd  xorps   xmm0, xmm0
0x1800183c0  movups  xmmword ptr [rsi+8], xmm0
0x1800183c4  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x1800183c8  xor     r14d, r14d
0x1800183cb  mov     dword ptr [rsi], 1
0x1800183d1  test    rcx, rcx
0x1800183d4  jz      short loc_1800183DC
0x1800183d6  call    cs:__imp_ReleaseSRWLockExclusive
0x1800183dc  call    ?Provider@FirewallUxTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; FirewallUxTraceLoggingProvider::Provider(void)
0x1800183e1  mov     rsi, rax
0x1800183e4  mov     ecx, [rax]
0x1800183e6  cmp     ecx, 5
0x1800183e9  jbe     loc_18001849E
0x1800183ef  call    cs:__imp_GetCurrentThreadId
0x1800183f5  mov     r8, [rdi+110h]
0x1800183fc  mov     dword ptr [rbp+57h+SRWLock], eax
0x1800183ff  mov     [rbp+57h+var_78], r14
0x180018403  cmp     [r8+4], r14b
0x180018407  jz      short loc_180018424
0x180018409  lea     r9, [r8+18h]
0x18001840d  cmp     [r9], r14d
0x180018410  jnz     short loc_180018427
0x180018412  cmp     [r9+4], r14d
0x180018416  jnz     short loc_180018427
0x180018418  cmp     [r9+8], r14d
0x18001841c  jnz     short loc_180018427
0x18001841e  cmp     [r9+0Ch], r14d
0x180018422  jnz     short loc_180018427
0x180018424  mov     r9, r14
0x180018427  test    rbx, rbx
0x18001842a  jz      short loc_180018443
0x18001842c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180018430  inc     rax
0x180018433  cmp     [rbx+rax*2], r14w
0x180018438  jnz     short loc_180018430
0x18001843a  lea     eax, ds:2[rax*2]
0x180018441  jmp     short loc_18001844F
0x180018443  lea     rbx, szFile
0x18001844a  mov     eax, 2
0x18001844f  mov     [rbp+57h+var_28], eax
0x180018452  lea     rdx, byte_180032F3F
0x180018459  lea     rax, [rbp+57h+SRWLock]
0x18001845d  mov     [rbp+57h+var_30], rbx
0x180018461  mov     [rbp+57h+var_40], rax
0x180018465  add     r8, 8
0x180018469  lea     rax, [rbp+57h+var_78]
0x18001846d  mov     [rbp+57h+var_24], r14d
0x180018471  mov     [rbp+57h+var_50], rax
0x180018475  mov     rcx, rsi
0x180018478  lea     rax, [rbp+57h+var_70]
0x18001847c  mov     [rbp+57h+var_38], 4
0x180018484  mov     [rsp+0B0h+var_88], rax
0x180018489  mov     [rsp+0B0h+var_90], 5
0x180018491  mov     [rbp+57h+var_48], 8
0x180018499  call    _tlgWriteTransfer_EventWriteTransfer
0x18001849e  lea     rcx, [rdi+120h]; this
0x1800184a5  cmp     [rcx+18h], r14d
0x1800184a9  jnz     short loc_1800184B0
0x1800184ab  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x1800184b0  mov     rcx, [rbp+57h+var_20]
0x1800184b4  xor     rcx, rsp; StackCookie
0x1800184b7  call    __security_check_cookie
0x1800184bc  lea     r11, [rsp+0B0h+var_10]
0x1800184c4  mov     rbx, [r11+28h]
0x1800184c8  mov     rsi, [r11+30h]
0x1800184cc  mov     rsp, r11
0x1800184cf  pop     r14
0x1800184d1  pop     rdi
0x1800184d2  pop     rbp
0x1800184d3  retn
```
