# Comms::RpcClient::Binders::~Binders(void)

- ea: `0x180003224`
- end: `0x180003251`
- name: `??1Binders@RpcClient@Comms@@QEAA@XZ`
- size: `45`
- prototype: `void __fastcall(RPC_WSTR *String)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800031bc`
- `0x180003330`
- `0x1800035f8`

## callees

- `0x180003224`

## import_xrefs

- `RPCRT4!RpcStringFreeW` at `0x180003245`
- `RPCRT4!RpcStringFreeW` at `0x180003245`
- `RPCRT4!RpcBindingFree` at `0x180003236`
- `RPCRT4!RpcBindingFree` at `0x180003236`

## pseudocode

```c
void __fastcall Comms::RpcClient::Binders::~Binders(RPC_WSTR *String)
{
  RPC_BINDING_HANDLE *v2; // rcx

  v2 = (RPC_BINDING_HANDLE *)String[1];
  if ( v2 )
    RpcBindingFree(v2);
  if ( *String )
    RpcStringFreeW(String);
}

```

## disassembly

```asm
0x180003224  push    rbx
0x180003226  sub     rsp, 20h
0x18000322a  mov     rbx, rcx
0x18000322d  mov     rcx, [rcx+8]; Binding
0x180003231  test    rcx, rcx
0x180003234  jz      short loc_18000323C
0x180003236  call    cs:__imp_RpcBindingFree
0x18000323c  cmp     qword ptr [rbx], 0
0x180003240  jz      short loc_18000324B
0x180003242  mov     rcx, rbx; String
0x180003245  call    cs:__imp_RpcStringFreeW
0x18000324b  add     rsp, 20h
0x18000324f  pop     rbx
0x180003250  retn
```
