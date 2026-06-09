# ATL::CComObject<CAxInstaller>::`scalar deleting destructor'(uint)

- ea: `0x180008cc0`
- end: `0x180008cf4`
- name: `??_G?$CComObject@VCAxInstaller@@@ATL@@UEAAPEAXI@Z`
- size: `52`
- prototype: `CAxInstaller *__fastcall(CAxInstaller *Block, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x180001744`
- `0x180008384`
- `0x180008cc0`

## pseudocode

```c
CAxInstaller *__fastcall ATL::CComObject<CAxInstaller>::`scalar deleting destructor'(CAxInstaller *Block, char a2)
{
  ATL::CComObject<CAxInstaller>::~CComObject<CAxInstaller>(Block);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180008cc0  mov     [rsp+arg_0], rbx
0x180008cc5  push    rdi
0x180008cc6  sub     rsp, 20h
0x180008cca  mov     ebx, edx
0x180008ccc  mov     rdi, rcx
0x180008ccf  call    ??1?$CComObject@VCAxInstaller@@@ATL@@UEAA@XZ; ATL::CComObject<CAxInstaller>::~CComObject<CAxInstaller>(void)
0x180008cd4  test    bl, 1
0x180008cd7  jz      short loc_180008CE6
0x180008cd9  mov     edx, 2D0h
0x180008cde  mov     rcx, rdi; Block
0x180008ce1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180008ce6  mov     rbx, [rsp+28h+arg_0]
0x180008ceb  mov     rax, rdi
0x180008cee  add     rsp, 20h
0x180008cf2  pop     rdi
0x180008cf3  retn
```
