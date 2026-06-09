# UnionFs::UnionFsFilter::GenerateFileName(_FLT_INSTANCE const &,_FILE_OBJECT &,ulong,bool *,_FLT_NAME_CONTROL *,UnionFs::StackEventTracer &,_FLT_CALLBACK_DATA *)

- ea: `0x140036488`
- end: `0x140036b75`
- name: `?GenerateFileName@UnionFsFilter@UnionFs@@QEAAJAEBU_FLT_INSTANCE@@AEAU_FILE_OBJECT@@KPEA_NPEAU_FLT_NAME_CONTROL@@AEAVStackEventTracer@2@PEAU_FLT_CALLBACK_DATA@@@Z`
- size: `1773`
- prototype: `int(UnionFs::UnionFsFilter *__hidden this, const struct _FLT_INSTANCE *, struct _FILE_OBJECT *, unsigned int, bool *, struct _FLT_NAME_CONTROL *, struct UnionFs::StackEventTracer *, struct _FLT_CALLBACK_DATA *)`
- caller_count: `1`
- callee_count: `15`
- tags: `reparse_path, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140036b80`

## callees

- `0x140005ff8`
- `0x14000c008`
- `0x140027584`
- `0x1400279fc`
- `0x140036488`
- `0x140037924`
- `0x140037a14`
- `0x14003a064`
- `0x14003b4ec`
- `0x140056ac4`
- `0x140056afc`
- `0x14006efa8`
- `0x14007af90`
- `0x14007b7d0`
- `0x14007bc00`

## import_xrefs

- `ntoskrnl!IoGetTopLevelIrp` at `0x140036505`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140036516`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140036505`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140036516`
- `FLTMGR!FltReleaseContext` at `0x140036733`
- `FLTMGR!FltReleaseContext` at `0x1400367f7`
- `FLTMGR!FltReleaseContext` at `0x14003680f`
- `FLTMGR!FltReleaseContext` at `0x140036915`
- `FLTMGR!FltReleaseContext` at `0x140036929`
- `FLTMGR!FltReleaseContext` at `0x140036ae0`
- `FLTMGR!FltReleaseContext` at `0x140036af4`
- `FLTMGR!FltReleaseContext` at `0x140036733`
- `FLTMGR!FltReleaseContext` at `0x1400367f7`
- `FLTMGR!FltReleaseContext` at `0x14003680f`
- `FLTMGR!FltReleaseContext` at `0x140036915`
- `FLTMGR!FltReleaseContext` at `0x140036929`
- `FLTMGR!FltReleaseContext` at `0x140036ae0`
- `FLTMGR!FltReleaseContext` at `0x140036af4`

## string_xrefs

- `0x1400364f9`: `(nameFormat == FLT_FILE_NAME_OPENED) || (nameFormat == FLT_FILE_NAME_NORMALIZED) || (nameFormat == FLT_FILE_NAME_SHORT)`
- `0x1400365bc`: `Unsafe name query in pre-create`
- `0x1400365c8`: `ORIGIN: Unsafe name query in pre-create`
- `0x140036611`: `(Cbd->Iopb->MajorFunction == IRP_MJ_CREATE) || (Cbd->Iopb->MajorFunction == IRP_MJ_NETWORK_QUERY_OPEN) || (Cbd->Iopb->MajorFunction == IRP_MJ_QUERY_OPEN)`
- `0x14003667e`: `PUSH: GeneratePreCreateOpenedName`
- `0x1400366cd`: `PUSH: GeneratePreCreateNormalizedName`
- `0x140036629`: `Non-opened/normalized pre-create name query`
- `0x140036635`: `ORIGIN: Non-opened/normalized pre-create name query`
- `0x140036a52`: `PUSH: Generating post-create OPENED name`
- `0x140036ab1`: `PUSH: Generating post-create NORMALIZED name`

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
0x140036488  mov     [rsp-8+arg_0], rbx
0x14003648d  push    rbp
0x14003648e  push    rsi
0x14003648f  push    rdi
0x140036490  push    r12
0x140036492  push    r13
0x140036494  push    r14
0x140036496  push    r15
0x140036498  lea     rbp, [rsp-50h]
0x14003649d  sub     rsp, 150h
0x1400364a4  mov     rax, cs:__security_cookie
0x1400364ab  xor     rax, rsp
0x1400364ae  mov     [rbp+80h+var_38], rax
0x1400364b2  mov     rax, [rbp+80h+arg_28]
0x1400364b9  mov     esi, r9d
0x1400364bc  mov     rbx, [rbp+80h+arg_20]
0x1400364c3  mov     r13, r8
0x1400364c6  mov     r14, [rbp+80h+arg_30]
0x1400364cd  mov     rdi, rdx
0x1400364d0  mov     r12, [rbp+80h+arg_38]
0x1400364d7  mov     [rsp+180h+var_140], rax
0x1400364dc  mov     rax, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x1400364e3  movzx   r15d, r9b
0x1400364e7  mov     [rbp+80h+var_E0], rax
0x1400364eb  mov     [rsp+180h+var_130], rdx
0x1400364f0  lea     eax, [r15-1]
0x1400364f4  cmp     eax, 2
0x1400364f7  jbe     short loc_140036505
0x1400364f9  lea     rcx, aNameformatFltF; "(nameFormat == FLT_FILE_NAME_OPENED) ||"...
0x140036500  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140036505  call    cs:__imp_IoGetTopLevelIrp
0x14003650c  nop     dword ptr [rax+rax+00h]
0x140036511  test    rax, rax
0x140036514  jz      short loc_140036536
0x140036516  call    cs:__imp_IoGetTopLevelIrp
0x14003651d  nop     dword ptr [rax+rax+00h]
0x140036522  cmp     rax, 52336372h
0x140036528  jz      short loc_140036536
0x14003652a  lea     rcx, aIogettopleveli; "!IoGetTopLevelIrp() || SET.IsRecursive("...
0x140036531  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140036536  mov     r9, r14
0x140036539  mov     byte ptr [rbx], 1
0x14003653c  lea     r8, [rsp+180h+Context]
0x140036541  mov     [rsp+180h+Context], 0
0x14003654a  mov     rdx, r13
0x14003654d  mov     [rsp+180h+var_160], 0
0x140036556  mov     rcx, rdi
0x140036559  call    ?GetMappingTableForFileObject@Utils@UnionFs@@YAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@PEAPEAVUfsScratchMappingTable@2@AEAVStackEventTracer@2@PEAV?$unique_ptr@VUfsSiloCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?PsDereferenceSiloContext@@YAX0@Z@wil@@@wistd@@@Z; UnionFs::Utils::GetMappingTableForFileObject(_FLT_INSTANCE const &,_FILE_OBJECT const &,UnionFs::UfsScratchMappingTable * *,UnionFs::StackEventTracer &,wistd::unique_ptr<UnionFs::UfsSiloCtx,wil::function_deleter<void (*)(void *),&PsDereferenceSiloContext(void *)>> *)
0x14003655e  xor     edx, edx
0x140036560  mov     ebx, eax
0x140036562  test    eax, eax
0x140036564  jns     short loc_140036594
0x140036566  lea     rax, aPushGettingMap; "PUSH: Getting mapping table"
0x14003656d  mov     r8, 2B4000F0084h; struct UnionFs::StackEventTracer *
0x140036577  lea     r9, aUnionfsUnionfs_23; "UnionFs::UnionFsFilter::GenerateFileNam"...
0x14003657e  mov     [rsp+180h+var_160], rax; char *
0x140036583  mov     rdx, r14; int
0x140036586  mov     ecx, ebx; this
0x140036588  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14003658d  mov     eax, ebx
0x14003658f  jmp     loc_140036B02
0x140036594  cmp     [rsp+180h+Context], rdx
0x140036599  jz      loc_140036B2A
0x14003659f  test    dword ptr [r13+50h], 400000h
0x1400365a7  jnz     loc_140036B2A
0x1400365ad  cmp     [r13+18h], rdx
0x1400365b1  jnz     loc_1400366E3
0x1400365b7  test    r12, r12
0x1400365ba  jnz     short loc_1400365FB
0x1400365bc  lea     rcx, aUnsafeNameQuer; "Unsafe name query in pre-create"
0x1400365c3  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x1400365c8  lea     rax, aOriginUnsafeNa; "ORIGIN: Unsafe name query in pre-create"
0x1400365cf  mov     r8, 137000F00A0h; struct UnionFs::StackEventTracer *
0x1400365d9  mov     esi, 0C000000Dh
0x1400365de  mov     [rsp+180h+var_160], rax; char *
0x1400365e3  mov     ecx, esi; this
0x1400365e5  lea     r9, aUnionfsUnionfs_23; "UnionFs::UnionFsFilter::GenerateFileNam"...
0x1400365ec  mov     rdx, r14; int
0x1400365ef  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400365f4  mov     eax, esi
0x1400365f6  jmp     loc_140036B02
0x1400365fb  mov     rax, [r12+10h]
0x140036600  mov     cl, [rax+4]
0x140036603  test    cl, cl
0x140036605  jz      short loc_14003661D
0x140036607  cmp     cl, 0F2h
0x14003660a  jz      short loc_14003661D
0x14003660c  cmp     cl, 0F9h
0x14003660f  jz      short loc_14003661D
0x140036611  lea     rcx, aCbdIopbMajorfu; "(Cbd->Iopb->MajorFunction == IRP_MJ_CRE"...
0x140036618  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x14003661d  sub     r15d, 1
0x140036621  jz      short loc_140036694
0x140036623  cmp     r15d, 1
0x140036627  jz      short loc_140036648
0x140036629  lea     rcx, aNonOpenedNorma; "Non-opened/normalized pre-create name q"...
0x140036630  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140036635  lea     rax, aOriginNonOpene; "ORIGIN: Non-opened/normalized pre-creat"...
0x14003663c  mov     r8, 13A000F00CBh
0x140036646  jmp     short loc_1400365D9
0x140036648  mov     r9, [rsp+180h+var_140]
0x14003664d  and     esi, 0FE00FF00h
0x140036653  mov     [rsp+180h+var_150], r12; struct _FLT_CALLBACK_DATA *
0x140036658  bts     esi, 19h
0x14003665c  mov     [rsp+180h+NameCtrl], r14; struct UnionFs::StackEventTracer *
0x140036661  mov     r8, r13; struct _FILE_OBJECT *
0x140036664  mov     [rsp+180h+var_160], r9; struct _FLT_NAME_CONTROL *
0x140036669  mov     rdx, rdi; struct _FLT_INSTANCE *
0x14003666c  mov     r9d, esi; unsigned int
0x14003666f  call    ?GeneratePreCreateOpenedName@UnionFsFilter@UnionFs@@AEAAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@KPEAU_FLT_NAME_CONTROL@@AEAVStackEventTracer@2@PEAU_FLT_CALLBACK_DATA@@@Z; UnionFs::UnionFsFilter::GeneratePreCreateOpenedName(_FLT_INSTANCE const &,_FILE_OBJECT const &,ulong,_FLT_NAME_CONTROL *,UnionFs::StackEventTracer &,_FLT_CALLBACK_DATA *)
0x140036674  mov     ebx, eax
0x140036676  test    eax, eax
0x140036678  jns     loc_140036B00
0x14003667e  lea     rax, aPushGeneratepr_0; "PUSH: GeneratePreCreateOpenedName"
0x140036685  mov     r8, 138000F00B6h
0x14003668f  jmp     loc_140036577
0x140036694  mov     r9, [rsp+180h+var_140]
0x140036699  and     esi, 0FE00FF00h
0x14003669f  mov     rcx, [rbp+80h+var_E0]; this
0x1400366a3  bts     esi, 19h
0x1400366a7  mov     [rsp+180h+var_150], r14; struct _UNICODE_STRING *
0x1400366ac  mov     r8, r13; struct _FILE_OBJECT *
0x1400366af  mov     [rsp+180h+NameCtrl], r9; struct _FLT_NAME_CONTROL *
0x1400366b4  mov     rdx, rdi; struct _FLT_INSTANCE *
0x1400366b7  mov     r9, r12; struct _FLT_CALLBACK_DATA *
0x1400366ba  mov     dword ptr [rsp+180h+var_160], esi; unsigned int
0x1400366be  call    ?GeneratePreCreateNormalizedName@UnionFsFilter@UnionFs@@AEAAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@AEAU_FLT_CALLBACK_DATA@@KPEAU_FLT_NAME_CONTROL@@AEAVStackEventTracer@2@@Z; UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName(_FLT_INSTANCE const &,_FILE_OBJECT const &,_FLT_CALLBACK_DATA &,ulong,_FLT_NAME_CONTROL *,UnionFs::StackEventTracer &)
0x1400366c3  mov     ebx, eax
0x1400366c5  test    eax, eax
0x1400366c7  jns     loc_140036B00
0x1400366cd  lea     rax, aPushGeneratepr; "PUSH: GeneratePreCreateNormalizedName"
0x1400366d4  mov     r8, 139000F00C2h
0x1400366de  jmp     loc_140036577
0x1400366e3  mov     r9, r14
0x1400366e6  mov     [rsp+180h+Context], rdx
0x1400366eb  lea     r8, [rsp+180h+Context]
0x1400366f0  mov     rcx, r13; FileObject
0x1400366f3  call    ?FltGet@UfsInstanceCtx@UnionFs@@SAJAEBU_FILE_OBJECT@@_NAEAV?$unique_ptr@VUfsInstanceCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@@Z; UnionFs::UfsInstanceCtx::FltGet(_FILE_OBJECT const &,bool,wistd::unique_ptr<UnionFs::UfsInstanceCtx,wil::function_deleter<void (*)(void *),&FltReleaseContext(void *)>> &,UnionFs::StackEventTracer &)
0x1400366f8  mov     ebx, eax
0x1400366fa  test    eax, eax
0x1400366fc  jns     short loc_140036744
0x1400366fe  lea     rax, aPushGettingIns_1; "PUSH: Getting instance ctx from FileObj"...
0x140036705  mov     r8, 13F000F00DFh; struct UnionFs::StackEventTracer *
0x14003670f  lea     r9, aUnionfsUnionfs_23; "UnionFs::UnionFsFilter::GenerateFileNam"...
0x140036716  mov     [rsp+180h+var_160], rax; char *
0x14003671b  mov     rdx, r14; int
0x14003671e  mov     ecx, ebx; this
0x140036720  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140036725  mov     rcx, [rsp+180h+Context]; Context
0x14003672a  test    rcx, rcx
0x14003672d  jz      loc_14003658D
0x140036733  call    cs:__imp_FltReleaseContext
0x14003673a  nop     dword ptr [rax+rax+00h]
0x14003673f  jmp     loc_14003658D
0x140036744  xorps   xmm0, xmm0
0x140036747  mov     [rbp+80h+var_B8], 0
0x14003674b  xorps   xmm1, xmm1
0x14003674e  mov     [rbp+80h+var_40], 0
0x140036756  xor     edx, edx; Val
0x140036758  lea     rcx, [rbp+80h+var_C0]; void *
0x14003675c  mov     r8d, 88h; Size
0x140036762  movdqu  xmmword ptr [rbp+80h+var_D8], xmm0
0x140036767  movdqu  xmmword ptr [rbp-48h], xmm1
0x14003676c  call    memset
0x140036771  mov     rdi, [rsp+180h+Context]
0x140036776  test    rdi, rdi
0x140036779  jnz     loc_140036820
0x14003677f  xor     ebx, ebx
0x140036781  mov     rax, [rsp+180h+var_130]
0x140036786  lea     rdx, [rsp+180h+var_120]
0x14003678b  mov     r9, [rsp+180h+var_140]
0x140036790  and     esi, 0FE00FF00h
0x140036796  or      esi, r15d
0x140036799  mov     [rsp+180h+var_120], r12
0x14003679e  mov     r8d, esi
0x1400367a1  mov     [rsp+180h+var_118], r13
0x1400367a6  mov     [rsp+180h+var_110], rax
0x1400367ab  mov     [rsp+180h+var_160], r14
0x1400367b0  call    ?PassthroughNameQuery@UnionFsFilter@UnionFs@@AEAAJUNameInfoParams@Utils@2@KPEAU_FLT_NAME_CONTROL@@AEAVStackEventTracer@2@@Z; UnionFs::UnionFsFilter::PassthroughNameQuery(UnionFs::Utils::NameInfoParams,ulong,_FLT_NAME_CONTROL *,UnionFs::StackEventTracer &)
0x1400367b5  mov     esi, eax
0x1400367b7  test    eax, eax
0x1400367b9  jns     loc_140036ACF
0x1400367bf  lea     rax, aPushPassingNam; "PUSH: Passing name query through"
0x1400367c6  mov     r8, 141000F0106h; struct UnionFs::StackEventTracer *
0x1400367d0  lea     r9, aUnionfsUnionfs_23; "UnionFs::UnionFsFilter::GenerateFileNam"...
0x1400367d7  mov     [rsp+180h+var_160], rax; char *
0x1400367dc  mov     rdx, r14; int
0x1400367df  mov     ecx, esi; this
0x1400367e1  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400367e6  lea     rcx, [rbp+80h+var_D8]; this
0x1400367ea  call    ??1QueryInfoContext@UnionFs@@QEAA@XZ; UnionFs::QueryInfoContext::~QueryInfoContext(void)
0x1400367ef  test    rbx, rbx
0x1400367f2  jz      short loc_140036803
0x1400367f4  mov     rcx, rbx; Context
0x1400367f7  call    cs:__imp_FltReleaseContext
0x1400367fe  nop     dword ptr [rax+rax+00h]
0x140036803  test    rdi, rdi
0x140036806  jz      loc_1400365F4
0x14003680c  mov     rcx, rdi; Context
0x14003680f  call    cs:__imp_FltReleaseContext
0x140036816  nop     dword ptr [rax+rax+00h]
0x14003681b  jmp     loc_1400365F4
0x140036820  mov     rax, [rdi]
0x140036823  lea     r9, [rbp+80h+var_D8]; struct UnionFs::HandleCtxAndUnionWithRundown *
0x140036827  mov     rcx, rax; Instance
0x14003682a  mov     [rsp+180h+var_130], rax
0x14003682f  mov     rdx, r13; FileObject
0x140036832  mov     [rsp+180h+var_160], r14; struct UnionFs::StackEventTracer *
0x140036837  call    ?FltGet@UfsStreamHandleCtx@UnionFs@@SAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@_NAEAUHandleCtxAndUnionWithRundown@2@AEAVStackEventTracer@2@@Z; UnionFs::UfsStreamHandleCtx::FltGet(_FLT_INSTANCE const &,_FILE_OBJECT const &,bool,UnionFs::HandleCtxAndUnionWithRundown &,UnionFs::StackEventTracer &)
0x14003683c  xor     ecx, ecx; this
0x14003683e  mov     ebx, eax
0x140036840  test    eax, eax
0x140036842  jns     short loc_140036885
0x140036844  lea     rax, aPushGettingStr_0; "PUSH: Getting streamhandle ctx"
0x14003684b  mov     r8, 140000F00F6h; struct UnionFs::StackEventTracer *
0x140036855  lea     r9, aUnionfsUnionfs_23; "UnionFs::UnionFsFilter::GenerateFileNam"...
0x14003685c  mov     [rsp+180h+var_160], rax; char *
0x140036861  mov     rdx, r14; int
0x140036864  mov     ecx, ebx; this
0x140036866  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14003686b  lea     rcx, [rbp+80h+var_D8]; this
0x14003686f  call    ??1QueryInfoContext@UnionFs@@QEAA@XZ; UnionFs::QueryInfoContext::~QueryInfoContext(void)
0x140036874  test    rdi, rdi
0x140036877  jz      loc_14003658D
0x14003687d  mov     rcx, rdi
0x140036880  jmp     loc_140036733
0x140036885  mov     rbx, [rbp+80h+var_D8]
0x140036889  mov     [rbp+80h+var_D8], rcx
0x14003688d  test    rbx, rbx
0x140036890  jz      loc_140036781
0x140036896  mov     eax, [rbx]
0x140036898  test    al, 1
0x14003689a  jz      loc_140036781
0x1400368a0  mov     rdx, [rsp+180h+var_130]; struct _FLT_INSTANCE *
0x1400368a5  lea     r9, [rbp+80h+var_100]; struct UnionFs::MapShadowFileObjectResults *
0x1400368a9  xor     eax, eax
0x1400368ab  mov     [rsp+180h+NameCtrl], rbx; char *
0x1400368b0  xorps   xmm0, xmm0
0x1400368b3  mov     [rbp+80h+var_FB], ax
0x1400368b7  mov     r8, r13; struct _FILE_OBJECT *
0x1400368ba  mov     [rbp+80h+var_F9], al
0x1400368bd  movdqu  xmmword ptr [rbp+80h+var_F8], xmm0
0x1400368c2  mov     [rbp+80h+var_100], 3
0x1400368c9  mov     [rbp+80h+var_FC], cl
0x1400368cc  mov     [rbp+80h+var_E8], rcx
0x1400368d0  mov     [rsp+180h+var_160], r14; struct UnionFs::StackEventTracer *
0x1400368d5  call    ?MapShadowFileObjectToBacking@UnionFsFilter@UnionFs@@QEAAJAEBU_FLT_INSTANCE@@AEAU_FILE_OBJECT@@AEAUMapShadowFileObjectResults@2@AEAVStackEventTracer@2@PEBVUfsStreamHandleCtx@2@@Z; UnionFs::UnionFsFilter::MapShadowFileObjectToBacking(_FLT_INSTANCE const &,_FILE_OBJECT &,UnionFs::MapShadowFileObjectResults &,UnionFs::StackEventTracer &,UnionFs::UfsStreamHandleCtx const *)
0x1400368da  mov     r12d, eax
0x1400368dd  test    eax, eax
0x1400368df  jns     short loc_14003693D
0x1400368e1  lea     rax, aPushMapshadowf; "PUSH: MapShadowFileObjectToBacking fail"...
0x1400368e8  mov     r8, 235000F0117h; struct UnionFs::StackEventTracer *
0x1400368f2  lea     r9, aUnionfsUnionfs_23; "UnionFs::UnionFsFilter::GenerateFileNam"...
0x1400368f9  mov     [rsp+180h+var_160], rax; char *
0x1400368fe  mov     rdx, r14; int
0x140036901  mov     ecx, r12d; this
0x140036904  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140036909  lea     rcx, [rbp+80h+var_D8]; this
0x14003690d  call    ??1QueryInfoContext@UnionFs@@QEAA@XZ; UnionFs::QueryInfoContext::~QueryInfoContext(void)
0x140036912  mov     rcx, rbx; Context
0x140036915  call    cs:__imp_FltReleaseContext
0x14003691c  nop     dword ptr [rax+rax+00h]
0x140036921  test    rdi, rdi
0x140036924  jz      short loc_140036935
0x140036926  mov     rcx, rdi; Context
0x140036929  call    cs:__imp_FltReleaseContext
0x140036930  nop     dword ptr [rax+rax+00h]
0x140036935  mov     eax, r12d
0x140036938  jmp     loc_140036B02
0x14003693d  cmp     [rbp+80h+var_FC], 0
0x140036941  jnz     short loc_140036989
0x140036943  lea     rcx, aCouldnTMapSfoW; "Couldn't map SFO when handleCtx->IsShad"...
0x14003694a  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x14003694f  lea     rax, aOriginCouldnTM; "ORIGIN: Couldn't map SFO when handleCtx"...
0x140036956  mov     r8, 142000F0122h; struct UnionFs::StackEventTracer *
0x140036960  mov     esi, 0C00000E5h
0x140036965  mov     rdx, r14; int
0x140036968  mov     [rsp+180h+var_160], rax; char *
0x14003696d  lea     r9, aUnionfsUnionfs_23; "UnionFs::UnionFsFilter::GenerateFileNam"...
0x140036974  mov     ecx, esi; this
0x140036976  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14003697b  lea     rcx, [rbp+80h+var_D8]; this
0x14003697f  call    ??1QueryInfoContext@UnionFs@@QEAA@XZ; UnionFs::QueryInfoContext::~QueryInfoContext(void)
0x140036984  jmp     loc_1400367F4
0x140036989  sub     r15d, 1
0x14003698d  jz      loc_140036A7E
0x140036993  sub     r15d, 1
0x140036997  jz      loc_140036A1F
0x14003699d  cmp     r15d, 1
0x1400369a1  jz      short loc_1400369C7
0x1400369a3  lea     rcx, aFalse; "false"
0x1400369aa  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x1400369af  lea     rax, aOriginInvalidN; "ORIGIN: Invalid nameFormat"
0x1400369b6  mov     r8, 147000F0161h
0x1400369c0  mov     esi, 0C000000Dh
0x1400369c5  jmp     short loc_140036965
0x1400369c7  mov     rax, [rbp+80h+var_F8+8]
0x1400369cb  lea     rdx, [rsp+180h+var_120]
0x1400369d0  mov     r9, [rsp+180h+var_140]
0x1400369d5  and     esi, 0FE00FF03h
  ... truncated ...
```
