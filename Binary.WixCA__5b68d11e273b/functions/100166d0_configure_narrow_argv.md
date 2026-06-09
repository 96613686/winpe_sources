# __configure_narrow_argv

- ea: `0x100166d0`
- end: `0x100166db`
- name: `__configure_narrow_argv`
- size: `11`
- prototype: `errno_t __cdecl(_crt_argv_mode mode)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x10010d71`

## callees

- `0x100163d0`

## pseudocode

```c
errno_t __cdecl _configure_narrow_argv(_crt_argv_mode mode)
{
  return common_configure_argv<char>(mode);
}

```

## disassembly

```asm
0x100166d0  mov     edi, edi
0x100166d2  push    ebp
0x100166d3  mov     ebp, esp
0x100166d5  pop     ebp
0x100166d6  jmp     ??$common_configure_argv@D@@YAHW4_crt_argv_mode@@@Z
```
