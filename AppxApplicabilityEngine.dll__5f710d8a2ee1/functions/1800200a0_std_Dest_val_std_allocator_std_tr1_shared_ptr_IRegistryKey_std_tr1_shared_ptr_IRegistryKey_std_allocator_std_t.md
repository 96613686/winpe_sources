# std::_Dest_val<std::allocator<std::tr1::shared_ptr<IRegistryKey>>,std::tr1::shared_ptr<IRegistryKey>>(std::allocator<std::tr1::shared_ptr<IRegistryKey>> &,std::tr1::shared_ptr<IRegistryKey> *)

- ea: `0x1800200a0`
- end: `0x1800200c1`
- name: `??$_Dest_val@V?$allocator@V?$shared_ptr@VIRegistryKey@@@tr1@std@@@std@@V?$shared_ptr@VIRegistryKey@@@tr1@2@@std@@YAXAEAV?$allocator@V?$shared_ptr@VIRegistryKey@@@tr1@std@@@0@PEAV?$shared_ptr@VIRegistryKey@@@tr1@0@@Z`
- size: `33`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18002114c`
- `0x18002136c`
- `0x18002485b`

## callees

- `0x1800200a0`
- `0x180020edc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall std::_Dest_val<std::allocator<std::tr1::shared_ptr<IRegistryKey>>,std::tr1::shared_ptr<IRegistryKey>>(
        __int64 a1,
        __int64 a2)
{
  std::tr1::_Ref_count_base *v2; // rcx

  v2 = *(std::tr1::_Ref_count_base **)(a2 + 8);
  if ( v2 )
    std::tr1::_Ref_count_base::_Decref(v2);
}

```

## disassembly

```asm
0x1800200a0  sub     rsp, 38h
0x1800200a4  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1800200ad  mov     rcx, [rdx+8]; this
0x1800200b1  test    rcx, rcx
0x1800200b4  jz      short loc_1800200BC
0x1800200b6  call    ?_Decref@_Ref_count_base@tr1@std@@QEAAXXZ; std::tr1::_Ref_count_base::_Decref(void)
0x1800200bb  nop
0x1800200bc  add     rsp, 38h
0x1800200c0  retn
```
