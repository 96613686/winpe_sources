# ipp_is_ssx_extension

- ea: `0x18001f0b2`
- end: `0x18001f0cb`
- name: `ipp_is_ssx_extension`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## pseudocode

```c
_BOOL8 ipp_is_ssx_extension()
{
  _RAX = 1;
  __asm { cpuid }
  return (_RDX & 0x2000000) != 0;
}

```

## disassembly

```asm
0x18001f0b2  push    rbx
0x18001f0b3  mov     rax, 1
0x18001f0ba  cpuid
0x18001f0bc  xor     rax, rax
0x18001f0bf  test    rdx, 2000000h
0x18001f0c6  setnz   al
0x18001f0c9  pop     rbx
0x18001f0ca  retn
```
