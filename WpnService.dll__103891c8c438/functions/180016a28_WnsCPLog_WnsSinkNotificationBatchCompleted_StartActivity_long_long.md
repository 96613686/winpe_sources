# WnsCPLog::WnsSinkNotificationBatchCompleted::StartActivity(long,long)

- ea: `0x180016a28`
- end: `0x180016b36`
- name: `?StartActivity@WnsSinkNotificationBatchCompleted@WnsCPLog@@QEAAXJJ@Z`
- size: `270`
- prototype: `void __fastcall(WnsCPLog::WnsSinkNotificationBatchCompleted *__hidden this, int, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180016990`

## callees

- `0x18000d830`
- `0x18000d8f0`
- `0x18000dba0`
- `0x18000dc40`
- `0x180016a28`
- `0x180023dc4`
- `0x180026200`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016a76`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016a76`

## pseudocode

```c
void __fastcall WnsCPLog::WnsSinkNotificationBatchCompleted::StartActivity(
        WnsCPLog::WnsSinkNotificationBatchCompleted *this,
        int a2,
        int a3)
{
  const struct _tlgProvider_t *v6; // r14
  DWORD CurrentThreadId; // eax
  __int64 v8; // r8
  const GUID *v9; // r9
  const GUID *v10; // rcx
  int v11; // [rsp+30h] [rbp-49h] BYREF
  int v12; // [rsp+34h] [rbp-45h] BYREF
  DWORD v13; // [rsp+38h] [rbp-41h] BYREF
  __int64 v14; // [rsp+40h] [rbp-39h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v15; // [rsp+50h] [rbp-29h] BYREF
  __int64 *v16; // [rsp+70h] [rbp-9h]
  __int64 v17; // [rsp+78h] [rbp-1h]
  DWORD *v18; // [rsp+80h] [rbp+7h]
  __int64 v19; // [rsp+88h] [rbp+Fh]
  int *v20; // [rsp+90h] [rbp+17h]
  __int64 v21; // [rsp+98h] [rbp+1Fh]
  int *v22; // [rsp+A0h] [rbp+27h]
  __int64 v23; // [rsp+A8h] [rbp+2Fh]

  wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v6 = WnsCPTracelogger::Provider();
  if ( *(_DWORD *)v6 > 5u )
  {
    v11 = a3;
    v12 = a2;
    CurrentThreadId = GetCurrentThreadId();
    v8 = *((_QWORD *)this + 34);
    v9 = 0;
    v13 = CurrentThreadId;
    v14 = 0;
    if ( !*(_BYTE *)(v8 + 4) || _tlgGuidIsZero((const struct _GUID *)(v8 + 24)) )
      v10 = v9;
    v23 = 4;
    v22 = &v11;
    v21 = 4;
    v20 = &v12;
    v19 = 4;
    v18 = &v13;
    v17 = 8;
    v16 = &v14;
    tlgWriteTransfer_EventWriteTransfer(
      (__int64)v6,
      (unsigned __int8 *)&dword_180042024,
      (const GUID *)(v8 + 8),
      v10,
      6u,
      &v15);
  }
  wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x180016a28  mov     [rsp-8+arg_8], rbx
0x180016a2d  mov     [rsp-8+arg_10], rsi
0x180016a32  push    rbp
0x180016a33  push    rdi
0x180016a34  push    r14
0x180016a36  lea     rbp, [rsp-47h]
0x180016a3b  sub     rsp, 0C0h
0x180016a42  mov     rax, cs:__security_cookie
0x180016a49  xor     rax, rsp
0x180016a4c  mov     [rbp+57h+var_20], rax
0x180016a50  mov     edi, r8d
0x180016a53  mov     esi, edx
0x180016a55  mov     rbx, rcx
0x180016a58  call    ?zInternalStart@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180016a5d  call    ?Provider@WnsCPTracelogger@@SAPEBU_tlgProvider_t@@XZ; WnsCPTracelogger::Provider(void)
0x180016a62  mov     r14, rax
0x180016a65  mov     ecx, [rax]
0x180016a67  cmp     ecx, 5
0x180016a6a  jbe     loc_180016B0A
0x180016a70  mov     [rbp+57h+var_A0], edi
0x180016a73  mov     [rbp+57h+var_9C], esi
0x180016a76  call    cs:__imp_GetCurrentThreadId
0x180016a7c  mov     r8, [rbx+110h]
0x180016a83  xor     r9d, r9d
0x180016a86  mov     [rbp+57h+var_98], eax
0x180016a89  mov     [rbp+57h+var_90], r9
0x180016a8d  cmp     [r8+4], r9b
0x180016a91  jz      short loc_180016AA0
0x180016a93  lea     rcx, [r8+18h]; struct _GUID *
0x180016a97  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x180016a9c  test    al, al
0x180016a9e  jz      short loc_180016AA3
0x180016aa0  mov     rcx, r9
0x180016aa3  lea     rax, [rbp+57h+var_A0]
0x180016aa7  mov     [rbp+57h+var_28], 4
0x180016aaf  mov     [rbp+57h+var_30], rax
0x180016ab3  lea     rdx, dword_180042024
0x180016aba  lea     rax, [rbp+57h+var_9C]
0x180016abe  mov     [rbp+57h+var_38], 4
0x180016ac6  mov     [rbp+57h+var_40], rax
0x180016aca  mov     r9, rcx
0x180016acd  lea     rax, [rbp+57h+var_98]
0x180016ad1  mov     [rbp+57h+var_48], 4
0x180016ad9  mov     [rbp+57h+var_50], rax
0x180016add  add     r8, 8
0x180016ae1  lea     rax, [rbp+57h+var_90]
0x180016ae5  mov     [rbp+57h+var_58], 8
0x180016aed  mov     [rbp+57h+var_60], rax
0x180016af1  mov     rcx, r14
0x180016af4  lea     rax, [rbp+57h+var_80]
0x180016af8  mov     [rsp+0D0h+var_A8], rax
0x180016afd  mov     [rsp+0D0h+var_B0], 6
0x180016b05  call    _tlgWriteTransfer_EventWriteTransfer
0x180016b0a  mov     rcx, rbx
0x180016b0d  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x180016b12  mov     rcx, [rbp+57h+var_20]
0x180016b16  xor     rcx, rsp; StackCookie
0x180016b19  call    __security_check_cookie
0x180016b1e  lea     r11, [rsp+0D0h+var_10]
0x180016b26  mov     rbx, [r11+28h]
0x180016b2a  mov     rsi, [r11+30h]
0x180016b2e  mov     rsp, r11
0x180016b31  pop     r14
0x180016b33  pop     rdi
0x180016b34  pop     rbp
0x180016b35  retn
```
