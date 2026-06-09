# MapPropCacheFlagToControlCode(ulong)

- ea: `0x1800109c4`
- end: `0x1800109e5`
- name: `?MapPropCacheFlagToControlCode@@YAKK@Z`
- size: `33`
- prototype: `unsigned int __fastcall(unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180006b00`
- `0x180006d90`

## callees

- `0x1800109c4`

## pseudocode

```c
__int64 __fastcall MapPropCacheFlagToControlCode(int a1)
{
  int v1; // ecx

  if ( !a1 )
    return 0;
  v1 = a1 - 1;
  if ( !v1 )
    return 2;
  if ( v1 == 1 )
    return 1;
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x1800109c4  test    ecx, ecx
0x1800109c6  jz      short loc_1800109E2
0x1800109c8  sub     ecx, 1
0x1800109cb  jz      short loc_1800109DC
0x1800109cd  cmp     ecx, 1
0x1800109d0  jz      short loc_1800109D6
0x1800109d2  or      eax, 0FFFFFFFFh
0x1800109d5  retn
0x1800109d6  mov     eax, 1
0x1800109db  retn
0x1800109dc  mov     eax, 2
0x1800109e1  retn
0x1800109e2  xor     eax, eax
0x1800109e4  retn
```
