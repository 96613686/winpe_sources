# std::vector<std::shared_ptr<DeviceConfiguration::Device>,std::allocator<std::shared_ptr<DeviceConfiguration::Device>>>::_Tidy(void)

- ea: `0x180011550`
- end: `0x18001159a`
- name: `?_Tidy@?$vector@V?$shared_ptr@VDevice@DeviceConfiguration@@@std@@V?$allocator@V?$shared_ptr@VDevice@DeviceConfiguration@@@std@@@2@@std@@AEAAXXZ`
- size: `74`
- prototype: `void __fastcall(__int64 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000eab4`
- `0x18000ed18`

## callees

- `0x18000e220`
- `0x18000e254`
- `0x180011550`

## pseudocode

```c
void __fastcall std::vector<std::shared_ptr<DeviceConfiguration::Device>>::_Tidy(__int64 *a1)
{
  __int64 v2; // rcx

  v2 = *a1;
  if ( v2 )
  {
    std::_Destroy_range<std::allocator<std::shared_ptr<DeviceConfiguration::Device>>>(v2, a1[1]);
    std::_Deallocate<16>((_QWORD *)*a1, (a1[2] - *a1) & 0xFFFFFFFFFFFFFFF0uLL);
    *a1 = 0;
    a1[1] = 0;
    a1[2] = 0;
  }
}

```

## disassembly

```asm
0x180011550  push    rbx
0x180011552  sub     rsp, 20h
0x180011556  mov     rbx, rcx
0x180011559  mov     rcx, [rcx]
0x18001155c  test    rcx, rcx
0x18001155f  jz      short loc_180011594
0x180011561  mov     rdx, [rbx+8]
0x180011565  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@VDevice@DeviceConfiguration@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@VDevice@DeviceConfiguration@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@VDevice@DeviceConfiguration@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<DeviceConfiguration::Device>>>(std::shared_ptr<DeviceConfiguration::Device> *,std::shared_ptr<DeviceConfiguration::Device> * const,std::allocator<std::shared_ptr<DeviceConfiguration::Device>> &)
0x18001156a  mov     rdx, [rbx+10h]
0x18001156e  sub     rdx, [rbx]
0x180011571  mov     rcx, [rbx]
0x180011574  and     rdx, 0FFFFFFFFFFFFFFF0h
0x180011578  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001157d  mov     qword ptr [rbx], 0
0x180011584  mov     qword ptr [rbx+8], 0
0x18001158c  mov     qword ptr [rbx+10h], 0
0x180011594  add     rsp, 20h
0x180011598  pop     rbx
0x180011599  retn
```
