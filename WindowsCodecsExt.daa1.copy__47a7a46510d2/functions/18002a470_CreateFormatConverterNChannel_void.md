# CreateFormatConverterNChannel(void)

- ea: `0x18002a470`
- end: `0x18002a499`
- name: `?CreateFormatConverterNChannel@@YAPEAUIUnknown@@XZ`
- size: `41`
- prototype: `struct IUnknown *(void)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180016aa8`
- `0x1800215e8`
- `0x180024c08`
- `0x18002a470`

## pseudocode

```c
struct IUnknown *CreateFormatConverterNChannel(void)
{
  struct IUnknown *result; // rax

  CFormatConverterNChannel::InitConversionTable();
  result = (struct IUnknown *)operator new(0xE8u);
  if ( result )
    return (struct IUnknown *)CFormatConverterNChannel::CFormatConverterNChannel((CFormatConverterNChannel *)result);
  return result;
}

```

## disassembly

```asm
0x18002a470  sub     rsp, 28h
0x18002a474  call    ?InitConversionTable@CFormatConverterNChannel@@SAJXZ; CFormatConverterNChannel::InitConversionTable(void)
0x18002a479  mov     ecx, 0E8h; Size
0x18002a47e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002a483  test    rax, rax
0x18002a486  jz      short loc_18002A494
0x18002a488  mov     rcx, rax; this
0x18002a48b  add     rsp, 28h
0x18002a48f  jmp     ??0CFormatConverterNChannel@@QEAA@XZ; CFormatConverterNChannel::CFormatConverterNChannel(void)
0x18002a494  add     rsp, 28h
0x18002a498  retn
```
