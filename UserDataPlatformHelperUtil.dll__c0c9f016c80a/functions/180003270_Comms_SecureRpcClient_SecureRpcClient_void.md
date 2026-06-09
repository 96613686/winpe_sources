# Comms::SecureRpcClient::~SecureRpcClient(void)

- ea: `0x180003270`
- end: `0x18000329c`
- name: `??1SecureRpcClient@Comms@@UEAA@XZ`
- size: `44`
- prototype: `void __fastcall(Comms::SecureRpcClient *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800032b0`

## callees

- `0x180003270`

## import_xrefs

- `RPCRT4!RpcBindingFree` at `0x180003291`
- `RPCRT4!RpcBindingFree` at `0x180003291`

## pseudocode

```c
void __fastcall Comms::SecureRpcClient::~SecureRpcClient(Comms::SecureRpcClient *this)
{
  RPC_BINDING_HANDLE Binding; // [rsp+30h] [rbp+8h] BYREF

  *(_QWORD *)this = &Comms::SecureRpcClient::`vftable';
  if ( *((_QWORD *)this + 1) )
  {
    Binding = (RPC_BINDING_HANDLE)*((_QWORD *)this + 1);
    RpcBindingFree(&Binding);
  }
}

```

## disassembly

```asm
0x180003270  sub     rsp, 28h
0x180003274  lea     rax, ??_7SecureRpcClient@Comms@@6B@; const Comms::SecureRpcClient::`vftable'
0x18000327b  mov     [rcx], rax
0x18000327e  mov     rax, [rcx+8]
0x180003282  test    rax, rax
0x180003285  jz      short loc_180003297
0x180003287  lea     rcx, [rsp+28h+Binding]; Binding
0x18000328c  mov     [rsp+28h+Binding], rax
0x180003291  call    cs:__imp_RpcBindingFree
0x180003297  add     rsp, 28h
0x18000329b  retn
```
