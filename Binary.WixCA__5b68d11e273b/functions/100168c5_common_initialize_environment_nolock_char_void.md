# common_initialize_environment_nolock<char>(void)

- ea: `0x100168c5`
- end: `0x100168ca`
- name: `j_??$common_initialize_environment_nolock@D@@YAHXZ`
- size: `5`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x10010d71`

## callees

- `0x100166db`

## pseudocode

```c
// attributes: thunk
int common_initialize_environment_nolock<char>(void)
{
  return ??$common_initialize_environment_nolock@D@@YAHXZ();
}

```

## disassembly

```asm
0x100168c5  jmp     ??$common_initialize_environment_nolock@D@@YAHXZ
```
