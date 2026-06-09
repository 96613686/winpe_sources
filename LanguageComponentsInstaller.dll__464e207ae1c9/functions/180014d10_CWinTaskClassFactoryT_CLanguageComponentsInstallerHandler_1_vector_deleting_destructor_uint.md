# CWinTaskClassFactoryT<CLanguageComponentsInstallerHandler,1>::`vector deleting destructor'(uint)

- ea: `0x180014d10`
- end: `0x180014d42`
- name: `??_E?$CWinTaskClassFactoryT@VCLanguageComponentsInstallerHandler@@$00@@UEAAPEAXI@Z`
- size: `50`
- prototype: `_QWORD *__fastcall(_QWORD *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180003a34`
- `0x180014d10`

## pseudocode

```c
_QWORD *__fastcall CWinTaskClassFactoryT<CLanguageComponentsInstallerHandler,1>::`vector deleting destructor'(
        _QWORD *a1,
        char a2)
{
  *a1 = &CWinTaskClassFactoryT<CLanguageComponentsInstallerHandler,1>::`vftable';
  _InterlockedDecrement(&CWinTaskHandler::s_cInstances);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180014d10  push    rbx
0x180014d12  sub     rsp, 20h
0x180014d16  lea     rax, ??_7?$CWinTaskClassFactoryT@VCLanguageComponentsInstallerHandler@@$00@@6B@; const CWinTaskClassFactoryT<CLanguageComponentsInstallerHandler,1>::`vftable'
0x180014d1d  mov     rbx, rcx
0x180014d20  mov     [rcx], rax
0x180014d23  lock dec cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x180014d2a  test    dl, 1
0x180014d2d  jz      short loc_180014D39
0x180014d2f  mov     edx, 10h
0x180014d34  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180014d39  mov     rax, rbx
0x180014d3c  add     rsp, 20h
0x180014d40  pop     rbx
0x180014d41  retn
```
