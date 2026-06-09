# UnionFs::UnionFsFilter::PreWrite(_FLT_CALLBACK_DATA *,_FLT_RELATED_OBJECTS const *,void * *)

- ea: `0x140079920`
- end: `0x140079c89`
- name: `?PreWrite@UnionFsFilter@UnionFs@@SA?AW4_FLT_PREOP_CALLBACK_STATUS@@PEAU_FLT_CALLBACK_DATA@@PEBU_FLT_RELATED_OBJECTS@@PEAPEAX@Z`
- size: `873`
- prototype: `enum _FLT_PREOP_CALLBACK_STATUS __fastcall(enum _FLT_PREOP_CALLBACK_STATUS, const struct _FLT_RELATED_OBJECTS *, void **)`
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops, installer_update`

## callees

- `0x1400056b4`
- `0x140006168`
- `0x14000f3a0`
- `0x140010168`
- `0x140027890`
- `0x1400279dc`
- `0x1400295b8`
- `0x14002b6e0`
- `0x14002be04`
- `0x140056c44`
- `0x140056c7c`
- `0x140074ca4`
- `0x140079920`
- `0x14007a114`
- `0x14007baf0`
- `0x14007bbd0`

## import_xrefs

- `FLTMGR!FltReleaseContext` at `0x1400799d1`
- `FLTMGR!FltReleaseContext` at `0x140079aa5`
- `FLTMGR!FltReleaseContext` at `0x140079b61`
- `FLTMGR!FltReleaseContext` at `0x140079bbf`
- `FLTMGR!FltReleaseContext` at `0x140079c35`
- `FLTMGR!FltReleaseContext` at `0x1400799d1`
- `FLTMGR!FltReleaseContext` at `0x140079aa5`
- `FLTMGR!FltReleaseContext` at `0x140079b61`
- `FLTMGR!FltReleaseContext` at `0x140079bbf`
- `FLTMGR!FltReleaseContext` at `0x140079c35`

## string_xrefs

- `0x140079aee`: `ORIGIN: Allocating SetFileSizeContext`
- `0x1400799f5`: `UnionFs::UnionFsFilter::PreWrite`
- `0x140079a6e`: `UnionFs::UnionFsFilter::PreWrite`
- `0x140079b01`: `UnionFs::UnionFsFilter::PreWrite`
- `0x1400799e2`: `ORIGIN: Failing write on SFO`

## pseudocode

```c
enum _FLT_PREOP_CALLBACK_STATUS __fastcall UnionFs::UnionFsFilter::PreWrite(
        const struct _FLT_CALLBACK_DATA *a1,
        const struct _FLT_RELATED_OBJECTS *a2,
        void ***a3,
        int a4)
{
  PFILE_OBJECT FileObject; // r8
  _WORD *FsContext; // rax
  const PFLT_INSTANCE *p_Instance; // rbx
  char v10; // r14
  struct _FILE_OBJECT *v12; // rdx
  struct _FLT_INSTANCE *v13; // rcx
  int v14; // ebx
  int v15; // r9d
  enum _FLT_PREOP_CALLBACK_STATUS v16; // ebx
  PFLT_CONTEXT v17; // rbx
  void **v18; // rsi
  int v19; // r9d
  __int64 v20; // r8
  __int64 v21; // rcx
  enum _FLT_PREOP_CALLBACK_STATUS v22; // edi
  struct FsFltWil::Details::RundownRefCacheAware *v23; // rdx
  void *v24; // rcx
  struct FsFltWil::Details::RundownRefCacheAware *v25; // rdx
  struct FsFltWil::Details::RundownRefCacheAware *v26; // rdx
  char *v27; // [rsp+20h] [rbp-E0h]
  char *v28; // [rsp+20h] [rbp-E0h]
  char *v29; // [rsp+20h] [rbp-E0h]
  const char *v30; // [rsp+28h] [rbp-D8h]
  PFLT_CONTEXT Context; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v32[128]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v33; // [rsp+B8h] [rbp-48h]
  int v34[188]; // [rsp+C0h] [rbp-40h] BYREF

  if ( a1->Iopb->TargetFileObject && (a2->FileObject->Flags & 0x400000) == 0 )
  {
    UnionFs::StackEventTracer::StackEventTracer((UnionFs::StackEventTracer *)v34, 0x29900220026uLL, a1);
    FileObject = a2->FileObject;
    FsContext = FileObject->FsContext;
    if ( FsContext && *FsContext == 17217 )
    {
      p_Instance = &a2->Instance;
      UnionFs::UfsStreamHandleCtx::FltGet(&Context, a2->Instance, FileObject);
      if ( Context )
      {
        v10 = *(_BYTE *)Context & 1;
        FltReleaseContext(Context);
        if ( v10 )
        {
          UnionFs::ProcessTraceStatusOrigin(
            (UnionFs *)0xC00000BBLL,
            (int)v34,
            (struct UnionFs::StackEventTracer *)0x29A0022006ALL,
            (unsigned __int64)"UnionFs::UnionFsFilter::PreWrite",
            "ORIGIN: Failing write on SFO",
            v30);
          a1->IoStatus.Status = -1073741637;
          a1->IoStatus.Information = 0;
          UnionFs::StackEventTracer::~StackEventTracer((UnionFs::StackEventTracer *)v34);
          return 4;
        }
      }
    }
    else
    {
      p_Instance = &a2->Instance;
    }
    v12 = a2->FileObject;
    v13 = *p_Instance;
    Context = 0;
    v14 = UnionFs::UfsStreamCtx::FltGet(v13, v12, (int)v34);
    if ( v14 < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v14,
        (int)v34,
        (struct UnionFs::StackEventTracer *)0x4D400220037LL,
        (unsigned __int64)"UnionFs::UnionFsFilter::PreWrite",
        "PUSH: Getting stream context",
        v30);
      v16 = UnionFs::Utils::PreOpFinishProcessing(
              (UnionFs::Utils *)4,
              (enum _FLT_PREOP_CALLBACK_STATUS)a1,
              (struct _FLT_CALLBACK_DATA *)(unsigned int)v14,
              v15,
              (unsigned __int64)v29);
      if ( Context )
        FltReleaseContext(Context);
      goto LABEL_36;
    }
    v17 = Context;
    if ( Context )
    {
      UnionFs::UfsStreamCtx::SyncWithCOW((UnionFs::UfsStreamCtx *)Context);
      utl::make_unique<UnionFs::SetFileSizeContext,wil::unique_struct<FsFltWil::Details::RundownRefCacheAware,void (*)(FsFltWil::Details::RundownRefCacheAware *),&void FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *),std::nullptr_t,0>,0>(
        &Context,
        v32);
      v18 = (void **)Context;
      if ( !Context )
      {
        UnionFs::ProcessTraceStatusOrigin(
          (UnionFs *)0xC000009ALL,
          (int)v34,
          (struct UnionFs::StackEventTracer *)0x4D200220047LL,
          (unsigned __int64)"UnionFs::UnionFsFilter::PreWrite",
          "ORIGIN: Allocating SetFileSizeContext",
          v30);
        v20 = 3221225626LL;
        v21 = 4;
LABEL_15:
        v22 = UnionFs::Utils::PreOpFinishProcessing(
                (UnionFs::Utils *)v21,
                (enum _FLT_PREOP_CALLBACK_STATUS)a1,
                (struct _FLT_CALLBACK_DATA *)v20,
                v19,
                (unsigned __int64)v28);
        utl::unique_ptr<UnionFs::SetFileSizeContext,utl::default_delete<UnionFs::SetFileSizeContext>>::~unique_ptr<UnionFs::SetFileSizeContext,utl::default_delete<UnionFs::SetFileSizeContext>>(&Context);
        FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v32, v23);
        if ( v33 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 24LL))(v33);
        if ( v17 )
          FltReleaseContext(v17);
        v16 = v22;
        goto LABEL_36;
      }
      if ( *((_BYTE *)v17 + 160) && UnionFs::UfsStreamCtx::HasSFOs((UnionFs::UfsStreamCtx *)v17) )
      {
        if ( !(unsigned int)Feature_UnionFS_OplockSupport__private_IsEnabledDeviceUsageNoInline()
          || (a1->Flags & 2) == 0
          || *(_BYTE *)(*((_QWORD *)v17 + 4) + 5LL) == 1 )
        {
          v24 = *v18;
          *v18 = v17;
          if ( v24 )
            FltReleaseContext(v24);
          Context = 0;
          *a3 = v18;
          utl::unique_ptr<UnionFs::SetFileSizeContext,utl::default_delete<UnionFs::SetFileSizeContext>>::~unique_ptr<UnionFs::SetFileSizeContext,utl::default_delete<UnionFs::SetFileSizeContext>>(&Context);
          FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v32, v25);
          if ( v33 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 24LL))(v33);
          v16 = FLT_PREOP_SUCCESS_WITH_CALLBACK;
          goto LABEL_36;
        }
        v20 = 0;
        v21 = 3;
        goto LABEL_15;
      }
      utl::unique_ptr<UnionFs::SetFileSizeContext,utl::default_delete<UnionFs::SetFileSizeContext>>::~unique_ptr<UnionFs::SetFileSizeContext,utl::default_delete<UnionFs::SetFileSizeContext>>(&Context);
      FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v32, v26);
      if ( v33 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 24LL))(v33);
      if ( v17 )
        FltReleaseContext(v17);
    }
    v16 = FLT_PREOP_SUCCESS_NO_CALLBACK;
LABEL_36:
    UnionFs::StackEventTracer::~StackEventTracer((UnionFs::StackEventTracer *)v34);
    return v16;
  }
  return UnionFs::Utils::PreOpFinishProcessing(
           (UnionFs::Utils *)1,
           (enum _FLT_PREOP_CALLBACK_STATUS)a1,
           0,
           a4,
           (unsigned __int64)v27);
}

```

## disassembly

```asm
0x140079920  mov     [rsp-8+arg_18], rbx
0x140079925  push    rbp
0x140079926  push    rsi
0x140079927  push    rdi
0x140079928  push    r14
0x14007992a  push    r15
0x14007992c  lea     rbp, [rsp-2C0h]
0x140079934  sub     rsp, 3C0h
0x14007993b  mov     rax, cs:__security_cookie
0x140079942  xor     rax, rsp
0x140079945  mov     [rbp+2E0h+var_30], rax
0x14007994c  mov     rax, [rcx+10h]
0x140079950  mov     r15, r8
0x140079953  mov     rsi, rdx
0x140079956  mov     rdi, rcx
0x140079959  cmp     qword ptr [rax+8], 0
0x14007995e  jz      loc_140079C53
0x140079964  mov     rax, [rdx+20h]
0x140079968  test    dword ptr [rax+50h], 400000h
0x14007996f  jnz     loc_140079C53
0x140079975  mov     r8, rcx; struct _FLT_CALLBACK_DATA *
0x140079978  mov     rdx, 29900220026h; unsigned __int64
0x140079982  lea     rcx, [rbp+2E0h+var_320]; this
0x140079986  call    ??0StackEventTracer@UnionFs@@QEAA@_KPEBU_FLT_CALLBACK_DATA@@@Z; UnionFs::StackEventTracer::StackEventTracer(unsigned __int64,_FLT_CALLBACK_DATA const *)
0x14007998b  mov     r8, [rsi+20h]
0x14007998f  mov     rax, [r8+18h]
0x140079993  test    rax, rax
0x140079996  jz      loc_140079A2D
0x14007999c  mov     ecx, 4341h
0x1400799a1  cmp     [rax], cx
0x1400799a4  jnz     loc_140079A2D
0x1400799aa  lea     rbx, [rsi+18h]
0x1400799ae  mov     rdx, [rbx]
0x1400799b1  lea     rcx, [rsp+3E0h+Context]
0x1400799b6  call    ?FltGet@UfsStreamHandleCtx@UnionFs@@SA?AV?$unique_ptr@VUfsStreamHandleCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@AEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@@Z; UnionFs::UfsStreamHandleCtx::FltGet(_FLT_INSTANCE const &,_FILE_OBJECT const &)
0x1400799bb  mov     rcx, [rsp+3E0h+Context]; Context
0x1400799c0  test    rcx, rcx
0x1400799c3  jz      short loc_140079A31
0x1400799c5  mov     r14b, [rcx]
0x1400799c8  and     r14b, 1
0x1400799cc  test    rcx, rcx
0x1400799cf  jz      short loc_1400799DD
0x1400799d1  call    cs:__imp_FltReleaseContext
0x1400799d8  nop     dword ptr [rax+rax+00h]
0x1400799dd  test    r14b, r14b
0x1400799e0  jz      short loc_140079A31
0x1400799e2  lea     rax, aOriginFailingW; "ORIGIN: Failing write on SFO"
0x1400799e9  mov     ebx, 0C00000BBh
0x1400799ee  mov     ecx, ebx; this
0x1400799f0  mov     [rsp+3E0h+var_3C0], rax; char *
0x1400799f5  lea     r9, aUnionfsUnionfs_3; "UnionFs::UnionFsFilter::PreWrite"
0x1400799fc  mov     r8, 29A0022006Ah; struct UnionFs::StackEventTracer *
0x140079a06  lea     rdx, [rbp+2E0h+var_320]; int
0x140079a0a  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140079a0f  lea     rcx, [rbp+2E0h+var_320]; this
0x140079a13  mov     [rdi+18h], ebx
0x140079a16  mov     qword ptr [rdi+20h], 0
0x140079a1e  call    ??1StackEventTracer@UnionFs@@QEAA@XZ; UnionFs::StackEventTracer::~StackEventTracer(void)
0x140079a23  mov     eax, 4
0x140079a28  jmp     loc_140079C62
0x140079a2d  lea     rbx, [rsi+18h]
0x140079a31  mov     rdx, [rsi+20h]; FileObject
0x140079a35  lea     rax, [rbp+2E0h+var_320]
0x140079a39  mov     rcx, [rbx]; Instance
0x140079a3c  lea     r9, [rsp+3E0h+Context]
0x140079a41  mov     r8b, 1
0x140079a44  mov     [rsp+3E0h+var_3C0], rax; int
0x140079a49  mov     [rsp+3E0h+Context], 0
0x140079a52  call    ?FltGet@UfsStreamCtx@UnionFs@@SAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@_NAEAV?$unique_ptr@VUfsStreamCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@@Z; UnionFs::UfsStreamCtx::FltGet(_FLT_INSTANCE const &,_FILE_OBJECT const &,bool,wistd::unique_ptr<UnionFs::UfsStreamCtx,wil::function_deleter<void (*)(void *),&FltReleaseContext(void *)>> &,UnionFs::StackEventTracer &)
0x140079a57  mov     ebx, eax
0x140079a59  test    eax, eax
0x140079a5b  jns     short loc_140079AB6
0x140079a5d  lea     rax, aPushGettingStr; "PUSH: Getting stream context"
0x140079a64  mov     r8, 4D400220037h; struct UnionFs::StackEventTracer *
0x140079a6e  lea     r9, aUnionfsUnionfs_3; "UnionFs::UnionFsFilter::PreWrite"
0x140079a75  mov     [rsp+3E0h+var_3C0], rax; unsigned __int64
0x140079a7a  lea     rdx, [rbp+2E0h+var_320]; int
0x140079a7e  mov     ecx, ebx; this
0x140079a80  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140079a85  mov     r8d, ebx; struct _FLT_CALLBACK_DATA *
0x140079a88  mov     rdx, rdi; enum _FLT_PREOP_CALLBACK_STATUS
0x140079a8b  mov     ecx, 4; this
0x140079a90  call    ?PreOpFinishProcessing@Utils@UnionFs@@YA?AW4_FLT_PREOP_CALLBACK_STATUS@@W43@AEAU_FLT_CALLBACK_DATA@@J_K@Z; UnionFs::Utils::PreOpFinishProcessing(_FLT_PREOP_CALLBACK_STATUS,_FLT_CALLBACK_DATA &,long,unsigned __int64)
0x140079a95  mov     rcx, [rsp+3E0h+Context]; Context
0x140079a9a  mov     ebx, eax
0x140079a9c  test    rcx, rcx
0x140079a9f  jz      loc_140079C46
0x140079aa5  call    cs:__imp_FltReleaseContext
0x140079aac  nop     dword ptr [rax+rax+00h]
0x140079ab1  jmp     loc_140079C46
0x140079ab6  mov     rbx, [rsp+3E0h+Context]
0x140079abb  test    rbx, rbx
0x140079abe  jz      loc_140079C41
0x140079ac4  lea     rdx, [rsp+3E0h+var_3A8]
0x140079ac9  mov     rcx, rbx; this
0x140079acc  call    ?SyncWithCOW@UfsStreamCtx@UnionFs@@QEAA@XZ; UnionFs::UfsStreamCtx::SyncWithCOW(void)
0x140079ad1  lea     rdx, [rsp+3E0h+var_3A8]
0x140079ad6  lea     rcx, [rsp+3E0h+Context]
0x140079adb  call    ??$make_unique@USetFileSizeContext@UnionFs@@V?$unique_struct@URundownRefCacheAware@Details@FsFltWil@@P6AXPEAU123@@Z$1?ReleaseRundownProtectionCacheAware@23@YAX0@Z$$T$0A@@wil@@$0A@@utl@@YA?AV?$unique_ptr@USetFileSizeContext@UnionFs@@U?$default_delete@USetFileSizeContext@UnionFs@@@utl@@@0@$$QEAV?$unique_struct@URundownRefCacheAware@Details@FsFltWil@@P6AXPEAU123@@Z$1?ReleaseRundownProtectionCacheAware@23@YAX0@Z$$T$0A@@wil@@@Z; utl::make_unique<UnionFs::SetFileSizeContext,wil::unique_struct<FsFltWil::Details::RundownRefCacheAware,void (*)(FsFltWil::Details::RundownRefCacheAware *),&FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *),std::nullptr_t,0>,0>(wil::unique_struct<FsFltWil::Details::RundownRefCacheAware,void (*)(FsFltWil::Details::RundownRefCacheAware *),&FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *),std::nullptr_t,0> &&)
0x140079ae0  mov     rsi, [rsp+3E0h+Context]
0x140079ae5  test    rsi, rsi
0x140079ae8  jnz     loc_140079B74
0x140079aee  lea     rax, aOriginAllocati_89; "ORIGIN: Allocating SetFileSizeContext"
0x140079af5  mov     esi, 0C000009Ah
0x140079afa  mov     ecx, esi; this
0x140079afc  mov     [rsp+3E0h+var_3C0], rax; unsigned __int64
0x140079b01  lea     r9, aUnionfsUnionfs_3; "UnionFs::UnionFsFilter::PreWrite"
0x140079b08  mov     r8, 4D200220047h; struct UnionFs::StackEventTracer *
0x140079b12  lea     rdx, [rbp+2E0h+var_320]; int
0x140079b16  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140079b1b  mov     r8d, esi; struct _FLT_CALLBACK_DATA *
0x140079b1e  mov     ecx, 4; this
0x140079b23  mov     rdx, rdi; enum _FLT_PREOP_CALLBACK_STATUS
0x140079b26  call    ?PreOpFinishProcessing@Utils@UnionFs@@YA?AW4_FLT_PREOP_CALLBACK_STATUS@@W43@AEAU_FLT_CALLBACK_DATA@@J_K@Z; UnionFs::Utils::PreOpFinishProcessing(_FLT_PREOP_CALLBACK_STATUS,_FLT_CALLBACK_DATA &,long,unsigned __int64)
0x140079b2b  lea     rcx, [rsp+3E0h+Context]
0x140079b30  mov     edi, eax
0x140079b32  call    ??1?$unique_ptr@USetFileSizeContext@UnionFs@@U?$default_delete@USetFileSizeContext@UnionFs@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<UnionFs::SetFileSizeContext,utl::default_delete<UnionFs::SetFileSizeContext>>::~unique_ptr<UnionFs::SetFileSizeContext,utl::default_delete<UnionFs::SetFileSizeContext>>(void)
0x140079b37  lea     rcx, [rsp+3E0h+var_3A8]; this
0x140079b3c  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
0x140079b41  mov     rdx, [rbp+2E0h+var_328]
0x140079b45  test    rdx, rdx
0x140079b48  jz      short loc_140079B59
0x140079b4a  mov     rcx, [rdx]
0x140079b4d  mov     rax, [rcx+18h]
0x140079b51  mov     rcx, rdx
0x140079b54  call    _guard_dispatch_icall
0x140079b59  test    rbx, rbx
0x140079b5c  jz      short loc_140079B6D
0x140079b5e  mov     rcx, rbx; Context
0x140079b61  call    cs:__imp_FltReleaseContext
0x140079b68  nop     dword ptr [rax+rax+00h]
0x140079b6d  mov     ebx, edi
0x140079b6f  jmp     loc_140079C46
0x140079b74  cmp     byte ptr [rbx+0A0h], 0
0x140079b7b  jz      loc_140079C04
0x140079b81  mov     rcx, rbx; this
0x140079b84  call    ?HasSFOs@UfsStreamCtx@UnionFs@@QEBA_NXZ; UnionFs::UfsStreamCtx::HasSFOs(void)
0x140079b89  test    al, al
0x140079b8b  jz      short loc_140079C04
0x140079b8d  call    Feature_UnionFS_OplockSupport__private_IsEnabledDeviceUsageNoInline
0x140079b92  test    eax, eax
0x140079b94  jz      short loc_140079BB4
0x140079b96  mov     eax, [rdi]
0x140079b98  test    al, 2
0x140079b9a  jz      short loc_140079BB4
0x140079b9c  mov     rax, [rbx+20h]
0x140079ba0  mov     cl, [rax+5]
0x140079ba3  cmp     cl, 1
0x140079ba6  jz      short loc_140079BB4
0x140079ba8  xor     r8d, r8d
0x140079bab  lea     ecx, [r8+3]
0x140079baf  jmp     loc_140079B23
0x140079bb4  mov     rcx, [rsi]; Context
0x140079bb7  mov     [rsi], rbx
0x140079bba  test    rcx, rcx
0x140079bbd  jz      short loc_140079BCB
0x140079bbf  call    cs:__imp_FltReleaseContext
0x140079bc6  nop     dword ptr [rax+rax+00h]
0x140079bcb  lea     rcx, [rsp+3E0h+Context]
0x140079bd0  mov     [rsp+3E0h+Context], 0
0x140079bd9  mov     [r15], rsi
0x140079bdc  call    ??1?$unique_ptr@USetFileSizeContext@UnionFs@@U?$default_delete@USetFileSizeContext@UnionFs@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<UnionFs::SetFileSizeContext,utl::default_delete<UnionFs::SetFileSizeContext>>::~unique_ptr<UnionFs::SetFileSizeContext,utl::default_delete<UnionFs::SetFileSizeContext>>(void)
0x140079be1  lea     rcx, [rsp+3E0h+var_3A8]; this
0x140079be6  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
0x140079beb  mov     rcx, [rbp+2E0h+var_328]
0x140079bef  test    rcx, rcx
0x140079bf2  jz      short loc_140079C00
0x140079bf4  mov     rax, [rcx]
0x140079bf7  mov     rax, [rax+18h]
0x140079bfb  call    _guard_dispatch_icall
0x140079c00  xor     ebx, ebx
0x140079c02  jmp     short loc_140079C46
0x140079c04  lea     rcx, [rsp+3E0h+Context]
0x140079c09  call    ??1?$unique_ptr@USetFileSizeContext@UnionFs@@U?$default_delete@USetFileSizeContext@UnionFs@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<UnionFs::SetFileSizeContext,utl::default_delete<UnionFs::SetFileSizeContext>>::~unique_ptr<UnionFs::SetFileSizeContext,utl::default_delete<UnionFs::SetFileSizeContext>>(void)
0x140079c0e  lea     rcx, [rsp+3E0h+var_3A8]; this
0x140079c13  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
0x140079c18  mov     rcx, [rbp+2E0h+var_328]
0x140079c1c  test    rcx, rcx
0x140079c1f  jz      short loc_140079C2D
0x140079c21  mov     rax, [rcx]
0x140079c24  mov     rax, [rax+18h]
0x140079c28  call    _guard_dispatch_icall
0x140079c2d  test    rbx, rbx
0x140079c30  jz      short loc_140079C41
0x140079c32  mov     rcx, rbx; Context
0x140079c35  call    cs:__imp_FltReleaseContext
0x140079c3c  nop     dword ptr [rax+rax+00h]
0x140079c41  mov     ebx, 1
0x140079c46  lea     rcx, [rbp+2E0h+var_320]; this
0x140079c4a  call    ??1StackEventTracer@UnionFs@@QEAA@XZ; UnionFs::StackEventTracer::~StackEventTracer(void)
0x140079c4f  mov     eax, ebx
0x140079c51  jmp     short loc_140079C62
0x140079c53  xor     r8d, r8d; struct _FLT_CALLBACK_DATA *
0x140079c56  mov     rdx, rdi; enum _FLT_PREOP_CALLBACK_STATUS
0x140079c59  lea     ecx, [r8+1]; this
0x140079c5d  call    ?PreOpFinishProcessing@Utils@UnionFs@@YA?AW4_FLT_PREOP_CALLBACK_STATUS@@W43@AEAU_FLT_CALLBACK_DATA@@J_K@Z; UnionFs::Utils::PreOpFinishProcessing(_FLT_PREOP_CALLBACK_STATUS,_FLT_CALLBACK_DATA &,long,unsigned __int64)
0x140079c62  mov     rcx, [rbp+2E0h+var_30]
0x140079c69  xor     rcx, rsp; StackCookie
0x140079c6c  call    __security_check_cookie
0x140079c71  mov     rbx, [rsp+3E0h+arg_18]
0x140079c79  add     rsp, 3C0h
0x140079c80  pop     r15
0x140079c82  pop     r14
0x140079c84  pop     rdi
0x140079c85  pop     rsi
0x140079c86  pop     rbp
0x140079c87  retn
```
