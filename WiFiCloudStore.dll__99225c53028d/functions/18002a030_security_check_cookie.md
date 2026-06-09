# __security_check_cookie

- ea: `0x18002a030`
- end: `0x18002a04e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `168`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x18000110c`
- `0x180001200`
- `0x1800012c4`
- `0x180001368`
- `0x1800013fc`
- `0x1800016b0`
- `0x1800019cc`
- `0x180001a7c`
- `0x180001af4`
- `0x180001dc8`
- `0x180001e58`
- `0x180001f2c`
- `0x180001f8c`
- `0x180002058`
- `0x18000212c`
- `0x180003850`
- `0x180004540`
- `0x180004ce0`
- `0x180005ac0`
- `0x180005bb0`
- `0x180005e00`
- `0x1800062c0`
- `0x180006460`
- `0x180006cd0`
- `0x180006d7c`
- `0x1800070ec`
- `0x1800071e0`
- `0x18000769c`
- `0x180007810`
- `0x180007fd8`
- `0x18000869c`
- `0x180008970`
- `0x180008cb0`
- `0x180009240`
- `0x1800098b0`
- `0x180009d18`
- `0x180009fb8`
- `0x18000a410`
- `0x18000a5a8`
- `0x18000a710`
- `0x18000a944`
- `0x18000b3cc`
- `0x18000ba64`
- `0x18000c8a4`
- `0x18000cd40`
- `0x18000cfc0`
- `0x18000d82c`
- `0x18000daa0`
- `0x18000dcdc`

## callees

- `0x18002a030`
- `0x18002a620`

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
0x18002a030  cmp     rcx, cs:__security_cookie
0x18002a037  jnz     short ReportFailure
0x18002a039  rol     rcx, 10h
0x18002a03d  test    cx, 0FFFFh
0x18002a042  jnz     short RestoreRcx
0x18002a044  retn
0x18002a045  ror     rcx, 10h; StackCookie
0x18002a049  jmp     __report_gsfailure
```
