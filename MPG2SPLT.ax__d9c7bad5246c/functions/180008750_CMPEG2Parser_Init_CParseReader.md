# CMPEG2Parser::Init(CParseReader *)

- ea: `0x180008750`
- end: `0x180008bb1`
- name: `?Init@CMPEG2Parser@@UEAAJPEAVCParseReader@@@Z`
- size: `1121`
- prototype: `__int64 __fastcall(CMPEG2Parser *__hidden this, struct CParseReader *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops`

## callees

- `0x180001048`
- `0x1800076c0`
- `0x180008750`
- `0x180009220`
- `0x18000b1b4`
- `0x18000b26c`
- `0x18000d148`
- `0x180034010`

## pseudocode

```c
__int64 __fastcall CMPEG2Parser::Init(CMPEG2Parser *this, struct CParseReader *a2)
{
  __int64 v4; // rax
  CSpltBaseParser *v5; // rcx
  unsigned int inited; // eax
  unsigned int v7; // esi
  unsigned __int8 *v8; // rcx
  unsigned __int8 *v10; // r14
  int v11; // r12d
  unsigned __int8 *v12; // rdi
  unsigned __int8 v13; // al
  unsigned int v14; // eax
  CSpltBaseParser *v15; // rcx
  unsigned int v16; // eax
  unsigned int v17; // edi
  unsigned int v18; // ebx
  unsigned __int8 *v19; // r14
  unsigned __int8 v20; // r12
  unsigned int v21; // esi
  unsigned int v22; // esi
  __int64 v23; // rax
  unsigned int v24; // eax
  __int64 v25; // rdx
  __int64 v26; // r13
  __int64 v27; // rax
  unsigned __int8 v28; // r8
  __int64 v29; // rdx
  __int64 i; // rcx
  __int64 j; // rcx
  unsigned __int64 v32[2]; // [rsp+30h] [rbp-20h] BYREF
  __int64 v33; // [rsp+40h] [rbp-10h]
  unsigned int v34; // [rsp+98h] [rbp+48h] BYREF
  unsigned __int8 *v35; // [rsp+A0h] [rbp+50h] BYREF

  if ( !a2 )
    return 2147746346LL;
  *(_QWORD *)((char *)this + 44) = 0;
  v4 = *(_QWORD *)a2;
  v35 = 0;
  (*(void (__fastcall **)(struct CParseReader *, _QWORD))(v4 + 8))(a2, 0);
  inited = CSpltBaseParser::NewInitBuffer(v5, &v35, 0x20200u, a2);
  v7 = inited;
  if ( !inited )
  {
    v8 = v35;
LABEL_4:
    operator delete(v8);
    return 2147746346LL;
  }
  v10 = v35;
  v11 = 0;
  v12 = v35;
  if ( inited <= 0x101FA )
    goto LABEL_18;
  while ( 1 )
  {
    if ( !*v12 && !v12[1] && v12[2] == 1 )
    {
      v13 = v12[3];
      if ( v13 >= 0xBCu && v13 != 0xBE )
      {
        v33 = 0;
        *(_OWORD *)v32 = 0;
        v14 = ParseMPEG2Packet(v12, v7, (struct tag_MPEG_PACKET_DATA *)v32);
        if ( v14 == -1 )
        {
          v8 = v10;
          goto LABEL_4;
        }
        if ( v14 > 4 && !v12[HIDWORD(v32[0])] && !v12[HIDWORD(v32[0]) + 1] && (v12[HIDWORD(v32[0]) + 2] & 0xFE) == 0 )
          break;
      }
    }
    --v7;
    ++v12;
    if ( v7 <= 0x101FA )
      goto LABEL_18;
  }
  v11 = 1;
LABEL_18:
  operator delete(v10);
  if ( !v11 )
    return 2147746346LL;
  (*(void (__fastcall **)(struct CParseReader *, _QWORD))(*(_QWORD *)a2 + 8LL))(a2, 0);
  v16 = CSpltBaseParser::NewInitBuffer(v15, &v35, 0x300000u, a2);
  v17 = v16;
  if ( !v16 )
  {
    v18 = -2147220950;
    goto LABEL_58;
  }
  v19 = v35;
  v20 = -64;
  if ( v16 < 0x8C )
  {
LABEL_59:
    operator delete(v35);
    if ( *((__int64 *)this + 147) >= 0 && *((_DWORD *)this + 292) && (*((_DWORD *)this + 11) || *((_BYTE *)this + 1193)) )
    {
      if ( (*(unsigned int (__fastcall **)(struct CParseReader *))(*(_QWORD *)a2 + 24LL))(a2) )
        CMPEG2Parser::CalcDuration(this, a2);
      v28 = 0;
      do
      {
        v29 = 16LL * v20;
        if ( (CMPEG2Parser *)((char *)this + v29 - 2952) )
        {
          if ( v28 )
          {
            *(_DWORD *)((char *)this + v29 - 2944) = 1;
            for ( i = *((_QWORD *)this + 2 * v28 - 369); i; i = *(_QWORD *)(i + 40) )
            {
              if ( !*(_DWORD *)(i + 12) || !*(_BYTE *)(i + 9) )
                goto LABEL_74;
            }
            i = 0;
LABEL_74:
            *(_QWORD *)((char *)this + v29 - 2952) = i;
            *(_DWORD *)((char *)this + v29 - 2940) = 1;
          }
          else
          {
            v28 = v20;
          }
          *((_DWORD *)this + 4 * (unsigned __int8)(v20 + 16) - 736) = 1;
          for ( j = *((_QWORD *)this + 2 * v28 - 369); j; j = *(_QWORD *)(j + 40) )
          {
            if ( !*(_DWORD *)(j + 12) || !*(_BYTE *)(j + 9) )
              goto LABEL_82;
          }
          j = 0;
LABEL_82:
          *((_QWORD *)this + 2 * (unsigned __int8)(v20 + 16) - 369) = j;
          *((_DWORD *)this + 4 * (unsigned __int8)(v20 + 16) - 735) = 1;
        }
        ++v20;
      }
      while ( v20 < 0xD0u );
      return 0;
    }
    return 2147746346LL;
  }
  while ( 2 )
  {
    if ( (*(_DWORD *)v19 & 0xFFFFFF) != 0x10000 )
      goto LABEL_54;
    v21 = __ROL4__(((*(_DWORD *)v19 & 0xFFFF00FF) << 8) | (*(_DWORD *)v19 >> 8) & 0xFF00FF, 16);
    if ( v21 == 442 )
    {
      if ( v17 < 0xE )
        goto LABEL_59;
      v22 = (v19[13] & 7) + 14;
      if ( v22 > v17 )
        goto LABEL_59;
      if ( *((__int64 *)this + 147) < 0 )
      {
        v34 = 0;
        ParseMPEG2PackHeader(v19, v17, (__int64 *)this + 147, &v34);
      }
      v17 -= v22;
      *(_QWORD *)((char *)this + 1236) = *(_QWORD *)v19;
      *((_DWORD *)this + 311) = *((_DWORD *)v19 + 2);
      *((_BYTE *)this + 1248) = v19[12];
      v23 = v22;
      goto LABEL_55;
    }
    if ( v21 == 443 )
    {
      LODWORD(v23) = CMPEG2Parser::InitSystemHeader(this, v19, v17);
      if ( (unsigned int)v23 > 4 )
      {
        v17 -= v23;
        v23 = (unsigned int)v23;
LABEL_55:
        if ( v17 < 0x8C )
          goto LABEL_59;
        v19 += v23;
        continue;
      }
      if ( !(_DWORD)v23 )
        goto LABEL_59;
LABEL_54:
      --v17;
      v23 = 1;
      goto LABEL_55;
    }
    break;
  }
  if ( v21 < 0x1BC || v21 > 0x1FF )
    goto LABEL_54;
  v33 = 0;
  *(_OWORD *)v32 = 0;
  v24 = ParseMPEG2Packet(v19, v17, (struct tag_MPEG_PACKET_DATA *)v32);
  v26 = v24;
  if ( v24 != -1 )
  {
    if ( v24 <= 4 )
    {
      if ( !v24 )
        goto LABEL_59;
      goto LABEL_54;
    }
    LOBYTE(v25) = v21;
    if ( (*(int (__fastcall **)(CMPEG2Parser *, __int64, unsigned __int8 *, _QWORD))(*(_QWORD *)this + 136LL))(
           this,
           v25,
           &v19[LODWORD(v32[0])],
           (unsigned int)(HIDWORD(v32[0]) - LODWORD(v32[0]))) >= 0 )
    {
      if ( LODWORD(v32[1]) )
      {
        v27 = v33;
        if ( !*((_DWORD *)this + 292) )
        {
          *((_DWORD *)this + 292) = 1;
          goto LABEL_45;
        }
        if ( *((_QWORD *)this + 143) > v33 )
        {
LABEL_45:
          *((_QWORD *)this + 143) = v27;
          *((_QWORD *)this + 152) = v27;
        }
      }
      if ( (v21 & 0xF0) == 0xE0 )
      {
        if ( !*((_BYTE *)this + 1193) )
          *((_BYTE *)this + 1193) = v21;
      }
      else if ( (v21 & 0xE0) == 0xC0 && !*((_BYTE *)this + 1192) )
      {
        *((_BYTE *)this + 1192) = v21;
      }
    }
    v17 -= v26;
    v23 = v26;
    goto LABEL_55;
  }
  v18 = -2147023504;
LABEL_58:
  operator delete(v35);
  return v18;
}

```

## disassembly

```asm
0x180008750  mov     [rsp-38h+arg_0], rbx
0x180008755  push    rbp
0x180008756  push    rsi
0x180008757  push    rdi
0x180008758  push    r12
0x18000875a  push    r13
0x18000875c  push    r14
0x18000875e  push    r15
0x180008760  mov     rbp, rsp
0x180008763  sub     rsp, 50h
0x180008767  xor     r13d, r13d
0x18000876a  mov     r15, rdx
0x18000876d  mov     rbx, rcx
0x180008770  test    rdx, rdx
0x180008773  jz      short loc_1800087AF
0x180008775  mov     [rcx+2Ch], r13
0x180008779  mov     rcx, r15
0x18000877c  mov     rax, [rdx]
0x18000877f  xor     edx, edx
0x180008781  mov     [rbp+arg_10], r13
0x180008785  mov     rax, [rax+8]
0x180008789  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000878e  mov     r9, r15; struct CParseReader *
0x180008791  lea     rdx, [rbp+arg_10]; unsigned __int8 **
0x180008795  mov     r8d, 20200h; unsigned int
0x18000879b  call    ?NewInitBuffer@CSpltBaseParser@@IEAAIPEAPEAEIPEAVCParseReader@@@Z; CSpltBaseParser::NewInitBuffer(uchar * *,uint,CParseReader *)
0x1800087a0  mov     esi, eax
0x1800087a2  test    eax, eax
0x1800087a4  jnz     short loc_1800087CC
0x1800087a6  mov     rcx, [rbp+arg_10]; void *
0x1800087aa  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800087af  mov     eax, 8004022Ah
0x1800087b4  mov     rbx, [rsp+50h+arg_0]
0x1800087bc  add     rsp, 50h
0x1800087c0  pop     r15
0x1800087c2  pop     r14
0x1800087c4  pop     r13
0x1800087c6  pop     r12
0x1800087c8  pop     rdi
0x1800087c9  pop     rsi
0x1800087ca  pop     rbp
0x1800087cb  retn
0x1800087cc  mov     r14, [rbp+arg_10]
0x1800087d0  mov     r12d, r13d
0x1800087d3  mov     rdi, r14
0x1800087d6  cmp     eax, 101FAh
0x1800087db  jbe     short loc_180008846
0x1800087dd  cmp     [rdi], r13b
0x1800087e0  jnz     short loc_180008839
0x1800087e2  cmp     [rdi+1], r13b
0x1800087e6  jnz     short loc_180008839
0x1800087e8  cmp     byte ptr [rdi+2], 1
0x1800087ec  jnz     short loc_180008839
0x1800087ee  mov     al, [rdi+3]
0x1800087f1  cmp     al, 0BCh
0x1800087f3  jb      short loc_180008839
0x1800087f5  cmp     al, 0BEh
0x1800087f7  jz      short loc_180008839
0x1800087f9  xorps   xmm0, xmm0
0x1800087fc  lea     r8, [rbp+var_20]; struct tag_MPEG_PACKET_DATA *
0x180008800  xor     eax, eax
0x180008802  mov     edx, esi; unsigned int
0x180008804  mov     rcx, rdi; unsigned __int8 *
0x180008807  mov     [rbp+var_10], rax
0x18000880b  movups  xmmword ptr [rbp+var_20], xmm0
0x18000880f  call    ?ParseMPEG2Packet@@YAKPEBEKPEAUtag_MPEG_PACKET_DATA@@@Z; ParseMPEG2Packet(uchar const *,ulong,tag_MPEG_PACKET_DATA *)
0x180008814  cmp     eax, 0FFFFFFFFh
0x180008817  jz      short loc_180008892
0x180008819  cmp     eax, 4
0x18000881c  jbe     short loc_180008839
0x18000881e  mov     edx, dword ptr [rbp+var_20+4]; unsigned __int64
0x180008821  cmp     [rdx+rdi], r13b
0x180008825  jnz     short loc_180008839
0x180008827  lea     eax, [rdx+1]
0x18000882a  cmp     [rax+rdi], r13b
0x18000882e  jnz     short loc_180008839
0x180008830  lea     eax, [rdx+2]
0x180008833  test    byte ptr [rax+rdi], 0FEh
0x180008837  jz      short loc_18000888A
0x180008839  dec     esi
0x18000883b  inc     rdi
0x18000883e  cmp     esi, 101FAh
0x180008844  ja      short loc_1800087DD
0x180008846  mov     rcx, r14; void *
0x180008849  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000884e  test    r12d, r12d
0x180008851  jz      loc_1800087AF
0x180008857  mov     rax, [r15]
0x18000885a  xor     edx, edx
0x18000885c  mov     rcx, r15
0x18000885f  mov     rax, [rax+8]
0x180008863  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008868  mov     r9, r15; struct CParseReader *
0x18000886b  lea     rdx, [rbp+arg_10]; unsigned __int8 **
0x18000886f  mov     r8d, 300000h; unsigned int
0x180008875  call    ?NewInitBuffer@CSpltBaseParser@@IEAAIPEAPEAEIPEAVCParseReader@@@Z; CSpltBaseParser::NewInitBuffer(uchar * *,uint,CParseReader *)
0x18000887a  mov     edi, eax
0x18000887c  test    eax, eax
0x18000887e  jnz     short loc_18000889A
0x180008880  mov     ebx, 8004022Ah
0x180008885  jmp     loc_180008A7E
0x18000888a  mov     r12d, 1
0x180008890  jmp     short loc_180008846
0x180008892  mov     rcx, r14
0x180008895  jmp     loc_1800087AA
0x18000889a  mov     r14, [rbp+arg_10]
0x18000889e  mov     r12b, 0C0h
0x1800088a1  cmp     eax, 8Ch
0x1800088a6  jb      loc_180008A91
0x1800088ac  mov     ecx, [r14]
0x1800088af  mov     eax, ecx
0x1800088b1  and     eax, 0FFFFFFh
0x1800088b6  cmp     eax, 10000h
0x1800088bb  jnz     loc_180008A5F
0x1800088c1  mov     esi, ecx
0x1800088c3  and     ecx, 0FFFF00FFh
0x1800088c9  shr     esi, 8
0x1800088cc  and     esi, 0FF00FFh
0x1800088d2  shl     ecx, 8
0x1800088d5  or      esi, ecx
0x1800088d7  rol     esi, 10h
0x1800088da  cmp     esi, 1BAh
0x1800088e0  jnz     short loc_180008946
0x1800088e2  cmp     edi, 0Eh
0x1800088e5  jb      loc_180008A91
0x1800088eb  movzx   esi, byte ptr [r14+0Dh]
0x1800088f0  and     esi, 7
0x1800088f3  add     esi, 0Eh
0x1800088f6  cmp     esi, edi
0x1800088f8  ja      loc_180008A91
0x1800088fe  lea     r8, [rbx+498h]; __int64 *
0x180008905  cmp     [r8], r13
0x180008908  jge     short loc_18000891C
0x18000890a  lea     r9, [rbp+arg_8]; unsigned int *
0x18000890e  mov     [rbp+arg_8], r13d
0x180008912  mov     edx, edi; unsigned int
0x180008914  mov     rcx, r14; unsigned __int8 *
0x180008917  call    ?ParseMPEG2PackHeader@@YAKPEBEKPEA_JPEAK@Z; ParseMPEG2PackHeader(uchar const *,ulong,__int64 *,ulong *)
0x18000891c  movsd   xmm0, qword ptr [r14]
0x180008921  sub     edi, esi
0x180008923  movsd   qword ptr [rbx+4D4h], xmm0
0x18000892b  mov     eax, [r14+8]
0x18000892f  mov     [rbx+4DCh], eax
0x180008935  mov     al, [r14+0Ch]
0x180008939  mov     [rbx+4E0h], al
0x18000893f  mov     eax, esi
0x180008941  jmp     loc_180008A66
0x180008946  cmp     esi, 1BBh
0x18000894c  jnz     short loc_180008977
0x18000894e  mov     r8d, edi; unsigned int
0x180008951  mov     rdx, r14; unsigned __int8 *
0x180008954  mov     rcx, rbx; this
0x180008957  call    ?InitSystemHeader@CMPEG2Parser@@QEAAKPEBEK@Z; CMPEG2Parser::InitSystemHeader(uchar const *,ulong)
0x18000895c  cmp     eax, 4
0x18000895f  jbe     short loc_18000896A
0x180008961  sub     edi, eax
0x180008963  mov     eax, eax
0x180008965  jmp     loc_180008A66
0x18000896a  test    eax, eax
0x18000896c  jz      loc_180008A91
0x180008972  jmp     loc_180008A5F
0x180008977  cmp     esi, 1BCh
0x18000897d  jb      loc_180008A5F
0x180008983  cmp     esi, 1FFh
0x180008989  ja      loc_180008A5F
0x18000898f  xorps   xmm0, xmm0
0x180008992  lea     r8, [rbp+var_20]; struct tag_MPEG_PACKET_DATA *
0x180008996  xor     eax, eax
0x180008998  mov     edx, edi; unsigned int
0x18000899a  mov     rcx, r14; unsigned __int8 *
0x18000899d  mov     [rbp+var_10], rax
0x1800089a1  movups  xmmword ptr [rbp+var_20], xmm0
0x1800089a5  call    ?ParseMPEG2Packet@@YAKPEBEKPEAUtag_MPEG_PACKET_DATA@@@Z; ParseMPEG2Packet(uchar const *,ulong,tag_MPEG_PACKET_DATA *)
0x1800089aa  mov     r13d, eax
0x1800089ad  cmp     eax, 0FFFFFFFFh
0x1800089b0  jz      loc_180008A79
0x1800089b6  cmp     r13d, 4
0x1800089ba  jbe     loc_180008A5B
0x1800089c0  mov     rcx, [rbx]
0x1800089c3  mov     dl, sil
0x1800089c6  mov     r9d, dword ptr [rbp+var_20+4]
0x1800089ca  mov     r8d, dword ptr [rbp+var_20]
0x1800089ce  sub     r9d, dword ptr [rbp+var_20]
0x1800089d2  add     r8, r14
0x1800089d5  mov     rax, [rcx+88h]
0x1800089dc  mov     rcx, rbx
0x1800089df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800089e4  test    eax, eax
0x1800089e6  js      short loc_180008A53
0x1800089e8  cmp     dword ptr [rbp+var_20+8], 0
0x1800089ec  jz      short loc_180008A1E
0x1800089ee  cmp     dword ptr [rbx+490h], 0
0x1800089f5  mov     rax, [rbp+var_10]
0x1800089f9  jnz     short loc_180008A07
0x1800089fb  mov     dword ptr [rbx+490h], 1
0x180008a05  jmp     short loc_180008A10
0x180008a07  cmp     [rbx+478h], rax
0x180008a0e  jle     short loc_180008A1E
0x180008a10  mov     [rbx+478h], rax
0x180008a17  mov     [rbx+4C0h], rax
0x180008a1e  mov     al, sil
0x180008a21  and     al, 0F0h
0x180008a23  cmp     al, 0E0h
0x180008a25  jnz     short loc_180008A39
0x180008a27  cmp     byte ptr [rbx+4A9h], 0
0x180008a2e  jnz     short loc_180008A53
0x180008a30  mov     [rbx+4A9h], sil
0x180008a37  jmp     short loc_180008A53
0x180008a39  mov     al, sil
0x180008a3c  and     al, 0E0h
0x180008a3e  cmp     al, r12b
0x180008a41  jnz     short loc_180008A53
0x180008a43  cmp     byte ptr [rbx+4A8h], 0
0x180008a4a  jnz     short loc_180008A53
0x180008a4c  mov     [rbx+4A8h], sil
0x180008a53  sub     edi, r13d
0x180008a56  mov     rax, r13
0x180008a59  jmp     short loc_180008A66
0x180008a5b  test    eax, eax
0x180008a5d  jz      short loc_180008A8E
0x180008a5f  dec     edi
0x180008a61  mov     eax, 1
0x180008a66  cmp     edi, 8Ch
0x180008a6c  jb      short loc_180008A8E
0x180008a6e  add     r14, rax
0x180008a71  xor     r13d, r13d
0x180008a74  jmp     loc_1800088AC
0x180008a79  mov     ebx, 80070570h
0x180008a7e  mov     rcx, [rbp+arg_10]; void *
0x180008a82  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180008a87  mov     eax, ebx
0x180008a89  jmp     loc_1800087B4
0x180008a8e  xor     r13d, r13d
0x180008a91  mov     rcx, [rbp+arg_10]; void *
0x180008a95  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180008a9a  cmp     [rbx+498h], r13
0x180008aa1  jl      loc_1800087AF
0x180008aa7  cmp     [rbx+490h], r13d
0x180008aae  jz      loc_1800087AF
0x180008ab4  cmp     [rbx+2Ch], r13d
0x180008ab8  jnz     short loc_180008AC7
0x180008aba  cmp     [rbx+4A9h], r13b
0x180008ac1  jz      loc_1800087AF
0x180008ac7  mov     rax, [r15]
0x180008aca  mov     rcx, r15
0x180008acd  mov     rax, [rax+18h]
0x180008ad1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ad6  test    eax, eax
0x180008ad8  jz      short loc_180008AE5
0x180008ada  mov     rdx, r15; struct CParseReader *
0x180008add  mov     rcx, rbx; this
0x180008ae0  call    ?CalcDuration@CMPEG2Parser@@AEAAXPEAVCParseReader@@@Z; CMPEG2Parser::CalcDuration(CParseReader *)
0x180008ae5  mov     r8b, r13b
0x180008ae8  mov     r9d, 1
0x180008aee  movzx   edx, r12b
0x180008af2  lea     rax, [rbx-0B88h]
0x180008af9  shl     rdx, 4
0x180008afd  add     rax, rdx
0x180008b00  jz      loc_180008B9D
0x180008b06  test    r8b, r8b
0x180008b09  jz      short loc_180008B4E
0x180008b0b  movzx   eax, r8b
0x180008b0f  add     rax, rax
0x180008b12  mov     [rdx+rbx-0B80h], r9d
0x180008b1a  mov     rcx, [rbx+rax*8-0B88h]
0x180008b22  jmp     short loc_180008B34
0x180008b24  cmp     [rcx+0Ch], r13d
0x180008b28  jz      short loc_180008B3C
0x180008b2a  cmp     [rcx+9], r13b
0x180008b2e  jz      short loc_180008B3C
0x180008b30  mov     rcx, [rcx+28h]
0x180008b34  test    rcx, rcx
0x180008b37  jnz     short loc_180008B24
0x180008b39  mov     rcx, r13
0x180008b3c  mov     [rdx+rbx-0B88h], rcx
0x180008b44  mov     [rdx+rbx-0B7Ch], r9d
0x180008b4c  jmp     short loc_180008B51
0x180008b4e  mov     r8b, r12b
0x180008b51  lea     eax, [r12+10h]
0x180008b56  movzx   edx, al
0x180008b59  add     rdx, rdx
0x180008b5c  movzx   eax, r8b
0x180008b60  add     rax, rax
0x180008b63  mov     [rbx+rdx*8-0B80h], r9d
0x180008b6b  mov     rcx, [rbx+rax*8-0B88h]
0x180008b73  jmp     short loc_180008B85
0x180008b75  cmp     [rcx+0Ch], r13d
0x180008b79  jz      short loc_180008B8D
0x180008b7b  cmp     [rcx+9], r13b
0x180008b7f  jz      short loc_180008B8D
0x180008b81  mov     rcx, [rcx+28h]
0x180008b85  test    rcx, rcx
0x180008b88  jnz     short loc_180008B75
0x180008b8a  mov     rcx, r13
0x180008b8d  mov     [rbx+rdx*8-0B88h], rcx
0x180008b95  mov     [rbx+rdx*8-0B7Ch], r9d
0x180008b9d  add     r12b, r9b
0x180008ba0  cmp     r12b, 0D0h
0x180008ba4  jb      loc_180008AEE
0x180008baa  xor     eax, eax
  ... truncated ...
```
