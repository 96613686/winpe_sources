# PrinterCleanupTaskNotificationActivator::`vector deleting destructor'(uint)

- ea: `0x180006b50`
- end: `0x180006b78`
- name: `??_EPrinterCleanupTaskNotificationActivator@@UEAAPEAXI@Z`
- size: `40`
- prototype: `PrinterCleanupTaskNotificationActivator *__fastcall(PrinterCleanupTaskNotificationActivator *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, service_task`

## callees

- `0x180002434`
- `0x180006b50`

## pseudocode

```c
PrinterCleanupTaskNotificationActivator *__fastcall PrinterCleanupTaskNotificationActivator::`vector deleting destructor'(
        PrinterCleanupTaskNotificationActivator *this,
        char a2)
{
  *((_DWORD *)this + 3) = -1073741823;
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180006b50  push    rbx
0x180006b52  sub     rsp, 20h
0x180006b56  mov     dword ptr [rcx+0Ch], 0C0000001h
0x180006b5d  mov     rbx, rcx
0x180006b60  test    dl, 1
0x180006b63  jz      short loc_180006B6F
0x180006b65  mov     edx, 10h; unsigned __int64
0x180006b6a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180006b6f  mov     rax, rbx
0x180006b72  add     rsp, 20h
0x180006b76  pop     rbx
0x180006b77  retn
```
