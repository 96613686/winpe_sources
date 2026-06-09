# ___std_fs_create_symbolic_link@8_0

- ea: `0x1000ad18`
- end: `0x1000ad2c`
- name: `___std_fs_create_symbolic_link@8_0`
- size: `20`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `reparse_path`

## callers

- `0x100025ae`
- `0x1000265c`
- `0x1000bc7e`

## callees

- `0x1000ad2c`

## pseudocode

```c
int __stdcall __std_fs_create_symbolic_link(int a1, HMODULE *a2)
{
  return sub_1000AD2C(a1, a2, 0);
}

```

## disassembly

```asm
0x1000ad18  push    ebp
0x1000ad19  mov     ebp, esp
0x1000ad1b  push    0
0x1000ad1d  push    [ebp+arg_4]
0x1000ad20  push    [ebp+arg_0]
0x1000ad23  call    sub_1000AD2C
0x1000ad28  pop     ebp
0x1000ad29  retn    8
```
