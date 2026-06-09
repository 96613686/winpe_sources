# CWinTaskClassFactoryT<PrintJobCleanupTask,1>::`scalar deleting destructor'(uint)

- ea: `0x180003910`
- end: `0x180003942`
- name: `??_G?$CWinTaskClassFactoryT@VPrintJobCleanupTask@@$00@@UEAAPEAXI@Z`
- size: `50`
- prototype: `_QWORD *__fastcall(_QWORD *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting, service_task`

## callees

- `0x180002434`
- `0x180003910`

## pseudocode

```c
_QWORD *__fastcall CWinTaskClassFactoryT<PrintJobCleanupTask,1>::`scalar deleting destructor'(_QWORD *a1, char a2)
{
  *a1 = &CWinTaskClassFactoryT<PrintJobCleanupTask,1>::`vftable';
  _InterlockedDecrement(&CWinTaskHandler::s_cInstances);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180003910  push    rbx
0x180003912  sub     rsp, 20h
0x180003916  lea     rax, ??_7?$CWinTaskClassFactoryT@VPrintJobCleanupTask@@$00@@6B@; const CWinTaskClassFactoryT<PrintJobCleanupTask,1>::`vftable'
0x18000391d  mov     rbx, rcx
0x180003920  mov     [rcx], rax
0x180003923  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x18000392a  test    dl, 1
0x18000392d  jz      short loc_180003939
0x18000392f  mov     edx, 10h; unsigned __int64
0x180003934  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180003939  mov     rax, rbx
0x18000393c  add     rsp, 20h
0x180003940  pop     rbx
0x180003941  retn
```
