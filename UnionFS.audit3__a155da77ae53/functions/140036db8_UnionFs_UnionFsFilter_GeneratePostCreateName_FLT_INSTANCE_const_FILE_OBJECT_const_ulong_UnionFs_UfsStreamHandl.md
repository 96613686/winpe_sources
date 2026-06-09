# UnionFs::UnionFsFilter::GeneratePostCreateName(_FLT_INSTANCE const &,_FILE_OBJECT const &,ulong,UnionFs::UfsStreamHandleCtx const &,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0> &,UnionFs::StackEventTracer &,bool)

- ea: `0x140036db8`
- end: `0x140037a5e`
- name: `?GeneratePostCreateName@UnionFsFilter@UnionFs@@QEAAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@KAEBVUfsStreamHandleCtx@2@AEAV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@AEAVStackEventTracer@2@_N@Z`
- size: `3238`
- prototype: `__int64 __fastcall(int, int, int, int, UnionFs::UfsStreamHandleCtx *, __int64, struct UnionFs::StackEventTracer *, char)`
- caller_count: `2`
- callee_count: `24`
- tags: `file_ops, reparse_path, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400357f4`
- `0x140037a64`

## callees

- `0x14000f81c`
- `0x1400111b8`
- `0x140028990`
- `0x140028b3c`
- `0x140028c48`
- `0x14002aca0`
- `0x14002ad1c`
- `0x14002ae84`
- `0x140036db8`
- `0x14003cf90`
- `0x140043afc`
- `0x140044074`
- `0x1400446ac`
- `0x1400448c8`
- `0x140044d84`
- `0x140056c44`
- `0x140056c7c`
- `0x14006e394`
- `0x140079f68`
- `0x14007a114`
- `0x14007b2b0`
- `0x14007baf0`
- `0x14007bbd0`
- `0x14007bf40`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140036efa`
- `ntoskrnl!ExFreePoolWithTag` at `0x140036fab`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003701c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400370a0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400370ca`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400370f9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400371b7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400371e1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003720b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003729d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400372c7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400372f1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037405`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003742f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037459`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400374e3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037543`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003756d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037597`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037666`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003777e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400377a9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037809`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037833`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003785d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400378ae`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400378dc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003793c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037966`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400379de`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037a0d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140036efa`
- `ntoskrnl!ExFreePoolWithTag` at `0x140036fab`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003701c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400370a0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400370ca`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400370f9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400371b7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400371e1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003720b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003729d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400372c7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400372f1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037405`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003742f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037459`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400374e3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037543`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003756d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037597`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037666`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003777e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400377a9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037809`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037833`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003785d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400378ae`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400378dc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003793c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037966`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400379de`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037a0d`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140036e80`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140036f15`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140037114`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140037226`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14003730c`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400375b2`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140037878`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140037a28`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140036e80`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140036f15`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140037114`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140037226`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14003730c`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400375b2`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140037878`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140037a28`

## string_xrefs

- `0x140037497`: `PUSH: Getting opened path`
- `0x140036f5e`: `PUSH: Duplicating layer root path`
- `0x140036f6f`: `UnionFs::UfsLayerCtx::GetNormalizedLayerRootPath`
- `0x140036e5b`: `UnionFs::UnionFsFilter::GeneratePostCreateName`
- `0x140036ec1`: `UnionFs::UnionFsFilter::GeneratePostCreateName`
- `0x140036fe4`: `UnionFs::UnionFsFilter::GeneratePostCreateName`
- `0x140037067`: `UnionFs::UnionFsFilter::GeneratePostCreateName`
- `0x140037182`: `UnionFs::UnionFsFilter::GeneratePostCreateName`
- `0x140037269`: `UnionFs::UnionFsFilter::GeneratePostCreateName`
- `0x140037397`: `UnionFs::UnionFsFilter::GeneratePostCreateName`
- `0x1400374a8`: `UnionFs::UnionFsFilter::GeneratePostCreateName`
- `0x140037630`: `UnionFs::UnionFsFilter::GeneratePostCreateName`
- `0x140037740`: `UnionFs::UnionFsFilter::GeneratePostCreateName`
- `0x1400379a6`: `UnionFs::UnionFsFilter::GeneratePostCreateName`
- `0x140036e11`: `(FltGetFileNameFormat(NameOptions) == FLT_FILE_NAME_OPENED) || (FltGetFileNameFormat(NameOptions) == FLT_FILE_NAME_NORMALIZED)`
- `0x140036eb0`: `PUSH: Allocing backing file path`
- `0x140036fd3`: `PUSH: Getting layer root path`
- `0x140037056`: `PUSH: Getting normalized scratch root path`
- `0x140037132`: `PUSH: Getting opened scratch root path`
- `0x14003761f`: `PUSH: Path Cache lookup`
- `0x140037995`: `PUSH: Copying filePath to OutputName`

## pseudocode

```c
__int64 __fastcall UnionFs::UnionFsFilter::GeneratePostCreateName(
        __int64 a1,
        __int64 a2,
        WCHAR *a3,
        unsigned int a4,
        UnionFs::UfsStreamHandleCtx *a5,
        __int64 a6,
        struct UnionFs::StackEventTracer *a7,
        char a8)
{
  int v11; // r13d
  int v12; // ebx
  struct _FLT_FILE_NAME_INFORMATION *v13; // rcx
  int v15; // edi
  __int64 v16; // r9
  struct _UNICODE_STRING *v17; // rdx
  struct _UNICODE_STRING *v18; // rbx
  struct _FLT_FILE_NAME_INFORMATION *v19; // rcx
  __int64 BackingLayer; // rax
  struct _UNICODE_STRING *v21; // rbx
  struct _UNICODE_STRING *v22; // rdx
  struct _UNICODE_STRING *v23; // rsi
  int NormalizedScratchRootPath; // esi
  const char *v25; // rax
  __int64 v26; // r8
  struct _UNICODE_STRING *v27; // rdx
  struct _UNICODE_STRING *v28; // rdi
  struct _UNICODE_STRING *v29; // rbx
  struct _FLT_FILE_NAME_INFORMATION *v30; // rcx
  struct _UNICODE_STRING *v31; // rsi
  struct _UNICODE_STRING *v32; // rdi
  int v33; // r12d
  struct _UNICODE_STRING *v34; // rdx
  struct _FLT_FILE_NAME_INFORMATION *v35; // rcx
  const struct _FLT_INSTANCE *ScratchInstance; // r13
  struct _UNICODE_STRING *v37; // rdx
  struct _FLT_FILE_NAME_INFORMATION *v38; // rcx
  struct FsFltWil::Details::RundownRefCacheAware *v39; // rdx
  struct _UNICODE_STRING *v40; // rdx
  int OpenedPath; // r15d
  struct _UNICODE_STRING *v42; // rdx
  struct _UNICODE_STRING *v43; // r14
  struct _UNICODE_STRING *v44; // rdx
  struct _FLT_FILE_NAME_INFORMATION *v45; // rcx
  __int64 v46; // rcx
  struct _UNICODE_STRING *v47; // r15
  struct _UNICODE_STRING *v48; // rdx
  struct _UNICODE_STRING *v49; // rdx
  struct _UNICODE_STRING *v50; // r12
  __int128 v51; // xmm1
  struct _UNICODE_STRING *v52; // rdx
  int v53; // r13d
  struct _UNICODE_STRING *v54; // rdx
  struct _UNICODE_STRING *v55; // r14
  struct _UNICODE_STRING *v56; // rdx
  struct _FLT_FILE_NAME_INFORMATION *v57; // rcx
  struct _UNICODE_STRING *v58; // rdx
  struct _UNICODE_STRING *v59; // rdx
  struct _UNICODE_STRING *v60; // rdx
  struct _FLT_FILE_NAME_INFORMATION *v61; // rcx
  const char *v62; // [rsp+28h] [rbp-D8h]
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+40h] [rbp-C0h] BYREF
  PVOID v64; // [rsp+48h] [rbp-B8h] BYREF
  PVOID P[2]; // [rsp+50h] [rbp-B0h] BYREF
  char v66[16]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v67; // [rsp+70h] [rbp-90h]
  __int64 v68; // [rsp+80h] [rbp-80h]
  __int64 v69; // [rsp+88h] [rbp-78h]
  __int128 v70; // [rsp+90h] [rbp-70h]
  __int64 v71; // [rsp+A0h] [rbp-60h]
  UNICODE_STRING Source; // [rsp+A8h] [rbp-58h] BYREF
  struct _UNICODE_STRING v73; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v74; // [rsp+D0h] [rbp-30h]
  utl::_RefCountBase *v75[2]; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD v76[17]; // [rsp+F0h] [rbp-10h] BYREF

  v11 = (unsigned __int8)a4;
  v71 = a6;
  if ( (unsigned int)(unsigned __int8)a4 - 1 > 1 )
    MicrosoftTelemetryAssertTriggeredMsgKM(
      "(FltGetFileNameFormat(NameOptions) == FLT_FILE_NAME_OPENED) || (FltGetFileNameFormat(NameOptions) == FLT_FILE_NAME_NORMALIZED)");
  v73.Buffer = a3;
  FileNameInformation = 0;
  *(_QWORD *)&v73.Length = 0;
  v74 = a2;
  v12 = UnionFs::Utils::GetFileNameInformation(&v73, a4, &FileNameInformation, a7);
  if ( v12 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v12,
      (int)a7,
      (struct UnionFs::StackEventTracer *)0x14A000F059BLL,
      (unsigned __int64)"UnionFs::UnionFsFilter::GeneratePostCreateName",
      "PUSH: Getting backing file name info",
      v62);
LABEL_5:
    v13 = FileNameInformation;
    FileNameInformation = 0;
    if ( v13 )
      FltReleaseFileNameInformation(v13);
    return (unsigned int)v12;
  }
  P[0] = 0;
  v15 = UnionFs::UfsPathName::AllocAndInit(FileNameInformation, P, a7);
  if ( v15 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v15,
      (int)a7,
      (struct UnionFs::StackEventTracer *)0x67F000F05A1LL,
      (unsigned __int64)"UnionFs::UnionFsFilter::GeneratePostCreateName",
      "PUSH: Allocing backing file path",
      v62);
LABEL_10:
    v18 = (struct _UNICODE_STRING *)P[0];
    if ( P[0] )
    {
      if ( !*((_BYTE *)P[0] + 16) )
        *(_OWORD *)P[0] = 0;
      FsFltWil::Details::FreeUnicodeString(v18, v17);
      ExFreePoolWithTag(v18, 0);
    }
    v19 = FileNameInformation;
    FileNameInformation = 0;
    if ( v19 )
      FltReleaseFileNameInformation(v19);
    return (unsigned int)v15;
  }
  if ( (*(_DWORD *)a5 & 0x20) != 0 )
  {
    v32 = (struct _UNICODE_STRING *)P[0];
  }
  else
  {
    BackingLayer = UnionFs::UfsStreamHandleCtx::TryGetBackingLayer(a5, &Source);
    v64 = 0;
    v15 = UnionFs::UfsPathName::Copy(*(PCUNICODE_STRING *)(*(_QWORD *)BackingLayer + 16LL));
    if ( v15 >= 0 )
    {
      v21 = (struct _UNICODE_STRING *)v64;
      v15 = 0;
    }
    else
    {
      v21 = 0;
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v15,
        (int)a7,
        (struct UnionFs::StackEventTracer *)0x5A7000D00C0LL,
        (unsigned __int64)"UnionFs::UfsLayerCtx::GetNormalizedLayerRootPath",
        "PUSH: Duplicating layer root path",
        v62);
      v23 = (struct _UNICODE_STRING *)v64;
      if ( v64 )
      {
        if ( !*((_BYTE *)v64 + 16) )
          *(_OWORD *)v64 = 0;
        FsFltWil::Details::FreeUnicodeString(v23, v22);
        ExFreePoolWithTag(v23, 0);
      }
    }
    if ( Source.Buffer )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)Source.Buffer);
    if ( v15 < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v15,
        (int)a7,
        (struct UnionFs::StackEventTracer *)0x29D000F05ABLL,
        (unsigned __int64)"UnionFs::UnionFsFilter::GeneratePostCreateName",
        "PUSH: Getting layer root path",
        v62);
      if ( v21 )
      {
        if ( !LOBYTE(v21[1].Length) )
          *v21 = 0;
        FsFltWil::Details::FreeUnicodeString(v21, v17);
        ExFreePoolWithTag(v21, 0);
      }
      goto LABEL_10;
    }
    v64 = 0;
    if ( v11 == 1 )
    {
      NormalizedScratchRootPath = UnionFs::UfsStreamHandleCtx::GetNormalizedScratchRootPath(a5, &v64, a7);
      if ( NormalizedScratchRootPath < 0 )
      {
        v25 = "PUSH: Getting normalized scratch root path";
        v26 = 0x1B8000F05B3LL;
LABEL_34:
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)NormalizedScratchRootPath,
          (int)a7,
          (struct UnionFs::StackEventTracer *)v26,
          (unsigned __int64)"UnionFs::UnionFsFilter::GeneratePostCreateName",
          v25,
          v62);
        v28 = (struct _UNICODE_STRING *)v64;
        if ( v64 )
        {
          if ( !*((_BYTE *)v64 + 16) )
            *(_OWORD *)v64 = 0;
          FsFltWil::Details::FreeUnicodeString(v28, v27);
          ExFreePoolWithTag(v28, 0);
        }
        if ( v21 )
        {
          if ( !LOBYTE(v21[1].Length) )
            *v21 = 0;
          FsFltWil::Details::FreeUnicodeString(v21, v27);
          ExFreePoolWithTag(v21, 0);
        }
        v29 = (struct _UNICODE_STRING *)P[0];
        if ( P[0] )
        {
          if ( !*((_BYTE *)P[0] + 16) )
            *(_OWORD *)P[0] = 0;
          FsFltWil::Details::FreeUnicodeString(v29, v27);
          ExFreePoolWithTag(v29, 0);
        }
        v30 = FileNameInformation;
        FileNameInformation = 0;
        if ( v30 )
          FltReleaseFileNameInformation(v30);
        return (unsigned int)NormalizedScratchRootPath;
      }
    }
    else
    {
      NormalizedScratchRootPath = UnionFs::UfsStreamHandleCtx::GetOpenedScratchRootPath(a5, &v64, a7);
      if ( NormalizedScratchRootPath < 0 )
      {
        v25 = "PUSH: Getting opened scratch root path";
        v26 = 0x67C000F05BALL;
        goto LABEL_34;
      }
    }
    v31 = (struct _UNICODE_STRING *)v64;
    v32 = (struct _UNICODE_STRING *)P[0];
    v33 = UnionFs::UfsPathName::ReplacePathPrefix(
            (UnionFs::UfsPathName *)P[0],
            (const struct UnionFs::UfsPathName *)v21,
            (const struct UnionFs::UfsPathName *)v64,
            a7);
    if ( v33 < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v33,
        (int)a7,
        (struct UnionFs::StackEventTracer *)0x14C000F05C0LL,
        (unsigned __int64)"UnionFs::UnionFsFilter::GeneratePostCreateName",
        "PUSH: Replacing layer with scratch root",
        v62);
LABEL_53:
      if ( v31 )
      {
        if ( !LOBYTE(v31[1].Length) )
          *v31 = 0;
        FsFltWil::Details::FreeUnicodeString(v31, v34);
        ExFreePoolWithTag(v31, 0);
      }
      if ( v21 )
      {
        if ( !LOBYTE(v21[1].Length) )
          *v21 = 0;
        FsFltWil::Details::FreeUnicodeString(v21, v34);
        ExFreePoolWithTag(v21, 0);
      }
      if ( v32 )
      {
        if ( !LOBYTE(v32[1].Length) )
          *v32 = 0;
        FsFltWil::Details::FreeUnicodeString(v32, v34);
        ExFreePoolWithTag(v32, 0);
      }
      v35 = FileNameInformation;
      FileNameInformation = 0;
LABEL_66:
      if ( v35 )
        FltReleaseFileNameInformation(v35);
      return (unsigned int)v33;
    }
    ScratchInstance = UnionFs::UfsStreamHandleCtx::TryGetScratchInstance(a5);
    if ( !ScratchInstance )
    {
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC0ED0008LL,
        (int)a7,
        (struct UnionFs::StackEventTracer *)0x680000F05C7LL,
        (unsigned __int64)"UnionFs::UnionFsFilter::GeneratePostCreateName",
        "ORIGIN: Scratch instance not available",
        v62);
      if ( v31 )
      {
        if ( !LOBYTE(v31[1].Length) )
          *v31 = 0;
        FsFltWil::Details::FreeUnicodeString(v31, v37);
        ExFreePoolWithTag(v31, 0);
      }
      if ( v21 )
      {
        if ( !LOBYTE(v21[1].Length) )
          *v21 = 0;
        FsFltWil::Details::FreeUnicodeString(v21, v37);
        ExFreePoolWithTag(v21, 0);
      }
      if ( v32 )
      {
        if ( !LOBYTE(v32[1].Length) )
          *v32 = 0;
        FsFltWil::Details::FreeUnicodeString(v32, v37);
        ExFreePoolWithTag(v32, 0);
      }
      v38 = FileNameInformation;
      FileNameInformation = 0;
      if ( v38 )
        FltReleaseFileNameInformation(v38);
      return 3236757512LL;
    }
    v68 = 0;
    v67 = 0;
    *(_OWORD *)v66 = 0;
    v69 = 0;
    v70 = 0;
    *(_DWORD *)v66 = _mm_cvtsi128_si32((__m128i)0LL) | 3;
    *(_OWORD *)v75 = 0;
    memset(v76, 0, sizeof(v76));
    v33 = UnionFs::UfsStreamHandleCtx::TryLockOwningUnion(a5, (struct UnionFs::UfsUnionCtxWithRundown *)v75, a7);
    if ( v33 < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v33,
        (int)a7,
        (struct UnionFs::StackEventTracer *)0x685000F05D4LL,
        (unsigned __int64)"UnionFs::UnionFsFilter::GeneratePostCreateName",
        "PUSH: Inactive union",
        v62);
      FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v76, v39);
      if ( v76[16] )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v76[16] + 24LL))(v76[16]);
      if ( v75[1] )
        utl::_RefCountBase::_DecStrong(v75[1]);
      UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)v66);
      if ( v31 )
      {
        if ( !LOBYTE(v31[1].Length) )
          *v31 = 0;
        FsFltWil::Details::FreeUnicodeString(v31, v40);
        ExFreePoolWithTag(v31, 0);
      }
      if ( v21 )
      {
        if ( !LOBYTE(v21[1].Length) )
          *v21 = 0;
        FsFltWil::Details::FreeUnicodeString(v21, v40);
        ExFreePoolWithTag(v21, 0);
      }
      if ( v32 )
      {
        if ( !LOBYTE(v32[1].Length) )
          *v32 = 0;
        FsFltWil::Details::FreeUnicodeString(v32, v40);
        ExFreePoolWithTag(v32, 0);
      }
      v35 = FileNameInformation;
      FileNameInformation = 0;
      goto LABEL_66;
    }
    v64 = 0;
    OpenedPath = UnionFs::UfsStreamHandleCtx::GetOpenedPath(a5, &v64, a7);
    if ( OpenedPath < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)OpenedPath,
        (int)a7,
        (struct UnionFs::StackEventTracer *)0x67D000F05DDLL,
        (unsigned __int64)"UnionFs::UnionFsFilter::GeneratePostCreateName",
        "PUSH: Getting opened path",
        v62);
      v43 = (struct _UNICODE_STRING *)v64;
      if ( v64 )
      {
        if ( !*((_BYTE *)v64 + 16) )
          *(_OWORD *)v64 = 0;
        FsFltWil::Details::FreeUnicodeString(v43, v42);
        ExFreePoolWithTag(v43, 0);
      }
      FsFltWil::Details::ReleaseRundownProtectionCacheAware(
        (FsFltWil::Details *)v76,
        (struct FsFltWil::Details::RundownRefCacheAware *)v42);
      if ( v76[16] )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v76[16] + 24LL))(v76[16]);
      if ( v75[1] )
        utl::_RefCountBase::_DecStrong(v75[1]);
      UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)v66);
      if ( v31 )
      {
        if ( !LOBYTE(v31[1].Length) )
          *v31 = 0;
        FsFltWil::Details::FreeUnicodeString(v31, v44);
        ExFreePoolWithTag(v31, 0);
      }
      if ( v21 )
      {
        if ( !LOBYTE(v21[1].Length) )
          *v21 = 0;
        FsFltWil::Details::FreeUnicodeString(v21, v44);
        ExFreePoolWithTag(v21, 0);
      }
      if ( v32 )
      {
        if ( !LOBYTE(v32[1].Length) )
          *v32 = 0;
        FsFltWil::Details::FreeUnicodeString(v32, v44);
        ExFreePoolWithTag(v32, 0);
      }
      v45 = FileNameInformation;
      FileNameInformation = 0;
      if ( v45 )
        FltReleaseFileNameInformation(v45);
      return (unsigned int)OpenedPath;
    }
    if ( *((_DWORD *)v75[0] + 7) == 2 )
      v46 = *(_QWORD *)(*((_QWORD *)v75[0] + 4) + 16LL);
    else
      v46 = *((_QWORD *)UnionFs::g_FilterState + 10);
    v47 = (struct _UNICODE_STRING *)v64;
    v62 = v66;
    v33 = UnionFs::UfsPathCache::LookupEntryPriv(v46, ScratchInstance, v64, 0, 0);
    if ( v33 < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v33,
        (int)a7,
        (struct UnionFs::StackEventTracer *)0x681000F05E7LL,
        (unsigned __int64)"UnionFs::UnionFsFilter::GeneratePostCreateName",
        "PUSH: Path Cache lookup",
        v66);
      if ( v47 )
      {
        if ( !LOBYTE(v47[1].Length) )
          *v47 = 0;
        FsFltWil::Details::FreeUnicodeString(v47, v49);
        ExFreePoolWithTag(v47, 0);
      }
      FsFltWil::Details::ReleaseRundownProtectionCacheAware(
        (FsFltWil::Details *)v76,
        (struct FsFltWil::Details::RundownRefCacheAware *)v49);
      if ( v76[16] )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v76[16] + 24LL))(v76[16]);
      if ( v75[1] )
        utl::_RefCountBase::_DecStrong(v75[1]);
      UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)v66);
      goto LABEL_53;
    }
    if ( (_DWORD)v69 == 2 && (*(_DWORD *)&v66[4] != 1 || *(_WORD *)(v67 + 168) != 4) )
    {
      v64 = 0;
      v50 = v32;
      Source = *(UNICODE_STRING *)v70;
      v51 = **((_OWORD **)&v70 + 1);
      v73 = *v32;
      *(_OWORD *)P = v51;
      v53 = UnionFs::UfsPathName::AllocAndInitWithReplacedPathPrefix(
              (UnionFs::Rtl *)&v73,
              (struct _UNICODE_STRING *)P,
              &Source,
              &v64,
              (int)a7);
      if ( v53 < 0 )
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)v53,
          (int)a7,
          (struct UnionFs::StackEventTracer *)0x682000F05FALL,
          (unsigned __int64)"UnionFs::UnionFsFilter::GeneratePostCreateName",
          "PUSH: Replacing substring",
          v62);
        v55 = (struct _UNICODE_STRING *)v64;
        if ( v64 )
        {
          if ( !*((_BYTE *)v64 + 16) )
            *(_OWORD *)v64 = 0;
          FsFltWil::Details::FreeUnicodeString(v55, v54);
          ExFreePoolWithTag(v55, 0);
        }
        if ( v47 )
        {
          if ( !LOBYTE(v47[1].Length) )
            *v47 = 0;
          FsFltWil::Details::FreeUnicodeString(v47, v54);
          ExFreePoolWithTag(v47, 0);
        }
        FsFltWil::Details::ReleaseRundownProtectionCacheAware(
          (FsFltWil::Details *)v76,
          (struct FsFltWil::Details::RundownRefCacheAware *)v54);
        if ( v76[16] )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v76[16] + 24LL))(v76[16]);
        if ( v75[1] )
          utl::_RefCountBase::_DecStrong(v75[1]);
        UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)v66);
        if ( v31 )
        {
          if ( !LOBYTE(v31[1].Length) )
            *v31 = 0;
          FsFltWil::Details::FreeUnicodeString(v31, v56);
          ExFreePoolWithTag(v31, 0);
        }
        if ( v21 )
        {
          if ( !LOBYTE(v21[1].Length) )
            *v21 = 0;
          FsFltWil::Details::FreeUnicodeString(v21, v56);
          ExFreePoolWithTag(v21, 0);
        }
        if ( v32 )
        {
          if ( !LOBYTE(v32[1].Length) )
            *v32 = 0;
          FsFltWil::Details::FreeUnicodeString(v32, v56);
          ExFreePoolWithTag(v32, 0);
        }
        v57 = FileNameInformation;
        FileNameInformation = 0;
        if ( v57 )
          FltReleaseFileNameInformation(v57);
        return (unsigned int)v53;
      }
      v32 = (struct _UNICODE_STRING *)v64;
      if ( !LOBYTE(v50[1].Length) )
        *v50 = 0;
      FsFltWil::Details::FreeUnicodeString(v50, v52);
      ExFreePoolWithTag(v50, 0);
    }
    if ( v47 )
    {
      if ( !LOBYTE(v47[1].Length) )
        *v47 = 0;
      FsFltWil::Details::FreeUnicodeString(v47, v48);
      ExFreePoolWithTag(v47, 0);
    }
    FsFltWil::Details::ReleaseRundownProtectionCacheAware(
      (FsFltWil::Details *)v76,
      (struct FsFltWil::Details::RundownRefCacheAware *)v48);
    if ( v76[16] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v76[16] + 24LL))(v76[16]);
    if ( v75[1] )
      utl::_RefCountBase::_DecStrong(v75[1]);
    UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)v66);
    if ( v31 )
    {
      if ( !LOBYTE(v31[1].Length) )
        *v31 = 0;
      FsFltWil::Details::FreeUnicodeString(v31, v58);
      ExFreePoolWithTag(v31, 0);
    }
    if ( v21 )
    {
      if ( !LOBYTE(v21[1].Length) )
        *v21 = 0;
      FsFltWil::Details::FreeUnicodeString(v21, v58);
      ExFreePoolWithTag(v21, 0);
    }
  }
  LOBYTE(v16) = a8;
  v12 = UnionFs::UfsPathName::AsUnicodeString(v32, v71, a7, v16);
  if ( v12 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v12,
      (int)a7,
      (struct UnionFs::StackEventTracer *)0x683000F0603LL,
      (unsigned __int64)"UnionFs::UnionFsFilter::GeneratePostCreateName",
      "PUSH: Copying filePath to OutputName",
      v62);
    if ( v32 )
    {
      if ( !LOBYTE(v32[1].Length) )
        *v32 = 0;
      FsFltWil::Details::FreeUnicodeString(v32, v60);
      ExFreePoolWithTag(v32, 0);
    }
    goto LABEL_5;
  }
  if ( v32 )
  {
    if ( !LOBYTE(v32[1].Length) )
      *v32 = 0;
    FsFltWil::Details::FreeUnicodeString(v32, v59);
    ExFreePoolWithTag(v32, 0);
  }
  v61 = FileNameInformation;
  FileNameInformation = 0;
  if ( v61 )
    FltReleaseFileNameInformation(v61);
  return 0;
}

```

## disassembly

```asm
0x140036db8  mov     [rsp-8+arg_0], rbx
0x140036dbd  push    rbp
0x140036dbe  push    rsi
0x140036dbf  push    rdi
0x140036dc0  push    r12
0x140036dc2  push    r13
0x140036dc4  push    r14
0x140036dc6  push    r15
0x140036dc8  lea     rbp, [rsp-80h]
0x140036dcd  sub     rsp, 180h
0x140036dd4  mov     rax, cs:__security_cookie
0x140036ddb  xor     rax, rsp
0x140036dde  mov     [rbp+0B0h+var_38], rax
0x140036de2  mov     rax, [rbp+0B0h+arg_28]
0x140036de9  mov     ebx, r9d
0x140036dec  mov     r15, [rbp+0B0h+arg_20]
0x140036df3  mov     rsi, r8
0x140036df6  mov     r14, [rbp+0B0h+arg_30]
0x140036dfd  mov     rdi, rdx
0x140036e00  movzx   r13d, r9b
0x140036e04  mov     [rbp+0B0h+var_110], rax
0x140036e08  lea     eax, [r13-1]
0x140036e0c  cmp     eax, 1
0x140036e0f  jbe     short loc_140036E1D
0x140036e11  lea     rcx, aFltgetfilename; "(FltGetFileNameFormat(NameOptions) == F"...
0x140036e18  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140036e1d  xor     r12d, r12d
0x140036e20  mov     qword ptr [rbp+0B0h+var_F0+8], rsi
0x140036e24  mov     r9, r14
0x140036e27  mov     [rsp+1B0h+FileNameInformation], r12
0x140036e2c  lea     r8, [rsp+1B0h+FileNameInformation]
0x140036e31  mov     qword ptr [rbp+0B0h+var_F0], r12
0x140036e35  mov     edx, ebx
0x140036e37  mov     [rbp+0B0h+var_E0], rdi
0x140036e3b  lea     rcx, [rbp+0B0h+var_F0]
0x140036e3f  call    ?GetFileNameInformation@Utils@UnionFs@@YAJUNameInfoParams@12@KAEAV?$unique_ptr@U_FLT_FILE_NAME_INFORMATION@@U?$function_deleter@P6AXPEAU_FLT_FILE_NAME_INFORMATION@@@Z$1?FltReleaseFileNameInformation@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@@Z; UnionFs::Utils::GetFileNameInformation(UnionFs::Utils::NameInfoParams,ulong,wistd::unique_ptr<_FLT_FILE_NAME_INFORMATION,wil::function_deleter<void (*)(_FLT_FILE_NAME_INFORMATION *),&FltReleaseFileNameInformation(_FLT_FILE_NAME_INFORMATION *)>> &,UnionFs::StackEventTracer &)
0x140036e44  mov     ebx, eax
0x140036e46  test    eax, eax
0x140036e48  jns     short loc_140036E93
0x140036e4a  lea     rax, aPushGettingBac_2; "PUSH: Getting backing file name info"
0x140036e51  mov     r8, 14A000F059Bh; struct UnionFs::StackEventTracer *
0x140036e5b  lea     r9, aUnionfsUnionfs_1; "UnionFs::UnionFsFilter::GeneratePostCre"...
0x140036e62  mov     [rsp+1B0h+var_190], rax; char *
0x140036e67  mov     rdx, r14; int
0x140036e6a  mov     ecx, ebx; this
0x140036e6c  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140036e71  mov     rcx, [rsp+1B0h+FileNameInformation]; FileNameInformation
0x140036e76  mov     [rsp+1B0h+FileNameInformation], r12
0x140036e7b  test    rcx, rcx
0x140036e7e  jz      short loc_140036E8C
0x140036e80  call    cs:__imp_FltReleaseFileNameInformation
0x140036e87  nop     dword ptr [rax+rax+00h]
0x140036e8c  mov     eax, ebx
0x140036e8e  jmp     loc_140037A36
0x140036e93  mov     rcx, [rsp+1B0h+FileNameInformation]
0x140036e98  lea     rdx, [rsp+1B0h+P]
0x140036e9d  mov     r8, r14
0x140036ea0  mov     [rsp+1B0h+P], r12
0x140036ea5  call    ?AllocAndInit@UfsPathName@UnionFs@@SAJAEBU_FLT_FILE_NAME_INFORMATION@@AEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsPathName::AllocAndInit(_FLT_FILE_NAME_INFORMATION const &,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &,UnionFs::StackEventTracer &)
0x140036eaa  mov     edi, eax
0x140036eac  test    eax, eax
0x140036eae  jns     short loc_140036F28
0x140036eb0  lea     rax, aPushAllocingBa; "PUSH: Allocing backing file path"
0x140036eb7  mov     r8, 67F000F05A1h; struct UnionFs::StackEventTracer *
0x140036ec1  lea     r9, aUnionfsUnionfs_1; "UnionFs::UnionFsFilter::GeneratePostCre"...
0x140036ec8  mov     [rsp+1B0h+var_190], rax; char *
0x140036ecd  mov     rdx, r14; int
0x140036ed0  mov     ecx, edi; this
0x140036ed2  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140036ed7  mov     rbx, [rsp+1B0h+P]
0x140036edc  test    rbx, rbx
0x140036edf  jz      short loc_140036F06
0x140036ee1  cmp     [rbx+10h], r12b
0x140036ee5  jnz     short loc_140036EED
0x140036ee7  xorps   xmm0, xmm0
0x140036eea  movups  xmmword ptr [rbx], xmm0
0x140036eed  mov     rcx, rbx; UnicodeString
0x140036ef0  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140036ef5  xor     edx, edx; Tag
0x140036ef7  mov     rcx, rbx; P
0x140036efa  call    cs:__imp_ExFreePoolWithTag
0x140036f01  nop     dword ptr [rax+rax+00h]
0x140036f06  mov     rcx, [rsp+1B0h+FileNameInformation]; FileNameInformation
0x140036f0b  mov     [rsp+1B0h+FileNameInformation], r12
0x140036f10  test    rcx, rcx
0x140036f13  jz      short loc_140036F21
0x140036f15  call    cs:__imp_FltReleaseFileNameInformation
0x140036f1c  nop     dword ptr [rax+rax+00h]
0x140036f21  mov     eax, edi
0x140036f23  jmp     loc_140037A36
0x140036f28  mov     eax, [r15]
0x140036f2b  test    al, 20h
0x140036f2d  jnz     loc_140037974
0x140036f33  lea     rdx, [rbp+0B0h+Source]
0x140036f37  mov     rcx, r15
0x140036f3a  call    ?TryGetBackingLayer@UfsStreamHandleCtx@UnionFs@@QEBA?AV?$shared_ptr@VUfsLayerCtx@UnionFs@@@utl@@XZ; UnionFs::UfsStreamHandleCtx::TryGetBackingLayer(void)
0x140036f3f  mov     r8, r14
0x140036f42  mov     [rsp+1B0h+var_168], r12
0x140036f47  lea     rdx, [rsp+1B0h+var_168]
0x140036f4c  mov     rcx, [rax]
0x140036f4f  mov     rcx, [rcx+10h]; SourceString
0x140036f53  call    ?Copy@UfsPathName@UnionFs@@QEBAJAEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsPathName::Copy(utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &,UnionFs::StackEventTracer &)
0x140036f58  mov     edi, eax
0x140036f5a  test    eax, eax
0x140036f5c  jns     short loc_140036FB9
0x140036f5e  lea     rax, aPushDuplicatin_0; "PUSH: Duplicating layer root path"
0x140036f65  mov     r8, 5A7000D00C0h; struct UnionFs::StackEventTracer *
0x140036f6f  lea     r9, aUnionfsUfslaye_1; "UnionFs::UfsLayerCtx::GetNormalizedLaye"...
0x140036f76  mov     [rsp+1B0h+var_190], rax; char *
0x140036f7b  mov     rdx, r14; int
0x140036f7e  mov     ecx, edi; this
0x140036f80  mov     rbx, r12
0x140036f83  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140036f88  mov     rsi, [rsp+1B0h+var_168]
0x140036f8d  test    rsi, rsi
0x140036f90  jz      short loc_140036FC1
0x140036f92  cmp     [rsi+10h], r12b
0x140036f96  jnz     short loc_140036F9E
0x140036f98  xorps   xmm0, xmm0
0x140036f9b  movups  xmmword ptr [rsi], xmm0
0x140036f9e  mov     rcx, rsi; UnicodeString
0x140036fa1  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140036fa6  xor     edx, edx; Tag
0x140036fa8  mov     rcx, rsi; P
0x140036fab  call    cs:__imp_ExFreePoolWithTag
0x140036fb2  nop     dword ptr [rax+rax+00h]
0x140036fb7  jmp     short loc_140036FC1
0x140036fb9  mov     rbx, [rsp+1B0h+var_168]
0x140036fbe  mov     edi, r12d
0x140036fc1  mov     rcx, [rbp+0B0h+Source.Buffer]; this
0x140036fc5  test    rcx, rcx
0x140036fc8  jz      short loc_140036FCF
0x140036fca  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140036fcf  test    edi, edi
0x140036fd1  jns     short loc_14003702D
0x140036fd3  lea     rax, aPushGettingLay_0; "PUSH: Getting layer root path"
0x140036fda  mov     r8, 29D000F05ABh; struct UnionFs::StackEventTracer *
0x140036fe4  lea     r9, aUnionfsUnionfs_1; "UnionFs::UnionFsFilter::GeneratePostCre"...
0x140036feb  mov     [rsp+1B0h+var_190], rax; char *
0x140036ff0  mov     rdx, r14; int
0x140036ff3  mov     ecx, edi; this
0x140036ff5  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140036ffa  test    rbx, rbx
0x140036ffd  jz      loc_140036ED7
0x140037003  cmp     [rbx+10h], r12b
0x140037007  jnz     short loc_14003700F
0x140037009  xorps   xmm0, xmm0
0x14003700c  movups  xmmword ptr [rbx], xmm0
0x14003700f  mov     rcx, rbx; UnicodeString
0x140037012  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140037017  xor     edx, edx; Tag
0x140037019  mov     rcx, rbx; P
0x14003701c  call    cs:__imp_ExFreePoolWithTag
0x140037023  nop     dword ptr [rax+rax+00h]
0x140037028  jmp     loc_140036ED7
0x14003702d  mov     [rsp+1B0h+var_168], r12
0x140037032  mov     r8, r14
0x140037035  lea     rdx, [rsp+1B0h+var_168]
0x14003703a  mov     rcx, r15
0x14003703d  cmp     r13d, 1
0x140037041  jnz     loc_140037127
0x140037047  call    ?GetNormalizedScratchRootPath@UfsStreamHandleCtx@UnionFs@@QEBAJAEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsStreamHandleCtx::GetNormalizedScratchRootPath(utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &,UnionFs::StackEventTracer &)
0x14003704c  mov     esi, eax
0x14003704e  test    eax, eax
0x140037050  jns     loc_140037148
0x140037056  lea     rax, aPushGettingNor; "PUSH: Getting normalized scratch root p"...
0x14003705d  mov     r8, 1B8000F05B3h; struct UnionFs::StackEventTracer *
0x140037067  lea     r9, aUnionfsUnionfs_1; "UnionFs::UnionFsFilter::GeneratePostCre"...
0x14003706e  mov     [rsp+1B0h+var_190], rax; char *
0x140037073  mov     rdx, r14; int
0x140037076  mov     ecx, esi; this
0x140037078  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14003707d  mov     rdi, [rsp+1B0h+var_168]
0x140037082  test    rdi, rdi
0x140037085  jz      short loc_1400370AC
0x140037087  cmp     [rdi+10h], r12b
0x14003708b  jnz     short loc_140037093
0x14003708d  xorps   xmm0, xmm0
0x140037090  movups  xmmword ptr [rdi], xmm0
0x140037093  mov     rcx, rdi; UnicodeString
0x140037096  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14003709b  xor     edx, edx; Tag
0x14003709d  mov     rcx, rdi; P
0x1400370a0  call    cs:__imp_ExFreePoolWithTag
0x1400370a7  nop     dword ptr [rax+rax+00h]
0x1400370ac  test    rbx, rbx
0x1400370af  jz      short loc_1400370D6
0x1400370b1  cmp     [rbx+10h], r12b
0x1400370b5  jnz     short loc_1400370BD
0x1400370b7  xorps   xmm0, xmm0
0x1400370ba  movups  xmmword ptr [rbx], xmm0
0x1400370bd  mov     rcx, rbx; UnicodeString
0x1400370c0  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x1400370c5  xor     edx, edx; Tag
0x1400370c7  mov     rcx, rbx; P
0x1400370ca  call    cs:__imp_ExFreePoolWithTag
0x1400370d1  nop     dword ptr [rax+rax+00h]
0x1400370d6  mov     rbx, [rsp+1B0h+P]
0x1400370db  test    rbx, rbx
0x1400370de  jz      short loc_140037105
0x1400370e0  cmp     [rbx+10h], r12b
0x1400370e4  jnz     short loc_1400370EC
0x1400370e6  xorps   xmm0, xmm0
0x1400370e9  movups  xmmword ptr [rbx], xmm0
0x1400370ec  mov     rcx, rbx; UnicodeString
0x1400370ef  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x1400370f4  xor     edx, edx; Tag
0x1400370f6  mov     rcx, rbx; P
0x1400370f9  call    cs:__imp_ExFreePoolWithTag
0x140037100  nop     dword ptr [rax+rax+00h]
0x140037105  mov     rcx, [rsp+1B0h+FileNameInformation]; FileNameInformation
0x14003710a  mov     [rsp+1B0h+FileNameInformation], r12
0x14003710f  test    rcx, rcx
0x140037112  jz      short loc_140037120
0x140037114  call    cs:__imp_FltReleaseFileNameInformation
0x14003711b  nop     dword ptr [rax+rax+00h]
0x140037120  mov     eax, esi
0x140037122  jmp     loc_140037A36
0x140037127  call    ?GetOpenedScratchRootPath@UfsStreamHandleCtx@UnionFs@@QEBAJAEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsStreamHandleCtx::GetOpenedScratchRootPath(utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &,UnionFs::StackEventTracer &)
0x14003712c  mov     esi, eax
0x14003712e  test    eax, eax
0x140037130  jns     short loc_140037148
0x140037132  lea     rax, aPushGettingOpe_2; "PUSH: Getting opened scratch root path"
0x140037139  mov     r8, 67C000F05BAh
0x140037143  jmp     loc_140037067
0x140037148  mov     rsi, [rsp+1B0h+var_168]
0x14003714d  mov     r9, r14; struct UnionFs::StackEventTracer *
0x140037150  mov     rdi, [rsp+1B0h+P]
0x140037155  mov     r8, rsi; struct UnionFs::UfsPathName *
0x140037158  mov     rcx, rdi; this
0x14003715b  mov     rdx, rbx; struct UnionFs::UfsPathName *
0x14003715e  call    ?ReplacePathPrefix@UfsPathName@UnionFs@@QEAAJAEBV12@0AEAVStackEventTracer@2@@Z; UnionFs::UfsPathName::ReplacePathPrefix(UnionFs::UfsPathName const &,UnionFs::UfsPathName const &,UnionFs::StackEventTracer &)
0x140037163  xor     r13d, r13d
0x140037166  mov     r12d, eax
0x140037169  test    eax, eax
0x14003716b  jns     loc_14003723A
0x140037171  lea     rax, aPushReplacingL_0; "PUSH: Replacing layer with scratch root"
0x140037178  mov     r8, 14C000F05C0h; struct UnionFs::StackEventTracer *
0x140037182  lea     r9, aUnionfsUnionfs_1; "UnionFs::UnionFsFilter::GeneratePostCre"...
0x140037189  mov     [rsp+1B0h+var_190], rax; char *
0x14003718e  mov     rdx, r14; int
0x140037191  mov     ecx, r12d; this
0x140037194  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140037199  test    rsi, rsi
0x14003719c  jz      short loc_1400371C3
0x14003719e  cmp     [rsi+10h], r13b
0x1400371a2  jnz     short loc_1400371AA
0x1400371a4  xorps   xmm0, xmm0
0x1400371a7  movups  xmmword ptr [rsi], xmm0
0x1400371aa  mov     rcx, rsi; UnicodeString
0x1400371ad  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x1400371b2  xor     edx, edx; Tag
0x1400371b4  mov     rcx, rsi; P
0x1400371b7  call    cs:__imp_ExFreePoolWithTag
0x1400371be  nop     dword ptr [rax+rax+00h]
0x1400371c3  test    rbx, rbx
0x1400371c6  jz      short loc_1400371ED
0x1400371c8  cmp     [rbx+10h], r13b
0x1400371cc  jnz     short loc_1400371D4
0x1400371ce  xorps   xmm0, xmm0
0x1400371d1  movups  xmmword ptr [rbx], xmm0
0x1400371d4  mov     rcx, rbx; UnicodeString
0x1400371d7  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x1400371dc  xor     edx, edx; Tag
0x1400371de  mov     rcx, rbx; P
0x1400371e1  call    cs:__imp_ExFreePoolWithTag
0x1400371e8  nop     dword ptr [rax+rax+00h]
0x1400371ed  test    rdi, rdi
0x1400371f0  jz      short loc_140037217
0x1400371f2  cmp     [rdi+10h], r13b
0x1400371f6  jnz     short loc_1400371FE
0x1400371f8  xorps   xmm0, xmm0
0x1400371fb  movups  xmmword ptr [rdi], xmm0
0x1400371fe  mov     rcx, rdi; UnicodeString
0x140037201  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140037206  xor     edx, edx; Tag
0x140037208  mov     rcx, rdi; P
0x14003720b  call    cs:__imp_ExFreePoolWithTag
0x140037212  nop     dword ptr [rax+rax+00h]
0x140037217  mov     rcx, [rsp+1B0h+FileNameInformation]; FileNameInformation
0x14003721c  mov     [rsp+1B0h+FileNameInformation], r13
0x140037221  test    rcx, rcx
0x140037224  jz      short loc_140037232
0x140037226  call    cs:__imp_FltReleaseFileNameInformation
0x14003722d  nop     dword ptr [rax+rax+00h]
0x140037232  mov     eax, r12d
0x140037235  jmp     loc_140037A36
0x14003723a  mov     rcx, r15; this
0x14003723d  call    ?TryGetScratchInstance@UfsStreamHandleCtx@UnionFs@@QEBAPEBU_FLT_INSTANCE@@XZ; UnionFs::UfsStreamHandleCtx::TryGetScratchInstance(void)
0x140037242  xor     r12d, r12d
0x140037245  mov     r13, rax
0x140037248  test    rax, rax
0x14003724b  jnz     loc_140037320
0x140037251  mov     rdx, r14; int
0x140037254  lea     rax, aOriginScratchI; "ORIGIN: Scratch instance not available"
0x14003725b  mov     r14d, 0C0ED0008h
0x140037261  mov     [rsp+1B0h+var_190], rax; char *
0x140037266  mov     ecx, r14d; this
0x140037269  lea     r9, aUnionfsUnionfs_1; "UnionFs::UnionFsFilter::GeneratePostCre"...
0x140037270  mov     r8, 680000F05C7h; struct UnionFs::StackEventTracer *
  ... truncated ...
```
