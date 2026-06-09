# common_expand_argv_wildcards<wchar_t>(wchar_t * * const,wchar_t * * * const)

- ea: `0x14001dc0c`
- end: `0x14001dc11`
- name: `j_??$common_expand_argv_wildcards@_W@@YAHQEAPEA_WQEAPEAPEA_W@Z`
- size: `5`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140017f08`

## callees

- `0x14001d684`

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
0x14001dc0c  jmp     ??$common_expand_argv_wildcards@_W@@YAHQEAPEA_WQEAPEAPEA_W@Z
```
