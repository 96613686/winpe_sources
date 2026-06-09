# IssueBulkRequest

- ea: `0x140001020`
- end: `0x14000114e`
- name: `IssueBulkRequest`
- size: `302`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x140007f80`
- `0x140009c10`
- `0x140009fe0`
- `0x14000be7c`

## callees

- `0x140001020`
- `0x140001408`
- `0x140001d6c`

## import_xrefs

- `ntoskrnl!IoSetActivityIdIrp` at `0x1400010fe`
- `ntoskrnl!IoSetActivityIdIrp` at `0x1400010fe`

## pseudocode

```c
__int64 __fastcall IssueBulkRequest(
        __int64 a1,
        __int64 a2,
        int a3,
        unsigned __int16 a4,
        __int64 a5,
        __int64 a6,
        int a7,
        int a8,
        __int64 a9)
{
  _QWORD *v12; // rdi
  __int64 v13; // [rsp+50h] [rbp-31h] BYREF
  _QWORD *v14; // [rsp+58h] [rbp-29h] BYREF
  __int64 v15; // [rsp+60h] [rbp-21h] BYREF
  __int64 v16; // [rsp+68h] [rbp-19h] BYREF
  _QWORD v17[8]; // [rsp+70h] [rbp-11h] BYREF

  v13 = 0;
  v16 = 0;
  v15 = 0;
  v17[0] = 0;
  v14 = 0;
  if ( (unsigned int)(a3 - 1) > 3 )
    return 3221225485LL;
  PrepareBulkRequest(a1, a3, a4, a8, (__int64)&v14, (__int64)&v13, (__int64)v17, (__int64)&v16, (__int64)&v15);
  v12 = v14;
  *v14 = a5;
  v12[1] = a2;
  v12[3] = a9;
  v12[4] = v15;
  v12[2] = MEMORY[0xFFFFF78000000014];
  if ( *(_BYTE *)(a2 + 184) )
    IoSetActivityIdIrp(v13, a2 + 168);
  return UaspIssueBulkOrInterruptRequest(a1, v13, v17[0], v16, a8, a7, a5, a6);
}

```

## disassembly

```asm
0x140001020  push    rbp
0x140001022  push    rbx
0x140001023  push    rsi
0x140001024  push    rdi
0x140001025  push    r14
0x140001027  push    r15
0x140001029  lea     rbp, [rsp-7]
0x14000102e  sub     rsp, 88h
0x140001035  lea     eax, [r8-1]
0x140001039  mov     [rbp+2Fh+var_60], 0
0x140001041  mov     [rbp+2Fh+var_48], 0
0x140001049  movzx   r11d, r9w
0x14000104d  mov     [rbp+2Fh+var_50], 0
0x140001055  mov     r10d, r8d
0x140001058  mov     [rbp+2Fh+var_40], 0
0x140001060  mov     rbx, rdx
0x140001063  mov     [rbp+2Fh+var_58], 0
0x14000106b  mov     rsi, rcx
0x14000106e  cmp     eax, 3
0x140001071  jbe     short loc_14000107D
0x140001073  mov     eax, 0C000000Dh
0x140001078  jmp     loc_14000113D
0x14000107d  mov     r14d, [rbp+2Fh+arg_38]
0x140001081  lea     rax, [rbp+2Fh+var_50]
0x140001085  mov     [rsp+0B0h+var_70], rax
0x14000108a  mov     r9d, r14d
0x14000108d  lea     rax, [rbp+2Fh+var_48]
0x140001091  movzx   r8d, r11w
0x140001095  mov     [rsp+0B0h+var_78], rax
0x14000109a  mov     edx, r10d
0x14000109d  lea     rax, [rbp+2Fh+var_40]
0x1400010a1  mov     [rsp+0B0h+var_80], rax
0x1400010a6  lea     rax, [rbp+2Fh+var_60]
0x1400010aa  mov     [rsp+0B0h+var_88], rax
0x1400010af  lea     rax, [rbp+2Fh+var_58]
0x1400010b3  mov     [rsp+0B0h+var_90], rax
0x1400010b8  call    PrepareBulkRequest
0x1400010bd  mov     rdi, [rbp+2Fh+var_58]
0x1400010c1  mov     rax, [rbp+2Fh+arg_40]
0x1400010c5  mov     r15, [rbp+2Fh+arg_20]
0x1400010c9  mov     [rdi], r15
0x1400010cc  mov     [rdi+8], rbx
0x1400010d0  mov     [rdi+18h], rax
0x1400010d4  mov     rax, [rbp+2Fh+var_50]
0x1400010d8  mov     [rdi+20h], rax
0x1400010dc  mov     rax, ds:0FFFFF78000000014h
0x1400010e6  mov     [rdi+10h], rax
0x1400010ea  cmp     byte ptr [rbx+0B8h], 0
0x1400010f1  jz      short loc_14000110A
0x1400010f3  mov     rcx, [rbp+2Fh+var_60]
0x1400010f7  lea     rdx, [rbx+0A8h]
0x1400010fe  call    cs:__imp_IoSetActivityIdIrp
0x140001105  nop     dword ptr [rax+rax+00h]
0x14000110a  mov     rax, [rbp+2Fh+arg_28]
0x14000110e  mov     rcx, rsi
0x140001111  mov     r9, [rbp+2Fh+var_48]
0x140001115  mov     r8, [rbp+2Fh+var_40]
0x140001119  mov     rdx, [rbp+2Fh+var_60]
0x14000111d  mov     [rsp+0B0h+var_68], rdi
0x140001122  mov     [rsp+0B0h+var_78], rax
0x140001127  mov     eax, [rbp+2Fh+arg_30]
0x14000112a  mov     [rsp+0B0h+var_80], r15
0x14000112f  mov     dword ptr [rsp+0B0h+var_88], eax
0x140001133  mov     dword ptr [rsp+0B0h+var_90], r14d
0x140001138  call    UaspIssueBulkOrInterruptRequest
0x14000113d  add     rsp, 88h
0x140001144  pop     r15
0x140001146  pop     r14
0x140001148  pop     rdi
0x140001149  pop     rsi
0x14000114a  pop     rbx
0x14000114b  pop     rbp
0x14000114c  retn
```
