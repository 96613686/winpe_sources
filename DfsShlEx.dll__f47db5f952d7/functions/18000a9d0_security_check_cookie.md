# __security_check_cookie

- ea: `0x18000a9d0`
- end: `0x18000a9ee`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `22`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000271c`
- `0x18000286c`
- `0x180003280`
- `0x180003ad4`
- `0x180003c7c`
- `0x180004144`
- `0x180004e2c`
- `0x1800052a8`
- `0x1800053f8`
- `0x180005588`
- `0x180005764`
- `0x180006184`
- `0x18000633c`
- `0x1800065d0`
- `0x180006e88`
- `0x1800071d0`
- `0x180007368`
- `0x180008428`
- `0x1800086d4`
- `0x180008920`
- `0x180008ab8`
- `0x180009700`

## callees

- `0x180002010`
- `0x18000a9d0`

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
0x18000a9d0  cmp     rcx, cs:__security_cookie
0x18000a9d7  jnz     short ReportFailure
0x18000a9d9  rol     rcx, 10h
0x18000a9dd  test    cx, 0FFFFh
0x18000a9e2  jnz     short RestoreRcx
0x18000a9e4  retn
0x18000a9e5  ror     rcx, 10h
0x18000a9e9  jmp     __report_gsfailure
```
