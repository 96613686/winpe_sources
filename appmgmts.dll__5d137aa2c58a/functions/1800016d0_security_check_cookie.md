# __security_check_cookie

- ea: `0x1800016d0`
- end: `0x1800016ee`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `104`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002788`
- `0x180003370`
- `0x1800047d0`
- `0x1800049d0`
- `0x180004bf0`
- `0x180004d60`
- `0x180005294`
- `0x180005f2c`
- `0x1800060fc`
- `0x1800061f8`
- `0x180007410`
- `0x180007ea4`
- `0x180008fe4`
- `0x180009584`
- `0x18000aeb4`
- `0x18000b16c`
- `0x18000b3bc`
- `0x18000b7e8`
- `0x18000ba6c`
- `0x18000c1d0`
- `0x18000c6a0`
- `0x18000c790`
- `0x18000ce30`
- `0x18000d11c`
- `0x18000d1f4`
- `0x18000d2d8`
- `0x18000d44c`
- `0x18000d524`
- `0x18000d5fc`
- `0x18000d734`
- `0x18000e4f0`
- `0x18000e8e8`
- `0x18000eeac`
- `0x18000f024`
- `0x18000f470`
- `0x18000f634`
- `0x18000f8bc`
- `0x18000fe58`
- `0x18000ffdc`
- `0x1800101fc`
- `0x18001069c`
- `0x180010ae8`
- `0x180010f60`
- `0x180011268`
- `0x1800116e4`
- `0x1800117c4`
- `0x1800126ec`
- `0x180012750`
- `0x1800129c4`
- `0x180012dac`

## callees

- `0x1800016d0`
- `0x180001700`

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
0x1800016d0  cmp     rcx, cs:__security_cookie
0x1800016d7  jnz     short ReportFailure
0x1800016d9  rol     rcx, 10h
0x1800016dd  test    cx, 0FFFFh
0x1800016e2  jnz     short RestoreRcx
0x1800016e4  retn
0x1800016e5  ror     rcx, 10h; StackCookie
0x1800016e9  jmp     __report_gsfailure
```
