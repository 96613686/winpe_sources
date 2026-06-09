# CSmsBrokerHandler::Uninitialize(void)

- ea: `0x18003bc3c`
- end: `0x18003bd3b`
- name: `?Uninitialize@CSmsBrokerHandler@@QEAAJXZ`
- size: `255`
- prototype: `__int64 __fastcall(CSmsBrokerHandler *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001771c`
- `0x18006ec60`

## callees

- `0x180003a60`
- `0x18000cf90`
- `0x18003bc3c`
- `0x1800693e4`
- `0x18006f010`

## import_xrefs

- `ntdll!RtlReleaseSRWLockExclusive` at `0x18003bca5`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18003bcc1`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18003bca5`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18003bcc1`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18003bc5f`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18003bc5f`
- `ntdll!RtlRbRemoveNode` at `0x18003bc98`
- `ntdll!RtlRbRemoveNode` at `0x18003bc98`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSmsBrokerHandler::Uninitialize(CSmsBrokerHandler *this)
{
  unsigned __int64 v2; // rbx
  __int64 v3; // rcx
  __int64 v4; // r8
  struct _EVENT_DATA_DESCRIPTOR v6; // [rsp+30h] [rbp-28h] BYREF

  while ( 1 )
  {
    RtlAcquireSRWLockExclusive(&RpcContextTable);
    if ( (*(_BYTE *)(&xmmword_18008D488 + 1) & 1) != 0 )
    {
      if ( *(&xmmword_18008D488 + 1) == (struct _RTL_BALANCED_NODE *)1 )
        break;
      v2 = (unsigned __int64)*(&xmmword_18008D488 + 1) ^ ((unsigned __int64)&xmmword_18008D488 + 1);
    }
    else
    {
      v2 = (unsigned __int64)*(&xmmword_18008D488 + 1);
    }
    if ( !v2 )
      break;
    RtlRbRemoveNode(&xmmword_18008D488, v2);
    RtlReleaseSRWLockExclusive(&RpcContextTable);
    BrpRpcContextEntryDestroy(v2, 3);
  }
  RtlReleaseSRWLockExclusive(&RpcContextTable);
  (**((void (__fastcall ***)(char *))this + 2))((char *)this + 16);
  if ( *(_DWORD *)this )
  {
    if ( (Microsoft_Windows_CoreSystem_SmsRouterEnableBits & 1) != 0 )
      McGenEventWrite_EventWriteTransfer(v3, (const EVENT_DESCRIPTOR *)SmsBroker_Stop, v4, 1u, &v6);
    *(_DWORD *)this = 0;
    *((_QWORD *)this + 1) = 0;
  }
  (*(void (__fastcall **)(char *))(*((_QWORD *)this + 2) + 8LL))((char *)this + 16);
  return 0;
}

```

## disassembly

```asm
0x18003bc3c  mov     [rsp+arg_8], rbx
0x18003bc41  push    rdi
0x18003bc42  sub     rsp, 50h
0x18003bc46  mov     rax, cs:__security_cookie
0x18003bc4d  xor     rax, rsp
0x18003bc50  mov     [rsp+58h+var_18], rax
0x18003bc55  mov     rdi, rcx
0x18003bc58  lea     rcx, ?RpcContextTable@@3U_BR_RPC_CONTEXT_TABLE@@A; _BR_RPC_CONTEXT_TABLE RpcContextTable
0x18003bc5f  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18003bc65  mov     rax, qword ptr cs:xmmword_18008D488+8
0x18003bc6c  test    al, 1
0x18003bc6e  jz      short loc_18003BC86
0x18003bc70  cmp     rax, 1
0x18003bc74  jz      short loc_18003BCBA
0x18003bc76  lea     rbx, xmmword_18008D488
0x18003bc7d  or      rbx, 1
0x18003bc81  xor     rbx, rax
0x18003bc84  jmp     short loc_18003BC89
0x18003bc86  mov     rbx, rax
0x18003bc89  test    rbx, rbx
0x18003bc8c  jz      short loc_18003BCBA
0x18003bc8e  mov     rdx, rbx
0x18003bc91  lea     rcx, xmmword_18008D488
0x18003bc98  call    cs:__imp_RtlRbRemoveNode
0x18003bc9e  lea     rcx, ?RpcContextTable@@3U_BR_RPC_CONTEXT_TABLE@@A; _BR_RPC_CONTEXT_TABLE RpcContextTable
0x18003bca5  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18003bcab  mov     edx, 3
0x18003bcb0  mov     rcx, rbx
0x18003bcb3  call    ?BrpRpcContextEntryDestroy@@YAXPEAU_BR_RPC_CONTEXT_ENTRY@@W4_BR_EVENT_CALL_REASON@@@Z; BrpRpcContextEntryDestroy(_BR_RPC_CONTEXT_ENTRY *,_BR_EVENT_CALL_REASON)
0x18003bcb8  jmp     short loc_18003BC58
0x18003bcba  lea     rcx, ?RpcContextTable@@3U_BR_RPC_CONTEXT_TABLE@@A; _BR_RPC_CONTEXT_TABLE RpcContextTable
0x18003bcc1  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18003bcc7  lea     rbx, [rdi+10h]
0x18003bccb  mov     rax, [rbx]
0x18003bcce  mov     rcx, rbx
0x18003bcd1  mov     rax, [rax]
0x18003bcd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bcd9  cmp     dword ptr [rdi], 0
0x18003bcdc  jz      short loc_18003BD11
0x18003bcde  test    cs:Microsoft_Windows_CoreSystem_SmsRouterEnableBits, 1
0x18003bce5  jz      short loc_18003BD03
0x18003bce7  lea     rax, [rsp+58h+var_28]
0x18003bcec  mov     [rsp+58h+var_38], rax
0x18003bcf1  mov     r9d, 1
0x18003bcf7  lea     rdx, SmsBroker_Stop
0x18003bcfe  call    McGenEventWrite_EventWriteTransfer
0x18003bd03  mov     dword ptr [rdi], 0
0x18003bd09  mov     qword ptr [rdi+8], 0
0x18003bd11  mov     rax, [rbx]
0x18003bd14  mov     rcx, rbx
0x18003bd17  mov     rax, [rax+8]
0x18003bd1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bd20  nop
0x18003bd21  xor     eax, eax
0x18003bd23  mov     rcx, [rsp+58h+var_18]
0x18003bd28  xor     rcx, rsp; StackCookie
0x18003bd2b  call    __security_check_cookie
0x18003bd30  mov     rbx, [rsp+58h+arg_8]
0x18003bd35  add     rsp, 50h
0x18003bd39  pop     rdi
0x18003bd3a  retn
```
