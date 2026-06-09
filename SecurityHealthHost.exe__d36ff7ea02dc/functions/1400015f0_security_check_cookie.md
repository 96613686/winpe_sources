# __security_check_cookie

- ea: `0x1400015f0`
- end: `0x14000160e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `26`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140002a94`
- `0x140003188`
- `0x140004a70`
- `0x140004d60`
- `0x1400050f0`
- `0x140005260`
- `0x1400054f0`
- `0x14000581c`
- `0x140005ab0`
- `0x140005d20`
- `0x1400078ec`
- `0x140007cbc`
- `0x1400080b4`
- `0x140008bc4`
- `0x140009574`
- `0x140009e24`
- `0x14000b34c`
- `0x14000bc80`
- `0x14000bd90`
- `0x14000c688`
- `0x14000dc20`
- `0x14000e47c`
- `0x14000ee14`
- `0x14000f1bc`
- `0x14000f3e4`
- `0x14000f938`

## callees

- `0x1400015f0`
- `0x140002110`

## pseudocode

```c
void __cdecl _security_check_cookie(uintptr_t StackCookie)
{
  __int64 v1; // rcx

  if ( StackCookie != _security_cookie )
LABEL_4:
    _report_gsfailure(StackCookie);
  v1 = __ROL8__(StackCookie, 16);
  if ( (_WORD)v1 )
  {
    StackCookie = __ROR8__(v1, 16);
    goto LABEL_4;
  }
}

```

## disassembly

```asm
0x1400015f0  cmp     rcx, cs:__security_cookie
0x1400015f7  jnz     short loc_140001609
0x1400015f9  rol     rcx, 10h
0x1400015fd  test    cx, 0FFFFh
0x140001602  jnz     short loc_140001605
0x140001604  retn
0x140001605  ror     rcx, 10h; StackCookie
0x140001609  jmp     __report_gsfailure
```
