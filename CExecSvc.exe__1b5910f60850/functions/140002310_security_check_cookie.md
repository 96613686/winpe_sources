# __security_check_cookie

- ea: `0x140002310`
- end: `0x14000232e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `120`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001008`
- `0x14000113c`
- `0x1400013f0`
- `0x140001704`
- `0x140001794`
- `0x140001a8c`
- `0x140003440`
- `0x140003850`
- `0x140003a50`
- `0x140003bc0`
- `0x140003fe0`
- `0x140004550`
- `0x1400045bc`
- `0x1400048f0`
- `0x140005224`
- `0x140005cbc`
- `0x140005f68`
- `0x1400064c0`
- `0x140006684`
- `0x140007960`
- `0x1400079b8`
- `0x140008670`
- `0x140008a58`
- `0x140009108`
- `0x1400093d4`
- `0x1400097c4`
- `0x140009de4`
- `0x14000a110`
- `0x14000a53c`
- `0x14000a5e0`
- `0x14000a7bc`
- `0x14000b040`
- `0x14000b958`
- `0x14000bc7c`
- `0x14000c1d0`
- `0x14000c340`
- `0x14000cd1c`
- `0x14000d17c`
- `0x14000d358`
- `0x14000d65c`
- `0x14000daa0`
- `0x14000ec60`
- `0x14000ed90`
- `0x14000eed0`
- `0x14000f010`
- `0x14000f120`
- `0x14000f1ac`
- `0x14000f3c0`
- `0x14000fe64`
- `0x1400103e0`

## callees

- `0x140002310`
- `0x1400029e0`

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
