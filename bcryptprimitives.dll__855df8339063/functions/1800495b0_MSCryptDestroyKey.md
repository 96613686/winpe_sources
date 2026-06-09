# MSCryptDestroyKey

- ea: `0x1800495b0`
- end: `0x1800495f6`
- name: `MSCryptDestroyKey`
- size: `70`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18002cd40`
- `0x18002d2e0`
- `0x180067358`

## callees

- `0x18000ecb0`
- `0x1800495b0`
- `0x1800593e0`

## string_xrefs

- `0x1800495d7`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`

## pseudocode

```c
__int64 __fastcall MSCryptDestroyKey(unsigned int *a1)
{
  if ( a1 && a1[1] == 1297306443 )
  {
    SymCryptWipeAsm(a1, *a1);
    return 0;
  }
  else
  {
    DebugTraceError(3221225480LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c", 1901);
    return 3221225480LL;
  }
}

```

## disassembly

```asm
0x1800495b0  sub     rsp, 28h
0x1800495b4  test    rcx, rcx
0x1800495b7  jz      short loc_1800495D1
0x1800495b9  cmp     dword ptr [rcx+4], 4D53534Bh
0x1800495c0  jnz     short loc_1800495D1
0x1800495c2  mov     edx, [rcx]
0x1800495c4  call    SymCryptWipeAsm
0x1800495c9  xor     eax, eax
0x1800495cb  add     rsp, 28h
0x1800495cf  retn
0x1800495d1  mov     r9d, 76Dh
0x1800495d7  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800495de  lea     rdx, aStatus; "Status"
0x1800495e5  mov     ecx, 0C0000008h
0x1800495ea  call    DebugTraceError
0x1800495ef  mov     eax, 0C0000008h
0x1800495f4  jmp     short loc_1800495CB
```
