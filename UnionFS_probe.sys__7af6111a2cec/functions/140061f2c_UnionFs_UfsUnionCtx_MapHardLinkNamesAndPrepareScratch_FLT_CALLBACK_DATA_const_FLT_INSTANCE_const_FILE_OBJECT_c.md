# UnionFs::UfsUnionCtx::MapHardLinkNamesAndPrepareScratch(_FLT_CALLBACK_DATA const &,_FLT_INSTANCE const &,_FILE_OBJECT const &,utl::vector<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>,utl::allocator<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>> const &,utl::vector<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>,utl::allocator<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>> &,UnionFs::StackEventTracer &)

- ea: `0x140061f2c`
- end: `0x1400628db`
- name: `?MapHardLinkNamesAndPrepareScratch@UfsUnionCtx@UnionFs@@QEBAJAEBU_FLT_CALLBACK_DATA@@AEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@AEBV?$vector@V?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@V?$allocator@V?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@@2@@utl@@AEAV67@AEAVStackEventTracer@2@@Z`
- size: `2479`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, UnionFs::StackEventTracer *)`
- caller_count: `1`
- callee_count: `22`
- tags: `reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14006b59c`

## callees

- `0x1400015c4`
- `0x14000f7fc`
- `0x14001f428`
- `0x140027178`
- `0x1400438e4`
- `0x1400567f4`
- `0x140056a50`
- `0x140056ac4`
- `0x140056afc`
- `0x140060314`
- `0x1400605e4`
- `0x140061024`
- `0x140061f2c`
- `0x14006df24`
- `0x140077710`
- `0x140079a24`
- `0x140079c48`
- `0x140079d0c`
- `0x140079da0`
- `0x14007af90`
- `0x14007b7d0`
- `0x14007bc00`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400622ca`
- `ntoskrnl!ExFreePoolWithTag` at `0x140062317`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400622ca`
- `ntoskrnl!ExFreePoolWithTag` at `0x140062317`
- `ntoskrnl!PsGetHostSilo` at `0x1400620ee`
- `ntoskrnl!PsGetHostSilo` at `0x1400620ee`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140062413`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140062413`
- `FLTMGR!FltReleaseContext` at `0x1400625bf`
- `FLTMGR!FltReleaseContext` at `0x1400626fc`
- `FLTMGR!FltReleaseContext` at `0x1400625bf`
- `FLTMGR!FltReleaseContext` at `0x1400626fc`

## string_xrefs

- `0x14006279c`: `PUSH: Getting relative path`
- `0x140062819`: `ORIGIN: Setting EA on hard link`
- `0x140062022`: `PUSH: Converting layer paths to scratch paths`
- `0x140062534`: `UnionFs::UfsUnionCtx::EnsureParentPathInScratch`
- `0x140062523`: `PUSH: EnsureParentPathinScratch`
- `0x140062634`: `PUSH: Find and stat link name`
- `0x140062033`: `UnionFs::UfsUnionCtx::MapHardLinkNamesAndPrepareScratch`
- `0x14006215a`: `UnionFs::UfsUnionCtx::MapHardLinkNamesAndPrepareScratch`
- `0x140062645`: `UnionFs::UfsUnionCtx::MapHardLinkNamesAndPrepareScratch`
- `0x1400626a9`: `UnionFs::UfsUnionCtx::MapHardLinkNamesAndPrepareScratch`
- `0x1400626db`: `UnionFs::UfsUnionCtx::MapHardLinkNamesAndPrepareScratch`
- `0x1400627ad`: `UnionFs::UfsUnionCtx::MapHardLinkNamesAndPrepareScratch`
- `0x14006280f`: `UnionFs::UfsUnionCtx::MapHardLinkNamesAndPrepareScratch`
- `0x14006276e`: `ORIGIN: PathPrefix doesn't start with \Device`
- `0x140062762`: `PathPrefix is supposed to start with \Device`
- `0x14006274f`: `ORIGIN: Could not find PathPrefix in full path`
- `0x14006272b`: `UnionFs::Utils::GetRemainingPath`
- `0x140062785`: `UnionFs::Utils::GetRemainingPath`
- `0x140062716`: `ORIGIN: Allocating remainingPath`
- `0x1400623bf`: `PathPrefix goes past FullPathName.Path?`

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
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 HostSilo; // rax
  int v26; // eax
  struct _UNICODE_STRING *v27; // rdx
  int v28; // r15d
  UnionFs::UfsUnionCtx *v29; // r15
  FsFltWil::Details *v30; // rcx
  unsigned __int64 v31; // rdi
  bool v32; // di
  __int64 v33; // r15
  FsFltWil::Details *v34; // rcx
  __int64 v35; // rdi
  __int64 v36; // rdi
  __int64 v37; // rax
  __int64 v38; // r12
  __int64 v39; // rdi
  int v40; // r9d
  struct _UNICODE_STRING *v41; // r12
  __m128i v42; // xmm6
  const struct _UNICODE_STRING *v43; // r8
  unsigned __int8 v44; // r9
  USHORT *p_Length; // r15
  __int64 v46; // rcx
  USHORT v47; // r15
  USHORT Length; // di
  USHORT v49; // r15
  struct _UNICODE_STRING v50; // xmm1
  struct _UNICODE_STRING *v51; // rdx
  struct _FLT_CALLBACK_DATA *v52; // rdi
  int v53; // edx
  const struct UnionFs::UfsStreamHandleCtx *v54; // r12
  unsigned __int16 Buffer; // r8
  unsigned __int16 v56; // r8
  bool v57; // r11
  struct _UNICODE_STRING *v58; // rdx
  struct _UNICODE_STRING *v59; // rdx
  struct _UNICODE_STRING *v60; // rdx
  struct _UNICODE_STRING *v61; // rdx
  unsigned __int64 v62; // rcx
  struct _UNICODE_STRING *v63; // rdx
  const struct UnionFs::UfsStreamHandleCtx *v64; // rcx
  struct _UNICODE_STRING *v65; // rdx
  const char *v66; // rax
  __int64 v67; // r8
  struct _UNICODE_STRING *v68; // rdx
  int v69; // r8d
  int v70; // r9d
  struct UnionFs::UfsPathName *v71; // [rsp+30h] [rbp-D8h]
  struct UnionFs::UfsPathName *v72; // [rsp+30h] [rbp-D8h]
  struct UnionFs::UfsPathName *v73; // [rsp+30h] [rbp-D8h]
  struct UnionFs::UfsPathName *v74; // [rsp+30h] [rbp-D8h]
  __int64 v75; // [rsp+68h] [rbp-A0h] BYREF
  FsFltWil::Details *v76; // [rsp+70h] [rbp-98h] BYREF
  struct _UNICODE_STRING *Context; // [rsp+78h] [rbp-90h] BYREF
  struct _UNICODE_STRING Context_8; // [rsp+80h] [rbp-88h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+98h] [rbp-70h] BYREF
  struct _UNICODE_STRING v80; // [rsp+A8h] [rbp-60h] BYREF
  const char *v81; // [rsp+B8h] [rbp-50h] BYREF
  __m128i si128; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v83; // [rsp+D0h] [rbp-38h]
  struct _UNICODE_STRING DestinationString; // [rsp+D8h] [rbp-30h] BYREF
  FsFltWil::Details *v85; // [rsp+E8h] [rbp-20h] BYREF
  struct _UNICODE_STRING *v86; // [rsp+F0h] [rbp-18h]
  __int64 v87; // [rsp+F8h] [rbp-10h]
  struct _FLT_INSTANCE *v88; // [rsp+100h] [rbp-8h]
  UnionFs::UfsUnionCtx *v89; // [rsp+108h] [rbp+0h]
  __int64 *v90; // [rsp+110h] [rbp+8h]
  UNICODE_STRING SourceString; // [rsp+118h] [rbp+10h] BYREF
  _QWORD *v92; // [rsp+128h] [rbp+20h]
  volatile signed __int32 *v93; // [rsp+130h] [rbp+28h]
  struct _FLT_CALLBACK_DATA *v94; // [rsp+138h] [rbp+30h]
  struct _UNICODE_STRING v95; // [rsp+140h] [rbp+38h] BYREF
  struct _UNICODE_STRING v96; // [rsp+158h] [rbp+50h] BYREF
  char v97; // [rsp+168h] [rbp+60h]
  struct _UNICODE_STRING v98[5]; // [rsp+198h] [rbp+90h] BYREF
  utl::_RefCountBase *v99[2]; // [rsp+1E8h] [rbp+E0h]
  __int64 v100; // [rsp+1F8h] [rbp+F0h]
  _BYTE v101[80]; // [rsp+208h] [rbp+100h] BYREF

  v7 = a6;
  v94 = a2;
  v89 = a1;
  v87 = a4;
  v88 = a3;
  v90 = a6;
  v92 = (_QWORD *)((char *)a1 + 72);
  FsFltWil::AcquirePushLockShared(&v76, (char *)a1 + 72);
  v10 = (const char **)*((_QWORD *)a1 + 6);
  v11 = (volatile signed __int32 *)v10[1];
  v12 = *v10;
  v81 = *v10;
  v93 = v11;
  if ( v11 )
    _InterlockedIncrement(v11 + 2);
  if ( v76 )
    FsFltWil::Details::ReleasePushLockShared(v76, v9);
  v86 = (struct _UNICODE_STRING *)*((_QWORD *)v12 + 2);
  v83 = -1;
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
      (const char *)v71);
    if ( (unsigned int)dword_14009E178 > 2 )
    {
      *(_DWORD *)&Context_8.Length = v15;
      LOWORD(v75) = 1551;
      LODWORD(Context) = 454;
      v81 = "UnionFs::UfsUnionCtx::MapHardLinkNamesAndPrepareScratch";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        (unsigned int)&v81,
        (unsigned int)byte_140099275,
        v69,
        v70,
        (__int64)&v81,
        (__int64)&Context,
        (__int64)&v75,
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
      (const char *)v71);
    utl::vector<utl::shared_ptr<UnionFs::UfsTablePayload>,utl::allocator<utl::shared_ptr<UnionFs::UfsTablePayload>>>::~vector<utl::shared_ptr<UnionFs::UfsTablePayload>,utl::allocator<utl::shared_ptr<UnionFs::UfsTablePayload>>>(&si128);
    if ( v11 )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v11);
    return v15;
  }
  v17 = *a6;
  v18 = 0;
  v19 = 0;
  v20 = a6[1] - *a6;
  LODWORD(v75) = 0;
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
    v76 = *(FsFltWil::Details **)(si128.m128i_i64[0] + 16LL * (unsigned int)v18);
    if ( v22 )
      _InterlockedIncrement(v22 + 2);
    if ( v19 )
      utl::_RefCountBase::_DecStrong(v19);
    memset(v101, 0, 0x48u);
    v80 = *v21;
    HostSilo = PsGetHostSilo(v24, v23);
    v72 = a7;
    v26 = UnionFs::Utils::StatItem(&v80, v88, HostSilo, 1, v101);
    v28 = v26;
    if ( v26 != -1073741766 && v26 != -1073741772 )
    {
      if ( v26 < 0 )
      {
        UnionFs::ProcessTraceStatusFromApi(
          (UnionFs *)(unsigned int)v26,
          (int)a7,
          (struct UnionFs::StackEventTracer *)0x39600200654LL,
          (unsigned __int64)"UnionFs::UfsUnionCtx::MapHardLinkNamesAndPrepareScratch",
          "API: Stating scratch",
          (const char *)a7);
        goto LABEL_73;
      }
LABEL_27:
      v33 = 0;
      v34 = (FsFltWil::Details *)(*v7 + *(_QWORD *)&Context_8.Length);
      v35 = v7[1] - (_QWORD)v34;
      v76 = v34;
      v36 = (v35 - 8) >> 3;
      if ( v36 )
      {
        do
        {
          v37 = *((_QWORD *)v34 + v33 + 1);
          *((_QWORD *)v34 + v33 + 1) = 0;
          v38 = *((_QWORD *)v34 + v33);
          *((_QWORD *)v34 + v33) = v37;
          if ( v38 )
          {
            if ( !*(_BYTE *)(v38 + 16) )
              *(_OWORD *)v38 = 0;
            FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)v38, v27);
            ExFreePoolWithTag((PVOID)v38, 0);
            v34 = v76;
          }
          ++v33;
        }
        while ( v33 != v36 );
        v11 = v93;
        v7 = v90;
      }
      v7[1] -= 8;
      v39 = *(_QWORD *)v7[1];
      if ( v39 )
      {
        if ( !*(_BYTE *)(v39 + 16) )
          *(_OWORD *)v39 = 0;
        FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)v39, v27);
        ExFreePoolWithTag((PVOID)v39, 0);
      }
      v40 = v75 - 1;
      goto LABEL_65;
    }
    FsFltWil::AcquirePushLockShared(&v85, v92);
    v29 = v89;
    v30 = v85;
    v85 = 0;
    v31 = (__int64)(*((_QWORD *)v89 + 7) - *((_QWORD *)v89 + 6)) >> 4;
    if ( v30 )
      FsFltWil::Details::ReleasePushLockShared(v30, (unsigned __int64 *)&v27->Length);
    if ( v31 > 1 )
    {
      memset(v98, 0, sizeof(v98));
      v72 = a7;
      *(_OWORD *)v99 = 0;
      v100 = 0;
      v80 = *v86;
      v95 = *Context;
      v28 = UnionFs::UfsUnionCtx::FindAndStatItemInLayers(v29, &v95, &v80, 0, v98);
      if ( v28 < 0 )
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)v28,
          (int)a7,
          (struct UnionFs::StackEventTracer *)0x3B60020064ALL,
          (unsigned __int64)"UnionFs::UfsUnionCtx::MapHardLinkNamesAndPrepareScratch",
          "PUSH: Find and stat link name",
          (const char *)a7);
        if ( v99[1] )
          utl::_RefCountBase::_DecStrong(v99[1]);
        goto LABEL_73;
      }
      v32 = v76 != v99[0];
      if ( v99[1] )
        utl::_RefCountBase::_DecStrong(v99[1]);
      if ( v32 )
        goto LABEL_27;
    }
    v41 = v86;
    UnicodeString = 0;
    Context_8 = *v86;
    v42 = (__m128i)Context_8;
    FsFltWil::Details::FreeUnicodeString(&UnicodeString, v27);
    UnicodeString = 0;
    if ( *(_WORD *)(_mm_srli_si128(v42, 8).m128i_u64[0] + 2) != 68 )
      break;
    p_Length = &Context->Length;
    LOBYTE(v43) = 1;
    v80 = *Context;
    if ( !UnionFs::Rtl::FindUnicodeSubstring((UnionFs::Rtl *)&v80, &Context_8, v43, v44) )
    {
      v66 = "ORIGIN: Could not find PathPrefix in full path";
      v67 = 0x3E9002105A6LL;
      goto LABEL_86;
    }
    v46 = p_Length[12];
    v47 = *p_Length;
    Length = Context_8.Length - 2;
    if ( Context_8.Length != v46 + 2 )
      Length = Context_8.Length;
    if ( Length < v47 )
    {
      v49 = v47 - Length;
      FsFltWil::MakeUniqueUnicodeString(&DestinationString, v49, 1279685446);
      if ( !DestinationString.Buffer )
      {
        v14 = -1073741670;
        UnionFs::ProcessTraceStatusOrigin(
          (UnionFs *)0xC000009ALL,
          (int)a7,
          (struct UnionFs::StackEventTracer *)0x3EB002105C8LL,
          (unsigned __int64)"UnionFs::Utils::GetRemainingPath",
          "ORIGIN: Allocating remainingPath",
          (const char *)v72);
        FsFltWil::Details::FreeUnicodeString(&DestinationString, v65);
        goto LABEL_87;
      }
      SourceString.Buffer = (PWSTR)((char *)v80.Buffer + Length);
      *(_DWORD *)(&SourceString.MaximumLength + 1) = 0;
      SourceString.Length = v49;
      SourceString.MaximumLength = v49;
      RtlCopyUnicodeString(&DestinationString, &SourceString);
      v50 = UnicodeString;
      UnicodeString = DestinationString;
      DestinationString = v50;
      FsFltWil::Details::FreeUnicodeString(&DestinationString, v51);
    }
    else if ( Length != v47 )
    {
      MicrosoftTelemetryAssertTriggeredMsgKM("PathPrefix goes past FullPathName.Path?");
    }
    v52 = v94;
    v53 = 0;
    *(_QWORD *)&Context_8.Length = 0;
    if ( (v94->Iopb->Parameters.Create.Options & 0x1000) != 0 )
      v53 = 4;
    v28 = UnionFs::UfsStreamHandleCtx::FltAllocAndInit(v81, v87, v41, &UnicodeString, v53);
    if ( v28 < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v28,
        (int)a7,
        (struct UnionFs::StackEventTracer *)0xCC00200679LL,
        (unsigned __int64)"UnionFs::UfsUnionCtx::MapHardLinkNamesAndPrepareScratch",
        "PUSH: Creating fake streamhandle context",
        (const char *)&Context_8);
      v64 = *(const struct UnionFs::UfsStreamHandleCtx **)&Context_8.Length;
      if ( *(_QWORD *)&Context_8.Length )
LABEL_81:
        FltReleaseContext(v64);
LABEL_82:
      FsFltWil::Details::FreeUnicodeString(&UnicodeString, v63);
LABEL_73:
      if ( v22 )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v22);
      utl::vector<utl::shared_ptr<UnionFs::UfsTablePayload>,utl::allocator<utl::shared_ptr<UnionFs::UfsTablePayload>>>::~vector<utl::shared_ptr<UnionFs::UfsTablePayload>,utl::allocator<utl::shared_ptr<UnionFs::UfsTablePayload>>>(&si128);
      if ( v11 )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v11);
      return (unsigned int)v28;
    }
    v54 = *(const struct UnionFs::UfsStreamHandleCtx **)&Context_8.Length;
    Buffer = (unsigned __int16)Context[1].Buffer;
    v80 = *Context;
    v95 = v80;
    UnionFs::UfsPathName::UfsPathName((UnionFs::UfsPathName *)v98, &v95, Buffer);
    UnionFs::UfsPathName::UfsPathName((UnionFs::UfsPathName *)&v96, &v80, v56);
    v28 = UnionFs::UfsUnionCtx::EnsureParentPathInScratch(
            v89,
            v52,
            v88,
            (const struct UnionFs::UfsPathName *)v98,
            0,
            (const struct UnionFs::UfsPathName *)&v96,
            v57,
            v54,
            v76,
            a7,
            0);
    if ( v28 >= 0 )
    {
      if ( !v97 )
        v96 = 0;
      FsFltWil::Details::FreeUnicodeString(&v96, v58);
      if ( !LOBYTE(v98[1].Length) )
        v98[0] = 0;
      v28 = 0;
    }
    else
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v28,
        (int)a7,
        (struct UnionFs::StackEventTracer *)0x271002004ACLL,
        (unsigned __int64)"UnionFs::UfsUnionCtx::EnsureParentPathInScratch",
        "PUSH: EnsureParentPathinScratch",
        (const char *)v73);
      if ( !v97 )
        v96 = 0;
      FsFltWil::Details::FreeUnicodeString(&v96, v59);
      if ( !LOBYTE(v98[1].Length) )
        v98[0] = 0;
    }
    FsFltWil::Details::FreeUnicodeString(v98, v60);
    if ( v28 < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v28,
        (int)a7,
        (struct UnionFs::StackEventTracer *)0x3DC00200688LL,
        (unsigned __int64)"UnionFs::UfsUnionCtx::MapHardLinkNamesAndPrepareScratch",
        "PUSH: Preparing for COW",
        (const char *)v73);
      if ( v54 )
      {
        v64 = v54;
        goto LABEL_81;
      }
      goto LABEL_82;
    }
    if ( v54 )
      FltReleaseContext(v54);
    FsFltWil::Details::FreeUnicodeString(&UnicodeString, v61);
    v40 = v75;
    v7 = v90;
LABEL_65:
    v17 = *v7;
    v18 = (unsigned int)(v40 + 1);
    v62 = (v7[1] - *v7) >> 3;
    v19 = (utl::_RefCountBase *)v22;
    LODWORD(v75) = v18;
    if ( (unsigned int)v18 >= v62 )
    {
      if ( v22 )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v22);
      goto LABEL_68;
    }
  }
  MicrosoftTelemetryAssertTriggeredMsgKM("PathPrefix is supposed to start with \\Device");
  v66 = "ORIGIN: PathPrefix doesn't start with \\Device";
  v67 = 0x3E20021059BLL;
  v14 = -1073741773;
LABEL_86:
  UnionFs::ProcessTraceStatusOrigin(
    (UnionFs *)v14,
    (int)a7,
    (struct UnionFs::StackEventTracer *)v67,
    (unsigned __int64)"UnionFs::Utils::GetRemainingPath",
    v66,
    (const char *)v72);
LABEL_87:
  UnionFs::ProcessTraceStatusPushLocation(
    (UnionFs *)v14,
    (int)a7,
    (struct UnionFs::StackEventTracer *)0x29E0020066ALL,
    (unsigned __int64)"UnionFs::UfsUnionCtx::MapHardLinkNamesAndPrepareScratch",
    "PUSH: Getting relative path",
    (const char *)v74);
  FsFltWil::Details::FreeUnicodeString(&UnicodeString, v68);
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
0x140061f2c  mov     rax, rsp
0x140061f2f  push    rbp
0x140061f30  push    rbx
0x140061f31  push    rsi
0x140061f32  push    rdi
0x140061f33  push    r12
0x140061f35  push    r13
0x140061f37  push    r14
0x140061f39  push    r15
0x140061f3b  lea     rbp, [rax-1B8h]
0x140061f42  sub     rsp, 278h
0x140061f49  movaps  xmmword ptr [rax-58h], xmm6
0x140061f4d  mov     rax, cs:__security_cookie
0x140061f54  xor     rax, rsp
0x140061f57  mov     [rbp+1B0h+var_60], rax
0x140061f5e  mov     r12, [rbp+1B0h+arg_28]
0x140061f65  lea     rax, [rcx+48h]
0x140061f69  mov     rdi, [rbp+1B0h+arg_20]
0x140061f70  mov     r14, rcx
0x140061f73  mov     rsi, [rbp+1B0h+arg_30]
0x140061f7a  mov     [rbp+1B0h+var_180], rdx
0x140061f7e  mov     rdx, rax
0x140061f81  mov     [rbp+1B0h+var_1B0], rcx
0x140061f85  lea     rcx, [rsp+2B0h+var_248]
0x140061f8a  mov     [rbp+1B0h+var_1C0], r9
0x140061f8e  mov     [rbp+1B0h+var_1B8], r8
0x140061f92  mov     [rbp+1B0h+var_1A8], r12
0x140061f96  mov     [rbp+1B0h+var_190], rax
0x140061f9a  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x140061f9f  mov     rax, [r14+30h]
0x140061fa3  mov     rbx, [rax+8]
0x140061fa7  mov     r15, [rax]
0x140061faa  mov     [rbp+1B0h+var_200], r15
0x140061fae  mov     [rbp+1B0h+var_188], rbx
0x140061fb2  test    rbx, rbx
0x140061fb5  jz      short loc_140061FBB
0x140061fb7  lock inc dword ptr [rbx+8]
0x140061fbb  mov     rcx, [rsp+2B0h+var_248]; this
0x140061fc0  test    rcx, rcx
0x140061fc3  jz      short loc_140061FCA
0x140061fc5  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x140061fca  mov     rax, [r15+10h]
0x140061fce  mov     r9, rsi
0x140061fd1  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x140061fd9  mov     r8, r12
0x140061fdc  mov     [rbp+1B0h+var_1C8], rax
0x140061fe0  mov     rdx, rdi
0x140061fe3  lea     rax, [rbp+1B0h+var_1F8]
0x140061fe7  mov     [rbp+1B0h+var_1E8], 0FFFFFFFFFFFFFFFFh
0x140061fef  mov     rcx, r14
0x140061ff2  mov     [rsp+2B0h+var_290], rax
0x140061ff7  movdqu  [rbp+1B0h+var_1F8], xmm0
0x140061ffc  call    ?ConvertLayerPathsToScratchPaths@UfsUnionCtx@UnionFs@@QEBAJAEBV?$vector@V?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@V?$allocator@V?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@@2@@utl@@AEAV34@AEAVStackEventTracer@2@PEAV?$vector@V?$shared_ptr@VUfsLayerCtx@UnionFs@@@utl@@V?$allocator@V?$shared_ptr@VUfsLayerCtx@UnionFs@@@utl@@@2@@4@@Z; UnionFs::UfsUnionCtx::ConvertLayerPathsToScratchPaths(utl::vector<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>,utl::allocator<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>> const &,utl::vector<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>,utl::allocator<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>> &,UnionFs::StackEventTracer &,utl::vector<utl::shared_ptr<UnionFs::UfsLayerCtx>,utl::allocator<utl::shared_ptr<UnionFs::UfsLayerCtx>>> *)
0x140062001  mov     r13d, 0C0000225h
0x140062007  mov     r14d, eax
0x14006200a  cmp     eax, r13d
0x14006200d  jz      loc_1400627F8
0x140062013  cmp     eax, 0C000000Dh
0x140062018  jz      loc_1400627F8
0x14006201e  test    eax, eax
0x140062020  jns     short loc_140062068
0x140062022  lea     rax, aPushConverting_1; "PUSH: Converting layer paths to scratch"...
0x140062029  mov     r8, 5F800200612h; struct UnionFs::StackEventTracer *
0x140062033  lea     r9, aUnionfsUfsunio_3; "UnionFs::UfsUnionCtx::MapHardLinkNamesA"...
0x14006203a  mov     [rsp+2B0h+var_290], rax; char *
0x14006203f  mov     rdx, rsi; int
0x140062042  mov     ecx, r14d; this
0x140062045  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006204a  lea     rcx, [rbp+1B0h+var_1F8]
0x14006204e  call    ??1?$vector@V?$shared_ptr@VUfsTablePayload@UnionFs@@@utl@@V?$allocator@V?$shared_ptr@VUfsTablePayload@UnionFs@@@utl@@@2@@utl@@QEAA@XZ; utl::vector<utl::shared_ptr<UnionFs::UfsTablePayload>,utl::allocator<utl::shared_ptr<UnionFs::UfsTablePayload>>>::~vector<utl::shared_ptr<UnionFs::UfsTablePayload>,utl::allocator<utl::shared_ptr<UnionFs::UfsTablePayload>>>(void)
0x140062053  test    rbx, rbx
0x140062056  jz      short loc_140062060
0x140062058  mov     rcx, rbx; this
0x14006205b  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140062060  mov     eax, r14d
0x140062063  jmp     loc_1400628AF
0x140062068  mov     r8, [r12]
0x14006206c  xor     r9d, r9d
0x14006206f  mov     rax, [r12+8]
0x140062074  xor     edx, edx
0x140062076  sub     rax, r8
0x140062079  mov     dword ptr [rsp+2B0h+var_250], r9d
0x14006207e  sar     rax, 3
0x140062082  test    rax, rax
0x140062085  jz      loc_140062617
0x14006208b  lea     r15d, [rdx+1]
0x14006208f  lea     rcx, ds:0[r9*8]
0x140062097  mov     eax, r9d
0x14006209a  mov     rdi, [r8+rcx]
0x14006209e  add     rax, rax
0x1400620a1  mov     r8, qword ptr [rbp+1B0h+var_1F8]
0x1400620a5  mov     [rsp+2B0h+Context+8], rcx
0x1400620aa  mov     [rsp+2B0h+Context], rdi
0x1400620af  mov     r14, [r8+rax*8+8]
0x1400620b4  mov     rcx, [r8+rax*8]
0x1400620b8  mov     [rsp+2B0h+var_248], rcx
0x1400620bd  test    r14, r14
0x1400620c0  jz      short loc_1400620C7
0x1400620c2  lock inc dword ptr [r14+8]
0x1400620c7  test    rdx, rdx
0x1400620ca  jz      short loc_1400620D4
0x1400620cc  mov     rcx, rdx; this
0x1400620cf  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1400620d4  xor     edx, edx; Val
0x1400620d6  lea     rcx, [rbp+1B0h+var_B0]; void *
0x1400620dd  lea     r8d, [rdx+48h]; Size
0x1400620e1  call    memset
0x1400620e6  movups  xmm0, xmmword ptr [rdi]
0x1400620e9  movdqu  xmmword ptr [rbp+1B0h+var_210.Length], xmm0
0x1400620ee  call    cs:__imp_PsGetHostSilo
0x1400620f5  nop     dword ptr [rax+rax+00h]
0x1400620fa  mov     rdx, [rbp+1B0h+var_1B8]
0x1400620fe  lea     rcx, [rbp+1B0h+var_B0]
0x140062105  mov     [rsp+2B0h+var_278], 0
0x14006210e  mov     r9d, r15d
0x140062111  mov     qword ptr [rsp+2B0h+var_280], 0
0x14006211a  mov     r8, rax
0x14006211d  mov     [rsp+2B0h+var_288], rsi; char *
0x140062122  mov     [rsp+2B0h+var_290], rcx
0x140062127  lea     rcx, [rbp+1B0h+var_210]
0x14006212b  call    ?StatItem@Utils@UnionFs@@YAJAEBU_UNICODE_STRING@@AEBU_FLT_INSTANCE@@AEBU_EJOB@@W4StatItemFlags@12@PEAU_FILE_STAT_INFORMATION@@AEAVStackEventTracer@2@QEAU_TXN_PARAMETER_BLOCK@@PEAU_FLT_CALLBACK_DATA@@@Z; UnionFs::Utils::StatItem(_UNICODE_STRING const &,_FLT_INSTANCE const &,_EJOB const &,UnionFs::Utils::StatItemFlags,_FILE_STAT_INFORMATION *,UnionFs::StackEventTracer &,_TXN_PARAMETER_BLOCK * const,_FLT_CALLBACK_DATA *)
0x140062130  mov     r15d, eax
0x140062133  cmp     eax, 0C000003Ah
0x140062138  jz      short loc_140062176
0x14006213a  cmp     eax, 0C0000034h
0x14006213f  jz      short loc_140062176
0x140062141  test    eax, eax
0x140062143  jns     loc_14006226C
0x140062149  lea     rax, aApiStatingScra; "API: Stating scratch"
0x140062150  mov     r8, 39600200654h; struct UnionFs::StackEventTracer *
0x14006215a  lea     r9, aUnionfsUfsunio_3; "UnionFs::UfsUnionCtx::MapHardLinkNamesA"...
0x140062161  mov     [rsp+2B0h+var_290], rax; char *
0x140062166  mov     rdx, rsi; int
0x140062169  mov     ecx, r15d; this
0x14006216c  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140062171  jmp     loc_14006266D
0x140062176  mov     rdx, [rbp+1B0h+var_190]
0x14006217a  lea     rcx, [rbp+1B0h+var_1D0]
0x14006217e  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x140062183  mov     r15, [rbp+1B0h+var_1B0]
0x140062187  mov     rcx, [rbp+1B0h+var_1D0]; this
0x14006218b  mov     [rbp+1B0h+var_1D0], 0
0x140062193  mov     rdi, [r15+38h]
0x140062197  sub     rdi, [r15+30h]
0x14006219b  sar     rdi, 4
0x14006219f  test    rcx, rcx
0x1400621a2  jz      short loc_1400621A9
0x1400621a4  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x1400621a9  cmp     rdi, 1
0x1400621ad  jbe     loc_140062330
0x1400621b3  xor     eax, eax
0x1400621b5  lea     rcx, [rbp+1B0h+var_120.Buffer]; void *
0x1400621bc  xor     edx, edx; Val
0x1400621be  mov     [rbp+1B0h+var_120.Length], ax
0x1400621c5  mov     dword ptr [rbp+1B0h+var_120.MaximumLength], eax
0x1400621cb  mov     word ptr [rbp+1B0h+var_120+6], ax
0x1400621d2  lea     r8d, [rax+48h]; Size
0x1400621d6  call    memset
0x1400621db  mov     rax, [rbp+1B0h+var_1C8]
0x1400621df  lea     r8, [rbp+1B0h+var_210]
0x1400621e3  xorps   xmm0, xmm0
0x1400621e6  mov     [rsp+2B0h+var_288], rsi; char *
0x1400621eb  movdqa  xmmword ptr [rbp+1B0h+var_D0], xmm0
0x1400621f3  lea     rdx, [rbp+1B0h+var_178]
0x1400621f7  xor     r9d, r9d
0x1400621fa  mov     [rbp+1B0h+var_C0], 0
0x140062205  movups  xmm1, xmmword ptr [rax]
0x140062208  mov     rax, [rsp+2B0h+Context]
0x14006220d  mov     rcx, r15
0x140062210  movdqu  xmmword ptr [rbp+1B0h+var_210.Length], xmm1
0x140062215  movups  xmm0, xmmword ptr [rax]
0x140062218  lea     rax, [rbp+1B0h+var_120]
0x14006221f  mov     [rsp+2B0h+var_290], rax
0x140062224  movdqu  xmmword ptr [rbp+1B0h+var_178.Length], xmm0
0x140062229  call    ?FindAndStatItemInLayers@UfsUnionCtx@UnionFs@@QEBAJAEBU_UNICODE_STRING@@0W4StatItemFlags@Utils@2@AEAUFindAndStatResults@2@AEAVStackEventTracer@2@@Z; UnionFs::UfsUnionCtx::FindAndStatItemInLayers(_UNICODE_STRING const &,_UNICODE_STRING const &,UnionFs::Utils::StatItemFlags,UnionFs::FindAndStatResults &,UnionFs::StackEventTracer &)
0x14006222e  mov     r15d, eax
0x140062231  test    eax, eax
0x140062233  js      loc_140062634
0x140062239  mov     rcx, [rbp+1B0h+var_D0+8]; this
0x140062240  xor     al, al
0x140062242  movzx   edi, al
0x140062245  mov     rax, [rsp+2B0h+var_248]
0x14006224a  cmp     rax, [rbp+1B0h+var_D0]
0x140062251  mov     eax, 1
0x140062256  cmovnz  edi, eax
0x140062259  test    rcx, rcx
0x14006225c  jz      short loc_140062263
0x14006225e  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140062263  test    dil, dil
0x140062266  jz      loc_140062330
0x14006226c  mov     rcx, [rsp+2B0h+Context+8]
0x140062271  xor     r15d, r15d
0x140062274  add     rcx, [r12]
0x140062278  mov     rdi, [r12+8]
0x14006227d  sub     rdi, rcx
0x140062280  mov     [rsp+2B0h+var_248], rcx
0x140062285  sub     rdi, 8
0x140062289  sar     rdi, 3
0x14006228d  test    rdi, rdi
0x140062290  jz      short loc_1400622EB
0x140062292  mov     rax, [rcx+r15*8+8]
0x140062297  mov     qword ptr [rcx+r15*8+8], 0
0x1400622a0  mov     r12, [rcx+r15*8]
0x1400622a4  mov     [rcx+r15*8], rax
0x1400622a8  test    r12, r12
0x1400622ab  jz      short loc_1400622DB
0x1400622ad  cmp     byte ptr [r12+10h], 0
0x1400622b3  jnz     short loc_1400622BD
0x1400622b5  xorps   xmm0, xmm0
0x1400622b8  movups  xmmword ptr [r12], xmm0
0x1400622bd  mov     rcx, r12; UnicodeString
0x1400622c0  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x1400622c5  xor     edx, edx; Tag
0x1400622c7  mov     rcx, r12; P
0x1400622ca  call    cs:__imp_ExFreePoolWithTag
0x1400622d1  nop     dword ptr [rax+rax+00h]
0x1400622d6  mov     rcx, [rsp+2B0h+var_248]
0x1400622db  inc     r15
0x1400622de  cmp     r15, rdi
0x1400622e1  jnz     short loc_140062292
0x1400622e3  mov     rbx, [rbp+1B0h+var_188]
0x1400622e7  mov     r12, [rbp+1B0h+var_1A8]
0x1400622eb  add     qword ptr [r12+8], 0FFFFFFFFFFFFFFF8h
0x1400622f1  mov     rax, [r12+8]
0x1400622f6  mov     rdi, [rax]
0x1400622f9  test    rdi, rdi
0x1400622fc  jz      short loc_140062323
0x1400622fe  cmp     byte ptr [rdi+10h], 0
0x140062302  jnz     short loc_14006230A
0x140062304  xorps   xmm0, xmm0
0x140062307  movups  xmmword ptr [rdi], xmm0
0x14006230a  mov     rcx, rdi; UnicodeString
0x14006230d  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140062312  xor     edx, edx; Tag
0x140062314  mov     rcx, rdi; P
0x140062317  call    cs:__imp_ExFreePoolWithTag
0x14006231e  nop     dword ptr [rax+rax+00h]
0x140062323  mov     r9d, dword ptr [rsp+2B0h+var_250]
0x140062328  dec     r9d
0x14006232b  jmp     loc_1400625DD
0x140062330  mov     r12, [rbp+1B0h+var_1C8]
0x140062334  lea     rcx, [rbp+1B0h+UnicodeString]; UnicodeString
0x140062338  xorps   xmm0, xmm0
0x14006233b  movups  xmmword ptr [rbp+1B0h+UnicodeString.Length], xmm0
0x14006233f  movups  xmm6, xmmword ptr [r12]
0x140062344  movups  xmmword ptr [rsp+2B0h+Context+8], xmm6
0x140062349  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14006234e  psrldq  xmm6, 8
0x140062353  xorps   xmm0, xmm0
0x140062356  movq    rax, xmm6
0x14006235b  movups  xmmword ptr [rbp+1B0h+UnicodeString.Length], xmm0
0x14006235f  cmp     word ptr [rax+2], 44h ; 'D'
0x140062364  jnz     loc_140062762
0x14006236a  mov     r15, [rsp+2B0h+Context]
0x14006236f  lea     rdx, [rsp+2B0h+Context+8]; struct _UNICODE_STRING *
0x140062374  mov     r8b, 1; struct _UNICODE_STRING *
0x140062377  lea     rcx, [rbp+1B0h+var_210]; this
0x14006237b  movups  xmm0, xmmword ptr [r15]
0x14006237f  movdqu  xmmword ptr [rbp+1B0h+var_210.Length], xmm0
0x140062384  call    ?FindUnicodeSubstring@Rtl@UnionFs@@YAPEAGPEBU_UNICODE_STRING@@0E@Z; UnionFs::Rtl::FindUnicodeSubstring(_UNICODE_STRING const *,_UNICODE_STRING const *,uchar)
0x140062389  test    rax, rax
0x14006238c  jz      loc_14006274F
0x140062392  movzx   edx, word ptr [rsp+2B0h+Context+8]
0x140062397  mov     r8d, 2
0x14006239d  movzx   ecx, word ptr [r15+18h]
0x1400623a2  movzx   edi, dx
0x1400623a5  movzx   r15d, word ptr [r15]
0x1400623a9  sub     di, r8w
0x1400623ad  add     rcx, r8
0x1400623b0  cmp     rdx, rcx
0x1400623b3  cmovnz  di, dx
0x1400623b7  cmp     di, r15w
0x1400623bb  jb      short loc_1400623CD
0x1400623bd  jz      short loc_14006243A
0x1400623bf  lea     rcx, aPathprefixGoes; "PathPrefix goes past FullPathName.Path?"
0x1400623c6  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x1400623cb  jmp     short loc_14006243A
0x1400623cd  sub     r15w, di
0x1400623d1  lea     rcx, [rbp+1B0h+DestinationString]
0x1400623d5  movzx   edx, r15w
0x1400623d9  mov     r8d, 4C467346h
0x1400623df  call    ?MakeUniqueUnicodeString@FsFltWil@@YA?AV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@GKW4FSFLT_ALLOC_TYPE@@@Z; FsFltWil::MakeUniqueUnicodeString(ushort,ulong,FSFLT_ALLOC_TYPE)
0x1400623e4  cmp     [rbp+1B0h+DestinationString.Buffer], 0
0x1400623e9  jz      loc_140062716
0x1400623ef  movzx   eax, di
0x1400623f2  lea     rdx, [rbp+1B0h+SourceString]; SourceString
0x1400623f6  add     rax, [rbp+1B0h+var_210.Buffer]
0x1400623fa  lea     rcx, [rbp+1B0h+DestinationString]; DestinationString
0x1400623fe  mov     [rbp+1B0h+SourceString.Buffer], rax
0x140062402  mov     dword ptr [rbp+1B0h+SourceString+4], 0
0x140062409  mov     [rbp+1B0h+SourceString.Length], r15w
0x14006240e  mov     [rbp+1B0h+SourceString.MaximumLength], r15w
0x140062413  call    cs:__imp_RtlCopyUnicodeString
0x14006241a  nop     dword ptr [rax+rax+00h]
0x14006241f  movaps  xmm1, xmmword ptr [rbp+1B0h+UnicodeString.Length]
0x140062423  lea     rcx, [rbp+1B0h+DestinationString]; UnicodeString
0x140062427  movaps  xmm0, xmmword ptr [rbp+1B0h+DestinationString.Length]
0x14006242b  movdqa  xmmword ptr [rbp+1B0h+UnicodeString.Length], xmm0
0x140062430  movdqa  xmmword ptr [rbp+1B0h+DestinationString.Length], xmm1
0x140062435  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
  ... truncated ...
```
