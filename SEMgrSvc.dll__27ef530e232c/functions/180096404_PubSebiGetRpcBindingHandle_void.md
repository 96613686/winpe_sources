# PubSebiGetRpcBindingHandle(void * *)

- ea: `0x180096404`
- end: `0x18009648a`
- name: `?PubSebiGetRpcBindingHandle@@YAJPEAPEAX@Z`
- size: `134`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180096490`
- `0x180096774`
- `0x180096944`

## callees

- `0x180096404`

## import_xrefs

- `RPCRT4!RpcBindingFromStringBindingW` at `0x180096460`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180096460`
- `RPCRT4!RpcStringBindingComposeW` at `0x180096448`
- `RPCRT4!RpcStringBindingComposeW` at `0x180096448`
- `RPCRT4!RpcStringFreeW` at `0x18009646d`
- `RPCRT4!RpcStringFreeW` at `0x18009646d`

## string_xrefs

- `0x180096434`: `Security=Impersonation Dynamic True`

## pseudocode

```c
__int64 __fastcall PubSebiGetRpcBindingHandle(void **a1)
{
  unsigned int v1; // ebx
  RPC_WSTR StringBinding; // [rsp+40h] [rbp+8h] BYREF

  v1 = 0;
  StringBinding = 0;
  if ( !PubSebiServiceHandle )
  {
    v1 = RpcStringBindingComposeW(
           0,
           (RPC_WSTR)L"ncalrpc",
           0,
           (RPC_WSTR)L"csebpub",
           L"Security=Impersonation Dynamic True",
           &StringBinding);
    if ( !v1 )
    {
      v1 = RpcBindingFromStringBindingW(StringBinding, &PubSebiServiceHandle);
      RpcStringFreeW(&StringBinding);
    }
  }
  *a1 = PubSebiServiceHandle;
  return v1;
}

```

## disassembly

```asm
0x180096404  mov     r11, rsp
0x180096407  mov     [r11+10h], rbx
0x18009640b  push    rdi
0x18009640c  sub     rsp, 30h
0x180096410  xor     ebx, ebx
0x180096412  mov     rdi, rcx
0x180096415  cmp     cs:?PubSebiServiceHandle@@3PEAXEA, rbx; void * PubSebiServiceHandle
0x18009641c  mov     [r11+8], rbx
0x180096420  jnz     short loc_180096473
0x180096422  lea     rax, [r11+8]
0x180096426  xor     r8d, r8d; NetworkAddr
0x180096429  mov     [r11-10h], rax
0x18009642d  lea     r9, Endpoint; "csebpub"
0x180096434  lea     rax, aSecurityImpers; "Security=Impersonation Dynamic True"
0x18009643b  xor     ecx, ecx; ObjUuid
0x18009643d  lea     rdx, ProtSeq; "ncalrpc"
0x180096444  mov     [r11-18h], rax
0x180096448  call    cs:__imp_RpcStringBindingComposeW
0x18009644e  mov     ebx, eax
0x180096450  test    eax, eax
0x180096452  jnz     short loc_180096473
0x180096454  mov     rcx, [rsp+38h+StringBinding]; StringBinding
0x180096459  lea     rdx, ?PubSebiServiceHandle@@3PEAXEA; Binding
0x180096460  call    cs:__imp_RpcBindingFromStringBindingW
0x180096466  lea     rcx, [rsp+38h+StringBinding]; String
0x18009646b  mov     ebx, eax
0x18009646d  call    cs:__imp_RpcStringFreeW
0x180096473  mov     rax, cs:?PubSebiServiceHandle@@3PEAXEA; void * PubSebiServiceHandle
0x18009647a  mov     [rdi], rax
0x18009647d  mov     eax, ebx
0x18009647f  mov     rbx, [rsp+38h+arg_8]
0x180096484  add     rsp, 30h
0x180096488  pop     rdi
0x180096489  retn
```
