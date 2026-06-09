# std::_Task_async_state<void>::`vector deleting destructor'(uint)

- ea: `0x180010680`
- end: `0x1800106b4`
- name: `??_E?$_Task_async_state@X@std@@UEAAPEAXI@Z`
- size: `52`
- prototype: `_QWORD *__fastcall(_QWORD *, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, service_task`

## callees

- `0x180002054`
- `0x18000fae8`
- `0x180010680`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall std::_Task_async_state<void>::`vector deleting destructor'(_QWORD *a1, char a2)
{
  std::_Task_async_state<void>::~_Task_async_state<void>(a1);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180010680  mov     [rsp+arg_0], rbx
0x180010685  push    rdi
0x180010686  sub     rsp, 20h
0x18001068a  mov     ebx, edx
0x18001068c  mov     rdi, rcx
0x18001068f  call    ??1?$_Task_async_state@X@std@@UEAA@XZ; std::_Task_async_state<void>::~_Task_async_state<void>(void)
0x180010694  test    bl, 1
0x180010697  jz      short loc_1800106A6
0x180010699  mov     edx, 120h; unsigned __int64
0x18001069e  mov     rcx, rdi; void *
0x1800106a1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800106a6  mov     rbx, [rsp+28h+arg_0]
0x1800106ab  mov     rax, rdi
0x1800106ae  add     rsp, 20h
0x1800106b2  pop     rdi
0x1800106b3  retn
```
