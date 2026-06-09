# CVideoObjectDecoder::DecodeIMBAcPred(CMBMode *,uchar *,uchar *,uchar *,long *,long * *,long,long,long)

- ea: `0x18000ec38`
- end: `0x18000f024`
- name: `?DecodeIMBAcPred@CVideoObjectDecoder@@AEAAJPEAVCMBMode@@PEAE11PEAJPEAPEAJJJJ@Z`
- size: `1004`
- prototype: `__int64 __fastcall(CVideoObjectDecoder *this, struct CMBMode *, unsigned __int8 *, unsigned __int8 *, unsigned __int8 *, int *, int **, int, int, int)`
- caller_count: `6`
- callee_count: `6`
- tags: ``

## callers

- `0x18000f500`
- `0x18000fa90`
- `0x180010118`
- `0x1800106c0`
- `0x180011040`
- `0x180011aa8`

## callees

- `0x18000d6d8`
- `0x18000d7dc`
- `0x18000da60`
- `0x18000db00`
- `0x18000db8c`
- `0x18000ec38`

## pseudocode

```c
__int64 __fastcall CVideoObjectDecoder::DecodeIMBAcPred(
        CVideoObjectDecoder *this,
        struct CMBMode *a2,
        unsigned __int8 *a3,
        unsigned __int8 *a4,
        unsigned __int8 *a5,
        int *a6,
        int **a7,
        int a8,
        int a9,
        int a10)
{
  int v11; // r13d
  int **v12; // r15
  int *v14; // rsi
  int v16; // edi
  int v17; // eax
  int v18; // edx
  int *v19; // r8
  __int64 result; // rax
  int *v21; // rax
  int *v22; // r9
  int v23; // edx
  int v24; // edx
  int v25; // ecx
  int v26; // eax
  int v27; // eax
  int v28; // edx
  int v29; // eax
  int v30; // edx
  int *v31; // r8
  int v32; // r14d
  int *v33; // rax
  int *v34; // r9
  int v35; // edx
  int v36; // edx
  int v37; // ecx
  int v38; // eax
  int v39; // eax
  int v40; // edx
  struct CDCTTableInfo_Dec *v41; // rdx
  int v42; // r9d
  int v43; // edx
  int *v44; // r8
  int *v45; // rdi
  int *v46; // rax
  int *v47; // r9
  int v48; // edx
  int v49; // edx
  int v50; // eax
  int v51; // ecx
  int v52; // eax
  int v53; // edx
  struct CDCTTableInfo_Dec *v54; // rdx
  struct CDCTTableInfo_Dec *v55; // [rsp+50h] [rbp-20h]
  struct CDCTTableInfo_Dec *v56; // [rsp+58h] [rbp-18h]
  int v57[4]; // [rsp+60h] [rbp-10h]
  int v58; // [rsp+B0h] [rbp+40h] BYREF
  int v59; // [rsp+C0h] [rbp+50h] BYREF
  unsigned __int8 *v60; // [rsp+C8h] [rbp+58h]

  v60 = a4;
  v11 = a9;
  v12 = a7;
  v14 = a6;
  v56 = (struct CDCTTableInfo_Dec *)*((_QWORD *)this + 439);
  v16 = 0;
  v55 = (struct CDCTTableInfo_Dec *)*((_QWORD *)this + 440);
  v17 = a8;
  *((_DWORD *)this + 896) = 0;
  v57[2] = v17;
  v58 = 0;
  v59 = 0;
  v57[0] = a10;
  v57[1] = v11;
  v57[3] = a10;
  while ( 1 )
  {
    if ( *((int *)this + 2) < 3 )
    {
      if ( *((_DWORD *)this + 2) == 2 )
        CVideoObjectDecoder::decodeIntraDCAcPred(this, &v58, &gDecodeCodeTableIntraDCy, 7);
      else
        CVideoObjectDecoder::decodeIntraDCAcPred_MPEG4(this, &v58, &gDecodeCodeTableIntraDCMPEG4y, 11);
    }
    else
    {
      CVideoObjectDecoder::decodeIntraDCAcPredMSV(this, &v58, *((struct Huffman **)this + 329), (int)a4);
    }
    result = (unsigned int)v58;
    if ( v58 )
      break;
    v21 = CVideoObjectDecoder::decodeDiffDCTCoef(this, v18, v19, v12, a8, v11, v57[v16], &v59);
    v22 = v21;
    if ( *((_DWORD *)this + 2) )
    {
      v23 = *v21 + *((_DWORD *)this + 404);
      *v14 = v23;
      v24 = *((_DWORD *)this + 91) * v23;
    }
    else
    {
      v25 = *v21;
      v26 = *((int *)this + 91) >> 1;
      v27 = v25 < 0 ? v25 - v26 : v25 + v26;
      v28 = v27 / *((_DWORD *)this + 91) + *((_DWORD *)this + 404);
      *v14 = v28;
      v24 = *((_DWORD *)this + 91) * v28;
      *v14 = v24;
    }
    *((_DWORD *)this + 404) = v24;
    result = CVideoObjectDecoder::decodeIntraBlockAcPred(this, v55, a2, a3, *((_DWORD *)this + 84), v16, v14, v22, v59);
    v58 = result;
    if ( (_DWORD)result )
      break;
    v29 = 8;
    if ( v16 == 1 )
      v29 = *((_DWORD *)this + 924);
    v14 += 16;
    a3 += v29;
    v12 += 6;
    if ( (unsigned int)++v16 >= 4 )
    {
      if ( *((int *)this + 2) < 3 )
      {
        if ( *((_DWORD *)this + 2) == 2 )
          CVideoObjectDecoder::decodeIntraDCAcPred(this, &v58, &gDecodeCodeTableIntraDCc, 8);
        else
          CVideoObjectDecoder::decodeIntraDCAcPred_MPEG4(this, &v58, &gDecodeCodeTableIntraDCMPEG4c, 12);
      }
      else
      {
        CVideoObjectDecoder::decodeIntraDCAcPredMSV(this, &v58, *((struct Huffman **)this + 330), (int)a4);
      }
      result = (unsigned int)v58;
      if ( !v58 )
      {
        v32 = a8;
        v33 = CVideoObjectDecoder::decodeDiffDCTCoef(this, v30, v31, v12, a8, v11, a10, &v59);
        v34 = v33;
        if ( *((_DWORD *)this + 2) )
        {
          v35 = *v33 + *((_DWORD *)this + 404);
          *v14 = v35;
          v36 = *((_DWORD *)this + 92) * v35;
        }
        else
        {
          v37 = *v33;
          v38 = *((int *)this + 92) >> 1;
          if ( v37 < 0 )
            v39 = v37 - v38;
          else
            v39 = v37 + v38;
          v40 = v39 / *((_DWORD *)this + 92) + *((_DWORD *)this + 404);
          *v14 = v40;
          v36 = *((_DWORD *)this + 92) * v40;
          *v14 = v36;
        }
        *((_DWORD *)this + 404) = v36;
        v41 = v56;
        if ( !*((_DWORD *)this + 2) )
          v41 = v55;
        result = CVideoObjectDecoder::decodeIntraBlockAcPred(
                   this,
                   v41,
                   a2,
                   v60,
                   *((_DWORD *)this + 85),
                   4,
                   v14,
                   v34,
                   v59);
        v58 = result;
        if ( !(_DWORD)result )
        {
          if ( *((int *)this + 2) < 3 )
          {
            if ( *((_DWORD *)this + 2) == 2 )
              CVideoObjectDecoder::decodeIntraDCAcPred(this, &v58, &gDecodeCodeTableIntraDCc, 8);
            else
              CVideoObjectDecoder::decodeIntraDCAcPred_MPEG4(this, &v58, &gDecodeCodeTableIntraDCMPEG4c, 12);
          }
          else
          {
            CVideoObjectDecoder::decodeIntraDCAcPredMSV(this, &v58, *((struct Huffman **)this + 330), v42);
          }
          result = (unsigned int)v58;
          if ( !v58 )
          {
            v45 = v14 + 16;
            v46 = CVideoObjectDecoder::decodeDiffDCTCoef(this, v43, v44, v12 + 6, v32, v11, a10, &v59);
            v47 = v46;
            if ( *((_DWORD *)this + 2) )
            {
              v48 = *v46 + *((_DWORD *)this + 404);
              *v45 = v48;
              v49 = *((_DWORD *)this + 92) * v48;
            }
            else
            {
              v50 = *v46;
              v51 = *((int *)this + 92) >> 1;
              if ( v50 < 0 )
                v52 = v50 - v51;
              else
                v52 = v51 + v50;
              v53 = v52 / *((_DWORD *)this + 92) + *((_DWORD *)this + 404);
              *v45 = v53;
              v49 = *((_DWORD *)this + 92) * v53;
              *v45 = v49;
            }
            *((_DWORD *)this + 404) = v49;
            v54 = v56;
            if ( !*((_DWORD *)this + 2) )
              v54 = v55;
            return CVideoObjectDecoder::decodeIntraBlockAcPred(
                     this,
                     v54,
                     a2,
                     a5,
                     *((_DWORD *)this + 85),
                     5,
                     v14 + 16,
                     v47,
                     v59);
          }
        }
      }
      return result;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000ec38  mov     [rsp-38h+arg_8], rbx
0x18000ec3d  mov     [rsp-38h+arg_18], r9
0x18000ec42  push    rbp
0x18000ec43  push    rsi
0x18000ec44  push    rdi
0x18000ec45  push    r12
0x18000ec47  push    r13
0x18000ec49  push    r14
0x18000ec4b  push    r15
0x18000ec4d  mov     rbp, rsp
0x18000ec50  sub     rsp, 70h
0x18000ec54  mov     rax, [rcx+0DB8h]
0x18000ec5b  mov     r12, rdx
0x18000ec5e  mov     r13d, [rbp+arg_40]
0x18000ec65  xor     edx, edx
0x18000ec67  mov     r15, [rbp+arg_30]
0x18000ec6b  mov     rbx, rcx
0x18000ec6e  mov     rsi, [rbp+arg_28]
0x18000ec72  mov     r14, r8
0x18000ec75  mov     [rbp+var_18], rax
0x18000ec79  mov     edi, edx
0x18000ec7b  mov     rax, [rcx+0DC0h]
0x18000ec82  mov     [rbp+var_20], rax
0x18000ec86  mov     eax, [rbp+arg_38]
0x18000ec89  mov     [rcx+0E00h], edx
0x18000ec8f  mov     ecx, [rbp+arg_48]
0x18000ec95  mov     [rbp+var_8], eax
0x18000ec98  mov     [rbp+arg_0], edx
0x18000ec9b  mov     [rbp+arg_10], edx
0x18000ec9e  mov     [rbp+var_10], ecx
0x18000eca1  mov     [rbp+var_C], r13d
0x18000eca5  mov     [rbp+var_4], ecx
0x18000eca8  cmp     dword ptr [rbx+8], 3
0x18000ecac  lea     rdx, [rbp+arg_0]; int *
0x18000ecb0  mov     rcx, rbx; this
0x18000ecb3  jl      short loc_18000ECC3
0x18000ecb5  mov     r8, [rbx+0A48h]; struct Huffman *
0x18000ecbc  call    ?decodeIntraDCAcPredMSV@CVideoObjectDecoder@@AEAAXPEAJPEAVHuffman@@J@Z; CVideoObjectDecoder::decodeIntraDCAcPredMSV(long *,Huffman *,long)
0x18000ecc1  jmp     short loc_18000ECEF
0x18000ecc3  cmp     dword ptr [rbx+8], 2
0x18000ecc7  jnz     short loc_18000ECDD
0x18000ecc9  mov     r9d, 7; int
0x18000eccf  lea     r8, ?gDecodeCodeTableIntraDCy@@3PAEA; unsigned __int8 *
0x18000ecd6  call    ?decodeIntraDCAcPred@CVideoObjectDecoder@@AEAAXPEAJQEAEJ@Z; CVideoObjectDecoder::decodeIntraDCAcPred(long *,uchar * const,long)
0x18000ecdb  jmp     short loc_18000ECEF
0x18000ecdd  mov     r9d, 0Bh; int
0x18000ece3  lea     r8, ?gDecodeCodeTableIntraDCMPEG4y@@3PAEA; unsigned __int8 *
0x18000ecea  call    ?decodeIntraDCAcPred_MPEG4@CVideoObjectDecoder@@AEAAXPEAJQEAEJ@Z; CVideoObjectDecoder::decodeIntraDCAcPred_MPEG4(long *,uchar * const,long)
0x18000ecef  mov     eax, [rbp+arg_0]
0x18000ecf2  test    eax, eax
0x18000ecf4  jnz     loc_18000F00C
0x18000ecfa  mov     eax, edi
0x18000ecfc  lea     rcx, [rbp+arg_10]
0x18000ed00  mov     [rsp+70h+var_38], rcx; int *
0x18000ed05  mov     r9, r15; int **
0x18000ed08  mov     rcx, rbx; this
0x18000ed0b  mov     eax, [rbp+rax*4+var_10]
0x18000ed0f  mov     dword ptr [rsp+70h+var_40], eax; int
0x18000ed13  mov     eax, [rbp+arg_38]
0x18000ed16  mov     [rsp+70h+var_48], r13d; int
0x18000ed1b  mov     [rsp+70h+var_50], eax; int
0x18000ed1f  call    ?decodeDiffDCTCoef@CVideoObjectDecoder@@AEAAPEAJJPEAJPEAPEAJJJJAEAJ@Z; CVideoObjectDecoder::decodeDiffDCTCoef(long,long *,long * *,long,long,long,long &)
0x18000ed24  cmp     dword ptr [rbx+8], 0
0x18000ed28  mov     r9, rax
0x18000ed2b  jz      short loc_18000ED40
0x18000ed2d  mov     edx, [rbx+650h]
0x18000ed33  add     edx, [rax]
0x18000ed35  mov     [rsi], edx
0x18000ed37  imul    edx, [rbx+16Ch]
0x18000ed3e  jmp     short loc_18000ED73
0x18000ed40  mov     ecx, [rax]
0x18000ed42  mov     r8d, [rbx+16Ch]
0x18000ed49  mov     eax, r8d
0x18000ed4c  sar     eax, 1
0x18000ed4e  test    ecx, ecx
0x18000ed50  js      short loc_18000ED56
0x18000ed52  add     eax, ecx
0x18000ed54  jmp     short loc_18000ED5A
0x18000ed56  sub     ecx, eax
0x18000ed58  mov     eax, ecx
0x18000ed5a  cdq
0x18000ed5b  idiv    r8d
0x18000ed5e  mov     edx, [rbx+650h]
0x18000ed64  add     edx, eax
0x18000ed66  mov     ecx, eax
0x18000ed68  mov     [rsi], edx
0x18000ed6a  imul    edx, [rbx+16Ch]
0x18000ed71  mov     [rsi], edx
0x18000ed73  mov     [rbx+650h], edx
0x18000ed79  mov     r8, r12; struct CMBMode *
0x18000ed7c  mov     eax, [rbp+arg_10]
0x18000ed7f  mov     rcx, rbx; this
0x18000ed82  mov     rdx, [rbp+var_20]; struct CDCTTableInfo_Dec *
0x18000ed86  mov     [rsp+70h+var_30], eax; int
0x18000ed8a  mov     eax, [rbx+150h]
0x18000ed90  mov     [rsp+70h+var_38], r9; int *
0x18000ed95  mov     r9, r14; unsigned __int8 *
0x18000ed98  mov     [rsp+70h+var_40], rsi; int *
0x18000ed9d  mov     [rsp+70h+var_48], edi; int
0x18000eda1  mov     [rsp+70h+var_50], eax; int
0x18000eda5  call    ?decodeIntraBlockAcPred@CVideoObjectDecoder@@AEAAJPEAVCDCTTableInfo_Dec@@PEAVCMBMode@@PEAEJJPEAJ3J@Z; CVideoObjectDecoder::decodeIntraBlockAcPred(CDCTTableInfo_Dec *,CMBMode *,uchar *,long,long,long *,long *,long)
0x18000edaa  mov     [rbp+arg_0], eax
0x18000edad  test    eax, eax
0x18000edaf  jnz     loc_18000F00C
0x18000edb5  mov     eax, 8
0x18000edba  cmp     edi, 1
0x18000edbd  jnz     short loc_18000EDC5
0x18000edbf  mov     eax, [rbx+0E70h]
0x18000edc5  cdqe
0x18000edc7  add     rsi, 40h ; '@'
0x18000edcb  add     r14, rax
0x18000edce  add     r15, 30h ; '0'
0x18000edd2  inc     edi
0x18000edd4  cmp     edi, 4
0x18000edd7  jb      loc_18000ECA8
0x18000eddd  cmp     dword ptr [rbx+8], 3
0x18000ede1  lea     rdx, [rbp+arg_0]; int *
0x18000ede5  mov     edi, 0Ch
0x18000edea  mov     rcx, rbx; this
0x18000eded  jl      short loc_18000EDFD
0x18000edef  mov     r8, [rbx+0A50h]; struct Huffman *
0x18000edf6  call    ?decodeIntraDCAcPredMSV@CVideoObjectDecoder@@AEAAXPEAJPEAVHuffman@@J@Z; CVideoObjectDecoder::decodeIntraDCAcPredMSV(long *,Huffman *,long)
0x18000edfb  jmp     short loc_18000EE26
0x18000edfd  cmp     dword ptr [rbx+8], 2
0x18000ee01  jnz     short loc_18000EE17
0x18000ee03  mov     r9d, 8; int
0x18000ee09  lea     r8, ?gDecodeCodeTableIntraDCc@@3PAEA; unsigned __int8 *
0x18000ee10  call    ?decodeIntraDCAcPred@CVideoObjectDecoder@@AEAAXPEAJQEAEJ@Z; CVideoObjectDecoder::decodeIntraDCAcPred(long *,uchar * const,long)
0x18000ee15  jmp     short loc_18000EE26
0x18000ee17  mov     r9d, edi; int
0x18000ee1a  lea     r8, ?gDecodeCodeTableIntraDCMPEG4c@@3PAEA; unsigned __int8 *
0x18000ee21  call    ?decodeIntraDCAcPred_MPEG4@CVideoObjectDecoder@@AEAAXPEAJQEAEJ@Z; CVideoObjectDecoder::decodeIntraDCAcPred_MPEG4(long *,uchar * const,long)
0x18000ee26  mov     eax, [rbp+arg_0]
0x18000ee29  test    eax, eax
0x18000ee2b  jnz     loc_18000F00C
0x18000ee31  mov     r14d, [rbp+arg_38]
0x18000ee35  lea     rax, [rbp+arg_10]
0x18000ee39  mov     [rsp+70h+var_38], rax; int *
0x18000ee3e  mov     r9, r15; int **
0x18000ee41  mov     eax, [rbp+arg_48]
0x18000ee47  mov     rcx, rbx; this
0x18000ee4a  mov     dword ptr [rsp+70h+var_40], eax; int
0x18000ee4e  mov     [rsp+70h+var_48], r13d; int
0x18000ee53  mov     [rsp+70h+var_50], r14d; int
0x18000ee58  call    ?decodeDiffDCTCoef@CVideoObjectDecoder@@AEAAPEAJJPEAJPEAPEAJJJJAEAJ@Z; CVideoObjectDecoder::decodeDiffDCTCoef(long,long *,long * *,long,long,long,long &)
0x18000ee5d  cmp     dword ptr [rbx+8], 0
0x18000ee61  mov     r9, rax
0x18000ee64  jz      short loc_18000EE79
0x18000ee66  mov     edx, [rbx+650h]
0x18000ee6c  add     edx, [rax]
0x18000ee6e  mov     [rsi], edx
0x18000ee70  imul    edx, [rbx+170h]
0x18000ee77  jmp     short loc_18000EEAC
0x18000ee79  mov     ecx, [rax]
0x18000ee7b  mov     r8d, [rbx+170h]
0x18000ee82  mov     eax, r8d
0x18000ee85  sar     eax, 1
0x18000ee87  test    ecx, ecx
0x18000ee89  js      short loc_18000EE8F
0x18000ee8b  add     eax, ecx
0x18000ee8d  jmp     short loc_18000EE93
0x18000ee8f  sub     ecx, eax
0x18000ee91  mov     eax, ecx
0x18000ee93  cdq
0x18000ee94  idiv    r8d
0x18000ee97  mov     edx, [rbx+650h]
0x18000ee9d  add     edx, eax
0x18000ee9f  mov     ecx, eax
0x18000eea1  mov     [rsi], edx
0x18000eea3  imul    edx, [rbx+170h]
0x18000eeaa  mov     [rsi], edx
0x18000eeac  mov     [rbx+650h], edx
0x18000eeb2  mov     r8, r12; struct CMBMode *
0x18000eeb5  cmp     dword ptr [rbx+8], 0
0x18000eeb9  mov     ecx, [rbx+154h]
0x18000eebf  mov     eax, [rbp+arg_10]
0x18000eec2  mov     rdx, [rbp+var_18]
0x18000eec6  mov     [rsp+70h+var_30], eax; int
0x18000eeca  mov     [rsp+70h+var_38], r9; int *
0x18000eecf  mov     r9, [rbp+arg_18]; unsigned __int8 *
0x18000eed3  mov     [rsp+70h+var_40], rsi; int *
0x18000eed8  mov     [rsp+70h+var_48], 4; int
0x18000eee0  mov     [rsp+70h+var_50], ecx; int
0x18000eee4  mov     rcx, rbx; this
0x18000eee7  jnz     short loc_18000EEED
0x18000eee9  mov     rdx, [rbp+var_20]; struct CDCTTableInfo_Dec *
0x18000eeed  call    ?decodeIntraBlockAcPred@CVideoObjectDecoder@@AEAAJPEAVCDCTTableInfo_Dec@@PEAVCMBMode@@PEAEJJPEAJ3J@Z; CVideoObjectDecoder::decodeIntraBlockAcPred(CDCTTableInfo_Dec *,CMBMode *,uchar *,long,long,long *,long *,long)
0x18000eef2  mov     [rbp+arg_0], eax
0x18000eef5  test    eax, eax
0x18000eef7  jnz     loc_18000F00C
0x18000eefd  cmp     dword ptr [rbx+8], 3
0x18000ef01  lea     rdx, [rbp+arg_0]; int *
0x18000ef05  mov     rcx, rbx; this
0x18000ef08  jl      short loc_18000EF18
0x18000ef0a  mov     r8, [rbx+0A50h]; struct Huffman *
0x18000ef11  call    ?decodeIntraDCAcPredMSV@CVideoObjectDecoder@@AEAAXPEAJPEAVHuffman@@J@Z; CVideoObjectDecoder::decodeIntraDCAcPredMSV(long *,Huffman *,long)
0x18000ef16  jmp     short loc_18000EF41
0x18000ef18  cmp     dword ptr [rbx+8], 2
0x18000ef1c  jnz     short loc_18000EF32
0x18000ef1e  mov     r9d, 8; int
0x18000ef24  lea     r8, ?gDecodeCodeTableIntraDCc@@3PAEA; unsigned __int8 *
0x18000ef2b  call    ?decodeIntraDCAcPred@CVideoObjectDecoder@@AEAAXPEAJQEAEJ@Z; CVideoObjectDecoder::decodeIntraDCAcPred(long *,uchar * const,long)
0x18000ef30  jmp     short loc_18000EF41
0x18000ef32  mov     r9d, edi; int
0x18000ef35  lea     r8, ?gDecodeCodeTableIntraDCMPEG4c@@3PAEA; unsigned __int8 *
0x18000ef3c  call    ?decodeIntraDCAcPred_MPEG4@CVideoObjectDecoder@@AEAAXPEAJQEAEJ@Z; CVideoObjectDecoder::decodeIntraDCAcPred_MPEG4(long *,uchar * const,long)
0x18000ef41  mov     eax, [rbp+arg_0]
0x18000ef44  test    eax, eax
0x18000ef46  jnz     loc_18000F00C
0x18000ef4c  lea     rax, [rbp+arg_10]
0x18000ef50  mov     rcx, rbx; this
0x18000ef53  mov     [rsp+70h+var_38], rax; int *
0x18000ef58  lea     r9, [r15+30h]; int **
0x18000ef5c  mov     eax, [rbp+arg_48]
0x18000ef62  lea     rdi, [rsi+40h]
0x18000ef66  mov     dword ptr [rsp+70h+var_40], eax; int
0x18000ef6a  mov     [rsp+70h+var_48], r13d; int
0x18000ef6f  mov     [rsp+70h+var_50], r14d; int
0x18000ef74  call    ?decodeDiffDCTCoef@CVideoObjectDecoder@@AEAAPEAJJPEAJPEAPEAJJJJAEAJ@Z; CVideoObjectDecoder::decodeDiffDCTCoef(long,long *,long * *,long,long,long,long &)
0x18000ef79  cmp     dword ptr [rbx+8], 0
0x18000ef7d  mov     r9, rax
0x18000ef80  jz      short loc_18000EF95
0x18000ef82  mov     edx, [rbx+650h]
0x18000ef88  add     edx, [rax]
0x18000ef8a  mov     [rdi], edx
0x18000ef8c  imul    edx, [rbx+170h]
0x18000ef93  jmp     short loc_18000EFC6
0x18000ef95  mov     r8d, [rbx+170h]
0x18000ef9c  mov     ecx, r8d
0x18000ef9f  mov     eax, [rax]
0x18000efa1  sar     ecx, 1
0x18000efa3  test    eax, eax
0x18000efa5  js      short loc_18000EFAB
0x18000efa7  add     eax, ecx
0x18000efa9  jmp     short loc_18000EFAD
0x18000efab  sub     eax, ecx
0x18000efad  cdq
0x18000efae  idiv    r8d
0x18000efb1  mov     edx, [rbx+650h]
0x18000efb7  add     edx, eax
0x18000efb9  mov     ecx, eax
0x18000efbb  mov     [rdi], edx
0x18000efbd  imul    edx, [rbx+170h]
0x18000efc4  mov     [rdi], edx
0x18000efc6  mov     [rbx+650h], edx
0x18000efcc  mov     r8, r12; struct CMBMode *
0x18000efcf  cmp     dword ptr [rbx+8], 0
0x18000efd3  mov     ecx, [rbx+154h]
0x18000efd9  mov     eax, [rbp+arg_10]
0x18000efdc  mov     rdx, [rbp+var_18]
0x18000efe0  mov     [rsp+70h+var_30], eax; int
0x18000efe4  mov     [rsp+70h+var_38], r9; int *
0x18000efe9  mov     r9, [rbp+arg_20]; unsigned __int8 *
0x18000efed  mov     [rsp+70h+var_40], rdi; int *
0x18000eff2  mov     [rsp+70h+var_48], 5; int
0x18000effa  mov     [rsp+70h+var_50], ecx; int
0x18000effe  mov     rcx, rbx; this
0x18000f001  jnz     short loc_18000F007
0x18000f003  mov     rdx, [rbp+var_20]; struct CDCTTableInfo_Dec *
0x18000f007  call    ?decodeIntraBlockAcPred@CVideoObjectDecoder@@AEAAJPEAVCDCTTableInfo_Dec@@PEAVCMBMode@@PEAEJJPEAJ3J@Z; CVideoObjectDecoder::decodeIntraBlockAcPred(CDCTTableInfo_Dec *,CMBMode *,uchar *,long,long,long *,long *,long)
0x18000f00c  mov     rbx, [rsp+70h+arg_8]
0x18000f014  add     rsp, 70h
0x18000f018  pop     r15
0x18000f01a  pop     r14
0x18000f01c  pop     r13
0x18000f01e  pop     r12
0x18000f020  pop     rdi
0x18000f021  pop     rsi
0x18000f022  pop     rbp
0x18000f023  retn
```
