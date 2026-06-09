# CTieredVolume::SetCurrentLocation_ApiHandler(long,__MIDL___MIDL_itf_tieringengine_0000_0000_0005 *)

- ea: `0x14003eba8`
- end: `0x14003f4d1`
- name: `?SetCurrentLocation_ApiHandler@CTieredVolume@@QEAAJJPEAU__MIDL___MIDL_itf_tieringengine_0000_0000_0005@@@Z`
- size: `2345`
- prototype: `__int64 __fastcall(CTieredVolume *__hidden this, int, struct __MIDL___MIDL_itf_tieringengine_0000_0000_0005 *)`
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14003af90`

## callees

- `0x140004aa8`
- `0x140004ef0`
- `0x140005420`
- `0x14000b7f8`
- `0x14000ccc0`
- `0x1400127dc`
- `0x140017e78`
- `0x1400185a0`
- `0x1400188b8`
- `0x1400197b0`
- `0x14001a1d4`
- `0x14001b328`
- `0x140024b60`
- `0x1400280bc`
- `0x14003538c`
- `0x140035d68`
- `0x14003eba8`
- `0x14003f838`
- `0x14003f914`
- `0x14003f9dc`
- `0x14003fbb0`

## import_xrefs

- `ntdll!RtlCompareMemory` at `0x14003f09c`
- `ntdll!RtlCompareMemory` at `0x14003f14f`
- `ntdll!RtlCompareMemory` at `0x14003f354`
- `ntdll!RtlCompareMemory` at `0x14003f09c`
- `ntdll!RtlCompareMemory` at `0x14003f14f`
- `ntdll!RtlCompareMemory` at `0x14003f354`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14003edb6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14003edd0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14003edb6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14003edd0`

## pseudocode

```c
__int64 __fastcall CTieredVolume::SetCurrentLocation_ApiHandler(
        CTieredVolume *this,
        int a2,
        struct __MIDL___MIDL_itf_tieringengine_0000_0000_0005 *a3)
{
  struct __MIDL___MIDL_itf_tieringengine_0000_0000_0005 *v3; // rsi
  int v6; // eax
  int v7; // ebx
  int v8; // eax
  _QWORD *v9; // rcx
  int v10; // edx
  signed int v11; // r13d
  int v12; // ebx
  _QWORD *v13; // r10
  int v14; // edx
  int v15; // r8d
  int v16; // ecx
  int v17; // eax
  int v18; // edx
  int v19; // r8d
  __int64 v20; // rax
  __int64 v21; // rax
  unsigned __int64 v22; // rbx
  unsigned __int64 v23; // rcx
  unsigned __int8 v24; // r9
  int v25; // eax
  int v26; // edx
  int v27; // r8d
  __int64 v28; // rax
  unsigned __int64 v29; // r13
  __int64 v30; // rcx
  int v31; // edx
  __int64 v32; // rax
  unsigned __int64 v33; // rax
  unsigned __int8 v34; // r13
  unsigned __int64 v35; // rbx
  __int64 v36; // rsi
  unsigned __int64 v37; // rcx
  int v38; // eax
  unsigned __int8 v39; // al
  unsigned __int64 v40; // r13
  __int64 v41; // r8
  unsigned __int64 v42; // rax
  unsigned __int8 v43; // si
  unsigned __int64 v44; // rbx
  int v45; // eax
  unsigned __int64 v46; // rcx
  int v47; // eax
  unsigned int v49; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int8 v50[4]; // [rsp+44h] [rbp-BCh]
  int v51; // [rsp+48h] [rbp-B8h]
  __int64 v52; // [rsp+50h] [rbp-B0h]
  unsigned __int64 v53; // [rsp+58h] [rbp-A8h]
  struct __MIDL___MIDL_itf_tieringengine_0000_0000_0005 *v54; // [rsp+60h] [rbp-A0h]
  char v55[8]; // [rsp+68h] [rbp-98h] BYREF
  int v56; // [rsp+70h] [rbp-90h]
  signed int v57; // [rsp+78h] [rbp-88h]
  unsigned __int64 v58; // [rsp+80h] [rbp-80h]
  unsigned __int64 v59; // [rsp+88h] [rbp-78h]
  JET_SESID v60[4]; // [rsp+90h] [rbp-70h] BYREF
  __int16 v61; // [rsp+B0h] [rbp-50h]
  char v62; // [rsp+B2h] [rbp-4Eh]
  __int64 v63; // [rsp+B8h] [rbp-48h]
  char v64; // [rsp+C0h] [rbp-40h]
  __int128 Source1; // [rsp+F0h] [rbp-10h] BYREF
  GUID Source2; // [rsp+100h] [rbp+0h] BYREF

  v3 = a3;
  v54 = a3;
  v57 = a2;
  *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 8LL) = "CTieredVolume::SetCurrentLocation_ApiHandler";
  CHResultImp::CHResultImp((CHResultImp *)v55);
  LOBYTE(v60[0]) = 0;
  v61 = 0;
  v62 = 0;
  v63 = 0;
  v64 = 0;
  v6 = CTieredVolume::ReferenceVolume(this, 0);
  v7 = v6;
  v56 = v6;
  if ( v6 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        55,
        &WPP_db0c4653e1f131e4f6800413feb2b973_Traceguids,
        *((unsigned int *)this + 32),
        v6);
    }
    goto LABEL_132;
  }
  if ( *((_DWORD *)this + 46) == 7 )
    *((_DWORD *)this + 179) = 2;
  v8 = TieringJetSession::Initialize((TieringJetSession *)v60, (RTL_SRWLOCK **)this + 148);
  v7 = v8;
  v56 = v8;
  if ( v8 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_126;
    }
    v10 = 56;
    goto LABEL_13;
  }
  v8 = TieringJetSession::OpenJetTable((TieringJetSession *)v60, 0);
  v7 = v8;
  v56 = v8;
  if ( v8 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_126;
    }
    v10 = 57;
LABEL_13:
    WPP_SF_Zd(v9[2], v10, (unsigned int)&WPP_db0c4653e1f131e4f6800413feb2b973_Traceguids, (_DWORD)this + 672, v8);
    goto LABEL_126;
  }
  if ( v3 && a2 > 0 )
  {
    v11 = 0;
    v49 = 0;
    v12 = -1;
    v51 = -1;
    v52 = 0;
    v53 = 0;
    v50[0] = 0;
    Source2 = NullGuid;
    v13 = WPP_GLOBAL_Control;
    while ( 1 )
    {
      if ( *((_BYTE *)this + 165) || *((_BYTE *)this + 166) )
        goto LABEL_110;
      if ( WaitForSingleObject(*((HANDLE *)this + 96), 0) != 258
        || WaitForSingleObject(*((HANDLE *)this + 95), 0) != 258 )
      {
        v13 = WPP_GLOBAL_Control;
LABEL_110:
        if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 1) != 0 && *((_BYTE *)v13 + 25) >= 5u )
          WPP_SF_Z(v13[2], 252, &WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids, (char *)this + 672);
LABEL_114:
        if ( RtlCompareMemory(&Source2, &NullGuid, 0x10u) != 16 )
        {
          v40 = v53;
          v41 = v52;
          v42 = (v53 - v52) / *((unsigned int *)this + 79);
          if ( v42 )
          {
            v43 = v50[0];
            do
            {
              v44 = *((unsigned int *)this + 80);
              if ( v42 <= v44 )
                v44 = v42;
              v45 = TieringHeatSession::SetCurrentLocation(
                      (TieringHeatSession *)v60,
                      (const struct TE_FILE_ID_128 *)&Source2,
                      v41,
                      v43,
                      v44);
              v56 = v45;
              if ( v45 < 0
                && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_DiiZd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  64,
                  (unsigned int)&WPP_db0c4653e1f131e4f6800413feb2b973_Traceguids,
                  v43,
                  Source2.Data4[0],
                  Source2.Data1,
                  (__int64)this + 672,
                  v45);
              }
              v46 = *((unsigned int *)this + 79);
              v41 = v44 * v46 + v52;
              v52 = v41;
              v42 = (v40 - v41) / v46;
            }
            while ( v42 );
          }
        }
        break;
      }
      if ( *(_BYTE *)(v63 + 77) && *(_BYTE *)(v63 + 76) )
        goto LABEL_114;
      Source1 = *(_OWORD *)v3;
      v16 = *((unsigned __int16 *)v3 + 16);
      if ( (v16 & 0x42) == 0 )
      {
        if ( (v16 & 0x21) == 0 )
        {
          v13 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            WPP_SF_DiiZ(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v14,
              v15,
              v16,
              SBYTE8(Source1),
              Source1,
              (__int64)this + 672);
            goto LABEL_104;
          }
LABEL_105:
          v3 = (struct __MIDL___MIDL_itf_tieringengine_0000_0000_0005 *)((char *)v3 + 40);
          ++v11;
LABEL_106:
          v54 = v3;
          v49 = v11;
          goto LABEL_107;
        }
        v49 = 0;
        v17 = TieringHeatSession::DeleteRecordsWithGivenFileId(v60, (const struct TE_FILE_ID_128 *)&Source1, &v49);
        v56 = v17;
        if ( v17 >= 0 )
        {
          v13 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
          {
            goto LABEL_105;
          }
          WPP_SF_DDiiZ(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v18,
            v19,
            v49,
            *((_WORD *)v3 + 16),
            SBYTE8(Source1),
            Source1,
            (__int64)this + 672);
        }
        else
        {
          v13 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_105;
          }
          WPP_SF_iiZd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            58,
            (unsigned int)&WPP_db0c4653e1f131e4f6800413feb2b973_Traceguids,
            DWORD2(Source1),
            Source1,
            (__int64)this + 672,
            v17);
        }
LABEL_104:
        v13 = WPP_GLOBAL_Control;
        goto LABEL_105;
      }
      v20 = *((_QWORD *)v3 + 3);
      if ( v20 == -1 || (v16 & 0x10) != 0 )
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
        {
          goto LABEL_105;
        }
        WPP_SF_iiZ(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          61,
          (unsigned int)&WPP_db0c4653e1f131e4f6800413feb2b973_Traceguids,
          DWORD2(Source1),
          Source1,
          (__int64)this + 672);
        goto LABEL_104;
      }
      if ( (v16 & 2) != 0 && v11 != v12 && (v16 & 0x40) == 0 )
      {
        if ( *((_DWORD *)v3 + 9) == 2 )
          *((_QWORD *)this + 66) += v20;
        else
          *((_QWORD *)this + 67) += v20;
        v51 = v11;
      }
      v21 = *((_QWORD *)v3 + 2);
      v22 = v21 & 0xFFFFFFFFFFF00000uLL;
      v58 = v21 & 0xFFFFFFFFFFF00000uLL;
      v23 = *((_QWORD *)v3 + 3);
      if ( (v21 & 0xFFFFFFFFFFF00000uLL) != v21 || v23 < 0x100000 )
      {
        v29 = (v23 + v21 + 0xFFFFF) & 0xFFFFFFFFFFF00000uLL;
        v59 = v29;
        if ( v22 == v52 && RtlCompareMemory(&Source1, &Source2, 0x10u) == 16 )
        {
          v30 = *((_QWORD *)v3 + 2);
          if ( v30 != v53 )
            goto LABEL_70;
          if ( v50[0] == 16 )
          {
            if ( *((_DWORD *)v3 + 9) != 2 )
LABEL_70:
              v50[0] = 0;
          }
          else if ( v50[0] == 32 )
          {
            v31 = 32;
            if ( *((_DWORD *)v3 + 9) == 2 )
              v31 = 0;
            *(_DWORD *)v50 = v31;
          }
          v32 = *((_QWORD *)v3 + 3);
          v53 = v30 + v32;
          if ( v29 >= v30 + v32 )
          {
            v13 = WPP_GLOBAL_Control;
LABEL_78:
            v11 = v49 + 1;
            v3 = (struct __MIDL___MIDL_itf_tieringengine_0000_0000_0005 *)((char *)v3 + 40);
            v12 = v51;
            goto LABEL_106;
          }
LABEL_76:
          v53 = v29;
          *((_QWORD *)v3 + 3) = v32 + v30 - v29;
          *((_QWORD *)v3 + 2) = v22 + 0x100000;
          v13 = WPP_GLOBAL_Control;
          v11 = v49;
          v12 = v51;
          goto LABEL_107;
        }
        if ( RtlCompareMemory(&Source2, &NullGuid, 0x10u) == 16
          || (v33 = (v53 - v52) / *((unsigned int *)this + 79)) == 0 )
        {
          v13 = WPP_GLOBAL_Control;
LABEL_93:
          Source2 = (GUID)Source1;
          v52 = v22;
          v30 = *((_QWORD *)v3 + 2);
          if ( v22 == v30 )
          {
            v39 = 16;
            if ( *((_DWORD *)v3 + 9) != 2 )
              v39 = 32;
            v50[0] = v39;
          }
          else
          {
            v50[0] = 0;
          }
          v32 = *((_QWORD *)v3 + 3);
          v53 = v30 + v32;
          if ( v29 >= v30 + v32 )
            goto LABEL_78;
          goto LABEL_76;
        }
        v34 = v50[0];
        v35 = v53;
        v36 = v52;
        while ( 2 )
        {
          v37 = *((unsigned int *)this + 80);
          if ( v33 <= v37 )
            v37 = v33;
          v52 = v37;
          v38 = TieringHeatSession::SetCurrentLocation(
                  (TieringHeatSession *)v60,
                  (const struct TE_FILE_ID_128 *)&Source2,
                  v36,
                  v34,
                  v37);
          v56 = v38;
          if ( v38 >= 0 )
          {
LABEL_89:
            v13 = WPP_GLOBAL_Control;
          }
          else
          {
            v13 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_DiiZd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                63,
                (unsigned int)&WPP_db0c4653e1f131e4f6800413feb2b973_Traceguids,
                v34,
                Source2.Data4[0],
                Source2.Data1,
                (__int64)this + 672,
                v38);
              goto LABEL_89;
            }
          }
          v36 += v52 * *((unsigned int *)this + 79);
          v33 = (v35 - v36) / *((unsigned int *)this + 79);
          if ( !v33 )
          {
            v3 = v54;
            v22 = v58;
            v29 = v59;
            goto LABEL_93;
          }
          continue;
        }
      }
      v24 = 16;
      if ( *((_DWORD *)v3 + 9) != 2 )
        v24 = 32;
      v25 = TieringHeatSession::SetCurrentLocation(
              (TieringHeatSession *)v60,
              (const struct TE_FILE_ID_128 *)&Source1,
              v22,
              v24,
              *((_WORD *)this + 160));
      v56 = v25;
      if ( v25 < 0 )
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_62;
        }
        WPP_SF_LiiZd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v26,
          v27,
          *((_DWORD *)v3 + 9),
          SBYTE8(Source1),
          Source1,
          (__int64)this + 672,
          v25);
      }
      v13 = WPP_GLOBAL_Control;
LABEL_62:
      v28 = *((_QWORD *)v3 + 3);
      v12 = v51;
      if ( v28 == 0x100000 )
      {
        ++v11;
        v3 = (struct __MIDL___MIDL_itf_tieringengine_0000_0000_0005 *)((char *)v3 + 40);
        goto LABEL_106;
      }
      *((_QWORD *)v3 + 2) += 0x100000LL;
      *((_QWORD *)v3 + 3) = v28 - 0x100000;
      v13 = WPP_GLOBAL_Control;
LABEL_107:
      if ( v11 >= v57 )
        goto LABEL_114;
    }
  }
  v7 = 0;
  v56 = 0;
LABEL_126:
  v47 = TieringJetSession::CloseJetTable((TieringJetSession *)v60, v7 < 0);
  if ( v47 < 0
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_Zd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      65,
      (unsigned int)&WPP_db0c4653e1f131e4f6800413feb2b973_Traceguids,
      (_DWORD)this + 672,
      v47);
  }
  CTieredVolume::DereferenceVolume((RTL_SRWLOCK *)this);
LABEL_132:
  TieringJetSession::~TieringJetSession((TieringJetSession *)v60);
  CHResultImp::~CHResultImp((CHResultImp *)v55);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14003eba8  mov     [rsp-8+arg_8], rbx
0x14003ebad  mov     [rsp-8+arg_18], rsi
0x14003ebb2  push    rbp
0x14003ebb3  push    rdi
0x14003ebb4  push    r12
0x14003ebb6  push    r13
0x14003ebb8  push    r14
0x14003ebba  lea     rbp, [rsp-20h]
0x14003ebbf  sub     rsp, 120h
0x14003ebc6  mov     rax, cs:__security_cookie
0x14003ebcd  xor     rax, rsp
0x14003ebd0  mov     [rbp+40h+var_30], rax
0x14003ebd4  mov     rsi, r8
0x14003ebd7  mov     [rsp+140h+var_E0], r8
0x14003ebdc  mov     r13d, edx
0x14003ebdf  mov     [rsp+140h+var_C8], edx
0x14003ebe3  mov     rdi, rcx
0x14003ebe6  mov     edx, 8
0x14003ebeb  mov     rax, gs:58h
0x14003ebf4  mov     rcx, [rax]
0x14003ebf7  lea     rax, aCtieredvolumeS_0; "CTieredVolume::SetCurrentLocation_ApiHa"...
0x14003ebfe  mov     [rdx+rcx], rax
0x14003ec02  lea     rcx, [rsp+140h+var_D8]; this
0x14003ec07  call    ??0CHResultImp@@QEAA@XZ; CHResultImp::CHResultImp(void)
0x14003ec0c  nop
0x14003ec0d  xor     r14d, r14d
0x14003ec10  mov     byte ptr [rbp+40h+var_B0], r14b
0x14003ec14  mov     [rbp+40h+var_90], r14w
0x14003ec19  mov     [rbp+40h+var_8E], r14b
0x14003ec1d  mov     [rbp+40h+var_88], r14
0x14003ec21  mov     [rbp+40h+var_80], r14b
0x14003ec25  xor     edx, edx; bool
0x14003ec27  mov     rcx, rdi; this
0x14003ec2a  call    ?ReferenceVolume@CTieredVolume@@QEAAJ_N@Z; CTieredVolume::ReferenceVolume(bool)
0x14003ec2f  mov     ebx, eax
0x14003ec31  mov     [rsp+140h+var_D0], eax
0x14003ec35  test    eax, eax
0x14003ec37  jns     short loc_14003EC8E
0x14003ec39  lea     r12, WPP_GLOBAL_Control
0x14003ec40  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ec47  cmp     rcx, r12
0x14003ec4a  jz      loc_14003F493
0x14003ec50  mov     r14d, 1
0x14003ec56  test    [rcx+1Ch], r14b
0x14003ec5a  jz      loc_14003F493
0x14003ec60  cmp     byte ptr [rcx+19h], 2
0x14003ec64  jb      loc_14003F493
0x14003ec6a  lea     edx, [r14+36h]
0x14003ec6e  mov     dword ptr [rsp+140h+var_120], eax
0x14003ec72  mov     r9d, [rdi+80h]
0x14003ec79  lea     r8, WPP_db0c4653e1f131e4f6800413feb2b973_Traceguids
0x14003ec80  mov     rcx, [rcx+10h]
0x14003ec84  call    WPP_SF_Dd
0x14003ec89  jmp     loc_14003F493
0x14003ec8e  cmp     dword ptr [rdi+0B8h], 7
0x14003ec95  jnz     short loc_14003ECA1
0x14003ec97  mov     dword ptr [rdi+2CCh], 2
0x14003eca1  lea     rdx, [rdi+4A0h]; struct TieringJetDatabase *
0x14003eca8  lea     rcx, [rbp+40h+var_B0]; this
0x14003ecac  call    ?Initialize@TieringJetSession@@QEAAJPEAVTieringJetDatabase@@@Z; TieringJetSession::Initialize(TieringJetDatabase *)
0x14003ecb1  mov     ebx, eax
0x14003ecb3  mov     [rsp+140h+var_D0], eax
0x14003ecb7  lea     r12, WPP_GLOBAL_Control
0x14003ecbe  mov     r14d, 1
0x14003ecc4  test    eax, eax
0x14003ecc6  jns     short loc_14003ED10
0x14003ecc8  mov     rcx, cs:WPP_GLOBAL_Control
0x14003eccf  cmp     rcx, r12
0x14003ecd2  jz      loc_14003F440
0x14003ecd8  test    [rcx+1Ch], r14b
0x14003ecdc  jz      loc_14003F440
0x14003ece2  cmp     byte ptr [rcx+19h], 2
0x14003ece6  jb      loc_14003F440
0x14003ecec  lea     edx, [r14+37h]
0x14003ecf0  lea     r9, [rdi+2A0h]
0x14003ecf7  mov     dword ptr [rsp+140h+var_120], eax
0x14003ecfb  lea     r8, WPP_db0c4653e1f131e4f6800413feb2b973_Traceguids
0x14003ed02  mov     rcx, [rcx+10h]
0x14003ed06  call    WPP_SF_Zd
0x14003ed0b  jmp     loc_14003F440
0x14003ed10  xor     edx, edx; bool
0x14003ed12  lea     rcx, [rbp+40h+var_B0]; this
0x14003ed16  call    ?OpenJetTable@TieringJetSession@@QEAAJ_N@Z; TieringJetSession::OpenJetTable(bool)
0x14003ed1b  mov     ebx, eax
0x14003ed1d  mov     [rsp+140h+var_D0], eax
0x14003ed21  test    eax, eax
0x14003ed23  jns     short loc_14003ED50
0x14003ed25  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ed2c  cmp     rcx, r12
0x14003ed2f  jz      loc_14003F440
0x14003ed35  test    [rcx+1Ch], r14b
0x14003ed39  jz      loc_14003F440
0x14003ed3f  cmp     byte ptr [rcx+19h], 2
0x14003ed43  jb      loc_14003F440
0x14003ed49  mov     edx, 39h ; '9'
0x14003ed4e  jmp     short loc_14003ECF0
0x14003ed50  test    rsi, rsi
0x14003ed53  jz      loc_14003F43A
0x14003ed59  test    r13d, r13d
0x14003ed5c  jle     loc_14003F43A
0x14003ed62  xor     r13d, r13d
0x14003ed65  mov     [rsp+140h+var_100], r13d
0x14003ed6a  or      ebx, 0FFFFFFFFh
0x14003ed6d  mov     [rsp+140h+var_F8], ebx
0x14003ed71  mov     [rsp+140h+var_F0], r13
0x14003ed76  mov     [rsp+140h+var_E8], r13
0x14003ed7b  mov     [rsp+140h+var_FC], r13b
0x14003ed80  movups  xmm0, xmmword ptr cs:?NullGuid@@3U_GUID@@A.Data1; _GUID NullGuid ...
0x14003ed87  movdqu  [rbp+40h+Source2], xmm0
0x14003ed8c  mov     r10, cs:WPP_GLOBAL_Control
0x14003ed93  cmp     byte ptr [rdi+0A5h], 0
0x14003ed9a  jnz     loc_14003F315
0x14003eda0  cmp     byte ptr [rdi+0A6h], 0
0x14003eda7  jnz     loc_14003F315
0x14003edad  xor     edx, edx; dwMilliseconds
0x14003edaf  mov     rcx, [rdi+300h]; hHandle
0x14003edb6  call    cs:__imp_WaitForSingleObject
0x14003edbc  cmp     eax, 102h
0x14003edc1  jnz     loc_14003F30E
0x14003edc7  xor     edx, edx; dwMilliseconds
0x14003edc9  mov     rcx, [rdi+2F8h]; hHandle
0x14003edd0  call    cs:__imp_WaitForSingleObject
0x14003edd6  cmp     eax, 102h
0x14003eddb  jnz     loc_14003F30E
0x14003ede1  mov     rax, [rbp+40h+var_88]
0x14003ede5  cmp     byte ptr [rax+4Dh], 0
0x14003ede9  jz      short loc_14003EDF5
0x14003edeb  cmp     byte ptr [rax+4Ch], 0
0x14003edef  jnz     loc_14003F343
0x14003edf5  movups  xmm0, xmmword ptr [rsi]
0x14003edf8  movdqu  [rbp+40h+Source1], xmm0
0x14003edfd  movzx   ecx, word ptr [rsi+20h]
0x14003ee01  test    cl, 42h
0x14003ee04  jnz     loc_14003EF41
0x14003ee0a  test    cl, 21h
0x14003ee0d  jnz     short loc_14003EE63
0x14003ee0f  mov     r10, cs:WPP_GLOBAL_Control
0x14003ee16  cmp     r10, r12
0x14003ee19  jz      loc_14003F2F0
0x14003ee1f  test    [r10+1Ch], r14b
0x14003ee23  jz      loc_14003F2F0
0x14003ee29  cmp     byte ptr [r10+19h], 5
0x14003ee2e  jb      loc_14003F2F0
0x14003ee34  lea     rax, [rdi+2A0h]
0x14003ee3b  mov     r9d, ecx
0x14003ee3e  mov     [rsp+140h+var_110], rax
0x14003ee43  mov     rax, qword ptr [rbp+40h+Source1]
0x14003ee47  mov     [rsp+140h+var_118], rax
0x14003ee4c  mov     rax, qword ptr [rbp+40h+Source1+8]
0x14003ee50  mov     qword ptr [rsp+140h+var_120], rax
0x14003ee55  mov     rcx, [r10+10h]
0x14003ee59  call    WPP_SF_DiiZ
0x14003ee5e  jmp     loc_14003F2E9
0x14003ee63  mov     [rsp+140h+var_100], 0
0x14003ee6b  lea     r8, [rsp+140h+var_100]; unsigned int *
0x14003ee70  lea     rdx, [rbp+40h+Source1]; Source2
0x14003ee74  lea     rcx, [rbp+40h+var_B0]; this
0x14003ee78  call    ?DeleteRecordsWithGivenFileId@TieringHeatSession@@QEAAJPEBUTE_FILE_ID_128@@PEAK@Z; TieringHeatSession::DeleteRecordsWithGivenFileId(TE_FILE_ID_128 const *,ulong *)
0x14003ee7d  mov     ecx, eax
0x14003ee7f  mov     [rsp+140h+var_D0], eax
0x14003ee83  test    eax, eax
0x14003ee85  jns     short loc_14003EEE3
0x14003ee87  mov     r10, cs:WPP_GLOBAL_Control
0x14003ee8e  cmp     r10, r12
0x14003ee91  jz      loc_14003F2F0
0x14003ee97  test    [r10+1Ch], r14b
0x14003ee9b  jz      loc_14003F2F0
0x14003eea1  cmp     byte ptr [r10+19h], 2
0x14003eea6  jb      loc_14003F2F0
0x14003eeac  lea     rax, [rdi+2A0h]
0x14003eeb3  mov     edx, 3Ah ; ':'
0x14003eeb8  mov     dword ptr [rsp+140h+var_110], ecx
0x14003eebc  mov     [rsp+140h+var_118], rax
0x14003eec1  mov     rax, qword ptr [rbp+40h+Source1]
0x14003eec5  mov     qword ptr [rsp+140h+var_120], rax
0x14003eeca  mov     r9, qword ptr [rbp+40h+Source1+8]
0x14003eece  lea     r8, WPP_db0c4653e1f131e4f6800413feb2b973_Traceguids
0x14003eed5  mov     rcx, [r10+10h]
0x14003eed9  call    WPP_SF_iiZd
0x14003eede  jmp     loc_14003F2E9
0x14003eee3  mov     r10, cs:WPP_GLOBAL_Control
0x14003eeea  cmp     r10, r12
0x14003eeed  jz      loc_14003F2F0
0x14003eef3  test    [r10+1Ch], r14b
0x14003eef7  jz      loc_14003F2F0
0x14003eefd  cmp     byte ptr [r10+19h], 5
0x14003ef02  jb      loc_14003F2F0
0x14003ef08  lea     rax, [rdi+2A0h]
0x14003ef0f  movzx   ecx, word ptr [rsi+20h]
0x14003ef13  mov     [rsp+140h+var_108], rax
0x14003ef18  mov     rax, qword ptr [rbp+40h+Source1]
0x14003ef1c  mov     [rsp+140h+var_110], rax
0x14003ef21  mov     rax, qword ptr [rbp+40h+Source1+8]
0x14003ef25  mov     [rsp+140h+var_118], rax
0x14003ef2a  mov     dword ptr [rsp+140h+var_120], ecx
0x14003ef2e  mov     r9d, [rsp+140h+var_100]
0x14003ef33  mov     rcx, [r10+10h]
0x14003ef37  call    WPP_SF_DDiiZ
0x14003ef3c  jmp     loc_14003F2E9
0x14003ef41  mov     rax, [rsi+18h]
0x14003ef45  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14003ef49  jz      loc_14003F2A2
0x14003ef4f  test    cl, 10h
0x14003ef52  jnz     loc_14003F2A2
0x14003ef58  test    cl, 2
0x14003ef5b  jz      short loc_14003EF82
0x14003ef5d  cmp     r13d, ebx
0x14003ef60  jz      short loc_14003EF82
0x14003ef62  test    cl, 40h
0x14003ef65  jnz     short loc_14003EF82
0x14003ef67  cmp     dword ptr [rsi+24h], 2
0x14003ef6b  jnz     short loc_14003EF76
0x14003ef6d  add     [rdi+210h], rax
0x14003ef74  jmp     short loc_14003EF7D
0x14003ef76  add     [rdi+218h], rax
0x14003ef7d  mov     [rsp+140h+var_F8], r13d
0x14003ef82  mov     rax, [rsi+10h]
0x14003ef86  mov     rbx, rax
0x14003ef89  mov     rdx, 0FFFFFFFFFFF00000h
0x14003ef90  and     rbx, rdx
0x14003ef93  mov     [rbp+40h+var_C0], rbx
0x14003ef97  mov     rcx, [rsi+18h]
0x14003ef9b  cmp     rbx, rax
0x14003ef9e  jnz     loc_14003F072
0x14003efa4  cmp     rcx, 100000h
0x14003efab  jb      loc_14003F072
0x14003efb1  mov     r9d, 10h
0x14003efb7  cmp     dword ptr [rsi+24h], 2
0x14003efbb  lea     eax, [r9+10h]
0x14003efbf  cmovnz  r9d, eax; unsigned __int8
0x14003efc3  movzx   eax, word ptr [rdi+140h]
0x14003efca  mov     [rsp+140h+var_120], ax; unsigned __int16
0x14003efcf  mov     r8, rbx; __int64
0x14003efd2  lea     rdx, [rbp+40h+Source1]; struct TE_FILE_ID_128 *
0x14003efd6  lea     rcx, [rbp+40h+var_B0]; this
0x14003efda  call    ?SetCurrentLocation@TieringHeatSession@@QEAAJPEBUTE_FILE_ID_128@@_JEG@Z; TieringHeatSession::SetCurrentLocation(TE_FILE_ID_128 const *,__int64,uchar,ushort)
0x14003efdf  mov     ecx, eax
0x14003efe1  mov     [rsp+140h+var_D0], eax
0x14003efe5  test    eax, eax
0x14003efe7  jns     short loc_14003F031
0x14003efe9  mov     r10, cs:WPP_GLOBAL_Control
0x14003eff0  cmp     r10, r12
0x14003eff3  jz      short loc_14003F038
0x14003eff5  test    [r10+1Ch], r14b
0x14003eff9  jz      short loc_14003F038
0x14003effb  cmp     byte ptr [r10+19h], 2
0x14003f000  jb      short loc_14003F038
0x14003f002  lea     rax, [rdi+2A0h]
0x14003f009  mov     dword ptr [rsp+140h+var_108], ecx
0x14003f00d  mov     [rsp+140h+var_110], rax
0x14003f012  mov     rax, qword ptr [rbp+40h+Source1]
0x14003f016  mov     [rsp+140h+var_118], rax
0x14003f01b  mov     rax, qword ptr [rbp+40h+Source1+8]
0x14003f01f  mov     qword ptr [rsp+140h+var_120], rax
0x14003f024  mov     r9d, [rsi+24h]
0x14003f028  mov     rcx, [r10+10h]
0x14003f02c  call    WPP_SF_LiiZd
0x14003f031  mov     r10, cs:WPP_GLOBAL_Control
0x14003f038  mov     rax, [rsi+18h]
0x14003f03c  mov     ebx, [rsp+140h+var_F8]
0x14003f040  cmp     rax, 100000h
0x14003f046  jnz     short loc_14003F054
0x14003f048  add     r13d, r14d
0x14003f04b  add     rsi, 28h ; '('
0x14003f04f  jmp     loc_14003F2F7
0x14003f054  add     qword ptr [rsi+10h], 100000h
0x14003f05c  add     rax, 0FFFFFFFFFFF00000h
0x14003f062  mov     [rsi+18h], rax
0x14003f066  mov     r10, cs:WPP_GLOBAL_Control
0x14003f06d  jmp     loc_14003F301
0x14003f072  lea     r13, [rax+0FFFFFh]
0x14003f079  add     r13, rcx
0x14003f07c  and     r13, rdx
0x14003f07f  mov     [rbp+40h+var_B8], r13
0x14003f083  cmp     rbx, [rsp+140h+var_F0]
0x14003f088  jnz     loc_14003F13E
0x14003f08e  mov     r8d, 10h; Length
0x14003f094  lea     rdx, [rbp+40h+Source2]; Source2
0x14003f098  lea     rcx, [rbp+40h+Source1]; Source1
0x14003f09c  call    cs:__imp_RtlCompareMemory
0x14003f0a2  cmp     rax, 10h
0x14003f0a6  jnz     loc_14003F13E
0x14003f0ac  mov     rcx, [rsi+10h]
0x14003f0b0  cmp     rcx, [rsp+140h+var_E8]
0x14003f0b5  jnz     short loc_14003F0C5
0x14003f0b7  mov     edx, dword ptr [rsp+140h+var_FC]
0x14003f0bb  cmp     dl, al
0x14003f0bd  jnz     short loc_14003F0CC
0x14003f0bf  cmp     dword ptr [rsi+24h], 2
0x14003f0c3  jz      short loc_14003F0E1
0x14003f0c5  mov     [rsp+140h+var_FC], 0
0x14003f0ca  jmp     short loc_14003F0E1
0x14003f0cc  cmp     dl, 20h ; ' '
0x14003f0cf  jnz     short loc_14003F0E1
0x14003f0d1  movzx   edx, dl
0x14003f0d4  xor     eax, eax
0x14003f0d6  cmp     dword ptr [rsi+24h], 2
0x14003f0da  cmovz   edx, eax
0x14003f0dd  mov     dword ptr [rsp+140h+var_FC], edx
0x14003f0e1  mov     rax, [rsi+18h]
  ... truncated ...
```
