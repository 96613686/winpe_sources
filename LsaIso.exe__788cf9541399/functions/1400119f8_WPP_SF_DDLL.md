# WPP_SF_DDLL

- ea: `0x1400119f8`
- end: `0x140011a69`
- name: `WPP_SF_DDLL`
- size: `113`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1400021f0`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x140011a5b`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x140011a5b`

## pseudocode

```c
ULONG WPP_SF_DDLL(TRACEHANDLE a1, __int64 a2, __int64 a3, int a4, __int64 a5, ...)
{
  int v6[6]; // [rsp+70h] [rbp-18h] BYREF
  int v7; // [rsp+A8h] [rbp+20h] BYREF
  __int64 v8; // [rsp+B8h] [rbp+30h] BYREF
  va_list va; // [rsp+B8h] [rbp+30h]
  va_list va1; // [rsp+C0h] [rbp+38h] BYREF

  va_start(va1, a5);
  va_start(va, a5);
  v8 = va_arg(va1, _QWORD);
  v7 = a4;
  v6[0] = 1112100685;
  return TraceMessage(
           a1,
           0x2Bu,
           &WPP_1c970dcbbca03ea0fbb31f15829d3516_Traceguids,
           0x2Fu,
           &v7,
           4,
           v6,
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
0x1400119f8  mov     r11, rsp
0x1400119fb  mov     [r11+20h], r9d
0x1400119ff  sub     rsp, 88h
0x140011a06  mov     qword ptr [r11-28h], 0
0x140011a0e  lea     rax, [r11+38h]
0x140011a12  mov     r9d, 2Fh ; '/'; MessageNumber
0x140011a18  mov     [rsp+88h+var_18], 42494F4Dh
0x140011a20  lea     r8, WPP_1c970dcbbca03ea0fbb31f15829d3516_Traceguids; MessageGuid
0x140011a27  lea     edx, [r9-2Bh]
0x140011a2b  mov     [r11-30h], rdx
0x140011a2f  mov     [r11-38h], rax
0x140011a33  lea     rax, [r11+30h]
0x140011a37  mov     [r11-40h], rdx
0x140011a3b  mov     [r11-48h], rax
0x140011a3f  lea     rax, [r11-18h]
0x140011a43  mov     [r11-50h], rdx
0x140011a47  mov     [r11-58h], rax
0x140011a4b  lea     rax, [r11+20h]
0x140011a4f  mov     [r11-60h], rdx
0x140011a53  lea     edx, [r9-4]; MessageFlags
0x140011a57  mov     [r11-68h], rax
0x140011a5b  call    cs:__imp_TraceMessage
0x140011a61  add     rsp, 88h
0x140011a68  retn
```
