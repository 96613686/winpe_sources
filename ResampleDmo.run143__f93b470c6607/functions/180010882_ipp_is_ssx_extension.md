# ipp_is_ssx_extension

- ea: `0x180010882`
- end: `0x18001089b`
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
0x180010882  push    rbx
0x180010883  mov     rax, 1
0x18001088a  cpuid
0x18001088c  xor     rax, rax
0x18001088f  test    rdx, 2000000h
0x180010896  setnz   al
0x180010899  pop     rbx
0x18001089a  retn
```
