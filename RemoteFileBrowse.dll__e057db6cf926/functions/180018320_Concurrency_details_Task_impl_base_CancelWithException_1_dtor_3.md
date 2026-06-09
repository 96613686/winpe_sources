# _Concurrency::details::_Task_impl_base::_CancelWithException_::_1_::dtor$3

- ea: `0x180018320`
- end: `0x180018340`
- name: `_Concurrency::details::_Task_impl_base::_CancelWithException_::_1_::dtor$3`
- size: `32`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, service_task`

## callees

- `0x180002054`

## pseudocode

```c
void __fastcall Concurrency::details::_Task_impl_base::_CancelWithException_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 128));
}

```

## disassembly

```asm
0x180018320  push    rbp
0x180018322  sub     rsp, 20h
0x180018326  mov     rbp, rdx
0x180018329  mov     edx, 48h ; 'H'; unsigned __int64
0x18001832e  mov     rcx, [rbp+80h]; void *
0x180018335  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001833a  add     rsp, 20h
0x18001833e  pop     rbp
0x18001833f  retn
```
