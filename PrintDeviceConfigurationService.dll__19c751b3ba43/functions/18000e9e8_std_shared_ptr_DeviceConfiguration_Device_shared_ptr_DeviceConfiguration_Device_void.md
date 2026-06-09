# std::shared_ptr<DeviceConfiguration::Device>::~shared_ptr<DeviceConfiguration::Device>(void)

- ea: `0x18000e9e8`
- end: `0x18000e9ff`
- name: `??1?$shared_ptr@VDevice@DeviceConfiguration@@@std@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(__int64)`
- caller_count: `7`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180016d6c`
- `0x180016e43`
- `0x180016e55`
- `0x180016e67`
- `0x1800174b9`
- `0x180017564`
- `0x1800176ab`

## callees

- `0x18000af54`
- `0x18000e9e8`

## pseudocode

```c
void __fastcall std::shared_ptr<DeviceConfiguration::Device>::~shared_ptr<DeviceConfiguration::Device>(__int64 a1)
{
  std::_Ref_count_base *v1; // rcx

  v1 = *(std::_Ref_count_base **)(a1 + 8);
  if ( v1 )
    std::_Ref_count_base::_Decref(v1);
}

```

## disassembly

```asm
0x18000e9e8  sub     rsp, 28h
0x18000e9ec  mov     rcx, [rcx+8]; this
0x18000e9f0  test    rcx, rcx
0x18000e9f3  jz      short loc_18000E9FA
0x18000e9f5  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ
0x18000e9fa  add     rsp, 28h
0x18000e9fe  retn
```
