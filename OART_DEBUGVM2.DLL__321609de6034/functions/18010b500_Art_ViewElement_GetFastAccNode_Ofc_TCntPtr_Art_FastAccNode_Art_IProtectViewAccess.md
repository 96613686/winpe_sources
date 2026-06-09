# Art::ViewElement::GetFastAccNode(Ofc::TCntPtr<Art::FastAccNode> &,Art::IProtectViewAccess *)

- ea: `0x18010b500`
- end: `0x18010c1c1`
- name: `?GetFastAccNode@ViewElement@Art@@QEAAJAEAV?$TCntPtr@UFastAccNode@Art@@@Ofc@@PEAVIProtectViewAccess@2@@Z`
- size: `3265`
- prototype: `__int64 __fastcall(Art::ViewElement *this)`
- caller_count: `22`
- callee_count: `28`
- tags: ``

## callers

- `0x1800f61c8`
- `0x18010ac84`
- `0x18014aba0`
- `0x1801bdde0`
- `0x1801c4470`
- `0x180216ec0`
- `0x180241230`
- `0x1804a9bd0`
- `0x1804d6c10`
- `0x180560e3c`
- `0x18059d5e0`
- `0x18059f130`
- `0x1805a77ec`
- `0x18062f920`
- `0x1806592f0`
- `0x18065aba8`
- `0x1806a256c`
- `0x1807ac5c0`
- `0x1807cbddc`
- `0x1807d6e60`
- `0x1807dd25c`
- `0x18085e5e0`

## callees

- `0x18000e1b0`
- `0x18000e858`
- `0x18000f840`
- `0x180028b00`
- `0x18002a690`
- `0x1800d3e40`
- `0x1800fbe70`
- `0x18010b500`
- `0x18010ccd0`
- `0x180144e90`
- `0x1801c0390`
- `0x1801c0404`
- `0x1801c2830`
- `0x1801cb6a0`
- `0x180274528`
- `0x180279010`
- `0x180279050`
- `0x180289a5c`
- `0x18028ac00`
- `0x18038667c`
- `0x1804d6624`
- `0x180524bf8`
- `0x180650630`
- `0x1806bc2a8`
- `0x1806bc4f0`
- `0x1806bc6a8`
- `0x1806bc84c`
- `0x1806d19bc`

## import_xrefs

- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x18010c081`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x18010c0ea`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x18010c081`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x18010c0ea`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18010bfbe`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18010bfce`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18010bfbe`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18010bfce`
- `Mso20Win32Client!__imp_?GetCurrentExecutionContext@ApplicationModel@Mso@@YA?AV?$TCntPtr@UIExecutionContext@ApplicationModel@Mso@@@2@XZ` at `0x18010b5f0`
- `Mso20Win32Client!__imp_?GetCurrentExecutionContext@ApplicationModel@Mso@@YA?AV?$TCntPtr@UIExecutionContext@ApplicationModel@Mso@@@2@XZ` at `0x18010b5f0`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18010b705`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18010b705`
- `Mso20Win32Client!__imp_?VerifyUIThread@ApplicationModel@Mso@@YA_NPEBUIExecutionContext@12@@Z` at `0x18010b607`
- `Mso20Win32Client!__imp_?VerifyUIThread@ApplicationModel@Mso@@YA_NPEBUIExecutionContext@12@@Z` at `0x18010b67a`
- `Mso20Win32Client!__imp_?VerifyUIThread@ApplicationModel@Mso@@YA_NPEBUIExecutionContext@12@@Z` at `0x18010b607`
- `Mso20Win32Client!__imp_?VerifyUIThread@ApplicationModel@Mso@@YA_NPEBUIExecutionContext@12@@Z` at `0x18010b67a`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x18010bba0`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x18010bba0`
- `Mso20Win32Client!__imp_??0CurrentContextHolder@FastModel@@QEAA@AEAVContext@1@_N@Z` at `0x18010b917`
- `Mso20Win32Client!__imp_??0CurrentContextHolder@FastModel@@QEAA@AEAVContext@1@_N@Z` at `0x18010b917`
- `Mso20Win32Client!__imp_?VerifyAppThread@ApplicationModel@Mso@@YA_NPEBUIExecutionContext@12@@Z` at `0x18010be35`
- `Mso20Win32Client!__imp_?VerifyAppThread@ApplicationModel@Mso@@YA_NPEBUIExecutionContext@12@@Z` at `0x18010be35`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x18010bb89`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x18010bb89`
- `Mso20Win32Client!__imp_??1CurrentContextHolder@FastModel@@QEAA@XZ` at `0x18010bd09`
- `Mso20Win32Client!__imp_??1CurrentContextHolder@FastModel@@QEAA@XZ` at `0x18010bd09`

## pseudocode

```c
__int64 __fastcall Art::ViewElement::GetFastAccNode(Art::ViewElement *this, __int64 *a2, __int64 a3)
{
  int *v6; // rsi
  struct Art::ViewElement *v7; // rdx
  __int64 v8; // rax
  struct Ofc::CProxyPtrImpl *v9; // rax
  void *v10; // rax
  const struct Mso::ApplicationModel::IExecutionContext *v11; // rdx
  Mso::ApplicationModel *v12; // rcx
  const struct Mso::ApplicationModel::IExecutionContext *v13; // rdx
  _QWORD *v14; // r15
  __int64 v15; // rbx
  __int64 v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rcx
  bool v19; // bl
  Ofc::CProxyPtrImpl *v20; // rcx
  struct Ofc::CProxyPtrImpl **v21; // rax
  __int64 v22; // rcx
  __int64 v23; // rcx
  bool v25; // r15
  Ofc::CProxyPtrImpl *v26; // rcx
  Mso::ApplicationModel *v27; // rcx
  int v28; // ebx
  Mso::ApplicationModel *v29; // rcx
  __int64 v30; // rax
  struct FastModel::Context *v31; // rax
  struct Ofc::CProxyPtrImpl **View; // rax
  struct Art::ViewElement *v33; // rdx
  __int64 v34; // rbx
  __int64 v35; // rax
  __int64 *v36; // rax
  __int64 v37; // rdx
  char *v38; // rcx
  unsigned __int64 v39; // rdx
  unsigned int v40; // r8d
  struct Ofc::CProxyPtrImpl **v41; // rax
  void *v42; // rax
  struct Ofc::CProxyPtrImpl **v43; // rax
  _QWORD *v44; // rbx
  unsigned int v45; // r8d
  Ofc::CProxyPtrImpl *v46; // rax
  int *v47; // rdi
  struct Ofc::CProxyPtrImpl *v48; // rbx
  __int64 v49; // rax
  struct Ofc::CProxyPtrImpl **v50; // rax
  Ofc::CProxyPtrImpl *v51; // rcx
  Ofc::CProxyPtrImpl *v52; // rcx
  Mso::ApplicationModel *v53; // rcx
  __int64 v54; // r8
  __int64 v55; // rcx
  __int64 v56; // rcx
  Mso::ApplicationModel *v57; // rcx
  char *Checked; // rcx
  char *v59; // rcx
  struct Ofc::CProxyPtrImpl **v60; // rdx
  char *v61; // rcx
  char *v62; // rcx
  struct Ofc::CProxyPtrImpl **v63; // rdx
  __int64 v64; // rcx
  void (__fastcall *v65)(__int64, Ofc::CProxyPtrImpl **); // r8
  Mso::ApplicationModel *v66; // rcx
  __int64 v67; // rax
  __int64 *v68; // rax
  __int64 v69; // rdx
  char *v70; // rcx
  __int64 v71; // rax
  __int64 v72; // rsi
  void (__fastcall *v73)(__int64, __int64); // rbx
  __int64 v74; // rdx
  __int64 v75; // rcx
  HINSTANCE HinstIntl; // rax
  __int64 v77; // rdx
  __int64 v78; // rax
  void (__fastcall *v79)(int *, _QWORD); // rbx
  __int64 v80; // rdx
  __int64 v81; // rcx
  HINSTANCE v82; // rax
  _QWORD *v83; // rax
  __int64 v84; // rax
  __int64 v85; // rcx
  __int64 v86; // rdx
  Ofc::CProxyPtrImpl *v87; // [rsp+30h] [rbp-118h] BYREF
  Ofc::CProxyPtrImpl *v88; // [rsp+38h] [rbp-110h] BYREF
  struct Ofc::CProxyPtrImpl *v89; // [rsp+40h] [rbp-108h] BYREF
  __int64 v90; // [rsp+48h] [rbp-100h] BYREF
  struct Ofc::CProxyPtrImpl *v91; // [rsp+50h] [rbp-F8h] BYREF
  struct Ofc::CProxyPtrImpl *v92; // [rsp+58h] [rbp-F0h] BYREF
  Ofc::CProxyPtrImpl *v93; // [rsp+60h] [rbp-E8h] BYREF
  void **v94; // [rsp+68h] [rbp-E0h] BYREF
  __int64 (__fastcall ***v95)(_QWORD, Ofc::CProxyPtrImpl **, _QWORD); // [rsp+70h] [rbp-D8h]
  _OWORD v96[5]; // [rsp+80h] [rbp-C8h] BYREF
  int v97; // [rsp+D0h] [rbp-78h]
  const OLECHAR *v98; // [rsp+D8h] [rbp-70h]
  const OLECHAR *v99; // [rsp+E0h] [rbp-68h]
  char v100; // [rsp+E8h] [rbp-60h]
  const OLECHAR *v101; // [rsp+F0h] [rbp-58h]
  _BYTE v102[32]; // [rsp+100h] [rbp-48h] BYREF
  Mso::ApplicationModel *v103; // [rsp+150h] [rbp+8h] BYREF
  struct Ofc::CProxyPtrImpl *v104; // [rsp+168h] [rbp+20h] BYREF

  v6 = 0;
  LODWORD(v103) = 0;
  if ( (*((_BYTE *)this + 192) & 4) == 0
    && !(*(unsigned __int8 (__fastcall **)(Art::ViewElement *))(*(_QWORD *)this + 1168LL))(this)
    || !(*(unsigned __int8 (__fastcall **)(Art::ViewElement *))(*(_QWORD *)this + 712LL))(this)
    || ((*(unsigned __int8 (__fastcall **)(_QWORD))(**((_QWORD **)this + 18) + 256LL))(*((_QWORD *)this + 18))
     || (v8 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 18) + 744LL))(*((_QWORD *)this + 18)),
         (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v8 + 64LL))(v8)))
    && !Art::FShouldGenerateNodeForInvisibleObject(this, v7) )
  {
    if ( *a2 )
    {
      v23 = *a2 + 8 + *(int *)(*(_QWORD *)(*a2 + 8) + 4LL);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    }
    *a2 = 0;
    return 0;
  }
  v9 = Ofc::CProxyPtrImpl::CheckedStrongAddRef(*((struct Ofc::CProxyPtrImpl **)this + 20));
  v104 = v9;
  if ( *((_QWORD *)v9 + 2)
    && (v10 = Ofc::CProxyPtrImpl::GetChecked(v9),
        (*(unsigned __int8 (__fastcall **)(void *, Art::ViewElement *))(*(_QWORD *)v10 + 200LL))(v10, this)) )
  {
    if ( *a2 )
    {
      v55 = *a2 + 8 + *(int *)(*(_QWORD *)(*a2 + 8) + 4LL);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
    }
    *a2 = 0;
    Ofc::CProxyPtrImpl::DtorStrongRelease(&v104);
    return 0;
  }
  else
  {
    Mso::ApplicationModel::GetCurrentExecutionContext(&v103);
    v12 = v103;
    if ( !v103 )
    {
LABEL_22:
      if ( *a2 )
      {
        v22 = *a2 + 8 + *(int *)(*(_QWORD *)(*a2 + 8) + 4LL);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
        v12 = v103;
      }
      *a2 = 0;
      if ( v12 )
      {
        v103 = 0;
        (*(void (__fastcall **)(Mso::ApplicationModel *))(*(_QWORD *)v12 + 8LL))(v12);
      }
LABEL_83:
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v104);
      return 0;
    }
    if ( !Mso::ApplicationModel::VerifyUIThread(v103, v11) && !Mso::ApplicationModel::VerifyAppThread(v103, v13) )
    {
      if ( *a2 )
      {
        v56 = *a2 + 8 + *(int *)(*(_QWORD *)(*a2 + 8) + 4LL);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
      }
      *a2 = 0;
      v57 = v103;
      if ( v103 )
      {
        v103 = 0;
        (*(void (__fastcall **)(Mso::ApplicationModel *))(*(_QWORD *)v57 + 8LL))(v57);
      }
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v104);
      return 0;
    }
    v14 = (_QWORD *)((char *)this + 128);
    v15 = *((_QWORD *)this + 16);
    if ( v15 )
    {
      v16 = v15 + *(int *)(*(_QWORD *)(v15 + 8) + 4LL) + 8LL;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 8LL))(v16);
      v17 = *a2;
      if ( *a2 )
      {
        v18 = v17 + 8 + *(int *)(*(_QWORD *)(v17 + 8) + 4LL);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
      }
      *a2 = v15;
      v19 = 0;
      if ( v103 )
      {
        if ( Mso::ApplicationModel::VerifyUIThread(v103, (const struct Mso::ApplicationModel::IExecutionContext *)v17) )
        {
          LOBYTE(v6) = 1;
          if ( *(_QWORD *)(*(__int64 (__fastcall **)(_QWORD, Ofc::CProxyPtrImpl **))(*(_QWORD *)*v14 + 208LL))(
                            *v14,
                            &v88) )
            v19 = 1;
        }
      }
      if ( ((unsigned __int8)v6 & 1) != 0 )
      {
        LOBYTE(v6) = (unsigned __int8)v6 & 0xFE;
        v20 = v88;
        if ( v88 )
        {
          v88 = 0;
          (*(void (__fastcall **)(Ofc::CProxyPtrImpl *))(*(_QWORD *)v20 + 16LL))(v20);
        }
      }
      v21 = (struct Ofc::CProxyPtrImpl **)(*(__int64 (__fastcall **)(_QWORD, Ofc::CProxyPtrImpl **))(*(_QWORD *)*v14 + 208LL))(
                                            *v14,
                                            &v87);
      if ( v19 )
      {
        if ( !*v21 )
        {
          CrashWithRecovery(0x1E3C3840u, 0);
          goto LABEL_22;
        }
        v49 = (*(__int64 (__fastcall **)(struct Ofc::CProxyPtrImpl *))(*(_QWORD *)*v21 + 40LL))(*v21);
        v50 = (struct Ofc::CProxyPtrImpl **)qi_cast_or_crash<FastAcc::Abstract::IElement,FastAcc::Abstract::IObject>(
                                              &v88,
                                              v49);
        v48 = *v50;
        *v50 = 0;
        v89 = v48;
        v51 = v88;
        if ( v88 )
        {
          v88 = 0;
          (*(void (__fastcall **)(Ofc::CProxyPtrImpl *))(*(_QWORD *)v51 + 16LL))(v51);
        }
      }
      else
      {
        v48 = *v21;
        *v21 = 0;
        v89 = v48;
      }
      v52 = v87;
      if ( v87 )
      {
        v87 = 0;
        (*(void (__fastcall **)(Ofc::CProxyPtrImpl *))(*(_QWORD *)v52 + 16LL))(v52);
      }
      v25 = 0;
      if ( v48 )
      {
        LOBYTE(v6) = (unsigned __int8)v6 | 2;
        if ( !*(_QWORD *)(*(__int64 (__fastcall **)(struct Ofc::CProxyPtrImpl *, Ofc::CProxyPtrImpl **))(*(_QWORD *)v48 + 560LL))(
                           v48,
                           &v87)
          && (*(unsigned int (__fastcall **)(struct Ofc::CProxyPtrImpl *))(*(_QWORD *)v48 + 48LL))(v48) != 3 )
        {
          v25 = 1;
        }
      }
      if ( ((unsigned __int8)v6 & 2) != 0 )
      {
        v26 = v87;
        if ( v87 )
        {
          v87 = 0;
          (*(void (__fastcall **)(Ofc::CProxyPtrImpl *))(*(_QWORD *)v26 + 16LL))(v26);
        }
      }
      if ( !v25
        || (v88 = 0,
            (*(int (__fastcall **)(Art::ViewElement *, Ofc::CProxyPtrImpl **))(*(_QWORD *)this + 696LL))(this, &v88) < 0)
        || !v88 )
      {
LABEL_36:
        if ( v48 )
          (*(void (__fastcall **)(struct Ofc::CProxyPtrImpl *))(*(_QWORD *)v48 + 16LL))(v48);
        v27 = v103;
        if ( v103 )
        {
          v103 = 0;
          (*(void (__fastcall **)(Mso::ApplicationModel *))(*(_QWORD *)v27 + 8LL))(v27);
        }
        goto LABEL_83;
      }
      if ( (*(unsigned int (__fastcall **)(Ofc::CProxyPtrImpl *))(*(_QWORD *)v88 + 48LL))(v88) != 3 )
      {
        (*(void (__fastcall **)(Art::ViewElement *, Ofc::CProxyPtrImpl *))(*(_QWORD *)this + 728LL))(this, v88);
        goto LABEL_36;
      }
      if ( v48 )
        (*(void (__fastcall **)(struct Ofc::CProxyPtrImpl *))(*(_QWORD *)v48 + 16LL))(v48);
      v66 = v103;
      if ( v103 )
      {
        v103 = 0;
        (*(void (__fastcall **)(Mso::ApplicationModel *))(*(_QWORD *)v66 + 8LL))(v66);
      }
LABEL_68:
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v104);
      return 2147500037LL;
    }
    v90 = 0;
    v28 = (*(__int64 (__fastcall **)(Art::ViewElement *, __int64 *))(*(_QWORD *)this + 696LL))(this, &v90);
    if ( v28 >= 0 && v90 && (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v90 + 48LL))(v90) != 3 )
    {
      v30 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v90 + 32LL))(v90);
      v31 = (struct FastModel::Context *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v30 + 32LL))(v30);
      FastModel::CurrentContextHolder::CurrentContextHolder((FastModel::CurrentContextHolder *)v102, v31, 1);
      View = (struct Ofc::CProxyPtrImpl **)Art::ViewElement::GetView(this);
      v93 = Ofc::CProxyPtrImpl::CheckedStrongAddRef(*View);
      memset(v96, 0, sizeof(v96));
      v97 = 0;
      v98 = &word_180A9C374;
      v99 = &word_180A9C374;
      v100 = 0;
      v101 = &word_180A9C374;
      (*(void (__fastcall **)(Art::ViewElement *, _OWORD *))(*(_QWORD *)this + 968LL))(this, v96);
      if ( Art::ViewElement::FMinimalDecorativeFastAccNode(this) )
      {
        v54 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v90 + 32LL))(v90);
        v36 = (__int64 *)Art::ViewElement::CreateEmptyFastAccNode(this, &v89, v54, a3);
      }
      else
      {
        if ( Art::ViewElement::FInvisible(this)
          && Art::FShouldGenerateNodeForInvisibleObject(this, v33)
          && Ofc::runtime_cast<Dr::InkViewElement *>(this) )
        {
          v67 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v90 + 32LL))(v90);
          v68 = (__int64 *)Art::ViewElement::CreateEmptyFastAccNode(this, &v89, v67, a3);
          v69 = *v68;
          *v68 = 0;
          Ofc::TCntPtr<Art::FastAccNode>::Assign((char *)this + 128, v69);
          if ( v89 )
          {
            v70 = (char *)v89 + *(int *)(*((_QWORD *)v89 + 1) + 4LL) + 8;
            (*(void (__fastcall **)(char *))(*(_QWORD *)v70 + 16LL))(v70);
          }
          v71 = (*(__int64 (__fastcall **)(_QWORD, Ofc::CProxyPtrImpl **))(*(_QWORD *)*v14 + 208LL))(*v14, &v87);
          v72 = Mso::TCntPtr<Art::AugLoop::AppAugmentationStatefulRuntime>::operator->(v71);
          v73 = *(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v72 + 504LL);
          HinstIntl = (HINSTANCE)MsoGetHinstIntl(v75, v74);
          v77 = *(_QWORD *)Ofc::CVarStr::CVarStr((Ofc::CVarStr *)&v89, HinstIntl, 293591054);
          v73(v72, v77);
          Ofc::CVarStr::ReleaseBuffer((Ofc::CVarStr *)&v89);
          Mso::TCntPtr<Art::CMetroProgress>::Clear(&v87);
          v78 = (*(__int64 (__fastcall **)(_QWORD, Ofc::CProxyPtrImpl **))(*(_QWORD *)*v14 + 208LL))(*v14, &v87);
          v6 = (int *)Mso::TCntPtr<Art::AugLoop::AppAugmentationStatefulRuntime>::operator->(v78);
          v79 = *(void (__fastcall **)(int *, _QWORD))(*(_QWORD *)v6 + 312LL);
          v82 = (HINSTANCE)MsoGetHinstIntl(v81, v80);
          v83 = (_QWORD *)Ofc::CVarStr::CVarStr((Ofc::CVarStr *)&v89, v82, -588823970);
          v79(v6, *v83);
          Ofc::CVarStr::ReleaseBuffer((Ofc::CVarStr *)&v89);
          Mso::TCntPtr<Art::CMetroProgress>::Clear(&v87);
          v84 = (*(__int64 (__fastcall **)(_QWORD, struct Ofc::CProxyPtrImpl **))(*(_QWORD *)*v14 + 208LL))(*v14, &v89);
          v85 = Mso::TCntPtr<Art::AugLoop::AppAugmentationStatefulRuntime>::operator->(v84);
          LOBYTE(v86) = 1;
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v85 + 376LL))(v85, v86);
          Mso::TCntPtr<Art::CMetroProgress>::Clear(&v89);
          goto LABEL_56;
        }
        v6 = *(int **)(*(_QWORD *)this + 720LL);
        v34 = v90;
        v35 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v90 + 32LL))(v90);
        v36 = (__int64 *)((__int64 (__fastcall *)(Art::ViewElement *, struct Ofc::CProxyPtrImpl **, __int64, __int64, __int64))v6)(
                           this,
                           &v89,
                           v35,
                           v34,
                           a3);
      }
      v37 = *v36;
      *v36 = 0;
      Ofc::TCntPtr<Art::FastAccNode>::Assign((char *)this + 128, v37);
      if ( v89 )
      {
        v38 = (char *)v89 + *(int *)(*((_QWORD *)v89 + 1) + 4LL) + 8;
        (*(void (__fastcall **)(char *))(*(_QWORD *)v38 + 16LL))(v38);
      }
LABEL_56:
      if ( *v14 )
      {
        (*(void (__fastcall **)(Art::ViewElement *, __int64))(*(_QWORD *)this + 728LL))(this, v90);
        Ofc::TCntPtr<FastAcc::Abstract::ITextApp>::operator=(a2, *v14);
        v6 = &`Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_proxyPtrSentinel;
        v91 = (struct Ofc::CProxyPtrImpl *)&`Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_proxyPtrSentinel;
        if ( !*((_QWORD *)v93 + 2) )
        {
LABEL_63:
          v44 = Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0x10, v39, v40);
          if ( v44 )
          {
            *v44 = &Art::ViewElementFastAccNodeObserver::`vftable';
            v44[1] = Ofc::CProxyPtrImpl::WeakAddRef(*((struct Ofc::CProxyPtrImpl **)this + 4));
            v46 = (Ofc::CProxyPtrImpl *)Mso::Memory::AllocateEx((Mso::Memory *)0x18, 0, v45);
            v47 = (int *)v46;
            if ( !v46 )
            {
              CrashWithRecoveryOnOOM(0x1F3C0756u);
LABEL_66:
              if ( v29 )
              {
                v103 = 0;
                (*(void (__fastcall **)(Mso::ApplicationModel *))(*(_QWORD *)v29 + 8LL))(v29);
              }
              goto LABEL_68;
            }
            Ofc::CProxyPtrImpl::CProxyPtrImpl(v46, Ofc::TDeleteFromProxy<Art::UnsavedEnterpriseDocumentProtector>);
            *((_QWORD *)v47 + 2) = v44;
          }
          else
          {
            v47 = &`Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_proxyPtrSentinel;
          }
          v92 = (struct Ofc::CProxyPtrImpl *)v47;
          if ( !*((_QWORD *)v91 + 2) )
          {
            (*(void (__fastcall **)(_QWORD, struct Ofc::CProxyPtrImpl **))(*(_QWORD *)*v14 + 240LL))(*v14, &v92);
            goto LABEL_81;
          }
          Ofc::MakeOwningPtr<Art::AggregateFastAccNodeObserver,>(&v88);
          Checked = (char *)Ofc::CProxyPtrImpl::GetChecked(v88);
          if ( !*((_QWORD *)v92 + 2) )
          {
            MsoShipAssertTagProc(24662409);
            goto LABEL_102;
          }
          v59 = Checked + 8;
          v60 = (struct Ofc::CProxyPtrImpl **)*((_QWORD *)v59 + 1);
          if ( v60 != *((struct Ofc::CProxyPtrImpl ***)v59 + 2) )
          {
            *v60 = v92;
            v92 = (struct Ofc::CProxyPtrImpl *)&`Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_proxyPtrSentinel;
            *((_QWORD *)v59 + 1) += 8LL;
LABEL_102:
            v61 = (char *)Ofc::CProxyPtrImpl::GetChecked(v88);
            if ( *((_QWORD *)v91 + 2) )
            {
              v62 = v61 + 8;
              v63 = (struct Ofc::CProxyPtrImpl **)*((_QWORD *)v62 + 1);
              if ( v63 == *((struct Ofc::CProxyPtrImpl ***)v62 + 2) )
              {
                std::vector<Ofc::TOwningPtr<Art::IFastAccNodeObserver>>::_Emplace_reallocate<Ofc::TOwningPtr<Art::IFastAccNodeObserver>>(
                  v62,
                  v63,
                  &v91);
              }
              else
              {
                *v63 = v91;
                v91 = (struct Ofc::CProxyPtrImpl *)v6;
                *((_QWORD *)v62 + 1) += 8LL;
              }
            }
            else
            {
              MsoShipAssertTagProc(24662409);
            }
            v64 = *v14;
            v65 = *(void (__fastcall **)(__int64, Ofc::CProxyPtrImpl **))(*(_QWORD *)*v14 + 240LL);
            v87 = v88;
            v88 = (Ofc::CProxyPtrImpl *)v6;
            v65(v64, &v87);
            Ofc::CProxyPtrImpl::DtorStrongRelease(&v87);
            Ofc::CProxyPtrImpl::DtorStrongRelease(&v88);
LABEL_81:
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v14 + 176LL))(*v14);
            Ofc::CProxyPtrImpl::DtorStrongRelease(&v92);
            Ofc::CProxyPtrImpl::DtorStrongRelease(&v91);
            Art::NonVisualDrawingPropsData::~NonVisualDrawingPropsData((Art::NonVisualDrawingPropsData *)v96);
            Ofc::CProxyPtrImpl::DtorStrongRelease(&v93);
            FastModel::CurrentContextHolder::~CurrentContextHolder((FastModel::CurrentContextHolder *)v102);
            v53 = v103;
            if ( v103 )
            {
              v103 = 0;
              (*(void (__fastcall **)(Mso::ApplicationModel *))(*(_QWORD *)v53 + 8LL))(v53);
            }
            goto LABEL_83;
          }
LABEL_120:
          std::vector<Ofc::TOwningPtr<Art::IFastAccNodeObserver>>::_Emplace_reallocate<Ofc::TOwningPtr<Art::IFastAccNodeObserver>>(
            v59,
            v60,
            &v92);
          goto LABEL_102;
        }
        v41 = (struct Ofc::CProxyPtrImpl **)Ofc::CProxyPtrImpl::GetChecked(v93);
        v89 = Ofc::CProxyPtrImpl::WeakAddRef(v41[7]);
        v87 = Ofc::CProxyPtrImpl::CheckedStrongAddRef(v89);
        Ofc::CProxyPtrImpl::DtorWeakRelease(&v89);
        if ( !*((_QWORD *)v87 + 2)
          || (v95 = 0,
              v94 = &Art::THostInterfaceInfo<Art::FastAccNodeObserverFactory>::`vftable',
              v42 = Ofc::CProxyPtrImpl::GetChecked(v87),
              !(*(unsigned __int8 (__fastcall **)(void *, void ***))(*(_QWORD *)v42 + 16LL))(v42, &v94)) )
        {
LABEL_62:
          Ofc::CProxyPtrImpl::DtorStrongRelease(&v87);
          goto LABEL_63;
        }
        if ( v95 )
        {
          v43 = (struct Ofc::CProxyPtrImpl **)(**v95)(v95, &v88, *v14);
          Ofc::CProxyPtrImpl::StrongMoveAssign(&v91, v43);
          Ofc::CProxyPtrImpl::DtorStrongRelease(&v88);
          goto LABEL_62;
        }
      }
      else
      {
        Ofc::CInvalidOperationException::ThrowTag(0x140A653u);
      }
      Ofc::CObjectExpiredException::ThrowTag(0x134F08Cu);
      goto LABEL_120;
    }
    v29 = v103;
    if ( v28 != -2147467260 )
      goto LABEL_66;
    if ( v103 )
    {
      v103 = 0;
      (*(void (__fastcall **)(Mso::ApplicationModel *))(*(_QWORD *)v29 + 8LL))(v29);
    }
    Ofc::CProxyPtrImpl::DtorStrongRelease(&v104);
    return 2147500036LL;
  }
}

```

## disassembly

```asm
0x18010b500  mov     [rsp+arg_8], rbx
0x18010b505  mov     [rsp+arg_10], rsi
0x18010b50a  push    rdi
0x18010b50b  push    r12
0x18010b50d  push    r13
0x18010b50f  push    r14
0x18010b511  push    r15
0x18010b513  sub     rsp, 120h
0x18010b51a  mov     r13, r8
0x18010b51d  mov     r12, rdx
0x18010b520  mov     rdi, rcx
0x18010b523  xor     r14d, r14d
0x18010b526  mov     esi, r14d
0x18010b529  mov     dword ptr [rsp+148h+arg_0], r14d
0x18010b531  test    byte ptr [rcx+0C0h], 4
0x18010b538  jz      loc_18010B8AE
0x18010b53e  mov     rax, [rdi]
0x18010b541  mov     rcx, rdi
0x18010b544  mov     rax, [rax+2C8h]
0x18010b54b  call    cs:__guard_dispatch_icall_fptr
0x18010b551  test    al, al
0x18010b553  jz      loc_18010B77C
0x18010b559  mov     rcx, [rdi+90h]
0x18010b560  mov     rax, [rcx]
0x18010b563  mov     rax, [rax+100h]
0x18010b56a  call    cs:__guard_dispatch_icall_fptr
0x18010b570  test    al, al
0x18010b572  jnz     loc_18010B76C
0x18010b578  mov     rcx, [rdi+90h]
0x18010b57f  mov     rax, [rcx]
0x18010b582  mov     rax, [rax+2E8h]
0x18010b589  call    cs:__guard_dispatch_icall_fptr
0x18010b58f  mov     rcx, rax
0x18010b592  mov     rax, [rax]
0x18010b595  mov     rax, [rax+40h]
0x18010b599  call    cs:__guard_dispatch_icall_fptr
0x18010b59f  test    al, al
0x18010b5a1  jnz     loc_18010B76C
0x18010b5a7  mov     rcx, [rdi+0A0h]; struct Ofc::CProxyPtrImpl *
0x18010b5ae  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x18010b5b3  mov     [rsp+148h+arg_18], rax
0x18010b5bb  cmp     qword ptr [rax+10h], 0
0x18010b5c0  jz      short loc_18010B5E8
0x18010b5c2  mov     rcx, rax; this
0x18010b5c5  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x18010b5ca  mov     rcx, rax
0x18010b5cd  mov     rax, [rax]
0x18010b5d0  mov     rdx, rdi
0x18010b5d3  mov     rax, [rax+0C8h]
0x18010b5da  call    cs:__guard_dispatch_icall_fptr
0x18010b5e0  test    al, al
0x18010b5e2  jnz     loc_18010BD8A
0x18010b5e8  lea     rcx, [rsp+148h+arg_0]
0x18010b5f0  call    cs:__imp_?GetCurrentExecutionContext@ApplicationModel@Mso@@YA?AV?$TCntPtr@UIExecutionContext@ApplicationModel@Mso@@@2@XZ; Mso::ApplicationModel::GetCurrentExecutionContext(void)
0x18010b5f6  mov     rcx, [rsp+148h+arg_0]
0x18010b5fe  test    rcx, rcx
0x18010b601  jz      loc_18010B70C
0x18010b607  call    cs:__imp_?VerifyUIThread@ApplicationModel@Mso@@YA_NPEBUIExecutionContext@12@@Z; Mso::ApplicationModel::VerifyUIThread(Mso::ApplicationModel::IExecutionContext const *)
0x18010b60d  test    al, al
0x18010b60f  jz      loc_18010BE2D
0x18010b615  lea     r15, [rdi+80h]
0x18010b61c  mov     rbx, [r15]
0x18010b61f  test    rbx, rbx
0x18010b622  jz      loc_18010B845
0x18010b628  mov     rax, [rbx+8]
0x18010b62c  movsxd  rcx, dword ptr [rax+4]
0x18010b630  add     rcx, 8
0x18010b634  add     rcx, rbx
0x18010b637  mov     rax, [rcx]
0x18010b63a  mov     rax, [rax+8]
0x18010b63e  call    cs:__guard_dispatch_icall_fptr
0x18010b644  mov     rdx, [r12]
0x18010b648  test    rdx, rdx
0x18010b64b  jz      short loc_18010B669
0x18010b64d  mov     rax, [rdx+8]
0x18010b651  movsxd  rcx, dword ptr [rax+4]
0x18010b655  add     rdx, 8
0x18010b659  add     rcx, rdx
0x18010b65c  mov     rax, [rcx]
0x18010b65f  mov     rax, [rax+10h]
0x18010b663  call    cs:__guard_dispatch_icall_fptr
0x18010b669  mov     [r12], rbx
0x18010b66d  mov     rcx, [rsp+148h+arg_0]
0x18010b675  test    rcx, rcx
0x18010b678  jz      short loc_18010B6AB
0x18010b67a  call    cs:__imp_?VerifyUIThread@ApplicationModel@Mso@@YA_NPEBUIExecutionContext@12@@Z; Mso::ApplicationModel::VerifyUIThread(Mso::ApplicationModel::IExecutionContext const *)
0x18010b680  test    al, al
0x18010b682  jz      short loc_18010B6AB
0x18010b684  mov     rcx, [r15]
0x18010b687  mov     rax, [rcx]
0x18010b68a  lea     rdx, [rsp+148h+var_110]
0x18010b68f  mov     rax, [rax+0D0h]
0x18010b696  call    cs:__guard_dispatch_icall_fptr
0x18010b69c  mov     esi, 1
0x18010b6a1  cmp     qword ptr [rax], 0
0x18010b6a5  jnz     loc_18010B83C
0x18010b6ab  xor     bl, bl
0x18010b6ad  test    sil, 1
0x18010b6b1  jz      short loc_18010B6D2
0x18010b6b3  and     esi, 0FFFFFFFEh
0x18010b6b6  mov     rcx, [rsp+148h+var_110]
0x18010b6bb  test    rcx, rcx
0x18010b6be  jz      short loc_18010B6D2
0x18010b6c0  mov     [rsp+148h+var_110], r14
0x18010b6c5  mov     rax, [rcx]
0x18010b6c8  mov     rax, [rax+10h]
0x18010b6cc  call    cs:__guard_dispatch_icall_fptr
0x18010b6d2  mov     rcx, [r15]
0x18010b6d5  mov     rax, [rcx]
0x18010b6d8  lea     rdx, [rsp+148h+var_118]
0x18010b6dd  mov     rax, [rax+0D0h]
0x18010b6e4  call    cs:__guard_dispatch_icall_fptr
0x18010b6ea  test    bl, bl
0x18010b6ec  jz      loc_18010BBD9
0x18010b6f2  mov     rcx, [rax]
0x18010b6f5  test    rcx, rcx
0x18010b6f8  jnz     loc_18010BBE6
0x18010b6fe  xor     edx, edx
0x18010b700  mov     ecx, 1E3C3840h
0x18010b705  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x18010b70b  nop
0x18010b70c  mov     rdx, [r12]
0x18010b710  test    rdx, rdx
0x18010b713  jz      short loc_18010B739
0x18010b715  mov     rax, [rdx+8]
0x18010b719  movsxd  rcx, dword ptr [rax+4]
0x18010b71d  add     rdx, 8
0x18010b721  add     rcx, rdx
0x18010b724  mov     rax, [rcx]
0x18010b727  mov     rax, [rax+10h]
0x18010b72b  call    cs:__guard_dispatch_icall_fptr
0x18010b731  mov     rcx, [rsp+148h+arg_0]
0x18010b739  mov     [r12], r14
0x18010b73d  test    rcx, rcx
0x18010b740  jz      short loc_18010B758
0x18010b742  mov     [rsp+148h+arg_0], r14
0x18010b74a  mov     rax, [rcx]
0x18010b74d  mov     rax, [rax+8]
0x18010b751  call    cs:__guard_dispatch_icall_fptr
0x18010b757  nop
0x18010b758  lea     rcx, [rsp+148h+arg_18]; struct Ofc::CProxyPtrImpl **
0x18010b760  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x18010b765  xor     eax, eax
0x18010b767  jmp     loc_18010B81F
0x18010b76c  mov     rcx, rdi; this
0x18010b76f  call    ?FShouldGenerateNodeForInvisibleObject@Art@@YA_NPEAVViewElement@1@@Z; Art::FShouldGenerateNodeForInvisibleObject(Art::ViewElement *)
0x18010b774  test    al, al
0x18010b776  jnz     loc_18010B5A7
0x18010b77c  mov     rdx, [r12]
0x18010b780  test    rdx, rdx
0x18010b783  jz      short loc_18010B7A1
0x18010b785  mov     rax, [rdx+8]
0x18010b789  movsxd  rcx, dword ptr [rax+4]
0x18010b78d  add     rdx, 8
0x18010b791  add     rcx, rdx
0x18010b794  mov     rax, [rcx]
0x18010b797  mov     rax, [rax+10h]
0x18010b79b  call    cs:__guard_dispatch_icall_fptr
0x18010b7a1  mov     [r12], r14
0x18010b7a5  xor     eax, eax
0x18010b7a7  jmp     short loc_18010B81F
0x18010b7a9  xor     r15b, r15b
0x18010b7ac  test    sil, 2
0x18010b7b0  jz      short loc_18010B7CE
0x18010b7b2  mov     rcx, [rsp+148h+var_118]
0x18010b7b7  test    rcx, rcx
0x18010b7ba  jz      short loc_18010B7CE
0x18010b7bc  mov     [rsp+148h+var_118], r14
0x18010b7c1  mov     rax, [rcx]
0x18010b7c4  mov     rax, [rax+10h]
0x18010b7c8  call    cs:__guard_dispatch_icall_fptr
0x18010b7ce  test    r15b, r15b
0x18010b7d1  jnz     loc_18010BDC7
0x18010b7d7  test    rbx, rbx
0x18010b7da  jz      short loc_18010B7ED
0x18010b7dc  mov     rax, [rbx]
0x18010b7df  mov     rcx, rbx
0x18010b7e2  mov     rax, [rax+10h]
0x18010b7e6  call    cs:__guard_dispatch_icall_fptr
0x18010b7ec  nop
0x18010b7ed  mov     rcx, [rsp+148h+arg_0]
0x18010b7f5  test    rcx, rcx
0x18010b7f8  jz      short loc_18010B810
0x18010b7fa  mov     [rsp+148h+arg_0], r14
0x18010b802  mov     rax, [rcx]
0x18010b805  mov     rax, [rax+8]
0x18010b809  call    cs:__guard_dispatch_icall_fptr
0x18010b80f  nop
0x18010b810  lea     rcx, [rsp+148h+arg_18]; struct Ofc::CProxyPtrImpl **
0x18010b818  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x18010b81d  xor     eax, eax
0x18010b81f  lea     r11, [rsp+148h+var_28]
0x18010b827  mov     rbx, [r11+38h]
0x18010b82b  mov     rsi, [r11+40h]
0x18010b82f  mov     rsp, r11
0x18010b832  pop     r15
0x18010b834  pop     r14
0x18010b836  pop     r13
0x18010b838  pop     r12
0x18010b83a  pop     rdi
0x18010b83b  retn
0x18010b83c  movzx   ebx, sil
0x18010b840  jmp     loc_18010B6AD
0x18010b845  mov     [rsp+148h+var_100], r14
0x18010b84a  mov     rax, [rdi]
0x18010b84d  lea     rdx, [rsp+148h+var_100]
0x18010b852  mov     rcx, rdi
0x18010b855  mov     rax, [rax+2B8h]
0x18010b85c  call    cs:__guard_dispatch_icall_fptr
0x18010b862  mov     ebx, eax
0x18010b864  test    eax, eax
0x18010b866  jns     short loc_18010B8CB
0x18010b868  mov     rcx, [rsp+148h+arg_0]
0x18010b870  cmp     ebx, 80004004h
0x18010b876  jnz     loc_18010BBA7
0x18010b87c  test    rcx, rcx
0x18010b87f  jz      short loc_18010B897
0x18010b881  mov     [rsp+148h+arg_0], r14
0x18010b889  mov     rax, [rcx]
0x18010b88c  mov     rax, [rax+8]
0x18010b890  call    cs:__guard_dispatch_icall_fptr
0x18010b896  nop
0x18010b897  lea     rcx, [rsp+148h+arg_18]; struct Ofc::CProxyPtrImpl **
0x18010b89f  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x18010b8a4  mov     eax, 80004004h
0x18010b8a9  jmp     loc_18010B81F
0x18010b8ae  mov     rax, [rcx]
0x18010b8b1  mov     rax, [rax+490h]
0x18010b8b8  call    cs:__guard_dispatch_icall_fptr
0x18010b8be  test    al, al
0x18010b8c0  jnz     loc_18010B53E
0x18010b8c6  jmp     loc_18010B77C
0x18010b8cb  mov     rcx, [rsp+148h+var_100]
0x18010b8d0  test    rcx, rcx
0x18010b8d3  jz      short loc_18010B868
0x18010b8d5  mov     rax, [rcx]
0x18010b8d8  mov     rax, [rax+30h]
0x18010b8dc  call    cs:__guard_dispatch_icall_fptr
0x18010b8e2  cmp     eax, 3
0x18010b8e5  jz      short loc_18010B868
0x18010b8e7  mov     rcx, [rsp+148h+var_100]
0x18010b8ec  mov     rax, [rcx]
0x18010b8ef  mov     rax, [rax+20h]
0x18010b8f3  call    cs:__guard_dispatch_icall_fptr
0x18010b8f9  mov     rcx, rax
0x18010b8fc  mov     rax, [rax]
0x18010b8ff  mov     rax, [rax+20h]
0x18010b903  call    cs:__guard_dispatch_icall_fptr
0x18010b909  mov     rdx, rax
0x18010b90c  mov     r8b, 1
0x18010b90f  lea     rcx, [rsp+148h+var_48]
0x18010b917  call    cs:__imp_??0CurrentContextHolder@FastModel@@QEAA@AEAVContext@1@_N@Z; FastModel::CurrentContextHolder::CurrentContextHolder(FastModel::Context &,bool)
0x18010b91d  mov     rcx, rdi
0x18010b920  call    ?GetView@ViewElement@Art@@QEAAAEBV?$TWeakPtr@VView@Art@@@Ofc@@XZ; Art::ViewElement::GetView(void)
0x18010b925  mov     rcx, [rax]; struct Ofc::CProxyPtrImpl *
0x18010b928  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x18010b92d  mov     [rsp+148h+var_E8], rax
0x18010b932  xorps   xmm0, xmm0
0x18010b935  movdqa  [rsp+148h+var_C8], xmm0
0x18010b93e  mov     qword ptr [rsp+148h+var_C8+8], r14
0x18010b946  movdqa  [rsp+148h+var_B8], xmm0
0x18010b94f  mov     qword ptr [rsp+148h+var_B8+8], r14
0x18010b957  movdqa  [rsp+148h+var_A8], xmm0
0x18010b960  mov     qword ptr [rsp+148h+var_A8+8], r14
0x18010b968  movdqa  [rsp+148h+var_98], xmm0
0x18010b971  mov     qword ptr [rsp+148h+var_98+8], r14
0x18010b979  movdqa  [rsp+148h+var_88], xmm0
0x18010b982  mov     qword ptr [rsp+148h+var_88+8], r14
0x18010b98a  mov     [rsp+148h+var_78], r14d
0x18010b992  lea     rax, word_180A9C374
0x18010b999  mov     [rsp+148h+var_70], rax
0x18010b9a1  mov     [rsp+148h+var_68], rax
0x18010b9a9  mov     [rsp+148h+var_60], 0
0x18010b9b1  mov     [rsp+148h+var_58], rax
0x18010b9b9  mov     rax, [rdi]
0x18010b9bc  lea     rdx, [rsp+148h+var_C8]
0x18010b9c4  mov     rcx, rdi
0x18010b9c7  mov     rax, [rax+3C8h]
0x18010b9ce  call    cs:__guard_dispatch_icall_fptr
0x18010b9d4  mov     rcx, rdi; this
0x18010b9d7  call    ?FMinimalDecorativeFastAccNode@ViewElement@Art@@QEBA_NXZ; Art::ViewElement::FMinimalDecorativeFastAccNode(void)
0x18010b9dc  test    al, al
0x18010b9de  jnz     loc_18010BD48
0x18010b9e4  mov     rcx, rdi; this
0x18010b9e7  call    ?FInvisible@ViewElement@Art@@QEBA_NXZ; Art::ViewElement::FInvisible(void)
0x18010b9ec  test    al, al
0x18010b9ee  jnz     loc_18010BFD9
0x18010b9f4  mov     rax, [rdi]
0x18010b9f7  mov     rsi, [rax+2D0h]
0x18010b9fe  mov     rbx, [rsp+148h+var_100]
0x18010ba03  mov     rax, [rbx]
0x18010ba06  mov     rcx, rbx
0x18010ba09  mov     rax, [rax+20h]
0x18010ba0d  call    cs:__guard_dispatch_icall_fptr
0x18010ba13  mov     [rsp+148h+var_128], r13
0x18010ba18  mov     r9, rbx
0x18010ba1b  mov     r8, rax
0x18010ba1e  lea     rdx, [rsp+148h+var_108]
0x18010ba23  mov     rcx, rdi
0x18010ba26  mov     rax, rsi
  ... truncated ...
```
