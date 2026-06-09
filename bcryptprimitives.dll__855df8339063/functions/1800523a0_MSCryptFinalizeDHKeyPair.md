# MSCryptFinalizeDHKeyPair

- ea: `0x1800523a0`
- end: `0x180052524`
- name: `MSCryptFinalizeDHKeyPair`
- size: `388`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x18000ecb0`
- `0x18001bf34`
- `0x1800523a0`
- `0x180056cf0`
- `0x180057bb4`
- `0x180071418`
- `0x180071edc`

## string_xrefs

- `0x1800524d3`: `onecore\ds\security\cryptoapi\ncrypt\msprim\dsa\dh.c`
- `0x180052503`: `onecore\ds\security\cryptoapi\ncrypt\msprim\dsa\dh.c`

## pseudocode

```c
__int64 __fastcall MSCryptFinalizeDHKeyPair(__int64 a1, int a2)
{
  unsigned int v2; // edi
  __int64 v4; // rdx
  __int64 v5; // r9
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 (__fastcall **v8)(); // rcx
  unsigned int v9; // eax
  __int64 v10; // rax

  v2 = 0;
  if ( !a1 || a2 && a2 != 24 )
  {
    v5 = 1280;
    goto LABEL_27;
  }
  if ( *(_DWORD *)(a1 + 4) != 1297304409
    || *(_DWORD *)(a1 + 8) != 196610
    || (v4 = *(unsigned int *)(a1 + 12), (unsigned int)(v4 - 64) > 0x1C0) )
  {
    DebugTraceError(3221225485LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\dsa\\dh.c", 219);
    v5 = 1287;
    goto LABEL_27;
  }
  if ( (*(_BYTE *)(a1 + 16) & 1) != 0 )
  {
    v2 = -1073741816;
    v5 = 1295;
    v6 = 3221225480LL;
LABEL_28:
    DebugTraceError(v6, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\dsa\\dh.c", v5);
    return v2;
  }
  if ( (*(_BYTE *)(a1 + 16) & 2) != 0 )
  {
    if ( !*(_QWORD *)(a1 + 24) )
    {
      v5 = 1304;
LABEL_27:
      v2 = -1073741811;
      v6 = 3221225485LL;
      goto LABEL_28;
    }
  }
  else
  {
    if ( (unsigned int)v4 >= 0x100 )
    {
      v9 = SymCryptDlgroupSetValueSafePrime(2, *(_QWORD *)(a1 + 24));
    }
    else
    {
      v7 = *(_QWORD *)(a1 + 24);
      v8 = &SymCryptSha1Algorithm_default;
      if ( (unsigned int)v4 >= 0x80 )
        v8 = (__int64 (__fastcall **)())&SymCryptSha256Algorithm_default;
      v9 = SymCryptDlgroupGenerate(v8, 2, v7);
    }
    if ( v9 )
    {
      v2 = SymcryptErrorCodeToNtStatus(v9);
      v6 = v2;
      v5 = 1327;
      goto LABEL_28;
    }
    *(_DWORD *)(a1 + 16) |= 2u;
  }
  if ( !*(_QWORD *)(a1 + 32) )
  {
    v10 = SymCryptDlkeyAllocate(*(_QWORD *)(a1 + 24), v4);
    *(_QWORD *)(a1 + 32) = v10;
    if ( !v10 )
    {
      v2 = -1073741801;
      v5 = 1342;
      v6 = 3221225495LL;
      goto LABEL_28;
    }
    SymCryptDlkeyGenerate(*(_BYTE *)(*(_QWORD *)(a1 + 24) + 40LL) != 0 ? 0x2000 : 8448, v10);
  }
  *(_DWORD *)(a1 + 16) |= 1u;
  return v2;
}

```

## disassembly

```asm
0x1800523a0  mov     [rsp+arg_0], rbx
0x1800523a5  push    rdi
0x1800523a6  sub     rsp, 20h
0x1800523aa  xor     edi, edi
0x1800523ac  mov     rbx, rcx
0x1800523af  test    rcx, rcx
0x1800523b2  jz      loc_1800524F3
0x1800523b8  test    edx, edx
0x1800523ba  jz      short loc_1800523C5
0x1800523bc  cmp     edx, 18h
0x1800523bf  jnz     loc_1800524F3
0x1800523c5  cmp     dword ptr [rcx+4], 4D534B59h
0x1800523cc  jnz     loc_1800524CD
0x1800523d2  cmp     dword ptr [rcx+8], 30002h
0x1800523d9  jnz     loc_1800524CD
0x1800523df  mov     edx, [rcx+0Ch]
0x1800523e2  lea     eax, [rdx-40h]
0x1800523e5  cmp     eax, 1C0h
0x1800523ea  ja      loc_1800524CD
0x1800523f0  test    byte ptr [rcx+10h], 1
0x1800523f4  jz      short loc_18005240B
0x1800523f6  mov     edi, 0C0000008h
0x1800523fb  mov     r9d, 50Fh
0x180052401  mov     ecx, 0C0000008h
0x180052406  jmp     loc_180052503
0x18005240b  test    byte ptr [rcx+10h], 2
0x18005240f  jz      short loc_180052422
0x180052411  cmp     [rcx+18h], rdi
0x180052415  jnz     short loc_18005247E
0x180052417  mov     r9d, 518h
0x18005241d  jmp     loc_1800524F9
0x180052422  cmp     edx, 100h
0x180052428  jnb     short loc_180052452
0x18005242a  mov     r8, [rbx+18h]
0x18005242e  lea     rax, SymCryptSha256Algorithm_default
0x180052435  cmp     edx, 80h
0x18005243b  lea     rcx, SymCryptSha1Algorithm_default
0x180052442  mov     edx, 2
0x180052447  cmovnb  rcx, rax
0x18005244b  call    SymCryptDlgroupGenerate
0x180052450  jmp     short loc_180052460
0x180052452  mov     rdx, [rcx+18h]
0x180052456  mov     ecx, 2
0x18005245b  call    SymCryptDlgroupSetValueSafePrime
0x180052460  test    eax, eax
0x180052462  jz      short loc_18005247A
0x180052464  mov     ecx, eax
0x180052466  call    SymcryptErrorCodeToNtStatus
0x18005246b  mov     edi, eax
0x18005246d  mov     ecx, eax
0x18005246f  mov     r9d, 52Fh
0x180052475  jmp     loc_180052503
0x18005247a  or      dword ptr [rbx+10h], 2
0x18005247e  cmp     [rbx+20h], rdi
0x180052482  jnz     short loc_1800524C7
0x180052484  mov     rcx, [rbx+18h]
0x180052488  call    SymCryptDlkeyAllocate
0x18005248d  mov     [rbx+20h], rax
0x180052491  mov     rdx, rax
0x180052494  test    rax, rax
0x180052497  jnz     short loc_1800524AB
0x180052499  mov     edi, 0C0000017h
0x18005249e  mov     r9d, 53Eh
0x1800524a4  mov     ecx, 0C0000017h
0x1800524a9  jmp     short loc_180052503
0x1800524ab  mov     rax, [rbx+18h]
0x1800524af  mov     cl, [rax+28h]
0x1800524b2  neg     cl
0x1800524b4  sbb     ecx, ecx
0x1800524b6  and     ecx, 0FFFFFF00h
0x1800524bc  add     ecx, 2100h
0x1800524c2  call    SymCryptDlkeyGenerate
0x1800524c7  or      dword ptr [rbx+10h], 1
0x1800524cb  jmp     short loc_180052516
0x1800524cd  mov     r9d, 0DBh
0x1800524d3  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800524da  lea     rdx, aStatus; "Status"
0x1800524e1  mov     ecx, 0C000000Dh
0x1800524e6  call    DebugTraceError
0x1800524eb  mov     r9d, 507h
0x1800524f1  jmp     short loc_1800524F9
0x1800524f3  mov     r9d, 500h
0x1800524f9  mov     edi, 0C000000Dh
0x1800524fe  mov     ecx, 0C000000Dh
0x180052503  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005250a  lea     rdx, aStatus; "Status"
0x180052511  call    DebugTraceError
0x180052516  mov     rbx, [rsp+28h+arg_0]
0x18005251b  mov     eax, edi
0x18005251d  add     rsp, 20h
0x180052521  pop     rdi
0x180052522  retn
```
