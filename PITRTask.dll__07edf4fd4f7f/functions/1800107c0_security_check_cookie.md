# __security_check_cookie

- ea: `0x1800107c0`
- end: `0x1800107de`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `65`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800010c4`
- `0x180002570`
- `0x180002b7c`
- `0x180002e18`
- `0x180003eb0`
- `0x180004254`
- `0x180004664`
- `0x1800046b0`
- `0x180004bd4`
- `0x180004dc0`
- `0x180005028`
- `0x180005120`
- `0x180005240`
- `0x1800055d4`
- `0x1800056c8`
- `0x1800057bc`
- `0x1800058b0`
- `0x180005ba0`
- `0x180005d04`
- `0x180005e88`
- `0x180006054`
- `0x1800063d0`
- `0x1800066a4`
- `0x180006de0`
- `0x180006e80`
- `0x18000722c`
- `0x1800073bc`
- `0x1800074c8`
- `0x1800075d4`
- `0x180007954`
- `0x1800079a8`
- `0x180007a00`
- `0x180007ab8`
- `0x180007c84`
- `0x180008020`
- `0x180008698`
- `0x18000874c`
- `0x1800087f4`
- `0x180009758`
- `0x180009800`
- `0x180009bac`
- `0x180009f30`
- `0x18000a4f0`
- `0x18000b544`
- `0x18000c2f0`
- `0x18000c400`
- `0x18000c750`
- `0x18000c8f8`
- `0x18000d1a0`

## callees

- `0x180002030`
- `0x1800107c0`

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
0x1800107c0  cmp     rcx, cs:__security_cookie
0x1800107c7  jnz     short ReportFailure
0x1800107c9  rol     rcx, 10h
0x1800107cd  test    cx, 0FFFFh
0x1800107d2  jnz     short RestoreRcx
0x1800107d4  retn
0x1800107d5  ror     rcx, 10h
0x1800107d9  jmp     __report_gsfailure
```
