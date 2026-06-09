# MSCryptSetDHKeyPairProperty

- ea: `0x180068ab8`
- end: `0x180068d84`
- name: `MSCryptSetDHKeyPairProperty`
- size: `716`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180068d90`

## callees

- `0x18000ecb0`
- `0x18001b67c`
- `0x18001c878`
- `0x180056cf0`
- `0x1800581c0`
- `0x180058204`
- `0x180058288`
- `0x180068ab8`
- `0x180068e60`
- `0x18007f765`

## string_xrefs

- `0x180068d65`: `onecore\ds\security\cryptoapi\ncrypt\msprim\dsa\dh.c`

## pseudocode

```c
__int64 __fastcall MSCryptSetDHKeyPairProperty(__int64 a1, const wchar_t *a2, _DWORD *a3, unsigned int a4, int a5)
{
  unsigned __int64 v5; // rbp
  int v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // r9
  __int64 v11; // rcx
  __int64 v12; // rdi
  int v13; // esi
  __int64 v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rdi
  int v17; // edx
  __int64 v18; // rax
  unsigned int v19; // eax
  __int64 v21; // [rsp+A0h] [rbp+8h] BYREF

  v5 = a4;
  v21 = 0;
  if ( !a1 || !a2 || !a3 || !a4 || a5 )
  {
    v10 = 788;
    goto LABEL_44;
  }
  v8 = ValidateDHKey(a1, 0, &v21);
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = 795;
LABEL_8:
    v11 = (unsigned int)v8;
LABEL_45:
    DebugTraceError(v11, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\dsa\\dh.c", v10);
    return v9;
  }
  if ( !wcscmp_0(a2, L"DHParameters") || !wcscmp_0(a2, L"SecretAgreementParam") )
  {
    v16 = v21;
    v17 = *(_DWORD *)(v21 + 12);
    if ( v5 < (unsigned __int64)(unsigned int)(2 * v17) + 12 )
      return (unsigned int)-1073741789;
    if ( a3[1] != 1297107012 || a3[2] != v17 )
    {
      v10 = 819;
      goto LABEL_44;
    }
    if ( (*(_BYTE *)(v21 + 16) & 2) != 0 )
    {
      if ( *(_QWORD *)(v21 + 32) )
      {
        SymCryptDlkeyFree();
        *(_QWORD *)(v16 + 32) = 0;
      }
      SymCryptMlDsaTemporariesFree(*(_QWORD *)(v16 + 24));
      v18 = SymCryptDlgroupAllocate((unsigned int)(8 * *(_DWORD *)(v16 + 12)), 0);
      *(_QWORD *)(v16 + 24) = v18;
      if ( !v18 )
      {
        v10 = 837;
        goto LABEL_28;
      }
    }
    v19 = SymCryptDlgroupSetValue(
            (int)a3 + 12,
            *(_DWORD *)(v16 + 12),
            0,
            0,
            (__int64)a3 + (unsigned int)a3[2] + 12,
            *(_DWORD *)(v16 + 12),
            2,
            0,
            0,
            0,
            0,
            0,
            *(_QWORD *)(v16 + 24));
    if ( v19 )
    {
      v8 = SymcryptErrorCodeToNtStatus(v19);
      v9 = v8;
      v10 = 862;
      goto LABEL_8;
    }
    *(_DWORD *)(v16 + 16) |= 2u;
  }
  else
  {
    if ( !wcscmp_0(a2, L"PrivKeyVal") )
      return (unsigned int)SetPrivateKeyVal(v21, a3, (unsigned int)v5);
    if ( wcscmp_0(a2, L"KeyLength") && wcscmp_0(a2, L"KeyStrength") )
    {
      v10 = 940;
LABEL_16:
      v9 = -1073741637;
      v11 = 3221225659LL;
      goto LABEL_45;
    }
    v12 = v21;
    if ( (*(_BYTE *)(v21 + 16) & 2) != 0 )
    {
      v10 = 893;
      goto LABEL_16;
    }
    if ( (_DWORD)v5 != 4 )
    {
      v10 = 900;
LABEL_44:
      v11 = 3221225485LL;
      v9 = -1073741811;
      goto LABEL_45;
    }
    v13 = *a3 >> 3;
    if ( (unsigned int)(v13 - 64) > 0x1C0 )
    {
      v10 = 910;
      goto LABEL_44;
    }
    if ( *(_DWORD *)(v21 + 12) != v13 )
    {
      v14 = *(_QWORD *)(v21 + 24);
      if ( v14 )
      {
        SymCryptMlDsaTemporariesFree(v14);
        *(_QWORD *)(v12 + 24) = 0;
      }
    }
    *(_DWORD *)(v12 + 12) = v13;
    if ( !*(_QWORD *)(v12 + 24) )
    {
      v15 = SymCryptDlgroupAllocate((unsigned int)(8 * v13), 0);
      *(_QWORD *)(v12 + 24) = v15;
      if ( !v15 )
      {
        v10 = 929;
LABEL_28:
        v9 = -1073741801;
        v11 = 3221225495LL;
        goto LABEL_45;
      }
    }
  }
  return v9;
}

```

## disassembly

```asm
0x180068ab8  mov     rax, rsp
0x180068abb  push    rbx
0x180068abc  push    rbp
0x180068abd  push    rsi
0x180068abe  push    rdi
0x180068abf  sub     rsp, 78h
0x180068ac3  mov     ebp, r9d
0x180068ac6  mov     rsi, r8
0x180068ac9  mov     qword ptr [rax+8], 0
0x180068ad1  mov     rdi, rdx
0x180068ad4  test    rcx, rcx
0x180068ad7  jz      loc_180068D55
0x180068add  test    rdx, rdx
0x180068ae0  jz      loc_180068D55
0x180068ae6  test    r8, r8
0x180068ae9  jz      loc_180068D55
0x180068aef  test    r9d, r9d
0x180068af2  jz      loc_180068D55
0x180068af8  cmp     [rsp+98h+arg_20], 0
0x180068b00  jnz     loc_180068D55
0x180068b06  lea     r8, [rax+8]
0x180068b0a  xor     edx, edx
0x180068b0c  call    ValidateDHKey
0x180068b11  mov     ebx, eax
0x180068b13  test    eax, eax
0x180068b15  jns     short loc_180068B24
0x180068b17  mov     r9d, 31Bh
0x180068b1d  mov     ecx, eax
0x180068b1f  jmp     loc_180068D65
0x180068b24  lea     rdx, aDhparameters; "DHParameters"
0x180068b2b  mov     rcx, rdi; String1
0x180068b2e  call    wcscmp_0
0x180068b33  test    eax, eax
0x180068b35  jz      loc_180068C53
0x180068b3b  lea     rdx, aSecretagreemen; "SecretAgreementParam"
0x180068b42  mov     rcx, rdi; String1
0x180068b45  call    wcscmp_0
0x180068b4a  test    eax, eax
0x180068b4c  jz      loc_180068C53
0x180068b52  lea     rdx, aPrivkeyval; "PrivKeyVal"
0x180068b59  mov     rcx, rdi; String1
0x180068b5c  call    wcscmp_0
0x180068b61  test    eax, eax
0x180068b63  jnz     short loc_180068B7F
0x180068b65  mov     rcx, [rsp+98h+arg_0]
0x180068b6d  mov     r8d, ebp
0x180068b70  mov     rdx, rsi
0x180068b73  call    SetPrivateKeyVal
0x180068b78  mov     ebx, eax
0x180068b7a  jmp     loc_180068D78
0x180068b7f  lea     rdx, aKeylength; "KeyLength"
0x180068b86  mov     rcx, rdi; String1
0x180068b89  call    wcscmp_0
0x180068b8e  test    eax, eax
0x180068b90  jz      short loc_180068BBA
0x180068b92  lea     rdx, aKeystrength; "KeyStrength"
0x180068b99  mov     rcx, rdi; String1
0x180068b9c  call    wcscmp_0
0x180068ba1  test    eax, eax
0x180068ba3  jz      short loc_180068BBA
0x180068ba5  mov     r9d, 3ACh
0x180068bab  mov     ebx, 0C00000BBh
0x180068bb0  mov     ecx, 0C00000BBh
0x180068bb5  jmp     loc_180068D65
0x180068bba  mov     rdi, [rsp+98h+arg_0]
0x180068bc2  test    byte ptr [rdi+10h], 2
0x180068bc6  jz      short loc_180068BD0
0x180068bc8  mov     r9d, 37Dh
0x180068bce  jmp     short loc_180068BAB
0x180068bd0  cmp     ebp, 4
0x180068bd3  jz      short loc_180068BE0
0x180068bd5  mov     r9d, 384h
0x180068bdb  jmp     loc_180068D5B
0x180068be0  mov     esi, [rsi]
0x180068be2  shr     esi, 3
0x180068be5  lea     eax, [rsi-40h]
0x180068be8  cmp     eax, 1C0h
0x180068bed  ja      short loc_180068C48
0x180068bef  cmp     [rdi+0Ch], esi
0x180068bf2  jz      short loc_180068C0A
0x180068bf4  mov     rcx, [rdi+18h]
0x180068bf8  test    rcx, rcx
0x180068bfb  jz      short loc_180068C0A
0x180068bfd  call    SymCryptMlDsaTemporariesFree
0x180068c02  mov     qword ptr [rdi+18h], 0
0x180068c0a  mov     [rdi+0Ch], esi
0x180068c0d  cmp     qword ptr [rdi+18h], 0
0x180068c12  jnz     loc_180068D78
0x180068c18  lea     ecx, ds:0[rsi*8]
0x180068c1f  xor     edx, edx
0x180068c21  call    SymCryptDlgroupAllocate
0x180068c26  mov     [rdi+18h], rax
0x180068c2a  test    rax, rax
0x180068c2d  jnz     loc_180068D78
0x180068c33  mov     r9d, 3A1h
0x180068c39  mov     ebx, 0C0000017h
0x180068c3e  mov     ecx, 0C0000017h
0x180068c43  jmp     loc_180068D65
0x180068c48  mov     r9d, 38Eh
0x180068c4e  jmp     loc_180068D5B
0x180068c53  mov     rdi, [rsp+98h+arg_0]
0x180068c5b  mov     edx, [rdi+0Ch]
0x180068c5e  lea     ecx, [rdx+rdx]
0x180068c61  add     rcx, 0Ch
0x180068c65  cmp     rbp, rcx
0x180068c68  jnb     short loc_180068C74
0x180068c6a  mov     ebx, 0C0000023h
0x180068c6f  jmp     loc_180068D78
0x180068c74  cmp     dword ptr [rsi+4], 4D504844h
0x180068c7b  jnz     loc_180068D4D
0x180068c81  cmp     [rsi+8], edx
0x180068c84  jnz     loc_180068D4D
0x180068c8a  test    byte ptr [rdi+10h], 2
0x180068c8e  jz      short loc_180068CD0
0x180068c90  mov     rcx, [rdi+20h]
0x180068c94  test    rcx, rcx
0x180068c97  jz      short loc_180068CA6
0x180068c99  call    SymCryptDlkeyFree
0x180068c9e  mov     qword ptr [rdi+20h], 0
0x180068ca6  mov     rcx, [rdi+18h]
0x180068caa  call    SymCryptMlDsaTemporariesFree
0x180068caf  mov     ecx, [rdi+0Ch]
0x180068cb2  xor     edx, edx
0x180068cb4  shl     ecx, 3
0x180068cb7  call    SymCryptDlgroupAllocate
0x180068cbc  mov     [rdi+18h], rax
0x180068cc0  test    rax, rax
0x180068cc3  jnz     short loc_180068CD0
0x180068cc5  mov     r9d, 345h
0x180068ccb  jmp     loc_180068C39
0x180068cd0  mov     rax, [rdi+18h]
0x180068cd4  lea     rcx, [rsi+0Ch]; int
0x180068cd8  mov     r8d, [rsi+8]
0x180068cdc  xor     r9d, r9d; int
0x180068cdf  mov     edx, [rdi+0Ch]; int
0x180068ce2  add     r8, rcx
0x180068ce5  mov     [rsp+98h+var_38], rax; __int64
0x180068cea  mov     [rsp+98h+var_40], 0; int
0x180068cf2  mov     [rsp+98h+var_48], 0; int
0x180068cfa  mov     [rsp+98h+Size], 0; Size
0x180068d03  mov     [rsp+98h+var_58], 0; __int64
0x180068d0c  mov     [rsp+98h+var_60], 0; __int64
0x180068d15  mov     [rsp+98h+var_68], 2; int
0x180068d1d  mov     qword ptr [rsp+98h+var_70], rdx; int
0x180068d22  mov     [rsp+98h+var_78], r8; __int64
0x180068d27  xor     r8d, r8d; int
0x180068d2a  call    SymCryptDlgroupSetValue
0x180068d2f  test    eax, eax
0x180068d31  jz      short loc_180068D47
0x180068d33  mov     ecx, eax
0x180068d35  call    SymcryptErrorCodeToNtStatus
0x180068d3a  mov     ebx, eax
0x180068d3c  mov     r9d, 35Eh
0x180068d42  jmp     loc_180068B1D
0x180068d47  or      dword ptr [rdi+10h], 2
0x180068d4b  jmp     short loc_180068D78
0x180068d4d  mov     r9d, 333h
0x180068d53  jmp     short loc_180068D5B
0x180068d55  mov     r9d, 314h
0x180068d5b  mov     ecx, 0C000000Dh
0x180068d60  mov     ebx, 0C000000Dh
0x180068d65  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180068d6c  lea     rdx, aStatus; "Status"
0x180068d73  call    DebugTraceError
0x180068d78  mov     eax, ebx
0x180068d7a  add     rsp, 78h
0x180068d7e  pop     rdi
0x180068d7f  pop     rsi
0x180068d80  pop     rbp
0x180068d81  pop     rbx
0x180068d82  retn
```
