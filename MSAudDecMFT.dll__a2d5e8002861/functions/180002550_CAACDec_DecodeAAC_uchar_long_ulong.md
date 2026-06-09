# CAACDec::DecodeAAC(uchar *,long,ulong *)

- ea: `0x180002550`
- end: `0x180003549`
- name: `?DecodeAAC@CAACDec@@IEAAJPEAEJPEAK@Z`
- size: `4089`
- prototype: `__int64 __fastcall(CAACDec *__hidden this, unsigned __int8 *, int, unsigned int *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x1800019d0`

## callees

- `0x180001740`
- `0x1800018d0`
- `0x1800018ec`
- `0x180002550`
- `0x180003af0`
- `0x180003ec8`
- `0x180004fe0`
- `0x18003e4f0`
- `0x180058eac`
- `0x18005d170`
- `0x18005d1f8`
- `0x1800960c0`

## string_xrefs

- `0x1800029f3`: `CAACDec::DecodeAAC() Finished parsing ADTS header: m_dwInSamplesPerSec=%d, m_dwAACTransportStreamChannelConfig=%d, m_dwAACFrameSize=%d, m_fAACCRCExist=%d, pusCRC=0x%p`
- `0x180003025`: `ASC was read`
- `0x180003031`: `ASC was not read`
- `0x18000303d`: `CAACDec::DecodeAAC() ReadLATM() was successful. %s`
- `0x1800033f1`: `CAACDec::DecodeAAC() Finished parsing LOAS/LATM headers: m_dwInSamplesPerSec=%d, *m_pdwAACTransportStreamChannelConfig=%d, m_dwAACFrameSize=%d, dwByteOffsetToPayloadMux=%d, dwBitOffsetToPayloadMux=%d`

## pseudocode

```c
__int64 __fastcall CAACDec::DecodeAAC(CAACDec *this, unsigned __int8 *a2, int a3, unsigned int *a4)
{
  TraceLoggingHelperBase *v4; // rsi
  unsigned int *v5; // r12
  int v6; // r15d
  unsigned int v9; // edi
  int v10; // ecx
  __int64 v11; // rax
  unsigned __int8 *v12; // r14
  int v13; // eax
  unsigned int v14; // eax
  int v15; // ecx
  int v16; // ecx
  int v18; // ecx
  __int64 v19; // rax
  _BYTE *v20; // rcx
  _BYTE *v21; // rdx
  int *v22; // r15
  unsigned int v23; // r8d
  int v24; // ecx
  __int64 v25; // rax
  int v26; // ecx
  __int64 v27; // r14
  int v28; // eax
  __int64 v29; // rdx
  __int64 v30; // rax
  int v31; // ecx
  int v32; // r14d
  int v33; // eax
  int v34; // eax
  int v35; // edx
  unsigned __int16 v36; // cx
  unsigned int v37; // r8d
  unsigned int v38; // edi
  int *v39; // rcx
  int v40; // r8d
  unsigned int v41; // eax
  char v42; // r8
  int *v43; // rdx
  bool v44; // zf
  _BYTE *v45; // rax
  int v46; // eax
  _BYTE *v47; // rcx
  char v48; // r8
  int *v49; // rdx
  _BYTE *v50; // rax
  int v51; // eax
  __int64 v52; // rdx
  __int64 v53; // rcx
  int v54; // eax
  __int64 v55; // r8
  _BYTE *v56; // rcx
  unsigned int v57; // edx
  _DWORD *v58; // rdi
  unsigned int TotalNumberOfBitsRead; // r15d
  const char *v60; // rcx
  unsigned int v61; // ecx
  unsigned int v62; // r8d
  _DWORD *v63; // rdi
  unsigned int v64; // eax
  int v65; // ecx
  char *v66; // rdx
  char *v67; // rax
  int v68; // ecx
  __int64 v69; // rdx
  int v70; // r9d
  __int64 v71; // rax
  int v72; // ecx
  int v73; // edi
  int v74; // eax
  int v75; // eax
  _DWORD *v76; // rcx
  int v77; // edi
  unsigned int v78; // r15d
  __int64 v79; // rcx
  int v80; // r8d
  unsigned int v81; // eax
  __int64 v82; // [rsp+28h] [rbp-51h]
  __int64 v83; // [rsp+28h] [rbp-51h]
  __int64 v84; // [rsp+30h] [rbp-49h]
  __int64 v85; // [rsp+38h] [rbp-41h]
  __int64 v86; // [rsp+40h] [rbp-39h]
  __int64 v87; // [rsp+48h] [rbp-31h]
  int v88; // [rsp+50h] [rbp-29h] BYREF
  int v89; // [rsp+54h] [rbp-25h] BYREF
  int v90; // [rsp+58h] [rbp-21h] BYREF
  __int128 v91; // [rsp+60h] [rbp-19h] BYREF
  __int128 v92; // [rsp+70h] [rbp-9h]
  __int128 v93; // [rsp+80h] [rbp+7h]
  int v94; // [rsp+E0h] [rbp+67h] BYREF
  unsigned __int8 *v95; // [rsp+E8h] [rbp+6Fh] BYREF
  int v96; // [rsp+F0h] [rbp+77h]
  unsigned int *v97; // [rsp+F8h] [rbp+7Fh]

  v97 = a4;
  v96 = a3;
  v4 = (CAACDec *)((char *)this + 246488);
  v5 = a4;
  v6 = a3;
  v9 = 0;
  TraceLoggingHelperBase::TraceVA(
    (CAACDec *)((char *)this + 246488),
    5u,
    "CAACDec::DecodeAAC",
    0x575u,
    "CAACDec::DecodeAAC(In=%d,Rem=%d)",
    a3,
    *((_DWORD *)this + 6) - *((_DWORD *)this + 4));
  v94 = 0;
  v90 = 0;
  v88 = 0;
  *v5 = 0;
  if ( !a2 )
  {
    v15 = 1;
LABEL_18:
    v94 = v15;
    goto LABEL_8;
  }
  if ( *((_BYTE *)this + 245940) )
  {
    v15 = 3;
    goto LABEL_18;
  }
  v10 = v6 - (*(__int64 (__fastcall **)(CAACDec *))(*(_QWORD *)this + 56LL))(this);
  v11 = *(_QWORD *)this;
  v88 = v10;
  v12 = &a2[(*(unsigned int (__fastcall **)(CAACDec *))(v11 + 56))(this)];
  v13 = *((_DWORD *)this + 61486);
  v95 = v12;
  if ( v13 != 3 )
  {
    if ( v13 != 4 )
    {
      v14 = CAACDec::DecodeAACFrame(this, v12, v6, (enum BREAK_STATUS_t *)&v94);
      v5 = v97;
      v9 = v14;
      if ( *((_BYTE *)this + 245940) )
      {
        v15 = 3;
      }
      else
      {
        v88 = 0;
        v15 = 1;
        v9 = 0;
      }
      v94 = v15;
      goto LABEL_8;
    }
    v91 = 0;
    v92 = 0;
    v93 = 0;
LABEL_95:
    TraceLoggingHelperBase::TraceVA(v4, 5u, "CAACDec::DecodeAAC", 0x6CBu, "CAACDec::DecodeAAC() begin outer loop");
    v94 = 0;
    CAACDec::GetNextPacketChunk(this, &v95, &v90, &v88);
    while ( 1 )
    {
      TraceLoggingHelperBase::TraceVA(v4, 5u, "CAACDec::DecodeAAC", 0x6D8u, "CAACDec::DecodeAAC() begin inner loop");
      if ( (*(unsigned int (__fastcall **)(CAACDec *))(*(_QWORD *)this + 32LL))(this) == 1 )
      {
        v15 = 2;
        v9 = 0;
        v94 = 2;
        goto LABEL_50;
      }
      v47 = (_BYTE *)*((_QWORD *)this + 2);
      if ( (unsigned __int64)(v47 + 3) <= *((_QWORD *)this + 3) )
      {
        v48 = 0;
        v49 = (int *)((char *)this + 246556);
        while ( 1 )
        {
          v44 = *v47 == 86;
          v50 = ++v47;
          if ( v44 && (*v50 & 0xE0) == 0xE0 )
            break;
          v49 = (int *)((char *)this + 246556);
          *((_QWORD *)this + 2) = v47;
          ++*((_DWORD *)this + 61639);
          v48 = 1;
          if ( (unsigned __int64)(v47 + 3) > *((_QWORD *)this + 3) )
            goto LABEL_104;
        }
        if ( !v48 )
          goto LABEL_105;
LABEL_104:
        v51 = *v49;
        TraceLoggingHelperBase::TraceVA(
          v4,
          4u,
          "CAACDec::DecodeAAC",
          0x6F4u,
          "CAACDec::DecodeAAC() m_ulNumberOfGaps=%d, m_ulNumberOfBytesSkipped=%d)",
          ++*((_DWORD *)this + 61638),
          v51);
      }
LABEL_105:
      v52 = *((_QWORD *)this + 2);
      if ( (unsigned __int64)(v52 + 3) > *((_QWORD *)this + 3) )
      {
        v15 = 1;
        v9 = 0;
        v94 = 1;
        goto LABEL_170;
      }
      v53 = (unsigned int)(*((_DWORD *)this + 6) - v52);
      *((_QWORD *)&v92 + 1) = *((_QWORD *)this + 2);
      *(_QWORD *)&v92 = v52;
      v93 = (unsigned __int64)(v52 + v53);
      *((_QWORD *)&v91 + 1) = v52 + v53;
      LODWORD(v91) = 0;
      v54 = ReadLOAS(&v91, (char *)this + 246572);
      v55 = *((_QWORD *)this + 2);
      v56 = (_BYTE *)(v55 + 1);
      if ( v54 )
      {
        *((_QWORD *)this + 2) = v56;
      }
      else
      {
        v57 = ((*v56 & 0x1F) << 8) + *(unsigned __int8 *)(v55 + 2) + 3;
        *((_DWORD *)this + 61640) = v57;
        *((_DWORD *)this + 26) = v57;
        if ( v57 <= 3 )
        {
          TraceLoggingHelperBase::TraceVA(
            v4,
            4u,
            "CAACDec::DecodeAAC",
            0x714u,
            "CAACDec::DecodeAAC() zero LOAS frame size");
LABEL_110:
          ++*((_QWORD *)this + 2);
          goto LABEL_164;
        }
        *((_DWORD *)this + 61639) = 0;
        if ( v55 + (unsigned __int64)v57 > *((_QWORD *)this + 3) )
        {
          v15 = 1;
          v9 = 0;
          v94 = 1;
LABEL_167:
          if ( v15 != 1 )
            goto LABEL_50;
LABEL_170:
          if ( v88 <= 0 )
            goto LABEL_50;
          goto LABEL_95;
        }
        if ( (unsigned int)ReadLATM(&v91, (char *)this + 246572) )
          goto LABEL_110;
        v58 = (_DWORD *)((char *)this + 246612);
        TotalNumberOfBitsRead = GetTotalNumberOfBitsRead(&v91);
        *((_QWORD *)this + 30748) = 0;
        *((_QWORD *)this + 30750) = 0;
        if ( *((_DWORD *)this + 61646) || (v60 = "ASC was read", *v58) )
          v60 = "ASC was not read";
        TraceLoggingHelperBase::TraceVA(
          v4,
          4u,
          "CAACDec::DecodeAAC",
          0x737u,
          "CAACDec::DecodeAAC() ReadLATM() was successful. %s",
          v60);
        if ( !*((_DWORD *)this + 61734) )
        {
          if ( *((_DWORD *)this + 61646) || *v58 )
          {
            TraceLoggingHelperBase::TraceVA(
              v4,
              4u,
              "CAACDec::DecodeAAC",
              0x740u,
              "CAACDec::DecodeAAC() Skip this LATM header since it does not contain ASC. Skip frame of size %d bytes",
              *((_DWORD *)this + 61640));
            goto LABEL_163;
          }
          if ( *((_DWORD *)this + 31) )
          {
            v61 = *((_DWORD *)this + 61732);
            if ( v61 )
            {
              v62 = *((_DWORD *)this + 61733);
              if ( v62 >= v61 + 16 && (v61 & 7) == 0 )
                (*(void (__fastcall **)(CAACDec *, _QWORD, _QWORD))(*(_QWORD *)this + 88LL))(
                  this,
                  *((_QWORD *)this + 2) + (v61 >> 3),
                  ((v62 + 7) >> 3) - (v61 >> 3));
            }
          }
        }
        *((_DWORD *)this + 61734) = 1;
        v63 = (_DWORD *)((char *)this + 124);
        if ( *((_DWORD *)this + 61663) == 42 && *v63 )
        {
          TraceLoggingHelperBase::TraceVA(
            v4,
            2u,
            "CAACDec::DecodeAAC",
            0x767u,
            "CAACDec::DecodeAAC() LOAS to ADTS conversion is not supported for AOT USAC, returning 0x%X",
            -2147418113);
          return 2147549183LL;
        }
        v64 = *((_DWORD *)this + 61664);
        if ( v64 <= 0xB )
        {
          v65 = *((_DWORD *)this + 61671);
          *((_DWORD *)this + 61498) = v65;
          v66 = (char *)this + 246748;
          if ( v65 )
            v66 = 0;
          v67 = 0;
          if ( v65 )
            v67 = (char *)this + 245992;
          *((_QWORD *)this + 30748) = v67;
          *((_QWORD *)this + 30750) = v66;
          v68 = *((_DWORD *)this + 61475);
          if ( v68 == *((_DWORD *)this + 61665) )
          {
LABEL_138:
            if ( !*v63 && !*((_BYTE *)this + 97) && IsChannelConfigSupported(*((_DWORD *)this + 61498)) )
            {
              if ( *((_DWORD *)this + 61637) != v70
                || (v71 = *(int *)&byte_1800B5E60[8 * v69 + (-(__int64)(*((_DWORD *)this + 61481) == 0) & 4)],
                    v72 = dword_1800B5F20[2 * v71],
                    v73 = dword_1800B5F24[2 * v71],
                    *((_DWORD *)this + 61636) != v70)
                && (_DWORD)v69 == 1 )
              {
                v72 = 2;
                v73 = 3;
              }
              v74 = *((unsigned __int16 *)this + 122954);
              if ( v72 != v74 )
              {
                TraceLoggingHelperBase::TraceVA(
                  v4,
                  4u,
                  "CAACDec::DecodeAAC",
                  0x7BDu,
                  "CAACDec::DecodeAAC() LOAS header: output channel count change from %d to %d",
                  v74,
                  v72);
                *((_BYTE *)this + 98) = 1;
              }
              v75 = *((_DWORD *)this + 61479);
              if ( v73 != v75 )
              {
                TraceLoggingHelperBase::TraceVA(
                  v4,
                  4u,
                  "CAACDec::DecodeAAC",
                  0x7C3u,
                  "CAACDec::DecodeAAC() LOAS header: output channel mask change from %d to %d",
                  v75,
                  v73);
                *((_BYTE *)this + 98) = 1;
              }
            }
          }
          else
          {
            TraceLoggingHelperBase::TraceVA(
              v4,
              4u,
              "CAACDec::DecodeAAC",
              0x7A1u,
              "CAACDec::DecodeAAC() LOAS header: Sample rate has changed from %d to %d.",
              v68,
              *((_DWORD *)this + 61665));
            *((_DWORD *)this + 61475) = *((_DWORD *)this + 61665);
            if ( !*v63 )
            {
              if ( !*((_BYTE *)this + 97) )
              {
                *((_BYTE *)this + 98) = 1;
                v63 = (_DWORD *)((char *)this + 124);
              }
              goto LABEL_138;
            }
          }
          if ( *((_BYTE *)this + 98) )
          {
            TraceLoggingHelperBase::TraceVA(
              v4,
              5u,
              "CAACDec::DecodeAAC",
              0x7CDu,
              "CAACDec::DecodeAAC() set to flush after a format change");
            v94 = 1;
            v9 = CAACDec::DecodeAACFrame(this, 0, 0, (enum BREAK_STATUS_t *)&v94);
            TraceLoggingHelperBase::TraceVA(
              v4,
              5u,
              "CAACDec::DecodeAAC",
              0x7D3u,
              "CAACDec::DecodeAAC() after DecodeAACFrame en_status=%d",
              v94);
            v15 = v94;
            if ( v94 == 2 )
            {
              *((_BYTE *)this + 97) = 1;
              goto LABEL_58;
            }
            if ( v94 == 1 && *((_BYTE *)this + 97) )
            {
              *(_WORD *)((char *)this + 97) = 0;
              goto LABEL_93;
            }
            *(_WORD *)((char *)this + 97) = 0;
          }
          v76 = (_DWORD *)*((_QWORD *)this + 30748);
          v77 = TotalNumberOfBitsRead & 7;
          v78 = TotalNumberOfBitsRead >> 3;
          if ( v76 )
          {
            LODWORD(v87) = v77;
            LODWORD(v86) = v78;
            LODWORD(v85) = *((_DWORD *)this + 61640);
            LODWORD(v84) = *v76;
            LODWORD(v83) = *((_DWORD *)this + 61475);
            TraceLoggingHelperBase::TraceVA(
              v4,
              4u,
              "CAACDec::DecodeAAC",
              0x7EFu,
              "CAACDec::DecodeAAC() Finished parsing LOAS/LATM headers: m_dwInSamplesPerSec=%d, *m_pdwAACTransportStreamC"
              "hannelConfig=%d, m_dwAACFrameSize=%d, dwByteOffsetToPayloadMux=%d, dwBitOffsetToPayloadMux=%d",
              v83,
              v84,
              v85,
              v86,
              v87);
          }
          else
          {
            v79 = *((_QWORD *)this + 30750);
            if ( v79 )
            {
              LODWORD(v87) = v77;
              LODWORD(v86) = v78;
              LODWORD(v85) = *((_DWORD *)this + 61640);
              LODWORD(v83) = *((_DWORD *)this + 61475);
              TraceLoggingHelperBase::TraceVA(
                v4,
                4u,
                "CAACDec::DecodeAAC",
                0x7F3u,
                "CAACDec::DecodeAAC() Finished parsing LOAS/LATM headers: m_dwInSamplesPerSec=%d, m_pstAACTransportStream"
                "PCE=0x%p, m_dwAACFrameSize=%d, dwByteOffsetToPayloadMux=%d, dwBitOffsetToPayloadMux=%d",
                v83,
                v79,
                v85,
                v86,
                v87);
            }
            else
            {
              TraceLoggingHelperBase::TraceVA(
                v4,
                4u,
                "CAACDec::DecodeAAC",
                0x7F7u,
                "CAACDec::DecodeAAC() Finished parsing LOAS/LATM headers: m_dwInSamplesPerSec=%d, m_dwAACFrameSize=%d, dw"
                "ByteOffsetToPayloadMux=%d, dwBitOffsetToPayloadMux=%d",
                *((_DWORD *)this + 61475),
                *((_DWORD *)this + 61640),
                v78,
                v77);
            }
          }
          v80 = *((_DWORD *)this + 61640);
          if ( *((_DWORD *)this + 31) )
            v81 = CAACDec::ConvertAACFrameToADTS(
                    this,
                    (const unsigned __int8 *)(*((_QWORD *)this + 2) + v78),
                    v80 - v78,
                    v77,
                    (CAACDec *)((char *)this + 246652));
          else
            v81 = CAACDec::DecodeAACFrame(this, *((unsigned __int8 **)this + 2), v80, (enum BREAK_STATUS_t *)&v94);
          v9 = v81;
          if ( *((_BYTE *)this + 245940) )
            goto LABEL_59;
LABEL_163:
          *((_QWORD *)this + 2) += *((unsigned int *)this + 61640);
          goto LABEL_164;
        }
        TraceLoggingHelperBase::TraceVA(
          v4,
          4u,
          "CAACDec::DecodeAAC",
          0x770u,
          "CAACDec::DecodeAAC() invalid sample rate code %d",
          v64);
        ++*((_QWORD *)this + 2);
      }
LABEL_164:
      v15 = v94;
      v9 = 0;
      if ( v94 )
        goto LABEL_167;
    }
  }
  v89 = 0;
LABEL_20:
  TraceLoggingHelperBase::TraceVA(v4, 5u, "CAACDec::DecodeAAC", 0x59Du, "CAACDec::DecodeAAC() begin outer loop");
  v94 = 0;
  CAACDec::GetNextPacketChunk(this, &v95, &v90, &v88);
  while ( 1 )
  {
    TraceLoggingHelperBase::TraceVA(v4, 5u, "CAACDec::DecodeAAC", 0x5ABu, "CAACDec::DecodeAAC() begin inner loop");
    if ( (*(unsigned int (__fastcall **)(CAACDec *))(*(_QWORD *)this + 32LL))(this) == 1 )
    {
      v15 = 2;
      v94 = 2;
LABEL_58:
      v6 = v96;
      v5 = v97;
      goto LABEL_8;
    }
    v20 = (_BYTE *)*((_QWORD *)this + 2);
    if ( (unsigned __int64)(v20 + 2) <= *((_QWORD *)this + 3) )
    {
      v42 = 0;
      v43 = (int *)((char *)this + 246556);
      while ( 1 )
      {
        v44 = *v20 == 0xFF;
        v45 = ++v20;
        if ( v44 && (*v45 & 0xF6) == 0xF0 )
          break;
        v43 = (int *)((char *)this + 246556);
        *((_QWORD *)this + 2) = v20;
        ++*((_DWORD *)this + 61639);
        v42 = 1;
        if ( (unsigned __int64)(v20 + 2) > *((_QWORD *)this + 3) )
          goto LABEL_72;
      }
      if ( !v42 )
        goto LABEL_23;
LABEL_72:
      v46 = *v43;
      TraceLoggingHelperBase::TraceVA(
        v4,
        4u,
        "CAACDec::DecodeAAC",
        0x5D3u,
        "CAACDec::DecodeAAC() m_ulNumberOfGaps=%d, m_ulNumberOfBytesSkipped=%d",
        ++*((_DWORD *)this + 61638),
        v46);
    }
LABEL_23:
    v21 = (_BYTE *)*((_QWORD *)this + 2);
    if ( (unsigned __int64)(v21 + 9) > *((_QWORD *)this + 3) )
    {
      v15 = 1;
      v94 = 1;
      goto LABEL_62;
    }
    v22 = (int *)((char *)this + 245992);
    v23 = ((unsigned __int8)v21[5] >> 5) | (8 * ((unsigned __int8)v21[4] | ((v21[3] & 3) << 8)));
    *((_DWORD *)this + 61640) = v23;
    *((_DWORD *)this + 26) = v23;
    *((_DWORD *)this + 61641) = (v21[1] & 1) == 0;
    v24 = ((unsigned __int8)v21[3] >> 6) | (4 * (v21[2] & 1));
    *((_QWORD *)this + 30748) = (char *)this + 245992;
    *((_DWORD *)this + 61498) = v24;
    *((_QWORD *)this + 30750) = 0;
    if ( v23 < 7 )
    {
      LODWORD(v82) = v23;
      TraceLoggingHelperBase::TraceVA(
        v4,
        4u,
        "CAACDec::DecodeAAC",
        0x5F8u,
        "CAACDec::DecodeAAC() ADTS frame size %d is too small",
        v82);
LABEL_75:
      ++*((_QWORD *)this + 2);
      v15 = v94;
      goto LABEL_48;
    }
    if ( (unsigned __int8)v21[2] >> 6 != 1 )
    {
      LODWORD(v82) = (unsigned __int8)v21[2] >> 6;
      TraceLoggingHelperBase::TraceVA(
        v4,
        4u,
        "CAACDec::DecodeAAC",
        0x601u,
        "CAACDec::DecodeAAC() Unexpected profile = %d",
        v82);
      goto LABEL_75;
    }
    if ( (v21[6] & 3) != 0 )
    {
      LODWORD(v82) = v21[6] & 3;
      TraceLoggingHelperBase::TraceVA(
        v4,
        4u,
        "CAACDec::DecodeAAC",
        0x60Au,
        "CAACDec::DecodeAAC() Unexpected number_of_raw_data_blocks_in_frame = %d",
        v82);
      goto LABEL_75;
    }
    v25 = ((unsigned __int8)v21[2] >> 2) & 0xF;
    if ( (unsigned int)v25 > 0xB )
    {
      LODWORD(v82) = ((unsigned __int8)v21[2] >> 2) & 0xF;
      TraceLoggingHelperBase::TraceVA(
        v4,
        4u,
        "CAACDec::DecodeAAC",
        0x614u,
        "CAACDec::DecodeAAC() invalid sample rate code %d",
        v82);
      goto LABEL_75;
    }
    v26 = *((_DWORD *)this + 61475);
    v27 = (unsigned int)v25;
    v28 = dword_1800B5EC0[v25];
    if ( v26 != v28 )
    {
      TraceLoggingHelperBase::TraceVA(
        v4,
        4u,
        "CAACDec::DecodeAAC",
        0x61Du,
        "CAACDec::DecodeAAC() ADTS header: Sample rate has changed from %d to %d.",
        v26,
        v28);
      *((_DWORD *)this + 61475) = dword_1800B5EC0[v27];
      if ( *((_DWORD *)this + 32) )
        goto LABEL_38;
      if ( !*((_BYTE *)this + 97) )
        *((_BYTE *)this + 98) = 1;
    }
    if ( !*((_DWORD *)this + 32) && !*((_BYTE *)this + 97) && IsChannelConfigSupported(*v22) )
    {
      if ( *((_DWORD *)this + 61637)
        || (v30 = *(int *)((-(__int64)(*((_DWORD *)this + 61481) == 0) & 4) + 8LL * (unsigned int)*v22 + v29 + 745056),
            v31 = *(_DWORD *)(v29 + 8 * v30 + 745248),
            v32 = *(_DWORD *)(v29 + 8 * v30 + 745252),
            *((_DWORD *)this + 61636))
        && *v22 == 1 )
      {
        v31 = 2;
        v32 = 3;
      }
      v33 = *((unsigned __int16 *)this + 122954);
      if ( v31 != v33 )
      {
        TraceLoggingHelperBase::TraceVA(
          v4,
          4u,
          "CAACDec::DecodeAAC",
          0x639u,
          "CAACDec::DecodeAAC() ADTS header: output channel count change from %d to %d",
          v33,
          v31);
        *((_BYTE *)this + 98) = 1;
      }
      v34 = *((_DWORD *)this + 61479);
      if ( v32 != v34 )
      {
        TraceLoggingHelperBase::TraceVA(
          v4,
          4u,
          "CAACDec::DecodeAAC",
          0x63Fu,
          "CAACDec::DecodeAAC() ADTS header: output channel mask change from %d to %d",
          v34,
          v32);
        *((_BYTE *)this + 98) = 1;
      }
    }
LABEL_38:
    if ( *((_BYTE *)this + 98) )
      break;
LABEL_39:
    v35 = *((_DWORD *)this + 61641);
    if ( v35 )
      v36 = _byteswap_ushort(*(_WORD *)(*((_QWORD *)this + 2) + 7LL));
    else
      v36 = 0;
    *((_WORD *)this + 123284) = v36;
    v37 = *((_DWORD *)this + 61640);
    *((_DWORD *)this + 61639) = 0;
    if ( *((_QWORD *)this + 2) + (unsigned __int64)v37 > *((_QWORD *)this + 3) )
    {
      v15 = 1;
      v94 = 1;
LABEL_49:
      if ( v15 != 1 )
        goto LABEL_50;
LABEL_62:
      if ( v88 <= 0 )
        goto LABEL_58;
      goto LABEL_20;
    }
    if ( v35 )
    {
      v44 = *((_DWORD *)this + 61474) == 0;
      v38 = 9;
      HIWORD(v89) = v36;
      v39 = &v89;
      if ( !v44 )
        v39 = 0;
    }
    else
    {
      v38 = 7;
      v39 = 0;
    }
    TraceLoggingHelperBase::TraceVA(
      v4,
      5u,
      "CAACDec::DecodeAAC",
      0x693u,
      "CAACDec::DecodeAAC() Finished parsing ADTS header: m_dwInSamplesPerSec=%d, m_dwAACTransportStreamChannelConfig=%d,"
      " m_dwAACFrameSize=%d, m_fAACCRCExist=%d, pusCRC=0x%p",
      *((_DWORD *)this + 61475),
      *((_DWORD *)this + 61498),
      v37,
      v35,
      v39);
    v40 = *((_DWORD *)this + 61640);
    if ( *((_DWORD *)this + 32) )
    {
      v41 = CAACDec::WriteRawAACFrame(this, (const unsigned __int8 *)(*((_QWORD *)this + 2) + v38), v40 - v38);
      v15 = 2;
      v94 = 2;
    }
    else
    {
      v41 = CAACDec::DecodeAACFrame(this, *((unsigned __int8 **)this + 2), v40, (enum BREAK_STATUS_t *)&v94);
      v15 = v94;
    }
    v9 = v41;
    if ( *((_BYTE *)this + 245940) )
    {
LABEL_59:
      v15 = 3;
      v94 = 3;
      goto LABEL_50;
    }
    v9 = 0;
    *((_QWORD *)this + 2) += *((unsigned int *)this + 61640);
LABEL_48:
    if ( v15 )
      goto LABEL_49;
  }
  TraceLoggingHelperBase::TraceVA(
    v4,
    5u,
    "CAACDec::DecodeAAC",
    0x649u,
    "CAACDec::DecodeAAC() set to flush after a format change");
  v94 = 1;
  v9 = CAACDec::DecodeAACFrame(this, 0, 0, (enum BREAK_STATUS_t *)&v94);
  TraceLoggingHelperBase::TraceVA(
    v4,
    5u,
    "CAACDec::DecodeAAC",
    0x64Fu,
    "CAACDec::DecodeAAC() after DecodeAACFrame en_status=%d",
    v94);
  v15 = v94;
  if ( v94 == 2 )
  {
    *((_BYTE *)this + 97) = 1;
    goto LABEL_50;
  }
  if ( v94 != 1 || !*((_BYTE *)this + 97) )
  {
    *(_WORD *)((char *)this + 97) = 0;
    goto LABEL_39;
  }
  *(_WORD *)((char *)this + 97) = 0;
LABEL_93:
  CAACDec::CloseUpAACDec(this);
  v15 = v94;
LABEL_50:
  v6 = v96;
  v5 = v97;
LABEL_8:
  v16 = v15 - 1;
  if ( v16 )
  {
    v18 = v16 - 1;
    if ( v18 )
    {
      if ( v18 != 1 )
        goto LABEL_12;
      v19 = *(_QWORD *)this;
      *((_BYTE *)this + 245940) = 1;
      *((_BYTE *)this + 93) = 1;
      if ( !(*(unsigned int (__fastcall **)(CAACDec *))(v19 + 40))(this) )
      {
        TraceLoggingHelperBase::TraceVA(
          v4,
          5u,
          "CAACDec::DecodeAAC",
          0x852u,
          "CAACDec::DecodeAAC() format change, have no output");
        *v5 = 256;
        v9 = -1072861855;
        goto LABEL_12;
      }
      TraceLoggingHelperBase::TraceVA(
        v4,
        5u,
        "CAACDec::DecodeAAC",
        0x848u,
        "CAACDec::DecodeAAC() format change, have some output");
    }
    else
    {
      *v5 = 0x1000000;
      TraceLoggingHelperBase::TraceVA(v4, 5u, "CAACDec::DecodeAAC", 0x83Eu, "CAACDec::DecodeAAC() Need more output.");
    }
LABEL_11:
    v9 = 0;
  }
  else
  {
    if ( (*(unsigned int (__fastcall **)(CAACDec *))(*(_QWORD *)this + 40LL))(this) )
    {
      TraceLoggingHelperBase::TraceVA(
        v4,
        5u,
        "CAACDec::DecodeAAC",
        0x831u,
        "CAACDec::DecodeAAC() Need more input, but have some output.");
      goto LABEL_11;
    }
    TraceLoggingHelperBase::TraceVA(
      v4,
      5u,
      "CAACDec::DecodeAAC",
      0x837u,
      "CAACDec::DecodeAAC() Need more input, but have no output.");
    v9 = -1072861838;
  }
LABEL_12:
  (*(void (__fastcall **)(CAACDec *, _QWORD))(*(_QWORD *)this + 48LL))(this, (unsigned int)(v6 - v88));
  TraceLoggingHelperBase::TraceVA(v4, 5u, "CAACDec::DecodeAAC", 0x85Eu, "CAACDec::DecodeAAC() returns hr = 0x%X", v9);
  return v9;
}

```

## disassembly

```asm
0x180002550  mov     [rsp-8+arg_18], r9
0x180002555  mov     [rsp-8+arg_10], r8d
0x18000255a  push    rbp
0x18000255b  push    rbx
0x18000255c  push    rsi
0x18000255d  push    rdi
0x18000255e  push    r12
0x180002560  push    r13
0x180002562  push    r14
0x180002564  push    r15
0x180002566  lea     rbp, [rsp-1Fh]
0x18000256b  sub     rsp, 98h
0x180002572  mov     eax, [rcx+18h]
0x180002575  lea     rsi, [rcx+3C2D8h]
0x18000257c  sub     eax, [rcx+10h]
0x18000257f  xor     r13d, r13d
0x180002582  mov     dword ptr [rsp+0D0h+var_A0], eax
0x180002586  mov     r12, r9
0x180002589  mov     dword ptr [rsp+0D0h+var_A8], r8d
0x18000258e  lea     rax, aCaacdecDecodea_19; "CAACDec::DecodeAAC(In=%d,Rem=%d)"
0x180002595  mov     r15d, r8d
0x180002598  mov     [rsp+0D0h+Format], rax; Format
0x18000259d  mov     r14, rdx
0x1800025a0  lea     r8, aCaacdecDecodea_33; "CAACDec::DecodeAAC"
0x1800025a7  mov     rbx, rcx
0x1800025aa  lea     edx, [r13+5]; unsigned __int8
0x1800025ae  mov     r9d, 575h; unsigned int
0x1800025b4  mov     rcx, rsi; this
0x1800025b7  mov     edi, r13d
0x1800025ba  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x1800025bf  mov     [rbp+57h+arg_0], r13d
0x1800025c3  mov     [rbp+57h+var_78], r13d
0x1800025c7  mov     [rbp+57h+var_80], r13d
0x1800025cb  mov     [r12], r13d
0x1800025cf  test    r14, r14
0x1800025d2  jz      loc_180002760
0x1800025d8  cmp     [rbx+3C0B4h], r13b
0x1800025df  jnz     loc_180002C8C
0x1800025e5  mov     rax, [rbx]
0x1800025e8  mov     rcx, rbx
0x1800025eb  mov     rax, [rax+38h]
0x1800025ef  call    cs:__guard_dispatch_icall_fptr
0x1800025f5  mov     ecx, r15d
0x1800025f8  sub     ecx, eax
0x1800025fa  mov     rax, [rbx]
0x1800025fd  mov     [rbp+57h+var_80], ecx
0x180002600  mov     rcx, rbx
0x180002603  mov     rax, [rax+38h]
0x180002607  call    cs:__guard_dispatch_icall_fptr
0x18000260d  mov     eax, eax
0x18000260f  mov     r13d, 3
0x180002615  add     r14, rax
0x180002618  mov     eax, [rbx+3C0B8h]
0x18000261e  mov     [rbp+57h+arg_8], r14
0x180002622  lea     r12d, [r13+1]
0x180002626  cmp     eax, r13d
0x180002629  jz      loc_180002770
0x18000262f  cmp     eax, r12d
0x180002632  jz      loc_180002E13
0x180002638  lea     r9, [rbp+57h+arg_0]; enum BREAK_STATUS_t *
0x18000263c  mov     r8d, r15d; int
0x18000263f  mov     rdx, r14; unsigned __int8 *
0x180002642  mov     rcx, rbx; this
0x180002645  call    ?DecodeAACFrame@CAACDec@@IEAAJPEAEJPEAW4BREAK_STATUS_t@@@Z; CAACDec::DecodeAACFrame(uchar *,long,BREAK_STATUS_t *)
0x18000264a  mov     r12, [rbp+57h+arg_18]
0x18000264e  xor     r14d, r14d
0x180002651  mov     edi, eax
0x180002653  cmp     [rbx+3C0B4h], r14b
0x18000265a  jnz     loc_180002AE1
0x180002660  mov     [rbp+57h+var_80], r14d
0x180002664  lea     ecx, [r13-2]
0x180002668  mov     edi, r14d
0x18000266b  mov     [rbp+57h+arg_0], ecx
0x18000266e  sub     ecx, 1
0x180002671  jnz     loc_180002710
0x180002677  mov     rax, [rbx]
0x18000267a  mov     rcx, rbx
0x18000267d  mov     rax, [rax+28h]
0x180002681  call    cs:__guard_dispatch_icall_fptr
0x180002687  lea     r8, aCaacdecDecodea_33; "CAACDec::DecodeAAC"
0x18000268e  mov     edx, 5; unsigned __int8
0x180002693  mov     rcx, rsi; this
0x180002696  test    eax, eax
0x180002698  jz      loc_180002A6F
0x18000269e  lea     rax, aCaacdecDecodea_43; "CAACDec::DecodeAAC() Need more input, b"...
0x1800026a5  mov     r9d, 831h; unsigned int
0x1800026ab  mov     [rsp+0D0h+Format], rax; Format
0x1800026b0  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x1800026b5  mov     edi, r14d
0x1800026b8  mov     rax, [rbx]
0x1800026bb  mov     rcx, rbx
0x1800026be  sub     r15d, [rbp+57h+var_80]
0x1800026c2  mov     edx, r15d
0x1800026c5  mov     rax, [rax+30h]
0x1800026c9  call    cs:__guard_dispatch_icall_fptr
0x1800026cf  lea     rax, aCaacdecDecodea_27; "CAACDec::DecodeAAC() returns hr = 0x%X"
0x1800026d6  mov     dword ptr [rsp+0D0h+var_A8], edi
0x1800026da  mov     r9d, 85Eh; unsigned int
0x1800026e0  mov     [rsp+0D0h+Format], rax; Format
0x1800026e5  lea     r8, aCaacdecDecodea_33; "CAACDec::DecodeAAC"
0x1800026ec  mov     edx, 5; unsigned __int8
0x1800026f1  mov     rcx, rsi; this
0x1800026f4  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x1800026f9  mov     eax, edi
0x1800026fb  add     rsp, 98h
0x180002702  pop     r15
0x180002704  pop     r14
0x180002706  pop     r13
0x180002708  pop     r12
0x18000270a  pop     rdi
0x18000270b  pop     rsi
0x18000270c  pop     rbx
0x18000270d  pop     rbp
0x18000270e  retn
0x180002710  sub     ecx, 1
0x180002713  jz      loc_180002B0C
0x180002719  cmp     ecx, 1
0x18000271c  jnz     short loc_1800026B8
0x18000271e  mov     rax, [rbx]
0x180002721  mov     [rbx+3C0B4h], cl
0x180002727  mov     [rbx+5Dh], cl
0x18000272a  mov     rcx, rbx
0x18000272d  mov     rax, [rax+28h]
0x180002731  call    cs:__guard_dispatch_icall_fptr
0x180002737  lea     r8, aCaacdecDecodea_33; "CAACDec::DecodeAAC"
0x18000273e  mov     edx, 5; unsigned __int8
0x180002743  mov     rcx, rsi; this
0x180002746  test    eax, eax
0x180002748  jz      loc_180003520
0x18000274e  lea     rax, aCaacdecDecodea_15; "CAACDec::DecodeAAC() format change, hav"...
0x180002755  mov     r9d, 848h
0x18000275b  jmp     loc_1800026AB
0x180002760  mov     ecx, 1
0x180002765  mov     [rbp+57h+arg_0], ecx
0x180002768  xor     r14d, r14d
0x18000276b  jmp     loc_18000266E
0x180002770  mov     [rbp+57h+var_7C], edi
0x180002773  lea     r15, aCaacdecDecodea_35; "CAACDec::DecodeAAC() begin inner loop"
0x18000277a  lea     r14, aCaacdecDecodea_1; "CAACDec::DecodeAAC() invalid sample rat"...
0x180002781  lea     rcx, aCaacdecDecodea_30; "CAACDec::DecodeAAC() begin outer loop"
0x180002788  mov     r9d, 59Dh; unsigned int
0x18000278e  mov     [rsp+0D0h+Format], rcx; Format
0x180002793  lea     r8, aCaacdecDecodea_33; "CAACDec::DecodeAAC"
0x18000279a  mov     rcx, rsi; this
0x18000279d  mov     edx, 5; unsigned __int8
0x1800027a2  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x1800027a7  lea     r9, [rbp+57h+var_80]; int *
0x1800027ab  mov     [rbp+57h+arg_0], 0
0x1800027b2  lea     r8, [rbp+57h+var_78]; int *
0x1800027b6  mov     rcx, rbx; this
0x1800027b9  lea     rdx, [rbp+57h+arg_8]; unsigned __int8 **
0x1800027bd  call    ?GetNextPacketChunk@CAACDec@@AEAAXAEAPEAEAEAJ1@Z; CAACDec::GetNextPacketChunk(uchar * &,long &,long &)
0x1800027c2  mov     r9d, 5ABh; unsigned int
0x1800027c8  mov     [rsp+0D0h+Format], r15; Format
0x1800027cd  lea     r8, aCaacdecDecodea_33; "CAACDec::DecodeAAC"
0x1800027d4  mov     edx, 5; unsigned __int8
0x1800027d9  mov     rcx, rsi; this
0x1800027dc  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x1800027e1  mov     rax, [rbx]
0x1800027e4  mov     rcx, rbx
0x1800027e7  mov     rax, [rax+20h]
0x1800027eb  call    cs:__guard_dispatch_icall_fptr
0x1800027f1  cmp     eax, 1
0x1800027f4  jz      loc_180002AC4
0x1800027fa  mov     rcx, [rbx+10h]
0x1800027fe  lea     rax, [rcx+2]
0x180002802  cmp     rax, [rbx+18h]
0x180002806  jbe     loc_180002A90
0x18000280c  mov     rdx, [rbx+10h]
0x180002810  lea     rax, [rdx+9]
0x180002814  cmp     rax, [rbx+18h]
0x180002818  ja      loc_180002AE9
0x18000281e  movzx   eax, byte ptr [rdx+4]
0x180002822  lea     r15, [rbx+3C0E8h]
0x180002829  movzx   r8d, byte ptr [rdx+3]
0x18000282e  and     r8d, r13d
0x180002831  shl     r8d, 8
0x180002835  or      r8d, eax
0x180002838  movzx   eax, byte ptr [rdx+5]
0x18000283c  shr     eax, 5
0x18000283f  shl     r8d, 3
0x180002843  or      r8d, eax
0x180002846  mov     [rbx+3C320h], r8d
0x18000284d  mov     [rbx+68h], r8d
0x180002851  mov     al, [rdx+1]
0x180002854  not     al
0x180002856  and     eax, 1
0x180002859  mov     [rbx+3C324h], eax
0x18000285f  movzx   ecx, byte ptr [rdx+2]
0x180002863  movzx   eax, byte ptr [rdx+3]
0x180002867  and     ecx, 1
0x18000286a  shl     ecx, 2
0x18000286d  shr     eax, 6
0x180002870  or      ecx, eax
0x180002872  mov     [rbx+3C0E0h], r15
0x180002879  mov     [r15], ecx
0x18000287c  mov     qword ptr [rbx+3C0F0h], 0
0x180002887  cmp     r8d, 7
0x18000288b  jb      loc_180002C57
0x180002891  movzx   eax, byte ptr [rdx+2]
0x180002895  mov     ecx, eax
0x180002897  shr     ecx, 6
0x18000289a  cmp     ecx, 1
0x18000289d  jnz     loc_180002C96
0x1800028a3  movzx   ecx, byte ptr [rdx+6]
0x1800028a7  and     ecx, r13d
0x1800028aa  jnz     loc_180002CA9
0x1800028b0  shr     eax, 2
0x1800028b3  and     eax, 0Fh
0x1800028b6  cmp     eax, 0Bh
0x1800028b9  ja      loc_180002CBC
0x1800028bf  mov     ecx, [rbx+3C08Ch]
0x1800028c5  lea     rdx, __ImageBase
0x1800028cc  mov     r14d, eax
0x1800028cf  mov     eax, ds:rva dword_1800B5EC0[rdx+rax*4]
0x1800028d6  cmp     ecx, eax
0x1800028d8  jnz     loc_180002CCD
0x1800028de  xor     r14d, r14d
0x1800028e1  cmp     [rbx+80h], r14d
0x1800028e8  jnz     short loc_180002966
0x1800028ea  cmp     [rbx+61h], r14b
0x1800028ee  jnz     short loc_180002966
0x1800028f0  mov     ecx, [r15]; int
0x1800028f3  call    ?IsChannelConfigSupported@@YA_NH@Z; IsChannelConfigSupported(int)
0x1800028f8  test    al, al
0x1800028fa  jz      short loc_180002966
0x1800028fc  mov     eax, [rbx+3C0A4h]
0x180002902  neg     eax
0x180002904  sbb     rcx, rcx
0x180002907  not     rcx
0x18000290a  and     rcx, r12
0x18000290d  cmp     [rbx+3C314h], r14d
0x180002914  jnz     loc_180002D3B
0x18000291a  cmp     dword ptr [rbx+3C310h], 0
0x180002921  mov     eax, [r15]
0x180002924  lea     rcx, [rcx+rax*8]
0x180002928  movsxd  rax, dword ptr [rcx+rdx+0B5E60h]
0x180002930  mov     ecx, [rdx+rax*8+0B5F20h]
0x180002937  mov     r14d, [rdx+rax*8+0B5F24h]
0x18000293f  jnz     loc_180002D31
0x180002945  movzx   eax, word ptr [rbx+3C094h]
0x18000294c  cmp     ecx, eax
0x18000294e  jnz     loc_180002D48
0x180002954  mov     eax, [rbx+3C09Ch]
0x18000295a  cmp     r14d, eax
0x18000295d  jnz     loc_180002D7D
0x180002963  xor     r14d, r14d
0x180002966  cmp     [rbx+62h], r14b
0x18000296a  jnz     loc_180002B35
0x180002970  mov     edx, [rbx+3C324h]
0x180002976  mov     r8d, 3C328h
0x18000297c  test    edx, edx
0x18000297e  jnz     loc_180002BC7
0x180002984  mov     ecx, r14d
0x180002987  mov     [r8+rbx], cx
0x18000298c  mov     rax, rbx
0x18000298f  mov     r8d, [rbx+3C320h]
0x180002996  mov     eax, r8d
0x180002999  mov     [rbx+3C31Ch], r14d
0x1800029a0  add     rax, [rbx+10h]
0x1800029a4  cmp     rax, [rbx+18h]
0x1800029a8  ja      loc_180002DEE
0x1800029ae  test    edx, edx
0x1800029b0  jnz     loc_180002DC5
0x1800029b6  lea     edi, [rdx+7]
0x1800029b9  mov     rcx, r14
0x1800029bc  mov     eax, [rbx+3C0E8h]
0x1800029c2  mov     r9d, 693h; unsigned int
0x1800029c8  mov     [rsp+0D0h+var_88], rcx
0x1800029cd  mov     rcx, rsi; this
0x1800029d0  mov     dword ptr [rsp+0D0h+var_90], edx
0x1800029d4  mov     edx, 5; unsigned __int8
0x1800029d9  mov     dword ptr [rsp+0D0h+var_98], r8d
0x1800029de  lea     r8, aCaacdecDecodea_33; "CAACDec::DecodeAAC"
0x1800029e5  mov     dword ptr [rsp+0D0h+var_A0], eax
0x1800029e9  mov     eax, [rbx+3C08Ch]
0x1800029ef  mov     dword ptr [rsp+0D0h+var_A8], eax
0x1800029f3  lea     rax, aCaacdecDecodea_47; "CAACDec::DecodeAAC() Finished parsing A"...
0x1800029fa  mov     [rsp+0D0h+Format], rax; Format
0x1800029ff  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x180002a04  mov     rcx, rbx; this
0x180002a07  mov     r8d, [rbx+3C320h]; int
0x180002a0e  cmp     [rbx+80h], r14d
0x180002a15  jnz     loc_180002C3C
0x180002a1b  mov     rdx, [rbx+10h]; unsigned __int8 *
0x180002a1f  lea     r9, [rbp+57h+arg_0]; enum BREAK_STATUS_t *
0x180002a23  call    ?DecodeAACFrame@CAACDec@@IEAAJPEAEJPEAW4BREAK_STATUS_t@@@Z; CAACDec::DecodeAACFrame(uchar *,long,BREAK_STATUS_t *)
0x180002a28  mov     ecx, [rbp+57h+arg_0]
0x180002a2b  mov     edi, eax
0x180002a2d  cmp     [rbx+3C0B4h], r14b
0x180002a34  jnz     loc_180002AD9
0x180002a3a  mov     eax, [rbx+3C320h]
0x180002a40  mov     edi, r14d
0x180002a43  add     [rbx+10h], rax
0x180002a47  lea     r14, aCaacdecDecodea_1; "CAACDec::DecodeAAC() invalid sample rat"...
0x180002a4e  test    ecx, ecx
0x180002a50  jz      loc_180002DE2
0x180002a56  xor     r14d, r14d
0x180002a59  cmp     ecx, 1
0x180002a5c  jz      loc_180002AFC
  ... truncated ...
```
