# CWinTaskClassFactoryT<PerformanceTraceHandler,1>::`vector deleting destructor'(uint)

- ea: `0x18000b7b0`
- end: `0x18000b7e2`
- name: `??_E?$CWinTaskClassFactoryT@VPerformanceTraceHandler@@$00@@UEAAPEAXI@Z`
- size: `50`
- prototype: `_QWORD *__fastcall(_QWORD *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting, service_task`

## callees

- `0x180002fd0`
- `0x18000b7b0`

## pseudocode

```c
_QWORD *__fastcall CWinTaskClassFactoryT<PerformanceTraceHandler,1>::`vector deleting destructor'(_QWORD *a1, char a2)
{
  *a1 = &CWinTaskClassFactoryT<PerformanceTraceHandler,1>::`vftable';
  _InterlockedDecrement(&CWinTaskHandler::s_cInstances);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x18000b7b0  push    rbx
0x18000b7b2  sub     rsp, 20h
0x18000b7b6  lea     rax, ??_7?$CWinTaskClassFactoryT@VPerformanceTraceHandler@@$00@@6B@; const CWinTaskClassFactoryT<PerformanceTraceHandler,1>::`vftable'
0x18000b7bd  mov     rbx, rcx
0x18000b7c0  mov     [rcx], rax
0x18000b7c3  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x18000b7ca  test    dl, 1
0x18000b7cd  jz      short loc_18000B7D9
0x18000b7cf  mov     edx, 10h; unsigned __int64
0x18000b7d4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000b7d9  mov     rax, rbx
0x18000b7dc  add     rsp, 20h
0x18000b7e0  pop     rbx
0x18000b7e1  retn
```
