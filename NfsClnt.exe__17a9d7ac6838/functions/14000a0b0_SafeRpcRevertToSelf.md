# SafeRpcRevertToSelf

- ea: `0x14000a0b0`
- end: `0x14000a0f9`
- name: `SafeRpcRevertToSelf`
- size: `73`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `3`
- tags: `authz_impersonation, service_task`

## callers

- `0x140007860`
- `0x140007dd0`
- `0x140008280`
- `0x140008b50`
- `0x140009710`

## callees

- `0x140005134`
- `0x140007124`
- `0x14000a0b0`

## import_xrefs

- `RPCRT4!RpcRevertToSelf` at `0x14000a0bc`
- `RPCRT4!RpcRevertToSelf` at `0x14000a0bc`

## pseudocode

```c
__int64 SafeRpcRevertToSelf()
{
  unsigned int v0; // ebx
  NTSTATUS v1; // edx

  v0 = RpcRevertToSelf();
  if ( v0 )
  {
    ServiceStop(1);
    LOG_ERROR_EVENT_NTSTATUS((int)&EVENT_ERROR_REVERT_STOPPING, v1);
  }
  return v0;
}

```

## disassembly

```asm
0x14000a0b0  mov     [rsp+arg_0], rbx
0x14000a0b5  push    rdi
0x14000a0b6  sub     rsp, 30h
0x14000a0ba  mov     edi, edx
0x14000a0bc  call    cs:__imp_RpcRevertToSelf
0x14000a0c2  mov     ebx, eax
0x14000a0c4  test    eax, eax
0x14000a0c6  jz      short loc_14000A0EC
0x14000a0c8  mov     ecx, 1
0x14000a0cd  call    ServiceStop
0x14000a0d2  mov     r9d, edi
0x14000a0d5  mov     [rsp+38h+var_18], ebx
0x14000a0d9  lea     r8, aBaseFsRemotefs_1; "base\\fs\\remotefs\\nfs4\\client\\nfscl"...
0x14000a0e0  lea     rcx, EVENT_ERROR_REVERT_STOPPING; int
0x14000a0e7  call    LOG_ERROR_EVENT_NTSTATUS
0x14000a0ec  mov     eax, ebx
0x14000a0ee  mov     rbx, [rsp+38h+arg_0]
0x14000a0f3  add     rsp, 30h
0x14000a0f7  pop     rdi
0x14000a0f8  retn
```
