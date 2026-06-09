# common_set_variable_in_environment_nolock<wchar_t>(wchar_t * const,int)

- ea: `0x14001e274`
- end: `0x14001e279`
- name: `j_??$common_set_variable_in_environment_nolock@_W@@YAHQEA_WH@Z`
- size: `5`
- prototype: `__int64 __fastcall(_WORD *Block, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140018258`

## callees

- `0x14001de20`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall common_set_variable_in_environment_nolock<wchar_t>(_WORD *Block, int a2)
{
  return ??$common_set_variable_in_environment_nolock@_W@@YAHQEA_WH@Z(Block, a2);
}

```

## disassembly

```asm
0x14001e274  jmp     ??$common_set_variable_in_environment_nolock@_W@@YAHQEA_WH@Z
```
