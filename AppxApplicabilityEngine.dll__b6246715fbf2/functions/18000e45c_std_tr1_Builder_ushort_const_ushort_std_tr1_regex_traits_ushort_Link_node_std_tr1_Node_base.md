# std::tr1::_Builder<ushort const *,ushort,std::tr1::regex_traits<ushort>>::_Link_node(std::tr1::_Node_base *)

- ea: `0x18000e45c`
- end: `0x18000e491`
- name: `?_Link_node@?$_Builder@PEBGGV?$regex_traits@G@tr1@std@@@tr1@std@@AEAAPEAV_Node_base@23@PEAV423@@Z`
- size: `53`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b8d8`
- `0x18000bb30`
- `0x18000f418`
- `0x180018120`
- `0x180018300`
- `0x18001865c`
- `0x180018b84`
- `0x180018c8c`
- `0x180018dd0`
- `0x180018ea4`
- `0x180018f08`

## callees

- `0x18000e45c`

## pseudocode

```c
__int64 __fastcall std::tr1::_Builder<unsigned short const *,unsigned short,std::tr1::regex_traits<unsigned short>>::_Link_node(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // r8
  __int64 result; // rax

  *(_QWORD *)(a2 + 24) = *(_QWORD *)(a1 + 8);
  v2 = *(_QWORD *)(*(_QWORD *)(a1 + 8) + 16LL);
  if ( v2 )
  {
    *(_QWORD *)(a2 + 16) = v2;
    *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 16LL) + 24LL) = a2;
  }
  *(_QWORD *)(*(_QWORD *)(a1 + 8) + 16LL) = a2;
  result = a2;
  *(_QWORD *)(a1 + 8) = a2;
  return result;
}

```

## disassembly

```asm
0x18000e45c  mov     rax, [rcx+8]
0x18000e460  mov     [rdx+18h], rax
0x18000e464  mov     rax, [rcx+8]
0x18000e468  mov     r8, [rax+10h]
0x18000e46c  test    r8, r8
0x18000e46f  jz      short loc_18000E481
0x18000e471  mov     [rdx+10h], r8
0x18000e475  mov     rax, [rcx+8]
0x18000e479  mov     r8, [rax+10h]
0x18000e47d  mov     [r8+18h], rdx
0x18000e481  mov     rax, [rcx+8]
0x18000e485  mov     [rax+10h], rdx
0x18000e489  mov     rax, rdx
0x18000e48c  mov     [rcx+8], rdx
0x18000e490  retn
```
