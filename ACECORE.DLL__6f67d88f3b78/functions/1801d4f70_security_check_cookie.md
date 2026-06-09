# __security_check_cookie

- ea: `0x1801d4f70`
- end: `0x1801d4f8e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `820`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800012c4`
- `0x180001448`
- `0x180001c80`
- `0x180001e50`
- `0x180002480`
- `0x180002884`
- `0x180002cf0`
- `0x180004a30`
- `0x180005ddc`
- `0x1800062c0`
- `0x180006cb0`
- `0x180006e90`
- `0x180007634`
- `0x180007b20`
- `0x180007c50`
- `0x18000812c`
- `0x180008a20`
- `0x180008d74`
- `0x180009dac`
- `0x18000a274`
- `0x18000af88`
- `0x18000b3fc`
- `0x18000b770`
- `0x18000c4a8`
- `0x18000cac0`
- `0x18000edf0`
- `0x18000f040`
- `0x18000f4b0`
- `0x18000fa34`
- `0x1800100c8`
- `0x1800102fc`
- `0x180010440`
- `0x180010de0`
- `0x1800119f0`
- `0x1800120f4`
- `0x180012214`
- `0x180012510`
- `0x18001270c`
- `0x1800128f0`
- `0x180012b90`
- `0x180012e70`
- `0x180013030`
- `0x180013240`
- `0x180013620`
- `0x180015040`
- `0x180015608`
- `0x180015664`
- `0x1800162f8`
- `0x180016540`
- `0x180016984`

## callees

- `0x1801d4f70`
- `0x1801d50b0`

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
0x1801d4f70  cmp     rcx, cs:__security_cookie
0x1801d4f77  jnz     short ReportFailure
0x1801d4f79  rol     rcx, 10h
0x1801d4f7d  test    cx, 0FFFFh
0x1801d4f82  jnz     short RestoreRcx
0x1801d4f84  retn
0x1801d4f85  ror     rcx, 10h; StackCookie
0x1801d4f89  jmp     __report_gsfailure
```
