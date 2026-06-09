# CASFFrameIndexMaker::CreateStreamInfo(ushort)

- ea: `0x1800322f0`
- end: `0x180032590`
- name: `?CreateStreamInfo@CASFFrameIndexMaker@@MEAAJG@Z`
- size: `672`
- prototype: `__int64 __fastcall(CASFFrameIndexMaker *__hidden this, unsigned __int16)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x1800015d0`
- `0x180001ee8`
- `0x180031d98`
- `0x180031e50`
- `0x180031ed4`
- `0x180032000`
- `0x1800322f0`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFFrameIndexMaker::CreateStreamInfo(CASFFrameIndexMaker *this, unsigned __int16 a2)
{
  _QWORD *v4; // rax
  __int64 (__fastcall *v5)(CASFFrameIndexMaker *); // rax
  int v6; // ebx
  unsigned __int16 i; // di
  __int64 v8; // rax
  unsigned __int16 v9; // si
  unsigned __int16 v10; // r12
  __int64 v11; // r8
  char *j; // rdx
  unsigned int v13; // ecx
  unsigned int v14; // edi
  char *v15; // rdx
  __int64 v16; // rax
  _BYTE v18[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int16 v19; // [rsp+32h] [rbp-CEh]
  _BYTE v20[568]; // [rsp+58h] [rbp-A8h] BYREF
  __int16 v21[2]; // [rsp+290h] [rbp+190h] BYREF
  _WORD v22[6]; // [rsp+294h] [rbp+194h] BYREF
  _BYTE v23[2]; // [rsp+2A0h] [rbp+1A0h] BYREF
  __int16 v24; // [rsp+2A2h] [rbp+1A2h]
  __int16 v25; // [rsp+2A4h] [rbp+1A4h]
  __int64 v26; // [rsp+2A8h] [rbp+1A8h]
  __int64 v27; // [rsp+2B8h] [rbp+1B8h]
  __int64 v28; // [rsp+2C0h] [rbp+1C0h]
  _QWORD v29[5]; // [rsp+2C8h] [rbp+1C8h] BYREF
  __int16 v30; // [rsp+2F0h] [rbp+1F0h]
  char v31; // [rsp+2F2h] [rbp+1F2h]
  __int64 v32; // [rsp+4D8h] [rbp+3D8h]
  _QWORD *v33; // [rsp+4E0h] [rbp+3E0h]
  int v34; // [rsp+4E8h] [rbp+3E8h]
  int v35; // [rsp+4F0h] [rbp+3F0h]

  v30 = 0;
  v31 = 0;
  v22[0] = 0;
  v33 = v29;
  v29[0] = &CTDynArray<CASFBaseIndexMaker::SEEK_POINT,20>::`vftable';
  v4 = *(_QWORD **)this;
  v21[0] = 0;
  v29[1] = 0;
  v32 = 0;
  v5 = (__int64 (__fastcall *)(CASFFrameIndexMaker *))v4[10];
  v34 = 0;
  v35 = 0;
  v6 = v5(this);
  if ( v6 >= 0 )
  {
    for ( i = 0; i < a2; ++i )
    {
      v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _WORD *, __int16 *))(**((_QWORD **)this + 11) + 128LL))(
             *((_QWORD *)this + 11),
             i,
             v22,
             v21);
      if ( v6 < 0 )
        goto LABEL_25;
      if ( v21[0] != 255 )
      {
        v25 = v21[0];
        v24 = v22[0];
        v23[0] = -1;
        v26 = 0;
        v27 = 0;
        v28 = 0;
        v8 = CASFBaseIndexMaker::STREAM_INFO::STREAM_INFO(
               (CASFBaseIndexMaker::STREAM_INFO *)v18,
               (const struct CASFBaseIndexMaker::STREAM_INFO *)v23);
        if ( !(unsigned int)CTDynArray<CASFBaseIndexMaker::STREAM_INFO,20>::Add((char *)this + 352, v8) )
        {
LABEL_24:
          v6 = -2147024882;
          goto LABEL_25;
        }
      }
    }
    v9 = 0;
    v10 = a2 >> 1;
    while ( v9 < v10 )
    {
      v23[0] = -1;
      memset_0(v18, 0, 0x258u);
      if ( (unsigned int)v9 < *((_DWORD *)this + 3250) && this != (CASFFrameIndexMaker *)-352LL )
      {
        for ( j = (char *)this + 352; j; j = (char *)*((_QWORD *)j + 1578) )
        {
          v13 = *((_DWORD *)j + 2);
          if ( v9 >= v13 && v9 < v13 + 20 )
          {
            v14 = v9 - v13;
            v11 = v14;
            if ( ((unsigned __int8)j[((unsigned __int64)v14 >> 3) + 616]
                & *((_BYTE *)&CTSparseBlock<unsigned long,CASFBaseIndexMaker::STREAM_INFO,20,0>::s_bSingleBitMasks
                  + (v14 & 7))) != 0 )
            {
              v15 = &j[600 * v14 + 624];
              goto LABEL_21;
            }
            break;
          }
        }
        if ( (*((_BYTE *)this + 364) & 1) == 0 )
          goto LABEL_22;
        v15 = (char *)this + 368;
LABEL_21:
        CASFBaseIndexMaker::STREAM_INFO::operator=(v18, v15, v11);
      }
LABEL_22:
      v24 = v19;
      CTSparseBlock<unsigned long,CASFBaseIndexMaker::SEEK_POINT,20,0>::~CTSparseBlock<unsigned long,CASFBaseIndexMaker::SEEK_POINT,20,0>(v20);
      v26 = 0;
      v25 = 255;
      v27 = 0;
      v28 = 0;
      v16 = CASFBaseIndexMaker::STREAM_INFO::STREAM_INFO(
              (CASFBaseIndexMaker::STREAM_INFO *)v18,
              (const struct CASFBaseIndexMaker::STREAM_INFO *)v23);
      if ( !(unsigned int)CTDynArray<CASFBaseIndexMaker::STREAM_INFO,20>::Add((char *)this + 352, v16) )
        goto LABEL_24;
      ++v9;
    }
  }
LABEL_25:
  CTSparseBlock<unsigned long,CASFBaseIndexMaker::SEEK_POINT,20,0>::~CTSparseBlock<unsigned long,CASFBaseIndexMaker::SEEK_POINT,20,0>(v29);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800322f0  push    rbp
0x1800322f2  push    rbx
0x1800322f3  push    rsi
0x1800322f4  push    rdi
0x1800322f5  push    r12
0x1800322f7  push    r13
0x1800322f9  push    r14
0x1800322fb  push    r15
0x1800322fd  lea     rbp, [rsp-418h]
0x180032305  sub     rsp, 518h
0x18003230c  mov     rax, cs:__security_cookie
0x180032313  xor     rax, rsp
0x180032316  mov     [rbp+450h+var_50], rax
0x18003231d  xor     eax, eax
0x18003231f  xor     r13d, r13d
0x180032322  mov     [rbp+450h+var_260], ax
0x180032329  movzx   r12d, dx
0x18003232d  mov     [rbp+450h+var_25E], al
0x180032333  mov     r14, rcx
0x180032336  lea     rax, [rbp+450h+var_288]
0x18003233d  mov     [rbp+450h+var_2BC], r13w
0x180032345  mov     [rbp+450h+var_70], rax
0x18003234c  lea     rax, ??_7?$CTDynArray@USEEK_POINT@CASFBaseIndexMaker@@$0BE@@@6B@; const CTDynArray<CASFBaseIndexMaker::SEEK_POINT,20>::`vftable'
0x180032353  mov     [rbp+450h+var_288], rax
0x18003235a  mov     rax, [rcx]
0x18003235d  mov     [rbp+450h+var_2C0], r13w
0x180032365  mov     [rbp+450h+var_280], r13
0x18003236c  mov     [rbp+450h+var_78], r13
0x180032373  mov     rax, [rax+50h]
0x180032377  mov     [rbp+450h+var_68], r13d
0x18003237e  mov     [rbp+450h+var_60], r13d
0x180032385  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003238a  mov     ebx, eax
0x18003238c  test    eax, eax
0x18003238e  js      loc_18003255F
0x180032394  mov     edi, r13d
0x180032397  mov     r15d, 0FFh
0x18003239d  cmp     di, r12w
0x1800323a1  jnb     loc_180032443
0x1800323a7  mov     rcx, [r14+58h]
0x1800323ab  lea     r9, [rbp+450h+var_2C0]
0x1800323b2  lea     r8, [rbp+450h+var_2BC]
0x1800323b9  movzx   edx, di
0x1800323bc  mov     rax, [rcx]
0x1800323bf  mov     rax, [rax+80h]
0x1800323c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800323cb  mov     ebx, eax
0x1800323cd  test    eax, eax
0x1800323cf  js      loc_18003255F
0x1800323d5  movzx   ecx, [rbp+450h+var_2C0]
0x1800323dc  cmp     cx, r15w
0x1800323e0  jz      short loc_18003243B
0x1800323e2  movzx   eax, [rbp+450h+var_2BC]
0x1800323e9  lea     rdx, [rbp+450h+var_2B0]; struct CASFBaseIndexMaker::STREAM_INFO *
0x1800323f0  mov     [rbp+450h+var_2AC], cx
0x1800323f7  lea     rcx, [rsp+550h+var_520]; this
0x1800323fc  mov     [rbp+450h+var_2AE], ax
0x180032403  mov     [rbp+450h+var_2B0], r15b
0x18003240a  mov     [rbp+450h+var_2A8], r13
0x180032411  mov     [rbp+450h+var_298], r13
0x180032418  mov     [rbp+450h+var_290], r13
0x18003241f  call    ??0STREAM_INFO@CASFBaseIndexMaker@@QEAA@AEBU01@@Z; CASFBaseIndexMaker::STREAM_INFO::STREAM_INFO(CASFBaseIndexMaker::STREAM_INFO const &)
0x180032424  mov     rdx, rax
0x180032427  lea     rcx, [r14+160h]
0x18003242e  call    ?Add@?$CTDynArray@USTREAM_INFO@CASFBaseIndexMaker@@$0BE@@@QEAAHUSTREAM_INFO@CASFBaseIndexMaker@@PEAK@Z; CTDynArray<CASFBaseIndexMaker::STREAM_INFO,20>::Add(CASFBaseIndexMaker::STREAM_INFO,ulong *)
0x180032433  test    eax, eax
0x180032435  jz      loc_18003255A
0x18003243b  inc     di
0x18003243e  jmp     loc_18003239D
0x180032443  mov     esi, r13d
0x180032446  shr     r12w, 1
0x18003244a  cmp     si, r12w
0x18003244e  jnb     loc_18003255F
0x180032454  mov     [rbp+450h+var_2B0], r15b
0x18003245b  lea     rcx, [rsp+550h+var_520]; void *
0x180032460  xor     edx, edx; Val
0x180032462  movzx   edi, si
0x180032465  mov     r8d, 258h; Size
0x18003246b  lea     r15, [r14+160h]
0x180032472  call    memset_0
0x180032477  cmp     edi, [r15+3168h]
0x18003247e  jnb     short loc_1800324F5
0x180032480  test    r15, r15
0x180032483  jz      short loc_1800324F5
0x180032485  mov     rdx, r15
0x180032488  test    rdx, rdx
0x18003248b  jz      short loc_1800324DA
0x18003248d  mov     ecx, [rdx+8]
0x180032490  cmp     edi, ecx
0x180032492  jb      short loc_18003249B
0x180032494  lea     eax, [rcx+14h]
0x180032497  cmp     edi, eax
0x180032499  jb      short loc_1800324A4
0x18003249b  mov     rdx, [rdx+3150h]
0x1800324a2  jmp     short loc_180032488
0x1800324a4  sub     edi, ecx
0x1800324a6  lea     r9, ?s_bSingleBitMasks@?$CTSparseBlock@KUSTREAM_INFO@CASFBaseIndexMaker@@$0BE@$0A@@@0PAEA; uchar near * CTSparseBlock<ulong,CASFBaseIndexMaker::STREAM_INFO,20,0>::s_bSingleBitMasks
0x1800324ad  mov     ecx, edi
0x1800324af  mov     eax, edi
0x1800324b1  and     ecx, 7
0x1800324b4  shr     rax, 3
0x1800324b8  mov     r8d, edi
0x1800324bb  mov     al, [rax+rdx+268h]
0x1800324c2  test    [rcx+r9], al
0x1800324c6  jz      short loc_1800324DA
0x1800324c8  imul    rax, r8, 258h
0x1800324cf  add     rax, 270h
0x1800324d5  add     rdx, rax
0x1800324d8  jmp     short loc_1800324EB
0x1800324da  test    byte ptr [r14+16Ch], 1
0x1800324e2  jz      short loc_1800324F5
0x1800324e4  lea     rdx, [r14+170h]
0x1800324eb  lea     rcx, [rsp+550h+var_520]
0x1800324f0  call    ??4STREAM_INFO@CASFBaseIndexMaker@@QEAAAEAU01@AEBU01@@Z; CASFBaseIndexMaker::STREAM_INFO::operator=(CASFBaseIndexMaker::STREAM_INFO const &)
0x1800324f5  movzx   eax, [rsp+550h+var_51E]
0x1800324fa  lea     rcx, [rsp+550h+var_4F8]
0x1800324ff  mov     [rbp+450h+var_2AE], ax
0x180032506  call    ??1?$CTSparseBlock@KUSEEK_POINT@CASFBaseIndexMaker@@$0BE@$0A@@@QEAA@XZ; CTSparseBlock<ulong,CASFBaseIndexMaker::SEEK_POINT,20,0>::~CTSparseBlock<ulong,CASFBaseIndexMaker::SEEK_POINT,20,0>(void)
0x18003250b  mov     eax, 0FFh
0x180032510  mov     [rbp+450h+var_2A8], r13
0x180032517  lea     rdx, [rbp+450h+var_2B0]; struct CASFBaseIndexMaker::STREAM_INFO *
0x18003251e  mov     [rbp+450h+var_2AC], ax
0x180032525  lea     rcx, [rsp+550h+var_520]; this
0x18003252a  mov     [rbp+450h+var_298], r13
0x180032531  mov     [rbp+450h+var_290], r13
0x180032538  call    ??0STREAM_INFO@CASFBaseIndexMaker@@QEAA@AEBU01@@Z; CASFBaseIndexMaker::STREAM_INFO::STREAM_INFO(CASFBaseIndexMaker::STREAM_INFO const &)
0x18003253d  mov     rdx, rax
0x180032540  mov     rcx, r15
0x180032543  call    ?Add@?$CTDynArray@USTREAM_INFO@CASFBaseIndexMaker@@$0BE@@@QEAAHUSTREAM_INFO@CASFBaseIndexMaker@@PEAK@Z; CTDynArray<CASFBaseIndexMaker::STREAM_INFO,20>::Add(CASFBaseIndexMaker::STREAM_INFO,ulong *)
0x180032548  test    eax, eax
0x18003254a  jz      short loc_18003255A
0x18003254c  inc     si
0x18003254f  mov     r15d, 0FFh
0x180032555  jmp     loc_18003244A
0x18003255a  mov     ebx, 8007000Eh
0x18003255f  lea     rcx, [rbp+450h+var_288]
0x180032566  call    ??1?$CTSparseBlock@KUSEEK_POINT@CASFBaseIndexMaker@@$0BE@$0A@@@QEAA@XZ; CTSparseBlock<ulong,CASFBaseIndexMaker::SEEK_POINT,20,0>::~CTSparseBlock<ulong,CASFBaseIndexMaker::SEEK_POINT,20,0>(void)
0x18003256b  mov     eax, ebx
0x18003256d  mov     rcx, [rbp+450h+var_50]
0x180032574  xor     rcx, rsp; StackCookie
0x180032577  call    __security_check_cookie
0x18003257c  add     rsp, 518h
0x180032583  pop     r15
0x180032585  pop     r14
0x180032587  pop     r13
0x180032589  pop     r12
0x18003258b  pop     rdi
0x18003258c  pop     rsi
0x18003258d  pop     rbx
0x18003258e  pop     rbp
0x18003258f  retn
```
