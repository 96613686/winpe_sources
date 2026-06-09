# Art::PCPath2D::InitFrom(Art::CGuideNameList const &,Art::Path2D const &)

- ea: `0x18006fd30`
- end: `0x1800702f8`
- name: `?InitFrom@PCPath2D@Art@@QEAAXAEBVCGuideNameList@2@AEBVPath2D@2@@Z`
- size: `1480`
- prototype: `void(Art::PCPath2D *__hidden this, const struct Art::CGuideNameList *, const struct Art::Path2D *)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x180043d84`

## callees

- `0x180044dc0`
- `0x180068cc0`
- `0x18006fd30`
- `0x180070300`
- `0x1800704f0`
- `0x180070580`
- `0x1800705f0`
- `0x1800f7360`
- `0x180203418`
- `0x1802036d8`
- `0x18027e59c`
- `0x18027e60c`
- `0x1802c8bdc`
- `0x1806b5b28`
- `0x1808ceba0`

## import_xrefs

- `VCRUNTIME140!__std_type_info_compare` at `0x18006ff27`
- `VCRUNTIME140!__std_type_info_compare` at `0x180070086`
- `VCRUNTIME140!__std_type_info_compare` at `0x1800700a9`
- `VCRUNTIME140!__std_type_info_compare` at `0x1800700cc`
- `VCRUNTIME140!__std_type_info_compare` at `0x1800700ef`
- `VCRUNTIME140!__std_type_info_compare` at `0x180070112`
- `VCRUNTIME140!__std_type_info_compare` at `0x18006ff27`
- `VCRUNTIME140!__std_type_info_compare` at `0x180070086`
- `VCRUNTIME140!__std_type_info_compare` at `0x1800700a9`
- `VCRUNTIME140!__std_type_info_compare` at `0x1800700cc`
- `VCRUNTIME140!__std_type_info_compare` at `0x1800700ef`
- `VCRUNTIME140!__std_type_info_compare` at `0x180070112`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18007018e`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180070244`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180070254`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18007018e`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180070244`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180070254`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18006fdf3`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18006fdf3`

## pseudocode

```c
void __fastcall Art::PCPath2D::InitFrom(
        Art::PCPath2D *this,
        const struct Art::CGuideNameList *a2,
        const struct Art::Path2D *a3)
{
  _DWORD *v6; // rsi
  unsigned int v7; // r12d
  _DWORD *v8; // rdx
  __int64 v9; // rbx
  __int64 *v10; // rcx
  __int64 v11; // rcx
  __int64 v13; // rax
  _QWORD *v14; // rbx
  double *v15; // rdi
  void ****v16; // rcx
  void ****v17; // rcx
  void ****v18; // rcx
  void ****v19; // rcx
  __int64 *v20; // rcx
  __int64 v21; // rcx
  __int64 *v23; // rcx
  __int64 v24; // rcx
  __int64 *v26; // rcx
  __int64 v27; // rcx
  __int64 *v29; // rcx
  __int64 v30; // rcx
  __int64 *v32; // rcx
  __int64 v33; // rcx
  const struct Art::Path2DCubicBezierTo *v35; // rax
  const struct Art::AdjPoint2D *v36; // rax
  const struct Art::Path2DArcTo *v37; // rax
  const struct Art::Path2DQuadBezierTo *v38; // rax

  *((_DWORD *)this + 2) = *((_DWORD *)a3 + 10);
  *((_BYTE *)this + 12) = *((_BYTE *)a3 + 44);
  *((_BYTE *)this + 13) = *((_BYTE *)a3 + 45);
  *((_QWORD *)this + 2) = *((_QWORD *)a3 + 3);
  *((_QWORD *)this + 3) = *((_QWORD *)a3 + 4);
  *((_BYTE *)this + 14) = *((_BYTE *)a3 + 56);
  v6 = 0;
  v7 = 0;
  if ( *(_DWORD *)this )
  {
    while ( 1 )
    {
      if ( v6 )
      {
        v8 = 0;
        if ( *v6 < 2u )
        {
          v8 = v6 + 6;
          goto LABEL_9;
        }
        if ( *v6 == 2 || *v6 == 3 )
        {
          v8 = v6 + 10;
          goto LABEL_9;
        }
        if ( *v6 != 4 )
        {
          if ( *v6 == 5 )
            v8 = v6 + 2;
          goto LABEL_9;
        }
        goto LABEL_13;
      }
      v6 = (_DWORD *)((char *)this + 32);
      while ( v7 >= *((_DWORD *)a3 + 4) )
      {
        CrashWithRecovery(0x1E892498u, 0);
LABEL_13:
        v8 = v6 + 14;
LABEL_9:
        v6 = v8;
        if ( (char *)v8 - (char *)this - 32 >= *((unsigned int *)this + 1) )
          v6 = 0;
      }
      v9 = *((_QWORD *)a3 + 1) + 16LL * v7;
      v10 = *(__int64 **)(v9 + 8);
      if ( (unsigned __int64)v10 <= 1
        || (v11 = *v10, (struct Art::Path2DData::LineTo **)v11 != &Ofc::TypeInfoImpl<Art::Path2DData::LineTo>::c_typeInfo)
        && (*(const int **)(v11 + 8) == &Ofc::TypeInfo::s_moduleTag
         || (unsigned int)__std_type_info_compare(*(_QWORD *)v11 + 8LL, &qword_180E1BE60)) )
      {
        v20 = *(__int64 **)(v9 + 8);
        if ( (unsigned __int64)v20 > 1
          && ((v21 = *v20,
               (struct Art::Path2DData::MoveTo **)v21 == &Ofc::TypeInfoImpl<Art::Path2DData::MoveTo>::c_typeInfo)
           || *(const int **)(v21 + 8) != &Ofc::TypeInfo::s_moduleTag
           && !(unsigned int)__std_type_info_compare(*(_QWORD *)v21 + 8LL, &qword_180E1BEC0)) )
        {
          v36 = (const struct Art::AdjPoint2D *)Ofc::TChoice<Art::Path2DData::SegmentChoiceIDsImpl>::Get<Art::Path2DData::MoveTo>(v9);
          *v6 = 0;
          Art::PCAdjPoint2D::InitFrom((Art::PCAdjPoint2D *)(v6 + 2), a2, v36);
        }
        else
        {
          v23 = *(__int64 **)(v9 + 8);
          if ( (unsigned __int64)v23 <= 1
            || (v24 = *v23,
                (struct Art::Path2DData::Close **)v24 == &Ofc::TypeInfoImpl<Art::Path2DData::Close>::c_typeInfo)
            || *(const int **)(v24 + 8) != &Ofc::TypeInfo::s_moduleTag
            && !(unsigned int)__std_type_info_compare(*(_QWORD *)v24 + 8LL, &qword_180E1BE90) )
          {
            if ( !Ofc::TChoice<Art::Path2DData::SegmentChoiceIDsImpl>::GetPtr<Art::Path2DData::Close>(v9) )
            {
LABEL_101:
              Ofc::CInvalidParamException::ThrowTag(0x66356D62u);
              __debugbreak();
            }
            *v6 = 5;
          }
          else
          {
            v26 = *(__int64 **)(v9 + 8);
            if ( (unsigned __int64)v26 > 1
              && ((v27 = *v26,
                   (struct Art::Path2DData::ArcTo **)v27 == &Ofc::TypeInfoImpl<Art::Path2DData::ArcTo>::c_typeInfo)
               || *(const int **)(v27 + 8) != &Ofc::TypeInfo::s_moduleTag
               && !(unsigned int)__std_type_info_compare(*(_QWORD *)v27 + 8LL, &qword_180E1BF28)) )
            {
              v37 = (const struct Art::Path2DArcTo *)Ofc::TChoice<Art::Path2DData::SegmentChoiceIDsImpl>::Get<Art::Path2DData::ArcTo>(v9);
              Art::PCPath2DArcTo::InitFrom((Art::PCPath2DArcTo *)v6, a2, v37);
            }
            else
            {
              v29 = *(__int64 **)(v9 + 8);
              if ( (unsigned __int64)v29 > 1
                && ((v30 = *v29,
                     (struct Art::Path2DData::QuadBezierTo **)v30 == &Ofc::TypeInfoImpl<Art::Path2DData::QuadBezierTo>::c_typeInfo)
                 || *(const int **)(v30 + 8) != &Ofc::TypeInfo::s_moduleTag
                 && !(unsigned int)__std_type_info_compare(*(_QWORD *)v30 + 8LL, &qword_180E1BEF0)) )
              {
                v38 = (const struct Art::Path2DQuadBezierTo *)Ofc::TChoice<Art::Path2DData::SegmentChoiceIDsImpl>::Get<Art::Path2DData::QuadBezierTo>(v9);
                Art::PCPath2DQuadBezierTo::InitFrom((Art::PCPath2DQuadBezierTo *)v6, a2, v38);
              }
              else
              {
                v32 = *(__int64 **)(v9 + 8);
                if ( (unsigned __int64)v32 > 1 )
                {
                  v33 = *v32;
                  if ( (struct Art::Path2DData::CubicBezierTo **)v33 == &Ofc::TypeInfoImpl<Art::Path2DData::CubicBezierTo>::c_typeInfo
                    || *(const int **)(v33 + 8) != &Ofc::TypeInfo::s_moduleTag
                    && !(unsigned int)__std_type_info_compare(*(_QWORD *)v33 + 8LL, &qword_180E1BE28) )
                  {
                    v35 = (const struct Art::Path2DCubicBezierTo *)Ofc::TChoice<Art::Path2DData::SegmentChoiceIDsImpl>::GetPtr<Art::Path2DData::CubicBezierTo>(v9);
                    if ( !v35 )
                      goto LABEL_101;
                    Art::PCPath2DCubicBezierTo::InitFrom((Art::PCPath2DCubicBezierTo *)v6, a2, v35);
                  }
                }
              }
            }
          }
        }
        goto LABEL_31;
      }
      v13 = Ofc::TChoice<Art::Path2DData::SegmentChoiceIDsImpl>::GetPtr<Art::Path2DData::LineTo>(v9);
      v14 = (_QWORD *)v13;
      if ( !v13 )
        goto LABEL_101;
      *v6 = 1;
      v15 = (double *)(v6 + 2);
      v16 = *(void *****)(v13 + 8);
      if ( !v16 )
        break;
      if ( v16 != &off_180A850B0
        && (v16[6] == (void ***)&Ofc::TypeInfo::s_moduleTag
         || !(unsigned __int8)Ofc::TypeInfo::operator==(
                                *v16,
                                &Ofc::TypeInfoImpl<Art::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>>>::c_typeInfo)) )
      {
        goto LABEL_76;
      }
      v17 = (void ****)v14[1];
      if ( !v17 )
        goto LABEL_79;
      if ( v17 != &off_180A850B0
        && (v17[6] == (void ***)&Ofc::TypeInfo::s_moduleTag
         || !(unsigned __int8)Ofc::TypeInfo::operator==(
                                *v17,
                                &Ofc::TypeInfoImpl<Art::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>>>::c_typeInfo)) )
      {
        goto LABEL_80;
      }
      *v15 = (double)(int)*v14;
LABEL_26:
      v18 = (void ****)v14[3];
      if ( !v18 )
      {
        MsoShipAssertTagProc(895891042);
LABEL_82:
        if ( !(unsigned __int8)Ofc::TVariant<Art::AdjCoordDataIDsImpl>::Is<Art::GeomGuideName>(v14 + 2) )
          goto LABEL_80;
        Art::PCGeomGuideName::InitFrom(
          (Art::PCGeomGuideName *)(v6 + 4),
          a2,
          (const struct Art::GeomGuideName *)(v14 + 2));
        v6[5] = -1;
        if ( v6[4] == 0x7FFFFFFF )
          *((_QWORD *)v6 + 2) = 0;
        goto LABEL_31;
      }
      if ( v18 != &off_180A850B0
        && (v18[6] == (void ***)&Ofc::TypeInfo::s_moduleTag
         || !(unsigned __int8)Ofc::TypeInfo::operator==(
                                *v18,
                                &Ofc::TypeInfoImpl<Art::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>>>::c_typeInfo)) )
      {
        goto LABEL_82;
      }
      v19 = (void ****)v14[3];
      if ( !v19 )
      {
LABEL_79:
        MsoShipAssertTagProc(895891042);
LABEL_80:
        Ofc::CInvalidParamException::ThrowTag(0x65747234u);
        __debugbreak();
      }
      if ( v19 != &off_180A850B0
        && (v19[6] == (void ***)&Ofc::TypeInfo::s_moduleTag
         || !(unsigned __int8)Ofc::TypeInfo::operator==(
                                *v19,
                                &Ofc::TypeInfoImpl<Art::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>>>::c_typeInfo)) )
      {
        goto LABEL_80;
      }
      *((double *)v6 + 2) = (double)(int)v14[2];
LABEL_31:
      if ( ++v7 >= *(_DWORD *)this )
        return;
    }
    MsoShipAssertTagProc(895891042);
LABEL_76:
    if ( !(unsigned __int8)Ofc::TVariant<Art::AdjCoordDataIDsImpl>::Is<Art::GeomGuideName>(v14) )
      goto LABEL_80;
    Art::PCGeomGuideName::InitFrom((Art::PCGeomGuideName *)(v6 + 2), a2, (const struct Art::GeomGuideName *)v14);
    v6[3] = -1;
    if ( *(_DWORD *)v15 == 0x7FFFFFFF )
      *v15 = 0.0;
    goto LABEL_26;
  }
}

```

## disassembly

```asm
0x18006fd30  mov     [rsp+arg_0], rbx
0x18006fd35  mov     [rsp+arg_8], rbp
0x18006fd3a  mov     [rsp+arg_10], rsi
0x18006fd3f  push    rdi
0x18006fd40  push    r12
0x18006fd42  push    r13
0x18006fd44  push    r14
0x18006fd46  push    r15
0x18006fd48  sub     rsp, 20h
0x18006fd4c  mov     r15, r8
0x18006fd4f  mov     r13, rdx
0x18006fd52  mov     r14, rcx
0x18006fd55  mov     eax, [r8+28h]
0x18006fd59  mov     [rcx+8], eax
0x18006fd5c  mov     al, [r8+2Ch]
0x18006fd60  mov     [rcx+0Ch], al
0x18006fd63  mov     al, [r8+2Dh]
0x18006fd67  mov     [rcx+0Dh], al
0x18006fd6a  mov     rax, [r8+18h]
0x18006fd6e  mov     [rcx+10h], rax
0x18006fd72  mov     rax, [r8+20h]
0x18006fd76  mov     [rcx+18h], rax
0x18006fd7a  mov     al, [r8+38h]
0x18006fd7e  mov     [rcx+0Eh], al
0x18006fd81  xor     ebp, ebp
0x18006fd83  mov     esi, ebp
0x18006fd85  mov     r12d, ebp
0x18006fd88  cmp     [rcx], ebp
0x18006fd8a  jbe     loc_18006FEFC
0x18006fd90  lea     rdi, ?s_moduleTag@TypeInfo@Ofc@@2HB; int const Ofc::TypeInfo::s_moduleTag
0x18006fd97  test    rsi, rsi
0x18006fd9a  jz      short loc_18006FE00
0x18006fd9c  mov     rdx, rbp
0x18006fd9f  mov     ecx, [rsi]
0x18006fda1  test    ecx, ecx
0x18006fda3  jz      loc_1800702C9
0x18006fda9  sub     ecx, 1
0x18006fdac  jz      loc_1800702C9
0x18006fdb2  sub     ecx, 1
0x18006fdb5  jz      loc_1800702C0
0x18006fdbb  sub     ecx, 1
0x18006fdbe  jz      loc_1800702C0
0x18006fdc4  sub     ecx, 1
0x18006fdc7  jz      short loc_18006FDFA
0x18006fdc9  cmp     ecx, 1
0x18006fdcc  jz      short loc_18006FE06
0x18006fdce  mov     rcx, rdx
0x18006fdd1  sub     rcx, r14
0x18006fdd4  sub     rcx, 20h ; ' '
0x18006fdd8  mov     eax, [r14+4]
0x18006fddc  mov     rsi, rdx
0x18006fddf  cmp     rcx, rax
0x18006fde2  cmovge  rsi, rbp
0x18006fde6  cmp     r12d, [r15+10h]
0x18006fdea  jb      short loc_18006FE0C
0x18006fdec  xor     edx, edx
0x18006fdee  mov     ecx, 1E892498h
0x18006fdf3  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x18006fdf9  nop
0x18006fdfa  lea     rdx, [rsi+38h]
0x18006fdfe  jmp     short loc_18006FDCE
0x18006fe00  lea     rsi, [r14+20h]
0x18006fe04  jmp     short loc_18006FDE6
0x18006fe06  lea     rdx, [rsi+8]
0x18006fe0a  jmp     short loc_18006FDCE
0x18006fe0c  mov     ebx, r12d
0x18006fe0f  shl     rbx, 4
0x18006fe13  add     rbx, [r15+8]
0x18006fe17  mov     rcx, [rbx+8]
0x18006fe1b  cmp     rcx, 1
0x18006fe1f  jbe     short loc_18006FE3E
0x18006fe21  mov     rcx, [rcx]
0x18006fe24  lea     rax, ?c_typeInfo@?$TypeInfoImpl@ULineTo@Path2DData@Art@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Art::Path2DData::LineTo>::c_typeInfo
0x18006fe2b  cmp     rcx, rax
0x18006fe2e  jz      loc_18006FF35
0x18006fe34  cmp     [rcx+8], rdi
0x18006fe38  jnz     loc_18006FF19
0x18006fe3e  mov     al, bpl
0x18006fe41  test    al, al
0x18006fe43  jz      loc_18006FF3C
0x18006fe49  mov     rcx, rbx
0x18006fe4c  call    ??$GetPtr@ULineTo@Path2DData@Art@@@?$TChoice@VSegmentChoiceIDsImpl@Path2DData@Art@@@Ofc@@QEAAPEAVPath2DLineTo@Art@@XZ; Ofc::TChoice<Art::Path2DData::SegmentChoiceIDsImpl>::GetPtr<Art::Path2DData::LineTo>(void)
0x18006fe51  mov     rbx, rax
0x18006fe54  test    rax, rax
0x18006fe57  jz      loc_1800702ED
0x18006fe5d  mov     dword ptr [rsi], 1
0x18006fe63  lea     rdi, [rsi+8]
0x18006fe67  mov     rcx, [rax+8]
0x18006fe6b  test    rcx, rcx
0x18006fe6e  jz      loc_18007023F
0x18006fe74  lea     rax, off_180A850B0
0x18006fe7b  cmp     rcx, rax
0x18006fe7e  jnz     loc_180070143
0x18006fe84  mov     rcx, [rbx+8]
0x18006fe88  test    rcx, rcx
0x18006fe8b  jz      loc_180070189
0x18006fe91  cmp     rcx, rax
0x18006fe94  jnz     loc_1800701EC
0x18006fe9a  xorps   xmm0, xmm0
0x18006fe9d  cvtsi2sd xmm0, qword ptr [rbx]
0x18006fea2  movsd   qword ptr [rdi], xmm0
0x18006fea6  mov     rcx, [rbx+18h]
0x18006feaa  test    rcx, rcx
0x18006fead  jz      loc_18007024F
0x18006feb3  lea     rax, off_180A850B0
0x18006feba  cmp     rcx, rax
0x18006febd  jnz     loc_18007019F
0x18006fec3  mov     rcx, [rbx+18h]
0x18006fec7  xor     ebp, ebp
0x18006fec9  test    rcx, rcx
0x18006fecc  jz      loc_180070189
0x18006fed2  cmp     rcx, rax
0x18006fed5  jnz     loc_180070212
0x18006fedb  xorps   xmm0, xmm0
0x18006fede  cvtsi2sd xmm0, qword ptr [rbx+10h]
0x18006fee4  movsd   qword ptr [rdi+8], xmm0
0x18006fee9  lea     rdi, ?s_moduleTag@TypeInfo@Ofc@@2HB; int const Ofc::TypeInfo::s_moduleTag
0x18006fef0  inc     r12d
0x18006fef3  cmp     r12d, [r14]
0x18006fef6  jb      loc_18006FD97
0x18006fefc  mov     rbx, [rsp+48h+arg_0]
0x18006ff01  mov     rbp, [rsp+48h+arg_8]
0x18006ff06  mov     rsi, [rsp+48h+arg_10]
0x18006ff0b  add     rsp, 20h
0x18006ff0f  pop     r15
0x18006ff11  pop     r14
0x18006ff13  pop     r13
0x18006ff15  pop     r12
0x18006ff17  pop     rdi
0x18006ff18  retn
0x18006ff19  mov     rcx, [rcx]
0x18006ff1c  add     rcx, 8
0x18006ff20  lea     rdx, qword_180E1BE60
0x18006ff27  call    cs:__imp___std_type_info_compare
0x18006ff2d  test    eax, eax
0x18006ff2f  jnz     loc_18006FE3E
0x18006ff35  mov     al, 1
0x18006ff37  jmp     loc_18006FE41
0x18006ff3c  mov     rcx, [rbx+8]
0x18006ff40  cmp     rcx, 1
0x18006ff44  jbe     short loc_18006FF63
0x18006ff46  mov     rcx, [rcx]
0x18006ff49  lea     rax, ?c_typeInfo@?$TypeInfoImpl@UMoveTo@Path2DData@Art@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Art::Path2DData::MoveTo>::c_typeInfo
0x18006ff50  cmp     rcx, rax
0x18006ff53  jz      loc_1800700DA
0x18006ff59  cmp     [rcx+8], rdi
0x18006ff5d  jnz     loc_1800700BE
0x18006ff63  mov     al, bpl
0x18006ff66  test    al, al
0x18006ff68  jnz     loc_18007005A
0x18006ff6e  mov     rcx, [rbx+8]
0x18006ff72  cmp     rcx, 1
0x18006ff76  jbe     loc_1800700FD
0x18006ff7c  mov     rcx, [rcx]
0x18006ff7f  lea     rax, ?c_typeInfo@?$TypeInfoImpl@UClose@Path2DData@Art@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Art::Path2DData::Close>::c_typeInfo
0x18006ff86  cmp     rcx, rax
0x18006ff89  jz      loc_1800700FD
0x18006ff8f  cmp     [rcx+8], rdi
0x18006ff93  jnz     loc_1800700E1
0x18006ff99  mov     al, bpl
0x18006ff9c  test    al, al
0x18006ff9e  jnz     loc_180070127
0x18006ffa4  mov     rcx, [rbx+8]
0x18006ffa8  cmp     rcx, 1
0x18006ffac  jbe     short loc_18006FFCB
0x18006ffae  mov     rcx, [rcx]
0x18006ffb1  lea     rax, ?c_typeInfo@?$TypeInfoImpl@UArcTo@Path2DData@Art@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Art::Path2DData::ArcTo>::c_typeInfo
0x18006ffb8  cmp     rcx, rax
0x18006ffbb  jz      loc_1800700B7
0x18006ffc1  cmp     [rcx+8], rdi
0x18006ffc5  jnz     loc_18007009B
0x18006ffcb  mov     al, bpl
0x18006ffce  test    al, al
0x18006ffd0  jnz     loc_18007025F
0x18006ffd6  mov     rcx, [rbx+8]
0x18006ffda  cmp     rcx, 1
0x18006ffde  jbe     short loc_18006FFF9
0x18006ffe0  mov     rcx, [rcx]
0x18006ffe3  lea     rax, ?c_typeInfo@?$TypeInfoImpl@UQuadBezierTo@Path2DData@Art@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Art::Path2DData::QuadBezierTo>::c_typeInfo
0x18006ffea  cmp     rcx, rax
0x18006ffed  jz      loc_180070094
0x18006fff3  cmp     [rcx+8], rdi
0x18006fff7  jnz     short loc_180070078
0x18006fff9  mov     al, bpl
0x18006fffc  test    al, al
0x18006fffe  jnz     loc_1800702D2
0x180070004  mov     rcx, [rbx+8]
0x180070008  cmp     rcx, 1
0x18007000c  jbe     short loc_18007002B
0x18007000e  mov     rcx, [rcx]
0x180070011  lea     rax, ?c_typeInfo@?$TypeInfoImpl@UCubicBezierTo@Path2DData@Art@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Art::Path2DData::CubicBezierTo>::c_typeInfo
0x180070018  cmp     rcx, rax
0x18007001b  jz      loc_180070120
0x180070021  cmp     [rcx+8], rdi
0x180070025  jnz     loc_180070104
0x18007002b  mov     al, bpl
0x18007002e  test    al, al
0x180070030  jz      loc_18006FEF0
0x180070036  mov     rcx, rbx
0x180070039  call    ??$GetPtr@UCubicBezierTo@Path2DData@Art@@@?$TChoice@VSegmentChoiceIDsImpl@Path2DData@Art@@@Ofc@@QEAAPEAVPath2DCubicBezierTo@Art@@XZ; Ofc::TChoice<Art::Path2DData::SegmentChoiceIDsImpl>::GetPtr<Art::Path2DData::CubicBezierTo>(void)
0x18007003e  test    rax, rax
0x180070041  jz      loc_1800702ED
0x180070047  mov     r8, rax; struct Art::Path2DCubicBezierTo *
0x18007004a  mov     rdx, r13; struct Art::CGuideNameList *
0x18007004d  mov     rcx, rsi; this
0x180070050  call    ?InitFrom@PCPath2DCubicBezierTo@Art@@QEAAXAEBVCGuideNameList@2@AEBVPath2DCubicBezierTo@2@@Z; Art::PCPath2DCubicBezierTo::InitFrom(Art::CGuideNameList const &,Art::Path2DCubicBezierTo const &)
0x180070055  jmp     loc_18006FEF0
0x18007005a  mov     rcx, rbx
0x18007005d  call    ??$Get@UMoveTo@Path2DData@Art@@@?$TChoice@VSegmentChoiceIDsImpl@Path2DData@Art@@@Ofc@@QEAAAEAVPath2DMoveTo@Art@@XZ; Ofc::TChoice<Art::Path2DData::SegmentChoiceIDsImpl>::Get<Art::Path2DData::MoveTo>(void)
0x180070062  mov     [rsi], ebp
0x180070064  lea     rcx, [rsi+8]; this
0x180070068  mov     r8, rax; struct Art::AdjPoint2D *
0x18007006b  mov     rdx, r13; struct Art::CGuideNameList *
0x18007006e  call    ?InitFrom@PCAdjPoint2D@Art@@QEAAXAEBVCGuideNameList@2@AEBVAdjPoint2D@2@@Z; Art::PCAdjPoint2D::InitFrom(Art::CGuideNameList const &,Art::AdjPoint2D const &)
0x180070073  jmp     loc_18006FEF0
0x180070078  mov     rcx, [rcx]
0x18007007b  add     rcx, 8
0x18007007f  lea     rdx, qword_180E1BEF0
0x180070086  call    cs:__imp___std_type_info_compare
0x18007008c  test    eax, eax
0x18007008e  jnz     loc_18006FFF9
0x180070094  mov     al, 1
0x180070096  jmp     loc_18006FFFC
0x18007009b  mov     rcx, [rcx]
0x18007009e  add     rcx, 8
0x1800700a2  lea     rdx, qword_180E1BF28
0x1800700a9  call    cs:__imp___std_type_info_compare
0x1800700af  test    eax, eax
0x1800700b1  jnz     loc_18006FFCB
0x1800700b7  mov     al, 1
0x1800700b9  jmp     loc_18006FFCE
0x1800700be  mov     rcx, [rcx]
0x1800700c1  add     rcx, 8
0x1800700c5  lea     rdx, qword_180E1BEC0
0x1800700cc  call    cs:__imp___std_type_info_compare
0x1800700d2  test    eax, eax
0x1800700d4  jnz     loc_18006FF63
0x1800700da  mov     al, 1
0x1800700dc  jmp     loc_18006FF66
0x1800700e1  mov     rcx, [rcx]
0x1800700e4  add     rcx, 8
0x1800700e8  lea     rdx, qword_180E1BE90
0x1800700ef  call    cs:__imp___std_type_info_compare
0x1800700f5  test    eax, eax
0x1800700f7  jnz     loc_18006FF99
0x1800700fd  mov     al, 1
0x1800700ff  jmp     loc_18006FF9C
0x180070104  mov     rcx, [rcx]
0x180070107  add     rcx, 8
0x18007010b  lea     rdx, qword_180E1BE28
0x180070112  call    cs:__imp___std_type_info_compare
0x180070118  test    eax, eax
0x18007011a  jnz     loc_18007002B
0x180070120  mov     al, 1
0x180070122  jmp     loc_18007002E
0x180070127  mov     rcx, rbx
0x18007012a  call    ??$GetPtr@UClose@Path2DData@Art@@@?$TChoice@VSegmentChoiceIDsImpl@Path2DData@Art@@@Ofc@@QEAAPEAVPath2DClose@Art@@XZ; Ofc::TChoice<Art::Path2DData::SegmentChoiceIDsImpl>::GetPtr<Art::Path2DData::Close>(void)
0x18007012f  test    rax, rax
0x180070132  jz      loc_1800702ED
0x180070138  mov     dword ptr [rsi], 5
0x18007013e  jmp     loc_18006FEF0
0x180070143  lea     rax, ?s_moduleTag@TypeInfo@Ofc@@2HB; int const Ofc::TypeInfo::s_moduleTag
0x18007014a  cmp     [rcx+30h], rax
0x18007014e  jnz     loc_18007027A
0x180070154  mov     rcx, rbx
0x180070157  call    ??$Is@VGeomGuideName@Art@@@?$TVariant@VAdjCoordDataIDsImpl@Art@@@Ofc@@QEBA_NXZ; Ofc::TVariant<Art::AdjCoordDataIDsImpl>::Is<Art::GeomGuideName>(void)
0x18007015c  test    al, al
0x18007015e  jz      short loc_180070194
0x180070160  mov     r8, rbx; struct Art::GeomGuideName *
0x180070163  mov     rdx, r13; struct Art::CGuideNameList *
0x180070166  mov     rcx, rdi; this
0x180070169  call    ?InitFrom@PCGeomGuideName@Art@@QEAAXAEBVCGuideNameList@2@AEBVGeomGuideName@2@@Z; Art::PCGeomGuideName::InitFrom(Art::CGuideNameList const &,Art::GeomGuideName const &)
0x18007016e  mov     dword ptr [rdi+4], 0FFFFFFFFh
0x180070175  cmp     dword ptr [rdi], 7FFFFFFFh
0x18007017b  jnz     loc_18006FEA6
0x180070181  mov     [rdi], rbp
0x180070184  jmp     loc_18006FEA6
0x180070189  mov     ecx, 35663662h
0x18007018e  call    cs:__imp_MsoShipAssertTagProc
0x180070194  mov     ecx, 65747234h; unsigned int
0x180070199  call    ?ThrowTag@CInvalidParamException@Ofc@@SAXK@Z; Ofc::CInvalidParamException::ThrowTag(ulong)
0x18007019e  int     3; Trap to Debugger
0x18007019f  lea     rax, ?s_moduleTag@TypeInfo@Ofc@@2HB; int const Ofc::TypeInfo::s_moduleTag
0x1800701a6  cmp     [rcx+30h], rax
0x1800701aa  jnz     loc_18007029D
0x1800701b0  lea     rcx, [rbx+10h]
0x1800701b4  call    ??$Is@VGeomGuideName@Art@@@?$TVariant@VAdjCoordDataIDsImpl@Art@@@Ofc@@QEBA_NXZ; Ofc::TVariant<Art::AdjCoordDataIDsImpl>::Is<Art::GeomGuideName>(void)
0x1800701b9  test    al, al
0x1800701bb  jz      short loc_180070194
0x1800701bd  lea     r8, [rbx+10h]; struct Art::GeomGuideName *
0x1800701c1  mov     rdx, r13; struct Art::CGuideNameList *
0x1800701c4  lea     rcx, [rdi+8]; this
0x1800701c8  call    ?InitFrom@PCGeomGuideName@Art@@QEAAXAEBVCGuideNameList@2@AEBVGeomGuideName@2@@Z; Art::PCGeomGuideName::InitFrom(Art::CGuideNameList const &,Art::GeomGuideName const &)
0x1800701cd  mov     dword ptr [rdi+0Ch], 0FFFFFFFFh
0x1800701d4  xor     ebp, ebp
0x1800701d6  cmp     dword ptr [rdi+8], 7FFFFFFFh
0x1800701dd  jnz     loc_18006FEE9
0x1800701e3  mov     [rdi+8], rbp
0x1800701e7  jmp     loc_18006FEE9
0x1800701ec  lea     rax, ?s_moduleTag@TypeInfo@Ofc@@2HB; int const Ofc::TypeInfo::s_moduleTag
  ... truncated ...
```
