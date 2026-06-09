# __security_check_cookie

- ea: `0x18004d320`
- end: `0x18004d33e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `182`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x180001100`
- `0x180001324`
- `0x180003af0`
- `0x180004970`
- `0x1800069ec`
- `0x1800083e0`
- `0x18000a810`
- `0x18000c510`
- `0x18000ebe0`
- `0x18000f6a0`
- `0x180010838`
- `0x180011b10`
- `0x1800127d8`
- `0x180012bf8`
- `0x180013718`
- `0x180017e54`
- `0x180019ec4`
- `0x18001bb08`
- `0x18001bee0`
- `0x18001c420`
- `0x180022bc4`
- `0x180023574`
- `0x180023b24`
- `0x180024330`
- `0x180025160`
- `0x1800269c0`
- `0x1800283d0`
- `0x180028b20`
- `0x180029a20`
- `0x18002e710`
- `0x18002fbe0`
- `0x18002fecc`
- `0x1800305d4`
- `0x180030924`
- `0x1800312d0`
- `0x180036f08`
- `0x180037b80`
- `0x180038ed4`
- `0x18003b0d4`
- `0x18003b360`
- `0x18003b520`
- `0x18003b984`
- `0x18003c3b4`
- `0x18003e600`
- `0x18003fbe0`
- `0x180041464`
- `0x180041630`
- `0x180042a3c`
- `0x18004420c`

## callees

- `0x18004d320`
- `0x18004d8b0`

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
0x18004d320  cmp     rcx, cs:__security_cookie
0x18004d327  jnz     short ReportFailure
0x18004d329  rol     rcx, 10h
0x18004d32d  test    cx, 0FFFFh
0x18004d332  jnz     short RestoreRcx
0x18004d334  retn
0x18004d335  ror     rcx, 10h; StackCookie
0x18004d339  jmp     __report_gsfailure
```
