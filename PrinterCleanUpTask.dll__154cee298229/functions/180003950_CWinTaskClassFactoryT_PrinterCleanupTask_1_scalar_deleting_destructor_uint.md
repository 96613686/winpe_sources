# CWinTaskClassFactoryT<PrinterCleanupTask,1>::`scalar deleting destructor'(uint)

- ea: `0x180003950`
- end: `0x180003982`
- name: `??_G?$CWinTaskClassFactoryT@VPrinterCleanupTask@@$00@@UEAAPEAXI@Z`
- size: `50`
- prototype: `_QWORD *__fastcall(_QWORD *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting, service_task`

## callees

- `0x180002434`
- `0x180003950`

## pseudocode

```c
_QWORD *__fastcall CWinTaskClassFactoryT<PrinterCleanupTask,1>::`scalar deleting destructor'(_QWORD *a1, char a2)
{
  *a1 = &CWinTaskClassFactoryT<PrinterCleanupTask,1>::`vftable';
  _InterlockedDecrement(&CWinTaskHandler::s_cInstances);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180003950  push    rbx
0x180003952  sub     rsp, 20h
0x180003956  lea     rax, ??_7?$CWinTaskClassFactoryT@VPrinterCleanupTask@@$00@@6B@; const CWinTaskClassFactoryT<PrinterCleanupTask,1>::`vftable'
0x18000395d  mov     rbx, rcx
0x180003960  mov     [rcx], rax
0x180003963  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x18000396a  test    dl, 1
0x18000396d  jz      short loc_180003979
0x18000396f  mov     edx, 10h; unsigned __int64
0x180003974  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180003979  mov     rax, rbx
0x18000397c  add     rsp, 20h
0x180003980  pop     rbx
0x180003981  retn
```
