# ipp_is_pni_extension

- ea: `0x1800108d9`
- end: `0x1800108f2`
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
0x1800108d9  push    rbx
0x1800108da  mov     rax, 1
0x1800108e1  cpuid
0x1800108e3  xor     rax, rax
0x1800108e6  test    rcx, 1
0x1800108ed  setnz   al
0x1800108f0  pop     rbx
0x1800108f1  retn
```
