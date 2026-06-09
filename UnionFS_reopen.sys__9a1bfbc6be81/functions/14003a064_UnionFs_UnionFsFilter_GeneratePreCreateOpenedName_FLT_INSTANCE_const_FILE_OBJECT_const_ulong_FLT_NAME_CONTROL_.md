# UnionFs::UnionFsFilter::GeneratePreCreateOpenedName(_FLT_INSTANCE const &,_FILE_OBJECT const &,ulong,_FLT_NAME_CONTROL *,UnionFs::StackEventTracer &,_FLT_CALLBACK_DATA *)

- ea: `0x14003a064`
- end: `0x14003a520`
- name: `?GeneratePreCreateOpenedName@UnionFsFilter@UnionFs@@AEAAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@KPEAU_FLT_NAME_CONTROL@@AEAVStackEventTracer@2@PEAU_FLT_CALLBACK_DATA@@@Z`
- size: `1212`
- prototype: `int(UnionFs::UnionFsFilter *__hidden this, const struct _FLT_INSTANCE *, const struct _FILE_OBJECT *, unsigned int, struct _FLT_NAME_CONTROL *, struct UnionFs::StackEventTracer *, struct _FLT_CALLBACK_DATA *)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x140036488`

## callees

- `0x140005ff8`
- `0x14000c008`
- `0x140027584`
- `0x1400279fc`
- `0x140037924`
- `0x14003a064`
- `0x14003b4ec`
- `0x140056a50`
- `0x140056afc`
- `0x14007af90`
- `0x14007b7d0`
- `0x14007bc00`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeToString` at `0x14003a3de`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14003a3de`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14003a3f8`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14003a3f8`
- `FLTMGR!FltCheckAndGrowNameControl` at `0x14003a38a`
- `FLTMGR!FltCheckAndGrowNameControl` at `0x14003a38a`
- `FLTMGR!FltReleaseContext` at `0x14003a188`
- `FLTMGR!FltReleaseContext` at `0x14003a21f`
- `FLTMGR!FltReleaseContext` at `0x14003a2c6`
- `FLTMGR!FltReleaseContext` at `0x14003a2e4`
- `FLTMGR!FltReleaseContext` at `0x14003a495`
- `FLTMGR!FltReleaseContext` at `0x14003a4b3`
- `FLTMGR!FltReleaseContext` at `0x14003a4cc`
- `FLTMGR!FltReleaseContext` at `0x14003a4ea`
- `FLTMGR!FltReleaseContext` at `0x14003a188`
- `FLTMGR!FltReleaseContext` at `0x14003a21f`
- `FLTMGR!FltReleaseContext` at `0x14003a2c6`
- `FLTMGR!FltReleaseContext` at `0x14003a2e4`
- `FLTMGR!FltReleaseContext` at `0x14003a495`
- `FLTMGR!FltReleaseContext` at `0x14003a4b3`
- `FLTMGR!FltReleaseContext` at `0x14003a4cc`
- `FLTMGR!FltReleaseContext` at `0x14003a4ea`

## string_xrefs

- `0x14003a0be`: `FileObject must not be open`
- `0x14003a111`: `PUSH: Pass-through for non-relative open`
- `0x14003a122`: `UnionFs::UnionFsFilter::GeneratePreCreateOpenedName`
- `0x14003a168`: `UnionFs::UnionFsFilter::GeneratePreCreateOpenedName`
- `0x14003a1f7`: `UnionFs::UnionFsFilter::GeneratePreCreateOpenedName`
- `0x14003a2ac`: `UnionFs::UnionFsFilter::GeneratePreCreateOpenedName`
- `0x14003a353`: `UnionFs::UnionFsFilter::GeneratePreCreateOpenedName`
- `0x14003a3ae`: `UnionFs::UnionFsFilter::GeneratePreCreateOpenedName`
- `0x14003a476`: `UnionFs::UnionFsFilter::GeneratePreCreateOpenedName`
- `0x14003a465`: `PUSH: Pass-through for relative open`
- `0x14003a342`: `PUSH: Generating opened name for related FO`

## pseudocode

```c
__int64 __fastcall UnionFs::UnionFsFilter::GeneratePreCreateOpenedName(
        UnionFs::UnionFsFilter *this,
        const struct _FLT_INSTANCE *a2,
        const struct _FILE_OBJECT *a3,
        int a4,
        PFLT_NAME_CONTROL NameCtrl,
        struct UnionFs::StackEventTracer *a6,
        struct _FLT_CALLBACK_DATA *a7)
{
  struct _FLT_CALLBACK_DATA *v7; // rax
  struct _FILE_OBJECT *RelatedFileObject; // rcx
  int v11; // ebx
  __int64 v13; // rcx
  int v14; // r14d
  const char *v15; // [rsp+28h] [rbp-D8h]
  struct _FLT_CALLBACK_DATA *v16; // [rsp+40h] [rbp-C0h] BYREF
  struct _FILE_OBJECT *v17[2]; // [rsp+48h] [rbp-B8h]
  PFLT_CONTEXT Context; // [rsp+60h] [rbp-A0h]
  struct _FLT_CALLBACK_DATA *v19; // [rsp+68h] [rbp-98h]
  const struct _FLT_INSTANCE *v20; // [rsp+70h] [rbp-90h]
  PFLT_CONTEXT v21[2]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v22; // [rsp+88h] [rbp-78h]
  _QWORD v23[17]; // [rsp+90h] [rbp-70h] BYREF

  v7 = a7;
  v20 = a2;
  v19 = a7;
  if ( a3->FsContext )
  {
    MicrosoftTelemetryAssertTriggeredMsgKM("FileObject must not be open");
    v7 = v19;
  }
  RelatedFileObject = a3->RelatedFileObject;
  if ( RelatedFileObject )
  {
    Context = 0;
    v11 = UnionFs::UfsInstanceCtx::FltGet(RelatedFileObject);
    if ( v11 < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v11,
        (int)a6,
        (struct UnionFs::StackEventTracer *)0x158000F02A2LL,
        (unsigned __int64)"UnionFs::UnionFsFilter::GeneratePreCreateOpenedName",
        "PUSH: Getting instance ctx from FileObject",
        v15);
      return (unsigned int)v11;
    }
    *(_OWORD *)v21 = 0;
    v22 = 0;
    memset(v23, 0, sizeof(v23));
    v21[0] = 0;
    v16 = v19;
    v17[0] = 0;
    v17[1] = 0;
    v14 = UnionFs::UnionFsFilter::PassthroughNameQuery(v13, &v16, a4 & 0xFF00FF00 | 2, NameCtrl, a6);
    if ( v14 < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v14,
        (int)a6,
        (struct UnionFs::StackEventTracer *)0x15A000F02C4LL,
        (unsigned __int64)"UnionFs::UnionFsFilter::GeneratePreCreateOpenedName",
        "PUSH: Pass-through for relative open",
        v15);
      UnionFs::QueryInfoContext::~QueryInfoContext((UnionFs::QueryInfoContext *)v21);
      return (unsigned int)v14;
    }
    UnionFs::QueryInfoContext::~QueryInfoContext((UnionFs::QueryInfoContext *)v21);
  }
  else
  {
    v16 = v7;
    v17[0] = 0;
    v17[1] = 0;
    v11 = UnionFs::UnionFsFilter::PassthroughNameQuery(0, &v16, a4 & 0xFF00FF00 | 2, NameCtrl, a6);
    if ( v11 < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v11,
        (int)a6,
        (struct UnionFs::StackEventTracer *)0x157000F0293LL,
        (unsigned __int64)"UnionFs::UnionFsFilter::GeneratePreCreateOpenedName",
        "PUSH: Pass-through for non-relative open",
        v15);
      return (unsigned int)v11;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14003a064  mov     [rsp-8+arg_0], rbx
0x14003a069  push    rbp
0x14003a06a  push    rsi
0x14003a06b  push    rdi
0x14003a06c  push    r12
0x14003a06e  push    r13
0x14003a070  push    r14
0x14003a072  push    r15
0x14003a074  lea     rbp, [rsp-20h]
0x14003a079  sub     rsp, 120h
0x14003a080  mov     rax, cs:__security_cookie
0x14003a087  xor     rax, rsp
0x14003a08a  mov     [rbp+50h+var_38], rax
0x14003a08e  mov     rax, [rbp+50h+arg_30]
0x14003a095  xor     edi, edi
0x14003a097  mov     r14d, r9d
0x14003a09a  mov     r13, [rbp+50h+NameCtrl]
0x14003a0a1  mov     r15, r8
0x14003a0a4  mov     rsi, [rbp+50h+arg_28]
0x14003a0ab  mov     r12, rdx
0x14003a0ae  mov     [rsp+150h+var_E0], rdx
0x14003a0b3  mov     [rsp+150h+var_E8], rax
0x14003a0b8  cmp     [r8+18h], rdi
0x14003a0bc  jz      short loc_14003A0CF
0x14003a0be  lea     rcx, aFileobjectMust; "FileObject must not be open"
0x14003a0c5  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x14003a0ca  mov     rax, [rsp+150h+var_E8]
0x14003a0cf  mov     rcx, [r15+40h]; FileObject
0x14003a0d3  test    rcx, rcx
0x14003a0d6  jnz     short loc_14003A13F
0x14003a0d8  and     r14d, 0FF00FF02h
0x14003a0df  mov     [rsp+150h+var_110], rax
0x14003a0e4  or      r14d, 2
0x14003a0e8  mov     [rsp+150h+var_108], rdi
0x14003a0ed  mov     r8d, r14d
0x14003a0f0  mov     [rsp+150h+var_108+8], rdi
0x14003a0f5  mov     r9, r13
0x14003a0f8  mov     [rsp+150h+var_130], rsi
0x14003a0fd  lea     rdx, [rsp+150h+var_110]
0x14003a102  call    ?PassthroughNameQuery@UnionFsFilter@UnionFs@@AEAAJUNameInfoParams@Utils@2@KPEAU_FLT_NAME_CONTROL@@AEAVStackEventTracer@2@@Z; UnionFs::UnionFsFilter::PassthroughNameQuery(UnionFs::Utils::NameInfoParams,ulong,_FLT_NAME_CONTROL *,UnionFs::StackEventTracer &)
0x14003a107  mov     ebx, eax
0x14003a109  test    eax, eax
0x14003a10b  jns     loc_14003A4F6
0x14003a111  lea     rax, aPushPassThroug_0; "PUSH: Pass-through for non-relative ope"...
0x14003a118  mov     r8, 157000F0293h; struct UnionFs::StackEventTracer *
0x14003a122  lea     r9, aUnionfsUnionfs_7; "UnionFs::UnionFsFilter::GeneratePreCrea"...
0x14003a129  mov     [rsp+150h+var_130], rax; char *
0x14003a12e  mov     rdx, rsi; int
0x14003a131  mov     ecx, ebx; this
0x14003a133  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14003a138  mov     eax, ebx
0x14003a13a  jmp     loc_14003A4F8
0x14003a13f  mov     r9, rsi
0x14003a142  mov     [rsp+150h+Context], rdi
0x14003a147  lea     r8, [rsp+150h+Context]
0x14003a14c  call    ?FltGet@UfsInstanceCtx@UnionFs@@SAJAEBU_FILE_OBJECT@@_NAEAV?$unique_ptr@VUfsInstanceCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@@Z; UnionFs::UfsInstanceCtx::FltGet(_FILE_OBJECT const &,bool,wistd::unique_ptr<UnionFs::UfsInstanceCtx,wil::function_deleter<void (*)(void *),&FltReleaseContext(void *)>> &,UnionFs::StackEventTracer &)
0x14003a151  mov     ebx, eax
0x14003a153  test    eax, eax
0x14003a155  jns     short loc_14003A196
0x14003a157  lea     rax, aPushGettingIns_1; "PUSH: Getting instance ctx from FileObj"...
0x14003a15e  mov     r8, 158000F02A2h; struct UnionFs::StackEventTracer *
0x14003a168  lea     r9, aUnionfsUnionfs_7; "UnionFs::UnionFsFilter::GeneratePreCrea"...
0x14003a16f  mov     [rsp+150h+var_130], rax; char *
0x14003a174  mov     rdx, rsi; int
0x14003a177  mov     ecx, ebx; this
0x14003a179  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14003a17e  mov     rcx, [rsp+150h+Context]; Context
0x14003a183  test    rcx, rcx
0x14003a186  jz      short loc_14003A138
0x14003a188  call    cs:__imp_FltReleaseContext
0x14003a18f  nop     dword ptr [rax+rax+00h]
0x14003a194  jmp     short loc_14003A138
0x14003a196  xorps   xmm0, xmm0
0x14003a199  mov     [rbp+50h+var_B8], dil
0x14003a19d  xorps   xmm1, xmm1
0x14003a1a0  mov     [rbp+50h+var_40], rdi
0x14003a1a4  xor     edx, edx; Val
0x14003a1a6  lea     rcx, [rbp+50h+var_C0]; void *
0x14003a1aa  mov     r8d, 88h; Size
0x14003a1b0  movdqu  xmmword ptr [rsp+150h+var_D8], xmm0
0x14003a1b6  movdqu  xmmword ptr [rbp-78h], xmm1
0x14003a1bb  call    memset
0x14003a1c0  mov     rbx, [rsp+150h+Context]
0x14003a1c5  test    rbx, rbx
0x14003a1c8  jz      short loc_14003A232
0x14003a1ca  mov     rdx, [r15+40h]; FileObject
0x14003a1ce  lea     r9, [rsp+150h+var_D8]; struct UnionFs::HandleCtxAndUnionWithRundown *
0x14003a1d3  mov     rcx, [rbx]; Instance
0x14003a1d6  mov     [rsp+150h+var_130], rsi; struct UnionFs::StackEventTracer *
0x14003a1db  call    ?FltGet@UfsStreamHandleCtx@UnionFs@@SAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@_NAEAUHandleCtxAndUnionWithRundown@2@AEAVStackEventTracer@2@@Z; UnionFs::UfsStreamHandleCtx::FltGet(_FLT_INSTANCE const &,_FILE_OBJECT const &,bool,UnionFs::HandleCtxAndUnionWithRundown &,UnionFs::StackEventTracer &)
0x14003a1e0  mov     edi, eax
0x14003a1e2  test    eax, eax
0x14003a1e4  jns     short loc_14003A232
0x14003a1e6  lea     rax, aPushGettingStr_0; "PUSH: Getting streamhandle ctx"
0x14003a1ed  mov     r8, 159000F02B3h; struct UnionFs::StackEventTracer *
0x14003a1f7  lea     r9, aUnionfsUnionfs_7; "UnionFs::UnionFsFilter::GeneratePreCrea"...
0x14003a1fe  mov     [rsp+150h+var_130], rax; char *
0x14003a203  mov     rdx, rsi; int
0x14003a206  mov     ecx, edi; this
0x14003a208  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14003a20d  lea     rcx, [rsp+150h+var_D8]; this
0x14003a212  call    ??1QueryInfoContext@UnionFs@@QEAA@XZ; UnionFs::QueryInfoContext::~QueryInfoContext(void)
0x14003a217  test    rbx, rbx
0x14003a21a  jz      short loc_14003A22B
0x14003a21c  mov     rcx, rbx; Context
0x14003a21f  call    cs:__imp_FltReleaseContext
0x14003a226  nop     dword ptr [rax+rax+00h]
0x14003a22b  mov     eax, edi
0x14003a22d  jmp     loc_14003A4F8
0x14003a232  mov     rdi, [rsp+150h+var_D8]
0x14003a237  mov     [rsp+150h+var_D8], 0
0x14003a240  test    rdi, rdi
0x14003a243  jz      loc_14003A422
0x14003a249  mov     eax, [rdi]
0x14003a24b  test    al, 1
0x14003a24d  jz      loc_14003A422
0x14003a253  mov     r8, [r15+40h]; struct _FILE_OBJECT *
0x14003a257  lea     r9, [rsp+150h+var_110]; struct UnionFs::MapShadowFileObjectResults *
0x14003a25c  xor     eax, eax
0x14003a25e  mov     [rsp+150h+var_128], rdi; char *
0x14003a263  xorps   xmm0, xmm0
0x14003a266  mov     word ptr [rsp+150h+var_110+5], ax
0x14003a26b  mov     rdx, r12; struct _FLT_INSTANCE *
0x14003a26e  mov     byte ptr [rsp+150h+var_110+7], al
0x14003a272  movdqu  xmmword ptr [rsp+150h+var_108], xmm0
0x14003a278  mov     [rsp+150h+var_F8], rax
0x14003a27d  mov     dword ptr [rsp+150h+var_110], 3
0x14003a285  mov     byte ptr [rsp+150h+var_110+4], 0
0x14003a28a  mov     [rsp+150h+var_130], rsi; struct UnionFs::StackEventTracer *
0x14003a28f  call    ?MapShadowFileObjectToBacking@UnionFsFilter@UnionFs@@QEAAJAEBU_FLT_INSTANCE@@AEAU_FILE_OBJECT@@AEAUMapShadowFileObjectResults@2@AEAVStackEventTracer@2@PEBVUfsStreamHandleCtx@2@@Z; UnionFs::UnionFsFilter::MapShadowFileObjectToBacking(_FLT_INSTANCE const &,_FILE_OBJECT &,UnionFs::MapShadowFileObjectResults &,UnionFs::StackEventTracer &,UnionFs::UfsStreamHandleCtx const *)
0x14003a294  mov     r12d, eax
0x14003a297  test    eax, eax
0x14003a299  jns     short loc_14003A2F8
0x14003a29b  lea     rax, aPushCouldnTMap; "PUSH: Couldn't map SFO"
0x14003a2a2  mov     r8, 399000F02D6h; struct UnionFs::StackEventTracer *
0x14003a2ac  lea     r9, aUnionfsUnionfs_7; "UnionFs::UnionFsFilter::GeneratePreCrea"...
0x14003a2b3  mov     [rsp+150h+var_130], rax; char *
0x14003a2b8  mov     rdx, rsi; int
0x14003a2bb  mov     ecx, r12d; this
0x14003a2be  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14003a2c3  mov     rcx, rdi; Context
0x14003a2c6  call    cs:__imp_FltReleaseContext
0x14003a2cd  nop     dword ptr [rax+rax+00h]
0x14003a2d2  lea     rcx, [rsp+150h+var_D8]; this
0x14003a2d7  call    ??1QueryInfoContext@UnionFs@@QEAA@XZ; UnionFs::QueryInfoContext::~QueryInfoContext(void)
0x14003a2dc  test    rbx, rbx
0x14003a2df  jz      short loc_14003A2F0
0x14003a2e1  mov     rcx, rbx; Context
0x14003a2e4  call    cs:__imp_FltReleaseContext
0x14003a2eb  nop     dword ptr [rax+rax+00h]
0x14003a2f0  mov     eax, r12d
0x14003a2f3  jmp     loc_14003A4F8
0x14003a2f8  cmp     byte ptr [rsp+150h+var_110+4], 0
0x14003a2fd  jnz     short loc_14003A30A
0x14003a2ff  mov     r8, [r15+40h]
0x14003a303  mov     rdx, [rsp+150h+var_E0]
0x14003a308  jmp     short loc_14003A314
0x14003a30a  mov     rdx, [rsp+150h+var_108]; struct _FLT_INSTANCE *
0x14003a30f  mov     r8, [rsp+150h+var_108+8]; struct _FILE_OBJECT *
0x14003a314  mov     [rsp+150h+var_120], rsi; struct UnionFs::StackEventTracer *
0x14003a319  and     r14d, 0FF00FF02h
0x14003a320  mov     r12d, 2
0x14003a326  mov     [rsp+150h+var_128], r13; char *
0x14003a32b  or      r14d, r12d
0x14003a32e  mov     [rsp+150h+var_130], rdi; struct UnionFs::UfsStreamHandleCtx *
0x14003a333  mov     r9d, r14d; unsigned int
0x14003a336  call    ?GeneratePostCreateName@UnionFsFilter@UnionFs@@QEAAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@KAEBVUfsStreamHandleCtx@2@PEAU_FLT_NAME_CONTROL@@AEAVStackEventTracer@2@_N@Z; UnionFs::UnionFsFilter::GeneratePostCreateName(_FLT_INSTANCE const &,_FILE_OBJECT const &,ulong,UnionFs::UfsStreamHandleCtx const &,_FLT_NAME_CONTROL *,UnionFs::StackEventTracer &,bool)
0x14003a33b  mov     r14d, eax
0x14003a33e  test    eax, eax
0x14003a340  jns     short loc_14003A36F
0x14003a342  lea     rax, aPushGenerating; "PUSH: Generating opened name for relate"...
0x14003a349  mov     r8, 15B000F02EEh; struct UnionFs::StackEventTracer *
0x14003a353  lea     r9, aUnionfsUnionfs_7; "UnionFs::UnionFsFilter::GeneratePreCrea"...
0x14003a35a  mov     [rsp+150h+var_130], rax; char *
0x14003a35f  mov     rdx, rsi; int
0x14003a362  mov     ecx, r14d; this
0x14003a365  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14003a36a  jmp     loc_14003A492
0x14003a36f  movzx   edx, word ptr [r15+58h]
0x14003a374  cmp     dx, r12w
0x14003a378  jb      loc_14003A4C9
0x14003a37e  add     dx, [r13+0]
0x14003a383  mov     rcx, r13; NameCtrl
0x14003a386  add     dx, r12w; NewSize
0x14003a38a  call    cs:__imp_FltCheckAndGrowNameControl
0x14003a391  nop     dword ptr [rax+rax+00h]
0x14003a396  mov     r14d, eax
0x14003a399  test    eax, eax
0x14003a39b  jns     short loc_14003A3CA
0x14003a39d  lea     rax, aApiGrowingName; "API: Growing name control"
0x14003a3a4  mov     r8, 15C000F02F9h; struct UnionFs::StackEventTracer *
0x14003a3ae  lea     r9, aUnionfsUnionfs_7; "UnionFs::UnionFsFilter::GeneratePreCrea"...
0x14003a3b5  mov     [rsp+150h+var_130], rax; char *
0x14003a3ba  mov     rdx, rsi; int
0x14003a3bd  mov     ecx, r14d; this
0x14003a3c0  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14003a3c5  jmp     loc_14003A492
0x14003a3ca  mov     rax, [r15+60h]
0x14003a3ce  cmp     word ptr [rax], 5Ch ; '\'
0x14003a3d2  jz      short loc_14003A3F1
0x14003a3d4  lea     rdx, Source; "\\"
0x14003a3db  mov     rcx, r13; Destination
0x14003a3de  call    cs:__imp_RtlAppendUnicodeToString
0x14003a3e5  nop     dword ptr [rax+rax+00h]
0x14003a3ea  mov     r14d, eax
0x14003a3ed  test    eax, eax
0x14003a3ef  js      short loc_14003A40F
0x14003a3f1  lea     rdx, [r15+58h]; Source
0x14003a3f5  mov     rcx, r13; Destination
0x14003a3f8  call    cs:__imp_RtlAppendUnicodeStringToString
0x14003a3ff  nop     dword ptr [rax+rax+00h]
0x14003a404  mov     r14d, eax
0x14003a407  test    eax, eax
0x14003a409  jns     loc_14003A4C9
0x14003a40f  lea     rax, aApiAppendingRe; "API: Appending remaining name"
0x14003a416  mov     r8, 15D000F0302h
0x14003a420  jmp     short loc_14003A3AE
0x14003a422  mov     rax, [rsp+150h+var_E8]
0x14003a427  lea     rdx, [rsp+150h+var_110]
0x14003a42c  and     r14d, 0FF00FF02h
0x14003a433  mov     [rsp+150h+var_110], rax
0x14003a438  or      r14d, 2
0x14003a43c  mov     [rsp+150h+var_108], 0
0x14003a445  mov     r8d, r14d
0x14003a448  mov     [rsp+150h+var_108+8], 0
0x14003a451  mov     r9, r13
0x14003a454  mov     [rsp+150h+var_130], rsi
0x14003a459  call    ?PassthroughNameQuery@UnionFsFilter@UnionFs@@AEAAJUNameInfoParams@Utils@2@KPEAU_FLT_NAME_CONTROL@@AEAVStackEventTracer@2@@Z; UnionFs::UnionFsFilter::PassthroughNameQuery(UnionFs::Utils::NameInfoParams,ulong,_FLT_NAME_CONTROL *,UnionFs::StackEventTracer &)
0x14003a45e  mov     r14d, eax
0x14003a461  test    eax, eax
0x14003a463  jns     short loc_14003A4C4
0x14003a465  lea     rax, aPushPassThroug; "PUSH: Pass-through for relative open"
0x14003a46c  mov     r8, 15A000F02C4h; struct UnionFs::StackEventTracer *
0x14003a476  lea     r9, aUnionfsUnionfs_7; "UnionFs::UnionFsFilter::GeneratePreCrea"...
0x14003a47d  mov     [rsp+150h+var_130], rax; char *
0x14003a482  mov     rdx, rsi; int
0x14003a485  mov     ecx, r14d; this
0x14003a488  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14003a48d  test    rdi, rdi
0x14003a490  jz      short loc_14003A4A1
0x14003a492  mov     rcx, rdi; Context
0x14003a495  call    cs:__imp_FltReleaseContext
0x14003a49c  nop     dword ptr [rax+rax+00h]
0x14003a4a1  lea     rcx, [rsp+150h+var_D8]; this
0x14003a4a6  call    ??1QueryInfoContext@UnionFs@@QEAA@XZ; UnionFs::QueryInfoContext::~QueryInfoContext(void)
0x14003a4ab  test    rbx, rbx
0x14003a4ae  jz      short loc_14003A4BF
0x14003a4b0  mov     rcx, rbx; Context
0x14003a4b3  call    cs:__imp_FltReleaseContext
0x14003a4ba  nop     dword ptr [rax+rax+00h]
0x14003a4bf  mov     eax, r14d
0x14003a4c2  jmp     short loc_14003A4F8
0x14003a4c4  test    rdi, rdi
0x14003a4c7  jz      short loc_14003A4D8
0x14003a4c9  mov     rcx, rdi; Context
0x14003a4cc  call    cs:__imp_FltReleaseContext
0x14003a4d3  nop     dword ptr [rax+rax+00h]
0x14003a4d8  lea     rcx, [rsp+150h+var_D8]; this
0x14003a4dd  call    ??1QueryInfoContext@UnionFs@@QEAA@XZ; UnionFs::QueryInfoContext::~QueryInfoContext(void)
0x14003a4e2  test    rbx, rbx
0x14003a4e5  jz      short loc_14003A4F6
0x14003a4e7  mov     rcx, rbx; Context
0x14003a4ea  call    cs:__imp_FltReleaseContext
0x14003a4f1  nop     dword ptr [rax+rax+00h]
0x14003a4f6  xor     eax, eax
0x14003a4f8  mov     rcx, [rbp+50h+var_38]
0x14003a4fc  xor     rcx, rsp; StackCookie
0x14003a4ff  call    __security_check_cookie
0x14003a504  mov     rbx, [rsp+150h+arg_0]
0x14003a50c  add     rsp, 120h
0x14003a513  pop     r15
0x14003a515  pop     r14
0x14003a517  pop     r13
0x14003a519  pop     r12
0x14003a51b  pop     rdi
0x14003a51c  pop     rsi
0x14003a51d  pop     rbp
0x14003a51e  retn
```
