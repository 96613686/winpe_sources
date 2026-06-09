# CWLIDBinding::Unbind(void)

- ea: `0x18000730c`
- end: `0x18000732e`
- name: `?Unbind@CWLIDBinding@@QEAAXXZ`
- size: `34`
- prototype: `void __fastcall(RPC_BINDING_HANDLE *this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800066d4`
- `0x180006a78`

## callees

- `0x18000730c`

## import_xrefs

- `RPCRT4!RpcBindingFree` at `0x18000731b`
- `RPCRT4!RpcBindingFree` at `0x18000731b`

## pseudocode

```c
void __fastcall CWLIDBinding::Unbind(RPC_BINDING_HANDLE *this)
{
  if ( *this )
  {
    RpcBindingFree(this);
    *this = 0;
  }
}

```

## disassembly

```asm
0x18000730c  push    rbx
0x18000730e  sub     rsp, 20h
0x180007312  cmp     qword ptr [rcx], 0
0x180007316  mov     rbx, rcx
0x180007319  jz      short loc_180007328
0x18000731b  call    cs:__imp_RpcBindingFree
0x180007321  mov     qword ptr [rbx], 0
0x180007328  add     rsp, 20h
0x18000732c  pop     rbx
0x18000732d  retn
```
