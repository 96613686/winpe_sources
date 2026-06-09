# ipp_is_wni_extension

- ea: `0x18001089b`
- end: `0x1800108b4`
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
0x18001089b  push    rbx
0x18001089c  mov     rax, 1
0x1800108a3  cpuid
0x1800108a5  xor     rax, rax
0x1800108a8  test    rdx, 4000000h
0x1800108af  setnz   al
0x1800108b2  pop     rbx
0x1800108b3  retn
```
