# CWinTaskClassFactoryT<CDeferredChargingTaskHandler,1>::`scalar deleting destructor'(uint)

- ea: `0x1800288e0`
- end: `0x18002890e`
- name: `??_G?$CWinTaskClassFactoryT@VCDeferredChargingTaskHandler@@$00@@UEAAPEAXI@Z`
- size: `46`
- prototype: `_QWORD *__fastcall(_QWORD *, char)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, loader_planting, service_task`

## callees

- `0x1800288e0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800288ff`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800288ff`

## pseudocode

```c
_QWORD *__fastcall CWinTaskClassFactoryT<CDeferredChargingTaskHandler,1>::`scalar deleting destructor'(
        _QWORD *a1,
        char a2)
{
  *a1 = &CWinTaskClassFactoryT<CDeferredChargingTaskHandler,1>::`vftable';
  _InterlockedDecrement(&CWinTaskHandler::s_cInstances);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x1800288e0  push    rbx
0x1800288e2  sub     rsp, 20h
0x1800288e6  lea     rax, ??_7?$CWinTaskClassFactoryT@VCDeferredChargingTaskHandler@@$00@@6B@; const CWinTaskClassFactoryT<CDeferredChargingTaskHandler,1>::`vftable'
0x1800288ed  mov     rbx, rcx
0x1800288f0  mov     [rcx], rax
0x1800288f3  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x1800288fa  test    dl, 1
0x1800288fd  jz      short loc_180028905
0x1800288ff  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180028905  mov     rax, rbx
0x180028908  add     rsp, 20h
0x18002890c  pop     rbx
0x18002890d  retn
```
