# __security_check_cookie

- ea: `0x180001f20`
- end: `0x180001f3e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `184`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x180001264`
- `0x18000133c`
- `0x1800015f0`
- `0x180002a34`
- `0x180003c58`
- `0x180004240`
- `0x18000546c`
- `0x180006168`
- `0x180009f70`
- `0x18000a268`
- `0x18000a420`
- `0x18000a81c`
- `0x18000aa00`
- `0x18000ac50`
- `0x18000af70`
- `0x18000c180`
- `0x18000d0d0`
- `0x18000d200`
- `0x18000e910`
- `0x18000f2e4`
- `0x18000fe54`
- `0x1800101c8`
- `0x180010400`
- `0x180010820`
- `0x180010d00`
- `0x180012c30`
- `0x1800135b0`
- `0x180013780`
- `0x18001426c`
- `0x180014434`
- `0x180016444`
- `0x18001727c`
- `0x180017340`
- `0x180018b3c`
- `0x180018f58`
- `0x18001a264`
- `0x18001b388`
- `0x18001cf50`
- `0x18001d5f0`
- `0x18001d8e0`
- `0x18001db00`
- `0x18001dd3c`
- `0x18001e17c`
- `0x18001e3cc`
- `0x18001e5c4`
- `0x180021b34`
- `0x180021fdc`
- `0x1800220d8`
- `0x180023714`

## callees

- `0x180001f20`
- `0x180001f50`

## pseudocode

```c
void __cdecl _security_check_cookie(uintptr_t StackCookie)
{
  __int64 v1; // rcx

  if ( StackCookie != _security_cookie )
ReportFailure:
    _report_gsfailure(StackCookie);
  v1 = __ROL8__(StackCookie, 16);
  if ( (_WORD)v1 )
  {
    StackCookie = __ROR8__(v1, 16);
    goto ReportFailure;
  }
}

```

## disassembly

```asm
0x180001f20  cmp     rcx, cs:__security_cookie
0x180001f27  jnz     short ReportFailure
0x180001f29  rol     rcx, 10h
0x180001f2d  test    cx, 0FFFFh
0x180001f32  jnz     short RestoreRcx
0x180001f34  retn
0x180001f35  ror     rcx, 10h; StackCookie
0x180001f39  jmp     __report_gsfailure
```
