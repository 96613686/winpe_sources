# __security_check_cookie

- ea: `0x180001dc0`
- end: `0x180001dde`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `109`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800010c8`
- `0x1800011fc`
- `0x1800012b8`
- `0x180001348`
- `0x1800013f0`
- `0x18000155c`
- `0x1800016a4`
- `0x180001764`
- `0x180003750`
- `0x1800038d4`
- `0x180004690`
- `0x180004840`
- `0x180004a0c`
- `0x180004c54`
- `0x180004db0`
- `0x180004ef0`
- `0x1800052b0`
- `0x1800053f0`
- `0x180005810`
- `0x18000677c`
- `0x180006a10`
- `0x180006f80`
- `0x180007de8`
- `0x180008af0`
- `0x180008c20`
- `0x180008d50`
- `0x180008de0`
- `0x180008ea8`
- `0x180009570`
- `0x180009720`
- `0x1800098d0`
- `0x180009bc0`
- `0x18000a0f4`
- `0x18000a1f8`
- `0x18000a70c`
- `0x18000ae80`
- `0x18000af60`
- `0x18000b040`
- `0x18000b140`
- `0x18000b240`
- `0x18000b350`
- `0x18000b410`
- `0x18000b4d4`
- `0x18000bbd4`
- `0x18000c1c4`
- `0x18000c7c0`
- `0x18000c850`
- `0x18000ce88`
- `0x18000d1c0`

## callees

- `0x180001dc0`
- `0x180002400`

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
0x180001dc0  cmp     rcx, cs:__security_cookie
0x180001dc7  jnz     short ReportFailure
0x180001dc9  rol     rcx, 10h
0x180001dcd  test    cx, 0FFFFh
0x180001dd2  jnz     short RestoreRcx
0x180001dd4  retn
0x180001dd5  ror     rcx, 10h; StackCookie
0x180001dd9  jmp     __report_gsfailure
```
