# std::_Func_impl_no_alloc_std::_Fake_no_copy_callable_adapter__lambda_28acef7f84ef4b64850563b8e90ad6f2____void_::_Func_impl_no_alloc_std::_Fake_no_copy_callable_adapter__lambda_28acef7f84ef4b64850563b8e90ad6f2____void__std::_Fake_no_copy_callable_adapter__lambda_28acef7f84ef4b64850563b8e90ad6f2____const_&_0_

- ea: `0x18000e638`
- end: `0x18000e65e`
- name: `std::_Func_impl_no_alloc_std::_Fake_no_copy_callable_adapter__lambda_28acef7f84ef4b64850563b8e90ad6f2____void_::_Func_impl_no_alloc_std::_Fake_no_copy_callable_adapter__lambda_28acef7f84ef4b64850563b8e90ad6f2____void__std::_Fake_no_copy_callable_adapter__lambda_28acef7f84ef4b64850563b8e90ad6f2____const_&_0_`
- size: `38`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180011ae0`

## callees

- `0x18000f12c`
- `0x18000f138`

## pseudocode

```c
void __fastcall __noreturn std::_Func_impl_no_alloc_std::_Fake_no_copy_callable_adapter__lambda_28acef7f84ef4b64850563b8e90ad6f2____void_::_Func_impl_no_alloc_std::_Fake_no_copy_callable_adapter__lambda_28acef7f84ef4b64850563b8e90ad6f2____void__std::_Fake_no_copy_callable_adapter__lambda_28acef7f84ef4b64850563b8e90ad6f2____const___0_(
        _QWORD *a1,
        __int64 a2)
{
  __int64 v2; // rax
  __int64 v3; // r8

  *a1 = &off_18001A7A8;
  v2 = std::move_std::tuple__lambda_28acef7f84ef4b64850563b8e90ad6f2______(a2, a2, a1);
  std::_Fake_no_copy_callable_adapter__lambda_28acef7f84ef4b64850563b8e90ad6f2___::_Fake_no_copy_callable_adapter__lambda_28acef7f84ef4b64850563b8e90ad6f2___(
    v3 + 8,
    v2);
}

```

## disassembly

```asm
0x18000e638  sub     rsp, 28h
0x18000e63c  lea     rax, off_18001A7A8
0x18000e643  mov     r8, rcx
0x18000e646  mov     [rcx], rax
0x18000e649  mov     rcx, rdx
0x18000e64c  call    std__move_std__tuple__lambda_28acef7f84ef4b64850563b8e90ad6f2______
0x18000e651  mov     rdx, rax
0x18000e654  lea     rcx, [r8+8]
0x18000e658  call    std___Fake_no_copy_callable_adapter__lambda_28acef7f84ef4b64850563b8e90ad6f2______Fake_no_copy_callable_adapter__lambda_28acef7f84ef4b64850563b8e90ad6f2___
```
