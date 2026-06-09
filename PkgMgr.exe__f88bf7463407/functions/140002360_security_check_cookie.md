# __security_check_cookie

- ea: `0x140002360`
- end: `0x14000237e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `138`
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
- `0x140003640`
- `0x1400038dc`
- `0x140003ff8`
- `0x140004190`
- `0x140004564`
- `0x140004930`
- `0x140004bd4`
- `0x140005214`
- `0x140005280`
- `0x1400053f0`
- `0x140005c7c`
- `0x140005f40`
- `0x1400064d0`
- `0x1400067bc`
- `0x140006984`
- `0x140006b48`
- `0x140006c50`
- `0x140007524`
- `0x1400089c0`
- `0x140008de8`
- `0x14000903c`
- `0x1400092fc`
- `0x1400095ac`
- `0x1400096a4`
- `0x1400097d4`
- `0x1400098b8`
- `0x140009f08`
- `0x14000a1dc`
- `0x14000a714`
- `0x14000a8ac`
- `0x14000aae0`
- `0x14000aca8`
- `0x14000b454`
- `0x14000baa4`
- `0x14000bc74`
- `0x14000bdbc`
- `0x14000bf34`
- `0x14000c080`
- `0x14000c384`
- `0x14000ca60`
- `0x14000ccac`
- `0x14000d410`

## callees

- `0x140002360`
- `0x1400028f0`

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
0x140002360  cmp     rcx, cs:__security_cookie
0x140002367  jnz     short loc_140002379
0x140002369  rol     rcx, 10h
0x14000236d  test    cx, 0FFFFh
0x140002372  jnz     short loc_140002375
0x140002374  retn
0x140002375  ror     rcx, 10h; StackCookie
0x140002379  jmp     __report_gsfailure
```
