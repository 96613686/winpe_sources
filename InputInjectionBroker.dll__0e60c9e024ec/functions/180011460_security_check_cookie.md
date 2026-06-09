# __security_check_cookie

- ea: `0x180011460`
- end: `0x18001147e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `33`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000108c`
- `0x18000116c`
- `0x180002854`
- `0x180002ae8`
- `0x1800030a0`
- `0x180003470`
- `0x1800039d4`
- `0x180003d50`
- `0x18000531c`
- `0x180005e70`
- `0x180006a90`
- `0x180006bd0`
- `0x180008c10`
- `0x180009238`
- `0x180009ed8`
- `0x18000abd0`
- `0x18000aed8`
- `0x18000b4a0`
- `0x18000b830`
- `0x18000bb10`
- `0x18000bec0`
- `0x18000c264`
- `0x18000c330`
- `0x18000c440`
- `0x18000cd10`
- `0x18000cf90`
- `0x18000d7f0`
- `0x18000e580`
- `0x18000eb7c`
- `0x180010920`
- `0x180010aac`
- `0x180010d48`
- `0x180011334`

## callees

- `0x180002130`
- `0x180011460`

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
0x180011460  cmp     rcx, cs:__security_cookie
0x180011467  jnz     short ReportFailure
0x180011469  rol     rcx, 10h
0x18001146d  test    cx, 0FFFFh
0x180011472  jnz     short RestoreRcx
0x180011474  retn
0x180011475  ror     rcx, 10h
0x180011479  jmp     __report_gsfailure
```
