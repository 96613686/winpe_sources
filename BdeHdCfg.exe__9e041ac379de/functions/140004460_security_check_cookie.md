# __security_check_cookie

- ea: `0x140004460`
- end: `0x14000447e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `10`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140002014`
- `0x140002480`
- `0x140002930`
- `0x140002a00`
- `0x140002bc4`
- `0x140003340`
- `0x14000343c`
- `0x140003884`
- `0x140004010`
- `0x14000436c`

## callees

- `0x140001740`
- `0x140004460`

## pseudocode

```c
void __cdecl _security_check_cookie(uintptr_t StackCookie)
{
  __int64 v1; // rcx

  if ( StackCookie != _security_cookie )
LABEL_4:
    _report_gsfailure(StackCookie);
  v1 = __ROL8__(StackCookie, 16);
  if ( (_WORD)v1 )
  {
    StackCookie = __ROR8__(v1, 16);
    goto LABEL_4;
  }
}

```

## disassembly

```asm
0x140004460  cmp     rcx, cs:__security_cookie
0x140004467  jnz     short loc_140004479
0x140004469  rol     rcx, 10h
0x14000446d  test    cx, 0FFFFh
0x140004472  jnz     short loc_140004475
0x140004474  retn
0x140004475  ror     rcx, 10h
0x140004479  jmp     __report_gsfailure
```
