# DllUnload

- ea: `0x1800ed3c0`
- end: `0x1800ed3d6`
- name: `DllUnload`
- size: `22`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1800ed3ec`
- `0x1800f3918`

## pseudocode

```c
__int64 DllUnload()
{
  sub_1800F3918();
  sub_1800ED3EC();
  return 0;
}

```

## disassembly

```asm
0x1800ed3c0  sub     rsp, 28h
0x1800ed3c4  call    sub_1800F3918
0x1800ed3c9  call    sub_1800ED3EC
0x1800ed3ce  xor     eax, eax
0x1800ed3d0  add     rsp, 28h
0x1800ed3d4  retn
```
