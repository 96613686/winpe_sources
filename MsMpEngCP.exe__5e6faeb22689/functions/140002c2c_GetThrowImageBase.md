# _GetThrowImageBase

- ea: `0x140002c2c`
- end: `0x140002c3e`
- name: `_GetThrowImageBase`
- size: `18`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x140002e0c`
- `0x140003000`
- `0x140003198`
- `0x140003900`
- `0x140003a20`
- `0x14000420c`

## callees

- `0x140002260`

## pseudocode

```c
__int64 GetThrowImageBase()
{
  return *(_QWORD *)(sub_140002260() + 104);
}

```

## disassembly

```asm
0x140002c2c  sub     rsp, 28h
0x140002c30  call    sub_140002260
0x140002c35  mov     rax, [rax+68h]
0x140002c39  add     rsp, 28h
0x140002c3d  retn
```
