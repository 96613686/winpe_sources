# WPP_SF_d

- ea: `0x180004dec`
- end: `0x180004e23`
- name: `WPP_SF_d`
- size: `55`
- prototype: `ULONG __fastcall(TRACEHANDLE, USHORT, const GUID *, int)`
- caller_count: `30`
- callee_count: `0`
- tags: ``

## callers

- `0x180003b58`
- `0x180003fc0`
- `0x180004320`
- `0x1800047c4`
- `0x1800049bc`
- `0x180005660`
- `0x1800060d0`
- `0x1800064a8`
- `0x180006904`
- `0x18000768c`
- `0x180007c14`
- `0x18000913c`
- `0x18000b02c`
- `0x18000b324`
- `0x18000bbb8`
- `0x18000c500`
- `0x18000c590`
- `0x18000c610`
- `0x18000c690`
- `0x18000c880`
- `0x18000ca5c`
- `0x18000cc50`
- `0x18000d060`
- `0x18000d728`
- `0x18000dabc`
- `0x18000f154`
- `0x18001031c`
- `0x180010eac`
- `0x180011878`
- `0x180012650`

## import_xrefs

- `ADVAPI32!TraceMessage` at `0x180004e18`
- `ADVAPI32!TraceMessage` at `0x180004e18`

## pseudocode

```c
ULONG __fastcall WPP_SF_d(TRACEHANDLE a1, USHORT a2, const GUID *a3, int a4)
{
  int v5; // [rsp+68h] [rbp+20h] BYREF

  v5 = a4;
  return TraceMessage(a1, 0x2Bu, a3, a2, &v5, 4, 0);
}

```

## disassembly

```asm
0x180004dec  mov     r11, rsp
0x180004def  mov     [r11+20h], r9d
0x180004df3  sub     rsp, 48h
0x180004df7  mov     qword ptr [r11-18h], 0
0x180004dff  lea     rax, [r11+20h]
0x180004e03  movzx   r9d, dx; MessageNumber
0x180004e07  mov     edx, 2Bh ; '+'; MessageFlags
0x180004e0c  mov     qword ptr [r11-20h], 4
0x180004e14  mov     [r11-28h], rax
0x180004e18  call    cs:__imp_TraceMessage
0x180004e1e  add     rsp, 48h
0x180004e22  retn
```
