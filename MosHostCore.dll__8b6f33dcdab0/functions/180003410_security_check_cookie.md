# __security_check_cookie

- ea: `0x180003410`
- end: `0x18000342e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `103`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x180001160`
- `0x180001414`
- `0x18000170c`
- `0x180001898`
- `0x1800019b4`
- `0x180001aa4`
- `0x180001b84`
- `0x180001c74`
- `0x180001d54`
- `0x180001e8c`
- `0x180001ff0`
- `0x180002140`
- `0x18000225c`
- `0x180002394`
- `0x180002464`
- `0x180002520`
- `0x180002698`
- `0x180002744`
- `0x1800027d8`
- `0x1800028b8`
- `0x180002988`
- `0x180002a68`
- `0x180002b58`
- `0x180002c5c`
- `0x1800038cc`
- `0x180004750`
- `0x1800049ec`
- `0x180005064`
- `0x18000522c`
- `0x1800055c4`
- `0x180005978`
- `0x180007058`
- `0x1800075a0`
- `0x180007fb8`
- `0x180008c04`
- `0x180009128`
- `0x1800093bc`
- `0x1800094d4`
- `0x180009a4c`
- `0x180009e8c`
- `0x18000a538`
- `0x18000b220`
- `0x18000bd44`
- `0x18000c418`
- `0x18000c598`
- `0x18000d3cc`
- `0x18000ed40`
- `0x1800109f0`
- `0x180011d8c`

## callees

- `0x180003410`
- `0x180003d80`

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
0x180003410  cmp     rcx, cs:__security_cookie
0x180003417  jnz     short ReportFailure
0x180003419  rol     rcx, 10h
0x18000341d  test    cx, 0FFFFh
0x180003422  jnz     short RestoreRcx
0x180003424  retn
0x180003425  ror     rcx, 10h; StackCookie
0x180003429  jmp     __report_gsfailure
```
