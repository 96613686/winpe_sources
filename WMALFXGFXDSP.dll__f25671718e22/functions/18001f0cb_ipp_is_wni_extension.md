# ipp_is_wni_extension

- ea: `0x18001f0cb`
- end: `0x18001f0e4`
- name: `ipp_is_wni_extension`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## pseudocode

```c
_BOOL8 ipp_is_wni_extension()
{
  _RAX = 1;
  __asm { cpuid }
  return (_RDX & 0x4000000) != 0;
}

```

## disassembly

```asm
0x18001f0cb  push    rbx
0x18001f0cc  mov     rax, 1
0x18001f0d3  cpuid
0x18001f0d5  xor     rax, rax
0x18001f0d8  test    rdx, 4000000h
0x18001f0df  setnz   al
0x18001f0e2  pop     rbx
0x18001f0e3  retn
```
