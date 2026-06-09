# WPP_SF_dLLLLLLL

- ea: `0x14002b868`
- end: `0x14002b902`
- name: `WPP_SF_dLLLLLLL`
- size: `154`
- prototype: `ULONG(TRACEHANDLE, __int64, __int64, int, ...)`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x14002670c`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x14002b8f4`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x14002b8f4`

## pseudocode

```c
ULONG WPP_SF_dLLLLLLL(TRACEHANDLE a1, __int64 a2, __int64 a3, int a4, ...)
{
  int v5; // [rsp+D8h] [rbp+20h] BYREF
  __int64 v6; // [rsp+E0h] [rbp+28h] BYREF
  va_list va; // [rsp+E0h] [rbp+28h]
  __int64 v8; // [rsp+E8h] [rbp+30h] BYREF
  va_list va1; // [rsp+E8h] [rbp+30h]
  __int64 v10; // [rsp+F0h] [rbp+38h] BYREF
  va_list va2; // [rsp+F0h] [rbp+38h]
  __int64 v12; // [rsp+F8h] [rbp+40h] BYREF
  va_list va3; // [rsp+F8h] [rbp+40h]
  __int64 v14; // [rsp+100h] [rbp+48h] BYREF
  va_list va4; // [rsp+100h] [rbp+48h]
  __int64 v16; // [rsp+108h] [rbp+50h] BYREF
  va_list va5; // [rsp+108h] [rbp+50h]
  va_list va6; // [rsp+110h] [rbp+58h] BYREF

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
  v5 = a4;
  return TraceMessage(
           a1,
           0x2Bu,
           &WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids,
           0x2Bu,
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
           0);
}

```

## disassembly

```asm
0x14002b868  mov     r11, rsp
0x14002b86b  mov     [r11+20h], r9d
0x14002b86f  sub     rsp, 0B8h
0x14002b876  mov     qword ptr [r11-18h], 0
0x14002b87e  lea     rax, [r11+58h]
0x14002b882  mov     edx, 2Bh ; '+'; MessageFlags
0x14002b887  mov     r9d, edx; MessageNumber
0x14002b88a  lea     r8d, [rdx-27h]
0x14002b88e  mov     [r11-20h], r8
0x14002b892  mov     [r11-28h], rax
0x14002b896  lea     rax, [r11+50h]
0x14002b89a  mov     [r11-30h], r8
0x14002b89e  mov     [r11-38h], rax
0x14002b8a2  lea     rax, [r11+48h]
0x14002b8a6  mov     [r11-40h], r8
0x14002b8aa  mov     [r11-48h], rax
0x14002b8ae  lea     rax, [r11+40h]
0x14002b8b2  mov     [r11-50h], r8
0x14002b8b6  mov     [r11-58h], rax
0x14002b8ba  lea     rax, [r11+38h]
0x14002b8be  mov     [r11-60h], r8
0x14002b8c2  mov     [r11-68h], rax
0x14002b8c6  lea     rax, [r11+30h]
0x14002b8ca  mov     [r11-70h], r8
0x14002b8ce  mov     [r11-78h], rax
0x14002b8d2  lea     rax, [r11+28h]
0x14002b8d6  mov     [r11-80h], r8
0x14002b8da  mov     [rsp+0B8h+var_88], rax
0x14002b8df  lea     rax, [r11+20h]
0x14002b8e3  mov     [rsp+0B8h+var_90], r8
0x14002b8e8  lea     r8, WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids; MessageGuid
0x14002b8ef  mov     [rsp+0B8h+var_98], rax
0x14002b8f4  call    cs:__imp_TraceMessage
0x14002b8fa  add     rsp, 0B8h
0x14002b901  retn
```
