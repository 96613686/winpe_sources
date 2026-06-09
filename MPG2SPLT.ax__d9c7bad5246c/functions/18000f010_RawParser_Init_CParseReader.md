# RawParser::Init(CParseReader *)

- ea: `0x18000f010`
- end: `0x18000f1ad`
- name: `?Init@RawParser@@UEAAJPEAVCParseReader@@@Z`
- size: `413`
- prototype: `int(RawParser *__hidden this, struct CParseReader *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops`

## callees

- `0x180001048`
- `0x180001460`
- `0x180001e98`
- `0x18000ad44`
- `0x18000b3ac`
- `0x18000d148`
- `0x18000f010`
- `0x18000f220`
- `0x180034010`

## pseudocode

```c
__int64 __fastcall RawParser::Init(RawParser *this, struct CParseReader *a2)
{
  void (__fastcall **v4)(_QWORD, _QWORD); // rax
  CSpltBaseParser *v5; // rcx
  unsigned int inited; // eax
  unsigned int v7; // ebx
  unsigned __int8 *v9; // rdi
  unsigned int v10; // ebx
  RawParser *v11; // rcx
  int v12; // edx
  __int64 v13; // rcx
  unsigned __int8 *Src; // [rsp+20h] [rbp-168h] BYREF
  _BYTE v15[320]; // [rsp+30h] [rbp-158h] BYREF

  (**(void (__fastcall ***)(struct CParseReader *, char *))a2)(a2, (char *)this + 120);
  v4 = *(void (__fastcall ***)(_QWORD, _QWORD))a2;
  Src = 0;
  ((void (__fastcall **)(struct CParseReader *, _QWORD))v4)[1](a2, 0);
  inited = CSpltBaseParser::NewInitBuffer(v5, &Src, 0x80000u, a2);
  v7 = inited;
  if ( !inited )
    return 2147746346LL;
  v9 = Src;
  if ( inited < 0x8C )
  {
LABEL_7:
    v10 = -2147220950;
  }
  else
  {
    while ( (*(_DWORD *)v9 & 0xFFFFFF) != 0x10000
         || __ROL4__(((*(_DWORD *)v9 & 0xFFFF00FF) << 8) | (*(_DWORD *)v9 >> 8) & 0xFF00FF, 16) != 435 )
    {
      ++v9;
      if ( --v7 < 0x8C )
        goto LABEL_7;
    }
    memset_0(v15, 0, sizeof(v15));
    if ( (unsigned int)ParseSequenceHeader(v9, v7, (struct SEQHDR_INFO *)v15)
      && (int)RawParser::ParseMPEG2Extention(v11, v9, v7, (struct SEQHDR_INFO *)v15) >= 0 )
    {
      (***((void (__fastcall ****)(_QWORD, unsigned __int16 near **, char *))this + 1))(
        *((_QWORD *)this + 1),
        &RawParser::szOutputName,
        (char *)this + 24);
      GetMpeg2VideoMediaType((RawParser *)((char *)this + 32), v12, (const struct SEQHDR_INFO *)v15, 0);
      (*(void (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 3) + 16LL))(
        *((_QWORD *)this + 3),
        (char *)this + 32);
      v13 = *((_QWORD *)this + 3);
      *((_OWORD *)this + 3) = MMSubTypeMPEG2Payload;
      (*(void (__fastcall **)(__int64, char *))(*(_QWORD *)v13 + 16LL))(v13, (char *)this + 32);
      v10 = 0;
    }
    else
    {
      v10 = -2147220928;
    }
  }
  operator delete(Src);
  return v10;
}

```

## disassembly

```asm
0x18000f010  mov     [rsp+arg_10], rbx
0x18000f015  mov     [rsp+arg_18], rsi
0x18000f01a  push    rdi
0x18000f01b  sub     rsp, 180h
0x18000f022  mov     rax, cs:__security_cookie
0x18000f029  xor     rax, rsp
0x18000f02c  mov     [rsp+188h+var_18], rax
0x18000f034  mov     rax, [rdx]
0x18000f037  mov     rbx, rdx
0x18000f03a  mov     rsi, rcx
0x18000f03d  lea     rdx, [rcx+78h]
0x18000f041  mov     rcx, rbx
0x18000f044  mov     rax, [rax]
0x18000f047  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f04c  mov     rax, [rbx]
0x18000f04f  xor     edx, edx
0x18000f051  mov     rcx, rbx
0x18000f054  mov     [rsp+188h+Src], 0
0x18000f05d  mov     rax, [rax+8]
0x18000f061  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f066  mov     r9, rbx; struct CParseReader *
0x18000f069  lea     rdx, [rsp+188h+Src]; unsigned __int8 **
0x18000f06e  mov     r8d, 80000h; unsigned int
0x18000f074  call    ?NewInitBuffer@CSpltBaseParser@@IEAAIPEAPEAEIPEAVCParseReader@@@Z; CSpltBaseParser::NewInitBuffer(uchar * *,uint,CParseReader *)
0x18000f079  mov     ebx, eax
0x18000f07b  test    eax, eax
0x18000f07d  jnz     short loc_18000F086
0x18000f07f  mov     eax, 8004022Ah
0x18000f084  jmp     short loc_18000F0DD
0x18000f086  mov     rdi, [rsp+188h+Src]
0x18000f08b  mov     edx, 8Ch; unsigned __int64
0x18000f090  cmp     eax, edx
0x18000f092  jb      short loc_18000F0CC
0x18000f094  mov     ecx, [rdi]
0x18000f096  mov     eax, ecx
0x18000f098  and     eax, 0FFFFFFh
0x18000f09d  cmp     eax, 10000h
0x18000f0a2  jnz     short loc_18000F0C3
0x18000f0a4  mov     eax, ecx
0x18000f0a6  and     ecx, 0FFFF00FFh
0x18000f0ac  shr     eax, 8
0x18000f0af  and     eax, 0FF00FFh
0x18000f0b4  shl     ecx, 8
0x18000f0b7  or      eax, ecx
0x18000f0b9  rol     eax, 10h
0x18000f0bc  cmp     eax, 1B3h
0x18000f0c1  jz      short loc_18000F102
0x18000f0c3  inc     rdi
0x18000f0c6  dec     ebx
0x18000f0c8  cmp     ebx, edx
0x18000f0ca  jnb     short loc_18000F094
0x18000f0cc  mov     ebx, 8004022Ah
0x18000f0d1  mov     rcx, [rsp+188h+Src]; void *
0x18000f0d6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000f0db  mov     eax, ebx
0x18000f0dd  mov     rcx, [rsp+188h+var_18]
0x18000f0e5  xor     rcx, rsp; StackCookie
0x18000f0e8  call    __security_check_cookie
0x18000f0ed  lea     r11, [rsp+188h+var_8]
0x18000f0f5  mov     rbx, [r11+20h]
0x18000f0f9  mov     rsi, [r11+28h]
0x18000f0fd  mov     rsp, r11
0x18000f100  pop     rdi
0x18000f101  retn
0x18000f102  xor     edx, edx; Val
0x18000f104  lea     rcx, [rsp+188h+var_158]; void *
0x18000f109  mov     r8d, 140h; Size
0x18000f10f  call    memset_0
0x18000f114  lea     r8, [rsp+188h+var_158]; struct SEQHDR_INFO *
0x18000f119  mov     edx, ebx; int
0x18000f11b  mov     rcx, rdi; Src
0x18000f11e  call    ?ParseSequenceHeader@@YAHPEBEJPEAUSEQHDR_INFO@@@Z; ParseSequenceHeader(uchar const *,long,SEQHDR_INFO *)
0x18000f123  test    eax, eax
0x18000f125  jz      short loc_18000F1A3
0x18000f127  lea     r9, [rsp+188h+var_158]; struct SEQHDR_INFO *
0x18000f12c  mov     r8d, ebx; unsigned int
0x18000f12f  mov     rdx, rdi; unsigned __int8 *
0x18000f132  call    ?ParseMPEG2Extention@RawParser@@AEAAJPEBEKAEAUSEQHDR_INFO@@@Z; RawParser::ParseMPEG2Extention(uchar const *,ulong,SEQHDR_INFO &)
0x18000f137  test    eax, eax
0x18000f139  js      short loc_18000F1A3
0x18000f13b  mov     rcx, [rsi+8]
0x18000f13f  lea     rdi, [rsi+18h]
0x18000f143  mov     r8, rdi
0x18000f146  lea     rdx, ?szOutputName@RawParser@@0PAGA; "Video"
0x18000f14d  mov     rax, [rcx]
0x18000f150  mov     rax, [rax]
0x18000f153  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f158  lea     rbx, [rsi+20h]
0x18000f15c  xor     r9d, r9d; struct tag_MPEG2_VIDEO_DATA *
0x18000f15f  mov     rcx, rbx; struct CMediaType *
0x18000f162  lea     r8, [rsp+188h+var_158]; struct SEQHDR_INFO *
0x18000f167  call    ?GetMpeg2VideoMediaType@@YAJPEAVCMediaType@@HPEBUSEQHDR_INFO@@PEAUtag_MPEG2_VIDEO_DATA@@@Z; GetMpeg2VideoMediaType(CMediaType *,int,SEQHDR_INFO const *,tag_MPEG2_VIDEO_DATA *)
0x18000f16c  mov     rcx, [rdi]
0x18000f16f  mov     rdx, rbx
0x18000f172  mov     rax, [rcx]
0x18000f175  mov     rax, [rax+10h]
0x18000f179  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f17e  movups  xmm0, cs:MMSubTypeMPEG2Payload
0x18000f185  mov     rcx, [rdi]
0x18000f188  mov     rdx, rbx
0x18000f18b  movdqu  xmmword ptr [rsi+30h], xmm0
0x18000f190  mov     rax, [rcx]
0x18000f193  mov     rax, [rax+10h]
0x18000f197  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f19c  xor     ebx, ebx
0x18000f19e  jmp     loc_18000F0D1
0x18000f1a3  mov     ebx, 80040240h
0x18000f1a8  jmp     loc_18000F0D1
```
