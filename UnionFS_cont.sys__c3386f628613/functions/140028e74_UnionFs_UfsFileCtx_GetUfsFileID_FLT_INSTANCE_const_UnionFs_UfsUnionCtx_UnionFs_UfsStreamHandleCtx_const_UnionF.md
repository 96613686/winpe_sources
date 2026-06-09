# UnionFs::UfsFileCtx::GetUfsFileID(_FLT_INSTANCE const &,UnionFs::UfsUnionCtx &,UnionFs::UfsStreamHandleCtx const &,UnionFs::UfsFileID &,UnionFs::StackEventTracer &)

- ea: `0x140028e74`
- end: `0x140029510`
- name: `?GetUfsFileID@UfsFileCtx@UnionFs@@QEBAJAEBU_FLT_INSTANCE@@AEAVUfsUnionCtx@2@AEBVUfsStreamHandleCtx@2@AEAVUfsFileID@2@AEAVStackEventTracer@2@@Z`
- size: `1692`
- prototype: `__int64 __usercall@<rax>(UnionFs::UfsFileCtx *__hidden this@<rcx>, const struct _FLT_INSTANCE *@<rdx>, struct UnionFs::UfsUnionCtx *@<r8>, const struct UnionFs::UfsStreamHandleCtx *@<r9>, struct UnionFs::UfsFileID *, struct UnionFs::StackEventTracer *)`
- caller_count: `6`
- callee_count: `20`
- tags: `file_ops, reparse_path, loader_planting, installer_update`

## callers

- `0x14000f680`
- `0x1400352a8`
- `0x140035564`
- `0x140035890`
- `0x1400787d4`
- `0x140078930`

## callees

- `0x14000f7fc`
- `0x140010b88`
- `0x140024034`
- `0x140028e74`
- `0x14002ab84`
- `0x14002ac00`
- `0x140036128`
- `0x140056a50`
- `0x140056ac4`
- `0x140056afc`
- `0x14005ddac`
- `0x140061024`
- `0x14006e1a4`
- `0x1400799a4`
- `0x140079a24`
- `0x140079c48`
- `0x140079d0c`
- `0x140079da0`
- `0x14007b7d0`
- `0x14007bc00`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400291c1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002927e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400291c1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002927e`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14002944a`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14002944a`
- `ntoskrnl!ExReleaseFastMutex` at `0x140028f04`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400294e1`
- `ntoskrnl!ExReleaseFastMutex` at `0x140028f04`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400294e1`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140028f7b`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140029050`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400291ed`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14002930b`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400294cd`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140028f7b`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140029050`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400291ed`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14002930b`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400294cd`
- `FLTMGR!FltQueryInformationFile` at `0x140029096`
- `FLTMGR!FltQueryInformationFile` at `0x140029383`
- `FLTMGR!FltQueryInformationFile` at `0x140029096`
- `FLTMGR!FltQueryInformationFile` at `0x140029383`

## pseudocode

```c
__int64 __fastcall UnionFs::UfsFileCtx::GetUfsFileID(
        UnionFs::UfsFileCtx *this,
        const struct _FLT_INSTANCE *a2,
        union _LARGE_INTEGER **a3,
        const struct UnionFs::UfsStreamHandleCtx *a4,
        struct UnionFs::UfsFileID *a5,
        struct UnionFs::StackEventTracer *a6)
{
  struct _FAST_MUTEX *v6; // r12
  unsigned int v11; // eax
  NTSTATUS FileNameInformation; // ebx
  struct _FLT_FILE_NAME_INFORMATION *v13; // rcx
  unsigned __int64 *v15; // rdx
  union _LARGE_INTEGER *v16; // rax
  volatile signed __int32 *QuadPart; // rbx
  UnionFs::UfsLayerCtx *v18; // r12
  unsigned int InformationFile; // edi
  struct _FLT_FILE_NAME_INFORMATION *v20; // rcx
  PFLT_INSTANCE v21; // rdi
  int v22; // r12d
  utl::_RefCountBase *v23; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v24; // rcx
  union _LARGE_INTEGER v25; // rdx
  const struct UnionFs::UfsLayerCtx *v26; // r8
  _OWORD *v27; // rax
  __int128 v28; // xmm1
  utl::_RefCountBase *v29; // rcx
  USHORT v30; // bx
  struct _UNICODE_STRING *v31; // rdx
  struct _FLT_FILE_NAME_INFORMATION *v32; // rcx
  __int64 v33; // rbx
  unsigned __int64 *v34; // rdx
  struct _FILE_OBJECT *v35; // rbx
  const struct UnionFs::UfsLayerCtx *v36; // rdi
  utl::_RefCountBase *v37; // rcx
  struct _UNICODE_STRING *v38; // rdx
  struct _UNICODE_STRING *v39; // rdx
  struct _FLT_FILE_NAME_INFORMATION *v40; // rcx
  const char *LengthReturned; // [rsp+28h] [rbp-D8h]
  const char *LengthReturneda; // [rsp+28h] [rbp-D8h]
  const char *LengthReturnedb; // [rsp+28h] [rbp-D8h]
  PFAST_MUTEX FastMutex; // [rsp+30h] [rbp-D0h] BYREF
  union _LARGE_INTEGER v45; // [rsp+38h] [rbp-C8h] BYREF
  PFLT_INSTANCE Instance[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v47; // [rsp+50h] [rbp-B0h]
  struct _UNICODE_STRING v48; // [rsp+60h] [rbp-A0h] BYREF
  const struct _FLT_INSTANCE *v49; // [rsp+70h] [rbp-90h]
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-80h] BYREF
  struct _FAST_MUTEX *v51; // [rsp+90h] [rbp-70h]
  UNICODE_STRING SourceString; // [rsp+98h] [rbp-68h] BYREF
  _QWORD FileInformation[14]; // [rsp+B0h] [rbp-50h] BYREF

  v6 = 0;
  Instance[0] = a2;
  *(_QWORD *)a5 = 0;
  *((_QWORD *)a5 + 1) = 0;
  *((_QWORD *)a5 + 2) = 0;
  *((_QWORD *)a5 + 3) = 0;
  FsFltWil::AcquireFastMutex(&FastMutex, this);
  if ( !*((_QWORD *)this + 10) )
  {
    v11 = *((_DWORD *)this + 17);
    if ( v11 >= 0x10000000 || (v11 & 0x3F) == 0 )
      goto LABEL_4;
LABEL_13:
    v6 = FastMutex;
    *(_OWORD *)a5 = *((_OWORD *)this + 4);
    *((_OWORD *)a5 + 1) = *((_OWORD *)this + 5);
    goto LABEL_69;
  }
  if ( *((_QWORD *)this + 9) >= 0x400000000000000uLL )
    goto LABEL_13;
LABEL_4:
  v51 = 0;
  if ( FastMutex )
    ExReleaseFastMutex(FastMutex);
  v48.Buffer = (PWSTR)*((_QWORD *)a4 + 9);
  FastMutex = 0;
  *(_QWORD *)&v48.Length = 0;
  v49 = a2;
  FileNameInformation = UnionFs::Utils::GetFileNameInformation(&v48, 16777473, &FastMutex, a6);
  if ( FileNameInformation < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)FileNameInformation,
      (int)a6,
      (struct UnionFs::StackEventTracer *)0x5DF000A02E6LL,
      (unsigned __int64)"UnionFs::UfsFileCtx::GetUfsFileID",
      "PUSH: Get file name info",
      LengthReturned);
LABEL_8:
    v13 = (struct _FLT_FILE_NAME_INFORMATION *)FastMutex;
    FastMutex = 0;
LABEL_9:
    if ( v13 )
      FltReleaseFileNameInformation(v13);
    return (unsigned int)FileNameInformation;
  }
  if ( (*(_DWORD *)a4 & 1) != 0 )
  {
    v33 = *(_QWORD *)(*((_QWORD *)a4 + 9) + 32LL);
    FsFltWil::AcquirePushLockShared(Instance, v33 + 32);
    v35 = *(struct _FILE_OBJECT **)(v33 + 24);
    if ( Instance[0] )
      FsFltWil::Details::ReleasePushLockShared(Instance[0], v34);
    UnionFs::UfsStreamHandleCtx::TryGetBackingLayer(a4, Instance);
    v36 = Instance[0];
    v45.QuadPart = 0;
    FileNameInformation = FltQueryInformationFile(
                            **((PFLT_INSTANCE **)Instance[0] + 1),
                            v35,
                            &v45,
                            8u,
                            FileInternalInformation,
                            0);
    if ( FileNameInformation < 0 )
    {
      UnionFs::ProcessTraceStatusFromApi(
        (UnionFs *)(unsigned int)FileNameInformation,
        (int)a6,
        (struct UnionFs::StackEventTracer *)0x44A000A02FBLL,
        (unsigned __int64)"UnionFs::UfsFileCtx::GetUfsFileID",
        "API: Querying internal info",
        LengthReturnedb);
      if ( Instance[1] )
        utl::_RefCountBase::_DecStrong(Instance[1]);
      goto LABEL_8;
    }
    UnionFs::UfsFileID::UfsFileID((UnionFs::UfsFileID *)&v48, v45, v36, (const struct UnionFs::UfsUnionCtx *)a3);
    UnionFs::UfsFileCtx::SetFileID(this, (const struct UnionFs::UfsFileID *)&v48);
    v37 = Instance[1];
    *(_OWORD *)a5 = *((_OWORD *)this + 4);
    *((_OWORD *)a5 + 1) = *((_OWORD *)this + 5);
    if ( v37 )
      utl::_RefCountBase::_DecStrong(v37);
  }
  else
  {
    FsFltWil::AcquirePushLockShared(&v48, a3 + 9);
    v16 = a3[6];
    QuadPart = (volatile signed __int32 *)v16[1].QuadPart;
    v18 = (UnionFs::UfsLayerCtx *)v16->QuadPart;
    v45 = *v16;
    if ( QuadPart )
      _InterlockedIncrement(QuadPart + 2);
    if ( *(_QWORD *)&v48.Length )
      FsFltWil::Details::ReleasePushLockShared(*(FsFltWil::Details **)&v48.Length, v15);
    if ( !v18 )
    {
      InformationFile = -1058209784;
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC0ED0008LL,
        (int)a6,
        (struct UnionFs::StackEventTracer *)0x3F1000A030CLL,
        (unsigned __int64)"UnionFs::UfsFileCtx::GetUfsFileID",
        "ORIGIN: No scratchLayer",
        LengthReturned);
LABEL_21:
      if ( QuadPart )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)QuadPart);
      v20 = (struct _FLT_FILE_NAME_INFORMATION *)FastMutex;
      FastMutex = 0;
      if ( v20 )
        FltReleaseFileNameInformation(v20);
      return InformationFile;
    }
    memset(FileInformation, 0, 0x68u);
    InformationFile = FltQueryInformationFile(
                        Instance[0],
                        *((PFILE_OBJECT *)a4 + 9),
                        FileInformation,
                        0x68u,
                        FileAllInformation,
                        0);
    if ( (int)(InformationFile + 0x80000000) >= 0 && InformationFile != -2147483643 )
    {
      UnionFs::ProcessTraceStatusFromApi(
        (UnionFs *)InformationFile,
        (int)a6,
        (struct UnionFs::StackEventTracer *)0x44C000A031ALL,
        (unsigned __int64)"UnionFs::UfsFileCtx::GetUfsFileID",
        "API: Querying all info",
        LengthReturneda);
      goto LABEL_21;
    }
    v48 = 0;
    UnionFs::UfsLayerCtx::GetNormalizedLayerRootPath(v18, &v48, 1);
    utl::make_unique<UnionFs::FindAndStatResults,,0>(Instance);
    v21 = Instance[0];
    if ( !Instance[0] )
    {
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC000009ALL,
        (int)a6,
        (struct UnionFs::StackEventTracer *)0x3F7000A032ALL,
        (unsigned __int64)"UnionFs::UfsFileCtx::GetUfsFileID",
        "ORIGIN: Allocating findAndStatResults",
        LengthReturneda);
      if ( QuadPart )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)QuadPart);
      goto LABEL_55;
    }
    LengthReturnedb = (const char *)a6;
    v22 = UnionFs::UfsUnionCtx::FindAndStatItemInLayers(a3, &FastMutex->Owner, &v48, 1, Instance[0]);
    if ( v22 < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v22,
        (int)a6,
        (struct UnionFs::StackEventTracer *)0x428000A0333LL,
        (unsigned __int64)"UnionFs::UfsFileCtx::GetUfsFileID",
        "PUSH: Probing for item in layers",
        (const char *)a6);
      if ( v21 )
      {
        v23 = (utl::_RefCountBase *)*((_QWORD *)v21 + 11);
        if ( v23 )
          utl::_RefCountBase::_DecStrong(v23);
        ExFreePoolWithTag(v21, 0);
      }
      if ( QuadPart )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)QuadPart);
      v24 = (struct _FLT_FILE_NAME_INFORMATION *)FastMutex;
      FastMutex = 0;
      if ( v24 )
        FltReleaseFileNameInformation(v24);
      return (unsigned int)v22;
    }
    if ( *(_WORD *)v21 == 1 && FileInformation[0] == *((_QWORD *)v21 + 2) )
    {
      v25 = *(union _LARGE_INTEGER *)((char *)v21 + 8);
      v26 = (const struct UnionFs::UfsLayerCtx *)*((_QWORD *)v21 + 10);
    }
    else
    {
      v26 = (const struct UnionFs::UfsLayerCtx *)v45.QuadPart;
      v25 = (union _LARGE_INTEGER)FileInformation[8];
    }
    v27 = (_OWORD *)UnionFs::UfsFileID::UfsFileID(
                      (UnionFs::UfsFileID *)&v48,
                      v25,
                      v26,
                      (const struct UnionFs::UfsUnionCtx *)a3);
    v28 = v27[1];
    *(_OWORD *)Instance = *v27;
    v47 = v28;
    UnionFs::UfsFileCtx::SetFileID(this, (const struct UnionFs::UfsFileID *)Instance);
    *(_OWORD *)a5 = *((_OWORD *)this + 4);
    *((_OWORD *)a5 + 1) = *((_OWORD *)this + 5);
    if ( v21 )
    {
      v29 = (utl::_RefCountBase *)*((_QWORD *)v21 + 11);
      if ( v29 )
        utl::_RefCountBase::_DecStrong(v29);
      ExFreePoolWithTag(v21, 0);
    }
    if ( QuadPart )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)QuadPart);
    v6 = v51;
  }
  v30 = LOWORD(FastMutex->Owner) - LOWORD(FastMutex->Event.Header.Lock);
  FsFltWil::MakeUniqueUnicodeString(&DestinationString, v30, 1279685446);
  if ( !DestinationString.Buffer )
  {
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC000009ALL,
      (int)a6,
      (struct UnionFs::StackEventTracer *)0x46C000A0360LL,
      (unsigned __int64)"UnionFs::UfsFileCtx::GetUfsFileID",
      "ORIGIN: Allocating normalized name for map",
      LengthReturnedb);
    FsFltWil::Details::FreeUnicodeString(&DestinationString, v31);
LABEL_55:
    v32 = (struct _FLT_FILE_NAME_INFORMATION *)FastMutex;
    FastMutex = 0;
    if ( v32 )
      FltReleaseFileNameInformation(v32);
    return 3221225626LL;
  }
  SourceString = 0;
  SourceString.Length = v30;
  SourceString.MaximumLength = v30;
  SourceString.Buffer = (PWSTR)(*(_QWORD *)&FastMutex->Contention + LOWORD(FastMutex->Event.Header.Lock));
  RtlCopyUnicodeString(&DestinationString, &SourceString);
  FileNameInformation = UnionFs::UfsUnionCtx::AddFileIDMapping(a3, a5, &DestinationString, a6);
  if ( FileNameInformation < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)FileNameInformation,
      (int)a6,
      (struct UnionFs::StackEventTracer *)0x5E0000A036DLL,
      (unsigned __int64)"UnionFs::UfsFileCtx::GetUfsFileID",
      "PUSH: Adding file ID mapping",
      LengthReturnedb);
    FsFltWil::Details::FreeUnicodeString(&DestinationString, v39);
    v13 = (struct _FLT_FILE_NAME_INFORMATION *)FastMutex;
    FastMutex = 0;
    goto LABEL_9;
  }
  FsFltWil::Details::FreeUnicodeString(&DestinationString, v38);
  v40 = (struct _FLT_FILE_NAME_INFORMATION *)FastMutex;
  FastMutex = 0;
  if ( v40 )
    FltReleaseFileNameInformation(v40);
LABEL_69:
  if ( v6 )
    ExReleaseFastMutex(v6);
  return 0;
}

```

## disassembly

```asm
0x140028e74  push    rbp
0x140028e76  push    rbx
0x140028e77  push    rsi
0x140028e78  push    rdi
0x140028e79  push    r12
0x140028e7b  push    r13
0x140028e7d  push    r14
0x140028e7f  push    r15
0x140028e81  lea     rbp, [rsp-38h]
0x140028e86  sub     rsp, 138h
0x140028e8d  mov     rax, cs:__security_cookie
0x140028e94  xor     rax, rsp
0x140028e97  mov     [rbp+70h+var_50], rax
0x140028e9b  mov     r15, [rbp+70h+arg_20]
0x140028ea2  xor     r12d, r12d
0x140028ea5  mov     rsi, [rbp+70h+arg_28]
0x140028eac  mov     rbx, rdx
0x140028eaf  mov     [rsp+170h+Instance], rdx
0x140028eb4  mov     r14, rcx
0x140028eb7  mov     rdx, rcx
0x140028eba  mov     rdi, r9
0x140028ebd  mov     [r15], r12
0x140028ec0  lea     rcx, [rsp+170h+FastMutex]
0x140028ec5  mov     [r15+8], r12
0x140028ec9  mov     r13, r8
0x140028ecc  mov     [r15+10h], r12
0x140028ed0  mov     [r15+18h], r12
0x140028ed4  call    ?AcquireFastMutex@FsFltWil@@YA?AV?$unique_ptr@U_FAST_MUTEX@@U?$function_deleter@P6AXPEAU_FAST_MUTEX@@@Z$1?ExReleaseFastMutex@@YAX0@Z@wil@@@wistd@@AEAU_FAST_MUTEX@@@Z; FsFltWil::AcquireFastMutex(_FAST_MUTEX &)
0x140028ed9  cmp     [r14+50h], r12
0x140028edd  jnz     loc_140028F8E
0x140028ee3  mov     eax, [r14+44h]
0x140028ee7  cmp     eax, 10000000h
0x140028eec  jnb     short loc_140028EF6
0x140028eee  test    al, 3Fh
0x140028ef0  jnz     loc_140028FA2
0x140028ef6  mov     rcx, [rsp+170h+FastMutex]; FastMutex
0x140028efb  mov     [rbp+70h+var_E0], r12
0x140028eff  test    rcx, rcx
0x140028f02  jz      short loc_140028F10
0x140028f04  call    cs:__imp_ExReleaseFastMutex
0x140028f0b  nop     dword ptr [rax+rax+00h]
0x140028f10  mov     rax, [rdi+48h]
0x140028f14  lea     r8, [rsp+170h+FastMutex]
0x140028f19  mov     r9, rsi
0x140028f1c  mov     [rsp+170h+var_110.Buffer], rax
0x140028f21  mov     edx, 1000101h
0x140028f26  mov     [rsp+170h+FastMutex], r12
0x140028f2b  lea     rcx, [rsp+170h+var_110]
0x140028f30  mov     qword ptr [rsp+170h+var_110.Length], r12
0x140028f35  mov     [rsp+170h+var_100], rbx
0x140028f3a  call    ?GetFileNameInformation@Utils@UnionFs@@YAJUNameInfoParams@12@KAEAV?$unique_ptr@U_FLT_FILE_NAME_INFORMATION@@U?$function_deleter@P6AXPEAU_FLT_FILE_NAME_INFORMATION@@@Z$1?FltReleaseFileNameInformation@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@@Z; UnionFs::Utils::GetFileNameInformation(UnionFs::Utils::NameInfoParams,ulong,wistd::unique_ptr<_FLT_FILE_NAME_INFORMATION,wil::function_deleter<void (*)(_FLT_FILE_NAME_INFORMATION *),&FltReleaseFileNameInformation(_FLT_FILE_NAME_INFORMATION *)>> &,UnionFs::StackEventTracer &)
0x140028f3f  mov     ebx, eax
0x140028f41  test    eax, eax
0x140028f43  jns     short loc_140028FBF
0x140028f45  lea     rax, aPushGetFileNam; "PUSH: Get file name info"
0x140028f4c  mov     r8, 5DF000A02E6h; struct UnionFs::StackEventTracer *
0x140028f56  lea     r9, aUnionfsUfsfile_7; "UnionFs::UfsFileCtx::GetUfsFileID"
0x140028f5d  mov     qword ptr [rsp+170h+FileInformationClass], rax; char *
0x140028f62  mov     rdx, rsi; int
0x140028f65  mov     ecx, ebx; this
0x140028f67  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140028f6c  mov     rcx, [rsp+170h+FastMutex]; FileNameInformation
0x140028f71  mov     [rsp+170h+FastMutex], r12
0x140028f76  test    rcx, rcx
0x140028f79  jz      short loc_140028F87
0x140028f7b  call    cs:__imp_FltReleaseFileNameInformation
0x140028f82  nop     dword ptr [rax+rax+00h]
0x140028f87  mov     eax, ebx
0x140028f89  jmp     loc_1400294EF
0x140028f8e  mov     rax, 400000000000000h
0x140028f98  cmp     [r14+48h], rax
0x140028f9c  jb      loc_140028EF6
0x140028fa2  movups  xmm0, xmmword ptr [r14+40h]
0x140028fa7  mov     r12, [rsp+170h+FastMutex]
0x140028fac  movups  xmmword ptr [r15], xmm0
0x140028fb0  movups  xmm1, xmmword ptr [r14+50h]
0x140028fb5  movups  xmmword ptr [r15+10h], xmm1
0x140028fba  jmp     loc_1400294D9
0x140028fbf  mov     eax, [rdi]
0x140028fc1  test    al, 1
0x140028fc3  jnz     loc_140029321
0x140028fc9  lea     rdx, [r13+48h]
0x140028fcd  lea     rcx, [rsp+170h+var_110]
0x140028fd2  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x140028fd7  mov     rax, [r13+30h]
0x140028fdb  mov     rbx, [rax+8]
0x140028fdf  mov     r12, [rax]
0x140028fe2  mov     qword ptr [rsp+170h+var_138], r12
0x140028fe7  test    rbx, rbx
0x140028fea  jz      short loc_140028FF0
0x140028fec  lock inc dword ptr [rbx+8]
0x140028ff0  mov     rcx, qword ptr [rsp+170h+var_110.Length]; this
0x140028ff5  test    rcx, rcx
0x140028ff8  jz      short loc_140028FFF
0x140028ffa  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x140028fff  test    r12, r12
0x140029002  jnz     short loc_140029063
0x140029004  lea     rax, aOriginNoScratc_0; "ORIGIN: No scratchLayer"
0x14002900b  mov     edi, 0C0ED0008h
0x140029010  mov     ecx, edi; this
0x140029012  mov     qword ptr [rsp+170h+FileInformationClass], rax; char *
0x140029017  lea     r9, aUnionfsUfsfile_7; "UnionFs::UfsFileCtx::GetUfsFileID"
0x14002901e  mov     r8, 3F1000A030Ch; struct UnionFs::StackEventTracer *
0x140029028  mov     rdx, rsi; int
0x14002902b  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140029030  test    rbx, rbx
0x140029033  jz      short loc_14002903D
0x140029035  mov     rcx, rbx; this
0x140029038  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14002903d  mov     rcx, [rsp+170h+FastMutex]; FileNameInformation
0x140029042  mov     [rsp+170h+FastMutex], 0
0x14002904b  test    rcx, rcx
0x14002904e  jz      short loc_14002905C
0x140029050  call    cs:__imp_FltReleaseFileNameInformation
0x140029057  nop     dword ptr [rax+rax+00h]
0x14002905c  mov     eax, edi
0x14002905e  jmp     loc_1400294EF
0x140029063  xor     edx, edx; Val
0x140029065  lea     rcx, [rbp+70h+FileInformation]; void *
0x140029069  lea     r8d, [rdx+68h]; Size
0x14002906d  call    memset
0x140029072  mov     rdx, [rdi+48h]; FileObject
0x140029076  lea     r8, [rbp+70h+FileInformation]; FileInformation
0x14002907a  mov     rcx, [rsp+170h+Instance]; Instance
0x14002907f  mov     r9d, 68h ; 'h'; Length
0x140029085  mov     [rsp+170h+LengthReturned], 0; char *
0x14002908e  mov     [rsp+170h+FileInformationClass], 12h; FileInformationClass
0x140029096  call    cs:__imp_FltQueryInformationFile
0x14002909d  nop     dword ptr [rax+rax+00h]
0x1400290a2  mov     edi, eax
0x1400290a4  mov     eax, 80000000h
0x1400290a9  lea     ecx, [rdi+rax]
0x1400290ac  test    eax, ecx
0x1400290ae  jnz     short loc_1400290E4
0x1400290b0  cmp     edi, 80000005h
0x1400290b6  jz      short loc_1400290E4
0x1400290b8  lea     rax, aApiQueryingAll; "API: Querying all info"
0x1400290bf  mov     r8, 44C000A031Ah; struct UnionFs::StackEventTracer *
0x1400290c9  lea     r9, aUnionfsUfsfile_7; "UnionFs::UfsFileCtx::GetUfsFileID"
0x1400290d0  mov     qword ptr [rsp+170h+FileInformationClass], rax; char *
0x1400290d5  mov     rdx, rsi; int
0x1400290d8  mov     ecx, edi; this
0x1400290da  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400290df  jmp     loc_140029030
0x1400290e4  xorps   xmm0, xmm0
0x1400290e7  lea     rdx, [rsp+170h+var_110]; struct _UNICODE_STRING *
0x1400290ec  mov     r8b, 1; bool
0x1400290ef  mov     rcx, r12; this
0x1400290f2  movups  xmmword ptr [rsp+170h+var_110.Length], xmm0
0x1400290f7  call    ?GetNormalizedLayerRootPath@UfsLayerCtx@UnionFs@@QEBAGAEAU_UNICODE_STRING@@_N@Z; UnionFs::UfsLayerCtx::GetNormalizedLayerRootPath(_UNICODE_STRING &,bool)
0x1400290fc  lea     rcx, [rsp+170h+Instance]
0x140029101  call    ??$make_unique@UFindAndStatResults@UnionFs@@$$V$0A@@utl@@YA?AV?$unique_ptr@UFindAndStatResults@UnionFs@@U?$default_delete@UFindAndStatResults@UnionFs@@@utl@@@0@XZ; utl::make_unique<UnionFs::FindAndStatResults,,0>(void)
0x140029106  mov     rdi, [rsp+170h+Instance]
0x14002910b  test    rdi, rdi
0x14002910e  jnz     short loc_140029150
0x140029110  lea     rax, aOriginAllocati_60; "ORIGIN: Allocating findAndStatResults"
0x140029117  mov     r8, 3F7000A032Ah; struct UnionFs::StackEventTracer *
0x140029121  lea     r9, aUnionfsUfsfile_7; "UnionFs::UfsFileCtx::GetUfsFileID"
0x140029128  mov     qword ptr [rsp+170h+FileInformationClass], rax; char *
0x14002912d  mov     rdx, rsi; int
0x140029130  mov     ecx, 0C000009Ah; this
0x140029135  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14002913a  test    rbx, rbx
0x14002913d  jz      loc_1400292F8
0x140029143  mov     rcx, rbx; this
0x140029146  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14002914b  jmp     loc_1400292F8
0x140029150  mov     rdx, [rsp+170h+FastMutex]
0x140029155  lea     r8, [rsp+170h+var_110]
0x14002915a  add     rdx, 8
0x14002915e  mov     [rsp+170h+LengthReturned], rsi; char *
0x140029163  mov     r9d, 1
0x140029169  mov     qword ptr [rsp+170h+FileInformationClass], rdi
0x14002916e  mov     rcx, r13
0x140029171  call    ?FindAndStatItemInLayers@UfsUnionCtx@UnionFs@@QEBAJAEBU_UNICODE_STRING@@0W4StatItemFlags@Utils@2@AEAUFindAndStatResults@2@AEAVStackEventTracer@2@@Z; UnionFs::UfsUnionCtx::FindAndStatItemInLayers(_UNICODE_STRING const &,_UNICODE_STRING const &,UnionFs::Utils::StatItemFlags,UnionFs::FindAndStatResults &,UnionFs::StackEventTracer &)
0x140029176  mov     r12d, eax
0x140029179  test    eax, eax
0x14002917b  jns     loc_140029201
0x140029181  lea     rax, aPushProbingFor; "PUSH: Probing for item in layers"
0x140029188  mov     r8, 428000A0333h; struct UnionFs::StackEventTracer *
0x140029192  lea     r9, aUnionfsUfsfile_7; "UnionFs::UfsFileCtx::GetUfsFileID"
0x140029199  mov     qword ptr [rsp+170h+FileInformationClass], rax; char *
0x14002919e  mov     rdx, rsi; int
0x1400291a1  mov     ecx, r12d; this
0x1400291a4  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400291a9  test    rdi, rdi
0x1400291ac  jz      short loc_1400291CD
0x1400291ae  mov     rcx, [rdi+58h]; this
0x1400291b2  test    rcx, rcx
0x1400291b5  jz      short loc_1400291BC
0x1400291b7  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1400291bc  xor     edx, edx; Tag
0x1400291be  mov     rcx, rdi; P
0x1400291c1  call    cs:__imp_ExFreePoolWithTag
0x1400291c8  nop     dword ptr [rax+rax+00h]
0x1400291cd  test    rbx, rbx
0x1400291d0  jz      short loc_1400291DA
0x1400291d2  mov     rcx, rbx; this
0x1400291d5  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1400291da  mov     rcx, [rsp+170h+FastMutex]; FileNameInformation
0x1400291df  mov     [rsp+170h+FastMutex], 0
0x1400291e8  test    rcx, rcx
0x1400291eb  jz      short loc_1400291F9
0x1400291ed  call    cs:__imp_FltReleaseFileNameInformation
0x1400291f4  nop     dword ptr [rax+rax+00h]
0x1400291f9  mov     eax, r12d
0x1400291fc  jmp     loc_1400294EF
0x140029201  mov     eax, 1
0x140029206  cmp     [rdi], ax
0x140029209  jnz     short loc_14002921F
0x14002920b  mov     rax, [rdi+10h]
0x14002920f  cmp     [rbp+70h+FileInformation], rax
0x140029213  jnz     short loc_14002921F
0x140029215  mov     rdx, [rdi+8]
0x140029219  mov     r8, [rdi+50h]
0x14002921d  jmp     short loc_140029228
0x14002921f  mov     r8, qword ptr [rsp+170h+var_138]; struct UnionFs::UfsLayerCtx *
0x140029224  mov     rdx, qword ptr [rbp+70h+var_80]; union _LARGE_INTEGER
0x140029228  mov     r9, r13; struct UnionFs::UfsUnionCtx *
0x14002922b  lea     rcx, [rsp+170h+var_110]; this
0x140029230  call    ??0UfsFileID@UnionFs@@QEAA@T_LARGE_INTEGER@@AEBVUfsLayerCtx@1@AEBVUfsUnionCtx@1@@Z; UnionFs::UfsFileID::UfsFileID(_LARGE_INTEGER,UnionFs::UfsLayerCtx const &,UnionFs::UfsUnionCtx const &)
0x140029235  lea     rdx, [rsp+170h+Instance]; struct UnionFs::UfsFileID *
0x14002923a  mov     rcx, r14; this
0x14002923d  movups  xmm0, xmmword ptr [rax]
0x140029240  movups  xmm1, xmmword ptr [rax+10h]
0x140029244  movups  xmmword ptr [rsp+170h+Instance], xmm0
0x140029249  movups  [rsp+170h+var_120], xmm1
0x14002924e  call    ?SetFileID@UfsFileCtx@UnionFs@@AEBAXAEBVUfsFileID@2@@Z; UnionFs::UfsFileCtx::SetFileID(UnionFs::UfsFileID const &)
0x140029253  movups  xmm0, xmmword ptr [r14+40h]
0x140029258  movups  xmmword ptr [r15], xmm0
0x14002925c  movups  xmm1, xmmword ptr [r14+50h]
0x140029261  movups  xmmword ptr [r15+10h], xmm1
0x140029266  test    rdi, rdi
0x140029269  jz      short loc_14002928A
0x14002926b  mov     rcx, [rdi+58h]; this
0x14002926f  test    rcx, rcx
0x140029272  jz      short loc_140029279
0x140029274  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140029279  xor     edx, edx; Tag
0x14002927b  mov     rcx, rdi; P
0x14002927e  call    cs:__imp_ExFreePoolWithTag
0x140029285  nop     dword ptr [rax+rax+00h]
0x14002928a  test    rbx, rbx
0x14002928d  jz      short loc_140029297
0x14002928f  mov     rcx, rbx; this
0x140029292  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140029297  mov     r12, [rbp+70h+var_E0]
0x14002929b  mov     rax, [rsp+170h+FastMutex]
0x1400292a0  lea     rcx, [rbp+70h+DestinationString]
0x1400292a4  mov     r8d, 4C467346h
0x1400292aa  movzx   ebx, word ptr [rax+8]
0x1400292ae  sub     bx, [rax+18h]
0x1400292b2  movzx   edx, bx
0x1400292b5  call    ?MakeUniqueUnicodeString@FsFltWil@@YA?AV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@GKW4FSFLT_ALLOC_TYPE@@@Z; FsFltWil::MakeUniqueUnicodeString(ushort,ulong,FSFLT_ALLOC_TYPE)
0x1400292ba  cmp     [rbp+70h+DestinationString.Buffer], 0
0x1400292bf  jnz     loc_140029421
0x1400292c5  lea     rax, aOriginAllocati_37; "ORIGIN: Allocating normalized name for "...
0x1400292cc  mov     r8, 46C000A0360h; struct UnionFs::StackEventTracer *
0x1400292d6  lea     r9, aUnionfsUfsfile_7; "UnionFs::UfsFileCtx::GetUfsFileID"
0x1400292dd  mov     qword ptr [rsp+170h+FileInformationClass], rax; char *
0x1400292e2  mov     rdx, rsi; int
0x1400292e5  mov     ecx, 0C000009Ah; this
0x1400292ea  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400292ef  lea     rcx, [rbp+70h+DestinationString]; UnicodeString
0x1400292f3  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x1400292f8  mov     rcx, [rsp+170h+FastMutex]; FileNameInformation
0x1400292fd  mov     [rsp+170h+FastMutex], 0
0x140029306  test    rcx, rcx
0x140029309  jz      short loc_140029317
0x14002930b  call    cs:__imp_FltReleaseFileNameInformation
0x140029312  nop     dword ptr [rax+rax+00h]
0x140029317  mov     eax, 0C000009Ah
0x14002931c  jmp     loc_1400294EF
0x140029321  mov     rax, [rdi+48h]
0x140029325  lea     rcx, [rsp+170h+Instance]
0x14002932a  mov     rbx, [rax+20h]
0x14002932e  lea     rdx, [rbx+20h]
0x140029332  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x140029337  mov     rcx, [rsp+170h+Instance]; this
0x14002933c  mov     rbx, [rbx+18h]
0x140029340  test    rcx, rcx
0x140029343  jz      short loc_14002934A
0x140029345  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x14002934a  lea     rdx, [rsp+170h+Instance]
0x14002934f  mov     rcx, rdi
0x140029352  call    ?TryGetBackingLayer@UfsStreamHandleCtx@UnionFs@@QEBA?AV?$shared_ptr@VUfsLayerCtx@UnionFs@@@utl@@XZ; UnionFs::UfsStreamHandleCtx::TryGetBackingLayer(void)
0x140029357  mov     rdi, [rsp+170h+Instance]
0x14002935c  lea     r8, [rsp+170h+var_138]; FileInformation
0x140029361  mov     qword ptr [rsp+170h+var_138], r12
0x140029366  mov     r9d, 8; Length
0x14002936c  mov     [rsp+170h+LengthReturned], r12; char *
0x140029371  mov     rdx, rbx; FileObject
0x140029374  mov     [rsp+170h+FileInformationClass], 6; FileInformationClass
0x14002937c  mov     rcx, [rdi+8]
0x140029380  mov     rcx, [rcx]; Instance
0x140029383  call    cs:__imp_FltQueryInformationFile
0x14002938a  nop     dword ptr [rax+rax+00h]
0x14002938f  mov     ebx, eax
0x140029391  test    eax, eax
0x140029393  jns     short loc_1400293D4
  ... truncated ...
```
