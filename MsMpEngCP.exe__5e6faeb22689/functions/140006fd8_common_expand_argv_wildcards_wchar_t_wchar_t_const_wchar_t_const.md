# common_expand_argv_wildcards<wchar_t>(wchar_t * * const,wchar_t * * * const)

- ea: `0x140006fd8`
- end: `0x140006fdd`
- name: `j_??$common_expand_argv_wildcards@_W@@YAHQEAPEA_WQEAPEAPEA_W@Z`
- size: `5`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140004948`

## callees

- `0x1400069b4`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall common_expand_argv_wildcards<wchar_t>(const WCHAR **a1, __int64 *a2)
{
  return ??$common_expand_argv_wildcards@_W@@YAHQEAPEA_WQEAPEAPEA_W@Z(a1, a2);
}

```

## disassembly

```asm
0x140006fd8  jmp     ??$common_expand_argv_wildcards@_W@@YAHQEAPEA_WQEAPEAPEA_W@Z
```
