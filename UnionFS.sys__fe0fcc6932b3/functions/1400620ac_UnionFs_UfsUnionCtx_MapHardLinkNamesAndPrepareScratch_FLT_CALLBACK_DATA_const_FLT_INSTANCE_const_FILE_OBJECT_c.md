# UnionFs::UfsUnionCtx::MapHardLinkNamesAndPrepareScratch(_FLT_CALLBACK_DATA const &,_FLT_INSTANCE const &,_FILE_OBJECT const &,utl::vector<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>,utl::allocator<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>> const &,utl::vector<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>,utl::allocator<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>> &,UnionFs::StackEventTracer &)

- ea: `0x1400620ac`
- end: `0x140062a5b`
- name: `?MapHardLinkNamesAndPrepareScratch@UfsUnionCtx@UnionFs@@QEBAJAEBU_FLT_CALLBACK_DATA@@AEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@AEBV?$vector@V?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@V?$allocator@V?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@@2@@utl@@AEAV67@AEAVStackEventTracer@2@@Z`
- size: `2479`
- prototype: `__int64 __fastcall(UnionFs::UfsUnionCtx *, struct _FLT_CALLBACK_DATA *, struct _FLT_INSTANCE *, __int64, __int64, __int64 *, UnionFs::StackEventTracer *)`
- caller_count: `1`
- callee_count: `22`
- tags: `reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14006b78c`

## callees

- `0x1400015c4`
- `0x14000f81c`
- `0x14001f4c8`
- `0x140027218`
- `0x140043a64`
- `0x140056974`
- `0x140056bd0`
- `0x140056c44`
- `0x140056c7c`
- `0x140060494`
- `0x140060764`
- `0x1400611a4`
- `0x1400620ac`
- `0x14006e114`
- `0x1400779fc`
- `0x140079d44`
- `0x140079f68`
- `0x14007a02c`
- `0x14007a0c0`
- `0x14007b2b0`
- `0x14007baf0`
- `0x14007bf40`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14006244a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140062497`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006244a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140062497`
- `ntoskrnl!PsGetHostSilo` at `0x14006226e`
- `ntoskrnl!PsGetHostSilo` at `0x14006226e`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140062593`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140062593`
- `FLTMGR!FltReleaseContext` at `0x14006273f`
- `FLTMGR!FltReleaseContext` at `0x14006287c`
- `FLTMGR!FltReleaseContext` at `0x14006273f`
- `FLTMGR!FltReleaseContext` at `0x14006287c`

## string_xrefs

- `0x14006291c`: `PUSH: Getting relative path`
- `0x140062999`: `ORIGIN: Setting EA on hard link`
- `0x1400621a2`: `PUSH: Converting layer paths to scratch paths`
- `0x1400626b4`: `UnionFs::UfsUnionCtx::EnsureParentPathInScratch`
- `0x1400626a3`: `PUSH: EnsureParentPathinScratch`
- `0x1400621b3`: `UnionFs::UfsUnionCtx::MapHardLinkNamesAndPrepareScratch`
- `0x1400622da`: `UnionFs::UfsUnionCtx::MapHardLinkNamesAndPrepareScratch`
- `0x1400627c5`: `UnionFs::UfsUnionCtx::MapHardLinkNamesAndPrepareScratch`
- `0x140062829`: `UnionFs::UfsUnionCtx::MapHardLinkNamesAndPrepareScratch`
- `0x14006285b`: `UnionFs::UfsUnionCtx::MapHardLinkNamesAndPrepareScratch`
- `0x14006292d`: `UnionFs::UfsUnionCtx::MapHardLinkNamesAndPrepareScratch`
- `0x14006298f`: `UnionFs::UfsUnionCtx::MapHardLinkNamesAndPrepareScratch`
- `0x1400627b4`: `PUSH: Find and stat link name`
- `0x1400628e2`: `PathPrefix is supposed to start with \Device`
- `0x1400628ab`: `UnionFs::Utils::GetRemainingPath`
- `0x140062905`: `UnionFs::Utils::GetRemainingPath`
- `0x1400628ee`: `ORIGIN: PathPrefix doesn't start with \Device`
- `0x1400628cf`: `ORIGIN: Could not find PathPrefix in full path`
- `0x14006253f`: `PathPrefix goes past FullPathName.Path?`
- `0x140062896`: `ORIGIN: Allocating remainingPath`

## pseudocode

```c
__int64 __fastcall UnionFs::UfsUnionCtx::MapHardLinkNamesAndPrepareScratch(
        UnionFs::UfsUnionCtx *a1,
        struct _FLT_CALLBACK_DATA *a2,
        struct _FLT_INSTANCE *a3,
        __int64 a4,
        __int64 a5,
        __int64 *a6,
        UnionFs::StackEventTracer *a7)
{
  __int64 *v7; // r12
  unsigned __int64 *v9; // rdx
  const char **v10; // rax
  volatile signed __int32 *v11; // rbx
  const char *v12; // r15
  int v13; // eax
  unsigned int v14; // r13d
  unsigned int v15; // r14d
  __int64 v17; // r8
  __int64 v18; // r9
  utl::_RefCountBase *v19; // rdx
  __int64 v20; // rax
  struct _UNICODE_STRING *v21; // rdi
  volatile signed __int32 *v22; // r14
  __int64 HostSilo; // rax
  int v24; // eax
  struct _UNICODE_STRING *v25; // rdx
  int v26; // r15d
  UnionFs::UfsUnionCtx *v27; // r15
  FsFltWil::Details *v28; // rcx
  unsigned __int64 v29; // rdi
  bool v30; // di
  __int64 v31; // r15
  FsFltWil::Details *v32; // rcx
  __int64 v33; // rdi
  __int64 v34; // rdi
  __int64 v35; // rax
  __int64 v36; // r12
  __int64 v37; // rdi
  int v38; // r9d
  struct _UNICODE_STRING *v39; // r12
  __m128i v40; // xmm6
  const struct _UNICODE_STRING *v41; // r8
  unsigned __int8 v42; // r9
  USHORT *p_Length; // r15
  __int64 v44; // rcx
  USHORT v45; // r15
  USHORT Length; // di
  USHORT v47; // r15
  struct _UNICODE_STRING v48; // xmm1
  struct _UNICODE_STRING *v49; // rdx
  struct _FLT_CALLBACK_DATA *v50; // rdi
  int v51; // edx
  const struct UnionFs::UfsStreamHandleCtx *v52; // r12
  unsigned __int16 Buffer; // r8
  unsigned __int16 v54; // r8
  bool v55; // r11
  struct _UNICODE_STRING *v56; // rdx
  struct _UNICODE_STRING *v57; // rdx
  struct _UNICODE_STRING *v58; // rdx
  struct _UNICODE_STRING *v59; // rdx
  unsigned __int64 v60; // rcx
  struct _UNICODE_STRING *v61; // rdx
  const struct UnionFs::UfsStreamHandleCtx *v62; // rcx
  struct _UNICODE_STRING *v63; // rdx
  const char *v64; // rax
  __int64 v65; // r8
  struct _UNICODE_STRING *v66; // rdx
  int v67; // r8d
  int v68; // r9d
  struct UnionFs::UfsPathName *v69; // [rsp+30h] [rbp-D8h]
  struct UnionFs::UfsPathName *v70; // [rsp+30h] [rbp-D8h]
  struct UnionFs::UfsPathName *v71; // [rsp+30h] [rbp-D8h]
  struct UnionFs::UfsPathName *v72; // [rsp+30h] [rbp-D8h]
  __int64 v73; // [rsp+68h] [rbp-A0h] BYREF
  FsFltWil::Details *v74; // [rsp+70h] [rbp-98h] BYREF
  struct _UNICODE_STRING *Context; // [rsp+78h] [rbp-90h] BYREF
  struct _UNICODE_STRING Context_8; // [rsp+80h] [rbp-88h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+98h] [rbp-70h] BYREF
  struct _UNICODE_STRING v78; // [rsp+A8h] [rbp-60h] BYREF
  const char *v79; // [rsp+B8h] [rbp-50h] BYREF
  __m128i si128; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v81; // [rsp+D0h] [rbp-38h]
  struct _UNICODE_STRING DestinationString; // [rsp+D8h] [rbp-30h] BYREF
  FsFltWil::Details *v83; // [rsp+E8h] [rbp-20h] BYREF
  struct _UNICODE_STRING *v84; // [rsp+F0h] [rbp-18h]
  __int64 v85; // [rsp+F8h] [rbp-10h]
  struct _FLT_INSTANCE *v86; // [rsp+100h] [rbp-8h]
  UnionFs::UfsUnionCtx *v87; // [rsp+108h] [rbp+0h]
  __int64 *v88; // [rsp+110h] [rbp+8h]
  UNICODE_STRING SourceString; // [rsp+118h] [rbp+10h] BYREF
  _QWORD *v90; // [rsp+128h] [rbp+20h]
  volatile signed __int32 *v91; // [rsp+130h] [rbp+28h]
  struct _FLT_CALLBACK_DATA *v92; // [rsp+138h] [rbp+30h]
  struct _UNICODE_STRING v93; // [rsp+140h] [rbp+38h] BYREF
  struct _UNICODE_STRING v94; // [rsp+158h] [rbp+50h] BYREF
  char v95; // [rsp+168h] [rbp+60h]
  struct _UNICODE_STRING v96[5]; // [rsp+198h] [rbp+90h] BYREF
  utl::_RefCountBase *v97[2]; // [rsp+1E8h] [rbp+E0h]
  __int64 v98; // [rsp+1F8h] [rbp+F0h]
  _BYTE v99[80]; // [rsp+208h] [rbp+100h] BYREF

  v7 = a6;
  v92 = a2;
  v87 = a1;
  v85 = a4;
  v86 = a3;
  v88 = a6;
  v90 = (_QWORD *)((char *)a1 + 72);
  FsFltWil::AcquirePushLockShared(&v74, (char *)a1 + 72);
  v10 = (const char **)*((_QWORD *)a1 + 6);
  v11 = (volatile signed __int32 *)v10[1];
  v12 = *v10;
  v79 = *v10;
  v91 = v11;
  if ( v11 )
    _InterlockedIncrement(v11 + 2);
  if ( v74 )
    FsFltWil::Details::ReleasePushLockShared(v74, v9);
  v84 = (struct _UNICODE_STRING *)*((_QWORD *)v12 + 2);
  v81 = -1;
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v13 = UnionFs::UfsUnionCtx::ConvertLayerPathsToScratchPaths(a1, a5, a6, a7, &si128);
  v14 = -1073741275;
  v15 = v13;
  if ( v13 == -1073741275 || v13 == -1073741811 )
  {
    UnionFs::StackEventTracer::LogError(a7);
    *(_DWORD *)a7 = 0;
    *((_WORD *)a7 + 274) = 0;
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC0ED0003LL,
      (int)a7,
      (struct UnionFs::StackEventTracer *)0x1C60020060FLL,
      (unsigned __int64)"UnionFs::UfsUnionCtx::MapHardLinkNamesAndPrepareScratch",
      "ORIGIN: Setting EA on hard link",
      (const char *)v69);
    if ( (unsigned int)dword_14009E178 > 2 )
    {
      *(_DWORD *)&Context_8.Length = v15;
      LOWORD(v73) = 1551;
      LODWORD(Context) = 454;
      v79 = "UnionFs::UfsUnionCtx::MapHardLinkNamesAndPrepareScratch";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        (unsigned int)&v79,
        (unsigned int)&word_1400992AE,
        v67,
        v68,
        (__int64)&v79,
        (__int64)&Context,
        (__int64)&v73,
        (__int64)&Context_8);
    }
    utl::vector<utl::shared_ptr<UnionFs::UfsTablePayload>,utl::allocator<utl::shared_ptr<UnionFs::UfsTablePayload>>>::~vector<utl::shared_ptr<UnionFs::UfsTablePayload>,utl::allocator<utl::shared_ptr<UnionFs::UfsTablePayload>>>(&si128);
    if ( v11 )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v11);
    return 3236757507LL;
  }
  if ( v13 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v13,
      (int)a7,
      (struct UnionFs::StackEventTracer *)0x5F800200612LL,
      (unsigned __int64)"UnionFs::UfsUnionCtx::MapHardLinkNamesAndPrepareScratch",
      "PUSH: Converting layer paths to scratch paths",
      (const char *)v69);
    utl::vector<utl::shared_ptr<UnionFs::UfsTablePayload>,utl::allocator<utl::shared_ptr<UnionFs::UfsTablePayload>>>::~vector<utl::shared_ptr<UnionFs::UfsTablePayload>,utl::allocator<utl::shared_ptr<UnionFs::UfsTablePayload>>>(&si128);
    if ( v11 )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v11);
    return v15;
  }
  v17 = *a6;
  v18 = 0;
  v19 = 0;
  v20 = a6[1] - *a6;
  LODWORD(v73) = 0;
  if ( !(v20 >> 3) )
  {
LABEL_68:
    utl::vector<utl::shared_ptr<UnionFs::UfsTablePayload>,utl::allocator<utl::shared_ptr<UnionFs::UfsTablePayload>>>::~vector<utl::shared_ptr<UnionFs::UfsTablePayload>,utl::allocator<utl::shared_ptr<UnionFs::UfsTablePayload>>>(&si128);
    if ( v11 )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v11);
    return 0;
  }
  while ( 1 )
  {
    v21 = *(struct _UNICODE_STRING **)(v17 + 8 * v18);
    *(_QWORD *)&Context_8.Length = 8 * v18;
    Context = v21;
    v22 = *(volatile signed __int32 **)(si128.m128i_i64[0] + 16LL * (unsigned int)v18 + 8);
    v74 = *(FsFltWil::Details **)(si128.m128i_i64[0] + 16LL * (unsigned int)v18);
    if ( v22 )
      _InterlockedIncrement(v22 + 2);
    if ( v19 )
      utl::_RefCountBase::_DecStrong(v19);
    memset(v99, 0, 0x48u);
    v78 = *v21;
    HostSilo = PsGetHostSilo();
    v70 = a7;
    v24 = UnionFs::Utils::StatItem(&v78, v86, HostSilo, 1, v99);
    v26 = v24;
    if ( v24 != -1073741766 && v24 != -1073741772 )
    {
      if ( v24 < 0 )
      {
        UnionFs::ProcessTraceStatusFromApi(
          (UnionFs *)(unsigned int)v24,
          (int)a7,
          (struct UnionFs::StackEventTracer *)0x39600200654LL,
          (unsigned __int64)"UnionFs::UfsUnionCtx::MapHardLinkNamesAndPrepareScratch",
          "API: Stating scratch",
          (const char *)a7);
        goto LABEL_73;
      }
LABEL_27:
      v31 = 0;
      v32 = (FsFltWil::Details *)(*v7 + *(_QWORD *)&Context_8.Length);
      v33 = v7[1] - (_QWORD)v32;
      v74 = v32;
      v34 = (v33 - 8) >> 3;
      if ( v34 )
      {
        do
        {
          v35 = *((_QWORD *)v32 + v31 + 1);
          *((_QWORD *)v32 + v31 + 1) = 0;
          v36 = *((_QWORD *)v32 + v31);
          *((_QWORD *)v32 + v31) = v35;
          if ( v36 )
          {
            if ( !*(_BYTE *)(v36 + 16) )
              *(_OWORD *)v36 = 0;
            FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)v36, v25);
            ExFreePoolWithTag((PVOID)v36, 0);
            v32 = v74;
          }
          ++v31;
        }
        while ( v31 != v34 );
        v11 = v91;
        v7 = v88;
      }
      v7[1] -= 8;
      v37 = *(_QWORD *)v7[1];
      if ( v37 )
      {
        if ( !*(_BYTE *)(v37 + 16) )
          *(_OWORD *)v37 = 0;
        FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)v37, v25);
        ExFreePoolWithTag((PVOID)v37, 0);
      }
      v38 = v73 - 1;
      goto LABEL_65;
    }
    FsFltWil::AcquirePushLockShared(&v83, v90);
    v27 = v87;
    v28 = v83;
    v83 = 0;
    v29 = (__int64)(*((_QWORD *)v87 + 7) - *((_QWORD *)v87 + 6)) >> 4;
    if ( v28 )
      FsFltWil::Details::ReleasePushLockShared(v28, (unsigned __int64 *)&v25->Length);
    if ( v29 > 1 )
    {
      memset(v96, 0, sizeof(v96));
      v70 = a7;
      *(_OWORD *)v97 = 0;
      v98 = 0;
      v78 = *v84;
      v93 = *Context;
      v26 = UnionFs::UfsUnionCtx::FindAndStatItemInLayers(v27, &v93, &v78, 0, v96);
      if ( v26 < 0 )
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)v26,
          (int)a7,
          (struct UnionFs::StackEventTracer *)0x3B60020064ALL,
          (unsigned __int64)"UnionFs::UfsUnionCtx::MapHardLinkNamesAndPrepareScratch",
          "PUSH: Find and stat link name",
          (const char *)a7);
        if ( v97[1] )
          utl::_RefCountBase::_DecStrong(v97[1]);
        goto LABEL_73;
      }
      v30 = v74 != v97[0];
      if ( v97[1] )
        utl::_RefCountBase::_DecStrong(v97[1]);
      if ( v30 )
        goto LABEL_27;
    }
    v39 = v84;
    UnicodeString = 0;
    Context_8 = *v84;
    v40 = (__m128i)Context_8;
    FsFltWil::Details::FreeUnicodeString(&UnicodeString, v25);
    UnicodeString = 0;
    if ( *(_WORD *)(_mm_srli_si128(v40, 8).m128i_u64[0] + 2) != 68 )
      break;
    p_Length = &Context->Length;
    LOBYTE(v41) = 1;
    v78 = *Context;
    if ( !UnionFs::Rtl::FindUnicodeSubstring((UnionFs::Rtl *)&v78, &Context_8, v41, v42) )
    {
      v64 = "ORIGIN: Could not find PathPrefix in full path";
      v65 = 0x3E9002105A6LL;
      goto LABEL_86;
    }
    v44 = p_Length[12];
    v45 = *p_Length;
    Length = Context_8.Length - 2;
    if ( Context_8.Length != v44 + 2 )
      Length = Context_8.Length;
    if ( Length < v45 )
    {
      v47 = v45 - Length;
      FsFltWil::MakeUniqueUnicodeString(&DestinationString, v47, 1279685446);
      if ( !DestinationString.Buffer )
      {
        v14 = -1073741670;
        UnionFs::ProcessTraceStatusOrigin(
          (UnionFs *)0xC000009ALL,
          (int)a7,
          (struct UnionFs::StackEventTracer *)0x3EB002105C8LL,
          (unsigned __int64)"UnionFs::Utils::GetRemainingPath",
          "ORIGIN: Allocating remainingPath",
          (const char *)v70);
        FsFltWil::Details::FreeUnicodeString(&DestinationString, v63);
        goto LABEL_87;
      }
      SourceString.Buffer = (PWSTR)((char *)v78.Buffer + Length);
      *(_DWORD *)(&SourceString.MaximumLength + 1) = 0;
      SourceString.Length = v47;
      SourceString.MaximumLength = v47;
      RtlCopyUnicodeString(&DestinationString, &SourceString);
      v48 = UnicodeString;
      UnicodeString = DestinationString;
      DestinationString = v48;
      FsFltWil::Details::FreeUnicodeString(&DestinationString, v49);
    }
    else if ( Length != v45 )
    {
      MicrosoftTelemetryAssertTriggeredMsgKM("PathPrefix goes past FullPathName.Path?");
    }
    v50 = v92;
    v51 = 0;
    *(_QWORD *)&Context_8.Length = 0;
    if ( (v92->Iopb->Parameters.Create.Options & 0x1000) != 0 )
      v51 = 4;
    v26 = UnionFs::UfsStreamHandleCtx::FltAllocAndInit(v79, v85, v39, &UnicodeString, v51);
    if ( v26 < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v26,
        (int)a7,
        (struct UnionFs::StackEventTracer *)0xCC00200679LL,
        (unsigned __int64)"UnionFs::UfsUnionCtx::MapHardLinkNamesAndPrepareScratch",
        "PUSH: Creating fake streamhandle context",
        (const char *)&Context_8);
      v62 = *(const struct UnionFs::UfsStreamHandleCtx **)&Context_8.Length;
      if ( *(_QWORD *)&Context_8.Length )
LABEL_81:
        FltReleaseContext(v62);
LABEL_82:
      FsFltWil::Details::FreeUnicodeString(&UnicodeString, v61);
LABEL_73:
      if ( v22 )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v22);
      utl::vector<utl::shared_ptr<UnionFs::UfsTablePayload>,utl::allocator<utl::shared_ptr<UnionFs::UfsTablePayload>>>::~vector<utl::shared_ptr<UnionFs::UfsTablePayload>,utl::allocator<utl::shared_ptr<UnionFs::UfsTablePayload>>>(&si128);
      if ( v11 )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v11);
      return (unsigned int)v26;
    }
    v52 = *(const struct UnionFs::UfsStreamHandleCtx **)&Context_8.Length;
    Buffer = (unsigned __int16)Context[1].Buffer;
    v78 = *Context;
    v93 = v78;
    UnionFs::UfsPathName::UfsPathName((UnionFs::UfsPathName *)v96, &v93, Buffer);
    UnionFs::UfsPathName::UfsPathName((UnionFs::UfsPathName *)&v94, &v78, v54);
    v26 = UnionFs::UfsUnionCtx::EnsureParentPathInScratch(
            v87,
            v50,
            v86,
            (const struct UnionFs::UfsPathName *)v96,
            0,
            (const struct UnionFs::UfsPathName *)&v94,
            v55,
            v52,
            v74,
            a7,
            0);
    if ( v26 >= 0 )
    {
      if ( !v95 )
        v94 = 0;
      FsFltWil::Details::FreeUnicodeString(&v94, v56);
      if ( !LOBYTE(v96[1].Length) )
        v96[0] = 0;
      v26 = 0;
    }
    else
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v26,
        (int)a7,
        (struct UnionFs::StackEventTracer *)0x271002004ACLL,
        (unsigned __int64)"UnionFs::UfsUnionCtx::EnsureParentPathInScratch",
        "PUSH: EnsureParentPathinScratch",
        (const char *)v71);
      if ( !v95 )
        v94 = 0;
      FsFltWil::Details::FreeUnicodeString(&v94, v57);
      if ( !LOBYTE(v96[1].Length) )
        v96[0] = 0;
    }
    FsFltWil::Details::FreeUnicodeString(v96, v58);
    if ( v26 < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v26,
        (int)a7,
        (struct UnionFs::StackEventTracer *)0x3DC00200688LL,
        (unsigned __int64)"UnionFs::UfsUnionCtx::MapHardLinkNamesAndPrepareScratch",
        "PUSH: Preparing for COW",
        (const char *)v71);
      if ( v52 )
      {
        v62 = v52;
        goto LABEL_81;
      }
      goto LABEL_82;
    }
    if ( v52 )
      FltReleaseContext(v52);
    FsFltWil::Details::FreeUnicodeString(&UnicodeString, v59);
    v38 = v73;
    v7 = v88;
LABEL_65:
    v17 = *v7;
    v18 = (unsigned int)(v38 + 1);
    v60 = (v7[1] - *v7) >> 3;
    v19 = (utl::_RefCountBase *)v22;
    LODWORD(v73) = v18;
    if ( (unsigned int)v18 >= v60 )
    {
      if ( v22 )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v22);
      goto LABEL_68;
    }
  }
  MicrosoftTelemetryAssertTriggeredMsgKM("PathPrefix is supposed to start with \\Device");
  v64 = "ORIGIN: PathPrefix doesn't start with \\Device";
  v65 = 0x3E20021059BLL;
  v14 = -1073741773;
LABEL_86:
  UnionFs::ProcessTraceStatusOrigin(
    (UnionFs *)v14,
    (int)a7,
    (struct UnionFs::StackEventTracer *)v65,
    (unsigned __int64)"UnionFs::Utils::GetRemainingPath",
    v64,
    (const char *)v70);
LABEL_87:
  UnionFs::ProcessTraceStatusPushLocation(
    (UnionFs *)v14,
    (int)a7,
    (struct UnionFs::StackEventTracer *)0x29E0020066ALL,
    (unsigned __int64)"UnionFs::UfsUnionCtx::MapHardLinkNamesAndPrepareScratch",
    "PUSH: Getting relative path",
    (const char *)v72);
  FsFltWil::Details::FreeUnicodeString(&UnicodeString, v66);
  if ( v22 )
    utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v22);
  utl::vector<utl::shared_ptr<UnionFs::UfsTablePayload>,utl::allocator<utl::shared_ptr<UnionFs::UfsTablePayload>>>::~vector<utl::shared_ptr<UnionFs::UfsTablePayload>,utl::allocator<utl::shared_ptr<UnionFs::UfsTablePayload>>>(&si128);
  if ( v11 )
    utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v11);
  return v14;
}

```

## disassembly

```asm
0x1400620ac  mov     rax, rsp
0x1400620af  push    rbp
0x1400620b0  push    rbx
0x1400620b1  push    rsi
0x1400620b2  push    rdi
0x1400620b3  push    r12
0x1400620b5  push    r13
0x1400620b7  push    r14
0x1400620b9  push    r15
0x1400620bb  lea     rbp, [rax-1B8h]
0x1400620c2  sub     rsp, 278h
0x1400620c9  movaps  xmmword ptr [rax-58h], xmm6
0x1400620cd  mov     rax, cs:__security_cookie
0x1400620d4  xor     rax, rsp
0x1400620d7  mov     [rbp+1B0h+var_60], rax
0x1400620de  mov     r12, [rbp+1B0h+arg_28]
0x1400620e5  lea     rax, [rcx+48h]
0x1400620e9  mov     rdi, [rbp+1B0h+arg_20]
0x1400620f0  mov     r14, rcx
0x1400620f3  mov     rsi, [rbp+1B0h+arg_30]
0x1400620fa  mov     [rbp+1B0h+var_180], rdx
0x1400620fe  mov     rdx, rax
0x140062101  mov     [rbp+1B0h+var_1B0], rcx
0x140062105  lea     rcx, [rsp+2B0h+var_248]
0x14006210a  mov     [rbp+1B0h+var_1C0], r9
0x14006210e  mov     [rbp+1B0h+var_1B8], r8
0x140062112  mov     [rbp+1B0h+var_1A8], r12
0x140062116  mov     [rbp+1B0h+var_190], rax
0x14006211a  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x14006211f  mov     rax, [r14+30h]
0x140062123  mov     rbx, [rax+8]
0x140062127  mov     r15, [rax]
0x14006212a  mov     [rbp+1B0h+var_200], r15
0x14006212e  mov     [rbp+1B0h+var_188], rbx
0x140062132  test    rbx, rbx
0x140062135  jz      short loc_14006213B
0x140062137  lock inc dword ptr [rbx+8]
0x14006213b  mov     rcx, [rsp+2B0h+var_248]; this
0x140062140  test    rcx, rcx
0x140062143  jz      short loc_14006214A
0x140062145  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x14006214a  mov     rax, [r15+10h]
0x14006214e  mov     r9, rsi
0x140062151  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x140062159  mov     r8, r12
0x14006215c  mov     [rbp+1B0h+var_1C8], rax
0x140062160  mov     rdx, rdi
0x140062163  lea     rax, [rbp+1B0h+var_1F8]
0x140062167  mov     [rbp+1B0h+var_1E8], 0FFFFFFFFFFFFFFFFh
0x14006216f  mov     rcx, r14
0x140062172  mov     [rsp+2B0h+var_290], rax
0x140062177  movdqu  [rbp+1B0h+var_1F8], xmm0
0x14006217c  call    ?ConvertLayerPathsToScratchPaths@UfsUnionCtx@UnionFs@@QEBAJAEBV?$vector@V?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@V?$allocator@V?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@@2@@utl@@AEAV34@AEAVStackEventTracer@2@PEAV?$vector@V?$shared_ptr@VUfsLayerCtx@UnionFs@@@utl@@V?$allocator@V?$shared_ptr@VUfsLayerCtx@UnionFs@@@utl@@@2@@4@@Z; UnionFs::UfsUnionCtx::ConvertLayerPathsToScratchPaths(utl::vector<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>,utl::allocator<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>> const &,utl::vector<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>,utl::allocator<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>> &,UnionFs::StackEventTracer &,utl::vector<utl::shared_ptr<UnionFs::UfsLayerCtx>,utl::allocator<utl::shared_ptr<UnionFs::UfsLayerCtx>>> *)
0x140062181  mov     r13d, 0C0000225h
0x140062187  mov     r14d, eax
0x14006218a  cmp     eax, r13d
0x14006218d  jz      loc_140062978
0x140062193  cmp     eax, 0C000000Dh
0x140062198  jz      loc_140062978
0x14006219e  test    eax, eax
0x1400621a0  jns     short loc_1400621E8
0x1400621a2  lea     rax, aPushConverting_1; "PUSH: Converting layer paths to scratch"...
0x1400621a9  mov     r8, 5F800200612h; struct UnionFs::StackEventTracer *
0x1400621b3  lea     r9, aUnionfsUfsunio_3; "UnionFs::UfsUnionCtx::MapHardLinkNamesA"...
0x1400621ba  mov     [rsp+2B0h+var_290], rax; char *
0x1400621bf  mov     rdx, rsi; int
0x1400621c2  mov     ecx, r14d; this
0x1400621c5  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400621ca  lea     rcx, [rbp+1B0h+var_1F8]
0x1400621ce  call    ??1?$vector@V?$shared_ptr@VUfsTablePayload@UnionFs@@@utl@@V?$allocator@V?$shared_ptr@VUfsTablePayload@UnionFs@@@utl@@@2@@utl@@QEAA@XZ; utl::vector<utl::shared_ptr<UnionFs::UfsTablePayload>,utl::allocator<utl::shared_ptr<UnionFs::UfsTablePayload>>>::~vector<utl::shared_ptr<UnionFs::UfsTablePayload>,utl::allocator<utl::shared_ptr<UnionFs::UfsTablePayload>>>(void)
0x1400621d3  test    rbx, rbx
0x1400621d6  jz      short loc_1400621E0
0x1400621d8  mov     rcx, rbx; this
0x1400621db  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1400621e0  mov     eax, r14d
0x1400621e3  jmp     loc_140062A2F
0x1400621e8  mov     r8, [r12]
0x1400621ec  xor     r9d, r9d
0x1400621ef  mov     rax, [r12+8]
0x1400621f4  xor     edx, edx
0x1400621f6  sub     rax, r8
0x1400621f9  mov     dword ptr [rsp+2B0h+var_250], r9d
0x1400621fe  sar     rax, 3
0x140062202  test    rax, rax
0x140062205  jz      loc_140062797
0x14006220b  lea     r15d, [rdx+1]
0x14006220f  lea     rcx, ds:0[r9*8]
0x140062217  mov     eax, r9d
0x14006221a  mov     rdi, [r8+rcx]
0x14006221e  add     rax, rax
0x140062221  mov     r8, qword ptr [rbp+1B0h+var_1F8]
0x140062225  mov     [rsp+2B0h+Context+8], rcx
0x14006222a  mov     [rsp+2B0h+Context], rdi
0x14006222f  mov     r14, [r8+rax*8+8]
0x140062234  mov     rcx, [r8+rax*8]
0x140062238  mov     [rsp+2B0h+var_248], rcx
0x14006223d  test    r14, r14
0x140062240  jz      short loc_140062247
0x140062242  lock inc dword ptr [r14+8]
0x140062247  test    rdx, rdx
0x14006224a  jz      short loc_140062254
0x14006224c  mov     rcx, rdx; this
0x14006224f  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140062254  xor     edx, edx; Val
0x140062256  lea     rcx, [rbp+1B0h+var_B0]; void *
0x14006225d  lea     r8d, [rdx+48h]; Size
0x140062261  call    memset
0x140062266  movups  xmm0, xmmword ptr [rdi]
0x140062269  movdqu  xmmword ptr [rbp+1B0h+var_210.Length], xmm0
0x14006226e  call    cs:__imp_PsGetHostSilo
0x140062275  nop     dword ptr [rax+rax+00h]
0x14006227a  mov     rdx, [rbp+1B0h+var_1B8]
0x14006227e  lea     rcx, [rbp+1B0h+var_B0]
0x140062285  mov     [rsp+2B0h+var_278], 0
0x14006228e  mov     r9d, r15d
0x140062291  mov     qword ptr [rsp+2B0h+var_280], 0
0x14006229a  mov     r8, rax
0x14006229d  mov     [rsp+2B0h+var_288], rsi; char *
0x1400622a2  mov     [rsp+2B0h+var_290], rcx
0x1400622a7  lea     rcx, [rbp+1B0h+var_210]
0x1400622ab  call    ?StatItem@Utils@UnionFs@@YAJAEBU_UNICODE_STRING@@AEBU_FLT_INSTANCE@@AEBU_EJOB@@W4StatItemFlags@12@PEAU_FILE_STAT_INFORMATION@@AEAVStackEventTracer@2@QEAU_TXN_PARAMETER_BLOCK@@PEAU_FLT_CALLBACK_DATA@@@Z; UnionFs::Utils::StatItem(_UNICODE_STRING const &,_FLT_INSTANCE const &,_EJOB const &,UnionFs::Utils::StatItemFlags,_FILE_STAT_INFORMATION *,UnionFs::StackEventTracer &,_TXN_PARAMETER_BLOCK * const,_FLT_CALLBACK_DATA *)
0x1400622b0  mov     r15d, eax
0x1400622b3  cmp     eax, 0C000003Ah
0x1400622b8  jz      short loc_1400622F6
0x1400622ba  cmp     eax, 0C0000034h
0x1400622bf  jz      short loc_1400622F6
0x1400622c1  test    eax, eax
0x1400622c3  jns     loc_1400623EC
0x1400622c9  lea     rax, aApiStatingScra; "API: Stating scratch"
0x1400622d0  mov     r8, 39600200654h; struct UnionFs::StackEventTracer *
0x1400622da  lea     r9, aUnionfsUfsunio_3; "UnionFs::UfsUnionCtx::MapHardLinkNamesA"...
0x1400622e1  mov     [rsp+2B0h+var_290], rax; char *
0x1400622e6  mov     rdx, rsi; int
0x1400622e9  mov     ecx, r15d; this
0x1400622ec  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400622f1  jmp     loc_1400627ED
0x1400622f6  mov     rdx, [rbp+1B0h+var_190]
0x1400622fa  lea     rcx, [rbp+1B0h+var_1D0]
0x1400622fe  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x140062303  mov     r15, [rbp+1B0h+var_1B0]
0x140062307  mov     rcx, [rbp+1B0h+var_1D0]; this
0x14006230b  mov     [rbp+1B0h+var_1D0], 0
0x140062313  mov     rdi, [r15+38h]
0x140062317  sub     rdi, [r15+30h]
0x14006231b  sar     rdi, 4
0x14006231f  test    rcx, rcx
0x140062322  jz      short loc_140062329
0x140062324  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x140062329  cmp     rdi, 1
0x14006232d  jbe     loc_1400624B0
0x140062333  xor     eax, eax
0x140062335  lea     rcx, [rbp+1B0h+var_120.Buffer]; void *
0x14006233c  xor     edx, edx; Val
0x14006233e  mov     [rbp+1B0h+var_120.Length], ax
0x140062345  mov     dword ptr [rbp+1B0h+var_120.MaximumLength], eax
0x14006234b  mov     word ptr [rbp+1B0h+var_120+6], ax
0x140062352  lea     r8d, [rax+48h]; Size
0x140062356  call    memset
0x14006235b  mov     rax, [rbp+1B0h+var_1C8]
0x14006235f  lea     r8, [rbp+1B0h+var_210]
0x140062363  xorps   xmm0, xmm0
0x140062366  mov     [rsp+2B0h+var_288], rsi; char *
0x14006236b  movdqa  xmmword ptr [rbp+1B0h+var_D0], xmm0
0x140062373  lea     rdx, [rbp+1B0h+var_178]
0x140062377  xor     r9d, r9d
0x14006237a  mov     [rbp+1B0h+var_C0], 0
0x140062385  movups  xmm1, xmmword ptr [rax]
0x140062388  mov     rax, [rsp+2B0h+Context]
0x14006238d  mov     rcx, r15
0x140062390  movdqu  xmmword ptr [rbp+1B0h+var_210.Length], xmm1
0x140062395  movups  xmm0, xmmword ptr [rax]
0x140062398  lea     rax, [rbp+1B0h+var_120]
0x14006239f  mov     [rsp+2B0h+var_290], rax
0x1400623a4  movdqu  xmmword ptr [rbp+1B0h+var_178.Length], xmm0
0x1400623a9  call    ?FindAndStatItemInLayers@UfsUnionCtx@UnionFs@@QEBAJAEBU_UNICODE_STRING@@0W4StatItemFlags@Utils@2@AEAUFindAndStatResults@2@AEAVStackEventTracer@2@@Z; UnionFs::UfsUnionCtx::FindAndStatItemInLayers(_UNICODE_STRING const &,_UNICODE_STRING const &,UnionFs::Utils::StatItemFlags,UnionFs::FindAndStatResults &,UnionFs::StackEventTracer &)
0x1400623ae  mov     r15d, eax
0x1400623b1  test    eax, eax
0x1400623b3  js      loc_1400627B4
0x1400623b9  mov     rcx, [rbp+1B0h+var_D0+8]; this
0x1400623c0  xor     al, al
0x1400623c2  movzx   edi, al
0x1400623c5  mov     rax, [rsp+2B0h+var_248]
0x1400623ca  cmp     rax, [rbp+1B0h+var_D0]
0x1400623d1  mov     eax, 1
0x1400623d6  cmovnz  edi, eax
0x1400623d9  test    rcx, rcx
0x1400623dc  jz      short loc_1400623E3
0x1400623de  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1400623e3  test    dil, dil
0x1400623e6  jz      loc_1400624B0
0x1400623ec  mov     rcx, [rsp+2B0h+Context+8]
0x1400623f1  xor     r15d, r15d
0x1400623f4  add     rcx, [r12]
0x1400623f8  mov     rdi, [r12+8]
0x1400623fd  sub     rdi, rcx
0x140062400  mov     [rsp+2B0h+var_248], rcx
0x140062405  sub     rdi, 8
0x140062409  sar     rdi, 3
0x14006240d  test    rdi, rdi
0x140062410  jz      short loc_14006246B
0x140062412  mov     rax, [rcx+r15*8+8]
0x140062417  mov     qword ptr [rcx+r15*8+8], 0
0x140062420  mov     r12, [rcx+r15*8]
0x140062424  mov     [rcx+r15*8], rax
0x140062428  test    r12, r12
0x14006242b  jz      short loc_14006245B
0x14006242d  cmp     byte ptr [r12+10h], 0
0x140062433  jnz     short loc_14006243D
0x140062435  xorps   xmm0, xmm0
0x140062438  movups  xmmword ptr [r12], xmm0
0x14006243d  mov     rcx, r12; UnicodeString
0x140062440  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140062445  xor     edx, edx; Tag
0x140062447  mov     rcx, r12; P
0x14006244a  call    cs:__imp_ExFreePoolWithTag
0x140062451  nop     dword ptr [rax+rax+00h]
0x140062456  mov     rcx, [rsp+2B0h+var_248]
0x14006245b  inc     r15
0x14006245e  cmp     r15, rdi
0x140062461  jnz     short loc_140062412
0x140062463  mov     rbx, [rbp+1B0h+var_188]
0x140062467  mov     r12, [rbp+1B0h+var_1A8]
0x14006246b  add     qword ptr [r12+8], 0FFFFFFFFFFFFFFF8h
0x140062471  mov     rax, [r12+8]
0x140062476  mov     rdi, [rax]
0x140062479  test    rdi, rdi
0x14006247c  jz      short loc_1400624A3
0x14006247e  cmp     byte ptr [rdi+10h], 0
0x140062482  jnz     short loc_14006248A
0x140062484  xorps   xmm0, xmm0
0x140062487  movups  xmmword ptr [rdi], xmm0
0x14006248a  mov     rcx, rdi; UnicodeString
0x14006248d  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140062492  xor     edx, edx; Tag
0x140062494  mov     rcx, rdi; P
0x140062497  call    cs:__imp_ExFreePoolWithTag
0x14006249e  nop     dword ptr [rax+rax+00h]
0x1400624a3  mov     r9d, dword ptr [rsp+2B0h+var_250]
0x1400624a8  dec     r9d
0x1400624ab  jmp     loc_14006275D
0x1400624b0  mov     r12, [rbp+1B0h+var_1C8]
0x1400624b4  lea     rcx, [rbp+1B0h+UnicodeString]; UnicodeString
0x1400624b8  xorps   xmm0, xmm0
0x1400624bb  movups  xmmword ptr [rbp+1B0h+UnicodeString.Length], xmm0
0x1400624bf  movups  xmm6, xmmword ptr [r12]
0x1400624c4  movups  xmmword ptr [rsp+2B0h+Context+8], xmm6
0x1400624c9  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x1400624ce  psrldq  xmm6, 8
0x1400624d3  xorps   xmm0, xmm0
0x1400624d6  movq    rax, xmm6
0x1400624db  movups  xmmword ptr [rbp+1B0h+UnicodeString.Length], xmm0
0x1400624df  cmp     word ptr [rax+2], 44h ; 'D'
0x1400624e4  jnz     loc_1400628E2
0x1400624ea  mov     r15, [rsp+2B0h+Context]
0x1400624ef  lea     rdx, [rsp+2B0h+Context+8]; struct _UNICODE_STRING *
0x1400624f4  mov     r8b, 1; struct _UNICODE_STRING *
0x1400624f7  lea     rcx, [rbp+1B0h+var_210]; this
0x1400624fb  movups  xmm0, xmmword ptr [r15]
0x1400624ff  movdqu  xmmword ptr [rbp+1B0h+var_210.Length], xmm0
0x140062504  call    ?FindUnicodeSubstring@Rtl@UnionFs@@YAPEAGPEBU_UNICODE_STRING@@0E@Z; UnionFs::Rtl::FindUnicodeSubstring(_UNICODE_STRING const *,_UNICODE_STRING const *,uchar)
0x140062509  test    rax, rax
0x14006250c  jz      loc_1400628CF
0x140062512  movzx   edx, word ptr [rsp+2B0h+Context+8]
0x140062517  mov     r8d, 2
0x14006251d  movzx   ecx, word ptr [r15+18h]
0x140062522  movzx   edi, dx
0x140062525  movzx   r15d, word ptr [r15]
0x140062529  sub     di, r8w
0x14006252d  add     rcx, r8
0x140062530  cmp     rdx, rcx
0x140062533  cmovnz  di, dx
0x140062537  cmp     di, r15w
0x14006253b  jb      short loc_14006254D
0x14006253d  jz      short loc_1400625BA
0x14006253f  lea     rcx, aPathprefixGoes; "PathPrefix goes past FullPathName.Path?"
0x140062546  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x14006254b  jmp     short loc_1400625BA
0x14006254d  sub     r15w, di
0x140062551  lea     rcx, [rbp+1B0h+DestinationString]
0x140062555  movzx   edx, r15w
0x140062559  mov     r8d, 4C467346h
0x14006255f  call    ?MakeUniqueUnicodeString@FsFltWil@@YA?AV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@GKW4FSFLT_ALLOC_TYPE@@@Z; FsFltWil::MakeUniqueUnicodeString(ushort,ulong,FSFLT_ALLOC_TYPE)
0x140062564  cmp     [rbp+1B0h+DestinationString.Buffer], 0
0x140062569  jz      loc_140062896
0x14006256f  movzx   eax, di
0x140062572  lea     rdx, [rbp+1B0h+SourceString]; SourceString
0x140062576  add     rax, [rbp+1B0h+var_210.Buffer]
0x14006257a  lea     rcx, [rbp+1B0h+DestinationString]; DestinationString
0x14006257e  mov     [rbp+1B0h+SourceString.Buffer], rax
0x140062582  mov     dword ptr [rbp+1B0h+SourceString+4], 0
0x140062589  mov     [rbp+1B0h+SourceString.Length], r15w
0x14006258e  mov     [rbp+1B0h+SourceString.MaximumLength], r15w
0x140062593  call    cs:__imp_RtlCopyUnicodeString
0x14006259a  nop     dword ptr [rax+rax+00h]
0x14006259f  movaps  xmm1, xmmword ptr [rbp+1B0h+UnicodeString.Length]
0x1400625a3  lea     rcx, [rbp+1B0h+DestinationString]; UnicodeString
0x1400625a7  movaps  xmm0, xmmword ptr [rbp+1B0h+DestinationString.Length]
0x1400625ab  movdqa  xmmword ptr [rbp+1B0h+UnicodeString.Length], xmm0
0x1400625b0  movdqa  xmmword ptr [rbp+1B0h+DestinationString.Length], xmm1
0x1400625b5  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
  ... truncated ...
```
