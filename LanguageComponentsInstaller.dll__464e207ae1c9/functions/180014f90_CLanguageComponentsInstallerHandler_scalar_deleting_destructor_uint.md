# CLanguageComponentsInstallerHandler::`scalar deleting destructor'(uint)

- ea: `0x180014f90`
- end: `0x180014fc4`
- name: `??_GCLanguageComponentsInstallerHandler@@UEAAPEAXI@Z`
- size: `52`
- prototype: `CLanguageComponentsInstallerHandler *__fastcall(CLanguageComponentsInstallerHandler *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180003a34`
- `0x180012dc8`
- `0x180014f90`

## pseudocode

```c
CLanguageComponentsInstallerHandler *__fastcall CLanguageComponentsInstallerHandler::`scalar deleting destructor'(
        CLanguageComponentsInstallerHandler *this,
        char a2)
{
  CWinTaskHandler::~CWinTaskHandler(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180014f90  mov     [rsp+arg_0], rbx
0x180014f95  push    rdi
0x180014f96  sub     rsp, 20h
0x180014f9a  mov     ebx, edx
0x180014f9c  mov     rdi, rcx
0x180014f9f  call    ??1CWinTaskHandler@@MEAA@XZ; CWinTaskHandler::~CWinTaskHandler(void)
0x180014fa4  test    bl, 1
0x180014fa7  jz      short loc_180014FB6
0x180014fa9  mov     edx, 128h
0x180014fae  mov     rcx, rdi; Block
0x180014fb1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180014fb6  mov     rbx, [rsp+28h+arg_0]
0x180014fbb  mov     rax, rdi
0x180014fbe  add     rsp, 20h
0x180014fc2  pop     rdi
0x180014fc3  retn
```
