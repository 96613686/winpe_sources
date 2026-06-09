# CWinTaskClassFactoryT<CEcoScoreTaskHandler,1>::`vector deleting destructor'(uint)

- ea: `0x180003570`
- end: `0x18000359d`
- name: `??_E?$CWinTaskClassFactoryT@VCEcoScoreTaskHandler@@$00@@UEAAPEAXI@Z`
- size: `45`
- prototype: `_QWORD *__fastcall(_QWORD *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting, service_task`

## callees

- `0x180001aa4`
- `0x180003570`

## pseudocode

```c
_QWORD *__fastcall CWinTaskClassFactoryT<CEcoScoreTaskHandler,1>::`vector deleting destructor'(_QWORD *a1, char a2)
{
  *a1 = &CWinTaskClassFactoryT<CEcoScoreTaskHandler,1>::`vftable';
  _InterlockedDecrement(&CWinTaskHandler::s_cInstances);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180003570  push    rbx
0x180003572  sub     rsp, 20h
0x180003576  lea     rax, ??_7?$CWinTaskClassFactoryT@VCEcoScoreTaskHandler@@$00@@6B@; const CWinTaskClassFactoryT<CEcoScoreTaskHandler,1>::`vftable'
0x18000357d  mov     rbx, rcx
0x180003580  mov     [rcx], rax
0x180003583  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x18000358a  test    dl, 1
0x18000358d  jz      short loc_180003594
0x18000358f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003594  mov     rax, rbx
0x180003597  add     rsp, 20h
0x18000359b  pop     rbx
0x18000359c  retn
```
