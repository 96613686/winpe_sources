# __security_check_cookie

- ea: `0x140015aa0`
- end: `0x140015abe`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `43`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400022f8`
- `0x14000243c`
- `0x140002abc`
- `0x140002d58`
- `0x140004030`
- `0x140004198`
- `0x1400046ac`
- `0x1400051c0`
- `0x1400063d4`
- `0x140006888`
- `0x1400069fc`
- `0x140008428`
- `0x140008928`
- `0x140008ac4`
- `0x140009120`
- `0x14000931c`
- `0x140009430`
- `0x1400095a4`
- `0x140009754`
- `0x14000a7e4`
- `0x14000af14`
- `0x14000b238`
- `0x14000c470`
- `0x14000c658`
- `0x14000cd18`
- `0x14000ceb4`
- `0x14000d1f8`
- `0x14000d6d0`
- `0x14000f2c8`
- `0x14000f9ac`
- `0x14000fd90`
- `0x14000ff18`
- `0x140010178`
- `0x140010594`
- `0x140010868`
- `0x140010dc4`
- `0x140013ef8`
- `0x140014618`
- `0x140014ccc`
- `0x140015240`
- `0x140015400`
- `0x1400154b0`
- `0x140015548`

## callees

- `0x1400019a0`
- `0x140015aa0`

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
0x140015aa0  cmp     rcx, cs:__security_cookie
0x140015aa7  jnz     short loc_140015AB9
0x140015aa9  rol     rcx, 10h
0x140015aad  test    cx, 0FFFFh
0x140015ab2  jnz     short loc_140015AB5
0x140015ab4  retn
0x140015ab5  ror     rcx, 10h
0x140015ab9  jmp     __report_gsfailure
```
