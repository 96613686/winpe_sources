# CMpeg2PSIParse::ProcessBuffer_(uchar * *,int *,CTStickyVal<int> *)

- ea: `0x180029b4c`
- end: `0x180029f55`
- name: `?ProcessBuffer_@CMpeg2PSIParse@@AEAAHPEAPEAEPEAHPEAV?$CTStickyVal@H@@@Z`
- size: `1033`
- prototype: `__int64 __fastcall(CCopyFrameParser *this)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18002a7e0`

## callees

- `0x180028b18`
- `0x180028dc4`
- `0x180028fd8`
- `0x180029270`
- `0x180029b4c`
- `0x180034010`

## pseudocode

```c
__int64 __fastcall CMpeg2PSIParse::ProcessBuffer_(CCopyFrameParser *this, struct IMediaSample *a2, int *a3, _DWORD *a4)
{
  unsigned int v4; // esi
  int v6; // ecx
  _DWORD *v7; // r15
  int v10; // r13d
  int v11; // ecx
  int v12; // ecx
  int *v13; // r14
  __int64 v14; // r8
  struct IMediaSample *v15; // rdx
  int v16; // r8d
  unsigned __int8 *v17; // rdx
  __int64 v18; // rcx
  int v20; // edx
  int v21; // edx
  int v22; // ecx
  int v23; // r15d
  unsigned __int8 *v24; // rdx
  int v25; // ecx
  __int64 v26; // rdx
  __int64 v27; // rdx
  __int64 v28; // rdx
  int v29; // ecx
  int v30; // r14d
  unsigned __int8 *lpVtbl; // rdx
  bool v32; // zf
  int v33; // ecx
  __int64 v34; // rdx
  __int64 v35; // rbx
  int v36[4]; // [rsp+30h] [rbp-10h] BYREF
  int v37; // [rsp+80h] [rbp+40h] BYREF
  _DWORD *v38; // [rsp+98h] [rbp+58h]

  v38 = a4;
  v4 = 0;
  v6 = *((_DWORD *)this + 101);
  v7 = a4;
  v37 = 0;
  v10 = 1;
  if ( v6 )
  {
    v11 = v6 - 1;
    if ( v11 )
    {
      if ( v11 != 1 )
        return v4;
LABEL_64:
      v30 = *((_DWORD *)this + 99) - *((_DWORD *)this + 100);
      lpVtbl = (unsigned __int8 *)a2->lpVtbl;
      v32 = *((_DWORD *)this + 99) == *((_DWORD *)this + 100);
      v36[0] = 0;
      if ( v30 < 0 || v32 )
        v30 = 0;
      if ( *a3 < v30 )
        v30 = *a3;
      v4 = CBufferSourceManager::CopyBlock((CCopyFrameParser *)((char *)this + 48), lpVtbl, v30, v36);
      if ( v4 )
      {
        *((_DWORD *)this + 100) += v30;
        *a3 -= v30;
        v33 = *((_DWORD *)this + 99) - *((_DWORD *)this + 100);
        a2->lpVtbl = (struct IMediaSampleVtbl *)((char *)a2->lpVtbl + v30);
        if ( v33 <= 0 )
          v33 = 0;
        if ( !v33 )
        {
          v34 = 0;
          if ( *((_QWORD *)this + 17) )
            v34 = *((_QWORD *)this + 17);
          v4 = (*(__int64 (__fastcall **)(CCopyFrameParser *, __int64, _QWORD))(*(_QWORD *)this + 72LL))(
                 this,
                 v34,
                 (unsigned int)(*((_DWORD *)this + 38) - *((_DWORD *)this + 34)));
          if ( v4 )
          {
            v35 = (unsigned int)CBufferSourceManager::Complete((char *)this + 48, v7);
            (*(void (__fastcall **)(CCopyFrameParser *, __int64))(*(_QWORD *)this + 112LL))(this, v35);
            *((_QWORD *)this + 50) = 0;
            *((_DWORD *)this + 99) = 0;
            return (int)v35 >= 0;
          }
        }
        return v4;
      }
LABEL_23:
      CMpeg2PSIParse::AbortPSICollection_(this);
      return v4;
    }
  }
  else
  {
    *((_DWORD *)this + 101) = 1;
  }
  v12 = *((_DWORD *)this + 100);
  v13 = (int *)((char *)this + 392);
  if ( v12 || (v14 = (unsigned int)*v13, *a3 < (int)v14) )
  {
    v23 = *v13 - v12;
    if ( v23 <= 0 )
      v23 = 0;
    if ( *a3 < v23 )
      v23 = *a3;
    if ( v23 > 0 && !v12 && (int)CCopyFrameParser::GetNewFrameBuffer(this, a2) < 0 )
      goto LABEL_23;
    v24 = (unsigned __int8 *)a2->lpVtbl;
    v36[0] = 0;
    v4 = CBufferSourceManager::CopyBlock((CCopyFrameParser *)((char *)this + 48), v24, v23, v36);
    if ( !v4 )
      goto LABEL_23;
    *((_DWORD *)this + 100) += v23;
    *a3 -= v23;
    v25 = *v13 - *((_DWORD *)this + 100);
    a2->lpVtbl = (struct IMediaSampleVtbl *)((char *)a2->lpVtbl + v23);
    if ( v25 <= 0 )
      v25 = 0;
    if ( !v25 )
    {
      v26 = 0;
      if ( *((_QWORD *)this + 17) )
        v26 = *((_QWORD *)this + 17);
      v4 = (*(__int64 (__fastcall **)(CCopyFrameParser *, __int64, _QWORD, char *, int *))(*(_QWORD *)this + 64LL))(
             this,
             v26,
             (unsigned int)*v13,
             (char *)this + 396,
             &v37);
      if ( !v4 )
        goto LABEL_23;
      if ( (*(unsigned int (__fastcall **)(CCopyFrameParser *))(*(_QWORD *)this + 96LL))(this) )
      {
        if ( !v37 )
        {
LABEL_58:
          v20 = *((_DWORD *)this + 99);
          goto LABEL_26;
        }
        v27 = 0;
        if ( *((_QWORD *)this + 17) )
          v27 = *((_QWORD *)this + 17);
        if ( !(*(unsigned int (__fastcall **)(CCopyFrameParser *, __int64, _QWORD))(*(_QWORD *)this + 88LL))(
                this,
                v27,
                (unsigned int)*v13) )
        {
          if ( v38[1] == *v38 )
            v10 = v38[1];
          v38[1] = v10;
        }
      }
      if ( !v37 || !(*(unsigned int (__fastcall **)(CCopyFrameParser *))(*(_QWORD *)this + 80LL))(this) )
        goto LABEL_58;
      v28 = 0;
      if ( *((_QWORD *)this + 17) )
        v28 = *((_QWORD *)this + 17);
      if ( !(*(unsigned int (__fastcall **)(CCopyFrameParser *, __int64, _QWORD))(*(_QWORD *)this + 88LL))(
              this,
              v28,
              (unsigned int)*v13) )
        goto LABEL_58;
    }
    v7 = v38;
    goto LABEL_60;
  }
  v4 = (*(__int64 (__fastcall **)(CCopyFrameParser *, struct IMediaSampleVtbl *, __int64, char *, int *))(*(_QWORD *)this + 64LL))(
         this,
         a2->lpVtbl,
         v14,
         (char *)this + 396,
         &v37);
  if ( !v4 )
    goto LABEL_23;
  if ( (*(unsigned int (__fastcall **)(CCopyFrameParser *))(*(_QWORD *)this + 96LL))(this) )
  {
    if ( !v37 )
    {
LABEL_25:
      v20 = *((_DWORD *)this + 99);
LABEL_26:
      v21 = v20 - *((_DWORD *)this + 100);
      v22 = *a3;
      if ( v21 <= 0 )
        v21 = 0;
      if ( v22 < v21 )
        v21 = *a3;
      a2->lpVtbl = (struct IMediaSampleVtbl *)((char *)a2->lpVtbl + v21);
      *a3 = v22 - v21;
      goto LABEL_23;
    }
    if ( !(*(unsigned int (__fastcall **)(CCopyFrameParser *, struct IMediaSampleVtbl *, _QWORD))(*(_QWORD *)this + 88LL))(
            this,
            a2->lpVtbl,
            (unsigned int)*v13) )
    {
      if ( v7[1] == *v7 )
        v10 = v7[1];
      v7[1] = v10;
    }
  }
  if ( !v37
    || !(*(unsigned int (__fastcall **)(CCopyFrameParser *))(*(_QWORD *)this + 80LL))(this)
    || !(*(unsigned int (__fastcall **)(CCopyFrameParser *, struct IMediaSampleVtbl *, _QWORD))(*(_QWORD *)this + 88LL))(
          this,
          a2->lpVtbl,
          (unsigned int)*v13) )
  {
    goto LABEL_25;
  }
  if ( (int)CCopyFrameParser::GetNewFrameBuffer(this, v15) < 0 )
  {
    v4 = 0;
  }
  else
  {
    v16 = *v13;
    v17 = (unsigned __int8 *)a2->lpVtbl;
    v36[0] = 0;
    v4 = CBufferSourceManager::CopyBlock((CCopyFrameParser *)((char *)this + 48), v17, v16, v36);
    if ( !v4 )
      goto LABEL_23;
    v18 = *v13;
    a2->lpVtbl = (struct IMediaSampleVtbl *)((char *)a2->lpVtbl + v18);
    *a3 -= v18;
    *((_DWORD *)this + 100) = v18;
  }
  if ( !v4 )
    goto LABEL_23;
LABEL_60:
  v29 = *v13 - *((_DWORD *)this + 100);
  if ( v29 <= 0 )
    v29 = 0;
  if ( v29 <= 0 )
  {
    *((_DWORD *)this + 101) = 2;
    goto LABEL_64;
  }
  return v4;
}

```

## disassembly

```asm
0x180029b4c  mov     [rsp-38h+arg_8], rbx
0x180029b51  mov     [rsp-38h+arg_18], r9
0x180029b56  push    rbp
0x180029b57  push    rsi
0x180029b58  push    rdi
0x180029b59  push    r12
0x180029b5b  push    r13
0x180029b5d  push    r14
0x180029b5f  push    r15
0x180029b61  mov     rbp, rsp
0x180029b64  sub     rsp, 40h
0x180029b68  xor     esi, esi
0x180029b6a  mov     rdi, rcx
0x180029b6d  mov     ecx, [rcx+194h]
0x180029b73  mov     r15, r9
0x180029b76  mov     [rbp+arg_0], esi
0x180029b79  mov     r12, r8
0x180029b7c  mov     rbx, rdx
0x180029b7f  lea     r13d, [rsi+1]
0x180029b83  test    ecx, ecx
0x180029b85  jz      short loc_180029B9A
0x180029b87  sub     ecx, r13d
0x180029b8a  jz      short loc_180029BA1
0x180029b8c  cmp     ecx, r13d
0x180029b8f  jz      loc_180029E74
0x180029b95  jmp     loc_180029CBE
0x180029b9a  mov     [rdi+194h], r13d
0x180029ba1  mov     ecx, [rdi+190h]
0x180029ba7  lea     r14, [rdi+188h]
0x180029bae  test    ecx, ecx
0x180029bb0  jnz     loc_180029D02
0x180029bb6  mov     r8d, [r14]
0x180029bb9  cmp     [r12], r8d
0x180029bbd  jl      loc_180029D02
0x180029bc3  mov     rax, [rdi]
0x180029bc6  lea     rdx, [rbp+arg_0]
0x180029bca  mov     [rsp+40h+var_20], rdx
0x180029bcf  lea     r9, [rdi+18Ch]
0x180029bd6  mov     rdx, [rbx]
0x180029bd9  mov     rcx, rdi
0x180029bdc  mov     rax, [rax+40h]
0x180029be0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029be5  mov     esi, eax
0x180029be7  test    eax, eax
0x180029be9  jz      loc_180029CB6
0x180029bef  mov     rcx, [rdi]
0x180029bf2  mov     rax, [rcx+60h]
0x180029bf6  mov     rcx, rdi
0x180029bf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029bfe  test    eax, eax
0x180029c00  jz      short loc_180029C34
0x180029c02  cmp     [rbp+arg_0], 0
0x180029c06  jz      loc_180029CD8
0x180029c0c  mov     rax, [rdi]
0x180029c0f  mov     rcx, rdi
0x180029c12  mov     r8d, [r14]
0x180029c15  mov     rdx, [rbx]
0x180029c18  mov     rax, [rax+58h]
0x180029c1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029c21  test    eax, eax
0x180029c23  jnz     short loc_180029C34
0x180029c25  mov     eax, [r15+4]
0x180029c29  cmp     eax, [r15]
0x180029c2c  cmovz   r13d, eax
0x180029c30  mov     [r15+4], r13d
0x180029c34  cmp     [rbp+arg_0], 0
0x180029c38  jz      loc_180029CD8
0x180029c3e  mov     rax, [rdi]
0x180029c41  mov     rcx, rdi
0x180029c44  mov     rax, [rax+50h]
0x180029c48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029c4d  test    eax, eax
0x180029c4f  jz      loc_180029CD8
0x180029c55  mov     rax, [rdi]
0x180029c58  mov     rcx, rdi
0x180029c5b  mov     r8d, [r14]
0x180029c5e  mov     rdx, [rbx]
0x180029c61  mov     rax, [rax+58h]
0x180029c65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029c6a  test    eax, eax
0x180029c6c  jz      short loc_180029CD8
0x180029c6e  mov     rcx, rdi; this
0x180029c71  call    ?GetNewFrameBuffer@CCopyFrameParser@@IEAAJPEAUIMediaSample@@@Z; CCopyFrameParser::GetNewFrameBuffer(IMediaSample *)
0x180029c76  test    eax, eax
0x180029c78  js      short loc_180029CAC
0x180029c7a  mov     r8d, [r14]; int
0x180029c7d  lea     rcx, [rdi+30h]; this
0x180029c81  mov     rdx, [rbx]; unsigned __int8 *
0x180029c84  lea     r9, [rbp+var_10]; int *
0x180029c88  mov     [rbp+var_10], 0
0x180029c8f  call    ?CopyBlock@CBufferSourceManager@@IEAAHPEAEHPEAH@Z; CBufferSourceManager::CopyBlock(uchar *,int,int *)
0x180029c94  mov     esi, eax
0x180029c96  test    eax, eax
0x180029c98  jz      short loc_180029CB6
0x180029c9a  movsxd  rcx, dword ptr [r14]
0x180029c9d  add     [rbx], rcx
0x180029ca0  sub     [r12], ecx
0x180029ca4  mov     [rdi+190h], ecx
0x180029caa  jmp     short loc_180029CAE
0x180029cac  xor     esi, esi
0x180029cae  test    esi, esi
0x180029cb0  jnz     loc_180029E52
0x180029cb6  mov     rcx, rdi; this
0x180029cb9  call    ?AbortPSICollection_@CMpeg2PSIParse@@AEAAXXZ; CMpeg2PSIParse::AbortPSICollection_(void)
0x180029cbe  mov     rbx, [rsp+40h+arg_8]
0x180029cc6  mov     eax, esi
0x180029cc8  add     rsp, 40h
0x180029ccc  pop     r15
0x180029cce  pop     r14
0x180029cd0  pop     r13
0x180029cd2  pop     r12
0x180029cd4  pop     rdi
0x180029cd5  pop     rsi
0x180029cd6  pop     rbp
0x180029cd7  retn
0x180029cd8  mov     edx, [rdi+18Ch]
0x180029cde  sub     edx, [rdi+190h]
0x180029ce4  xor     eax, eax
0x180029ce6  mov     ecx, [r12]
0x180029cea  test    edx, edx
0x180029cec  cmovle  edx, eax
0x180029cef  cmp     ecx, edx
0x180029cf1  cmovl   edx, ecx; struct IMediaSample *
0x180029cf4  movsxd  rax, edx
0x180029cf7  add     [rbx], rax
0x180029cfa  sub     ecx, edx
0x180029cfc  mov     [r12], ecx
0x180029d00  jmp     short loc_180029CB6
0x180029d02  mov     r15d, [r14]
0x180029d05  xor     eax, eax
0x180029d07  sub     r15d, ecx
0x180029d0a  test    r15d, r15d
0x180029d0d  cmovle  r15d, eax
0x180029d11  cmp     [r12], r15d
0x180029d15  cmovl   r15d, [r12]
0x180029d1a  test    r15d, r15d
0x180029d1d  jle     short loc_180029D2F
0x180029d1f  test    ecx, ecx
0x180029d21  jnz     short loc_180029D2F
0x180029d23  mov     rcx, rdi; this
0x180029d26  call    ?GetNewFrameBuffer@CCopyFrameParser@@IEAAJPEAUIMediaSample@@@Z; CCopyFrameParser::GetNewFrameBuffer(IMediaSample *)
0x180029d2b  test    eax, eax
0x180029d2d  js      short loc_180029CB6
0x180029d2f  mov     rdx, [rbx]; unsigned __int8 *
0x180029d32  lea     rcx, [rdi+30h]; this
0x180029d36  lea     r9, [rbp+var_10]; int *
0x180029d3a  mov     [rbp+var_10], esi
0x180029d3d  mov     r8d, r15d; int
0x180029d40  call    ?CopyBlock@CBufferSourceManager@@IEAAHPEAEHPEAH@Z; CBufferSourceManager::CopyBlock(uchar *,int,int *)
0x180029d45  mov     esi, eax
0x180029d47  test    eax, eax
0x180029d49  jz      loc_180029CB6
0x180029d4f  add     [rdi+190h], r15d
0x180029d56  sub     [r12], r15d
0x180029d5a  mov     ecx, [r14]
0x180029d5d  sub     ecx, [rdi+190h]
0x180029d63  movsxd  rax, r15d
0x180029d66  add     [rbx], rax
0x180029d69  xor     eax, eax
0x180029d6b  test    ecx, ecx
0x180029d6d  cmovle  ecx, eax
0x180029d70  test    ecx, ecx
0x180029d72  jnz     loc_180029E4E
0x180029d78  mov     rcx, [rdi+88h]
0x180029d7f  lea     r15, [rdi+18Ch]
0x180029d86  mov     rax, [rdi]
0x180029d89  xor     edx, edx
0x180029d8b  mov     r8d, [r14]
0x180029d8e  test    rcx, rcx
0x180029d91  mov     r9, r15
0x180029d94  cmovnz  rdx, rcx
0x180029d98  lea     rcx, [rbp+arg_0]
0x180029d9c  mov     rax, [rax+40h]
0x180029da0  mov     [rsp+40h+var_20], rcx
0x180029da5  mov     rcx, rdi
0x180029da8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029dad  mov     esi, eax
0x180029daf  test    eax, eax
0x180029db1  jz      loc_180029CB6
0x180029db7  mov     rax, [rdi]
0x180029dba  mov     rcx, rdi
0x180029dbd  mov     rax, [rax+60h]
0x180029dc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029dc6  test    eax, eax
0x180029dc8  jz      short loc_180029E07
0x180029dca  cmp     [rbp+arg_0], 0
0x180029dce  jz      short loc_180029E46
0x180029dd0  mov     rcx, [rdi+88h]
0x180029dd7  xor     edx, edx
0x180029dd9  mov     rax, [rdi]
0x180029ddc  test    rcx, rcx
0x180029ddf  mov     r8d, [r14]
0x180029de2  cmovnz  rdx, rcx
0x180029de6  mov     rcx, rdi
0x180029de9  mov     rax, [rax+58h]
0x180029ded  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029df2  test    eax, eax
0x180029df4  jnz     short loc_180029E07
0x180029df6  mov     rcx, [rbp+arg_18]
0x180029dfa  mov     eax, [rcx+4]
0x180029dfd  cmp     eax, [rcx]
0x180029dff  cmovz   r13d, eax
0x180029e03  mov     [rcx+4], r13d
0x180029e07  cmp     [rbp+arg_0], 0
0x180029e0b  jz      short loc_180029E46
0x180029e0d  mov     rax, [rdi]
0x180029e10  mov     rcx, rdi
0x180029e13  mov     rax, [rax+50h]
0x180029e17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029e1c  test    eax, eax
0x180029e1e  jz      short loc_180029E46
0x180029e20  mov     rcx, [rdi+88h]
0x180029e27  xor     edx, edx
0x180029e29  mov     rax, [rdi]
0x180029e2c  test    rcx, rcx
0x180029e2f  mov     r8d, [r14]
0x180029e32  cmovnz  rdx, rcx
0x180029e36  mov     rcx, rdi
0x180029e39  mov     rax, [rax+58h]
0x180029e3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029e42  test    eax, eax
0x180029e44  jnz     short loc_180029E4E
0x180029e46  mov     edx, [r15]
0x180029e49  jmp     loc_180029CDE
0x180029e4e  mov     r15, [rbp+arg_18]
0x180029e52  mov     ecx, [r14]
0x180029e55  xor     eax, eax
0x180029e57  sub     ecx, [rdi+190h]
0x180029e5d  test    ecx, ecx
0x180029e5f  cmovle  ecx, eax
0x180029e62  test    ecx, ecx
0x180029e64  jg      loc_180029CBE
0x180029e6a  mov     dword ptr [rdi+194h], 2
0x180029e74  mov     r14d, [rdi+18Ch]
0x180029e7b  lea     r9, [rbp+var_10]; int *
0x180029e7f  sub     r14d, [rdi+190h]
0x180029e86  lea     rcx, [rdi+30h]; this
0x180029e8a  mov     rdx, [rbx]; unsigned __int8 *
0x180029e8d  xor     eax, eax
0x180029e8f  test    r14d, r14d
0x180029e92  mov     [rbp+var_10], eax
0x180029e95  cmovle  r14d, eax
0x180029e99  cmp     [r12], r14d
0x180029e9d  cmovl   r14d, [r12]
0x180029ea2  mov     r8d, r14d; int
0x180029ea5  call    ?CopyBlock@CBufferSourceManager@@IEAAHPEAEHPEAH@Z; CBufferSourceManager::CopyBlock(uchar *,int,int *)
0x180029eaa  mov     esi, eax
0x180029eac  test    eax, eax
0x180029eae  jz      loc_180029CB6
0x180029eb4  add     [rdi+190h], r14d
0x180029ebb  sub     [r12], r14d
0x180029ebf  mov     ecx, [rdi+18Ch]
0x180029ec5  sub     ecx, [rdi+190h]
0x180029ecb  movsxd  rax, r14d
0x180029ece  xor     r14d, r14d
0x180029ed1  add     [rbx], rax
0x180029ed4  test    ecx, ecx
0x180029ed6  cmovle  ecx, r14d
0x180029eda  test    ecx, ecx
0x180029edc  jnz     loc_180029CBE
0x180029ee2  mov     r9, [rdi+88h]
0x180029ee9  mov     edx, r14d
0x180029eec  mov     r8d, [rdi+98h]
0x180029ef3  mov     rcx, rdi
0x180029ef6  sub     r8d, [rdi+88h]
0x180029efd  mov     rax, [rdi]
0x180029f00  test    r9, r9
0x180029f03  cmovnz  rdx, r9
0x180029f07  mov     rax, [rax+48h]
0x180029f0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029f10  mov     esi, eax
0x180029f12  test    eax, eax
0x180029f14  jz      loc_180029CBE
0x180029f1a  mov     rdx, r15
0x180029f1d  lea     rcx, [rdi+30h]
0x180029f21  call    ?Complete@CBufferSourceManager@@IEAAJPEAV?$CTStickyVal@H@@@Z; CBufferSourceManager::Complete(CTStickyVal<int> *)
0x180029f26  mov     rcx, [rdi]
0x180029f29  mov     ebx, eax
0x180029f2b  mov     edx, ebx
0x180029f2d  mov     rax, [rcx+70h]
0x180029f31  mov     rcx, rdi
0x180029f34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029f39  test    ebx, ebx
0x180029f3b  mov     [rdi+190h], r14
0x180029f42  mov     esi, r14d
0x180029f45  mov     [rdi+18Ch], r14d
0x180029f4c  setns   sil
0x180029f50  jmp     loc_180029CBE
```
