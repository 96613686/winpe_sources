# std::tr1::shared_ptr<IRegistryMultiStringValue>::~shared_ptr<IRegistryMultiStringValue>(void)

- ea: `0x180020394`
- end: `0x1800203b5`
- name: `??1?$shared_ptr@VIRegistryMultiStringValue@@@tr1@std@@QEAA@XZ`
- size: `33`
- prototype: `void __fastcall(__int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800235ad`
- `0x1800235e3`
- `0x180024961`
- `0x180024a91`
- `0x180024b49`

## callees

- `0x180020394`
- `0x180020edc`

## pseudocode

```c
void __fastcall std::tr1::shared_ptr<IRegistryMultiStringValue>::~shared_ptr<IRegistryMultiStringValue>(__int64 a1)
{
  std::tr1::_Ref_count_base *v1; // rcx

  v1 = *(std::tr1::_Ref_count_base **)(a1 + 8);
  if ( v1 )
    std::tr1::_Ref_count_base::_Decref(v1);
}

```

## disassembly

```asm
0x180020394  sub     rsp, 38h
0x180020398  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1800203a1  mov     rcx, [rcx+8]; this
0x1800203a5  test    rcx, rcx
0x1800203a8  jz      short loc_1800203B0
0x1800203aa  call    ?_Decref@_Ref_count_base@tr1@std@@QEAAXXZ; std::tr1::_Ref_count_base::_Decref(void)
0x1800203af  nop
0x1800203b0  add     rsp, 38h
0x1800203b4  retn
```
