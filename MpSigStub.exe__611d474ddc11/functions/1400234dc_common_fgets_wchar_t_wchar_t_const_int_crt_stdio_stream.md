# common_fgets<wchar_t>(wchar_t * const,int,__crt_stdio_stream)

- ea: `0x1400234dc`
- end: `0x1400234e1`
- name: `j_??$common_fgets@_W@@YAPEA_WQEA_WHV__crt_stdio_stream@@@Z`
- size: `5`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400a36d8`

## callees

- `0x140023408`

## pseudocode

```c
// attributes: thunk
_WORD *__fastcall common_fgets<wchar_t>(_WORD *a1, int a2, FILE *a3)
{
  return ??$common_fgets@_W@@YAPEA_WQEA_WHV__crt_stdio_stream@@@Z(a1, a2, a3);
}

```

## disassembly

```asm
0x1400234dc  jmp     ??$common_fgets@_W@@YAPEA_WQEA_WHV__crt_stdio_stream@@@Z
```
