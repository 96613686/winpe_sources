# WPP_SF_ddlllllllllldddddd

- ea: `0x1800163e0`
- end: `0x18001653c`
- name: `WPP_SF_ddlllllllllldddddd`
- size: `348`
- prototype: `ULONG(__int64, __int64, __int64, int, ...)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000fb40`

## callees

- `0x1800014b0`
- `0x18000b794`

## pseudocode

```c
ULONG WPP_SF_ddlllllllllldddddd(__int64 a1, __int64 a2, __int64 a3, int a4, ...)
{
  int v5; // [rsp+148h] [rbp-80h] BYREF
  __int64 v6; // [rsp+188h] [rbp-40h] BYREF
  va_list va; // [rsp+188h] [rbp-40h]
  __int64 v8; // [rsp+190h] [rbp-38h] BYREF
  va_list va1; // [rsp+190h] [rbp-38h]
  __int64 v10; // [rsp+198h] [rbp-30h] BYREF
  va_list va2; // [rsp+198h] [rbp-30h]
  __int64 v12; // [rsp+1A0h] [rbp-28h] BYREF
  va_list va3; // [rsp+1A0h] [rbp-28h]
  __int64 v14; // [rsp+1A8h] [rbp-20h] BYREF
  va_list va4; // [rsp+1A8h] [rbp-20h]
  __int64 v16; // [rsp+1B0h] [rbp-18h] BYREF
  va_list va5; // [rsp+1B0h] [rbp-18h]
  __int64 v18; // [rsp+1B8h] [rbp-10h] BYREF
  va_list va6; // [rsp+1B8h] [rbp-10h]
  __int64 v20; // [rsp+1C0h] [rbp-8h] BYREF
  va_list va7; // [rsp+1C0h] [rbp-8h]
  __int64 v22; // [rsp+1C8h] [rbp+0h] BYREF
  va_list va8; // [rsp+1C8h] [rbp+0h]
  __int64 v24; // [rsp+1D0h] [rbp+8h] BYREF
  va_list va9; // [rsp+1D0h] [rbp+8h]
  __int64 v26; // [rsp+1D8h] [rbp+10h] BYREF
  va_list va10; // [rsp+1D8h] [rbp+10h]
  __int64 v28; // [rsp+1E0h] [rbp+18h] BYREF
  va_list va11; // [rsp+1E0h] [rbp+18h]
  __int64 v30; // [rsp+1E8h] [rbp+20h] BYREF
  va_list va12; // [rsp+1E8h] [rbp+20h]
  __int64 v32; // [rsp+1F0h] [rbp+28h] BYREF
  va_list va13; // [rsp+1F0h] [rbp+28h]
  __int64 v34; // [rsp+1F8h] [rbp+30h] BYREF
  va_list va14; // [rsp+1F8h] [rbp+30h]
  __int64 v36; // [rsp+200h] [rbp+38h] BYREF
  va_list va15; // [rsp+200h] [rbp+38h]
  va_list va16; // [rsp+208h] [rbp+40h] BYREF

  va_start(va16, a4);
  va_start(va15, a4);
  va_start(va14, a4);
  va_start(va13, a4);
  va_start(va12, a4);
  va_start(va11, a4);
  va_start(va10, a4);
  va_start(va9, a4);
  va_start(va8, a4);
  va_start(va7, a4);
  va_start(va6, a4);
  va_start(va5, a4);
  va_start(va4, a4);
  va_start(va3, a4);
  va_start(va2, a4);
  va_start(va1, a4);
  va_start(va, a4);
  v6 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v8 = va_arg(va2, _QWORD);
  va_copy(va3, va2);
  v10 = va_arg(va3, _QWORD);
  va_copy(va4, va3);
  v12 = va_arg(va4, _QWORD);
  va_copy(va5, va4);
  v14 = va_arg(va5, _QWORD);
  va_copy(va6, va5);
  v16 = va_arg(va6, _QWORD);
  va_copy(va7, va6);
  v18 = va_arg(va7, _QWORD);
  va_copy(va8, va7);
  v20 = va_arg(va8, _QWORD);
  va_copy(va9, va8);
  v22 = va_arg(va9, _QWORD);
  va_copy(va10, va9);
  v24 = va_arg(va10, _QWORD);
  va_copy(va11, va10);
  v26 = va_arg(va11, _QWORD);
  va_copy(va12, va11);
  v28 = va_arg(va12, _QWORD);
  va_copy(va13, va12);
  v30 = va_arg(va13, _QWORD);
  va_copy(va14, va13);
  v32 = va_arg(va14, _QWORD);
  va_copy(va15, va14);
  v34 = va_arg(va15, _QWORD);
  va_copy(va16, va15);
  v36 = va_arg(va16, _QWORD);
  v5 = a4;
  return FastWppTraceMessage(
           1035,
           0x16u,
           (ULONGLONG)WPP_7eb1482970b13f51d23b3992b8531bf6_Traceguids,
           &v5,
           4,
           va,
           4,
           va1,
           4,
           va2,
           4,
           va3,
           4,
           va4,
           4,
           va5,
           4,
           va6,
           4,
           va7,
           4,
           va8,
           4,
           va9,
           4,
           va10,
           4,
           va11,
           4,
           va12,
           4,
           va13,
           4,
           va14,
           4,
           va15,
           4,
           va16,
           4,
           0);
}

```

## disassembly

```asm
0x1800163e0  mov     r11, rsp
0x1800163e3  push    rbp
0x1800163e4  lea     rbp, [r11+68h]
0x1800163e8  sub     rsp, 150h
0x1800163ef  mov     rax, cs:__security_cookie
0x1800163f6  xor     rax, rsp
0x1800163f9  mov     [rbp-70h+var_8], rax
0x1800163fd  mov     qword ptr [r11-20h], 0
0x180016405  lea     rax, [rbp-70h+arg_A0]
0x180016409  mov     edx, 16h
0x18001640e  mov     [rbp-70h+var_10], r9d
0x180016412  mov     r10d, 40Bh
0x180016418  lea     r9, [rbp-70h+var_10]
0x18001641c  lea     r8, WPP_7eb1482970b13f51d23b3992b8531bf6_Traceguids
0x180016423  lea     ecx, [rdx-12h]
0x180016426  mov     [r11-28h], rcx
0x18001642a  mov     [r11-30h], rax
0x18001642e  lea     rax, [rbp-70h+arg_98]
0x180016432  mov     [r11-38h], rcx
0x180016436  mov     [r11-40h], rax
0x18001643a  lea     rax, [rbp-70h+arg_90]
0x18001643e  mov     [r11-48h], rcx
0x180016442  mov     [r11-50h], rax
0x180016446  lea     rax, [rbp-70h+arg_88]
0x18001644a  mov     [r11-58h], rcx
0x18001644e  mov     [r11-60h], rax
0x180016452  lea     rax, [rbp-70h+arg_80]
0x180016456  mov     [r11-68h], rcx
0x18001645a  mov     [r11-70h], rax
0x18001645e  lea     rax, [rbp-70h+arg_78]
0x180016462  mov     [r11-78h], rcx
0x180016466  mov     [r11-80h], rax
0x18001646a  lea     rax, [rbp-70h+arg_70]
0x18001646e  mov     [r11-88h], rcx
0x180016475  mov     [r11-90h], rax
0x18001647c  lea     rax, [rbp-70h+arg_68]
0x180016480  mov     [r11-98h], rcx
0x180016487  mov     [r11-0A0h], rax
0x18001648e  lea     rax, [rbp-70h+arg_60]
0x180016492  mov     [r11-0A8h], rcx
0x180016499  mov     [r11-0B0h], rax
0x1800164a0  lea     rax, [rbp-70h+arg_58]
0x1800164a4  mov     [r11-0B8h], rcx
0x1800164ab  mov     [r11-0C0h], rax
0x1800164b2  lea     rax, [rbp-70h+arg_50]
0x1800164b6  mov     [r11-0C8h], rcx
0x1800164bd  mov     [r11-0D0h], rax
0x1800164c4  lea     rax, [rbp-70h+arg_48]
0x1800164c8  mov     [r11-0D8h], rcx
0x1800164cf  mov     [rsp+78h], rax
0x1800164d4  lea     rax, [rbp-70h+arg_40]
0x1800164d8  mov     [rsp+150h+var_E0], rcx
0x1800164dd  mov     [rsp+150h+var_E8], rax
0x1800164e2  lea     rax, [rbp-70h+arg_38]
0x1800164e6  mov     [rsp+150h+var_F0], rcx
0x1800164eb  mov     [rsp+150h+var_F8], rax
0x1800164f0  lea     rax, [rbp-70h+arg_30]
0x1800164f4  mov     [rsp+150h+var_100], rcx
0x1800164f9  mov     [rsp+150h+var_108], rax
0x1800164fe  lea     rax, [rbp-70h+arg_28]
0x180016502  mov     [rsp+150h+var_110], rcx
0x180016507  mov     [rsp+150h+var_118], rax
0x18001650c  lea     rax, [rbp-70h+arg_20]
0x180016510  mov     [rsp+150h+var_120], rcx
0x180016515  mov     [rsp+150h+var_128], rax
0x18001651a  mov     [rsp+150h+var_130], rcx
0x18001651f  mov     ecx, r10d
0x180016522  call    FastWppTraceMessage
0x180016527  mov     rcx, [rbp-70h+var_8]
0x18001652b  xor     rcx, rsp; StackCookie
0x18001652e  call    __security_check_cookie
0x180016533  add     rsp, 150h
0x18001653a  pop     rbp
0x18001653b  retn
```
