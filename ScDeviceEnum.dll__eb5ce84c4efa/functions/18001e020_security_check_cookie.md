# __security_check_cookie

- ea: `0x18001e020`
- end: `0x18001e03e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `95`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x18000284c`
- `0x180002ae8`
- `0x180003160`
- `0x180003328`
- `0x1800036b4`
- `0x180003a68`
- `0x180005110`
- `0x180005cb0`
- `0x180006130`
- `0x1800064c4`
- `0x180006670`
- `0x180006ad0`
- `0x18000754c`
- `0x18000770c`
- `0x180007bb4`
- `0x180007d34`
- `0x180007ec0`
- `0x180008130`
- `0x1800081f0`
- `0x180008274`
- `0x18000853c`
- `0x180008684`
- `0x180008b24`
- `0x180008c14`
- `0x1800090b4`
- `0x180009274`
- `0x180009490`
- `0x1800096f4`
- `0x180009b0c`
- `0x180009fbc`
- `0x18000a0c4`
- `0x18000a150`
- `0x18000a424`
- `0x18000aacc`
- `0x18000ad10`
- `0x18000aedc`
- `0x18000b1f8`
- `0x18000b4a0`
- `0x18000b7cc`
- `0x18000bb00`
- `0x18000c5d8`
- `0x18000cb00`
- `0x18000d35c`
- `0x18000d604`
- `0x18000d754`
- `0x18000d8f0`
- `0x18000da20`
- `0x18000db7c`
- `0x18000dda0`

## callees

- `0x180001d30`
- `0x18001e020`

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
0x18001e020  cmp     rcx, cs:__security_cookie
0x18001e027  jnz     short ReportFailure
0x18001e029  rol     rcx, 10h
0x18001e02d  test    cx, 0FFFFh
0x18001e032  jnz     short RestoreRcx
0x18001e034  retn
0x18001e035  ror     rcx, 10h
0x18001e039  jmp     __report_gsfailure
```
