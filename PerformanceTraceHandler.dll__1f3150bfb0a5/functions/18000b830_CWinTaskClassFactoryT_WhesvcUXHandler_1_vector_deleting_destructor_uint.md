# CWinTaskClassFactoryT<WhesvcUXHandler,1>::`vector deleting destructor'(uint)

- ea: `0x18000b830`
- end: `0x18000b862`
- name: `??_E?$CWinTaskClassFactoryT@VWhesvcUXHandler@@$00@@UEAAPEAXI@Z`
- size: `50`
- prototype: `_QWORD *__fastcall(_QWORD *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting, service_task`

## callees

- `0x180002fd0`
- `0x18000b830`

## pseudocode

```c
_QWORD *__fastcall CWinTaskClassFactoryT<WhesvcUXHandler,1>::`vector deleting destructor'(_QWORD *a1, char a2)
{
  *a1 = &CWinTaskClassFactoryT<WhesvcUXHandler,1>::`vftable';
  _InterlockedDecrement(&CWinTaskHandler::s_cInstances);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x18000b830  push    rbx
0x18000b832  sub     rsp, 20h
0x18000b836  lea     rax, ??_7?$CWinTaskClassFactoryT@VWhesvcUXHandler@@$00@@6B@; const CWinTaskClassFactoryT<WhesvcUXHandler,1>::`vftable'
0x18000b83d  mov     rbx, rcx
0x18000b840  mov     [rcx], rax
0x18000b843  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x18000b84a  test    dl, 1
0x18000b84d  jz      short loc_18000B859
0x18000b84f  mov     edx, 10h; unsigned __int64
0x18000b854  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000b859  mov     rax, rbx
0x18000b85c  add     rsp, 20h
0x18000b860  pop     rbx
0x18000b861  retn
```
