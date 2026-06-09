# UnionFs::UnionFsFilter::GeneratePostCreateName(_FLT_INSTANCE const &,_FILE_OBJECT const &,ulong,UnionFs::UfsStreamHandleCtx const &,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0> &,UnionFs::StackEventTracer &,bool)

- ea: `0x140036c78`
- end: `0x14003791e`
- name: `?GeneratePostCreateName@UnionFsFilter@UnionFs@@QEAAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@KAEBVUfsStreamHandleCtx@2@AEAV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@AEAVStackEventTracer@2@_N@Z`
- size: `3238`
- prototype: `__int64 __fastcall(int, int, int, int, UnionFs::UfsStreamHandleCtx *, __int64, struct UnionFs::StackEventTracer *, char)`
- caller_count: `2`
- callee_count: `24`
- tags: `file_ops, reparse_path, installer_update, broker_com_uri`

## callers

- `0x1400356bc`
- `0x140037924`

## callees

- `0x14000f7fc`
- `0x140011198`
- `0x1400288f0`
- `0x140028a9c`
- `0x140028ba8`
- `0x14002ac00`
- `0x14002ac7c`
- `0x14002ade4`
- `0x140036c78`
- `0x14003ce70`
- `0x14004397c`
- `0x140043ef4`
- `0x14004452c`
- `0x140044748`
- `0x140044c04`
- `0x140056ac4`
- `0x140056afc`
- `0x14006e1a4`
- `0x140079c48`
- `0x140079df4`
- `0x14007af90`
- `0x14007b7d0`
- `0x14007b8b0`
- `0x14007bc00`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140036dba`
- `ntoskrnl!ExFreePoolWithTag` at `0x140036e6b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140036edc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140036f60`
- `ntoskrnl!ExFreePoolWithTag` at `0x140036f8a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140036fb9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037077`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400370a1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400370cb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003715d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037187`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400371b1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400372c5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400372ef`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037319`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400373a3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037403`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003742d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037457`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037526`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003763e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037669`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400376c9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400376f3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003771d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003776e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003779c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400377fc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037826`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003789e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400378cd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140036dba`
- `ntoskrnl!ExFreePoolWithTag` at `0x140036e6b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140036edc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140036f60`
- `ntoskrnl!ExFreePoolWithTag` at `0x140036f8a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140036fb9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037077`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400370a1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400370cb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003715d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037187`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400371b1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400372c5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400372ef`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037319`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400373a3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037403`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003742d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037457`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037526`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003763e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037669`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400376c9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400376f3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003771d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003776e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003779c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400377fc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037826`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003789e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400378cd`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140036d40`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140036dd5`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140036fd4`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400370e6`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400371cc`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140037472`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140037738`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400378e8`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140036d40`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140036dd5`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140036fd4`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400370e6`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400371cc`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140037472`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140037738`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400378e8`

## string_xrefs

- `0x140037357`: `PUSH: Getting opened path`
- `0x140036e1e`: `PUSH: Duplicating layer root path`
- `0x140036e2f`: `UnionFs::UfsLayerCtx::GetNormalizedLayerRootPath`
- `0x140036d1b`: `UnionFs::UnionFsFilter::GeneratePostCreateName`
- `0x140036d81`: `UnionFs::UnionFsFilter::GeneratePostCreateName`
- `0x140036ea4`: `UnionFs::UnionFsFilter::GeneratePostCreateName`
- `0x140036f27`: `UnionFs::UnionFsFilter::GeneratePostCreateName`
- `0x140037042`: `UnionFs::UnionFsFilter::GeneratePostCreateName`
- `0x140037129`: `UnionFs::UnionFsFilter::GeneratePostCreateName`
- `0x140037257`: `UnionFs::UnionFsFilter::GeneratePostCreateName`
- `0x140037368`: `UnionFs::UnionFsFilter::GeneratePostCreateName`
- `0x1400374f0`: `UnionFs::UnionFsFilter::GeneratePostCreateName`
- `0x140037600`: `UnionFs::UnionFsFilter::GeneratePostCreateName`
- `0x140037866`: `UnionFs::UnionFsFilter::GeneratePostCreateName`
- `0x140036cd1`: `(FltGetFileNameFormat(NameOptions) == FLT_FILE_NAME_OPENED) || (FltGetFileNameFormat(NameOptions) == FLT_FILE_NAME_NORMALIZED)`
- `0x140036d70`: `PUSH: Allocing backing file path`
- `0x140036e93`: `PUSH: Getting layer root path`
- `0x140036f16`: `PUSH: Getting normalized scratch root path`
- `0x140036ff2`: `PUSH: Getting opened scratch root path`
- `0x1400374df`: `PUSH: Path Cache lookup`
- `0x140037855`: `PUSH: Copying filePath to OutputName`

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
      (struct UnionFs::StackEventTracer *)0x14A000F059ALL,
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
      (struct UnionFs::StackEventTracer *)0x67F000F05A0LL,
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
        (struct UnionFs::StackEventTracer *)0x29D000F05AALL,
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
        v26 = 0x1B8000F05B2LL;
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
        v26 = 0x67C000F05B9LL;
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
        (struct UnionFs::StackEventTracer *)0x14C000F05BFLL,
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
        (struct UnionFs::StackEventTracer *)0x680000F05C6LL,
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
        (struct UnionFs::StackEventTracer *)0x685000F05D3LL,
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
        (struct UnionFs::StackEventTracer *)0x67D000F05DCLL,
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
        (struct UnionFs::StackEventTracer *)0x681000F05E6LL,
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
    if ( (_DWORD)v69 == 2 && (*(_DWORD *)&v66[4] != 1 || *(_WORD *)(v67 + 160) != 4) )
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
          (struct UnionFs::StackEventTracer *)0x682000F05F9LL,
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
      (struct UnionFs::StackEventTracer *)0x683000F0602LL,
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
0x140036c78  mov     [rsp-8+arg_0], rbx
0x140036c7d  push    rbp
0x140036c7e  push    rsi
0x140036c7f  push    rdi
0x140036c80  push    r12
0x140036c82  push    r13
0x140036c84  push    r14
0x140036c86  push    r15
0x140036c88  lea     rbp, [rsp-80h]
0x140036c8d  sub     rsp, 180h
0x140036c94  mov     rax, cs:__security_cookie
0x140036c9b  xor     rax, rsp
0x140036c9e  mov     [rbp+0B0h+var_38], rax
0x140036ca2  mov     rax, [rbp+0B0h+arg_28]
0x140036ca9  mov     ebx, r9d
0x140036cac  mov     r15, [rbp+0B0h+arg_20]
0x140036cb3  mov     rsi, r8
0x140036cb6  mov     r14, [rbp+0B0h+arg_30]
0x140036cbd  mov     rdi, rdx
0x140036cc0  movzx   r13d, r9b
0x140036cc4  mov     [rbp+0B0h+var_110], rax
0x140036cc8  lea     eax, [r13-1]
0x140036ccc  cmp     eax, 1
0x140036ccf  jbe     short loc_140036CDD
0x140036cd1  lea     rcx, aFltgetfilename; "(FltGetFileNameFormat(NameOptions) == F"...
0x140036cd8  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140036cdd  xor     r12d, r12d
0x140036ce0  mov     qword ptr [rbp+0B0h+var_F0+8], rsi
0x140036ce4  mov     r9, r14
0x140036ce7  mov     [rsp+1B0h+FileNameInformation], r12
0x140036cec  lea     r8, [rsp+1B0h+FileNameInformation]
0x140036cf1  mov     qword ptr [rbp+0B0h+var_F0], r12
0x140036cf5  mov     edx, ebx
0x140036cf7  mov     [rbp+0B0h+var_E0], rdi
0x140036cfb  lea     rcx, [rbp+0B0h+var_F0]
0x140036cff  call    ?GetFileNameInformation@Utils@UnionFs@@YAJUNameInfoParams@12@KAEAV?$unique_ptr@U_FLT_FILE_NAME_INFORMATION@@U?$function_deleter@P6AXPEAU_FLT_FILE_NAME_INFORMATION@@@Z$1?FltReleaseFileNameInformation@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@@Z; UnionFs::Utils::GetFileNameInformation(UnionFs::Utils::NameInfoParams,ulong,wistd::unique_ptr<_FLT_FILE_NAME_INFORMATION,wil::function_deleter<void (*)(_FLT_FILE_NAME_INFORMATION *),&FltReleaseFileNameInformation(_FLT_FILE_NAME_INFORMATION *)>> &,UnionFs::StackEventTracer &)
0x140036d04  mov     ebx, eax
0x140036d06  test    eax, eax
0x140036d08  jns     short loc_140036D53
0x140036d0a  lea     rax, aPushGettingBac_1; "PUSH: Getting backing file name info"
0x140036d11  mov     r8, 14A000F059Ah; struct UnionFs::StackEventTracer *
0x140036d1b  lea     r9, aUnionfsUnionfs_1; "UnionFs::UnionFsFilter::GeneratePostCre"...
0x140036d22  mov     [rsp+1B0h+var_190], rax; char *
0x140036d27  mov     rdx, r14; int
0x140036d2a  mov     ecx, ebx; this
0x140036d2c  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140036d31  mov     rcx, [rsp+1B0h+FileNameInformation]; FileNameInformation
0x140036d36  mov     [rsp+1B0h+FileNameInformation], r12
0x140036d3b  test    rcx, rcx
0x140036d3e  jz      short loc_140036D4C
0x140036d40  call    cs:__imp_FltReleaseFileNameInformation
0x140036d47  nop     dword ptr [rax+rax+00h]
0x140036d4c  mov     eax, ebx
0x140036d4e  jmp     loc_1400378F6
0x140036d53  mov     rcx, [rsp+1B0h+FileNameInformation]
0x140036d58  lea     rdx, [rsp+1B0h+P]
0x140036d5d  mov     r8, r14
0x140036d60  mov     [rsp+1B0h+P], r12
0x140036d65  call    ?AllocAndInit@UfsPathName@UnionFs@@SAJAEBU_FLT_FILE_NAME_INFORMATION@@AEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsPathName::AllocAndInit(_FLT_FILE_NAME_INFORMATION const &,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &,UnionFs::StackEventTracer &)
0x140036d6a  mov     edi, eax
0x140036d6c  test    eax, eax
0x140036d6e  jns     short loc_140036DE8
0x140036d70  lea     rax, aPushAllocingBa; "PUSH: Allocing backing file path"
0x140036d77  mov     r8, 67F000F05A0h; struct UnionFs::StackEventTracer *
0x140036d81  lea     r9, aUnionfsUnionfs_1; "UnionFs::UnionFsFilter::GeneratePostCre"...
0x140036d88  mov     [rsp+1B0h+var_190], rax; char *
0x140036d8d  mov     rdx, r14; int
0x140036d90  mov     ecx, edi; this
0x140036d92  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140036d97  mov     rbx, [rsp+1B0h+P]
0x140036d9c  test    rbx, rbx
0x140036d9f  jz      short loc_140036DC6
0x140036da1  cmp     [rbx+10h], r12b
0x140036da5  jnz     short loc_140036DAD
0x140036da7  xorps   xmm0, xmm0
0x140036daa  movups  xmmword ptr [rbx], xmm0
0x140036dad  mov     rcx, rbx; UnicodeString
0x140036db0  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140036db5  xor     edx, edx; Tag
0x140036db7  mov     rcx, rbx; P
0x140036dba  call    cs:__imp_ExFreePoolWithTag
0x140036dc1  nop     dword ptr [rax+rax+00h]
0x140036dc6  mov     rcx, [rsp+1B0h+FileNameInformation]; FileNameInformation
0x140036dcb  mov     [rsp+1B0h+FileNameInformation], r12
0x140036dd0  test    rcx, rcx
0x140036dd3  jz      short loc_140036DE1
0x140036dd5  call    cs:__imp_FltReleaseFileNameInformation
0x140036ddc  nop     dword ptr [rax+rax+00h]
0x140036de1  mov     eax, edi
0x140036de3  jmp     loc_1400378F6
0x140036de8  mov     eax, [r15]
0x140036deb  test    al, 20h
0x140036ded  jnz     loc_140037834
0x140036df3  lea     rdx, [rbp+0B0h+Source]
0x140036df7  mov     rcx, r15
0x140036dfa  call    ?TryGetBackingLayer@UfsStreamHandleCtx@UnionFs@@QEBA?AV?$shared_ptr@VUfsLayerCtx@UnionFs@@@utl@@XZ; UnionFs::UfsStreamHandleCtx::TryGetBackingLayer(void)
0x140036dff  mov     r8, r14
0x140036e02  mov     [rsp+1B0h+var_168], r12
0x140036e07  lea     rdx, [rsp+1B0h+var_168]
0x140036e0c  mov     rcx, [rax]
0x140036e0f  mov     rcx, [rcx+10h]; SourceString
0x140036e13  call    ?Copy@UfsPathName@UnionFs@@QEBAJAEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsPathName::Copy(utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &,UnionFs::StackEventTracer &)
0x140036e18  mov     edi, eax
0x140036e1a  test    eax, eax
0x140036e1c  jns     short loc_140036E79
0x140036e1e  lea     rax, aPushDuplicatin_0; "PUSH: Duplicating layer root path"
0x140036e25  mov     r8, 5A7000D00C0h; struct UnionFs::StackEventTracer *
0x140036e2f  lea     r9, aUnionfsUfslaye_1; "UnionFs::UfsLayerCtx::GetNormalizedLaye"...
0x140036e36  mov     [rsp+1B0h+var_190], rax; char *
0x140036e3b  mov     rdx, r14; int
0x140036e3e  mov     ecx, edi; this
0x140036e40  mov     rbx, r12
0x140036e43  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140036e48  mov     rsi, [rsp+1B0h+var_168]
0x140036e4d  test    rsi, rsi
0x140036e50  jz      short loc_140036E81
0x140036e52  cmp     [rsi+10h], r12b
0x140036e56  jnz     short loc_140036E5E
0x140036e58  xorps   xmm0, xmm0
0x140036e5b  movups  xmmword ptr [rsi], xmm0
0x140036e5e  mov     rcx, rsi; UnicodeString
0x140036e61  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140036e66  xor     edx, edx; Tag
0x140036e68  mov     rcx, rsi; P
0x140036e6b  call    cs:__imp_ExFreePoolWithTag
0x140036e72  nop     dword ptr [rax+rax+00h]
0x140036e77  jmp     short loc_140036E81
0x140036e79  mov     rbx, [rsp+1B0h+var_168]
0x140036e7e  mov     edi, r12d
0x140036e81  mov     rcx, [rbp+0B0h+Source.Buffer]; this
0x140036e85  test    rcx, rcx
0x140036e88  jz      short loc_140036E8F
0x140036e8a  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140036e8f  test    edi, edi
0x140036e91  jns     short loc_140036EED
0x140036e93  lea     rax, aPushGettingLay_0; "PUSH: Getting layer root path"
0x140036e9a  mov     r8, 29D000F05AAh; struct UnionFs::StackEventTracer *
0x140036ea4  lea     r9, aUnionfsUnionfs_1; "UnionFs::UnionFsFilter::GeneratePostCre"...
0x140036eab  mov     [rsp+1B0h+var_190], rax; char *
0x140036eb0  mov     rdx, r14; int
0x140036eb3  mov     ecx, edi; this
0x140036eb5  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140036eba  test    rbx, rbx
0x140036ebd  jz      loc_140036D97
0x140036ec3  cmp     [rbx+10h], r12b
0x140036ec7  jnz     short loc_140036ECF
0x140036ec9  xorps   xmm0, xmm0
0x140036ecc  movups  xmmword ptr [rbx], xmm0
0x140036ecf  mov     rcx, rbx; UnicodeString
0x140036ed2  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140036ed7  xor     edx, edx; Tag
0x140036ed9  mov     rcx, rbx; P
0x140036edc  call    cs:__imp_ExFreePoolWithTag
0x140036ee3  nop     dword ptr [rax+rax+00h]
0x140036ee8  jmp     loc_140036D97
0x140036eed  mov     [rsp+1B0h+var_168], r12
0x140036ef2  mov     r8, r14
0x140036ef5  lea     rdx, [rsp+1B0h+var_168]
0x140036efa  mov     rcx, r15
0x140036efd  cmp     r13d, 1
0x140036f01  jnz     loc_140036FE7
0x140036f07  call    ?GetNormalizedScratchRootPath@UfsStreamHandleCtx@UnionFs@@QEBAJAEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsStreamHandleCtx::GetNormalizedScratchRootPath(utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &,UnionFs::StackEventTracer &)
0x140036f0c  mov     esi, eax
0x140036f0e  test    eax, eax
0x140036f10  jns     loc_140037008
0x140036f16  lea     rax, aPushGettingNor; "PUSH: Getting normalized scratch root p"...
0x140036f1d  mov     r8, 1B8000F05B2h; struct UnionFs::StackEventTracer *
0x140036f27  lea     r9, aUnionfsUnionfs_1; "UnionFs::UnionFsFilter::GeneratePostCre"...
0x140036f2e  mov     [rsp+1B0h+var_190], rax; char *
0x140036f33  mov     rdx, r14; int
0x140036f36  mov     ecx, esi; this
0x140036f38  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140036f3d  mov     rdi, [rsp+1B0h+var_168]
0x140036f42  test    rdi, rdi
0x140036f45  jz      short loc_140036F6C
0x140036f47  cmp     [rdi+10h], r12b
0x140036f4b  jnz     short loc_140036F53
0x140036f4d  xorps   xmm0, xmm0
0x140036f50  movups  xmmword ptr [rdi], xmm0
0x140036f53  mov     rcx, rdi; UnicodeString
0x140036f56  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140036f5b  xor     edx, edx; Tag
0x140036f5d  mov     rcx, rdi; P
0x140036f60  call    cs:__imp_ExFreePoolWithTag
0x140036f67  nop     dword ptr [rax+rax+00h]
0x140036f6c  test    rbx, rbx
0x140036f6f  jz      short loc_140036F96
0x140036f71  cmp     [rbx+10h], r12b
0x140036f75  jnz     short loc_140036F7D
0x140036f77  xorps   xmm0, xmm0
0x140036f7a  movups  xmmword ptr [rbx], xmm0
0x140036f7d  mov     rcx, rbx; UnicodeString
0x140036f80  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140036f85  xor     edx, edx; Tag
0x140036f87  mov     rcx, rbx; P
0x140036f8a  call    cs:__imp_ExFreePoolWithTag
0x140036f91  nop     dword ptr [rax+rax+00h]
0x140036f96  mov     rbx, [rsp+1B0h+P]
0x140036f9b  test    rbx, rbx
0x140036f9e  jz      short loc_140036FC5
0x140036fa0  cmp     [rbx+10h], r12b
0x140036fa4  jnz     short loc_140036FAC
0x140036fa6  xorps   xmm0, xmm0
0x140036fa9  movups  xmmword ptr [rbx], xmm0
0x140036fac  mov     rcx, rbx; UnicodeString
0x140036faf  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140036fb4  xor     edx, edx; Tag
0x140036fb6  mov     rcx, rbx; P
0x140036fb9  call    cs:__imp_ExFreePoolWithTag
0x140036fc0  nop     dword ptr [rax+rax+00h]
0x140036fc5  mov     rcx, [rsp+1B0h+FileNameInformation]; FileNameInformation
0x140036fca  mov     [rsp+1B0h+FileNameInformation], r12
0x140036fcf  test    rcx, rcx
0x140036fd2  jz      short loc_140036FE0
0x140036fd4  call    cs:__imp_FltReleaseFileNameInformation
0x140036fdb  nop     dword ptr [rax+rax+00h]
0x140036fe0  mov     eax, esi
0x140036fe2  jmp     loc_1400378F6
0x140036fe7  call    ?GetOpenedScratchRootPath@UfsStreamHandleCtx@UnionFs@@QEBAJAEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsStreamHandleCtx::GetOpenedScratchRootPath(utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &,UnionFs::StackEventTracer &)
0x140036fec  mov     esi, eax
0x140036fee  test    eax, eax
0x140036ff0  jns     short loc_140037008
0x140036ff2  lea     rax, aPushGettingOpe_2; "PUSH: Getting opened scratch root path"
0x140036ff9  mov     r8, 67C000F05B9h
0x140037003  jmp     loc_140036F27
0x140037008  mov     rsi, [rsp+1B0h+var_168]
0x14003700d  mov     r9, r14; struct UnionFs::StackEventTracer *
0x140037010  mov     rdi, [rsp+1B0h+P]
0x140037015  mov     r8, rsi; struct UnionFs::UfsPathName *
0x140037018  mov     rcx, rdi; this
0x14003701b  mov     rdx, rbx; struct UnionFs::UfsPathName *
0x14003701e  call    ?ReplacePathPrefix@UfsPathName@UnionFs@@QEAAJAEBV12@0AEAVStackEventTracer@2@@Z; UnionFs::UfsPathName::ReplacePathPrefix(UnionFs::UfsPathName const &,UnionFs::UfsPathName const &,UnionFs::StackEventTracer &)
0x140037023  xor     r13d, r13d
0x140037026  mov     r12d, eax
0x140037029  test    eax, eax
0x14003702b  jns     loc_1400370FA
0x140037031  lea     rax, aPushReplacingL_0; "PUSH: Replacing layer with scratch root"
0x140037038  mov     r8, 14C000F05BFh; struct UnionFs::StackEventTracer *
0x140037042  lea     r9, aUnionfsUnionfs_1; "UnionFs::UnionFsFilter::GeneratePostCre"...
0x140037049  mov     [rsp+1B0h+var_190], rax; char *
0x14003704e  mov     rdx, r14; int
0x140037051  mov     ecx, r12d; this
0x140037054  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140037059  test    rsi, rsi
0x14003705c  jz      short loc_140037083
0x14003705e  cmp     [rsi+10h], r13b
0x140037062  jnz     short loc_14003706A
0x140037064  xorps   xmm0, xmm0
0x140037067  movups  xmmword ptr [rsi], xmm0
0x14003706a  mov     rcx, rsi; UnicodeString
0x14003706d  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140037072  xor     edx, edx; Tag
0x140037074  mov     rcx, rsi; P
0x140037077  call    cs:__imp_ExFreePoolWithTag
0x14003707e  nop     dword ptr [rax+rax+00h]
0x140037083  test    rbx, rbx
0x140037086  jz      short loc_1400370AD
0x140037088  cmp     [rbx+10h], r13b
0x14003708c  jnz     short loc_140037094
0x14003708e  xorps   xmm0, xmm0
0x140037091  movups  xmmword ptr [rbx], xmm0
0x140037094  mov     rcx, rbx; UnicodeString
0x140037097  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14003709c  xor     edx, edx; Tag
0x14003709e  mov     rcx, rbx; P
0x1400370a1  call    cs:__imp_ExFreePoolWithTag
0x1400370a8  nop     dword ptr [rax+rax+00h]
0x1400370ad  test    rdi, rdi
0x1400370b0  jz      short loc_1400370D7
0x1400370b2  cmp     [rdi+10h], r13b
0x1400370b6  jnz     short loc_1400370BE
0x1400370b8  xorps   xmm0, xmm0
0x1400370bb  movups  xmmword ptr [rdi], xmm0
0x1400370be  mov     rcx, rdi; UnicodeString
0x1400370c1  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x1400370c6  xor     edx, edx; Tag
0x1400370c8  mov     rcx, rdi; P
0x1400370cb  call    cs:__imp_ExFreePoolWithTag
0x1400370d2  nop     dword ptr [rax+rax+00h]
0x1400370d7  mov     rcx, [rsp+1B0h+FileNameInformation]; FileNameInformation
0x1400370dc  mov     [rsp+1B0h+FileNameInformation], r13
0x1400370e1  test    rcx, rcx
0x1400370e4  jz      short loc_1400370F2
0x1400370e6  call    cs:__imp_FltReleaseFileNameInformation
0x1400370ed  nop     dword ptr [rax+rax+00h]
0x1400370f2  mov     eax, r12d
0x1400370f5  jmp     loc_1400378F6
0x1400370fa  mov     rcx, r15; this
0x1400370fd  call    ?TryGetScratchInstance@UfsStreamHandleCtx@UnionFs@@QEBAPEBU_FLT_INSTANCE@@XZ; UnionFs::UfsStreamHandleCtx::TryGetScratchInstance(void)
0x140037102  xor     r12d, r12d
0x140037105  mov     r13, rax
0x140037108  test    rax, rax
0x14003710b  jnz     loc_1400371E0
0x140037111  mov     rdx, r14; int
0x140037114  lea     rax, aOriginScratchI; "ORIGIN: Scratch instance not available"
0x14003711b  mov     r14d, 0C0ED0008h
0x140037121  mov     [rsp+1B0h+var_190], rax; char *
0x140037126  mov     ecx, r14d; this
0x140037129  lea     r9, aUnionfsUnionfs_1; "UnionFs::UnionFsFilter::GeneratePostCre"...
0x140037130  mov     r8, 680000F05C6h; struct UnionFs::StackEventTracer *
  ... truncated ...
```
