# ipp_is_mni_extension

- ea: `0x18001f142`
- end: `0x18001f157`
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
0x18001f142  push    rbx
0x18001f143  mov     eax, 1
0x18001f148  cpuid
0x18001f14a  xor     eax, eax
0x18001f14c  test    ecx, 200h
0x18001f152  setnz   al
0x18001f155  pop     rbx
0x18001f156  retn
```
