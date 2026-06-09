# __security_check_cookie

- ea: `0x180003fc0`
- end: `0x180003fde`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `68`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x180001178`
- `0x1800012b8`
- `0x18000140c`
- `0x180001570`
- `0x1800017f4`
- `0x180001b88`
- `0x180001d28`
- `0x180001e7c`
- `0x180001fec`
- `0x18000216c`
- `0x180002318`
- `0x180002498`
- `0x180002618`
- `0x1800027ac`
- `0x180002b78`
- `0x180002f88`
- `0x1800031e4`
- `0x180003378`
- `0x180003538`
- `0x18000374c`
- `0x1800049a0`
- `0x180005398`
- `0x180008ea0`
- `0x18000913c`
- `0x18000a6c8`
- `0x18000a830`
- `0x18000acc8`
- `0x18000cad0`
- `0x18000cccc`
- `0x18000d144`
- `0x18000ed4c`
- `0x18000f4a8`
- `0x1800108d0`
- `0x18001187c`
- `0x180011b80`
- `0x180012e10`
- `0x180013018`
- `0x1800131f4`
- `0x1800138a0`
- `0x180015978`
- `0x180016c90`
- `0x180016d70`
- `0x180017e20`
- `0x180018750`
- `0x180019bb8`
- `0x18001a640`
- `0x18001a8ac`
- `0x18001ac20`
- `0x18001b2c0`

## callees

- `0x180003fc0`
- `0x1800046b0`

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
0x180003fc0  cmp     rcx, cs:__security_cookie
0x180003fc7  jnz     short ReportFailure
0x180003fc9  rol     rcx, 10h
0x180003fcd  test    cx, 0FFFFh
0x180003fd2  jnz     short RestoreRcx
0x180003fd4  retn
0x180003fd5  ror     rcx, 10h; StackCookie
0x180003fd9  jmp     __report_gsfailure
```
