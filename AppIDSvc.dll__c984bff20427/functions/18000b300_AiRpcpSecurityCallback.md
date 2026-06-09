# AiRpcpSecurityCallback

- ea: `0x18000b300`
- end: `0x18000b37a`
- name: `AiRpcpSecurityCallback`
- size: `122`
- prototype: `RPC_STATUS __fastcall(__int64, void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000b300`
- `0x18000c0a2`
- `0x18000c0e0`

## import_xrefs

- `RPCRT4!RpcServerInqCallAttributesW` at `0x18000b346`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18000b346`

## pseudocode

```c
RPC_STATUS __fastcall AiRpcpSecurityCallback(__int64 a1, void *a2)
{
  RPC_STATUS result; // eax
  _DWORD RpcCallAttributes[28]; // [rsp+20h] [rbp-88h] BYREF

  memset_0(RpcCallAttributes, 0, sizeof(RpcCallAttributes));
  RpcCallAttributes[0] = 2;
  RpcCallAttributes[1] = 32;
  result = RpcServerInqCallAttributesW(a2, RpcCallAttributes);
  if ( !result && (!RpcCallAttributes[13] || !RpcCallAttributes[15]) )
    return 5;
  return result;
}

```

## disassembly

```asm
0x18000b300  push    rbx
0x18000b302  sub     rsp, 0A0h
0x18000b309  mov     rax, cs:__security_cookie
0x18000b310  xor     rax, rsp
0x18000b313  mov     [rsp+0A8h+var_18], rax
0x18000b31b  mov     rbx, rdx
0x18000b31e  xor     edx, edx; Val
0x18000b320  lea     r8d, [rdx+70h]; Size
0x18000b324  lea     rcx, [rsp+0A8h+RpcCallAttributes]; void *
0x18000b329  call    memset_0
0x18000b32e  mov     [rsp+0A8h+RpcCallAttributes], 2
0x18000b336  mov     [rsp+0A8h+var_84], 20h ; ' '
0x18000b33e  lea     rdx, [rsp+0A8h+RpcCallAttributes]; RpcCallAttributes
0x18000b343  mov     rcx, rbx; ClientBinding
0x18000b346  call    cs:__imp_RpcServerInqCallAttributesW
0x18000b34c  test    eax, eax
0x18000b34e  jnz     short loc_18000B361
0x18000b350  cmp     [rsp+0A8h+var_54], eax
0x18000b354  jz      short loc_18000B35C
0x18000b356  cmp     [rsp+0A8h+var_4C], eax
0x18000b35a  jnz     short loc_18000B361
0x18000b35c  mov     eax, 5
0x18000b361  mov     rcx, [rsp+0A8h+var_18]
0x18000b369  xor     rcx, rsp; StackCookie
0x18000b36c  call    __security_check_cookie
0x18000b371  add     rsp, 0A0h
0x18000b378  pop     rbx
0x18000b379  retn
0x18000ca68  push    rbp
0x18000ca6a  sub     rsp, 20h
0x18000ca6e  mov     rbp, rdx
0x18000ca71  add     rsp, 20h
0x18000ca75  pop     rbp
0x18000ca76  retn
```
