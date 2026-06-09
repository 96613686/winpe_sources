# Kerb3961::RC4_4757::CommonUnwrap(Kerb3961::ReadOnlyBinary const &,utl::function<Kerb3961::ReturnType<Kerb3961::OwnedBinary,&Kerb3961::SingleGetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary const &),&Kerb3961::SingleSetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary &)> (Kerb3961::ReadOnlyBinary const &)> const &,Kerb3961::ReadOnlyBinary const &,bool,bool)

- ea: `0x18000d900`
- end: `0x18000e30a`
- name: `?CommonUnwrap@RC4_4757@Kerb3961@@EEAA?AU?$ReturnType@UUnwrapResult@Kerb3961@@$1??$DoubleGetter@UUnwrapResult@Kerb3961@@UOwnedBinary@2@$0A@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$DoubleSetter@UUnwrapResult@Kerb3961@@UOwnedBinary@2@$0A@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@AEBV?$function@$$A6A?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@Kerb3961@@AEBUReadOnlyBinary@2@@Z@utl@@0_N2@Z`
- size: `2570`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x180001464`
- `0x180001580`
- `0x180003910`
- `0x180003a38`
- `0x180003a54`
- `0x18000d900`
- `0x18000fd70`
- `0x18000fe44`
- `0x180010290`
- `0x180011760`
- `0x1800118cc`
- `0x180011b40`
- `0x180012200`
- `0x180012240`

## string_xrefs

- `0x18000d97a`: `message.length >= sizeof(WrapToken)`

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
  __int64 v25; // rcx
  int v26; // eax
  const char *v27; // rdx
  int v28; // r8d
  int v29; // esi
  unsigned int *v30; // rcx
  char *v31; // rcx
  unsigned __int64 v32; // rax
  unsigned int *i; // rsi
  int v34; // r8d
  unsigned int v35; // r14d
  __int64 v36; // r14
  __int128 *v37; // rcx
  int v38; // eax
  int v39; // r8d
  int v40; // r14d
  char *v41; // rcx
  int v42; // r8d
  unsigned int v43; // r14d
  char *v44; // rcx
  char *v45; // rcx
  __int64 *v46; // rax
  __int128 v47; // xmm2
  __int64 v48; // rax
  int v49; // r8d
  __int64 v50; // r13
  char *v51; // r14
  int v52; // r15d
  char *v53; // rcx
  unsigned int *v54; // rcx
  unsigned int *v55; // rcx
  const char *v56; // rdx
  int v57; // r8d
  unsigned int v58; // esi
  char *v59; // rcx
  __int64 *v60; // rcx
  __int64 v61; // rax
  int v62; // r8d
  int v63; // esi
  int v64; // r8d
  unsigned int v65; // esi
  __int64 v66; // rsi
  unsigned int *v67; // rcx
  int v68; // eax
  char v69; // r8
  __int64 j; // rdx
  char v71; // cl
  char v72; // al
  char v74; // [rsp+20h] [rbp-E0h]
  __int64 v75; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v76; // [rsp+30h] [rbp-D0h]
  char *v77; // [rsp+38h] [rbp-C8h]
  __int64 v78; // [rsp+40h] [rbp-C0h] BYREF
  char *v79; // [rsp+48h] [rbp-B8h]
  int v80; // [rsp+50h] [rbp-B0h]
  char v81[8]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v82; // [rsp+60h] [rbp-A0h]
  char *v83; // [rsp+68h] [rbp-98h]
  unsigned __int64 v84; // [rsp+70h] [rbp-90h] BYREF
  unsigned int *v85; // [rsp+78h] [rbp-88h]
  char *v86; // [rsp+80h] [rbp-80h]
  __int64 v87; // [rsp+88h] [rbp-78h] BYREF
  __int128 *v88; // [rsp+90h] [rbp-70h]
  char *v89; // [rsp+98h] [rbp-68h]
  __int64 v90; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int *v91; // [rsp+A8h] [rbp-58h]
  char *v92; // [rsp+B0h] [rbp-50h]
  unsigned __int32 v93; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v94; // [rsp+C8h] [rbp-38h] BYREF
  char *v95; // [rsp+D0h] [rbp-30h]
  char *v96; // [rsp+D8h] [rbp-28h]
  __int64 v97; // [rsp+E0h] [rbp-20h] BYREF
  unsigned int *v98; // [rsp+E8h] [rbp-18h]
  char *v99; // [rsp+F0h] [rbp-10h]
  _QWORD v100[2]; // [rsp+F8h] [rbp-8h] BYREF
  __int16 v101; // [rsp+108h] [rbp+8h]
  unsigned __int16 v102; // [rsp+10Ah] [rbp+Ah]
  unsigned __int16 v103; // [rsp+10Ch] [rbp+Ch]
  unsigned __int16 v104; // [rsp+10Eh] [rbp+Eh]
  unsigned int v105; // [rsp+110h] [rbp+10h] BYREF
  int v106; // [rsp+114h] [rbp+14h]
  __int128 v107; // [rsp+118h] [rbp+18h] BYREF
  char v108[8]; // [rsp+128h] [rbp+28h] BYREF
  __int64 v109; // [rsp+130h] [rbp+30h]
  char v110[32]; // [rsp+140h] [rbp+40h] BYREF
  __int128 v111; // [rsp+160h] [rbp+60h] BYREF
  __int64 v112; // [rsp+170h] [rbp+70h]
  __int64 v113; // [rsp+178h] [rbp+78h]
  __int128 v114; // [rsp+180h] [rbp+80h]
  __int128 v115; // [rsp+190h] [rbp+90h]
  __int128 v116; // [rsp+1A0h] [rbp+A0h] BYREF
  _QWORD v117[4]; // [rsp+1B0h] [rbp+B0h] BYREF
  __int128 v118; // [rsp+1D0h] [rbp+D0h]

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
  v84 = 8;
  v87 = 8;
  v90 = 8;
  v11 = (const unsigned __int16 *)*v14;
  v101 = (__int16)v11;
  v15 = v14[1];
  v102 = v15;
  v16 = v14[2];
  v103 = v16;
  v17 = v14[3];
  v104 = v17;
  v105 = *((_DWORD *)v14 + 2);
  v106 = *((_DWORD *)v14 + 3);
  v18 = *((_OWORD *)v14 + 1);
  v85 = &v105;
  v88 = &v107;
  v91 = (unsigned int *)&v107 + 2;
  v100[0] = v12 - 32;
  v100[1] = v14 + 16;
  v107 = v18;
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
    v74 = 1;
  }
  else
  {
    v74 = 0;
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
    v81,
    a5,
    &__S363__1__CommonUnwrap_RC4_4757_Kerb3961__EEAA_AU__ReturnType_UUnwrapResult_Kerb3961___1___DoubleGetter_UUnwrapResult_Kerb3961__UOwnedBinary_2__0A__0BA__2_YAAEBUResultBlock_2_AEBU12__Z_1___DoubleSetter_UUnwrapResult_Kerb3961__UOwnedBinary_2__0A__0BA__2_YAAEAU32_AEAU12__Z_3_AEBUReadOnlyBinary_3_AEBV__function___A6A_AU__ReturnType_UOwnedBinary_Kerb3961___1___SingleGetter_UOwnedBinary_Kerb3961___0BA__2_YAAEBUResultBlock_2_AEBU12__Z_1___SingleSetter_UOwnedBinary_Kerb3961___0BA__2_YAAEAU32_AEAU12__Z_Kerb3961__AEBUReadOnlyBinary_2__Z_utl__0_N2_Z_4U53_B);
  v20 = (int)v83;
  if ( (int)v83 >= 0 )
  {
    Kerb3961::RC4_4757::HmacData(
      a1,
      &v75,
      a5,
      &__S364__1__CommonUnwrap_RC4_4757_Kerb3961__EEAA_AU__ReturnType_UUnwrapResult_Kerb3961___1___DoubleGetter_UUnwrapResult_Kerb3961__UOwnedBinary_2__0A__0BA__2_YAAEBUResultBlock_2_AEBU12__Z_1___DoubleSetter_UUnwrapResult_Kerb3961__UOwnedBinary_2__0A__0BA__2_YAAEAU32_AEAU12__Z_3_AEBUReadOnlyBinary_3_AEBV__function___A6A_AU__ReturnType_UOwnedBinary_Kerb3961___1___SingleGetter_UOwnedBinary_Kerb3961___0BA__2_YAAEBUResultBlock_2_AEBU12__Z_1___SingleSetter_UOwnedBinary_Kerb3961___0BA__2_YAAEAU32_AEAU12__Z_Kerb3961__AEBUReadOnlyBinary_2__Z_utl__0_N2_Z_4U53_B);
    v22 = (int)v77;
    if ( (int)v77 < 0 )
      goto LABEL_19;
    v24 = Kerb3961::RC4_4757::HmacData(a1, &v94, &v75, &v87);
    if ( v76 )
      Kerb3961Free(v76);
    v75 = *(_QWORD *)v24;
    v25 = *(_QWORD *)(v24 + 8);
    *(_QWORD *)v24 = 0;
    v76 = v25;
    v26 = *(_DWORD *)(v24 + 16);
    *(_QWORD *)(v24 + 8) = 0;
    LODWORD(v77) = v26;
    *(_DWORD *)(v24 + 16) = -1073741823;
    if ( v95 )
      Kerb3961Free(v95);
    v22 = (int)v77;
    if ( (int)v77 < 0 )
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
      if ( v76 )
        Kerb3961Free(v76);
      goto LABEL_132;
    }
    v22 = *(_DWORD *)Kerb3961::RC4_4757::RC4Data(a1, &v93, &v75, &v84);
    if ( v22 < 0 )
    {
      v23 = "RC4Data(Kseq, sequenceBuffer)";
      goto LABEL_20;
    }
    if ( v106 != -(a6 != 0) )
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
    v93 = _byteswap_ulong(v105);
    v78 = 0;
    v79 = 0;
    v80 = -1073741823;
    if ( v74 )
    {
      Kerb3961::CopyBuffer(&v84, a5);
      v29 = (int)v86;
      if ( (int)v86 < 0 )
      {
        Kerb3961::Logging::Verify::StatusFailed(
          (Kerb3961::Logging::Verify *)"Klocal",
          (const char *)(unsigned int)v86,
          v28);
        *(_QWORD *)(a2 + 20) = 0;
        *(_QWORD *)(a2 + 28) = 0;
        *(_DWORD *)(a2 + 36) = 0;
        v30 = v85;
        *(_QWORD *)a2 = 0;
        *(_QWORD *)(a2 + 8) = 0;
        *(_DWORD *)(a2 + 16) = v29;
        goto LABEL_32;
      }
      v32 = 0;
      for ( i = v85; v32 < v84; ++v32 )
        *((_BYTE *)i + v32) ^= 0xF0u;
      Kerb3961::RC4_4757::HmacData(
        a1,
        &v87,
        &v84,
        &__S364__1__CommonUnwrap_RC4_4757_Kerb3961__EEAA_AU__ReturnType_UUnwrapResult_Kerb3961___1___DoubleGetter_UUnwrapResult_Kerb3961__UOwnedBinary_2__0A__0BA__2_YAAEBUResultBlock_2_AEBU12__Z_1___DoubleSetter_UUnwrapResult_Kerb3961__UOwnedBinary_2__0A__0BA__2_YAAEAU32_AEAU12__Z_3_AEBUReadOnlyBinary_3_AEBV__function___A6A_AU__ReturnType_UOwnedBinary_Kerb3961___1___SingleGetter_UOwnedBinary_Kerb3961___0BA__2_YAAEBUResultBlock_2_AEBU12__Z_1___SingleSetter_UOwnedBinary_Kerb3961___0BA__2_YAAEAU32_AEAU12__Z_Kerb3961__AEBUReadOnlyBinary_2__Z_utl__0_N2_Z_4U53_B);
      v35 = (unsigned int)v89;
      if ( (int)v89 < 0 )
        goto LABEL_39;
      v84 = 4;
      v85 = &v105;
      v36 = Kerb3961::RC4_4757::HmacData(a1, v108, &v87, &v84);
      if ( v88 )
        Kerb3961Free(v88);
      v87 = *(_QWORD *)v36;
      v37 = *(__int128 **)(v36 + 8);
      *(_QWORD *)v36 = 0;
      v88 = v37;
      v38 = *(_DWORD *)(v36 + 16);
      *(_QWORD *)(v36 + 8) = 0;
      LODWORD(v89) = v38;
      *(_DWORD *)(v36 + 16) = -1073741823;
      if ( v109 )
        Kerb3961Free(v109);
      v35 = (unsigned int)v89;
      if ( (int)v89 < 0 )
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
        if ( v88 )
          Kerb3961Free(v88);
        if ( !i )
        {
LABEL_34:
          v31 = v79;
          if ( !v79 )
            goto LABEL_130;
          goto LABEL_35;
        }
        v30 = i;
LABEL_33:
        Kerb3961Free(v30);
        goto LABEL_34;
      }
      Kerb3961::Concatenate(&v84, &v90, v100);
      v40 = (int)v86;
      if ( (int)v86 < 0 )
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
        if ( v85 )
          Kerb3961Free(v85);
        goto LABEL_40;
      }
      v40 = *(_DWORD *)Kerb3961::RC4_4757::RC4Data(a1, v110, &v87, &v84);
      if ( v40 < 0 )
      {
        v41 = "RC4Data(Kcrypt, tmp)";
        goto LABEL_51;
      }
      v91 = (unsigned int *)v100[0];
      v90 = 8;
      Kerb3961::Split<2>(&v116, &v84, &v90);
      if ( !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a4 + 32LL))(a4) )
        __int2c();
      (*(void (__fastcall **)(__int64, __int64 *, _QWORD *))(*(_QWORD *)a4 + 24LL))(a4, &v94, v117);
      v43 = (unsigned int)v96;
      if ( (int)v96 < 0 )
      {
        v44 = "authData";
        goto LABEL_60;
      }
      v46 = &v94;
      v112 = 8;
      if ( !v95 )
        v46 = v117;
      v111 = __S365__1__CommonUnwrap_RC4_4757_Kerb3961__EEAA_AU__ReturnType_UUnwrapResult_Kerb3961___1___DoubleGetter_UUnwrapResult_Kerb3961__UOwnedBinary_2__0A__0BA__2_YAAEBUResultBlock_2_AEBU12__Z_1___DoubleSetter_UUnwrapResult_Kerb3961__UOwnedBinary_2__0A__0BA__2_YAAEAU32_AEAU12__Z_3_AEBUReadOnlyBinary_3_AEBV__function___A6A_AU__ReturnType_UOwnedBinary_Kerb3961___1___SingleGetter_UOwnedBinary_Kerb3961___0BA__2_YAAEBUResultBlock_2_AEBU12__Z_1___SingleSetter_UOwnedBinary_Kerb3961___0BA__2_YAAEAU32_AEAU12__Z_Kerb3961__AEBUReadOnlyBinary_2__Z_utl__0_N2_Z_4U53_B;
      v47 = *(_OWORD *)v46;
      v113 = a3[1];
      v115 = v47;
      v114 = v116;
      Kerb3961::Concatenate<4>(&v90, &v111);
      if ( v79 )
        Kerb3961Free(v79);
      v43 = (unsigned int)v92;
      v78 = v90;
      v79 = (char *)v91;
      v80 = (int)v92;
      if ( (int)v92 < 0 )
      {
        v44 = "checksummedData";
LABEL_60:
        Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)v44, (const char *)v43, v42);
        *(_QWORD *)(a2 + 20) = 0;
        *(_QWORD *)(a2 + 28) = 0;
        *(_DWORD *)(a2 + 36) = 0;
        v45 = v95;
        *(_QWORD *)a2 = 0;
        *(_QWORD *)(a2 + 8) = 0;
        *(_DWORD *)(a2 + 16) = v43;
        if ( v45 )
          Kerb3961Free(v45);
        goto LABEL_52;
      }
      v48 = Kerb3961::CopyBuffer(v108, v117);
      v50 = *(_QWORD *)v48;
      v51 = *(char **)(v48 + 8);
      v52 = *(_DWORD *)(v48 + 16);
      *(_QWORD *)v48 = 0;
      *(_QWORD *)(v48 + 8) = 0;
      *(_DWORD *)(v48 + 16) = -1073741823;
      if ( v109 )
        Kerb3961Free(v109);
      if ( v52 < 0 )
      {
        Kerb3961::Logging::Verify::StatusFailed(
          (Kerb3961::Logging::Verify *)"outputMessage",
          (const char *)(unsigned int)v52,
          v49);
        *(_QWORD *)(a2 + 20) = 0;
        *(_QWORD *)(a2 + 28) = 0;
        *(_DWORD *)(a2 + 36) = 0;
        v53 = v95;
        *(_QWORD *)a2 = 0;
        *(_QWORD *)(a2 + 8) = 0;
        *(_DWORD *)(a2 + 16) = v52;
        if ( v53 )
          Kerb3961Free(v53);
        if ( v85 )
          Kerb3961Free(v85);
        if ( v88 )
          Kerb3961Free(v88);
        if ( !i )
          goto LABEL_80;
        v54 = i;
LABEL_79:
        Kerb3961Free(v54);
LABEL_80:
        if ( v79 )
          Kerb3961Free(v79);
        if ( !v51 )
          goto LABEL_130;
        v31 = v51;
LABEL_35:
        Kerb3961Free(v31);
        goto LABEL_130;
      }
      if ( v95 )
        Kerb3961Free(v95);
      if ( v85 )
        Kerb3961Free(v85);
      if ( v88 )
        Kerb3961Free(v88);
      if ( !i )
        goto LABEL_113;
      v55 = i;
LABEL_112:
      Kerb3961Free(v55);
LABEL_113:
      Kerb3961::RC4_4757::HashData(a1, &v97, &v78);
      v65 = (unsigned int)v99;
      if ( (int)v99 < 0 )
        goto LABEL_114;
      v66 = Kerb3961::RC4_4757::HmacData(a1, v108, v81, &v97);
      if ( v98 )
        Kerb3961Free(v98);
      v97 = *(_QWORD *)v66;
      v67 = *(unsigned int **)(v66 + 8);
      *(_QWORD *)v66 = 0;
      v98 = v67;
      v68 = *(_DWORD *)(v66 + 16);
      *(_QWORD *)(v66 + 8) = 0;
      LODWORD(v99) = v68;
      *(_DWORD *)(v66 + 16) = -1073741823;
      if ( v109 )
        Kerb3961Free(v109);
      v65 = (unsigned int)v99;
      if ( (int)v99 < 0 )
      {
LABEL_114:
        Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)"Sgn_Cksum", (const char *)v65, v64);
        *(_QWORD *)(a2 + 20) = 0;
        *(_QWORD *)(a2 + 28) = 0;
        *(_DWORD *)(a2 + 36) = 0;
        *(_QWORD *)a2 = 0;
        *(_QWORD *)(a2 + 8) = 0;
        *(_DWORD *)(a2 + 16) = v65;
LABEL_115:
        v54 = v98;
LABEL_116:
        if ( !v54 )
          goto LABEL_80;
        goto LABEL_79;
      }
      v69 = 0;
      for ( j = 0; j != 8; ++j )
      {
        v71 = v108[j - 16];
        v72 = *((_BYTE *)v98 + j);
        v69 |= v72 ^ v71;
      }
      if ( v69 )
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
      v30 = v98;
      *(_QWORD *)(a2 + 24) = v93;
      *(_BYTE *)(a2 + 36) = v74;
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
    (*(void (__fastcall **)(__int64, __int64 *, _QWORD *))(*(_QWORD *)a4 + 24LL))(a4, &v90, v100);
    v58 = (unsigned int)v92;
    if ( (int)v92 >= 0 )
    {
      if ( v90 && v100[0] )
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
      v60 = v100;
      v117[0] = 8;
      if ( v90 )
        v60 = &v90;
      v117[2] = 8;
      v117[1] = a3[1];
      v116 = __S365__1__CommonUnwrap_RC4_4757_Kerb3961__EEAA_AU__ReturnType_UUnwrapResult_Kerb3961___1___DoubleGetter_UUnwrapResult_Kerb3961__UOwnedBinary_2__0A__0BA__2_YAAEBUResultBlock_2_AEBU12__Z_1___DoubleSetter_UUnwrapResult_Kerb3961__UOwnedBinary_2__0A__0BA__2_YAAEAU32_AEAU12__Z_3_AEBUReadOnlyBinary_3_AEBV__function___A6A_AU__ReturnType_UOwnedBinary_Kerb3961___1___SingleGetter_UOwnedBinary_Kerb3961___0BA__2_YAAEBUResultBlock_2_AEBU12__Z_1___SingleSetter_UOwnedBinary_Kerb3961___0BA__2_YAAEAU32_AEAU12__Z_Kerb3961__AEBUReadOnlyBinary_2__Z_utl__0_N2_Z_4U53_B;
      v117[3] = (char *)&v107 + 8;
      v118 = *(_OWORD *)v60;
      Kerb3961::Concatenate<4>(&v94, &v116);
      if ( v79 )
        Kerb3961Free(v79);
      v58 = (unsigned int)v96;
      v78 = v94;
      v79 = v95;
      v80 = (int)v96;
      if ( (int)v96 >= 0 )
      {
        v61 = Kerb3961::CopyBuffer(v108, v100);
        v50 = *(_QWORD *)v61;
        v51 = *(char **)(v61 + 8);
        v63 = *(_DWORD *)(v61 + 16);
        *(_QWORD *)v61 = 0;
        *(_QWORD *)(v61 + 8) = 0;
        *(_DWORD *)(v61 + 16) = -1073741823;
        if ( v109 )
          Kerb3961Free(v109);
        if ( v63 < 0 )
        {
          Kerb3961::Logging::Verify::StatusFailed(
            (Kerb3961::Logging::Verify *)"outputMessage",
            (const char *)(unsigned int)v63,
            v62);
          *(_QWORD *)(a2 + 20) = 0;
          *(_QWORD *)(a2 + 28) = 0;
          *(_DWORD *)(a2 + 36) = 0;
          v54 = v91;
          *(_QWORD *)a2 = 0;
          *(_QWORD *)(a2 + 8) = 0;
          *(_DWORD *)(a2 + 16) = v63;
          goto LABEL_116;
        }
        v55 = v91;
        if ( !v91 )
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
    v30 = v91;
    goto LABEL_32;
  }
  Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)"Ksign", (const char *)(unsigned int)v83, v19);
  *(_QWORD *)(a2 + 20) = 0;
  *(_QWORD *)(a2 + 28) = 0;
  *(_DWORD *)(a2 + 36) = 0;
  *(_QWORD *)a2 = 0;
  *(_QWORD *)(a2 + 8) = 0;
  *(_DWORD *)(a2 + 16) = v20;
LABEL_132:
  if ( v82 )
    Kerb3961Free(v82);
  return a2;
}

```

## disassembly

```asm
0x18000d900  mov     [rsp-8+arg_10], rbx
0x18000d905  push    rbp
0x18000d906  push    rsi
0x18000d907  push    rdi
0x18000d908  push    r12
0x18000d90a  push    r13
0x18000d90c  push    r14
0x18000d90e  push    r15
0x18000d910  lea     rbp, [rsp-0F0h]
0x18000d918  sub     rsp, 1F0h
0x18000d91f  mov     rax, cs:__security_cookie
0x18000d926  xor     rax, rsp
0x18000d929  mov     [rbp+120h+var_40], rax
0x18000d930  mov     r14, [rbp+120h+arg_20]
0x18000d937  mov     r12, rcx
0x18000d93a  add     rcx, 8
0x18000d93e  mov     r15, r9
0x18000d941  mov     r13, r8
0x18000d944  mov     rdi, rdx
0x18000d947  mov     rax, [rcx]
0x18000d94a  mov     rax, [rax+68h]
0x18000d94e  call    _guard_dispatch_icall
0x18000d953  mov     ebx, eax
0x18000d955  mov     rcx, r12
0x18000d958  mov     rax, [r12]
0x18000d95c  mov     rax, [rax+0E0h]
0x18000d963  call    _guard_dispatch_icall
0x18000d968  cmp     ebx, eax
0x18000d96a  jnz     loc_18000E2FD
0x18000d970  mov     r8, [r13+0]
0x18000d974  cmp     r8, 20h ; ' '
0x18000d978  jnb     short loc_18000D9A6
0x18000d97a  lea     rcx, aMessageLengthS; "message.length >= sizeof(WrapToken)"
0x18000d981  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000d986  xor     ebx, ebx
0x18000d988  mov     [rdi+14h], rbx
0x18000d98c  mov     [rdi+1Ch], rbx
0x18000d990  mov     [rdi+24h], ebx
0x18000d993  mov     [rdi], rbx
0x18000d996  mov     [rdi+8], rbx
0x18000d99a  mov     dword ptr [rdi+10h], 8009030Fh
0x18000d9a1  jmp     loc_18000E2CF
0x18000d9a6  mov     rcx, [r13+8]
0x18000d9aa  mov     ebx, 8
0x18000d9af  mov     [rsp+220h+var_1B0], rbx
0x18000d9b4  mov     [rbp+120h+var_198], rbx
0x18000d9b8  mov     [rbp+120h+var_180], rbx
0x18000d9bc  movzx   edx, word ptr [rcx]; char *
0x18000d9bf  mov     [rbp+120h+var_118], dx
0x18000d9c3  movzx   r10d, word ptr [rcx+2]
0x18000d9c8  mov     [rbp+120h+var_116], r10w
0x18000d9cd  movzx   r9d, word ptr [rcx+4]
0x18000d9d2  mov     [rbp+120h+var_114], r9w
0x18000d9d7  movzx   r11d, word ptr [rcx+6]
0x18000d9dc  mov     [rbp+120h+var_112], r11w
0x18000d9e1  mov     eax, [rcx+8]
0x18000d9e4  mov     [rbp+120h+var_110], eax
0x18000d9e7  mov     eax, [rcx+0Ch]
0x18000d9ea  mov     [rbp+120h+var_10C], eax
0x18000d9ed  lea     rax, [rbp+120h+var_110]
0x18000d9f1  movups  xmm0, xmmword ptr [rcx+10h]
0x18000d9f5  mov     [rsp+220h+var_1A8], rax
0x18000d9fa  lea     rax, [rbp+120h+var_108]
0x18000d9fe  mov     [rbp+120h+var_190], rax
0x18000da02  lea     rax, [rbp+120h+var_108+8]
0x18000da06  mov     [rbp+120h+var_178], rax
0x18000da0a  lea     rax, [r8-20h]
0x18000da0e  mov     [rbp+120h+var_128], rax
0x18000da12  lea     rax, [rcx+20h]
0x18000da16  mov     [rbp+120h+var_120], rax
0x18000da1a  mov     eax, 102h
0x18000da1f  movdqu  [rbp+120h+var_108], xmm0
0x18000da24  cmp     dx, ax
0x18000da27  jz      short loc_18000DA35
0x18000da29  lea     rcx, aHeaderTokIdHea; "header.TOK_ID == header.ID"
0x18000da30  jmp     loc_18000D981
0x18000da35  cmp     r10w, 11h
0x18000da3a  jz      short loc_18000DA48
0x18000da3c  lea     rcx, aHeaderSgnAlgHe; "header.SGN_ALG == header.SignAlgorithm"
0x18000da43  jmp     loc_18000D981
0x18000da48  mov     eax, 0FFFFh
0x18000da4d  cmp     r11w, ax
0x18000da51  jz      short loc_18000DA5F
0x18000da53  lea     rcx, aHeaderFillerHe; "header.Filler == header.FillerBytes"
0x18000da5a  jmp     loc_18000D981
0x18000da5f  xor     ebx, ebx
0x18000da61  cmp     r9w, 10h
0x18000da66  jnz     short loc_18000DAB4
0x18000da68  mov     [rsp+220h+var_200], 1
0x18000da6d  lea     r9, ?$S363@?1??CommonUnwrap@RC4_4757@Kerb3961@@EEAA?AU?$ReturnType@UUnwrapResult@Kerb3961@@$1??$DoubleGetter@UUnwrapResult@Kerb3961@@UOwnedBinary@2@$0A@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$DoubleSetter@UUnwrapResult@Kerb3961@@UOwnedBinary@2@$0A@$0BA@@2@YAAEAU32@AEAU12@@Z@3@AEBUReadOnlyBinary@3@AEBV?$function@$$A6A?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@Kerb3961@@AEBUReadOnlyBinary@2@@Z@utl@@0_N2@Z@4U53@B
0x18000da74  mov     r8, r14
0x18000da77  lea     rdx, [rsp+220h+var_1C8]
0x18000da7c  mov     rcx, r12
0x18000da7f  call    ?HmacData@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0@Z; Kerb3961::RC4_4757::HmacData(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x18000da84  mov     esi, dword ptr [rsp+220h+var_1B8]
0x18000da88  test    esi, esi
0x18000da8a  jns     short loc_18000DACF
0x18000da8c  mov     edx, esi; char *
0x18000da8e  lea     rcx, aKsign; "Ksign"
0x18000da95  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000da9a  mov     [rdi+14h], rbx
0x18000da9e  mov     [rdi+1Ch], rbx
0x18000daa2  mov     [rdi+24h], ebx
0x18000daa5  mov     [rdi], rbx
0x18000daa8  mov     [rdi+8], rbx
0x18000daac  mov     [rdi+10h], esi
0x18000daaf  jmp     loc_18000E2C0
0x18000dab4  mov     [rsp+220h+var_200], bl
0x18000dab8  cmp     r9w, ax
0x18000dabc  jz      short loc_18000DA6D
0x18000dabe  lea     rcx, aEncryptedHeade; "encrypted || header.SEAL_ALG == header."...
0x18000dac5  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000daca  jmp     loc_18000D988
0x18000dacf  lea     r9, ?$S364@?1??CommonUnwrap@RC4_4757@Kerb3961@@EEAA?AU?$ReturnType@UUnwrapResult@Kerb3961@@$1??$DoubleGetter@UUnwrapResult@Kerb3961@@UOwnedBinary@2@$0A@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$DoubleSetter@UUnwrapResult@Kerb3961@@UOwnedBinary@2@$0A@$0BA@@2@YAAEAU32@AEAU12@@Z@3@AEBUReadOnlyBinary@3@AEBV?$function@$$A6A?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@Kerb3961@@AEBUReadOnlyBinary@2@@Z@utl@@0_N2@Z@4U53@B
0x18000dad6  mov     r8, r14
0x18000dad9  lea     rdx, [rsp+220h+var_1F8]
0x18000dade  mov     rcx, r12
0x18000dae1  call    ?HmacData@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0@Z; Kerb3961::RC4_4757::HmacData(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x18000dae6  mov     esi, dword ptr [rsp+220h+var_1E8]
0x18000daea  test    esi, esi
0x18000daec  jns     short loc_18000DB0F
0x18000daee  lea     rcx, aKseq; "Kseq"
0x18000daf5  mov     edx, esi; char *
0x18000daf7  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000dafc  mov     [rdi+14h], rbx
0x18000db00  mov     [rdi+1Ch], rbx
0x18000db04  mov     [rdi+24h], ebx
0x18000db07  mov     [rdi+10h], esi
0x18000db0a  jmp     loc_18000E2AA
0x18000db0f  lea     r9, [rbp+120h+var_198]
0x18000db13  mov     rcx, r12
0x18000db16  lea     r8, [rsp+220h+var_1F8]
0x18000db1b  lea     rdx, [rbp+120h+var_158]
0x18000db1f  call    ?HmacData@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0@Z; Kerb3961::RC4_4757::HmacData(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x18000db24  mov     rcx, [rsp+220h+var_1F0]
0x18000db29  mov     rsi, rax
0x18000db2c  test    rcx, rcx
0x18000db2f  jz      short loc_18000DB36
0x18000db31  call    Kerb3961Free
0x18000db36  mov     rcx, [rsi]
0x18000db39  mov     [rsp+220h+var_1F8], rcx
0x18000db3e  mov     rcx, [rsi+8]
0x18000db42  mov     [rsi], rbx
0x18000db45  mov     [rsp+220h+var_1F0], rcx
0x18000db4a  mov     eax, [rsi+10h]
0x18000db4d  mov     [rsi+8], rbx
0x18000db51  mov     dword ptr [rsp+220h+var_1E8], eax
0x18000db55  mov     dword ptr [rsi+10h], 0C0000001h
0x18000db5c  mov     rcx, [rbp+120h+var_150]
0x18000db60  test    rcx, rcx
0x18000db63  jz      short loc_18000DB6A
0x18000db65  call    Kerb3961Free
0x18000db6a  mov     esi, dword ptr [rsp+220h+var_1E8]
0x18000db6e  test    esi, esi
0x18000db70  js      loc_18000DAEE
0x18000db76  lea     r9, [rsp+220h+var_1B0]
0x18000db7b  mov     rcx, r12
0x18000db7e  lea     r8, [rsp+220h+var_1F8]
0x18000db83  lea     rdx, [rbp+120h+var_160]
0x18000db87  call    ?RC4Data@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UStatusOnly@Kerb3961@@$1??$SingleGetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@AEBUMutableBinary@2@@Z; Kerb3961::RC4_4757::RC4Data(Kerb3961::ReadOnlyBinary const &,Kerb3961::MutableBinary const &)
0x18000db8c  mov     esi, [rax]
0x18000db8e  test    esi, esi
0x18000db90  jns     short loc_18000DB9E
0x18000db92  lea     rcx, aRc4dataKseqSeq; "RC4Data(Kseq, sequenceBuffer)"
0x18000db99  jmp     loc_18000DAF5
0x18000db9e  neg     [rbp+120h+arg_28]
0x18000dba4  sbb     eax, eax
0x18000dba6  cmp     [rbp+120h+var_10C], eax
0x18000dba9  jnz     loc_18000E28C
0x18000dbaf  mov     eax, [rbp+120h+var_110]
0x18000dbb2  bswap   eax
0x18000dbb4  mov     [rbp+120h+var_160], eax
0x18000dbb7  mov     [rsp+220h+var_1E0], rbx
0x18000dbbc  mov     [rsp+220h+var_1D8], rbx
0x18000dbc1  mov     [rsp+220h+var_1D0], 0C0000001h
0x18000dbc9  cmp     [rsp+220h+var_200], bl
0x18000dbcd  jz      loc_18000DFC6
0x18000dbd3  mov     rdx, r14
0x18000dbd6  lea     rcx, [rsp+220h+var_1B0]
0x18000dbdb  call    ?CopyBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyBinary@1@@Z; Kerb3961::CopyBuffer(Kerb3961::ReadOnlyBinary const &)
0x18000dbe0  mov     esi, dword ptr [rbp+120h+var_1A0]
0x18000dbe3  test    esi, esi
0x18000dbe5  jns     short loc_18000DC31
0x18000dbe7  mov     edx, esi; char *
0x18000dbe9  lea     rcx, aKlocal; "Klocal"
0x18000dbf0  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000dbf5  mov     [rdi+14h], rbx
0x18000dbf9  mov     [rdi+1Ch], rbx
0x18000dbfd  mov     [rdi+24h], ebx
0x18000dc00  mov     rcx, [rsp+220h+var_1A8]
0x18000dc05  mov     [rdi], rbx
0x18000dc08  mov     [rdi+8], rbx
0x18000dc0c  mov     [rdi+10h], esi
0x18000dc0f  test    rcx, rcx
0x18000dc12  jz      short loc_18000DC19
0x18000dc14  call    Kerb3961Free
0x18000dc19  mov     rcx, [rsp+220h+var_1D8]
0x18000dc1e  test    rcx, rcx
0x18000dc21  jz      loc_18000E2B1
0x18000dc27  call    Kerb3961Free
0x18000dc2c  jmp     loc_18000E2B1
0x18000dc31  mov     rax, rbx
0x18000dc34  mov     rsi, [rsp+220h+var_1A8]
0x18000dc39  cmp     [rsp+220h+var_1B0], rbx
0x18000dc3e  jbe     short loc_18000DC4E
0x18000dc40  xor     byte ptr [rsi+rax], 0F0h
0x18000dc44  inc     rax
0x18000dc47  cmp     rax, [rsp+220h+var_1B0]
0x18000dc4c  jb      short loc_18000DC40
0x18000dc4e  lea     r9, ?$S364@?1??CommonUnwrap@RC4_4757@Kerb3961@@EEAA?AU?$ReturnType@UUnwrapResult@Kerb3961@@$1??$DoubleGetter@UUnwrapResult@Kerb3961@@UOwnedBinary@2@$0A@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$DoubleSetter@UUnwrapResult@Kerb3961@@UOwnedBinary@2@$0A@$0BA@@2@YAAEAU32@AEAU12@@Z@3@AEBUReadOnlyBinary@3@AEBV?$function@$$A6A?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@Kerb3961@@AEBUReadOnlyBinary@2@@Z@utl@@0_N2@Z@4U53@B
0x18000dc55  mov     rcx, r12
0x18000dc58  lea     r8, [rsp+220h+var_1B0]
0x18000dc5d  lea     rdx, [rbp+120h+var_198]
0x18000dc61  call    ?HmacData@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0@Z; Kerb3961::RC4_4757::HmacData(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x18000dc66  mov     r14d, dword ptr [rbp+120h+var_188]
0x18000dc6a  test    r14d, r14d
0x18000dc6d  jns     short loc_18000DCB3
0x18000dc6f  mov     edx, r14d; char *
0x18000dc72  lea     rcx, aKcrypt; "Kcrypt"
0x18000dc79  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000dc7e  mov     [rdi+14h], rbx
0x18000dc82  mov     [rdi+1Ch], rbx
0x18000dc86  mov     [rdi+24h], ebx
0x18000dc89  mov     [rdi], rbx
0x18000dc8c  mov     [rdi+10h], r14d
0x18000dc90  mov     [rdi+8], rbx
0x18000dc94  mov     rcx, [rbp+120h+var_190]
0x18000dc98  test    rcx, rcx
0x18000dc9b  jz      short loc_18000DCA2
0x18000dc9d  call    Kerb3961Free
0x18000dca2  test    rsi, rsi
0x18000dca5  jz      loc_18000DC19
0x18000dcab  mov     rcx, rsi
0x18000dcae  jmp     loc_18000DC14
0x18000dcb3  lea     rax, [rbp+120h+var_110]
0x18000dcb7  mov     [rsp+220h+var_1B0], 4
0x18000dcc0  lea     r9, [rsp+220h+var_1B0]
0x18000dcc5  mov     [rsp+220h+var_1A8], rax
0x18000dcca  lea     r8, [rbp+120h+var_198]
0x18000dcce  mov     rcx, r12
0x18000dcd1  lea     rdx, [rbp+120h+var_F8]
0x18000dcd5  call    ?HmacData@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0@Z; Kerb3961::RC4_4757::HmacData(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x18000dcda  mov     rcx, [rbp+120h+var_190]
0x18000dcde  mov     r14, rax
0x18000dce1  test    rcx, rcx
0x18000dce4  jz      short loc_18000DCEB
0x18000dce6  call    Kerb3961Free
0x18000dceb  mov     rcx, [r14]
0x18000dcee  mov     [rbp+120h+var_198], rcx
0x18000dcf2  mov     rcx, [r14+8]
0x18000dcf6  mov     [r14], rbx
0x18000dcf9  mov     [rbp+120h+var_190], rcx
0x18000dcfd  mov     eax, [r14+10h]
0x18000dd01  mov     [r14+8], rbx
0x18000dd05  mov     dword ptr [rbp+120h+var_188], eax
0x18000dd08  mov     dword ptr [r14+10h], 0C0000001h
0x18000dd10  mov     rcx, [rbp+120h+var_F0]
0x18000dd14  test    rcx, rcx
0x18000dd17  jz      short loc_18000DD1E
0x18000dd19  call    Kerb3961Free
0x18000dd1e  mov     r14d, dword ptr [rbp+120h+var_188]
0x18000dd22  test    r14d, r14d
0x18000dd25  js      loc_18000DC6F
0x18000dd2b  lea     r8, [rbp+120h+var_128]
0x18000dd2f  lea     rdx, [rbp+120h+var_180]
0x18000dd33  lea     rcx, [rsp+220h+var_1B0]
0x18000dd38  call    ?Concatenate@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyBinary@1@0@Z; Kerb3961::Concatenate(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)
0x18000dd3d  mov     r14d, dword ptr [rbp+120h+var_1A0]
0x18000dd41  test    r14d, r14d
0x18000dd44  jns     short loc_18000DD83
0x18000dd46  lea     rcx, aTmp; "tmp"
0x18000dd4d  mov     edx, r14d; char *
0x18000dd50  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000dd55  mov     [rdi+14h], rbx
0x18000dd59  mov     [rdi+1Ch], rbx
0x18000dd5d  mov     [rdi+24h], ebx
0x18000dd60  mov     [rdi], rbx
0x18000dd63  mov     [rdi+8], rbx
0x18000dd67  mov     [rdi+10h], r14d
0x18000dd6b  mov     rcx, [rsp+220h+var_1A8]
0x18000dd70  test    rcx, rcx
0x18000dd73  jz      loc_18000DC94
0x18000dd79  call    Kerb3961Free
0x18000dd7e  jmp     loc_18000DC94
0x18000dd83  lea     r9, [rsp+220h+var_1B0]
0x18000dd88  mov     rcx, r12
0x18000dd8b  lea     r8, [rbp+120h+var_198]
0x18000dd8f  lea     rdx, [rbp+120h+var_E0]
0x18000dd93  call    ?RC4Data@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UStatusOnly@Kerb3961@@$1??$SingleGetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@AEBUMutableBinary@2@@Z; Kerb3961::RC4_4757::RC4Data(Kerb3961::ReadOnlyBinary const &,Kerb3961::MutableBinary const &)
0x18000dd98  mov     r14d, [rax]
0x18000dd9b  test    r14d, r14d
0x18000dd9e  jns     short loc_18000DDA9
0x18000dda0  lea     rcx, aRc4dataKcryptT; "RC4Data(Kcrypt, tmp)"
0x18000dda7  jmp     short loc_18000DD4D
0x18000dda9  mov     rax, [rbp+120h+var_128]
0x18000ddad  lea     r8, [rbp+120h+var_180]
0x18000ddb1  lea     rdx, [rsp+220h+var_1B0]
0x18000ddb6  mov     [rbp+120h+var_178], rax
0x18000ddba  lea     rcx, [rbp+120h+var_80]
0x18000ddc1  mov     [rbp+120h+var_180], 8
  ... truncated ...
```
