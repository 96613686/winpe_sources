# __security_check_cookie

- ea: `0x1800181b0`
- end: `0x1800181ce`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `87`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001000`
- `0x180001120`
- `0x180001490`
- `0x1800017d0`
- `0x180001970`
- `0x180001ce0`
- `0x1800027b0`
- `0x180002c80`
- `0x180003860`
- `0x180003b50`
- `0x180003c60`
- `0x180004650`
- `0x180004970`
- `0x180004c30`
- `0x180004e80`
- `0x180005200`
- `0x180005740`
- `0x180005ba0`
- `0x180005e70`
- `0x1800060e0`
- `0x180006470`
- `0x180006750`
- `0x180007190`
- `0x180007330`
- `0x180007410`
- `0x180007c40`
- `0x180007ef0`
- `0x180008c70`
- `0x180009cc0`
- `0x18000a470`
- `0x18000a770`
- `0x18000a930`
- `0x18000adb0`
- `0x18000aec0`
- `0x18000b3a0`
- `0x18000b580`
- `0x18000b7c0`
- `0x18000be70`
- `0x18000c990`
- `0x18000e5e0`
- `0x18000e830`
- `0x18000ec30`
- `0x18000f140`
- `0x18000f240`
- `0x18000f430`
- `0x18000f5f0`
- `0x18000f840`
- `0x180010950`
- `0x180010d30`
- `0x180010f40`

## callees

- `0x1800181b0`
- `0x180018d70`

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
0x1800181b0  cmp     rcx, cs:__security_cookie
0x1800181b7  jnz     short ReportFailure
0x1800181b9  rol     rcx, 10h
0x1800181bd  test    cx, 0FFFFh
0x1800181c2  jnz     short RestoreRcx
0x1800181c4  retn
0x1800181c5  ror     rcx, 10h
0x1800181c9  jmp     __report_gsfailure
```
