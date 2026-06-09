# __security_check_cookie

- ea: `0x180001d40`
- end: `0x180001d5e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `39`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800010d0`
- `0x180002a40`
- `0x180002c64`
- `0x180002d18`
- `0x180002ec0`
- `0x180002fc0`
- `0x180003098`
- `0x1800045b8`
- `0x180005480`
- `0x1800071e0`
- `0x180007a90`
- `0x180008018`
- `0x1800082f0`
- `0x1800095b0`
- `0x18000fe88`
- `0x1800109f4`
- `0x180011530`
- `0x18001190c`
- `0x1800124b0`
- `0x1800126e0`
- `0x180012c40`
- `0x1800130b0`
- `0x180014338`
- `0x1800152d0`
- `0x1800153dc`
- `0x180015d68`
- `0x1800175e8`
- `0x18001836c`
- `0x18001863c`
- `0x180019550`
- `0x180019cc0`
- `0x180019f70`
- `0x18001a760`
- `0x18001aaf0`
- `0x18001ade0`
- `0x18001bbb0`
- `0x18001c7b4`
- `0x18001d288`

## callees

- `0x180001d40`
- `0x180002300`

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
0x180001d40  cmp     rcx, cs:__security_cookie
0x180001d47  jnz     short ReportFailure
0x180001d49  rol     rcx, 10h
0x180001d4d  test    cx, 0FFFFh
0x180001d52  jnz     short RestoreRcx
0x180001d54  retn
0x180001d55  ror     rcx, 10h; StackCookie
0x180001d59  jmp     __report_gsfailure
```
