# UnionFs::UnionFsFilter::PreDirControl(_FLT_CALLBACK_DATA *,_FLT_RELATED_OBJECTS const *,void * *)

- ea: `0x14001b820`
- end: `0x14001beb9`
- name: `?PreDirControl@UnionFsFilter@UnionFs@@SA?AW4_FLT_PREOP_CALLBACK_STATUS@@PEAU_FLT_CALLBACK_DATA@@PEBU_FLT_RELATED_OBJECTS@@PEAPEAX@Z`
- size: `1689`
- prototype: `enum _FLT_PREOP_CALLBACK_STATUS __fastcall(struct _FLT_CALLBACK_DATA *, const struct _FLT_RELATED_OBJECTS *, void **)`
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
- `0x14000f7fc`
- `0x14001012c`
- `0x14001b820`
- `0x140025d48`
- `0x1400279fc`
- `0x14002ac7c`
- `0x140056a50`
- `0x140056ac4`
- `0x140056afc`
- `0x140079df4`
- `0x14007af90`
- `0x14007b7d0`
- `0x14007b8b0`
- `0x14007bc00`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14001bc58`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14001bc58`
- `FLTMGR!FltLockUserBuffer` at `0x14001bbeb`
- `FLTMGR!FltLockUserBuffer` at `0x14001bbeb`
- `FLTMGR!FltReleaseContext` at `0x14001bdb4`
- `FLTMGR!FltReleaseContext` at `0x14001bdf6`
- `FLTMGR!FltReleaseContext` at `0x14001bdb4`
- `FLTMGR!FltReleaseContext` at `0x14001bdf6`

## string_xrefs

- `0x14001b9e5`: `ORIGIN: PreDirControl for FileReparsePointInformation`

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
  struct _KEVENT *v9; // r13
  struct FsFltWil::Details::RundownRefCacheAware *v10; // rdx
  unsigned __int64 v11; // rcx
  int v12; // r9d
  LONG LockNV; // r8d
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
  struct _UNICODE_STRING *FileName; // r9
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
    v9 = (struct _KEVENT *)Context[0];
    v45 = Context[1];
    v46 = (utl::_RefCountBase *)Context[2];
    v47 = v52[0];
    v48 = v52[1];
    memset(Context, 0, sizeof(Context));
    wistd::function<void (bool)>::function<void (bool)>(v49, &v52[2]);
    memset(v52, 0, sizeof(v52));
    if ( !v9 || (LockNV = v9->Header.LockNV, LOBYTE(v12) = 8, (v9->Header.LockNV & 8) != 0) )
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
            (unsigned int)word_140096562,
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
      if ( (LockNV & 1) != 0 )
      {
        if ( (LockNV & 0x20) == 0 )
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
      JUMPOUT(0x14001BEB8LL);
    }
    FileName = (struct _UNICODE_STRING *)&UnionFs::g_AllFilesFilter;
    v42[0] = Iopb->Parameters.Read.Length;
    v44 = RequestorMode;
    v29 = a1->Iopb;
    v42[1] = EaBuffer;
    v43 = 0;
    if ( Iopb->Parameters.QueryEa.EaList )
      FileName = Iopb->Parameters.DirectoryControl.QueryDirectory.FileName;
    LOBYTE(Priority) = v29->OperationFlags;
    v20 = UnionFs::UfsStreamHandleCtx::EnumerateDirectoryWithMerge(
            v9,
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
0x14001b820  mov     [rsp-8+arg_10], rbx
0x14001b825  push    rbp
0x14001b826  push    rsi
0x14001b827  push    rdi
0x14001b828  push    r12
0x14001b82a  push    r13
0x14001b82c  push    r14
0x14001b82e  push    r15
0x14001b830  lea     rbp, [rsp-3D0h]
0x14001b838  sub     rsp, 4D0h
0x14001b83f  mov     rax, cs:__security_cookie
0x14001b846  xor     rax, rsp
0x14001b849  mov     [rbp+400h+var_38], rax
0x14001b850  mov     rbx, rdx
0x14001b853  mov     [rsp+500h+var_488], rdx
0x14001b858  mov     rsi, rcx
0x14001b85b  mov     r8, rcx; struct _FLT_CALLBACK_DATA *
0x14001b85e  mov     rdx, 1920004054Ah; unsigned __int64
0x14001b868  lea     rcx, [rbp+400h+var_328]; this
0x14001b86f  call    ??0StackEventTracer@UnionFs@@QEAA@_KPEBU_FLT_CALLBACK_DATA@@@Z; UnionFs::StackEventTracer::StackEventTracer(unsigned __int64,_FLT_CALLBACK_DATA const *)
0x14001b874  mov     rax, [rsi+10h]
0x14001b878  mov     r12d, 1
0x14001b87e  xor     edi, edi
0x14001b880  cmp     [rax+5], r12b
0x14001b884  jnz     loc_14001BE10
0x14001b88a  xorps   xmm0, xmm0
0x14001b88d  mov     [rbp+400h+var_3A8], dil
0x14001b891  xorps   xmm1, xmm1
0x14001b894  mov     [rbp+400h+var_330], rdi
0x14001b89b  mov     r15d, 88h
0x14001b8a1  lea     rcx, [rbp+400h+var_3B0]; void *
0x14001b8a5  mov     r8d, r15d; Size
0x14001b8a8  xor     edx, edx; Val
0x14001b8aa  movdqu  xmmword ptr [rbp+400h+Context], xmm0
0x14001b8af  movdqu  xmmword ptr [rbp+48h], xmm1
0x14001b8b4  call    memset
0x14001b8b9  mov     rdx, [rbx+20h]; FileObject
0x14001b8bd  lea     rax, [rbp+400h+var_328]
0x14001b8c4  mov     rcx, [rbx+18h]; Instance
0x14001b8c8  lea     r9, [rbp+400h+Context]; struct UnionFs::HandleCtxAndUnionWithRundown *
0x14001b8cc  mov     qword ptr [rsp+500h+BugCheckOnFailure], rax; struct UnionFs::StackEventTracer *
0x14001b8d1  call    ?FltGet@UfsStreamHandleCtx@UnionFs@@SAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@_NAEAUHandleCtxAndUnionWithRundown@2@AEAVStackEventTracer@2@@Z; UnionFs::UfsStreamHandleCtx::FltGet(_FLT_INSTANCE const &,_FILE_OBJECT const &,bool,UnionFs::HandleCtxAndUnionWithRundown &,UnionFs::StackEventTracer &)
0x14001b8d6  mov     r14d, eax
0x14001b8d9  test    eax, eax
0x14001b8db  jns     short loc_14001B91B
0x14001b8dd  lea     rax, aPushGettingHan; "PUSH: Getting handle ctx"
0x14001b8e4  mov     r8, 1930004055Dh; struct UnionFs::StackEventTracer *
0x14001b8ee  lea     r9, aUnionfsUnionfs_15; "UnionFs::UnionFsFilter::PreDirControl"
0x14001b8f5  mov     qword ptr [rsp+500h+BugCheckOnFailure], rax; char *
0x14001b8fa  lea     rdx, [rbp+400h+var_328]; int
0x14001b901  mov     ecx, r14d; this
0x14001b904  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14001b909  mov     [rsi+18h], r14d
0x14001b90d  lea     r14d, [r12+3]
0x14001b912  mov     [rsi+20h], rdi
0x14001b916  jmp     loc_14001BE05
0x14001b91b  mov     rax, [rbp+400h+Context+8]
0x14001b91f  lea     rdx, [rbp+400h+var_3A0]
0x14001b923  mov     r13, [rbp+400h+Context]
0x14001b927  lea     rcx, [rbp+400h+var_440]
0x14001b92b  mov     [rbp+400h+var_460], rax
0x14001b92f  xorps   xmm0, xmm0
0x14001b932  mov     rax, [rbp+400h+var_3B8]
0x14001b936  mov     [rbp+400h+var_458], rax
0x14001b93a  mov     rax, [rbp+400h+var_3B0]
0x14001b93e  mov     [rbp+400h+var_450], rax
0x14001b942  mov     al, [rbp+400h+var_3A8]
0x14001b945  mov     [rbp+400h+var_448], al
0x14001b948  mov     [rbp+400h+Context], rdi
0x14001b94c  movdqu  xmmword ptr [rbp+400h+Context+8], xmm0
0x14001b951  call    ??0?$function@$$A6AX_N@Z@wistd@@QEAA@AEBV01@@Z; wistd::function<void (bool)>::function<void (bool)>(wistd::function<void (bool)> const &)
0x14001b956  mov     r8, r15; Size
0x14001b959  lea     rcx, [rbp+400h+var_3B0]; void *
0x14001b95d  xor     edx, edx; Val
0x14001b95f  call    memset
0x14001b964  test    r13, r13
0x14001b967  jz      loc_14001BDC2
0x14001b96d  mov     r8d, [r13+0]
0x14001b971  mov     r9b, 8
0x14001b974  test    r9b, r8b
0x14001b977  jnz     loc_14001BDC2
0x14001b97d  mov     r15, [rsi+10h]
0x14001b981  mov     r14d, 4
0x14001b987  mov     edx, [r15+28h]; struct FsFltWil::Details::RundownRefCacheAware *
0x14001b98b  mov     [rsp+500h+var_4AC], edx
0x14001b98f  cmp     edx, 26h ; '&'
0x14001b992  jg      loc_14001BA21
0x14001b998  jz      loc_14001BB4F
0x14001b99e  mov     ecx, edx
0x14001b9a0  sub     ecx, r12d
0x14001b9a3  jz      loc_14001BB4F
0x14001b9a9  sub     ecx, r12d
0x14001b9ac  jz      loc_14001BB4F
0x14001b9b2  sub     ecx, r12d
0x14001b9b5  jz      loc_14001BB4F
0x14001b9bb  sub     ecx, 9
0x14001b9be  jz      loc_14001BB4F
0x14001b9c4  sub     ecx, 15h
0x14001b9c7  jz      short loc_14001B9D1
0x14001b9c9  cmp     ecx, r14d
0x14001b9cc  jmp     loc_14001BA53
0x14001b9d1  mov     rax, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14001b9d8  cmp     [rax+0C8h], dil
0x14001b9df  jnz     loc_14001BBA9
0x14001b9e5  lea     rax, aOriginPredirco; "ORIGIN: PreDirControl for FileReparsePo"...
0x14001b9ec  mov     r8, 19D0004058Fh; struct UnionFs::StackEventTracer *
0x14001b9f6  mov     ebx, 0C0000002h
0x14001b9fb  lea     rdx, [rbp+400h+var_328]; int
0x14001ba02  mov     qword ptr [rsp+500h+BugCheckOnFailure], rax; char *
0x14001ba07  lea     r9, aUnionfsUnionfs_15; "UnionFs::UnionFsFilter::PreDirControl"
0x14001ba0e  mov     ecx, ebx; this
0x14001ba10  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14001ba15  mov     [rsi+18h], ebx
0x14001ba18  mov     [rsi+20h], rdi
0x14001ba1c  jmp     loc_14001BD85
0x14001ba21  mov     ecx, edx
0x14001ba23  sub     ecx, 3Ch ; '<'
0x14001ba26  jz      loc_14001BB4F
0x14001ba2c  sub     ecx, 3
0x14001ba2f  jz      loc_14001BB4F
0x14001ba35  sub     ecx, 0Fh
0x14001ba38  jz      loc_14001BB4F
0x14001ba3e  sub     ecx, r12d
0x14001ba41  jz      loc_14001BB4F
0x14001ba47  sub     ecx, r12d
0x14001ba4a  jz      loc_14001BB4F
0x14001ba50  cmp     ecx, r12d
0x14001ba53  jz      loc_14001BB4F
0x14001ba59  mov     eax, cs:dword_14009E178
0x14001ba5f  lea     rbx, aUnionfsUnionfs_15; "UnionFs::UnionFsFilter::PreDirControl"
0x14001ba66  cmp     eax, 3
0x14001ba69  jbe     loc_14001BAFA
0x14001ba6f  mov     rcx, cs:qword_14009E190
0x14001ba76  mov     r8d, 40000h
0x14001ba7c  mov     rax, cs:qword_14009E188
0x14001ba83  test    r8, rax
0x14001ba86  jz      short loc_14001BAFA
0x14001ba88  mov     rax, rcx
0x14001ba8b  and     rax, r8
0x14001ba8e  cmp     rax, rcx
0x14001ba91  jnz     short loc_14001BAFA
0x14001ba93  lea     rax, aOnecoreBaseFsU_9; "onecore\\base\\fs\\unionfs\\sys\\dir.cp"...
0x14001ba9a  mov     [rsp+500h+var_4A8], edx
0x14001ba9e  mov     [rsp+500h+var_4A0], rax
0x14001baa3  lea     rdx, word_140096562
0x14001baaa  lea     rax, aNotHandlingFil; "Not handling FILE_INFORMATION_CLASS"
0x14001bab1  mov     [rsp+500h+var_4AC], 596h
0x14001bab9  mov     [rsp+500h+var_490], rax
0x14001babe  lea     rax, [rsp+500h+var_4A8]
0x14001bac3  mov     qword ptr [rsp+500h+var_4C0], rax
0x14001bac8  lea     rax, [rsp+500h+var_4AC]
0x14001bacd  mov     [rsp+500h+var_4C8], rax
0x14001bad2  lea     rax, [rsp+500h+var_4A0]
0x14001bad7  mov     [rsp+500h+var_4D0], rax
0x14001badc  lea     rax, [rsp+500h+var_498]
0x14001bae1  mov     qword ptr [rsp+500h+Priority], rax; char *
0x14001bae6  lea     rax, [rsp+500h+var_490]
0x14001baeb  mov     qword ptr [rsp+500h+BugCheckOnFailure], rax
0x14001baf0  mov     qword ptr [rsp+500h+var_498], rbx
0x14001baf5  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14001bafa  mov     r8, [rsp+500h+var_488]; struct _FLT_RELATED_OBJECTS *
0x14001baff  lea     r9, [rbp+400h+var_328]; struct UnionFs::StackEventTracer *
0x14001bb06  mov     rdx, rsi; struct _FLT_CALLBACK_DATA *
0x14001bb09  mov     qword ptr [rsp+500h+BugCheckOnFailure], rdi; struct UnionFs::CheckAndSwitchResults *
0x14001bb0e  call    ?CheckAndSwitchTarget@UnionFsFilter@UnionFs@@QEAAJAEAU_FLT_CALLBACK_DATA@@AEBU_FLT_RELATED_OBJECTS@@AEAVStackEventTracer@2@PEAUCheckAndSwitchResults@2@@Z; UnionFs::UnionFsFilter::CheckAndSwitchTarget(_FLT_CALLBACK_DATA &,_FLT_RELATED_OBJECTS const &,UnionFs::StackEventTracer &,UnionFs::CheckAndSwitchResults *)
0x14001bb13  mov     r15d, eax
0x14001bb16  test    eax, eax
0x14001bb18  jns     loc_14001BBA9
0x14001bb1e  mov     r9, rbx; unsigned __int64
0x14001bb21  mov     r8, 19C000405A2h; struct UnionFs::StackEventTracer *
0x14001bb2b  lea     rax, aPushCheckingFo; "PUSH: Checking for SFO"
0x14001bb32  lea     rdx, [rbp+400h+var_328]; int
0x14001bb39  mov     qword ptr [rsp+500h+BugCheckOnFailure], rax; char *
0x14001bb3e  mov     ecx, r15d; this
0x14001bb41  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14001bb46  mov     [rsi+18h], r15d
0x14001bb4a  jmp     loc_14001BA18
0x14001bb4f  test    [r15+6], r9b
0x14001bb53  jz      loc_14001BBDE
0x14001bb59  test    r12b, r8b
0x14001bb5c  jz      short loc_14001BBA9
0x14001bb5e  test    r8b, 20h
0x14001bb62  jnz     short loc_14001BB70
0x14001bb64  mov     dword ptr [rsi+18h], 0C000000Fh
0x14001bb6b  jmp     loc_14001BA18
0x14001bb70  lea     rax, [rbp+400h+var_328]
0x14001bb77  mov     qword ptr [rsp+500h+Priority], rdi; struct UnionFs::CheckAndSwitchResults *
0x14001bb7c  mov     r9, r13; struct UnionFs::UfsStreamHandleCtx *
0x14001bb7f  mov     qword ptr [rsp+500h+BugCheckOnFailure], rax; struct UnionFs::StackEventTracer *
0x14001bb84  mov     r8, rbx; struct _FLT_RELATED_OBJECTS *
0x14001bb87  mov     rdx, rsi; struct _FLT_CALLBACK_DATA *
0x14001bb8a  call    ?CheckAndSwitchTarget@UnionFsFilter@UnionFs@@QEAAJAEAU_FLT_CALLBACK_DATA@@AEBU_FLT_RELATED_OBJECTS@@AEBVUfsStreamHandleCtx@2@AEAVStackEventTracer@2@PEAUCheckAndSwitchResults@2@@Z; UnionFs::UnionFsFilter::CheckAndSwitchTarget(_FLT_CALLBACK_DATA &,_FLT_RELATED_OBJECTS const &,UnionFs::UfsStreamHandleCtx const &,UnionFs::StackEventTracer &,UnionFs::CheckAndSwitchResults *)
0x14001bb8f  mov     r15d, eax
0x14001bb92  test    eax, eax
0x14001bb94  jns     short loc_14001BBA9
0x14001bb96  lea     r9, aUnionfsUnionfs_15; "UnionFs::UnionFsFilter::PreDirControl"
0x14001bb9d  mov     r8, 41A000405BCh
0x14001bba7  jmp     short loc_14001BB2B
0x14001bba9  lea     rcx, [rbp+400h+var_450]; this
0x14001bbad  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
0x14001bbb2  mov     rcx, [rbp+400h+var_3D0]
0x14001bbb6  test    rcx, rcx
0x14001bbb9  jz      short loc_14001BBC7
0x14001bbbb  mov     rax, [rcx]
0x14001bbbe  mov     rax, [rax+18h]
0x14001bbc2  call    _guard_dispatch_icall
0x14001bbc7  mov     rcx, [rbp+400h+var_458]; this
0x14001bbcb  test    rcx, rcx
0x14001bbce  jz      loc_14001BDF3
0x14001bbd4  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14001bbd9  jmp     loc_14001BDF3
0x14001bbde  cmp     [r15+40h], rdi
0x14001bbe2  jz      loc_14001BC8E
0x14001bbe8  mov     rcx, rsi; CallbackData
0x14001bbeb  call    cs:__imp_FltLockUserBuffer
0x14001bbf2  nop     dword ptr [rax+rax+00h]
0x14001bbf7  mov     r12d, eax
0x14001bbfa  test    eax, eax
0x14001bbfc  jns     short loc_14001BC33
0x14001bbfe  lea     rax, aApiFltlockuser; "API: FltLockUserBuffer"
0x14001bc05  mov     r8, 197000405D4h; struct UnionFs::StackEventTracer *
0x14001bc0f  lea     r9, aUnionfsUnionfs_15; "UnionFs::UnionFsFilter::PreDirControl"
0x14001bc16  mov     qword ptr [rsp+500h+BugCheckOnFailure], rax; char *
0x14001bc1b  lea     rdx, [rbp+400h+var_328]; int
0x14001bc22  mov     ecx, r12d; this
0x14001bc25  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14001bc2a  mov     [rsi+18h], r12d
0x14001bc2e  jmp     loc_14001BA18
0x14001bc33  mov     rcx, [r15+40h]; MemoryDescriptorList
0x14001bc37  test    byte ptr [rcx+0Ah], 5
0x14001bc3b  jz      short loc_14001BC43
0x14001bc3d  mov     r12, [rcx+18h]
0x14001bc41  jmp     short loc_14001BC67
0x14001bc43  xor     r9d, r9d; RequestedAddress
0x14001bc46  mov     [rsp+500h+Priority], 40000010h; Priority
0x14001bc4e  xor     edx, edx; AccessMode
0x14001bc50  mov     [rsp+500h+BugCheckOnFailure], edi; BugCheckOnFailure
0x14001bc54  lea     r8d, [r9+1]; CacheType
0x14001bc58  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14001bc5f  nop     dword ptr [rax+rax+00h]
0x14001bc64  mov     r12, rax
0x14001bc67  test    r12, r12
0x14001bc6a  jnz     short loc_14001BC87
0x14001bc6c  lea     rax, aOriginMmgetsys; "ORIGIN: MmGetSystemAddressForMdlSafe"
0x14001bc73  mov     r8, 198000405DEh
0x14001bc7d  mov     ebx, 0C0000017h
0x14001bc82  jmp     loc_14001B9FB
0x14001bc87  mov     [rsp+500h+var_4B0], dil
0x14001bc8c  jmp     short loc_14001BCA0
0x14001bc8e  mov     eax, [rsi]
0x14001bc90  mov     r12, [r15+38h]
0x14001bc94  test    r9b, al
0x14001bc97  jnz     short loc_14001BC87
0x14001bc99  mov     al, [rsi+50h]
0x14001bc9c  mov     [rsp+500h+var_4B0], al
0x14001bca0  mov     rbx, [rbx+18h]
0x14001bca4  mov     rcx, r13; this
0x14001bca7  call    ?TryGetScratchInstance@UfsStreamHandleCtx@UnionFs@@QEBAPEBU_FLT_INSTANCE@@XZ; UnionFs::UfsStreamHandleCtx::TryGetScratchInstance(void)
0x14001bcac  cmp     rbx, rax
0x14001bcaf  jz      short loc_14001BCBD
0x14001bcb1  lea     rcx, aMustBeEnumerat; "Must be enumerating on a scratch handle"
0x14001bcb8  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x14001bcbd  mov     eax, [r15+18h]
0x14001bcc1  test    r12, r12
0x14001bcc4  jnz     short loc_14001BCCF
0x14001bcc6  test    rax, rax
0x14001bcc9  jnz     loc_14001BEB3
0x14001bccf  mov     r8d, [rsp+500h+var_4AC]; enum _FILE_INFORMATION_CLASS
0x14001bcd4  lea     r9, ?g_AllFilesFilter@UnionFs@@3U_UNICODE_STRING@@B; _UNICODE_STRING const UnionFs::g_AllFilesFilter
0x14001bcdb  mov     [rbp+400h+var_480], rax
0x14001bcdf  mov     al, [rsp+500h+var_4B0]
0x14001bce3  mov     [rbp+400h+var_468], al
0x14001bce6  mov     rax, [rsi+10h]
0x14001bcea  mov     [rbp+400h+var_478], r12
0x14001bcee  mov     [rbp+400h+var_470], rdi
0x14001bcf2  mov     edx, [r15+30h]
0x14001bcf6  mov     cl, [rax+6]
0x14001bcf9  mov     rax, [r15+20h]
0x14001bcfd  test    rax, rax
0x14001bd00  mov     [rsp+500h+var_4C0], 1; bool
0x14001bd05  cmovnz  r9, rax; struct _UNICODE_STRING *
0x14001bd09  lea     rax, [rbp+400h+var_328]
0x14001bd10  mov     [rsp+500h+var_4C8], rax; struct UnionFs::StackEventTracer *
0x14001bd15  lea     rax, [rbp+400h+var_480]
0x14001bd19  mov     [rsp+500h+var_4D0], rax; struct UnionFs::EnumerateDirResults *
0x14001bd1e  mov     byte ptr [rsp+500h+Priority], cl; char *
0x14001bd22  mov     rcx, r13; this
0x14001bd25  mov     [rsp+500h+BugCheckOnFailure], edx; unsigned int
0x14001bd29  mov     rdx, rsi; struct _FLT_CALLBACK_DATA *
0x14001bd2c  call    ?EnumerateDirectoryWithMerge@UfsStreamHandleCtx@UnionFs@@QEBAJAEBU_FLT_CALLBACK_DATA@@W4_FILE_INFORMATION_CLASS@@AEBU_UNICODE_STRING@@KEAEAUEnumerateDirResults@2@AEAVStackEventTracer@2@_N@Z; UnionFs::UfsStreamHandleCtx::EnumerateDirectoryWithMerge(_FLT_CALLBACK_DATA const &,_FILE_INFORMATION_CLASS,_UNICODE_STRING const &,ulong,uchar,UnionFs::EnumerateDirResults &,UnionFs::StackEventTracer &,bool)
0x14001bd31  mov     r15d, eax
0x14001bd34  test    eax, eax
0x14001bd36  jns     short loc_14001BD55
0x14001bd38  lea     rax, aPushEnumeratin_1; "PUSH: Enumerating union"
0x14001bd3f  mov     r8, 19A00040602h
0x14001bd49  lea     r9, aUnionfsUnionfs_15; "UnionFs::UnionFsFilter::PreDirControl"
0x14001bd50  jmp     loc_14001BB32
0x14001bd55  mov     eax, dword ptr [rbp+400h+var_470+4]
0x14001bd58  mov     [rbp+400h+var_328], edi
0x14001bd5e  mov     [rbp+400h+var_104], di
  ... truncated ...
```
