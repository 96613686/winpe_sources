# _std::_Uninit_move_std::unique_ptr_FilterAgent_std::default_delete_FilterAgent______std::unique_ptr_FilterAgent_std::default_delete_FilterAgent______std::allocator_std::unique_ptr_FilterAgent_std::default_delete_FilterAgent______std::unique_ptr_FilterAgent_std::default_delete_FilterAgent______::_1_::catch$0

- ea: `0x18002286d`
- end: `0x18002289d`
- name: `_std::_Uninit_move_std::unique_ptr_FilterAgent_std::default_delete_FilterAgent______std::unique_ptr_FilterAgent_std::default_delete_FilterAgent______std::allocator_std::unique_ptr_FilterAgent_std::default_delete_FilterAgent______std::unique_ptr_FilterAgent_std::default_delete_FilterAgent______::_1_::catch$0`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x18000230c`
- `0x18000db14`
- `0x18002286d`

## pseudocode

```c
void __fastcall __noreturn std::_Uninit_move_std::unique_ptr_FilterAgent_std::default_delete_FilterAgent______std::unique_ptr_FilterAgent_std::default_delete_FilterAgent______std::allocator_std::unique_ptr_FilterAgent_std::default_delete_FilterAgent______std::unique_ptr_FilterAgent_std::default_delete_FilterAgent______::_1_::catch_0(
        __int64 a1,
        __int64 a2)
{
  FilterAgent **i; // rbx

  for ( i = *(FilterAgent ***)(a2 + 72); i != *(FilterAgent ***)(a2 + 64); ++i )
    std::_Wrap_alloc<std::allocator<std::unique_ptr<FilterAgent>>>::destroy<std::unique_ptr<FilterAgent>>(a1, i);
  throw;
}

```

## disassembly

```asm
0x18002286d  mov     [rsp+arg_8], rdx
0x180022872  push    rbx
0x180022873  push    rbp
0x180022874  sub     rsp, 28h
0x180022878  mov     rbp, rdx
0x18002287b  mov     rbx, [rbp+48h]
0x18002287f  jmp     short loc_18002288D
0x180022881  mov     rdx, rbx
0x180022884  call    ??$destroy@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@?$_Wrap_alloc@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@std@@@std@@QEAAXPEAV?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@1@@Z; std::_Wrap_alloc<std::allocator<std::unique_ptr<FilterAgent>>>::destroy<std::unique_ptr<FilterAgent>>(std::unique_ptr<FilterAgent> *)
0x180022889  add     rbx, 8
0x18002288d  cmp     rbx, [rbp+40h]
0x180022891  jnz     short loc_180022881
0x180022893  xor     edx, edx; pThrowInfo
0x180022895  xor     ecx, ecx; pExceptionObject
0x180022897  call    _CxxThrowException_0
```
