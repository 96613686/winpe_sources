# ASN1DER_DecExplicitTag

- ea: `0x180056274`
- end: `0x1800564d6`
- name: `ASN1DER_DecExplicitTag`
- size: `610`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18005615c`
- `0x1800564dc`
- `0x180056748`
- `0x180057a40`
- `0x180057ff0`
- `0x1800580d0`

## callees

- `0x180056274`
- `0x180056a94`

## string_xrefs

- `0x1800562dd`: `onecore\ds\security\asn1\ntasn1\ntasn1der\derdec.c`
- `0x180056309`: `onecore\ds\security\asn1\ntasn1\ntasn1der\derdec.c`
- `0x18005635e`: `onecore\ds\security\asn1\ntasn1\ntasn1der\derdec.c`
- `0x18005637c`: `onecore\ds\security\asn1\ntasn1\ntasn1der\derdec.c`
- `0x18005647b`: `onecore\ds\security\asn1\ntasn1\ntasn1der\derdec.c`
- `0x1800564b0`: `onecore\ds\security\asn1\ntasn1\ntasn1der\derdec.c`

## pseudocode

```c
__int64 __fastcall ASN1DER_DecExplicitTag(__int64 a1, __int64 a2, int a3, unsigned __int64 *a4)
{
  _BYTE *v4; // rsi
  int v7; // ebx
  unsigned int v9; // ebx
  __int64 v10; // r9
  __int64 v11; // rcx
  unsigned __int64 v12; // rdx
  int v13; // r10d
  char *v14; // rax
  __int64 v15; // r9
  char v16; // al
  char *v17; // r8
  __int64 v18; // r9
  __int64 v19; // rcx
  unsigned __int8 *v20; // r8
  unsigned __int64 v21; // r10
  __int64 v22; // r9
  __int64 v23; // rcx
  unsigned __int64 v24; // rax
  unsigned __int8 *v25; // r8
  unsigned __int64 v26; // rcx
  unsigned int v27; // r9d
  __int64 v28; // rax

  v4 = *(_BYTE **)(a1 + 16);
  v7 = a2;
  *a4 = 0;
  if ( (unsigned __int64)v4 >= *(_QWORD *)(a1 + 24) )
  {
    v9 = -2146881278;
    v10 = 436;
    v11 = 2148086018LL;
LABEL_17:
    DebugTraceError(v11, a2, "onecore\\ds\\security\\asn1\\ntasn1\\ntasn1der\\derdec.c", v10);
    v18 = 772;
LABEL_18:
    v19 = v9;
LABEL_44:
    DebugTraceError(v19, v12, "onecore\\ds\\security\\asn1\\ntasn1\\ntasn1der\\derdec.c", v18);
    goto LABEL_45;
  }
  v12 = *v4 & 0x1F;
  v13 = *v4 & 0xE0;
  v14 = v4 + 1;
  *(_QWORD *)(a1 + 16) = v4 + 1;
  if ( (_DWORD)v12 == 31 )
  {
    if ( (unsigned __int64)v14 >= *(_QWORD *)(a1 + 24) )
    {
      v15 = 100;
LABEL_6:
      DebugTraceError(2148086018LL, v12, "onecore\\ds\\security\\asn1\\ntasn1\\ntasn1der\\derdec.c", v15);
      v9 = -2146881278;
      goto LABEL_16;
    }
    v16 = *v14;
    v17 = v4 + 2;
    *(_QWORD *)(a1 + 16) = v4 + 2;
    if ( v16 == (char)0x80 )
    {
      DebugTraceError(2148086029LL, v12, "onecore\\ds\\security\\asn1\\ntasn1\\ntasn1der\\derdec.c", 114);
      v9 = -2146881267;
LABEL_16:
      v10 = 455;
      v11 = v9;
      goto LABEL_17;
    }
    v12 = 0;
    while ( v16 < 0 )
    {
      if ( (v12 & 0xFE000000) != 0 )
      {
        DebugTraceError(2148086020LL, v12, "onecore\\ds\\security\\asn1\\ntasn1\\ntasn1der\\derdec.c", 127);
        v9 = -2146881276;
        goto LABEL_16;
      }
      if ( (unsigned __int64)v17 >= *(_QWORD *)(a1 + 24) )
      {
        v15 = 142;
        goto LABEL_6;
      }
      v12 = ((_DWORD)v12 << 7) | v16 & 0x7Fu;
      v16 = *v17++;
      *(_QWORD *)(a1 + 16) = v17;
    }
    v12 = (unsigned int)(unsigned __int8)v16 | ((_DWORD)v12 << 7);
  }
  if ( ((unsigned int)v12 | (v13 << 24)) == a3 )
  {
    v20 = *(unsigned __int8 **)(a1 + 16);
    v21 = *(_QWORD *)(a1 + 24);
    *a4 = 0;
    if ( (unsigned __int64)v20 >= v21 )
    {
      v9 = -2146881278;
      v22 = 281;
      v23 = 2148086018LL;
LABEL_39:
      DebugTraceError(v23, v12, "onecore\\ds\\security\\asn1\\ntasn1\\ntasn1der\\derdec.c", v22);
      v18 = 790;
      goto LABEL_18;
    }
    v24 = *v20;
    v25 = v20 + 1;
    *(_QWORD *)(a1 + 16) = v25;
    if ( (v24 & 0x80u) != 0LL )
    {
      if ( (_BYTE)v24 == 0x80 )
      {
        v9 = -2146881267;
        v22 = 315;
        v23 = 2148086029LL;
        goto LABEL_39;
      }
      v27 = v24 & 0x7F;
      if ( v27 > 4 )
      {
        v22 = 348;
LABEL_38:
        v23 = 2148086020LL;
        v9 = -2146881276;
        goto LABEL_39;
      }
      if ( v27 > *(_DWORD *)(a1 + 24) - *(_DWORD *)(a1 + 16) )
      {
        v9 = -2146881277;
        v22 = 358;
        v23 = 2148086019LL;
        goto LABEL_39;
      }
      if ( (v24 & 0x7F) == 0 )
      {
        v24 = 0;
        goto LABEL_41;
      }
      v12 = 0;
      do
      {
        v28 = *v25++;
        v12 = v28 | (v12 << 8);
        *(_QWORD *)(a1 + 16) = v25;
        --v27;
      }
      while ( v27 );
      v24 = v12;
      v26 = v12;
    }
    else
    {
      v12 = (unsigned int)v24;
      v26 = (unsigned int)v24;
    }
    *a4 = v26;
    if ( v12 > 0x7FFFFFF0 )
    {
      v22 = 374;
      goto LABEL_38;
    }
LABEL_41:
    if ( v7 >= 0 || v24 <= v21 - (unsigned __int64)v25 )
      return 0;
    v9 = -2146881278;
    v18 = 799;
    v19 = 2148086018LL;
    goto LABEL_44;
  }
  v9 = -2146881269;
LABEL_45:
  *(_QWORD *)(a1 + 16) = v4;
  return v9;
}

```

## disassembly

```asm
0x180056274  mov     [rsp+arg_0], rbx
0x180056279  mov     [rsp+arg_8], rsi
0x18005627e  push    rdi
0x18005627f  sub     rsp, 20h
0x180056283  mov     rsi, [rcx+10h]
0x180056287  mov     r11, r9
0x18005628a  mov     r9d, r8d
0x18005628d  mov     ebx, edx
0x18005628f  mov     rdi, rcx
0x180056292  mov     qword ptr [r11], 0
0x180056299  cmp     rsi, [rcx+18h]
0x18005629d  jb      short loc_1800562B4
0x18005629f  mov     ebx, 80093102h
0x1800562a4  mov     r9d, 1B4h
0x1800562aa  mov     ecx, 80093102h
0x1800562af  jmp     loc_18005637C
0x1800562b4  movzx   edx, byte ptr [rsi]
0x1800562b7  mov     al, dl
0x1800562b9  and     edx, 1Fh
0x1800562bc  and     al, 0E0h
0x1800562be  movzx   r10d, al
0x1800562c2  lea     rax, [rsi+1]
0x1800562c6  mov     [rcx+10h], rax
0x1800562ca  cmp     edx, 1Fh
0x1800562cd  jnz     loc_18005639D
0x1800562d3  cmp     rax, [rcx+18h]
0x1800562d7  jb      short loc_1800562F5
0x1800562d9  lea     r9d, [rdx+45h]
0x1800562dd  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\asn1\\ntasn1\\nt"...
0x1800562e4  mov     ecx, 80093102h
0x1800562e9  call    DebugTraceError
0x1800562ee  mov     ebx, 80093102h
0x1800562f3  jmp     short loc_180056374
0x1800562f5  mov     al, [rax]
0x1800562f7  lea     r8, [rsi+2]
0x1800562fb  mov     [rcx+10h], r8
0x1800562ff  cmp     al, 80h
0x180056301  jnz     short loc_180056321
0x180056303  mov     r9d, 72h ; 'r'
0x180056309  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\asn1\\ntasn1\\nt"...
0x180056310  mov     ecx, 8009310Dh
0x180056315  call    DebugTraceError
0x18005631a  mov     ebx, 8009310Dh
0x18005631f  jmp     short loc_180056374
0x180056321  xor     edx, edx
0x180056323  test    al, al
0x180056325  jns     short loc_180056395
0x180056327  test    edx, 0FE000000h
0x18005632d  jnz     short loc_180056358
0x18005632f  cmp     r8, [rdi+18h]
0x180056333  jnb     short loc_180056350
0x180056335  movzx   ecx, al
0x180056338  mov     eax, edx
0x18005633a  shl     eax, 7
0x18005633d  and     ecx, 7Fh
0x180056340  mov     edx, ecx
0x180056342  or      edx, eax
0x180056344  mov     al, [r8]
0x180056347  inc     r8
0x18005634a  mov     [rdi+10h], r8
0x18005634e  jmp     short loc_180056323
0x180056350  mov     r9d, 8Eh
0x180056356  jmp     short loc_1800562DD
0x180056358  mov     r9d, 7Fh
0x18005635e  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\asn1\\ntasn1\\nt"...
0x180056365  mov     ecx, 80093104h
0x18005636a  call    DebugTraceError
0x18005636f  mov     ebx, 80093104h
0x180056374  mov     r9d, 1C7h
0x18005637a  mov     ecx, ebx
0x18005637c  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\asn1\\ntasn1\\nt"...
0x180056383  call    DebugTraceError
0x180056388  mov     r9d, 304h
0x18005638e  mov     ecx, ebx
0x180056390  jmp     loc_1800564B0
0x180056395  shl     edx, 7
0x180056398  movzx   eax, al
0x18005639b  or      edx, eax
0x18005639d  mov     eax, r10d
0x1800563a0  shl     eax, 18h
0x1800563a3  or      eax, edx
0x1800563a5  cmp     eax, r9d
0x1800563a8  jz      short loc_1800563B4
0x1800563aa  mov     ebx, 8009310Bh
0x1800563af  jmp     loc_1800564BC
0x1800563b4  mov     r8, [rdi+10h]
0x1800563b8  mov     r10, [rdi+18h]
0x1800563bc  mov     qword ptr [r11], 0
0x1800563c3  cmp     r8, r10
0x1800563c6  jb      short loc_1800563DD
0x1800563c8  mov     ebx, 80093102h
0x1800563cd  mov     r9d, 119h
0x1800563d3  mov     ecx, 80093102h
0x1800563d8  jmp     loc_18005647B
0x1800563dd  movzx   eax, byte ptr [r8]
0x1800563e1  inc     r8
0x1800563e4  mov     [rdi+10h], r8
0x1800563e8  test    al, al
0x1800563ea  js      short loc_1800563F2
0x1800563ec  mov     edx, eax
0x1800563ee  mov     ecx, eax
0x1800563f0  jmp     short loc_18005645F
0x1800563f2  cmp     al, 80h
0x1800563f4  jnz     short loc_180056408
0x1800563f6  mov     ebx, 8009310Dh
0x1800563fb  mov     r9d, 13Bh
0x180056401  mov     ecx, 8009310Dh
0x180056406  jmp     short loc_18005647B
0x180056408  mov     r9d, eax
0x18005640b  and     r9d, 7Fh
0x18005640f  cmp     r9d, 4
0x180056413  jbe     short loc_18005641D
0x180056415  mov     r9d, 15Ch
0x18005641b  jmp     short loc_180056471
0x18005641d  mov     eax, [rdi+18h]
0x180056420  sub     eax, [rdi+10h]
0x180056423  cmp     r9d, eax
0x180056426  jbe     short loc_18005643A
0x180056428  mov     ebx, 80093103h
0x18005642d  mov     r9d, 166h
0x180056433  mov     ecx, 80093103h
0x180056438  jmp     short loc_18005647B
0x18005643a  test    r9d, r9d
0x18005643d  jz      short loc_180056492
0x18005643f  xor     edx, edx
0x180056441  movzx   eax, byte ptr [r8]
0x180056445  inc     r8
0x180056448  shl     rdx, 8
0x18005644c  or      rdx, rax
0x18005644f  mov     [rdi+10h], r8
0x180056453  add     r9d, 0FFFFFFFFh
0x180056457  jnz     short loc_180056441
0x180056459  mov     rax, rdx
0x18005645c  mov     rcx, rdx
0x18005645f  mov     [r11], rcx
0x180056462  cmp     rdx, 7FFFFFF0h
0x180056469  jbe     short loc_180056494
0x18005646b  mov     r9d, 176h
0x180056471  mov     ecx, 80093104h
0x180056476  mov     ebx, 80093104h
0x18005647b  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\asn1\\ntasn1\\nt"...
0x180056482  call    DebugTraceError
0x180056487  mov     r9d, 316h
0x18005648d  jmp     loc_18005638E
0x180056492  xor     eax, eax
0x180056494  test    ebx, ebx
0x180056496  jns     short loc_1800564C2
0x180056498  sub     r10, r8
0x18005649b  cmp     rax, r10
0x18005649e  jbe     short loc_1800564C2
0x1800564a0  mov     ebx, 80093102h
0x1800564a5  mov     r9d, 31Fh
0x1800564ab  mov     ecx, 80093102h
0x1800564b0  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\asn1\\ntasn1\\nt"...
0x1800564b7  call    DebugTraceError
0x1800564bc  mov     [rdi+10h], rsi
0x1800564c0  jmp     short loc_1800564C4
0x1800564c2  xor     ebx, ebx
0x1800564c4  mov     rsi, [rsp+28h+arg_8]
0x1800564c9  mov     eax, ebx
0x1800564cb  mov     rbx, [rsp+28h+arg_0]
0x1800564d0  add     rsp, 20h
0x1800564d4  pop     rdi
0x1800564d5  retn
```
