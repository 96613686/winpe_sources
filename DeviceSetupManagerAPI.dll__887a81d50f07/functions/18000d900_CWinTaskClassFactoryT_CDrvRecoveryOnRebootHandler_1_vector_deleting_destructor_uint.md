# CWinTaskClassFactoryT<CDrvRecoveryOnRebootHandler,1>::`vector deleting destructor'(uint)

- ea: `0x18000d900`
- end: `0x18000d932`
- name: `??_E?$CWinTaskClassFactoryT@VCDrvRecoveryOnRebootHandler@@$00@@UEAAPEAXI@Z`
- size: `50`
- prototype: `_QWORD *__fastcall(_QWORD *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting, service_task`

## callees

- `0x180001c6c`
- `0x18000d900`

## pseudocode

```c
_QWORD *__fastcall CWinTaskClassFactoryT<CDrvRecoveryOnRebootHandler,1>::`vector deleting destructor'(
        _QWORD *a1,
        char a2)
{
  *a1 = &CWinTaskClassFactoryT<CDrvRecoveryOnRebootHandler,1>::`vftable';
  _InterlockedDecrement(&CWinTaskHandler::s_cInstances);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x18000d900  push    rbx
0x18000d902  sub     rsp, 20h
0x18000d906  lea     rax, ??_7?$CWinTaskClassFactoryT@VCDrvRecoveryOnRebootHandler@@$00@@6B@; const CWinTaskClassFactoryT<CDrvRecoveryOnRebootHandler,1>::`vftable'
0x18000d90d  mov     rbx, rcx
0x18000d910  mov     [rcx], rax
0x18000d913  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x18000d91a  test    dl, 1
0x18000d91d  jz      short loc_18000D929
0x18000d91f  mov     edx, 10h
0x18000d924  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000d929  mov     rax, rbx
0x18000d92c  add     rsp, 20h
0x18000d930  pop     rbx
0x18000d931  retn
```
