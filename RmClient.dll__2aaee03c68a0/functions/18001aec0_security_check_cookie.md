# __security_check_cookie

- ea: `0x18001aec0`
- end: `0x18001aede`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `51`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001e00`
- `0x180001ff0`
- `0x180002320`
- `0x180002860`
- `0x180002f50`
- `0x180003430`
- `0x180003e80`
- `0x180004e10`
- `0x1800050b0`
- `0x180006ae0`
- `0x180006bf8`
- `0x180008060`
- `0x18000b020`
- `0x18000b670`
- `0x18000bd00`
- `0x18000c0a0`
- `0x18000c340`
- `0x18000c420`
- `0x18000c65c`
- `0x18000c768`
- `0x18000caa0`
- `0x18000d4b0`
- `0x18000dab0`
- `0x18000dfcc`
- `0x18000e3d0`
- `0x18000ea10`
- `0x18000eae0`
- `0x18000ed44`
- `0x18000f3e0`
- `0x18000fbb0`
- `0x18000ffd0`
- `0x180010650`
- `0x180011360`
- `0x180011650`
- `0x180011a90`
- `0x180012170`
- `0x180012240`
- `0x180012660`
- `0x1800128e0`
- `0x180012bfc`
- `0x180015d10`
- `0x18001607c`
- `0x1800163b4`
- `0x1800166cc`
- `0x180017600`
- `0x1800177d0`
- `0x1800178f0`
- `0x180019620`
- `0x180019cd0`
- `0x180019e00`

## callees

- `0x180014020`
- `0x18001aec0`

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
0x18001aec0  cmp     rcx, cs:__security_cookie
0x18001aec7  jnz     short ReportFailure
0x18001aec9  rol     rcx, 10h
0x18001aecd  test    cx, 0FFFFh
0x18001aed2  jnz     short RestoreRcx
0x18001aed4  retn
0x18001aed5  ror     rcx, 10h
0x18001aed9  jmp     __report_gsfailure
```
