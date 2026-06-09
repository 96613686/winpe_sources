# EdpIsPluginConfigPresent

- ea: `0x14002d170`
- end: `0x14002d182`
- name: `EdpIsPluginConfigPresent`
- size: `18`
- prototype: `bool __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x14002b5e0`
- `0x14002d18c`

## callees

- `0x14002d170`

## pseudocode

```c
bool __fastcall EdpIsPluginConfigPresent(__int64 a1)
{
  bool result; // al

  result = 0;
  if ( *(_BYTE *)a1 )
  {
    if ( *(_DWORD *)(a1 + 4) )
      return *(_DWORD *)(a1 + 32) != 0;
  }
  return result;
}

```

## disassembly

```asm
0x14002d170  xor     eax, eax
0x14002d172  cmp     [rcx], al
0x14002d174  jz      short locret_14002D181
0x14002d176  cmp     [rcx+4], eax
0x14002d179  jz      short locret_14002D181
0x14002d17b  cmp     [rcx+20h], eax
0x14002d17e  setnbe  al
0x14002d181  retn
```
