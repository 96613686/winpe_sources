# Art::ViewElement::GetFastAccNode(Ofc::TCntPtr<Art::FastAccNode> &,Art::IProtectViewAccess *)

- ea: `0x180221d30`
- end: `0x180222675`
- name: `?GetFastAccNode@ViewElement@Art@@QEAAJAEAV?$TCntPtr@UFastAccNode@Art@@@Ofc@@PEAVIProtectViewAccess@2@@Z`
- size: `2373`
- prototype: `__int64 __fastcall(Art::ViewElement *this)`
- caller_count: `22`
- callee_count: `27`
- tags: ``

## callers

- `0x18001f6c0`
- `0x18012ff50`
- `0x180221498`
- `0x1802226c8`
- `0x180411d60`
- `0x18046acf0`
- `0x1804fb340`
- `0x180507ca0`
- `0x18057f270`
- `0x1805810c0`
- `0x180585cd0`
- `0x180613fa0`
- `0x18063f060`
- `0x1806432c0`
- `0x18068702c`
- `0x1806a2ea0`
- `0x18079c850`
- `0x1807bd580`
- `0x1807c9620`
- `0x1807c99e0`
- `0x1807cfad4`
- `0x180852730`

## callees

- `0x18001daf0`
- `0x18001df54`
- `0x1800445c0`
- `0x180059cbc`
- `0x1800659a0`
- `0x180071000`
- `0x180071720`
- `0x180072540`
- `0x1800ce118`
- `0x180124150`
- `0x1801c0940`
- `0x180221d30`
- `0x1802efaf0`
- `0x1802fb8e0`
- `0x1803b6f90`
- `0x180469fc4`
- `0x18046acac`
- `0x1804ac138`
- `0x1804fc5c4`
- `0x18054a960`
- `0x18063cd4c`
- `0x180678ba8`
- `0x1806a5054`
- `0x1806a5084`
- `0x1806a51d0`
- `0x1806a57c4`
- `0x1806a59d4`

## import_xrefs

- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x180222242`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x1802222b7`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x180222242`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x1802222b7`
- `Mso20Win32Client!__imp_?GetCurrentExecutionContext@ApplicationModel@Mso@@YA?AV?$TCntPtr@UIExecutionContext@ApplicationModel@Mso@@@2@XZ` at `0x180221e12`
- `Mso20Win32Client!__imp_?GetCurrentExecutionContext@ApplicationModel@Mso@@YA?AV?$TCntPtr@UIExecutionContext@ApplicationModel@Mso@@@2@XZ` at `0x180221e12`
- `Mso20Win32Client!__imp_?VerifyUIThread@ApplicationModel@Mso@@YA_NPEBUIExecutionContext@12@@Z` at `0x180221e50`
- `Mso20Win32Client!__imp_?VerifyUIThread@ApplicationModel@Mso@@YA_NPEBUIExecutionContext@12@@Z` at `0x180221ebf`
- `Mso20Win32Client!__imp_?VerifyUIThread@ApplicationModel@Mso@@YA_NPEBUIExecutionContext@12@@Z` at `0x180221e50`
- `Mso20Win32Client!__imp_?VerifyUIThread@ApplicationModel@Mso@@YA_NPEBUIExecutionContext@12@@Z` at `0x180221ebf`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x180222504`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x180222504`
- `Mso20Win32Client!__imp_??0CurrentContextHolder@FastModel@@QEAA@AEAVContext@1@_N@Z` at `0x18022212f`
- `Mso20Win32Client!__imp_??0CurrentContextHolder@FastModel@@QEAA@AEAVContext@1@_N@Z` at `0x18022212f`
- `Mso20Win32Client!__imp_?VerifyAppThread@ApplicationModel@Mso@@YA_NPEBUIExecutionContext@12@@Z` at `0x180221e62`
- `Mso20Win32Client!__imp_?VerifyAppThread@ApplicationModel@Mso@@YA_NPEBUIExecutionContext@12@@Z` at `0x180221e62`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1802224f1`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1802224f1`
- `Mso20Win32Client!__imp_??1CurrentContextHolder@FastModel@@QEAA@XZ` at `0x1802225fb`
- `Mso20Win32Client!__imp_??1CurrentContextHolder@FastModel@@QEAA@XZ` at `0x1802225fb`

## pseudocode

```c
__int64 __fastcall Art::ViewElement::GetFastAccNode(Art::ViewElement *this, __int64 a2, __int64 a3)
{
  char v5; // di
  struct Art::ViewElement *v6; // rdx
  struct Ofc::CProxyPtrImpl *v7; // rax
  void *Checked; // rax
  const struct Mso::ApplicationModel::IExecutionContext *v10; // rdx
  const struct Mso::ApplicationModel::IExecutionContext *v11; // rdx
  _QWORD *v12; // r15
  const struct Mso::ApplicationModel::IExecutionContext *v13; // rdx
  char v14; // r12
  char v15; // bl
  Ofc::CProxyPtrImpl **v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  Ofc::CProxyPtrImpl **v19; // rax
  Ofc::CProxyPtrImpl *v20; // rbx
  __int64 v21; // rax
  __int64 v22; // rax
  int v23; // ebx
  __int64 v24; // rax
  struct FastModel::Context *v25; // rax
  struct Ofc::CProxyPtrImpl **View; // rax
  __int64 v27; // r8
  __int64 *v28; // rax
  struct Art::ViewElement *v29; // rdx
  __int64 v30; // rax
  __int64 *v31; // rax
  __int64 v32; // rdx
  char *v33; // rcx
  __int64 v34; // rax
  __int64 v35; // rdi
  void (__fastcall *v36)(__int64, __int64); // rbx
  __int64 v37; // rdx
  __int64 v38; // rcx
  HINSTANCE HinstIntl; // rax
  __int64 v40; // rdx
  __int64 v41; // rax
  __int64 v42; // rdi
  void (__fastcall *v43)(__int64, _QWORD); // rbx
  __int64 v44; // rdx
  __int64 v45; // rcx
  HINSTANCE v46; // rax
  _QWORD *v47; // rax
  __int64 v48; // rax
  __int64 v49; // rcx
  __int64 v50; // rdx
  __int64 (__fastcall *v51)(Art::ViewElement *, struct Ofc::CProxyPtrImpl **, __int64, __int64, __int64); // rdi
  __int64 v52; // rbx
  __int64 v53; // rax
  __int64 v54; // rdx
  char *v55; // rcx
  unsigned __int64 v56; // rdx
  unsigned int v57; // r8d
  volatile signed __int32 *v58; // rcx
  void *v59; // rax
  __int64 (__fastcall ***v60)(_QWORD, Ofc::CProxyPtrImpl **, _QWORD); // rcx
  struct Ofc::CProxyPtrImpl **v61; // rax
  _QWORD *v62; // rax
  unsigned int v63; // r8d
  _QWORD *v64; // rbx
  __int64 v65; // rcx
  Ofc::CProxyPtrImpl *v66; // rax
  int *v67; // rdi
  void *v68; // rax
  void *v69; // rax
  __int64 v70; // rcx
  void (__fastcall *v71)(__int64, Ofc::CProxyPtrImpl **); // r8
  struct Ofc::CProxyPtrImpl *v72; // [rsp+30h] [rbp-98h] BYREF
  Ofc::CProxyPtrImpl *v73; // [rsp+38h] [rbp-90h] BYREF
  Ofc::CProxyPtrImpl *v74; // [rsp+40h] [rbp-88h] BYREF
  __int64 v75; // [rsp+48h] [rbp-80h] BYREF
  struct Ofc::CProxyPtrImpl *v76; // [rsp+50h] [rbp-78h] BYREF
  struct Ofc::CProxyPtrImpl *v77; // [rsp+58h] [rbp-70h] BYREF
  Ofc::CProxyPtrImpl *v78; // [rsp+60h] [rbp-68h] BYREF
  void **v79; // [rsp+68h] [rbp-60h] BYREF
  __int64 (__fastcall ***v80)(_QWORD, Ofc::CProxyPtrImpl **, _QWORD); // [rsp+70h] [rbp-58h]
  _BYTE v81[80]; // [rsp+78h] [rbp-50h] BYREF
  Mso::ApplicationModel *v82; // [rsp+D0h] [rbp+8h] BYREF
  __int64 v83; // [rsp+E0h] [rbp+18h]
  struct Ofc::CProxyPtrImpl *v84; // [rsp+E8h] [rbp+20h] BYREF

  v83 = a3;
  v5 = 0;
  LODWORD(v82) = 0;
  if ( (*((_BYTE *)this + 192) & 4) == 0
    && !(*(unsigned __int8 (__fastcall **)(Art::ViewElement *))(*(_QWORD *)this + 1192LL))(this)
    || !(*(unsigned __int8 (__fastcall **)(Art::ViewElement *))(*(_QWORD *)this + 720LL))(this)
    || Art::ViewElement::FInvisible(this) && !Art::FShouldGenerateNodeForInvisibleObject(this, v6) )
  {
    Ofc::TCntPtr<FastAcc::Abstract::ITextApp>::operator=(a2, 0);
    return 0;
  }
  v7 = Ofc::CProxyPtrImpl::CheckedStrongAddRef(*((struct Ofc::CProxyPtrImpl **)this + 20));
  v84 = v7;
  if ( *((_QWORD *)v7 + 2) )
  {
    Checked = Ofc::CProxyPtrImpl::GetChecked(v7);
    if ( (*(unsigned __int8 (__fastcall **)(void *, Art::ViewElement *))(*(_QWORD *)Checked + 200LL))(Checked, this) )
    {
      Ofc::TCntPtr<FastAcc::Abstract::ITextApp>::operator=(a2, 0);
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v84);
      return 0;
    }
  }
  Mso::ApplicationModel::GetCurrentExecutionContext(&v82);
  if ( !v82 || !Mso::ApplicationModel::VerifyUIThread(v82, v10) && !Mso::ApplicationModel::VerifyAppThread(v82, v11) )
  {
    Ofc::TCntPtr<FastAcc::Abstract::ITextApp>::operator=(a2, 0);
    Mso::TCntPtr<Art::Resource>::Clear(&v82);
    Ofc::CProxyPtrImpl::DtorStrongRelease(&v84);
    return 0;
  }
  v12 = (_QWORD *)((char *)this + 128);
  if ( !*((_QWORD *)this + 16) )
  {
    v75 = 0;
    v23 = (*(__int64 (__fastcall **)(Art::ViewElement *, __int64 *))(*(_QWORD *)this + 704LL))(this, &v75);
    if ( v23 < 0 || !v75 || (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v75 + 48LL))(v75) == 3 )
    {
      Mso::TCntPtr<Art::Resource>::Clear(&v82);
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v84);
      if ( v23 == -2147467260 )
        return 2147500036LL;
      else
        return 2147500037LL;
    }
    v24 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v75 + 32LL))(v75);
    v25 = (struct FastModel::Context *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v24 + 32LL))(v24);
    FastModel::CurrentContextHolder::CurrentContextHolder((FastModel::CurrentContextHolder *)v81, v25, 1);
    View = (struct Ofc::CProxyPtrImpl **)Art::ViewElement::GetView(this);
    v78 = Ofc::CProxyPtrImpl::CheckedStrongAddRef(*View);
    if ( Art::ViewElement::FMinimalDecorativeFastAccNode(this) )
    {
      v27 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v75 + 32LL))(v75);
      v28 = (__int64 *)Art::ViewElement::CreateEmptyFastAccNode(this, &v72, v27, v83);
    }
    else
    {
      if ( Art::ViewElement::FInvisible(this)
        && Art::FShouldGenerateNodeForInvisibleObject(this, v29)
        && Ofc::runtime_cast<Dr::InkViewElement *>(this) )
      {
        v30 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v75 + 32LL))(v75);
        v31 = (__int64 *)Art::ViewElement::CreateEmptyFastAccNode(this, &v72, v30, v83);
        v32 = *v31;
        *v31 = 0;
        Ofc::TCntPtr<Art::FastAccNode>::Assign((char *)this + 128, v32);
        if ( v72 )
        {
          v33 = (char *)v72 + *(int *)(*((_QWORD *)v72 + 1) + 4LL) + 8;
          (*(void (__fastcall **)(char *))(*(_QWORD *)v33 + 16LL))(v33);
        }
        v34 = (*(__int64 (__fastcall **)(_QWORD, Ofc::CProxyPtrImpl **))(*(_QWORD *)*v12 + 208LL))(*v12, &v73);
        v35 = Mso::TCntPtr<Art::AugLoop::AppAugmentationStatefulRuntime>::operator->(v34);
        v36 = *(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v35 + 504LL);
        HinstIntl = (HINSTANCE)MsoGetHinstIntl(v38, v37);
        v40 = *(_QWORD *)Ofc::CVarStr::CVarStr((Ofc::CVarStr *)&v72, HinstIntl, 293591054);
        v36(v35, v40);
        Ofc::CVarStr::ReleaseBuffer((Ofc::CVarStr *)&v72);
        Mso::TCntPtr<Art::CMetroProgress>::Clear(&v73);
        v41 = (*(__int64 (__fastcall **)(_QWORD, Ofc::CProxyPtrImpl **))(*(_QWORD *)*v12 + 208LL))(*v12, &v73);
        v42 = Mso::TCntPtr<Art::AugLoop::AppAugmentationStatefulRuntime>::operator->(v41);
        v43 = *(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v42 + 312LL);
        v46 = (HINSTANCE)MsoGetHinstIntl(v45, v44);
        v47 = (_QWORD *)Ofc::CVarStr::CVarStr((Ofc::CVarStr *)&v72, v46, -588823970);
        v43(v42, *v47);
        Ofc::CVarStr::ReleaseBuffer((Ofc::CVarStr *)&v72);
        Mso::TCntPtr<Art::CMetroProgress>::Clear(&v73);
        v48 = (*(__int64 (__fastcall **)(_QWORD, struct Ofc::CProxyPtrImpl **))(*(_QWORD *)*v12 + 208LL))(*v12, &v72);
        v49 = Mso::TCntPtr<Art::AugLoop::AppAugmentationStatefulRuntime>::operator->(v48);
        LOBYTE(v50) = 1;
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v49 + 376LL))(v49, v50);
        Mso::TCntPtr<Art::CMetroProgress>::Clear(&v72);
        goto LABEL_56;
      }
      v51 = *(__int64 (__fastcall **)(Art::ViewElement *, struct Ofc::CProxyPtrImpl **, __int64, __int64, __int64))(*(_QWORD *)this + 728LL);
      v52 = v75;
      v53 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v75 + 32LL))(v75);
      v28 = (__int64 *)v51(this, &v72, v53, v52, v83);
    }
    v54 = *v28;
    *v28 = 0;
    Ofc::TCntPtr<Art::FastAccNode>::Assign((char *)this + 128, v54);
    if ( v72 )
    {
      v55 = (char *)v72 + *(int *)(*((_QWORD *)v72 + 1) + 4LL) + 8;
      (*(void (__fastcall **)(char *))(*(_QWORD *)v55 + 16LL))(v55);
    }
LABEL_56:
    if ( !*v12 )
      Ofc::CInvalidOperationException::ThrowTag(0x140A653u);
    (*(void (__fastcall **)(Art::ViewElement *, __int64))(*(_QWORD *)this + 736LL))(this, v75);
    Ofc::TCntPtr<FastAcc::Abstract::ITextApp>::operator=(a2, *v12);
    v76 = (struct Ofc::CProxyPtrImpl *)&`Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_proxyPtrSentinel;
    if ( *((_QWORD *)v78 + 2) )
    {
      v58 = (volatile signed __int32 *)*((_QWORD *)Ofc::CProxyPtrImpl::GetChecked(v78) + 7);
      if ( *((_DWORD *)v58 + 1) != 0x80000000 )
        _InterlockedAdd(v58 + 1, 1u);
      v72 = (struct Ofc::CProxyPtrImpl *)v58;
      v73 = Ofc::CProxyPtrImpl::CheckedStrongAddRef((struct Ofc::CProxyPtrImpl *)v58);
      Ofc::CProxyPtrImpl::DtorWeakRelease(&v72);
      if ( *((_QWORD *)v73 + 2) )
      {
        v80 = 0;
        v79 = &Art::THostInterfaceInfo<Art::FastAccNodeObserverFactory>::`vftable';
        v59 = Ofc::CProxyPtrImpl::GetChecked(v73);
        if ( (*(unsigned __int8 (__fastcall **)(void *, void ***))(*(_QWORD *)v59 + 16LL))(v59, &v79) )
        {
          v60 = v80;
          if ( !v80 )
            Ofc::CObjectExpiredException::ThrowTag(0x134F08Cu);
          v61 = (struct Ofc::CProxyPtrImpl **)(**v60)(v60, &v74, *v12);
          Ofc::CProxyPtrImpl::StrongMoveAssign(&v76, v61);
          Ofc::CProxyPtrImpl::DtorStrongRelease(&v74);
        }
      }
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v73);
    }
    v62 = Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0x10, v56, v57);
    v64 = v62;
    if ( v62 )
    {
      *v62 = &Art::ViewElementFastAccNodeObserver::`vftable';
      v65 = *((_QWORD *)this + 4);
      if ( *(_DWORD *)(v65 + 4) != 0x80000000 )
        _InterlockedAdd((volatile signed __int32 *)(v65 + 4), 1u);
      v62[1] = v65;
    }
    else
    {
      v64 = 0;
    }
    if ( v64 )
    {
      v66 = (Ofc::CProxyPtrImpl *)Mso::Memory::AllocateEx((Mso::Memory *)0x18, 0, v63);
      v67 = (int *)v66;
      if ( !v66 )
      {
        CrashWithRecoveryOnOOM(0x1E000188u);
        __debugbreak();
      }
      Ofc::CProxyPtrImpl::CProxyPtrImpl(v66, Ofc::TDeleteFromProxy<Art::UnsavedEnterpriseDocumentProtector>);
      *((_QWORD *)v67 + 2) = v64;
    }
    else
    {
      v67 = &`Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_proxyPtrSentinel;
    }
    v77 = (struct Ofc::CProxyPtrImpl *)v67;
    if ( *((_QWORD *)v76 + 2) )
    {
      Ofc::MakeOwningPtr<Art::AggregateFastAccNodeObserver,>(&v74);
      v68 = Ofc::CProxyPtrImpl::GetChecked(v74);
      Art::AggregateFastAccNodeObserver::AddObserver(v68, &v77);
      v69 = Ofc::CProxyPtrImpl::GetChecked(v74);
      Art::AggregateFastAccNodeObserver::AddObserver(v69, &v76);
      v70 = *v12;
      v71 = *(void (__fastcall **)(__int64, Ofc::CProxyPtrImpl **))(*(_QWORD *)*v12 + 240LL);
      v73 = v74;
      v74 = (Ofc::CProxyPtrImpl *)&`Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_proxyPtrSentinel;
      v71(v70, &v73);
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v73);
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v74);
    }
    else
    {
      (*(void (__fastcall **)(_QWORD, struct Ofc::CProxyPtrImpl **))(*(_QWORD *)*v12 + 240LL))(*v12, &v77);
    }
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v12 + 176LL))(*v12);
    Ofc::CProxyPtrImpl::DtorStrongRelease(&v77);
    Ofc::CProxyPtrImpl::DtorStrongRelease(&v76);
    Ofc::CProxyPtrImpl::DtorStrongRelease(&v78);
    FastModel::CurrentContextHolder::~CurrentContextHolder((FastModel::CurrentContextHolder *)v81);
    Mso::TCntPtr<Art::Resource>::Clear(&v82);
    Ofc::CProxyPtrImpl::DtorStrongRelease(&v84);
    return 0;
  }
  Ofc::TCntPtr<FastAcc::Abstract::ITextApp>::operator=(a2, *v12);
  if ( !v82 || !Mso::ApplicationModel::VerifyUIThread(v82, v13) )
  {
    v14 = 1;
    goto LABEL_19;
  }
  v14 = 1;
  v5 = 1;
  if ( !*(_QWORD *)(*(__int64 (__fastcall **)(_QWORD, Ofc::CProxyPtrImpl **))(*(_QWORD *)*v12 + 208LL))(*v12, &v73) )
  {
LABEL_19:
    v15 = 0;
    goto LABEL_20;
  }
  v15 = 1;
LABEL_20:
  if ( (v5 & 1) != 0 )
  {
    v5 &= ~1u;
    Mso::TCntPtr<Art::CMetroProgress>::Clear(&v73);
  }
  v16 = (Ofc::CProxyPtrImpl **)(*(__int64 (__fastcall **)(_QWORD, struct Ofc::CProxyPtrImpl **))(*(_QWORD *)*v12 + 208LL))(
                                 *v12,
                                 &v72);
  if ( v15 )
  {
    v17 = Mso::TCntPtr<Art::AugLoop::AppAugmentationStatefulRuntime>::operator->(v16);
    v18 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 40LL))(v17);
    v19 = (Ofc::CProxyPtrImpl **)qi_cast_or_crash<FastAcc::Abstract::IElement,FastAcc::Abstract::IObject>(&v73, v18);
    v20 = *v19;
    *v19 = 0;
    v74 = v20;
    Mso::TCntPtr<Art::CMetroProgress>::Clear(&v73);
  }
  else
  {
    v20 = *v16;
    *v16 = 0;
    v74 = v20;
  }
  Mso::TCntPtr<Art::CMetroProgress>::Clear(&v72);
  if ( !v20
    || (v21 = Mso::TCntPtr<Art::AugLoop::AppAugmentationStatefulRuntime>::operator->(&v74),
        v5 |= 2u,
        *(_QWORD *)(*(__int64 (__fastcall **)(__int64, struct Ofc::CProxyPtrImpl **))(*(_QWORD *)v21 + 560LL))(
                     v21,
                     &v72))
    || (v22 = Mso::TCntPtr<Art::AugLoop::AppAugmentationStatefulRuntime>::operator->(&v74),
        (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v22 + 48LL))(v22) == 3) )
  {
    v14 = 0;
  }
  if ( (v5 & 2) != 0 )
    Mso::TCntPtr<Art::CMetroProgress>::Clear(&v72);
  if ( !v14 )
    goto LABEL_39;
  v73 = 0;
  if ( (*(int (__fastcall **)(Art::ViewElement *, Ofc::CProxyPtrImpl **))(*(_QWORD *)this + 704LL))(this, &v73) < 0
    || !v73 )
  {
    goto LABEL_39;
  }
  if ( (*(unsigned int (__fastcall **)(Ofc::CProxyPtrImpl *))(*(_QWORD *)v73 + 48LL))(v73) != 3 )
  {
    (*(void (__fastcall **)(Art::ViewElement *, Ofc::CProxyPtrImpl *))(*(_QWORD *)this + 736LL))(this, v73);
LABEL_39:
    if ( v20 )
      (*(void (__fastcall **)(Ofc::CProxyPtrImpl *))(*(_QWORD *)v20 + 16LL))(v20);
    Mso::TCntPtr<Art::Resource>::Clear(&v82);
    Ofc::CProxyPtrImpl::DtorStrongRelease(&v84);
    return 0;
  }
  if ( v20 )
    (*(void (__fastcall **)(Ofc::CProxyPtrImpl *))(*(_QWORD *)v20 + 16LL))(v20);
  Mso::TCntPtr<Art::Resource>::Clear(&v82);
  Ofc::CProxyPtrImpl::DtorStrongRelease(&v84);
  return 2147500037LL;
}

```

## disassembly

```asm
0x180221d30  mov     [rsp+arg_10], r8
0x180221d35  push    rbx
0x180221d36  push    rsi
0x180221d37  push    rdi
0x180221d38  push    r12
0x180221d3a  push    r13
0x180221d3c  push    r14
0x180221d3e  push    r15
0x180221d40  sub     rsp, 90h
0x180221d47  mov     r13, rdx
0x180221d4a  mov     r14, rcx
0x180221d4d  xor     esi, esi
0x180221d4f  mov     edi, esi
0x180221d51  mov     dword ptr [rsp+0C8h+arg_0], esi
0x180221d58  test    byte ptr [rcx+0C0h], 4
0x180221d5f  jnz     short loc_180221D79
0x180221d61  mov     rax, [rcx]
0x180221d64  mov     rax, [rax+4A8h]
0x180221d6b  call    cs:__guard_dispatch_icall_fptr
0x180221d71  test    al, al
0x180221d73  jz      loc_18022264B
0x180221d79  mov     rax, [r14]
0x180221d7c  mov     rcx, r14
0x180221d7f  mov     rax, [rax+2D0h]
0x180221d86  call    cs:__guard_dispatch_icall_fptr
0x180221d8c  test    al, al
0x180221d8e  jz      loc_18022264B
0x180221d94  mov     rcx, r14; this
0x180221d97  call    ?FInvisible@ViewElement@Art@@QEBA_NXZ; Art::ViewElement::FInvisible(void)
0x180221d9c  test    al, al
0x180221d9e  jz      short loc_180221DB0
0x180221da0  mov     rcx, r14; this
0x180221da3  call    ?FShouldGenerateNodeForInvisibleObject@Art@@YA_NPEAVViewElement@1@@Z; Art::FShouldGenerateNodeForInvisibleObject(Art::ViewElement *)
0x180221da8  test    al, al
0x180221daa  jz      loc_18022264B
0x180221db0  mov     rcx, [r14+0A0h]; struct Ofc::CProxyPtrImpl *
0x180221db7  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x180221dbc  mov     [rsp+0C8h+arg_18], rax
0x180221dc4  cmp     [rax+10h], rsi
0x180221dc8  jz      short loc_180221E0A
0x180221dca  mov     rcx, rax; this
0x180221dcd  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x180221dd2  mov     rcx, rax
0x180221dd5  mov     rax, [rax]
0x180221dd8  mov     rdx, r14
0x180221ddb  mov     rax, [rax+0C8h]
0x180221de2  call    cs:__guard_dispatch_icall_fptr
0x180221de8  test    al, al
0x180221dea  jz      short loc_180221E0A
0x180221dec  xor     edx, edx
0x180221dee  mov     rcx, r13
0x180221df1  call    ??4?$TCntPtr@UITextApp@Abstract@FastAcc@@@Ofc@@QEAAAEAV01@PEAUITextApp@Abstract@FastAcc@@@Z; Ofc::TCntPtr<FastAcc::Abstract::ITextApp>::operator=(FastAcc::Abstract::ITextApp *)
0x180221df6  lea     rcx, [rsp+0C8h+arg_18]; struct Ofc::CProxyPtrImpl **
0x180221dfe  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x180221e03  xor     eax, eax
0x180221e05  jmp     loc_180222662
0x180221e0a  lea     rcx, [rsp+0C8h+arg_0]
0x180221e12  call    cs:__imp_?GetCurrentExecutionContext@ApplicationModel@Mso@@YA?AV?$TCntPtr@UIExecutionContext@ApplicationModel@Mso@@@2@XZ; Mso::ApplicationModel::GetCurrentExecutionContext(void)
0x180221e18  mov     rcx, [rsp+0C8h+arg_0]
0x180221e20  test    rcx, rcx
0x180221e23  jnz     short loc_180221E50
0x180221e25  xor     edx, edx
0x180221e27  mov     rcx, r13
0x180221e2a  call    ??4?$TCntPtr@UITextApp@Abstract@FastAcc@@@Ofc@@QEAAAEAV01@PEAUITextApp@Abstract@FastAcc@@@Z; Ofc::TCntPtr<FastAcc::Abstract::ITextApp>::operator=(FastAcc::Abstract::ITextApp *)
0x180221e2f  lea     rcx, [rsp+0C8h+arg_0]; void *
0x180221e37  call    ?Clear@?$TCntPtr@VResource@Art@@@Mso@@QEAAXXZ; Mso::TCntPtr<Art::Resource>::Clear(void)
0x180221e3c  lea     rcx, [rsp+0C8h+arg_18]; struct Ofc::CProxyPtrImpl **
0x180221e44  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x180221e49  xor     eax, eax
0x180221e4b  jmp     loc_180222662
0x180221e50  call    cs:__imp_?VerifyUIThread@ApplicationModel@Mso@@YA_NPEBUIExecutionContext@12@@Z; Mso::ApplicationModel::VerifyUIThread(Mso::ApplicationModel::IExecutionContext const *)
0x180221e56  test    al, al
0x180221e58  jnz     short loc_180221E97
0x180221e5a  mov     rcx, [rsp+0C8h+arg_0]
0x180221e62  call    cs:__imp_?VerifyAppThread@ApplicationModel@Mso@@YA_NPEBUIExecutionContext@12@@Z; Mso::ApplicationModel::VerifyAppThread(Mso::ApplicationModel::IExecutionContext const *)
0x180221e68  test    al, al
0x180221e6a  jnz     short loc_180221E97
0x180221e6c  xor     edx, edx
0x180221e6e  mov     rcx, r13
0x180221e71  call    ??4?$TCntPtr@UITextApp@Abstract@FastAcc@@@Ofc@@QEAAAEAV01@PEAUITextApp@Abstract@FastAcc@@@Z; Ofc::TCntPtr<FastAcc::Abstract::ITextApp>::operator=(FastAcc::Abstract::ITextApp *)
0x180221e76  lea     rcx, [rsp+0C8h+arg_0]; void *
0x180221e7e  call    ?Clear@?$TCntPtr@VResource@Art@@@Mso@@QEAAXXZ; Mso::TCntPtr<Art::Resource>::Clear(void)
0x180221e83  lea     rcx, [rsp+0C8h+arg_18]; struct Ofc::CProxyPtrImpl **
0x180221e8b  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x180221e90  xor     eax, eax
0x180221e92  jmp     loc_180222662
0x180221e97  lea     r15, [r14+80h]
0x180221e9e  cmp     [r15], rsi
0x180221ea1  jz      loc_1802220B1
0x180221ea7  mov     rdx, [r15]
0x180221eaa  mov     rcx, r13
0x180221ead  call    ??4?$TCntPtr@UITextApp@Abstract@FastAcc@@@Ofc@@QEAAAEAV01@PEAUITextApp@Abstract@FastAcc@@@Z; Ofc::TCntPtr<FastAcc::Abstract::ITextApp>::operator=(FastAcc::Abstract::ITextApp *)
0x180221eb2  mov     rcx, [rsp+0C8h+arg_0]
0x180221eba  test    rcx, rcx
0x180221ebd  jz      short loc_180221EF4
0x180221ebf  call    cs:__imp_?VerifyUIThread@ApplicationModel@Mso@@YA_NPEBUIExecutionContext@12@@Z; Mso::ApplicationModel::VerifyUIThread(Mso::ApplicationModel::IExecutionContext const *)
0x180221ec5  test    al, al
0x180221ec7  jz      short loc_180221EF4
0x180221ec9  mov     rcx, [r15]
0x180221ecc  mov     rax, [rcx]
0x180221ecf  lea     rdx, [rsp+0C8h+var_90]
0x180221ed4  mov     rax, [rax+0D0h]
0x180221edb  call    cs:__guard_dispatch_icall_fptr
0x180221ee1  mov     r12d, 1
0x180221ee7  mov     edi, r12d
0x180221eea  cmp     [rax], rsi
0x180221eed  jz      short loc_180221EFA
0x180221eef  mov     bl, r12b
0x180221ef2  jmp     short loc_180221EFD
0x180221ef4  mov     r12d, 1
0x180221efa  mov     bl, sil
0x180221efd  test    r12b, dil
0x180221f00  jz      short loc_180221F0F
0x180221f02  and     edi, 0FFFFFFFEh
0x180221f05  lea     rcx, [rsp+0C8h+var_90]
0x180221f0a  call    ?Clear@?$TCntPtr@VCMetroProgress@Art@@@Mso@@QEAAXXZ; Mso::TCntPtr<Art::CMetroProgress>::Clear(void)
0x180221f0f  mov     rcx, [r15]
0x180221f12  mov     rax, [rcx]
0x180221f15  lea     rdx, [rsp+0C8h+var_98]
0x180221f1a  mov     rax, [rax+0D0h]
0x180221f21  call    cs:__guard_dispatch_icall_fptr
0x180221f27  test    bl, bl
0x180221f29  jz      short loc_180221F67
0x180221f2b  mov     rcx, rax
0x180221f2e  call    ??C?$TCntPtr@VAppAugmentationStatefulRuntime@AugLoop@Art@@@Mso@@QEBAPEAVAppAugmentationStatefulRuntime@AugLoop@Art@@XZ; Mso::TCntPtr<Art::AugLoop::AppAugmentationStatefulRuntime>::operator->(void)
0x180221f33  mov     rcx, rax
0x180221f36  mov     rax, [rax]
0x180221f39  mov     rax, [rax+28h]
0x180221f3d  call    cs:__guard_dispatch_icall_fptr
0x180221f43  mov     rdx, rax
0x180221f46  lea     rcx, [rsp+0C8h+var_90]
0x180221f4b  call    ??$qi_cast_or_crash@UIElement@Abstract@FastAcc@@UIObject@23@@@YA?AV?$TCntPtr@UIElement@Abstract@FastAcc@@@Mso@@PEBUIObject@Abstract@FastAcc@@AEBU_GUID@@@Z; qi_cast_or_crash<FastAcc::Abstract::IElement,FastAcc::Abstract::IObject>(FastAcc::Abstract::IObject const *,_GUID const &)
0x180221f50  mov     rbx, [rax]
0x180221f53  mov     [rax], rsi
0x180221f56  mov     [rsp+0C8h+var_88], rbx
0x180221f5b  lea     rcx, [rsp+0C8h+var_90]
0x180221f60  call    ?Clear@?$TCntPtr@VCMetroProgress@Art@@@Mso@@QEAAXXZ; Mso::TCntPtr<Art::CMetroProgress>::Clear(void)
0x180221f65  jmp     short loc_180221F72
0x180221f67  mov     rbx, [rax]
0x180221f6a  mov     [rax], rsi
0x180221f6d  mov     [rsp+0C8h+var_88], rbx
0x180221f72  lea     rcx, [rsp+0C8h+var_98]
0x180221f77  call    ?Clear@?$TCntPtr@VCMetroProgress@Art@@@Mso@@QEAAXXZ; Mso::TCntPtr<Art::CMetroProgress>::Clear(void)
0x180221f7c  mov     rax, rbx
0x180221f7f  test    rax, rax
0x180221f82  jz      short loc_180221FCD
0x180221f84  lea     rcx, [rsp+0C8h+var_88]
0x180221f89  call    ??C?$TCntPtr@VAppAugmentationStatefulRuntime@AugLoop@Art@@@Mso@@QEBAPEAVAppAugmentationStatefulRuntime@AugLoop@Art@@XZ; Mso::TCntPtr<Art::AugLoop::AppAugmentationStatefulRuntime>::operator->(void)
0x180221f8e  mov     rcx, rax
0x180221f91  mov     rax, [rax]
0x180221f94  lea     rdx, [rsp+0C8h+var_98]
0x180221f99  mov     rax, [rax+230h]
0x180221fa0  call    cs:__guard_dispatch_icall_fptr
0x180221fa6  or      edi, 2
0x180221fa9  cmp     [rax], rsi
0x180221fac  jnz     short loc_180221FCD
0x180221fae  lea     rcx, [rsp+0C8h+var_88]
0x180221fb3  call    ??C?$TCntPtr@VAppAugmentationStatefulRuntime@AugLoop@Art@@@Mso@@QEBAPEAVAppAugmentationStatefulRuntime@AugLoop@Art@@XZ; Mso::TCntPtr<Art::AugLoop::AppAugmentationStatefulRuntime>::operator->(void)
0x180221fb8  mov     rcx, rax
0x180221fbb  mov     rax, [rax]
0x180221fbe  mov     rax, [rax+30h]
0x180221fc2  call    cs:__guard_dispatch_icall_fptr
0x180221fc8  cmp     eax, 3
0x180221fcb  jnz     short loc_180221FD0
0x180221fcd  mov     r12b, sil
0x180221fd0  test    dil, 2
0x180221fd4  jz      short loc_180221FE0
0x180221fd6  lea     rcx, [rsp+0C8h+var_98]
0x180221fdb  call    ?Clear@?$TCntPtr@VCMetroProgress@Art@@@Mso@@QEAAXXZ; Mso::TCntPtr<Art::CMetroProgress>::Clear(void)
0x180221fe0  test    r12b, r12b
0x180221fe3  jz      loc_18022207A
0x180221fe9  mov     [rsp+0C8h+var_90], rsi
0x180221fee  mov     rax, [r14]
0x180221ff1  lea     rdx, [rsp+0C8h+var_90]
0x180221ff6  mov     rcx, r14
0x180221ff9  mov     rax, [rax+2C0h]
0x180222000  call    cs:__guard_dispatch_icall_fptr
0x180222006  test    eax, eax
0x180222008  js      short loc_18022207A
0x18022200a  mov     rcx, [rsp+0C8h+var_90]
0x18022200f  test    rcx, rcx
0x180222012  jz      short loc_18022207A
0x180222014  mov     rax, [rcx]
0x180222017  mov     rax, [rax+30h]
0x18022201b  call    cs:__guard_dispatch_icall_fptr
0x180222021  cmp     eax, 3
0x180222024  jz      short loc_180222040
0x180222026  mov     rax, [r14]
0x180222029  mov     rdx, [rsp+0C8h+var_90]
0x18022202e  mov     rcx, r14
0x180222031  mov     rax, [rax+2E0h]
0x180222038  call    cs:__guard_dispatch_icall_fptr
0x18022203e  jmp     short loc_18022207A
0x180222040  test    rbx, rbx
0x180222043  jz      short loc_180222056
0x180222045  mov     rax, [rbx]
0x180222048  mov     rcx, rbx
0x18022204b  mov     rax, [rax+10h]
0x18022204f  call    cs:__guard_dispatch_icall_fptr
0x180222055  nop
0x180222056  lea     rcx, [rsp+0C8h+arg_0]; void *
0x18022205e  call    ?Clear@?$TCntPtr@VResource@Art@@@Mso@@QEAAXXZ; Mso::TCntPtr<Art::Resource>::Clear(void)
0x180222063  lea     rcx, [rsp+0C8h+arg_18]; struct Ofc::CProxyPtrImpl **
0x18022206b  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x180222070  mov     eax, 80004005h
0x180222075  jmp     loc_180222662
0x18022207a  test    rbx, rbx
0x18022207d  jz      short loc_180222090
0x18022207f  mov     rax, [rbx]
0x180222082  mov     rcx, rbx
0x180222085  mov     rax, [rax+10h]
0x180222089  call    cs:__guard_dispatch_icall_fptr
0x18022208f  nop
0x180222090  lea     rcx, [rsp+0C8h+arg_0]; void *
0x180222098  call    ?Clear@?$TCntPtr@VResource@Art@@@Mso@@QEAAXXZ; Mso::TCntPtr<Art::Resource>::Clear(void)
0x18022209d  lea     rcx, [rsp+0C8h+arg_18]; struct Ofc::CProxyPtrImpl **
0x1802220a5  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x1802220aa  xor     eax, eax
0x1802220ac  jmp     loc_180222662
0x1802220b1  mov     [rsp+0C8h+var_80], rsi
0x1802220b6  mov     rax, [r14]
0x1802220b9  lea     rdx, [rsp+0C8h+var_80]
0x1802220be  mov     rcx, r14
0x1802220c1  mov     rax, [rax+2C0h]
0x1802220c8  call    cs:__guard_dispatch_icall_fptr
0x1802220ce  mov     ebx, eax
0x1802220d0  test    eax, eax
0x1802220d2  js      loc_18022261D
0x1802220d8  mov     rcx, [rsp+0C8h+var_80]
0x1802220dd  test    rcx, rcx
0x1802220e0  jz      loc_18022261D
0x1802220e6  mov     rax, [rcx]
0x1802220e9  mov     rax, [rax+30h]
0x1802220ed  call    cs:__guard_dispatch_icall_fptr
0x1802220f3  cmp     eax, 3
0x1802220f6  jz      loc_18022261D
0x1802220fc  mov     rcx, [rsp+0C8h+var_80]
0x180222101  mov     rax, [rcx]
0x180222104  mov     rax, [rax+20h]
0x180222108  call    cs:__guard_dispatch_icall_fptr
0x18022210e  mov     rcx, rax
0x180222111  mov     rax, [rax]
0x180222114  mov     rax, [rax+20h]
0x180222118  call    cs:__guard_dispatch_icall_fptr
0x18022211e  mov     rdx, rax
0x180222121  mov     r12d, 1
0x180222127  mov     r8b, r12b
0x18022212a  lea     rcx, [rsp+0C8h+var_50]
0x18022212f  call    cs:__imp_??0CurrentContextHolder@FastModel@@QEAA@AEAVContext@1@_N@Z; FastModel::CurrentContextHolder::CurrentContextHolder(FastModel::Context &,bool)
0x180222135  mov     rcx, r14
0x180222138  call    ?GetView@ViewElement@Art@@QEAAAEBV?$TWeakPtr@VView@Art@@@Ofc@@XZ; Art::ViewElement::GetView(void)
0x18022213d  mov     rcx, [rax]; struct Ofc::CProxyPtrImpl *
0x180222140  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x180222145  mov     [rsp+0C8h+var_68], rax
0x18022214a  mov     rcx, r14; this
0x18022214d  call    ?FMinimalDecorativeFastAccNode@ViewElement@Art@@QEBA_NXZ; Art::ViewElement::FMinimalDecorativeFastAccNode(void)
0x180222152  test    al, al
0x180222154  jz      short loc_180222185
0x180222156  mov     rcx, [rsp+0C8h+var_80]
0x18022215b  mov     rax, [rcx]
0x18022215e  mov     rax, [rax+20h]
0x180222162  call    cs:__guard_dispatch_icall_fptr
0x180222168  mov     r8, rax
0x18022216b  mov     r9, [rsp+0C8h+arg_10]
0x180222173  lea     rdx, [rsp+0C8h+var_98]
0x180222178  mov     rcx, r14
0x18022217b  call    ?CreateEmptyFastAccNode@ViewElement@Art@@AEAA?AV?$TCntPtr@UFastAccNode@Art@@@Ofc@@AEAUIExecutionContext@ApplicationModel@Mso@@PEAVIProtectViewAccess@2@@Z; Art::ViewElement::CreateEmptyFastAccNode(Mso::ApplicationModel::IExecutionContext &,Art::IProtectViewAccess *)
0x180222180  jmp     loc_180222379
0x180222185  mov     rcx, r14; this
0x180222188  call    ?FInvisible@ViewElement@Art@@QEBA_NXZ; Art::ViewElement::FInvisible(void)
0x18022218d  test    al, al
0x18022218f  jz      loc_180222336
0x180222195  mov     rcx, r14; this
0x180222198  call    ?FShouldGenerateNodeForInvisibleObject@Art@@YA_NPEAVViewElement@1@@Z; Art::FShouldGenerateNodeForInvisibleObject(Art::ViewElement *)
0x18022219d  test    al, al
0x18022219f  jz      loc_180222336
0x1802221a5  mov     rcx, r14
0x1802221a8  call    ??$runtime_cast@PEAVInkViewElement@Dr@@@Ofc@@YAPEAVInkViewElement@Dr@@PEAVCObject@0@@Z; Ofc::runtime_cast<Dr::InkViewElement *>(Ofc::CObject *)
0x1802221ad  test    rax, rax
0x1802221b0  jz      loc_180222336
0x1802221b6  mov     rcx, [rsp+0C8h+var_80]
0x1802221bb  mov     rax, [rcx]
0x1802221be  mov     rax, [rax+20h]
0x1802221c2  call    cs:__guard_dispatch_icall_fptr
0x1802221c8  mov     r8, rax
0x1802221cb  mov     r9, [rsp+0C8h+arg_10]
0x1802221d3  lea     rdx, [rsp+0C8h+var_98]
0x1802221d8  mov     rcx, r14
0x1802221db  call    ?CreateEmptyFastAccNode@ViewElement@Art@@AEAA?AV?$TCntPtr@UFastAccNode@Art@@@Ofc@@AEAUIExecutionContext@ApplicationModel@Mso@@PEAVIProtectViewAccess@2@@Z; Art::ViewElement::CreateEmptyFastAccNode(Mso::ApplicationModel::IExecutionContext &,Art::IProtectViewAccess *)
0x1802221e0  mov     rdx, [rax]
0x1802221e3  mov     [rax], rsi
0x1802221e6  mov     rcx, r15
0x1802221e9  call    ?Assign@?$TCntPtr@UFastAccNode@Art@@@Ofc@@AEAAXPEAUFastAccNode@Art@@@Z; Ofc::TCntPtr<Art::FastAccNode>::Assign(Art::FastAccNode *)
0x1802221ee  mov     rax, [rsp+0C8h+var_98]
0x1802221f3  test    rax, rax
0x1802221f6  jz      short loc_180222214
0x1802221f8  mov     rcx, [rax+8]
0x1802221fc  movsxd  rcx, dword ptr [rcx+4]
0x180222200  add     rax, 8
0x180222204  add     rcx, rax
  ... truncated ...
```
