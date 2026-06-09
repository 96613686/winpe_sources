# ipp_is_pni_extension

- ea: `0x18001f109`
- end: `0x18001f122`
- name: `ipp_is_pni_extension`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## pseudocode

```c
_BOOL8 ipp_is_pni_extension()
{
  _RAX = 1;
  __asm { cpuid }
  return (_RCX & 1) != 0;
}

```

## disassembly

```asm
0x18001f109  push    rbx
0x18001f10a  mov     rax, 1
0x18001f111  cpuid
0x18001f113  xor     rax, rax
0x18001f116  test    rcx, 1
0x18001f11d  setnz   al
0x18001f120  pop     rbx
0x18001f121  retn
```
