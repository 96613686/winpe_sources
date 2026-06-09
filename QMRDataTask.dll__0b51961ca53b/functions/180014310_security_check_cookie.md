# __security_check_cookie

- ea: `0x180014310`
- end: `0x18001432e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `37`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000108c`
- `0x1800021c0`
- `0x18000220c`
- `0x180003000`
- `0x180003140`
- `0x180003f20`
- `0x1800041a4`
- `0x180004344`
- `0x180004d4c`
- `0x180004fe8`
- `0x180006108`
- `0x1800064ac`
- `0x180007134`
- `0x180007490`
- `0x180009a20`
- `0x180009d9c`
- `0x180009ec8`
- `0x18000a1c0`
- `0x18000a520`
- `0x18000b290`
- `0x18000c6bc`
- `0x18000cad8`
- `0x18000cbe4`
- `0x18000d5a0`
- `0x18000e074`
- `0x18000ea9c`
- `0x18000ebf8`
- `0x18000f270`
- `0x18000f330`
- `0x18000f418`
- `0x180010af4`
- `0x180011fd0`
- `0x1800120e0`
- `0x180012320`
- `0x1800128a0`
- `0x18001331c`
- `0x1800141e4`

## callees

- `0x180001f60`
- `0x180014310`

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
0x180014310  cmp     rcx, cs:__security_cookie
0x180014317  jnz     short ReportFailure
0x180014319  rol     rcx, 10h
0x18001431d  test    cx, 0FFFFh
0x180014322  jnz     short RestoreRcx
0x180014324  retn
0x180014325  ror     rcx, 10h
0x180014329  jmp     __report_gsfailure
```
