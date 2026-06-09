# CWinTaskClassFactoryT<CTempSignedLicenseExchangeTaskHandler,1>::`vector deleting destructor'(uint)

- ea: `0x180002430`
- end: `0x180002462`
- name: `??_E?$CWinTaskClassFactoryT@VCTempSignedLicenseExchangeTaskHandler@@$00@@UEAAPEAXI@Z`
- size: `50`
- prototype: `_QWORD *__fastcall(_QWORD *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting, service_task`

## callees

- `0x180001424`
- `0x180002430`

## pseudocode

```c
_QWORD *__fastcall CWinTaskClassFactoryT<CTempSignedLicenseExchangeTaskHandler,1>::`vector deleting destructor'(
        _QWORD *a1,
        char a2)
{
  *a1 = &CWinTaskClassFactoryT<CTempSignedLicenseExchangeTaskHandler,1>::`vftable';
  _InterlockedDecrement(&CWinTaskHandler::s_cInstances);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180002430  push    rbx
0x180002432  sub     rsp, 20h
0x180002436  lea     rax, ??_7?$CWinTaskClassFactoryT@VCTempSignedLicenseExchangeTaskHandler@@$00@@6B@; const CWinTaskClassFactoryT<CTempSignedLicenseExchangeTaskHandler,1>::`vftable'
0x18000243d  mov     rbx, rcx
0x180002440  mov     [rcx], rax
0x180002443  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x18000244a  test    dl, 1
0x18000244d  jz      short loc_180002459
0x18000244f  mov     edx, 10h; unsigned __int64
0x180002454  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180002459  mov     rax, rbx
0x18000245c  add     rsp, 20h
0x180002460  pop     rbx
0x180002461  retn
```
