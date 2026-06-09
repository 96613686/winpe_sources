# WPP_SF_dddddqd_CTDSTRW_

- ea: `0x18000c370`
- end: `0x18000c425`
- name: `WPP_SF_dddddqd_CTDSTRW_`
- size: `181`
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
ULONG __fastcall WPP_SF_dddddqd_CTDSTRW_(
        __int64 a1,
        USHORT a2,
        __int64 a3,
        int a4,
        int a5,
        int a6,
        int a7,
        int a8,
        int a9,
        int a10,
        unsigned __int16 *a11)
{
  int v12; // [rsp+D8h] [rbp+20h] BYREF

  v12 = a4;
  return FastWppTraceMessage(
           1050,
           a2,
           (ULONGLONG)WPP_9757c9c47725323be14918a4f6df94b6_Traceguids,
           &v12,
           4,
           &a5,
           4,
           &a6,
           4,
           &a7,
           4,
           &a8,
           4,
           &a9,
           8,
           &a10,
           4,
           a11,
           2,
           *((_QWORD *)a11 + 1),
           *a11,
           0);
}

```

## disassembly

```asm
0x18000c370  mov     r11, rsp
0x18000c373  mov     [r11+20h], r9d
0x18000c377  sub     rsp, 0B8h
0x18000c37e  mov     rcx, [rsp+0B8h+arg_50]
0x18000c386  lea     r9, [r11+20h]
0x18000c38a  mov     qword ptr [r11-10h], 0
0x18000c392  lea     r8, WPP_9757c9c47725323be14918a4f6df94b6_Traceguids
0x18000c399  mov     r10d, 41Ah
0x18000c39f  movzx   edx, dx
0x18000c3a2  movzx   eax, word ptr [rcx]
0x18000c3a5  mov     [r11-18h], rax
0x18000c3a9  mov     rax, [rcx+8]
0x18000c3ad  mov     [r11-20h], rax
0x18000c3b1  lea     rax, [r11+50h]
0x18000c3b5  mov     qword ptr [r11-28h], 2
0x18000c3bd  mov     [r11-30h], rcx
0x18000c3c1  mov     ecx, 4
0x18000c3c6  mov     [r11-38h], rcx
0x18000c3ca  mov     [r11-40h], rax
0x18000c3ce  lea     rax, [r11+48h]
0x18000c3d2  mov     qword ptr [r11-48h], 8
0x18000c3da  mov     [r11-50h], rax
0x18000c3de  lea     rax, [r11+40h]
0x18000c3e2  mov     [r11-58h], rcx
0x18000c3e6  mov     [r11-60h], rax
0x18000c3ea  lea     rax, [r11+38h]
0x18000c3ee  mov     [r11-68h], rcx
0x18000c3f2  mov     [r11-70h], rax
0x18000c3f6  lea     rax, [r11+30h]
0x18000c3fa  mov     [r11-78h], rcx
0x18000c3fe  mov     [r11-80h], rax
0x18000c402  lea     rax, [r11+28h]
0x18000c406  mov     [rsp+0B8h+var_88], rcx
0x18000c40b  mov     [rsp+0B8h+var_90], rax
0x18000c410  mov     [rsp+0B8h+var_98], rcx
0x18000c415  mov     ecx, r10d
0x18000c418  call    FastWppTraceMessage
0x18000c41d  add     rsp, 0B8h
0x18000c424  retn
```
