# CMpeg2SCRParser::ProcessSysBuffer(IMediaSample *,MPEG2_SYS_BUFFER *,int,int,int,int,int,CTStickyVal<int> *)

- ea: `0x18002a9a0`
- end: `0x18002accc`
- name: `?ProcessSysBuffer@CMpeg2SCRParser@@UEAAJPEAUIMediaSample@@PEAUMPEG2_SYS_BUFFER@@HHHHHPEAV?$CTStickyVal@H@@@Z`
- size: `812`
- prototype: `__int64 __usercall@<rax>(CCopyFrameParser *this@<rcx>, int, int, int, int, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180028a7c`
- `0x180028dc4`
- `0x180028fd8`
- `0x180029270`
- `0x18002a9a0`
- `0x180033dfd`

## pseudocode

```c
__int64 __fastcall CMpeg2SCRParser::ProcessSysBuffer(
        CCopyFrameParser *this,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        int a6,
        int a7)
{
  int v7; // edx
  int v10; // ecx
  BOOL v11; // edi
  char *v12; // rcx
  char *v13; // rdx
  unsigned __int64 v14; // rdx
  unsigned __int64 v15; // rcx
  unsigned __int64 v16; // r8
  unsigned __int64 v17; // rcx
  __int64 v18; // rax
  unsigned __int64 v19; // rsi
  size_t v20; // rsi
  __int64 v21; // r8
  unsigned __int64 v22; // rcx
  int NewFrameBuffer; // edi
  int v24; // ecx
  int v25; // eax
  CBufferSourceManager *v26; // rcx
  unsigned __int8 v28[16]; // [rsp+20h] [rbp-38h] BYREF

  v7 = a7;
  *(_OWORD *)v28 = 0;
  if ( a5 || a7 )
    *((_DWORD *)this + 112) = 0;
  v10 = *((_DWORD *)this + 112);
  v11 = 1;
  if ( v10 )
  {
    if ( v10 != 1 )
      return !v11 ? 0x80004005 : 0;
  }
  else
  {
    if ( !v7 )
      return !v11 ? 0x80004005 : 0;
    *((_QWORD *)this + 52) = *((_QWORD *)this + 51);
    *((_DWORD *)this + 112) = 1;
  }
  v12 = (char *)*((_QWORD *)this + 52);
  v13 = &v12[-*((_QWORD *)this + 51)];
  if ( !v13 )
  {
    if ( *(int *)(a3 + 8) < 10 )
    {
      v19 = *(int *)(a3 + 8);
      if ( v19 >= (unsigned __int64)&v12[v19] || v19 > *((_QWORD *)this + 53) )
      {
        v11 = 0;
      }
      else
      {
        memcpy_0(v12, *(const void **)a3, *(int *)(a3 + 8));
        *((_QWORD *)this + 52) += v19;
      }
      goto LABEL_27;
    }
    v14 = *(_QWORD *)a3;
    v15 = *(_QWORD *)(*(_QWORD *)a3 + 1LL);
    v16 = (8 * (v15 & 0x38000000 | (2 * (v15 & 0x3000000))))
        | ((v15 & 0xFF00000000LL
          | ((v15 & 0x30000000000LL | ((v15 & 0xF80000000000LL | (((v15 >> 16) | v15 & 0xFF000000000000LL) >> 15)) >> 1)) >> 15)) >> 12);
    *((_QWORD *)this + 49) = v16;
    v17 = *(_QWORD *)(v14 + 2) & 0x3000000000000LL | (*(_QWORD *)(v14 + 2) >> 16);
    v18 = 300 * v16;
LABEL_22:
    v22 = v17 >> 41;
    *(_QWORD *)v28 = v22 + v18;
    *((_QWORD *)this + 50) = v22;
    NewFrameBuffer = CCopyFrameParser::GetNewFrameBuffer(this, (struct IMediaSample *)v14);
    if ( NewFrameBuffer >= 0 )
    {
      v24 = *(_DWORD *)(a3 + 28) & 0x1FFF;
      a5 = 0;
      *(_DWORD *)&v28[8] = v24;
      v25 = CBufferSourceManager::CopyBlock((CCopyFrameParser *)((char *)this + 48), v28, 16, &a5);
      v26 = (CCopyFrameParser *)((char *)this + 48);
      if ( v25 )
      {
        CBufferSourceManager::Complete((__int64)v26);
      }
      else
      {
        CBufferSourceManager::AbortBuffer(v26);
        NewFrameBuffer = -2147467259;
      }
    }
    *((_DWORD *)this + 112) = 0;
    v11 = NewFrameBuffer >= 0;
LABEL_27:
    if ( !v11 )
      goto LABEL_30;
    return !v11 ? 0x80004005 : 0;
  }
  v20 = 10LL - (_QWORD)v13;
  if ( 10 - (__int64)v13 >= (unsigned __int64)*(int *)(a3 + 8) )
    v20 = *(int *)(a3 + 8);
  if ( v20 >= (unsigned __int64)&v12[v20] || v20 > *((_QWORD *)this + 53) - (_QWORD)v13 )
  {
    v11 = 0;
LABEL_30:
    *((_DWORD *)this + 112) = 0;
    return !v11 ? 0x80004005 : 0;
  }
  memcpy_0(v12, *(const void **)a3, v20);
  *((_QWORD *)this + 52) += v20;
  v21 = *((_QWORD *)this + 51);
  if ( *((_QWORD *)this + 52) - v21 == 10 )
  {
    v14 = (8 * (*(_QWORD *)(v21 + 1) & 0x38000000LL | (2 * (*(_QWORD *)(v21 + 1) & 0x3000000LL))))
        | ((*(_QWORD *)(v21 + 1) & 0xFF00000000LL
          | ((*(_QWORD *)(v21 + 1) & 0x30000000000LL
            | ((*(_QWORD *)(v21 + 1) & 0xF80000000000LL
              | (((*(_QWORD *)(v21 + 1) >> 16) | *(_QWORD *)(v21 + 1) & 0xFF000000000000uLL) >> 15)) >> 1)) >> 15)) >> 12);
    *((_QWORD *)this + 49) = v14;
    v17 = *(_QWORD *)(v21 + 2) & 0x3000000000000LL | (*(_QWORD *)(v21 + 2) >> 16);
    v18 = 300 * v14;
    goto LABEL_22;
  }
  return !v11 ? 0x80004005 : 0;
}

```

## disassembly

```asm
0x18002a9a0  push    rbx
0x18002a9a2  push    rsi
0x18002a9a3  push    rdi
0x18002a9a4  push    r14
0x18002a9a6  sub     rsp, 38h
0x18002a9aa  cmp     [rsp+58h+arg_20], 0
0x18002a9b2  xorps   xmm0, xmm0
0x18002a9b5  mov     edx, [rsp+58h+arg_30]
0x18002a9bc  mov     r14, r8
0x18002a9bf  movups  xmmword ptr [rsp+58h+var_38], xmm0
0x18002a9c4  mov     rbx, rcx
0x18002a9c7  jnz     short loc_18002A9CD
0x18002a9c9  test    edx, edx
0x18002a9cb  jz      short loc_18002A9D7
0x18002a9cd  mov     dword ptr [rcx+1C0h], 0
0x18002a9d7  mov     ecx, [rcx+1C0h]
0x18002a9dd  mov     edi, 1
0x18002a9e2  test    ecx, ecx
0x18002a9e4  jz      short loc_18002A9EF
0x18002a9e6  cmp     ecx, edi
0x18002a9e8  jz      short loc_18002AA0B
0x18002a9ea  jmp     loc_18002ACB7
0x18002a9ef  test    edx, edx
0x18002a9f1  jz      loc_18002ACB7
0x18002a9f7  mov     rax, [rbx+198h]
0x18002a9fe  mov     [rbx+1A0h], rax
0x18002aa05  mov     [rbx+1C0h], edi
0x18002aa0b  mov     rcx, [rbx+1A0h]; void *
0x18002aa12  mov     rdx, rcx
0x18002aa15  sub     rdx, [rbx+198h]
0x18002aa1c  jnz     loc_18002AB13
0x18002aa22  cmp     dword ptr [r8+8], 0Ah
0x18002aa27  jl      loc_18002AADF
0x18002aa2d  mov     rdx, [r8]
0x18002aa30  mov     rax, 0FF000000000000h
0x18002aa3a  mov     r9, 0F80000000000h
0x18002aa44  mov     rcx, [rdx+1]
0x18002aa48  mov     r8, rcx
0x18002aa4b  and     r8, rax
0x18002aa4e  mov     rax, rcx
0x18002aa51  shr     rax, 10h
0x18002aa55  or      r8, rax
0x18002aa58  mov     rax, rcx
0x18002aa5b  and     rax, r9
0x18002aa5e  shr     r8, 0Fh
0x18002aa62  or      r8, rax
0x18002aa65  mov     r9, 30000000000h
0x18002aa6f  shr     r8, 1
0x18002aa72  mov     rax, rcx
0x18002aa75  and     rax, r9
0x18002aa78  mov     r9, 0FF00000000h
0x18002aa82  or      r8, rax
0x18002aa85  mov     rax, rcx
0x18002aa88  and     rax, r9
0x18002aa8b  shr     r8, 0Fh
0x18002aa8f  or      r8, rax
0x18002aa92  mov     r9, 3000000000000h
0x18002aa9c  mov     rax, rcx
0x18002aa9f  shr     r8, 0Ch
0x18002aaa3  and     eax, 3000000h
0x18002aaa8  and     ecx, 38000000h
0x18002aaae  add     rax, rax
0x18002aab1  or      rax, rcx
0x18002aab4  shl     rax, 3
0x18002aab8  or      r8, rax
0x18002aabb  mov     [rbx+188h], r8
0x18002aac2  mov     rax, [rdx+2]
0x18002aac6  mov     rcx, rax
0x18002aac9  and     rax, r9
0x18002aacc  shr     rcx, 10h
0x18002aad0  or      rcx, rax
0x18002aad3  imul    rax, r8, 12Ch
0x18002aada  jmp     loc_18002AC1D
0x18002aadf  movsxd  rsi, dword ptr [r8+8]
0x18002aae3  lea     rax, [rsi+rcx]
0x18002aae7  cmp     rsi, rax
0x18002aaea  jnb     short loc_18002AB0C
0x18002aaec  cmp     rsi, [rbx+1A8h]
0x18002aaf3  ja      short loc_18002AB0C
0x18002aaf5  mov     rdx, [r14]; Src
0x18002aaf8  mov     r8, rsi; Size
0x18002aafb  call    memcpy_0
0x18002ab00  add     [rbx+1A0h], rsi
0x18002ab07  jmp     loc_18002ACA5
0x18002ab0c  xor     edi, edi
0x18002ab0e  jmp     loc_18002ACA5
0x18002ab13  movsxd  rax, dword ptr [r8+8]
0x18002ab17  mov     esi, 0Ah
0x18002ab1c  sub     rsi, rdx
0x18002ab1f  cmp     rsi, rax
0x18002ab22  cmovnb  rsi, rax
0x18002ab26  lea     rax, [rsi+rcx]
0x18002ab2a  cmp     rsi, rax
0x18002ab2d  jnb     loc_18002ACAB
0x18002ab33  mov     rax, [rbx+1A8h]
0x18002ab3a  sub     rax, rdx
0x18002ab3d  cmp     rsi, rax
0x18002ab40  ja      loc_18002ACAB
0x18002ab46  mov     rdx, [r14]; Src
0x18002ab49  mov     r8, rsi; Size
0x18002ab4c  call    memcpy_0
0x18002ab51  add     [rbx+1A0h], rsi
0x18002ab58  mov     rax, [rbx+1A0h]
0x18002ab5f  mov     r8, [rbx+198h]
0x18002ab66  sub     rax, r8
0x18002ab69  cmp     rax, 0Ah
0x18002ab6d  jnz     loc_18002ACB7
0x18002ab73  mov     rcx, [r8+1]
0x18002ab77  mov     rax, 0FF000000000000h
0x18002ab81  mov     rdx, rcx
0x18002ab84  mov     r9, 0F80000000000h
0x18002ab8e  and     rdx, rax
0x18002ab91  mov     rax, rcx
0x18002ab94  shr     rax, 10h
0x18002ab98  or      rdx, rax
0x18002ab9b  mov     rax, rcx
0x18002ab9e  and     rax, r9
0x18002aba1  shr     rdx, 0Fh
0x18002aba5  or      rdx, rax
0x18002aba8  mov     r9, 30000000000h
0x18002abb2  shr     rdx, 1
0x18002abb5  mov     rax, rcx
0x18002abb8  and     rax, r9
0x18002abbb  mov     r9, 0FF00000000h
0x18002abc5  or      rdx, rax
0x18002abc8  mov     rax, rcx
0x18002abcb  and     rax, r9
0x18002abce  shr     rdx, 0Fh
0x18002abd2  or      rdx, rax
0x18002abd5  mov     r9, 3000000000000h
0x18002abdf  mov     rax, rcx
0x18002abe2  shr     rdx, 0Ch
0x18002abe6  and     eax, 3000000h
0x18002abeb  and     ecx, 38000000h
0x18002abf1  add     rax, rax
0x18002abf4  or      rax, rcx
0x18002abf7  shl     rax, 3
0x18002abfb  or      rdx, rax; struct IMediaSample *
0x18002abfe  mov     [rbx+188h], rdx
0x18002ac05  mov     rax, [r8+2]
0x18002ac09  mov     rcx, rax
0x18002ac0c  and     rax, r9
0x18002ac0f  shr     rcx, 10h
0x18002ac13  or      rcx, rax
0x18002ac16  imul    rax, rdx, 12Ch
0x18002ac1d  shr     rcx, 29h
0x18002ac21  add     rax, rcx
0x18002ac24  mov     qword ptr [rsp+58h+var_38], rax
0x18002ac29  mov     [rbx+190h], rcx
0x18002ac30  mov     rcx, rbx; this
0x18002ac33  call    ?GetNewFrameBuffer@CCopyFrameParser@@IEAAJPEAUIMediaSample@@@Z; CCopyFrameParser::GetNewFrameBuffer(IMediaSample *)
0x18002ac38  mov     edi, eax
0x18002ac3a  test    eax, eax
0x18002ac3c  js      short loc_18002AC96
0x18002ac3e  mov     ecx, [r14+1Ch]
0x18002ac42  lea     rsi, [rbx+30h]
0x18002ac46  and     ecx, 1FFFh
0x18002ac4c  mov     [rsp+58h+arg_20], 0
0x18002ac57  mov     dword ptr [rsp+58h+var_38+8], ecx
0x18002ac5b  lea     r9, [rsp+58h+arg_20]; int *
0x18002ac63  mov     rcx, rsi; this
0x18002ac66  lea     rdx, [rsp+58h+var_38]; unsigned __int8 *
0x18002ac6b  mov     r8d, 10h; int
0x18002ac71  call    ?CopyBlock@CBufferSourceManager@@IEAAHPEAEHPEAH@Z; CBufferSourceManager::CopyBlock(uchar *,int,int *)
0x18002ac76  mov     rcx, rsi; this
0x18002ac79  test    eax, eax
0x18002ac7b  jz      short loc_18002AC8C
0x18002ac7d  mov     rdx, [rsp+58h+arg_40]
0x18002ac85  call    ?Complete@CBufferSourceManager@@IEAAJPEAV?$CTStickyVal@H@@@Z; CBufferSourceManager::Complete(CTStickyVal<int> *)
0x18002ac8a  jmp     short loc_18002AC96
0x18002ac8c  call    ?AbortBuffer@CBufferSourceManager@@IEAAXXZ; CBufferSourceManager::AbortBuffer(void)
0x18002ac91  mov     edi, 80004005h
0x18002ac96  not     edi
0x18002ac98  mov     dword ptr [rbx+1C0h], 0
0x18002aca2  shr     edi, 1Fh
0x18002aca5  test    edi, edi
0x18002aca7  jnz     short loc_18002ACB7
0x18002aca9  jmp     short loc_18002ACAD
0x18002acab  xor     edi, edi
0x18002acad  mov     dword ptr [rbx+1C0h], 0
0x18002acb7  neg     edi
0x18002acb9  sbb     eax, eax
0x18002acbb  not     eax
0x18002acbd  and     eax, 80004005h
0x18002acc2  add     rsp, 38h
0x18002acc6  pop     r14
0x18002acc8  pop     rdi
0x18002acc9  pop     rsi
0x18002acca  pop     rbx
0x18002accb  retn
```
