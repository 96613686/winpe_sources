# __security_check_cookie

- ea: `0x180026400`
- end: `0x18002641e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `21`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001158`
- `0x180001760`
- `0x180001fd0`
- `0x180002c20`
- `0x180002f80`
- `0x180011574`
- `0x180013d10`
- `0x180017930`
- `0x18001df30`
- `0x18001e0b0`
- `0x18001e2e0`
- `0x1800202a0`
- `0x180021d48`
- `0x180023618`
- `0x180023810`
- `0x180023968`
- `0x1800239dc`
- `0x180023acc`
- `0x180023c64`
- `0x180024f6c`
- `0x1800262dc`

## callees

- `0x180015380`
- `0x180026400`

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
0x180026400  cmp     rcx, cs:__security_cookie
0x180026407  jnz     short ReportFailure
0x180026409  rol     rcx, 10h
0x18002640d  test    cx, 0FFFFh
0x180026412  jnz     short RestoreRcx
0x180026414  retn
0x180026415  ror     rcx, 10h
0x180026419  jmp     __report_gsfailure
```
