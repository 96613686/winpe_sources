# VBSAttestationSerializeRootHeader(_NCRYPT_VBS_ROOT_ATTESTATION_HEADER *,uchar *,ulong *)

- ea: `0x140037bec`
- end: `0x140037e8a`
- name: `?VBSAttestationSerializeRootHeader@@YAJPEAU_NCRYPT_VBS_ROOT_ATTESTATION_HEADER@@PEAEPEAK@Z`
- size: `670`
- prototype: `__int64 __fastcall(struct _NCRYPT_VBS_ROOT_ATTESTATION_HEADER *, unsigned __int8 *, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140037edc`

## callees

- `0x140003ad6`
- `0x140037b10`
- `0x140037bec`
- `0x140037e90`
- `0x140038074`
- `0x140038b40`

## string_xrefs

- `0x140037e64`: `onecore\ds\security\cryptoapi\ncrypt\common\vbsattestation\serialization.cxx`

## pseudocode

```c
__int64 __fastcall VBSAttestationSerializeRootHeader(
        struct _NCRYPT_VBS_ROOT_ATTESTATION_HEADER *a1,
        unsigned __int8 *a2,
        unsigned int *a3)
{
  char *v6; // r12
  int v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // r8
  __int64 v10; // rcx
  unsigned int v11; // ecx
  _DWORD *v12; // r14
  __int64 v13; // rax
  int v14; // r15d
  int v15; // ecx
  unsigned int *v16; // r15
  unsigned int v17; // eax
  unsigned int *v18; // r13
  _DWORD *v19; // rdi
  char *v20; // rdi
  char *v21; // rsi
  __int64 v22; // rax
  struct tag_VSM_SK_REPORT *Src; // [rsp+20h] [rbp-10h]
  unsigned int v25; // [rsp+70h] [rbp+40h] BYREF
  _DWORD *v26; // [rsp+78h] [rbp+48h] BYREF
  unsigned __int64 v27; // [rsp+88h] [rbp+58h] BYREF

  v26 = a2;
  v25 = 0;
  v27 = 0;
  if ( !a1 || !a3 )
  {
    v8 = -2146893819;
    v9 = 403;
    goto LABEL_40;
  }
  v6 = (char *)a1 + 24;
  v7 = VBSAttestationSerializeClaimAttributes((__int64)a1 + 24, 0, &v25);
  v8 = v7;
  if ( v7 < 0 )
  {
    v9 = 421;
LABEL_5:
    v10 = (unsigned int)v7;
LABEL_41:
    VBS_ATTEST_TRACE_ERROR_IN(
      v10,
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\vbsattestation\\serialization.cxx",
      v9);
    return v8;
  }
  v11 = v25 + 24;
  if ( v25 + 24 < v25 )
  {
    v10 = 3221225621LL;
    v9 = 427;
    v8 = -1073741675;
    goto LABEL_41;
  }
  v12 = (_DWORD *)((char *)a1 + 12);
  v13 = *((unsigned int *)a1 + 3);
  v14 = v13 + v11;
  if ( (unsigned int)v13 + v11 < (unsigned int)v13 )
  {
    v10 = 3221225621LL;
    v9 = 434;
    v8 = -1073741675;
    goto LABEL_41;
  }
  Src = (struct tag_VSM_SK_REPORT *)&v6[v13 + *((unsigned int *)a1 + 2)];
  v7 = SerializeVsmSKReport(Src, *((unsigned int *)a1 + 4), &v27, 0);
  v8 = v7;
  if ( v7 < 0 )
  {
    v9 = 447;
    goto LABEL_5;
  }
  if ( v27 >= 0xFFFFFFFF )
  {
    v8 = -1073741595;
    v9 = 453;
LABEL_40:
    v10 = v8;
    goto LABEL_41;
  }
  v15 = v14 + v27;
  if ( v14 + (int)v27 < (unsigned int)v27 )
  {
    v10 = 3221225621LL;
    v9 = 459;
    v8 = -1073741675;
    goto LABEL_41;
  }
  v16 = (unsigned int *)((char *)a1 + 20);
  v17 = *((_DWORD *)a1 + 5);
  if ( v17 + v15 < v17 )
  {
    v10 = 3221225621LL;
    v9 = 466;
    v8 = -1073741675;
    goto LABEL_41;
  }
  v8 = 0;
  *a3 = v17 + v15;
  if ( a2 )
  {
    if ( (int)CopyULONGAdvanceDest(&v26, a1) < 0 )
    {
      v9 = 483;
LABEL_21:
      v10 = 3221225701LL;
      goto LABEL_41;
    }
    if ( (int)CopyULONGAdvanceDest(&v26, (_DWORD *)a1 + 1) < 0 )
    {
      v9 = 488;
      goto LABEL_21;
    }
    if ( (int)CopyULONGAdvanceDest(&v26, &v25) < 0 )
    {
      v9 = 493;
      goto LABEL_21;
    }
    if ( (int)CopyULONGAdvanceDest(&v26, (_DWORD *)a1 + 3) < 0 )
    {
      v9 = 498;
      goto LABEL_21;
    }
    v18 = (unsigned int *)((char *)a1 + 16);
    if ( (int)CopyULONGAdvanceDest(&v26, (_DWORD *)a1 + 4) < 0 )
    {
      v9 = 503;
      goto LABEL_21;
    }
    if ( (int)CopyULONGAdvanceDest(&v26, (_DWORD *)a1 + 5) < 0 )
    {
      v9 = 508;
      goto LABEL_21;
    }
    v19 = v26;
    v7 = VBSAttestationSerializeClaimAttributes((__int64)v6, v26, &v25);
    v8 = v7;
    if ( v7 < 0 )
    {
      v9 = 521;
      goto LABEL_5;
    }
    v20 = (char *)v19 + v25;
    v21 = &v6[*((unsigned int *)a1 + 2)];
    if ( *v12 )
    {
      memcpy_0(v20, v21, (unsigned int)*v12);
      v22 = (unsigned int)*v12;
      v20 += v22;
      v21 += v22;
    }
    v7 = SerializeVsmSKReport(Src, *v18, &v27, (unsigned __int8 *)v20);
    v8 = v7;
    if ( v7 < 0 )
    {
      v9 = 548;
      goto LABEL_5;
    }
    memcpy_0(&v20[v27], &v21[*v18], *v16);
    return 0;
  }
  return v8;
}

```

## disassembly

```asm
0x140037bec  mov     [rsp-38h+arg_10], rbx
0x140037bf1  mov     [rsp-38h+arg_8], rdx
0x140037bf6  push    rbp
0x140037bf7  push    rsi
0x140037bf8  push    rdi
0x140037bf9  push    r12
0x140037bfb  push    r13
0x140037bfd  push    r14
0x140037bff  push    r15
0x140037c01  mov     rbp, rsp
0x140037c04  sub     rsp, 30h
0x140037c08  mov     [rbp+arg_0], 0
0x140037c0f  mov     rdi, r8
0x140037c12  mov     [rbp+arg_18], 0
0x140037c1a  mov     r13, rdx
0x140037c1d  mov     rsi, rcx
0x140037c20  test    rcx, rcx
0x140037c23  jz      loc_140037E57
0x140037c29  test    r8, r8
0x140037c2c  jz      loc_140037E57
0x140037c32  lea     r12, [rcx+18h]
0x140037c36  xor     edx, edx
0x140037c38  mov     rcx, r12
0x140037c3b  lea     r8, [rbp+arg_0]
0x140037c3f  call    VBSAttestationSerializeClaimAttributes
0x140037c44  mov     ebx, eax
0x140037c46  test    eax, eax
0x140037c48  jns     short loc_140037C57
0x140037c4a  mov     r8d, 1A5h
0x140037c50  mov     ecx, eax
0x140037c52  jmp     loc_140037E64
0x140037c57  mov     eax, [rbp+arg_0]
0x140037c5a  lea     ecx, [rax+18h]
0x140037c5d  cmp     ecx, eax
0x140037c5f  jnb     short loc_140037C73
0x140037c61  mov     ecx, 0C0000095h
0x140037c66  mov     r8d, 1ABh
0x140037c6c  mov     ebx, ecx
0x140037c6e  jmp     loc_140037E64
0x140037c73  lea     r14, [rsi+0Ch]
0x140037c77  mov     eax, [r14]
0x140037c7a  lea     r15d, [rax+rcx]
0x140037c7e  cmp     r15d, eax
0x140037c81  jnb     short loc_140037C95
0x140037c83  mov     ecx, 0C0000095h
0x140037c88  mov     r8d, 1B2h
0x140037c8e  mov     ebx, ecx
0x140037c90  jmp     loc_140037E64
0x140037c95  mov     ecx, [rsi+8]
0x140037c98  lea     r8, [rbp+arg_18]; unsigned __int64 *
0x140037c9c  mov     edx, [rsi+10h]; Size
0x140037c9f  add     rax, r12
0x140037ca2  add     rax, rcx
0x140037ca5  xor     r9d, r9d; unsigned __int8 *
0x140037ca8  mov     rcx, rax; Src
0x140037cab  mov     [rbp+Src], rax
0x140037caf  call    ?SerializeVsmSKReport@@YAJPEAUtag_VSM_SK_REPORT@@_KPEA_KPEAE@Z; SerializeVsmSKReport(tag_VSM_SK_REPORT *,unsigned __int64,unsigned __int64 *,uchar *)
0x140037cb4  mov     ebx, eax
0x140037cb6  test    eax, eax
0x140037cb8  jns     short loc_140037CC2
0x140037cba  mov     r8d, 1BFh
0x140037cc0  jmp     short loc_140037C50
0x140037cc2  mov     rax, [rbp+arg_18]
0x140037cc6  mov     ecx, 0FFFFFFFFh
0x140037ccb  cmp     rax, rcx
0x140037cce  jb      short loc_140037CE0
0x140037cd0  mov     ebx, 0C00000E5h
0x140037cd5  mov     r8d, 1C5h
0x140037cdb  jmp     loc_140037E62
0x140037ce0  lea     ecx, [r15+rax]
0x140037ce4  cmp     ecx, eax
0x140037ce6  jnb     short loc_140037CFA
0x140037ce8  mov     ecx, 0C0000095h
0x140037ced  mov     r8d, 1CBh
0x140037cf3  mov     ebx, ecx
0x140037cf5  jmp     loc_140037E64
0x140037cfa  lea     r15, [rsi+14h]
0x140037cfe  mov     eax, [r15]
0x140037d01  lea     edx, [rax+rcx]
0x140037d04  cmp     edx, eax
0x140037d06  jnb     short loc_140037D1A
0x140037d08  mov     ecx, 0C0000095h
0x140037d0d  mov     r8d, 1D2h
0x140037d13  mov     ebx, ecx
0x140037d15  jmp     loc_140037E64
0x140037d1a  xor     ebx, ebx
0x140037d1c  mov     [rdi], edx
0x140037d1e  test    r13, r13
0x140037d21  jz      loc_140037E70
0x140037d27  mov     rdx, rsi
0x140037d2a  lea     rcx, [rbp+arg_8]
0x140037d2e  call    CopyULONGAdvanceDest
0x140037d33  test    eax, eax
0x140037d35  jns     short loc_140037D47
0x140037d37  mov     r8d, 1E3h
0x140037d3d  mov     ecx, 0C00000E5h
0x140037d42  jmp     loc_140037E64
0x140037d47  lea     rdx, [rsi+4]
0x140037d4b  lea     rcx, [rbp+arg_8]
0x140037d4f  call    CopyULONGAdvanceDest
0x140037d54  test    eax, eax
0x140037d56  jns     short loc_140037D60
0x140037d58  mov     r8d, 1E8h
0x140037d5e  jmp     short loc_140037D3D
0x140037d60  lea     rdx, [rbp+arg_0]
0x140037d64  lea     rcx, [rbp+arg_8]
0x140037d68  call    CopyULONGAdvanceDest
0x140037d6d  test    eax, eax
0x140037d6f  jns     short loc_140037D79
0x140037d71  mov     r8d, 1EDh
0x140037d77  jmp     short loc_140037D3D
0x140037d79  mov     rdx, r14
0x140037d7c  lea     rcx, [rbp+arg_8]
0x140037d80  call    CopyULONGAdvanceDest
0x140037d85  test    eax, eax
0x140037d87  jns     short loc_140037D91
0x140037d89  mov     r8d, 1F2h
0x140037d8f  jmp     short loc_140037D3D
0x140037d91  lea     r13, [rsi+10h]
0x140037d95  mov     rdx, r13
0x140037d98  lea     rcx, [rbp+arg_8]
0x140037d9c  call    CopyULONGAdvanceDest
0x140037da1  test    eax, eax
0x140037da3  jns     short loc_140037DAD
0x140037da5  mov     r8d, 1F7h
0x140037dab  jmp     short loc_140037D3D
0x140037dad  mov     rdx, r15
0x140037db0  lea     rcx, [rbp+arg_8]
0x140037db4  call    CopyULONGAdvanceDest
0x140037db9  test    eax, eax
0x140037dbb  jns     short loc_140037DC8
0x140037dbd  mov     r8d, 1FCh
0x140037dc3  jmp     loc_140037D3D
0x140037dc8  mov     rdi, [rbp+arg_8]
0x140037dcc  lea     r8, [rbp+arg_0]
0x140037dd0  mov     rdx, rdi
0x140037dd3  mov     rcx, r12
0x140037dd6  call    VBSAttestationSerializeClaimAttributes
0x140037ddb  mov     ebx, eax
0x140037ddd  test    eax, eax
0x140037ddf  jns     short loc_140037DEC
0x140037de1  mov     r8d, 209h
0x140037de7  jmp     loc_140037C50
0x140037dec  mov     eax, [rbp+arg_0]
0x140037def  mov     esi, [rsi+8]
0x140037df2  add     rdi, rax
0x140037df5  add     rsi, r12
0x140037df8  cmp     dword ptr [r14], 0
0x140037dfc  jbe     short loc_140037E15
0x140037dfe  mov     r8d, [r14]; Size
0x140037e01  mov     rdx, rsi; Src
0x140037e04  mov     rcx, rdi; void *
0x140037e07  call    memcpy_0
0x140037e0c  mov     eax, [r14]
0x140037e0f  add     rdi, rax
0x140037e12  add     rsi, rax
0x140037e15  mov     edx, [r13+0]; Size
0x140037e19  lea     r8, [rbp+arg_18]; unsigned __int64 *
0x140037e1d  mov     rcx, [rbp+Src]; Src
0x140037e21  mov     r9, rdi; unsigned __int8 *
0x140037e24  mov     r14, rdi
0x140037e27  call    ?SerializeVsmSKReport@@YAJPEAUtag_VSM_SK_REPORT@@_KPEA_KPEAE@Z; SerializeVsmSKReport(tag_VSM_SK_REPORT *,unsigned __int64,unsigned __int64 *,uchar *)
0x140037e2c  mov     ebx, eax
0x140037e2e  test    eax, eax
0x140037e30  jns     short loc_140037E3D
0x140037e32  mov     r8d, 224h
0x140037e38  jmp     loc_140037C50
0x140037e3d  mov     edx, [r13+0]
0x140037e41  mov     rcx, [rbp+arg_18]
0x140037e45  add     rdx, rsi; Src
0x140037e48  mov     r8d, [r15]; Size
0x140037e4b  add     rcx, r14; void *
0x140037e4e  call    memcpy_0
0x140037e53  xor     ebx, ebx
0x140037e55  jmp     short loc_140037E70
0x140037e57  mov     ebx, 80090005h
0x140037e5c  mov     r8d, 193h
0x140037e62  mov     ecx, ebx
0x140037e64  lea     rdx, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x140037e6b  call    VBS_ATTEST_TRACE_ERROR_IN
0x140037e70  mov     eax, ebx
0x140037e72  mov     rbx, [rsp+30h+arg_10]
0x140037e7a  add     rsp, 30h
0x140037e7e  pop     r15
0x140037e80  pop     r14
0x140037e82  pop     r13
0x140037e84  pop     r12
0x140037e86  pop     rdi
0x140037e87  pop     rsi
0x140037e88  pop     rbp
0x140037e89  retn
```
