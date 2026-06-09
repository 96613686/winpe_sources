# Concurrency::details::_Task_impl<uchar>::`vector deleting destructor'(uint)

- ea: `0x1800106c0`
- end: `0x1800106f4`
- name: `??_E?$_Task_impl@E@details@Concurrency@@UEAAPEAXI@Z`
- size: `52`
- prototype: `Concurrency::details::_Task_impl_base *__fastcall(Concurrency::details::_Task_impl_base *, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, service_task`

## callees

- `0x180002054`
- `0x18000fb74`
- `0x1800106c0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
Concurrency::details::_Task_impl_base *__fastcall Concurrency::details::_Task_impl<unsigned char>::`vector deleting destructor'(
        Concurrency::details::_Task_impl_base *a1,
        char a2)
{
  Concurrency::details::_Task_impl<unsigned char>::~_Task_impl<unsigned char>(a1);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x1800106c0  mov     [rsp+arg_0], rbx
0x1800106c5  push    rdi
0x1800106c6  sub     rsp, 20h
0x1800106ca  mov     ebx, edx
0x1800106cc  mov     rdi, rcx
0x1800106cf  call    ??1?$_Task_impl@E@details@Concurrency@@UEAA@XZ; Concurrency::details::_Task_impl<uchar>::~_Task_impl<uchar>(void)
0x1800106d4  test    bl, 1
0x1800106d7  jz      short loc_1800106E6
0x1800106d9  mov     edx, 1B8h; unsigned __int64
0x1800106de  mov     rcx, rdi; void *
0x1800106e1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800106e6  mov     rbx, [rsp+28h+arg_0]
0x1800106eb  mov     rax, rdi
0x1800106ee  add     rsp, 20h
0x1800106f2  pop     rdi
0x1800106f3  retn
```
