# WMDSPPropMemSize(ushort)

- ea: `0x180083768`
- end: `0x18008379c`
- name: `?WMDSPPropMemSize@@YAJG@Z`
- size: `52`
- prototype: `__int64 __fastcall(unsigned __int16)`
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180083b10`
- `0x180083cd0`

## callees

- `0x180083768`

## pseudocode

```c
__int64 __fastcall WMDSPPropMemSize(__int16 a1)
{
  __int64 result; // rax

  if ( a1 == 3 || a1 == 4 )
    return 4;
  result = 8;
  switch ( a1 )
  {
    case 5:
      return result;
    case 11:
      return 2;
    case 19:
      return 4;
  }
  if ( a1 != 20 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x180083768  movzx   edx, cx
0x18008376b  sub     edx, 3
0x18008376e  jz      short loc_180083796
0x180083770  sub     edx, 1
0x180083773  jz      short loc_180083796
0x180083775  mov     eax, 8
0x18008377a  sub     edx, 1
0x18008377d  jz      short locret_18008379B
0x18008377f  sub     edx, 6
0x180083782  jz      short loc_180083790
0x180083784  sub     edx, eax
0x180083786  jz      short loc_180083796
0x180083788  cmp     edx, 1
0x18008378b  jz      short locret_18008379B
0x18008378d  xor     eax, eax
0x18008378f  retn
0x180083790  mov     eax, 2
0x180083795  retn
0x180083796  mov     eax, 4
0x18008379b  retn
```
