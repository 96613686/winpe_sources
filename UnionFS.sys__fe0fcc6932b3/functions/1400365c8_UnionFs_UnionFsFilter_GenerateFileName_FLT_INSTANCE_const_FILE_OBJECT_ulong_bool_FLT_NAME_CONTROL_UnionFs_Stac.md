# UnionFs::UnionFsFilter::GenerateFileName(_FLT_INSTANCE const &,_FILE_OBJECT &,ulong,bool *,_FLT_NAME_CONTROL *,UnionFs::StackEventTracer &,_FLT_CALLBACK_DATA *)

- ea: `0x1400365c8`
- end: `0x140036cb5`
- name: `?GenerateFileName@UnionFsFilter@UnionFs@@QEAAJAEBU_FLT_INSTANCE@@AEAU_FILE_OBJECT@@KPEA_NPEAU_FLT_NAME_CONTROL@@AEAVStackEventTracer@2@PEAU_FLT_CALLBACK_DATA@@@Z`
- size: `1773`
- prototype: `int(UnionFs::UnionFsFilter *__hidden this, const struct _FLT_INSTANCE *, struct _FILE_OBJECT *, unsigned int, bool *, struct _FLT_NAME_CONTROL *, struct UnionFs::StackEventTracer *, struct _FLT_CALLBACK_DATA *)`
- caller_count: `1`
- callee_count: `15`
- tags: `reparse_path, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140036cc0`

## callees

- `0x140005ff8`
- `0x14000bfd8`
- `0x140027624`
- `0x140027a9c`
- `0x1400365c8`
- `0x140037a64`
- `0x140037b54`
- `0x14003a1a4`
- `0x14003b60c`
- `0x140056c44`
- `0x140056c7c`
- `0x14006f198`
- `0x14007b2b0`
- `0x14007baf0`
- `0x14007bf40`

## import_xrefs

- `ntoskrnl!IoGetTopLevelIrp` at `0x140036645`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140036656`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140036645`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140036656`
- `FLTMGR!FltReleaseContext` at `0x140036873`
- `FLTMGR!FltReleaseContext` at `0x140036937`
- `FLTMGR!FltReleaseContext` at `0x14003694f`
- `FLTMGR!FltReleaseContext` at `0x140036a55`
- `FLTMGR!FltReleaseContext` at `0x140036a69`
- `FLTMGR!FltReleaseContext` at `0x140036c20`
- `FLTMGR!FltReleaseContext` at `0x140036c34`
- `FLTMGR!FltReleaseContext` at `0x140036873`
- `FLTMGR!FltReleaseContext` at `0x140036937`
- `FLTMGR!FltReleaseContext` at `0x14003694f`
- `FLTMGR!FltReleaseContext` at `0x140036a55`
- `FLTMGR!FltReleaseContext` at `0x140036a69`
- `FLTMGR!FltReleaseContext` at `0x140036c20`
- `FLTMGR!FltReleaseContext` at `0x140036c34`

## string_xrefs

- `0x140036639`: `(nameFormat == FLT_FILE_NAME_OPENED) || (nameFormat == FLT_FILE_NAME_NORMALIZED) || (nameFormat == FLT_FILE_NAME_SHORT)`
- `0x1400366fc`: `Unsafe name query in pre-create`
- `0x140036708`: `ORIGIN: Unsafe name query in pre-create`
- `0x140036751`: `(Cbd->Iopb->MajorFunction == IRP_MJ_CREATE) || (Cbd->Iopb->MajorFunction == IRP_MJ_NETWORK_QUERY_OPEN) || (Cbd->Iopb->MajorFunction == IRP_MJ_QUERY_OPEN)`
- `0x1400367be`: `PUSH: GeneratePreCreateOpenedName`
- `0x14003680d`: `PUSH: GeneratePreCreateNormalizedName`
- `0x140036769`: `Non-opened/normalized pre-create name query`
- `0x140036775`: `ORIGIN: Non-opened/normalized pre-create name query`
- `0x140036b92`: `PUSH: Generating post-create OPENED name`
- `0x140036bf1`: `PUSH: Generating post-create NORMALIZED name`

## pseudocode

```c
__int64 __fastcall UnionFs::UnionFsFilter::GenerateFileName(
        UnionFs::UnionFsFilter *this,
        const struct _FLT_INSTANCE *a2,
        struct _FILE_OBJECT *a3,
        int a4,
        bool *a5,
        struct _FLT_NAME_CONTROL *a6,
        struct _UNICODE_STRING *a7,
        struct _FLT_CALLBACK_DATA *a8)
{
  int v11; // r15d
  int MappingTableForFileObject; // eax
  UnionFs::UnionFsFilter *v13; // rcx
  __int64 v14; // rdx
  int OpenedName; // ebx
  const char *v16; // rax
  __int64 v17; // r8
  const char *v19; // rax
  __int64 v20; // r8
  int Name; // esi
  int v22; // r15d
  PFLT_CONTEXT v23; // rcx
  __int64 v24; // rcx
  bool v25; // r8
  PFLT_CONTEXT v26; // rdi
  const struct UnionFs::UfsStreamHandleCtx *v27; // rbx
  int v28; // eax
  UnionFs::UnionFsFilter *v29; // rcx
  int v30; // r12d
  const char *v31; // rax
  __int64 v32; // r8
  int v33; // r15d
  int v34; // r15d
  const char *v35; // rax
  __int64 v36; // r8
  const char *NameCtrl; // [rsp+28h] [rbp-D8h]
  const char *NameCtrla; // [rsp+28h] [rbp-D8h]
  bool v39; // [rsp+38h] [rbp-C8h]
  PFLT_CONTEXT Context; // [rsp+48h] [rbp-B8h] BYREF
  struct _FLT_INSTANCE *v41; // [rsp+50h] [rbp-B0h]
  struct _FLT_CALLBACK_DATA *v42; // [rsp+60h] [rbp-A0h] BYREF
  struct _FILE_OBJECT *v43; // [rsp+68h] [rbp-98h]
  struct _FLT_INSTANCE *v44; // [rsp+70h] [rbp-90h]
  int v45; // [rsp+80h] [rbp-80h] BYREF
  char v46; // [rsp+84h] [rbp-7Ch]
  __int16 v47; // [rsp+85h] [rbp-7Bh]
  char v48; // [rsp+87h] [rbp-79h]
  struct _FILE_OBJECT *v49[2]; // [rsp+88h] [rbp-78h]
  __int64 v50; // [rsp+98h] [rbp-68h]
  UnionFs::UnionFsFilter *v51; // [rsp+A0h] [rbp-60h]
  PFLT_CONTEXT v52[2]; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v53; // [rsp+B8h] [rbp-48h]
  _QWORD v54[17]; // [rsp+C0h] [rbp-40h] BYREF

  v11 = (unsigned __int8)a4;
  v51 = (UnionFs::UnionFsFilter *)UnionFs::g_FilterState;
  v41 = a2;
  if ( (unsigned int)(unsigned __int8)a4 - 1 > 2 )
    MicrosoftTelemetryAssertTriggeredMsgKM(
      "(nameFormat == FLT_FILE_NAME_OPENED) || (nameFormat == FLT_FILE_NAME_NORMALIZED) || (nameFormat == FLT_FILE_NAME_SHORT)");
  if ( IoGetTopLevelIrp() && IoGetTopLevelIrp() != (PIRP)1379099506 )
    MicrosoftTelemetryAssertTriggeredMsgKM("!IoGetTopLevelIrp() || SET.IsRecursive(IoGetTopLevelIrp())");
  *a5 = 1;
  Context = 0;
  MappingTableForFileObject = UnionFs::Utils::GetMappingTableForFileObject(a2, a3, &Context, a7, 0);
  v14 = 0;
  OpenedName = MappingTableForFileObject;
  if ( MappingTableForFileObject < 0 )
  {
    v16 = "PUSH: Getting mapping table";
    v17 = 0x2B4000F0084LL;
LABEL_8:
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)OpenedName,
      (int)a7,
      (struct UnionFs::StackEventTracer *)v17,
      (unsigned __int64)"UnionFs::UnionFsFilter::GenerateFileName",
      v16,
      NameCtrl);
    return (unsigned int)OpenedName;
  }
  if ( !Context || (a3->Flags & 0x400000) != 0 )
  {
    v42 = a8;
    v43 = a3;
    v44 = a2;
    OpenedName = UnionFs::UnionFsFilter::PassthroughNameQuery(v13, &v42, v11 | a4 & 0xFE00FF00, a6, a7);
    if ( OpenedName < 0 )
    {
      v16 = "PUSH: Passing through name query";
      v17 = 0x136000F008FLL;
      goto LABEL_8;
    }
    return 0;
  }
  if ( !a3->FsContext )
  {
    if ( !a8 )
    {
      MicrosoftTelemetryAssertTriggeredMsgKM("Unsafe name query in pre-create", 0);
      v19 = "ORIGIN: Unsafe name query in pre-create";
      v20 = 0x137000F00A0LL;
LABEL_15:
      Name = -1073741811;
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC000000DLL,
        (int)a7,
        (struct UnionFs::StackEventTracer *)v20,
        (unsigned __int64)"UnionFs::UnionFsFilter::GenerateFileName",
        v19,
        NameCtrl);
      return (unsigned int)Name;
    }
    LOBYTE(v13) = a8->Iopb->MajorFunction;
    if ( (_BYTE)v13 && (_BYTE)v13 != 0xF2 && (_BYTE)v13 != 0xF9 )
      MicrosoftTelemetryAssertTriggeredMsgKM(
        "(Cbd->Iopb->MajorFunction == IRP_MJ_CREATE) || (Cbd->Iopb->MajorFunction == IRP_MJ_NETWORK_QUERY_OPEN) || (Cbd->"
        "Iopb->MajorFunction == IRP_MJ_QUERY_OPEN)",
        0);
    v22 = v11 - 1;
    if ( v22 )
    {
      if ( v22 != 1 )
      {
        MicrosoftTelemetryAssertTriggeredMsgKM("Non-opened/normalized pre-create name query", v14);
        v19 = "ORIGIN: Non-opened/normalized pre-create name query";
        v20 = 0x13A000F00CBLL;
        goto LABEL_15;
      }
      OpenedName = UnionFs::UnionFsFilter::GeneratePreCreateOpenedName(
                     v13,
                     a2,
                     a3,
                     a4 & 0xFC00FF00 | 0x2000000,
                     a6,
                     (struct UnionFs::StackEventTracer *)a7,
                     a8);
      if ( OpenedName < 0 )
      {
        v16 = "PUSH: GeneratePreCreateOpenedName";
        v17 = 0x138000F00B6LL;
        goto LABEL_8;
      }
    }
    else
    {
      OpenedName = UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName(
                     v51,
                     a2,
                     a3,
                     a8,
                     a4 & 0xFC00FF00 | 0x2000000,
                     a6,
                     a7);
      if ( OpenedName < 0 )
      {
        v16 = "PUSH: GeneratePreCreateNormalizedName";
        v17 = 0x139000F00C2LL;
        goto LABEL_8;
      }
    }
    return 0;
  }
  Context = 0;
  OpenedName = UnionFs::UfsInstanceCtx::FltGet(a3);
  if ( OpenedName < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)OpenedName,
      (int)a7,
      (struct UnionFs::StackEventTracer *)0x13F000F00DFLL,
      (unsigned __int64)"UnionFs::UnionFsFilter::GenerateFileName",
      "PUSH: Getting instance ctx from FileObject",
      NameCtrl);
    v23 = Context;
    if ( !Context )
      return (unsigned int)OpenedName;
LABEL_30:
    FltReleaseContext(v23);
    return (unsigned int)OpenedName;
  }
  *(_OWORD *)v52 = 0;
  v53 = 0;
  memset(v54, 0, sizeof(v54));
  v26 = Context;
  if ( !Context )
  {
    v27 = 0;
    goto LABEL_33;
  }
  v41 = *(struct _FLT_INSTANCE **)Context;
  v28 = UnionFs::UfsStreamHandleCtx::FltGet(
          v41,
          a3,
          v25,
          (struct UnionFs::HandleCtxAndUnionWithRundown *)v52,
          (struct UnionFs::StackEventTracer *)a7);
  v24 = 0;
  OpenedName = v28;
  if ( v28 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v28,
      (int)a7,
      (struct UnionFs::StackEventTracer *)0x140000F00F6LL,
      (unsigned __int64)"UnionFs::UnionFsFilter::GenerateFileName",
      "PUSH: Getting streamhandle ctx",
      NameCtrl);
    UnionFs::QueryInfoContext::~QueryInfoContext((UnionFs::QueryInfoContext *)v52);
    if ( !v26 )
      return (unsigned int)OpenedName;
    v23 = v26;
    goto LABEL_30;
  }
  v27 = (const struct UnionFs::UfsStreamHandleCtx *)v52[0];
  v52[0] = 0;
  if ( !v27 || (*(_DWORD *)v27 & 1) == 0 )
  {
LABEL_33:
    v42 = a8;
    v43 = a3;
    v44 = v41;
    Name = UnionFs::UnionFsFilter::PassthroughNameQuery(v24, &v42, v11 | a4 & 0xFE00FF00, a6, a7);
    if ( Name < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)Name,
        (int)a7,
        (struct UnionFs::StackEventTracer *)0x141000F0106LL,
        (unsigned __int64)"UnionFs::UnionFsFilter::GenerateFileName",
        "PUSH: Passing name query through",
        NameCtrl);
      UnionFs::QueryInfoContext::~QueryInfoContext((UnionFs::QueryInfoContext *)v52);
      if ( !v27 )
        goto LABEL_36;
      goto LABEL_35;
    }
    UnionFs::QueryInfoContext::~QueryInfoContext((UnionFs::QueryInfoContext *)v52);
    if ( !v27 )
      goto LABEL_65;
    goto LABEL_64;
  }
  v47 = 0;
  v48 = 0;
  *(_OWORD *)v49 = 0;
  v45 = 3;
  v46 = 0;
  v50 = 0;
  v30 = UnionFs::UnionFsFilter::MapShadowFileObjectToBacking(
          0,
          v41,
          a3,
          (struct UnionFs::MapShadowFileObjectResults *)&v45,
          (struct UnionFs::StackEventTracer *)a7,
          v27);
  if ( v30 >= 0 )
  {
    if ( !v46 )
    {
      MicrosoftTelemetryAssertTriggeredMsgKM("Couldn't map SFO when handleCtx->IsShadowFoCtx() is true");
      v31 = "ORIGIN: Couldn't map SFO when handleCtx->IsShadowFoCtx() is true";
      v32 = 0x142000F0122LL;
      Name = -1073741595;
LABEL_49:
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)(unsigned int)Name,
        (int)a7,
        (struct UnionFs::StackEventTracer *)v32,
        (unsigned __int64)"UnionFs::UnionFsFilter::GenerateFileName",
        v31,
        NameCtrla);
LABEL_50:
      UnionFs::QueryInfoContext::~QueryInfoContext((UnionFs::QueryInfoContext *)v52);
LABEL_35:
      FltReleaseContext(v27);
LABEL_36:
      if ( v26 )
        FltReleaseContext(v26);
      return (unsigned int)Name;
    }
    v33 = v11 - 1;
    if ( v33 )
    {
      v34 = v33 - 1;
      if ( v34 )
      {
        if ( v34 != 1 )
        {
          MicrosoftTelemetryAssertTriggeredMsgKM("false");
          v31 = "ORIGIN: Invalid nameFormat";
          v32 = 0x147000F0161LL;
          Name = -1073741811;
          goto LABEL_49;
        }
        v43 = v49[1];
        v44 = (struct _FLT_INSTANCE *)v49[0];
        v42 = 0;
        Name = UnionFs::UnionFsFilter::PassthroughNameQuery(v29, &v42, a4 & 0xFE00FF00 | 3, a6, a7);
        if ( Name < 0 )
        {
          v35 = "PUSH: Passing SHORT name query through";
          v36 = 0x146000F0158LL;
LABEL_59:
          UnionFs::ProcessTraceStatusPushLocation(
            (UnionFs *)(unsigned int)Name,
            (int)a7,
            (struct UnionFs::StackEventTracer *)v36,
            (unsigned __int64)"UnionFs::UnionFsFilter::GenerateFileName",
            v35,
            NameCtrla);
          goto LABEL_50;
        }
      }
      else
      {
        Name = UnionFs::UnionFsFilter::GeneratePostCreateName(
                 v29,
                 (const struct _FLT_INSTANCE *)v49[0],
                 v49[1],
                 a4 & 0xFE00FF00 | 2,
                 v27,
                 a6,
                 (struct UnionFs::StackEventTracer *)a7,
                 v39);
        if ( Name < 0 )
        {
          v35 = "PUSH: Generating post-create OPENED name";
          v36 = 0x143000F0132LL;
          goto LABEL_59;
        }
      }
    }
    else
    {
      Name = UnionFs::UnionFsFilter::GeneratePostCreateName(
               v29,
               (const struct _FLT_INSTANCE *)v49[0],
               v49[1],
               a4 & 0xFE00FF00 | 1,
               v27,
               a6,
               (struct UnionFs::StackEventTracer *)a7,
               v39);
      if ( Name < 0 )
      {
        v35 = "PUSH: Generating post-create NORMALIZED name";
        v36 = 0x145000F0140LL;
        goto LABEL_59;
      }
    }
    UnionFs::QueryInfoContext::~QueryInfoContext((UnionFs::QueryInfoContext *)v52);
LABEL_64:
    FltReleaseContext(v27);
LABEL_65:
    if ( v26 )
      FltReleaseContext(v26);
    return 0;
  }
  UnionFs::ProcessTraceStatusPushLocation(
    (UnionFs *)(unsigned int)v30,
    (int)a7,
    (struct UnionFs::StackEventTracer *)0x235000F0117LL,
    (unsigned __int64)"UnionFs::UnionFsFilter::GenerateFileName",
    "PUSH: MapShadowFileObjectToBacking failure when handleCtx->IsShadowFoCtx() is true",
    NameCtrla);
  UnionFs::QueryInfoContext::~QueryInfoContext((UnionFs::QueryInfoContext *)v52);
  FltReleaseContext(v27);
  if ( v26 )
    FltReleaseContext(v26);
  return (unsigned int)v30;
}

```

## disassembly

```asm
0x1400365c8  mov     [rsp-8+arg_0], rbx
0x1400365cd  push    rbp
0x1400365ce  push    rsi
0x1400365cf  push    rdi
0x1400365d0  push    r12
0x1400365d2  push    r13
0x1400365d4  push    r14
0x1400365d6  push    r15
0x1400365d8  lea     rbp, [rsp-50h]
0x1400365dd  sub     rsp, 150h
0x1400365e4  mov     rax, cs:__security_cookie
0x1400365eb  xor     rax, rsp
0x1400365ee  mov     [rbp+80h+var_38], rax
0x1400365f2  mov     rax, [rbp+80h+arg_28]
0x1400365f9  mov     esi, r9d
0x1400365fc  mov     rbx, [rbp+80h+arg_20]
0x140036603  mov     r13, r8
0x140036606  mov     r14, [rbp+80h+arg_30]
0x14003660d  mov     rdi, rdx
0x140036610  mov     r12, [rbp+80h+arg_38]
0x140036617  mov     [rsp+180h+var_140], rax
0x14003661c  mov     rax, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140036623  movzx   r15d, r9b
0x140036627  mov     [rbp+80h+var_E0], rax
0x14003662b  mov     [rsp+180h+var_130], rdx
0x140036630  lea     eax, [r15-1]
0x140036634  cmp     eax, 2
0x140036637  jbe     short loc_140036645
0x140036639  lea     rcx, aNameformatFltF; "(nameFormat == FLT_FILE_NAME_OPENED) ||"...
0x140036640  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140036645  call    cs:__imp_IoGetTopLevelIrp
0x14003664c  nop     dword ptr [rax+rax+00h]
0x140036651  test    rax, rax
0x140036654  jz      short loc_140036676
0x140036656  call    cs:__imp_IoGetTopLevelIrp
0x14003665d  nop     dword ptr [rax+rax+00h]
0x140036662  cmp     rax, 52336372h
0x140036668  jz      short loc_140036676
0x14003666a  lea     rcx, aIogettopleveli; "!IoGetTopLevelIrp() || SET.IsRecursive("...
0x140036671  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140036676  mov     r9, r14
0x140036679  mov     byte ptr [rbx], 1
0x14003667c  lea     r8, [rsp+180h+Context]
0x140036681  mov     [rsp+180h+Context], 0
0x14003668a  mov     rdx, r13
0x14003668d  mov     [rsp+180h+var_160], 0
0x140036696  mov     rcx, rdi
0x140036699  call    ?GetMappingTableForFileObject@Utils@UnionFs@@YAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@PEAPEAVUfsScratchMappingTable@2@AEAVStackEventTracer@2@PEAV?$unique_ptr@VUfsSiloCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?PsDereferenceSiloContext@@YAX0@Z@wil@@@wistd@@@Z; UnionFs::Utils::GetMappingTableForFileObject(_FLT_INSTANCE const &,_FILE_OBJECT const &,UnionFs::UfsScratchMappingTable * *,UnionFs::StackEventTracer &,wistd::unique_ptr<UnionFs::UfsSiloCtx,wil::function_deleter<void (*)(void *),&PsDereferenceSiloContext(void *)>> *)
0x14003669e  xor     edx, edx
0x1400366a0  mov     ebx, eax
0x1400366a2  test    eax, eax
0x1400366a4  jns     short loc_1400366D4
0x1400366a6  lea     rax, aPushGettingMap; "PUSH: Getting mapping table"
0x1400366ad  mov     r8, 2B4000F0084h; struct UnionFs::StackEventTracer *
0x1400366b7  lea     r9, aUnionfsUnionfs_24; "UnionFs::UnionFsFilter::GenerateFileNam"...
0x1400366be  mov     [rsp+180h+var_160], rax; char *
0x1400366c3  mov     rdx, r14; int
0x1400366c6  mov     ecx, ebx; this
0x1400366c8  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400366cd  mov     eax, ebx
0x1400366cf  jmp     loc_140036C42
0x1400366d4  cmp     [rsp+180h+Context], rdx
0x1400366d9  jz      loc_140036C6A
0x1400366df  test    dword ptr [r13+50h], 400000h
0x1400366e7  jnz     loc_140036C6A
0x1400366ed  cmp     [r13+18h], rdx
0x1400366f1  jnz     loc_140036823
0x1400366f7  test    r12, r12
0x1400366fa  jnz     short loc_14003673B
0x1400366fc  lea     rcx, aUnsafeNameQuer; "Unsafe name query in pre-create"
0x140036703  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140036708  lea     rax, aOriginUnsafeNa; "ORIGIN: Unsafe name query in pre-create"
0x14003670f  mov     r8, 137000F00A0h; struct UnionFs::StackEventTracer *
0x140036719  mov     esi, 0C000000Dh
0x14003671e  mov     [rsp+180h+var_160], rax; char *
0x140036723  mov     ecx, esi; this
0x140036725  lea     r9, aUnionfsUnionfs_24; "UnionFs::UnionFsFilter::GenerateFileNam"...
0x14003672c  mov     rdx, r14; int
0x14003672f  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140036734  mov     eax, esi
0x140036736  jmp     loc_140036C42
0x14003673b  mov     rax, [r12+10h]
0x140036740  mov     cl, [rax+4]
0x140036743  test    cl, cl
0x140036745  jz      short loc_14003675D
0x140036747  cmp     cl, 0F2h
0x14003674a  jz      short loc_14003675D
0x14003674c  cmp     cl, 0F9h
0x14003674f  jz      short loc_14003675D
0x140036751  lea     rcx, aCbdIopbMajorfu; "(Cbd->Iopb->MajorFunction == IRP_MJ_CRE"...
0x140036758  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x14003675d  sub     r15d, 1
0x140036761  jz      short loc_1400367D4
0x140036763  cmp     r15d, 1
0x140036767  jz      short loc_140036788
0x140036769  lea     rcx, aNonOpenedNorma; "Non-opened/normalized pre-create name q"...
0x140036770  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140036775  lea     rax, aOriginNonOpene; "ORIGIN: Non-opened/normalized pre-creat"...
0x14003677c  mov     r8, 13A000F00CBh
0x140036786  jmp     short loc_140036719
0x140036788  mov     r9, [rsp+180h+var_140]
0x14003678d  and     esi, 0FE00FF00h
0x140036793  mov     [rsp+180h+var_150], r12; struct _FLT_CALLBACK_DATA *
0x140036798  bts     esi, 19h
0x14003679c  mov     [rsp+180h+NameCtrl], r14; struct UnionFs::StackEventTracer *
0x1400367a1  mov     r8, r13; struct _FILE_OBJECT *
0x1400367a4  mov     [rsp+180h+var_160], r9; struct _FLT_NAME_CONTROL *
0x1400367a9  mov     rdx, rdi; struct _FLT_INSTANCE *
0x1400367ac  mov     r9d, esi; unsigned int
0x1400367af  call    ?GeneratePreCreateOpenedName@UnionFsFilter@UnionFs@@AEAAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@KPEAU_FLT_NAME_CONTROL@@AEAVStackEventTracer@2@PEAU_FLT_CALLBACK_DATA@@@Z; UnionFs::UnionFsFilter::GeneratePreCreateOpenedName(_FLT_INSTANCE const &,_FILE_OBJECT const &,ulong,_FLT_NAME_CONTROL *,UnionFs::StackEventTracer &,_FLT_CALLBACK_DATA *)
0x1400367b4  mov     ebx, eax
0x1400367b6  test    eax, eax
0x1400367b8  jns     loc_140036C40
0x1400367be  lea     rax, aPushGeneratepr_0; "PUSH: GeneratePreCreateOpenedName"
0x1400367c5  mov     r8, 138000F00B6h
0x1400367cf  jmp     loc_1400366B7
0x1400367d4  mov     r9, [rsp+180h+var_140]
0x1400367d9  and     esi, 0FE00FF00h
0x1400367df  mov     rcx, [rbp+80h+var_E0]; this
0x1400367e3  bts     esi, 19h
0x1400367e7  mov     [rsp+180h+var_150], r14; struct _UNICODE_STRING *
0x1400367ec  mov     r8, r13; struct _FILE_OBJECT *
0x1400367ef  mov     [rsp+180h+NameCtrl], r9; struct _FLT_NAME_CONTROL *
0x1400367f4  mov     rdx, rdi; struct _FLT_INSTANCE *
0x1400367f7  mov     r9, r12; struct _FLT_CALLBACK_DATA *
0x1400367fa  mov     dword ptr [rsp+180h+var_160], esi; unsigned int
0x1400367fe  call    ?GeneratePreCreateNormalizedName@UnionFsFilter@UnionFs@@AEAAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@AEAU_FLT_CALLBACK_DATA@@KPEAU_FLT_NAME_CONTROL@@AEAVStackEventTracer@2@@Z; UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName(_FLT_INSTANCE const &,_FILE_OBJECT const &,_FLT_CALLBACK_DATA &,ulong,_FLT_NAME_CONTROL *,UnionFs::StackEventTracer &)
0x140036803  mov     ebx, eax
0x140036805  test    eax, eax
0x140036807  jns     loc_140036C40
0x14003680d  lea     rax, aPushGeneratepr; "PUSH: GeneratePreCreateNormalizedName"
0x140036814  mov     r8, 139000F00C2h
0x14003681e  jmp     loc_1400366B7
0x140036823  mov     r9, r14
0x140036826  mov     [rsp+180h+Context], rdx
0x14003682b  lea     r8, [rsp+180h+Context]
0x140036830  mov     rcx, r13; FileObject
0x140036833  call    ?FltGet@UfsInstanceCtx@UnionFs@@SAJAEBU_FILE_OBJECT@@_NAEAV?$unique_ptr@VUfsInstanceCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@@Z; UnionFs::UfsInstanceCtx::FltGet(_FILE_OBJECT const &,bool,wistd::unique_ptr<UnionFs::UfsInstanceCtx,wil::function_deleter<void (*)(void *),&FltReleaseContext(void *)>> &,UnionFs::StackEventTracer &)
0x140036838  mov     ebx, eax
0x14003683a  test    eax, eax
0x14003683c  jns     short loc_140036884
0x14003683e  lea     rax, aPushGettingIns_1; "PUSH: Getting instance ctx from FileObj"...
0x140036845  mov     r8, 13F000F00DFh; struct UnionFs::StackEventTracer *
0x14003684f  lea     r9, aUnionfsUnionfs_24; "UnionFs::UnionFsFilter::GenerateFileNam"...
0x140036856  mov     [rsp+180h+var_160], rax; char *
0x14003685b  mov     rdx, r14; int
0x14003685e  mov     ecx, ebx; this
0x140036860  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140036865  mov     rcx, [rsp+180h+Context]; Context
0x14003686a  test    rcx, rcx
0x14003686d  jz      loc_1400366CD
0x140036873  call    cs:__imp_FltReleaseContext
0x14003687a  nop     dword ptr [rax+rax+00h]
0x14003687f  jmp     loc_1400366CD
0x140036884  xorps   xmm0, xmm0
0x140036887  mov     [rbp+80h+var_B8], 0
0x14003688b  xorps   xmm1, xmm1
0x14003688e  mov     [rbp+80h+var_40], 0
0x140036896  xor     edx, edx; Val
0x140036898  lea     rcx, [rbp+80h+var_C0]; void *
0x14003689c  mov     r8d, 88h; Size
0x1400368a2  movdqu  xmmword ptr [rbp+80h+var_D8], xmm0
0x1400368a7  movdqu  xmmword ptr [rbp-48h], xmm1
0x1400368ac  call    memset
0x1400368b1  mov     rdi, [rsp+180h+Context]
0x1400368b6  test    rdi, rdi
0x1400368b9  jnz     loc_140036960
0x1400368bf  xor     ebx, ebx
0x1400368c1  mov     rax, [rsp+180h+var_130]
0x1400368c6  lea     rdx, [rsp+180h+var_120]
0x1400368cb  mov     r9, [rsp+180h+var_140]
0x1400368d0  and     esi, 0FE00FF00h
0x1400368d6  or      esi, r15d
0x1400368d9  mov     [rsp+180h+var_120], r12
0x1400368de  mov     r8d, esi
0x1400368e1  mov     [rsp+180h+var_118], r13
0x1400368e6  mov     [rsp+180h+var_110], rax
0x1400368eb  mov     [rsp+180h+var_160], r14
0x1400368f0  call    ?PassthroughNameQuery@UnionFsFilter@UnionFs@@AEAAJUNameInfoParams@Utils@2@KPEAU_FLT_NAME_CONTROL@@AEAVStackEventTracer@2@@Z; UnionFs::UnionFsFilter::PassthroughNameQuery(UnionFs::Utils::NameInfoParams,ulong,_FLT_NAME_CONTROL *,UnionFs::StackEventTracer &)
0x1400368f5  mov     esi, eax
0x1400368f7  test    eax, eax
0x1400368f9  jns     loc_140036C0F
0x1400368ff  lea     rax, aPushPassingNam; "PUSH: Passing name query through"
0x140036906  mov     r8, 141000F0106h; struct UnionFs::StackEventTracer *
0x140036910  lea     r9, aUnionfsUnionfs_24; "UnionFs::UnionFsFilter::GenerateFileNam"...
0x140036917  mov     [rsp+180h+var_160], rax; char *
0x14003691c  mov     rdx, r14; int
0x14003691f  mov     ecx, esi; this
0x140036921  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140036926  lea     rcx, [rbp+80h+var_D8]; this
0x14003692a  call    ??1QueryInfoContext@UnionFs@@QEAA@XZ; UnionFs::QueryInfoContext::~QueryInfoContext(void)
0x14003692f  test    rbx, rbx
0x140036932  jz      short loc_140036943
0x140036934  mov     rcx, rbx; Context
0x140036937  call    cs:__imp_FltReleaseContext
0x14003693e  nop     dword ptr [rax+rax+00h]
0x140036943  test    rdi, rdi
0x140036946  jz      loc_140036734
0x14003694c  mov     rcx, rdi; Context
0x14003694f  call    cs:__imp_FltReleaseContext
0x140036956  nop     dword ptr [rax+rax+00h]
0x14003695b  jmp     loc_140036734
0x140036960  mov     rax, [rdi]
0x140036963  lea     r9, [rbp+80h+var_D8]; struct UnionFs::HandleCtxAndUnionWithRundown *
0x140036967  mov     rcx, rax; Instance
0x14003696a  mov     [rsp+180h+var_130], rax
0x14003696f  mov     rdx, r13; FileObject
0x140036972  mov     [rsp+180h+var_160], r14; struct UnionFs::StackEventTracer *
0x140036977  call    ?FltGet@UfsStreamHandleCtx@UnionFs@@SAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@_NAEAUHandleCtxAndUnionWithRundown@2@AEAVStackEventTracer@2@@Z; UnionFs::UfsStreamHandleCtx::FltGet(_FLT_INSTANCE const &,_FILE_OBJECT const &,bool,UnionFs::HandleCtxAndUnionWithRundown &,UnionFs::StackEventTracer &)
0x14003697c  xor     ecx, ecx; this
0x14003697e  mov     ebx, eax
0x140036980  test    eax, eax
0x140036982  jns     short loc_1400369C5
0x140036984  lea     rax, aPushGettingStr_0; "PUSH: Getting streamhandle ctx"
0x14003698b  mov     r8, 140000F00F6h; struct UnionFs::StackEventTracer *
0x140036995  lea     r9, aUnionfsUnionfs_24; "UnionFs::UnionFsFilter::GenerateFileNam"...
0x14003699c  mov     [rsp+180h+var_160], rax; char *
0x1400369a1  mov     rdx, r14; int
0x1400369a4  mov     ecx, ebx; this
0x1400369a6  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400369ab  lea     rcx, [rbp+80h+var_D8]; this
0x1400369af  call    ??1QueryInfoContext@UnionFs@@QEAA@XZ; UnionFs::QueryInfoContext::~QueryInfoContext(void)
0x1400369b4  test    rdi, rdi
0x1400369b7  jz      loc_1400366CD
0x1400369bd  mov     rcx, rdi
0x1400369c0  jmp     loc_140036873
0x1400369c5  mov     rbx, [rbp+80h+var_D8]
0x1400369c9  mov     [rbp+80h+var_D8], rcx
0x1400369cd  test    rbx, rbx
0x1400369d0  jz      loc_1400368C1
0x1400369d6  mov     eax, [rbx]
0x1400369d8  test    al, 1
0x1400369da  jz      loc_1400368C1
0x1400369e0  mov     rdx, [rsp+180h+var_130]; struct _FLT_INSTANCE *
0x1400369e5  lea     r9, [rbp+80h+var_100]; struct UnionFs::MapShadowFileObjectResults *
0x1400369e9  xor     eax, eax
0x1400369eb  mov     [rsp+180h+NameCtrl], rbx; char *
0x1400369f0  xorps   xmm0, xmm0
0x1400369f3  mov     [rbp+80h+var_FB], ax
0x1400369f7  mov     r8, r13; struct _FILE_OBJECT *
0x1400369fa  mov     [rbp+80h+var_F9], al
0x1400369fd  movdqu  xmmword ptr [rbp+80h+var_F8], xmm0
0x140036a02  mov     [rbp+80h+var_100], 3
0x140036a09  mov     [rbp+80h+var_FC], cl
0x140036a0c  mov     [rbp+80h+var_E8], rcx
0x140036a10  mov     [rsp+180h+var_160], r14; struct UnionFs::StackEventTracer *
0x140036a15  call    ?MapShadowFileObjectToBacking@UnionFsFilter@UnionFs@@QEAAJAEBU_FLT_INSTANCE@@AEAU_FILE_OBJECT@@AEAUMapShadowFileObjectResults@2@AEAVStackEventTracer@2@PEBVUfsStreamHandleCtx@2@@Z; UnionFs::UnionFsFilter::MapShadowFileObjectToBacking(_FLT_INSTANCE const &,_FILE_OBJECT &,UnionFs::MapShadowFileObjectResults &,UnionFs::StackEventTracer &,UnionFs::UfsStreamHandleCtx const *)
0x140036a1a  mov     r12d, eax
0x140036a1d  test    eax, eax
0x140036a1f  jns     short loc_140036A7D
0x140036a21  lea     rax, aPushMapshadowf; "PUSH: MapShadowFileObjectToBacking fail"...
0x140036a28  mov     r8, 235000F0117h; struct UnionFs::StackEventTracer *
0x140036a32  lea     r9, aUnionfsUnionfs_24; "UnionFs::UnionFsFilter::GenerateFileNam"...
0x140036a39  mov     [rsp+180h+var_160], rax; char *
0x140036a3e  mov     rdx, r14; int
0x140036a41  mov     ecx, r12d; this
0x140036a44  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140036a49  lea     rcx, [rbp+80h+var_D8]; this
0x140036a4d  call    ??1QueryInfoContext@UnionFs@@QEAA@XZ; UnionFs::QueryInfoContext::~QueryInfoContext(void)
0x140036a52  mov     rcx, rbx; Context
0x140036a55  call    cs:__imp_FltReleaseContext
0x140036a5c  nop     dword ptr [rax+rax+00h]
0x140036a61  test    rdi, rdi
0x140036a64  jz      short loc_140036A75
0x140036a66  mov     rcx, rdi; Context
0x140036a69  call    cs:__imp_FltReleaseContext
0x140036a70  nop     dword ptr [rax+rax+00h]
0x140036a75  mov     eax, r12d
0x140036a78  jmp     loc_140036C42
0x140036a7d  cmp     [rbp+80h+var_FC], 0
0x140036a81  jnz     short loc_140036AC9
0x140036a83  lea     rcx, aCouldnTMapSfoW; "Couldn't map SFO when handleCtx->IsShad"...
0x140036a8a  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140036a8f  lea     rax, aOriginCouldnTM; "ORIGIN: Couldn't map SFO when handleCtx"...
0x140036a96  mov     r8, 142000F0122h; struct UnionFs::StackEventTracer *
0x140036aa0  mov     esi, 0C00000E5h
0x140036aa5  mov     rdx, r14; int
0x140036aa8  mov     [rsp+180h+var_160], rax; char *
0x140036aad  lea     r9, aUnionfsUnionfs_24; "UnionFs::UnionFsFilter::GenerateFileNam"...
0x140036ab4  mov     ecx, esi; this
0x140036ab6  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140036abb  lea     rcx, [rbp+80h+var_D8]; this
0x140036abf  call    ??1QueryInfoContext@UnionFs@@QEAA@XZ; UnionFs::QueryInfoContext::~QueryInfoContext(void)
0x140036ac4  jmp     loc_140036934
0x140036ac9  sub     r15d, 1
0x140036acd  jz      loc_140036BBE
0x140036ad3  sub     r15d, 1
0x140036ad7  jz      loc_140036B5F
0x140036add  cmp     r15d, 1
0x140036ae1  jz      short loc_140036B07
0x140036ae3  lea     rcx, aFalse; "false"
0x140036aea  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140036aef  lea     rax, aOriginInvalidN; "ORIGIN: Invalid nameFormat"
0x140036af6  mov     r8, 147000F0161h
0x140036b00  mov     esi, 0C000000Dh
0x140036b05  jmp     short loc_140036AA5
0x140036b07  mov     rax, [rbp+80h+var_F8+8]
0x140036b0b  lea     rdx, [rsp+180h+var_120]
0x140036b10  mov     r9, [rsp+180h+var_140]
0x140036b15  and     esi, 0FE00FF03h
  ... truncated ...
```
