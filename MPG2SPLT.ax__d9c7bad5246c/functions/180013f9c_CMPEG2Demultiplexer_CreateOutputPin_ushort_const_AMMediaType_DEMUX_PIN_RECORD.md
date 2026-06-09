# CMPEG2Demultiplexer::CreateOutputPin_(ushort const *,_AMMediaType *,DEMUX_PIN_RECORD * *)

- ea: `0x180013f9c`
- end: `0x1800140b6`
- name: `?CreateOutputPin_@CMPEG2Demultiplexer@@AEAAJPEBGPEAU_AMMediaType@@PEAPEAUDEMUX_PIN_RECORD@@@Z`
- size: `282`
- prototype: `__int64 __fastcall(CMPEG2Demultiplexer *__hidden this, const unsigned __int16 *, struct _AMMediaType *, struct DEMUX_PIN_RECORD **)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x1800170b4`
- `0x18001be80`
- `0x18001bf80`
- `0x18001e880`

## callees

- `0x180013f9c`
- `0x1800140bc`
- `0x180018b7c`

## import_xrefs

- `KERNEL32!MulDiv` at `0x180014043`
- `KERNEL32!MulDiv` at `0x180014043`

## pseudocode

```c
__int64 __fastcall CMPEG2Demultiplexer::CreateOutputPin_(
        CMPEG2Demultiplexer *this,
        struct _AMMediaType *a2,
        struct _AMMediaType *a3,
        struct DEMUX_PIN_RECORD **a4)
{
  unsigned int v8; // esi
  unsigned int v9; // edi
  unsigned int StreamAvgBitRate; // eax
  __int64 v11; // r8
  __int64 v12; // r10
  unsigned int v13; // eax
  int v14; // eax
  int v16; // [rsp+20h] [rbp-68h]
  int v17; // [rsp+28h] [rbp-60h]

  v8 = 0x2000;
  if ( *(_OWORD *)&a3->majortype == *(_OWORD *)&MEDIATYPE_Video
    && *(_QWORD *)&a3->subtype.Data1 == *(_QWORD *)&MEDIASUBTYPE_MPEG2_VIDEO.Data1
    && *(_QWORD *)a3->subtype.Data4 == *(_QWORD *)MEDIASUBTYPE_MPEG2_VIDEO.Data4
    && *(_QWORD *)&a3->formattype.Data1 == *(_QWORD *)&FORMAT_MPEG2Video.Data1
    && *(_QWORD *)a3->formattype.Data4 == *(_QWORD *)FORMAT_MPEG2Video.Data4
    && Mpeg2Demultiplexer::GetStreamAvgBitRate((Mpeg2Demultiplexer *)a3, a2) - 1 <= 0x98967F )
  {
    v8 = 2048;
  }
  v9 = 64;
  StreamAvgBitRate = Mpeg2Demultiplexer::GetStreamAvgBitRate((Mpeg2Demultiplexer *)a3, a2);
  if ( StreamAvgBitRate )
  {
    v13 = MulDiv((StreamAvgBitRate >> 3) / v8, 1500, 1000);
    v11 = *(_QWORD *)MEDIATYPE_Video.Data4;
    v12 = *(_QWORD *)&MEDIATYPE_Video.Data1;
    if ( v13 < 0x40 )
      v13 = 64;
    v9 = v13;
  }
  if ( *(_QWORD *)&a3->majortype.Data1 == v12 && *(_QWORD *)a3->majortype.Data4 == v11
    || *(_QWORD *)&a3->majortype.Data1 == *(_QWORD *)&MEDIATYPE_Audio.Data1
    && *(_QWORD *)a3->majortype.Data4 == *(_QWORD *)MEDIATYPE_Audio.Data4 )
  {
    v14 = 256;
    if ( v9 > 0x100 )
      v14 = v9;
    v9 = v14;
  }
  return CMPEG2Demultiplexer::CreatePin_(
           this,
           (const unsigned __int16 *)a2,
           (enum _PinDirection)v11,
           a3,
           v16,
           v17,
           v8,
           v9,
           a4);
}

```

## disassembly

```asm
0x180013f9c  push    rbx
0x180013f9e  push    rbp
0x180013f9f  push    rsi
0x180013fa0  push    rdi
0x180013fa1  push    r14
0x180013fa3  push    r15
0x180013fa5  sub     rsp, 58h
0x180013fa9  mov     r10, qword ptr cs:MEDIATYPE_Video.Data1
0x180013fb0  mov     rbx, r8
0x180013fb3  mov     r8, qword ptr cs:MEDIATYPE_Video.Data4
0x180013fba  mov     rbp, r9
0x180013fbd  mov     r14, rdx
0x180013fc0  mov     r15, rcx
0x180013fc3  mov     esi, 2000h
0x180013fc8  cmp     [rbx], r10
0x180013fcb  jnz     short loc_18001401E
0x180013fcd  cmp     [rbx+8], r8
0x180013fd1  jnz     short loc_18001401E
0x180013fd3  mov     rax, [rbx+10h]
0x180013fd7  cmp     rax, qword ptr cs:MEDIASUBTYPE_MPEG2_VIDEO.Data1
0x180013fde  jnz     short loc_18001401E
0x180013fe0  mov     rax, [rbx+18h]
0x180013fe4  cmp     rax, qword ptr cs:MEDIASUBTYPE_MPEG2_VIDEO.Data4
0x180013feb  jnz     short loc_18001401E
0x180013fed  mov     rax, [rbx+2Ch]
0x180013ff1  cmp     rax, qword ptr cs:FORMAT_MPEG2Video.Data1
0x180013ff8  jnz     short loc_18001401E
0x180013ffa  mov     rax, [rbx+34h]
0x180013ffe  cmp     rax, qword ptr cs:FORMAT_MPEG2Video.Data4
0x180014005  jnz     short loc_18001401E
0x180014007  mov     rcx, rbx; this
0x18001400a  call    ?GetStreamAvgBitRate@Mpeg2Demultiplexer@@YAKPEAU_AMMediaType@@@Z; Mpeg2Demultiplexer::GetStreamAvgBitRate(_AMMediaType *)
0x18001400f  dec     eax
0x180014011  mov     ecx, 800h
0x180014016  cmp     eax, 98967Fh
0x18001401b  cmovbe  esi, ecx
0x18001401e  mov     rcx, rbx; this
0x180014021  mov     edi, 40h ; '@'
0x180014026  call    ?GetStreamAvgBitRate@Mpeg2Demultiplexer@@YAKPEAU_AMMediaType@@@Z; Mpeg2Demultiplexer::GetStreamAvgBitRate(_AMMediaType *)
0x18001402b  test    eax, eax
0x18001402d  jz      short loc_18001405E
0x18001402f  xor     edx, edx
0x180014031  shr     eax, 3
0x180014034  div     esi
0x180014036  mov     edx, 5DCh; nNumerator
0x18001403b  mov     r8d, 3E8h; nDenominator
0x180014041  mov     ecx, eax; nNumber
0x180014043  call    cs:__imp_MulDiv
0x180014049  mov     r8, qword ptr cs:MEDIATYPE_Video.Data4; enum _PinDirection
0x180014050  cmp     eax, edi
0x180014052  mov     r10, qword ptr cs:MEDIATYPE_Video.Data1
0x180014059  cmovb   eax, edi
0x18001405c  mov     edi, eax
0x18001405e  cmp     [rbx], r10
0x180014061  jnz     short loc_180014069
0x180014063  cmp     [rbx+8], r8
0x180014067  jz      short loc_180014082
0x180014069  mov     rax, [rbx]
0x18001406c  cmp     rax, qword ptr cs:MEDIATYPE_Audio.Data1
0x180014073  jnz     short loc_18001408E
0x180014075  mov     rax, [rbx+8]
0x180014079  cmp     rax, qword ptr cs:MEDIATYPE_Audio.Data4
0x180014080  jnz     short loc_18001408E
0x180014082  mov     eax, 100h
0x180014087  cmp     edi, eax
0x180014089  cmova   eax, edi
0x18001408c  mov     edi, eax
0x18001408e  mov     [rsp+88h+var_48], rbp; struct DEMUX_PIN_RECORD **
0x180014093  mov     r9, rbx; struct _AMMediaType *
0x180014096  mov     [rsp+88h+var_50], edi; unsigned int
0x18001409a  mov     rdx, r14; unsigned __int16 *
0x18001409d  mov     rcx, r15; this
0x1800140a0  mov     [rsp+88h+var_58], esi; unsigned int
0x1800140a4  call    ?CreatePin_@CMPEG2Demultiplexer@@AEAAJPEBGW4_PinDirection@@PEAU_AMMediaType@@JHKKPEAPEAUDEMUX_PIN_RECORD@@@Z; CMPEG2Demultiplexer::CreatePin_(ushort const *,_PinDirection,_AMMediaType *,long,int,ulong,ulong,DEMUX_PIN_RECORD * *)
0x1800140a9  add     rsp, 58h
0x1800140ad  pop     r15
0x1800140af  pop     r14
0x1800140b1  pop     rdi
0x1800140b2  pop     rsi
0x1800140b3  pop     rbp
0x1800140b4  pop     rbx
0x1800140b5  retn
```
