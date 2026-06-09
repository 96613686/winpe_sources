# CompletePendingEprRequests

- ea: `0x1800023a8`
- end: `0x180002518`
- name: `CompletePendingEprRequests`
- size: `368`
- prototype: `RPC_STATUS __fastcall(const UUID *, __int128 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800018a0`

## callees

- `0x1800023a8`
- `0x180002520`
- `0x180002a88`
- `0x180002ae0`
- `0x180004f94`
- `0x18000a980`

## import_xrefs

- `RPCRT4!UuidToStringW` at `0x1800023f2`
- `RPCRT4!UuidToStringW` at `0x1800023f2`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800024e9`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800024e9`
- `RPCRT4!RpcStringFreeW` at `0x18000240d`
- `RPCRT4!RpcStringFreeW` at `0x18000240d`

## pseudocode

```c
RPC_STATUS __fastcall CompletePendingEprRequests(const UUID *a1, __int128 *a2)
{
  RPC_STATUS result; // eax
  __int64 v5; // r8
  __int128 v6; // xmm1
  __int64 v7; // rbx
  RPC_WSTR StringUuid; // [rsp+80h] [rbp+17h] BYREF
  __int64 v9; // [rsp+88h] [rbp+1Fh] BYREF
  UUID v10; // [rsp+90h] [rbp+27h] BYREF
  __int128 v11; // [rsp+A0h] [rbp+37h]

  v9 = 0;
  StringUuid = 0;
  v10 = 0;
  v11 = 0;
  result = UuidToStringW(a1, &StringUuid);
  if ( !result )
  {
    if ( (Microsoft_Windows_ServiceTriggerPerfEventProviderEnableBits & 1) != 0 )
      McTemplateU0zz_EtwEventWriteTransfer(
        SERVICE_TRIGGER_PERF_EVENT_GUID_Context,
        ServiceTriggerPerfServiceArrived,
        v5,
        StringUuid);
    result = RpcStringFreeW(&StringUuid);
  }
  v6 = *a2;
  v10 = *a1;
  v11 = v6;
  while ( !g_TriggersDisabled )
  {
    result = NtrbDequeueRequest(&v10, &v9);
    if ( result )
      break;
    v7 = v9;
    **(_DWORD **)(v7 + 96) = GetEntries(
                               v9 + 24,
                               v9 + 8,
                               *(_DWORD *)(v9 + 56),
                               *(_QWORD *)(v9 + 64),
                               *(void **)(v9 + 48),
                               *(__int64 **)(v9 + 88),
                               *(_QWORD *)(v9 + 80),
                               8 * *(_DWORD *)(v9 + 40),
                               2u,
                               *(_DWORD *)(v9 + 40),
                               *(unsigned int **)(v9 + 72),
                               0,
                               0,
                               (unsigned int (__fastcall *)(__int64 *, __int64, __int64, _QWORD, int, int))WildCardMatch,
                               0);
    RpcAsyncCompleteCall(*(PRPC_ASYNC_STATE *)v7, 0);
    result = BufferedRequestCleanup((_QWORD *)v7);
  }
  return result;
}

```

## disassembly

```asm
0x1800023a8  mov     [rsp-8+arg_10], rbx
0x1800023ad  mov     [rsp-8+arg_18], rdi
0x1800023b2  push    rbp
0x1800023b3  lea     rbp, [rsp-57h]
0x1800023b8  sub     rsp, 0C0h
0x1800023bf  mov     rax, cs:__security_cookie
0x1800023c6  xor     rax, rsp
0x1800023c9  mov     [rbp+57h+var_10], rax
0x1800023cd  xorps   xmm0, xmm0
0x1800023d0  mov     [rbp+57h+var_38], 0
0x1800023d8  mov     rdi, rdx
0x1800023db  mov     [rbp+57h+StringUuid], 0
0x1800023e3  lea     rdx, [rbp+57h+StringUuid]; StringUuid
0x1800023e7  mov     rbx, rcx
0x1800023ea  movups  [rbp+57h+var_30], xmm0
0x1800023ee  movups  [rbp+57h+var_20], xmm0
0x1800023f2  call    cs:__imp_UuidToStringW
0x1800023f8  test    eax, eax
0x1800023fa  jnz     short loc_180002413
0x1800023fc  test    cs:Microsoft_Windows_ServiceTriggerPerfEventProviderEnableBits, 1
0x180002403  jnz     loc_1800024FC
0x180002409  lea     rcx, [rbp+57h+StringUuid]; String
0x18000240d  call    cs:__imp_RpcStringFreeW
0x180002413  movups  xmm0, xmmword ptr [rbx]
0x180002416  movups  xmm1, xmmword ptr [rdi]
0x180002419  movdqu  [rbp+57h+var_30], xmm0
0x18000241e  movdqu  [rbp+57h+var_20], xmm1
0x180002423  cmp     cs:g_TriggersDisabled, 0
0x18000242a  jnz     short loc_18000243D
0x18000242c  lea     rdx, [rbp+57h+var_38]
0x180002430  lea     rcx, [rbp+57h+var_30]
0x180002434  call    NtrbDequeueRequest
0x180002439  test    eax, eax
0x18000243b  jz      short loc_18000245E
0x18000243d  mov     rcx, [rbp+57h+var_10]
0x180002441  xor     rcx, rsp; StackCookie
0x180002444  call    __security_check_cookie
0x180002449  lea     r11, [rsp+0C0h+var_s0]
0x180002451  mov     rbx, [r11+20h]
0x180002455  mov     rdi, [r11+28h]
0x180002459  mov     rsp, r11
0x18000245c  pop     rbp
0x18000245d  retn
0x18000245e  mov     rbx, [rbp+57h+var_38]
0x180002462  lea     rax, WildCardMatch
0x180002469  mov     [rsp+0C0h+var_50], 0
0x180002472  mov     [rsp+0C0h+var_58], rax
0x180002477  mov     [rsp+0C0h+var_60], 0
0x18000247f  mov     r8d, [rbx+28h]
0x180002483  lea     rdx, [rbx+8]
0x180002487  mov     rax, [rbx+48h]
0x18000248b  lea     rcx, [rbx+18h]
0x18000248f  mov     [rsp+0C0h+var_68], 0
0x180002497  mov     [rsp+0C0h+var_70], rax
0x18000249c  mov     rax, [rbx+50h]
0x1800024a0  lea     r9d, ds:0[r8*8]
0x1800024a8  mov     [rsp+0C0h+var_78], r8d
0x1800024ad  mov     r8d, [rbx+38h]
0x1800024b1  mov     [rsp+0C0h+var_80], 2
0x1800024b9  mov     [rsp+0C0h+var_88], r9d
0x1800024be  mov     r9, [rbx+40h]
0x1800024c2  mov     [rsp+0C0h+var_90], rax
0x1800024c7  mov     rax, [rbx+58h]
0x1800024cb  mov     [rsp+0C0h+var_98], rax
0x1800024d0  mov     rax, [rbx+30h]
0x1800024d4  mov     [rsp+0C0h+var_A0], rax
0x1800024d9  call    GetEntries
0x1800024de  mov     rdx, [rbx+60h]
0x1800024e2  mov     [rdx], eax
0x1800024e4  xor     edx, edx; Reply
0x1800024e6  mov     rcx, [rbx]; pAsync
0x1800024e9  call    cs:__imp_RpcAsyncCompleteCall
0x1800024ef  mov     rcx, rbx
0x1800024f2  call    BufferedRequestCleanup
0x1800024f7  jmp     loc_180002423
0x1800024fc  mov     r9, [rbp+57h+StringUuid]
0x180002500  lea     rdx, ServiceTriggerPerfServiceArrived
0x180002507  lea     rcx, SERVICE_TRIGGER_PERF_EVENT_GUID_Context
0x18000250e  call    McTemplateU0zz_EtwEventWriteTransfer
0x180002513  jmp     loc_180002409
```
