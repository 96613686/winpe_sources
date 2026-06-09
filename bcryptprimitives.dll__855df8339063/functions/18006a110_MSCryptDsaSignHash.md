# MSCryptDsaSignHash

- ea: `0x18006a110`
- end: `0x18006a23e`
- name: `MSCryptDsaSignHash`
- size: `302`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000ecb0`
- `0x18005196c`
- `0x180055ac0`
- `0x180056cf0`
- `0x18006a110`

## string_xrefs

- `0x18006a21f`: `onecore\ds\security\cryptoapi\ncrypt\msprim\dsa\dsa.c`

## pseudocode

```c
__int64 __fastcall MSCryptDsaSignHash(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        __int64 a5,
        unsigned int a6,
        _DWORD *a7,
        int a8)
{
  int v9; // esi
  _DWORD *v10; // rdi
  int v11; // eax
  unsigned int v12; // ebx
  __int64 v13; // r9
  __int64 v14; // rcx
  __int64 v15; // rcx
  int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // rax
  unsigned int v19; // eax
  __int64 v21; // [rsp+70h] [rbp+8h] BYREF

  v9 = a3;
  v21 = 0;
  if ( !a1 || (v10 = a7) == 0 || !a3 || a8 )
  {
    v13 = 1361;
    goto LABEL_18;
  }
  v11 = ValidateDSAKey(a1, 1, &v21);
  v12 = v11;
  if ( v11 < 0 )
  {
    v13 = 1369;
LABEL_7:
    v14 = (unsigned int)v11;
LABEL_19:
    DebugTraceError(v14, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\dsa\\dsa.c", v13);
    return v12;
  }
  v15 = v21;
  if ( (*(_BYTE *)(v21 + 28) & 1) == 0 )
  {
    v12 = -1073741816;
    v13 = 1379;
    v14 = 3221225480LL;
    goto LABEL_19;
  }
  v16 = *(_DWORD *)(v21 + 16);
  if ( a4 != v16 )
  {
    v13 = 1388;
LABEL_18:
    v14 = 3221225485LL;
    v12 = -1073741811;
    goto LABEL_19;
  }
  v17 = a5;
  v18 = (unsigned int)(2 * v16);
  *v10 = v18;
  if ( v17 )
  {
    if ( a6 >= (unsigned int)v18 )
    {
      v19 = SymCryptDsaSignEx(*(_QWORD *)(v15 + 40), v9, a4, 0, 2, 0, v17, v18);
      if ( v19 )
      {
        v11 = SymcryptErrorCodeToNtStatus(v19);
        v12 = v11;
        v13 = 1422;
        goto LABEL_7;
      }
    }
    else
    {
      return (unsigned int)-1073741789;
    }
  }
  return v12;
}

```

## disassembly

```asm
0x18006a110  push    rbx
0x18006a112  push    rbp
0x18006a113  push    rsi
0x18006a114  push    rdi
0x18006a115  sub     rsp, 48h
0x18006a119  mov     ebp, r9d
0x18006a11c  mov     rsi, r8
0x18006a11f  mov     [rsp+68h+arg_0], 0
0x18006a128  test    rcx, rcx
0x18006a12b  jz      loc_18006A20F
0x18006a131  mov     rdi, [rsp+68h+arg_30]
0x18006a139  test    rdi, rdi
0x18006a13c  jz      loc_18006A20F
0x18006a142  test    r8, r8
0x18006a145  jz      loc_18006A20F
0x18006a14b  cmp     [rsp+68h+arg_38], 0
0x18006a153  jnz     loc_18006A20F
0x18006a159  lea     r8, [rsp+68h+arg_0]
0x18006a15e  mov     edx, 1
0x18006a163  call    ValidateDSAKey
0x18006a168  mov     ebx, eax
0x18006a16a  test    eax, eax
0x18006a16c  jns     short loc_18006A17B
0x18006a16e  mov     r9d, 559h
0x18006a174  mov     ecx, eax
0x18006a176  jmp     loc_18006A21F
0x18006a17b  mov     rcx, [rsp+68h+arg_0]
0x18006a180  test    byte ptr [rcx+1Ch], 1
0x18006a184  jnz     short loc_18006A19B
0x18006a186  mov     ebx, 0C0000008h
0x18006a18b  mov     r9d, 563h
0x18006a191  mov     ecx, 0C0000008h
0x18006a196  jmp     loc_18006A21F
0x18006a19b  mov     eax, [rcx+10h]
0x18006a19e  cmp     ebp, eax
0x18006a1a0  jz      short loc_18006A1AA
0x18006a1a2  mov     r9d, 56Ch
0x18006a1a8  jmp     short loc_18006A215
0x18006a1aa  mov     rdx, [rsp+68h+arg_20]
0x18006a1b2  add     eax, eax
0x18006a1b4  mov     [rdi], eax
0x18006a1b6  test    rdx, rdx
0x18006a1b9  jz      short loc_18006A232
0x18006a1bb  cmp     [rsp+68h+arg_28], eax
0x18006a1c2  jnb     short loc_18006A1CB
0x18006a1c4  mov     ebx, 0C0000023h
0x18006a1c9  jmp     short loc_18006A232
0x18006a1cb  mov     rcx, [rcx+28h]
0x18006a1cf  mov     r8, rbp
0x18006a1d2  mov     [rsp+68h+var_30], rax
0x18006a1d7  xor     r9d, r9d
0x18006a1da  mov     [rsp+68h+var_38], rdx
0x18006a1df  mov     rdx, rsi
0x18006a1e2  mov     [rsp+68h+var_40], 0
0x18006a1ea  mov     [rsp+68h+var_48], 2
0x18006a1f2  call    SymCryptDsaSignEx
0x18006a1f7  test    eax, eax
0x18006a1f9  jz      short loc_18006A232
0x18006a1fb  mov     ecx, eax
0x18006a1fd  call    SymcryptErrorCodeToNtStatus
0x18006a202  mov     ebx, eax
0x18006a204  mov     r9d, 58Eh
0x18006a20a  jmp     loc_18006A174
0x18006a20f  mov     r9d, 551h
0x18006a215  mov     ecx, 0C000000Dh
0x18006a21a  mov     ebx, 0C000000Dh
0x18006a21f  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18006a226  lea     rdx, aStatus; "Status"
0x18006a22d  call    DebugTraceError
0x18006a232  mov     eax, ebx
0x18006a234  add     rsp, 48h
0x18006a238  pop     rdi
0x18006a239  pop     rsi
0x18006a23a  pop     rbp
0x18006a23b  pop     rbx
0x18006a23c  retn
```
