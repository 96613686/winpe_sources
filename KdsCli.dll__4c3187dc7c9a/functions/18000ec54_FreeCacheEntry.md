# FreeCacheEntry

- ea: `0x18000ec54`
- end: `0x18000ec9b`
- name: `FreeCacheEntry`
- size: `71`
- prototype: `__int64 __fastcall(void *lpMem)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180003fd8`
- `0x18000eab8`

## callees

- `0x18000ec54`
- `0x180010950`

## import_xrefs

- `RPCRT4!RpcBindingFree` at `0x18000ec80`
- `RPCRT4!RpcBindingFree` at `0x18000ec80`

## pseudocode

```c
void __fastcall FreeCacheEntry(RPC_BINDING_HANDLE *lpMem)
{
  RPC_BINDING_HANDLE v2; // rcx

  if ( lpMem )
  {
    v2 = lpMem[1];
    if ( v2 )
    {
      SIDKeyProvFree(v2);
      lpMem[1] = 0;
    }
    if ( *lpMem )
    {
      RpcBindingFree(lpMem);
      *lpMem = 0;
    }
    SIDKeyProvFree(lpMem);
  }
}

```

## disassembly

```asm
0x18000ec54  test    rcx, rcx
0x18000ec57  jz      short locret_18000EC9A
0x18000ec59  push    rbx
0x18000ec5a  sub     rsp, 20h
0x18000ec5e  mov     rbx, rcx
0x18000ec61  mov     rcx, [rcx+8]; lpMem
0x18000ec65  test    rcx, rcx
0x18000ec68  jz      short loc_18000EC77
0x18000ec6a  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x18000ec6f  mov     qword ptr [rbx+8], 0
0x18000ec77  cmp     qword ptr [rbx], 0
0x18000ec7b  jz      short loc_18000EC8D
0x18000ec7d  mov     rcx, rbx; Binding
0x18000ec80  call    cs:__imp_RpcBindingFree
0x18000ec86  mov     qword ptr [rbx], 0
0x18000ec8d  mov     rcx, rbx; lpMem
0x18000ec90  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x18000ec95  add     rsp, 20h
0x18000ec99  pop     rbx
0x18000ec9a  retn
```
