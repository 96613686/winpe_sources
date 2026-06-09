# ipp_is_sse41_extension

- ea: `0x180010927`
- end: `0x18001093c`
- name: `ipp_is_sse41_extension`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## pseudocode

```c
_BOOL8 ipp_is_sse41_extension()
{
  _RAX = 1;
  __asm { cpuid }
  return (_RCX & 0x80000) != 0;
}

```

## disassembly

```asm
0x180010927  push    rbx
0x180010928  mov     eax, 1
0x18001092d  cpuid
0x18001092f  xor     eax, eax
0x180010931  test    ecx, 80000h
0x180010937  setnz   al
0x18001093a  pop     rbx
0x18001093b  retn
```
