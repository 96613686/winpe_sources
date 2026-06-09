# std::shared_ptr<DeviceConfiguration::DeviceManager>::shared_ptr<DeviceConfiguration::DeviceManager>(std::shared_ptr<DeviceConfiguration::DeviceManager> const &)

- ea: `0x18000b838`
- end: `0x18000b866`
- name: `??0?$shared_ptr@VDeviceManager@DeviceConfiguration@@@std@@QEAA@AEBV01@@Z`
- size: `46`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *)`
- caller_count: `9`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000bac8`
- `0x18000e294`
- `0x18000ed18`
- `0x18000fbe0`
- `0x180010b10`
- `0x180010ca4`
- `0x180014e28`
- `0x180015088`
- `0x180015d8c`

## callees

- `0x18000b838`

## pseudocode

```c
_QWORD *__fastcall std::shared_ptr<DeviceConfiguration::DeviceManager>::shared_ptr<DeviceConfiguration::DeviceManager>(
        _QWORD *a1,
        _QWORD *a2)
{
  __int64 v2; // rax

  *a1 = 0;
  a1[1] = 0;
  v2 = a2[1];
  if ( v2 )
    _InterlockedIncrement((volatile signed __int32 *)(v2 + 8));
  *a1 = *a2;
  a1[1] = a2[1];
  return a1;
}

```

## disassembly

```asm
0x18000b838  mov     qword ptr [rcx], 0
0x18000b83f  mov     qword ptr [rcx+8], 0
0x18000b847  mov     rax, [rdx+8]
0x18000b84b  test    rax, rax
0x18000b84e  jz      short loc_18000B854
0x18000b850  lock inc dword ptr [rax+8]
0x18000b854  mov     rax, [rdx]
0x18000b857  mov     [rcx], rax
0x18000b85a  mov     rax, [rdx+8]
0x18000b85e  mov     [rcx+8], rax
0x18000b862  mov     rax, rcx
0x18000b865  retn
```
