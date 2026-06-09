# __security_check_cookie

- ea: `0x180001d30`
- end: `0x180001d4e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `37`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800012bc`
- `0x180002f5c`
- `0x1800031f8`
- `0x180003f58`
- `0x1800042fc`
- `0x1800046cc`
- `0x1800051f4`
- `0x180005570`
- `0x1800065dc`
- `0x1800066e8`
- `0x1800070fc`
- `0x18000871c`
- `0x180009200`
- `0x180009328`
- `0x1800095f8`
- `0x1800098fc`
- `0x180009a9c`
- `0x180009be0`
- `0x18000b810`
- `0x18000b948`
- `0x18000eca0`
- `0x18000ef00`
- `0x18000f2ac`
- `0x18000f664`
- `0x18000ff54`
- `0x1800110c0`
- `0x180011408`
- `0x180016db0`
- `0x180017278`
- `0x18001c924`
- `0x18001fa80`
- `0x180025b00`
- `0x180026c98`
- `0x180027990`
- `0x180028850`
- `0x180029740`

## callees

- `0x180001d30`
- `0x180002380`

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
0x180001d30  cmp     rcx, cs:__security_cookie
0x180001d37  jnz     short ReportFailure
0x180001d39  rol     rcx, 10h
0x180001d3d  test    cx, 0FFFFh
0x180001d42  jnz     short RestoreRcx
0x180001d44  retn
0x180001d45  ror     rcx, 10h; StackCookie
0x180001d49  jmp     __report_gsfailure
```
