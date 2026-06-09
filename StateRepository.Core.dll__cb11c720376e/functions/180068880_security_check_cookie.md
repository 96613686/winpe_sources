# __security_check_cookie

- ea: `0x180068880`
- end: `0x18006889e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `82`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001160`
- `0x18000126c`
- `0x180002770`
- `0x1800061e4`
- `0x180007154`
- `0x18000ad30`
- `0x18000f820`
- `0x180015248`
- `0x1800155e4`
- `0x180019da4`
- `0x18001ddf0`
- `0x18001f678`
- `0x180020e14`
- `0x1800224a0`
- `0x180023e18`
- `0x1800256c4`
- `0x180026410`
- `0x18002762c`
- `0x1800276f8`
- `0x18002a050`
- `0x180030918`
- `0x180030d98`
- `0x180037194`
- `0x18003f984`
- `0x18003ff20`
- `0x180041090`
- `0x180042af0`
- `0x180044e14`
- `0x180049864`
- `0x180049d1c`
- `0x180049f00`
- `0x18004cca0`
- `0x18004e2a0`
- `0x18004ed80`
- `0x180050420`
- `0x180053ef8`
- `0x180054f08`
- `0x1800557f8`
- `0x18005cb30`
- `0x18005ead0`
- `0x180061780`
- `0x180061cdc`
- `0x1800626dc`
- `0x180065620`
- `0x1800659c0`
- `0x18006ba34`
- `0x18006d500`
- `0x18006d700`
- `0x18006dd50`
- `0x18006dff0`

## callees

- `0x180068880`
- `0x1800688b0`

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
0x180068880  cmp     rcx, cs:__security_cookie
0x180068887  jnz     short ReportFailure
0x180068889  rol     rcx, 10h
0x18006888d  test    cx, 0FFFFh
0x180068892  jnz     short RestoreRcx
0x180068894  retn
0x180068895  ror     rcx, 10h; StackCookie
0x180068899  jmp     __report_gsfailure
```
