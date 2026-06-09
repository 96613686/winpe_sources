# std::_Func_impl_no_alloc_std::_Fake_no_copy_callable_adapter__lambda_28acef7f84ef4b64850563b8e90ad6f2____void_::_Copy

- ea: `0x180011ae0`
- end: `0x180011af9`
- name: `std::_Func_impl_no_alloc_std::_Fake_no_copy_callable_adapter__lambda_28acef7f84ef4b64850563b8e90ad6f2____void_::_Copy`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180005b34`
- `0x18000e638`

## pseudocode

```c
void __fastcall __noreturn std::_Func_impl_no_alloc_std::_Fake_no_copy_callable_adapter__lambda_28acef7f84ef4b64850563b8e90ad6f2____void_::_Copy(
        unsigned __int64 a1,
        void *a2)
{
  _QWORD *v2; // rax
  __int64 v3; // r8

  v2 = operator new(a1, a2);
  std::_Func_impl_no_alloc_std::_Fake_no_copy_callable_adapter__lambda_28acef7f84ef4b64850563b8e90ad6f2____void_::_Func_impl_no_alloc_std::_Fake_no_copy_callable_adapter__lambda_28acef7f84ef4b64850563b8e90ad6f2____void__std::_Fake_no_copy_callable_adapter__lambda_28acef7f84ef4b64850563b8e90ad6f2____const___0_(
    v2,
    v3);
}

```

## disassembly

```asm
0x180011ae0  sub     rsp, 28h
0x180011ae4  lea     r8, [rcx+8]
0x180011ae8  call    ??2@YAPEAX_KPEAX@Z; operator new(unsigned __int64,void *)
0x180011aed  mov     rcx, rax
0x180011af0  mov     rdx, r8
0x180011af3  call    std___Func_impl_no_alloc_std___Fake_no_copy_callable_adapter__lambda_28acef7f84ef4b64850563b8e90ad6f2____void____Func_impl_no_alloc_std___Fake_no_copy_callable_adapter__lambda_28acef7f84ef4b64850563b8e90ad6f2____void__std___Fake_no_copy_callable_adapter__lambda_28acef7f84ef4b64850563b8e90ad6f2____const___0_
```
