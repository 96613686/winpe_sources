# ATL::CComAggObject<CAxInstaller>::`scalar deleting destructor'(uint)

- ea: `0x180008c40`
- end: `0x180008c74`
- name: `??_G?$CComAggObject@VCAxInstaller@@@ATL@@UEAAPEAXI@Z`
- size: `52`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x180001744`
- `0x180008340`
- `0x180008c40`

## pseudocode

```c
void *__fastcall ATL::CComAggObject<CAxInstaller>::`scalar deleting destructor'(void *Block, char a2)
{
  ATL::CComAggObject<CAxInstaller>::~CComAggObject<CAxInstaller>((__int64)Block);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180008c40  mov     [rsp+arg_0], rbx
0x180008c45  push    rdi
0x180008c46  sub     rsp, 20h
0x180008c4a  mov     ebx, edx
0x180008c4c  mov     rdi, rcx
0x180008c4f  call    ??1?$CComAggObject@VCAxInstaller@@@ATL@@UEAA@XZ; ATL::CComAggObject<CAxInstaller>::~CComAggObject<CAxInstaller>(void)
0x180008c54  test    bl, 1
0x180008c57  jz      short loc_180008C66
0x180008c59  mov     edx, 2E8h
0x180008c5e  mov     rcx, rdi; Block
0x180008c61  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180008c66  mov     rbx, [rsp+28h+arg_0]
0x180008c6b  mov     rax, rdi
0x180008c6e  add     rsp, 20h
0x180008c72  pop     rdi
0x180008c73  retn
```
