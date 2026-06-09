# av_image_copy

- ea: `0x1800406f0`
- end: `0x180040760`
- name: `av_image_copy`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18003c258`

## callees

- `0x1800406f0`
- `0x1800417ac`

## pseudocode

```c
__int64 __fastcall av_image_copy(int a1, __int64 a2, int a3, int *a4, int a5, int a6, int a7)
{
  __int64 v7; // rdx
  __int64 i; // r10
  __int64 v9; // rax
  _QWORD v11[4]; // [rsp+40h] [rbp-48h] BYREF
  _QWORD v12[5]; // [rsp+60h] [rbp-28h] BYREF

  v7 = a2 - (_QWORD)a4;
  for ( i = 0; i < 4; ++i )
  {
    v12[i] = *(int *)((char *)a4 + v7);
    v9 = *a4++;
    v11[i] = v9;
  }
  return sub_1800417AC(a1, (unsigned int)v12, a3, (unsigned int)v11, a5, a6, a7, (__int64)sub_180041950);
}

```

## disassembly

```asm
0x1800406f0  sub     rsp, 88h
0x1800406f7  sub     rdx, r9
0x1800406fa  xor     r10d, r10d
0x1800406fd  movsxd  rax, dword ptr [r9+rdx]
0x180040701  mov     [rsp+r10+88h+var_28], rax
0x180040706  movsxd  rax, dword ptr [r9]
0x180040709  lea     r9, [r9+4]
0x18004070d  mov     [rsp+r10+88h+var_48], rax
0x180040712  add     r10, 8
0x180040716  cmp     r10, 20h ; ' '
0x18004071a  jl      short loc_1800406FD
0x18004071c  lea     rax, sub_180041950
0x180040723  mov     [rsp+88h+var_50], rax
0x180040728  lea     r9, [rsp+88h+var_48]
0x18004072d  mov     eax, [rsp+88h+arg_30]
0x180040734  lea     rdx, [rsp+88h+var_28]
0x180040739  mov     [rsp+88h+var_58], eax
0x18004073d  mov     eax, [rsp+88h+arg_28]
0x180040744  mov     [rsp+88h+var_60], eax
0x180040748  mov     eax, [rsp+88h+arg_20]
0x18004074f  mov     [rsp+88h+var_68], eax
0x180040753  call    sub_1800417AC
0x180040758  add     rsp, 88h
0x18004075f  retn
```
