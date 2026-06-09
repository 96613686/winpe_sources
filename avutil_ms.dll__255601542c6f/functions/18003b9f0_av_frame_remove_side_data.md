# av_frame_remove_side_data

- ea: `0x18003b9f0`
- end: `0x18003ba06`
- name: `av_frame_remove_side_data`
- size: `22`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x180050c40`

## pseudocode

```c
__int64 __fastcall av_frame_remove_side_data(__int64 a1, int a2)
{
  return av_frame_side_data_remove((__int64 *)(a1 + 264), (int *)(a1 + 272), a2);
}

```

## disassembly

```asm
0x18003b9f0  mov     r8d, edx
0x18003b9f3  lea     rdx, [rcx+110h]
0x18003b9fa  add     rcx, 108h
0x18003ba01  jmp     av_frame_side_data_remove
```
