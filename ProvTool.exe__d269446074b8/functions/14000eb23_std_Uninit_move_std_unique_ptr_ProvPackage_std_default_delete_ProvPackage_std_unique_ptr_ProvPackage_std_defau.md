# _std::_Uninit_move_std::unique_ptr_ProvPackage_std::default_delete_ProvPackage______std::unique_ptr_ProvPackage_std::default_delete_ProvPackage______std::allocator_std::unique_ptr_ProvPackage_std::default_delete_ProvPackage______std::unique_ptr_ProvPackage_std::default_delete_ProvPackage______::_1_::catch$0

- ea: `0x14000eb23`
- end: `0x14000eb53`
- name: `_std::_Uninit_move_std::unique_ptr_ProvPackage_std::default_delete_ProvPackage______std::unique_ptr_ProvPackage_std::default_delete_ProvPackage______std::allocator_std::unique_ptr_ProvPackage_std::default_delete_ProvPackage______std::unique_ptr_ProvPackage_std::default_delete_ProvPackage______::_1_::catch$0`
- size: `48`
- prototype: `void __fastcall __noreturn(__int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1400032c0`
- `0x14000dd7c`
- `0x14000eb23`

## pseudocode

```c
void __fastcall __noreturn std::_Uninit_move_std::unique_ptr_ProvPackage_std::default_delete_ProvPackage______std::unique_ptr_ProvPackage_std::default_delete_ProvPackage______std::allocator_std::unique_ptr_ProvPackage_std::default_delete_ProvPackage______std::unique_ptr_ProvPackage_std::default_delete_ProvPackage______::_1_::catch_0(
        __int64 a1,
        __int64 a2)
{
  _QWORD *i; // rbx

  for ( i = *(_QWORD **)(a2 + 72); i != *(_QWORD **)(a2 + 64); ++i )
    std::_Wrap_alloc<std::allocator<std::unique_ptr<ProvPackage>>>::destroy<std::unique_ptr<ProvPackage>>(a1, i);
  throw;
}

```

## disassembly

```asm
0x14000eb23  mov     [rsp+arg_8], rdx
0x14000eb28  push    rbx
0x14000eb29  push    rbp
0x14000eb2a  sub     rsp, 28h
0x14000eb2e  mov     rbp, rdx
0x14000eb31  mov     rbx, [rbp+48h]
0x14000eb35  jmp     short loc_14000EB43
0x14000eb37  mov     rdx, rbx
0x14000eb3a  call    ??$destroy@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@?$_Wrap_alloc@V?$allocator@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@std@@@std@@QEAAXPEAV?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@1@@Z; std::_Wrap_alloc<std::allocator<std::unique_ptr<ProvPackage>>>::destroy<std::unique_ptr<ProvPackage>>(std::unique_ptr<ProvPackage> *)
0x14000eb3f  add     rbx, 8
0x14000eb43  cmp     rbx, [rbp+40h]
0x14000eb47  jnz     short loc_14000EB37
0x14000eb49  xor     edx, edx; pThrowInfo
0x14000eb4b  xor     ecx, ecx; pExceptionObject
0x14000eb4d  call    _CxxThrowException_0
```
