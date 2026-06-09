# ipp_is_sse41_extension

- ea: `0x18001f157`
- end: `0x18001f16c`
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
0x18001f157  push    rbx
0x18001f158  mov     eax, 1
0x18001f15d  cpuid
0x18001f15f  xor     eax, eax
0x18001f161  test    ecx, 80000h
0x18001f167  setnz   al
0x18001f16a  pop     rbx
0x18001f16b  retn
```
