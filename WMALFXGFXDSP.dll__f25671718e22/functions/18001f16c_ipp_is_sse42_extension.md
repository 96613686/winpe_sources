# ipp_is_sse42_extension

- ea: `0x18001f16c`
- end: `0x18001f181`
- name: `ipp_is_sse42_extension`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## pseudocode

```c
_BOOL8 ipp_is_sse42_extension()
{
  _RAX = 1;
  __asm { cpuid }
  return (_RCX & 0x100000) != 0;
}

```

## disassembly

```asm
0x18001f16c  push    rbx
0x18001f16d  mov     eax, 1
0x18001f172  cpuid
0x18001f174  xor     eax, eax
0x18001f176  test    ecx, 100000h
0x18001f17c  setnz   al
0x18001f17f  pop     rbx
0x18001f180  retn
```
