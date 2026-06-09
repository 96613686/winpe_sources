# DeviceConfiguration::Device::GetDeviceId(void)

- ea: `0x180014658`
- end: `0x180014675`
- name: `?GetDeviceId@Device@DeviceConfiguration@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `29`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `6`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000ed18`
- `0x18000fad4`
- `0x180010b10`
- `0x180010ca4`
- `0x180015678`
- `0x180015ad0`

## callees

- `0x18001436c`

## pseudocode

```c
__int64 __fastcall DeviceConfiguration::Device::GetDeviceId(__int64 a1, __int64 a2)
{
  std::wstring::wstring(a2, a1);
  return a2;
}

```

## disassembly

```asm
0x180014658  push    rbx
0x18001465a  sub     rsp, 30h
0x18001465e  mov     rbx, rdx
0x180014661  mov     rdx, rcx
0x180014664  mov     rcx, rbx
0x180014667  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001466c  mov     rax, rbx
0x18001466f  add     rsp, 30h
0x180014673  pop     rbx
0x180014674  retn
```
