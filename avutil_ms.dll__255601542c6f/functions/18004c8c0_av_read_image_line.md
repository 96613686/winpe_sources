# av_read_image_line

- ea: `0x18004c8c0`
- end: `0x18004c90d`
- name: `av_read_image_line`
- size: `77`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18004c910`

## pseudocode

```c
unsigned __int64 __fastcall av_read_image_line(
        _WORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        int a6,
        int a7,
        int a8,
        int a9)
{
  return av_read_image_line2(a1, a2, a3, a4, a5, a6, a7, a8, a9, 2);
}

```

## disassembly

```asm
0x18004c8c0  sub     rsp, 58h
0x18004c8c4  mov     eax, [rsp+58h+arg_40]
0x18004c8cb  mov     [rsp+58h+var_10], 2
0x18004c8d3  mov     [rsp+58h+var_18], eax
0x18004c8d7  mov     eax, [rsp+58h+arg_38]
0x18004c8de  mov     [rsp+58h+var_20], eax
0x18004c8e2  mov     eax, [rsp+58h+arg_30]
0x18004c8e9  mov     [rsp+58h+var_28], eax
0x18004c8ed  mov     eax, [rsp+58h+arg_28]
0x18004c8f4  mov     [rsp+58h+var_30], eax
0x18004c8f8  mov     eax, [rsp+58h+arg_20]
0x18004c8ff  mov     [rsp+58h+var_38], eax
0x18004c903  call    av_read_image_line2
0x18004c908  add     rsp, 58h
0x18004c90c  retn
```
