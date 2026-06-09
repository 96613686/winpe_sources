# CreateFormatConverterWMPhoto(void)

- ea: `0x18002b260`
- end: `0x18002b284`
- name: `?CreateFormatConverterWMPhoto@@YAPEAUIUnknown@@XZ`
- size: `36`
- prototype: `struct IUnknown *(void)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800215e8`
- `0x18002b05c`
- `0x18002b260`

## pseudocode

```c
struct IUnknown *CreateFormatConverterWMPhoto(void)
{
  struct IUnknown *result; // rax

  result = (struct IUnknown *)operator new(0x98u);
  if ( result )
    return (struct IUnknown *)CFormatConverterWMPhoto::CFormatConverterWMPhoto((CFormatConverterWMPhoto *)result);
  return result;
}

```

## disassembly

```asm
0x18002b260  sub     rsp, 28h
0x18002b264  mov     ecx, 98h; Size
0x18002b269  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002b26e  test    rax, rax
0x18002b271  jz      short loc_18002B27F
0x18002b273  mov     rcx, rax; this
0x18002b276  add     rsp, 28h
0x18002b27a  jmp     ??0CFormatConverterWMPhoto@@QEAA@XZ; CFormatConverterWMPhoto::CFormatConverterWMPhoto(void)
0x18002b27f  add     rsp, 28h
0x18002b283  retn
```
