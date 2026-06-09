# MSCryptDestroyDHKeyPair

- ea: `0x18001c7a0`
- end: `0x18001c86f`
- name: `MSCryptDestroyDHKeyPair`
- size: `207`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18000ecb0`
- `0x18000ee60`
- `0x180010270`
- `0x18001c7a0`
- `0x18001c878`
- `0x1800581c0`

## string_xrefs

- `0x18001c7d8`: `onecore\ds\security\cryptoapi\ncrypt\msprim\dsa\dh.c`
- `0x1800814a6`: `onecore\ds\security\cryptoapi\ncrypt\msprim\dsa\dh.c`

## pseudocode

```c
__int64 __fastcall MSCryptDestroyDHKeyPair(__int64 a1, int a2, int a3)
{
  unsigned int v4; // edi
  __int64 v6; // rcx

  if ( a1 )
  {
    if ( *(_DWORD *)(a1 + 4) == 1297304409
      && *(_DWORD *)(a1 + 8) == 196610
      && (unsigned int)(*(_DWORD *)(a1 + 12) - 64) <= 0x1C0 )
    {
      v4 = 0;
      if ( *(_QWORD *)(a1 + 32) )
      {
        SymCryptDlkeyFree();
        *(_QWORD *)(a1 + 32) = 0;
      }
      v6 = *(_QWORD *)(a1 + 24);
      if ( v6 )
      {
        SymCryptMlDsaTemporariesFree(v6);
        *(_QWORD *)(a1 + 24) = 0;
      }
      MSCryptFree(a1);
    }
    else
    {
      DebugTraceError(3221225485LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\dsa\\dh.c", 219);
      v4 = -1073741811;
      DebugTraceError(3221225485LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\dsa\\dh.c", 1828);
    }
  }
  else
  {
    v4 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        a3,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\dsa\\dh.c",
        29);
  }
  return v4;
}

```

## disassembly

```asm
0x18001c7a0  mov     [rsp+arg_0], rbx
0x18001c7a5  push    rdi
0x18001c7a6  sub     rsp, 40h
0x18001c7aa  mov     rbx, rcx
0x18001c7ad  test    rcx, rcx
0x18001c7b0  jnz     loc_18001C837
0x18001c7b6  mov     edi, 0C000000Dh
0x18001c7bb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c7c2  lea     rax, WPP_GLOBAL_Control
0x18001c7c9  cmp     rcx, rax
0x18001c7cc  jz      short loc_18001C813
0x18001c7ce  test    byte ptr [rcx+1Ch], 1
0x18001c7d2  jz      short loc_18001C813
0x18001c7d4  mov     rcx, [rcx+10h]
0x18001c7d8  lea     rbx, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001c7df  mov     [rsp+48h+var_18], 71Dh
0x18001c7e7  lea     r9, aStatus; "Status"
0x18001c7ee  mov     [rsp+48h+var_20], rbx
0x18001c7f3  mov     [rsp+48h+var_28], 0C000000Dh
0x18001c7fb  call    WPP_SF_sDsd
0x18001c800  jmp     short loc_18001C813
0x18001c802  call    SymCryptMlDsaTemporariesFree
0x18001c807  mov     [rbx+18h], rdi
0x18001c80b  mov     rcx, rbx
0x18001c80e  call    MSCryptFree
0x18001c813  mov     rbx, [rsp+48h+arg_0]
0x18001c818  mov     eax, edi
0x18001c81a  add     rsp, 40h
0x18001c81e  pop     rdi
0x18001c81f  retn
0x18001c821  mov     rcx, [rcx+20h]
0x18001c825  xor     edi, edi
0x18001c827  test    rcx, rcx
0x18001c82a  jnz     short loc_18001C864
0x18001c82c  mov     rcx, [rbx+18h]
0x18001c830  test    rcx, rcx
0x18001c833  jnz     short loc_18001C802
0x18001c835  jmp     short loc_18001C80B
0x18001c837  cmp     dword ptr [rcx+4], 4D534B59h
0x18001c83e  jnz     loc_1800814A6
0x18001c844  cmp     dword ptr [rcx+8], 30002h
0x18001c84b  jnz     loc_1800814A6
0x18001c851  mov     eax, [rcx+0Ch]
0x18001c854  sub     eax, 40h ; '@'
0x18001c857  cmp     eax, 1C0h
0x18001c85c  ja      loc_1800814A6
0x18001c862  jmp     short loc_18001C821
0x18001c864  call    SymCryptDlkeyFree
0x18001c869  mov     [rbx+20h], rdi
0x18001c86d  jmp     short loc_18001C82C
0x1800814a6  lea     rbx, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800814ad  mov     r9d, 0DBh
0x1800814b3  mov     r8, rbx
0x1800814b6  lea     rdx, aStatus; "Status"
0x1800814bd  mov     ecx, 0C000000Dh
0x1800814c2  call    DebugTraceError
0x1800814c7  mov     r9d, 724h
0x1800814cd  lea     rdx, aStatus; "Status"
0x1800814d4  mov     r8, rbx
0x1800814d7  mov     ecx, 0C000000Dh
0x1800814dc  mov     edi, 0C000000Dh
0x1800814e1  call    DebugTraceError
0x1800814e6  nop
0x1800814e7  jmp     loc_18001C813
```
