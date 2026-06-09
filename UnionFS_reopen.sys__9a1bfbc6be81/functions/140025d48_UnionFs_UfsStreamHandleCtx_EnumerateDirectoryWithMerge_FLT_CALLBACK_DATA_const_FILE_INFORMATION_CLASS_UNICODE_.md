# UnionFs::UfsStreamHandleCtx::EnumerateDirectoryWithMerge(_FLT_CALLBACK_DATA const &,_FILE_INFORMATION_CLASS,_UNICODE_STRING const &,ulong,uchar,UnionFs::EnumerateDirResults &,UnionFs::StackEventTracer &,bool)

- ea: `0x140025d48`
- end: `0x1400266f2`
- name: `?EnumerateDirectoryWithMerge@UfsStreamHandleCtx@UnionFs@@QEBAJAEBU_FLT_CALLBACK_DATA@@W4_FILE_INFORMATION_CLASS@@AEBU_UNICODE_STRING@@KEAEAUEnumerateDirResults@2@AEAVStackEventTracer@2@_N@Z`
- size: `2474`
- prototype: `__int64 __usercall@<rax>(UnionFs::UfsStreamHandleCtx *__hidden this@<rcx>, const struct _FLT_CALLBACK_DATA *@<rdx>, enum _FILE_INFORMATION_CLASS@<r8d>, const struct _UNICODE_STRING *@<r9>, unsigned int, char *, struct UnionFs::EnumerateDirResults *, struct UnionFs::StackEventTracer *, bool)`
- caller_count: `2`
- callee_count: `24`
- tags: `reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14001b820`
- `0x140029560`

## callees

- `0x14000502c`
- `0x1400069b4`
- `0x14000f374`
- `0x14000f7fc`
- `0x140025168`
- `0x140025d48`
- `0x1400266f8`
- `0x1400287c8`
- `0x140029790`
- `0x140029e68`
- `0x14002aaac`
- `0x14002ac7c`
- `0x14002accc`
- `0x140036180`
- `0x140056ac4`
- `0x140056afc`
- `0x140079c48`
- `0x140079d0c`
- `0x140079df4`
- `0x14007af90`
- `0x14007b7d0`
- `0x14007b8b0`
- `0x14007b900`
- `0x14007bc00`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14002605c`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002605c`
- `ntoskrnl!KeSetEvent` at `0x14002610e`
- `ntoskrnl!KeSetEvent` at `0x140026585`
- `ntoskrnl!KeSetEvent` at `0x140026673`
- `ntoskrnl!KeSetEvent` at `0x14002610e`
- `ntoskrnl!KeSetEvent` at `0x140026585`
- `ntoskrnl!KeSetEvent` at `0x140026673`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400262c8`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14002656c`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14002665a`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400262c8`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14002656c`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14002665a`

## string_xrefs

- `0x140025dbd`: `UnionFs::UfsStreamHandleCtx::EnumerateDirectoryWithMerge`
- `0x140025e42`: `UnionFs::UfsStreamHandleCtx::EnumerateDirectoryWithMerge`
- `0x140025f5d`: `UnionFs::UfsStreamHandleCtx::EnumerateDirectoryWithMerge`
- `0x1400260eb`: `UnionFs::UfsStreamHandleCtx::EnumerateDirectoryWithMerge`
- `0x1400261e0`: `UnionFs::UfsStreamHandleCtx::EnumerateDirectoryWithMerge`
- `0x14002628e`: `UnionFs::UfsStreamHandleCtx::EnumerateDirectoryWithMerge`
- `0x14002630c`: `UnionFs::UfsStreamHandleCtx::EnumerateDirectoryWithMerge`
- `0x14002650d`: `UnionFs::UfsStreamHandleCtx::EnumerateDirectoryWithMerge`
- `0x14002627b`: `ORIGIN: Allocating full path buffer`

## pseudocode

```c
__int64 __fastcall UnionFs::UfsStreamHandleCtx::EnumerateDirectoryWithMerge(
        struct _KEVENT *this,
        struct _FLT_CALLBACK_DATA *a2,
        enum _FILE_INFORMATION_CLASS a3,
        struct _UNICODE_STRING *a4,
        unsigned int a5,
        char *a6,
        struct UnionFs::EnumerateDirResults *a7,
        struct UnionFs::StackEventTracer *a8,
        bool a9)
{
  unsigned int OwningUnion; // ebx
  UnionFs::UfsLayerCtx **ScratchLayer; // rax
  struct FsFltWil::Details::RundownRefCacheAware *v14; // rdx
  enum _FILE_INFORMATION_CLASS v15; // r12d
  unsigned __int64 v16; // rax
  unsigned int v17; // r15d
  const char *v18; // rax
  __int64 v19; // r8
  unsigned __int64 v20; // rcx
  void *v21; // rax
  struct FsFltWil::Details::RundownRefCacheAware *v22; // rdx
  unsigned int Blink; // ecx
  char v24; // r8
  unsigned __int64 v25; // rdx
  int NormalizedNameForEnum; // edi
  struct FsFltWil::Details::RundownRefCacheAware *v27; // rdx
  struct FsFltWil::Details::RundownRefCacheAware *v28; // rdx
  const struct _FLT_INSTANCE *ScratchInstance; // rcx
  struct _UNICODE_STRING *UniqueUnicodeString; // rax
  struct _UNICODE_STRING *v31; // rdx
  __int64 v32; // rdi
  WCHAR *Buffer; // rsi
  struct _UNICODE_STRING *v34; // rdx
  struct _FLT_FILE_NAME_INFORMATION *v35; // rcx
  unsigned __int64 v36; // rax
  int v37; // edi
  int v38; // esi
  struct UnionFs::EnumerateDirResults *v39; // rcx
  int v40; // eax
  __int128 v41; // xmm0
  int v42; // eax
  int v43; // eax
  int v44; // eax
  const char *v45; // rcx
  __int64 v46; // r8
  __int64 v47; // rcx
  struct _LIST_ENTRY *v48; // rdx
  __int64 v49; // r8
  struct _UNICODE_STRING *v50; // rdx
  struct FsFltWil::Details::RundownRefCacheAware *v51; // rdx
  struct _FLT_FILE_NAME_INFORMATION *v52; // rcx
  struct FsFltWil::Details::RundownRefCacheAware *v53; // rdx
  struct UnionFs::EnumerateDirResults *v54; // rax
  struct _LIST_ENTRY *v55; // rdx
  __int64 v56; // r8
  struct _UNICODE_STRING *v57; // rdx
  struct _FLT_FILE_NAME_INFORMATION *v58; // rcx
  struct FsFltWil::Details::RundownRefCacheAware *v59; // rdx
  struct UnionFs::StackEventTracer *v60; // [rsp+28h] [rbp-D8h]
  struct UnionFs::StackEventTracer *v61; // [rsp+28h] [rbp-D8h]
  unsigned int v62; // [rsp+40h] [rbp-C0h]
  _QWORD v63[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int16 v64; // [rsp+58h] [rbp-A8h]
  int v65; // [rsp+5Ah] [rbp-A6h]
  __int16 v66; // [rsp+5Eh] [rbp-A2h]
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+60h] [rbp-A0h]
  struct _UNICODE_STRING UnicodeString; // [rsp+68h] [rbp-98h] BYREF
  struct UnionFs::EnumerateDirResults *v69; // [rsp+78h] [rbp-88h]
  enum _FILE_INFORMATION_CLASS v70; // [rsp+80h] [rbp-80h]
  unsigned int v71; // [rsp+84h] [rbp-7Ch]
  struct _UNICODE_STRING *v72; // [rsp+88h] [rbp-78h]
  __int128 v73; // [rsp+90h] [rbp-70h] BYREF
  __int64 v74; // [rsp+A0h] [rbp-60h]
  void *Src; // [rsp+A8h] [rbp-58h]
  __int64 v76; // [rsp+B0h] [rbp-50h]
  char v77; // [rsp+B8h] [rbp-48h]
  struct _FLT_CALLBACK_DATA *v78; // [rsp+C0h] [rbp-40h]
  struct _UNICODE_STRING v79; // [rsp+C8h] [rbp-38h] BYREF
  utl::_RefCountBase *v80[2]; // [rsp+D8h] [rbp-28h] BYREF
  _QWORD v81[17]; // [rsp+E8h] [rbp-18h] BYREF
  _QWORD v82[17]; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v83[128]; // [rsp+1F8h] [rbp+F8h] BYREF
  __int64 v84; // [rsp+278h] [rbp+178h]

  v72 = a4;
  *((_DWORD *)a7 + 5) = 0;
  v70 = a3;
  v78 = a2;
  v69 = a7;
  if ( ((unsigned __int8)a6 & 4) != 0 )
  {
    OwningUnion = -1073741637;
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC00000BBLL,
      (int)a8,
      (struct UnionFs::StackEventTracer *)0x19E000A0754LL,
      (unsigned __int64)"UnionFs::UfsStreamHandleCtx::EnumerateDirectoryWithMerge",
      "ORIGIN: SL_INDEX_SPECIFIED not supported",
      (const char *)v60);
    return OwningUnion;
  }
  *(_OWORD *)v80 = 0;
  memset(v81, 0, sizeof(v81));
  ScratchLayer = (UnionFs::UfsLayerCtx **)UnionFs::UfsStreamHandleCtx::TryGetScratchLayer(this, &v79);
  OwningUnion = UnionFs::UfsLayerCtx::TryGetOwningUnion(
                  *ScratchLayer,
                  (struct UnionFs::UfsUnionCtxWithRundown *)v80,
                  a8);
  if ( v79.Buffer )
    utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v79.Buffer);
  if ( (OwningUnion & 0x80000000) != 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)OwningUnion,
      (int)a8,
      (struct UnionFs::StackEventTracer *)0x473000A075CLL,
      (unsigned __int64)"UnionFs::UfsStreamHandleCtx::EnumerateDirectoryWithMerge",
      "PUSH: Union inactive",
      (const char *)v60);
LABEL_8:
    FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v81, v14);
    if ( v81[16] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v81[16] + 24LL))(v81[16]);
    if ( v80[1] )
      utl::_RefCountBase::_DecStrong(v80[1]);
    return OwningUnion;
  }
  v15 = FileMaximumInformation|FileBasicInformation;
  if ( a3 > (FileMaximumInformation|FileBasicInformation) )
  {
    v15 = FileMaximumInformation|FileEaInformation;
    switch ( a3 )
    {
      case '?':
        v16 = 114;
        v17 = 634;
        break;
      case 'N':
        goto LABEL_20;
      case 'O':
        v16 = 106;
        goto LABEL_24;
      case 'P':
        v16 = 96;
        v17 = 616;
        v15 = 80;
        break;
      case 'Q':
        v16 = 122;
        v17 = 642;
        v15 = FileAlignmentInformation|0x40;
        break;
      default:
        goto LABEL_34;
    }
  }
  else
  {
    if ( a3 != (FileMaximumInformation|FileBasicInformation) )
    {
      switch ( a3 )
      {
        case FileDirectoryInformation:
          v16 = 64;
          goto LABEL_27;
        case FileFullDirectoryInformation:
          v16 = 68;
          goto LABEL_27;
        case FileBothDirectoryInformation:
          v16 = 94;
          break;
        case FileNamesInformation:
          v16 = 12;
          goto LABEL_27;
        case FileIdBothDirectoryInformation:
          v16 = 104;
          break;
        case FileIdFullDirectoryInformation:
LABEL_20:
          v16 = 80;
LABEL_27:
          v17 = 600;
          v15 = FilePositionInformation|0x40;
          goto LABEL_40;
        default:
LABEL_34:
          MicrosoftTelemetryAssertTriggeredMsgKM("Unexpected FILE_INFORMATION_CLASS");
          v18 = "ORIGIN: Invalid FILE_INFORMATION_CLASS";
          v19 = 0x19F000A07ACLL;
          OwningUnion = -1073741811;
LABEL_35:
          UnionFs::ProcessTraceStatusOrigin(
            (UnionFs *)OwningUnion,
            (int)a8,
            (struct UnionFs::StackEventTracer *)v19,
            (unsigned __int64)"UnionFs::UfsStreamHandleCtx::EnumerateDirectoryWithMerge",
            v18,
            (const char *)v60);
          goto LABEL_8;
      }
LABEL_24:
      v17 = 626;
      v15 = FileFullEaInformation|0x40;
      goto LABEL_40;
    }
    v16 = 88;
    v17 = 608;
  }
LABEL_40:
  v20 = *(_QWORD *)a7;
  if ( *(_QWORD *)a7 < v16 )
  {
    v18 = "ORIGIN: User buffer too small";
    v19 = 0x1A4000A07BALL;
    OwningUnion = -1073741820;
    goto LABEL_35;
  }
  if ( v20 >= v17 )
  {
    v17 = 65556;
    if ( v20 <= 0x10014 )
      v17 = *(_QWORD *)a7;
  }
  memset(v82, 0, sizeof(v82));
  if ( (this->Header.LockNV & 1) != 0 && (this->Header.LockNV & 0x20) == 0 )
  {
    v21 = (void *)UnionFs::UfsStreamCtx::SyncWithCOW(*(UnionFs::UfsStreamCtx **)(*(_QWORD *)(*(_QWORD *)&this[3].Header.Lock
                                                                                           + 24LL)
                                                                               + 136LL));
    wil::unique_struct<FsFltWil::Details::RundownRefCacheAware,void (*)(FsFltWil::Details::RundownRefCacheAware *),&void FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *),std::nullptr_t,0>::operator=(
      (FsFltWil::Details *)v82,
      v21);
    FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v83, v22);
    if ( v84 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v84 + 24LL))(v84);
  }
  KeWaitForSingleObject(&this[4], Executive, 0, 0, 0);
  Blink = (unsigned int)this[3].Header.WaitListHead.Blink;
  if ( (Blink & 8) == 0 )
  {
    Blink |= 1u;
    LODWORD(this[3].Header.WaitListHead.Blink) = Blink;
  }
  v24 = (char)a6;
  v25 = Blink;
  if ( ((unsigned __int8)a6 & 1) != 0 )
  {
    v25 = Blink & 0xFFFFFFFD;
    LODWORD(this[3].Header.WaitListHead.Blink) = v25;
    Blink &= ~2u;
  }
  if ( (v25 & 2) != 0 )
  {
    *((_DWORD *)v69 + 5) = -2147483642;
LABEL_131:
    if ( this != (struct _KEVENT *)-96LL )
      KeSetEvent(this + 4, 0, 0);
    FsFltWil::Details::ReleaseRundownProtectionCacheAware(
      (FsFltWil::Details *)v82,
      (struct FsFltWil::Details::RundownRefCacheAware *)v25);
    if ( v82[16] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v82[16] + 24LL))(v82[16]);
    FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v81, v59);
    if ( v81[16] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v81[16] + 24LL))(v81[16]);
    if ( v80[1] )
      utl::_RefCountBase::_DecStrong(v80[1]);
    return 0;
  }
  if ( *(struct _LIST_ENTRY **)&this[5].Header.Lock == this[5].Header.WaitListHead.Flink )
  {
    NormalizedNameForEnum = UnionFs::UfsStreamHandleCtx::BuildEnumerationSourceList(
                              (UnionFs::UfsStreamHandleCtx *)this,
                              v80[0],
                              a8,
                              a9);
    if ( NormalizedNameForEnum < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)NormalizedNameForEnum,
        (int)a8,
        (struct UnionFs::StackEventTracer *)0x1A5000A07FFLL,
        (unsigned __int64)"UnionFs::UfsStreamHandleCtx::EnumerateDirectoryWithMerge",
        "PUSH: Building source list",
        (const char *)v60);
LABEL_58:
      if ( this != (struct _KEVENT *)-96LL )
        KeSetEvent(this + 4, 0, 0);
      FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v82, v27);
      if ( v82[16] )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v82[16] + 24LL))(v82[16]);
      FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v81, v28);
      if ( v81[16] )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v81[16] + 24LL))(v81[16]);
      if ( v80[1] )
        utl::_RefCountBase::_DecStrong(v80[1]);
      return (unsigned int)NormalizedNameForEnum;
    }
    LODWORD(this[3].Header.WaitListHead.Blink) |= 4u;
    LODWORD(v25) = this[3].Header.WaitListHead.Blink;
    Blink = v25;
    v24 = (char)a6;
  }
  if ( ((unsigned __int8)a6 & 1) != 0 )
  {
    *(_QWORD *)&this[7].Header.Lock = 0;
    LODWORD(this[3].Header.WaitListHead.Blink) = Blink | 4;
  }
  else if ( (v25 & 4) != 0 && this[7].Header.LockNV && !this[7].Header.SignalState )
  {
    LOBYTE(a6) = v24 | 1;
  }
  ScratchInstance = UnionFs::UfsStreamHandleCtx::TryGetScratchInstance((UnionFs::UfsStreamHandleCtx *)this);
  if ( !ScratchInstance )
  {
    NormalizedNameForEnum = -1058209784;
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC0ED0008LL,
      (int)a8,
      (struct UnionFs::StackEventTracer *)0x3D5000A0824LL,
      (unsigned __int64)"UnionFs::UfsStreamHandleCtx::EnumerateDirectoryWithMerge",
      "ORIGIN: Cannot get scratch instance",
      (const char *)v60);
    goto LABEL_58;
  }
  v63[0] = v80[0];
  v63[1] = ScratchInstance;
  v65 = 0;
  v66 = 0;
  FileNameInformation = 0;
  v64 = 0;
  UnicodeString = 0;
  UniqueUnicodeString = (struct _UNICODE_STRING *)FsFltWil::MakeUniqueUnicodeString(&v79, 520, 1752188501);
  if ( &UnicodeString != UniqueUnicodeString )
  {
    v32 = *(_QWORD *)&UniqueUnicodeString->Length;
    Buffer = UniqueUnicodeString->Buffer;
    *UniqueUnicodeString = 0;
    FsFltWil::Details::FreeUnicodeString(&UnicodeString, v31);
    *(_QWORD *)&UnicodeString.Length = v32;
    UnicodeString.Buffer = Buffer;
  }
  FsFltWil::Details::FreeUnicodeString(&v79, v31);
  if ( !UnicodeString.Buffer )
  {
    NormalizedNameForEnum = -1073741670;
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC000009ALL,
      (int)a8,
      (struct UnionFs::StackEventTracer *)0x7CD000A082FLL,
      (unsigned __int64)"UnionFs::UfsStreamHandleCtx::EnumerateDirectoryWithMerge",
      "ORIGIN: Allocating full path buffer",
      (const char *)v60);
    goto LABEL_80;
  }
  NormalizedNameForEnum = UnionFs::UfsStreamHandleCtx::GetNormalizedNameForEnum((UnionFs::UfsStreamHandleCtx *)this);
  if ( NormalizedNameForEnum < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)NormalizedNameForEnum,
      (int)a8,
      (struct UnionFs::StackEventTracer *)0x656000A083ALL,
      (unsigned __int64)"UnionFs::UfsStreamHandleCtx::EnumerateDirectoryWithMerge",
      "PUSH: Getting normalized name",
      (const char *)v60);
LABEL_80:
    FsFltWil::Details::FreeUnicodeString(&UnicodeString, v34);
    v35 = FileNameInformation;
    FileNameInformation = 0;
    if ( v35 )
      FltReleaseFileNameInformation(v35);
    goto LABEL_58;
  }
  v36 = 0;
  v37 = -1073741823;
  v71 = 0;
  v38 = 0;
  while ( 1 )
  {
    v39 = v69;
    if ( v36 >= *(_QWORD *)v69 )
      goto LABEL_99;
    v40 = UnionFs::UfsStreamHandleCtx::PrepareEnumerationContexts(
            (UnionFs::UfsStreamHandleCtx *)this,
            v80[0],
            v17,
            v15,
            v72,
            (unsigned __int8)a6,
            a8);
    v62 = v40;
    if ( v40 < 0 )
      break;
    v40 = UnionFs::UfsStreamHandleCtx::EnumerateLayeredDirectories((UnionFs::UfsStreamHandleCtx *)this, v72, a5, a8);
    v62 = v40;
    if ( v40 < 0 )
    {
      v45 = "PUSH: Enumerating directories";
      v46 = 0x1A7000A0867LL;
      goto LABEL_108;
    }
    v74 = 0;
    v41 = *(_OWORD *)v69;
    v77 = *((_BYTE *)v69 + 24);
    Src = 0;
    v76 = 0;
    v73 = v41;
    v40 = UnionFs::UfsStreamHandleCtx::MergeEnumerationResults(
            (UnionFs::UfsStreamHandleCtx *)this,
            v78,
            v70,
            (struct UnionFs::Utils::MergeEnumerationParams *)v63,
            (struct UnionFs::MergeResults *)&v73,
            a8);
    v62 = v40;
    if ( v40 < 0 )
    {
      v45 = "PUSH: Merging results";
      v46 = 0x1A8000A0872LL;
      goto LABEL_108;
    }
    v37 = HIDWORD(v76);
    if ( HIDWORD(v76) == -2147483642 || HIDWORD(v76) == -1073741809 )
    {
      v38 += v76;
      goto LABEL_99;
    }
    if ( HIDWORD(v76) == -2147483643 )
    {
      v44 = v76;
      this[7].Header.LockNV += v76;
      LODWORD(this[3].Header.WaitListHead.Blink) |= 4u;
      v38 += v44;
      goto LABEL_99;
    }
    if ( HIDWORD(v76) )
      MicrosoftTelemetryAssertTriggeredMsgKM("enumStatus == STATUS_SUCCESS", 3221225487LL);
    if ( 2 * v74 )
      memmove(&this[7].Header.WaitListHead, Src, 2 * v74);
    this[7].Header.SignalState = 2 * v74;
    v42 = v76;
    if ( (_DWORD)v76 )
    {
      this[7].Header.LockNV += v76;
      v38 += v42;
LABEL_99:
      LODWORD(this[3].Header.WaitListHead.Blink) |= 8u;
      v43 = (int)this[3].Header.WaitListHead.Blink;
      if ( (v43 & 1) != 0 )
      {
        if ( v37 == -2147483643 )
        {
          if ( !this[7].Header.LockNV )
            MicrosoftTelemetryAssertTriggeredMsgKM("Expected to have returned data on BUFFER_OVERFLOW", 3221225487LL);
        }
        else
        {
          if ( v37 == -2147483642 && !this[7].Header.LockNV )
            v37 = -1073741809;
          LODWORD(this[3].Header.WaitListHead.Blink) = v43 & 0xFFFFFFFE;
        }
      }
      v54 = v69;
      *((_DWORD *)v69 + 4) = v38;
      *((_DWORD *)v54 + 5) = v37;
      if ( v37 >= 0 )
      {
        UnionFs::UfsStreamHandleCtx::ResetEnumerationContexts((UnionFs::UfsStreamHandleCtx *)this, 0);
      }
      else
      {
        v55 = *(struct _LIST_ENTRY **)&this[6].Header.Lock;
        v56 = (char *)this[6].Header.WaitListHead.Flink - (char *)v55;
        this[6].Header.WaitListHead.Flink = v55;
        utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<UnionFs::UfsEnumContext,utl::default_delete<UnionFs::UfsEnumContext>>>>(
          v39,
          v55,
          v56 >> 3);
      }
      FsFltWil::Details::FreeUnicodeString(&UnicodeString, v57);
      v58 = FileNameInformation;
      FileNameInformation = 0;
      if ( v58 )
        FltReleaseFileNameInformation(v58);
      goto LABEL_131;
    }
    UnionFs::UfsStreamHandleCtx::ResetEnumerationContexts((UnionFs::UfsStreamHandleCtx *)this, 1);
    LOBYTE(a6) = (unsigned __int8)a6 & 0xFE;
    v38 += v76;
    v36 = v71;
  }
  v45 = "PUSH: Preparing enum contexts";
  v46 = 0x1A6000A0862LL;
LABEL_108:
  UnionFs::ProcessTraceStatusPushLocation(
    (UnionFs *)(unsigned int)v40,
    (int)a8,
    (struct UnionFs::StackEventTracer *)v46,
    (unsigned __int64)"UnionFs::UfsStreamHandleCtx::EnumerateDirectoryWithMerge",
    v45,
    (const char *)v61);
  if ( v37 >= 0 )
  {
    UnionFs::UfsStreamHandleCtx::ResetEnumerationContexts((UnionFs::UfsStreamHandleCtx *)this, 0);
  }
  else
  {
    v48 = *(struct _LIST_ENTRY **)&this[6].Header.Lock;
    v49 = (char *)this[6].Header.WaitListHead.Flink - (char *)v48;
    this[6].Header.WaitListHead.Flink = v48;
    utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<UnionFs::UfsEnumContext,utl::default_delete<UnionFs::UfsEnumContext>>>>(
      v47,
      v48,
      v49 >> 3);
  }
  FsFltWil::Details::FreeUnicodeString(&UnicodeString, v50);
  v52 = FileNameInformation;
  FileNameInformation = 0;
  if ( v52 )
    FltReleaseFileNameInformation(v52);
  if ( this != (struct _KEVENT *)-96LL )
    KeSetEvent(this + 4, 0, 0);
  FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v82, v51);
  if ( v82[16] )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v82[16] + 24LL))(v82[16]);
  FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v81, v53);
  if ( v81[16] )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v81[16] + 24LL))(v81[16]);
  if ( v80[1] )
    utl::_RefCountBase::_DecStrong(v80[1]);
  return v62;
}

```

## disassembly

```asm
0x140025d48  push    rbp
0x140025d4a  push    rbx
0x140025d4b  push    rsi
0x140025d4c  push    rdi
0x140025d4d  push    r12
0x140025d4f  push    r13
0x140025d51  push    r14
0x140025d53  push    r15
0x140025d55  lea     rbp, [rsp-198h]
0x140025d5d  sub     rsp, 298h
0x140025d64  mov     rax, cs:__security_cookie
0x140025d6b  xor     rax, rsp
0x140025d6e  mov     [rbp+1D0h+var_50], rax
0x140025d75  mov     rsi, [rbp+1D0h+arg_30]
0x140025d7c  xor     r15d, r15d
0x140025d7f  test    byte ptr [rbp+1D0h+arg_28], 4
0x140025d86  mov     edi, r8d
0x140025d89  mov     r13, [rbp+1D0h+arg_38]
0x140025d90  mov     r14, rcx
0x140025d93  mov     [rbp+1D0h+var_248], r9
0x140025d97  mov     [rsi+14h], r15d
0x140025d9b  mov     [rbp+1D0h+var_250], r8d
0x140025d9f  mov     [rbp+1D0h+var_210], rdx
0x140025da3  mov     [rsp+2D0h+var_258], rsi
0x140025da8  jz      short loc_140025DDD
0x140025daa  lea     rax, aOriginSlIndexS; "ORIGIN: SL_INDEX_SPECIFIED not supporte"...
0x140025db1  mov     ebx, 0C00000BBh
0x140025db6  mov     ecx, ebx; this
0x140025db8  mov     [rsp+2D0h+Timeout], rax; char *
0x140025dbd  lea     r9, aUnionfsUfsstre_4; "UnionFs::UfsStreamHandleCtx::EnumerateD"...
0x140025dc4  mov     r8, 19E000A0754h; struct UnionFs::StackEventTracer *
0x140025dce  mov     rdx, r13; int
0x140025dd1  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140025dd6  mov     eax, ebx
0x140025dd8  jmp     loc_1400266CE
0x140025ddd  xorps   xmm0, xmm0
0x140025de0  mov     [rbp+1D0h+var_1E8], r15
0x140025de4  xor     edx, edx; Val
0x140025de6  mov     [rbp+1D0h+var_1E0], r15b
0x140025dea  mov     r8d, 88h; Size
0x140025df0  mov     [rbp+1D0h+var_168], r15
0x140025df4  lea     rcx, [rbp+1D0h+var_1E8]; void *
0x140025df8  movdqu  xmmword ptr [rbp+1D0h+var_1F8], xmm0
0x140025dfd  call    memset
0x140025e02  lea     rdx, [rbp+1D0h+var_208]
0x140025e06  mov     rcx, r14
0x140025e09  call    ?TryGetScratchLayer@UfsStreamHandleCtx@UnionFs@@QEBA?AV?$shared_ptr@$$CBVUfsLayerCtx@UnionFs@@@utl@@XZ; UnionFs::UfsStreamHandleCtx::TryGetScratchLayer(void)
0x140025e0e  mov     r8, r13; struct UnionFs::StackEventTracer *
0x140025e11  lea     rdx, [rbp+1D0h+var_1F8]; struct UnionFs::UfsUnionCtxWithRundown *
0x140025e15  mov     rcx, [rax]; this
0x140025e18  call    ?TryGetOwningUnion@UfsLayerCtx@UnionFs@@QEBAJAEAUUfsUnionCtxWithRundown@2@AEAVStackEventTracer@2@@Z; UnionFs::UfsLayerCtx::TryGetOwningUnion(UnionFs::UfsUnionCtxWithRundown &,UnionFs::StackEventTracer &)
0x140025e1d  mov     rcx, [rbp+1D0h+var_208.Buffer]; this
0x140025e21  mov     ebx, eax
0x140025e23  test    rcx, rcx
0x140025e26  jz      short loc_140025E2D
0x140025e28  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140025e2d  test    ebx, ebx
0x140025e2f  jns     short loc_140025E8D
0x140025e31  lea     rax, aPushUnionInact; "PUSH: Union inactive"
0x140025e38  mov     r8, 473000A075Ch; struct UnionFs::StackEventTracer *
0x140025e42  lea     r9, aUnionfsUfsstre_4; "UnionFs::UfsStreamHandleCtx::EnumerateD"...
0x140025e49  mov     [rsp+2D0h+Timeout], rax; char *
0x140025e4e  mov     rdx, r13; int
0x140025e51  mov     ecx, ebx; this
0x140025e53  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140025e58  lea     rcx, [rbp+1D0h+var_1E8]; this
0x140025e5c  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
0x140025e61  mov     rcx, [rbp+1D0h+var_168]
0x140025e65  test    rcx, rcx
0x140025e68  jz      short loc_140025E76
0x140025e6a  mov     rax, [rcx]
0x140025e6d  mov     rax, [rax+18h]
0x140025e71  call    _guard_dispatch_icall
0x140025e76  mov     rcx, [rbp+1D0h+var_1F8+8]; this
0x140025e7a  test    rcx, rcx
0x140025e7d  jz      loc_140025DD6
0x140025e83  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140025e88  jmp     loc_140025DD6
0x140025e8d  mov     r12d, 3Ch ; '<'
0x140025e93  cmp     edi, r12d
0x140025e96  jg      short loc_140025F12
0x140025e98  jz      short loc_140025F02
0x140025e9a  mov     ecx, edi
0x140025e9c  sub     ecx, 1
0x140025e9f  jz      short loc_140025EEC
0x140025ea1  sub     ecx, 1
0x140025ea4  jz      short loc_140025EE5
0x140025ea6  sub     ecx, 1
0x140025ea9  jz      short loc_140025ECF
0x140025eab  sub     ecx, 9
0x140025eae  jz      short loc_140025EC8
0x140025eb0  sub     ecx, 19h
0x140025eb3  jz      short loc_140025EC1
0x140025eb5  cmp     ecx, 1
0x140025eb8  jnz     short loc_140025F33
0x140025eba  mov     eax, 50h ; 'P'
0x140025ebf  jmp     short loc_140025EF1
0x140025ec1  mov     eax, 68h ; 'h'
0x140025ec6  jmp     short loc_140025ED4
0x140025ec8  mov     eax, 0Ch
0x140025ecd  jmp     short loc_140025EF1
0x140025ecf  mov     eax, 5Eh ; '^'
0x140025ed4  mov     r15d, 272h
0x140025eda  mov     r12d, 4Fh ; 'O'
0x140025ee0  jmp     loc_140025FA7
0x140025ee5  mov     eax, 44h ; 'D'
0x140025eea  jmp     short loc_140025EF1
0x140025eec  mov     eax, 40h ; '@'
0x140025ef1  mov     r15d, 258h
0x140025ef7  mov     r12d, 4Eh ; 'N'
0x140025efd  jmp     loc_140025FA7
0x140025f02  mov     eax, 58h ; 'X'
0x140025f07  mov     r15d, 260h
0x140025f0d  jmp     loc_140025FA7
0x140025f12  mov     ecx, edi
0x140025f14  mov     r12d, 3Fh ; '?'
0x140025f1a  sub     ecx, r12d
0x140025f1d  jz      short loc_140025F9C
0x140025f1f  sub     ecx, 0Fh
0x140025f22  jz      short loc_140025EBA
0x140025f24  sub     ecx, 1
0x140025f27  jz      short loc_140025F92
0x140025f29  sub     ecx, 1
0x140025f2c  jz      short loc_140025F81
0x140025f2e  cmp     ecx, 1
0x140025f31  jz      short loc_140025F70
0x140025f33  lea     rcx, aUnexpectedFile; "Unexpected FILE_INFORMATION_CLASS"
0x140025f3a  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140025f3f  lea     rax, aOriginInvalidF_0; "ORIGIN: Invalid FILE_INFORMATION_CLASS"
0x140025f46  mov     r8, 19F000A07ACh; struct UnionFs::StackEventTracer *
0x140025f50  mov     ebx, 0C000000Dh
0x140025f55  mov     rdx, r13; int
0x140025f58  mov     [rsp+2D0h+Timeout], rax; char *
0x140025f5d  lea     r9, aUnionfsUfsstre_4; "UnionFs::UfsStreamHandleCtx::EnumerateD"...
0x140025f64  mov     ecx, ebx; this
0x140025f66  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140025f6b  jmp     loc_140025E58
0x140025f70  mov     eax, 7Ah ; 'z'
0x140025f75  mov     r15d, 282h
0x140025f7b  lea     r12d, [rax-29h]
0x140025f7f  jmp     short loc_140025FA7
0x140025f81  mov     eax, 60h ; '`'
0x140025f86  mov     r15d, 268h
0x140025f8c  lea     r12d, [rax-10h]
0x140025f90  jmp     short loc_140025FA7
0x140025f92  mov     eax, 6Ah ; 'j'
0x140025f97  jmp     loc_140025ED4
0x140025f9c  mov     eax, 72h ; 'r'
0x140025fa1  mov     r15d, 27Ah
0x140025fa7  mov     rcx, [rsi]
0x140025faa  cmp     rcx, rax
0x140025fad  jnb     short loc_140025FC7
0x140025faf  lea     rax, aOriginUserBuff; "ORIGIN: User buffer too small"
0x140025fb6  mov     r8, 1A4000A07BAh
0x140025fc0  mov     ebx, 0C0000004h
0x140025fc5  jmp     short loc_140025F55
0x140025fc7  mov     eax, r15d
0x140025fca  cmp     rcx, rax
0x140025fcd  jb      short loc_140025FDD
0x140025fcf  mov     r15d, 10014h
0x140025fd5  cmp     rcx, r15
0x140025fd8  ja      short loc_140025FDD
0x140025fda  mov     r15d, ecx
0x140025fdd  xor     edx, edx; Val
0x140025fdf  lea     rcx, [rbp+1D0h+var_160]; void *
0x140025fe3  mov     r8d, 88h; Size
0x140025fe9  call    memset
0x140025fee  mov     eax, [r14]
0x140025ff1  test    al, 1
0x140025ff3  jz      short loc_140026044
0x140025ff5  test    al, 20h
0x140025ff7  jnz     short loc_140026044
0x140025ff9  mov     rax, [r14+48h]
0x140025ffd  lea     rdx, [rbp+1D0h+var_D8]
0x140026004  mov     rcx, [rax+18h]
0x140026008  mov     rcx, [rcx+88h]; this
0x14002600f  call    ?SyncWithCOW@UfsStreamCtx@UnionFs@@QEAA@XZ; UnionFs::UfsStreamCtx::SyncWithCOW(void)
0x140026014  mov     rdx, rax; void *
0x140026017  lea     rcx, [rbp+1D0h+var_160]; this
0x14002601b  call    ??4?$unique_struct@URundownRefCacheAware@Details@FsFltWil@@P6AXPEAU123@@Z$1?ReleaseRundownProtectionCacheAware@23@YAX0@Z$$T$0A@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_struct<FsFltWil::Details::RundownRefCacheAware,void (*)(FsFltWil::Details::RundownRefCacheAware *),&FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *),std::nullptr_t,0>::operator=(wil::unique_struct<FsFltWil::Details::RundownRefCacheAware,void (*)(FsFltWil::Details::RundownRefCacheAware *),&FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *),std::nullptr_t,0> &&)
0x140026020  lea     rcx, [rbp+1D0h+var_D8]; this
0x140026027  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
0x14002602c  mov     rcx, [rbp+1D0h+var_58]
0x140026033  test    rcx, rcx
0x140026036  jz      short loc_140026044
0x140026038  mov     rax, [rcx]
0x14002603b  mov     rax, [rax+18h]
0x14002603f  call    _guard_dispatch_icall
0x140026044  lea     rbx, [r14+60h]
0x140026048  mov     [rsp+2D0h+Timeout], 0; Timeout
0x140026051  mov     rcx, rbx; Object
0x140026054  xor     r9d, r9d; Alertable
0x140026057  xor     r8d, r8d; WaitMode
0x14002605a  xor     edx, edx; WaitReason
0x14002605c  call    cs:__imp_KeWaitForSingleObject
0x140026063  nop     dword ptr [rax+rax+00h]
0x140026068  mov     ecx, [r14+58h]
0x14002606c  test    cl, 8
0x14002606f  jnz     short loc_140026078
0x140026071  or      ecx, 1
0x140026074  mov     [r14+58h], ecx
0x140026078  mov     r8b, byte ptr [rbp+1D0h+arg_28]
0x14002607f  mov     edx, ecx
0x140026081  mov     sil, r8b
0x140026084  and     sil, 1
0x140026088  jz      short loc_140026093
0x14002608a  and     edx, 0FFFFFFFDh
0x14002608d  mov     [r14+58h], edx
0x140026091  mov     ecx, edx
0x140026093  test    dl, 2
0x140026096  jz      short loc_1400260A9
0x140026098  mov     rcx, [rsp+2D0h+var_258]
0x14002609d  mov     dword ptr [rcx+14h], 80000006h
0x1400260a4  jmp     loc_140026666
0x1400260a9  mov     rax, [r14+80h]
0x1400260b0  cmp     [r14+78h], rax
0x1400260b4  jnz     loc_140026180
0x1400260ba  mov     r9b, [rbp+1D0h+arg_40]; bool
0x1400260c1  mov     r8, r13; struct UnionFs::StackEventTracer *
0x1400260c4  mov     rdx, [rbp+1D0h+var_1F8]; struct UnionFs::UfsUnionCtx *
0x1400260c8  mov     rcx, r14; this
0x1400260cb  call    ?BuildEnumerationSourceList@UfsStreamHandleCtx@UnionFs@@AEBAJAEBVUfsUnionCtx@2@AEAVStackEventTracer@2@_N@Z; UnionFs::UfsStreamHandleCtx::BuildEnumerationSourceList(UnionFs::UfsUnionCtx const &,UnionFs::StackEventTracer &,bool)
0x1400260d0  mov     edi, eax
0x1400260d2  test    eax, eax
0x1400260d4  jns     loc_14002616E
0x1400260da  lea     rax, aPushBuildingSo; "PUSH: Building source list"
0x1400260e1  mov     r8, 1A5000A07FFh; struct UnionFs::StackEventTracer *
0x1400260eb  lea     r9, aUnionfsUfsstre_4; "UnionFs::UfsStreamHandleCtx::EnumerateD"...
0x1400260f2  mov     [rsp+2D0h+Timeout], rax; char *
0x1400260f7  mov     rdx, r13; int
0x1400260fa  mov     ecx, edi; this
0x1400260fc  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140026101  test    rbx, rbx
0x140026104  jz      short loc_14002611A
0x140026106  xor     r8d, r8d; Wait
0x140026109  xor     edx, edx; Increment
0x14002610b  mov     rcx, rbx; Event
0x14002610e  call    cs:__imp_KeSetEvent
0x140026115  nop     dword ptr [rax+rax+00h]
0x14002611a  lea     rcx, [rbp+1D0h+var_160]; this
0x14002611e  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
0x140026123  mov     rcx, [rbp+1D0h+var_E0]
0x14002612a  test    rcx, rcx
0x14002612d  jz      short loc_14002613B
0x14002612f  mov     rax, [rcx]
0x140026132  mov     rax, [rax+18h]
0x140026136  call    _guard_dispatch_icall
0x14002613b  lea     rcx, [rbp+1D0h+var_1E8]; this
0x14002613f  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
0x140026144  mov     rcx, [rbp+1D0h+var_168]
0x140026148  test    rcx, rcx
0x14002614b  jz      short loc_140026159
0x14002614d  mov     rax, [rcx]
0x140026150  mov     rax, [rax+18h]
0x140026154  call    _guard_dispatch_icall
0x140026159  mov     rcx, [rbp+1D0h+var_1F8+8]; this
0x14002615d  test    rcx, rcx
0x140026160  jz      short loc_140026167
0x140026162  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140026167  mov     eax, edi
0x140026169  jmp     loc_1400266CE
0x14002616e  or      dword ptr [r14+58h], 4
0x140026173  mov     edx, [r14+58h]
0x140026177  mov     ecx, edx
0x140026179  mov     r8b, byte ptr [rbp+1D0h+arg_28]
0x140026180  test    sil, sil
0x140026183  jz      short loc_140026199
0x140026185  or      ecx, 4
0x140026188  mov     qword ptr [r14+0A8h], 0
0x140026193  mov     [r14+58h], ecx
0x140026197  jmp     short loc_1400261BD
0x140026199  test    dl, 4
0x14002619c  jz      short loc_1400261BD
0x14002619e  cmp     dword ptr [r14+0A8h], 0
0x1400261a6  jbe     short loc_1400261BD
0x1400261a8  cmp     dword ptr [r14+0ACh], 0
0x1400261b0  jnz     short loc_1400261BD
0x1400261b2  or      r8b, 1
0x1400261b6  mov     byte ptr [rbp+1D0h+arg_28], r8b
0x1400261bd  mov     rcx, r14; this
0x1400261c0  call    ?TryGetScratchInstance@UfsStreamHandleCtx@UnionFs@@QEBAPEBU_FLT_INSTANCE@@XZ; UnionFs::UfsStreamHandleCtx::TryGetScratchInstance(void)
0x1400261c5  mov     rcx, rax
0x1400261c8  test    rax, rax
0x1400261cb  jnz     short loc_1400261FE
0x1400261cd  lea     rax, aOriginCannotGe; "ORIGIN: Cannot get scratch instance"
0x1400261d4  mov     edi, 0C0ED0008h
0x1400261d9  mov     ecx, edi; this
0x1400261db  mov     [rsp+2D0h+Timeout], rax; char *
0x1400261e0  lea     r9, aUnionfsUfsstre_4; "UnionFs::UfsStreamHandleCtx::EnumerateD"...
0x1400261e7  mov     r8, 3D5000A0824h; struct UnionFs::StackEventTracer *
0x1400261f1  mov     rdx, r13; int
0x1400261f4  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400261f9  jmp     loc_140026101
0x1400261fe  mov     rax, [rbp+1D0h+var_1F8]
0x140026202  xorps   xmm0, xmm0
0x140026205  mov     [rsp+2D0h+var_288], rax
0x14002620a  mov     edx, 208h
0x14002620f  xor     eax, eax
0x140026211  mov     [rsp+2D0h+var_280], rcx
0x140026216  mov     r8d, 68704655h
  ... truncated ...
```
