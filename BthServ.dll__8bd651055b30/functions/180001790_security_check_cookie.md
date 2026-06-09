# __security_check_cookie

- ea: `0x180001790`
- end: `0x1800017ae`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `64`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800030cc`
- `0x180003378`
- `0x180004148`
- `0x18000451c`
- `0x180004918`
- `0x180005464`
- `0x1800057e0`
- `0x1800068a4`
- `0x1800069b0`
- `0x1800073bc`
- `0x180008b6c`
- `0x180009680`
- `0x1800097a8`
- `0x180009a78`
- `0x180009e08`
- `0x18000b6f4`
- `0x18000f780`
- `0x180010410`
- `0x180012f00`
- `0x18001413c`
- `0x180014734`
- `0x180014f04`
- `0x180015b04`
- `0x1800160d8`
- `0x180016354`
- `0x180016f20`
- `0x180019d04`
- `0x18001b2b4`
- `0x18001b9d8`
- `0x18001bf4c`
- `0x18001d5a0`
- `0x18001f1c8`
- `0x18001fac8`
- `0x180020058`
- `0x180020258`
- `0x1800209fc`
- `0x18002103c`
- `0x180021cc8`
- `0x180021f6c`
- `0x18002226c`
- `0x180022688`
- `0x1800229d8`
- `0x180022d74`
- `0x180023214`
- `0x1800234fc`
- `0x1800237e8`
- `0x180024004`
- `0x1800248ac`
- `0x180024bd4`
- `0x180024e1c`

## callees

- `0x180001790`
- `0x180002050`

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
0x180001790  cmp     rcx, cs:__security_cookie
0x180001797  jnz     short ReportFailure
0x180001799  rol     rcx, 10h
0x18000179d  test    cx, 0FFFFh
0x1800017a2  jnz     short RestoreRcx
0x1800017a4  retn
0x1800017a5  ror     rcx, 10h; StackCookie
0x1800017a9  jmp     __report_gsfailure
```
