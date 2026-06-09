# UnionFs::UnionFsFilter::PreDirControl(_FLT_CALLBACK_DATA *,_FLT_RELATED_OBJECTS const *,void * *)

- ea: `0x14001b8c0`
- end: `0x14001bf59`
- name: `?PreDirControl@UnionFsFilter@UnionFs@@SA?AW4_FLT_PREOP_CALLBACK_STATUS@@PEAU_FLT_CALLBACK_DATA@@PEBU_FLT_RELATED_OBJECTS@@PEAPEAX@Z`
- size: `1689`
- prototype: `__int64 __fastcall(struct _FLT_CALLBACK_DATA *, struct _FLT_RELATED_OBJECTS *, void **)`
- caller_count: `0`
- callee_count: `21`
- tags: `reparse_path, loader_planting, installer_update, broker_com_uri`

## callees

- `0x14000110c`
- `0x140005574`
- `0x1400056b4`
- `0x140005ff8`
- `0x140006168`
- `0x140008140`
- `0x140008388`
- `0x14000f81c`
- `0x14001014c`
- `0x14001b8c0`
- `0x140025de8`
- `0x140027a9c`
- `0x14002ad1c`
- `0x140056bd0`
- `0x140056c44`
- `0x140056c7c`
- `0x14007a114`
- `0x14007b2b0`
- `0x14007baf0`
- `0x14007bbd0`
- `0x14007bf40`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14001bcf8`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14001bcf8`
- `FLTMGR!FltLockUserBuffer` at `0x14001bc8b`
- `FLTMGR!FltLockUserBuffer` at `0x14001bc8b`
- `FLTMGR!FltReleaseContext` at `0x14001be54`
- `FLTMGR!FltReleaseContext` at `0x14001be96`
- `FLTMGR!FltReleaseContext` at `0x14001be54`
- `FLTMGR!FltReleaseContext` at `0x14001be96`

## string_xrefs

- `0x14001ba85`: `ORIGIN: PreDirControl for FileReparsePointInformation`

## pseudocode

```c
__int64 __fastcall UnionFs::UnionFsFilter::PreDirControl(
        struct _FLT_CALLBACK_DATA *a1,
        struct _FLT_RELATED_OBJECTS *a2,
        void **a3)
{
  UnionFs::UnionFsFilter *v5; // rcx
  bool v6; // r8
  NTSTATUS v7; // r14d
  unsigned int v8; // r14d
  int *v9; // r13
  struct FsFltWil::Details::RundownRefCacheAware *v10; // rdx
  unsigned __int64 v11; // rcx
  int v12; // r9d
  int v13; // r8d
  PFLT_IO_PARAMETER_BLOCK Iopb; // r15
  struct FsFltWil::Details::RundownRefCacheAware *LowPart; // rdx
  bool v16; // zf
  const char *v17; // rax
  __int64 v18; // r8
  unsigned int v19; // ebx
  NTSTATUS v20; // r15d
  __int64 v21; // r8
  const char *v22; // rax
  int v23; // r12d
  LARGE_INTEGER AllocationSize; // rcx
  PVOID EaBuffer; // r12
  const struct _FLT_INSTANCE *Instance; // rbx
  gsl::details *v27; // rcx
  const struct _UNICODE_STRING *FileName; // r9
  PFLT_IO_PARAMETER_BLOCK v29; // rax
  int v30; // eax
  unsigned int v31; // ecx
  NTSTATUS v32; // r14d
  char *Priority; // [rsp+28h] [rbp-D8h]
  KPROCESSOR_MODE RequestorMode; // [rsp+50h] [rbp-B0h]
  enum _FILE_INFORMATION_CLASS v36; // [rsp+54h] [rbp-ACh] BYREF
  int v37; // [rsp+58h] [rbp-A8h] BYREF
  const char *v38; // [rsp+60h] [rbp-A0h] BYREF
  char v39[8]; // [rsp+68h] [rbp-98h] BYREF
  const char *v40; // [rsp+70h] [rbp-90h] BYREF
  struct _FLT_RELATED_OBJECTS *v41; // [rsp+78h] [rbp-88h]
  _QWORD v42[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v43; // [rsp+90h] [rbp-70h]
  KPROCESSOR_MODE v44; // [rsp+98h] [rbp-68h]
  PFLT_CONTEXT v45; // [rsp+A0h] [rbp-60h]
  utl::_RefCountBase *v46; // [rsp+A8h] [rbp-58h]
  __int64 v47; // [rsp+B0h] [rbp-50h] BYREF
  char v48; // [rsp+B8h] [rbp-48h]
  _BYTE v49[112]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v50; // [rsp+130h] [rbp+30h]
  PFLT_CONTEXT Context[3]; // [rsp+138h] [rbp+38h] BYREF
  _QWORD v52[17]; // [rsp+150h] [rbp+50h] BYREF
  int v53[137]; // [rsp+1D8h] [rbp+D8h] BYREF
  __int16 v54; // [rsp+3FCh] [rbp+2FCh]

  v41 = a2;
  UnionFs::StackEventTracer::StackEventTracer((UnionFs::StackEventTracer *)v53, 0x1920004054AuLL, a1);
  if ( a1->Iopb->MinorFunction == 1 )
  {
    memset(Context, 0, sizeof(Context));
    memset(v52, 0, sizeof(v52));
    v7 = UnionFs::UfsStreamHandleCtx::FltGet(
           a2->Instance,
           a2->FileObject,
           v6,
           (struct UnionFs::HandleCtxAndUnionWithRundown *)Context,
           (struct UnionFs::StackEventTracer *)v53);
    if ( v7 < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v7,
        (int)v53,
        (struct UnionFs::StackEventTracer *)0x1930004055DLL,
        (unsigned __int64)"UnionFs::UnionFsFilter::PreDirControl",
        "PUSH: Getting handle ctx",
        Priority);
      a1->IoStatus.Status = v7;
      v8 = 4;
      a1->IoStatus.Information = 0;
LABEL_79:
      UnionFs::QueryInfoContext::~QueryInfoContext((UnionFs::QueryInfoContext *)Context);
LABEL_82:
      UnionFs::StackEventTracer::~StackEventTracer((UnionFs::StackEventTracer *)v53);
      return v8;
    }
    v9 = (int *)Context[0];
    v45 = Context[1];
    v46 = (utl::_RefCountBase *)Context[2];
    v47 = v52[0];
    v48 = v52[1];
    memset(Context, 0, sizeof(Context));
    wistd::function<void (bool)>::function<void (bool)>(v49, &v52[2]);
    memset(v52, 0, sizeof(v52));
    if ( !v9 || (v13 = *v9, LOBYTE(v12) = 8, (*v9 & 8) != 0) )
    {
      FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)&v47, v10);
      if ( v50 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 24LL))(v50);
      if ( v46 )
        utl::_RefCountBase::_DecStrong(v46);
      if ( !v9 )
        goto LABEL_78;
      goto LABEL_77;
    }
    Iopb = a1->Iopb;
    v8 = 4;
    LowPart = (struct FsFltWil::Details::RundownRefCacheAware *)Iopb->Parameters.Read.ByteOffset.LowPart;
    v36 = (int)LowPart;
    if ( (int)LowPart > 38 )
    {
      v11 = (unsigned int)((_DWORD)LowPart - 60);
      if ( (_DWORD)LowPart == 60 )
        goto LABEL_33;
      v11 = (unsigned int)((_DWORD)LowPart - 63);
      if ( (_DWORD)LowPart == 63 )
        goto LABEL_33;
      v11 = (unsigned int)((_DWORD)LowPart - 78);
      if ( (_DWORD)LowPart == 78 )
        goto LABEL_33;
      v11 = (unsigned int)((_DWORD)LowPart - 79);
      if ( (_DWORD)LowPart == 79 )
        goto LABEL_33;
      v11 = (unsigned int)((_DWORD)LowPart - 80);
      if ( (_DWORD)LowPart == 80 )
        goto LABEL_33;
      v16 = (_DWORD)v11 == 1;
    }
    else
    {
      if ( (_DWORD)LowPart == 38 )
        goto LABEL_33;
      v11 = (unsigned int)((_DWORD)LowPart - 1);
      if ( (_DWORD)LowPart == 1 )
        goto LABEL_33;
      v11 = (unsigned int)((_DWORD)LowPart - 2);
      if ( (_DWORD)LowPart == 2 )
        goto LABEL_33;
      v11 = (unsigned int)((_DWORD)LowPart - 3);
      if ( (_DWORD)LowPart == 3 )
        goto LABEL_33;
      v11 = (unsigned int)((_DWORD)LowPart - 12);
      if ( (_DWORD)LowPart == 12 )
        goto LABEL_33;
      v11 = (unsigned int)((_DWORD)LowPart - 33);
      if ( (_DWORD)LowPart == 33 )
      {
        if ( *((_BYTE *)UnionFs::g_FilterState + 200) )
        {
LABEL_39:
          FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)&v47, LowPart);
          if ( v50 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 24LL))(v50);
          if ( v46 )
            utl::_RefCountBase::_DecStrong(v46);
LABEL_77:
          FltReleaseContext(v9);
LABEL_78:
          v8 = 1;
          goto LABEL_79;
        }
        v17 = "ORIGIN: PreDirControl for FileReparsePointInformation";
        v18 = 0x19D0004058FLL;
        v19 = -1073741822;
LABEL_16:
        UnionFs::ProcessTraceStatusOrigin(
          (UnionFs *)v19,
          (int)v53,
          (struct UnionFs::StackEventTracer *)v18,
          (unsigned __int64)"UnionFs::UnionFsFilter::PreDirControl",
          v17,
          Priority);
        a1->IoStatus.Status = v19;
LABEL_17:
        a1->IoStatus.Information = 0;
LABEL_67:
        FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)&v47, LowPart);
        if ( v50 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 24LL))(v50);
        if ( v46 )
          utl::_RefCountBase::_DecStrong(v46);
        FltReleaseContext(v9);
        goto LABEL_79;
      }
      v16 = (_DWORD)v11 == 4;
    }
    if ( !v16 )
    {
      if ( (unsigned int)dword_14009E178 > 3 )
      {
        v11 = qword_14009E190;
        if ( (qword_14009E188 & 0x40000) != 0 && (qword_14009E190 & 0x40000) == qword_14009E190 )
        {
          v37 = (int)LowPart;
          v38 = "onecore\\base\\fs\\unionfs\\sys\\dir.cpp";
          v36 = 1430;
          v40 = "Not handling FILE_INFORMATION_CLASS";
          *(_QWORD *)v39 = "UnionFs::UnionFsFilter::PreDirControl";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            qword_14009E190,
            (unsigned int)word_1400965E2,
            0x40000,
            v12,
            (__int64)&v40,
            (__int64)v39,
            (__int64)&v38,
            (__int64)&v36,
            (__int64)&v37);
        }
      }
      v20 = UnionFs::UnionFsFilter::CheckAndSwitchTarget(
              (UnionFs::UnionFsFilter *)v11,
              a1,
              v41,
              (struct UnionFs::StackEventTracer *)v53,
              0);
      if ( v20 < 0 )
      {
        v21 = 0x19C000405A2LL;
LABEL_31:
        v22 = "PUSH: Checking for SFO";
LABEL_32:
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)v20,
          (int)v53,
          (struct UnionFs::StackEventTracer *)v21,
          (unsigned __int64)"UnionFs::UnionFsFilter::PreDirControl",
          v22,
          Priority);
        a1->IoStatus.Status = v20;
        goto LABEL_17;
      }
      goto LABEL_39;
    }
LABEL_33:
    if ( (Iopb->OperationFlags & 8) != 0 )
    {
      if ( (v13 & 1) != 0 )
      {
        if ( (v13 & 0x20) == 0 )
        {
          a1->IoStatus.Status = -1073741809;
          goto LABEL_17;
        }
        v20 = UnionFs::UnionFsFilter::CheckAndSwitchTarget(
                (UnionFs::UnionFsFilter *)v11,
                a1,
                a2,
                (const struct UnionFs::UfsStreamHandleCtx *)v9,
                (struct UnionFs::StackEventTracer *)v53,
                0);
        if ( v20 < 0 )
        {
          v21 = 0x41A000405BCLL;
          goto LABEL_31;
        }
      }
      goto LABEL_39;
    }
    if ( Iopb->Parameters.Create.AllocationSize.QuadPart )
    {
      v23 = FltLockUserBuffer(a1);
      if ( v23 < 0 )
      {
        UnionFs::ProcessTraceStatusFromApi(
          (UnionFs *)(unsigned int)v23,
          (int)v53,
          (struct UnionFs::StackEventTracer *)0x197000405D4LL,
          (unsigned __int64)"UnionFs::UnionFsFilter::PreDirControl",
          "API: FltLockUserBuffer",
          Priority);
        a1->IoStatus.Status = v23;
        goto LABEL_17;
      }
      AllocationSize = Iopb->Parameters.Create.AllocationSize;
      if ( (*(_BYTE *)(AllocationSize.QuadPart + 10) & 5) != 0 )
        EaBuffer = *(PVOID *)(AllocationSize.QuadPart + 24);
      else
        EaBuffer = MmMapLockedPagesSpecifyCache((PMDL)AllocationSize.QuadPart, 0, MmCached, 0, 0, 0x40000010u);
      if ( !EaBuffer )
      {
        v17 = "ORIGIN: MmGetSystemAddressForMdlSafe";
        v18 = 0x198000405DELL;
        v19 = -1073741801;
        goto LABEL_16;
      }
    }
    else
    {
      EaBuffer = Iopb->Parameters.Create.EaBuffer;
      if ( (a1->Flags & 8) == 0 )
      {
        RequestorMode = a1->RequestorMode;
        goto LABEL_54;
      }
    }
    RequestorMode = 0;
LABEL_54:
    Instance = a2->Instance;
    if ( Instance != UnionFs::UfsStreamHandleCtx::TryGetScratchInstance((UnionFs::UfsStreamHandleCtx *)v9) )
      MicrosoftTelemetryAssertTriggeredMsgKM("Must be enumerating on a scratch handle");
    if ( !EaBuffer && Iopb->Parameters.Read.Length )
    {
      gsl::details::terminate(v27);
      JUMPOUT(0x14001BF58LL);
    }
    FileName = &UnionFs::g_AllFilesFilter;
    v42[0] = Iopb->Parameters.Read.Length;
    v44 = RequestorMode;
    v29 = a1->Iopb;
    v42[1] = EaBuffer;
    v43 = 0;
    if ( Iopb->Parameters.QueryEa.EaList )
      FileName = Iopb->Parameters.DirectoryControl.QueryDirectory.FileName;
    LOBYTE(Priority) = v29->OperationFlags;
    v20 = UnionFs::UfsStreamHandleCtx::EnumerateDirectoryWithMerge(
            (UnionFs::UfsStreamHandleCtx *)v9,
            a1,
            v36,
            FileName,
            Iopb->Parameters.Create.EaLength,
            Priority,
            (struct UnionFs::EnumerateDirResults *)v42,
            (struct UnionFs::StackEventTracer *)v53,
            1);
    if ( v20 >= 0 )
    {
      v30 = HIDWORD(v43);
      v53[0] = 0;
      v54 = 0;
      if ( v43 >= 0 || (v31 = 0, HIDWORD(v43) == -2147483643) )
        v31 = v43;
      a1->IoStatus.Status = HIDWORD(v43);
      if ( v30 != 260 )
        a1->IoStatus.Information = v31;
      goto LABEL_67;
    }
    v22 = "PUSH: Enumerating union";
    v21 = 0x19A00040602LL;
    goto LABEL_32;
  }
  v32 = UnionFs::UnionFsFilter::CheckAndSwitchTarget(v5, a1, a2, (struct UnionFs::StackEventTracer *)v53, 0);
  if ( v32 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v32,
      (int)v53,
      (struct UnionFs::StackEventTracer *)0x19B0004061BLL,
      (unsigned __int64)"UnionFs::UnionFsFilter::PreDirControl",
      "PUSH: Checking for SFO",
      Priority);
    a1->IoStatus.Status = v32;
    v8 = 4;
    a1->IoStatus.Information = 0;
    goto LABEL_82;
  }
  UnionFs::StackEventTracer::~StackEventTracer((UnionFs::StackEventTracer *)v53);
  return 1;
}

```

## disassembly

```asm
0x14001b8c0  mov     [rsp-8+arg_10], rbx
0x14001b8c5  push    rbp
0x14001b8c6  push    rsi
0x14001b8c7  push    rdi
0x14001b8c8  push    r12
0x14001b8ca  push    r13
0x14001b8cc  push    r14
0x14001b8ce  push    r15
0x14001b8d0  lea     rbp, [rsp-3D0h]
0x14001b8d8  sub     rsp, 4D0h
0x14001b8df  mov     rax, cs:__security_cookie
0x14001b8e6  xor     rax, rsp
0x14001b8e9  mov     [rbp+400h+var_38], rax
0x14001b8f0  mov     rbx, rdx
0x14001b8f3  mov     [rsp+500h+var_488], rdx
0x14001b8f8  mov     rsi, rcx
0x14001b8fb  mov     r8, rcx; struct _FLT_CALLBACK_DATA *
0x14001b8fe  mov     rdx, 1920004054Ah; unsigned __int64
0x14001b908  lea     rcx, [rbp+400h+var_328]; this
0x14001b90f  call    ??0StackEventTracer@UnionFs@@QEAA@_KPEBU_FLT_CALLBACK_DATA@@@Z; UnionFs::StackEventTracer::StackEventTracer(unsigned __int64,_FLT_CALLBACK_DATA const *)
0x14001b914  mov     rax, [rsi+10h]
0x14001b918  mov     r12d, 1
0x14001b91e  xor     edi, edi
0x14001b920  cmp     [rax+5], r12b
0x14001b924  jnz     loc_14001BEB0
0x14001b92a  xorps   xmm0, xmm0
0x14001b92d  mov     [rbp+400h+var_3A8], dil
0x14001b931  xorps   xmm1, xmm1
0x14001b934  mov     [rbp+400h+var_330], rdi
0x14001b93b  mov     r15d, 88h
0x14001b941  lea     rcx, [rbp+400h+var_3B0]; void *
0x14001b945  mov     r8d, r15d; Size
0x14001b948  xor     edx, edx; Val
0x14001b94a  movdqu  xmmword ptr [rbp+400h+Context], xmm0
0x14001b94f  movdqu  xmmword ptr [rbp+48h], xmm1
0x14001b954  call    memset
0x14001b959  mov     rdx, [rbx+20h]; FileObject
0x14001b95d  lea     rax, [rbp+400h+var_328]
0x14001b964  mov     rcx, [rbx+18h]; Instance
0x14001b968  lea     r9, [rbp+400h+Context]; struct UnionFs::HandleCtxAndUnionWithRundown *
0x14001b96c  mov     qword ptr [rsp+500h+BugCheckOnFailure], rax; struct UnionFs::StackEventTracer *
0x14001b971  call    ?FltGet@UfsStreamHandleCtx@UnionFs@@SAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@_NAEAUHandleCtxAndUnionWithRundown@2@AEAVStackEventTracer@2@@Z; UnionFs::UfsStreamHandleCtx::FltGet(_FLT_INSTANCE const &,_FILE_OBJECT const &,bool,UnionFs::HandleCtxAndUnionWithRundown &,UnionFs::StackEventTracer &)
0x14001b976  mov     r14d, eax
0x14001b979  test    eax, eax
0x14001b97b  jns     short loc_14001B9BB
0x14001b97d  lea     rax, aPushGettingHan; "PUSH: Getting handle ctx"
0x14001b984  mov     r8, 1930004055Dh; struct UnionFs::StackEventTracer *
0x14001b98e  lea     r9, aUnionfsUnionfs_15; "UnionFs::UnionFsFilter::PreDirControl"
0x14001b995  mov     qword ptr [rsp+500h+BugCheckOnFailure], rax; char *
0x14001b99a  lea     rdx, [rbp+400h+var_328]; int
0x14001b9a1  mov     ecx, r14d; this
0x14001b9a4  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14001b9a9  mov     [rsi+18h], r14d
0x14001b9ad  lea     r14d, [r12+3]
0x14001b9b2  mov     [rsi+20h], rdi
0x14001b9b6  jmp     loc_14001BEA5
0x14001b9bb  mov     rax, [rbp+400h+Context+8]
0x14001b9bf  lea     rdx, [rbp+400h+var_3A0]
0x14001b9c3  mov     r13, [rbp+400h+Context]
0x14001b9c7  lea     rcx, [rbp+400h+var_440]
0x14001b9cb  mov     [rbp+400h+var_460], rax
0x14001b9cf  xorps   xmm0, xmm0
0x14001b9d2  mov     rax, [rbp+400h+var_3B8]
0x14001b9d6  mov     [rbp+400h+var_458], rax
0x14001b9da  mov     rax, [rbp+400h+var_3B0]
0x14001b9de  mov     [rbp+400h+var_450], rax
0x14001b9e2  mov     al, [rbp+400h+var_3A8]
0x14001b9e5  mov     [rbp+400h+var_448], al
0x14001b9e8  mov     [rbp+400h+Context], rdi
0x14001b9ec  movdqu  xmmword ptr [rbp+400h+Context+8], xmm0
0x14001b9f1  call    ??0?$function@$$A6AX_N@Z@wistd@@QEAA@AEBV01@@Z; wistd::function<void (bool)>::function<void (bool)>(wistd::function<void (bool)> const &)
0x14001b9f6  mov     r8, r15; Size
0x14001b9f9  lea     rcx, [rbp+400h+var_3B0]; void *
0x14001b9fd  xor     edx, edx; Val
0x14001b9ff  call    memset
0x14001ba04  test    r13, r13
0x14001ba07  jz      loc_14001BE62
0x14001ba0d  mov     r8d, [r13+0]
0x14001ba11  mov     r9b, 8
0x14001ba14  test    r9b, r8b
0x14001ba17  jnz     loc_14001BE62
0x14001ba1d  mov     r15, [rsi+10h]
0x14001ba21  mov     r14d, 4
0x14001ba27  mov     edx, [r15+28h]; struct FsFltWil::Details::RundownRefCacheAware *
0x14001ba2b  mov     [rsp+500h+var_4AC], edx
0x14001ba2f  cmp     edx, 26h ; '&'
0x14001ba32  jg      loc_14001BAC1
0x14001ba38  jz      loc_14001BBEF
0x14001ba3e  mov     ecx, edx
0x14001ba40  sub     ecx, r12d
0x14001ba43  jz      loc_14001BBEF
0x14001ba49  sub     ecx, r12d
0x14001ba4c  jz      loc_14001BBEF
0x14001ba52  sub     ecx, r12d
0x14001ba55  jz      loc_14001BBEF
0x14001ba5b  sub     ecx, 9
0x14001ba5e  jz      loc_14001BBEF
0x14001ba64  sub     ecx, 15h
0x14001ba67  jz      short loc_14001BA71
0x14001ba69  cmp     ecx, r14d
0x14001ba6c  jmp     loc_14001BAF3
0x14001ba71  mov     rax, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14001ba78  cmp     [rax+0C8h], dil
0x14001ba7f  jnz     loc_14001BC49
0x14001ba85  lea     rax, aOriginPredirco; "ORIGIN: PreDirControl for FileReparsePo"...
0x14001ba8c  mov     r8, 19D0004058Fh; struct UnionFs::StackEventTracer *
0x14001ba96  mov     ebx, 0C0000002h
0x14001ba9b  lea     rdx, [rbp+400h+var_328]; int
0x14001baa2  mov     qword ptr [rsp+500h+BugCheckOnFailure], rax; char *
0x14001baa7  lea     r9, aUnionfsUnionfs_15; "UnionFs::UnionFsFilter::PreDirControl"
0x14001baae  mov     ecx, ebx; this
0x14001bab0  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14001bab5  mov     [rsi+18h], ebx
0x14001bab8  mov     [rsi+20h], rdi
0x14001babc  jmp     loc_14001BE25
0x14001bac1  mov     ecx, edx
0x14001bac3  sub     ecx, 3Ch ; '<'
0x14001bac6  jz      loc_14001BBEF
0x14001bacc  sub     ecx, 3
0x14001bacf  jz      loc_14001BBEF
0x14001bad5  sub     ecx, 0Fh
0x14001bad8  jz      loc_14001BBEF
0x14001bade  sub     ecx, r12d
0x14001bae1  jz      loc_14001BBEF
0x14001bae7  sub     ecx, r12d
0x14001baea  jz      loc_14001BBEF
0x14001baf0  cmp     ecx, r12d
0x14001baf3  jz      loc_14001BBEF
0x14001baf9  mov     eax, cs:dword_14009E178
0x14001baff  lea     rbx, aUnionfsUnionfs_15; "UnionFs::UnionFsFilter::PreDirControl"
0x14001bb06  cmp     eax, 3
0x14001bb09  jbe     loc_14001BB9A
0x14001bb0f  mov     rcx, cs:qword_14009E190
0x14001bb16  mov     r8d, 40000h
0x14001bb1c  mov     rax, cs:qword_14009E188
0x14001bb23  test    r8, rax
0x14001bb26  jz      short loc_14001BB9A
0x14001bb28  mov     rax, rcx
0x14001bb2b  and     rax, r8
0x14001bb2e  cmp     rax, rcx
0x14001bb31  jnz     short loc_14001BB9A
0x14001bb33  lea     rax, aOnecoreBaseFsU_9; "onecore\\base\\fs\\unionfs\\sys\\dir.cp"...
0x14001bb3a  mov     [rsp+500h+var_4A8], edx
0x14001bb3e  mov     [rsp+500h+var_4A0], rax
0x14001bb43  lea     rdx, word_1400965E2
0x14001bb4a  lea     rax, aNotHandlingFil; "Not handling FILE_INFORMATION_CLASS"
0x14001bb51  mov     [rsp+500h+var_4AC], 596h
0x14001bb59  mov     [rsp+500h+var_490], rax
0x14001bb5e  lea     rax, [rsp+500h+var_4A8]
0x14001bb63  mov     qword ptr [rsp+500h+var_4C0], rax
0x14001bb68  lea     rax, [rsp+500h+var_4AC]
0x14001bb6d  mov     [rsp+500h+var_4C8], rax
0x14001bb72  lea     rax, [rsp+500h+var_4A0]
0x14001bb77  mov     [rsp+500h+var_4D0], rax
0x14001bb7c  lea     rax, [rsp+500h+var_498]
0x14001bb81  mov     qword ptr [rsp+500h+Priority], rax; char *
0x14001bb86  lea     rax, [rsp+500h+var_490]
0x14001bb8b  mov     qword ptr [rsp+500h+BugCheckOnFailure], rax
0x14001bb90  mov     qword ptr [rsp+500h+var_498], rbx
0x14001bb95  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14001bb9a  mov     r8, [rsp+500h+var_488]; struct _FLT_RELATED_OBJECTS *
0x14001bb9f  lea     r9, [rbp+400h+var_328]; struct UnionFs::StackEventTracer *
0x14001bba6  mov     rdx, rsi; struct _FLT_CALLBACK_DATA *
0x14001bba9  mov     qword ptr [rsp+500h+BugCheckOnFailure], rdi; struct UnionFs::CheckAndSwitchResults *
0x14001bbae  call    ?CheckAndSwitchTarget@UnionFsFilter@UnionFs@@QEAAJAEAU_FLT_CALLBACK_DATA@@AEBU_FLT_RELATED_OBJECTS@@AEAVStackEventTracer@2@PEAUCheckAndSwitchResults@2@@Z; UnionFs::UnionFsFilter::CheckAndSwitchTarget(_FLT_CALLBACK_DATA &,_FLT_RELATED_OBJECTS const &,UnionFs::StackEventTracer &,UnionFs::CheckAndSwitchResults *)
0x14001bbb3  mov     r15d, eax
0x14001bbb6  test    eax, eax
0x14001bbb8  jns     loc_14001BC49
0x14001bbbe  mov     r9, rbx; unsigned __int64
0x14001bbc1  mov     r8, 19C000405A2h; struct UnionFs::StackEventTracer *
0x14001bbcb  lea     rax, aPushCheckingFo; "PUSH: Checking for SFO"
0x14001bbd2  lea     rdx, [rbp+400h+var_328]; int
0x14001bbd9  mov     qword ptr [rsp+500h+BugCheckOnFailure], rax; char *
0x14001bbde  mov     ecx, r15d; this
0x14001bbe1  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14001bbe6  mov     [rsi+18h], r15d
0x14001bbea  jmp     loc_14001BAB8
0x14001bbef  test    [r15+6], r9b
0x14001bbf3  jz      loc_14001BC7E
0x14001bbf9  test    r12b, r8b
0x14001bbfc  jz      short loc_14001BC49
0x14001bbfe  test    r8b, 20h
0x14001bc02  jnz     short loc_14001BC10
0x14001bc04  mov     dword ptr [rsi+18h], 0C000000Fh
0x14001bc0b  jmp     loc_14001BAB8
0x14001bc10  lea     rax, [rbp+400h+var_328]
0x14001bc17  mov     qword ptr [rsp+500h+Priority], rdi; struct UnionFs::CheckAndSwitchResults *
0x14001bc1c  mov     r9, r13; struct UnionFs::UfsStreamHandleCtx *
0x14001bc1f  mov     qword ptr [rsp+500h+BugCheckOnFailure], rax; struct UnionFs::StackEventTracer *
0x14001bc24  mov     r8, rbx; struct _FLT_RELATED_OBJECTS *
0x14001bc27  mov     rdx, rsi; struct _FLT_CALLBACK_DATA *
0x14001bc2a  call    ?CheckAndSwitchTarget@UnionFsFilter@UnionFs@@QEAAJAEAU_FLT_CALLBACK_DATA@@AEBU_FLT_RELATED_OBJECTS@@AEBVUfsStreamHandleCtx@2@AEAVStackEventTracer@2@PEAUCheckAndSwitchResults@2@@Z; UnionFs::UnionFsFilter::CheckAndSwitchTarget(_FLT_CALLBACK_DATA &,_FLT_RELATED_OBJECTS const &,UnionFs::UfsStreamHandleCtx const &,UnionFs::StackEventTracer &,UnionFs::CheckAndSwitchResults *)
0x14001bc2f  mov     r15d, eax
0x14001bc32  test    eax, eax
0x14001bc34  jns     short loc_14001BC49
0x14001bc36  lea     r9, aUnionfsUnionfs_15; "UnionFs::UnionFsFilter::PreDirControl"
0x14001bc3d  mov     r8, 41A000405BCh
0x14001bc47  jmp     short loc_14001BBCB
0x14001bc49  lea     rcx, [rbp+400h+var_450]; this
0x14001bc4d  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
0x14001bc52  mov     rcx, [rbp+400h+var_3D0]
0x14001bc56  test    rcx, rcx
0x14001bc59  jz      short loc_14001BC67
0x14001bc5b  mov     rax, [rcx]
0x14001bc5e  mov     rax, [rax+18h]
0x14001bc62  call    _guard_dispatch_icall
0x14001bc67  mov     rcx, [rbp+400h+var_458]; this
0x14001bc6b  test    rcx, rcx
0x14001bc6e  jz      loc_14001BE93
0x14001bc74  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14001bc79  jmp     loc_14001BE93
0x14001bc7e  cmp     [r15+40h], rdi
0x14001bc82  jz      loc_14001BD2E
0x14001bc88  mov     rcx, rsi; CallbackData
0x14001bc8b  call    cs:__imp_FltLockUserBuffer
0x14001bc92  nop     dword ptr [rax+rax+00h]
0x14001bc97  mov     r12d, eax
0x14001bc9a  test    eax, eax
0x14001bc9c  jns     short loc_14001BCD3
0x14001bc9e  lea     rax, aApiFltlockuser; "API: FltLockUserBuffer"
0x14001bca5  mov     r8, 197000405D4h; struct UnionFs::StackEventTracer *
0x14001bcaf  lea     r9, aUnionfsUnionfs_15; "UnionFs::UnionFsFilter::PreDirControl"
0x14001bcb6  mov     qword ptr [rsp+500h+BugCheckOnFailure], rax; char *
0x14001bcbb  lea     rdx, [rbp+400h+var_328]; int
0x14001bcc2  mov     ecx, r12d; this
0x14001bcc5  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14001bcca  mov     [rsi+18h], r12d
0x14001bcce  jmp     loc_14001BAB8
0x14001bcd3  mov     rcx, [r15+40h]; MemoryDescriptorList
0x14001bcd7  test    byte ptr [rcx+0Ah], 5
0x14001bcdb  jz      short loc_14001BCE3
0x14001bcdd  mov     r12, [rcx+18h]
0x14001bce1  jmp     short loc_14001BD07
0x14001bce3  xor     r9d, r9d; RequestedAddress
0x14001bce6  mov     [rsp+500h+Priority], 40000010h; Priority
0x14001bcee  xor     edx, edx; AccessMode
0x14001bcf0  mov     [rsp+500h+BugCheckOnFailure], edi; BugCheckOnFailure
0x14001bcf4  lea     r8d, [r9+1]; CacheType
0x14001bcf8  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14001bcff  nop     dword ptr [rax+rax+00h]
0x14001bd04  mov     r12, rax
0x14001bd07  test    r12, r12
0x14001bd0a  jnz     short loc_14001BD27
0x14001bd0c  lea     rax, aOriginMmgetsys; "ORIGIN: MmGetSystemAddressForMdlSafe"
0x14001bd13  mov     r8, 198000405DEh
0x14001bd1d  mov     ebx, 0C0000017h
0x14001bd22  jmp     loc_14001BA9B
0x14001bd27  mov     [rsp+500h+var_4B0], dil
0x14001bd2c  jmp     short loc_14001BD40
0x14001bd2e  mov     eax, [rsi]
0x14001bd30  mov     r12, [r15+38h]
0x14001bd34  test    r9b, al
0x14001bd37  jnz     short loc_14001BD27
0x14001bd39  mov     al, [rsi+50h]
0x14001bd3c  mov     [rsp+500h+var_4B0], al
0x14001bd40  mov     rbx, [rbx+18h]
0x14001bd44  mov     rcx, r13; this
0x14001bd47  call    ?TryGetScratchInstance@UfsStreamHandleCtx@UnionFs@@QEBAPEBU_FLT_INSTANCE@@XZ; UnionFs::UfsStreamHandleCtx::TryGetScratchInstance(void)
0x14001bd4c  cmp     rbx, rax
0x14001bd4f  jz      short loc_14001BD5D
0x14001bd51  lea     rcx, aMustBeEnumerat; "Must be enumerating on a scratch handle"
0x14001bd58  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x14001bd5d  mov     eax, [r15+18h]
0x14001bd61  test    r12, r12
0x14001bd64  jnz     short loc_14001BD6F
0x14001bd66  test    rax, rax
0x14001bd69  jnz     loc_14001BF53
0x14001bd6f  mov     r8d, [rsp+500h+var_4AC]; enum _FILE_INFORMATION_CLASS
0x14001bd74  lea     r9, ?g_AllFilesFilter@UnionFs@@3U_UNICODE_STRING@@B; _UNICODE_STRING const UnionFs::g_AllFilesFilter
0x14001bd7b  mov     [rbp+400h+var_480], rax
0x14001bd7f  mov     al, [rsp+500h+var_4B0]
0x14001bd83  mov     [rbp+400h+var_468], al
0x14001bd86  mov     rax, [rsi+10h]
0x14001bd8a  mov     [rbp+400h+var_478], r12
0x14001bd8e  mov     [rbp+400h+var_470], rdi
0x14001bd92  mov     edx, [r15+30h]
0x14001bd96  mov     cl, [rax+6]
0x14001bd99  mov     rax, [r15+20h]
0x14001bd9d  test    rax, rax
0x14001bda0  mov     [rsp+500h+var_4C0], 1; bool
0x14001bda5  cmovnz  r9, rax; struct _UNICODE_STRING *
0x14001bda9  lea     rax, [rbp+400h+var_328]
0x14001bdb0  mov     [rsp+500h+var_4C8], rax; struct UnionFs::StackEventTracer *
0x14001bdb5  lea     rax, [rbp+400h+var_480]
0x14001bdb9  mov     [rsp+500h+var_4D0], rax; struct UnionFs::EnumerateDirResults *
0x14001bdbe  mov     byte ptr [rsp+500h+Priority], cl; char *
0x14001bdc2  mov     rcx, r13; this
0x14001bdc5  mov     [rsp+500h+BugCheckOnFailure], edx; unsigned int
0x14001bdc9  mov     rdx, rsi; struct _FLT_CALLBACK_DATA *
0x14001bdcc  call    ?EnumerateDirectoryWithMerge@UfsStreamHandleCtx@UnionFs@@QEBAJAEBU_FLT_CALLBACK_DATA@@W4_FILE_INFORMATION_CLASS@@AEBU_UNICODE_STRING@@KEAEAUEnumerateDirResults@2@AEAVStackEventTracer@2@_N@Z; UnionFs::UfsStreamHandleCtx::EnumerateDirectoryWithMerge(_FLT_CALLBACK_DATA const &,_FILE_INFORMATION_CLASS,_UNICODE_STRING const &,ulong,uchar,UnionFs::EnumerateDirResults &,UnionFs::StackEventTracer &,bool)
0x14001bdd1  mov     r15d, eax
0x14001bdd4  test    eax, eax
0x14001bdd6  jns     short loc_14001BDF5
0x14001bdd8  lea     rax, aPushEnumeratin_1; "PUSH: Enumerating union"
0x14001bddf  mov     r8, 19A00040602h
0x14001bde9  lea     r9, aUnionfsUnionfs_15; "UnionFs::UnionFsFilter::PreDirControl"
0x14001bdf0  jmp     loc_14001BBD2
0x14001bdf5  mov     eax, dword ptr [rbp+400h+var_470+4]
0x14001bdf8  mov     [rbp+400h+var_328], edi
0x14001bdfe  mov     [rbp+400h+var_104], di
  ... truncated ...
```
