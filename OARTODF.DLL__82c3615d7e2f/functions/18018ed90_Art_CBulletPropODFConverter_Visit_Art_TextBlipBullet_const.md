# Art::CBulletPropODFConverter::Visit(Art::TextBlipBullet const &)

- ea: `0x18018ed90`
- end: `0x18018f21f`
- name: `?Visit@CBulletPropODFConverter@Art@@UEAAXAEBVTextBlipBullet@2@@Z`
- size: `1167`
- prototype: `void __fastcall(Art::CBulletPropODFConverter *__hidden this, const struct Art::TextBlipBullet *)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x180004818`
- `0x1800048d4`
- `0x1800078b4`
- `0x180022f80`
- `0x180092cf8`
- `0x1800b3e24`
- `0x1800b40f4`
- `0x18016248c`
- `0x18017ea8c`
- `0x18018674c`
- `0x18018ed90`
- `0x1801a80e0`

## import_xrefs

- `KERNEL32!EncodePointer` at `0x18018f11b`
- `KERNEL32!EncodePointer` at `0x18018f11b`
- `oart!__imp_??1TextCharPropertyBag@Art@@QEAA@XZ` at `0x18018efcb`
- `oart!__imp_??1TextCharPropertyBag@Art@@QEAA@XZ` at `0x18018efcb`
- `oart!__imp_?GetCharPropertyBagResolved@TextBodyWithStyleCache@Art@@QEBAXAEBUTextRange@2@AEAVTextCharPropertyBag@2@@Z` at `0x18018ef7e`
- `oart!__imp_?GetCharPropertyBagResolved@TextBodyWithStyleCache@Art@@QEBAXAEBUTextRange@2@AEAVTextCharPropertyBag@2@@Z` at `0x18018ef7e`
- `oart!__imp_??0Blip@Art@@QEAA@AEBV01@@Z` at `0x18018f0cc`
- `oart!__imp_??0Blip@Art@@QEAA@AEBV01@@Z` at `0x18018f0cc`
- `oart!__imp_??0TextCharPropertyBag@Art@@QEAA@XZ` at `0x18018ef5d`
- `oart!__imp_??0TextCharPropertyBag@Art@@QEAA@XZ` at `0x18018ef5d`
- `oart!__imp_?GetImage@Blip@Art@@QEBA?AV?$TCntPtr@UIImage@GEL@@@Ofc@@XZ` at `0x18018efdd`
- `oart!__imp_?GetImage@Blip@Art@@QEBA?AV?$TCntPtr@UIImage@GEL@@@Ofc@@XZ` at `0x18018efdd`
- `VCRUNTIME140!__std_type_info_compare` at `0x18018ee0d`
- `VCRUNTIME140!__std_type_info_compare` at `0x18018eea1`
- `VCRUNTIME140!__std_type_info_compare` at `0x18018ef11`
- `VCRUNTIME140!__std_type_info_compare` at `0x18018ee0d`
- `VCRUNTIME140!__std_type_info_compare` at `0x18018eea1`
- `VCRUNTIME140!__std_type_info_compare` at `0x18018ef11`
- `mso40uiWin32Client!__imp_?GetPropertyStgType@CPropertySetImpl@Tph@Ofc@@IEBAPEBV?$TAnyStorage@$07@3@I@Z` at `0x18018ee5a`
- `mso40uiWin32Client!__imp_?GetPropertyStgType@CPropertySetImpl@Tph@Ofc@@IEBAPEBV?$TAnyStorage@$07@3@I@Z` at `0x18018efaa`
- `mso40uiWin32Client!__imp_?GetPropertyStgType@CPropertySetImpl@Tph@Ofc@@IEBAPEBV?$TAnyStorage@$07@3@I@Z` at `0x18018ee5a`
- `mso40uiWin32Client!__imp_?GetPropertyStgType@CPropertySetImpl@Tph@Ofc@@IEBAPEBV?$TAnyStorage@$07@3@I@Z` at `0x18018efaa`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x18018f1aa`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x18018f1aa`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x18018f100`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x18018f100`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x18018f0b0`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x18018f0df`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x18018f0b0`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x18018f0df`
- `Mso20Win32Client!__imp_?ThrowOOM@@YAXXZ` at `0x18018f0bb`
- `Mso20Win32Client!__imp_?ThrowOOM@@YAXXZ` at `0x18018f0bb`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall Art::CBulletPropODFConverter::Visit(
        Art::CBulletPropODFConverter *this,
        const struct Art::TextBlipBullet *a2)
{
  unsigned __int64 v4; // rax
  struct ODF::TextListStyleContentChoiceChoices::listLevelStyleImage **v5; // rcx
  bool v6; // zf
  __int64 v8; // rdi
  double v9; // xmm7_8
  double v10; // xmm8_8
  __int64 *PropertyStgType; // rax
  __int64 v12; // rbx
  __int64 *v13; // rcx
  __int64 v14; // rcx
  int *v16; // rax
  double v17; // xmm6_8
  __int64 *v18; // rcx
  __int64 v19; // rcx
  int *v21; // rbx
  __int64 v22; // rax
  int v23; // ebx
  int v24; // ecx
  unsigned int v25; // r8d
  double v26; // xmm6_8
  double v27; // xmm1_8
  double v28; // xmm0_8
  double v29; // xmm6_8
  int v30; // eax
  double v31; // xmm0_8
  double v32; // xmm1_8
  Art::Blip *v33; // rax
  unsigned int v34; // r8d
  __int64 v35; // r14
  int *v36; // rax
  unsigned int v37; // edx
  int *v38; // rbx
  MsoReserveTag *v39; // rax
  unsigned int v40; // eax
  struct Ofc::CProxyPtrImpl *v41; // rax
  __int64 v42; // rbx
  _OWORD *Target; // rax
  _OWORD *v44; // rax
  unsigned int v45; // eax
  struct Ofc::CProxyPtrImpl *v46; // [rsp+28h] [rbp-39h] BYREF
  __int128 v47; // [rsp+30h] [rbp-31h] BYREF
  __int64 v48; // [rsp+40h] [rbp-21h] BYREF
  unsigned __int64 v49; // [rsp+48h] [rbp-19h]
  _BYTE v50[32]; // [rsp+50h] [rbp-11h] BYREF
  Art::Blip *v51; // [rsp+D8h] [rbp+77h] BYREF
  __int64 v52; // [rsp+E0h] [rbp+7Fh] BYREF

  v48 = 0;
  v49 = 0;
  Ofc::TChoice<ODF::TextListStyleContentChoiceChoiceIDsImpl>::SwitchTo<ODF::TextListStyleContentChoiceChoices::listLevelStyleImage>(&v48);
  v4 = v49;
  if ( v49 > 1
    && ((v5 = *(struct ODF::TextListStyleContentChoiceChoices::listLevelStyleImage ***)v49,
         *(struct ODF::TextListStyleContentChoiceChoices::listLevelStyleImage ***)v49 == &Ofc::TypeInfoImpl<ODF::TextListStyleContentChoiceChoices::listLevelStyleImage>::c_typeInfo)
     || v5[1] != (struct ODF::TextListStyleContentChoiceChoices::listLevelStyleImage *)&Ofc::TypeInfo::s_moduleTag
     && (v6 = (unsigned int)__std_type_info_compare((char *)*v5 + 8, &qword_180265E98) == 0, v4 = v49, v6)) )
  {
    if ( v4 <= 1 )
      Ofc::TChoice<ODF::TextListStyleContentChoiceChoiceIDsImpl>::DemandInit(&v48);
    v8 = v48;
  }
  else
  {
    v8 = 0;
  }
  if ( !v8 )
  {
    v45 = MsoReserveTag::operator unsigned int("bm5f");
    Ofc::CInvalidParamException::ThrowTag(v45);
    __debugbreak();
  }
  v9 = DOUBLE_1_0;
  v10 = DOUBLE_1_0;
  PropertyStgType = (__int64 *)Ofc::Tph::CPropertySetImpl::GetPropertyStgType(*((_QWORD *)this + 3), 4);
  if ( PropertyStgType )
    v12 = *PropertyStgType;
  else
    v12 = 0;
  if ( v12 )
  {
    v13 = *(__int64 **)(v12 + 8);
    if ( (unsigned __int64)v13 > 1
      && ((v14 = *v13,
           (struct Art::BulletSize::BulletSizePts **)v14 == &Ofc::TypeInfoImpl<Art::BulletSize::BulletSizePts>::c_typeInfo)
       || *(const int **)(v14 + 8) != &Ofc::TypeInfo::s_moduleTag
       && !(unsigned int)__std_type_info_compare(*(_QWORD *)v14 + 8LL, &qword_18026F790)) )
    {
      if ( *(_QWORD *)(v12 + 8) <= 1u )
        Ofc::TChoice<Art::TextBulletSizeDataChoiceIDsImpl>::DemandInit(v12);
      v16 = (int *)v12;
    }
    else
    {
      v16 = 0;
    }
    if ( v16 )
    {
      v17 = (double)*v16 / 100.0;
      goto LABEL_45;
    }
    v18 = *(__int64 **)(v12 + 8);
    if ( (unsigned __int64)v18 > 1
      && ((v19 = *v18,
           (struct Art::BulletSize::BulletSizePercent **)v19 == &Ofc::TypeInfoImpl<Art::BulletSize::BulletSizePercent>::c_typeInfo)
       || *(const int **)(v19 + 8) != &Ofc::TypeInfo::s_moduleTag
       && !(unsigned int)__std_type_info_compare(*(_QWORD *)v19 + 8LL, &qword_18026F758)) )
    {
      if ( *(_QWORD *)(v12 + 8) <= 1u )
        Ofc::TChoice<Art::TextBulletSizeDataChoiceIDsImpl>::DemandInit(v12);
    }
    else
    {
      v12 = 0;
    }
    if ( v12 )
      v10 = (double)*(int *)v12 / 1000.0 / 100.0;
  }
  Art::TextCharPropertyBag::TextCharPropertyBag((Art::TextCharPropertyBag *)v50);
  v51 = (Art::Blip *)*((unsigned int *)this + 12);
  Art::TextBodyWithStyleCache::GetCharPropertyBagResolved(
    *((Art::TextBodyWithStyleCache **)this + 4),
    (const struct Art::TextRange *)&v51,
    (struct Art::TextCharPropertyBag *)v50);
  *(double *)&v47 = DOUBLE_18_0;
  v21 = (int *)Art::TextFontSize::TextFontSize((Art::TextFontSize *)&v51, (const struct Art::Points *)&v47);
  v22 = Ofc::Tph::CPropertySetImpl::GetPropertyStgType(v50, 17);
  if ( v22 )
    v21 = (int *)v22;
  v17 = (double)*v21 / 100.0;
  Art::TextCharPropertyBag::~TextCharPropertyBag(v50);
LABEL_45:
  Art::Blip::GetImage(a2, &v52);
  v23 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v52 + 48LL))(v52);
  v24 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v52 + 40LL))(v52);
  v26 = v17 * v10 * 70.0 / 100.0 * 12700.0;
  v27 = DOUBLE_0_5;
  if ( v26 < 0.0 )
    v28 = DOUBLE_N0_5;
  else
    v28 = DOUBLE_0_5;
  v29 = v26 + v28;
  if ( v23 )
  {
    v9 = (double)v24 / (double)v23;
  }
  else if ( v24 )
  {
    if ( v24 <= 0 )
      v30 = (v24 >= 0) - 1;
    else
      v30 = 1;
    v9 = (double)v30 * 1.797693134862316e308;
  }
  v31 = (double)(int)v29 * v9;
  if ( v31 < 0.0 )
    v27 = DOUBLE_N0_5;
  v32 = v27 + v31;
  v33 = (Art::Blip *)Mso::Memory::AllocateEx((Mso::Memory *)0x238, 0, v25);
  if ( !v33 )
  {
    ThrowOOM();
    __debugbreak();
  }
  v51 = v33;
  v35 = Art::Blip::Blip(v33, a2);
  if ( v35 )
  {
    v36 = (int *)Mso::Memory::AllocateEx((Mso::Memory *)0x18, 0, v34);
    v38 = v36;
    if ( !v36 )
    {
      v39 = MsoReserveTag::MsoReserveTag((MsoReserveTag *)&v51, v37);
      v40 = MsoReserveTag::operator unsigned int(v39);
      CrashWithRecoveryOnOOM(v40);
      __debugbreak();
    }
    *v36 = 1;
    v36[1] = 1;
    *((_QWORD *)v36 + 1) = EncodePointer(Ofc::TDeleteFromProxy<Art::Blip>);
    *((_QWORD *)v38 + 2) = v35;
  }
  else
  {
    v38 = &`Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_proxyPtrSentinel;
  }
  v46 = (struct Ofc::CProxyPtrImpl *)v38;
  v41 = *(struct Ofc::CProxyPtrImpl **)(v8 + 56);
  *(_QWORD *)(v8 + 56) = v38;
  v46 = v41;
  if ( (int)v32 && (int)v29 )
  {
    if ( !*(_QWORD *)(v8 + 40) )
      Ofc::TOptional<ODF::StyleListLevelPropertiesContent>::CreateStorage(v8 + 40);
    v42 = *(_QWORD *)(v8 + 40);
    LODWORD(v47) = 0;
    *((_QWORD *)&v47 + 1) = (unsigned int)(int)v32;
    Target = (_OWORD *)Ofc::TOptionalAdapter<ODF::NonNegativeLength>::GetTarget(v42 + 48);
    *Target = v47;
    LODWORD(v47) = 0;
    *((_QWORD *)&v47 + 1) = (unsigned int)(int)v29;
    v44 = (_OWORD *)Ofc::TOptionalAdapter<ODF::NonNegativeLength>::GetTarget(v42 + 56);
    *v44 = v47;
  }
  Art::CBulletPropODFConverter::FillLevelProperties<ODF::TextListStyleContentChoiceChoices::listLevelStyleImage>(
    this,
    &v48);
  Ofc::CProxyPtrImpl::DtorStrongRelease(&v46);
  if ( v52 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 8LL))(v52);
  if ( v49 > 1 )
    (*(void (__fastcall **)(__int64 *))(v49 + 16))(&v48);
}

```

## disassembly

```asm
0x18018ed90  mov     rax, rsp
0x18018ed93  mov     [rax+8], rbx
0x18018ed97  mov     [rax+10h], rsi
0x18018ed9b  push    rbp
0x18018ed9c  push    rdi
0x18018ed9d  push    r13
0x18018ed9f  push    r14
0x18018eda1  push    r15
0x18018eda3  lea     rbp, [rax-5Fh]
0x18018eda7  sub     rsp, 90h
0x18018edae  movaps  xmmword ptr [rax-38h], xmm6
0x18018edb2  movaps  xmmword ptr [rax-48h], xmm7
0x18018edb6  movaps  xmmword ptr [rax-58h], xmm8
0x18018edbb  mov     r14, rdx
0x18018edbe  mov     r13, rcx
0x18018edc1  xor     eax, eax
0x18018edc3  mov     [rbp+57h+var_78], rax
0x18018edc7  mov     [rbp+57h+var_70], rax
0x18018edcb  lea     rcx, [rbp+57h+var_78]
0x18018edcf  call    ??$SwitchTo@UlistLevelStyleImage@TextListStyleContentChoiceChoices@ODF@@@?$TChoice@VTextListStyleContentChoiceChoiceIDsImpl@ODF@@@Ofc@@QEAAAEAVListLevelStyleImage@ODF@@XZ; Ofc::TChoice<ODF::TextListStyleContentChoiceChoiceIDsImpl>::SwitchTo<ODF::TextListStyleContentChoiceChoices::listLevelStyleImage>(void)
0x18018edd4  lea     rsi, ?s_moduleTag@TypeInfo@Ofc@@2HB; int const Ofc::TypeInfo::s_moduleTag
0x18018eddb  mov     rax, [rbp+57h+var_70]
0x18018eddf  mov     r15d, 1
0x18018ede5  cmp     rax, r15
0x18018ede8  jbe     short loc_18018EE20
0x18018edea  mov     rcx, [rax]
0x18018eded  lea     rdx, ?c_typeInfo@?$TypeInfoImpl@UlistLevelStyleImage@TextListStyleContentChoiceChoices@ODF@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<ODF::TextListStyleContentChoiceChoices::listLevelStyleImage>::c_typeInfo
0x18018edf4  cmp     rcx, rdx
0x18018edf7  jz      short loc_18018EE1B
0x18018edf9  cmp     [rcx+8], rsi
0x18018edfd  jz      short loc_18018EE20
0x18018edff  mov     rcx, [rcx]
0x18018ee02  add     rcx, 8
0x18018ee06  lea     rdx, qword_180265E98
0x18018ee0d  call    cs:__imp___std_type_info_compare
0x18018ee13  test    eax, eax
0x18018ee15  mov     rax, [rbp+57h+var_70]
0x18018ee19  jnz     short loc_18018EE20
0x18018ee1b  mov     cl, r15b
0x18018ee1e  jmp     short loc_18018EE22
0x18018ee20  xor     cl, cl
0x18018ee22  test    cl, cl
0x18018ee24  jnz     short loc_18018EE2A
0x18018ee26  xor     edi, edi
0x18018ee28  jmp     short loc_18018EE3C
0x18018ee2a  cmp     rax, r15
0x18018ee2d  ja      short loc_18018EE38
0x18018ee2f  lea     rcx, [rbp+57h+var_78]
0x18018ee33  call    ?DemandInit@?$TChoice@VTextListStyleContentChoiceChoiceIDsImpl@ODF@@@Ofc@@AEBAXXZ; Ofc::TChoice<ODF::TextListStyleContentChoiceChoiceIDsImpl>::DemandInit(void)
0x18018ee38  mov     rdi, [rbp+57h+var_78]
0x18018ee3c  test    rdi, rdi
0x18018ee3f  jz      loc_18018F20B
0x18018ee45  movsd   xmm7, cs:__real@3ff0000000000000
0x18018ee4d  movaps  xmm8, xmm7
0x18018ee51  mov     edx, 4
0x18018ee56  mov     rcx, [r13+18h]
0x18018ee5a  call    cs:__imp_?GetPropertyStgType@CPropertySetImpl@Tph@Ofc@@IEBAPEBV?$TAnyStorage@$07@3@I@Z; Ofc::Tph::CPropertySetImpl::GetPropertyStgType(uint)
0x18018ee60  test    rax, rax
0x18018ee63  jz      short loc_18018EE6A
0x18018ee65  mov     rbx, [rax]
0x18018ee68  jmp     short loc_18018EE6C
0x18018ee6a  xor     ebx, ebx
0x18018ee6c  test    rbx, rbx
0x18018ee6f  jz      loc_18018EF59
0x18018ee75  mov     rcx, [rbx+8]
0x18018ee79  cmp     rcx, r15
0x18018ee7c  jbe     short loc_18018EEB0
0x18018ee7e  mov     rcx, [rcx]
0x18018ee81  lea     rax, ?c_typeInfo@?$TypeInfoImpl@UBulletSizePts@BulletSize@Art@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Art::BulletSize::BulletSizePts>::c_typeInfo
0x18018ee88  cmp     rcx, rax
0x18018ee8b  jz      short loc_18018EEAB
0x18018ee8d  cmp     [rcx+8], rsi
0x18018ee91  jz      short loc_18018EEB0
0x18018ee93  mov     rcx, [rcx]
0x18018ee96  add     rcx, 8
0x18018ee9a  lea     rdx, qword_18026F790
0x18018eea1  call    cs:__imp___std_type_info_compare
0x18018eea7  test    eax, eax
0x18018eea9  jnz     short loc_18018EEB0
0x18018eeab  mov     al, r15b
0x18018eeae  jmp     short loc_18018EEB2
0x18018eeb0  xor     al, al
0x18018eeb2  test    al, al
0x18018eeb4  jnz     short loc_18018EEBA
0x18018eeb6  xor     eax, eax
0x18018eeb8  jmp     short loc_18018EECB
0x18018eeba  cmp     [rbx+8], r15
0x18018eebe  ja      short loc_18018EEC8
0x18018eec0  mov     rcx, rbx
0x18018eec3  call    ?DemandInit@?$TChoice@VTextBulletSizeDataChoiceIDsImpl@Art@@@Ofc@@AEBAXXZ; Ofc::TChoice<Art::TextBulletSizeDataChoiceIDsImpl>::DemandInit(void)
0x18018eec8  mov     rax, rbx
0x18018eecb  test    rax, rax
0x18018eece  jz      short loc_18018EEE5
0x18018eed0  movd    xmm6, dword ptr [rax]
0x18018eed4  cvtdq2pd xmm6, xmm6
0x18018eed8  divsd   xmm6, cs:__real@4059000000000000
0x18018eee0  jmp     loc_18018EFD1
0x18018eee5  mov     rcx, [rbx+8]
0x18018eee9  cmp     rcx, r15
0x18018eeec  jbe     short loc_18018EF20
0x18018eeee  mov     rcx, [rcx]
0x18018eef1  lea     rax, ?c_typeInfo@?$TypeInfoImpl@UBulletSizePercent@BulletSize@Art@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Art::BulletSize::BulletSizePercent>::c_typeInfo
0x18018eef8  cmp     rcx, rax
0x18018eefb  jz      short loc_18018EF1B
0x18018eefd  cmp     [rcx+8], rsi
0x18018ef01  jz      short loc_18018EF20
0x18018ef03  mov     rcx, [rcx]
0x18018ef06  add     rcx, 8
0x18018ef0a  lea     rdx, qword_18026F758
0x18018ef11  call    cs:__imp___std_type_info_compare
0x18018ef17  test    eax, eax
0x18018ef19  jnz     short loc_18018EF20
0x18018ef1b  mov     al, r15b
0x18018ef1e  jmp     short loc_18018EF22
0x18018ef20  xor     al, al
0x18018ef22  test    al, al
0x18018ef24  jnz     short loc_18018EF2A
0x18018ef26  xor     ebx, ebx
0x18018ef28  jmp     short loc_18018EF38
0x18018ef2a  cmp     [rbx+8], r15
0x18018ef2e  ja      short loc_18018EF38
0x18018ef30  mov     rcx, rbx
0x18018ef33  call    ?DemandInit@?$TChoice@VTextBulletSizeDataChoiceIDsImpl@Art@@@Ofc@@AEBAXXZ; Ofc::TChoice<Art::TextBulletSizeDataChoiceIDsImpl>::DemandInit(void)
0x18018ef38  test    rbx, rbx
0x18018ef3b  jz      short loc_18018EF59
0x18018ef3d  movd    xmm8, dword ptr [rbx]
0x18018ef42  cvtdq2pd xmm8, xmm8
0x18018ef47  divsd   xmm8, cs:__real@408f400000000000
0x18018ef50  divsd   xmm8, cs:__real@4059000000000000
0x18018ef59  lea     rcx, [rbp+57h+var_68]
0x18018ef5d  call    cs:__imp_??0TextCharPropertyBag@Art@@QEAA@XZ; Art::TextCharPropertyBag::TextCharPropertyBag(void)
0x18018ef63  nop
0x18018ef64  mov     eax, [r13+30h]
0x18018ef68  mov     dword ptr [rbp+57h+arg_10], eax
0x18018ef6b  mov     dword ptr [rbp+57h+arg_10+4], 0
0x18018ef72  lea     r8, [rbp+57h+var_68]
0x18018ef76  lea     rdx, [rbp+57h+arg_10]
0x18018ef7a  mov     rcx, [r13+20h]
0x18018ef7e  call    cs:__imp_?GetCharPropertyBagResolved@TextBodyWithStyleCache@Art@@QEBAXAEBUTextRange@2@AEAVTextCharPropertyBag@2@@Z; Art::TextBodyWithStyleCache::GetCharPropertyBagResolved(Art::TextRange const &,Art::TextCharPropertyBag &)
0x18018ef84  movsd   xmm0, cs:__real@4032000000000000
0x18018ef8c  movsd   qword ptr [rbp+57h+var_88], xmm0
0x18018ef91  lea     rdx, [rbp+57h+var_88]; struct Art::Points *
0x18018ef95  lea     rcx, [rbp+57h+arg_10]; this
0x18018ef99  call    ??0TextFontSize@Art@@QEAA@AEBVPoints@1@@Z; Art::TextFontSize::TextFontSize(Art::Points const &)
0x18018ef9e  mov     rbx, rax
0x18018efa1  mov     edx, 11h
0x18018efa6  lea     rcx, [rbp+57h+var_68]
0x18018efaa  call    cs:__imp_?GetPropertyStgType@CPropertySetImpl@Tph@Ofc@@IEBAPEBV?$TAnyStorage@$07@3@I@Z; Ofc::Tph::CPropertySetImpl::GetPropertyStgType(uint)
0x18018efb0  test    rax, rax
0x18018efb3  cmovnz  rbx, rax
0x18018efb7  movd    xmm6, dword ptr [rbx]
0x18018efbb  cvtdq2pd xmm6, xmm6
0x18018efbf  divsd   xmm6, cs:__real@4059000000000000
0x18018efc7  lea     rcx, [rbp+57h+var_68]
0x18018efcb  call    cs:__imp_??1TextCharPropertyBag@Art@@QEAA@XZ; Art::TextCharPropertyBag::~TextCharPropertyBag(void)
0x18018efd1  mulsd   xmm6, xmm8
0x18018efd6  lea     rdx, [rbp+57h+arg_18]
0x18018efda  mov     rcx, r14
0x18018efdd  call    cs:__imp_?GetImage@Blip@Art@@QEBA?AV?$TCntPtr@UIImage@GEL@@@Ofc@@XZ; Art::Blip::GetImage(void)
0x18018efe3  nop
0x18018efe4  mov     rcx, [rbp+57h+arg_18]
0x18018efe8  mov     rax, [rcx]
0x18018efeb  mov     rax, [rax+30h]
0x18018efef  call    cs:__guard_dispatch_icall_fptr
0x18018eff5  mov     ebx, eax
0x18018eff7  mov     rcx, [rbp+57h+arg_18]
0x18018effb  mov     rdx, [rcx]
0x18018effe  mov     rax, [rdx+28h]
0x18018f002  call    cs:__guard_dispatch_icall_fptr
0x18018f008  mov     ecx, eax
0x18018f00a  mulsd   xmm6, cs:__real@4051800000000000
0x18018f012  divsd   xmm6, cs:__real@4059000000000000
0x18018f01a  mulsd   xmm6, cs:__real@40c8ce0000000000
0x18018f022  xorps   xmm3, xmm3
0x18018f025  movsd   xmm2, cs:__real@bfe0000000000000
0x18018f02d  movsd   xmm1, cs:__real@3fe0000000000000
0x18018f035  comisd  xmm6, xmm3
0x18018f039  jb      short loc_18018F040
0x18018f03b  movaps  xmm0, xmm1
0x18018f03e  jmp     short loc_18018F043
0x18018f040  movaps  xmm0, xmm2
0x18018f043  addsd   xmm6, xmm0
0x18018f047  cvttsd2si rsi, xmm6
0x18018f04c  test    ebx, ebx
0x18018f04e  jz      short loc_18018F066
0x18018f050  movd    xmm7, ecx
0x18018f054  cvtdq2pd xmm7, xmm7
0x18018f058  movd    xmm0, ebx
0x18018f05c  cvtdq2pd xmm0, xmm0
0x18018f060  divsd   xmm7, xmm0
0x18018f064  jmp     short loc_18018F08B
0x18018f066  test    ecx, ecx
0x18018f068  jz      short loc_18018F08B
0x18018f06a  jle     short loc_18018F071
0x18018f06c  mov     eax, r15d
0x18018f06f  jmp     short loc_18018F07B
0x18018f071  xor     eax, eax
0x18018f073  test    ecx, ecx
0x18018f075  setns   al
0x18018f078  sub     eax, r15d
0x18018f07b  movd    xmm7, eax
0x18018f07f  cvtdq2pd xmm7, xmm7
0x18018f083  mulsd   xmm7, cs:__real@7fefffffffffffff
0x18018f08b  xorps   xmm0, xmm0
0x18018f08e  cvtsi2sd xmm0, rsi
0x18018f093  mulsd   xmm0, xmm7
0x18018f097  comisd  xmm0, xmm3
0x18018f09b  jnb     short loc_18018F0A0
0x18018f09d  movaps  xmm1, xmm2
0x18018f0a0  addsd   xmm1, xmm0
0x18018f0a4  cvttsd2si r15, xmm1
0x18018f0a9  xor     edx, edx
0x18018f0ab  mov     ecx, 238h
0x18018f0b0  call    cs:__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::AllocateEx(unsigned __int64,ulong)
0x18018f0b6  test    rax, rax
0x18018f0b9  jnz     short loc_18018F0C2
0x18018f0bb  call    cs:__imp_?ThrowOOM@@YAXXZ; ThrowOOM(void)
0x18018f0c1  int     3; Trap to Debugger
0x18018f0c2  mov     [rbp+57h+arg_10], rax
0x18018f0c6  mov     rdx, r14
0x18018f0c9  mov     rcx, rax
0x18018f0cc  call    cs:__imp_??0Blip@Art@@QEAA@AEBV01@@Z; Art::Blip::Blip(Art::Blip const &)
0x18018f0d2  mov     r14, rax
0x18018f0d5  test    rax, rax
0x18018f0d8  jz      short loc_18018F12B
0x18018f0da  xor     edx, edx
0x18018f0dc  lea     ecx, [rdx+18h]
0x18018f0df  call    cs:__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::AllocateEx(unsigned __int64,ulong)
0x18018f0e5  mov     rbx, rax
0x18018f0e8  test    rax, rax
0x18018f0eb  jnz     short loc_18018F107
0x18018f0ed  lea     rcx, [rbp+57h+arg_10]; this
0x18018f0f1  call    ??0MsoReserveTag@@QEAA@I@Z; MsoReserveTag::MsoReserveTag(uint)
0x18018f0f6  mov     rcx, rax
0x18018f0f9  call    ??BMsoReserveTag@@QEBAIXZ; MsoReserveTag::operator uint(void)
0x18018f0fe  mov     ecx, eax
0x18018f100  call    cs:__imp_?CrashWithRecoveryOnOOM@@YAXI@Z; CrashWithRecoveryOnOOM(uint)
0x18018f106  int     3; Trap to Debugger
0x18018f107  mov     dword ptr [rax], 1
0x18018f10d  mov     dword ptr [rax+4], 1
0x18018f114  lea     rcx, ??$TDeleteFromProxy@VBlip@Art@@@Ofc@@YAXPEAX@Z; Ptr
0x18018f11b  call    cs:__imp_EncodePointer
0x18018f121  mov     [rbx+8], rax
0x18018f125  mov     [rbx+10h], r14
0x18018f129  jmp     short loc_18018F132
0x18018f12b  lea     rbx, ?s_proxyPtrSentinel@?1??GetSentinel@CProxyPtrImpl@Ofc@@KAAEBQEAV23@XZ@4UProxyPtrSentinel@?1??123@KAAEBQEAV23@XZ@B; `Ofc::CProxyPtrImpl::GetSentinel(void)'::`2'::ProxyPtrSentinel const `Ofc::CProxyPtrImpl::GetSentinel(void)'::`2'::s_proxyPtrSentinel
0x18018f132  mov     [rbp+57h+var_90], rbx
0x18018f136  mov     rax, [rdi+38h]
0x18018f13a  mov     [rdi+38h], rbx
0x18018f13e  mov     [rbp+57h+var_90], rax
0x18018f142  test    r15, r15
0x18018f145  jle     short loc_18018F199
0x18018f147  test    rsi, rsi
0x18018f14a  jle     short loc_18018F199
0x18018f14c  lea     rbx, [rdi+28h]
0x18018f150  cmp     qword ptr [rbx], 0
0x18018f154  jnz     short loc_18018F15E
0x18018f156  mov     rcx, rbx
0x18018f159  call    ?CreateStorage@?$TOptional@VStyleListLevelPropertiesContent@ODF@@@Ofc@@QEAAAEAVStyleListLevelPropertiesContent@ODF@@PEAVCRollbackTransaction@2@@Z; Ofc::TOptional<ODF::StyleListLevelPropertiesContent>::CreateStorage(Ofc::CRollbackTransaction *)
0x18018f15e  mov     rbx, [rbx]
0x18018f161  mov     dword ptr [rbp+57h+var_88], 0
0x18018f168  mov     qword ptr [rbp+57h+var_88+8], r15
0x18018f16c  lea     rcx, [rbx+30h]
0x18018f170  call    ?GetTarget@?$TOptionalAdapter@VNonNegativeLength@ODF@@@Ofc@@SAAEAVNonNegativeLength@ODF@@AEAV?$TOptional@VNonNegativeLength@ODF@@@2@@Z; Ofc::TOptionalAdapter<ODF::NonNegativeLength>::GetTarget(Ofc::TOptional<ODF::NonNegativeLength> &)
0x18018f175  movups  xmm0, [rbp+57h+var_88]
0x18018f179  movdqu  xmmword ptr [rax], xmm0
0x18018f17d  mov     dword ptr [rbp+57h+var_88], 0
0x18018f184  mov     qword ptr [rbp+57h+var_88+8], rsi
0x18018f188  lea     rcx, [rbx+38h]
0x18018f18c  call    ?GetTarget@?$TOptionalAdapter@VNonNegativeLength@ODF@@@Ofc@@SAAEAVNonNegativeLength@ODF@@AEAV?$TOptional@VNonNegativeLength@ODF@@@2@@Z; Ofc::TOptionalAdapter<ODF::NonNegativeLength>::GetTarget(Ofc::TOptional<ODF::NonNegativeLength> &)
0x18018f191  movups  xmm0, [rbp+57h+var_88]
0x18018f195  movdqu  xmmword ptr [rax], xmm0
0x18018f199  lea     rdx, [rbp+57h+var_78]
0x18018f19d  mov     rcx, r13
0x18018f1a0  call    ??$FillLevelProperties@UlistLevelStyleImage@TextListStyleContentChoiceChoices@ODF@@@CBulletPropODFConverter@Art@@IEAAXAEAV?$TextListStyleContentChoice_@$0A@@ODF@@@Z; Art::CBulletPropODFConverter::FillLevelProperties<ODF::TextListStyleContentChoiceChoices::listLevelStyleImage>(ODF::TextListStyleContentChoice_<0> &)
0x18018f1a5  nop
0x18018f1a6  lea     rcx, [rbp+57h+var_90]
0x18018f1aa  call    cs:__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x18018f1b0  mov     rcx, [rbp+57h+arg_18]
0x18018f1b4  test    rcx, rcx
0x18018f1b7  jz      short loc_18018F1C7
0x18018f1b9  mov     rax, [rcx]
0x18018f1bc  mov     rax, [rax+8]
0x18018f1c0  call    cs:__guard_dispatch_icall_fptr
0x18018f1c6  nop
0x18018f1c7  mov     rax, [rbp+57h+var_70]
0x18018f1cb  cmp     rax, 1
0x18018f1cf  jbe     short loc_18018F1E0
0x18018f1d1  lea     rcx, [rbp+57h+var_78]
0x18018f1d5  mov     rax, [rax+10h]
0x18018f1d9  call    cs:__guard_dispatch_icall_fptr
0x18018f1df  nop
0x18018f1e0  lea     r11, [rsp+0B0h+var_20]
0x18018f1e8  mov     rbx, [r11+30h]
0x18018f1ec  mov     rsi, [r11+38h]
0x18018f1f0  movaps  xmm6, xmmword ptr [r11-10h]
0x18018f1f5  movaps  xmm7, [rsp+0B0h+var_48+8]
0x18018f1fa  movaps  xmm8, xmmword ptr [r11-30h]
0x18018f1ff  mov     rsp, r11
0x18018f202  pop     r15
  ... truncated ...
```
