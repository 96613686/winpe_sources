# KeyAtt_PcpCertifyKey12(void *,uint,uchar *,uint,uint,uchar *,uint,uchar const *,uint,uchar *,uint,uint *)

- ea: `0x18009366c`
- end: `0x1800942e2`
- name: `?KeyAtt_PcpCertifyKey12@@YAJPEAXIPEAEII1IPEBEI1IPEAI@Z`
- size: `3190`
- prototype: `__int64 __usercall@<rax>(TBS_HCONTEXT hContext@<rcx>, unsigned int@<edx>, unsigned __int8 *@<r8>, unsigned int@<r9d>, unsigned int, unsigned __int8 *, unsigned int, const unsigned __int8 *Source, rsize_t SourceSize, unsigned __int8 *, unsigned int, unsigned int *)`
- caller_count: `2`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x180051618`
- `0x180098970`

## callees

- `0x180015660`
- `0x1800157c0`
- `0x180029260`
- `0x18004d8b0`
- `0x1800592f4`
- `0x1800764d0`
- `0x180077028`
- `0x18007704c`
- `0x1800924d4`
- `0x18009366c`
- `0x1800942e8`
- `0x1800946d4`
- `0x180094714`
- `0x1800947cc`

## import_xrefs

- `tbs!Tbsi_ShaHash` at `0x180093a5d`
- `tbs!Tbsi_ShaHash` at `0x180093b08`
- `tbs!Tbsi_ShaHash` at `0x180093fa1`
- `tbs!Tbsi_ShaHash` at `0x180094039`
- `tbs!Tbsi_ShaHash` at `0x180094126`
- `tbs!Tbsi_ShaHash` at `0x1800941bb`
- `tbs!Tbsi_ShaHash` at `0x180093a5d`
- `tbs!Tbsi_ShaHash` at `0x180093b08`
- `tbs!Tbsi_ShaHash` at `0x180093fa1`
- `tbs!Tbsi_ShaHash` at `0x180094039`
- `tbs!Tbsi_ShaHash` at `0x180094126`
- `tbs!Tbsi_ShaHash` at `0x1800941bb`
- `tbs!Tbsip_Submit_Command` at `0x180093bbe`
- `tbs!Tbsip_Submit_Command` at `0x180093bbe`

## pseudocode

```c
__int64 __fastcall KeyAtt_PcpCertifyKey12(
        TBS_HCONTEXT hContext,
        unsigned int a2,
        unsigned __int8 *a3,
        __int64 a4,
        unsigned int a5,
        unsigned __int8 *a6,
        unsigned int a7,
        const unsigned __int8 *Source,
        rsize_t SourceSize,
        unsigned __int8 *a10,
        unsigned int DestinationSize,
        unsigned int *a12)
{
  unsigned int *v13; // r12
  unsigned int v15; // esi
  int v16; // ebx
  int v17; // esi
  int v18; // esi
  int v19; // eax
  UINT32 cbCommand; // edi
  int v21; // eax
  unsigned int v22; // edi
  unsigned int v23; // esi
  unsigned int v24; // r14d
  unsigned int v25; // r14d
  __int64 v26; // rsi
  rsize_t v27; // r14
  unsigned __int16 v28; // di
  unsigned int v29; // ebx
  unsigned int v30; // r13d
  unsigned int v31; // r12d
  unsigned int v32; // r15d
  int v33; // eax
  int v34; // eax
  int v35; // eax
  int v36; // eax
  char *v37; // r15
  unsigned int v38; // eax
  __int64 v40; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v41; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v42; // [rsp+4Ch] [rbp-B4h] BYREF
  unsigned int v43; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v44; // [rsp+54h] [rbp-ACh] BYREF
  unsigned __int16 v45[2]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int pcbResult; // [rsp+5Ch] [rbp-A4h] BYREF
  unsigned int v47; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v48; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned int v49; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v50[3]; // [rsp+6Ch] [rbp-94h] BYREF
  unsigned __int8 *v51; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int8 *v52; // [rsp+80h] [rbp-80h]
  unsigned int *v53; // [rsp+88h] [rbp-78h]
  void *v54; // [rsp+90h] [rbp-70h]
  _BYTE v55[24]; // [rsp+98h] [rbp-68h] BYREF
  __int128 v56; // [rsp+B0h] [rbp-50h] BYREF
  int v57; // [rsp+C0h] [rbp-40h]
  unsigned __int8 v58[16]; // [rsp+C4h] [rbp-3Ch] BYREF
  int v59; // [rsp+D4h] [rbp-2Ch]
  UCHAR pbBuffer[16]; // [rsp+D8h] [rbp-28h] BYREF
  int v61; // [rsp+E8h] [rbp-18h]
  BYTE v62; // [rsp+ECh] [rbp-14h]
  __int128 v63; // [rsp+F0h] [rbp-10h] BYREF
  int v64; // [rsp+100h] [rbp+0h]
  __int128 v65; // [rsp+104h] [rbp+4h] BYREF
  int v66; // [rsp+114h] [rbp+14h]
  __int128 v67; // [rsp+118h] [rbp+18h]
  int v68; // [rsp+128h] [rbp+28h]
  BYTE v69; // [rsp+12Ch] [rbp+2Ch]
  __int128 Buf1; // [rsp+130h] [rbp+30h] BYREF
  int v71; // [rsp+140h] [rbp+40h]
  __int128 Destination; // [rsp+148h] [rbp+48h] BYREF
  int v73; // [rsp+158h] [rbp+58h]
  BYTE pabResult[512]; // [rsp+160h] [rbp+60h] BYREF
  BYTE pabCommand[512]; // [rsp+360h] [rbp+260h] BYREF
  unsigned __int8 v76[512]; // [rsp+560h] [rbp+460h] BYREF

  v13 = a12;
  v52 = a6;
  v54 = a10;
  v53 = a12;
  LODWORD(v40) = 0;
  KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v55, L"KeyAtt_PcpCertifyKey12", (const int *)&v40);
  v41 = 0;
  memset_0(pabCommand, 0, sizeof(pabCommand));
  memset_0(pabResult, 0, sizeof(pabResult));
  memset_0(v76, 0, sizeof(v76));
  pcbResult = 512;
  HIDWORD(v40) = 0;
  v42 = 0;
  v43 = 0;
  v47 = 0;
  v15 = 0;
  v57 = 0;
  v59 = 0;
  v61 = 0;
  v62 = 0;
  v64 = 0;
  v66 = 0;
  v68 = 0;
  v69 = 0;
  v71 = 0;
  v73 = 0;
  v45[0] = 0;
  v44 = 0;
  v48 = 0;
  v49 = 0;
  memset(v50, 0, sizeof(v50));
  v51 = 0;
  v56 = 0;
  *(_OWORD *)v58 = 0;
  *(_OWORD *)pbBuffer = 0;
  v63 = 0;
  v65 = 0;
  v67 = 0;
  Buf1 = 0;
  Destination = 0;
  if ( !hContext || !a2 || !a5 || Source && (_DWORD)SourceSize != 20 || !a12 )
    goto LABEL_127;
  *a12 = 0;
  if ( Source )
    memcpy_s(&Destination, 0x14u, Source, (unsigned int)SourceSize);
  if ( a6 )
  {
    LODWORD(v40) = KeyAtt_StartOIAPSession(hContext, &v47, v58, pbBuffer);
    v16 = v40;
    if ( (int)v40 < 0 )
      goto LABEL_129;
    LODWORD(v40) = WriteBigEndian(pabCommand, 0x200u, (unsigned int *)&v40 + 1, 0xC2u);
    v16 = v40;
    if ( (int)v40 < 0 )
      goto LABEL_129;
    v15 = v47;
  }
  else
  {
    LODWORD(v40) = WriteBigEndian(pabCommand, 0x200u, (unsigned int *)&v40 + 1, 0xC1u);
    v16 = v40;
    if ( (int)v40 < 0 )
      goto LABEL_129;
  }
  LODWORD(v40) = WriteBigEndian(pabCommand, 0x200u, (unsigned int *)&v40 + 1, 0x26u);
  v16 = v40;
  if ( (int)v40 < 0 )
    goto LABEL_129;
  LODWORD(v40) = WriteBigEndian(pabCommand, 0x200u, (unsigned int *)&v40 + 1, 0x32u);
  v16 = v40;
  if ( (int)v40 < 0 )
    goto LABEL_129;
  LODWORD(v40) = WriteBigEndian(pabCommand, 0x200u, (unsigned int *)&v40 + 1, a2);
  v16 = v40;
  if ( (int)v40 < 0 )
    goto LABEL_129;
  LODWORD(v40) = WriteBigEndian(pabCommand, 0x200u, (unsigned int *)&v40 + 1, a5);
  v16 = v40;
  if ( (int)v40 < 0 )
    goto LABEL_129;
  LODWORD(v40) = WriteBigEndian(
                   pabCommand,
                   0x200u,
                   (unsigned int *)&v40 + 1,
                   (const unsigned __int8 *)&Destination,
                   0x14u);
  v16 = v40;
  if ( (int)v40 < 0 )
    goto LABEL_129;
  if ( !v15 )
  {
    cbCommand = HIDWORD(v40);
    goto LABEL_46;
  }
  LODWORD(v40) = WriteBigEndian(pabCommand, 0x200u, (unsigned int *)&v40 + 1, v15);
  v16 = v40;
  if ( (int)v40 < 0 )
    goto LABEL_129;
  LODWORD(v40) = WriteBigEndian(pabCommand, 0x200u, (unsigned int *)&v40 + 1, pbBuffer, 0x14u);
  v16 = v40;
  if ( (int)v40 < 0 )
    goto LABEL_129;
  v17 = HIDWORD(v40);
  if ( HIDWORD(v40) >= 0x200 )
  {
LABEL_127:
    v16 = -2147024809;
    goto LABEL_128;
  }
  pabCommand[HIDWORD(v40)] = v62;
  v18 = v17 + 1;
  LODWORD(v40) = WriteBigEndian(v76, 0x200u, &v42, 0x32u);
  v16 = v40;
  if ( (int)v40 < 0 )
    goto LABEL_129;
  LODWORD(v40) = WriteBigEndian(v76, 0x200u, &v42, (const unsigned __int8 *)&Destination, 0x14u);
  v16 = v40;
  if ( (int)v40 < 0 )
    goto LABEL_129;
  v19 = Tbsi_ShaHash(L"SHA1", 0, 0, v76, v42, &v56, 20, &v41, v40);
  if ( v19 )
  {
    if ( (v19 & 0xFFFF000) == 0x290000 )
    {
      v16 = v19 & 0xFFF | 0x80280000;
    }
    else if ( (v19 & 0xFFF0000) == 0x70000 )
    {
      v16 = (unsigned __int16)v19;
      if ( (_WORD)v19 )
        v16 = (unsigned __int16)v19 | 0x80070000;
    }
    else
    {
      v16 = v19 | 0x10000000;
    }
    LODWORD(v40) = v16;
    if ( v16 < 0 )
      goto LABEL_129;
  }
  else
  {
    LODWORD(v40) = 0;
  }
  cbCommand = v18 + 20;
  if ( (unsigned int)(v18 + 20) > 0x200 )
    goto LABEL_53;
  v21 = Tbsi_ShaHash(L"SHA1", a6, a7, &v56, 61, &pabCommand[v18], 20, &v41, v40);
  if ( v21 )
  {
    if ( (v21 & 0xFFFF000) == 0x290000 )
    {
      v16 = v21 & 0xFFF | 0x80280000;
    }
    else if ( (v21 & 0xFFF0000) == 0x70000 )
    {
      v16 = (unsigned __int16)v21;
      if ( (_WORD)v21 )
        v16 = (unsigned __int16)v21 | 0x80070000;
    }
    else
    {
      v16 = v21 | 0x10000000;
    }
    LODWORD(v40) = v16;
    if ( v16 < 0 )
      goto LABEL_129;
  }
  else
  {
    LODWORD(v40) = 0;
  }
LABEL_46:
  pabCommand[5] = cbCommand;
  pabCommand[2] = HIBYTE(cbCommand);
  pabCommand[3] = BYTE2(cbCommand);
  pabCommand[4] = BYTE1(cbCommand);
  LODWORD(v40) = Tbsip_Submit_Command(hContext, 0, 0xC8u, pabCommand, cbCommand, pabResult, &pcbResult);
  v16 = v40;
  if ( (int)v40 >= 0 )
  {
    v22 = pcbResult;
    LODWORD(v40) = ReadBigEndian(pabResult, pcbResult, &v43, v45);
    v16 = v40;
    if ( (int)v40 >= 0 )
    {
      LODWORD(v40) = ReadBigEndian(pabResult, v22, &v43, &v48);
      v16 = v40;
      if ( (int)v40 >= 0 )
      {
        if ( v48 != v22 )
          goto LABEL_53;
        LODWORD(v40) = ReadBigEndian(pabResult, v22, &v43, &v49);
        v16 = v40;
        if ( (int)v40 >= 0 )
        {
          if ( v49 )
          {
            if ( (v49 & 0xFFFF0000) == 0 )
            {
              v16 = v49 | 0x80280000;
              goto LABEL_128;
            }
LABEL_53:
            v16 = -2147467259;
LABEL_128:
            LODWORD(v40) = v16;
            goto LABEL_129;
          }
          v23 = v43;
          HIDWORD(v40) = v43;
          LODWORD(v40) = ReadBigEndian(pabResult, v22, (unsigned int *)&v40 + 1, &v44);
          v16 = v40;
          if ( (int)v40 >= 0 )
          {
            if ( v44 == 257 )
            {
              HIDWORD(v40) = v23 + 19;
              LODWORD(v40) = ReadBigEndian(pabResult, v22, (unsigned int *)&v40 + 1, &v41);
              v16 = v40;
              if ( (int)v40 < 0 )
                goto LABEL_129;
              v24 = v41 + 64;
            }
            else
            {
              if ( v44 != 41 )
                goto LABEL_53;
              HIDWORD(v40) = v23 + 19;
              LODWORD(v40) = ReadBigEndian(pabResult, v22, (unsigned int *)&v40 + 1, &v41);
              v16 = v40;
              if ( (int)v40 < 0 )
                goto LABEL_129;
              v25 = v41 + 64;
              HIDWORD(v40) = v41 + 64 + v23;
              LODWORD(v40) = ReadBigEndian(pabResult, v22, (unsigned int *)&v40 + 1, &v41);
              v16 = v40;
              if ( (int)v40 < 0 )
                goto LABEL_129;
              v24 = v41 + 4 + v25;
            }
            HIDWORD(v40) = v24 + v23;
            LODWORD(v40) = ReadBigEndian(pabResult, v22, (unsigned int *)&v40 + 1, &v41);
            v16 = v40;
            if ( (int)v40 < 0 )
              goto LABEL_129;
            v26 = v24 + v41 + 4;
            LODWORD(v40) = ReadBigEndian(pabResult, v22, &v43, (unsigned __int8 **)&v50[1], v24 + v41 + 4);
            v16 = v40;
            if ( (int)v40 < 0 )
              goto LABEL_129;
            LODWORD(v40) = ReadBigEndian(pabResult, v22, &v43, v50);
            v16 = v40;
            if ( (int)v40 < 0 )
              goto LABEL_129;
            v27 = v50[0];
            LODWORD(v40) = ReadBigEndian(pabResult, v22, &v43, &v51, v50[0]);
            v16 = v40;
            if ( (int)v40 < 0 )
              goto LABEL_129;
            v28 = v45[0];
            if ( v45[0] != 196 )
            {
              v42 = 0;
              memset_0(v76, 0, sizeof(v76));
              LODWORD(v40) = WriteBigEndian(v76, 0x200u, &v42, 0);
              v16 = v40;
              if ( (int)v40 < 0 )
                goto LABEL_129;
              LODWORD(v40) = WriteBigEndian(v76, 0x200u, &v42, 0x32u);
              v16 = v40;
              if ( (int)v40 < 0 )
                goto LABEL_129;
              LODWORD(v40) = WriteBigEndian(v76, 0x200u, &v42, *(const unsigned __int8 **)&v50[1], v26);
              v16 = v40;
              if ( (int)v40 < 0 )
                goto LABEL_129;
              LODWORD(v40) = WriteBigEndian(v76, 0x200u, &v42, v27);
              v16 = v40;
              if ( (int)v40 < 0 )
                goto LABEL_129;
              LODWORD(v40) = WriteBigEndian(v76, 0x200u, &v42, v51, v27);
              v16 = v40;
              if ( (int)v40 < 0 )
                goto LABEL_129;
              v29 = v43;
              if ( v28 == 197 && v43 + 40 + 1LL != pcbResult
                || v28 == 198 && v43 + 80 + 2LL != pcbResult
                || memcpy_s(v58, 0x14u, &pabResult[v43], 0x14u) )
              {
                goto LABEL_53;
              }
              v30 = v29 + 21;
              v62 = pabResult[v29 + 20];
              v31 = v42;
              v32 = v29 + 41;
              v33 = Tbsi_ShaHash(L"SHA1", 0, 0, v76, v42, &v56, 20, &v41, v40);
              if ( v33 )
              {
                if ( (v33 & 0xFFFF000) == 0x290000 )
                {
                  v16 = v33 & 0xFFF | 0x80280000;
                }
                else if ( (v33 & 0xFFF0000) == 0x70000 )
                {
                  v16 = (unsigned __int16)v33;
                  if ( (_WORD)v33 )
                    v16 = (unsigned __int16)v33 | 0x80070000;
                }
                else
                {
                  v16 = v33 | 0x10000000;
                }
                LODWORD(v40) = v16;
                if ( v16 < 0 )
                  goto LABEL_129;
              }
              else
              {
                LODWORD(v40) = 0;
              }
              v34 = Tbsi_ShaHash(L"SHA1", v52, a7, &v56, 61, &Buf1, 20, &v41, v40);
              v16 = v34;
              if ( v34 )
              {
                if ( (v34 & 0xFFFF000) == 0x290000 )
                {
                  v16 = v34 & 0xFFF | 0x80280000;
                }
                else if ( (v34 & 0xFFF0000) == 0x70000 )
                {
                  v16 = (unsigned __int16)v34;
                  if ( (_WORD)v34 )
                    v16 = (unsigned __int16)v34 | 0x80070000;
                }
                else
                {
                  v16 = v34 | 0x10000000;
                }
                LODWORD(v40) = v16;
                if ( v16 < 0 )
                  goto LABEL_129;
              }
              else
              {
                LODWORD(v40) = 0;
              }
              if ( memcmp_0(&Buf1, &pabResult[v30], 0x14u) )
                goto LABEL_53;
              if ( v28 == 198 )
              {
                if ( memcpy_s(&v65, 0x14u, &pabResult[v32], 0x14u) )
                  goto LABEL_53;
                v69 = pabResult[v32 + 20];
                v35 = Tbsi_ShaHash(L"SHA1", 0, 0, v76, v31, &v63, 20, &v41, v40);
                if ( v35 )
                {
                  if ( (v35 & 0xFFFF000) == 0x290000 )
                  {
                    v16 = v35 & 0xFFF | 0x80280000;
                  }
                  else if ( (v35 & 0xFFF0000) == 0x70000 )
                  {
                    v16 = (unsigned __int16)v35;
                    if ( (_WORD)v35 )
                      v16 = (unsigned __int16)v35 | 0x80070000;
                  }
                  else
                  {
                    v16 = v35 | 0x10000000;
                  }
                  LODWORD(v40) = v16;
                  if ( v16 < 0 )
                    goto LABEL_129;
                }
                else
                {
                  LODWORD(v40) = 0;
                }
                v36 = Tbsi_ShaHash(L"SHA1", v52, a7, &v63, 61, &Buf1, 20, &v41, v40);
                v16 = v36;
                if ( v36 )
                {
                  if ( (v36 & 0xFFFF000) == 0x290000 )
                  {
                    v16 = v36 & 0xFFF | 0x80280000;
                  }
                  else if ( (v36 & 0xFFF0000) == 0x70000 )
                  {
                    v16 = (unsigned __int16)v36;
                    if ( (_WORD)v36 )
                      v16 = (unsigned __int16)v36 | 0x80070000;
                  }
                  else
                  {
                    v16 = v36 | 0x10000000;
                  }
                  LODWORD(v40) = v16;
                  if ( v16 < 0 )
                    goto LABEL_129;
                }
                else
                {
                  LODWORD(v40) = 0;
                }
                if ( memcmp_0(&Buf1, &pabResult[v32 + 21], 0x14u) )
                  goto LABEL_53;
              }
              v13 = v53;
            }
            v37 = (char *)v54;
            v38 = v27 + v26;
            v41 = v27 + v26;
            if ( v54 && DestinationSize )
            {
              *v13 = v38;
              if ( DestinationSize < v38 )
              {
                v16 = -2147024774;
                goto LABEL_128;
              }
              if ( memcpy_s(v37, DestinationSize, *(const void *const *)&v50[1], (unsigned int)v26)
                || memcpy_s(&v37[v26], DestinationSize - (unsigned int)v26, v51, v27) )
              {
                goto LABEL_53;
              }
              v16 = v40;
            }
            else
            {
              *v13 = v38;
            }
          }
        }
      }
    }
  }
LABEL_129:
  KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v55);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x18009366c  push    rbp
0x18009366e  push    rbx
0x18009366f  push    rsi
0x180093670  push    rdi
0x180093671  push    r12
0x180093673  push    r13
0x180093675  push    r14
0x180093677  push    r15
0x180093679  lea     rbp, [rsp-678h]
0x180093681  sub     rsp, 778h
0x180093688  mov     rax, cs:__security_cookie
0x18009368f  xor     rax, rsp
0x180093692  mov     [rbp+6B0h+var_50], rax
0x180093699  mov     rax, [rbp+6B0h+arg_48]
0x1800936a0  lea     r8, [rsp+7B0h+var_770]; int *
0x1800936a5  mov     r13, [rbp+6B0h+arg_28]
0x1800936ac  mov     r14d, edx
0x1800936af  mov     r12, [rbp+6B0h+arg_58]
0x1800936b6  lea     rdx, aKeyattPcpcerti; "KeyAtt_PcpCertifyKey12"
0x1800936bd  mov     rbx, [rbp+6B0h+Source]
0x1800936c4  mov     r15, rcx
0x1800936c7  lea     rcx, [rbp+6B0h+var_718]; this
0x1800936cb  mov     [rbp+6B0h+var_730], r13
0x1800936cf  mov     [rbp+6B0h+var_720], rax
0x1800936d3  mov     [rbp+6B0h+var_728], r12
0x1800936d7  mov     [rsp+7B0h+var_770], 0
0x1800936df  call    ??0KspFunctionLogger@@QEAA@QEBGAEBJ@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,long const &)
0x1800936e4  mov     edi, 200h
0x1800936e9  mov     [rsp+7B0h+var_768], 0
0x1800936f1  mov     r8d, edi; Size
0x1800936f4  lea     rcx, [rbp+6B0h+pabCommand]; void *
0x1800936fb  xor     edx, edx; Val
0x1800936fd  call    memset_0
0x180093702  mov     r8d, edi; Size
0x180093705  lea     rcx, [rbp+6B0h+var_650]; void *
0x180093709  xor     edx, edx; Val
0x18009370b  call    memset_0
0x180093710  mov     r8d, edi; Size
0x180093713  lea     rcx, [rbp+6B0h+var_250]; void *
0x18009371a  xor     edx, edx; Val
0x18009371c  call    memset_0
0x180093721  xor     r11d, r11d
0x180093724  mov     [rsp+7B0h+var_754], edi
0x180093728  xor     eax, eax
0x18009372a  mov     [rsp+7B0h+var_76C], r11d
0x18009372f  mov     [rsp+7B0h+var_764], r11d
0x180093734  xorps   xmm0, xmm0
0x180093737  mov     [rsp+7B0h+var_760], r11d
0x18009373c  xorps   xmm1, xmm1
0x18009373f  mov     [rsp+7B0h+var_750], r11d
0x180093744  mov     esi, r11d
0x180093747  mov     [rbp+6B0h+var_6F0], eax
0x18009374a  mov     [rbp+6B0h+var_6DC], eax
0x18009374d  mov     [rbp+6B0h+var_6C8], eax
0x180093750  mov     [rbp+6B0h+var_6C4], r11b
0x180093754  mov     [rbp+6B0h+var_6B0], eax
0x180093757  mov     [rbp+6B0h+var_69C], eax
0x18009375a  mov     [rbp+6B0h+var_688], eax
0x18009375d  mov     [rbp+6B0h+var_684], r11b
0x180093761  mov     [rbp+6B0h+var_670], eax
0x180093764  mov     [rbp+6B0h+var_658], eax
0x180093767  mov     [rsp+7B0h+var_758], r11w
0x18009376d  mov     [rsp+7B0h+var_75C], r11w
0x180093773  mov     [rsp+7B0h+var_74C], r11d
0x180093778  mov     [rsp+7B0h+var_748], r11d
0x18009377d  mov     qword ptr [rsp+7B0h+var_744+4], r11
0x180093782  mov     dword ptr [rsp+7B0h+var_744], r11d
0x180093787  mov     [rsp+7B0h+var_738], r11
0x18009378c  movups  [rbp+6B0h+var_700], xmm0
0x180093790  movups  xmmword ptr [rbp+6B0h+var_6EC], xmm1
0x180093794  movups  xmmword ptr [rbp+6B0h+pbBuffer], xmm0
0x180093798  movups  [rbp+6B0h+var_6C0], xmm0
0x18009379c  movups  [rbp+6B0h+var_6AC], xmm1
0x1800937a0  movups  [rbp+6B0h+var_698], xmm0
0x1800937a4  movups  [rbp+6B0h+Buf1], xmm0
0x1800937a8  movups  [rbp+6B0h+Destination], xmm1
0x1800937ac  test    r15, r15
0x1800937af  jz      loc_1800942AA
0x1800937b5  test    r14d, r14d
0x1800937b8  jz      loc_1800942AA
0x1800937be  mov     edi, [rbp+6B0h+arg_20]
0x1800937c4  test    edi, edi
0x1800937c6  jz      loc_1800942AA
0x1800937cc  test    rbx, rbx
0x1800937cf  jz      short loc_1800937DE
0x1800937d1  cmp     dword ptr [rbp+6B0h+SourceSize], 14h
0x1800937d8  jnz     loc_1800942AA
0x1800937de  test    r12, r12
0x1800937e1  jz      loc_1800942AA
0x1800937e7  mov     [r12], r11d
0x1800937eb  test    rbx, rbx
0x1800937ee  jz      short loc_180093808
0x1800937f0  mov     r9d, dword ptr [rbp+6B0h+SourceSize]; SourceSize
0x1800937f7  lea     rcx, [rbp+6B0h+Destination]; Destination
0x1800937fb  mov     r8, rbx; Source
0x1800937fe  mov     edx, 14h; DestinationSize
0x180093803  call    memcpy_s
0x180093808  test    r13, r13
0x18009380b  jz      short loc_180093860
0x18009380d  lea     r9, [rbp+6B0h+pbBuffer]; pbBuffer
0x180093811  mov     rcx, r15; hContext
0x180093814  lea     r8, [rbp+6B0h+var_6EC]; Destination
0x180093818  lea     rdx, [rsp+7B0h+var_750]; unsigned int *
0x18009381d  call    ?KeyAtt_StartOIAPSession@@YAJPEAXPEAIPEAE2@Z; KeyAtt_StartOIAPSession(void *,uint *,uchar *,uchar *)
0x180093822  mov     [rsp+7B0h+var_770], eax
0x180093826  mov     ebx, eax
0x180093828  test    eax, eax
0x18009382a  js      loc_1800942B3
0x180093830  mov     r9d, 0C2h; unsigned __int16
0x180093836  lea     r8, [rsp+7B0h+var_76C]; unsigned int *
0x18009383b  mov     edx, 200h; unsigned int
0x180093840  lea     rcx, [rbp+6B0h+pabCommand]; unsigned __int8 *
0x180093847  call    ?WriteBigEndian@@YAJPEAEIPEAIG@Z; WriteBigEndian(uchar *,uint,uint *,ushort)
0x18009384c  mov     [rsp+7B0h+var_770], eax
0x180093850  mov     ebx, eax
0x180093852  test    eax, eax
0x180093854  js      loc_1800942B3
0x18009385a  mov     esi, [rsp+7B0h+var_750]
0x18009385e  jmp     short loc_18009388A
0x180093860  mov     r9d, 0C1h; unsigned __int16
0x180093866  lea     r8, [rsp+7B0h+var_76C]; unsigned int *
0x18009386b  mov     edx, 200h; unsigned int
0x180093870  lea     rcx, [rbp+6B0h+pabCommand]; unsigned __int8 *
0x180093877  call    ?WriteBigEndian@@YAJPEAEIPEAIG@Z; WriteBigEndian(uchar *,uint,uint *,ushort)
0x18009387c  mov     [rsp+7B0h+var_770], eax
0x180093880  mov     ebx, eax
0x180093882  test    eax, eax
0x180093884  js      loc_1800942B3
0x18009388a  mov     r9d, 26h ; '&'; unsigned int
0x180093890  lea     r8, [rsp+7B0h+var_76C]; unsigned int *
0x180093895  mov     edx, 200h; unsigned int
0x18009389a  lea     rcx, [rbp+6B0h+pabCommand]; unsigned __int8 *
0x1800938a1  call    ?WriteBigEndian@@YAJPEAEIPEAII@Z; WriteBigEndian(uchar *,uint,uint *,uint)
0x1800938a6  mov     [rsp+7B0h+var_770], eax
0x1800938aa  mov     ebx, eax
0x1800938ac  test    eax, eax
0x1800938ae  js      loc_1800942B3
0x1800938b4  mov     r9d, 32h ; '2'; unsigned int
0x1800938ba  lea     r8, [rsp+7B0h+var_76C]; unsigned int *
0x1800938bf  mov     edx, 200h; unsigned int
0x1800938c4  lea     rcx, [rbp+6B0h+pabCommand]; unsigned __int8 *
0x1800938cb  call    ?WriteBigEndian@@YAJPEAEIPEAII@Z; WriteBigEndian(uchar *,uint,uint *,uint)
0x1800938d0  mov     [rsp+7B0h+var_770], eax
0x1800938d4  mov     ebx, eax
0x1800938d6  test    eax, eax
0x1800938d8  js      loc_1800942B3
0x1800938de  mov     r9d, r14d; unsigned int
0x1800938e1  lea     r8, [rsp+7B0h+var_76C]; unsigned int *
0x1800938e6  mov     r14d, 200h
0x1800938ec  lea     rcx, [rbp+6B0h+pabCommand]; unsigned __int8 *
0x1800938f3  mov     edx, r14d; unsigned int
0x1800938f6  call    ?WriteBigEndian@@YAJPEAEIPEAII@Z; WriteBigEndian(uchar *,uint,uint *,uint)
0x1800938fb  mov     [rsp+7B0h+var_770], eax
0x1800938ff  mov     ebx, eax
0x180093901  test    eax, eax
0x180093903  js      loc_1800942B3
0x180093909  mov     r9d, edi; unsigned int
0x18009390c  lea     r8, [rsp+7B0h+var_76C]; unsigned int *
0x180093911  mov     edx, r14d; unsigned int
0x180093914  lea     rcx, [rbp+6B0h+pabCommand]; unsigned __int8 *
0x18009391b  call    ?WriteBigEndian@@YAJPEAEIPEAII@Z; WriteBigEndian(uchar *,uint,uint *,uint)
0x180093920  mov     [rsp+7B0h+var_770], eax
0x180093924  mov     ebx, eax
0x180093926  test    eax, eax
0x180093928  js      loc_1800942B3
0x18009392e  mov     edi, 14h
0x180093933  lea     r9, [rbp+6B0h+Destination]; unsigned __int8 *
0x180093937  lea     r8, [rsp+7B0h+var_76C]; unsigned int *
0x18009393c  mov     [rsp+7B0h+cbCommand], edi; unsigned int
0x180093940  mov     edx, r14d; unsigned int
0x180093943  lea     rcx, [rbp+6B0h+pabCommand]; unsigned __int8 *
0x18009394a  call    ?WriteBigEndian@@YAJPEAEIPEAIPEBEI@Z; WriteBigEndian(uchar *,uint,uint *,uchar const *,uint)
0x18009394f  mov     [rsp+7B0h+var_770], eax
0x180093953  mov     ebx, eax
0x180093955  test    eax, eax
0x180093957  js      loc_1800942B3
0x18009395d  test    esi, esi
0x18009395f  jz      loc_180093B69
0x180093965  mov     r9d, esi; unsigned int
0x180093968  lea     r8, [rsp+7B0h+var_76C]; unsigned int *
0x18009396d  mov     edx, r14d; unsigned int
0x180093970  lea     rcx, [rbp+6B0h+pabCommand]; unsigned __int8 *
0x180093977  call    ?WriteBigEndian@@YAJPEAEIPEAII@Z; WriteBigEndian(uchar *,uint,uint *,uint)
0x18009397c  mov     [rsp+7B0h+var_770], eax
0x180093980  mov     ebx, eax
0x180093982  test    eax, eax
0x180093984  js      loc_1800942B3
0x18009398a  lea     r9, [rbp+6B0h+pbBuffer]; unsigned __int8 *
0x18009398e  mov     [rsp+7B0h+cbCommand], edi; unsigned int
0x180093992  lea     r8, [rsp+7B0h+var_76C]; unsigned int *
0x180093997  mov     edx, r14d; unsigned int
0x18009399a  lea     rcx, [rbp+6B0h+pabCommand]; unsigned __int8 *
0x1800939a1  call    ?WriteBigEndian@@YAJPEAEIPEAIPEBEI@Z; WriteBigEndian(uchar *,uint,uint *,uchar const *,uint)
0x1800939a6  mov     [rsp+7B0h+var_770], eax
0x1800939aa  mov     ebx, eax
0x1800939ac  test    eax, eax
0x1800939ae  js      loc_1800942B3
0x1800939b4  mov     esi, [rsp+7B0h+var_76C]
0x1800939b8  cmp     esi, r14d
0x1800939bb  ja      loc_1800942AA
0x1800939c1  mov     eax, r14d
0x1800939c4  sub     eax, esi
0x1800939c6  cmp     eax, 1
0x1800939c9  jb      loc_1800942AA
0x1800939cf  mov     al, [rbp+6B0h+var_6C4]
0x1800939d2  lea     r9d, [rdi+1Eh]; unsigned int
0x1800939d6  mov     [rbp+rsi+6B0h+pabCommand], al
0x1800939dd  lea     r8, [rsp+7B0h+var_764]; unsigned int *
0x1800939e2  mov     edx, r14d; unsigned int
0x1800939e5  lea     rcx, [rbp+6B0h+var_250]; unsigned __int8 *
0x1800939ec  inc     esi
0x1800939ee  call    ?WriteBigEndian@@YAJPEAEIPEAII@Z; WriteBigEndian(uchar *,uint,uint *,uint)
0x1800939f3  mov     [rsp+7B0h+var_770], eax
0x1800939f7  mov     ebx, eax
0x1800939f9  test    eax, eax
0x1800939fb  js      loc_1800942B3
0x180093a01  lea     r9, [rbp+6B0h+Destination]; unsigned __int8 *
0x180093a05  mov     [rsp+7B0h+cbCommand], edi; unsigned int
0x180093a09  lea     r8, [rsp+7B0h+var_764]; unsigned int *
0x180093a0e  mov     edx, r14d; unsigned int
0x180093a11  lea     rcx, [rbp+6B0h+var_250]; unsigned __int8 *
0x180093a18  call    ?WriteBigEndian@@YAJPEAEIPEAIPEBEI@Z; WriteBigEndian(uchar *,uint,uint *,uchar const *,uint)
0x180093a1d  mov     [rsp+7B0h+var_770], eax
0x180093a21  mov     ebx, eax
0x180093a23  test    eax, eax
0x180093a25  js      loc_1800942B3
0x180093a2b  lea     rax, [rsp+7B0h+var_768]
0x180093a30  xor     r8d, r8d
0x180093a33  mov     [rsp+7B0h+var_778], rax
0x180093a38  lea     r9, [rbp+6B0h+var_250]
0x180093a3f  lea     rax, [rbp+6B0h+var_700]
0x180093a43  mov     dword ptr [rsp+7B0h+pcbResult], edi
0x180093a47  mov     [rsp+7B0h+pabResult], rax
0x180093a4c  lea     rcx, aSha1_0; "SHA1"
0x180093a53  mov     eax, [rsp+7B0h+var_764]
0x180093a57  xor     edx, edx
0x180093a59  mov     [rsp+7B0h+cbCommand], eax
0x180093a5d  call    cs:__imp_Tbsi_ShaHash
0x180093a64  nop     dword ptr [rax+rax+00h]
0x180093a69  mov     ebx, eax
0x180093a6b  test    eax, eax
0x180093a6d  jnz     short loc_180093A75
0x180093a6f  mov     [rsp+7B0h+var_770], eax
0x180093a73  jmp     short loc_180093ABC
0x180093a75  and     eax, 0FFFF000h
0x180093a7a  cmp     eax, 290000h
0x180093a7f  jnz     short loc_180093A8F
0x180093a81  and     ebx, 0FFFh
0x180093a87  or      ebx, 80280000h
0x180093a8d  jmp     short loc_180093AB0
0x180093a8f  mov     eax, ebx
0x180093a91  and     eax, 0FFF0000h
0x180093a96  cmp     eax, 70000h
0x180093a9b  jnz     short loc_180093AAC
0x180093a9d  movzx   ebx, bx
0x180093aa0  test    ebx, ebx
0x180093aa2  jz      short loc_180093AB0
0x180093aa4  or      ebx, 80070000h
0x180093aaa  jmp     short loc_180093AB0
0x180093aac  bts     ebx, 1Ch
0x180093ab0  mov     [rsp+7B0h+var_770], ebx
0x180093ab4  test    ebx, ebx
0x180093ab6  js      loc_1800942B3
0x180093abc  lea     edi, [rsi+14h]
0x180093abf  cmp     edi, r14d
0x180093ac2  ja      loc_180093C5B
0x180093ac8  mov     r8d, [rbp+6B0h+arg_30]
0x180093acf  lea     rcx, [rbp+6B0h+pabCommand]
0x180093ad6  mov     eax, esi
0x180093ad8  lea     r9, [rbp+6B0h+var_700]
0x180093adc  add     rcx, rax
0x180093adf  mov     rdx, r13
0x180093ae2  lea     rax, [rsp+7B0h+var_768]
0x180093ae7  mov     [rsp+7B0h+var_778], rax
0x180093aec  mov     dword ptr [rsp+7B0h+pcbResult], 14h
0x180093af4  mov     [rsp+7B0h+pabResult], rcx
0x180093af9  lea     rcx, aSha1_0; "SHA1"
0x180093b00  mov     [rsp+7B0h+cbCommand], 3Dh ; '='
0x180093b08  call    cs:__imp_Tbsi_ShaHash
0x180093b0f  nop     dword ptr [rax+rax+00h]
0x180093b14  mov     ebx, eax
0x180093b16  test    eax, eax
0x180093b18  jnz     short loc_180093B20
0x180093b1a  mov     [rsp+7B0h+var_770], eax
0x180093b1e  jmp     short loc_180093B6D
0x180093b20  and     eax, 0FFFF000h
0x180093b25  cmp     eax, 290000h
0x180093b2a  jnz     short loc_180093B3A
0x180093b2c  and     ebx, 0FFFh
0x180093b32  or      ebx, 80280000h
0x180093b38  jmp     short loc_180093B5B
0x180093b3a  mov     eax, ebx
0x180093b3c  and     eax, 0FFF0000h
0x180093b41  cmp     eax, 70000h
0x180093b46  jnz     short loc_180093B57
0x180093b48  movzx   ebx, bx
0x180093b4b  test    ebx, ebx
0x180093b4d  jz      short loc_180093B5B
0x180093b4f  or      ebx, 80070000h
0x180093b55  jmp     short loc_180093B5B
  ... truncated ...
```
