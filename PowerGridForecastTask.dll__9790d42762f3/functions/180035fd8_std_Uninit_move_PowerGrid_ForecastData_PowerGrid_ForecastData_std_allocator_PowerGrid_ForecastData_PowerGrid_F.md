# _std::_Uninit_move_PowerGrid::ForecastData___PowerGrid::ForecastData___std::allocator_PowerGrid::ForecastData__PowerGrid::ForecastData__::_1_::catch$0

- ea: `0x180035fd8`
- end: `0x180035fef`
- name: `_std::_Uninit_move_PowerGrid::ForecastData___PowerGrid::ForecastData___std::allocator_PowerGrid::ForecastData__PowerGrid::ForecastData__::_1_::catch$0`
- size: `23`
- prototype: `void __noreturn()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180026778`

## pseudocode

```c
void __noreturn std::_Uninit_move_PowerGrid::ForecastData___PowerGrid::ForecastData___std::allocator_PowerGrid::ForecastData__PowerGrid::ForecastData__::_1_::catch_0()
{
  throw;
}

```

## disassembly

```asm
0x180035fd8  mov     [rsp+arg_8], rdx
0x180035fdd  push    rbp
0x180035fde  sub     rsp, 20h
0x180035fe2  mov     rbp, rdx
0x180035fe5  xor     edx, edx; pThrowInfo
0x180035fe7  xor     ecx, ecx; pExceptionObject
0x180035fe9  call    _CxxThrowException_0
```
