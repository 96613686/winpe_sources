# ASN1_Encode_Sequence

- ea: `0x180057c50`
- end: `0x180057e28`
- name: `ASN1_Encode_Sequence`
- size: `472`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18003b148`
- `0x1800559a4`
- `0x180056a94`
- `0x180057c50`
- `0x18005e010`

## string_xrefs

- `0x180057e00`: `onecore\ds\security\asn1\ntasn1\ntasn1obj\sequence.c`
- `0x180057d09`: `onecore\ds\security\asn1\ntasn1\ntasn1obj\objptr.c`

## pseudocode

```c
__int64 __fastcall ASN1_Encode_Sequence(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  unsigned int v6; // ebx
  int v7; // ebp
  __int64 v8; // rdi
  __int64 v9; // rdx
  _QWORD *v10; // r8
  int v11; // eax
  bool v12; // zf
  __int64 v13; // r12
  __int64 v14; // r13
  __int64 v15; // rax
  int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // r9
  __int64 v19; // rax
  __int64 v20; // rdx
  __int64 v22; // [rsp+70h] [rbp+8h]
  __int64 v23; // [rsp+78h] [rbp+10h]

  v22 = a2[3];
  v6 = 0;
  v7 = *(_DWORD *)(*(_QWORD *)(a1 + 64) + 24LL);
  v23 = a2[2];
  while ( v7 )
  {
    v8 = *(_QWORD *)(*(_QWORD *)(a1 + 64) + 32LL) + 88LL * (unsigned int)--v7;
    v9 = *(unsigned int *)(v8 + 72);
    if ( (v9 & 4) != 0 )
      v10 = a3;
    else
      v10 = (_QWORD *)((char *)a3 + *(_QWORD *)(v8 + 8));
    v11 = *(_DWORD *)(v8 + 28);
    if ( (v11 & 4) != 0 )
    {
      v12 = *(_DWORD *)((char *)a3 + *(_QWORD *)(v8 + 16)) == 0;
    }
    else
    {
      if ( (v11 & 8) == 0 )
        goto LABEL_11;
      v12 = (*(_WORD *)(v8 + 56) & *(_WORD *)((_BYTE *)a3 + *(_QWORD *)(v8 + 16))) == 0;
    }
    if ( !v12 )
    {
LABEL_11:
      v13 = a2[3];
      v14 = a2[2];
      if ( (v9 & 1) == 0 || (v10 = (_QWORD *)*v10) != 0 )
      {
        v6 = (*(__int64 (__fastcall **)(__int64, _QWORD *, _QWORD *))(*(_QWORD *)(v8 + 64) + 8LL))(v8, a2, v10);
      }
      else
      {
        v6 = 0;
        if ( (*(_BYTE *)(v8 + 28) & 2) == 0 )
        {
          v6 = -2146893785;
          DebugTraceError(2148073511LL, v9, "onecore\\ds\\security\\asn1\\ntasn1\\ntasn1obj\\objptr.c", 56);
        }
      }
      if ( (v6 & 0x80000000) != 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_ssD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            10,
            (unsigned int)WPP_54c28acdadbf318fdf603a2d0ae0fcb3_Traceguids,
            *(_QWORD *)a1,
            *(_QWORD *)v8,
            v6);
        return v6;
      }
      v15 = v14 + a2[3] - v13 - a2[2];
      if ( v15 )
      {
        if ( (*(_BYTE *)(v8 + 28) & 1) != 0 )
        {
          v16 = ASN1DER_EncExplicitTag(a2, *(unsigned int *)(v8 + 32), (unsigned int)v15);
          v6 = v16;
          if ( v16 < 0 )
          {
            v18 = 220;
LABEL_29:
            DebugTraceError((unsigned int)v16, v17, "onecore\\ds\\security\\asn1\\ntasn1\\ntasn1obj\\sequence.c", v18);
            return v6;
          }
        }
      }
    }
  }
  v19 = a2[3] - a2[2] - v22;
  if ( v19 + v23 || (*(_DWORD *)(a1 + 28) & 2) == 0 )
  {
    v20 = *(unsigned int *)(a1 + 24);
    if ( (_DWORD)v20 )
    {
      v16 = ASN1DER_EncExplicitTag(a2, v20, (unsigned int)(v19 + v23));
      v6 = v16;
      if ( v16 < 0 )
      {
        v18 = 253;
        goto LABEL_29;
      }
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180057c50  mov     [rsp+arg_10], rbx
0x180057c55  mov     [rsp+arg_18], r9d
0x180057c5a  push    rbp
0x180057c5b  push    rsi
0x180057c5c  push    rdi
0x180057c5d  push    r12
0x180057c5f  push    r13
0x180057c61  push    r14
0x180057c63  push    r15
0x180057c65  sub     rsp, 30h
0x180057c69  mov     rax, [rcx+40h]
0x180057c6d  mov     r14, rcx
0x180057c70  mov     rcx, [rdx+18h]
0x180057c74  mov     r15, r8
0x180057c77  mov     [rsp+68h+arg_0], rcx
0x180057c7c  mov     rsi, rdx
0x180057c7f  mov     rcx, [rdx+10h]
0x180057c83  xor     ebx, ebx
0x180057c85  mov     ebp, [rax+18h]
0x180057c88  mov     [rsp+68h+arg_8], rcx
0x180057c8d  test    ebp, ebp
0x180057c8f  jz      loc_180057DC2
0x180057c95  dec     ebp
0x180057c97  mov     eax, ebp
0x180057c99  imul    rdi, rax, 58h ; 'X'
0x180057c9d  mov     rax, [r14+40h]
0x180057ca1  add     rdi, [rax+20h]
0x180057ca5  mov     edx, [rdi+48h]
0x180057ca8  test    dl, 4
0x180057cab  jnz     short loc_180057CB6
0x180057cad  mov     r8, [rdi+8]
0x180057cb1  add     r8, r15
0x180057cb4  jmp     short loc_180057CB9
0x180057cb6  mov     r8, r15
0x180057cb9  mov     eax, [rdi+1Ch]
0x180057cbc  test    al, 4
0x180057cbe  jz      short loc_180057CCB
0x180057cc0  mov     rax, [rdi+10h]
0x180057cc4  cmp     dword ptr [r15+rax], 0
0x180057cc9  jmp     short loc_180057CE1
0x180057ccb  test    al, 8
0x180057ccd  jz      short loc_180057CE3
0x180057ccf  mov     rax, [rdi+10h]
0x180057cd3  movzx   ecx, word ptr [r15+rax]
0x180057cd8  xor     eax, eax
0x180057cda  and     cx, [rdi+38h]
0x180057cde  cmp     ax, cx
0x180057ce1  jz      short loc_180057C8D
0x180057ce3  mov     r12, [rsi+18h]
0x180057ce7  mov     r13, [rsi+10h]
0x180057ceb  test    dl, 1
0x180057cee  jz      short loc_180057D1C
0x180057cf0  mov     r8, [r8]
0x180057cf3  test    r8, r8
0x180057cf6  jnz     short loc_180057D1C
0x180057cf8  xor     ebx, ebx
0x180057cfa  test    byte ptr [rdi+1Ch], 2
0x180057cfe  jnz     short loc_180057D31
0x180057d00  lea     r9d, [r8+38h]
0x180057d04  mov     ecx, 80090027h
0x180057d09  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\asn1\\ntasn1\\nt"...
0x180057d10  mov     ebx, 80090027h
0x180057d15  call    DebugTraceError
0x180057d1a  jmp     short loc_180057D31
0x180057d1c  mov     rax, [rdi+40h]
0x180057d20  mov     rdx, rsi
0x180057d23  mov     rcx, rdi
0x180057d26  mov     rax, [rax+8]
0x180057d2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057d2f  mov     ebx, eax
0x180057d31  test    ebx, ebx
0x180057d33  js      short loc_180057D83
0x180057d35  mov     rax, [rsi+18h]
0x180057d39  mov     r9d, [rsp+68h+arg_18]
0x180057d41  sub     rax, r12
0x180057d44  sub     rax, [rsi+10h]
0x180057d48  add     rax, r13
0x180057d4b  jz      loc_180057C8D
0x180057d51  test    byte ptr [rdi+1Ch], 1
0x180057d55  jz      loc_180057C8D
0x180057d5b  mov     edx, [rdi+20h]
0x180057d5e  mov     rcx, rsi
0x180057d61  mov     r8d, eax
0x180057d64  call    ASN1DER_EncExplicitTag
0x180057d69  mov     r9d, [rsp+68h+arg_18]
0x180057d71  mov     ebx, eax
0x180057d73  test    eax, eax
0x180057d75  jns     loc_180057C8D
0x180057d7b  mov     r9d, 0DCh
0x180057d81  jmp     short loc_180057E00
0x180057d83  mov     rcx, cs:WPP_GLOBAL_Control
0x180057d8a  lea     rax, WPP_GLOBAL_Control
0x180057d91  cmp     rcx, rax
0x180057d94  jz      short loc_180057E0E
0x180057d96  test    byte ptr [rcx+1Ch], 1
0x180057d9a  jz      short loc_180057E0E
0x180057d9c  mov     rax, [rdi]
0x180057d9f  lea     r8, WPP_54c28acdadbf318fdf603a2d0ae0fcb3_Traceguids
0x180057da6  mov     r9, [r14]
0x180057da9  mov     edx, 0Ah
0x180057dae  mov     rcx, [rcx+10h]
0x180057db2  mov     [rsp+68h+var_40], ebx
0x180057db6  mov     [rsp+68h+var_48], rax
0x180057dbb  call    WPP_SF_ssD
0x180057dc0  jmp     short loc_180057E0E
0x180057dc2  mov     rax, [rsi+18h]
0x180057dc6  sub     rax, [rsi+10h]
0x180057dca  sub     rax, [rsp+68h+arg_0]
0x180057dcf  mov     rcx, [rsp+68h+arg_8]
0x180057dd4  add     rcx, rax
0x180057dd7  jnz     short loc_180057DE1
0x180057dd9  mov     eax, [r14+1Ch]
0x180057ddd  test    al, 2
0x180057ddf  jnz     short loc_180057E0E
0x180057de1  mov     edx, [r14+18h]
0x180057de5  test    edx, edx
0x180057de7  jz      short loc_180057E0E
0x180057de9  mov     r8d, ecx
0x180057dec  mov     rcx, rsi
0x180057def  call    ASN1DER_EncExplicitTag
0x180057df4  mov     ebx, eax
0x180057df6  test    eax, eax
0x180057df8  jns     short loc_180057E0E
0x180057dfa  mov     r9d, 0FDh
0x180057e00  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\asn1\\ntasn1\\nt"...
0x180057e07  mov     ecx, eax
0x180057e09  call    DebugTraceError
0x180057e0e  mov     eax, ebx
0x180057e10  mov     rbx, [rsp+68h+arg_10]
0x180057e18  add     rsp, 30h
0x180057e1c  pop     r15
0x180057e1e  pop     r14
0x180057e20  pop     r13
0x180057e22  pop     r12
0x180057e24  pop     rdi
0x180057e25  pop     rsi
0x180057e26  pop     rbp
0x180057e27  retn
```
