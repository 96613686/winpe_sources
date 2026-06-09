# PrinterCleanupTask::`vector deleting destructor'(uint)

- ea: `0x1800039d0`
- end: `0x180003a04`
- name: `??_EPrinterCleanupTask@@UEAAPEAXI@Z`
- size: `52`
- prototype: `PrinterCleanupTask *__fastcall(PrinterCleanupTask *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting, service_task`

## callees

- `0x180002434`
- `0x18000385c`
- `0x1800039d0`

## pseudocode

```c
PrinterCleanupTask *__fastcall PrinterCleanupTask::`vector deleting destructor'(PrinterCleanupTask *this, char a2)
{
  CWinTaskHandler::~CWinTaskHandler(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1800039d0  mov     [rsp+arg_0], rbx
0x1800039d5  push    rdi
0x1800039d6  sub     rsp, 20h
0x1800039da  mov     ebx, edx
0x1800039dc  mov     rdi, rcx
0x1800039df  call    ??1CWinTaskHandler@@MEAA@XZ; CWinTaskHandler::~CWinTaskHandler(void)
0x1800039e4  test    bl, 1
0x1800039e7  jz      short loc_1800039F6
0x1800039e9  mov     edx, 38h ; '8'; unsigned __int64
0x1800039ee  mov     rcx, rdi; void *
0x1800039f1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800039f6  mov     rbx, [rsp+28h+arg_0]
0x1800039fb  mov     rax, rdi
0x1800039fe  add     rsp, 20h
0x180003a02  pop     rdi
0x180003a03  retn
```
