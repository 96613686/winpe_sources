# __security_check_cookie

- ea: `0x180002810`
- end: `0x18000282e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `91`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002320`
- `0x1800027a0`
- `0x1800078e4`
- `0x18000867c`
- `0x180008d88`
- `0x1800090e8`
- `0x180009fac`
- `0x18000a66c`
- `0x18000aca0`
- `0x18000e4d0`
- `0x180011034`
- `0x1800110ac`
- `0x180011ad8`
- `0x180011d70`
- `0x180012134`
- `0x180012820`
- `0x180013120`
- `0x180013754`
- `0x18001390c`
- `0x180015210`
- `0x1800157e4`
- `0x1800158ec`
- `0x180015a08`
- `0x180017480`
- `0x180018e68`
- `0x1800190b0`
- `0x1800193b0`
- `0x18001955c`
- `0x180019960`
- `0x180019c60`
- `0x180019eb0`
- `0x18001a224`
- `0x18001ab7c`
- `0x18001afcc`
- `0x18001d820`
- `0x18001d99c`
- `0x180021460`
- `0x18002200c`
- `0x18002219c`
- `0x180023a4c`
- `0x180023b50`
- `0x180024cf8`
- `0x180024da4`
- `0x18002c7dc`
- `0x18002cc84`
- `0x18002d9b4`
- `0x18002f118`
- `0x18002f61c`
- `0x18002fdcc`
- `0x1800315f0`

## callees

- `0x180002810`
- `0x180002bf0`

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
0x180002810  cmp     rcx, cs:__security_cookie
0x180002817  jnz     short ReportFailure
0x180002819  rol     rcx, 10h
0x18000281d  test    cx, 0FFFFh
0x180002822  jnz     short RestoreRcx
0x180002824  retn
0x180002825  ror     rcx, 10h
0x180002829  jmp     __report_gsfailure
```
