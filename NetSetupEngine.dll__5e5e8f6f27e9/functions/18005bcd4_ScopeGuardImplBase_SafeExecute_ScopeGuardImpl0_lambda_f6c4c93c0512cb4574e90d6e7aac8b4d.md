# ScopeGuardImplBase::SafeExecute_ScopeGuardImpl0__lambda_f6c4c93c0512cb4574e90d6e7aac8b4d_____

- ea: `0x18005bcd4`
- end: `0x18005bcfc`
- name: `ScopeGuardImplBase::SafeExecute_ScopeGuardImpl0__lambda_f6c4c93c0512cb4574e90d6e7aac8b4d_____`
- size: `40`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `16`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800370e0`
- `0x1800375dc`
- `0x180037858`
- `0x180037e64`
- `0x180038620`
- `0x1800388e4`
- `0x180039718`
- `0x18004f788`
- `0x18004faf0`
- `0x18004fcb8`
- `0x180050e20`
- `0x180050ffc`
- `0x1800511d8`
- `0x18005187c`
- `0x180051a58`
- `0x18005bcc8`

## callees

- `0x18005bcd4`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x18005bcee`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18005bcee`

## pseudocode

```c
RPC_STATUS __fastcall ScopeGuardImplBase::SafeExecute_ScopeGuardImpl0__lambda_f6c4c93c0512cb4574e90d6e7aac8b4d_____(
        __int64 a1)
{
  RPC_STATUS result; // eax

  if ( !*(_BYTE *)a1 )
    return RpcAsyncCompleteCall(*(PRPC_ASYNC_STATE *)(a1 + 8), *(void **)(a1 + 16));
  return result;
}

```

## disassembly

```asm
0x18005bcd4  sub     rsp, 38h
0x18005bcd8  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18005bce1  cmp     byte ptr [rcx], 0
0x18005bce4  jnz     short loc_18005BCF7
0x18005bce6  mov     rdx, [rcx+10h]; Reply
0x18005bcea  mov     rcx, [rcx+8]; pAsync
0x18005bcee  call    cs:__imp_RpcAsyncCompleteCall
0x18005bcf4  nop
0x18005bcf5  jmp     short $+2
0x18005bcf7  add     rsp, 38h
0x18005bcfb  retn
```
