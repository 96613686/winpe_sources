# ASN1BER_DecExplicitTag

- ea: `0x180055ea8`
- end: `0x180056155`
- name: `ASN1BER_DecExplicitTag`
- size: `685`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800574b0`

## callees

- `0x180055ea8`
- `0x180056a94`

## string_xrefs

- `0x180055f1c`: `onecore\ds\security\asn1\ntasn1\ntasn1der\derdec.c`
- `0x180055f48`: `onecore\ds\security\asn1\ntasn1\ntasn1der\derdec.c`
- `0x180055f9d`: `onecore\ds\security\asn1\ntasn1\ntasn1der\derdec.c`
- `0x180055fbb`: `onecore\ds\security\asn1\ntasn1\ntasn1der\derdec.c`
- `0x1800560ab`: `onecore\ds\security\asn1\ntasn1\ntasn1der\derdec.c`
- `0x180056131`: `onecore\ds\security\asn1\ntasn1\ntasn1der\derdec.c`

## pseudocode

```c
__int64 __fastcall ASN1BER_DecExplicitTag(__int64 a1, __int64 a2, int a3, unsigned __int64 *a4, _DWORD *a5)
{
  __int64 v6; // rbp
  int v7; // esi
  _BYTE *v9; // rcx
  unsigned int v10; // ebx
  __int64 v11; // r9
  __int64 v12; // rcx
  unsigned __int64 v13; // rdx
  int v14; // ebx
  char *v15; // rax
  __int64 v16; // r9
  char v17; // al
  char *v18; // r8
  __int64 v19; // r9
  __int64 v20; // rcx
  unsigned __int64 v21; // rax
  __int64 v22; // r9
  __int64 v23; // rcx
  unsigned __int8 *v24; // rax
  unsigned int v25; // ecx
  unsigned __int8 *v26; // r11
  unsigned int v27; // r8d
  __int64 v28; // rax

  v6 = *(_QWORD *)(a1 + 16);
  v7 = a2;
  *a4 = 0;
  if ( a5 )
    *a5 = 0;
  v9 = *(_BYTE **)(a1 + 16);
  if ( (unsigned __int64)v9 >= *(_QWORD *)(a1 + 24) )
  {
    v10 = -2146881278;
    v11 = 436;
    v12 = 2148086018LL;
LABEL_19:
    DebugTraceError(v12, a2, "onecore\\ds\\security\\asn1\\ntasn1\\ntasn1der\\derdec.c", v11);
    v19 = 850;
LABEL_20:
    v20 = v10;
LABEL_40:
    DebugTraceError(v20, v13, "onecore\\ds\\security\\asn1\\ntasn1\\ntasn1der\\derdec.c", v19);
    goto LABEL_41;
  }
  v13 = *v9 & 0x1F;
  v14 = *v9 & 0xE0;
  v15 = v9 + 1;
  *(_QWORD *)(a1 + 16) = v9 + 1;
  if ( (_DWORD)v13 == 31 )
  {
    if ( (unsigned __int64)v15 >= *(_QWORD *)(a1 + 24) )
    {
      v16 = 100;
LABEL_8:
      DebugTraceError(2148086018LL, v13, "onecore\\ds\\security\\asn1\\ntasn1\\ntasn1der\\derdec.c", v16);
      v10 = -2146881278;
      goto LABEL_18;
    }
    v17 = *v15;
    v18 = v9 + 2;
    *(_QWORD *)(a1 + 16) = v9 + 2;
    if ( v17 == (char)0x80 )
    {
      DebugTraceError(2148086029LL, v13, "onecore\\ds\\security\\asn1\\ntasn1\\ntasn1der\\derdec.c", 114);
      v10 = -2146881267;
LABEL_18:
      v11 = 455;
      v12 = v10;
      goto LABEL_19;
    }
    v13 = 0;
    while ( v17 < 0 )
    {
      if ( (v13 & 0xFE000000) != 0 )
      {
        DebugTraceError(2148086020LL, v13, "onecore\\ds\\security\\asn1\\ntasn1\\ntasn1der\\derdec.c", 127);
        v10 = -2146881276;
        goto LABEL_18;
      }
      if ( (unsigned __int64)v18 >= *(_QWORD *)(a1 + 24) )
      {
        v16 = 142;
        goto LABEL_8;
      }
      v13 = ((_DWORD)v13 << 7) | v17 & 0x7Fu;
      v17 = *v18++;
      *(_QWORD *)(a1 + 16) = v18;
    }
    v13 = (unsigned int)(unsigned __int8)v17 | ((_DWORD)v13 << 7);
  }
  if ( ((unsigned int)v13 | (v14 << 24)) == a3 )
  {
    v21 = *(_QWORD *)(a1 + 24);
    *a4 = 0;
    if ( *(_QWORD *)(a1 + 16) >= v21 )
    {
      v10 = -2146881278;
      v22 = 281;
      v23 = 2148086018LL;
LABEL_51:
      DebugTraceError(v23, v13, "onecore\\ds\\security\\asn1\\ntasn1\\ntasn1der\\derdec.c", v22);
      v19 = 868;
      goto LABEL_20;
    }
    if ( a5 )
      *a5 = 0;
    v24 = *(unsigned __int8 **)(a1 + 16);
    v25 = *v24;
    v26 = v24 + 1;
    *(_QWORD *)(a1 + 16) = v24 + 1;
    if ( (v25 & 0x80u) != 0 )
    {
      if ( (_BYTE)v25 == 0x80 )
      {
        if ( a5 )
        {
          *a5 = 1;
          v13 = (unsigned int)(*(_DWORD *)(a1 + 24) - *(_DWORD *)(a1 + 16));
          *a4 = v13;
          if ( v13 >= 2 )
          {
            v13 -= 2LL;
            *a4 = v13;
            goto LABEL_37;
          }
          v22 = 330;
        }
        else
        {
          v22 = 315;
        }
        v10 = -2146881267;
        v23 = 2148086029LL;
        goto LABEL_51;
      }
      v27 = v25 & 0x7F;
      if ( v27 > 4 )
      {
        v22 = 348;
LABEL_50:
        v23 = 2148086020LL;
        v10 = -2146881276;
        goto LABEL_51;
      }
      if ( v27 > *(_DWORD *)(a1 + 24) - *(_DWORD *)(a1 + 16) )
      {
        v10 = -2146881277;
        v22 = 358;
        v23 = 2148086019LL;
        goto LABEL_51;
      }
      v13 = 0;
      if ( (v25 & 0x7F) == 0 )
      {
LABEL_37:
        if ( v7 >= 0 || v13 <= *(_QWORD *)(a1 + 24) - *(_QWORD *)(a1 + 16) )
          return 0;
        v10 = -2146881278;
        v19 = 877;
        v20 = 2148086018LL;
        goto LABEL_40;
      }
      do
      {
        v28 = *v26++;
        v13 = v28 | (v13 << 8);
        *(_QWORD *)(a1 + 16) = v26;
        --v27;
      }
      while ( v27 );
    }
    else
    {
      v13 = v25;
    }
    *a4 = v13;
    if ( v13 > 0x7FFFFFF0 )
    {
      v22 = 374;
      goto LABEL_50;
    }
    goto LABEL_37;
  }
  v10 = -2146881269;
LABEL_41:
  *(_QWORD *)(a1 + 16) = v6;
  return v10;
}

```

## disassembly

```asm
0x180055ea8  push    rbx
0x180055eaa  push    rbp
0x180055eab  push    rsi
0x180055eac  push    rdi
0x180055ead  sub     rsp, 28h
0x180055eb1  mov     r10, [rsp+48h+arg_20]
0x180055eb6  mov     r11d, r8d
0x180055eb9  mov     rbp, [rcx+10h]
0x180055ebd  mov     esi, edx
0x180055ebf  mov     qword ptr [r9], 0
0x180055ec6  mov     rdi, rcx
0x180055ec9  test    r10, r10
0x180055ecc  jz      short loc_180055ED5
0x180055ece  mov     dword ptr [r10], 0
0x180055ed5  mov     rcx, [rcx+10h]
0x180055ed9  cmp     rcx, [rdi+18h]
0x180055edd  jb      short loc_180055EF4
0x180055edf  mov     ebx, 80093102h
0x180055ee4  mov     r9d, 1B4h
0x180055eea  mov     ecx, 80093102h
0x180055eef  jmp     loc_180055FBB
0x180055ef4  movzx   edx, byte ptr [rcx]
0x180055ef7  mov     al, dl
0x180055ef9  and     edx, 1Fh
0x180055efc  and     al, 0E0h
0x180055efe  movzx   ebx, al
0x180055f01  lea     rax, [rcx+1]
0x180055f05  mov     [rdi+10h], rax
0x180055f09  cmp     edx, 1Fh
0x180055f0c  jnz     loc_180055FDC
0x180055f12  cmp     rax, [rdi+18h]
0x180055f16  jb      short loc_180055F34
0x180055f18  lea     r9d, [rdx+45h]
0x180055f1c  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\asn1\\ntasn1\\nt"...
0x180055f23  mov     ecx, 80093102h
0x180055f28  call    DebugTraceError
0x180055f2d  mov     ebx, 80093102h
0x180055f32  jmp     short loc_180055FB3
0x180055f34  mov     al, [rax]
0x180055f36  lea     r8, [rcx+2]
0x180055f3a  mov     [rdi+10h], r8
0x180055f3e  cmp     al, 80h
0x180055f40  jnz     short loc_180055F60
0x180055f42  mov     r9d, 72h ; 'r'
0x180055f48  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\asn1\\ntasn1\\nt"...
0x180055f4f  mov     ecx, 8009310Dh
0x180055f54  call    DebugTraceError
0x180055f59  mov     ebx, 8009310Dh
0x180055f5e  jmp     short loc_180055FB3
0x180055f60  xor     edx, edx
0x180055f62  test    al, al
0x180055f64  jns     short loc_180055FD4
0x180055f66  test    edx, 0FE000000h
0x180055f6c  jnz     short loc_180055F97
0x180055f6e  cmp     r8, [rdi+18h]
0x180055f72  jnb     short loc_180055F8F
0x180055f74  movzx   ecx, al
0x180055f77  mov     eax, edx
0x180055f79  shl     eax, 7
0x180055f7c  and     ecx, 7Fh
0x180055f7f  mov     edx, ecx
0x180055f81  or      edx, eax
0x180055f83  mov     al, [r8]
0x180055f86  inc     r8
0x180055f89  mov     [rdi+10h], r8
0x180055f8d  jmp     short loc_180055F62
0x180055f8f  mov     r9d, 8Eh
0x180055f95  jmp     short loc_180055F1C
0x180055f97  mov     r9d, 7Fh
0x180055f9d  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\asn1\\ntasn1\\nt"...
0x180055fa4  mov     ecx, 80093104h
0x180055fa9  call    DebugTraceError
0x180055fae  mov     ebx, 80093104h
0x180055fb3  mov     r9d, 1C7h
0x180055fb9  mov     ecx, ebx
0x180055fbb  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\asn1\\ntasn1\\nt"...
0x180055fc2  call    DebugTraceError
0x180055fc7  mov     r9d, 352h
0x180055fcd  mov     ecx, ebx
0x180055fcf  jmp     loc_1800560AB
0x180055fd4  shl     edx, 7
0x180055fd7  movzx   eax, al
0x180055fda  or      edx, eax
0x180055fdc  mov     eax, ebx
0x180055fde  shl     eax, 18h
0x180055fe1  or      eax, edx
0x180055fe3  cmp     eax, r11d
0x180055fe6  jz      short loc_180055FF2
0x180055fe8  mov     ebx, 8009310Bh
0x180055fed  jmp     loc_1800560B7
0x180055ff2  mov     rax, [rdi+18h]
0x180055ff6  mov     qword ptr [r9], 0
0x180055ffd  cmp     [rdi+10h], rax
0x180056001  jb      short loc_180056018
0x180056003  mov     ebx, 80093102h
0x180056008  mov     r9d, 119h
0x18005600e  mov     ecx, 80093102h
0x180056013  jmp     loc_180056131
0x180056018  test    r10, r10
0x18005601b  jz      short loc_180056024
0x18005601d  mov     dword ptr [r10], 0
0x180056024  mov     rax, [rdi+10h]
0x180056028  movzx   ecx, byte ptr [rax]
0x18005602b  lea     r11, [rax+1]
0x18005602f  mov     [rdi+10h], r11
0x180056033  test    cl, cl
0x180056035  js      short loc_18005603E
0x180056037  mov     edx, ecx
0x180056039  jmp     loc_180056111
0x18005603e  cmp     cl, 80h
0x180056041  jnz     short loc_1800560C0
0x180056043  test    r10, r10
0x180056046  jnz     short loc_18005605D
0x180056048  mov     r9d, 13Bh
0x18005604e  mov     ebx, 8009310Dh
0x180056053  mov     ecx, 8009310Dh
0x180056058  jmp     loc_180056131
0x18005605d  mov     dword ptr [r10], 1
0x180056064  mov     edx, [rdi+18h]
0x180056067  sub     edx, [rdi+10h]
0x18005606a  mov     [r9], rdx
0x18005606d  cmp     rdx, 2
0x180056071  jnb     short loc_18005607B
0x180056073  mov     r9d, 14Ah
0x180056079  jmp     short loc_18005604E
0x18005607b  add     rdx, 0FFFFFFFFFFFFFFFEh
0x18005607f  mov     [r9], rdx
0x180056082  test    esi, esi
0x180056084  jns     loc_180056148
0x18005608a  mov     rax, [rdi+18h]
0x18005608e  sub     rax, [rdi+10h]
0x180056092  cmp     rdx, rax
0x180056095  jbe     loc_180056148
0x18005609b  mov     ebx, 80093102h
0x1800560a0  mov     r9d, 36Dh
0x1800560a6  mov     ecx, 80093102h
0x1800560ab  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\asn1\\ntasn1\\nt"...
0x1800560b2  call    DebugTraceError
0x1800560b7  mov     [rdi+10h], rbp
0x1800560bb  jmp     loc_18005614A
0x1800560c0  mov     r8d, ecx
0x1800560c3  and     r8d, 7Fh
0x1800560c7  cmp     r8d, 4
0x1800560cb  jbe     short loc_1800560D5
0x1800560cd  mov     r9d, 15Ch
0x1800560d3  jmp     short loc_180056127
0x1800560d5  mov     eax, [rdi+18h]
0x1800560d8  sub     eax, [rdi+10h]
0x1800560db  cmp     r8d, eax
0x1800560de  jbe     short loc_1800560F2
0x1800560e0  mov     ebx, 80093103h
0x1800560e5  mov     r9d, 166h
0x1800560eb  mov     ecx, 80093103h
0x1800560f0  jmp     short loc_180056131
0x1800560f2  xor     edx, edx
0x1800560f4  test    r8d, r8d
0x1800560f7  jz      short loc_180056082
0x1800560f9  movzx   eax, byte ptr [r11]
0x1800560fd  inc     r11
0x180056100  shl     rdx, 8
0x180056104  or      rdx, rax
0x180056107  mov     [rdi+10h], r11
0x18005610b  add     r8d, 0FFFFFFFFh
0x18005610f  jnz     short loc_1800560F9
0x180056111  mov     [r9], rdx
0x180056114  cmp     rdx, 7FFFFFF0h
0x18005611b  jbe     loc_180056082
0x180056121  mov     r9d, 176h
0x180056127  mov     ecx, 80093104h
0x18005612c  mov     ebx, 80093104h
0x180056131  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\asn1\\ntasn1\\nt"...
0x180056138  call    DebugTraceError
0x18005613d  mov     r9d, 364h
0x180056143  jmp     loc_180055FCD
0x180056148  xor     ebx, ebx
0x18005614a  mov     eax, ebx
0x18005614c  add     rsp, 28h
0x180056150  pop     rdi
0x180056151  pop     rsi
0x180056152  pop     rbp
0x180056153  pop     rbx
0x180056154  retn
```
