# UnionFs::UfsFileCtx::FltSet(_FLT_INSTANCE const &,_FILE_OBJECT &,wistd::unique_ptr<UnionFs::UfsFileCtx,wil::function_deleter<void (*)(void *),&FltReleaseContext(void *)>> &,UnionFs::StackEventTracer &,UnionFs::SetContextOperation,ulong)

- ea: `0x140028058`
- end: `0x1400283c4`
- name: `?FltSet@UfsFileCtx@UnionFs@@SAJAEBU_FLT_INSTANCE@@AEAU_FILE_OBJECT@@AEAV?$unique_ptr@VUfsFileCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@W4SetContextOperation@2@K@Z`
- size: `876`
- prototype: `__int64 __usercall@<rax>(PFLT_INSTANCE Instance@<rcx>, PFILE_OBJECT FileObject@<rdx>, int, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140027cb8`
- `0x1400761d8`

## callees

- `0x140005ff8`
- `0x14000bfd8`
- `0x140027a9c`
- `0x140028058`
- `0x140056bd0`
- `0x140056c44`
- `0x140056c7c`
- `0x14007b2b0`
- `0x14007baf0`
- `0x14007bf40`

## import_xrefs

- `FLTMGR!FltSetFileContext` at `0x1400282dd`
- `FLTMGR!FltSetFileContext` at `0x1400282dd`
- `FLTMGR!FltIsDirectory` at `0x140028216`
- `FLTMGR!FltIsDirectory` at `0x140028216`
- `FLTMGR!FltReleaseContext` at `0x140028257`
- `FLTMGR!FltReleaseContext` at `0x14002828c`
- `FLTMGR!FltReleaseContext` at `0x140028307`
- `FLTMGR!FltReleaseContext` at `0x140028363`
- `FLTMGR!FltReleaseContext` at `0x140028395`
- `FLTMGR!FltReleaseContext` at `0x140028257`
- `FLTMGR!FltReleaseContext` at `0x14002828c`
- `FLTMGR!FltReleaseContext` at `0x140028307`
- `FLTMGR!FltReleaseContext` at `0x140028363`
- `FLTMGR!FltReleaseContext` at `0x140028395`

## string_xrefs

- `0x140028228`: `API: FltIsDirectory`

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
0x140028058  push    rbp
0x14002805a  push    rbx
0x14002805b  push    rsi
0x14002805c  push    rdi
0x14002805d  push    r12
0x14002805f  push    r13
0x140028061  push    r14
0x140028063  push    r15
0x140028065  lea     rbp, [rsp-18h]
0x14002806a  sub     rsp, 118h
0x140028071  mov     rax, cs:__security_cookie
0x140028078  xor     rax, rsp
0x14002807b  mov     [rbp+50h+var_50], rax
0x14002807f  mov     r12, rdx
0x140028082  xor     r13d, r13d
0x140028085  mov     edx, [rbp+50h+arg_28]
0x14002808b  mov     r14, r9
0x14002808e  mov     rsi, r8
0x140028091  mov     r15, rcx
0x140028094  test    edx, edx
0x140028096  jz      short loc_1400280B7
0x140028098  mov     rax, [r8]
0x14002809b  mov     ecx, edx
0x14002809d  shr     ecx, 4
0x1400280a0  and     cl, 1
0x1400280a3  shr     edx, 17h
0x1400280a6  and     dl, 1
0x1400280a9  mov     [rax+60h], cl
0x1400280ac  mov     rax, [r8]
0x1400280af  mov     [rax+61h], dl
0x1400280b2  jmp     loc_1400282A2
0x1400280b7  xorps   xmm0, xmm0
0x1400280ba  mov     [rbp+50h+var_D0], r13b
0x1400280be  xorps   xmm1, xmm1
0x1400280c1  mov     [rbp+50h+var_58], r13
0x1400280c5  xor     edx, edx; Val
0x1400280c7  lea     rcx, [rsp+150h+var_D8]; void *
0x1400280cc  mov     r8d, 88h; Size
0x1400280d2  movdqu  xmmword ptr [rsp+150h+Context], xmm0
0x1400280d8  movdqu  xmmword ptr [rsp+70h], xmm1
0x1400280de  call    memset
0x1400280e3  lea     r9, [rsp+150h+Context]; struct UnionFs::HandleCtxAndUnionWithRundown *
0x1400280e8  mov     [rsp+150h+OldContext], r14; struct UnionFs::StackEventTracer *
0x1400280ed  mov     rdx, r12; FileObject
0x1400280f0  mov     rcx, r15; Instance
0x1400280f3  call    ?FltGet@UfsStreamHandleCtx@UnionFs@@SAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@_NAEAUHandleCtxAndUnionWithRundown@2@AEAVStackEventTracer@2@@Z; UnionFs::UfsStreamHandleCtx::FltGet(_FLT_INSTANCE const &,_FILE_OBJECT const &,bool,UnionFs::HandleCtxAndUnionWithRundown &,UnionFs::StackEventTracer &)
0x1400280f8  mov     ebx, eax
0x1400280fa  test    eax, eax
0x1400280fc  jns     short loc_14002812A
0x1400280fe  lea     rax, aPushGettingHan; "PUSH: Getting handle ctx"
0x140028105  mov     r8, 465000A024Bh; struct UnionFs::StackEventTracer *
0x14002810f  lea     r9, aUnionfsUfsfile_4; "UnionFs::UfsFileCtx::FltSet"
0x140028116  mov     [rsp+150h+OldContext], rax; char *
0x14002811b  mov     rdx, r14; int
0x14002811e  mov     ecx, ebx; this
0x140028120  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140028125  jmp     loc_140028265
0x14002812a  mov     rbx, [rsp+150h+Context]
0x14002812f  mov     [rsp+150h+Context], r13
0x140028134  test    rbx, rbx
0x140028137  jz      loc_140028206
0x14002813d  mov     eax, [rbx]
0x14002813f  test    al, 1
0x140028141  jz      loc_140028206
0x140028147  xor     eax, eax
0x140028149  mov     [rsp+150h+var_128], rbx; char *
0x14002814e  xorps   xmm0, xmm0
0x140028151  mov     word ptr [rsp+150h+var_110+5], ax
0x140028156  lea     r9, [rsp+150h+var_110]; struct UnionFs::MapShadowFileObjectResults *
0x14002815b  mov     byte ptr [rsp+150h+var_110+7], al
0x14002815f  mov     r8, r12; struct _FILE_OBJECT *
0x140028162  mov     dword ptr [rsp+150h+var_110], 3
0x14002816a  mov     rdx, r15; struct _FLT_INSTANCE *
0x14002816d  mov     byte ptr [rsp+150h+var_110+4], r13b
0x140028172  movdqu  xmmword ptr [rsp+150h+var_108], xmm0
0x140028178  mov     [rsp+150h+var_F8], r13
0x14002817d  mov     [rsp+150h+OldContext], r14; struct UnionFs::StackEventTracer *
0x140028182  call    ?MapShadowFileObjectToBacking@UnionFsFilter@UnionFs@@QEAAJAEBU_FLT_INSTANCE@@AEAU_FILE_OBJECT@@AEAUMapShadowFileObjectResults@2@AEAVStackEventTracer@2@PEBVUfsStreamHandleCtx@2@@Z; UnionFs::UnionFsFilter::MapShadowFileObjectToBacking(_FLT_INSTANCE const &,_FILE_OBJECT &,UnionFs::MapShadowFileObjectResults &,UnionFs::StackEventTracer &,UnionFs::UfsStreamHandleCtx const *)
0x140028187  mov     edi, eax
0x140028189  test    eax, eax
0x14002818b  jns     short loc_1400281B9
0x14002818d  lea     rax, aPushMapshadowf; "PUSH: MapShadowFileObjectToBacking fail"...
0x140028194  mov     r8, 3B4000A025Dh; struct UnionFs::StackEventTracer *
0x14002819e  lea     r9, aUnionfsUfsfile_4; "UnionFs::UfsFileCtx::FltSet"
0x1400281a5  mov     [rsp+150h+OldContext], rax; char *
0x1400281aa  mov     rdx, r14; int
0x1400281ad  mov     ecx, edi; this
0x1400281af  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400281b4  jmp     loc_140028254
0x1400281b9  cmp     byte ptr [rsp+150h+var_110+4], r13b
0x1400281be  jnz     short loc_1400281FA
0x1400281c0  lea     rcx, aCouldnTMapSfoW; "Couldn't map SFO when handleCtx->IsShad"...
0x1400281c7  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x1400281cc  lea     rax, aOriginCouldnTM; "ORIGIN: Couldn't map SFO when handleCtx"...
0x1400281d3  mov     edi, 0C00000E5h
0x1400281d8  mov     ecx, edi; this
0x1400281da  mov     [rsp+150h+OldContext], rax; char *
0x1400281df  lea     r9, aUnionfsUfsfile_4; "UnionFs::UfsFileCtx::FltSet"
0x1400281e6  mov     r8, 3B7000A0268h; struct UnionFs::StackEventTracer *
0x1400281f0  mov     rdx, r14; int
0x1400281f3  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400281f8  jmp     short loc_140028254
0x1400281fa  mov     rdx, [rsp+150h+var_108]
0x1400281ff  mov     rcx, [rsp+150h+var_108+8]
0x140028204  jmp     short loc_14002820C
0x140028206  mov     rdx, r15; Instance
0x140028209  mov     rcx, r12; FileObject
0x14002820c  lea     r8, [rsp+150h+IsDirectory]; IsDirectory
0x140028211  mov     [rsp+150h+IsDirectory], r13b
0x140028216  call    cs:__imp_FltIsDirectory
0x14002821d  nop     dword ptr [rax+rax+00h]
0x140028222  mov     edi, eax
0x140028224  test    eax, eax
0x140028226  jns     short loc_140028276
0x140028228  lea     rax, aApiFltisdirect; "API: FltIsDirectory"
0x14002822f  mov     r8, 34E000A027Ah; struct UnionFs::StackEventTracer *
0x140028239  lea     r9, aUnionfsUfsfile_4; "UnionFs::UfsFileCtx::FltSet"
0x140028240  mov     [rsp+150h+OldContext], rax; char *
0x140028245  mov     rdx, r14; int
0x140028248  mov     ecx, edi; this
0x14002824a  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14002824f  test    rbx, rbx
0x140028252  jz      short loc_140028263
0x140028254  mov     rcx, rbx; Context
0x140028257  call    cs:__imp_FltReleaseContext
0x14002825e  nop     dword ptr [rax+rax+00h]
0x140028263  mov     ebx, edi
0x140028265  lea     rcx, [rsp+150h+Context]; this
0x14002826a  call    ??1QueryInfoContext@UnionFs@@QEAA@XZ; UnionFs::QueryInfoContext::~QueryInfoContext(void)
0x14002826f  mov     eax, ebx
0x140028271  jmp     loc_1400283A3
0x140028276  cmp     [rsp+150h+IsDirectory], r13b
0x14002827b  mov     rax, [rsi]
0x14002827e  setnz   cl
0x140028281  mov     [rax+60h], cl
0x140028284  test    rbx, rbx
0x140028287  jz      short loc_140028298
0x140028289  mov     rcx, rbx; Context
0x14002828c  call    cs:__imp_FltReleaseContext
0x140028293  nop     dword ptr [rax+rax+00h]
0x140028298  lea     rcx, [rsp+150h+Context]; this
0x14002829d  call    ??1QueryInfoContext@UnionFs@@QEAA@XZ; UnionFs::QueryInfoContext::~QueryInfoContext(void)
0x1400282a2  mov     ebx, [rbp+50h+arg_20]
0x1400282a8  lea     rax, [rsp+150h+var_118]
0x1400282ad  mov     r9, [rsi]; NewContext
0x1400282b0  mov     r8d, r13d
0x1400282b3  mov     [rsp+150h+var_110], rax
0x1400282b8  test    ebx, ebx
0x1400282ba  lea     rax, [rsp+150h+var_108]
0x1400282bf  mov     [rsp+150h+var_118], r13
0x1400282c4  setnz   r8b; Operation
0x1400282c8  mov     [rsp+150h+OldContext], rax; OldContext
0x1400282cd  mov     rdx, r12; FileObject
0x1400282d0  mov     [rsp+150h+var_108], r13
0x1400282d5  mov     rcx, r15; Instance
0x1400282d8  mov     byte ptr [rsp+150h+var_108+8], 1
0x1400282dd  call    cs:__imp_FltSetFileContext
0x1400282e4  nop     dword ptr [rax+rax+00h]
0x1400282e9  mov     edi, eax
0x1400282eb  cmp     byte ptr [rsp+150h+var_108+8], r13b
0x1400282f0  jz      short loc_140028313
0x1400282f2  mov     r8, [rsp+150h+var_110]
0x1400282f7  mov     rdx, [rsp+150h+var_108]
0x1400282fc  mov     rcx, [r8]; Context
0x1400282ff  mov     [r8], rdx
0x140028302  test    rcx, rcx
0x140028305  jz      short loc_140028313
0x140028307  call    cs:__imp_FltReleaseContext
0x14002830e  nop     dword ptr [rax+rax+00h]
0x140028313  test    edi, edi
0x140028315  jns     short loc_140028373
0x140028317  test    ebx, ebx
0x140028319  jz      short loc_14002832D
0x14002831b  cmp     ebx, 1
0x14002831e  jnz     short loc_140028328
0x140028320  cmp     edi, 0C01C0002h
0x140028326  jnz     short loc_14002832D
0x140028328  cmp     ebx, 2
0x14002832b  jnz     short loc_140028373
0x14002832d  lea     rax, aApiSettingFile; "API: Setting file context"
0x140028334  mov     r8, 112000A0293h; struct UnionFs::StackEventTracer *
0x14002833e  lea     r9, aUnionfsUfsfile_4; "UnionFs::UfsFileCtx::FltSet"
0x140028345  mov     [rsp+150h+OldContext], rax; char *
0x14002834a  mov     rdx, r14; int
0x14002834d  mov     ecx, edi; this
0x14002834f  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140028354  mov     rcx, [rsp+150h+var_118]; Context
0x140028359  mov     [rsp+150h+var_118], r13
0x14002835e  test    rcx, rcx
0x140028361  jz      short loc_14002836F
0x140028363  call    cs:__imp_FltReleaseContext
0x14002836a  nop     dword ptr [rax+rax+00h]
0x14002836f  mov     eax, edi
0x140028371  jmp     short loc_1400283A3
0x140028373  mov     rcx, [rsp+150h+var_118]
0x140028378  test    rcx, rcx
0x14002837b  jz      short loc_14002838B
0x14002837d  cmp     ebx, 1
0x140028380  jnz     short loc_14002838B
0x140028382  mov     rax, [rsi]
0x140028385  mov     [rsi], rcx
0x140028388  mov     rcx, rax; Context
0x14002838b  mov     [rsp+150h+var_118], r13
0x140028390  test    rcx, rcx
0x140028393  jz      short loc_1400283A1
0x140028395  call    cs:__imp_FltReleaseContext
0x14002839c  nop     dword ptr [rax+rax+00h]
0x1400283a1  xor     eax, eax
0x1400283a3  mov     rcx, [rbp+50h+var_50]
0x1400283a7  xor     rcx, rsp; StackCookie
0x1400283aa  call    __security_check_cookie
0x1400283af  add     rsp, 118h
0x1400283b6  pop     r15
0x1400283b8  pop     r14
0x1400283ba  pop     r13
0x1400283bc  pop     r12
0x1400283be  pop     rdi
0x1400283bf  pop     rsi
0x1400283c0  pop     rbx
0x1400283c1  pop     rbp
0x1400283c2  retn
```
