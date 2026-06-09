# CWinTaskClassFactoryT<CWofTasksHandler,1>::`scalar deleting destructor'(uint)

- ea: `0x180002b80`
- end: `0x180002bad`
- name: `??_G?$CWinTaskClassFactoryT@VCWofTasksHandler@@$00@@UEAAPEAXI@Z`
- size: `45`
- prototype: `_QWORD *__fastcall(_QWORD *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting, service_task`

## callees

- `0x180001048`
- `0x180002b80`

## pseudocode

```c
_QWORD *__fastcall CWinTaskClassFactoryT<CWofTasksHandler,1>::`scalar deleting destructor'(_QWORD *a1, char a2)
{
  *a1 = &CWinTaskClassFactoryT<CWofTasksHandler,1>::`vftable';
  _InterlockedDecrement(&CWinTaskHandler::s_cInstances);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180002b80  push    rbx
0x180002b82  sub     rsp, 20h
0x180002b86  lea     rax, ??_7?$CWinTaskClassFactoryT@VCWofTasksHandler@@$00@@6B@; const CWinTaskClassFactoryT<CWofTasksHandler,1>::`vftable'
0x180002b8d  mov     rbx, rcx
0x180002b90  mov     [rcx], rax
0x180002b93  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x180002b9a  test    dl, 1
0x180002b9d  jz      short loc_180002BA4
0x180002b9f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002ba4  mov     rax, rbx
0x180002ba7  add     rsp, 20h
0x180002bab  pop     rbx
0x180002bac  retn
```
