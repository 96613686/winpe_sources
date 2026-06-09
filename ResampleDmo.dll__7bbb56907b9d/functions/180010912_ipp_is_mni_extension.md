# ipp_is_mni_extension

- ea: `0x180010912`
- end: `0x180010927`
- name: `ipp_is_mni_extension`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## pseudocode

```c
_BOOL8 ipp_is_mni_extension()
{
  _RAX = 1;
  __asm { cpuid }
  return (_RCX & 0x200) != 0;
}

```

## disassembly

```asm
0x180010912  push    rbx
0x180010913  mov     eax, 1
0x180010918  cpuid
0x18001091a  xor     eax, eax
0x18001091c  test    ecx, 200h
0x180010922  setnz   al
0x180010925  pop     rbx
0x180010926  retn
```
