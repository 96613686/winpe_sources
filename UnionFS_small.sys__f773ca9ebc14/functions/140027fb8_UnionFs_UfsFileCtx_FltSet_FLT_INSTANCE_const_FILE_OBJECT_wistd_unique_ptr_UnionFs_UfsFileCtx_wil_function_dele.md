# UnionFs::UfsFileCtx::FltSet(_FLT_INSTANCE const &,_FILE_OBJECT &,wistd::unique_ptr<UnionFs::UfsFileCtx,wil::function_deleter<void (*)(void *),&FltReleaseContext(void *)>> &,UnionFs::StackEventTracer &,UnionFs::SetContextOperation,ulong)

- ea: `0x140027fb8`
- end: `0x140028324`
- name: `?FltSet@UfsFileCtx@UnionFs@@SAJAEBU_FLT_INSTANCE@@AEAU_FILE_OBJECT@@AEAV?$unique_ptr@VUfsFileCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@W4SetContextOperation@2@K@Z`
- size: `876`
- prototype: `__int64 __usercall@<rax>(PFLT_INSTANCE Instance@<rcx>, PFILE_OBJECT FileObject@<rdx>, int, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140027c18`
- `0x140075fd8`

## callees

- `0x140005ff8`
- `0x14000c008`
- `0x1400279fc`
- `0x140027fb8`
- `0x140056a50`
- `0x140056ac4`
- `0x140056afc`
- `0x14007af90`
- `0x14007b7d0`
- `0x14007bc00`

## import_xrefs

- `FLTMGR!FltSetFileContext` at `0x14002823d`
- `FLTMGR!FltSetFileContext` at `0x14002823d`
- `FLTMGR!FltIsDirectory` at `0x140028176`
- `FLTMGR!FltIsDirectory` at `0x140028176`
- `FLTMGR!FltReleaseContext` at `0x1400281b7`
- `FLTMGR!FltReleaseContext` at `0x1400281ec`
- `FLTMGR!FltReleaseContext` at `0x140028267`
- `FLTMGR!FltReleaseContext` at `0x1400282c3`
- `FLTMGR!FltReleaseContext` at `0x1400282f5`
- `FLTMGR!FltReleaseContext` at `0x1400281b7`
- `FLTMGR!FltReleaseContext` at `0x1400281ec`
- `FLTMGR!FltReleaseContext` at `0x140028267`
- `FLTMGR!FltReleaseContext` at `0x1400282c3`
- `FLTMGR!FltReleaseContext` at `0x1400282f5`

## string_xrefs

- `0x140028188`: `API: FltIsDirectory`

## pseudocode

```c
__int64 __fastcall UnionFs::UfsFileCtx::FltSet(
        PFLT_INSTANCE Instance,
        PFILE_OBJECT FileObject,
        __int64 a3,
        struct UnionFs::StackEventTracer *a4,
        int a5,
        int a6)
{
  bool v10; // r8
  UnionFs::UnionFsFilter *v11; // rcx
  int v12; // ebx
  const struct UnionFs::UfsStreamHandleCtx *v13; // rbx
  NTSTATUS v14; // edi
  struct _FLT_INSTANCE *v15; // rdx
  struct _FILE_OBJECT *v16; // rcx
  void *v18; // r9
  NTSTATUS v19; // edi
  PFLT_CONTEXT v20; // rcx
  PFLT_CONTEXT v21; // rcx
  PFLT_CONTEXT v22; // rcx
  void *v23; // rax
  struct UnionFs::UfsStreamHandleCtx *v24; // [rsp+28h] [rbp-D8h]
  unsigned __int8 IsDirectory[8]; // [rsp+30h] [rbp-D0h] BYREF
  PFLT_CONTEXT v26; // [rsp+38h] [rbp-C8h] BYREF
  PFLT_CONTEXT *v27; // [rsp+40h] [rbp-C0h] BYREF
  PFLT_CONTEXT OldContext[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v29; // [rsp+58h] [rbp-A8h]
  PFLT_CONTEXT Context[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v31; // [rsp+70h] [rbp-90h]
  _QWORD v32[17]; // [rsp+78h] [rbp-88h] BYREF

  if ( !a6 )
  {
    *(_OWORD *)Context = 0;
    v31 = 0;
    memset(v32, 0, sizeof(v32));
    v12 = UnionFs::UfsStreamHandleCtx::FltGet(
            Instance,
            FileObject,
            v10,
            (struct UnionFs::HandleCtxAndUnionWithRundown *)Context,
            a4);
    if ( v12 < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v12,
        (int)a4,
        (struct UnionFs::StackEventTracer *)0x465000A024BLL,
        (unsigned __int64)"UnionFs::UfsFileCtx::FltSet",
        "PUSH: Getting handle ctx",
        (const char *)v24);
LABEL_17:
      UnionFs::QueryInfoContext::~QueryInfoContext((UnionFs::QueryInfoContext *)Context);
      return (unsigned int)v12;
    }
    v13 = (const struct UnionFs::UfsStreamHandleCtx *)Context[0];
    Context[0] = 0;
    if ( v13 && (*(_DWORD *)v13 & 1) != 0 )
    {
      v27 = (PFLT_CONTEXT *)3;
      *(_OWORD *)OldContext = 0;
      v29 = 0;
      v14 = UnionFs::UnionFsFilter::MapShadowFileObjectToBacking(
              v11,
              Instance,
              FileObject,
              (struct UnionFs::MapShadowFileObjectResults *)&v27,
              a4,
              v13);
      if ( v14 < 0 )
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)v14,
          (int)a4,
          (struct UnionFs::StackEventTracer *)0x3B4000A025DLL,
          (unsigned __int64)"UnionFs::UfsFileCtx::FltSet",
          "PUSH: MapShadowFileObjectToBacking failure when handleCtx->IsShadowFoCtx() is true",
          (const char *)v24);
LABEL_15:
        FltReleaseContext(v13);
LABEL_16:
        v12 = v14;
        goto LABEL_17;
      }
      if ( !BYTE4(v27) )
      {
        MicrosoftTelemetryAssertTriggeredMsgKM("Couldn't map SFO when handleCtx->IsShadowFoCtx() is true");
        v14 = -1073741595;
        UnionFs::ProcessTraceStatusOrigin(
          (UnionFs *)0xC00000E5LL,
          (int)a4,
          (struct UnionFs::StackEventTracer *)0x3B7000A0268LL,
          (unsigned __int64)"UnionFs::UfsFileCtx::FltSet",
          "ORIGIN: Couldn't map SFO when handleCtx->IsShadowFoCtx() is true",
          (const char *)v24);
        goto LABEL_15;
      }
      v15 = (struct _FLT_INSTANCE *)OldContext[0];
      v16 = (struct _FILE_OBJECT *)OldContext[1];
    }
    else
    {
      v15 = Instance;
      v16 = FileObject;
    }
    IsDirectory[0] = 0;
    v14 = FltIsDirectory(v16, v15, IsDirectory);
    if ( v14 >= 0 )
    {
      *(_BYTE *)(*(_QWORD *)a3 + 96LL) = IsDirectory[0] != 0;
      if ( v13 )
        FltReleaseContext(v13);
      UnionFs::QueryInfoContext::~QueryInfoContext((UnionFs::QueryInfoContext *)Context);
      goto LABEL_21;
    }
    UnionFs::ProcessTraceStatusFromApi(
      (UnionFs *)(unsigned int)v14,
      (int)a4,
      (struct UnionFs::StackEventTracer *)0x34E000A027ALL,
      (unsigned __int64)"UnionFs::UfsFileCtx::FltSet",
      "API: FltIsDirectory",
      (const char *)v24);
    if ( !v13 )
      goto LABEL_16;
    goto LABEL_15;
  }
  *(_BYTE *)(*(_QWORD *)a3 + 96LL) = (a6 & 0x10) != 0;
  *(_BYTE *)(*(_QWORD *)a3 + 97LL) = (a6 & 0x800000) != 0;
LABEL_21:
  v18 = *(void **)a3;
  v27 = &v26;
  v26 = 0;
  OldContext[0] = 0;
  LOBYTE(OldContext[1]) = 1;
  v19 = FltSetFileContext(Instance, FileObject, (FLT_SET_CONTEXT_OPERATION)(a5 != 0), v18, OldContext);
  if ( LOBYTE(OldContext[1]) )
  {
    v20 = *v27;
    *v27 = OldContext[0];
    if ( v20 )
      FltReleaseContext(v20);
  }
  if ( v19 >= 0 || a5 && (a5 != 1 || v19 == -1071906814) && a5 != 2 )
  {
    v22 = v26;
    if ( v26 && a5 == 1 )
    {
      v23 = *(void **)a3;
      *(_QWORD *)a3 = v26;
      v22 = v23;
    }
    v26 = 0;
    if ( v22 )
      FltReleaseContext(v22);
    return 0;
  }
  else
  {
    UnionFs::ProcessTraceStatusFromApi(
      (UnionFs *)(unsigned int)v19,
      (int)a4,
      (struct UnionFs::StackEventTracer *)0x112000A0293LL,
      (unsigned __int64)"UnionFs::UfsFileCtx::FltSet",
      "API: Setting file context",
      (const char *)v24);
    v21 = v26;
    v26 = 0;
    if ( v21 )
      FltReleaseContext(v21);
    return (unsigned int)v19;
  }
}

```

## disassembly

```asm
0x140027fb8  push    rbp
0x140027fba  push    rbx
0x140027fbb  push    rsi
0x140027fbc  push    rdi
0x140027fbd  push    r12
0x140027fbf  push    r13
0x140027fc1  push    r14
0x140027fc3  push    r15
0x140027fc5  lea     rbp, [rsp-18h]
0x140027fca  sub     rsp, 118h
0x140027fd1  mov     rax, cs:__security_cookie
0x140027fd8  xor     rax, rsp
0x140027fdb  mov     [rbp+50h+var_50], rax
0x140027fdf  mov     r12, rdx
0x140027fe2  xor     r13d, r13d
0x140027fe5  mov     edx, [rbp+50h+arg_28]
0x140027feb  mov     r14, r9
0x140027fee  mov     rsi, r8
0x140027ff1  mov     r15, rcx
0x140027ff4  test    edx, edx
0x140027ff6  jz      short loc_140028017
0x140027ff8  mov     rax, [r8]
0x140027ffb  mov     ecx, edx
0x140027ffd  shr     ecx, 4
0x140028000  and     cl, 1
0x140028003  shr     edx, 17h
0x140028006  and     dl, 1
0x140028009  mov     [rax+60h], cl
0x14002800c  mov     rax, [r8]
0x14002800f  mov     [rax+61h], dl
0x140028012  jmp     loc_140028202
0x140028017  xorps   xmm0, xmm0
0x14002801a  mov     [rbp+50h+var_D0], r13b
0x14002801e  xorps   xmm1, xmm1
0x140028021  mov     [rbp+50h+var_58], r13
0x140028025  xor     edx, edx; Val
0x140028027  lea     rcx, [rsp+150h+var_D8]; void *
0x14002802c  mov     r8d, 88h; Size
0x140028032  movdqu  xmmword ptr [rsp+150h+Context], xmm0
0x140028038  movdqu  xmmword ptr [rsp+70h], xmm1
0x14002803e  call    memset
0x140028043  lea     r9, [rsp+150h+Context]; struct UnionFs::HandleCtxAndUnionWithRundown *
0x140028048  mov     [rsp+150h+OldContext], r14; struct UnionFs::StackEventTracer *
0x14002804d  mov     rdx, r12; FileObject
0x140028050  mov     rcx, r15; Instance
0x140028053  call    ?FltGet@UfsStreamHandleCtx@UnionFs@@SAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@_NAEAUHandleCtxAndUnionWithRundown@2@AEAVStackEventTracer@2@@Z; UnionFs::UfsStreamHandleCtx::FltGet(_FLT_INSTANCE const &,_FILE_OBJECT const &,bool,UnionFs::HandleCtxAndUnionWithRundown &,UnionFs::StackEventTracer &)
0x140028058  mov     ebx, eax
0x14002805a  test    eax, eax
0x14002805c  jns     short loc_14002808A
0x14002805e  lea     rax, aPushGettingHan; "PUSH: Getting handle ctx"
0x140028065  mov     r8, 465000A024Bh; struct UnionFs::StackEventTracer *
0x14002806f  lea     r9, aUnionfsUfsfile_4; "UnionFs::UfsFileCtx::FltSet"
0x140028076  mov     [rsp+150h+OldContext], rax; char *
0x14002807b  mov     rdx, r14; int
0x14002807e  mov     ecx, ebx; this
0x140028080  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140028085  jmp     loc_1400281C5
0x14002808a  mov     rbx, [rsp+150h+Context]
0x14002808f  mov     [rsp+150h+Context], r13
0x140028094  test    rbx, rbx
0x140028097  jz      loc_140028166
0x14002809d  mov     eax, [rbx]
0x14002809f  test    al, 1
0x1400280a1  jz      loc_140028166
0x1400280a7  xor     eax, eax
0x1400280a9  mov     [rsp+150h+var_128], rbx; char *
0x1400280ae  xorps   xmm0, xmm0
0x1400280b1  mov     word ptr [rsp+150h+var_110+5], ax
0x1400280b6  lea     r9, [rsp+150h+var_110]; struct UnionFs::MapShadowFileObjectResults *
0x1400280bb  mov     byte ptr [rsp+150h+var_110+7], al
0x1400280bf  mov     r8, r12; struct _FILE_OBJECT *
0x1400280c2  mov     dword ptr [rsp+150h+var_110], 3
0x1400280ca  mov     rdx, r15; struct _FLT_INSTANCE *
0x1400280cd  mov     byte ptr [rsp+150h+var_110+4], r13b
0x1400280d2  movdqu  xmmword ptr [rsp+150h+var_108], xmm0
0x1400280d8  mov     [rsp+150h+var_F8], r13
0x1400280dd  mov     [rsp+150h+OldContext], r14; struct UnionFs::StackEventTracer *
0x1400280e2  call    ?MapShadowFileObjectToBacking@UnionFsFilter@UnionFs@@QEAAJAEBU_FLT_INSTANCE@@AEAU_FILE_OBJECT@@AEAUMapShadowFileObjectResults@2@AEAVStackEventTracer@2@PEBVUfsStreamHandleCtx@2@@Z; UnionFs::UnionFsFilter::MapShadowFileObjectToBacking(_FLT_INSTANCE const &,_FILE_OBJECT &,UnionFs::MapShadowFileObjectResults &,UnionFs::StackEventTracer &,UnionFs::UfsStreamHandleCtx const *)
0x1400280e7  mov     edi, eax
0x1400280e9  test    eax, eax
0x1400280eb  jns     short loc_140028119
0x1400280ed  lea     rax, aPushMapshadowf; "PUSH: MapShadowFileObjectToBacking fail"...
0x1400280f4  mov     r8, 3B4000A025Dh; struct UnionFs::StackEventTracer *
0x1400280fe  lea     r9, aUnionfsUfsfile_4; "UnionFs::UfsFileCtx::FltSet"
0x140028105  mov     [rsp+150h+OldContext], rax; char *
0x14002810a  mov     rdx, r14; int
0x14002810d  mov     ecx, edi; this
0x14002810f  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140028114  jmp     loc_1400281B4
0x140028119  cmp     byte ptr [rsp+150h+var_110+4], r13b
0x14002811e  jnz     short loc_14002815A
0x140028120  lea     rcx, aCouldnTMapSfoW; "Couldn't map SFO when handleCtx->IsShad"...
0x140028127  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x14002812c  lea     rax, aOriginCouldnTM; "ORIGIN: Couldn't map SFO when handleCtx"...
0x140028133  mov     edi, 0C00000E5h
0x140028138  mov     ecx, edi; this
0x14002813a  mov     [rsp+150h+OldContext], rax; char *
0x14002813f  lea     r9, aUnionfsUfsfile_4; "UnionFs::UfsFileCtx::FltSet"
0x140028146  mov     r8, 3B7000A0268h; struct UnionFs::StackEventTracer *
0x140028150  mov     rdx, r14; int
0x140028153  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140028158  jmp     short loc_1400281B4
0x14002815a  mov     rdx, [rsp+150h+var_108]
0x14002815f  mov     rcx, [rsp+150h+var_108+8]
0x140028164  jmp     short loc_14002816C
0x140028166  mov     rdx, r15; Instance
0x140028169  mov     rcx, r12; FileObject
0x14002816c  lea     r8, [rsp+150h+IsDirectory]; IsDirectory
0x140028171  mov     [rsp+150h+IsDirectory], r13b
0x140028176  call    cs:__imp_FltIsDirectory
0x14002817d  nop     dword ptr [rax+rax+00h]
0x140028182  mov     edi, eax
0x140028184  test    eax, eax
0x140028186  jns     short loc_1400281D6
0x140028188  lea     rax, aApiFltisdirect; "API: FltIsDirectory"
0x14002818f  mov     r8, 34E000A027Ah; struct UnionFs::StackEventTracer *
0x140028199  lea     r9, aUnionfsUfsfile_4; "UnionFs::UfsFileCtx::FltSet"
0x1400281a0  mov     [rsp+150h+OldContext], rax; char *
0x1400281a5  mov     rdx, r14; int
0x1400281a8  mov     ecx, edi; this
0x1400281aa  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400281af  test    rbx, rbx
0x1400281b2  jz      short loc_1400281C3
0x1400281b4  mov     rcx, rbx; Context
0x1400281b7  call    cs:__imp_FltReleaseContext
0x1400281be  nop     dword ptr [rax+rax+00h]
0x1400281c3  mov     ebx, edi
0x1400281c5  lea     rcx, [rsp+150h+Context]; this
0x1400281ca  call    ??1QueryInfoContext@UnionFs@@QEAA@XZ; UnionFs::QueryInfoContext::~QueryInfoContext(void)
0x1400281cf  mov     eax, ebx
0x1400281d1  jmp     loc_140028303
0x1400281d6  cmp     [rsp+150h+IsDirectory], r13b
0x1400281db  mov     rax, [rsi]
0x1400281de  setnz   cl
0x1400281e1  mov     [rax+60h], cl
0x1400281e4  test    rbx, rbx
0x1400281e7  jz      short loc_1400281F8
0x1400281e9  mov     rcx, rbx; Context
0x1400281ec  call    cs:__imp_FltReleaseContext
0x1400281f3  nop     dword ptr [rax+rax+00h]
0x1400281f8  lea     rcx, [rsp+150h+Context]; this
0x1400281fd  call    ??1QueryInfoContext@UnionFs@@QEAA@XZ; UnionFs::QueryInfoContext::~QueryInfoContext(void)
0x140028202  mov     ebx, [rbp+50h+arg_20]
0x140028208  lea     rax, [rsp+150h+var_118]
0x14002820d  mov     r9, [rsi]; NewContext
0x140028210  mov     r8d, r13d
0x140028213  mov     [rsp+150h+var_110], rax
0x140028218  test    ebx, ebx
0x14002821a  lea     rax, [rsp+150h+var_108]
0x14002821f  mov     [rsp+150h+var_118], r13
0x140028224  setnz   r8b; Operation
0x140028228  mov     [rsp+150h+OldContext], rax; OldContext
0x14002822d  mov     rdx, r12; FileObject
0x140028230  mov     [rsp+150h+var_108], r13
0x140028235  mov     rcx, r15; Instance
0x140028238  mov     byte ptr [rsp+150h+var_108+8], 1
0x14002823d  call    cs:__imp_FltSetFileContext
0x140028244  nop     dword ptr [rax+rax+00h]
0x140028249  mov     edi, eax
0x14002824b  cmp     byte ptr [rsp+150h+var_108+8], r13b
0x140028250  jz      short loc_140028273
0x140028252  mov     r8, [rsp+150h+var_110]
0x140028257  mov     rdx, [rsp+150h+var_108]
0x14002825c  mov     rcx, [r8]; Context
0x14002825f  mov     [r8], rdx
0x140028262  test    rcx, rcx
0x140028265  jz      short loc_140028273
0x140028267  call    cs:__imp_FltReleaseContext
0x14002826e  nop     dword ptr [rax+rax+00h]
0x140028273  test    edi, edi
0x140028275  jns     short loc_1400282D3
0x140028277  test    ebx, ebx
0x140028279  jz      short loc_14002828D
0x14002827b  cmp     ebx, 1
0x14002827e  jnz     short loc_140028288
0x140028280  cmp     edi, 0C01C0002h
0x140028286  jnz     short loc_14002828D
0x140028288  cmp     ebx, 2
0x14002828b  jnz     short loc_1400282D3
0x14002828d  lea     rax, aApiSettingFile; "API: Setting file context"
0x140028294  mov     r8, 112000A0293h; struct UnionFs::StackEventTracer *
0x14002829e  lea     r9, aUnionfsUfsfile_4; "UnionFs::UfsFileCtx::FltSet"
0x1400282a5  mov     [rsp+150h+OldContext], rax; char *
0x1400282aa  mov     rdx, r14; int
0x1400282ad  mov     ecx, edi; this
0x1400282af  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400282b4  mov     rcx, [rsp+150h+var_118]; Context
0x1400282b9  mov     [rsp+150h+var_118], r13
0x1400282be  test    rcx, rcx
0x1400282c1  jz      short loc_1400282CF
0x1400282c3  call    cs:__imp_FltReleaseContext
0x1400282ca  nop     dword ptr [rax+rax+00h]
0x1400282cf  mov     eax, edi
0x1400282d1  jmp     short loc_140028303
0x1400282d3  mov     rcx, [rsp+150h+var_118]
0x1400282d8  test    rcx, rcx
0x1400282db  jz      short loc_1400282EB
0x1400282dd  cmp     ebx, 1
0x1400282e0  jnz     short loc_1400282EB
0x1400282e2  mov     rax, [rsi]
0x1400282e5  mov     [rsi], rcx
0x1400282e8  mov     rcx, rax; Context
0x1400282eb  mov     [rsp+150h+var_118], r13
0x1400282f0  test    rcx, rcx
0x1400282f3  jz      short loc_140028301
0x1400282f5  call    cs:__imp_FltReleaseContext
0x1400282fc  nop     dword ptr [rax+rax+00h]
0x140028301  xor     eax, eax
0x140028303  mov     rcx, [rbp+50h+var_50]
0x140028307  xor     rcx, rsp; StackCookie
0x14002830a  call    __security_check_cookie
0x14002830f  add     rsp, 118h
0x140028316  pop     r15
0x140028318  pop     r14
0x14002831a  pop     r13
0x14002831c  pop     r12
0x14002831e  pop     rdi
0x14002831f  pop     rsi
0x140028320  pop     rbx
0x140028321  pop     rbp
0x140028322  retn
```
