# ipp_is_mmx_extension

- ea: `0x180010869`
- end: `0x180010882`
- name: `ipp_is_mmx_extension`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## pseudocode

```c
_BOOL8 ipp_is_mmx_extension()
{
  _RAX = 1;
  __asm { cpuid }
  return (_RDX & 0x800000) != 0;
}

```

## disassembly

```asm
0x180010869  push    rbx
0x18001086a  mov     rax, 1
0x180010871  cpuid
0x180010873  xor     rax, rax
0x180010876  test    rdx, 800000h
0x18001087d  setnz   al
0x180010880  pop     rbx
0x180010881  retn
```
