# WPP_SF_DLL

- ea: `0x18000b5e8`
- end: `0x18000b63d`
- name: `WPP_SF_DLL`
- size: `85`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001af0`

## callees

- `0x1800072e0`

## pseudocode

```c
ULONG WPP_SF_DLL(__int64 a1, __int64 a2, __int64 a3, int a4, ...)
{
  int v5; // [rsp+78h] [rbp+20h] BYREF
  __int64 v6; // [rsp+80h] [rbp+28h] BYREF
  va_list va; // [rsp+80h] [rbp+28h]
  va_list va1; // [rsp+88h] [rbp+30h] BYREF

  va_start(va1, a4);
  va_start(va, a4);
  v6 = va_arg(va1, _QWORD);
  v5 = a4;
  return FastWppTraceMessage(
           1050,
           0xBu,
           (ULONGLONG)WPP_f1658a4ec5ab39d8945ab61867572c0f_Traceguids,
           &v5,
           4,
           va,
           4,
           va1,
           4,
           0);
}

```

## disassembly

```asm
0x18000b5e8  mov     r11, rsp
0x18000b5eb  mov     [r11+20h], r9d
0x18000b5ef  sub     rsp, 58h
0x18000b5f3  mov     qword ptr [r11-10h], 0
0x18000b5fb  lea     rax, [r11+30h]
0x18000b5ff  mov     edx, 0Bh
0x18000b604  lea     r9, [r11+20h]
0x18000b608  mov     r10d, 41Ah
0x18000b60e  lea     r8, WPP_f1658a4ec5ab39d8945ab61867572c0f_Traceguids
0x18000b615  lea     ecx, [rdx-7]
0x18000b618  mov     [r11-18h], rcx
0x18000b61c  mov     [r11-20h], rax
0x18000b620  lea     rax, [r11+28h]
0x18000b624  mov     [r11-28h], rcx
0x18000b628  mov     [r11-30h], rax
0x18000b62c  mov     [r11-38h], rcx
0x18000b630  mov     ecx, r10d
0x18000b633  call    FastWppTraceMessage
0x18000b638  add     rsp, 58h
0x18000b63c  retn
```
