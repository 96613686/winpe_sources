# ipp_is_em64t_extension

- ea: `0x18001f122`
- end: `0x18001f142`
- name: `ipp_is_em64t_extension`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001f122`

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
0x18001f122  push    rbx
0x18001f123  mov     eax, 80000000h
0x18001f128  cpuid
0x18001f12a  cmp     eax, 80000001h
0x18001f12f  jb      short loc_18001F140
0x18001f131  mov     eax, 80000001h
0x18001f136  cpuid
0x18001f138  shr     edx, 1Dh
0x18001f13b  mov     eax, edx
0x18001f13d  and     eax, 1
0x18001f140  pop     rbx
0x18001f141  retn
```
