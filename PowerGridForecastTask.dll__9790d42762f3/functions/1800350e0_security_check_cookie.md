# __security_check_cookie

- ea: `0x1800350e0`
- end: `0x1800350fe`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `157`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800012e0`
- `0x1800013a4`
- `0x180001658`
- `0x1800018fc`
- `0x180002a24`
- `0x1800034a4`
- `0x180003cfc`
- `0x1800047b8`
- `0x1800053b4`
- `0x180005b54`
- `0x180006920`
- `0x180006a70`
- `0x180006bc0`
- `0x180006cf0`
- `0x180006e20`
- `0x180006f20`
- `0x180007020`
- `0x180007120`
- `0x180007250`
- `0x180007380`
- `0x1800074b0`
- `0x180007810`
- `0x1800078d0`
- `0x180007990`
- `0x180007b50`
- `0x180007cf0`
- `0x180007da0`
- `0x180007e60`
- `0x180007f20`
- `0x180008c34`
- `0x180008e00`
- `0x18000bd00`
- `0x18000c1a0`
- `0x18000c720`
- `0x18000c83c`
- `0x18000d948`
- `0x18000e050`
- `0x18000e758`
- `0x18000eee8`
- `0x18000fa28`
- `0x18000fe64`
- `0x1800102a0`
- `0x18001046c`
- `0x18001108c`
- `0x180012068`
- `0x180012268`
- `0x1800124d0`
- `0x180012884`
- `0x180014638`

## callees

- `0x180026b70`
- `0x1800350e0`

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
0x1800350e0  cmp     rcx, cs:__security_cookie
0x1800350e7  jnz     short ReportFailure
0x1800350e9  rol     rcx, 10h
0x1800350ed  test    cx, 0FFFFh
0x1800350f2  jnz     short RestoreRcx
0x1800350f4  retn
0x1800350f5  ror     rcx, 10h
0x1800350f9  jmp     __report_gsfailure
```
