# std::_Destroy_range<std::allocator<std::shared_ptr<DeviceConfiguration::Device>>>(std::shared_ptr<DeviceConfiguration::Device> *,std::shared_ptr<DeviceConfiguration::Device> * const,std::allocator<std::shared_ptr<DeviceConfiguration::Device>> &)

- ea: `0x18000e254`
- end: `0x18000e28b`
- name: `??$_Destroy_range@V?$allocator@V?$shared_ptr@VDevice@DeviceConfiguration@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@VDevice@DeviceConfiguration@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@VDevice@DeviceConfiguration@@@std@@@0@@Z`
- size: `55`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000e294`
- `0x18000e554`
- `0x18000eb28`
- `0x180011550`

## callees

- `0x18000af54`
- `0x18000e254`

## pseudocode

```c
void __fastcall std::_Destroy_range<std::allocator<std::shared_ptr<DeviceConfiguration::Device>>>(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rbx
  std::_Ref_count_base *v4; // rcx

  if ( a1 != a2 )
  {
    v3 = a1;
    do
    {
      v4 = *(std::_Ref_count_base **)(v3 + 8);
      if ( v4 )
        std::_Ref_count_base::_Decref(v4);
      v3 += 16;
    }
    while ( v3 != a2 );
  }
}

```

## disassembly

```asm
0x18000e254  cmp     rcx, rdx
0x18000e257  jz      short locret_18000E28A
0x18000e259  mov     [rsp+arg_0], rbx
0x18000e25e  push    rdi
0x18000e25f  sub     rsp, 20h
0x18000e263  mov     rdi, rdx
0x18000e266  mov     rbx, rcx
0x18000e269  mov     rcx, [rbx+8]; this
0x18000e26d  test    rcx, rcx
0x18000e270  jz      short loc_18000E277
0x18000e272  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000e277  add     rbx, 10h
0x18000e27b  cmp     rbx, rdi
0x18000e27e  jnz     short loc_18000E269
0x18000e280  mov     rbx, [rsp+28h+arg_0]
0x18000e285  add     rsp, 20h
0x18000e289  pop     rdi
0x18000e28a  retn
```
