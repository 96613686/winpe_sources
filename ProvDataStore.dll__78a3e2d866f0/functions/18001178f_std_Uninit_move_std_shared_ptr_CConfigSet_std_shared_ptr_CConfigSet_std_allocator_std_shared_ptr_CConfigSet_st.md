# _std::_Uninit_move_std::shared_ptr_CConfigSet____std::shared_ptr_CConfigSet____std::allocator_std::shared_ptr_CConfigSet____std::shared_ptr_CConfigSet____::_1_::catch$0

- ea: `0x18001178f`
- end: `0x1800117bf`
- name: `_std::_Uninit_move_std::shared_ptr_CConfigSet____std::shared_ptr_CConfigSet____std::allocator_std::shared_ptr_CConfigSet____std::shared_ptr_CConfigSet____::_1_::catch$0`
- size: `48`
- prototype: `void __fastcall __noreturn(__int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x180008e30`
- `0x180010e2c`
- `0x18001178f`

## pseudocode

```c
void __fastcall __noreturn std::_Uninit_move_std::shared_ptr_CConfigSet____std::shared_ptr_CConfigSet____std::allocator_std::shared_ptr_CConfigSet____std::shared_ptr_CConfigSet____::_1_::catch_0(
        __int64 a1,
        __int64 a2)
{
  __int64 i; // rbx

  for ( i = *(_QWORD *)(a2 + 72); i != *(_QWORD *)(a2 + 64); i += 16 )
    std::_Wrap_alloc<std::allocator<std::shared_ptr<CConfigSet>>>::destroy<std::shared_ptr<CConfigSet>>(a1, i);
  throw;
}

```

## disassembly

```asm
0x18001178f  mov     [rsp+arg_8], rdx
0x180011794  push    rbx
0x180011795  push    rbp
0x180011796  sub     rsp, 28h
0x18001179a  mov     rbp, rdx
0x18001179d  mov     rbx, [rbp+48h]
0x1800117a1  jmp     short loc_1800117AF
0x1800117a3  mov     rdx, rbx
0x1800117a6  call    ??$destroy@V?$shared_ptr@VCConfigSet@@@std@@@?$_Wrap_alloc@V?$allocator@V?$shared_ptr@VCConfigSet@@@std@@@std@@@std@@QEAAXPEAV?$shared_ptr@VCConfigSet@@@1@@Z; std::_Wrap_alloc<std::allocator<std::shared_ptr<CConfigSet>>>::destroy<std::shared_ptr<CConfigSet>>(std::shared_ptr<CConfigSet> *)
0x1800117ab  add     rbx, 10h
0x1800117af  cmp     rbx, [rbp+40h]
0x1800117b3  jnz     short loc_1800117A3
0x1800117b5  xor     edx, edx; pThrowInfo
0x1800117b7  xor     ecx, ecx; pExceptionObject
0x1800117b9  call    _CxxThrowException_0
```
