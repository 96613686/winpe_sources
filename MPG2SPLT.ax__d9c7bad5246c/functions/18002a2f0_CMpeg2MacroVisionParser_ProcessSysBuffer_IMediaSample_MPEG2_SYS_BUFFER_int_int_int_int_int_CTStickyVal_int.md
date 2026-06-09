# CMpeg2MacroVisionParser::ProcessSysBuffer(IMediaSample *,MPEG2_SYS_BUFFER *,int,int,int,int,int,CTStickyVal<int> *)

- ea: `0x18002a2f0`
- end: `0x18002a478`
- name: `?ProcessSysBuffer@CMpeg2MacroVisionParser@@UEAAJPEAUIMediaSample@@PEAUMPEG2_SYS_BUFFER@@HHHHHPEAV?$CTStickyVal@H@@@Z`
- size: `392`
- prototype: `__int64 __usercall@<rax>(CCopyFrameParser *this@<rcx>, int, int, int, int, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180028a7c`
- `0x180028dc4`
- `0x180028fd8`
- `0x180029270`
- `0x18002a2f0`
- `0x180033dfd`

## pseudocode

```c
__int64 __fastcall CMpeg2MacroVisionParser::ProcessSysBuffer(
        CCopyFrameParser *this,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        int a6,
        int a7)
{
  int v7; // eax
  unsigned int NewFrameBuffer; // r14d
  void **v11; // rsi
  void **v12; // rbx
  char *v13; // rdx
  char *v14; // rcx
  int v15; // eax
  char *v16; // r8
  int v17; // edx
  __int64 v18; // r15
  unsigned __int64 v19; // rcx
  int v20; // ebp
  int v21; // eax
  CBufferSourceManager *v22; // rcx

  v7 = a7;
  NewFrameBuffer = 0;
  if ( a7 || a5 )
  {
    v11 = (void **)((char *)this + 392);
    v13 = (char *)*((_QWORD *)this + 49);
    v12 = (void **)((char *)this + 400);
    *((_QWORD *)this + 50) = v13;
    if ( v7 )
    {
      v14 = (char *)*((_QWORD *)this + 50);
      if ( v14 != v13 )
        goto LABEL_23;
      goto LABEL_5;
    }
  }
  else
  {
    v11 = (void **)((char *)this + 392);
    v12 = (void **)((char *)this + 400);
  }
  v13 = (char *)*v11;
  v14 = (char *)v11[1];
  if ( v14 == *v11 )
    goto LABEL_23;
LABEL_5:
  v15 = *(_DWORD *)(a3 + 24);
  v16 = (char *)(v14 - v13);
  v17 = 13 - ((_DWORD)v14 - (_DWORD)v13);
  if ( v15 >= v17 )
    v15 = v17;
  v18 = v15;
  if ( v15 < (unsigned __int64)&v14[v15] && (unsigned __int64)v15 <= *((_QWORD *)this + 51) - (_QWORD)v16 )
  {
    memcpy_0(v14, *(const void **)(a3 + 16), v15);
    *v12 = (char *)*v12 + v18;
    v14 = (char *)*v12;
  }
  v13 = (char *)*v11;
  v19 = v14 - (_BYTE *)*v11;
  if ( v19 < 0xD )
  {
    if ( v19 < 6 || (HIBYTE(*((unsigned __int16 *)v13 + 2)) | ((unsigned __int8)*((_WORD *)v13 + 2) << 8)) >= 7u )
      return NewFrameBuffer;
LABEL_23:
    *v12 = v13;
    return NewFrameBuffer;
  }
  if ( !v13[6] )
  {
    v20 = (*(unsigned __int16 *)(v13 + 11) >> 6) & 3;
    if ( v20 != *((_DWORD *)this + 108) )
    {
      NewFrameBuffer = CCopyFrameParser::GetNewFrameBuffer(this, (struct IMediaSample *)v13);
      if ( (NewFrameBuffer & 0x80000000) == 0 )
      {
        a7 = 0;
        *((_DWORD *)this + 109) = v20;
        v21 = CBufferSourceManager::CopyBlock(
                (CCopyFrameParser *)((char *)this + 48),
                (unsigned __int8 *)this + 436,
                4,
                &a7);
        v22 = (CCopyFrameParser *)((char *)this + 48);
        if ( v21 )
        {
          CBufferSourceManager::Complete((__int64)v22);
          *((_DWORD *)this + 108) = v20;
        }
        else
        {
          CBufferSourceManager::AbortBuffer(v22);
          NewFrameBuffer = -2147467259;
        }
      }
    }
  }
  *v12 = *v11;
  return NewFrameBuffer;
}

```

## disassembly

```asm
0x18002a2f0  push    rbx
0x18002a2f2  push    rbp
0x18002a2f3  push    rsi
0x18002a2f4  push    rdi
0x18002a2f5  push    r14
0x18002a2f7  push    r15
0x18002a2f9  sub     rsp, 28h
0x18002a2fd  mov     eax, [rsp+58h+arg_30]
0x18002a304  xor     r14d, r14d
0x18002a307  mov     r9, r8
0x18002a30a  mov     rdi, rcx
0x18002a30d  test    eax, eax
0x18002a30f  jnz     loc_18002A40E
0x18002a315  cmp     [rsp+58h+arg_20], r14d
0x18002a31d  jnz     loc_18002A40E
0x18002a323  lea     rsi, [rcx+188h]
0x18002a32a  lea     rbx, [rcx+190h]
0x18002a331  mov     rdx, [rsi]
0x18002a334  mov     rcx, [rsi+8]; void *
0x18002a338  cmp     rcx, rdx
0x18002a33b  jz      loc_18002A465
0x18002a341  mov     eax, [r9+18h]
0x18002a345  mov     r8, rcx
0x18002a348  sub     r8, rdx
0x18002a34b  mov     edx, 0Dh
0x18002a350  sub     edx, r8d
0x18002a353  cmp     eax, edx
0x18002a355  cmovge  eax, edx
0x18002a358  movsxd  r15, eax
0x18002a35b  lea     rax, [r15+rcx]
0x18002a35f  cmp     r15, rax
0x18002a362  jnb     short loc_18002A385
0x18002a364  mov     rax, [rdi+198h]
0x18002a36b  sub     rax, r8
0x18002a36e  cmp     r15, rax
0x18002a371  ja      short loc_18002A385
0x18002a373  mov     rdx, [r9+10h]; Src
0x18002a377  mov     r8, r15; Size
0x18002a37a  call    memcpy_0
0x18002a37f  add     [rbx], r15
0x18002a382  mov     rcx, [rbx]
0x18002a385  mov     rdx, [rsi]; struct IMediaSample *
0x18002a388  sub     rcx, rdx
0x18002a38b  cmp     rcx, 0Dh
0x18002a38f  jb      loc_18002A44B
0x18002a395  cmp     [rdx+6], r14b
0x18002a399  jnz     loc_18002A443
0x18002a39f  movzx   ebp, word ptr [rdx+0Bh]
0x18002a3a3  shr     ebp, 6
0x18002a3a6  and     ebp, 3
0x18002a3a9  cmp     ebp, [rdi+1B0h]
0x18002a3af  jz      loc_18002A443
0x18002a3b5  mov     rcx, rdi; this
0x18002a3b8  call    ?GetNewFrameBuffer@CCopyFrameParser@@IEAAJPEAUIMediaSample@@@Z; CCopyFrameParser::GetNewFrameBuffer(IMediaSample *)
0x18002a3bd  mov     r14d, eax
0x18002a3c0  test    eax, eax
0x18002a3c2  js      short loc_18002A443
0x18002a3c4  lea     rdx, [rdi+1B4h]; unsigned __int8 *
0x18002a3cb  mov     [rsp+58h+arg_30], 0
0x18002a3d6  lea     r15, [rdi+30h]
0x18002a3da  mov     [rdx], ebp
0x18002a3dc  mov     rcx, r15; this
0x18002a3df  lea     r9, [rsp+58h+arg_30]; int *
0x18002a3e7  mov     r8d, 4; int
0x18002a3ed  call    ?CopyBlock@CBufferSourceManager@@IEAAHPEAEHPEAH@Z; CBufferSourceManager::CopyBlock(uchar *,int,int *)
0x18002a3f2  mov     rcx, r15; this
0x18002a3f5  test    eax, eax
0x18002a3f7  jz      short loc_18002A438
0x18002a3f9  mov     rdx, [rsp+58h+arg_40]
0x18002a401  call    ?Complete@CBufferSourceManager@@IEAAJPEAV?$CTStickyVal@H@@@Z; CBufferSourceManager::Complete(CTStickyVal<int> *)
0x18002a406  mov     [rdi+1B0h], ebp
0x18002a40c  jmp     short loc_18002A443
0x18002a40e  lea     rsi, [rcx+188h]
0x18002a415  mov     rdx, [rsi]
0x18002a418  lea     rbx, [rcx+190h]
0x18002a41f  mov     [rbx], rdx
0x18002a422  test    eax, eax
0x18002a424  jz      loc_18002A331
0x18002a42a  mov     rcx, [rsi+8]
0x18002a42e  cmp     rcx, rdx
0x18002a431  jnz     short loc_18002A465
0x18002a433  jmp     loc_18002A341
0x18002a438  call    ?AbortBuffer@CBufferSourceManager@@IEAAXXZ; CBufferSourceManager::AbortBuffer(void)
0x18002a43d  mov     r14d, 80004005h
0x18002a443  mov     rax, [rsi]
0x18002a446  mov     [rbx], rax
0x18002a449  jmp     short loc_18002A468
0x18002a44b  cmp     rcx, 6
0x18002a44f  jb      short loc_18002A468
0x18002a451  movzx   ecx, word ptr [rdx+4]
0x18002a455  movzx   eax, cl
0x18002a458  shl     eax, 8
0x18002a45b  shr     ecx, 8
0x18002a45e  or      eax, ecx
0x18002a460  cmp     eax, 7
0x18002a463  jnb     short loc_18002A468
0x18002a465  mov     [rbx], rdx
0x18002a468  mov     eax, r14d
0x18002a46b  add     rsp, 28h
0x18002a46f  pop     r15
0x18002a471  pop     r14
0x18002a473  pop     rdi
0x18002a474  pop     rsi
0x18002a475  pop     rbp
0x18002a476  pop     rbx
0x18002a477  retn
```
