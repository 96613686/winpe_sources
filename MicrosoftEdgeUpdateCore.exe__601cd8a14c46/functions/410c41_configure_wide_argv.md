# __configure_wide_argv

- ea: `0x410c41`
- end: `0x410c4c`
- name: `__configure_wide_argv`
- size: `11`
- prototype: `errno_t __cdecl(_crt_argv_mode mode)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x40d4f0`

## callees

- `0x41092f`

## pseudocode

```c
errno_t __cdecl _configure_wide_argv(_crt_argv_mode mode)
{
  return common_configure_argv<wchar_t>(mode);
}

```

## disassembly

```asm
0x410c41  mov     edi, edi
0x410c43  push    ebp
0x410c44  mov     ebp, esp
0x410c46  pop     ebp
0x410c47  jmp     ??$common_configure_argv@_W@@YAHW4_crt_argv_mode@@@Z
```
