# WPP_SF_dddqd_CTDSTRW_

- ea: `0x18000c42c`
- end: `0x18000c4c6`
- name: `WPP_SF_dddqd_CTDSTRW_`
- size: `154`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180008b90`
- `0x1800097c4`

## callees

- `0x1800072e0`

## pseudocode

```c
ULONG __fastcall WPP_SF_dddqd_CTDSTRW_(
        __int64 a1,
        USHORT a2,
        __int64 a3,
        int a4,
        int a5,
        int a6,
        int a7,
        int a8,
        unsigned __int16 *a9)
{
  int v10; // [rsp+B8h] [rbp+20h] BYREF

  v10 = a4;
  return FastWppTraceMessage(
           1050,
           a2,
           (ULONGLONG)WPP_9757c9c47725323be14918a4f6df94b6_Traceguids,
           &v10,
           4,
           &a5,
           4,
           &a6,
           4,
           &a7,
           8,
           &a8,
           4,
           a9,
           2,
           *((_QWORD *)a9 + 1),
           *a9,
           0);
}

```

## disassembly

```asm
0x18000c42c  mov     r11, rsp
0x18000c42f  mov     [r11+20h], r9d
0x18000c433  sub     rsp, 98h
0x18000c43a  mov     rcx, [rsp+98h+arg_40]
0x18000c442  lea     r9, [r11+20h]
0x18000c446  mov     qword ptr [r11-10h], 0
0x18000c44e  lea     r8, WPP_9757c9c47725323be14918a4f6df94b6_Traceguids
0x18000c455  mov     r10d, 41Ah
0x18000c45b  movzx   edx, dx
0x18000c45e  movzx   eax, word ptr [rcx]
0x18000c461  mov     [r11-18h], rax
0x18000c465  mov     rax, [rcx+8]
0x18000c469  mov     [r11-20h], rax
0x18000c46d  lea     rax, [r11+40h]
0x18000c471  mov     qword ptr [r11-28h], 2
0x18000c479  mov     [r11-30h], rcx
0x18000c47d  mov     ecx, 4
0x18000c482  mov     [r11-38h], rcx
0x18000c486  mov     [r11-40h], rax
0x18000c48a  lea     rax, [r11+38h]
0x18000c48e  mov     qword ptr [r11-48h], 8
0x18000c496  mov     [r11-50h], rax
0x18000c49a  lea     rax, [r11+30h]
0x18000c49e  mov     [r11-58h], rcx
0x18000c4a2  mov     [r11-60h], rax
0x18000c4a6  lea     rax, [r11+28h]
0x18000c4aa  mov     [r11-68h], rcx
0x18000c4ae  mov     [r11-70h], rax
0x18000c4b2  mov     [r11-78h], rcx
0x18000c4b6  mov     ecx, r10d
0x18000c4b9  call    FastWppTraceMessage
0x18000c4be  add     rsp, 98h
0x18000c4c5  retn
```
