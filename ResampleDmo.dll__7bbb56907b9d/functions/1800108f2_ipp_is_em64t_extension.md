# ipp_is_em64t_extension

- ea: `0x1800108f2`
- end: `0x180010912`
- name: `ipp_is_em64t_extension`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800108f2`

## pseudocode

```c
_BOOL8 ipp_is_em64t_extension()
{
  _BOOL8 result; // rax

  _RAX = 0x80000000LL;
  __asm { cpuid }
  if ( (unsigned int)result >= 0x80000001 )
  {
    _RAX = 2147483649LL;
    __asm { cpuid }
    return (_RDX & 0x20000000) != 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800108f2  push    rbx
0x1800108f3  mov     eax, 80000000h
0x1800108f8  cpuid
0x1800108fa  cmp     eax, 80000001h
0x1800108ff  jb      short loc_180010910
0x180010901  mov     eax, 80000001h
0x180010906  cpuid
0x180010908  shr     edx, 1Dh
0x18001090b  mov     eax, edx
0x18001090d  and     eax, 1
0x180010910  pop     rbx
0x180010911  retn
```
