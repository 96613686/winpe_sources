# _std::_Uninit_move_Microsoft::WRL::ComPtr_IFilterRule____Microsoft::WRL::ComPtr_IFilterRule____std::allocator_Microsoft::WRL::ComPtr_IFilterRule____Microsoft::WRL::ComPtr_IFilterRule____::_1_::catch$0

- ea: `0x180023145`
- end: `0x180023175`
- name: `_std::_Uninit_move_Microsoft::WRL::ComPtr_IFilterRule____Microsoft::WRL::ComPtr_IFilterRule____std::allocator_Microsoft::WRL::ComPtr_IFilterRule____Microsoft::WRL::ComPtr_IFilterRule____::_1_::catch$0`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000230c`
- `0x1800171b0`
- `0x180023145`

## pseudocode

```c
void __fastcall __noreturn std::_Uninit_move_Microsoft::WRL::ComPtr_IFilterRule____Microsoft::WRL::ComPtr_IFilterRule____std::allocator_Microsoft::WRL::ComPtr_IFilterRule____Microsoft::WRL::ComPtr_IFilterRule____::_1_::catch_0(
        __int64 a1,
        __int64 a2)
{
  __int64 *i; // rbx

  for ( i = *(__int64 **)(a2 + 72); i != *(__int64 **)(a2 + 64); ++i )
    std::_Wrap_alloc<std::allocator<Microsoft::WRL::ComPtr<IFilterRule>>>::destroy<Microsoft::WRL::ComPtr<IFilterRule>>(
      a1,
      i);
  throw;
}

```

## disassembly

```asm
0x180023145  mov     [rsp+arg_8], rdx
0x18002314a  push    rbx
0x18002314b  push    rbp
0x18002314c  sub     rsp, 28h
0x180023150  mov     rbp, rdx
0x180023153  mov     rbx, [rbp+48h]
0x180023157  jmp     short loc_180023165
0x180023159  mov     rdx, rbx
0x18002315c  call    ??$destroy@V?$ComPtr@UIFilterRule@@@WRL@Microsoft@@@?$_Wrap_alloc@V?$allocator@V?$ComPtr@UIFilterRule@@@WRL@Microsoft@@@std@@@std@@QEAAXPEAV?$ComPtr@UIFilterRule@@@WRL@Microsoft@@@Z; std::_Wrap_alloc<std::allocator<Microsoft::WRL::ComPtr<IFilterRule>>>::destroy<Microsoft::WRL::ComPtr<IFilterRule>>(Microsoft::WRL::ComPtr<IFilterRule> *)
0x180023161  add     rbx, 8
0x180023165  cmp     rbx, [rbp+40h]
0x180023169  jnz     short loc_180023159
0x18002316b  xor     edx, edx; pThrowInfo
0x18002316d  xor     ecx, ecx; pExceptionObject
0x18002316f  call    _CxxThrowException_0
```
