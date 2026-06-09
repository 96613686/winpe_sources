# Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::`vector deleting destructor'(uint)

- ea: `0x1800044a0`
- end: `0x1800044d4`
- name: `??_E?$OutOfProcModuleBase@VServiceModule@Internal@Windows@@@Details@WRL@Microsoft@@UEAAPEAXI@Z`
- size: `52`
- prototype: `Microsoft::WRL::Details *__fastcall(Microsoft::WRL::Details *, __int64, const unsigned __int16 *, bool)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180001644`
- `0x180003c6c`
- `0x1800044a0`

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
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x1800044a0  mov     [rsp+arg_0], rbx
0x1800044a5  push    rdi
0x1800044a6  sub     rsp, 20h
0x1800044aa  mov     ebx, edx
0x1800044ac  mov     rdi, rcx
0x1800044af  call    ??1?$OutOfProcModuleBase@VServiceModule@Internal@Windows@@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::~OutOfProcModuleBase<Windows::Internal::ServiceModule>(void)
0x1800044b4  test    bl, 1
0x1800044b7  jz      short loc_1800044C6
0x1800044b9  mov     edx, 10h; unsigned __int64
0x1800044be  mov     rcx, rdi; void *
0x1800044c1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800044c6  mov     rbx, [rsp+28h+arg_0]
0x1800044cb  mov     rax, rdi
0x1800044ce  add     rsp, 20h
0x1800044d2  pop     rdi
0x1800044d3  retn
```
