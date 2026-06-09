# __security_check_cookie

- ea: `0x1800014b0`
- end: `0x1800014ce`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `86`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800023d0`
- `0x18000376c`
- `0x1800039e4`
- `0x1800044e4`
- `0x1800049b0`
- `0x180004e18`
- `0x1800052c4`
- `0x1800054bc`
- `0x180005924`
- `0x180005d90`
- `0x18000604c`
- `0x180006940`
- `0x1800077b0`
- `0x180007b64`
- `0x180008190`
- `0x18000ab10`
- `0x18000afd8`
- `0x18000b120`
- `0x18000b5f8`
- `0x18000b794`
- `0x18000b924`
- `0x18000bb18`
- `0x18000bc50`
- `0x18000bfac`
- `0x18000c224`
- `0x18000c37c`
- `0x18000c8a8`
- `0x18000cb0c`
- `0x18000cc24`
- `0x18000cee8`
- `0x18000d0a0`
- `0x18000d308`
- `0x18000d424`
- `0x18000d5b4`
- `0x18000df6c`
- `0x18000ea2c`
- `0x18000eb7c`
- `0x18000efc8`
- `0x18000f150`
- `0x18000f1cc`
- `0x18000f470`
- `0x18000f670`
- `0x18000f8f0`
- `0x18000f9c8`
- `0x18000ff50`
- `0x180010908`
- `0x180010c18`
- `0x1800110b8`
- `0x180011e34`
- `0x180012284`

## callees

- `0x1800014b0`
- `0x180001a90`

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
0x1800014b0  cmp     rcx, cs:__security_cookie
0x1800014b7  jnz     short ReportFailure
0x1800014b9  rol     rcx, 10h
0x1800014bd  test    cx, 0FFFFh
0x1800014c2  jnz     short RestoreRcx
0x1800014c4  retn
0x1800014c5  ror     rcx, 10h; StackCookie
0x1800014c9  jmp     __report_gsfailure
```
