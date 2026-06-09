# Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::`vector deleting destructor'(uint)

- ea: `0x180004a40`
- end: `0x180004a74`
- name: `??_E?$OutOfProcModuleBase@VServiceModule@Internal@Windows@@@Details@WRL@Microsoft@@UEAAPEAXI@Z`
- size: `52`
- prototype: `Microsoft::WRL::Details *__fastcall(Microsoft::WRL::Details *, __int64, const unsigned __int16 *, bool)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180001b6c`
- `0x1800043a0`
- `0x180004a40`

## pseudocode

```c
Microsoft::WRL::Details *__fastcall Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::`vector deleting destructor'(
        Microsoft::WRL::Details *a1,
        __int64 a2,
        const unsigned __int16 *a3,
        bool a4)
{
  char v4; // bl

  v4 = a2;
  Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::~OutOfProcModuleBase<Windows::Internal::ServiceModule>(
    a1,
    a2,
    a3,
    a4);
  if ( (v4 & 1) != 0 )
    operator delete(a1, (const struct std::nothrow_t *)0x10);
  return a1;
}

```

## disassembly

```asm
0x180004a40  mov     [rsp+arg_0], rbx
0x180004a45  push    rdi
0x180004a46  sub     rsp, 20h
0x180004a4a  mov     ebx, edx
0x180004a4c  mov     rdi, rcx
0x180004a4f  call    ??1?$OutOfProcModuleBase@VServiceModule@Internal@Windows@@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::~OutOfProcModuleBase<Windows::Internal::ServiceModule>(void)
0x180004a54  test    bl, 1
0x180004a57  jz      short loc_180004A66
0x180004a59  mov     edx, 10h; struct std::nothrow_t *
0x180004a5e  mov     rcx, rdi; void *
0x180004a61  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180004a66  mov     rbx, [rsp+28h+arg_0]
0x180004a6b  mov     rax, rdi
0x180004a6e  add     rsp, 20h
0x180004a72  pop     rdi
0x180004a73  retn
```
