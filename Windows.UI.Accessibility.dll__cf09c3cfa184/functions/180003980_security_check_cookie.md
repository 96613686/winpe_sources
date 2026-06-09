# __security_check_cookie

- ea: `0x180003980`
- end: `0x18000399e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `112`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x18000112c`
- `0x18000118c`
- `0x180001440`
- `0x180001738`
- `0x1800018c8`
- `0x1800019c0`
- `0x180002970`
- `0x180002c80`
- `0x180002da0`
- `0x180004ff0`
- `0x18000530c`
- `0x1800055c0`
- `0x18000586c`
- `0x180005dc8`
- `0x180007300`
- `0x180007620`
- `0x1800085b8`
- `0x1800094b4`
- `0x180009620`
- `0x1800097ec`
- `0x180009960`
- `0x18000a250`
- `0x18000b278`
- `0x18000b3f0`
- `0x18000bb6c`
- `0x18000c858`
- `0x18000d460`
- `0x18000d658`
- `0x18000d950`
- `0x18000f640`
- `0x180010214`
- `0x180010490`
- `0x1800114fc`
- `0x1800116e4`
- `0x180011ae8`
- `0x180011b54`
- `0x180011bcc`
- `0x180011ce8`
- `0x180011d9c`
- `0x180011fa8`
- `0x180012b98`
- `0x180013a20`
- `0x180013afc`
- `0x180014764`
- `0x1800158a4`
- `0x180015cf0`
- `0x180017240`
- `0x180017330`
- `0x180017af4`

## callees

- `0x180003980`
- `0x180003f40`

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
0x180003980  cmp     rcx, cs:__security_cookie
0x180003987  jnz     short ReportFailure
0x180003989  rol     rcx, 10h
0x18000398d  test    cx, 0FFFFh
0x180003992  jnz     short RestoreRcx
0x180003994  retn
0x180003995  ror     rcx, 10h; StackCookie
0x180003999  jmp     __report_gsfailure
```
