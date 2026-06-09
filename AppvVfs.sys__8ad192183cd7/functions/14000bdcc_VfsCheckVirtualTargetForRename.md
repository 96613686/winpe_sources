# VfsCheckVirtualTargetForRename

- ea: `0x14000bdcc`
- end: `0x14000be35`
- name: `VfsCheckVirtualTargetForRename`
- size: `105`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, unsigned int *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14000c574`
- `0x14000cfd8`

## callees

- `0x14000bbf4`

## pseudocode

```c
__int64 __fastcall VfsCheckVirtualTargetForRename(__int64 a1, __int64 a2, __int64 a3, __int64 a4, unsigned int *a5)
{
  return VfsCheckTargetForRename(
           a1,
           *(struct _FLT_INSTANCE **)(a3 + 40),
           *(_QWORD *)(a3 + 56),
           a2 + 88,
           *(PFLT_INSTANCE *)(a3 + 64),
           *(_QWORD *)(a3 + 80),
           a2 + 88,
           *(_QWORD *)(a3 + 24) + 220LL,
           *(_QWORD *)(a3 + 24) + 152LL,
           a4,
           a5);
}

```

## disassembly

```asm
0x14000bdcc  push    rbx
0x14000bdce  sub     rsp, 60h
0x14000bdd2  mov     rax, [r8+18h]
0x14000bdd6  lea     r11, [rdx+58h]
0x14000bdda  mov     rbx, r8
0x14000bddd  lea     rdx, [rax+98h]
0x14000bde4  lea     r10, [rax+0DCh]
0x14000bdeb  mov     rax, [rsp+68h+arg_20]
0x14000bdf3  mov     [rsp+68h+var_18], rax
0x14000bdf8  mov     rax, [r8+50h]
0x14000bdfc  mov     [rsp+68h+var_20], r9
0x14000be01  mov     r9, r11
0x14000be04  mov     [rsp+68h+var_28], rdx
0x14000be09  mov     rdx, [rbx+28h]
0x14000be0d  mov     [rsp+68h+var_30], r10
0x14000be12  mov     [rsp+68h+var_38], r11
0x14000be17  mov     [rsp+68h+var_40], rax
0x14000be1c  mov     rax, [r8+40h]
0x14000be20  mov     r8, [r8+38h]
0x14000be24  mov     [rsp+68h+var_48], rax
0x14000be29  call    VfsCheckTargetForRename
0x14000be2e  add     rsp, 60h
0x14000be32  pop     rbx
0x14000be33  retn
```
