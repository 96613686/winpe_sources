# DeviceConfiguration::Device::GetPrinterName(void)

- ea: `0x1800146a0`
- end: `0x1800146be`
- name: `?GetPrinterName@Device@DeviceConfiguration@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000ed18`
- `0x180010e44`
- `0x180015088`
- `0x180015e58`

## callees

- `0x18001436c`

## pseudocode

```c
__int64 __fastcall DeviceConfiguration::Device::GetPrinterName(__int64 a1, __int64 a2)
{
  std::wstring::wstring(a2, a1 + 32);
  return a2;
}

```

## disassembly

```asm
0x1800146a0  push    rbx
0x1800146a2  sub     rsp, 30h
0x1800146a6  mov     rbx, rdx
0x1800146a9  lea     rdx, [rcx+20h]
0x1800146ad  mov     rcx, rbx
0x1800146b0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800146b5  mov     rax, rbx
0x1800146b8  add     rsp, 30h
0x1800146bc  pop     rbx
0x1800146bd  retn
```
