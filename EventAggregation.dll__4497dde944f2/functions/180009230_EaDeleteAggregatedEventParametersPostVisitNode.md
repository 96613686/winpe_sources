# EaDeleteAggregatedEventParametersPostVisitNode

- ea: `0x180009230`
- end: `0x180009245`
- name: `EaDeleteAggregatedEventParametersPostVisitNode`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180009230`

## import_xrefs

- `ntdll!ZwDeleteKey` at `0x18000923e`

## pseudocode

```c
NTSTATUS __fastcall EaDeleteAggregatedEventParametersPostVisitNode(__int64 a1, void *a2)
{
  if ( a2 )
    return ZwDeleteKey(a2);
  else
    return -1073741811;
}

```

## disassembly

```asm
0x180009230  test    rdx, rdx
0x180009233  jnz     short loc_18000923B
0x180009235  mov     eax, 0C000000Dh
0x18000923a  retn
0x18000923b  mov     rcx, rdx
0x18000923e  jmp     cs:__imp_ZwDeleteKey
```
