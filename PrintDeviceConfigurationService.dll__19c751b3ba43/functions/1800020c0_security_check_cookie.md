# __security_check_cookie

- ea: `0x1800020c0`
- end: `0x1800020de`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `59`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x1800012dc`
- `0x1800015d4`
- `0x1800017f8`
- `0x1800018d0`
- `0x180002e10`
- `0x180003090`
- `0x1800035a0`
- `0x180004314`
- `0x1800045c0`
- `0x180005498`
- `0x180005604`
- `0x1800057d0`
- `0x180005f94`
- `0x180006348`
- `0x180007938`
- `0x18000808c`
- `0x18000951c`
- `0x18000a180`
- `0x18000a388`
- `0x18000a5e8`
- `0x18000a8e0`
- `0x18000ae04`
- `0x18000aeac`
- `0x18000b178`
- `0x18000b210`
- `0x18000bfd4`
- `0x18000c19c`
- `0x18000c384`
- `0x18000c6e0`
- `0x18000ca08`
- `0x18000d668`
- `0x18000ebbc`
- `0x18000ed18`
- `0x18000fad4`
- `0x18000fbe0`
- `0x180010b10`
- `0x180010ca4`
- `0x180010e44`
- `0x180011174`
- `0x18001260c`
- `0x1800128e8`
- `0x180012c70`
- `0x1800131dc`
- `0x1800132d8`
- `0x180013644`
- `0x180013e50`
- `0x18001445c`
- `0x18001481c`
- `0x18001497c`

## callees

- `0x1800020c0`
- `0x1800026d0`

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
0x1800020c0  cmp     rcx, cs:__security_cookie
0x1800020c7  jnz     short ReportFailure
0x1800020c9  rol     rcx, 10h
0x1800020cd  test    cx, 0FFFFh
0x1800020d2  jnz     short RestoreRcx
0x1800020d4  retn
0x1800020d5  ror     rcx, 10h; StackCookie
0x1800020d9  jmp     __report_gsfailure
```
