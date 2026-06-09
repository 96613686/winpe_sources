# Microsoft::WRL::SimpleClassFactory<PrinterCleanupTaskNotificationActivator,0>::`vector deleting destructor'(uint)

- ea: `0x180006b20`
- end: `0x180006b48`
- name: `??_E?$SimpleClassFactory@VPrinterCleanupTaskNotificationActivator@@$0A@@WRL@Microsoft@@UEAAPEAXI@Z`
- size: `40`
- prototype: `_DWORD *__fastcall(_DWORD *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180002434`
- `0x180006b20`

## pseudocode

```c
_DWORD *__fastcall Microsoft::WRL::SimpleClassFactory<PrinterCleanupTaskNotificationActivator,0>::`vector deleting destructor'(
        _DWORD *a1,
        char a2)
{
  a1[3] = -1073741823;
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180006b20  push    rbx
0x180006b22  sub     rsp, 20h
0x180006b26  mov     dword ptr [rcx+0Ch], 0C0000001h
0x180006b2d  mov     rbx, rcx
0x180006b30  test    dl, 1
0x180006b33  jz      short loc_180006B3F
0x180006b35  mov     edx, 18h; unsigned __int64
0x180006b3a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180006b3f  mov     rax, rbx
0x180006b42  add     rsp, 20h
0x180006b46  pop     rbx
0x180006b47  retn
```
