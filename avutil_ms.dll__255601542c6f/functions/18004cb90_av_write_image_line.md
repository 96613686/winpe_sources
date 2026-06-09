# av_write_image_line

- ea: `0x18004cb90`
- end: `0x18004cbd2`
- name: `av_write_image_line`
- size: `66`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18004cbe0`

## pseudocode

```c
int __fastcall av_write_image_line(int *a1, __int64 a2, __int64 a3, __int64 a4, int a5, int a6, int a7, int a8)
{
  return av_write_image_line2(a1, a2, a3, a4, a5, a6, a7, a8, 2);
}

```

## disassembly

```asm
0x18004cb90  sub     rsp, 58h
0x18004cb94  mov     eax, [rsp+58h+arg_38]
0x18004cb9b  mov     [rsp+58h+var_18], 2
0x18004cba3  mov     [rsp+58h+var_20], eax
0x18004cba7  mov     eax, [rsp+58h+arg_30]
0x18004cbae  mov     [rsp+58h+var_28], eax
0x18004cbb2  mov     eax, [rsp+58h+arg_28]
0x18004cbb9  mov     [rsp+58h+var_30], eax
0x18004cbbd  mov     eax, [rsp+58h+arg_20]
0x18004cbc4  mov     [rsp+58h+var_38], eax
0x18004cbc8  call    av_write_image_line2
0x18004cbcd  add     rsp, 58h
0x18004cbd1  retn
```
