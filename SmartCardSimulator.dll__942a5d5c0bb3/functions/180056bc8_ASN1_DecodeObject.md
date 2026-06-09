# ASN1_DecodeObject

- ea: `0x180056bc8`
- end: `0x180056de5`
- name: `ASN1_DecodeObject`
- size: `541`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, void *, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180056e4c`

## callees

- `0x180056a94`
- `0x180056bc8`
- `0x1800572b8`
- `0x180057300`
- `0x1800586c6`
- `0x18005e010`

## string_xrefs

- `0x180056dba`: `onecore\ds\security\asn1\ntasn1\ntasn1obj\object.c`

## pseudocode

```c
__int64 __fastcall ASN1_DecodeObject(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        unsigned __int64 a4,
        _QWORD *a5,
        char *a6,
        size_t *a7)
{
  size_t *v10; // rbx
  int v11; // r14d
  __int64 v12; // r9
  __int64 v13; // rcx
  _QWORD *v14; // r15
  size_t v15; // r14
  size_t v16; // r14
  __int64 v17; // rcx
  __int64 v18; // rax
  int v19; // edx
  int v20; // r8d
  __int64 v21; // rbx
  PVOID *v22; // rcx
  PVOID v23; // rcx
  __int64 v24; // rax
  char *v26; // [rsp+40h] [rbp-41h] BYREF
  _QWORD v27[2]; // [rsp+50h] [rbp-31h] BYREF
  _QWORD v28[2]; // [rsp+60h] [rbp-21h] BYREF
  __int64 v29; // [rsp+70h] [rbp-11h]
  __int64 v30; // [rsp+78h] [rbp-9h]
  __int64 v31; // [rsp+80h] [rbp-1h]
  __int64 v32; // [rsp+88h] [rbp+7h]
  __int128 v33; // [rsp+90h] [rbp+Fh]
  size_t v34; // [rsp+D0h] [rbp+4Fh] BYREF

  v26 = 0;
  v34 = 0;
  if ( !a1 || !a3 || (v10 = a7) == 0 )
  {
    v11 = -2146893785;
    v12 = 200;
    v13 = 2148073511LL;
    goto LABEL_26;
  }
  if ( a4 > 0x7FFFFFF0 )
  {
    v11 = -2146881276;
    v12 = 207;
    v13 = 2148086020LL;
LABEL_26:
    DebugTraceError(v13, a2, "onecore\\ds\\security\\asn1\\ntasn1\\ntasn1obj\\object.c", v12);
    return (unsigned int)v11;
  }
  v14 = a1 + 8;
  v30 = a3 + a4;
  v33 = 0;
  v28[0] = a3;
  v29 = a3;
  v28[1] = a4;
  v31 = 0;
  v32 = 0;
  if ( a6 )
  {
    v16 = *a7;
    if ( *a7 < *(unsigned int *)(*v14 + 4LL) )
    {
      v11 = -2146893784;
      v12 = 234;
      v13 = 2148073512LL;
      goto LABEL_26;
    }
    memset_0(a6, 0, *a7);
    v17 = *v14;
    v26 = &a6[*(unsigned int *)(*v14 + 4LL)];
    v15 = v16 - *(unsigned int *)(v17 + 4);
  }
  else
  {
    v15 = 0;
  }
  v18 = *v14;
  v34 = v15;
  v11 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD *, _QWORD, char *, char **, size_t *))(v18 + 16))(
          a1,
          v28,
          0,
          a6,
          &v26,
          &v34);
  if ( v11 >= 0 )
  {
    if ( a6 )
    {
      *v10 -= v34;
    }
    else
    {
      v24 = *v14;
      v34 = -(__int64)v34;
      *v10 = v34 + *(unsigned int *)(v24 + 4);
    }
    if ( a5 )
      *a5 = v29 - v28[0];
  }
  else
  {
    v21 = a4;
    if ( a4 >= 0x100 )
      v21 = 256;
    v22 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_sqPD(*((_QWORD *)WPP_GLOBAL_Control + 2), v19, v20, *a1, a3, a4, v11);
        v22 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v22 != &WPP_GLOBAL_Control && (*((_BYTE *)v22 + 28) & 8) != 0 )
      {
        v23 = v22[2];
        v27[0] = a3;
        v27[1] = v21;
        WPP_SF__HEX_(v23, 11, WPP_372720a491483449580c10019a44365b_Traceguids, v27);
      }
    }
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180056bc8  mov     [rsp-8+arg_8], rbx
0x180056bcd  mov     [rsp-8+arg_10], rsi
0x180056bd2  push    rbp
0x180056bd3  push    rdi
0x180056bd4  push    r13
0x180056bd6  push    r14
0x180056bd8  push    r15
0x180056bda  lea     rbp, [rsp-1Fh]
0x180056bdf  sub     rsp, 0A0h
0x180056be6  mov     r13, rcx
0x180056be9  mov     rsi, r9
0x180056bec  xor     ecx, ecx
0x180056bee  mov     rdi, r8
0x180056bf1  mov     [rbp+3Fh+var_80], rcx
0x180056bf5  mov     [rbp+3Fh+arg_0], rcx
0x180056bf9  test    r13, r13
0x180056bfc  jz      loc_180056DA9
0x180056c02  test    r8, r8
0x180056c05  jz      loc_180056DA9
0x180056c0b  mov     rbx, [rbp+3Fh+arg_30]
0x180056c0f  test    rbx, rbx
0x180056c12  jz      loc_180056DA9
0x180056c18  cmp     r9, 7FFFFFF0h
0x180056c1f  jbe     short loc_180056C37
0x180056c21  mov     r14d, 80093104h
0x180056c27  mov     r9d, 0CFh
0x180056c2d  mov     ecx, 80093104h
0x180056c32  jmp     loc_180056DBA
0x180056c37  lea     rax, [r8+r9]
0x180056c3b  xorps   xmm0, xmm0
0x180056c3e  lea     r15, [r13+40h]
0x180056c42  mov     [rbp+3Fh+var_48], rax
0x180056c46  movdqa  [rbp+3Fh+var_30], xmm0
0x180056c4b  mov     [rbp+3Fh+var_60], rdi
0x180056c4f  mov     [rbp+3Fh+var_50], rdi
0x180056c53  mov     [rbp+3Fh+var_58], rsi
0x180056c57  mov     [rbp+3Fh+var_40], rcx
0x180056c5b  mov     [rbp+3Fh+var_38], rcx
0x180056c5f  cmp     [rbp+3Fh+arg_28], rcx
0x180056c63  jnz     short loc_180056C6A
0x180056c65  mov     r14, rcx
0x180056c68  jmp     short loc_180056CB0
0x180056c6a  mov     rax, [r15]
0x180056c6d  mov     r14, [rbx]
0x180056c70  mov     ecx, [rax+4]
0x180056c73  cmp     r14, rcx
0x180056c76  jnb     short loc_180056C8E
0x180056c78  mov     r14d, 80090028h
0x180056c7e  mov     r9d, 0EAh
0x180056c84  mov     ecx, 80090028h
0x180056c89  jmp     loc_180056DBA
0x180056c8e  mov     rcx, [rbp+3Fh+arg_28]; void *
0x180056c92  mov     r8, r14; Size
0x180056c95  xor     edx, edx; Val
0x180056c97  call    memset_0
0x180056c9c  mov     rcx, [r15]
0x180056c9f  mov     eax, [rcx+4]
0x180056ca2  add     rax, [rbp+3Fh+arg_28]
0x180056ca6  mov     [rbp+3Fh+var_80], rax
0x180056caa  mov     eax, [rcx+4]
0x180056cad  sub     r14, rax
0x180056cb0  mov     rax, [r15]
0x180056cb3  lea     rcx, [rbp+3Fh+arg_0]
0x180056cb7  mov     r9, [rbp+3Fh+arg_28]
0x180056cbb  lea     rdx, [rbp+3Fh+var_60]
0x180056cbf  mov     [rsp+0C0h+var_98], rcx
0x180056cc4  xor     r8d, r8d
0x180056cc7  lea     rcx, [rbp+3Fh+var_80]
0x180056ccb  mov     [rbp+3Fh+arg_0], r14
0x180056ccf  mov     rax, [rax+10h]
0x180056cd3  mov     [rsp+0C0h+var_A0], rcx
0x180056cd8  mov     rcx, r13
0x180056cdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056ce0  mov     r14d, eax
0x180056ce3  test    eax, eax
0x180056ce5  jns     loc_180056D6C
0x180056ceb  mov     eax, 100h
0x180056cf0  mov     rbx, rsi
0x180056cf3  cmp     rsi, rax
0x180056cf6  cmovnb  rbx, rax
0x180056cfa  mov     rcx, cs:WPP_GLOBAL_Control
0x180056d01  lea     r15, WPP_GLOBAL_Control
0x180056d08  cmp     rcx, r15
0x180056d0b  jz      loc_180056DC6
0x180056d11  test    byte ptr [rcx+1Ch], 1
0x180056d15  jz      short loc_180056D3A
0x180056d17  mov     r9, [r13+0]
0x180056d1b  mov     rcx, [rcx+10h]
0x180056d1f  mov     [rsp+0C0h+var_90], r14d
0x180056d24  mov     [rsp+0C0h+var_98], rsi
0x180056d29  mov     [rsp+0C0h+var_A0], rdi
0x180056d2e  call    WPP_SF_sqPD
0x180056d33  mov     rcx, cs:WPP_GLOBAL_Control
0x180056d3a  cmp     rcx, r15
0x180056d3d  jz      loc_180056DC6
0x180056d43  test    byte ptr [rcx+1Ch], 8
0x180056d47  jz      short loc_180056DC6
0x180056d49  mov     rcx, [rcx+10h]
0x180056d4d  lea     r9, [rbp+3Fh+var_70]
0x180056d51  mov     edx, 0Bh
0x180056d56  mov     [rbp+3Fh+var_70], rdi
0x180056d5a  lea     r8, WPP_372720a491483449580c10019a44365b_Traceguids
0x180056d61  mov     [rbp+3Fh+var_68], rbx
0x180056d65  call    WPP_SF__HEX_
0x180056d6a  jmp     short loc_180056DC6
0x180056d6c  cmp     [rbp+3Fh+arg_28], 0
0x180056d71  jnz     short loc_180056D8C
0x180056d73  mov     rdx, [rbp+3Fh+arg_0]
0x180056d77  mov     rax, [r15]
0x180056d7a  neg     rdx
0x180056d7d  mov     [rbp+3Fh+arg_0], rdx
0x180056d81  mov     ecx, [rax+4]
0x180056d84  add     rcx, rdx
0x180056d87  mov     [rbx], rcx
0x180056d8a  jmp     short loc_180056D93
0x180056d8c  mov     rax, [rbp+3Fh+arg_0]
0x180056d90  sub     [rbx], rax
0x180056d93  mov     rcx, [rbp+3Fh+arg_20]
0x180056d97  test    rcx, rcx
0x180056d9a  jz      short loc_180056DC6
0x180056d9c  mov     rax, [rbp+3Fh+var_50]
0x180056da0  sub     rax, [rbp+3Fh+var_60]
0x180056da4  mov     [rcx], rax
0x180056da7  jmp     short loc_180056DC6
0x180056da9  mov     r14d, 80090027h
0x180056daf  mov     r9d, 0C8h
0x180056db5  mov     ecx, 80090027h
0x180056dba  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\asn1\\ntasn1\\nt"...
0x180056dc1  call    DebugTraceError
0x180056dc6  lea     r11, [rsp+0C0h+var_20]
0x180056dce  mov     eax, r14d
0x180056dd1  mov     rbx, [r11+38h]
0x180056dd5  mov     rsi, [r11+40h]
0x180056dd9  mov     rsp, r11
0x180056ddc  pop     r15
0x180056dde  pop     r14
0x180056de0  pop     r13
0x180056de2  pop     rdi
0x180056de3  pop     rbp
0x180056de4  retn
```
