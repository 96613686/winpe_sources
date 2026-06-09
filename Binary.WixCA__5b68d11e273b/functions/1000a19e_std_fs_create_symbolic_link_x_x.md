# __std_fs_create_symbolic_link(x,x)

- ea: `0x1000a19e`
- end: `0x1000a1b2`
- name: `___std_fs_create_symbolic_link@8`
- size: `20`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: `reparse_path`

## callers

- `0x100069b8`
- `0x1000ba7f`
- `0x1000c3df`
- `0x1000e439`
- `0x1000e662`
- `0x1000e78c`
- `0x1000e9ed`
- `0x1000eafc`
- `0x1000f269`
- `0x1000f9cc`

## callees

- `0x10009b18`

## pseudocode

```c
int __stdcall __std_fs_create_symbolic_link(int a1, int a2)
{
  return sub_10009B18(a1, a2, 0);
}

```

## disassembly

```asm
0x1000a19e  push    ebp
0x1000a19f  mov     ebp, esp
0x1000a1a1  push    0
0x1000a1a3  push    [ebp+arg_4]
0x1000a1a6  push    [ebp+arg_0]
0x1000a1a9  call    sub_10009B18
0x1000a1ae  pop     ebp
0x1000a1af  retn    8
```
