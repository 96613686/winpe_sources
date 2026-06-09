# ASN1DER_DecTagLength

- ea: `0x18005686c`
- end: `0x180056a8d`
- name: `ASN1DER_DecTagLength`
- size: `545`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800195a0`
- `0x18004fdc4`
- `0x180056748`

## callees

- `0x18005686c`
- `0x180056a94`

## string_xrefs

- `0x1800568ca`: `onecore\ds\security\asn1\ntasn1\ntasn1der\derdec.c`
- `0x1800568f6`: `onecore\ds\security\asn1\ntasn1\ntasn1der\derdec.c`
- `0x18005694b`: `onecore\ds\security\asn1\ntasn1\ntasn1der\derdec.c`
- `0x180056969`: `onecore\ds\security\asn1\ntasn1\ntasn1der\derdec.c`
- `0x18005697d`: `onecore\ds\security\asn1\ntasn1\ntasn1der\derdec.c`
- `0x180056a63`: `onecore\ds\security\asn1\ntasn1\ntasn1der\derdec.c`

## pseudocode

```c
__int64 __fastcall ASN1DER_DecTagLength(__int64 a1, int *a2, __int64 *a3)
{
  char *v3; // rax
  unsigned int v7; // ebx
  __int64 v8; // r9
  __int64 v9; // rcx
  char v10; // al
  __int64 v11; // rdx
  char *v12; // r8
  int v13; // ebx
  __int64 v14; // r9
  char v15; // al
  char *v16; // r8
  __int64 v17; // rdx
  __int64 v18; // r9
  __int64 v19; // rcx
  unsigned __int8 *v20; // rax
  __int64 v21; // r9
  __int64 v22; // rcx
  __int64 v23; // rcx
  unsigned int v24; // r8d
  unsigned __int8 *v25; // rax
  __int64 v26; // rcx

  v3 = *(char **)(a1 + 16);
  if ( (unsigned __int64)v3 < *(_QWORD *)(a1 + 24) )
  {
    v10 = *v3;
    *a2 = v10 & 0x1F;
    ++*(_QWORD *)(a1 + 16);
    v11 = (unsigned int)*a2;
    v12 = *(char **)(a1 + 16);
    v13 = v10 & 0xE0;
    if ( (_DWORD)v11 == 31 )
    {
      if ( (unsigned __int64)v12 >= *(_QWORD *)(a1 + 24) )
      {
        v14 = 100;
LABEL_6:
        DebugTraceError(2148086018LL, v11, "onecore\\ds\\security\\asn1\\ntasn1\\ntasn1der\\derdec.c", v14);
        v7 = -2146881278;
        goto LABEL_16;
      }
      v15 = *v12;
      v16 = v12 + 1;
      *(_QWORD *)(a1 + 16) = v16;
      if ( v15 == (char)0x80 )
      {
        DebugTraceError(2148086029LL, v11, "onecore\\ds\\security\\asn1\\ntasn1\\ntasn1der\\derdec.c", 114);
        v7 = -2146881267;
LABEL_16:
        v8 = 455;
        v9 = v7;
        goto LABEL_17;
      }
      v11 = 0;
      while ( v15 < 0 )
      {
        if ( (v11 & 0xFE000000) != 0 )
        {
          DebugTraceError(2148086020LL, v11, "onecore\\ds\\security\\asn1\\ntasn1\\ntasn1der\\derdec.c", 127);
          v7 = -2146881276;
          goto LABEL_16;
        }
        if ( (unsigned __int64)v16 >= *(_QWORD *)(a1 + 24) )
        {
          v14 = 142;
          goto LABEL_6;
        }
        v11 = ((_DWORD)v11 << 7) | v15 & 0x7Fu;
        v15 = *v16++;
        *(_QWORD *)(a1 + 16) = v16;
      }
      v11 = (unsigned int)(unsigned __int8)v15 | ((_DWORD)v11 << 7);
    }
    *a2 = v11 | (v13 << 24);
    *a3 = 0;
    v20 = *(unsigned __int8 **)(a1 + 16);
    if ( (unsigned __int64)v20 >= *(_QWORD *)(a1 + 24) )
    {
      v7 = -2146881278;
      v21 = 281;
      v22 = 2148086018LL;
LABEL_35:
      DebugTraceError(v22, v11, "onecore\\ds\\security\\asn1\\ntasn1\\ntasn1der\\derdec.c", v21);
      v18 = 553;
      v19 = v7;
      goto LABEL_18;
    }
    v23 = *v20;
    *(_QWORD *)(a1 + 16) = v20 + 1;
    if ( (v23 & 0x80u) != 0LL )
    {
      if ( (_BYTE)v23 == 0x80 )
      {
        v7 = -2146881267;
        v21 = 315;
        v22 = 2148086029LL;
        goto LABEL_35;
      }
      v24 = v23 & 0x7F;
      if ( v24 > 4 )
      {
        v21 = 348;
LABEL_34:
        v22 = 2148086020LL;
        v7 = -2146881276;
        goto LABEL_35;
      }
      if ( v24 > *(_DWORD *)(a1 + 24) - *(_DWORD *)(a1 + 16) )
      {
        v7 = -2146881277;
        v21 = 358;
        v22 = 2148086019LL;
        goto LABEL_35;
      }
      if ( (v23 & 0x7F) != 0 )
      {
        do
        {
          v25 = *(unsigned __int8 **)(a1 + 16);
          v26 = *v25;
          *(_QWORD *)(a1 + 16) = v25 + 1;
          v11 = v26 | (*a3 << 8);
          *a3 = v11;
          --v24;
        }
        while ( v24 );
      }
    }
    else
    {
      *a3 = v23;
    }
    if ( (unsigned __int64)*a3 <= 0x7FFFFFF0 )
      return 0;
    v21 = 374;
    goto LABEL_34;
  }
  v7 = -2146881278;
  v8 = 436;
  v9 = 2148086018LL;
LABEL_17:
  DebugTraceError(v9, a2, "onecore\\ds\\security\\asn1\\ntasn1\\ntasn1der\\derdec.c", v8);
  v18 = 538;
  v19 = v7;
LABEL_18:
  DebugTraceError(v19, v17, "onecore\\ds\\security\\asn1\\ntasn1\\ntasn1der\\derdec.c", v18);
  return v7;
}

```

## disassembly

```asm
0x18005686c  mov     [rsp+arg_0], rbx
0x180056871  push    rdi
0x180056872  sub     rsp, 20h
0x180056876  mov     rax, [rcx+10h]
0x18005687a  mov     r10, r8
0x18005687d  mov     r11, rdx
0x180056880  mov     r9, rcx
0x180056883  cmp     rax, [rcx+18h]
0x180056887  jb      short loc_18005689E
0x180056889  mov     ebx, 80093102h
0x18005688e  mov     r9d, 1B4h
0x180056894  mov     ecx, 80093102h
0x180056899  jmp     loc_180056969
0x18005689e  movzx   ecx, byte ptr [rax]
0x1800568a1  mov     al, cl
0x1800568a3  and     ecx, 1Fh
0x1800568a6  mov     [rdx], ecx
0x1800568a8  and     al, 0E0h
0x1800568aa  inc     qword ptr [r9+10h]
0x1800568ae  mov     edx, [rdx]
0x1800568b0  mov     r8, [r9+10h]
0x1800568b4  movzx   ebx, al
0x1800568b7  cmp     edx, 1Fh
0x1800568ba  jnz     loc_180056996
0x1800568c0  cmp     r8, [r9+18h]
0x1800568c4  jb      short loc_1800568E2
0x1800568c6  lea     r9d, [rdx+45h]
0x1800568ca  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\asn1\\ntasn1\\nt"...
0x1800568d1  mov     ecx, 80093102h
0x1800568d6  call    DebugTraceError
0x1800568db  mov     ebx, 80093102h
0x1800568e0  jmp     short loc_180056961
0x1800568e2  mov     al, [r8]
0x1800568e5  inc     r8
0x1800568e8  mov     [r9+10h], r8
0x1800568ec  cmp     al, 80h
0x1800568ee  jnz     short loc_18005690E
0x1800568f0  mov     r9d, 72h ; 'r'
0x1800568f6  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\asn1\\ntasn1\\nt"...
0x1800568fd  mov     ecx, 8009310Dh
0x180056902  call    DebugTraceError
0x180056907  mov     ebx, 8009310Dh
0x18005690c  jmp     short loc_180056961
0x18005690e  xor     edx, edx
0x180056910  test    al, al
0x180056912  jns     short loc_18005698E
0x180056914  test    edx, 0FE000000h
0x18005691a  jnz     short loc_180056945
0x18005691c  cmp     r8, [r9+18h]
0x180056920  jnb     short loc_18005693D
0x180056922  movzx   ecx, al
0x180056925  mov     eax, edx
0x180056927  shl     eax, 7
0x18005692a  and     ecx, 7Fh
0x18005692d  mov     edx, ecx
0x18005692f  or      edx, eax
0x180056931  mov     al, [r8]
0x180056934  inc     r8
0x180056937  mov     [r9+10h], r8
0x18005693b  jmp     short loc_180056910
0x18005693d  mov     r9d, 8Eh
0x180056943  jmp     short loc_1800568CA
0x180056945  mov     r9d, 7Fh
0x18005694b  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\asn1\\ntasn1\\nt"...
0x180056952  mov     ecx, 80093104h
0x180056957  call    DebugTraceError
0x18005695c  mov     ebx, 80093104h
0x180056961  mov     r9d, 1C7h
0x180056967  mov     ecx, ebx
0x180056969  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\asn1\\ntasn1\\nt"...
0x180056970  call    DebugTraceError
0x180056975  mov     r9d, 21Ah
0x18005697b  mov     ecx, ebx
0x18005697d  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\asn1\\ntasn1\\nt"...
0x180056984  call    DebugTraceError
0x180056989  jmp     loc_180056A80
0x18005698e  shl     edx, 7
0x180056991  movzx   eax, al
0x180056994  or      edx, eax
0x180056996  mov     eax, ebx
0x180056998  shl     eax, 18h
0x18005699b  or      eax, edx
0x18005699d  mov     [r11], eax
0x1800569a0  mov     qword ptr [r10], 0
0x1800569a7  mov     rax, [r9+10h]
0x1800569ab  cmp     rax, [r9+18h]
0x1800569af  jb      short loc_1800569C6
0x1800569b1  mov     ebx, 80093102h
0x1800569b6  mov     r9d, 119h
0x1800569bc  mov     ecx, 80093102h
0x1800569c1  jmp     loc_180056A63
0x1800569c6  movzx   ecx, byte ptr [rax]
0x1800569c9  inc     rax
0x1800569cc  mov     [r9+10h], rax
0x1800569d0  test    cl, cl
0x1800569d2  js      short loc_1800569D9
0x1800569d4  mov     [r10], rcx
0x1800569d7  jmp     short loc_180056A4A
0x1800569d9  cmp     cl, 80h
0x1800569dc  jnz     short loc_1800569F0
0x1800569de  mov     ebx, 8009310Dh
0x1800569e3  mov     r9d, 13Bh
0x1800569e9  mov     ecx, 8009310Dh
0x1800569ee  jmp     short loc_180056A63
0x1800569f0  mov     r8d, ecx
0x1800569f3  and     r8d, 7Fh
0x1800569f7  cmp     r8d, 4
0x1800569fb  jbe     short loc_180056A05
0x1800569fd  mov     r9d, 15Ch
0x180056a03  jmp     short loc_180056A59
0x180056a05  mov     eax, [r9+18h]
0x180056a09  sub     eax, [r9+10h]
0x180056a0d  cmp     r8d, eax
0x180056a10  jbe     short loc_180056A24
0x180056a12  mov     ebx, 80093103h
0x180056a17  mov     r9d, 166h
0x180056a1d  mov     ecx, 80093103h
0x180056a22  jmp     short loc_180056A63
0x180056a24  test    r8d, r8d
0x180056a27  jz      short loc_180056A4A
0x180056a29  mov     rax, [r9+10h]
0x180056a2d  movzx   ecx, byte ptr [rax]
0x180056a30  inc     rax
0x180056a33  mov     [r9+10h], rax
0x180056a37  mov     rdx, [r10]
0x180056a3a  shl     rdx, 8
0x180056a3e  or      rdx, rcx
0x180056a41  mov     [r10], rdx
0x180056a44  add     r8d, 0FFFFFFFFh
0x180056a48  jnz     short loc_180056A29
0x180056a4a  cmp     qword ptr [r10], 7FFFFFF0h
0x180056a51  jbe     short loc_180056A7E
0x180056a53  mov     r9d, 176h
0x180056a59  mov     ecx, 80093104h
0x180056a5e  mov     ebx, 80093104h
0x180056a63  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\asn1\\ntasn1\\nt"...
0x180056a6a  mov     edi, ebx
0x180056a6c  call    DebugTraceError
0x180056a71  mov     r9d, 229h
0x180056a77  mov     ecx, ebx
0x180056a79  jmp     loc_18005697D
0x180056a7e  xor     ebx, ebx
0x180056a80  mov     eax, ebx
0x180056a82  mov     rbx, [rsp+28h+arg_0]
0x180056a87  add     rsp, 20h
0x180056a8b  pop     rdi
0x180056a8c  retn
```
