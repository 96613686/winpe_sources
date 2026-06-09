# __security_check_cookie

- ea: `0x180001620`
- end: `0x18000163e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `17`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002250`
- `0x180002f6c`
- `0x180003598`
- `0x180003844`
- `0x1800046d8`
- `0x180004ae4`
- `0x1800052f4`
- `0x1800056b0`
- `0x18000752c`
- `0x180007e70`
- `0x180007fa0`
- `0x180008bbc`
- `0x180009824`
- `0x18000ad54`
- `0x18000b680`
- `0x18000bd2c`
- `0x18000c6a8`

## callees

- `0x180001620`
- `0x180001c80`

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
0x180001620  cmp     rcx, cs:__security_cookie
0x180001627  jnz     short ReportFailure
0x180001629  rol     rcx, 10h
0x18000162d  test    cx, 0FFFFh
0x180001632  jnz     short RestoreRcx
0x180001634  retn
0x180001635  ror     rcx, 10h; StackCookie
0x180001639  jmp     __report_gsfailure
```
