# Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::ReleaseNotifier::`vector deleting destructor'(uint)

- ea: `0x180004520`
- end: `0x18000454b`
- name: `??_EReleaseNotifier@?$OutOfProcModuleBase@VServiceModule@Internal@Windows@@@Details@WRL@Microsoft@@UEAAPEAXI@Z`
- size: `43`
- prototype: `_QWORD *__fastcall(_QWORD *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180001644`
- `0x180004520`

## pseudocode

```c
_QWORD *__fastcall Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::ReleaseNotifier::`vector deleting destructor'(
        _QWORD *a1,
        char a2)
{
  *a1 = &Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::ReleaseNotifier::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180004520  push    rbx
0x180004522  sub     rsp, 20h
0x180004526  lea     rax, ??_7ReleaseNotifier@?$OutOfProcModuleBase@VServiceModule@Internal@Windows@@@Details@WRL@Microsoft@@6B@; const Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::ReleaseNotifier::`vftable'
0x18000452d  mov     rbx, rcx
0x180004530  mov     [rcx], rax
0x180004533  test    dl, 1
0x180004536  jz      short loc_180004542
0x180004538  mov     edx, 10h; unsigned __int64
0x18000453d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180004542  mov     rax, rbx
0x180004545  add     rsp, 20h
0x180004549  pop     rbx
0x18000454a  retn
```
