# CWinTaskClassFactoryT<CPlutonTasksHandler,1>::`scalar deleting destructor'(uint)

- ea: `0x180003b00`
- end: `0x180003b32`
- name: `??_G?$CWinTaskClassFactoryT@VCPlutonTasksHandler@@$00@@UEAAPEAXI@Z`
- size: `50`
- prototype: `_QWORD *__fastcall(_QWORD *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting, service_task`

## callees

- `0x180002214`
- `0x180003b00`

## pseudocode

```c
_QWORD *__fastcall CWinTaskClassFactoryT<CPlutonTasksHandler,1>::`scalar deleting destructor'(_QWORD *a1, char a2)
{
  *a1 = &CWinTaskClassFactoryT<CPlutonTasksHandler,1>::`vftable';
  _InterlockedDecrement(&CWinTaskHandler::s_cInstances);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180003b00  push    rbx
0x180003b02  sub     rsp, 20h
0x180003b06  lea     rax, ??_7?$CWinTaskClassFactoryT@VCPlutonTasksHandler@@$00@@6B@; const CWinTaskClassFactoryT<CPlutonTasksHandler,1>::`vftable'
0x180003b0d  mov     rbx, rcx
0x180003b10  mov     [rcx], rax
0x180003b13  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x180003b1a  test    dl, 1
0x180003b1d  jz      short loc_180003B29
0x180003b1f  mov     edx, 10h; unsigned __int64
0x180003b24  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180003b29  mov     rax, rbx
0x180003b2c  add     rsp, 20h
0x180003b30  pop     rbx
0x180003b31  retn
```
