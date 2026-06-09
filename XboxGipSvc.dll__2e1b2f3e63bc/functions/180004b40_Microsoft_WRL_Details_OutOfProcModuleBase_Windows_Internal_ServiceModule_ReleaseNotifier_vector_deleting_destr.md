# Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::ReleaseNotifier::`vector deleting destructor'(uint)

- ea: `0x180004b40`
- end: `0x180004b6b`
- name: `??_EReleaseNotifier@?$OutOfProcModuleBase@VServiceModule@Internal@Windows@@@Details@WRL@Microsoft@@UEAAPEAXI@Z`
- size: `43`
- prototype: `_QWORD *__fastcall(_QWORD *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180001b6c`
- `0x180004b40`

## pseudocode

```c
_QWORD *__fastcall Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::ReleaseNotifier::`vector deleting destructor'(
        _QWORD *a1,
        char a2)
{
  *a1 = &Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::ReleaseNotifier::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(a1, (const struct std::nothrow_t *)0x10);
  return a1;
}

```

## disassembly

```asm
0x180004b40  push    rbx
0x180004b42  sub     rsp, 20h
0x180004b46  lea     rax, ??_7ReleaseNotifier@?$OutOfProcModuleBase@VServiceModule@Internal@Windows@@@Details@WRL@Microsoft@@6B@; const Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::ReleaseNotifier::`vftable'
0x180004b4d  mov     rbx, rcx
0x180004b50  mov     [rcx], rax
0x180004b53  test    dl, 1
0x180004b56  jz      short loc_180004B62
0x180004b58  mov     edx, 10h; struct std::nothrow_t *
0x180004b5d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180004b62  mov     rax, rbx
0x180004b65  add     rsp, 20h
0x180004b69  pop     rbx
0x180004b6a  retn
```
