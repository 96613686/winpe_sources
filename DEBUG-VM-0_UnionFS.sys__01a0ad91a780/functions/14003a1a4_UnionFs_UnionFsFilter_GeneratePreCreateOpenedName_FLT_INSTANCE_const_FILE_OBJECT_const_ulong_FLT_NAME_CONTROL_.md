# UnionFs::UnionFsFilter::GeneratePreCreateOpenedName(_FLT_INSTANCE const &,_FILE_OBJECT const &,ulong,_FLT_NAME_CONTROL *,UnionFs::StackEventTracer &,_FLT_CALLBACK_DATA *)

- ea: `0x14003a1a4`
- end: `0x14003a660`
- name: `?GeneratePreCreateOpenedName@UnionFsFilter@UnionFs@@AEAAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@KPEAU_FLT_NAME_CONTROL@@AEAVStackEventTracer@2@PEAU_FLT_CALLBACK_DATA@@@Z`
- size: `1212`
- prototype: `int(UnionFs::UnionFsFilter *__hidden this, const struct _FLT_INSTANCE *, const struct _FILE_OBJECT *, unsigned int, struct _FLT_NAME_CONTROL *, struct UnionFs::StackEventTracer *, struct _FLT_CALLBACK_DATA *)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x1400365c8`

## callees

- `0x140005ff8`
- `0x14000bfd8`
- `0x140027624`
- `0x140027a9c`
- `0x140037a64`
- `0x14003a1a4`
- `0x14003b60c`
- `0x140056bd0`
- `0x140056c7c`
- `0x14007b2b0`
- `0x14007baf0`
- `0x14007bf40`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeToString` at `0x14003a51e`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14003a51e`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14003a538`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14003a538`
- `FLTMGR!FltCheckAndGrowNameControl` at `0x14003a4ca`
- `FLTMGR!FltCheckAndGrowNameControl` at `0x14003a4ca`
- `FLTMGR!FltReleaseContext` at `0x14003a2c8`
- `FLTMGR!FltReleaseContext` at `0x14003a35f`
- `FLTMGR!FltReleaseContext` at `0x14003a406`
- `FLTMGR!FltReleaseContext` at `0x14003a424`
- `FLTMGR!FltReleaseContext` at `0x14003a5d5`
- `FLTMGR!FltReleaseContext` at `0x14003a5f3`
- `FLTMGR!FltReleaseContext` at `0x14003a60c`
- `FLTMGR!FltReleaseContext` at `0x14003a62a`
- `FLTMGR!FltReleaseContext` at `0x14003a2c8`
- `FLTMGR!FltReleaseContext` at `0x14003a35f`
- `FLTMGR!FltReleaseContext` at `0x14003a406`
- `FLTMGR!FltReleaseContext` at `0x14003a424`
- `FLTMGR!FltReleaseContext` at `0x14003a5d5`
- `FLTMGR!FltReleaseContext` at `0x14003a5f3`
- `FLTMGR!FltReleaseContext` at `0x14003a60c`
- `FLTMGR!FltReleaseContext` at `0x14003a62a`

## string_xrefs

- `0x14003a1fe`: `FileObject must not be open`
- `0x14003a251`: `PUSH: Pass-through for non-relative open`
- `0x14003a262`: `UnionFs::UnionFsFilter::GeneratePreCreateOpenedName`
- `0x14003a2a8`: `UnionFs::UnionFsFilter::GeneratePreCreateOpenedName`
- `0x14003a337`: `UnionFs::UnionFsFilter::GeneratePreCreateOpenedName`
- `0x14003a3ec`: `UnionFs::UnionFsFilter::GeneratePreCreateOpenedName`
- `0x14003a493`: `UnionFs::UnionFsFilter::GeneratePreCreateOpenedName`
- `0x14003a4ee`: `UnionFs::UnionFsFilter::GeneratePreCreateOpenedName`
- `0x14003a5b6`: `UnionFs::UnionFsFilter::GeneratePreCreateOpenedName`
- `0x14003a5a5`: `PUSH: Pass-through for relative open`
- `0x14003a482`: `PUSH: Generating opened name for related FO`

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
        (struct UnionFs::StackEventTracer *)0x158000F02A3LL,
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
        (struct UnionFs::StackEventTracer *)0x15A000F02C5LL,
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
        (struct UnionFs::StackEventTracer *)0x157000F0294LL,
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
0x14003a1a4  mov     [rsp-8+arg_0], rbx
0x14003a1a9  push    rbp
0x14003a1aa  push    rsi
0x14003a1ab  push    rdi
0x14003a1ac  push    r12
0x14003a1ae  push    r13
0x14003a1b0  push    r14
0x14003a1b2  push    r15
0x14003a1b4  lea     rbp, [rsp-20h]
0x14003a1b9  sub     rsp, 120h
0x14003a1c0  mov     rax, cs:__security_cookie
0x14003a1c7  xor     rax, rsp
0x14003a1ca  mov     [rbp+50h+var_38], rax
0x14003a1ce  mov     rax, [rbp+50h+arg_30]
0x14003a1d5  xor     edi, edi
0x14003a1d7  mov     r14d, r9d
0x14003a1da  mov     r13, [rbp+50h+NameCtrl]
0x14003a1e1  mov     r15, r8
0x14003a1e4  mov     rsi, [rbp+50h+arg_28]
0x14003a1eb  mov     r12, rdx
0x14003a1ee  mov     [rsp+150h+var_E0], rdx
0x14003a1f3  mov     [rsp+150h+var_E8], rax
0x14003a1f8  cmp     [r8+18h], rdi
0x14003a1fc  jz      short loc_14003A20F
0x14003a1fe  lea     rcx, aFileobjectMust; "FileObject must not be open"
0x14003a205  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x14003a20a  mov     rax, [rsp+150h+var_E8]
0x14003a20f  mov     rcx, [r15+40h]; FileObject
0x14003a213  test    rcx, rcx
0x14003a216  jnz     short loc_14003A27F
0x14003a218  and     r14d, 0FF00FF02h
0x14003a21f  mov     [rsp+150h+var_110], rax
0x14003a224  or      r14d, 2
0x14003a228  mov     [rsp+150h+var_108], rdi
0x14003a22d  mov     r8d, r14d
0x14003a230  mov     [rsp+150h+var_108+8], rdi
0x14003a235  mov     r9, r13
0x14003a238  mov     [rsp+150h+var_130], rsi
0x14003a23d  lea     rdx, [rsp+150h+var_110]
0x14003a242  call    ?PassthroughNameQuery@UnionFsFilter@UnionFs@@AEAAJUNameInfoParams@Utils@2@KPEAU_FLT_NAME_CONTROL@@AEAVStackEventTracer@2@@Z; UnionFs::UnionFsFilter::PassthroughNameQuery(UnionFs::Utils::NameInfoParams,ulong,_FLT_NAME_CONTROL *,UnionFs::StackEventTracer &)
0x14003a247  mov     ebx, eax
0x14003a249  test    eax, eax
0x14003a24b  jns     loc_14003A636
0x14003a251  lea     rax, aPushPassThroug_0; "PUSH: Pass-through for non-relative ope"...
0x14003a258  mov     r8, 157000F0294h; struct UnionFs::StackEventTracer *
0x14003a262  lea     r9, aUnionfsUnionfs_7; "UnionFs::UnionFsFilter::GeneratePreCrea"...
0x14003a269  mov     [rsp+150h+var_130], rax; char *
0x14003a26e  mov     rdx, rsi; int
0x14003a271  mov     ecx, ebx; this
0x14003a273  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14003a278  mov     eax, ebx
0x14003a27a  jmp     loc_14003A638
0x14003a27f  mov     r9, rsi
0x14003a282  mov     [rsp+150h+Context], rdi
0x14003a287  lea     r8, [rsp+150h+Context]
0x14003a28c  call    ?FltGet@UfsInstanceCtx@UnionFs@@SAJAEBU_FILE_OBJECT@@_NAEAV?$unique_ptr@VUfsInstanceCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@@Z; UnionFs::UfsInstanceCtx::FltGet(_FILE_OBJECT const &,bool,wistd::unique_ptr<UnionFs::UfsInstanceCtx,wil::function_deleter<void (*)(void *),&FltReleaseContext(void *)>> &,UnionFs::StackEventTracer &)
0x14003a291  mov     ebx, eax
0x14003a293  test    eax, eax
0x14003a295  jns     short loc_14003A2D6
0x14003a297  lea     rax, aPushGettingIns_1; "PUSH: Getting instance ctx from FileObj"...
0x14003a29e  mov     r8, 158000F02A3h; struct UnionFs::StackEventTracer *
0x14003a2a8  lea     r9, aUnionfsUnionfs_7; "UnionFs::UnionFsFilter::GeneratePreCrea"...
0x14003a2af  mov     [rsp+150h+var_130], rax; char *
0x14003a2b4  mov     rdx, rsi; int
0x14003a2b7  mov     ecx, ebx; this
0x14003a2b9  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14003a2be  mov     rcx, [rsp+150h+Context]; Context
0x14003a2c3  test    rcx, rcx
0x14003a2c6  jz      short loc_14003A278
0x14003a2c8  call    cs:__imp_FltReleaseContext
0x14003a2cf  nop     dword ptr [rax+rax+00h]
0x14003a2d4  jmp     short loc_14003A278
0x14003a2d6  xorps   xmm0, xmm0
0x14003a2d9  mov     [rbp+50h+var_B8], dil
0x14003a2dd  xorps   xmm1, xmm1
0x14003a2e0  mov     [rbp+50h+var_40], rdi
0x14003a2e4  xor     edx, edx; Val
0x14003a2e6  lea     rcx, [rbp+50h+var_C0]; void *
0x14003a2ea  mov     r8d, 88h; Size
0x14003a2f0  movdqu  xmmword ptr [rsp+150h+var_D8], xmm0
0x14003a2f6  movdqu  xmmword ptr [rbp-78h], xmm1
0x14003a2fb  call    memset
0x14003a300  mov     rbx, [rsp+150h+Context]
0x14003a305  test    rbx, rbx
0x14003a308  jz      short loc_14003A372
0x14003a30a  mov     rdx, [r15+40h]; FileObject
0x14003a30e  lea     r9, [rsp+150h+var_D8]; struct UnionFs::HandleCtxAndUnionWithRundown *
0x14003a313  mov     rcx, [rbx]; Instance
0x14003a316  mov     [rsp+150h+var_130], rsi; struct UnionFs::StackEventTracer *
0x14003a31b  call    ?FltGet@UfsStreamHandleCtx@UnionFs@@SAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@_NAEAUHandleCtxAndUnionWithRundown@2@AEAVStackEventTracer@2@@Z; UnionFs::UfsStreamHandleCtx::FltGet(_FLT_INSTANCE const &,_FILE_OBJECT const &,bool,UnionFs::HandleCtxAndUnionWithRundown &,UnionFs::StackEventTracer &)
0x14003a320  mov     edi, eax
0x14003a322  test    eax, eax
0x14003a324  jns     short loc_14003A372
0x14003a326  lea     rax, aPushGettingStr_0; "PUSH: Getting streamhandle ctx"
0x14003a32d  mov     r8, 159000F02B4h; struct UnionFs::StackEventTracer *
0x14003a337  lea     r9, aUnionfsUnionfs_7; "UnionFs::UnionFsFilter::GeneratePreCrea"...
0x14003a33e  mov     [rsp+150h+var_130], rax; char *
0x14003a343  mov     rdx, rsi; int
0x14003a346  mov     ecx, edi; this
0x14003a348  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14003a34d  lea     rcx, [rsp+150h+var_D8]; this
0x14003a352  call    ??1QueryInfoContext@UnionFs@@QEAA@XZ; UnionFs::QueryInfoContext::~QueryInfoContext(void)
0x14003a357  test    rbx, rbx
0x14003a35a  jz      short loc_14003A36B
0x14003a35c  mov     rcx, rbx; Context
0x14003a35f  call    cs:__imp_FltReleaseContext
0x14003a366  nop     dword ptr [rax+rax+00h]
0x14003a36b  mov     eax, edi
0x14003a36d  jmp     loc_14003A638
0x14003a372  mov     rdi, [rsp+150h+var_D8]
0x14003a377  mov     [rsp+150h+var_D8], 0
0x14003a380  test    rdi, rdi
0x14003a383  jz      loc_14003A562
0x14003a389  mov     eax, [rdi]
0x14003a38b  test    al, 1
0x14003a38d  jz      loc_14003A562
0x14003a393  mov     r8, [r15+40h]; struct _FILE_OBJECT *
0x14003a397  lea     r9, [rsp+150h+var_110]; struct UnionFs::MapShadowFileObjectResults *
0x14003a39c  xor     eax, eax
0x14003a39e  mov     [rsp+150h+var_128], rdi; char *
0x14003a3a3  xorps   xmm0, xmm0
0x14003a3a6  mov     word ptr [rsp+150h+var_110+5], ax
0x14003a3ab  mov     rdx, r12; struct _FLT_INSTANCE *
0x14003a3ae  mov     byte ptr [rsp+150h+var_110+7], al
0x14003a3b2  movdqu  xmmword ptr [rsp+150h+var_108], xmm0
0x14003a3b8  mov     [rsp+150h+var_F8], rax
0x14003a3bd  mov     dword ptr [rsp+150h+var_110], 3
0x14003a3c5  mov     byte ptr [rsp+150h+var_110+4], 0
0x14003a3ca  mov     [rsp+150h+var_130], rsi; struct UnionFs::StackEventTracer *
0x14003a3cf  call    ?MapShadowFileObjectToBacking@UnionFsFilter@UnionFs@@QEAAJAEBU_FLT_INSTANCE@@AEAU_FILE_OBJECT@@AEAUMapShadowFileObjectResults@2@AEAVStackEventTracer@2@PEBVUfsStreamHandleCtx@2@@Z; UnionFs::UnionFsFilter::MapShadowFileObjectToBacking(_FLT_INSTANCE const &,_FILE_OBJECT &,UnionFs::MapShadowFileObjectResults &,UnionFs::StackEventTracer &,UnionFs::UfsStreamHandleCtx const *)
0x14003a3d4  mov     r12d, eax
0x14003a3d7  test    eax, eax
0x14003a3d9  jns     short loc_14003A438
0x14003a3db  lea     rax, aPushCouldnTMap; "PUSH: Couldn't map SFO"
0x14003a3e2  mov     r8, 399000F02D7h; struct UnionFs::StackEventTracer *
0x14003a3ec  lea     r9, aUnionfsUnionfs_7; "UnionFs::UnionFsFilter::GeneratePreCrea"...
0x14003a3f3  mov     [rsp+150h+var_130], rax; char *
0x14003a3f8  mov     rdx, rsi; int
0x14003a3fb  mov     ecx, r12d; this
0x14003a3fe  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14003a403  mov     rcx, rdi; Context
0x14003a406  call    cs:__imp_FltReleaseContext
0x14003a40d  nop     dword ptr [rax+rax+00h]
0x14003a412  lea     rcx, [rsp+150h+var_D8]; this
0x14003a417  call    ??1QueryInfoContext@UnionFs@@QEAA@XZ; UnionFs::QueryInfoContext::~QueryInfoContext(void)
0x14003a41c  test    rbx, rbx
0x14003a41f  jz      short loc_14003A430
0x14003a421  mov     rcx, rbx; Context
0x14003a424  call    cs:__imp_FltReleaseContext
0x14003a42b  nop     dword ptr [rax+rax+00h]
0x14003a430  mov     eax, r12d
0x14003a433  jmp     loc_14003A638
0x14003a438  cmp     byte ptr [rsp+150h+var_110+4], 0
0x14003a43d  jnz     short loc_14003A44A
0x14003a43f  mov     r8, [r15+40h]
0x14003a443  mov     rdx, [rsp+150h+var_E0]
0x14003a448  jmp     short loc_14003A454
0x14003a44a  mov     rdx, [rsp+150h+var_108]; struct _FLT_INSTANCE *
0x14003a44f  mov     r8, [rsp+150h+var_108+8]; struct _FILE_OBJECT *
0x14003a454  mov     [rsp+150h+var_120], rsi; struct UnionFs::StackEventTracer *
0x14003a459  and     r14d, 0FF00FF02h
0x14003a460  mov     r12d, 2
0x14003a466  mov     [rsp+150h+var_128], r13; char *
0x14003a46b  or      r14d, r12d
0x14003a46e  mov     [rsp+150h+var_130], rdi; struct UnionFs::UfsStreamHandleCtx *
0x14003a473  mov     r9d, r14d; unsigned int
0x14003a476  call    ?GeneratePostCreateName@UnionFsFilter@UnionFs@@QEAAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@KAEBVUfsStreamHandleCtx@2@PEAU_FLT_NAME_CONTROL@@AEAVStackEventTracer@2@_N@Z; UnionFs::UnionFsFilter::GeneratePostCreateName(_FLT_INSTANCE const &,_FILE_OBJECT const &,ulong,UnionFs::UfsStreamHandleCtx const &,_FLT_NAME_CONTROL *,UnionFs::StackEventTracer &,bool)
0x14003a47b  mov     r14d, eax
0x14003a47e  test    eax, eax
0x14003a480  jns     short loc_14003A4AF
0x14003a482  lea     rax, aPushGenerating; "PUSH: Generating opened name for relate"...
0x14003a489  mov     r8, 15B000F02EFh; struct UnionFs::StackEventTracer *
0x14003a493  lea     r9, aUnionfsUnionfs_7; "UnionFs::UnionFsFilter::GeneratePreCrea"...
0x14003a49a  mov     [rsp+150h+var_130], rax; char *
0x14003a49f  mov     rdx, rsi; int
0x14003a4a2  mov     ecx, r14d; this
0x14003a4a5  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14003a4aa  jmp     loc_14003A5D2
0x14003a4af  movzx   edx, word ptr [r15+58h]
0x14003a4b4  cmp     dx, r12w
0x14003a4b8  jb      loc_14003A609
0x14003a4be  add     dx, [r13+0]
0x14003a4c3  mov     rcx, r13; NameCtrl
0x14003a4c6  add     dx, r12w; NewSize
0x14003a4ca  call    cs:__imp_FltCheckAndGrowNameControl
0x14003a4d1  nop     dword ptr [rax+rax+00h]
0x14003a4d6  mov     r14d, eax
0x14003a4d9  test    eax, eax
0x14003a4db  jns     short loc_14003A50A
0x14003a4dd  lea     rax, aApiGrowingName; "API: Growing name control"
0x14003a4e4  mov     r8, 15C000F02FAh; struct UnionFs::StackEventTracer *
0x14003a4ee  lea     r9, aUnionfsUnionfs_7; "UnionFs::UnionFsFilter::GeneratePreCrea"...
0x14003a4f5  mov     [rsp+150h+var_130], rax; char *
0x14003a4fa  mov     rdx, rsi; int
0x14003a4fd  mov     ecx, r14d; this
0x14003a500  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14003a505  jmp     loc_14003A5D2
0x14003a50a  mov     rax, [r15+60h]
0x14003a50e  cmp     word ptr [rax], 5Ch ; '\'
0x14003a512  jz      short loc_14003A531
0x14003a514  lea     rdx, Source; "\\"
0x14003a51b  mov     rcx, r13; Destination
0x14003a51e  call    cs:__imp_RtlAppendUnicodeToString
0x14003a525  nop     dword ptr [rax+rax+00h]
0x14003a52a  mov     r14d, eax
0x14003a52d  test    eax, eax
0x14003a52f  js      short loc_14003A54F
0x14003a531  lea     rdx, [r15+58h]; Source
0x14003a535  mov     rcx, r13; Destination
0x14003a538  call    cs:__imp_RtlAppendUnicodeStringToString
0x14003a53f  nop     dword ptr [rax+rax+00h]
0x14003a544  mov     r14d, eax
0x14003a547  test    eax, eax
0x14003a549  jns     loc_14003A609
0x14003a54f  lea     rax, aApiAppendingRe; "API: Appending remaining name"
0x14003a556  mov     r8, 15D000F0303h
0x14003a560  jmp     short loc_14003A4EE
0x14003a562  mov     rax, [rsp+150h+var_E8]
0x14003a567  lea     rdx, [rsp+150h+var_110]
0x14003a56c  and     r14d, 0FF00FF02h
0x14003a573  mov     [rsp+150h+var_110], rax
0x14003a578  or      r14d, 2
0x14003a57c  mov     [rsp+150h+var_108], 0
0x14003a585  mov     r8d, r14d
0x14003a588  mov     [rsp+150h+var_108+8], 0
0x14003a591  mov     r9, r13
0x14003a594  mov     [rsp+150h+var_130], rsi
0x14003a599  call    ?PassthroughNameQuery@UnionFsFilter@UnionFs@@AEAAJUNameInfoParams@Utils@2@KPEAU_FLT_NAME_CONTROL@@AEAVStackEventTracer@2@@Z; UnionFs::UnionFsFilter::PassthroughNameQuery(UnionFs::Utils::NameInfoParams,ulong,_FLT_NAME_CONTROL *,UnionFs::StackEventTracer &)
0x14003a59e  mov     r14d, eax
0x14003a5a1  test    eax, eax
0x14003a5a3  jns     short loc_14003A604
0x14003a5a5  lea     rax, aPushPassThroug; "PUSH: Pass-through for relative open"
0x14003a5ac  mov     r8, 15A000F02C5h; struct UnionFs::StackEventTracer *
0x14003a5b6  lea     r9, aUnionfsUnionfs_7; "UnionFs::UnionFsFilter::GeneratePreCrea"...
0x14003a5bd  mov     [rsp+150h+var_130], rax; char *
0x14003a5c2  mov     rdx, rsi; int
0x14003a5c5  mov     ecx, r14d; this
0x14003a5c8  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14003a5cd  test    rdi, rdi
0x14003a5d0  jz      short loc_14003A5E1
0x14003a5d2  mov     rcx, rdi; Context
0x14003a5d5  call    cs:__imp_FltReleaseContext
0x14003a5dc  nop     dword ptr [rax+rax+00h]
0x14003a5e1  lea     rcx, [rsp+150h+var_D8]; this
0x14003a5e6  call    ??1QueryInfoContext@UnionFs@@QEAA@XZ; UnionFs::QueryInfoContext::~QueryInfoContext(void)
0x14003a5eb  test    rbx, rbx
0x14003a5ee  jz      short loc_14003A5FF
0x14003a5f0  mov     rcx, rbx; Context
0x14003a5f3  call    cs:__imp_FltReleaseContext
0x14003a5fa  nop     dword ptr [rax+rax+00h]
0x14003a5ff  mov     eax, r14d
0x14003a602  jmp     short loc_14003A638
0x14003a604  test    rdi, rdi
0x14003a607  jz      short loc_14003A618
0x14003a609  mov     rcx, rdi; Context
0x14003a60c  call    cs:__imp_FltReleaseContext
0x14003a613  nop     dword ptr [rax+rax+00h]
0x14003a618  lea     rcx, [rsp+150h+var_D8]; this
0x14003a61d  call    ??1QueryInfoContext@UnionFs@@QEAA@XZ; UnionFs::QueryInfoContext::~QueryInfoContext(void)
0x14003a622  test    rbx, rbx
0x14003a625  jz      short loc_14003A636
0x14003a627  mov     rcx, rbx; Context
0x14003a62a  call    cs:__imp_FltReleaseContext
0x14003a631  nop     dword ptr [rax+rax+00h]
0x14003a636  xor     eax, eax
0x14003a638  mov     rcx, [rbp+50h+var_38]
0x14003a63c  xor     rcx, rsp; StackCookie
0x14003a63f  call    __security_check_cookie
0x14003a644  mov     rbx, [rsp+150h+arg_0]
0x14003a64c  add     rsp, 120h
0x14003a653  pop     r15
0x14003a655  pop     r14
0x14003a657  pop     r13
0x14003a659  pop     r12
0x14003a65b  pop     rdi
0x14003a65c  pop     rsi
0x14003a65d  pop     rbp
0x14003a65e  retn
```
