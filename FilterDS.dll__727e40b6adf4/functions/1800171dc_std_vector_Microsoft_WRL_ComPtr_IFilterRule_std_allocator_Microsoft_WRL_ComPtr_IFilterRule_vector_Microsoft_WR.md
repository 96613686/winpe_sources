# std::vector<Microsoft::WRL::ComPtr<IFilterRule>,std::allocator<Microsoft::WRL::ComPtr<IFilterRule>>>::~vector<Microsoft::WRL::ComPtr<IFilterRule>,std::allocator<Microsoft::WRL::ComPtr<IFilterRule>>>(void)

- ea: `0x1800171dc`
- end: `0x1800171e1`
- name: `??1?$vector@V?$ComPtr@UIFilterRule@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIFilterRule@@@WRL@Microsoft@@@std@@@std@@QEAA@XZ`
- size: `5`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800231b5`
- `0x180023207`

## callees

- `0x1800192b0`

## pseudocode

```c
// attributes: thunk
__int64 std::vector<Microsoft::WRL::ComPtr<IFilterRule>>::~vector<Microsoft::WRL::ComPtr<IFilterRule>>()
{
  return std::vector<Microsoft::WRL::ComPtr<IFilterRule>>::_Tidy();
}

```

## disassembly

```asm
0x1800171dc  jmp     ?_Tidy@?$vector@V?$ComPtr@UIFilterRule@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIFilterRule@@@WRL@Microsoft@@@std@@@std@@IEAAXXZ; std::vector<Microsoft::WRL::ComPtr<IFilterRule>>::_Tidy(void)
```
