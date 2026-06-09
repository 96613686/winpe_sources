# CWinTaskClassFactoryT<SetupRecoveryTaskHandler,1>::`vector deleting destructor'(uint)

- ea: `0x180003820`
- end: `0x18000384e`
- name: `??_E?$CWinTaskClassFactoryT@VSetupRecoveryTaskHandler@@$00@@UEAAPEAXI@Z`
- size: `46`
- prototype: `_QWORD *__fastcall(_QWORD *, char)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, loader_planting, service_task, installer_update`

## callees

- `0x180003820`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000383f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000383f`

## pseudocode

```c
_QWORD *__fastcall CWinTaskClassFactoryT<SetupRecoveryTaskHandler,1>::`vector deleting destructor'(_QWORD *a1, char a2)
{
  *a1 = &CWinTaskClassFactoryT<SetupRecoveryTaskHandler,1>::`vftable';
  _InterlockedDecrement(&CWinTaskHandler::s_cInstances);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180003820  push    rbx
0x180003822  sub     rsp, 20h
0x180003826  lea     rax, ??_7?$CWinTaskClassFactoryT@VSetupRecoveryTaskHandler@@$00@@6B@; const CWinTaskClassFactoryT<SetupRecoveryTaskHandler,1>::`vftable'
0x18000382d  mov     rbx, rcx
0x180003830  mov     [rcx], rax
0x180003833  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x18000383a  test    dl, 1
0x18000383d  jz      short loc_180003845
0x18000383f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180003845  mov     rax, rbx
0x180003848  add     rsp, 20h
0x18000384c  pop     rbx
0x18000384d  retn
```
