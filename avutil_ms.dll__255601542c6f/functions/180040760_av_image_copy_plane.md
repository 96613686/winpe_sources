# av_image_copy_plane

- ea: `0x180040760`
- end: `0x180040775`
- name: `av_image_copy_plane`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180041950`

## pseudocode

```c
__int64 __fastcall av_image_copy_plane(int a1, int a2, int a3, int a4, __int64 a5, int a6)
{
  return sub_180041950(a1, a2, a3, a4, (int)a5, a6);
}

```

## disassembly

```asm
0x180040760  movsxd  r10, dword ptr [rsp+arg_20]
0x180040765  movsxd  r9, r9d
0x180040768  movsxd  rdx, edx
0x18004076b  mov     [rsp+arg_20], r10
0x180040770  jmp     sub_180041950
```
