# __security_check_cookie

- ea: `0x18000f5f0`
- end: `0x18000f60e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `34`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001b14`
- `0x180001c48`
- `0x1800027cc`
- `0x180002a68`
- `0x1800044a8`
- `0x18000487c`
- `0x180004f68`
- `0x180005310`
- `0x180005528`
- `0x1800062b4`
- `0x180006834`
- `0x180006a40`
- `0x180006b94`
- `0x180007988`
- `0x180007f44`
- `0x1800080dc`
- `0x180008408`
- `0x180008514`
- `0x180008ed8`
- `0x18000a3fc`
- `0x18000a534`
- `0x18000a840`
- `0x18000aa08`
- `0x18000b40c`
- `0x18000c614`
- `0x18000ccc0`
- `0x18000cde8`
- `0x18000d1e0`
- `0x18000d3e0`
- `0x18000e368`
- `0x18000e884`
- `0x18000eb70`
- `0x18000f324`
- `0x18000f39c`

## callees

- `0x180001f40`
- `0x18000f5f0`

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
0x18000f5f0  cmp     rcx, cs:__security_cookie
0x18000f5f7  jnz     short ReportFailure
0x18000f5f9  rol     rcx, 10h
0x18000f5fd  test    cx, 0FFFFh
0x18000f602  jnz     short RestoreRcx
0x18000f604  retn
0x18000f605  ror     rcx, 10h
0x18000f609  jmp     __report_gsfailure
```
