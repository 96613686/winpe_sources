# std::vector<std::tr1::shared_ptr<IRegistryKey>,std::allocator<std::tr1::shared_ptr<IRegistryKey>>>::~vector<std::tr1::shared_ptr<IRegistryKey>,std::allocator<std::tr1::shared_ptr<IRegistryKey>>>(void)

- ea: `0x1800203f0`
- end: `0x1800203f5`
- name: `??1?$vector@V?$shared_ptr@VIRegistryKey@@@tr1@std@@V?$allocator@V?$shared_ptr@VIRegistryKey@@@tr1@std@@@3@@std@@QEAA@XZ`
- size: `5`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180024921`
- `0x180024b1d`

## callees

- `0x18002114c`

## pseudocode

```c
// attributes: thunk
__int64 std::vector<std::tr1::shared_ptr<IRegistryKey>>::~vector<std::tr1::shared_ptr<IRegistryKey>>()
{
  return std::vector<std::tr1::shared_ptr<IRegistryKey>>::_Tidy();
}

```

## disassembly

```asm
0x1800203f0  jmp     ?_Tidy@?$vector@V?$shared_ptr@VIRegistryKey@@@tr1@std@@V?$allocator@V?$shared_ptr@VIRegistryKey@@@tr1@std@@@3@@std@@IEAAXXZ; std::vector<std::tr1::shared_ptr<IRegistryKey>>::_Tidy(void)
```
