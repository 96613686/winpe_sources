# CWinTaskClassFactoryT<ShowFeedbackToastHandler,1>::`scalar deleting destructor'(uint)

- ea: `0x18000b7f0`
- end: `0x18000b822`
- name: `??_G?$CWinTaskClassFactoryT@VShowFeedbackToastHandler@@$00@@UEAAPEAXI@Z`
- size: `50`
- prototype: `_QWORD *__fastcall(_QWORD *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting, service_task`

## callees

- `0x180002fd0`
- `0x18000b7f0`

## pseudocode

```c
_QWORD *__fastcall CWinTaskClassFactoryT<ShowFeedbackToastHandler,1>::`scalar deleting destructor'(_QWORD *a1, char a2)
{
  *a1 = &CWinTaskClassFactoryT<ShowFeedbackToastHandler,1>::`vftable';
  _InterlockedDecrement(&CWinTaskHandler::s_cInstances);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x18000b7f0  push    rbx
0x18000b7f2  sub     rsp, 20h
0x18000b7f6  lea     rax, ??_7?$CWinTaskClassFactoryT@VShowFeedbackToastHandler@@$00@@6B@; const CWinTaskClassFactoryT<ShowFeedbackToastHandler,1>::`vftable'
0x18000b7fd  mov     rbx, rcx
0x18000b800  mov     [rcx], rax
0x18000b803  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x18000b80a  test    dl, 1
0x18000b80d  jz      short loc_18000B819
0x18000b80f  mov     edx, 10h; unsigned __int64
0x18000b814  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000b819  mov     rax, rbx
0x18000b81c  add     rsp, 20h
0x18000b820  pop     rbx
0x18000b821  retn
```
