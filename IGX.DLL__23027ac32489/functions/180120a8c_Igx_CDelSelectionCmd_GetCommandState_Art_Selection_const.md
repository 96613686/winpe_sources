# Igx::CDelSelectionCmd::GetCommandState(Art::Selection const &)

- ea: `0x180120a8c`
- end: `0x180120e57`
- name: `?GetCommandState@CDelSelectionCmd@Igx@@SA?AVCommandState@Art@@AEBVSelection@4@@Z`
- size: `971`
- prototype: `static struct Art::CommandState __high(const struct Art::Selection *)`
- caller_count: `3`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18008e060`
- `0x18011d128`
- `0x180120ed0`

## callees

- `0x180001560`
- `0x1800092a0`
- `0x18001b7a0`
- `0x18001ca60`
- `0x18001e3b0`
- `0x180024bd0`
- `0x180024e90`
- `0x180028190`
- `0x1800285c0`
- `0x180028e40`
- `0x180029140`
- `0x180029590`
- `0x1800aa790`
- `0x1800ca830`
- `0x1800e2af0`
- `0x180120a8c`
- `0x180121de0`
- `0x1801762c4`
- `0x1801cbab8`

## import_xrefs

- `oart!__imp_??0CommandState@Art@@QEAA@AEBV01@@Z` at `0x180120b09`
- `oart!__imp_??0CommandState@Art@@QEAA@AEBV01@@Z` at `0x180120bde`
- `oart!__imp_??0CommandState@Art@@QEAA@AEBV01@@Z` at `0x180120d92`
- `oart!__imp_??0CommandState@Art@@QEAA@AEBV01@@Z` at `0x180120b09`
- `oart!__imp_??0CommandState@Art@@QEAA@AEBV01@@Z` at `0x180120bde`
- `oart!__imp_??0CommandState@Art@@QEAA@AEBV01@@Z` at `0x180120d92`
- `oart!__imp_??0CommandState@Art@@QEAA@XZ` at `0x180120afa`
- `oart!__imp_??0CommandState@Art@@QEAA@XZ` at `0x180120bcf`
- `oart!__imp_??0CommandState@Art@@QEAA@XZ` at `0x180120d83`
- `oart!__imp_??0CommandState@Art@@QEAA@XZ` at `0x180120e1a`
- `oart!__imp_??0CommandState@Art@@QEAA@XZ` at `0x180120e2b`
- `oart!__imp_??0CommandState@Art@@QEAA@XZ` at `0x180120afa`
- `oart!__imp_??0CommandState@Art@@QEAA@XZ` at `0x180120bcf`
- `oart!__imp_??0CommandState@Art@@QEAA@XZ` at `0x180120d83`
- `oart!__imp_??0CommandState@Art@@QEAA@XZ` at `0x180120e1a`
- `oart!__imp_??0CommandState@Art@@QEAA@XZ` at `0x180120e2b`
- `oart!__imp_??0?$ShapePropsMethods@V?$ShapePropsDataTransacted_@$0A@@Art@@@Art@@QEAA@XZ` at `0x180120b88`
- `oart!__imp_??0?$ShapePropsMethods@V?$ShapePropsDataTransacted_@$0A@@Art@@@Art@@QEAA@XZ` at `0x180120d04`
- `oart!__imp_??0?$ShapePropsMethods@V?$ShapePropsDataTransacted_@$0A@@Art@@@Art@@QEAA@XZ` at `0x180120b88`
- `oart!__imp_??0?$ShapePropsMethods@V?$ShapePropsDataTransacted_@$0A@@Art@@@Art@@QEAA@XZ` at `0x180120d04`
- `oart!__imp_??1?$ShapePropsMethods@V?$ShapePropsDataTransacted_@$0A@@Art@@@Art@@QEAA@XZ` at `0x180120bc2`
- `oart!__imp_??1?$ShapePropsMethods@V?$ShapePropsDataTransacted_@$0A@@Art@@@Art@@QEAA@XZ` at `0x180120be8`
- `oart!__imp_??1?$ShapePropsMethods@V?$ShapePropsDataTransacted_@$0A@@Art@@@Art@@QEAA@XZ` at `0x180120d40`
- `oart!__imp_??1?$ShapePropsMethods@V?$ShapePropsDataTransacted_@$0A@@Art@@@Art@@QEAA@XZ` at `0x180120d9c`
- `oart!__imp_??1?$ShapePropsMethods@V?$ShapePropsDataTransacted_@$0A@@Art@@@Art@@QEAA@XZ` at `0x180120bc2`
- `oart!__imp_??1?$ShapePropsMethods@V?$ShapePropsDataTransacted_@$0A@@Art@@@Art@@QEAA@XZ` at `0x180120be8`
- `oart!__imp_??1?$ShapePropsMethods@V?$ShapePropsDataTransacted_@$0A@@Art@@@Art@@QEAA@XZ` at `0x180120d40`
- `oart!__imp_??1?$ShapePropsMethods@V?$ShapePropsDataTransacted_@$0A@@Art@@@Art@@QEAA@XZ` at `0x180120d9c`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x180120c08`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x180120c2b`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x180120dfe`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x180120c08`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x180120c2b`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x180120dfe`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
Art::CommandState *__fastcall Igx::CDelSelectionCmd::GetCommandState(
        Art::CommandState *a1,
        const struct Art::Selection *a2)
{
  __int64 v4; // rcx
  const struct Art::CommandState *v5; // rax
  const struct Igx::AElementSelectionInfo *Selection; // rax
  const struct Igx::AElementSelectionInfo *v7; // r14
  __int64 v8; // rax
  const struct Art::CommandState *v9; // rax
  __int64 v10; // rbx
  __int64 v11; // rdi
  __int64 v12; // rax
  const struct Art::CommandState *v13; // rax
  bool v15[8]; // [rsp+30h] [rbp-89h] BYREF
  __int64 v16; // [rsp+38h] [rbp-81h] BYREF
  _BYTE v17[24]; // [rsp+40h] [rbp-79h] BYREF
  __int64 v18; // [rsp+58h] [rbp-61h] BYREF
  __int64 v19; // [rsp+60h] [rbp-59h] BYREF
  struct Ofc::CProxyPtrImpl *v20[3]; // [rsp+68h] [rbp-51h] BYREF
  _QWORD v21[12]; // [rsp+80h] [rbp-39h] BYREF

  v4 = Ofc::TSingleton<CIgxFeaturesWin32>::s_pInstance;
  if ( (unsigned __int64)Ofc::TSingleton<CIgxFeaturesWin32>::s_pInstance <= 1 )
  {
    Ofc::ThreadSafeInitPointerOnce<CIgxFeaturesWin32 *,Ofc::TSingletonFactory<CIgxFeaturesWin32>>();
    v4 = Ofc::TSingleton<CIgxFeaturesWin32>::s_pInstance;
  }
  if ( !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v4 + 448LL))(v4) )
    goto LABEL_45;
  if ( Igx::CNumSAUtils::FSelectionHasAutoNumberElement(a2) )
  {
    v5 = (const struct Art::CommandState *)Art::CommandState::CommandState((Art::CommandState *)v15);
    *(_BYTE *)v5 &= ~1u;
LABEL_6:
    Art::CommandState::CommandState(a1, v5);
    return a1;
  }
  Selection = (const struct Igx::AElementSelectionInfo *)Art::Selection::ValidateAndQuerySelection(
                                                           a2,
                                                           (const struct Ofc::TypeInfo *)&Ofc::TypeInfoImpl<Igx::AElementSelectionInfo>::c_typeInfo);
  v7 = Selection;
  v15[0] = 0;
  if ( !Selection )
  {
LABEL_45:
    Art::CommandState::CommandState(a1);
    return a1;
  }
  if ( !(*(unsigned __int8 (__fastcall **)(const struct Igx::AElementSelectionInfo *, __int64))(*(_QWORD *)Selection
                                                                                              + 216LL))(
          Selection,
          4) )
  {
    Igx::CSelectionIter::CSelectionIter(v20, 4, v7);
    v16 = 0;
    while ( (unsigned __int8)Igx::CSelectionIter::Next(v20, &v16) )
    {
      Art::ShapePropsMethods<Art::ShapePropsDataTransacted_<0>>::ShapePropsMethods<Art::ShapePropsDataTransacted_<0>>(v17);
      Igx::AElement::GetShapeProps(v16, v17);
      if ( (unsigned __int8)Ofc::TPropertySet<Igx::ElementProps>::IsValid<Igx::Eps::PresAssocID>(v17) )
      {
        v8 = Ofc::TPropertySet<Art::ShapePropsIDs>::Get<Art::SpPr::Fill>(v17);
        if ( (unsigned __int8)Ofc::TChoice<Art::FillPropsDataChoiceIDsImpl>::Is<Art::FillPr::BlipFill>(v8) )
        {
          v9 = (const struct Art::CommandState *)Art::CommandState::CommandState((Art::CommandState *)v15);
          *(_BYTE *)v9 |= 1u;
          Art::CommandState::CommandState(a1, v9);
          Art::ShapePropsMethods<Art::ShapePropsDataTransacted_<0>>::~ShapePropsMethods<Art::ShapePropsDataTransacted_<0>>(v17);
          if ( v16 )
            Ofc::TRefCountNoVirt<Ofc::TRefCount<Ofc::CThreadingPolicyMultiThread>,Ofc::CThreadingPolicyMultiThread>::Release(v16 + 8);
          goto LABEL_16;
        }
      }
      Art::ShapePropsMethods<Art::ShapePropsDataTransacted_<0>>::~ShapePropsMethods<Art::ShapePropsDataTransacted_<0>>(v17);
    }
    if ( v16 )
      Ofc::TRefCountNoVirt<Ofc::TRefCount<Ofc::CThreadingPolicyMultiThread>,Ofc::CThreadingPolicyMultiThread>::Release(v16 + 8);
    Ofc::CProxyPtrImpl::DtorStrongRelease(v20);
  }
  if ( (*(unsigned __int8 (__fastcall **)(const struct Igx::AElementSelectionInfo *, _QWORD))(*(_QWORD *)v7 + 216LL))(
         v7,
         0) )
  {
LABEL_43:
    if ( Igx::CDelSelectionCmd::VerifySelection(v7, v15) )
    {
      v5 = (const struct Art::CommandState *)Art::CommandState::CommandState((Art::CommandState *)v15);
      *(_BYTE *)v5 |= 1u;
      goto LABEL_6;
    }
    goto LABEL_45;
  }
  Igx::CSelectionIter::CSelectionIter(v20, 0, v7);
  v16 = 0;
  do
  {
LABEL_22:
    if ( !(unsigned __int8)Igx::CSelectionIter::Next(v20, &v16) )
    {
      if ( v16 )
        Ofc::TRefCountNoVirt<Ofc::TRefCount<Ofc::CThreadingPolicyMultiThread>,Ofc::CThreadingPolicyMultiThread>::Release(v16 + 8);
      Ofc::CProxyPtrImpl::DtorStrongRelease(v20);
      goto LABEL_43;
    }
  }
  while ( !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v16 + 144LL))(v16) );
  Igx::CBreadthIterator::CBreadthIterator((Igx::CBreadthIterator *)v21, 0);
  while ( 1 )
  {
    if ( !Igx::ARelationshipIterator::Step((Igx::ARelationshipIterator *)v21, 1) )
    {
      v21[0] = &Igx::CBreadthIterator::`vftable';
      Igx::ARelationshipIterator::~ARelationshipIterator((Igx::ARelationshipIterator *)v21);
      goto LABEL_22;
    }
    v18 = 0;
    Igx::ARelationshipIterator::Relationship(v21, &v18);
    v19 = 0;
    v10 = v18;
    Igx::ARelationship::GetDestElement(v18, &v19);
    Art::ShapePropsMethods<Art::ShapePropsDataTransacted_<0>>::ShapePropsMethods<Art::ShapePropsDataTransacted_<0>>(v17);
    v11 = v19;
    Igx::AElement::GetShapeProps(v19, v17);
    if ( (unsigned __int8)Ofc::TPropertySet<Igx::ElementProps>::IsValid<Igx::Eps::PresAssocID>(v17) )
    {
      v12 = Ofc::TPropertySet<Art::ShapePropsIDs>::Get<Art::SpPr::Fill>(v17);
      if ( (unsigned __int8)Ofc::TChoice<Art::FillPropsDataChoiceIDsImpl>::Is<Art::FillPr::BlipFill>(v12) )
        break;
    }
    Art::ShapePropsMethods<Art::ShapePropsDataTransacted_<0>>::~ShapePropsMethods<Art::ShapePropsDataTransacted_<0>>(v17);
    if ( v11 )
      Ofc::TRefCountNoVirt<Ofc::TRefCount<Ofc::CThreadingPolicyMultiThread>,Ofc::CThreadingPolicyMultiThread>::Release(v11 + 8);
    if ( v10 )
      Ofc::TRefCountNoVirt<Ofc::TRefCount<Ofc::CThreadingPolicyMultiThread>,Ofc::CThreadingPolicyMultiThread>::Release(v10 + 8);
  }
  v13 = (const struct Art::CommandState *)Art::CommandState::CommandState((Art::CommandState *)v15);
  *(_BYTE *)v13 |= 1u;
  Art::CommandState::CommandState(a1, v13);
  Art::ShapePropsMethods<Art::ShapePropsDataTransacted_<0>>::~ShapePropsMethods<Art::ShapePropsDataTransacted_<0>>(v17);
  if ( v11 )
    Ofc::TRefCountNoVirt<Ofc::TRefCount<Ofc::CThreadingPolicyMultiThread>,Ofc::CThreadingPolicyMultiThread>::Release(v11 + 8);
  if ( v10 )
    Ofc::TRefCountNoVirt<Ofc::TRefCount<Ofc::CThreadingPolicyMultiThread>,Ofc::CThreadingPolicyMultiThread>::Release(v10 + 8);
  v21[0] = &Igx::CBreadthIterator::`vftable';
  Igx::ARelationshipIterator::~ARelationshipIterator((Igx::ARelationshipIterator *)v21);
  if ( v16 )
    Ofc::TRefCountNoVirt<Ofc::TRefCount<Ofc::CThreadingPolicyMultiThread>,Ofc::CThreadingPolicyMultiThread>::Release(v16 + 8);
LABEL_16:
  Ofc::CProxyPtrImpl::DtorStrongRelease(v20);
  return a1;
}

```

## disassembly

```asm
0x180120a8c  mov     [rsp-8+arg_10], rbx
0x180120a91  push    rbp
0x180120a92  push    rsi
0x180120a93  push    rdi
0x180120a94  push    r12
0x180120a96  push    r14
0x180120a98  lea     rbp, [rsp-37h]
0x180120a9d  sub     rsp, 0F0h
0x180120aa4  mov     rax, cs:__security_cookie
0x180120aab  xor     rax, rsp
0x180120aae  mov     [rbp+57h+var_30], rax
0x180120ab2  mov     rbx, rdx
0x180120ab5  mov     rsi, rcx
0x180120ab8  mov     rcx, cs:?s_pInstance@?$TSingleton@VCIgxFeaturesWin32@@@Ofc@@0PEAVCIgxFeaturesWin32@@EA; CIgxFeaturesWin32 * Ofc::TSingleton<CIgxFeaturesWin32>::s_pInstance
0x180120abf  cmp     rcx, 1
0x180120ac3  ja      short loc_180120AD1
0x180120ac5  call    ??$ThreadSafeInitPointerOnce@PEAVCIgxFeaturesWin32@@V?$TSingletonFactory@VCIgxFeaturesWin32@@@Ofc@@@Ofc@@YAXPECREAVCIgxFeaturesWin32@@@Z; Ofc::ThreadSafeInitPointerOnce<CIgxFeaturesWin32 *,Ofc::TSingletonFactory<CIgxFeaturesWin32>>(CIgxFeaturesWin32 * volatile *)
0x180120aca  mov     rcx, cs:?s_pInstance@?$TSingleton@VCIgxFeaturesWin32@@@Ofc@@0PEAVCIgxFeaturesWin32@@EA; CIgxFeaturesWin32 * Ofc::TSingleton<CIgxFeaturesWin32>::s_pInstance
0x180120ad1  mov     rax, [rcx]
0x180120ad4  mov     rax, [rax+1C0h]
0x180120adb  call    cs:__guard_dispatch_icall_fptr
0x180120ae1  test    al, al
0x180120ae3  jz      loc_180120E28
0x180120ae9  mov     rcx, rbx; struct Art::Selection *
0x180120aec  call    ?FSelectionHasAutoNumberElement@CNumSAUtils@Igx@@SA_NAEBVSelection@Art@@@Z; Igx::CNumSAUtils::FSelectionHasAutoNumberElement(Art::Selection const &)
0x180120af1  test    al, al
0x180120af3  jz      short loc_180120B14
0x180120af5  lea     rcx, [rsp+110h+var_E0]
0x180120afa  call    cs:__imp_??0CommandState@Art@@QEAA@XZ; Art::CommandState::CommandState(void)
0x180120b00  and     byte ptr [rax], 0FEh
0x180120b03  mov     rdx, rax
0x180120b06  mov     rcx, rsi
0x180120b09  call    cs:__imp_??0CommandState@Art@@QEAA@AEBV01@@Z; Art::CommandState::CommandState(Art::CommandState const &)
0x180120b0f  jmp     loc_180120E31
0x180120b14  lea     rdx, ?c_typeInfo@?$TypeInfoImpl@VAElementSelectionInfo@Igx@@@Ofc@@2VTypeInfo@2@B; struct Ofc::TypeInfo *
0x180120b1b  mov     rcx, rbx; this
0x180120b1e  call    ?ValidateAndQuerySelection@Selection@Art@@AEAAPEAXAEBVTypeInfo@Ofc@@@Z; Art::Selection::ValidateAndQuerySelection(Ofc::TypeInfo const &)
0x180120b23  mov     r14, rax
0x180120b26  mov     [rsp+110h+var_E0], 0
0x180120b2b  test    rax, rax
0x180120b2e  jz      loc_180120E28
0x180120b34  mov     rcx, [rax]
0x180120b37  mov     rax, [rcx+0D8h]
0x180120b3e  mov     ebx, 4
0x180120b43  mov     edx, ebx
0x180120b45  mov     rcx, r14
0x180120b48  call    cs:__guard_dispatch_icall_fptr
0x180120b4e  test    al, al
0x180120b50  jnz     loc_180120C31
0x180120b56  mov     r8, r14
0x180120b59  mov     edx, ebx
0x180120b5b  lea     rcx, [rbp+57h+var_A8]
0x180120b5f  call    ??0CSelectionIter@Igx@@QEAA@W4ElementSelectionType@1@PEBVAElementSelectionInfo@1@@Z; Igx::CSelectionIter::CSelectionIter(Igx::ElementSelectionType,Igx::AElementSelectionInfo const *)
0x180120b64  nop
0x180120b65  mov     [rsp+110h+var_D8], 0
0x180120b6e  lea     rdx, [rsp+110h+var_D8]
0x180120b73  lea     rcx, [rbp+57h+var_A8]
0x180120b77  call    ?Next@CSelectionIter@Igx@@QEAA_NAEAV?$TCntPtr@VAElement@Igx@@@Ofc@@@Z; Igx::CSelectionIter::Next(Ofc::TCntPtr<Igx::AElement> &)
0x180120b7c  test    al, al
0x180120b7e  jz      loc_180120C13
0x180120b84  lea     rcx, [rbp+57h+var_D0]
0x180120b88  call    cs:__imp_??0?$ShapePropsMethods@V?$ShapePropsDataTransacted_@$0A@@Art@@@Art@@QEAA@XZ; Art::ShapePropsMethods<Art::ShapePropsDataTransacted_<0>>::ShapePropsMethods<Art::ShapePropsDataTransacted_<0>>(void)
0x180120b8e  lea     rdx, [rbp+57h+var_D0]
0x180120b92  mov     rcx, [rsp+110h+var_D8]
0x180120b97  call    ?GetShapeProps@AElement@Igx@@QEAAXAEAV?$TIgxPropertySet@V?$ShapePropsMethods@V?$ShapePropsDataTransacted_@$0A@@Art@@@Art@@@2@@Z; Igx::AElement::GetShapeProps(Igx::TIgxPropertySet<Art::ShapePropsMethods<Art::ShapePropsDataTransacted_<0>>> &)
0x180120b9c  lea     rcx, [rbp+57h+var_D0]
0x180120ba0  call    ??$IsValid@UPresAssocID@Eps@Igx@@@?$TPropertySet@VElementProps@Igx@@@Ofc@@QEBA_NXZ; Ofc::TPropertySet<Igx::ElementProps>::IsValid<Igx::Eps::PresAssocID>(void)
0x180120ba5  test    al, al
0x180120ba7  jz      short loc_180120BBE
0x180120ba9  lea     rcx, [rbp+57h+var_D0]
0x180120bad  call    ??$Get@UFill@SpPr@Art@@@?$TPropertySet@VShapePropsIDs@Art@@@Ofc@@QEBAAEBVFillProps@Art@@XZ; Ofc::TPropertySet<Art::ShapePropsIDs>::Get<Art::SpPr::Fill>(void)
0x180120bb2  mov     rcx, rax
0x180120bb5  call    ??$Is@UBlipFill@FillPr@Art@@@?$TChoice@VFillPropsDataChoiceIDsImpl@Art@@@Ofc@@QEBA_NXZ; Ofc::TChoice<Art::FillPropsDataChoiceIDsImpl>::Is<Art::FillPr::BlipFill>(void)
0x180120bba  test    al, al
0x180120bbc  jnz     short loc_180120BCA
0x180120bbe  lea     rcx, [rbp+57h+var_D0]
0x180120bc2  call    cs:__imp_??1?$ShapePropsMethods@V?$ShapePropsDataTransacted_@$0A@@Art@@@Art@@QEAA@XZ; Art::ShapePropsMethods<Art::ShapePropsDataTransacted_<0>>::~ShapePropsMethods<Art::ShapePropsDataTransacted_<0>>(void)
0x180120bc8  jmp     short loc_180120B6E
0x180120bca  lea     rcx, [rsp+110h+var_E0]
0x180120bcf  call    cs:__imp_??0CommandState@Art@@QEAA@XZ; Art::CommandState::CommandState(void)
0x180120bd5  or      byte ptr [rax], 1
0x180120bd8  mov     rdx, rax
0x180120bdb  mov     rcx, rsi
0x180120bde  call    cs:__imp_??0CommandState@Art@@QEAA@AEBV01@@Z; Art::CommandState::CommandState(Art::CommandState const &)
0x180120be4  lea     rcx, [rbp+57h+var_D0]
0x180120be8  call    cs:__imp_??1?$ShapePropsMethods@V?$ShapePropsDataTransacted_@$0A@@Art@@@Art@@QEAA@XZ; Art::ShapePropsMethods<Art::ShapePropsDataTransacted_<0>>::~ShapePropsMethods<Art::ShapePropsDataTransacted_<0>>(void)
0x180120bee  xchg    ax, ax
0x180120bf0  mov     rcx, [rsp+110h+var_D8]
0x180120bf5  test    rcx, rcx
0x180120bf8  jz      short loc_180120C04
0x180120bfa  add     rcx, 8
0x180120bfe  call    ?Release@?$TRefCountNoVirt@V?$TRefCount@VCThreadingPolicyMultiThread@Ofc@@@Ofc@@VCThreadingPolicyMultiThread@2@@Ofc@@QEBAXXZ; Ofc::TRefCountNoVirt<Ofc::TRefCount<Ofc::CThreadingPolicyMultiThread>,Ofc::CThreadingPolicyMultiThread>::Release(void)
0x180120c03  nop
0x180120c04  lea     rcx, [rbp+57h+var_A8]
0x180120c08  call    cs:__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x180120c0e  jmp     loc_180120E31
0x180120c13  mov     rcx, [rsp+110h+var_D8]
0x180120c18  test    rcx, rcx
0x180120c1b  jz      short loc_180120C27
0x180120c1d  add     rcx, 8
0x180120c21  call    ?Release@?$TRefCountNoVirt@V?$TRefCount@VCThreadingPolicyMultiThread@Ofc@@@Ofc@@VCThreadingPolicyMultiThread@2@@Ofc@@QEBAXXZ; Ofc::TRefCountNoVirt<Ofc::TRefCount<Ofc::CThreadingPolicyMultiThread>,Ofc::CThreadingPolicyMultiThread>::Release(void)
0x180120c26  nop
0x180120c27  lea     rcx, [rbp+57h+var_A8]
0x180120c2b  call    cs:__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x180120c31  mov     rax, [r14]
0x180120c34  xor     edx, edx
0x180120c36  mov     rcx, r14
0x180120c39  mov     rax, [rax+0D8h]
0x180120c40  call    cs:__guard_dispatch_icall_fptr
0x180120c46  test    al, al
0x180120c48  jnz     loc_180120E04
0x180120c4e  mov     r8, r14
0x180120c51  xor     edx, edx
0x180120c53  lea     rcx, [rbp+57h+var_A8]
0x180120c57  call    ??0CSelectionIter@Igx@@QEAA@W4ElementSelectionType@1@PEBVAElementSelectionInfo@1@@Z; Igx::CSelectionIter::CSelectionIter(Igx::ElementSelectionType,Igx::AElementSelectionInfo const *)
0x180120c5c  nop
0x180120c5d  mov     [rsp+110h+var_D8], 0
0x180120c66  lea     r12, ??_7CBreadthIterator@Igx@@6B@; const Igx::CBreadthIterator::`vftable'
0x180120c6d  lea     rdx, [rsp+110h+var_D8]
0x180120c72  lea     rcx, [rbp+57h+var_A8]
0x180120c76  call    ?Next@CSelectionIter@Igx@@QEAA_NAEAV?$TCntPtr@VAElement@Igx@@@Ofc@@@Z; Igx::CSelectionIter::Next(Ofc::TCntPtr<Igx::AElement> &)
0x180120c7b  test    al, al
0x180120c7d  jz      loc_180120DE6
0x180120c83  mov     rcx, [rsp+110h+var_D8]
0x180120c88  mov     rax, [rcx]
0x180120c8b  mov     rax, [rax+90h]
0x180120c92  call    cs:__guard_dispatch_icall_fptr
0x180120c98  test    al, al
0x180120c9a  jz      short loc_180120C6D
0x180120c9c  mov     [rsp+110h+var_F0], 0; int
0x180120ca4  mov     r9d, 200h
0x180120caa  mov     r8d, 8
0x180120cb0  lea     rdx, [rsp+110h+var_D8]
0x180120cb5  lea     rcx, [rbp+57h+var_90]; this
0x180120cb9  call    ??0CBreadthIterator@Igx@@QEAA@AEBV?$TCntPtr@VAElement@Igx@@@Ofc@@W4RelationshipType@1@W4ElementType@1@J@Z; Igx::CBreadthIterator::CBreadthIterator(Ofc::TCntPtr<Igx::AElement> const &,Igx::RelationshipType,Igx::ElementType,long)
0x180120cbe  nop
0x180120cbf  nop
0x180120cc0  mov     dl, 1; bool
0x180120cc2  lea     rcx, [rbp+57h+var_90]; this
0x180120cc6  call    ?Step@ARelationshipIterator@Igx@@AEAA_N_N@Z; Igx::ARelationshipIterator::Step(bool)
0x180120ccb  test    al, al
0x180120ccd  jz      loc_180120D6C
0x180120cd3  mov     [rbp+57h+var_B8], 0
0x180120cdb  lea     rdx, [rbp+57h+var_B8]
0x180120cdf  lea     rcx, [rbp+57h+var_90]
0x180120ce3  call    ?Relationship@ARelationshipIterator@Igx@@QEBA_NAEAV?$TCntPtr@VARelationship@Igx@@@Ofc@@@Z; Igx::ARelationshipIterator::Relationship(Ofc::TCntPtr<Igx::ARelationship> &)
0x180120ce8  mov     [rbp+57h+var_B0], 0
0x180120cf0  lea     rdx, [rbp+57h+var_B0]
0x180120cf4  mov     rbx, [rbp+57h+var_B8]
0x180120cf8  mov     rcx, rbx
0x180120cfb  call    ?GetDestElement@ARelationship@Igx@@QEBAXAEAV?$TCntPtr@VAElement@Igx@@@Ofc@@@Z; Igx::ARelationship::GetDestElement(Ofc::TCntPtr<Igx::AElement> &)
0x180120d00  lea     rcx, [rbp+57h+var_D0]
0x180120d04  call    cs:__imp_??0?$ShapePropsMethods@V?$ShapePropsDataTransacted_@$0A@@Art@@@Art@@QEAA@XZ; Art::ShapePropsMethods<Art::ShapePropsDataTransacted_<0>>::ShapePropsMethods<Art::ShapePropsDataTransacted_<0>>(void)
0x180120d0a  lea     rdx, [rbp+57h+var_D0]
0x180120d0e  mov     rdi, [rbp+57h+var_B0]
0x180120d12  mov     rcx, rdi
0x180120d15  call    ?GetShapeProps@AElement@Igx@@QEAAXAEAV?$TIgxPropertySet@V?$ShapePropsMethods@V?$ShapePropsDataTransacted_@$0A@@Art@@@Art@@@2@@Z; Igx::AElement::GetShapeProps(Igx::TIgxPropertySet<Art::ShapePropsMethods<Art::ShapePropsDataTransacted_<0>>> &)
0x180120d1a  lea     rcx, [rbp+57h+var_D0]
0x180120d1e  call    ??$IsValid@UPresAssocID@Eps@Igx@@@?$TPropertySet@VElementProps@Igx@@@Ofc@@QEBA_NXZ; Ofc::TPropertySet<Igx::ElementProps>::IsValid<Igx::Eps::PresAssocID>(void)
0x180120d23  test    al, al
0x180120d25  jz      short loc_180120D3C
0x180120d27  lea     rcx, [rbp+57h+var_D0]
0x180120d2b  call    ??$Get@UFill@SpPr@Art@@@?$TPropertySet@VShapePropsIDs@Art@@@Ofc@@QEBAAEBVFillProps@Art@@XZ; Ofc::TPropertySet<Art::ShapePropsIDs>::Get<Art::SpPr::Fill>(void)
0x180120d30  mov     rcx, rax
0x180120d33  call    ??$Is@UBlipFill@FillPr@Art@@@?$TChoice@VFillPropsDataChoiceIDsImpl@Art@@@Ofc@@QEBA_NXZ; Ofc::TChoice<Art::FillPropsDataChoiceIDsImpl>::Is<Art::FillPr::BlipFill>(void)
0x180120d38  test    al, al
0x180120d3a  jnz     short loc_180120D7E
0x180120d3c  lea     rcx, [rbp+57h+var_D0]
0x180120d40  call    cs:__imp_??1?$ShapePropsMethods@V?$ShapePropsDataTransacted_@$0A@@Art@@@Art@@QEAA@XZ; Art::ShapePropsMethods<Art::ShapePropsDataTransacted_<0>>::~ShapePropsMethods<Art::ShapePropsDataTransacted_<0>>(void)
0x180120d46  test    rdi, rdi
0x180120d49  jz      short loc_180120D55
0x180120d4b  lea     rcx, [rdi+8]
0x180120d4f  call    ?Release@?$TRefCountNoVirt@V?$TRefCount@VCThreadingPolicyMultiThread@Ofc@@@Ofc@@VCThreadingPolicyMultiThread@2@@Ofc@@QEBAXXZ; Ofc::TRefCountNoVirt<Ofc::TRefCount<Ofc::CThreadingPolicyMultiThread>,Ofc::CThreadingPolicyMultiThread>::Release(void)
0x180120d54  nop
0x180120d55  test    rbx, rbx
0x180120d58  jz      loc_180120CC0
0x180120d5e  lea     rcx, [rbx+8]
0x180120d62  call    ?Release@?$TRefCountNoVirt@V?$TRefCount@VCThreadingPolicyMultiThread@Ofc@@@Ofc@@VCThreadingPolicyMultiThread@2@@Ofc@@QEBAXXZ; Ofc::TRefCountNoVirt<Ofc::TRefCount<Ofc::CThreadingPolicyMultiThread>,Ofc::CThreadingPolicyMultiThread>::Release(void)
0x180120d67  jmp     loc_180120CC0
0x180120d6c  mov     [rbp+57h+var_90], r12
0x180120d70  lea     rcx, [rbp+57h+var_90]; this
0x180120d74  call    ??1ARelationshipIterator@Igx@@UEAA@XZ; Igx::ARelationshipIterator::~ARelationshipIterator(void)
0x180120d79  jmp     loc_180120C6D
0x180120d7e  lea     rcx, [rsp+110h+var_E0]
0x180120d83  call    cs:__imp_??0CommandState@Art@@QEAA@XZ; Art::CommandState::CommandState(void)
0x180120d89  or      byte ptr [rax], 1
0x180120d8c  mov     rdx, rax
0x180120d8f  mov     rcx, rsi
0x180120d92  call    cs:__imp_??0CommandState@Art@@QEAA@AEBV01@@Z; Art::CommandState::CommandState(Art::CommandState const &)
0x180120d98  lea     rcx, [rbp+57h+var_D0]
0x180120d9c  call    cs:__imp_??1?$ShapePropsMethods@V?$ShapePropsDataTransacted_@$0A@@Art@@@Art@@QEAA@XZ; Art::ShapePropsMethods<Art::ShapePropsDataTransacted_<0>>::~ShapePropsMethods<Art::ShapePropsDataTransacted_<0>>(void)
0x180120da2  test    rdi, rdi
0x180120da5  jz      short loc_180120DB1
0x180120da7  lea     rcx, [rdi+8]
0x180120dab  call    ?Release@?$TRefCountNoVirt@V?$TRefCount@VCThreadingPolicyMultiThread@Ofc@@@Ofc@@VCThreadingPolicyMultiThread@2@@Ofc@@QEBAXXZ; Ofc::TRefCountNoVirt<Ofc::TRefCount<Ofc::CThreadingPolicyMultiThread>,Ofc::CThreadingPolicyMultiThread>::Release(void)
0x180120db0  nop
0x180120db1  test    rbx, rbx
0x180120db4  jz      short loc_180120DC0
0x180120db6  lea     rcx, [rbx+8]
0x180120dba  call    ?Release@?$TRefCountNoVirt@V?$TRefCount@VCThreadingPolicyMultiThread@Ofc@@@Ofc@@VCThreadingPolicyMultiThread@2@@Ofc@@QEBAXXZ; Ofc::TRefCountNoVirt<Ofc::TRefCount<Ofc::CThreadingPolicyMultiThread>,Ofc::CThreadingPolicyMultiThread>::Release(void)
0x180120dbf  nop
0x180120dc0  mov     [rbp+57h+var_90], r12
0x180120dc4  lea     rcx, [rbp+57h+var_90]; this
0x180120dc8  call    ??1ARelationshipIterator@Igx@@UEAA@XZ; Igx::ARelationshipIterator::~ARelationshipIterator(void)
0x180120dcd  mov     rcx, [rsp+110h+var_D8]
0x180120dd2  test    rcx, rcx
0x180120dd5  jz      short loc_180120DE1
0x180120dd7  add     rcx, 8
0x180120ddb  call    ?Release@?$TRefCountNoVirt@V?$TRefCount@VCThreadingPolicyMultiThread@Ofc@@@Ofc@@VCThreadingPolicyMultiThread@2@@Ofc@@QEBAXXZ; Ofc::TRefCountNoVirt<Ofc::TRefCount<Ofc::CThreadingPolicyMultiThread>,Ofc::CThreadingPolicyMultiThread>::Release(void)
0x180120de0  nop
0x180120de1  jmp     loc_180120C04
0x180120de6  mov     rcx, [rsp+110h+var_D8]
0x180120deb  test    rcx, rcx
0x180120dee  jz      short loc_180120DFA
0x180120df0  add     rcx, 8
0x180120df4  call    ?Release@?$TRefCountNoVirt@V?$TRefCount@VCThreadingPolicyMultiThread@Ofc@@@Ofc@@VCThreadingPolicyMultiThread@2@@Ofc@@QEBAXXZ; Ofc::TRefCountNoVirt<Ofc::TRefCount<Ofc::CThreadingPolicyMultiThread>,Ofc::CThreadingPolicyMultiThread>::Release(void)
0x180120df9  nop
0x180120dfa  lea     rcx, [rbp+57h+var_A8]
0x180120dfe  call    cs:__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x180120e04  lea     rdx, [rsp+110h+var_E0]; bool *
0x180120e09  mov     rcx, r14; struct Igx::AElementSelectionInfo *
0x180120e0c  call    ?VerifySelection@CDelSelectionCmd@Igx@@CA_NPEBVAElementSelectionInfo@2@AEA_N@Z; Igx::CDelSelectionCmd::VerifySelection(Igx::AElementSelectionInfo const *,bool &)
0x180120e11  test    al, al
0x180120e13  jz      short loc_180120E28
0x180120e15  lea     rcx, [rsp+110h+var_E0]
0x180120e1a  call    cs:__imp_??0CommandState@Art@@QEAA@XZ; Art::CommandState::CommandState(void)
0x180120e20  or      byte ptr [rax], 1
0x180120e23  jmp     loc_180120B03
0x180120e28  mov     rcx, rsi
0x180120e2b  call    cs:__imp_??0CommandState@Art@@QEAA@XZ; Art::CommandState::CommandState(void)
0x180120e31  mov     rax, rsi
0x180120e34  mov     rcx, [rbp+57h+var_30]
0x180120e38  xor     rcx, rsp; StackCookie
0x180120e3b  call    __security_check_cookie
0x180120e40  mov     rbx, [rsp+110h+arg_10]
0x180120e48  add     rsp, 0F0h
0x180120e4f  pop     r14
0x180120e51  pop     r12
0x180120e53  pop     rdi
0x180120e54  pop     rsi
0x180120e55  pop     rbp
0x180120e56  retn
```
