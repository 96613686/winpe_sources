# __security_check_cookie

- ea: `0x1800024c0`
- end: `0x1800024de`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `101`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x180001178`
- `0x180001224`
- `0x1800012e0`
- `0x1800013ac`
- `0x180001488`
- `0x18000158c`
- `0x1800016c0`
- `0x180001c10`
- `0x180001e90`
- `0x180002930`
- `0x180004640`
- `0x1800050b8`
- `0x180005190`
- `0x180005554`
- `0x180005b34`
- `0x180005f5c`
- `0x1800063f4`
- `0x180006c00`
- `0x180006da4`
- `0x1800071d0`
- `0x1800073b8`
- `0x180007838`
- `0x180007f3c`
- `0x1800081e8`
- `0x180008e8c`
- `0x180008ff8`
- `0x1800093d8`
- `0x180009b84`
- `0x180009f38`
- `0x18000b6dc`
- `0x18000be38`
- `0x18000c034`
- `0x18000ca4c`
- `0x18000dcdc`
- `0x18000e960`
- `0x18000eb48`
- `0x18000ed24`
- `0x18000ed94`
- `0x18000f080`
- `0x18000f23c`
- `0x18000f35c`
- `0x18000fd90`
- `0x18001006c`
- `0x1800101f0`
- `0x1800107e0`
- `0x180010dd4`
- `0x18001122c`
- `0x1800115e0`
- `0x180011bf0`

## callees

- `0x1800024c0`
- `0x180002de0`

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
0x1800024c0  cmp     rcx, cs:__security_cookie
0x1800024c7  jnz     short ReportFailure
0x1800024c9  rol     rcx, 10h
0x1800024cd  test    cx, 0FFFFh
0x1800024d2  jnz     short RestoreRcx
0x1800024d4  retn
0x1800024d5  ror     rcx, 10h; StackCookie
0x1800024d9  jmp     __report_gsfailure
```
