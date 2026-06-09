# av_image_copy_uc_from

- ea: `0x180040a40`
- end: `0x180040a75`
- name: `av_image_copy_uc_from`
- size: `53`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800417ac`

## pseudocode

```c
__int64 __fastcall av_image_copy_uc_from(int a1, int a2, int a3, int a4, int a5, int a6, int a7)
{
  return sub_1800417AC(a1, a2, a3, a4, a5, a6, a7, (__int64)av_image_copy_plane_uc_from);
}

```

## disassembly

```asm
0x180040a40  sub     rsp, 48h
0x180040a44  lea     rax, av_image_copy_plane_uc_from
0x180040a4b  mov     [rsp+48h+var_10], rax
0x180040a50  mov     eax, [rsp+48h+arg_30]
0x180040a57  mov     [rsp+48h+var_18], eax
0x180040a5b  mov     eax, [rsp+48h+arg_28]
0x180040a5f  mov     [rsp+48h+var_20], eax
0x180040a63  mov     eax, [rsp+48h+arg_20]
0x180040a67  mov     [rsp+48h+var_28], eax
0x180040a6b  call    sub_1800417AC
0x180040a70  add     rsp, 48h
0x180040a74  retn
```
