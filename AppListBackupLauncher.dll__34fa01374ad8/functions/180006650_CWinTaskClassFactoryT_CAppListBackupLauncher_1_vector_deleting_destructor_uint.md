# CWinTaskClassFactoryT<CAppListBackupLauncher,1>::`vector deleting destructor'(uint)

- ea: `0x180006650`
- end: `0x180006682`
- name: `??_E?$CWinTaskClassFactoryT@VCAppListBackupLauncher@@$00@@UEAAPEAXI@Z`
- size: `50`
- prototype: `_QWORD *__fastcall(_QWORD *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting, service_task`

## callees

- `0x180002738`
- `0x180006650`

## pseudocode

```c
_QWORD *__fastcall CWinTaskClassFactoryT<CAppListBackupLauncher,1>::`vector deleting destructor'(_QWORD *a1, char a2)
{
  *a1 = &CWinTaskClassFactoryT<CAppListBackupLauncher,1>::`vftable';
  _InterlockedDecrement(&CWinTaskHandler::s_cInstances);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180006650  push    rbx
0x180006652  sub     rsp, 20h
0x180006656  lea     rax, ??_7?$CWinTaskClassFactoryT@VCAppListBackupLauncher@@$00@@6B@; const CWinTaskClassFactoryT<CAppListBackupLauncher,1>::`vftable'
0x18000665d  mov     rbx, rcx
0x180006660  mov     [rcx], rax
0x180006663  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x18000666a  test    dl, 1
0x18000666d  jz      short loc_180006679
0x18000666f  mov     edx, 10h; unsigned __int64
0x180006674  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180006679  mov     rax, rbx
0x18000667c  add     rsp, 20h
0x180006680  pop     rbx
0x180006681  retn
```
