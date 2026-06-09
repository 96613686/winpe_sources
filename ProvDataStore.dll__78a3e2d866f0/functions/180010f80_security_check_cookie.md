# __security_check_cookie

- ea: `0x180010f80`
- end: `0x180010f9e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `32`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000108c`
- `0x180001118`
- `0x180001264`
- `0x18000135c`
- `0x180001478`
- `0x1800015e4`
- `0x180002cbc`
- `0x180002f68`
- `0x180003670`
- `0x180003a9c`
- `0x1800041c4`
- `0x180004580`
- `0x18000608c`
- `0x180006890`
- `0x1800069f0`
- `0x180006c84`
- `0x180006e2c`
- `0x180006eb0`
- `0x180007050`
- `0x180007a30`
- `0x180007e18`
- `0x180007fa4`
- `0x180009750`
- `0x18000b8f8`
- `0x18000bf1c`
- `0x18000c884`
- `0x18000dd4c`
- `0x18000e184`
- `0x18000fe94`
- `0x180010750`
- `0x180010ae4`
- `0x180010e5c`

## callees

- `0x1800021b0`
- `0x180010f80`

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
0x180010f80  cmp     rcx, cs:__security_cookie
0x180010f87  jnz     short ReportFailure
0x180010f89  rol     rcx, 10h
0x180010f8d  test    cx, 0FFFFh
0x180010f92  jnz     short RestoreRcx
0x180010f94  retn
0x180010f95  ror     rcx, 10h
0x180010f99  jmp     __report_gsfailure
```
