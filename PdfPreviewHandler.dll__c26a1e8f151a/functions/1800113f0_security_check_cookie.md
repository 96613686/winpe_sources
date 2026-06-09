# __security_check_cookie

- ea: `0x1800113f0`
- end: `0x18001140e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `61`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001001`
- `0x1800010bd`
- `0x18000128e`
- `0x1800014c1`
- `0x18000157d`
- `0x180001c51`
- `0x180001d6d`
- `0x180001fb1`
- `0x18000233b`
- `0x1800027b0`
- `0x180002c96`
- `0x180002ebf`
- `0x180003a0a`
- `0x180003a7f`
- `0x180003ced`
- `0x180003e05`
- `0x180003f93`
- `0x180004086`
- `0x180004504`
- `0x180004750`
- `0x180004c2a`
- `0x180004dd0`
- `0x1800050f0`
- `0x180005340`
- `0x1800055f0`
- `0x180005752`
- `0x1800059cc`
- `0x180005b46`
- `0x180005c98`
- `0x180005de0`
- `0x1800064e8`
- `0x18000674c`
- `0x18000796c`
- `0x180007a30`
- `0x18000fd02`
- `0x18000fd77`
- `0x180011f52`
- `0x180013670`
- `0x180013890`
- `0x180013d12`
- `0x180014090`
- `0x18001420c`
- `0x180014450`
- `0x1800145a0`
- `0x180014770`
- `0x1800148fc`
- `0x180014ba0`
- `0x180017f10`
- `0x18001bee0`
- `0x180027110`

## callees

- `0x1800113f0`
- `0x180011750`

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
0x1800113f0  cmp     rcx, cs:__security_cookie
0x1800113f7  jnz     short ReportFailure
0x1800113f9  rol     rcx, 10h
0x1800113fd  test    cx, 0FFFFh
0x180011402  jnz     short RestoreRcx
0x180011404  retn
0x180011405  ror     rcx, 10h; StackCookie
0x180011409  jmp     __report_gsfailure
```
