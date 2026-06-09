# CWinTaskClassFactoryT<CPITRTaskHandler,1>::`scalar deleting destructor'(uint)

- ea: `0x180003d90`
- end: `0x180003dbe`
- name: `??_G?$CWinTaskClassFactoryT@VCPITRTaskHandler@@$00@@UEAAPEAXI@Z`
- size: `46`
- prototype: `_QWORD *__fastcall(_QWORD *, char)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, loader_planting, service_task`

## callees

- `0x180003d90`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180003daf`
- `msvcrt!??3@YAXPEAX@Z` at `0x180003daf`

## pseudocode

```c
_QWORD *__fastcall CWinTaskClassFactoryT<CPITRTaskHandler,1>::`scalar deleting destructor'(_QWORD *a1, char a2)
{
  *a1 = &CWinTaskClassFactoryT<CPITRTaskHandler,1>::`vftable';
  _InterlockedDecrement(&CWinTaskHandler::s_cInstances);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180003d90  push    rbx
0x180003d92  sub     rsp, 20h
0x180003d96  lea     rax, ??_7?$CWinTaskClassFactoryT@VCPITRTaskHandler@@$00@@6B@; const CWinTaskClassFactoryT<CPITRTaskHandler,1>::`vftable'
0x180003d9d  mov     rbx, rcx
0x180003da0  mov     [rcx], rax
0x180003da3  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x180003daa  test    dl, 1
0x180003dad  jz      short loc_180003DB5
0x180003daf  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180003db5  mov     rax, rbx
0x180003db8  add     rsp, 20h
0x180003dbc  pop     rbx
0x180003dbd  retn
```
