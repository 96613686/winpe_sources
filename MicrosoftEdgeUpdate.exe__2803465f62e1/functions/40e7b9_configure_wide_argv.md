# __configure_wide_argv

- ea: `0x40e7b9`
- end: `0x40e7c4`
- name: `__configure_wide_argv`
- size: `11`
- prototype: `errno_t __cdecl(_crt_argv_mode mode)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x40b630`

## callees

- `0x40e4a7`

## pseudocode

```c
errno_t __cdecl _configure_wide_argv(_crt_argv_mode mode)
{
  return common_configure_argv<wchar_t>(mode);
}

```

## disassembly

```asm
0x40e7b9  mov     edi, edi
0x40e7bb  push    ebp
0x40e7bc  mov     ebp, esp
0x40e7be  pop     ebp
0x40e7bf  jmp     ??$common_configure_argv@_W@@YAHW4_crt_argv_mode@@@Z
```
