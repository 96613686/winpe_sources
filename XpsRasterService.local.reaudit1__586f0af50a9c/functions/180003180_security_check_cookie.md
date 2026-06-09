# __security_check_cookie

- ea: `0x180003180`
- end: `0x18000319e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `343`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003e40`
- `0x180004440`
- `0x1800046b0`
- `0x180004940`
- `0x180004b20`
- `0x180004da0`
- `0x180004f80`
- `0x180005110`
- `0x1800056f0`
- `0x180005970`
- `0x180005b80`
- `0x180005eb0`
- `0x180006070`
- `0x180006140`
- `0x180006660`
- `0x180006940`
- `0x180006de0`
- `0x180007150`
- `0x1800077f0`
- `0x180007960`
- `0x180007f90`
- `0x180009b40`
- `0x18000a2b0`
- `0x18000b100`
- `0x18000bd30`
- `0x18000c660`
- `0x18000d7e0`
- `0x18000dbb0`
- `0x18000df50`
- `0x18000e100`
- `0x18000e1d0`
- `0x18000e290`
- `0x18000e3b0`
- `0x18000e700`
- `0x18000f900`
- `0x1800108d0`
- `0x180011680`
- `0x180011b20`
- `0x180012380`
- `0x180012740`
- `0x1800129f0`
- `0x180013310`
- `0x180013d40`
- `0x180013f90`
- `0x1800143e0`
- `0x180014660`
- `0x180014a60`
- `0x1800157a0`
- `0x180015870`
- `0x180015b20`

## callees

- `0x180003180`
- `0x1800037b0`

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
0x180003180  cmp     rcx, cs:__security_cookie
0x180003187  jnz     short ReportFailure
0x180003189  rol     rcx, 10h
0x18000318d  test    cx, 0FFFFh
0x180003192  jnz     short RestoreRcx
0x180003194  retn
0x180003195  ror     rcx, 10h; StackCookie
0x180003199  jmp     __report_gsfailure
```
