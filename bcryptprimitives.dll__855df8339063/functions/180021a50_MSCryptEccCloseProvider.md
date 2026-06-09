# MSCryptEccCloseProvider

- ea: `0x180021a50`
- end: `0x180021c47`
- name: `MSCryptEccCloseProvider`
- size: `503`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180010cc0`
- `0x1800213c0`
- `0x180051a30`

## callees

- `0x18000ecb0`
- `0x18000ee60`
- `0x180021a50`
- `0x1800225a0`
- `0x180023ce0`

## string_xrefs

- `0x180021a6d`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x180021bdd`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`

## pseudocode

```c
__int64 __fastcall MSCryptEccCloseProvider(unsigned int *a1, __int64 a2, int a3)
{
  wchar_t **v5; // r8
  __int64 i; // rcx
  void *v7; // rcx
  unsigned int v8; // edi
  int v9; // r8d
  __int64 v10; // rax
  _BYTE *v11; // rcx

  if ( (_DWORD)a2 )
  {
    v8 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        a3,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
        132);
    return v8;
  }
  if ( !a1 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        0,
        a3,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
        231);
    goto LABEL_21;
  }
  if ( a1[1] != 1297301836 || *a1 != 24 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        0,
        a3,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
        241);
    goto LABEL_21;
  }
  v5 = &off_180084710;
  if ( !a3 )
    v5 = &off_1800847D0;
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= 4 )
      goto LABEL_22;
    a2 = 6 * i;
    if ( a1[2] == LODWORD(v5[6 * i + 1]) )
      break;
  }
  if ( !v5[6 * i] )
  {
LABEL_22:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        (_DWORD)v5,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
        249);
LABEL_21:
    v8 = -1073741811;
    DebugTraceError(3221225485LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", 2699);
    return v8;
  }
  v7 = (void *)*((_QWORD *)a1 + 2);
  if ( !v7 )
  {
LABEL_15:
    v10 = *a1;
    v11 = a1;
    if ( *a1 )
    {
      do
      {
        *v11++ = 0;
        --v10;
      }
      while ( v10 );
    }
    BCryptFree(a1, a2);
    return 0;
  }
  v8 = FreeGenericEccKeyParameters(v7);
  if ( (v8 & 0x80000000) == 0 )
  {
    *((_QWORD *)a1 + 2) = 0;
    goto LABEL_15;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      a2,
      v9,
      (unsigned int)"Status",
      v8,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
      148);
  return v8;
}

```

## disassembly

```asm
0x180021a50  mov     [rsp+arg_0], rbx
0x180021a55  mov     [rsp+arg_8], rbp
0x180021a5a  push    rdi
0x180021a5b  sub     rsp, 40h
0x180021a5f  mov     eax, r8d
0x180021a62  mov     rbx, rcx
0x180021a65  test    edx, edx
0x180021a67  jnz     loc_180021BAF
0x180021a6d  lea     rbp, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180021a74  test    rcx, rcx
0x180021a77  jz      loc_180021B25
0x180021a7d  cmp     dword ptr [rcx+4], 4D53414Ch
0x180021a84  jnz     loc_180021B89
0x180021a8a  cmp     dword ptr [rcx], 18h
0x180021a8d  jnz     loc_180021B89
0x180021a93  test    eax, eax
0x180021a95  lea     rcx, off_1800847D0; "ECDH_P256"
0x180021a9c  lea     r8, off_180084710; "ECDSA_P256"
0x180021aa3  cmovz   r8, rcx
0x180021aa7  xor     ecx, ecx
0x180021aa9  cmp     ecx, 4
0x180021aac  jnb     loc_180021B63
0x180021ab2  lea     rdx, [rcx+rcx*2]
0x180021ab6  add     rdx, rdx
0x180021ab9  mov     eax, [r8+rdx*8+8]
0x180021abe  cmp     [rbx+8], eax
0x180021ac1  jz      short loc_180021AC7
0x180021ac3  inc     ecx
0x180021ac5  jmp     short loc_180021AA9
0x180021ac7  cmp     qword ptr [r8+rdx*8], 0
0x180021acc  jz      loc_180021B63
0x180021ad2  mov     rcx, [rbx+10h]; P
0x180021ad6  test    rcx, rcx
0x180021ad9  jz      short loc_180021AF2
0x180021adb  call    FreeGenericEccKeyParameters
0x180021ae0  mov     edi, eax
0x180021ae2  test    eax, eax
0x180021ae4  js      loc_180021C06
0x180021aea  mov     qword ptr [rbx+10h], 0
0x180021af2  mov     eax, [rbx]
0x180021af4  mov     rcx, rbx
0x180021af7  test    rax, rax
0x180021afa  jz      short loc_180021B08
0x180021afc  mov     byte ptr [rcx], 0
0x180021aff  inc     rcx
0x180021b02  sub     rax, 1
0x180021b06  jnz     short loc_180021AFC
0x180021b08  mov     rcx, rbx
0x180021b0b  call    BCryptFree
0x180021b10  xor     edi, edi
0x180021b12  mov     rbx, [rsp+48h+arg_0]
0x180021b17  mov     eax, edi
0x180021b19  mov     rbp, [rsp+48h+arg_8]
0x180021b1e  add     rsp, 40h
0x180021b22  pop     rdi
0x180021b23  retn
0x180021b25  mov     rcx, cs:WPP_GLOBAL_Control
0x180021b2c  lea     rax, WPP_GLOBAL_Control
0x180021b33  cmp     rcx, rax
0x180021b36  jz      short loc_180021B42
0x180021b38  test    byte ptr [rcx+1Ch], 1
0x180021b3c  jnz     loc_180021C3A
0x180021b42  mov     r9d, 0A8Bh
0x180021b48  lea     rdx, aStatus; "Status"
0x180021b4f  mov     r8, rbp
0x180021b52  mov     ecx, 0C000000Dh
0x180021b57  mov     edi, 0C000000Dh
0x180021b5c  call    DebugTraceError
0x180021b61  jmp     short loc_180021B12
0x180021b63  mov     rcx, cs:WPP_GLOBAL_Control
0x180021b6a  lea     rax, WPP_GLOBAL_Control
0x180021b71  cmp     rcx, rax
0x180021b74  jz      short loc_180021B42
0x180021b76  test    byte ptr [rcx+1Ch], 1
0x180021b7a  jz      short loc_180021B42
0x180021b7c  mov     [rsp+48h+var_18], 1F9h
0x180021b84  jmp     loc_180081556
0x180021b89  mov     rcx, cs:WPP_GLOBAL_Control
0x180021b90  lea     rax, WPP_GLOBAL_Control
0x180021b97  cmp     rcx, rax
0x180021b9a  jz      short loc_180021B42
0x180021b9c  test    byte ptr [rcx+1Ch], 1
0x180021ba0  jz      short loc_180021B42
0x180021ba2  mov     [rsp+48h+var_18], 1F1h
0x180021baa  jmp     loc_180081556
0x180021baf  mov     edi, 0C000000Dh
0x180021bb4  mov     rcx, cs:WPP_GLOBAL_Control
0x180021bbb  lea     rax, WPP_GLOBAL_Control
0x180021bc2  cmp     rcx, rax
0x180021bc5  jz      loc_180021B12
0x180021bcb  test    byte ptr [rcx+1Ch], 1
0x180021bcf  jz      loc_180021B12
0x180021bd5  mov     [rsp+48h+var_18], 0A84h
0x180021bdd  lea     rbp, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180021be4  mov     [rsp+48h+var_20], rbp
0x180021be9  mov     [rsp+48h+var_28], 0C000000Dh
0x180021bf1  mov     rcx, [rcx+10h]
0x180021bf5  lea     r9, aStatus; "Status"
0x180021bfc  call    WPP_SF_sDsd
0x180021c01  jmp     loc_180021B12
0x180021c06  mov     rcx, cs:WPP_GLOBAL_Control
0x180021c0d  lea     rax, WPP_GLOBAL_Control
0x180021c14  cmp     rcx, rax
0x180021c17  jz      loc_180021B12
0x180021c1d  test    byte ptr [rcx+1Ch], 1
0x180021c21  jz      loc_180021B12
0x180021c27  mov     [rsp+48h+var_18], 0A94h
0x180021c2f  mov     [rsp+48h+var_20], rbp
0x180021c34  mov     [rsp+48h+var_28], edi
0x180021c38  jmp     short loc_180021BF1
0x180021c3a  mov     [rsp+48h+var_18], 1E7h
0x180021c42  jmp     loc_180081556
0x180081556  mov     rcx, [rcx+10h]
0x18008155a  lea     r9, aStatus; "Status"
0x180081561  mov     [rsp+48h+var_20], rbp
0x180081566  mov     [rsp+48h+var_28], 0C000000Dh
0x18008156e  call    WPP_SF_sDsd
0x180081573  nop
0x180081574  jmp     loc_180021B42
```
