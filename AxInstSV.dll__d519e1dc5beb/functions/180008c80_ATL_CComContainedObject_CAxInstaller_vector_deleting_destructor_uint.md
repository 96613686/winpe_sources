# ATL::CComContainedObject<CAxInstaller>::`vector deleting destructor'(uint)

- ea: `0x180008c80`
- end: `0x180008cb4`
- name: `??_E?$CComContainedObject@VCAxInstaller@@@ATL@@UEAAPEAXI@Z`
- size: `52`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x180001744`
- `0x180005e18`
- `0x180008c80`

## pseudocode

```c
CAxInstaller *__fastcall ATL::CComContainedObject<CAxInstaller>::`vector deleting destructor'(
        CAxInstaller *Block,
        char a2)
{
  CAxInstaller::~CAxInstaller(Block);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180008c80  mov     [rsp+arg_0], rbx
0x180008c85  push    rdi
0x180008c86  sub     rsp, 20h
0x180008c8a  mov     ebx, edx
0x180008c8c  mov     rdi, rcx
0x180008c8f  call    ??1CAxInstaller@@UEAA@XZ; CAxInstaller::~CAxInstaller(void)
0x180008c94  test    bl, 1
0x180008c97  jz      short loc_180008CA6
0x180008c99  mov     edx, 2D0h
0x180008c9e  mov     rcx, rdi; Block
0x180008ca1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180008ca6  mov     rbx, [rsp+28h+arg_0]
0x180008cab  mov     rax, rdi
0x180008cae  add     rsp, 20h
0x180008cb2  pop     rdi
0x180008cb3  retn
```
