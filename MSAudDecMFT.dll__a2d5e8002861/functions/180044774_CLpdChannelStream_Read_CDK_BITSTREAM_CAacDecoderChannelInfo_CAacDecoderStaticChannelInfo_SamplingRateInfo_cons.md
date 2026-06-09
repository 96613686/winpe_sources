# CLpdChannelStream_Read(CDK_BITSTREAM *,CAacDecoderChannelInfo *,CAacDecoderStaticChannelInfo *,SamplingRateInfo const *,uint)

- ea: `0x180044774`
- end: `0x180044c56`
- name: `?CLpdChannelStream_Read@@YA?AW4AAC_DECODER_ERROR@@PEAUCDK_BITSTREAM@@PEAUCAacDecoderChannelInfo@@PEAUCAacDecoderStaticChannelInfo@@PEBUSamplingRateInfo@@I@Z`
- size: `1250`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x180014ae0`

## callees

- `0x1800110c0`
- `0x180013550`
- `0x180044774`
- `0x180044c5c`
- `0x180048474`
- `0x18007a8ac`
- `0x18007a968`
- `0x18007aa3c`
- `0x180080608`
- `0x180080b34`
- `0x18008444c`
- `0x180085a00`

## pseudocode

```c
__int64 __fastcall CLpdChannelStream_Read(struct CDK_BITSTREAM *a1, __int64 a2, __int64 a3, __int64 a4, int a5)
{
  bool v5; // zf
  __int64 *v6; // rax
  int LastFrameOk; // eax
  __int64 v11; // r8
  __int64 v12; // r9
  int v13; // ebx
  int v14; // r13d
  int v15; // r14d
  _BYTE *v16; // r15
  unsigned int v17; // edi
  int v18; // ebx
  int v19; // eax
  __int64 v20; // rcx
  int v21; // r13d
  int v22; // ebx
  int v23; // edx
  float *v24; // rax
  BOOL v25; // ecx
  int v26; // r8d
  int v27; // eax
  __int64 v28; // rdx
  __int64 i; // rax
  float v30; // xmm1_4
  float *v31; // rdx
  char v32; // cl
  float *Memory; // rax
  float *v34; // r10
  int v35; // eax
  int v37; // [rsp+20h] [rbp-88h]
  int v38; // [rsp+20h] [rbp-88h]
  int v39; // [rsp+50h] [rbp-58h]
  int v40; // [rsp+54h] [rbp-54h] BYREF
  int v41; // [rsp+58h] [rbp-50h]
  int v42; // [rsp+5Ch] [rbp-4Ch]
  int v43; // [rsp+60h] [rbp-48h]
  __int64 *v44; // [rsp+68h] [rbp-40h]
  int v45; // [rsp+B8h] [rbp+10h]
  int v46; // [rsp+C0h] [rbp+18h]
  int v47; // [rsp+C8h] [rbp+20h]

  v5 = *(_DWORD *)(a2 + 1692) == 128;
  v6 = qword_1800B3440;
  v40 = 0;
  if ( !v5 )
    v6 = qword_1800B3450;
  v44 = v6;
  LastFrameOk = CConcealment_GetLastFrameOk((struct CConcealmentInfo *)(a3 + 4176), 1);
  v13 = *(_DWORD *)(v12 + 24);
  v14 = LastFrameOk;
  v39 = LastFrameOk;
  if ( (unsigned int)(v13 - 6000) > 0x4650 )
    return 16386;
  v15 = *(unsigned __int8 *)(a3 + 1834);
  v16 = (_BYTE *)(a2 + 553);
  v42 = CDKreadBits(a1, 3, v11);
  v17 = CLpd_ReadAndMapLpdModeToModArray(a2 + 553, a1);
  if ( !v17 )
  {
    v46 = v15;
    v41 = ((int)((unsigned __int64)(1374389535LL * (34 * v13 + 6400)) >> 32) >> 12)
        - 34
        + ((unsigned int)((unsigned __int64)(1374389535LL * (34 * v13 + 6400)) >> 32) >> 31);
    *(_BYTE *)(a2 + 557) = CDKreadBit((__int64)a1);
    v18 = CDKreadBit((__int64)a1);
    v19 = CDKreadBit((__int64)a1);
    v20 = *(unsigned int *)(a3 + 1828);
    *(_DWORD *)(a2 + 548) = v20;
    LOBYTE(v20) = *(_BYTE *)(a3 + 1832);
    *(_BYTE *)(a2 + 552) = v20;
    v45 = v19;
    if ( !v18 )
    {
      *(_DWORD *)(a2 + 548) = 0;
      *(_BYTE *)(a2 + 552) = -1;
LABEL_11:
      v47 = 1;
      v43 = v18 != 2;
      if ( *(_DWORD *)(a3 + 1828) != 2 )
      {
        CLpd_Reset(v20, a3, 0);
        if ( !v14 )
          v46 = v15 | (v18 == 2);
        v19 = v45;
      }
      v21 = *(_DWORD *)(a2 + 548);
      v22 = 0;
      v23 = *(unsigned __int8 *)(a2 + 552);
      while ( 1 )
      {
        if ( v22 >= 4 )
        {
          v25 = (*v16 & 3) == 0 && v46 && *(_DWORD *)(a3 + 1828) != 2;
          if ( (unsigned int)CLpc_Read(
                               a1,
                               (float (*const)[16])(a2 + 580),
                               (float *const)(a3 + 1836),
                               (float *const)(a2 + 1220),
                               (float *const)(a2 + 1284),
                               (unsigned __int8 *)(a2 + 553),
                               v43,
                               v25,
                               v39) )
            return 16386;
          if ( v46 && !v39 )
          {
            v26 = 0;
            do
            {
              v27 = 1;
              if ( (v16[v26] & 3) != 0 )
                v27 = 1 << (v16[v26] - 1);
              v28 = a2 + 580 + ((__int64)v26 << 6);
              v26 += v27;
              for ( i = 0; i != 16; ++i )
              {
                v30 = *(float *)(a2 + ((__int64)v26 << 6) + 4 * i + 580);
                if ( *(float *)(v28 + 4 * i) > v30 )
                  *(float *)(v28 + 4 * i) = v30;
              }
            }
            while ( v26 < 4 );
          }
          if ( !(unsigned int)CConcealment_GetLastFrameOk((struct CConcealmentInfo *)(a3 + 4176), 1) )
          {
            v31 = (float *)(a2 + 900);
            goto LABEL_56;
          }
          v32 = *(_BYTE *)(a3 + 1832);
          if ( v32 )
          {
            if ( v32 == -1 )
            {
              v31 = (float *)(a2 + 900);
LABEL_56:
              E_LPC_f_lsp_a_conversion((float *)(a2 + 580), v31);
            }
            else
            {
              *(_OWORD *)(a2 + 900) = *(_OWORD *)(a3 + 1964);
              *(_OWORD *)(a2 + 916) = *(_OWORD *)(a3 + 1980);
              *(_OWORD *)(a2 + 932) = *(_OWORD *)(a3 + 1996);
              *(_OWORD *)(a2 + 948) = *(_OWORD *)(a3 + 2012);
            }
          }
          if ( v45 && v21 != 2 )
          {
            if ( (unsigned int)CDKreadBit((__int64)a1) )
            {
              v21 = 1;
              *(_DWORD *)(a2 + 548) = 1;
              *(_BYTE *)(a2 + 552) = -1;
              if ( *(_DWORD *)(a3 + 1828) != 1 )
              {
                if ( (unsigned int)CConcealment_GetLastFrameOk((struct CConcealmentInfo *)(a3 + 4176), 1) )
                  return 16386;
              }
            }
            Memory = CLpd_FAC_GetMemory((struct CAacDecoderChannelInfo *)a2, (unsigned __int8 *const)(a2 + 553), &v40);
            *(_QWORD *)(a2 + 512) = Memory;
            v34 = Memory;
            v35 = *(_DWORD *)(a2 + 1692);
            if ( v21 == 1 )
              v35 /= 2;
            if ( (unsigned int)CLpd_FAC_Read(a1, v34, v35, 1, v38) )
              return 16386;
          }
          return v17;
        }
        *(_QWORD *)(a2 + 8LL * v22 + 512) = 0;
        if ( v22 || v21 != 2 || !v19 )
        {
          if ( v23 )
          {
            if ( v23 == 255 || v16[v22] )
              goto LABEL_29;
          }
          else if ( !v16[v22] )
          {
            goto LABEL_29;
          }
        }
        v24 = CLpd_FAC_GetMemory((struct CAacDecoderChannelInfo *)a2, (unsigned __int8 *const)(a2 + 553), &v40);
        *(_QWORD *)(a2 + 8LL * v22 + 512) = v24;
        if ( (unsigned int)CLpd_FAC_Read(a1, v24, *(_DWORD *)(a2 + 1692), 0, v37) )
          return 16386;
LABEL_29:
        if ( v16[v22] )
        {
          v17 = CLpd_TCX_Read((_DWORD)a1, a2, a3, *((_DWORD *)v44 + (unsigned __int8)v16[v22]), v47, v22, a5);
          if ( v17 )
            return 16386;
          v23 = (unsigned __int8)v16[v22];
          v47 = 0;
          v22 += 1 << (v23 - 1);
        }
        else
        {
          if ( (unsigned int)CLpd_AcelpRead(
                               a1,
                               (struct CAcelpChannelData *)(a2 + 86LL * v22 + 1300),
                               v42,
                               8 * *(_DWORD *)(a2 + 1692),
                               v41) )
            return 16386;
          v23 = 0;
          ++v22;
        }
        v19 = v45;
      }
    }
    *(_DWORD *)(a2 + 548) = 2;
    if ( *v16 )
    {
      if ( v19 )
        goto LABEL_9;
    }
    else if ( !v19 )
    {
LABEL_9:
      *(_BYTE *)(a2 + 552) = 0;
LABEL_10:
      v18 = 2;
      goto LABEL_11;
    }
    if ( !(_BYTE)v20 )
      *(_BYTE *)(a2 + 552) = 1;
    goto LABEL_10;
  }
  return v17;
}

```

## disassembly

```asm
0x180044774  mov     [rsp+arg_0], rbx
0x180044779  push    rbp
0x18004477a  push    rsi
0x18004477b  push    rdi
0x18004477c  push    r12
0x18004477e  push    r13
0x180044780  push    r14
0x180044782  push    r15
0x180044784  sub     rsp, 70h
0x180044788  cmp     dword ptr [rdx+69Ch], 80h
0x180044792  lea     rax, qword_1800B3440
0x180044799  mov     r12, rcx
0x18004479c  mov     [rsp+0A8h+var_54], 0
0x1800447a4  lea     rcx, qword_1800B3450
0x1800447ab  mov     rsi, rdx
0x1800447ae  cmovnz  rax, rcx
0x1800447b2  mov     edx, 1; int
0x1800447b7  lea     rcx, [r8+1050h]; struct CConcealmentInfo *
0x1800447be  mov     [rsp+0A8h+var_40], rax
0x1800447c3  mov     rbp, r8
0x1800447c6  call    ?CConcealment_GetLastFrameOk@@YAHPEAUCConcealmentInfo@@H@Z; CConcealment_GetLastFrameOk(CConcealmentInfo *,int)
0x1800447cb  mov     ebx, [r9+18h]
0x1800447cf  mov     r13d, eax
0x1800447d2  mov     [rsp+0A8h+var_58], eax
0x1800447d6  lea     eax, [rbx-1770h]
0x1800447dc  cmp     eax, 4650h
0x1800447e1  ja      loc_180044C36
0x1800447e7  movzx   r14d, byte ptr [rbp+72Ah]
0x1800447ef  lea     r15, [rsi+229h]
0x1800447f6  mov     edx, 3
0x1800447fb  mov     rcx, r12
0x1800447fe  call    CDKreadBits
0x180044803  mov     rdx, r12
0x180044806  mov     [rsp+0A8h+var_4C], eax
0x18004480a  mov     rcx, r15
0x18004480d  call    CLpd_ReadAndMapLpdModeToModArray
0x180044812  mov     edi, eax
0x180044814  test    eax, eax
0x180044816  jnz     loc_180044C3B
0x18004481c  imul    ecx, ebx, 22h ; '"'
0x18004481f  mov     eax, 51EB851Fh
0x180044824  mov     [rsp+0A8h+arg_10], r14d
0x18004482c  add     ecx, 1900h
0x180044832  imul    ecx
0x180044834  mov     rcx, r12
0x180044837  sar     edx, 0Ch
0x18004483a  mov     eax, edx
0x18004483c  add     edx, 0FFFFFFDEh
0x18004483f  shr     eax, 1Fh
0x180044842  add     eax, edx
0x180044844  mov     [rsp+0A8h+var_50], eax
0x180044848  call    CDKreadBit
0x18004484d  mov     rcx, r12
0x180044850  mov     [rsi+22Dh], al
0x180044856  call    CDKreadBit
0x18004485b  mov     rcx, r12
0x18004485e  mov     ebx, eax
0x180044860  call    CDKreadBit
0x180044865  mov     ecx, [rbp+724h]
0x18004486b  lea     r8d, [rdi+2]
0x18004486f  mov     [rsi+224h], ecx
0x180044875  mov     cl, [rbp+728h]
0x18004487b  mov     [rsi+228h], cl
0x180044881  mov     [rsp+0A8h+arg_8], eax
0x180044888  test    ebx, ebx
0x18004488a  jnz     short loc_18004489B
0x18004488c  mov     [rsi+224h], ebx
0x180044892  mov     byte ptr [rsi+228h], 0FFh
0x180044899  jmp     short loc_1800448BE
0x18004489b  mov     [rsi+224h], r8d
0x1800448a2  cmp     byte ptr [r15], 0
0x1800448a6  jnz     loc_180044951
0x1800448ac  test    eax, eax
0x1800448ae  jnz     loc_180044959
0x1800448b4  mov     byte ptr [rsi+228h], 0
0x1800448bb  mov     ebx, r8d
0x1800448be  xor     r10d, r10d
0x1800448c1  mov     [rsp+0A8h+arg_18], 1
0x1800448cc  cmp     ebx, r8d
0x1800448cf  setnz   r10b
0x1800448d3  mov     [rsp+0A8h+var_48], r10d
0x1800448d8  cmp     [rbp+724h], r8d
0x1800448df  jz      short loc_180044910
0x1800448e1  xor     r8d, r8d
0x1800448e4  mov     rdx, rbp
0x1800448e7  call    CLpd_Reset
0x1800448ec  mov     r8d, 2
0x1800448f2  test    r13d, r13d
0x1800448f5  jnz     short loc_180044909
0x1800448f7  xor     eax, eax
0x1800448f9  cmp     ebx, r8d
0x1800448fc  setz    al
0x1800448ff  or      eax, r14d
0x180044902  mov     [rsp+0A8h+arg_10], eax
0x180044909  mov     eax, [rsp+0A8h+arg_8]
0x180044910  mov     r13d, [rsi+224h]
0x180044917  xor     ebx, ebx
0x180044919  movzx   edx, byte ptr [rsi+228h]
0x180044920  cmp     ebx, 4
0x180044923  jge     loc_180044A5D
0x180044929  movsxd  r14, ebx
0x18004492c  mov     qword ptr [rsi+r14*8+200h], 0
0x180044938  test    ebx, ebx
0x18004493a  jnz     short loc_180044945
0x18004493c  cmp     r13d, r8d
0x18004493f  jnz     short loc_180044945
0x180044941  test    eax, eax
0x180044943  jnz     short loc_180044980
0x180044945  test    edx, edx
0x180044947  jnz     short loc_18004496D
0x180044949  cmp     [r14+r15], dl
0x18004494d  jbe     short loc_1800449B5
0x18004494f  jmp     short loc_180044980
0x180044951  test    eax, eax
0x180044953  jnz     loc_1800448B4
0x180044959  test    cl, cl
0x18004495b  jnz     loc_1800448BB
0x180044961  mov     byte ptr [rsi+228h], 1
0x180044968  jmp     loc_1800448BB
0x18004496d  cmp     edx, 0FFh
0x180044973  jz      short loc_1800449B5
0x180044975  test    edx, edx
0x180044977  jz      short loc_1800449B5
0x180044979  cmp     byte ptr [r14+r15], 0
0x18004497e  jnz     short loc_1800449B5
0x180044980  lea     r8, [rsp+0A8h+var_54]; int *
0x180044985  mov     rdx, r15; unsigned __int8 *
0x180044988  mov     rcx, rsi; struct CAacDecoderChannelInfo *
0x18004498b  call    ?CLpd_FAC_GetMemory@@YAPEAMPEAUCAacDecoderChannelInfo@@QEAEPEAH@Z; CLpd_FAC_GetMemory(CAacDecoderChannelInfo *,uchar * const,int *)
0x180044990  mov     [rsi+r14*8+200h], rax
0x180044998  xor     r9d, r9d; int
0x18004499b  mov     r8d, [rsi+69Ch]; int
0x1800449a2  mov     rdx, rax; float *
0x1800449a5  mov     rcx, r12; struct CDK_BITSTREAM *
0x1800449a8  call    ?CLpd_FAC_Read@@YAHPEAUCDK_BITSTREAM@@PEAMHHH@Z; CLpd_FAC_Read(CDK_BITSTREAM *,float *,int,int,int)
0x1800449ad  test    eax, eax
0x1800449af  jnz     loc_180044C36
0x1800449b5  movzx   eax, byte ptr [r14+r15]
0x1800449ba  mov     rcx, r12; struct CDK_BITSTREAM *
0x1800449bd  test    al, al
0x1800449bf  jnz     short loc_1800449FA
0x1800449c1  mov     r9d, [rsi+69Ch]
0x1800449c8  mov     eax, [rsp+0A8h+var_50]
0x1800449cc  mov     r8d, [rsp+0A8h+var_4C]; int
0x1800449d1  imul    rdx, r14, 56h ; 'V'
0x1800449d5  shl     r9d, 3; int
0x1800449d9  add     rdx, 514h
0x1800449e0  mov     dword ptr [rsp+0A8h+var_88], eax; int
0x1800449e4  add     rdx, rsi; struct CAcelpChannelData *
0x1800449e7  call    ?CLpd_AcelpRead@@YAHPEAUCDK_BITSTREAM@@PEAUCAcelpChannelData@@HHH@Z; CLpd_AcelpRead(CDK_BITSTREAM *,CAcelpChannelData *,int,int,int)
0x1800449ec  test    eax, eax
0x1800449ee  jnz     loc_180044C36
0x1800449f4  xor     edx, edx
0x1800449f6  inc     ebx
0x1800449f8  jmp     short loc_180044A4B
0x1800449fa  mov     r9, rax
0x1800449fd  mov     r8, rbp
0x180044a00  mov     eax, [rsp+0A8h+arg_20]
0x180044a07  mov     rdx, rsi
0x180044a0a  mov     [rsp+0A8h+var_78], eax
0x180044a0e  mov     eax, [rsp+0A8h+arg_18]
0x180044a15  mov     dword ptr [rsp+0A8h+var_80], ebx
0x180044a19  mov     dword ptr [rsp+0A8h+var_88], eax
0x180044a1d  mov     rax, [rsp+0A8h+var_40]
0x180044a22  mov     r9d, [rax+r9*4]
0x180044a26  call    CLpd_TCX_Read
0x180044a2b  mov     edi, eax
0x180044a2d  test    eax, eax
0x180044a2f  jnz     loc_180044C36
0x180044a35  movzx   edx, byte ptr [r14+r15]
0x180044a3a  mov     [rsp+0A8h+arg_18], eax
0x180044a41  lea     eax, [rdi+1]
0x180044a44  lea     ecx, [rdx-1]
0x180044a47  shl     eax, cl
0x180044a49  add     ebx, eax
0x180044a4b  mov     eax, [rsp+0A8h+arg_8]
0x180044a52  mov     r8d, 2
0x180044a58  jmp     loc_180044920
0x180044a5d  test    byte ptr [r15], 3
0x180044a61  mov     r14d, [rsp+0A8h+arg_10]
0x180044a69  jnz     short loc_180044A80
0x180044a6b  test    r14d, r14d
0x180044a6e  jz      short loc_180044A80
0x180044a70  cmp     [rbp+724h], r8d
0x180044a77  jz      short loc_180044A80
0x180044a79  mov     ecx, 1
0x180044a7e  jmp     short loc_180044A82
0x180044a80  xor     ecx, ecx
0x180044a82  mov     edx, [rsp+0A8h+var_58]
0x180044a86  lea     rax, [rsi+504h]
0x180044a8d  mov     [rsp+0A8h+var_68], edx; int
0x180044a91  lea     rbx, [rsi+244h]
0x180044a98  mov     [rsp+0A8h+var_70], ecx; int
0x180044a9c  lea     r9, [rsi+4C4h]; float *
0x180044aa3  mov     ecx, [rsp+0A8h+var_48]
0x180044aa7  lea     r8, [rbp+72Ch]; float *
0x180044aae  mov     [rsp+0A8h+var_78], ecx; int
0x180044ab2  mov     rdx, rbx; float (*)[16]
0x180044ab5  mov     [rsp+0A8h+var_80], r15; unsigned __int8 *
0x180044aba  mov     rcx, r12; struct CDK_BITSTREAM *
0x180044abd  mov     [rsp+0A8h+var_88], rax; int
0x180044ac2  call    ?CLpc_Read@@YAHPEAUCDK_BITSTREAM@@QEAY0BA@MQEAM22PEAEHHH@Z; CLpc_Read(CDK_BITSTREAM *,float (* const)[16],float * const,float * const,float * const,uchar *,int,int,int)
0x180044ac7  test    eax, eax
0x180044ac9  jnz     loc_180044C36
0x180044acf  test    r14d, r14d
0x180044ad2  jz      short loc_180044B35
0x180044ad4  cmp     [rsp+0A8h+var_58], eax
0x180044ad8  jnz     short loc_180044B35
0x180044ada  xor     r8d, r8d
0x180044add  movsxd  rdx, r8d
0x180044ae0  mov     eax, 1
0x180044ae5  test    byte ptr [rdx+r15], 3
0x180044aea  jz      short loc_180044AF5
0x180044aec  movzx   ecx, byte ptr [rdx+r15]
0x180044af1  dec     ecx
0x180044af3  shl     eax, cl
0x180044af5  add     eax, r8d
0x180044af8  shl     rdx, 6
0x180044afc  movsxd  rcx, eax
0x180044aff  add     rdx, rbx
0x180044b02  shl     rcx, 6
0x180044b06  mov     r8d, eax
0x180044b09  add     rcx, rsi
0x180044b0c  xor     eax, eax
0x180044b0e  movss   xmm1, dword ptr [rcx+rax*4+244h]
0x180044b17  movss   xmm0, dword ptr [rdx+rax*4]
0x180044b1c  comiss  xmm0, xmm1
0x180044b1f  jbe     short loc_180044B26
0x180044b21  movss   dword ptr [rdx+rax*4], xmm1
0x180044b26  inc     rax
0x180044b29  cmp     rax, 10h
0x180044b2d  jnz     short loc_180044B0E
0x180044b2f  cmp     r8d, 4
0x180044b33  jl      short loc_180044ADD
0x180044b35  lea     r14, [rbp+1050h]
0x180044b3c  mov     edx, 1; int
0x180044b41  mov     rcx, r14; struct CConcealmentInfo *
0x180044b44  call    ?CConcealment_GetLastFrameOk@@YAHPEAUCConcealmentInfo@@H@Z; CConcealment_GetLastFrameOk(CConcealmentInfo *,int)
0x180044b49  test    eax, eax
0x180044b4b  jnz     short loc_180044B56
0x180044b4d  lea     rdx, [rsi+384h]
0x180044b54  jmp     short loc_180044B6F
0x180044b56  mov     cl, [rbp+728h]
0x180044b5c  test    cl, cl
0x180044b5e  jz      short loc_180044BA4
0x180044b60  lea     rax, [rsi+384h]
0x180044b67  cmp     cl, 0FFh
0x180044b6a  jnz     short loc_180044B79
0x180044b6c  mov     rdx, rax; float *
0x180044b6f  mov     rcx, rbx; float *
0x180044b72  call    ?E_LPC_f_lsp_a_conversion@@YAXPEAM0@Z; E_LPC_f_lsp_a_conversion(float *,float *)
0x180044b77  jmp     short loc_180044BA4
0x180044b79  movups  xmm0, xmmword ptr [rbp+7ACh]
0x180044b80  movups  xmmword ptr [rax], xmm0
0x180044b83  movups  xmm1, xmmword ptr [rbp+7BCh]
0x180044b8a  movups  xmmword ptr [rax+10h], xmm1
0x180044b8e  movups  xmm0, xmmword ptr [rbp+7CCh]
0x180044b95  movups  xmmword ptr [rax+20h], xmm0
0x180044b99  movups  xmm1, xmmword ptr [rbp+7DCh]
0x180044ba0  movups  xmmword ptr [rax+30h], xmm1
0x180044ba4  cmp     [rsp+0A8h+arg_8], 0
0x180044bac  jz      loc_180044C3B
0x180044bb2  mov     ebx, 2
0x180044bb7  cmp     r13d, ebx
0x180044bba  jz      short loc_180044C3B
0x180044bbc  mov     rcx, r12
0x180044bbf  call    CDKreadBit
0x180044bc4  test    eax, eax
0x180044bc6  jz      short loc_180044BF5
0x180044bc8  lea     r13d, [rbx-1]
0x180044bcc  mov     dword ptr [rsi+224h], 1
0x180044bd6  mov     byte ptr [rsi+228h], 0FFh
0x180044bdd  cmp     [rbp+724h], r13d
0x180044be4  jz      short loc_180044BF5
0x180044be6  mov     edx, r13d; int
0x180044be9  mov     rcx, r14; struct CConcealmentInfo *
0x180044bec  call    ?CConcealment_GetLastFrameOk@@YAHPEAUCConcealmentInfo@@H@Z; CConcealment_GetLastFrameOk(CConcealmentInfo *,int)
0x180044bf1  test    eax, eax
0x180044bf3  jnz     short loc_180044C36
0x180044bf5  lea     r8, [rsp+0A8h+var_54]; int *
0x180044bfa  mov     rdx, r15; unsigned __int8 *
0x180044bfd  mov     rcx, rsi; struct CAacDecoderChannelInfo *
0x180044c00  call    ?CLpd_FAC_GetMemory@@YAPEAMPEAUCAacDecoderChannelInfo@@QEAEPEAH@Z; CLpd_FAC_GetMemory(CAacDecoderChannelInfo *,uchar * const,int *)
0x180044c05  mov     [rsi+200h], rax
0x180044c0c  mov     r10, rax
0x180044c0f  mov     eax, [rsi+69Ch]
0x180044c15  cmp     r13d, 1
0x180044c19  jnz     short loc_180044C1E
0x180044c1b  cdq
0x180044c1c  idiv    ebx
0x180044c1e  mov     r9d, 1; int
0x180044c24  mov     r8d, eax; int
0x180044c27  mov     rdx, r10; float *
0x180044c2a  mov     rcx, r12; struct CDK_BITSTREAM *
0x180044c2d  call    ?CLpd_FAC_Read@@YAHPEAUCDK_BITSTREAM@@PEAMHHH@Z; CLpd_FAC_Read(CDK_BITSTREAM *,float *,int,int,int)
0x180044c32  test    eax, eax
0x180044c34  jz      short loc_180044C3B
0x180044c36  mov     edi, 4002h
0x180044c3b  mov     rbx, [rsp+0A8h+arg_0]
0x180044c43  mov     eax, edi
  ... truncated ...
```
