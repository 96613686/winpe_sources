# common_set_variable_in_environment_nolock<wchar_t>(wchar_t * const,int)

- ea: `0x140008194`
- end: `0x140008199`
- name: `j_??$common_set_variable_in_environment_nolock@_W@@YAHQEA_WH@Z`
- size: `5`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140004c98`

## callees

- `0x140007d40`

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
0x140008194  jmp     ??$common_set_variable_in_environment_nolock@_W@@YAHQEA_WH@Z
```
