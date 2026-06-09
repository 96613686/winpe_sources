# _GetImageBase

- ea: `0x140002c18`
- end: `0x140002c2a`
- name: `_GetImageBase`
- size: `18`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x140002e0c`
- `0x1400030c0`
- `0x140003198`
- `0x14000369c`
- `0x140003900`
- `0x140003a20`
- `0x140003fe4`
- `0x14000420c`
- `0x1400042f4`

## callees

- `0x140002260`

## pseudocode

```c
__int64 GetImageBase()
{
  return *(_QWORD *)(sub_140002260() + 96);
}

```

## disassembly

```asm
0x140002c18  sub     rsp, 28h
0x140002c1c  call    sub_140002260
0x140002c21  mov     rax, [rax+60h]
0x140002c25  add     rsp, 28h
0x140002c29  retn
```
