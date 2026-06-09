# CleanupLib(void)

- ea: `0x180016868`
- end: `0x180016926`
- name: `?CleanupLib@@YAXXZ`
- size: `190`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800114fc`

## callees

- `0x1800010d4`
- `0x18000aff4`
- `0x180016868`

## import_xrefs

- `ntdll!RtlRbRemoveNode` at `0x1800168b5`
- `ntdll!RtlRbRemoveNode` at `0x1800168b5`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001687c`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001687c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800168be`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800168d6`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800168be`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800168d6`
- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x1800168fa`
- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x1800168fa`

## pseudocode

```c
void CleanupLib(void)
{
  unsigned __int64 v0; // rbx
  _QWORD *v1; // rbx
  TRACEHANDLE v2; // rcx

  while ( 1 )
  {
    RtlAcquireSRWLockExclusive(&RpcContextTable);
    if ( (*(_BYTE *)(&xmmword_180028970 + 1) & 1) != 0 )
    {
      if ( *(&xmmword_180028970 + 1) == (struct _RTL_BALANCED_NODE *)1 )
        break;
      v0 = (unsigned __int64)*(&xmmword_180028970 + 1) ^ ((unsigned __int64)&xmmword_180028970 + 1);
    }
    else
    {
      v0 = (unsigned __int64)*(&xmmword_180028970 + 1);
    }
    if ( !v0 )
      break;
    RtlRbRemoveNode(&xmmword_180028970, v0);
    RtlReleaseSRWLockExclusive(&RpcContextTable);
    BrpRpcContextEntryDestroy(v0, 3);
  }
  RtlReleaseSRWLockExclusive(&RpcContextTable);
  v1 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    while ( v1 )
    {
      v2 = v1[1];
      if ( v2 )
      {
        UnregisterTraceGuids(v2);
        v1[1] = 0;
      }
      v1 = (_QWORD *)*v1;
    }
    WPP_GLOBAL_Control = &WPP_GLOBAL_Control;
  }
  TraceLoggingUnregister_EventUnregister();
}

```

## disassembly

```asm
0x180016868  mov     [rsp+arg_0], rbx
0x18001686d  push    rdi
0x18001686e  sub     rsp, 20h
0x180016872  lea     rdi, ?RpcContextTable@@3U_BR_RPC_CONTEXT_TABLE@@A; _BR_RPC_CONTEXT_TABLE RpcContextTable
0x180016879  mov     rcx, rdi
0x18001687c  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180016882  mov     rax, qword ptr cs:xmmword_180028970+8
0x180016889  test    al, 1
0x18001688b  jz      short loc_1800168A3
0x18001688d  cmp     rax, 1
0x180016891  jz      short loc_1800168D3
0x180016893  lea     rbx, xmmword_180028970
0x18001689a  or      rbx, 1
0x18001689e  xor     rbx, rax
0x1800168a1  jmp     short loc_1800168A6
0x1800168a3  mov     rbx, rax
0x1800168a6  test    rbx, rbx
0x1800168a9  jz      short loc_1800168D3
0x1800168ab  mov     rdx, rbx
0x1800168ae  lea     rcx, xmmword_180028970
0x1800168b5  call    cs:__imp_RtlRbRemoveNode
0x1800168bb  mov     rcx, rdi
0x1800168be  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800168c4  mov     edx, 3
0x1800168c9  mov     rcx, rbx
0x1800168cc  call    ?BrpRpcContextEntryDestroy@@YAXPEAU_BR_RPC_CONTEXT_ENTRY@@W4_BR_EVENT_CALL_REASON@@@Z; BrpRpcContextEntryDestroy(_BR_RPC_CONTEXT_ENTRY *,_BR_EVENT_CALL_REASON)
0x1800168d1  jmp     short loc_180016879
0x1800168d3  mov     rcx, rdi
0x1800168d6  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800168dc  mov     rbx, cs:WPP_GLOBAL_Control
0x1800168e3  lea     rdi, WPP_GLOBAL_Control
0x1800168ea  cmp     rbx, rdi
0x1800168ed  jz      short loc_180016917
0x1800168ef  jmp     short loc_18001690B
0x1800168f1  mov     rcx, [rbx+8]; RegistrationHandle
0x1800168f5  test    rcx, rcx
0x1800168f8  jz      short loc_180016908
0x1800168fa  call    cs:__imp_UnregisterTraceGuids
0x180016900  mov     qword ptr [rbx+8], 0
0x180016908  mov     rbx, [rbx]
0x18001690b  test    rbx, rbx
0x18001690e  jnz     short loc_1800168F1
0x180016910  mov     cs:WPP_GLOBAL_Control, rdi
0x180016917  mov     rbx, [rsp+28h+arg_0]
0x18001691c  add     rsp, 20h
0x180016920  pop     rdi
0x180016921  jmp     TraceLoggingUnregister_EventUnregister
```
