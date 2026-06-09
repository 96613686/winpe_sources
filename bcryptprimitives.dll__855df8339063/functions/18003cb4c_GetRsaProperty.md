# GetRsaProperty

- ea: `0x18003cb4c`
- end: `0x18003ce52`
- name: `GetRsaProperty`
- size: `774`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003cb20`
- `0x180067358`
- `0x18006c8c0`

## callees

- `0x18000ecb0`
- `0x18000ee60`
- `0x18003cb4c`
- `0x18003ce58`
- `0x18003cfd4`
- `0x18006c820`
- `0x18007f765`

## import_xrefs

- `ntdll!wcscpy_s` at `0x180081f91`
- `ntdll!wcscpy_s` at `0x180081f91`

## string_xrefs

- `0x18003cbbf`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x18003cd5d`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x180081f7f`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`

## pseudocode

```c
__int64 __fastcall GetRsaProperty(
        __int64 a1,
        const wchar_t *a2,
        __int64 a3,
        unsigned int a4,
        unsigned int *a5,
        unsigned int a6,
        char a7)
{
  unsigned __int64 v8; // rsi
  unsigned int v11; // ebx
  __int64 v12; // rbp
  __int64 v13; // rax
  int v14; // eax
  unsigned int v15; // eax
  char v17; // r8
  unsigned int v18; // ecx
  bool v19; // zf
  const wchar_t *v20; // r8
  __int64 v21; // r9
  __int64 v22; // rcx

  v8 = a4;
  if ( a6 )
  {
    v11 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)a2,
        a3,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c",
        78);
    return v11;
  }
  if ( !a2 )
  {
    v11 = -1073741811;
    v21 = 597;
    v22 = 3221225485LL;
LABEL_50:
    DebugTraceError(v22, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c", v21);
    return v11;
  }
  if ( !a1 || *(_DWORD *)(a1 + 4) != 1297306187 && *(_DWORD *)(a1 + 4) != 1297306177 )
  {
    v11 = -1073741816;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)a2,
        a3,
        (unsigned int)"Status",
        8,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c",
        93);
    return v11;
  }
  if ( !wcscmp_0(a2, L"AlgorithmName") )
  {
    v17 = a7;
    v18 = a7 != 0 ? 18 : 8;
    *a5 = v18;
    if ( !a3 )
      return 0;
    if ( (unsigned int)v8 >= v18 )
    {
      v19 = v17 == 0;
      v20 = L"RSA_SIGN";
      if ( v19 )
        v20 = L"RSA";
      wcscpy_s((wchar_t *)a3, v8 >> 1, v20);
      return 0;
    }
    return (unsigned int)-1073741789;
  }
  if ( validateMSCryptRsaAlgorithm(a1) )
  {
    if ( !wcscmp_0(a2, L"PaddingSchemes") )
    {
      *a5 = 4;
      if ( !a3 )
        return 0;
      if ( (unsigned int)v8 >= 4 )
      {
        *(_DWORD *)a3 = a7 != 0 ? 20 : 30;
        return 0;
      }
      return (unsigned int)-1073741789;
    }
    if ( !wcscmp_0(a2, L"KeyLengths") )
    {
      *a5 = 12;
      if ( !a3 )
        return 0;
      if ( (unsigned int)v8 >= 0xC )
      {
        *(_DWORD *)a3 = 512;
        *(_DWORD *)(a3 + 4) = 0x4000;
        *(_DWORD *)(a3 + 8) = 8;
        return 0;
      }
      return (unsigned int)-1073741789;
    }
    v21 = 707;
LABEL_49:
    v11 = -1073741637;
    v22 = 3221225659LL;
    goto LABEL_50;
  }
  v12 = validateMSCryptRsaKey(a1);
  if ( v12 )
  {
    if ( !wcscmp_0(a2, L"KeyStrength") || !wcscmp_0(a2, L"KeyLength") || !wcscmp_0(a2, L"PublicKeyLength") )
    {
      *a5 = 4;
      if ( !a3 )
        return 0;
      if ( (unsigned int)v8 >= 4 )
      {
        v15 = *(_DWORD *)(v12 + 12);
LABEL_22:
        *(_DWORD *)a3 = v15;
        return 0;
      }
      return (unsigned int)-1073741789;
    }
    if ( !wcscmp_0(a2, L"BlockLength") || !wcscmp_0(a2, L"SignatureLength") )
    {
      *a5 = 4;
      if ( !a3 )
        return 0;
      if ( (unsigned int)v8 >= 4 )
      {
        v13 = *(_QWORD *)(v12 + 32);
        if ( v13 )
          v14 = *(_DWORD *)(v13 + 16);
        else
          v14 = *(_DWORD *)(v12 + 12);
        v15 = (unsigned int)(v14 + 7) >> 3;
        goto LABEL_22;
      }
      return (unsigned int)-1073741789;
    }
    if ( !wcscmp_0(a2, L"IsIfxTpmWeakKey") )
    {
      a6 = 0;
      *a5 = 4;
      if ( !a3 )
        return 0;
      if ( (unsigned int)v8 >= 4 )
      {
        v11 = IsIfxTpmWeakKeyProperty(a1, &a6);
        if ( (v11 & 0x80000000) != 0 )
          return v11;
        v15 = a6;
        goto LABEL_22;
      }
      return (unsigned int)-1073741789;
    }
    v21 = 781;
    goto LABEL_49;
  }
  return 3221225480LL;
}

```

## disassembly

```asm
0x18003cb4c  push    rbx
0x18003cb4e  push    rbp
0x18003cb4f  push    rsi
0x18003cb50  push    rdi
0x18003cb51  push    r14
0x18003cb53  sub     rsp, 40h
0x18003cb57  cmp     [rsp+68h+arg_28], 0
0x18003cb5f  mov     rdi, r8
0x18003cb62  mov     esi, r9d
0x18003cb65  mov     rbx, rdx
0x18003cb68  mov     r14, rcx
0x18003cb6b  jnz     loc_18003CD2F
0x18003cb71  test    rdx, rdx
0x18003cb74  jz      loc_18003CDED
0x18003cb7a  test    rcx, rcx
0x18003cb7d  jz      short loc_18003CB91
0x18003cb7f  cmp     dword ptr [rcx+4], 4D53524Bh
0x18003cb86  jz      short loc_18003CBD8
0x18003cb88  cmp     dword ptr [rcx+4], 4D535241h
0x18003cb8f  jz      short loc_18003CBD8
0x18003cb91  mov     ebx, 0C0000008h
0x18003cb96  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cb9d  lea     rax, WPP_GLOBAL_Control
0x18003cba4  cmp     rcx, rax
0x18003cba7  jz      loc_18003CCB9
0x18003cbad  test    byte ptr [rcx+1Ch], 1
0x18003cbb1  jz      loc_18003CCB9
0x18003cbb7  mov     [rsp+68h+var_38], 25Dh
0x18003cbbf  lea     rax, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003cbc6  mov     [rsp+68h+var_40], rax
0x18003cbcb  mov     [rsp+68h+var_48], 0C0000008h
0x18003cbd3  jmp     loc_18003CD71
0x18003cbd8  lea     rdx, aAlgorithmname; "AlgorithmName"
0x18003cbdf  mov     rcx, rbx; String1
0x18003cbe2  call    wcscmp_0
0x18003cbe7  test    eax, eax
0x18003cbe9  jz      loc_18003CD90
0x18003cbef  mov     rcx, r14
0x18003cbf2  call    validateMSCryptRsaAlgorithm
0x18003cbf7  test    rax, rax
0x18003cbfa  jnz     loc_18003CCC7
0x18003cc00  mov     rcx, r14
0x18003cc03  call    validateMSCryptRsaKey
0x18003cc08  mov     rbp, rax
0x18003cc0b  test    rax, rax
0x18003cc0e  jz      loc_18003CD86
0x18003cc14  lea     rdx, aKeystrength; "KeyStrength"
0x18003cc1b  mov     rcx, rbx; String1
0x18003cc1e  call    wcscmp_0
0x18003cc23  test    eax, eax
0x18003cc25  jz      loc_18003CD0B
0x18003cc2b  lea     rdx, aKeylength; "KeyLength"
0x18003cc32  mov     rcx, rbx; String1
0x18003cc35  call    wcscmp_0
0x18003cc3a  test    eax, eax
0x18003cc3c  jz      loc_18003CD0B
0x18003cc42  lea     rdx, aPublickeylengt; "PublicKeyLength"
0x18003cc49  mov     rcx, rbx; String1
0x18003cc4c  call    wcscmp_0
0x18003cc51  test    eax, eax
0x18003cc53  jz      loc_18003CD0B
0x18003cc59  lea     rdx, aBlocklength; "BlockLength"
0x18003cc60  mov     rcx, rbx; String1
0x18003cc63  call    wcscmp_0
0x18003cc68  test    eax, eax
0x18003cc6a  jz      short loc_18003CC83
0x18003cc6c  lea     rdx, aSignaturelengt; "SignatureLength"
0x18003cc73  mov     rcx, rbx; String1
0x18003cc76  call    wcscmp_0
0x18003cc7b  test    eax, eax
0x18003cc7d  jnz     loc_180081FA3
0x18003cc83  mov     rax, [rsp+68h+arg_20]
0x18003cc8b  mov     dword ptr [rax], 4
0x18003cc91  test    rdi, rdi
0x18003cc94  jz      short loc_18003CCB7
0x18003cc96  cmp     esi, 4
0x18003cc99  jb      loc_18003CD28
0x18003cc9f  mov     rax, [rbp+20h]
0x18003cca3  test    rax, rax
0x18003cca6  jz      loc_18003CDE5
0x18003ccac  mov     eax, [rax+10h]
0x18003ccaf  add     eax, 7
0x18003ccb2  shr     eax, 3
0x18003ccb5  mov     [rdi], eax
0x18003ccb7  xor     ebx, ebx
0x18003ccb9  mov     eax, ebx
0x18003ccbb  add     rsp, 40h
0x18003ccbf  pop     r14
0x18003ccc1  pop     rdi
0x18003ccc2  pop     rsi
0x18003ccc3  pop     rbp
0x18003ccc4  pop     rbx
0x18003ccc5  retn
0x18003ccc7  lea     rdx, aPaddingschemes; "PaddingSchemes"
0x18003ccce  mov     rcx, rbx; String1
0x18003ccd1  call    wcscmp_0
0x18003ccd6  test    eax, eax
0x18003ccd8  jnz     loc_18003CE02
0x18003ccde  mov     rax, [rsp+68h+arg_20]
0x18003cce6  mov     dword ptr [rax], 4
0x18003ccec  test    rdi, rdi
0x18003ccef  jz      short loc_18003CCB7
0x18003ccf1  cmp     esi, 4
0x18003ccf4  jb      short loc_18003CD28
0x18003ccf6  mov     al, [rsp+68h+arg_30]
0x18003ccfd  neg     al
0x18003ccff  sbb     ecx, ecx
0x18003cd01  and     ecx, 0FFFFFFF6h
0x18003cd04  add     ecx, 1Eh
0x18003cd07  mov     [rdi], ecx
0x18003cd09  jmp     short loc_18003CCB7
0x18003cd0b  mov     rax, [rsp+68h+arg_20]
0x18003cd13  mov     dword ptr [rax], 4
0x18003cd19  test    rdi, rdi
0x18003cd1c  jz      short loc_18003CCB7
0x18003cd1e  cmp     esi, 4
0x18003cd21  jb      short loc_18003CD28
0x18003cd23  mov     eax, [rbp+0Ch]
0x18003cd26  jmp     short loc_18003CCB5
0x18003cd28  mov     ebx, 0C0000023h
0x18003cd2d  jmp     short loc_18003CCB9
0x18003cd2f  mov     ebx, 0C000000Dh
0x18003cd34  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cd3b  lea     rax, WPP_GLOBAL_Control
0x18003cd42  cmp     rcx, rax
0x18003cd45  jz      loc_18003CCB9
0x18003cd4b  test    byte ptr [rcx+1Ch], 1
0x18003cd4f  jz      loc_18003CCB9
0x18003cd55  mov     [rsp+68h+var_38], 24Eh
0x18003cd5d  lea     rax, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003cd64  mov     [rsp+68h+var_40], rax
0x18003cd69  mov     [rsp+68h+var_48], 0C000000Dh
0x18003cd71  mov     rcx, [rcx+10h]
0x18003cd75  lea     r9, aStatus; "Status"
0x18003cd7c  call    WPP_SF_sDsd
0x18003cd81  jmp     loc_18003CCB9
0x18003cd86  mov     eax, 0C0000008h
0x18003cd8b  jmp     loc_18003CCBB
0x18003cd90  mov     r8b, [rsp+68h+arg_30]
0x18003cd98  mov     al, r8b
0x18003cd9b  neg     al
0x18003cd9d  mov     rax, [rsp+68h+arg_20]
0x18003cda5  sbb     ecx, ecx
0x18003cda7  and     ecx, 0Ah
0x18003cdaa  add     ecx, 8
0x18003cdad  mov     [rax], ecx
0x18003cdaf  test    rdi, rdi
0x18003cdb2  jz      loc_18003CCB7
0x18003cdb8  cmp     esi, ecx
0x18003cdba  jb      loc_18003CD28
0x18003cdc0  mov     rdx, rsi
0x18003cdc3  mov     rcx, rdi; Destination
0x18003cdc6  shr     rdx, 1; SizeInWords
0x18003cdc9  test    r8b, r8b
0x18003cdcc  lea     r8, aRsaSign; "RSA_SIGN"
0x18003cdd3  jnz     loc_180081F91
0x18003cdd9  lea     r8, aRsa; "RSA"
0x18003cde0  jmp     loc_180081F91
0x18003cde5  mov     eax, [rbp+0Ch]
0x18003cde8  jmp     loc_18003CCAF
0x18003cded  mov     ebx, 0C000000Dh
0x18003cdf2  mov     r9d, 255h
0x18003cdf8  mov     ecx, 0C000000Dh
0x18003cdfd  jmp     loc_180081F78
0x18003ce02  lea     rdx, aKeylengths; "KeyLengths"
0x18003ce09  mov     rcx, rbx; String1
0x18003ce0c  call    wcscmp_0
0x18003ce11  test    eax, eax
0x18003ce13  jnz     loc_180081F68
0x18003ce19  mov     rax, [rsp+68h+arg_20]
0x18003ce21  mov     dword ptr [rax], 0Ch
0x18003ce27  test    rdi, rdi
0x18003ce2a  jz      loc_18003CCB7
0x18003ce30  cmp     esi, 0Ch
0x18003ce33  jb      loc_18003CD28
0x18003ce39  mov     dword ptr [rdi], 200h
0x18003ce3f  mov     dword ptr [rdi+4], 4000h
0x18003ce46  mov     dword ptr [rdi+8], 8
0x18003ce4d  jmp     loc_18003CCB7
0x180081f68  mov     r9d, 2C3h
0x180081f6e  mov     ebx, 0C00000BBh
0x180081f73  mov     ecx, 0C00000BBh
0x180081f78  lea     rdx, aStatus; "Status"
0x180081f7f  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180081f86  call    DebugTraceError
0x180081f8b  nop
0x180081f8c  jmp     loc_18003CCB9
0x180081f91  call    cs:__imp_wcscpy_s
0x180081f98  nop     dword ptr [rax+rax+00h]
0x180081f9d  nop
0x180081f9e  jmp     loc_18003CCB7
0x180081fa3  lea     rdx, aIsifxtpmweakke; "IsIfxTpmWeakKey"
0x180081faa  mov     rcx, rbx; String1
0x180081fad  call    wcscmp_0
0x180081fb2  test    eax, eax
0x180081fb4  jnz     short loc_180082003
0x180081fb6  mov     [rsp+68h+arg_28], eax
0x180081fbd  mov     rax, [rsp+68h+arg_20]
0x180081fc5  mov     dword ptr [rax], 4
0x180081fcb  test    rdi, rdi
0x180081fce  jz      loc_18003CCB7
0x180081fd4  cmp     esi, 4
0x180081fd7  jb      loc_18003CD28
0x180081fdd  lea     rdx, [rsp+68h+arg_28]
0x180081fe5  mov     rcx, r14
0x180081fe8  call    IsIfxTpmWeakKeyProperty
0x180081fed  mov     ebx, eax
0x180081fef  test    eax, eax
0x180081ff1  js      loc_18003CCB9
0x180081ff7  mov     eax, [rsp+68h+arg_28]
0x180081ffe  jmp     loc_18003CCB5
0x180082003  mov     r9d, 30Dh
0x180082009  jmp     loc_180081F6E
```
