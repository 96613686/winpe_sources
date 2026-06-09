# _std::_Uninit_move_std::tr1::shared_ptr_IRegistryKey____std::tr1::shared_ptr_IRegistryKey____std::allocator_std::tr1::shared_ptr_IRegistryKey____std::tr1::shared_ptr_IRegistryKey____::_1_::catch$0

- ea: `0x18002485b`
- end: `0x18002488b`
- name: `_std::_Uninit_move_std::tr1::shared_ptr_IRegistryKey____std::tr1::shared_ptr_IRegistryKey____std::allocator_std::tr1::shared_ptr_IRegistryKey____std::tr1::shared_ptr_IRegistryKey____::_1_::catch$0`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x180013294`
- `0x1800200a0`
- `0x18002485b`

## pseudocode

```c
void __fastcall __noreturn std::_Uninit_move_std::tr1::shared_ptr_IRegistryKey____std::tr1::shared_ptr_IRegistryKey____std::allocator_std::tr1::shared_ptr_IRegistryKey____std::tr1::shared_ptr_IRegistryKey____::_1_::catch_0(
        __int64 a1,
        __int64 a2)
{
  __int64 i; // rbx

  for ( i = *(_QWORD *)(a2 + 88); i != *(_QWORD *)(a2 + 80); i += 16 )
    std::_Dest_val<std::allocator<std::tr1::shared_ptr<IRegistryKey>>,std::tr1::shared_ptr<IRegistryKey>>(a1, i);
  throw;
}

```

## disassembly

```asm
0x18002485b  mov     [rsp+arg_8], rdx
0x180024860  push    rbx
0x180024861  push    rbp
0x180024862  sub     rsp, 28h
0x180024866  mov     rbp, rdx
0x180024869  mov     rbx, [rbp+58h]
0x18002486d  jmp     short loc_18002487B
0x18002486f  mov     rdx, rbx
0x180024872  call    ??$_Dest_val@V?$allocator@V?$shared_ptr@VIRegistryKey@@@tr1@std@@@std@@V?$shared_ptr@VIRegistryKey@@@tr1@2@@std@@YAXAEAV?$allocator@V?$shared_ptr@VIRegistryKey@@@tr1@std@@@0@PEAV?$shared_ptr@VIRegistryKey@@@tr1@0@@Z; std::_Dest_val<std::allocator<std::tr1::shared_ptr<IRegistryKey>>,std::tr1::shared_ptr<IRegistryKey>>(std::allocator<std::tr1::shared_ptr<IRegistryKey>> &,std::tr1::shared_ptr<IRegistryKey> *)
0x180024877  add     rbx, 10h
0x18002487b  cmp     rbx, [rbp+50h]
0x18002487f  jnz     short loc_18002486F
0x180024881  xor     edx, edx; pThrowInfo
0x180024883  xor     ecx, ecx; pExceptionObject
0x180024885  call    _CxxThrowException_0
```
