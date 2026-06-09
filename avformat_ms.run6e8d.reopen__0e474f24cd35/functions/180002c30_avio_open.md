# avio_open

- ea: `0x180002c30`
- end: `0x180002c52`
- name: `avio_open`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800030bc`

## pseudocode

```c
__int64 __fastcall avio_open(int a1, int a2, int a3)
{
  return sub_1800030BC(a1, a2, a3, 0, 0, 0, 0);
}

```

## disassembly

```asm
0x180002c30  sub     rsp, 48h
0x180002c34  xor     eax, eax
0x180002c36  xor     r9d, r9d
0x180002c39  mov     [rsp+48h+var_18], rax
0x180002c3e  mov     [rsp+48h+var_20], rax
0x180002c43  mov     [rsp+48h+var_28], rax
0x180002c48  call    sub_1800030BC
0x180002c4d  add     rsp, 48h
0x180002c51  retn
```
