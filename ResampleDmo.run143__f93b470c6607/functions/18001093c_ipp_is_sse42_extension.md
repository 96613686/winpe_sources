# ipp_is_sse42_extension

- ea: `0x18001093c`
- end: `0x180010951`
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
0x18001093c  push    rbx
0x18001093d  mov     eax, 1
0x180010942  cpuid
0x180010944  xor     eax, eax
0x180010946  test    ecx, 100000h
0x18001094c  setnz   al
0x18001094f  pop     rbx
0x180010950  retn
```
