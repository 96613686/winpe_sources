# BrpRpcContextFindAndRemove(unsigned __int64,uchar)

- ea: `0x180069520`
- end: `0x18006958e`
- name: `?BrpRpcContextFindAndRemove@@YAPEAU_BR_RPC_CONTEXT_ENTRY@@_KE@Z`
- size: `110`
- prototype: `struct _BR_RPC_CONTEXT_ENTRY *__fastcall(unsigned __int64, unsigned __int8)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18003c580`
- `0x18003cb80`

## callees

- `0x1800691a0`
- `0x180069520`
- `0x180069594`

## import_xrefs

- `ntdll!RtlReleaseSRWLockExclusive` at `0x18006957a`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18006957a`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180069537`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180069537`
- `ntdll!RtlRbRemoveNode` at `0x18006956d`
- `ntdll!RtlRbRemoveNode` at `0x18006956d`

## pseudocode

```c
struct _BR_RPC_CONTEXT_ENTRY *__fastcall BrpRpcContextFindAndRemove(unsigned __int64 a1, char a2)
{
  struct _BR_RPC_CONTEXT_ENTRY *v4; // rax
  struct _BR_RPC_CONTEXT_ENTRY *v5; // rbx

  RtlAcquireSRWLockExclusive(&RpcContextTable);
  v4 = BrpRpcContextFindWithLockHeld(a1);
  v5 = v4;
  if ( v4 )
  {
    if ( a2 && BrpRpcClientProcessHandleCheck(*((HANDLE *)v4 + 4)) )
      v5 = 0;
    else
      RtlRbRemoveNode(&xmmword_18008D488, v5);
  }
  RtlReleaseSRWLockExclusive(&RpcContextTable);
  return v5;
}

```

## disassembly

```asm
0x180069520  mov     [rsp+arg_0], rbx
0x180069525  push    rdi
0x180069526  sub     rsp, 20h
0x18006952a  mov     rbx, rcx
0x18006952d  mov     dil, dl
0x180069530  lea     rcx, ?RpcContextTable@@3U_BR_RPC_CONTEXT_TABLE@@A; _BR_RPC_CONTEXT_TABLE RpcContextTable
0x180069537  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18006953d  mov     rcx, rbx; unsigned __int64
0x180069540  call    ?BrpRpcContextFindWithLockHeld@@YAPEAU_BR_RPC_CONTEXT_ENTRY@@_K@Z; BrpRpcContextFindWithLockHeld(unsigned __int64)
0x180069545  mov     rbx, rax
0x180069548  test    rax, rax
0x18006954b  jz      short loc_180069573
0x18006954d  test    dil, dil
0x180069550  jz      short loc_180069563
0x180069552  mov     rcx, [rax+20h]; ProcessHandle
0x180069556  call    ?BrpRpcClientProcessHandleCheck@@YAKPEAX@Z; BrpRpcClientProcessHandleCheck(void *)
0x18006955b  test    eax, eax
0x18006955d  jz      short loc_180069563
0x18006955f  xor     ebx, ebx
0x180069561  jmp     short loc_180069573
0x180069563  mov     rdx, rbx
0x180069566  lea     rcx, xmmword_18008D488
0x18006956d  call    cs:__imp_RtlRbRemoveNode
0x180069573  lea     rcx, ?RpcContextTable@@3U_BR_RPC_CONTEXT_TABLE@@A; _BR_RPC_CONTEXT_TABLE RpcContextTable
0x18006957a  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180069580  mov     rax, rbx
0x180069583  mov     rbx, [rsp+28h+arg_0]
0x180069588  add     rsp, 20h
0x18006958c  pop     rdi
0x18006958d  retn
```
