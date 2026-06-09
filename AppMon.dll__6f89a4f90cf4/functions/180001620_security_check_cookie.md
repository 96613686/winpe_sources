# __security_check_cookie

- ea: `0x180001620`
- end: `0x18000163e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `22`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002250`
- `0x1800024d0`
- `0x180002770`
- `0x180002bb8`
- `0x180002cac`
- `0x1800032f8`
- `0x1800034c0`
- `0x180003824`
- `0x180003bd8`
- `0x180005328`
- `0x1800057e0`
- `0x18000681c`
- `0x180006bb0`
- `0x1800074ac`
- `0x180008d9c`
- `0x18000b6a8`
- `0x18000bafc`
- `0x18000c234`
- `0x18000c808`
- `0x18000ca20`
- `0x18000e0e4`
- `0x18000e84c`

## callees

- `0x180001620`
- `0x180001be0`

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
0x180001620  cmp     rcx, cs:__security_cookie
0x180001627  jnz     short ReportFailure
0x180001629  rol     rcx, 10h
0x18000162d  test    cx, 0FFFFh
0x180001632  jnz     short RestoreRcx
0x180001634  retn
0x180001635  ror     rcx, 10h; StackCookie
0x180001639  jmp     __report_gsfailure
```
