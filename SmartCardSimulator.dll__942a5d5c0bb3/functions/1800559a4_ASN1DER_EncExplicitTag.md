# ASN1DER_EncExplicitTag

- ea: `0x1800559a4`
- end: `0x180055d4e`
- name: `ASN1DER_EncExplicitTag`
- size: `938`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180055d54`
- `0x180057c50`
- `0x180057e30`
- `0x1800581b0`

## callees

- `0x1800559a4`
- `0x180056a94`
- `0x18005e010`

## string_xrefs

- `0x180055b4e`: `onecore\ds\security\asn1\ntasn1\ntasn1der\derenc.c`
- `0x180055b62`: `onecore\ds\security\asn1\ntasn1\ntasn1der\derenc.c`
- `0x180055c8c`: `onecore\ds\security\asn1\ntasn1\ntasn1der\derenc.c`
- `0x180055d18`: `onecore\ds\security\asn1\ntasn1\ntasn1der\derenc.c`

## pseudocode

```c
__int64 __fastcall ASN1DER_EncExplicitTag(_QWORD *a1, __int64 a2, unsigned __int64 a3)
{
  unsigned __int64 v3; // rbp
  int v4; // r15d
  __int64 v6; // rsi
  int v7; // ebx
  __int64 v8; // rax
  unsigned int v9; // r15d
  _QWORD *v10; // rdi
  __int64 (__fastcall *v11)(_QWORD *, __int64); // rax
  __int64 v12; // r9
  unsigned __int64 v13; // r13
  _QWORD *v14; // rax
  __int64 v15; // rcx
  __int64 (__fastcall *v16)(_QWORD *, unsigned __int64); // rax
  __int64 v17; // rdx
  __int64 v18; // r9
  __int64 v19; // rcx
  unsigned __int64 v20; // r13
  unsigned int v21; // ebp
  __int64 v22; // rax
  char v23; // r15
  __int64 (__fastcall *v24)(_QWORD *, __int64); // rax
  _BYTE *v25; // rcx
  __int64 v26; // r9
  char i; // al
  __int64 (__fastcall *v28)(_QWORD *, __int64); // rax
  __int64 v29; // r9
  __int64 (__fastcall *v30)(_QWORD *, __int64); // rax
  __int64 (__fastcall *v31)(_QWORD *, __int64); // rax

  v3 = a3;
  v4 = a2;
  v6 = 2;
  if ( !*a1 )
  {
    v7 = 0;
    if ( a3 >= 0x80 )
    {
      if ( a3 >= 0x100 )
      {
        if ( a3 >= 0x10000 )
          v8 = 5LL - (a3 < 0x1000000);
        else
          v8 = 3;
      }
      else
      {
        v8 = 2;
      }
    }
    else
    {
      v8 = 1;
    }
    v9 = a2 & 0x1FFFFFFF;
    if ( ((unsigned int)a2 & 0x1FFFFFFF) <= 0x1E )
    {
      v6 = 1;
    }
    else if ( v9 >= 0x80 )
    {
      if ( v9 >= 0x4000 )
      {
        if ( v9 >= 0x200000 )
          v6 = 6LL - (v9 < 0x10000000);
        else
          v6 = 4;
      }
      else
      {
        v6 = 3;
      }
    }
    a1[2] -= v6 + v8;
    return (unsigned int)v7;
  }
  if ( a3 < 0x80 )
  {
    v7 = 0;
    v10 = a1 + 2;
    if ( a1[2] == *a1 )
    {
      v11 = (__int64 (__fastcall *)(_QWORD *, __int64))a1[5];
      if ( v11 )
        v7 = v11(a1, 1);
      else
        v7 = -2146893784;
    }
    --*v10;
    if ( v7 < 0 )
    {
      v12 = 318;
LABEL_42:
      v15 = (unsigned int)v7;
      goto LABEL_43;
    }
    *(_BYTE *)*v10 = v3;
    goto LABEL_47;
  }
  if ( a3 >= 0x100 )
  {
    if ( a3 >= 0x10000 )
    {
      if ( a3 >= 0x1000000 )
      {
        if ( a3 > 0xFFFFFFFF )
        {
          v7 = -2146881276;
          v12 = 294;
          v15 = 2148086020LL;
LABEL_43:
          DebugTraceError(v15, a2, "onecore\\ds\\security\\asn1\\ntasn1\\ntasn1der\\derenc.c", v12);
          v18 = 544;
          v19 = (unsigned int)v7;
LABEL_44:
          DebugTraceError(v19, v17, "onecore\\ds\\security\\asn1\\ntasn1\\ntasn1der\\derenc.c", v18);
          return (unsigned int)v7;
        }
        v14 = a1 + 2;
        v13 = 5;
        v10 = a1 + 2;
        goto LABEL_36;
      }
      v13 = 4;
    }
    else
    {
      v13 = 3;
    }
  }
  else
  {
    v13 = 2;
  }
  v10 = a1 + 2;
  v14 = a1 + 2;
LABEL_36:
  v7 = 0;
  if ( v13 > *v14 - *a1 )
  {
    v16 = (__int64 (__fastcall *)(_QWORD *, unsigned __int64))a1[5];
    if ( v16 )
      v7 = v16(a1, v13);
    else
      v7 = -2146893784;
  }
  *v10 -= v13;
  if ( v7 < 0 )
  {
    v12 = 333;
    goto LABEL_42;
  }
  v20 = v13 - 1;
  *(_BYTE *)*v10 = v20 | 0x80;
  do
  {
    *(_BYTE *)(*v10 + v20) = v3;
    v3 >>= 8;
    --v20;
  }
  while ( v20 );
LABEL_47:
  v21 = v4 & 0x1FFFFFFF;
  if ( *a1 )
  {
    v7 = 0;
    v22 = *v10 - *a1;
    v23 = HIBYTE(v4) & 0xE0;
    if ( v21 <= 0x1E )
    {
      if ( !v22 )
      {
        v31 = (__int64 (__fastcall *)(_QWORD *, __int64))a1[5];
        if ( v31 )
          v7 = v31(a1, 1);
        else
          v7 = -2146893784;
      }
      --*v10;
      if ( v7 >= 0 )
      {
        *(_BYTE *)*v10 = v23 | v21;
        return (unsigned int)v7;
      }
      v29 = 469;
    }
    else
    {
      if ( !v22 )
      {
        v24 = (__int64 (__fastcall *)(_QWORD *, __int64))a1[5];
        if ( v24 )
          v7 = v24(a1, 1);
        else
          v7 = -2146893784;
      }
      v25 = (_BYTE *)--*v10;
      if ( v7 >= 0 )
      {
        for ( i = v21 & 0x7F; ; i = v21 | 0x80 )
        {
          v21 >>= 7;
          v7 = 0;
          *v25 = i;
          if ( !v21 )
            break;
          if ( *a1 && *v10 == *a1 )
          {
            v28 = (__int64 (__fastcall *)(_QWORD *, __int64))a1[5];
            if ( v28 )
              v7 = v28(a1, 1);
            else
              v7 = -2146893784;
          }
          v25 = (_BYTE *)--*v10;
          if ( v7 < 0 )
          {
            v26 = 138;
            goto LABEL_74;
          }
        }
        if ( *a1 && *v10 == *a1 )
        {
          v30 = (__int64 (__fastcall *)(_QWORD *, __int64))a1[5];
          if ( v30 )
            v7 = v30(a1, 1);
          else
            v7 = -2146893784;
        }
        --*v10;
        if ( v7 >= 0 )
        {
          *(_BYTE *)*v10 = v23 | 0x1F;
          return (unsigned int)v7;
        }
        v29 = 454;
      }
      else
      {
        v26 = 121;
LABEL_74:
        DebugTraceError((unsigned int)v7, a2, "onecore\\ds\\security\\asn1\\ntasn1\\ntasn1der\\derenc.c", v26);
        v29 = 447;
      }
    }
    DebugTraceError((unsigned int)v7, a2, "onecore\\ds\\security\\asn1\\ntasn1\\ntasn1der\\derenc.c", v29);
    v18 = 554;
    v19 = (unsigned int)v7;
    goto LABEL_44;
  }
  if ( v21 <= 0x1E )
  {
    v6 = 1;
  }
  else if ( v21 >= 0x80 )
  {
    if ( v21 >= 0x4000 )
    {
      if ( v21 >= 0x200000 )
        v6 = 6LL - (v21 < 0x10000000);
      else
        v6 = 4;
    }
    else
    {
      v6 = 3;
    }
  }
  *v10 -= v6;
  return 0;
}

```

## disassembly

```asm
0x1800559a4  push    rbx
0x1800559a6  push    rbp
0x1800559a7  push    rsi
0x1800559a8  push    rdi
0x1800559a9  push    r12
0x1800559ab  push    r13
0x1800559ad  push    r14
0x1800559af  push    r15
0x1800559b1  sub     rsp, 28h
0x1800559b5  cmp     qword ptr [rcx], 0
0x1800559b9  mov     rbp, r8
0x1800559bc  mov     r15d, edx
0x1800559bf  mov     r14, rcx
0x1800559c2  mov     esi, 2
0x1800559c7  jnz     loc_180055A5C
0x1800559cd  xor     ebx, ebx
0x1800559cf  lea     edx, [rsi+7Eh]
0x1800559d2  lea     ecx, [rsi+1]
0x1800559d5  lea     r12d, [rsi-1]
0x1800559d9  cmp     r8, rdx
0x1800559dc  jnb     short loc_1800559E3
0x1800559de  mov     eax, r12d
0x1800559e1  jmp     short loc_180055A0D
0x1800559e3  cmp     rbp, 100h
0x1800559ea  jnb     short loc_1800559F1
0x1800559ec  mov     rax, rsi
0x1800559ef  jmp     short loc_180055A0D
0x1800559f1  cmp     rbp, 10000h
0x1800559f8  jnb     short loc_1800559FF
0x1800559fa  mov     rax, rcx
0x1800559fd  jmp     short loc_180055A0D
0x1800559ff  cmp     rbp, 1000000h
0x180055a06  sbb     rax, rax
0x180055a09  add     rax, 5
0x180055a0d  and     r15d, 1FFFFFFFh
0x180055a14  cmp     r15d, 1Eh
0x180055a18  jbe     short loc_180055A4D
0x180055a1a  cmp     r15d, edx
0x180055a1d  jb      short loc_180055A50
0x180055a1f  cmp     r15d, 4000h
0x180055a26  jnb     short loc_180055A2D
0x180055a28  mov     rsi, rcx
0x180055a2b  jmp     short loc_180055A50
0x180055a2d  cmp     r15d, 200000h
0x180055a34  jnb     short loc_180055A3D
0x180055a36  mov     esi, 4
0x180055a3b  jmp     short loc_180055A50
0x180055a3d  cmp     r15d, 10000000h
0x180055a44  sbb     rsi, rsi
0x180055a47  add     rsi, 6
0x180055a4b  jmp     short loc_180055A50
0x180055a4d  mov     rsi, r12
0x180055a50  add     rax, rsi
0x180055a53  sub     [r14+10h], rax
0x180055a57  jmp     loc_180055D3B
0x180055a5c  cmp     rbp, 80h
0x180055a63  jnb     short loc_180055AB5
0x180055a65  xor     ebx, ebx
0x180055a67  lea     rdi, [rcx+10h]
0x180055a6b  mov     rax, [rdi]
0x180055a6e  mov     r13d, 80090028h
0x180055a74  sub     rax, [rcx]
0x180055a77  lea     r12d, [rbx+1]
0x180055a7b  cmp     rax, r12
0x180055a7e  jnb     short loc_180055A98
0x180055a80  mov     rax, [rcx+28h]
0x180055a84  test    rax, rax
0x180055a87  jz      short loc_180055A95
0x180055a89  mov     edx, r12d
0x180055a8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055a91  mov     ebx, eax
0x180055a93  jmp     short loc_180055A98
0x180055a95  mov     ebx, r13d
0x180055a98  dec     qword ptr [rdi]
0x180055a9b  mov     rax, [rdi]
0x180055a9e  test    ebx, ebx
0x180055aa0  jns     short loc_180055AAD
0x180055aa2  mov     r9d, 13Eh
0x180055aa8  jmp     loc_180055B4C
0x180055aad  mov     [rax], bpl
0x180055ab0  jmp     loc_180055B99
0x180055ab5  cmp     rbp, 100h
0x180055abc  jnb     short loc_180055ACA
0x180055abe  mov     r13, rsi
0x180055ac1  lea     rdi, [rcx+10h]
0x180055ac5  mov     rax, rdi
0x180055ac8  jmp     short loc_180055B15
0x180055aca  cmp     rbp, 10000h
0x180055ad1  jnb     short loc_180055ADB
0x180055ad3  mov     r13d, 3
0x180055ad9  jmp     short loc_180055AC1
0x180055adb  cmp     rbp, 1000000h
0x180055ae2  jnb     short loc_180055AEC
0x180055ae4  mov     r13d, 4
0x180055aea  jmp     short loc_180055AC1
0x180055aec  mov     eax, 0FFFFFFFFh
0x180055af1  cmp     rbp, rax
0x180055af4  jbe     short loc_180055B08
0x180055af6  mov     ebx, 80093104h
0x180055afb  mov     r9d, 126h
0x180055b01  mov     ecx, 80093104h
0x180055b06  jmp     short loc_180055B4E
0x180055b08  lea     rax, [rcx+10h]
0x180055b0c  mov     r13d, 5
0x180055b12  mov     rdi, rax
0x180055b15  mov     rax, [rax]
0x180055b18  xor     ebx, ebx
0x180055b1a  sub     rax, [rcx]
0x180055b1d  cmp     r13, rax
0x180055b20  jbe     short loc_180055B3C
0x180055b22  mov     rax, [rcx+28h]
0x180055b26  test    rax, rax
0x180055b29  jz      short loc_180055B37
0x180055b2b  mov     rdx, r13
0x180055b2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055b33  mov     ebx, eax
0x180055b35  jmp     short loc_180055B3C
0x180055b37  mov     ebx, 80090028h
0x180055b3c  sub     [rdi], r13
0x180055b3f  mov     rcx, [rdi]
0x180055b42  test    ebx, ebx
0x180055b44  jns     short loc_180055B73
0x180055b46  mov     r9d, 14Dh
0x180055b4c  mov     ecx, ebx
0x180055b4e  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\asn1\\ntasn1\\nt"...
0x180055b55  call    DebugTraceError
0x180055b5a  mov     r9d, 220h
0x180055b60  mov     ecx, ebx
0x180055b62  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\asn1\\ntasn1\\nt"...
0x180055b69  call    DebugTraceError
0x180055b6e  jmp     loc_180055D3B
0x180055b73  dec     r13
0x180055b76  mov     r12d, 1
0x180055b7c  mov     al, r13b
0x180055b7f  or      al, 80h
0x180055b81  mov     [rcx], al
0x180055b83  mov     rax, [rdi]
0x180055b86  mov     [rax+r13], bpl
0x180055b8a  shr     rbp, 8
0x180055b8e  sub     r13, r12
0x180055b91  jnz     short loc_180055B83
0x180055b93  mov     r13d, 80090028h
0x180055b99  mov     ebp, r15d
0x180055b9c  and     ebp, 1FFFFFFFh
0x180055ba2  cmp     qword ptr [r14], 0
0x180055ba6  jnz     short loc_180055BEF
0x180055ba8  cmp     ebp, 1Eh
0x180055bab  jbe     short loc_180055BE2
0x180055bad  cmp     ebp, 80h
0x180055bb3  jb      short loc_180055BE5
0x180055bb5  cmp     ebp, 4000h
0x180055bbb  jnb     short loc_180055BC4
0x180055bbd  mov     esi, 3
0x180055bc2  jmp     short loc_180055BE5
0x180055bc4  cmp     ebp, 200000h
0x180055bca  jnb     short loc_180055BD3
0x180055bcc  mov     esi, 4
0x180055bd1  jmp     short loc_180055BE5
0x180055bd3  cmp     ebp, 10000000h
0x180055bd9  sbb     rsi, rsi
0x180055bdc  add     rsi, 6
0x180055be0  jmp     short loc_180055BE5
0x180055be2  mov     rsi, r12
0x180055be5  sub     [rdi], rsi
0x180055be8  xor     ebx, ebx
0x180055bea  jmp     loc_180055D3B
0x180055bef  mov     rax, [rdi]
0x180055bf2  xor     ebx, ebx
0x180055bf4  sub     rax, [r14]
0x180055bf7  shr     r15d, 18h
0x180055bfb  and     r15b, 0E0h
0x180055bff  cmp     ebp, 1Eh
0x180055c02  jbe     loc_180055CE8
0x180055c08  cmp     rax, r12
0x180055c0b  jnb     short loc_180055C28
0x180055c0d  mov     rax, [r14+28h]
0x180055c11  test    rax, rax
0x180055c14  jz      short loc_180055C25
0x180055c16  mov     rdx, r12
0x180055c19  mov     rcx, r14
0x180055c1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055c21  mov     ebx, eax
0x180055c23  jmp     short loc_180055C28
0x180055c25  mov     ebx, r13d
0x180055c28  dec     qword ptr [rdi]
0x180055c2b  mov     rcx, [rdi]
0x180055c2e  test    ebx, ebx
0x180055c30  jns     short loc_180055C3A
0x180055c32  mov     r9d, 79h ; 'y'
0x180055c38  jmp     short loc_180055C8C
0x180055c3a  mov     al, bpl
0x180055c3d  and     al, 7Fh
0x180055c3f  shr     ebp, 7
0x180055c42  xor     ebx, ebx
0x180055c44  mov     [rcx], al
0x180055c46  test    ebp, ebp
0x180055c48  jz      short loc_180055CA2
0x180055c4a  cmp     [r14], rbx
0x180055c4d  jz      short loc_180055C75
0x180055c4f  mov     rax, [rdi]
0x180055c52  sub     rax, [r14]
0x180055c55  cmp     rax, r12
0x180055c58  jnb     short loc_180055C75
0x180055c5a  mov     rax, [r14+28h]
0x180055c5e  test    rax, rax
0x180055c61  jz      short loc_180055C72
0x180055c63  mov     rdx, r12
0x180055c66  mov     rcx, r14
0x180055c69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055c6e  mov     ebx, eax
0x180055c70  jmp     short loc_180055C75
0x180055c72  mov     ebx, r13d
0x180055c75  dec     qword ptr [rdi]
0x180055c78  mov     rcx, [rdi]
0x180055c7b  test    ebx, ebx
0x180055c7d  js      short loc_180055C86
0x180055c7f  mov     al, bpl
0x180055c82  or      al, 80h
0x180055c84  jmp     short loc_180055C3F
0x180055c86  mov     r9d, 8Ah
0x180055c8c  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\asn1\\ntasn1\\nt"...
0x180055c93  mov     ecx, ebx
0x180055c95  call    DebugTraceError
0x180055c9a  mov     r9d, 1BFh
0x180055ca0  jmp     short loc_180055D18
0x180055ca2  cmp     [r14], rbx
0x180055ca5  jz      short loc_180055CCD
0x180055ca7  mov     rax, [rdi]
0x180055caa  sub     rax, [r14]
0x180055cad  cmp     rax, r12
0x180055cb0  jnb     short loc_180055CCD
0x180055cb2  mov     rax, [r14+28h]
0x180055cb6  test    rax, rax
0x180055cb9  jz      short loc_180055CCA
0x180055cbb  mov     rdx, r12
0x180055cbe  mov     rcx, r14
0x180055cc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055cc6  mov     ebx, eax
0x180055cc8  jmp     short loc_180055CCD
0x180055cca  mov     ebx, r13d
0x180055ccd  dec     qword ptr [rdi]
0x180055cd0  mov     rax, [rdi]
0x180055cd3  test    ebx, ebx
0x180055cd5  jns     short loc_180055CDF
0x180055cd7  mov     r9d, 1C6h
0x180055cdd  jmp     short loc_180055D18
0x180055cdf  or      r15b, 1Fh
0x180055ce3  mov     [rax], r15b
0x180055ce6  jmp     short loc_180055D3B
0x180055ce8  cmp     rax, r12
0x180055ceb  jnb     short loc_180055D08
0x180055ced  mov     rax, [r14+28h]
0x180055cf1  test    rax, rax
0x180055cf4  jz      short loc_180055D05
0x180055cf6  mov     rdx, r12
0x180055cf9  mov     rcx, r14
0x180055cfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055d01  mov     ebx, eax
0x180055d03  jmp     short loc_180055D08
0x180055d05  mov     ebx, r13d
0x180055d08  dec     qword ptr [rdi]
0x180055d0b  mov     rax, [rdi]
0x180055d0e  test    ebx, ebx
0x180055d10  jns     short loc_180055D35
0x180055d12  mov     r9d, 1D5h
0x180055d18  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\asn1\\ntasn1\\nt"...
0x180055d1f  mov     ecx, ebx
0x180055d21  mov     edi, ebx
0x180055d23  call    DebugTraceError
0x180055d28  mov     r9d, 22Ah
0x180055d2e  mov     ecx, ebx
0x180055d30  jmp     loc_180055B62
0x180055d35  or      bpl, r15b
0x180055d38  mov     [rax], bpl
0x180055d3b  mov     eax, ebx
0x180055d3d  add     rsp, 28h
0x180055d41  pop     r15
0x180055d43  pop     r14
0x180055d45  pop     r13
0x180055d47  pop     r12
0x180055d49  pop     rdi
0x180055d4a  pop     rsi
0x180055d4b  pop     rbp
0x180055d4c  pop     rbx
0x180055d4d  retn
```
