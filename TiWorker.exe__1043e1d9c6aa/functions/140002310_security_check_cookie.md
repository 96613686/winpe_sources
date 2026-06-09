# __security_check_cookie

- ea: `0x140002310`
- end: `0x14000232e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `176`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001010`
- `0x140001304`
- `0x1400013d8`
- `0x14000149c`
- `0x140001750`
- `0x140001a48`
- `0x140001aec`
- `0x140001c88`
- `0x140003670`
- `0x140003904`
- `0x140003d34`
- `0x140003ecc`
- `0x140004294`
- `0x140004648`
- `0x14000491c`
- `0x140004f4c`
- `0x140004fb8`
- `0x140005130`
- `0x140005798`
- `0x140005988`
- `0x140005f88`
- `0x140006810`
- `0x1400069e0`
- `0x140007004`
- `0x140007228`
- `0x140007758`
- `0x1400079e8`
- `0x140007eb8`
- `0x1400087d0`
- `0x140008b30`
- `0x140008d38`
- `0x140008ef4`
- `0x140009364`
- `0x1400094f4`
- `0x140009c48`
- `0x14000a414`
- `0x14000a5b4`
- `0x14000aa6c`
- `0x14000ac1c`
- `0x14000b4a0`
- `0x14000b5fc`
- `0x14000b6cc`
- `0x14000ba88`
- `0x14000bb7c`
- `0x14000bc84`
- `0x14000bebc`
- `0x14000bf10`
- `0x14000bf68`
- `0x14000bfe8`
- `0x14000c0f8`

## callees

- `0x140002310`
- `0x140002860`

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
0x140002310  cmp     rcx, cs:__security_cookie
0x140002317  jnz     short loc_140002329
0x140002319  rol     rcx, 10h
0x14000231d  test    cx, 0FFFFh
0x140002322  jnz     short loc_140002325
0x140002324  retn
0x140002325  ror     rcx, 10h; StackCookie
0x140002329  jmp     __report_gsfailure
```
