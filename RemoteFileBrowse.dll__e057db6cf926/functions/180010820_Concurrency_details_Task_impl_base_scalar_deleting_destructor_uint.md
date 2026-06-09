# Concurrency::details::_Task_impl_base::`scalar deleting destructor'(uint)

- ea: `0x180010820`
- end: `0x180010854`
- name: `??_G_Task_impl_base@details@Concurrency@@UEAAPEAXI@Z`
- size: `52`
- prototype: `Concurrency::details::_Task_impl_base *__fastcall(Concurrency::details::_Task_impl_base *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, service_task`

## callees

- `0x180002054`
- `0x180010008`
- `0x180010820`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
Concurrency::details::_Task_impl_base *__fastcall Concurrency::details::_Task_impl_base::`scalar deleting destructor'(
        Concurrency::details::_Task_impl_base *this,
        char a2)
{
  Concurrency::details::_Task_impl_base::~_Task_impl_base(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180010820  mov     [rsp+arg_0], rbx
0x180010825  push    rdi
0x180010826  sub     rsp, 20h
0x18001082a  mov     ebx, edx
0x18001082c  mov     rdi, rcx
0x18001082f  call    ??1_Task_impl_base@details@Concurrency@@UEAA@XZ; Concurrency::details::_Task_impl_base::~_Task_impl_base(void)
0x180010834  test    bl, 1
0x180010837  jz      short loc_180010846
0x180010839  mov     edx, 170h; unsigned __int64
0x18001083e  mov     rcx, rdi; void *
0x180010841  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180010846  mov     rbx, [rsp+28h+arg_0]
0x18001084b  mov     rax, rdi
0x18001084e  add     rsp, 20h
0x180010852  pop     rdi
0x180010853  retn
```
