# AipCompleteRpc

- ea: `0x14002b494`
- end: `0x14002b52e`
- name: `AipCompleteRpc`
- size: `154`
- prototype: `__int64 __fastcall(int, struct _RPC_ASYNC_STATE *, void *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140003878`
- `0x14002b378`

## callees

- `0x14002b494`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14002b4bc`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002b4f8`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002b4bc`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002b4f8`
- `msrpc!RpcAsyncCompleteCall` at `0x14002b517`
- `msrpc!RpcAsyncCompleteCall` at `0x14002b517`
- `msrpc!RpcAsyncCancelCall` at `0x14002b4d4`
- `msrpc!RpcAsyncCancelCall` at `0x14002b4d4`

## pseudocode

```c
__int64 __fastcall AipCompleteRpc(int a1, struct _RPC_ASYNC_STATE *a2, void *a3)
{
  if ( a1 )
    return 3221225473LL;
  if ( KeWaitForSingleObject(a3, Executive, 0, 0, 0) )
  {
    if ( !RpcAsyncCancelCall(a2, 1) )
      KeWaitForSingleObject(a3, Executive, 0, 0, 0);
    return 3221225473LL;
  }
  return RpcAsyncCompleteCall(a2, 0) != 0 ? 0xC0000001 : 0;
}

```

## disassembly

```asm
0x14002b494  mov     [rsp+arg_0], rbx
0x14002b499  push    rdi
0x14002b49a  sub     rsp, 30h
0x14002b49e  mov     rdi, r8
0x14002b4a1  mov     rbx, rdx
0x14002b4a4  test    ecx, ecx
0x14002b4a6  jnz     short loc_14002B504
0x14002b4a8  xor     r9d, r9d; Alertable
0x14002b4ab  mov     [rsp+38h+Timeout], 0; Timeout
0x14002b4b4  xor     r8d, r8d; WaitMode
0x14002b4b7  xor     edx, edx; WaitReason
0x14002b4b9  mov     rcx, rdi; Object
0x14002b4bc  call    cs:__imp_KeWaitForSingleObject
0x14002b4c3  nop     dword ptr [rax+rax+00h]
0x14002b4c8  mov     rcx, rbx; pAsync
0x14002b4cb  test    eax, eax
0x14002b4cd  jz      short loc_14002B515
0x14002b4cf  mov     edx, 1; fAbort
0x14002b4d4  call    cs:__imp_RpcAsyncCancelCall
0x14002b4db  nop     dword ptr [rax+rax+00h]
0x14002b4e0  test    eax, eax
0x14002b4e2  jnz     short loc_14002B504
0x14002b4e4  xor     r9d, r9d; Alertable
0x14002b4e7  mov     [rsp+38h+Timeout], 0; Timeout
0x14002b4f0  xor     r8d, r8d; WaitMode
0x14002b4f3  xor     edx, edx; WaitReason
0x14002b4f5  mov     rcx, rdi; Object
0x14002b4f8  call    cs:__imp_KeWaitForSingleObject
0x14002b4ff  nop     dword ptr [rax+rax+00h]
0x14002b504  mov     eax, 0C0000001h
0x14002b509  mov     rbx, [rsp+38h+arg_0]
0x14002b50e  add     rsp, 30h
0x14002b512  pop     rdi
0x14002b513  retn
0x14002b515  xor     edx, edx; Reply
0x14002b517  call    cs:__imp_RpcAsyncCompleteCall
0x14002b51e  nop     dword ptr [rax+rax+00h]
0x14002b523  neg     eax
0x14002b525  sbb     eax, eax
0x14002b527  and     eax, 0C0000001h
0x14002b52c  jmp     short loc_14002B509
```
