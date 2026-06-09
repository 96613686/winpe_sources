# Kerb3961::RC4_4757::CommonUnwrap(Kerb3961::ReadOnlyBinary const &,utl::function<Kerb3961::ReturnType<Kerb3961::OwnedBinary,&Kerb3961::SingleGetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary const &),&Kerb3961::SingleSetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary &)> (Kerb3961::ReadOnlyBinary const &)> const &,Kerb3961::ReadOnlyBinary const &,bool,bool)

- ea: `0x180005480`
- end: `0x180005ec1`
- name: `?CommonUnwrap@RC4_4757@Kerb3961@@EEAA?AU?$ReturnType@UUnwrapResult@Kerb3961@@$1??$DoubleGetter@UUnwrapResult@Kerb3961@@UOwnedBinary@2@$0A@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$DoubleSetter@UUnwrapResult@Kerb3961@@UOwnedBinary@2@$0A@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@AEBV?$function@$$A6A?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@Kerb3961@@AEBUReadOnlyBinary@2@@Z@utl@@0_N2@Z`
- size: `2625`
- prototype: `__int64 __fastcall(_QWORD *, __int64, __int64 *, __int64, __int64, char)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001d40`
- `0x180001d64`
- `0x180002c64`
- `0x180002fc0`
- `0x1800033f4`
- `0x180004118`
- `0x1800046e0`
- `0x180005480`
- `0x18000700c`
- `0x18000712c`
- `0x180008500`
- `0x1800085cc`
- `0x180009190`
- `0x18001e010`

## string_xrefs

- `0x1800054fa`: `message.length >= sizeof(WrapToken)`

## pseudocode

```c
__int64 __fastcall Kerb3961::RC4_4757::CommonUnwrap(
        _QWORD *a1,
        __int64 a2,
        __int64 *a3,
        __int64 a4,
        __int64 a5,
        char a6)
{
  int v10; // ebx
  const unsigned __int16 *v11; // rdx
  __int64 v12; // r8
  char *v13; // rcx
  unsigned __int16 *v14; // rcx
  unsigned __int16 v15; // r10
  unsigned __int16 v16; // r9
  unsigned __int16 v17; // r11
  __int128 v18; // xmm0
  int v19; // r8d
  int v20; // esi
  int v21; // r8d
  int v22; // esi
  char *v23; // rcx
  __int64 v24; // rsi
  void *v25; // rcx
  int v26; // eax
  const char *v27; // rdx
  int v28; // r8d
  int v29; // esi
  void *v30; // rcx
  void *v31; // rcx
  unsigned __int64 v32; // rax
  _BYTE *i; // rsi
  int v34; // r8d
  unsigned int v35; // r14d
  __int64 v36; // r14
  void *v37; // rcx
  int v38; // eax
  int v39; // r8d
  int v40; // r14d
  char *v41; // rcx
  int v42; // r8d
  unsigned int v43; // r14d
  char *v44; // rcx
  void *v45; // rcx
  __int64 *v46; // rax
  __int128 v47; // xmm2
  __int64 v48; // rax
  int v49; // r8d
  __int64 v50; // r13
  void *v51; // r14
  int v52; // r15d
  void *v53; // rcx
  void *v54; // rcx
  void *v55; // rcx
  const char *v56; // rdx
  int v57; // r8d
  unsigned int v58; // esi
  char *v59; // rcx
  __int64 *v60; // rcx
  __int64 v61; // rax
  __int128 v62; // xmm0
  __int64 v63; // rax
  int v64; // r8d
  int v65; // esi
  int v66; // r8d
  unsigned int v67; // esi
  __int64 v68; // rsi
  void *v69; // rcx
  int v70; // eax
  char v71; // r8
  __int64 j; // rdx
  char v73; // cl
  char v74; // al
  char v76; // [rsp+20h] [rbp-E0h]
  __int64 v77; // [rsp+28h] [rbp-D8h] BYREF
  void *v78; // [rsp+30h] [rbp-D0h]
  char *v79; // [rsp+38h] [rbp-C8h]
  __int64 v80; // [rsp+40h] [rbp-C0h] BYREF
  void *v81; // [rsp+48h] [rbp-B8h]
  int v82; // [rsp+50h] [rbp-B0h]
  char v83[8]; // [rsp+58h] [rbp-A8h] BYREF
  void *v84; // [rsp+60h] [rbp-A0h]
  char *v85; // [rsp+68h] [rbp-98h]
  unsigned __int64 v86; // [rsp+70h] [rbp-90h] BYREF
  void *v87; // [rsp+78h] [rbp-88h]
  char *v88; // [rsp+80h] [rbp-80h]
  __int64 v89; // [rsp+88h] [rbp-78h] BYREF
  void *v90; // [rsp+90h] [rbp-70h]
  char *v91; // [rsp+98h] [rbp-68h]
  __int64 v92; // [rsp+A0h] [rbp-60h] BYREF
  void *v93; // [rsp+A8h] [rbp-58h]
  char *v94; // [rsp+B0h] [rbp-50h]
  unsigned __int32 v95; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v96; // [rsp+C8h] [rbp-38h] BYREF
  void *v97; // [rsp+D0h] [rbp-30h]
  char *v98; // [rsp+D8h] [rbp-28h]
  __int64 v99; // [rsp+E0h] [rbp-20h] BYREF
  void *v100; // [rsp+E8h] [rbp-18h]
  char *v101; // [rsp+F0h] [rbp-10h]
  _QWORD v102[2]; // [rsp+F8h] [rbp-8h] BYREF
  __int16 v103; // [rsp+108h] [rbp+8h]
  unsigned __int16 v104; // [rsp+10Ah] [rbp+Ah]
  unsigned __int16 v105; // [rsp+10Ch] [rbp+Ch]
  unsigned __int16 v106; // [rsp+10Eh] [rbp+Eh]
  unsigned int v107; // [rsp+110h] [rbp+10h] BYREF
  int v108; // [rsp+114h] [rbp+14h]
  __int128 v109; // [rsp+118h] [rbp+18h] BYREF
  char v110[8]; // [rsp+128h] [rbp+28h] BYREF
  void *v111; // [rsp+130h] [rbp+30h]
  char v112[32]; // [rsp+140h] [rbp+40h] BYREF
  __int128 v113; // [rsp+160h] [rbp+60h] BYREF
  __int64 v114; // [rsp+170h] [rbp+70h]
  __int64 v115; // [rsp+178h] [rbp+78h]
  __int128 v116; // [rsp+180h] [rbp+80h]
  __int128 v117; // [rsp+190h] [rbp+90h]
  __int128 v118; // [rsp+1A0h] [rbp+A0h] BYREF
  _QWORD v119[4]; // [rsp+1B0h] [rbp+B0h] BYREF
  __int128 v120; // [rsp+1D0h] [rbp+D0h]

  v10 = (*(__int64 (__fastcall **)(_QWORD *))(a1[1] + 104LL))(a1 + 1);
  if ( v10 != (*(unsigned int (__fastcall **)(_QWORD *))(*a1 + 224LL))(a1) )
    Kerb3961::ConsistencyFail(
      (Kerb3961 *)L"A cipher suite's included checksum must be the required checksum for the included cipher",
      v11);
  v12 = *a3;
  if ( (unsigned __int64)*a3 < 0x20 )
  {
    v13 = "message.length >= sizeof(WrapToken)";
LABEL_4:
    Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)v13, (const char *)v11);
LABEL_5:
    *(_QWORD *)(a2 + 20) = 0;
    *(_QWORD *)(a2 + 28) = 0;
    *(_DWORD *)(a2 + 36) = 0;
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = -2146893041;
    return a2;
  }
  v14 = (unsigned __int16 *)a3[1];
  v86 = 8;
  v89 = 8;
  v92 = 8;
  v11 = (const unsigned __int16 *)*v14;
  v103 = (__int16)v11;
  v15 = v14[1];
  v104 = v15;
  v16 = v14[2];
  v105 = v16;
  v17 = v14[3];
  v106 = v17;
  v107 = *((_DWORD *)v14 + 2);
  v108 = *((_DWORD *)v14 + 3);
  v18 = *((_OWORD *)v14 + 1);
  v87 = &v107;
  v90 = &v109;
  v93 = (char *)&v109 + 8;
  v102[0] = v12 - 32;
  v102[1] = v14 + 16;
  v109 = v18;
  if ( (_WORD)v11 != 258 )
  {
    v13 = "header.TOK_ID == header.ID";
    goto LABEL_4;
  }
  if ( v15 != 17 )
  {
    v13 = "header.SGN_ALG == header.SignAlgorithm";
    goto LABEL_4;
  }
  if ( v17 != 0xFFFF )
  {
    v13 = "header.Filler == header.FillerBytes";
    goto LABEL_4;
  }
  if ( v16 == 16 )
  {
    v76 = 1;
  }
  else
  {
    v76 = 0;
    if ( v16 != 0xFFFF )
    {
      Kerb3961::Logging::Verify::ConditionFailed(
        (Kerb3961::Logging::Verify *)"encrypted || header.SEAL_ALG == header.IntegrityOnly",
        (const char *)v11);
      goto LABEL_5;
    }
  }
  Kerb3961::RC4_4757::HmacData(
    a1,
    v83,
    a5,
    &__S41__1__CommonUnwrap_RC4_4757_Kerb3961__EEAA_AU__ReturnType_UUnwrapResult_Kerb3961___1___DoubleGetter_UUnwrapResult_Kerb3961__UOwnedBinary_2__0A__0BA__2_YAAEBUResultBlock_2_AEBU12__Z_1___DoubleSetter_UUnwrapResult_Kerb3961__UOwnedBinary_2__0A__0BA__2_YAAEAU32_AEAU12__Z_3_AEBUReadOnlyBinary_3_AEBV__function___A6A_AU__ReturnType_UOwnedBinary_Kerb3961___1___SingleGetter_UOwnedBinary_Kerb3961___0BA__2_YAAEBUResultBlock_2_AEBU12__Z_1___SingleSetter_UOwnedBinary_Kerb3961___0BA__2_YAAEAU32_AEAU12__Z_Kerb3961__AEBUReadOnlyBinary_2__Z_utl__0_N2_Z_4U53_B);
  v20 = (int)v85;
  if ( (int)v85 >= 0 )
  {
    Kerb3961::RC4_4757::HmacData(
      a1,
      &v77,
      a5,
      &__S42__1__CommonUnwrap_RC4_4757_Kerb3961__EEAA_AU__ReturnType_UUnwrapResult_Kerb3961___1___DoubleGetter_UUnwrapResult_Kerb3961__UOwnedBinary_2__0A__0BA__2_YAAEBUResultBlock_2_AEBU12__Z_1___DoubleSetter_UUnwrapResult_Kerb3961__UOwnedBinary_2__0A__0BA__2_YAAEAU32_AEAU12__Z_3_AEBUReadOnlyBinary_3_AEBV__function___A6A_AU__ReturnType_UOwnedBinary_Kerb3961___1___SingleGetter_UOwnedBinary_Kerb3961___0BA__2_YAAEBUResultBlock_2_AEBU12__Z_1___SingleSetter_UOwnedBinary_Kerb3961___0BA__2_YAAEAU32_AEAU12__Z_Kerb3961__AEBUReadOnlyBinary_2__Z_utl__0_N2_Z_4U53_B);
    v22 = (int)v79;
    if ( (int)v79 < 0 )
      goto LABEL_19;
    v24 = Kerb3961::RC4_4757::HmacData(a1, &v96, &v77, &v89);
    if ( v78 )
      operator delete(v78, 0);
    v77 = *(_QWORD *)v24;
    v25 = *(void **)(v24 + 8);
    *(_QWORD *)v24 = 0;
    v78 = v25;
    v26 = *(_DWORD *)(v24 + 16);
    *(_QWORD *)(v24 + 8) = 0;
    LODWORD(v79) = v26;
    *(_DWORD *)(v24 + 16) = -1073741823;
    if ( v97 )
      operator delete(v97, 0);
    v22 = (int)v79;
    if ( (int)v79 < 0 )
    {
LABEL_19:
      v23 = "Kseq";
LABEL_20:
      Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)v23, (const char *)(unsigned int)v22, v21);
      *(_QWORD *)(a2 + 20) = 0;
      *(_QWORD *)(a2 + 28) = 0;
      *(_DWORD *)(a2 + 36) = 0;
      *(_DWORD *)(a2 + 16) = v22;
LABEL_129:
      *(_QWORD *)(a2 + 8) = 0;
      *(_QWORD *)a2 = 0;
LABEL_130:
      if ( v78 )
        operator delete(v78, 0);
      goto LABEL_132;
    }
    v22 = *(_DWORD *)Kerb3961::RC4_4757::RC4Data(a1, &v95, &v77, &v86);
    if ( v22 < 0 )
    {
      v23 = "RC4Data(Kseq, sequenceBuffer)";
      goto LABEL_20;
    }
    if ( v108 != -(a6 != 0) )
    {
      Kerb3961::Logging::Verify::ConditionFailed(
        (Kerb3961::Logging::Verify *)"header.SND_SEQ.Direction == expectedDirection",
        v27);
      *(_QWORD *)(a2 + 20) = 0;
      *(_QWORD *)(a2 + 28) = 0;
      *(_DWORD *)(a2 + 36) = 0;
      *(_DWORD *)(a2 + 16) = -2146893041;
      goto LABEL_129;
    }
    v95 = _byteswap_ulong(v107);
    v80 = 0;
    v81 = 0;
    v82 = -1073741823;
    if ( v76 )
    {
      Kerb3961::CopyBuffer(&v86, a5);
      v29 = (int)v88;
      if ( (int)v88 < 0 )
      {
        Kerb3961::Logging::Verify::StatusFailed(
          (Kerb3961::Logging::Verify *)"Klocal",
          (const char *)(unsigned int)v88,
          v28);
        *(_QWORD *)(a2 + 20) = 0;
        *(_QWORD *)(a2 + 28) = 0;
        *(_DWORD *)(a2 + 36) = 0;
        v30 = v87;
        *(_QWORD *)a2 = 0;
        *(_QWORD *)(a2 + 8) = 0;
        *(_DWORD *)(a2 + 16) = v29;
        goto LABEL_32;
      }
      v32 = 0;
      for ( i = v87; v32 < v86; ++v32 )
        i[v32] ^= 0xF0u;
      Kerb3961::RC4_4757::HmacData(
        a1,
        &v89,
        &v86,
        &__S42__1__CommonUnwrap_RC4_4757_Kerb3961__EEAA_AU__ReturnType_UUnwrapResult_Kerb3961___1___DoubleGetter_UUnwrapResult_Kerb3961__UOwnedBinary_2__0A__0BA__2_YAAEBUResultBlock_2_AEBU12__Z_1___DoubleSetter_UUnwrapResult_Kerb3961__UOwnedBinary_2__0A__0BA__2_YAAEAU32_AEAU12__Z_3_AEBUReadOnlyBinary_3_AEBV__function___A6A_AU__ReturnType_UOwnedBinary_Kerb3961___1___SingleGetter_UOwnedBinary_Kerb3961___0BA__2_YAAEBUResultBlock_2_AEBU12__Z_1___SingleSetter_UOwnedBinary_Kerb3961___0BA__2_YAAEAU32_AEAU12__Z_Kerb3961__AEBUReadOnlyBinary_2__Z_utl__0_N2_Z_4U53_B);
      v35 = (unsigned int)v91;
      if ( (int)v91 < 0 )
        goto LABEL_39;
      v86 = 4;
      v87 = &v107;
      v36 = Kerb3961::RC4_4757::HmacData(a1, v110, &v89, &v86);
      if ( v90 )
        operator delete(v90, 0);
      v89 = *(_QWORD *)v36;
      v37 = *(void **)(v36 + 8);
      *(_QWORD *)v36 = 0;
      v90 = v37;
      v38 = *(_DWORD *)(v36 + 16);
      *(_QWORD *)(v36 + 8) = 0;
      LODWORD(v91) = v38;
      *(_DWORD *)(v36 + 16) = -1073741823;
      if ( v111 )
        operator delete(v111, 0);
      v35 = (unsigned int)v91;
      if ( (int)v91 < 0 )
      {
LABEL_39:
        Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)"Kcrypt", (const char *)v35, v34);
        *(_QWORD *)(a2 + 20) = 0;
        *(_QWORD *)(a2 + 28) = 0;
        *(_DWORD *)(a2 + 36) = 0;
        *(_QWORD *)a2 = 0;
        *(_DWORD *)(a2 + 16) = v35;
        *(_QWORD *)(a2 + 8) = 0;
LABEL_40:
        if ( v90 )
          operator delete(v90, 0);
        if ( !i )
        {
LABEL_34:
          v31 = v81;
          if ( !v81 )
            goto LABEL_130;
          goto LABEL_35;
        }
        v30 = i;
LABEL_33:
        operator delete(v30, 0);
        goto LABEL_34;
      }
      Kerb3961::Concatenate(&v86, &v92, v102);
      v40 = (int)v88;
      if ( (int)v88 < 0 )
      {
        v41 = "tmp";
LABEL_51:
        Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)v41, (const char *)(unsigned int)v40, v39);
        *(_QWORD *)(a2 + 20) = 0;
        *(_QWORD *)(a2 + 28) = 0;
        *(_DWORD *)(a2 + 36) = 0;
        *(_QWORD *)a2 = 0;
        *(_QWORD *)(a2 + 8) = 0;
        *(_DWORD *)(a2 + 16) = v40;
LABEL_52:
        if ( v87 )
          operator delete(v87, 0);
        goto LABEL_40;
      }
      v40 = *(_DWORD *)Kerb3961::RC4_4757::RC4Data(a1, v112, &v89, &v86);
      if ( v40 < 0 )
      {
        v41 = "RC4Data(Kcrypt, tmp)";
        goto LABEL_51;
      }
      v93 = (void *)v102[0];
      v92 = 8;
      Kerb3961::Split<2>(&v118, &v86, &v92);
      if ( !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a4 + 32LL))(a4) )
        __int2c();
      (*(void (__fastcall **)(__int64, __int64 *, _QWORD *))(*(_QWORD *)a4 + 24LL))(a4, &v96, v119);
      v43 = (unsigned int)v98;
      if ( (int)v98 < 0 )
      {
        v44 = "authData";
        goto LABEL_60;
      }
      v46 = &v96;
      v114 = 8;
      if ( !v97 )
        v46 = v119;
      v113 = *(_OWORD *)__S43__1__CommonUnwrap_RC4_4757_Kerb3961__EEAA_AU__ReturnType_UUnwrapResult_Kerb3961___1___DoubleGetter_UUnwrapResult_Kerb3961__UOwnedBinary_2__0A__0BA__2_YAAEBUResultBlock_2_AEBU12__Z_1___DoubleSetter_UUnwrapResult_Kerb3961__UOwnedBinary_2__0A__0BA__2_YAAEAU32_AEAU12__Z_3_AEBUReadOnlyBinary_3_AEBV__function___A6A_AU__ReturnType_UOwnedBinary_Kerb3961___1___SingleGetter_UOwnedBinary_Kerb3961___0BA__2_YAAEBUResultBlock_2_AEBU12__Z_1___SingleSetter_UOwnedBinary_Kerb3961___0BA__2_YAAEAU32_AEAU12__Z_Kerb3961__AEBUReadOnlyBinary_2__Z_utl__0_N2_Z_4U53_B;
      v47 = *(_OWORD *)v46;
      v115 = a3[1];
      v117 = v47;
      v116 = v118;
      Kerb3961::Concatenate<4>(&v92, &v113);
      if ( v81 )
        operator delete(v81, 0);
      v43 = (unsigned int)v94;
      v80 = v92;
      v81 = v93;
      v82 = (int)v94;
      if ( (int)v94 < 0 )
      {
        v44 = "checksummedData";
LABEL_60:
        Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)v44, (const char *)v43, v42);
        *(_QWORD *)(a2 + 20) = 0;
        *(_QWORD *)(a2 + 28) = 0;
        *(_DWORD *)(a2 + 36) = 0;
        v45 = v97;
        *(_QWORD *)a2 = 0;
        *(_QWORD *)(a2 + 8) = 0;
        *(_DWORD *)(a2 + 16) = v43;
        if ( v45 )
          operator delete(v45, 0);
        goto LABEL_52;
      }
      v48 = Kerb3961::CopyBuffer(v110, v119);
      v50 = *(_QWORD *)v48;
      v51 = *(void **)(v48 + 8);
      v52 = *(_DWORD *)(v48 + 16);
      *(_QWORD *)v48 = 0;
      *(_QWORD *)(v48 + 8) = 0;
      *(_DWORD *)(v48 + 16) = -1073741823;
      if ( v111 )
        operator delete(v111, 0);
      if ( v52 < 0 )
      {
        Kerb3961::Logging::Verify::StatusFailed(
          (Kerb3961::Logging::Verify *)"outputMessage",
          (const char *)(unsigned int)v52,
          v49);
        *(_QWORD *)(a2 + 20) = 0;
        *(_QWORD *)(a2 + 28) = 0;
        *(_DWORD *)(a2 + 36) = 0;
        v53 = v97;
        *(_QWORD *)a2 = 0;
        *(_QWORD *)(a2 + 8) = 0;
        *(_DWORD *)(a2 + 16) = v52;
        if ( v53 )
          operator delete(v53, 0);
        if ( v87 )
          operator delete(v87, 0);
        if ( v90 )
          operator delete(v90, 0);
        if ( !i )
          goto LABEL_80;
        v54 = i;
LABEL_79:
        operator delete(v54, 0);
LABEL_80:
        if ( v81 )
          operator delete(v81, 0);
        if ( !v51 )
          goto LABEL_130;
        v31 = v51;
LABEL_35:
        operator delete(v31, 0);
        goto LABEL_130;
      }
      if ( v97 )
        operator delete(v97, 0);
      if ( v87 )
        operator delete(v87, 0);
      if ( v90 )
        operator delete(v90, 0);
      if ( !i )
        goto LABEL_113;
      v55 = i;
LABEL_112:
      operator delete(v55, 0);
LABEL_113:
      Kerb3961::RC4_4757::HashData(a1, &v99, &v80);
      v67 = (unsigned int)v101;
      if ( (int)v101 < 0 )
        goto LABEL_114;
      v68 = Kerb3961::RC4_4757::HmacData(a1, v110, v83, &v99);
      if ( v100 )
        operator delete(v100, 0);
      v99 = *(_QWORD *)v68;
      v69 = *(void **)(v68 + 8);
      *(_QWORD *)v68 = 0;
      v100 = v69;
      v70 = *(_DWORD *)(v68 + 16);
      *(_QWORD *)(v68 + 8) = 0;
      LODWORD(v101) = v70;
      *(_DWORD *)(v68 + 16) = -1073741823;
      if ( v111 )
        operator delete(v111, 0);
      v67 = (unsigned int)v101;
      if ( (int)v101 < 0 )
      {
LABEL_114:
        Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)"Sgn_Cksum", (const char *)v67, v66);
        *(_QWORD *)(a2 + 20) = 0;
        *(_QWORD *)(a2 + 28) = 0;
        *(_DWORD *)(a2 + 36) = 0;
        *(_QWORD *)a2 = 0;
        *(_QWORD *)(a2 + 8) = 0;
        *(_DWORD *)(a2 + 16) = v67;
LABEL_115:
        v54 = v100;
LABEL_116:
        if ( !v54 )
          goto LABEL_80;
        goto LABEL_79;
      }
      v71 = 0;
      for ( j = 0; j != 8; ++j )
      {
        v73 = v110[j - 16];
        v74 = *((_BYTE *)v100 + j);
        v71 |= v74 ^ v73;
      }
      if ( v71 )
      {
        Kerb3961::Logging::Verify::ConditionFailed(
          (Kerb3961::Logging::Verify *)"SecureEqualBuffer(checksumBuffer, Sgn_Cksum.buffer, checksumBuffer.length)",
          (const char *)8);
        *(_QWORD *)(a2 + 20) = 0;
        *(_QWORD *)(a2 + 28) = 0;
        *(_DWORD *)(a2 + 36) = 0;
        *(_QWORD *)a2 = 0;
        *(_QWORD *)(a2 + 8) = 0;
        *(_DWORD *)(a2 + 16) = -2146893041;
        goto LABEL_115;
      }
      v30 = v100;
      *(_QWORD *)(a2 + 24) = v95;
      *(_BYTE *)(a2 + 36) = v76;
      *(_QWORD *)a2 = v50;
      *(_QWORD *)(a2 + 8) = v51;
      *(_DWORD *)(a2 + 32) = 0;
      *(_DWORD *)(a2 + 16) = 0;
LABEL_32:
      if ( !v30 )
        goto LABEL_34;
      goto LABEL_33;
    }
    if ( !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a4 + 32LL))(a4) )
      __int2c();
    (*(void (__fastcall **)(__int64, __int64 *, _QWORD *))(*(_QWORD *)a4 + 24LL))(a4, &v92, v102);
    v58 = (unsigned int)v94;
    if ( (int)v94 >= 0 )
    {
      if ( v92 && v102[0] )
      {
        Kerb3961::Logging::Verify::ConditionFailed(
          (Kerb3961::Logging::Verify *)"authData.length == 0 || payloadBuffer.length == 0",
          v56);
        *(_QWORD *)(a2 + 20) = 0;
        *(_QWORD *)(a2 + 28) = 0;
        *(_DWORD *)(a2 + 36) = 0;
        *(_QWORD *)a2 = 0;
        *(_QWORD *)(a2 + 8) = 0;
        *(_DWORD *)(a2 + 16) = -2146893046;
        goto LABEL_97;
      }
      v60 = v102;
      v119[0] = 8;
      if ( v92 )
        v60 = &v92;
      v119[2] = 8;
      v61 = a3[1];
      v118 = *(_OWORD *)__S43__1__CommonUnwrap_RC4_4757_Kerb3961__EEAA_AU__ReturnType_UUnwrapResult_Kerb3961___1___DoubleGetter_UUnwrapResult_Kerb3961__UOwnedBinary_2__0A__0BA__2_YAAEBUResultBlock_2_AEBU12__Z_1___DoubleSetter_UUnwrapResult_Kerb3961__UOwnedBinary_2__0A__0BA__2_YAAEAU32_AEAU12__Z_3_AEBUReadOnlyBinary_3_AEBV__function___A6A_AU__ReturnType_UOwnedBinary_Kerb3961___1___SingleGetter_UOwnedBinary_Kerb3961___0BA__2_YAAEBUResultBlock_2_AEBU12__Z_1___SingleSetter_UOwnedBinary_Kerb3961___0BA__2_YAAEAU32_AEAU12__Z_Kerb3961__AEBUReadOnlyBinary_2__Z_utl__0_N2_Z_4U53_B;
      v119[1] = v61;
      v62 = *(_OWORD *)v60;
      v119[3] = (char *)&v109 + 8;
      v120 = v62;
      Kerb3961::Concatenate<4>(&v96, &v118);
      if ( v81 )
        operator delete(v81, 0);
      v58 = (unsigned int)v98;
      v80 = v96;
      v81 = v97;
      v82 = (int)v98;
      if ( (int)v98 >= 0 )
      {
        v63 = Kerb3961::CopyBuffer(v110, v102);
        v50 = *(_QWORD *)v63;
        v51 = *(void **)(v63 + 8);
        v65 = *(_DWORD *)(v63 + 16);
        *(_QWORD *)v63 = 0;
        *(_QWORD *)(v63 + 8) = 0;
        *(_DWORD *)(v63 + 16) = -1073741823;
        if ( v111 )
          operator delete(v111, 0);
        if ( v65 < 0 )
        {
          Kerb3961::Logging::Verify::StatusFailed(
            (Kerb3961::Logging::Verify *)"outputMessage",
            (const char *)(unsigned int)v65,
            v64);
          *(_QWORD *)(a2 + 20) = 0;
          *(_QWORD *)(a2 + 28) = 0;
          *(_DWORD *)(a2 + 36) = 0;
          v54 = v93;
          *(_QWORD *)a2 = 0;
          *(_QWORD *)(a2 + 8) = 0;
          *(_DWORD *)(a2 + 16) = v65;
          goto LABEL_116;
        }
        v55 = v93;
        if ( !v93 )
          goto LABEL_113;
        goto LABEL_112;
      }
      v59 = "checksummedData";
    }
    else
    {
      v59 = "authData";
    }
    Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)v59, (const char *)v58, v57);
    *(_QWORD *)(a2 + 20) = 0;
    *(_QWORD *)(a2 + 28) = 0;
    *(_DWORD *)(a2 + 36) = 0;
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = v58;
LABEL_97:
    v30 = v93;
    goto LABEL_32;
  }
  Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)"Ksign", (const char *)(unsigned int)v85, v19);
  *(_QWORD *)(a2 + 20) = 0;
  *(_QWORD *)(a2 + 28) = 0;
  *(_DWORD *)(a2 + 36) = 0;
  *(_QWORD *)a2 = 0;
  *(_QWORD *)(a2 + 8) = 0;
  *(_DWORD *)(a2 + 16) = v20;
LABEL_132:
  if ( v84 )
    operator delete(v84, 0);
  return a2;
}

```

## disassembly

```asm
0x180005480  mov     [rsp-8+arg_10], rbx
0x180005485  push    rbp
0x180005486  push    rsi
0x180005487  push    rdi
0x180005488  push    r12
0x18000548a  push    r13
0x18000548c  push    r14
0x18000548e  push    r15
0x180005490  lea     rbp, [rsp-0F0h]
0x180005498  sub     rsp, 1F0h
0x18000549f  mov     rax, cs:__security_cookie
0x1800054a6  xor     rax, rsp
0x1800054a9  mov     [rbp+120h+var_40], rax
0x1800054b0  mov     r14, [rbp+120h+arg_20]
0x1800054b7  mov     r12, rcx
0x1800054ba  add     rcx, 8
0x1800054be  mov     r15, r9
0x1800054c1  mov     r13, r8
0x1800054c4  mov     rdi, rdx
0x1800054c7  mov     rax, [rcx]
0x1800054ca  mov     rax, [rax+68h]
0x1800054ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054d3  mov     ebx, eax
0x1800054d5  mov     rcx, r12
0x1800054d8  mov     rax, [r12]
0x1800054dc  mov     rax, [rax+0E0h]
0x1800054e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054e8  cmp     ebx, eax
0x1800054ea  jnz     loc_180005EB4
0x1800054f0  mov     r8, [r13+0]
0x1800054f4  cmp     r8, 20h ; ' '
0x1800054f8  jnb     short loc_180005526
0x1800054fa  lea     rcx, aMessageLengthS; "message.length >= sizeof(WrapToken)"
0x180005501  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180005506  xor     ebx, ebx
0x180005508  mov     [rdi+14h], rbx
0x18000550c  mov     [rdi+1Ch], rbx
0x180005510  mov     [rdi+24h], ebx
0x180005513  mov     [rdi], rbx
0x180005516  mov     [rdi+8], rbx
0x18000551a  mov     dword ptr [rdi+10h], 8009030Fh
0x180005521  jmp     loc_180005E87
0x180005526  mov     rcx, [r13+8]
0x18000552a  mov     ebx, 8
0x18000552f  mov     [rsp+220h+var_1B0], rbx
0x180005534  mov     [rbp+120h+var_198], rbx
0x180005538  mov     [rbp+120h+var_180], rbx
0x18000553c  movzx   edx, word ptr [rcx]; char *
0x18000553f  mov     [rbp+120h+var_118], dx
0x180005543  movzx   r10d, word ptr [rcx+2]
0x180005548  mov     [rbp+120h+var_116], r10w
0x18000554d  movzx   r9d, word ptr [rcx+4]
0x180005552  mov     [rbp+120h+var_114], r9w
0x180005557  movzx   r11d, word ptr [rcx+6]
0x18000555c  mov     [rbp+120h+var_112], r11w
0x180005561  mov     eax, [rcx+8]
0x180005564  mov     [rbp+120h+var_110], eax
0x180005567  mov     eax, [rcx+0Ch]
0x18000556a  mov     [rbp+120h+var_10C], eax
0x18000556d  lea     rax, [rbp+120h+var_110]
0x180005571  movups  xmm0, xmmword ptr [rcx+10h]
0x180005575  mov     [rsp+220h+var_1A8], rax
0x18000557a  lea     rax, [rbp+120h+var_108]
0x18000557e  mov     [rbp+120h+var_190], rax
0x180005582  lea     rax, [rbp+120h+var_108+8]
0x180005586  mov     [rbp+120h+var_178], rax
0x18000558a  lea     rax, [r8-20h]
0x18000558e  mov     [rbp+120h+var_128], rax
0x180005592  lea     rax, [rcx+20h]
0x180005596  mov     [rbp+120h+var_120], rax
0x18000559a  mov     eax, 102h
0x18000559f  movdqu  [rbp+120h+var_108], xmm0
0x1800055a4  cmp     dx, ax
0x1800055a7  jz      short loc_1800055B5
0x1800055a9  lea     rcx, aHeaderTokIdHea; "header.TOK_ID == header.ID"
0x1800055b0  jmp     loc_180005501
0x1800055b5  cmp     r10w, 11h
0x1800055ba  jz      short loc_1800055C8
0x1800055bc  lea     rcx, aHeaderSgnAlgHe; "header.SGN_ALG == header.SignAlgorithm"
0x1800055c3  jmp     loc_180005501
0x1800055c8  mov     eax, 0FFFFh
0x1800055cd  cmp     r11w, ax
0x1800055d1  jz      short loc_1800055DF
0x1800055d3  lea     rcx, aHeaderFillerHe; "header.Filler == header.FillerBytes"
0x1800055da  jmp     loc_180005501
0x1800055df  xor     ebx, ebx
0x1800055e1  cmp     r9w, 10h
0x1800055e6  jnz     short loc_180005634
0x1800055e8  mov     [rsp+220h+var_200], 1
0x1800055ed  lea     r9, ?$S41@?1??CommonUnwrap@RC4_4757@Kerb3961@@EEAA?AU?$ReturnType@UUnwrapResult@Kerb3961@@$1??$DoubleGetter@UUnwrapResult@Kerb3961@@UOwnedBinary@2@$0A@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$DoubleSetter@UUnwrapResult@Kerb3961@@UOwnedBinary@2@$0A@$0BA@@2@YAAEAU32@AEAU12@@Z@3@AEBUReadOnlyBinary@3@AEBV?$function@$$A6A?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@Kerb3961@@AEBUReadOnlyBinary@2@@Z@utl@@0_N2@Z@4U53@B
0x1800055f4  mov     r8, r14
0x1800055f7  lea     rdx, [rsp+220h+var_1C8]
0x1800055fc  mov     rcx, r12
0x1800055ff  call    ?HmacData@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0@Z; Kerb3961::RC4_4757::HmacData(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x180005604  mov     esi, dword ptr [rsp+220h+var_1B8]
0x180005608  test    esi, esi
0x18000560a  jns     short loc_18000564F
0x18000560c  mov     edx, esi; char *
0x18000560e  lea     rcx, aKsign; "Ksign"
0x180005615  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000561a  mov     [rdi+14h], rbx
0x18000561e  mov     [rdi+1Ch], rbx
0x180005622  mov     [rdi+24h], ebx
0x180005625  mov     [rdi], rbx
0x180005628  mov     [rdi+8], rbx
0x18000562c  mov     [rdi+10h], esi
0x18000562f  jmp     loc_180005E76
0x180005634  mov     [rsp+220h+var_200], bl
0x180005638  cmp     r9w, ax
0x18000563c  jz      short loc_1800055ED
0x18000563e  lea     rcx, aEncryptedHeade; "encrypted || header.SEAL_ALG == header."...
0x180005645  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000564a  jmp     loc_180005508
0x18000564f  lea     r9, ?$S42@?1??CommonUnwrap@RC4_4757@Kerb3961@@EEAA?AU?$ReturnType@UUnwrapResult@Kerb3961@@$1??$DoubleGetter@UUnwrapResult@Kerb3961@@UOwnedBinary@2@$0A@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$DoubleSetter@UUnwrapResult@Kerb3961@@UOwnedBinary@2@$0A@$0BA@@2@YAAEAU32@AEAU12@@Z@3@AEBUReadOnlyBinary@3@AEBV?$function@$$A6A?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@Kerb3961@@AEBUReadOnlyBinary@2@@Z@utl@@0_N2@Z@4U53@B
0x180005656  mov     r8, r14
0x180005659  lea     rdx, [rsp+220h+var_1F8]
0x18000565e  mov     rcx, r12
0x180005661  call    ?HmacData@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0@Z; Kerb3961::RC4_4757::HmacData(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x180005666  mov     esi, dword ptr [rsp+220h+var_1E8]
0x18000566a  test    esi, esi
0x18000566c  jns     short loc_18000568F
0x18000566e  lea     rcx, aKseq; "Kseq"
0x180005675  mov     edx, esi; char *
0x180005677  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000567c  mov     [rdi+14h], rbx
0x180005680  mov     [rdi+1Ch], rbx
0x180005684  mov     [rdi+24h], ebx
0x180005687  mov     [rdi+10h], esi
0x18000568a  jmp     loc_180005E5E
0x18000568f  lea     r9, [rbp+120h+var_198]
0x180005693  mov     rcx, r12
0x180005696  lea     r8, [rsp+220h+var_1F8]
0x18000569b  lea     rdx, [rbp+120h+var_158]
0x18000569f  call    ?HmacData@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0@Z; Kerb3961::RC4_4757::HmacData(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x1800056a4  mov     rcx, [rsp+220h+var_1F0]; void *
0x1800056a9  mov     rsi, rax
0x1800056ac  test    rcx, rcx
0x1800056af  jz      short loc_1800056B8
0x1800056b1  xor     edx, edx; struct std::nothrow_t *
0x1800056b3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800056b8  mov     rcx, [rsi]
0x1800056bb  mov     [rsp+220h+var_1F8], rcx
0x1800056c0  mov     rcx, [rsi+8]
0x1800056c4  mov     [rsi], rbx
0x1800056c7  mov     [rsp+220h+var_1F0], rcx
0x1800056cc  mov     eax, [rsi+10h]
0x1800056cf  mov     [rsi+8], rbx
0x1800056d3  mov     dword ptr [rsp+220h+var_1E8], eax
0x1800056d7  mov     dword ptr [rsi+10h], 0C0000001h
0x1800056de  mov     rcx, [rbp+120h+var_150]; void *
0x1800056e2  test    rcx, rcx
0x1800056e5  jz      short loc_1800056EE
0x1800056e7  xor     edx, edx; struct std::nothrow_t *
0x1800056e9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800056ee  mov     esi, dword ptr [rsp+220h+var_1E8]
0x1800056f2  test    esi, esi
0x1800056f4  js      loc_18000566E
0x1800056fa  lea     r9, [rsp+220h+var_1B0]
0x1800056ff  mov     rcx, r12
0x180005702  lea     r8, [rsp+220h+var_1F8]
0x180005707  lea     rdx, [rbp+120h+var_160]
0x18000570b  call    ?RC4Data@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UStatusOnly@Kerb3961@@$1??$SingleGetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@AEBUMutableBinary@2@@Z; Kerb3961::RC4_4757::RC4Data(Kerb3961::ReadOnlyBinary const &,Kerb3961::MutableBinary const &)
0x180005710  mov     esi, [rax]
0x180005712  test    esi, esi
0x180005714  jns     short loc_180005722
0x180005716  lea     rcx, aRc4dataKseqSeq; "RC4Data(Kseq, sequenceBuffer)"
0x18000571d  jmp     loc_180005675
0x180005722  neg     [rbp+120h+arg_28]
0x180005728  sbb     eax, eax
0x18000572a  cmp     [rbp+120h+var_10C], eax
0x18000572d  jnz     loc_180005E40
0x180005733  mov     eax, [rbp+120h+var_110]
0x180005736  bswap   eax
0x180005738  mov     [rbp+120h+var_160], eax
0x18000573b  mov     [rsp+220h+var_1E0], rbx
0x180005740  mov     [rsp+220h+var_1D8], rbx
0x180005745  mov     [rsp+220h+var_1D0], 0C0000001h
0x18000574d  cmp     [rsp+220h+var_200], bl
0x180005751  jz      loc_180005B70
0x180005757  mov     rdx, r14
0x18000575a  lea     rcx, [rsp+220h+var_1B0]
0x18000575f  call    ?CopyBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyBinary@1@@Z; Kerb3961::CopyBuffer(Kerb3961::ReadOnlyBinary const &)
0x180005764  mov     esi, dword ptr [rbp+120h+var_1A0]
0x180005767  test    esi, esi
0x180005769  jns     short loc_1800057B9
0x18000576b  mov     edx, esi; char *
0x18000576d  lea     rcx, aKlocal; "Klocal"
0x180005774  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180005779  mov     [rdi+14h], rbx
0x18000577d  mov     [rdi+1Ch], rbx
0x180005781  mov     [rdi+24h], ebx
0x180005784  mov     rcx, [rsp+220h+var_1A8]; void *
0x180005789  mov     [rdi], rbx
0x18000578c  mov     [rdi+8], rbx
0x180005790  mov     [rdi+10h], esi
0x180005793  test    rcx, rcx
0x180005796  jz      short loc_18000579F
0x180005798  xor     edx, edx; struct std::nothrow_t *
0x18000579a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000579f  mov     rcx, [rsp+220h+var_1D8]; void *
0x1800057a4  test    rcx, rcx
0x1800057a7  jz      loc_180005E65
0x1800057ad  xor     edx, edx; struct std::nothrow_t *
0x1800057af  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800057b4  jmp     loc_180005E65
0x1800057b9  mov     rax, rbx
0x1800057bc  mov     rsi, [rsp+220h+var_1A8]
0x1800057c1  cmp     [rsp+220h+var_1B0], rbx
0x1800057c6  jbe     short loc_1800057D6
0x1800057c8  xor     byte ptr [rsi+rax], 0F0h
0x1800057cc  inc     rax
0x1800057cf  cmp     rax, [rsp+220h+var_1B0]
0x1800057d4  jb      short loc_1800057C8
0x1800057d6  lea     r9, ?$S42@?1??CommonUnwrap@RC4_4757@Kerb3961@@EEAA?AU?$ReturnType@UUnwrapResult@Kerb3961@@$1??$DoubleGetter@UUnwrapResult@Kerb3961@@UOwnedBinary@2@$0A@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$DoubleSetter@UUnwrapResult@Kerb3961@@UOwnedBinary@2@$0A@$0BA@@2@YAAEAU32@AEAU12@@Z@3@AEBUReadOnlyBinary@3@AEBV?$function@$$A6A?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@Kerb3961@@AEBUReadOnlyBinary@2@@Z@utl@@0_N2@Z@4U53@B
0x1800057dd  mov     rcx, r12
0x1800057e0  lea     r8, [rsp+220h+var_1B0]
0x1800057e5  lea     rdx, [rbp+120h+var_198]
0x1800057e9  call    ?HmacData@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0@Z; Kerb3961::RC4_4757::HmacData(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x1800057ee  mov     r14d, dword ptr [rbp+120h+var_188]
0x1800057f2  test    r14d, r14d
0x1800057f5  jns     short loc_18000583D
0x1800057f7  mov     edx, r14d; char *
0x1800057fa  lea     rcx, aKcrypt; "Kcrypt"
0x180005801  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180005806  mov     [rdi+14h], rbx
0x18000580a  mov     [rdi+1Ch], rbx
0x18000580e  mov     [rdi+24h], ebx
0x180005811  mov     [rdi], rbx
0x180005814  mov     [rdi+10h], r14d
0x180005818  mov     [rdi+8], rbx
0x18000581c  mov     rcx, [rbp+120h+var_190]; void *
0x180005820  test    rcx, rcx
0x180005823  jz      short loc_18000582C
0x180005825  xor     edx, edx; struct std::nothrow_t *
0x180005827  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000582c  test    rsi, rsi
0x18000582f  jz      loc_18000579F
0x180005835  mov     rcx, rsi
0x180005838  jmp     loc_180005798
0x18000583d  lea     rax, [rbp+120h+var_110]
0x180005841  mov     [rsp+220h+var_1B0], 4
0x18000584a  lea     r9, [rsp+220h+var_1B0]
0x18000584f  mov     [rsp+220h+var_1A8], rax
0x180005854  lea     r8, [rbp+120h+var_198]
0x180005858  mov     rcx, r12
0x18000585b  lea     rdx, [rbp+120h+var_F8]
0x18000585f  call    ?HmacData@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0@Z; Kerb3961::RC4_4757::HmacData(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x180005864  mov     rcx, [rbp+120h+var_190]; void *
0x180005868  mov     r14, rax
0x18000586b  test    rcx, rcx
0x18000586e  jz      short loc_180005877
0x180005870  xor     edx, edx; struct std::nothrow_t *
0x180005872  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180005877  mov     rcx, [r14]
0x18000587a  mov     [rbp+120h+var_198], rcx
0x18000587e  mov     rcx, [r14+8]
0x180005882  mov     [r14], rbx
0x180005885  mov     [rbp+120h+var_190], rcx
0x180005889  mov     eax, [r14+10h]
0x18000588d  mov     [r14+8], rbx
0x180005891  mov     dword ptr [rbp+120h+var_188], eax
0x180005894  mov     dword ptr [r14+10h], 0C0000001h
0x18000589c  mov     rcx, [rbp+120h+var_F0]; void *
0x1800058a0  test    rcx, rcx
0x1800058a3  jz      short loc_1800058AC
0x1800058a5  xor     edx, edx; struct std::nothrow_t *
0x1800058a7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800058ac  mov     r14d, dword ptr [rbp+120h+var_188]
0x1800058b0  test    r14d, r14d
0x1800058b3  js      loc_1800057F7
0x1800058b9  lea     r8, [rbp+120h+var_128]
0x1800058bd  lea     rdx, [rbp+120h+var_180]
0x1800058c1  lea     rcx, [rsp+220h+var_1B0]
0x1800058c6  call    ?Concatenate@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyBinary@1@0@Z; Kerb3961::Concatenate(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x1800058cb  mov     r14d, dword ptr [rbp+120h+var_1A0]
0x1800058cf  test    r14d, r14d
0x1800058d2  jns     short loc_180005913
0x1800058d4  lea     rcx, aTmp; "tmp"
0x1800058db  mov     edx, r14d; char *
0x1800058de  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x1800058e3  mov     [rdi+14h], rbx
0x1800058e7  mov     [rdi+1Ch], rbx
0x1800058eb  mov     [rdi+24h], ebx
0x1800058ee  mov     [rdi], rbx
0x1800058f1  mov     [rdi+8], rbx
0x1800058f5  mov     [rdi+10h], r14d
0x1800058f9  mov     rcx, [rsp+220h+var_1A8]; void *
0x1800058fe  test    rcx, rcx
0x180005901  jz      loc_18000581C
0x180005907  xor     edx, edx; struct std::nothrow_t *
0x180005909  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000590e  jmp     loc_18000581C
0x180005913  lea     r9, [rsp+220h+var_1B0]
0x180005918  mov     rcx, r12
0x18000591b  lea     r8, [rbp+120h+var_198]
0x18000591f  lea     rdx, [rbp+120h+var_E0]
0x180005923  call    ?RC4Data@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UStatusOnly@Kerb3961@@$1??$SingleGetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@AEBUMutableBinary@2@@Z; Kerb3961::RC4_4757::RC4Data(Kerb3961::ReadOnlyBinary const &,Kerb3961::MutableBinary const &)
0x180005928  mov     r14d, [rax]
0x18000592b  test    r14d, r14d
0x18000592e  jns     short loc_180005939
  ... truncated ...
```
