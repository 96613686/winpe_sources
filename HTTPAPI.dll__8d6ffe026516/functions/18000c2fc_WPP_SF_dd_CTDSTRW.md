# WPP_SF_dd_CTDSTRW_

- ea: `0x18000c2fc`
- end: `0x18000c368`
- name: `WPP_SF_dd_CTDSTRW_`
- size: `108`
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
ULONG __fastcall WPP_SF_dd_CTDSTRW_(__int64 a1, USHORT a2, __int64 a3, int a4, int a5, unsigned __int16 *a6)
{
  int v7; // [rsp+88h] [rbp+20h] BYREF

  v7 = a4;
  return FastWppTraceMessage(
           1050,
           a2,
           (ULONGLONG)WPP_9757c9c47725323be14918a4f6df94b6_Traceguids,
           &v7,
           4,
           &a5,
           4,
           a6,
           2,
           *((_QWORD *)a6 + 1),
           *a6,
           0);
}

```

## disassembly

```asm
0x18000c2fc  mov     r11, rsp
0x18000c2ff  mov     [r11+20h], r9d
0x18000c303  sub     rsp, 68h
0x18000c307  mov     rcx, [rsp+68h+arg_28]
0x18000c30f  lea     r9, [r11+20h]
0x18000c313  mov     qword ptr [r11-10h], 0
0x18000c31b  lea     r8, WPP_9757c9c47725323be14918a4f6df94b6_Traceguids
0x18000c322  mov     r10d, 41Ah
0x18000c328  movzx   edx, dx
0x18000c32b  movzx   eax, word ptr [rcx]
0x18000c32e  mov     [r11-18h], rax
0x18000c332  mov     rax, [rcx+8]
0x18000c336  mov     [r11-20h], rax
0x18000c33a  lea     rax, [r11+28h]
0x18000c33e  mov     qword ptr [r11-28h], 2
0x18000c346  mov     [r11-30h], rcx
0x18000c34a  mov     ecx, 4
0x18000c34f  mov     [r11-38h], rcx
0x18000c353  mov     [r11-40h], rax
0x18000c357  mov     [r11-48h], rcx
0x18000c35b  mov     ecx, r10d
0x18000c35e  call    FastWppTraceMessage
0x18000c363  add     rsp, 68h
0x18000c367  retn
```
