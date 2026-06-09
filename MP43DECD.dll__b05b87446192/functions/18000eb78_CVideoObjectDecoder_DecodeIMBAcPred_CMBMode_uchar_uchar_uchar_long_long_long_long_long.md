# CVideoObjectDecoder::DecodeIMBAcPred(CMBMode *,uchar *,uchar *,uchar *,long *,long * *,long,long,long)

- ea: `0x18000eb78`
- end: `0x18000ef64`
- name: `?DecodeIMBAcPred@CVideoObjectDecoder@@AEAAJPEAVCMBMode@@PEAE11PEAJPEAPEAJJJJ@Z`
- size: `1004`
- prototype: `__int64 __usercall@<rax>(CVideoObjectDecoder *__hidden this@<rcx>, struct CMBMode *@<rdx>, unsigned __int8 *@<r8>, unsigned __int8 *@<r9>, unsigned __int8 *, int *, int **, int, int, int)`
- caller_count: `6`
- callee_count: `6`
- tags: ``

## callers

- `0x18000f440`
- `0x18000f9d0`
- `0x180010058`
- `0x180010600`
- `0x180010f80`
- `0x1800119e8`

## callees

- `0x18000d618`
- `0x18000d71c`
- `0x18000d9a0`
- `0x18000da40`
- `0x18000dacc`
- `0x18000eb78`

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
0x18000eb78  mov     [rsp-38h+arg_8], rbx
0x18000eb7d  mov     [rsp-38h+arg_18], r9
0x18000eb82  push    rbp
0x18000eb83  push    rsi
0x18000eb84  push    rdi
0x18000eb85  push    r12
0x18000eb87  push    r13
0x18000eb89  push    r14
0x18000eb8b  push    r15
0x18000eb8d  mov     rbp, rsp
0x18000eb90  sub     rsp, 70h
0x18000eb94  mov     rax, [rcx+0DB8h]
0x18000eb9b  mov     r12, rdx
0x18000eb9e  mov     r13d, [rbp+arg_40]
0x18000eba5  xor     edx, edx
0x18000eba7  mov     r15, [rbp+arg_30]
0x18000ebab  mov     rbx, rcx
0x18000ebae  mov     rsi, [rbp+arg_28]
0x18000ebb2  mov     r14, r8
0x18000ebb5  mov     [rbp+var_18], rax
0x18000ebb9  mov     edi, edx
0x18000ebbb  mov     rax, [rcx+0DC0h]
0x18000ebc2  mov     [rbp+var_20], rax
0x18000ebc6  mov     eax, [rbp+arg_38]
0x18000ebc9  mov     [rcx+0E00h], edx
0x18000ebcf  mov     ecx, [rbp+arg_48]
0x18000ebd5  mov     [rbp+var_8], eax
0x18000ebd8  mov     [rbp+arg_0], edx
0x18000ebdb  mov     [rbp+arg_10], edx
0x18000ebde  mov     [rbp+var_10], ecx
0x18000ebe1  mov     [rbp+var_C], r13d
0x18000ebe5  mov     [rbp+var_4], ecx
0x18000ebe8  cmp     dword ptr [rbx+8], 3
0x18000ebec  lea     rdx, [rbp+arg_0]; int *
0x18000ebf0  mov     rcx, rbx; this
0x18000ebf3  jl      short loc_18000EC03
0x18000ebf5  mov     r8, [rbx+0A48h]; struct Huffman *
0x18000ebfc  call    ?decodeIntraDCAcPredMSV@CVideoObjectDecoder@@AEAAXPEAJPEAVHuffman@@J@Z; CVideoObjectDecoder::decodeIntraDCAcPredMSV(long *,Huffman *,long)
0x18000ec01  jmp     short loc_18000EC2F
0x18000ec03  cmp     dword ptr [rbx+8], 2
0x18000ec07  jnz     short loc_18000EC1D
0x18000ec09  mov     r9d, 7; int
0x18000ec0f  lea     r8, ?gDecodeCodeTableIntraDCy@@3PAEA; unsigned __int8 *
0x18000ec16  call    ?decodeIntraDCAcPred@CVideoObjectDecoder@@AEAAXPEAJQEAEJ@Z; CVideoObjectDecoder::decodeIntraDCAcPred(long *,uchar * const,long)
0x18000ec1b  jmp     short loc_18000EC2F
0x18000ec1d  mov     r9d, 0Bh; int
0x18000ec23  lea     r8, ?gDecodeCodeTableIntraDCMPEG4y@@3PAEA; unsigned __int8 *
0x18000ec2a  call    ?decodeIntraDCAcPred_MPEG4@CVideoObjectDecoder@@AEAAXPEAJQEAEJ@Z; CVideoObjectDecoder::decodeIntraDCAcPred_MPEG4(long *,uchar * const,long)
0x18000ec2f  mov     eax, [rbp+arg_0]
0x18000ec32  test    eax, eax
0x18000ec34  jnz     loc_18000EF4C
0x18000ec3a  mov     eax, edi
0x18000ec3c  lea     rcx, [rbp+arg_10]
0x18000ec40  mov     [rsp+70h+var_38], rcx; int *
0x18000ec45  mov     r9, r15; int **
0x18000ec48  mov     rcx, rbx; this
0x18000ec4b  mov     eax, [rbp+rax*4+var_10]
0x18000ec4f  mov     dword ptr [rsp+70h+var_40], eax; int
0x18000ec53  mov     eax, [rbp+arg_38]
0x18000ec56  mov     [rsp+70h+var_48], r13d; int
0x18000ec5b  mov     [rsp+70h+var_50], eax; int
0x18000ec5f  call    ?decodeDiffDCTCoef@CVideoObjectDecoder@@AEAAPEAJJPEAJPEAPEAJJJJAEAJ@Z; CVideoObjectDecoder::decodeDiffDCTCoef(long,long *,long * *,long,long,long,long &)
0x18000ec64  cmp     dword ptr [rbx+8], 0
0x18000ec68  mov     r9, rax
0x18000ec6b  jz      short loc_18000EC80
0x18000ec6d  mov     edx, [rbx+650h]
0x18000ec73  add     edx, [rax]
0x18000ec75  mov     [rsi], edx
0x18000ec77  imul    edx, [rbx+16Ch]
0x18000ec7e  jmp     short loc_18000ECB3
0x18000ec80  mov     ecx, [rax]
0x18000ec82  mov     r8d, [rbx+16Ch]
0x18000ec89  mov     eax, r8d
0x18000ec8c  sar     eax, 1
0x18000ec8e  test    ecx, ecx
0x18000ec90  js      short loc_18000EC96
0x18000ec92  add     eax, ecx
0x18000ec94  jmp     short loc_18000EC9A
0x18000ec96  sub     ecx, eax
0x18000ec98  mov     eax, ecx
0x18000ec9a  cdq
0x18000ec9b  idiv    r8d
0x18000ec9e  mov     edx, [rbx+650h]
0x18000eca4  add     edx, eax
0x18000eca6  mov     ecx, eax
0x18000eca8  mov     [rsi], edx
0x18000ecaa  imul    edx, [rbx+16Ch]
0x18000ecb1  mov     [rsi], edx
0x18000ecb3  mov     [rbx+650h], edx
0x18000ecb9  mov     r8, r12; struct CMBMode *
0x18000ecbc  mov     eax, [rbp+arg_10]
0x18000ecbf  mov     rcx, rbx; this
0x18000ecc2  mov     rdx, [rbp+var_20]; struct CDCTTableInfo_Dec *
0x18000ecc6  mov     [rsp+70h+var_30], eax; int
0x18000ecca  mov     eax, [rbx+150h]
0x18000ecd0  mov     [rsp+70h+var_38], r9; int *
0x18000ecd5  mov     r9, r14; unsigned __int8 *
0x18000ecd8  mov     [rsp+70h+var_40], rsi; int *
0x18000ecdd  mov     [rsp+70h+var_48], edi; int
0x18000ece1  mov     [rsp+70h+var_50], eax; int
0x18000ece5  call    ?decodeIntraBlockAcPred@CVideoObjectDecoder@@AEAAJPEAVCDCTTableInfo_Dec@@PEAVCMBMode@@PEAEJJPEAJ3J@Z; CVideoObjectDecoder::decodeIntraBlockAcPred(CDCTTableInfo_Dec *,CMBMode *,uchar *,long,long,long *,long *,long)
0x18000ecea  mov     [rbp+arg_0], eax
0x18000eced  test    eax, eax
0x18000ecef  jnz     loc_18000EF4C
0x18000ecf5  mov     eax, 8
0x18000ecfa  cmp     edi, 1
0x18000ecfd  jnz     short loc_18000ED05
0x18000ecff  mov     eax, [rbx+0E70h]
0x18000ed05  cdqe
0x18000ed07  add     rsi, 40h ; '@'
0x18000ed0b  add     r14, rax
0x18000ed0e  add     r15, 30h ; '0'
0x18000ed12  inc     edi
0x18000ed14  cmp     edi, 4
0x18000ed17  jb      loc_18000EBE8
0x18000ed1d  cmp     dword ptr [rbx+8], 3
0x18000ed21  lea     rdx, [rbp+arg_0]; int *
0x18000ed25  mov     edi, 0Ch
0x18000ed2a  mov     rcx, rbx; this
0x18000ed2d  jl      short loc_18000ED3D
0x18000ed2f  mov     r8, [rbx+0A50h]; struct Huffman *
0x18000ed36  call    ?decodeIntraDCAcPredMSV@CVideoObjectDecoder@@AEAAXPEAJPEAVHuffman@@J@Z; CVideoObjectDecoder::decodeIntraDCAcPredMSV(long *,Huffman *,long)
0x18000ed3b  jmp     short loc_18000ED66
0x18000ed3d  cmp     dword ptr [rbx+8], 2
0x18000ed41  jnz     short loc_18000ED57
0x18000ed43  mov     r9d, 8; int
0x18000ed49  lea     r8, ?gDecodeCodeTableIntraDCc@@3PAEA; unsigned __int8 *
0x18000ed50  call    ?decodeIntraDCAcPred@CVideoObjectDecoder@@AEAAXPEAJQEAEJ@Z; CVideoObjectDecoder::decodeIntraDCAcPred(long *,uchar * const,long)
0x18000ed55  jmp     short loc_18000ED66
0x18000ed57  mov     r9d, edi; int
0x18000ed5a  lea     r8, ?gDecodeCodeTableIntraDCMPEG4c@@3PAEA; unsigned __int8 *
0x18000ed61  call    ?decodeIntraDCAcPred_MPEG4@CVideoObjectDecoder@@AEAAXPEAJQEAEJ@Z; CVideoObjectDecoder::decodeIntraDCAcPred_MPEG4(long *,uchar * const,long)
0x18000ed66  mov     eax, [rbp+arg_0]
0x18000ed69  test    eax, eax
0x18000ed6b  jnz     loc_18000EF4C
0x18000ed71  mov     r14d, [rbp+arg_38]
0x18000ed75  lea     rax, [rbp+arg_10]
0x18000ed79  mov     [rsp+70h+var_38], rax; int *
0x18000ed7e  mov     r9, r15; int **
0x18000ed81  mov     eax, [rbp+arg_48]
0x18000ed87  mov     rcx, rbx; this
0x18000ed8a  mov     dword ptr [rsp+70h+var_40], eax; int
0x18000ed8e  mov     [rsp+70h+var_48], r13d; int
0x18000ed93  mov     [rsp+70h+var_50], r14d; int
0x18000ed98  call    ?decodeDiffDCTCoef@CVideoObjectDecoder@@AEAAPEAJJPEAJPEAPEAJJJJAEAJ@Z; CVideoObjectDecoder::decodeDiffDCTCoef(long,long *,long * *,long,long,long,long &)
0x18000ed9d  cmp     dword ptr [rbx+8], 0
0x18000eda1  mov     r9, rax
0x18000eda4  jz      short loc_18000EDB9
0x18000eda6  mov     edx, [rbx+650h]
0x18000edac  add     edx, [rax]
0x18000edae  mov     [rsi], edx
0x18000edb0  imul    edx, [rbx+170h]
0x18000edb7  jmp     short loc_18000EDEC
0x18000edb9  mov     ecx, [rax]
0x18000edbb  mov     r8d, [rbx+170h]
0x18000edc2  mov     eax, r8d
0x18000edc5  sar     eax, 1
0x18000edc7  test    ecx, ecx
0x18000edc9  js      short loc_18000EDCF
0x18000edcb  add     eax, ecx
0x18000edcd  jmp     short loc_18000EDD3
0x18000edcf  sub     ecx, eax
0x18000edd1  mov     eax, ecx
0x18000edd3  cdq
0x18000edd4  idiv    r8d
0x18000edd7  mov     edx, [rbx+650h]
0x18000eddd  add     edx, eax
0x18000eddf  mov     ecx, eax
0x18000ede1  mov     [rsi], edx
0x18000ede3  imul    edx, [rbx+170h]
0x18000edea  mov     [rsi], edx
0x18000edec  mov     [rbx+650h], edx
0x18000edf2  mov     r8, r12; struct CMBMode *
0x18000edf5  cmp     dword ptr [rbx+8], 0
0x18000edf9  mov     ecx, [rbx+154h]
0x18000edff  mov     eax, [rbp+arg_10]
0x18000ee02  mov     rdx, [rbp+var_18]
0x18000ee06  mov     [rsp+70h+var_30], eax; int
0x18000ee0a  mov     [rsp+70h+var_38], r9; int *
0x18000ee0f  mov     r9, [rbp+arg_18]; unsigned __int8 *
0x18000ee13  mov     [rsp+70h+var_40], rsi; int *
0x18000ee18  mov     [rsp+70h+var_48], 4; int
0x18000ee20  mov     [rsp+70h+var_50], ecx; int
0x18000ee24  mov     rcx, rbx; this
0x18000ee27  jnz     short loc_18000EE2D
0x18000ee29  mov     rdx, [rbp+var_20]; struct CDCTTableInfo_Dec *
0x18000ee2d  call    ?decodeIntraBlockAcPred@CVideoObjectDecoder@@AEAAJPEAVCDCTTableInfo_Dec@@PEAVCMBMode@@PEAEJJPEAJ3J@Z; CVideoObjectDecoder::decodeIntraBlockAcPred(CDCTTableInfo_Dec *,CMBMode *,uchar *,long,long,long *,long *,long)
0x18000ee32  mov     [rbp+arg_0], eax
0x18000ee35  test    eax, eax
0x18000ee37  jnz     loc_18000EF4C
0x18000ee3d  cmp     dword ptr [rbx+8], 3
0x18000ee41  lea     rdx, [rbp+arg_0]; int *
0x18000ee45  mov     rcx, rbx; this
0x18000ee48  jl      short loc_18000EE58
0x18000ee4a  mov     r8, [rbx+0A50h]; struct Huffman *
0x18000ee51  call    ?decodeIntraDCAcPredMSV@CVideoObjectDecoder@@AEAAXPEAJPEAVHuffman@@J@Z; CVideoObjectDecoder::decodeIntraDCAcPredMSV(long *,Huffman *,long)
0x18000ee56  jmp     short loc_18000EE81
0x18000ee58  cmp     dword ptr [rbx+8], 2
0x18000ee5c  jnz     short loc_18000EE72
0x18000ee5e  mov     r9d, 8; int
0x18000ee64  lea     r8, ?gDecodeCodeTableIntraDCc@@3PAEA; unsigned __int8 *
0x18000ee6b  call    ?decodeIntraDCAcPred@CVideoObjectDecoder@@AEAAXPEAJQEAEJ@Z; CVideoObjectDecoder::decodeIntraDCAcPred(long *,uchar * const,long)
0x18000ee70  jmp     short loc_18000EE81
0x18000ee72  mov     r9d, edi; int
0x18000ee75  lea     r8, ?gDecodeCodeTableIntraDCMPEG4c@@3PAEA; unsigned __int8 *
0x18000ee7c  call    ?decodeIntraDCAcPred_MPEG4@CVideoObjectDecoder@@AEAAXPEAJQEAEJ@Z; CVideoObjectDecoder::decodeIntraDCAcPred_MPEG4(long *,uchar * const,long)
0x18000ee81  mov     eax, [rbp+arg_0]
0x18000ee84  test    eax, eax
0x18000ee86  jnz     loc_18000EF4C
0x18000ee8c  lea     rax, [rbp+arg_10]
0x18000ee90  mov     rcx, rbx; this
0x18000ee93  mov     [rsp+70h+var_38], rax; int *
0x18000ee98  lea     r9, [r15+30h]; int **
0x18000ee9c  mov     eax, [rbp+arg_48]
0x18000eea2  lea     rdi, [rsi+40h]
0x18000eea6  mov     dword ptr [rsp+70h+var_40], eax; int
0x18000eeaa  mov     [rsp+70h+var_48], r13d; int
0x18000eeaf  mov     [rsp+70h+var_50], r14d; int
0x18000eeb4  call    ?decodeDiffDCTCoef@CVideoObjectDecoder@@AEAAPEAJJPEAJPEAPEAJJJJAEAJ@Z; CVideoObjectDecoder::decodeDiffDCTCoef(long,long *,long * *,long,long,long,long &)
0x18000eeb9  cmp     dword ptr [rbx+8], 0
0x18000eebd  mov     r9, rax
0x18000eec0  jz      short loc_18000EED5
0x18000eec2  mov     edx, [rbx+650h]
0x18000eec8  add     edx, [rax]
0x18000eeca  mov     [rdi], edx
0x18000eecc  imul    edx, [rbx+170h]
0x18000eed3  jmp     short loc_18000EF06
0x18000eed5  mov     r8d, [rbx+170h]
0x18000eedc  mov     ecx, r8d
0x18000eedf  mov     eax, [rax]
0x18000eee1  sar     ecx, 1
0x18000eee3  test    eax, eax
0x18000eee5  js      short loc_18000EEEB
0x18000eee7  add     eax, ecx
0x18000eee9  jmp     short loc_18000EEED
0x18000eeeb  sub     eax, ecx
0x18000eeed  cdq
0x18000eeee  idiv    r8d
0x18000eef1  mov     edx, [rbx+650h]
0x18000eef7  add     edx, eax
0x18000eef9  mov     ecx, eax
0x18000eefb  mov     [rdi], edx
0x18000eefd  imul    edx, [rbx+170h]
0x18000ef04  mov     [rdi], edx
0x18000ef06  mov     [rbx+650h], edx
0x18000ef0c  mov     r8, r12; struct CMBMode *
0x18000ef0f  cmp     dword ptr [rbx+8], 0
0x18000ef13  mov     ecx, [rbx+154h]
0x18000ef19  mov     eax, [rbp+arg_10]
0x18000ef1c  mov     rdx, [rbp+var_18]
0x18000ef20  mov     [rsp+70h+var_30], eax; int
0x18000ef24  mov     [rsp+70h+var_38], r9; int *
0x18000ef29  mov     r9, [rbp+arg_20]; unsigned __int8 *
0x18000ef2d  mov     [rsp+70h+var_40], rdi; int *
0x18000ef32  mov     [rsp+70h+var_48], 5; int
0x18000ef3a  mov     [rsp+70h+var_50], ecx; int
0x18000ef3e  mov     rcx, rbx; this
0x18000ef41  jnz     short loc_18000EF47
0x18000ef43  mov     rdx, [rbp+var_20]; struct CDCTTableInfo_Dec *
0x18000ef47  call    ?decodeIntraBlockAcPred@CVideoObjectDecoder@@AEAAJPEAVCDCTTableInfo_Dec@@PEAVCMBMode@@PEAEJJPEAJ3J@Z; CVideoObjectDecoder::decodeIntraBlockAcPred(CDCTTableInfo_Dec *,CMBMode *,uchar *,long,long,long *,long *,long)
0x18000ef4c  mov     rbx, [rsp+70h+arg_8]
0x18000ef54  add     rsp, 70h
0x18000ef58  pop     r15
0x18000ef5a  pop     r14
0x18000ef5c  pop     r13
0x18000ef5e  pop     r12
0x18000ef60  pop     rdi
0x18000ef61  pop     rsi
0x18000ef62  pop     rbp
0x18000ef63  retn
```
