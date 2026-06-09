# std::_Fake_no_copy_callable_adapter__lambda_28acef7f84ef4b64850563b8e90ad6f2___::_Fake_no_copy_callable_adapter__lambda_28acef7f84ef4b64850563b8e90ad6f2___

- ea: `0x18000f138`
- end: `0x18000f159`
- name: `std::_Fake_no_copy_callable_adapter__lambda_28acef7f84ef4b64850563b8e90ad6f2___::_Fake_no_copy_callable_adapter__lambda_28acef7f84ef4b64850563b8e90ad6f2___`
- size: `33`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000e638`

## callees

- `0x18000f12c`
- `0x18000f4b8`

## pseudocode

```c
void __fastcall __noreturn std::_Fake_no_copy_callable_adapter__lambda_28acef7f84ef4b64850563b8e90ad6f2___::_Fake_no_copy_callable_adapter__lambda_28acef7f84ef4b64850563b8e90ad6f2___(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // rax
  __int64 v3; // r8

  v2 = std::move_std::tuple__lambda_28acef7f84ef4b64850563b8e90ad6f2______(a2, a2, a1);
  std::tuple__lambda_28acef7f84ef4b64850563b8e90ad6f2___::tuple__lambda_28acef7f84ef4b64850563b8e90ad6f2___(v3, v2);
  __fastfail(5u);
}

```

## disassembly

```asm
0x18000f138  sub     rsp, 28h
0x18000f13c  mov     r8, rcx
0x18000f13f  mov     rcx, rdx
0x18000f142  call    std__move_std__tuple__lambda_28acef7f84ef4b64850563b8e90ad6f2______
0x18000f147  mov     rdx, rax
0x18000f14a  mov     rcx, r8
0x18000f14d  call    std__tuple__lambda_28acef7f84ef4b64850563b8e90ad6f2_____tuple__lambda_28acef7f84ef4b64850563b8e90ad6f2___
0x18000f152  mov     ecx, 5
0x18000f157  int     29h; Win8: RtlFailFast(ecx)
```
