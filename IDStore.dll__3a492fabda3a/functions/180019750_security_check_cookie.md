# __security_check_cookie

- ea: `0x180019750`
- end: `0x18001976e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `41`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800014fc`
- `0x180001808`
- `0x180002500`
- `0x180003be0`
- `0x180004490`
- `0x180005000`
- `0x180006260`
- `0x180007c30`
- `0x180008260`
- `0x180008910`
- `0x180009cd0`
- `0x18000a120`
- `0x18000b460`
- `0x18000d620`
- `0x18000e660`
- `0x18000eb30`
- `0x18000edb4`
- `0x18000fdec`
- `0x180011074`
- `0x1800113ac`
- `0x180012610`
- `0x180012b10`
- `0x180013170`
- `0x1800132b0`
- `0x180013430`
- `0x1800139bc`
- `0x180013b40`
- `0x180013ff4`
- `0x180014140`
- `0x180014974`
- `0x180015790`
- `0x180015b30`
- `0x180015d10`
- `0x180016400`
- `0x180016718`
- `0x180017ec0`
- `0x180018040`
- `0x1800183dc`
- `0x180018ecc`
- `0x180019290`
- `0x1800194dc`

## callees

- `0x18000f860`
- `0x180019750`

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
0x180019750  cmp     rcx, cs:__security_cookie
0x180019757  jnz     short ReportFailure
0x180019759  rol     rcx, 10h
0x18001975d  test    cx, 0FFFFh
0x180019762  jnz     short RestoreRcx
0x180019764  retn
0x180019765  ror     rcx, 10h
0x180019769  jmp     __report_gsfailure
```
