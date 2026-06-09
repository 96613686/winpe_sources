# __security_check_cookie

- ea: `0x180007280`
- end: `0x18000729e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `24`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800011f0`
- `0x180001530`
- `0x1800017b0`
- `0x180001850`
- `0x180001dc0`
- `0x1800022e0`
- `0x180002800`
- `0x180003580`
- `0x180003f20`
- `0x180004260`
- `0x1800043e0`
- `0x180005300`
- `0x1800053e0`
- `0x180005680`
- `0x180005e50`
- `0x1800064b0`
- `0x180006850`
- `0x180006f90`
- `0x180007070`
- `0x180008510`
- `0x1800095ac`
- `0x180009af8`
- `0x18000a9c4`
- `0x18000b648`

## callees

- `0x180007280`
- `0x180007a40`

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
0x180007280  cmp     rcx, cs:__security_cookie
0x180007287  jnz     short ReportFailure
0x180007289  rol     rcx, 10h
0x18000728d  test    cx, 0FFFFh
0x180007292  jnz     short RestoreRcx
0x180007294  retn
0x180007295  ror     rcx, 10h
0x180007299  jmp     __report_gsfailure
```
