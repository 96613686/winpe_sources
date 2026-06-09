# __security_check_cookie

- ea: `0x1800072e0`
- end: `0x1800072fe`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `33`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800011e0`
- `0x180001460`
- `0x180002130`
- `0x1800022b0`
- `0x1800026f0`
- `0x180002ae0`
- `0x1800038c0`
- `0x1800040c0`
- `0x1800044c0`
- `0x180004b30`
- `0x180004cd0`
- `0x180005030`
- `0x1800054c0`
- `0x180005940`
- `0x180005cc0`
- `0x1800062e0`
- `0x1800064b0`
- `0x1800066d0`
- `0x1800069d0`
- `0x180007c10`
- `0x180007de0`
- `0x180007f00`
- `0x180008010`
- `0x18000814c`
- `0x180008240`
- `0x180008410`
- `0x180009d38`
- `0x18000a414`
- `0x18000a5f8`
- `0x18000ab7c`
- `0x18000ad20`
- `0x18000aec4`
- `0x18000bd80`

## callees

- `0x1800072e0`
- `0x180007810`

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
0x1800072e0  cmp     rcx, cs:__security_cookie
0x1800072e7  jnz     short ReportFailure
0x1800072e9  rol     rcx, 10h
0x1800072ed  test    cx, 0FFFFh
0x1800072f2  jnz     short RestoreRcx
0x1800072f4  retn
0x1800072f5  ror     rcx, 10h; StackCookie
0x1800072f9  jmp     __report_gsfailure
```
