# WPP_SF_sq

- ea: `0x180005b0c`
- end: `0x180005b59`
- name: `WPP_SF_sq`
- size: `77`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `13`
- callee_count: `0`
- tags: ``

## callers

- `0x180002920`
- `0x180005010`
- `0x180005100`
- `0x180005160`
- `0x1800051c0`
- `0x180005260`
- `0x180005390`
- `0x180005430`
- `0x180005490`
- `0x180005530`
- `0x180005690`
- `0x180005730`
- `0x1800057a0`

## import_xrefs

- `ADVAPI32!TraceMessage` at `0x180005b4e`
- `ADVAPI32!TraceMessage` at `0x180005b4e`

## pseudocode

```c
ULONG WPP_SF_sq(TRACEHANDLE a1, USHORT a2, __int64 a3, __int64 a4, ...)
{
  va_list va; // [rsp+80h] [rbp+28h] BYREF

  va_start(va, a4);
  return TraceMessage(a1, 0x2Bu, &WPP_85f567f30ac03a1b1e78961f0afc6072_Traceguids, a2, "Enter to", 9, va, 8, 0);
}

```

## disassembly

```asm
0x180005b0c  mov     r11, rsp
0x180005b0f  sub     rsp, 58h
0x180005b13  mov     qword ptr [r11-18h], 0
0x180005b1b  lea     rax, [r11+28h]
0x180005b1f  mov     qword ptr [r11-20h], 8
0x180005b27  lea     r8, WPP_85f567f30ac03a1b1e78961f0afc6072_Traceguids; MessageGuid
0x180005b2e  mov     [r11-28h], rax
0x180005b32  lea     rax, aEnterTo; "Enter to"
0x180005b39  movzx   r9d, dx; MessageNumber
0x180005b3d  mov     edx, 2Bh ; '+'; MessageFlags
0x180005b42  mov     qword ptr [r11-30h], 9
0x180005b4a  mov     [r11-38h], rax
0x180005b4e  call    cs:__imp_TraceMessage
0x180005b54  add     rsp, 58h
0x180005b58  retn
```
