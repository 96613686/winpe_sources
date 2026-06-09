# CBandWorkArea::SetOuterWorkArea(tagRECT const *,bool)

- ea: `0x180036540`
- end: `0x180036fb9`
- name: `?SetOuterWorkArea@CBandWorkArea@@UEAA_NPEBUtagRECT@@_N@Z`
- size: `2681`
- prototype: `bool(CBandWorkArea *__hidden this, const struct tagRECT *, bool)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180009dd0`
- `0x180036540`
- `0x1800378dc`
- `0x180037958`
- `0x180037bd0`
- `0x180037c3c`
- `0x1800f35e0`
- `0x180142e10`
- `0x180142e34`
- `0x180143a7c`
- `0x180144006`
- `0x18014404e`
- `0x1803bb010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180036589`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800365e2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180036a9b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180036f18`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180036589`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800365e2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180036a9b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180036f18`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800365c6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180036637`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180036adc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180036f3f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800365c6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180036637`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180036adc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180036f3f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800368f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180036a0a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180036bc6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180036ce2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800368f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180036a0a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180036bc6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180036ce2`
- `api-ms-win-ntuser-rectangle-l1-1-0!SubtractRect` at `0x180036f09`
- `api-ms-win-ntuser-rectangle-l1-1-0!SubtractRect` at `0x180036f09`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x18003660a`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x180036628`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x180036acd`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x18003660a`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x180036628`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x180036acd`
- `api-ms-win-ntuser-rectangle-l1-1-0!EqualRect` at `0x1800365a0`
- `api-ms-win-ntuser-rectangle-l1-1-0!EqualRect` at `0x1800365f4`
- `api-ms-win-ntuser-rectangle-l1-1-0!EqualRect` at `0x180036ab0`
- `api-ms-win-ntuser-rectangle-l1-1-0!EqualRect` at `0x180036f2a`
- `api-ms-win-ntuser-rectangle-l1-1-0!EqualRect` at `0x1800365a0`
- `api-ms-win-ntuser-rectangle-l1-1-0!EqualRect` at `0x1800365f4`
- `api-ms-win-ntuser-rectangle-l1-1-0!EqualRect` at `0x180036ab0`
- `api-ms-win-ntuser-rectangle-l1-1-0!EqualRect` at `0x180036f2a`
- `api-ms-win-ntuser-rectangle-l1-1-0!IsRectEmpty` at `0x180036647`
- `api-ms-win-ntuser-rectangle-l1-1-0!IsRectEmpty` at `0x180036647`

## pseudocode

```c
bool __fastcall CBandWorkArea::SetOuterWorkArea(RTL_SRWLOCK *this, const struct tagRECT *a2, char a3)
{
  RTL_SRWLOCK *v3; // rsi
  RTL_SRWLOCK *v4; // r12
  const RECT *v6; // r15
  const RECT *v7; // r14
  BOOL v8; // edi
  char v9; // bl
  RTL_SRWLOCK *v10; // rax
  int v11; // r13d
  Microsoft::WRL::FtmBase *v12; // rax
  Microsoft::WRL::FtmBase *v13; // rdi
  struct Microsoft::WRL::Details::ModuleBase *v14; // rcx
  unsigned __int64 Ptr; // rsi
  int v16; // ebx
  bool v17; // di
  unsigned int v18; // ebx
  __int64 v19; // rcx
  bool result; // al
  unsigned int i; // esi
  __int64 v22; // rcx
  unsigned __int64 v23; // rbx
  char *v24; // rax
  char *v25; // r14
  unsigned __int64 v26; // rax
  __int64 *v27; // r15
  __int64 *v28; // r12
  unsigned __int64 v29; // rcx
  __int64 v30; // rsi
  unsigned __int64 v31; // rsi
  unsigned __int64 v32; // r8
  unsigned __int64 v33; // rbx
  char *v34; // rax
  char *v35; // r14
  unsigned __int64 v36; // rax
  __int64 *v37; // rdx
  __int64 v38; // rcx
  RTL_SRWLOCK *v39; // r15
  CGITCallbackArray *v40; // rax
  CGITCallbackArray *v41; // rax
  unsigned __int64 v42; // rdi
  CGITCallbackArray *v43; // rbx
  unsigned __int64 v44; // r8
  unsigned __int64 v45; // rcx
  unsigned __int64 v46; // rsi
  char *v47; // rax
  char *v48; // r14
  unsigned __int64 v49; // rax
  int v50; // eax
  __int64 *v51; // r15
  __int64 *v52; // r12
  unsigned __int64 v53; // rcx
  __int64 v54; // rdi
  unsigned __int64 v55; // rdi
  unsigned __int64 v56; // r8
  unsigned __int64 v57; // rsi
  unsigned int v58; // edi
  char *v59; // rax
  char *v60; // r14
  unsigned __int64 v61; // rax
  int v62; // eax
  __int64 *v63; // rdx
  __int64 v64; // rcx
  __int64 v65; // rdi
  int (__fastcall *v66)(__int64, _QWORD, GUID *, Microsoft::WRL::FtmBase **); // rbx
  Microsoft::WRL::FtmBase *v67; // rcx
  Microsoft::WRL::FtmBase *v68; // rcx
  int v69; // [rsp+20h] [rbp-49h]
  bool v70; // [rsp+30h] [rbp-39h]
  char v71; // [rsp+31h] [rbp-38h]
  Microsoft::WRL::FtmBase *v72; // [rsp+38h] [rbp-31h] BYREF
  __int64 v73; // [rsp+40h] [rbp-29h] BYREF
  const struct tagRECT *v74; // [rsp+48h] [rbp-21h] BYREF
  PSRWLOCK SRWLock; // [rsp+50h] [rbp-19h]
  RTL_SRWLOCK *v76; // [rsp+58h] [rbp-11h]
  BOOL v77; // [rsp+60h] [rbp-9h]
  RECT rcSrc2; // [rsp+68h] [rbp-1h] BYREF
  struct tagRECT rcDst; // [rsp+78h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v3 = this + 10;
  v76 = this;
  v4 = this;
  v74 = a2;
  SRWLock = this + 10;
  v6 = a2;
  AcquireSRWLockExclusive(this + 10);
  v7 = (const RECT *)&v4[5];
  v77 = EqualRect(v6, (const RECT *)&v4[5]);
  v8 = v77;
  if ( a3 || (v10 = v4 + 9, LOBYTE(v4[9].Ptr)) || !v77 )
  {
    v9 = 1;
    v10 = v4 + 9;
  }
  else
  {
    v9 = 0;
  }
  LOBYTE(v10->Ptr) = 0;
  ReleaseSRWLockExclusive(v3);
  if ( !v9 )
    return 0;
  v70 = 0;
  AcquireSRWLockExclusive(v3);
  if ( !EqualRect(v6, (const RECT *)&v4[5]) )
  {
    CopyRect((LPRECT)&v4[5], v6);
    v70 = 1;
  }
  rcDst = 0;
  CopyRect(&rcDst, (const RECT *)&v4[5]);
  ReleaseSRWLockExclusive(v3);
  v11 = -2147024882;
  if ( !IsRectEmpty(&rcDst) )
  {
    v71 = 1;
    AcquireSRWLockShared_0(v4 + 12);
    v73 = 0;
    v12 = (Microsoft::WRL::FtmBase *)operator new(0x50u, (const struct std::nothrow_t *)std::nothrow);
    v72 = v12;
    v13 = v12;
    if ( !v12 )
    {
      Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::SimpleClassFactory<CAccessibilityDock,0>>::~MakeAllocator<Microsoft::WRL::SimpleClassFactory<CAccessibilityDock,0>>(&v72);
      v16 = -2147024882;
LABEL_17:
      ReleaseSRWLockShared_0(v4 + 12);
      if ( v16 >= 0 )
      {
        LODWORD(v74) = 0;
        if ( (*(int (__fastcall **)(__int64, const struct tagRECT **))(*(_QWORD *)v73 + 24LL))(v73, &v74) >= 0 )
        {
          v17 = 1;
          v18 = 0;
          do
          {
            if ( v18 >= (unsigned int)v74 )
              break;
            v72 = 0;
            if ( (*(int (__fastcall **)(__int64, _QWORD, GUID *, Microsoft::WRL::FtmBase **))(*(_QWORD *)v73 + 32LL))(
                   v73,
                   v18,
                   &GUID_05088755_ef51_4684_8f7c_b07c8d5d5f39,
                   &v72) >= 0 )
            {
              rcSrc2 = 0;
              if ( (*(int (__fastcall **)(Microsoft::WRL::FtmBase *, struct tagRECT *, RECT *))(*(_QWORD *)v72 + 32LL))(
                     v72,
                     &rcDst,
                     &rcSrc2) >= 0 )
              {
                (*(void (__fastcall **)(Microsoft::WRL::FtmBase *, _QWORD, struct tagRECT *))(*(_QWORD *)v72 + 24LL))(
                  v72,
                  LODWORD(v4[2].Ptr),
                  &rcDst);
                SubtractRect(&rcDst, &rcDst, &rcSrc2);
              }
              AcquireSRWLockExclusive(v3);
              v17 = EqualRect(v6, v7);
              ReleaseSRWLockExclusive(v3);
            }
            v68 = v72;
            if ( v72 )
            {
              v72 = 0;
              (*(void (__fastcall **)(Microsoft::WRL::FtmBase *))(*(_QWORD *)v68 + 16LL))(v68);
            }
            ++v18;
          }
          while ( v17 );
          v71 = v17;
        }
      }
      v19 = v73;
      if ( v73 )
      {
        v73 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
      }
      if ( !v71 )
        return 0;
      v8 = v77;
      goto LABEL_70;
    }
    Microsoft::WRL::FtmBase::FtmBase(v12);
    v14 = Microsoft::WRL::Details::ModuleBase::module_;
    *(_QWORD *)v13 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::WRL::FtmBase,IObjectArray>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,IObjectArray>>'};
    *((_QWORD *)v13 + 4) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::WRL::FtmBase,IObjectArray>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IObjectArray>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,IObjectArray>>'};
    *((_DWORD *)v13 + 11) = 1;
    if ( v14 )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)v14 + 8LL))(v14);
    v72 = 0;
    *(_QWORD *)v13 = &CGITCallbackArray::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,IObjectArray>>'};
    *((_QWORD *)v13 + 4) = &CGITCallbackArray::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IObjectArray>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,IObjectArray>>'};
    *((_QWORD *)v13 + 6) = 0;
    *((_QWORD *)v13 + 7) = 0;
    *((_QWORD *)v13 + 8) = 0;
    *((_QWORD *)v13 + 9) = 0;
    Ptr = (unsigned __int64)v4[14].Ptr;
    if ( !Ptr )
      goto LABEL_15;
    if ( Ptr > 0xFFFFFFFE )
    {
      v16 = -2147024774;
    }
    else
    {
      *(_QWORD *)&rcSrc2.left = 0;
      if ( is_mul_ok(0, 2u) && (*(_QWORD *)&rcSrc2.left = 0, v23 = 8 * Ptr, is_mul_ok(Ptr, 8u)) )
      {
        v24 = (char *)CoTaskMemRealloc(*((LPVOID *)v13 + 6), 8 * Ptr);
        v25 = v24;
        if ( v24 )
        {
          v26 = CTCoAllocPolicy::_CoTaskMemSize(v24);
          if ( v26 > v23 )
            memset_0(&v25[v23], 0, v26 - v23);
          v16 = 0;
        }
        else
        {
          v16 = -2147024882;
        }
        if ( v16 >= 0 )
        {
          *((_QWORD *)v13 + 9) = Ptr;
          *((_QWORD *)v13 + 6) = v25;
          v27 = (__int64 *)v4[13].Ptr;
          v28 = &v27[(__int64)v4[14].Ptr];
          while ( v27 != v28 )
          {
            v29 = *((_QWORD *)v13 + 9);
            v30 = *((_QWORD *)v13 + 7);
            if ( v30 == v29 )
            {
              v31 = v30 + 1;
              v16 = -2147024774;
              if ( v31 > 0xFFFFFFFE )
                goto LABEL_53;
              if ( v31 > v29 )
              {
                *(_QWORD *)&rcSrc2.left = 0;
                v32 = 2 * v29;
                if ( !is_mul_ok(v29, 2u) )
                  goto LABEL_52;
                if ( v29 > 0x1000 )
                  v32 = v29 + 4096;
                if ( v31 <= v32 )
                {
                  v31 = v32;
                  if ( v32 > 0xFFFFFFFE )
                    v31 = 4294967294LL;
                }
                *(_QWORD *)&rcSrc2.left = 0;
                v33 = 8 * v31;
                if ( !is_mul_ok(v31, 8u) )
                {
LABEL_52:
                  v16 = -2147024362;
LABEL_53:
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x63,
                    (unsigned int)"shell\\lib\\gitreglist.cpp",
                    (const char *)(unsigned int)v16,
                    v69);
                  v4 = v76;
                  v6 = v74;
                  goto LABEL_54;
                }
                v34 = (char *)CoTaskMemRealloc(*((LPVOID *)v13 + 6), 8 * v31);
                v35 = v34;
                if ( v34 )
                {
                  v36 = CTCoAllocPolicy::_CoTaskMemSize(v34);
                  if ( v36 > v33 )
                    memset_0(&v35[v33], 0, v36 - v33);
                  v16 = 0;
                }
                else
                {
                  v16 = -2147024882;
                }
                if ( v16 < 0 )
                  goto LABEL_53;
                *((_QWORD *)v13 + 9) = v31;
                *((_QWORD *)v13 + 6) = v35;
              }
            }
            v37 = (__int64 *)(*((_QWORD *)v13 + 6) + 8 * (*((_QWORD *)v13 + 7))++);
            if ( v37 )
            {
              v38 = *v27;
              *v37 = *v27;
              if ( v38 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 8LL))(v38);
            }
            ++v27;
          }
          v4 = v76;
          v6 = v74;
LABEL_15:
          v16 = (**(__int64 (__fastcall ***)(Microsoft::WRL::FtmBase *, GUID *, __int64 *))v13)(
                  v13,
                  &GUID_92ca9dcd_5622_4bba_a805_5e9f541bd8c9,
                  &v73);
          (*(void (__fastcall **)(Microsoft::WRL::FtmBase *))(*(_QWORD *)v13 + 16LL))(v13);
LABEL_16:
          v3 = SRWLock;
          v7 = (const RECT *)&v4[5];
          goto LABEL_17;
        }
      }
      else
      {
        v16 = -2147024362;
      }
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5F,
      (unsigned int)"shell\\lib\\gitreglist.cpp",
      (const char *)(unsigned int)v16,
      v69);
LABEL_54:
    (*(void (__fastcall **)(Microsoft::WRL::FtmBase *))(*(_QWORD *)v13 + 16LL))(v13);
    Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::SimpleClassFactory<CAccessibilityDock,0>>::~MakeAllocator<Microsoft::WRL::SimpleClassFactory<CAccessibilityDock,0>>(&v72);
    goto LABEL_16;
  }
LABEL_70:
  AcquireSRWLockExclusive(v3);
  if ( !EqualRect(&rcDst, (const RECT *)&v4[7]) )
  {
    v70 = 1;
    CopyRect((LPRECT)&v4[7], &rcDst);
  }
  ReleaseSRWLockExclusive(v3);
  result = v70;
  if ( v70 && !v8 )
  {
    v39 = v4 + 24;
    v73 = 0;
    SRWLock = v4 + 24;
    rcDst = 0;
    AcquireSRWLockShared_0(v4 + 24);
    v73 = 0;
    v40 = (CGITCallbackArray *)operator new(0x50u, (const struct std::nothrow_t *)std::nothrow);
    v72 = v40;
    if ( v40 )
    {
      v41 = CGITCallbackArray::CGITCallbackArray(v40);
      v42 = (unsigned __int64)v4[26].Ptr;
      v43 = v41;
      v72 = 0;
      if ( !v42 )
      {
LABEL_28:
        v11 = (**(__int64 (__fastcall ***)(CGITCallbackArray *, GUID *, __int64 *))v43)(
                v43,
                &GUID_92ca9dcd_5622_4bba_a805_5e9f541bd8c9,
                &v73);
        (*(void (__fastcall **)(CGITCallbackArray *))(*(_QWORD *)v43 + 16LL))(v43);
        goto LABEL_29;
      }
      if ( v42 > 0xFFFFFFFE )
      {
        v11 = -2147024774;
      }
      else
      {
        v44 = *((_QWORD *)v41 + 9);
        if ( v42 <= v44 )
          goto LABEL_91;
        v45 = 2 * v44;
        if ( !is_mul_ok(v44, 2u) )
          goto LABEL_26;
        if ( v44 > 0x1000 )
          v45 = v44 + 4096;
        if ( v42 <= v45 )
        {
          v42 = v45;
          if ( v45 > 0xFFFFFFFE )
            v42 = 4294967294LL;
        }
        v46 = 8 * v42;
        if ( is_mul_ok(v42, 8u) )
        {
          v47 = (char *)CoTaskMemRealloc(*((LPVOID *)v41 + 6), 8 * v42);
          v48 = v47;
          if ( v47 )
          {
            v49 = CTCoAllocPolicy::_CoTaskMemSize(v47);
            if ( v49 > v46 )
              memset_0(&v48[v46], 0, v49 - v46);
            v50 = 0;
          }
          else
          {
            v50 = -2147024882;
          }
          if ( v50 >= 0 )
          {
            *((_QWORD *)v43 + 6) = v48;
            *((_QWORD *)v43 + 9) = v42;
LABEL_91:
            v51 = (__int64 *)v4[25].Ptr;
            v52 = &v51[(__int64)v4[26].Ptr];
            while ( v51 != v52 )
            {
              v53 = *((_QWORD *)v43 + 9);
              v54 = *((_QWORD *)v43 + 7);
              if ( v54 == v53 )
              {
                v55 = v54 + 1;
                if ( v55 > 0xFFFFFFFE )
                {
                  v58 = -2147024774;
                  goto LABEL_102;
                }
                if ( v55 > v53 )
                {
                  v56 = 2 * v53;
                  if ( !is_mul_ok(v53, 2u) )
                    goto LABEL_101;
                  if ( v53 > 0x1000 )
                    v56 = v53 + 4096;
                  if ( v55 <= v56 )
                  {
                    v55 = v56;
                    if ( v56 > 0xFFFFFFFE )
                      v55 = 4294967294LL;
                  }
                  v57 = 8 * v55;
                  if ( !is_mul_ok(v55, 8u) )
                  {
LABEL_101:
                    v58 = -2147024362;
LABEL_102:
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x63,
                      (unsigned int)"shell\\lib\\gitreglist.cpp",
                      (const char *)v58,
                      v69);
                    v39 = SRWLock;
                    v4 = v76;
                    v11 = v58;
                    goto LABEL_103;
                  }
                  v59 = (char *)CoTaskMemRealloc(*((LPVOID *)v43 + 6), 8 * v55);
                  v60 = v59;
                  if ( v59 )
                  {
                    v61 = CTCoAllocPolicy::_CoTaskMemSize(v59);
                    if ( v61 > v57 )
                      memset_0(&v60[v57], 0, v61 - v57);
                    v62 = 0;
                  }
                  else
                  {
                    v62 = -2147024882;
                  }
                  if ( v62 < 0 )
                  {
                    v58 = v62;
                    goto LABEL_102;
                  }
                  *((_QWORD *)v43 + 6) = v60;
                  *((_QWORD *)v43 + 9) = v55;
                }
              }
              v63 = (__int64 *)(*((_QWORD *)v43 + 6) + 8 * (*((_QWORD *)v43 + 7))++);
              if ( v63 )
              {
                v64 = *v51;
                *v63 = *v51;
                if ( v64 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 8LL))(v64);
              }
              ++v51;
            }
            v39 = SRWLock;
            v4 = v76;
            goto LABEL_28;
          }
          v11 = v50;
        }
        else
        {
LABEL_26:
          v11 = -2147024362;
        }
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5F,
        (unsigned int)"shell\\lib\\gitreglist.cpp",
        (const char *)(unsigned int)v11,
        v69);
LABEL_103:
      if ( v43 )
        (*(void (__fastcall **)(CGITCallbackArray *))(*(_QWORD *)v43 + 16LL))(v43);
    }
    Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::SimpleClassFactory<CAccessibilityDock,0>>::~MakeAllocator<Microsoft::WRL::SimpleClassFactory<CAccessibilityDock,0>>(&v72);
LABEL_29:
    ReleaseSRWLockShared_0(v39);
    if ( v11 >= 0 )
    {
      LODWORD(v74) = 0;
      if ( (*(int (__fastcall **)(__int64, const struct tagRECT **))(*(_QWORD *)v73 + 24LL))(v73, &v74) >= 0 )
      {
        for ( i = 0; i < (unsigned int)v74; ++i )
        {
          v65 = v73;
          v72 = 0;
          v66 = *(int (__fastcall **)(__int64, _QWORD, GUID *, Microsoft::WRL::FtmBase **))(*(_QWORD *)v73 + 32LL);
          Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v72);
          if ( v66(v65, i, &GUID_6a5e657d_223a_4875_838b_c311ed73523b, &v72) >= 0 )
            (*(void (__fastcall **)(Microsoft::WRL::FtmBase *, _QWORD, struct tagRECT *))(*(_QWORD *)v72 + 24LL))(
              v72,
              LODWORD(v4[2].Ptr),
              &rcDst);
          v67 = v72;
          if ( v72 )
          {
            v72 = 0;
            (*(void (__fastcall **)(Microsoft::WRL::FtmBase *))(*(_QWORD *)v67 + 16LL))(v67);
          }
        }
      }
    }
    v22 = v73;
    if ( v73 )
    {
      v73 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    }
    return v70;
  }
  return result;
}

```

## disassembly

```asm
0x180036540  mov     [rsp-8+arg_10], rbx
0x180036545  push    rbp
0x180036546  push    rsi
0x180036547  push    rdi
0x180036548  push    r12
0x18003654a  push    r13
0x18003654c  push    r14
0x18003654e  push    r15
0x180036550  lea     rbp, [rsp-27h]
0x180036555  sub     rsp, 90h
0x18003655c  mov     rax, cs:__security_cookie
0x180036563  xor     rax, rsp
0x180036566  mov     [rbp+57h+var_38], rax
0x18003656a  lea     rsi, [rcx+50h]
0x18003656e  mov     [rbp+57h+var_68], rcx
0x180036572  mov     r12, rcx
0x180036575  mov     [rbp+57h+var_78], rdx
0x180036579  mov     rcx, rsi; SRWLock
0x18003657c  mov     [rbp+57h+SRWLock], rsi
0x180036580  mov     bl, r8b
0x180036583  mov     r15, rdx
0x180036586  xor     r13d, r13d
0x180036589  call    cs:__imp_AcquireSRWLockExclusive
0x180036590  nop     dword ptr [rax+rax+00h]
0x180036595  lea     r14, [r12+28h]
0x18003659a  mov     rcx, r15; lprc1
0x18003659d  mov     rdx, r14; lprc2
0x1800365a0  call    cs:__imp_EqualRect
0x1800365a7  nop     dword ptr [rax+rax+00h]
0x1800365ac  mov     [rbp+57h+var_60], eax
0x1800365af  mov     edi, eax
0x1800365b1  test    bl, bl
0x1800365b3  jz      loc_180036E2F
0x1800365b9  mov     bl, 1
0x1800365bb  lea     rax, [r12+48h]
0x1800365c0  mov     rcx, rsi; SRWLock
0x1800365c3  mov     [rax], r13b
0x1800365c6  call    cs:__imp_ReleaseSRWLockExclusive
0x1800365cd  nop     dword ptr [rax+rax+00h]
0x1800365d2  test    bl, bl
0x1800365d4  jz      loc_180036D82
0x1800365da  xor     ebx, ebx
0x1800365dc  mov     rcx, rsi; SRWLock
0x1800365df  mov     [rbp+57h+var_90], bl
0x1800365e2  call    cs:__imp_AcquireSRWLockExclusive
0x1800365e9  nop     dword ptr [rax+rax+00h]
0x1800365ee  mov     rdx, r14; lprc2
0x1800365f1  mov     rcx, r15; lprc1
0x1800365f4  call    cs:__imp_EqualRect
0x1800365fb  nop     dword ptr [rax+rax+00h]
0x180036600  test    eax, eax
0x180036602  jnz     short loc_18003661A
0x180036604  mov     rdx, r15; lprcSrc
0x180036607  mov     rcx, r14; lprcDst
0x18003660a  call    cs:__imp_CopyRect
0x180036611  nop     dword ptr [rax+rax+00h]
0x180036616  mov     [rbp+57h+var_90], 1
0x18003661a  xorps   xmm0, xmm0
0x18003661d  lea     rcx, [rbp+57h+rcDst]; lprcDst
0x180036621  mov     rdx, r14; lprcSrc
0x180036624  movups  xmmword ptr [rbp+57h+rcDst.left], xmm0
0x180036628  call    cs:__imp_CopyRect
0x18003662f  nop     dword ptr [rax+rax+00h]
0x180036634  mov     rcx, rsi; SRWLock
0x180036637  call    cs:__imp_ReleaseSRWLockExclusive
0x18003663e  nop     dword ptr [rax+rax+00h]
0x180036643  lea     rcx, [rbp+57h+rcDst]; lprc
0x180036647  call    cs:__imp_IsRectEmpty
0x18003664e  nop     dword ptr [rax+rax+00h]
0x180036653  mov     r13d, 8007000Eh
0x180036659  test    eax, eax
0x18003665b  jnz     loc_180036D7A
0x180036661  lea     rcx, [r12+60h]; SRWLock
0x180036666  mov     [rbp+57h+var_8F], 1
0x18003666a  mov     [rbp+57h+var_80], rbx
0x18003666e  call    AcquireSRWLockShared_0
0x180036673  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003667a  mov     [rbp+57h+var_80], rbx
0x18003667e  mov     ecx, 50h ; 'P'; unsigned __int64
0x180036683  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180036688  mov     [rbp+57h+var_88], rax
0x18003668c  mov     rdi, rax
0x18003668f  test    rax, rax
0x180036692  jz      loc_180036E4D
0x180036698  mov     rcx, rax; this
0x18003669b  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x1800366a0  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800366a7  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@VFtmBase@23@UIObjectArray@@@WRL@Microsoft@@6B?$Selector@VFtmBase@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$0A@U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UIObjectArray@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::WRL::FtmBase,IObjectArray>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,IObjectArray>>'}
0x1800366ae  mov     [rdi], rax
0x1800366b1  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@VFtmBase@23@UIObjectArray@@@WRL@Microsoft@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIObjectArray@@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$0A@U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UIObjectArray@@@234@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::WRL::FtmBase,IObjectArray>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IObjectArray>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,IObjectArray>>'}
0x1800366b8  mov     [rdi+20h], rax
0x1800366bc  mov     dword ptr [rdi+2Ch], 1
0x1800366c3  test    rcx, rcx
0x1800366c6  jz      short loc_1800366D4
0x1800366c8  mov     rax, [rcx]
0x1800366cb  mov     rax, [rax+8]
0x1800366cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800366d4  lea     rax, ??_7CGITCallbackArray@@6B?$Selector@VFtmBase@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$0A@U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UIObjectArray@@@Details@23@@Details@WRL@Microsoft@@@; const CGITCallbackArray::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,IObjectArray>>'}
0x1800366db  mov     [rbp+57h+var_88], rbx
0x1800366df  mov     [rdi], rax
0x1800366e2  lea     rax, ??_7CGITCallbackArray@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIObjectArray@@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$0A@U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UIObjectArray@@@234@@Details@WRL@Microsoft@@@; const CGITCallbackArray::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IObjectArray>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,IObjectArray>>'}
0x1800366e9  mov     [rdi+20h], rax
0x1800366ed  mov     [rdi+30h], rbx
0x1800366f1  mov     [rdi+38h], rbx
0x1800366f5  mov     [rdi+40h], rbx
0x1800366f9  mov     [rdi+48h], rbx
0x1800366fd  mov     rsi, [r12+70h]
0x180036702  test    rsi, rsi
0x180036705  jz      short loc_180036750
0x180036707  mov     r8d, 0FFFFFFFEh
0x18003670d  cmp     rsi, r8
0x180036710  ja      loc_180036E8A
0x180036716  mov     eax, 2
0x18003671b  mov     qword ptr [rbp+57h+rcSrc2.left], rbx
0x18003671f  mul     rbx
0x180036722  test    rdx, rdx
0x180036725  jz      loc_1800368BD
0x18003672b  mov     ebx, 80070216h
0x180036730  mov     rcx, [rbp+5Fh]; this
0x180036734  lea     r8, aShellLibGitreg; "shell\\lib\\gitreglist.cpp"
0x18003673b  mov     r9d, ebx; char *
0x18003673e  mov     edx, 5Fh ; '_'; void *
0x180036743  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036748  test    ebx, ebx
0x18003674a  js      loc_1800369E6
0x180036750  mov     rax, [rdi]
0x180036753  lea     r8, [rbp+57h+var_80]
0x180036757  lea     rdx, _GUID_92ca9dcd_5622_4bba_a805_5e9f541bd8c9
0x18003675e  mov     rcx, rdi
0x180036761  mov     rax, [rax]
0x180036764  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036769  mov     ebx, eax
0x18003676b  mov     rcx, rdi
0x18003676e  mov     rax, [rdi]
0x180036771  mov     rax, [rax+10h]
0x180036775  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003677a  mov     rsi, [rbp+57h+SRWLock]
0x18003677e  lea     r14, [r12+28h]
0x180036783  lea     rcx, [r12+60h]; SRWLock
0x180036788  call    ReleaseSRWLockShared_0
0x18003678d  test    ebx, ebx
0x18003678f  js      short loc_1800367C3
0x180036791  mov     rcx, [rbp+57h+var_80]
0x180036795  lea     rdx, [rbp+57h+var_78]
0x180036799  mov     dword ptr [rbp+57h+var_78], 0
0x1800367a0  mov     rax, [rcx]
0x1800367a3  mov     rax, [rax+18h]
0x1800367a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800367ac  test    eax, eax
0x1800367ae  js      short loc_1800367C3
0x1800367b0  mov     dil, [rbp+57h+var_8F]
0x1800367b4  xor     ebx, ebx
0x1800367b6  cmp     ebx, dword ptr [rbp+57h+var_78]
0x1800367b9  jb      loc_180036E94
0x1800367bf  mov     [rbp+57h+var_8F], dil
0x1800367c3  mov     rcx, [rbp+57h+var_80]
0x1800367c7  xor     r14d, r14d
0x1800367ca  test    rcx, rcx
0x1800367cd  jz      short loc_1800367DF
0x1800367cf  mov     [rbp+57h+var_80], r14
0x1800367d3  mov     rax, [rcx]
0x1800367d6  mov     rax, [rax+10h]
0x1800367da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800367df  cmp     [rbp+57h+var_8F], r14b
0x1800367e3  jnz     loc_180036A95
0x1800367e9  mov     al, r14b
0x1800367ec  jmp     loc_180036895
0x1800367f1  mov     r13d, 80070216h
0x1800367f7  mov     rcx, [rbp+5Fh]; this
0x1800367fb  lea     r8, aShellLibGitreg; "shell\\lib\\gitreglist.cpp"
0x180036802  mov     r9d, r13d; char *
0x180036805  mov     edx, 5Fh ; '_'; void *
0x18003680a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003680f  test    r13d, r13d
0x180036812  js      loc_180036CB9
0x180036818  mov     rax, [rbx]
0x18003681b  lea     r8, [rbp+57h+var_80]
0x18003681f  lea     rdx, _GUID_92ca9dcd_5622_4bba_a805_5e9f541bd8c9
0x180036826  mov     rcx, rbx
0x180036829  mov     rax, [rax]
0x18003682c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036831  mov     r13d, eax
0x180036834  mov     rcx, rbx
0x180036837  mov     rax, [rbx]
0x18003683a  mov     rax, [rax+10h]
0x18003683e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036843  mov     rcx, r15; SRWLock
0x180036846  call    ReleaseSRWLockShared_0
0x18003684b  test    r13d, r13d
0x18003684e  js      short loc_180036879
0x180036850  mov     rcx, [rbp+57h+var_80]
0x180036854  lea     rdx, [rbp+57h+var_78]
0x180036858  mov     dword ptr [rbp+57h+var_78], r14d
0x18003685c  mov     rax, [rcx]
0x18003685f  mov     rax, [rax+18h]
0x180036863  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036868  test    eax, eax
0x18003686a  js      short loc_180036879
0x18003686c  mov     esi, r14d
0x18003686f  cmp     dword ptr [rbp+57h+var_78], r14d
0x180036873  ja      loc_180036D8A
0x180036879  mov     rcx, [rbp+57h+var_80]
0x18003687d  test    rcx, rcx
0x180036880  jz      short loc_180036892
0x180036882  mov     [rbp+57h+var_80], r14
0x180036886  mov     rdx, [rcx]
0x180036889  mov     rax, [rdx+10h]
0x18003688d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036892  mov     al, [rbp+57h+var_90]
0x180036895  mov     rcx, [rbp+57h+var_38]
0x180036899  xor     rcx, rsp; StackCookie
0x18003689c  call    __security_check_cookie
0x1800368a1  mov     rbx, [rsp+0C0h+arg_10]
0x1800368a9  add     rsp, 90h
0x1800368b0  pop     r15
0x1800368b2  pop     r14
0x1800368b4  pop     r13
0x1800368b6  pop     r12
0x1800368b8  pop     rdi
0x1800368b9  pop     rsi
0x1800368ba  pop     rbp
0x1800368bb  retn
0x1800368bd  mov     ecx, 1000h
0x1800368c2  cmp     rax, rcx
0x1800368c5  cmova   rax, rcx
0x1800368c9  cmp     rsi, rax
0x1800368cc  ja      short loc_1800368D8
0x1800368ce  cmp     rax, r8
0x1800368d1  mov     rsi, rax
0x1800368d4  cmova   rsi, r8
0x1800368d8  mov     eax, 8
0x1800368dd  mov     qword ptr [rbp+57h+rcSrc2.left], rbx
0x1800368e1  mul     rsi
0x1800368e4  mov     rbx, rax
0x1800368e7  test    rdx, rdx
0x1800368ea  jnz     loc_18003672B
0x1800368f0  mov     rcx, [rdi+30h]; pv
0x1800368f4  mov     rdx, rax; cb
0x1800368f7  call    cs:__imp_CoTaskMemRealloc
0x1800368fe  nop     dword ptr [rax+rax+00h]
0x180036903  mov     r14, rax
0x180036906  test    rax, rax
0x180036909  jz      loc_180036E1F
0x18003690f  mov     rcx, rax; void *
0x180036912  call    ?_CoTaskMemSize@CTCoAllocPolicy@@CA_KPEAX@Z; CTCoAllocPolicy::_CoTaskMemSize(void *)
0x180036917  cmp     rax, rbx
0x18003691a  ja      loc_180036E5E
0x180036920  xor     ebx, ebx
0x180036922  test    ebx, ebx
0x180036924  js      loc_180036730
0x18003692a  mov     [rdi+48h], rsi
0x18003692e  mov     [rdi+30h], r14
0x180036932  mov     r15, [r12+68h]
0x180036937  mov     rax, [r12+70h]
0x18003693c  lea     r12, [r15+rax*8]
0x180036940  cmp     r15, r12
0x180036943  jz      loc_180036A88
0x180036949  mov     rcx, [rdi+48h]
0x18003694d  mov     rsi, [rdi+38h]
0x180036951  cmp     rsi, rcx
0x180036954  jnz     loc_180036A41
0x18003695a  inc     rsi
0x18003695d  mov     r9d, 0FFFFFFFEh
0x180036963  mov     ebx, 8007007Ah
0x180036968  cmp     rsi, r9
0x18003696b  ja      short loc_1800369C6
0x18003696d  cmp     rsi, rcx
0x180036970  jbe     loc_180036A41
0x180036976  mov     eax, 2
0x18003697b  mov     qword ptr [rbp+57h+rcSrc2.left], 0
0x180036983  mul     rcx
0x180036986  mov     r8, rax
0x180036989  test    rdx, rdx
0x18003698c  jnz     short loc_1800369C1
0x18003698e  sub     rax, rcx
0x180036991  cmp     rax, 1000h
0x180036997  jbe     short loc_1800369A0
0x180036999  lea     r8, [rcx+1000h]
0x1800369a0  cmp     rsi, r8
0x1800369a3  jbe     loc_180036A79
0x1800369a9  mov     eax, 8
0x1800369ae  mov     qword ptr [rbp+57h+rcSrc2.left], 0
0x1800369b6  mul     rsi
0x1800369b9  mov     rbx, rax
0x1800369bc  test    rdx, rdx
0x1800369bf  jz      short loc_180036A03
0x1800369c1  mov     ebx, 80070216h
0x1800369c6  mov     rcx, [rbp+5Fh]; this
0x1800369ca  lea     r8, aShellLibGitreg; "shell\\lib\\gitreglist.cpp"
0x1800369d1  mov     r9d, ebx; char *
0x1800369d4  mov     edx, 63h ; 'c'; void *
0x1800369d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800369de  mov     r12, [rbp+57h+var_68]
0x1800369e2  mov     r15, [rbp+57h+var_78]
0x1800369e6  mov     rax, [rdi]
0x1800369e9  mov     rcx, rdi
0x1800369ec  mov     rax, [rax+10h]
0x1800369f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800369f5  lea     rcx, [rbp+57h+var_88]
0x1800369f9  call    ??1?$MakeAllocator@V?$SimpleClassFactory@VCAccessibilityDock@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::SimpleClassFactory<CAccessibilityDock,0>>::~MakeAllocator<Microsoft::WRL::SimpleClassFactory<CAccessibilityDock,0>>(void)
  ... truncated ...
```
