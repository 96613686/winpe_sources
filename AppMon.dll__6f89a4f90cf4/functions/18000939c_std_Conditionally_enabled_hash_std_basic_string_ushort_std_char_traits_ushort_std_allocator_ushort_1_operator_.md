# std::_Conditionally_enabled_hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,1>::operator()(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18000939c`
- end: `0x1800093b5`
- name: `??R?$_Conditionally_enabled_hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$00@std@@SA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z`
- size: `25`
- prototype: `__int64 __fastcall(unsigned __int8 *)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x180007e5c`
- `0x180008428`
- `0x180009b90`
- `0x180009dc0`
- `0x18000a9a8`
- `0x18000ad94`
- `0x18000d96c`
- `0x18000dccc`

## callees

- `0x18000939c`
- `0x180009b54`

## pseudocode

```c
unsigned __int64 __fastcall std::_Conditionally_enabled_hash<std::wstring,1>::operator()(unsigned __int8 *a1)
{
  __int64 v1; // r8

  v1 = *((_QWORD *)a1 + 2);
  if ( *((_QWORD *)a1 + 3) > 7u )
    a1 = *(unsigned __int8 **)a1;
  return std::_Fnv1a_append_bytes((unsigned __int64)a1, a1, 2 * v1);
}

```

## disassembly

```asm
0x18000939c  cmp     qword ptr [rcx+18h], 7
0x1800093a1  mov     r8, [rcx+10h]
0x1800093a5  jbe     short loc_1800093AA
0x1800093a7  mov     rcx, [rcx]; unsigned __int64
0x1800093aa  add     r8, r8; unsigned __int64
0x1800093ad  mov     rdx, rcx; unsigned __int8 *
0x1800093b0  jmp     ?_Fnv1a_append_bytes@std@@YA_K_KQEBE_K@Z; std::_Fnv1a_append_bytes(unsigned __int64,uchar const * const,unsigned __int64)
```
