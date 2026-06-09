# ASN1_Decode_SequenceOf

- ea: `0x180057a40`
- end: `0x180057c4a`
- name: `ASN1_Decode_SequenceOf`
- size: `522`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180056274`
- `0x180056748`
- `0x180056a94`
- `0x180057a40`
- `0x1800586c6`
- `0x18005e010`

## string_xrefs

- `0x180057c21`: `onecore\ds\security\asn1\ntasn1\ntasn1obj\sequence.c`

## pseudocode

```c
__int64 __fastcall ASN1_Decode_SequenceOf(__int64 a1, __int64 a2, unsigned int a3, __int64 a4, __int64 *a5, _QWORD *a6)
{
  __int64 v10; // rax
  int v11; // r8d
  __int64 v12; // r13
  __int64 v13; // r14
  unsigned int v14; // ebx
  unsigned __int64 v15; // rax
  int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // r9
  unsigned __int64 v19; // rdx
  unsigned __int64 v20; // rcx
  _QWORD *v21; // rdi
  unsigned __int64 v22; // rax
  _DWORD *v23; // rsi
  int v24; // r8d
  _QWORD *v25; // rsi
  bool v26; // sf
  __int64 v27; // rcx
  __int64 *v28; // r15
  __int64 v29; // rdi
  unsigned int v30; // r12d
  _QWORD v32[2]; // [rsp+40h] [rbp-40h] BYREF
  unsigned __int64 v33; // [rsp+50h] [rbp-30h]
  unsigned __int64 v34; // [rsp+58h] [rbp-28h]
  __int64 v35; // [rsp+60h] [rbp-20h]
  __int64 v36; // [rsp+68h] [rbp-18h]
  __int128 v37; // [rsp+70h] [rbp-10h]
  unsigned __int64 v38; // [rsp+C0h] [rbp+40h] BYREF
  unsigned int v39; // [rsp+D0h] [rbp+50h]

  v39 = a3;
  memset_0(v32, 0, 0x40u);
  v10 = *(_QWORD *)(a1 + 64);
  v11 = *(_DWORD *)(a1 + 24);
  v12 = *(_QWORD *)(a2 + 16);
  v38 = 0;
  v13 = *(_QWORD *)(v10 + 32);
  if ( v11 )
  {
    v16 = ASN1DER_DecExplicitTag(a2, 0x80000000LL, v11, &v38);
    v14 = v16;
    if ( v16 < 0 )
    {
      v18 = 789;
LABEL_22:
      v27 = (unsigned int)v16;
      goto LABEL_23;
    }
    v15 = v38;
  }
  else
  {
    v14 = 0;
    v15 = *(_QWORD *)(a2 + 24) - v12;
  }
  if ( !v15 )
    return v14;
  v19 = *(_QWORD *)(a2 + 16);
  v32[0] = v19;
  v33 = v19;
  v32[1] = v15;
  v37 = 0;
  v20 = v19 + v15;
  v34 = v19 + v15;
  v35 = 0;
  v36 = 0;
  if ( !a4 )
  {
    *(_QWORD *)(a2 + 16) = v20;
    v21 = a6;
    while ( v19 < v20 )
    {
      *v21 -= *(unsigned int *)(*(_QWORD *)(v13 + 64) + 4LL);
      v16 = (*(__int64 (__fastcall **)(__int64, _QWORD *, _QWORD, _QWORD, _QWORD, _QWORD *))(*(_QWORD *)(v13 + 64) + 16LL))(
              v13,
              v32,
              a3,
              0,
              0,
              v21);
      v14 = v16;
      if ( v16 < 0 )
      {
        v18 = 832;
        goto LABEL_22;
      }
      v20 = v34;
      v19 = v33;
    }
    return v14;
  }
  v22 = *(_QWORD *)(a1 + 8);
  v23 = (_DWORD *)(a4 + *(_QWORD *)(a1 + 16));
  *(_QWORD *)(a2 + 16) = v12;
  v24 = *(_DWORD *)(a1 + 24);
  v38 = v22;
  v16 = ASN1DER_DecSequenceOfAny(a2, v19, v24, (_DWORD)v23);
  v14 = v16;
  if ( v16 < 0 )
  {
    v18 = 870;
    goto LABEL_22;
  }
  v17 = (unsigned int)(*v23 * *(_DWORD *)(*(_QWORD *)(v13 + 64) + 4LL));
  v25 = a6;
  v26 = *a6 - v17 < 0;
  *a6 -= v17;
  if ( v26 )
  {
    v14 = -2146893784;
    v18 = 884;
    v27 = 2148073512LL;
LABEL_23:
    DebugTraceError(v27, v17, "onecore\\ds\\security\\asn1\\ntasn1\\ntasn1obj\\sequence.c", v18);
    return v14;
  }
  v28 = a5;
  *(_QWORD *)(v38 + a4) = *a5;
  v29 = *v28;
  v30 = v39;
  *v28 += v17;
  while ( v33 < v34 )
  {
    v16 = (*(__int64 (__fastcall **)(__int64, _QWORD *, _QWORD, __int64, __int64 *, _QWORD *))(*(_QWORD *)(v13 + 64)
                                                                                             + 16LL))(
            v13,
            v32,
            v30,
            v29,
            v28,
            v25);
    v14 = v16;
    if ( v16 < 0 )
    {
      v18 = 905;
      goto LABEL_22;
    }
    v29 += *(unsigned int *)(*(_QWORD *)(v13 + 64) + 4LL);
  }
  return v14;
}

```

## disassembly

```asm
0x180057a40  mov     [rsp-38h+arg_18], rbx
0x180057a45  mov     [rsp-38h+arg_10], r8d
0x180057a4a  push    rbp
0x180057a4b  push    rsi
0x180057a4c  push    rdi
0x180057a4d  push    r12
0x180057a4f  push    r13
0x180057a51  push    r14
0x180057a53  push    r15
0x180057a55  mov     rbp, rsp
0x180057a58  sub     rsp, 80h
0x180057a5f  mov     rdi, rdx
0x180057a62  mov     esi, r8d
0x180057a65  xor     edx, edx; Val
0x180057a67  mov     r15, rcx
0x180057a6a  lea     rcx, [rbp+var_40]; void *
0x180057a6e  mov     r12, r9
0x180057a71  lea     r8d, [rdx+40h]; Size
0x180057a75  call    memset_0
0x180057a7a  mov     rax, [r15+40h]
0x180057a7e  mov     r8d, [r15+18h]
0x180057a82  mov     r13, [rdi+10h]
0x180057a86  mov     [rbp+arg_0], 0
0x180057a8e  mov     r14, [rax+20h]
0x180057a92  test    r8d, r8d
0x180057a95  jnz     short loc_180057AA2
0x180057a97  mov     rax, [rdi+18h]
0x180057a9b  xor     ebx, ebx
0x180057a9d  sub     rax, r13
0x180057aa0  jmp     short loc_180057AC8
0x180057aa2  lea     r9, [rbp+arg_0]
0x180057aa6  mov     edx, 80000000h
0x180057aab  mov     rcx, rdi
0x180057aae  call    ASN1DER_DecExplicitTag
0x180057ab3  mov     ebx, eax
0x180057ab5  test    eax, eax
0x180057ab7  jns     short loc_180057AC4
0x180057ab9  mov     r9d, 315h
0x180057abf  jmp     loc_180057C1F
0x180057ac4  mov     rax, [rbp+arg_0]
0x180057ac8  test    rax, rax
0x180057acb  jz      loc_180057C2D
0x180057ad1  mov     rdx, [rdi+10h]
0x180057ad5  xorps   xmm0, xmm0
0x180057ad8  mov     [rbp+var_40], rdx
0x180057adc  mov     [rbp+var_30], rdx
0x180057ae0  mov     [rbp+var_38], rax
0x180057ae4  movdqa  [rbp+var_10], xmm0
0x180057ae9  lea     rcx, [rdx+rax]
0x180057aed  mov     [rbp+var_28], rcx
0x180057af1  mov     [rbp+var_20], 0
0x180057af9  mov     [rbp+var_18], 0
0x180057b01  test    r12, r12
0x180057b04  jnz     short loc_180057B64
0x180057b06  mov     [rdi+10h], rcx
0x180057b0a  mov     rdi, [rbp+arg_28]
0x180057b0e  cmp     rdx, rcx
0x180057b11  jnb     loc_180057C2D
0x180057b17  mov     rax, [r14+40h]
0x180057b1b  lea     rdx, [rbp+var_40]
0x180057b1f  mov     [rsp+80h+var_58], rdi
0x180057b24  xor     r9d, r9d
0x180057b27  mov     r8d, esi
0x180057b2a  mov     [rsp+80h+var_60], 0
0x180057b33  mov     ecx, [rax+4]
0x180057b36  sub     [rdi], rcx
0x180057b39  mov     rcx, r14
0x180057b3c  mov     rax, [r14+40h]
0x180057b40  mov     rax, [rax+10h]
0x180057b44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057b49  mov     ebx, eax
0x180057b4b  test    eax, eax
0x180057b4d  js      short loc_180057B59
0x180057b4f  mov     rcx, [rbp+var_28]
0x180057b53  mov     rdx, [rbp+var_30]
0x180057b57  jmp     short loc_180057B0E
0x180057b59  mov     r9d, 340h
0x180057b5f  jmp     loc_180057C1F
0x180057b64  mov     rsi, [r15+10h]
0x180057b68  mov     rcx, rdi
0x180057b6b  mov     rax, [r15+8]
0x180057b6f  add     rsi, r12
0x180057b72  mov     [rdi+10h], r13
0x180057b76  mov     r9, rsi
0x180057b79  mov     r8d, [r15+18h]
0x180057b7d  mov     [rbp+arg_0], rax
0x180057b81  call    ASN1DER_DecSequenceOfAny
0x180057b86  mov     ebx, eax
0x180057b88  test    eax, eax
0x180057b8a  jns     short loc_180057B97
0x180057b8c  mov     r9d, 366h
0x180057b92  jmp     loc_180057C1F
0x180057b97  mov     rax, [r14+40h]
0x180057b9b  mov     edx, [rax+4]
0x180057b9e  imul    edx, [rsi]
0x180057ba1  mov     rsi, [rbp+arg_28]
0x180057ba5  sub     [rsi], rdx
0x180057ba8  jns     short loc_180057BBC
0x180057baa  mov     ebx, 80090028h
0x180057baf  mov     r9d, 374h
0x180057bb5  mov     ecx, 80090028h
0x180057bba  jmp     short loc_180057C21
0x180057bbc  mov     r15, [rbp+arg_20]
0x180057bc0  mov     rcx, [rbp+arg_0]
0x180057bc4  mov     rax, [r15]
0x180057bc7  mov     [rcx+r12], rax
0x180057bcb  mov     rdi, [r15]
0x180057bce  mov     r12d, [rbp+arg_10]
0x180057bd2  lea     rax, [rdi+rdx]
0x180057bd6  mov     [r15], rax
0x180057bd9  mov     rax, [rbp+var_28]
0x180057bdd  cmp     [rbp+var_30], rax
0x180057be1  jnb     short loc_180057C2D
0x180057be3  mov     rax, [r14+40h]
0x180057be7  lea     rdx, [rbp+var_40]
0x180057beb  mov     [rsp+80h+var_58], rsi
0x180057bf0  mov     r9, rdi
0x180057bf3  mov     r8d, r12d
0x180057bf6  mov     [rsp+80h+var_60], r15
0x180057bfb  mov     rcx, r14
0x180057bfe  mov     rax, [rax+10h]
0x180057c02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057c07  mov     ebx, eax
0x180057c09  test    eax, eax
0x180057c0b  js      short loc_180057C19
0x180057c0d  mov     rax, [r14+40h]
0x180057c11  mov     ecx, [rax+4]
0x180057c14  add     rdi, rcx
0x180057c17  jmp     short loc_180057BD9
0x180057c19  mov     r9d, 389h
0x180057c1f  mov     ecx, eax
0x180057c21  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\asn1\\ntasn1\\nt"...
0x180057c28  call    DebugTraceError
0x180057c2d  mov     eax, ebx
0x180057c2f  mov     rbx, [rsp+80h+arg_18]
0x180057c37  add     rsp, 80h
0x180057c3e  pop     r15
0x180057c40  pop     r14
0x180057c42  pop     r13
0x180057c44  pop     r12
0x180057c46  pop     rdi
0x180057c47  pop     rsi
0x180057c48  pop     rbp
0x180057c49  retn
```
