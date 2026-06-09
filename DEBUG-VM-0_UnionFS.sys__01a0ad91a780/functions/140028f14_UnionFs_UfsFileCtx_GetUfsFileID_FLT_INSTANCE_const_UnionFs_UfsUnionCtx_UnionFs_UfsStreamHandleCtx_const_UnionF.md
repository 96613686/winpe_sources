# UnionFs::UfsFileCtx::GetUfsFileID(_FLT_INSTANCE const &,UnionFs::UfsUnionCtx &,UnionFs::UfsStreamHandleCtx const &,UnionFs::UfsFileID &,UnionFs::StackEventTracer &)

- ea: `0x140028f14`
- end: `0x1400295b0`
- name: `?GetUfsFileID@UfsFileCtx@UnionFs@@QEBAJAEBU_FLT_INSTANCE@@AEAVUfsUnionCtx@2@AEBVUfsStreamHandleCtx@2@AEAVUfsFileID@2@AEAVStackEventTracer@2@@Z`
- size: `1692`
- prototype: `__int64 __usercall@<rax>(UnionFs::UfsFileCtx *__hidden this@<rcx>, const struct _FLT_INSTANCE *@<rdx>, struct UnionFs::UfsUnionCtx *@<r8>, const struct UnionFs::UfsStreamHandleCtx *@<r9>, struct UnionFs::UfsFileID *, struct UnionFs::StackEventTracer *)`
- caller_count: `6`
- callee_count: `20`
- tags: `file_ops, reparse_path, loader_planting, installer_update`

## callers

- `0x14000f6a0`
- `0x1400353e0`
- `0x14003569c`
- `0x1400359c8`
- `0x140078afc`
- `0x140078c58`

## callees

- `0x14000f81c`
- `0x140010ba8`
- `0x1400240d4`
- `0x140028f14`
- `0x14002ac24`
- `0x14002aca0`
- `0x140036268`
- `0x140056bd0`
- `0x140056c44`
- `0x140056c7c`
- `0x14005df2c`
- `0x1400611a4`
- `0x14006e394`
- `0x140079cc4`
- `0x140079d44`
- `0x140079f68`
- `0x14007a02c`
- `0x14007a0c0`
- `0x14007baf0`
- `0x14007bf40`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140029261`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002931e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029261`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002931e`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400294ea`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400294ea`
- `ntoskrnl!ExReleaseFastMutex` at `0x140028fa4`
- `ntoskrnl!ExReleaseFastMutex` at `0x140029581`
- `ntoskrnl!ExReleaseFastMutex` at `0x140028fa4`
- `ntoskrnl!ExReleaseFastMutex` at `0x140029581`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14002901b`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400290f0`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14002928d`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400293ab`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14002956d`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14002901b`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400290f0`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14002928d`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400293ab`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14002956d`
- `FLTMGR!FltQueryInformationFile` at `0x140029136`
- `FLTMGR!FltQueryInformationFile` at `0x140029423`
- `FLTMGR!FltQueryInformationFile` at `0x140029136`
- `FLTMGR!FltQueryInformationFile` at `0x140029423`

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
0x140028f14  push    rbp
0x140028f16  push    rbx
0x140028f17  push    rsi
0x140028f18  push    rdi
0x140028f19  push    r12
0x140028f1b  push    r13
0x140028f1d  push    r14
0x140028f1f  push    r15
0x140028f21  lea     rbp, [rsp-38h]
0x140028f26  sub     rsp, 138h
0x140028f2d  mov     rax, cs:__security_cookie
0x140028f34  xor     rax, rsp
0x140028f37  mov     [rbp+70h+var_50], rax
0x140028f3b  mov     r15, [rbp+70h+arg_20]
0x140028f42  xor     r12d, r12d
0x140028f45  mov     rsi, [rbp+70h+arg_28]
0x140028f4c  mov     rbx, rdx
0x140028f4f  mov     [rsp+170h+Instance], rdx
0x140028f54  mov     r14, rcx
0x140028f57  mov     rdx, rcx
0x140028f5a  mov     rdi, r9
0x140028f5d  mov     [r15], r12
0x140028f60  lea     rcx, [rsp+170h+FastMutex]
0x140028f65  mov     [r15+8], r12
0x140028f69  mov     r13, r8
0x140028f6c  mov     [r15+10h], r12
0x140028f70  mov     [r15+18h], r12
0x140028f74  call    ?AcquireFastMutex@FsFltWil@@YA?AV?$unique_ptr@U_FAST_MUTEX@@U?$function_deleter@P6AXPEAU_FAST_MUTEX@@@Z$1?ExReleaseFastMutex@@YAX0@Z@wil@@@wistd@@AEAU_FAST_MUTEX@@@Z; FsFltWil::AcquireFastMutex(_FAST_MUTEX &)
0x140028f79  cmp     [r14+50h], r12
0x140028f7d  jnz     loc_14002902E
0x140028f83  mov     eax, [r14+44h]
0x140028f87  cmp     eax, 10000000h
0x140028f8c  jnb     short loc_140028F96
0x140028f8e  test    al, 3Fh
0x140028f90  jnz     loc_140029042
0x140028f96  mov     rcx, [rsp+170h+FastMutex]; FastMutex
0x140028f9b  mov     [rbp+70h+var_E0], r12
0x140028f9f  test    rcx, rcx
0x140028fa2  jz      short loc_140028FB0
0x140028fa4  call    cs:__imp_ExReleaseFastMutex
0x140028fab  nop     dword ptr [rax+rax+00h]
0x140028fb0  mov     rax, [rdi+48h]
0x140028fb4  lea     r8, [rsp+170h+FastMutex]
0x140028fb9  mov     r9, rsi
0x140028fbc  mov     [rsp+170h+var_110.Buffer], rax
0x140028fc1  mov     edx, 1000101h
0x140028fc6  mov     [rsp+170h+FastMutex], r12
0x140028fcb  lea     rcx, [rsp+170h+var_110]
0x140028fd0  mov     qword ptr [rsp+170h+var_110.Length], r12
0x140028fd5  mov     [rsp+170h+var_100], rbx
0x140028fda  call    ?GetFileNameInformation@Utils@UnionFs@@YAJUNameInfoParams@12@KAEAV?$unique_ptr@U_FLT_FILE_NAME_INFORMATION@@U?$function_deleter@P6AXPEAU_FLT_FILE_NAME_INFORMATION@@@Z$1?FltReleaseFileNameInformation@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@@Z; UnionFs::Utils::GetFileNameInformation(UnionFs::Utils::NameInfoParams,ulong,wistd::unique_ptr<_FLT_FILE_NAME_INFORMATION,wil::function_deleter<void (*)(_FLT_FILE_NAME_INFORMATION *),&FltReleaseFileNameInformation(_FLT_FILE_NAME_INFORMATION *)>> &,UnionFs::StackEventTracer &)
0x140028fdf  mov     ebx, eax
0x140028fe1  test    eax, eax
0x140028fe3  jns     short loc_14002905F
0x140028fe5  lea     rax, aPushGetFileNam; "PUSH: Get file name info"
0x140028fec  mov     r8, 5DF000A02E6h; struct UnionFs::StackEventTracer *
0x140028ff6  lea     r9, aUnionfsUfsfile_7; "UnionFs::UfsFileCtx::GetUfsFileID"
0x140028ffd  mov     qword ptr [rsp+170h+FileInformationClass], rax; char *
0x140029002  mov     rdx, rsi; int
0x140029005  mov     ecx, ebx; this
0x140029007  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14002900c  mov     rcx, [rsp+170h+FastMutex]; FileNameInformation
0x140029011  mov     [rsp+170h+FastMutex], r12
0x140029016  test    rcx, rcx
0x140029019  jz      short loc_140029027
0x14002901b  call    cs:__imp_FltReleaseFileNameInformation
0x140029022  nop     dword ptr [rax+rax+00h]
0x140029027  mov     eax, ebx
0x140029029  jmp     loc_14002958F
0x14002902e  mov     rax, 400000000000000h
0x140029038  cmp     [r14+48h], rax
0x14002903c  jb      loc_140028F96
0x140029042  movups  xmm0, xmmword ptr [r14+40h]
0x140029047  mov     r12, [rsp+170h+FastMutex]
0x14002904c  movups  xmmword ptr [r15], xmm0
0x140029050  movups  xmm1, xmmword ptr [r14+50h]
0x140029055  movups  xmmword ptr [r15+10h], xmm1
0x14002905a  jmp     loc_140029579
0x14002905f  mov     eax, [rdi]
0x140029061  test    al, 1
0x140029063  jnz     loc_1400293C1
0x140029069  lea     rdx, [r13+48h]
0x14002906d  lea     rcx, [rsp+170h+var_110]
0x140029072  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x140029077  mov     rax, [r13+30h]
0x14002907b  mov     rbx, [rax+8]
0x14002907f  mov     r12, [rax]
0x140029082  mov     qword ptr [rsp+170h+var_138], r12
0x140029087  test    rbx, rbx
0x14002908a  jz      short loc_140029090
0x14002908c  lock inc dword ptr [rbx+8]
0x140029090  mov     rcx, qword ptr [rsp+170h+var_110.Length]; this
0x140029095  test    rcx, rcx
0x140029098  jz      short loc_14002909F
0x14002909a  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x14002909f  test    r12, r12
0x1400290a2  jnz     short loc_140029103
0x1400290a4  lea     rax, aOriginNoScratc_0; "ORIGIN: No scratchLayer"
0x1400290ab  mov     edi, 0C0ED0008h
0x1400290b0  mov     ecx, edi; this
0x1400290b2  mov     qword ptr [rsp+170h+FileInformationClass], rax; char *
0x1400290b7  lea     r9, aUnionfsUfsfile_7; "UnionFs::UfsFileCtx::GetUfsFileID"
0x1400290be  mov     r8, 3F1000A030Ch; struct UnionFs::StackEventTracer *
0x1400290c8  mov     rdx, rsi; int
0x1400290cb  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400290d0  test    rbx, rbx
0x1400290d3  jz      short loc_1400290DD
0x1400290d5  mov     rcx, rbx; this
0x1400290d8  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1400290dd  mov     rcx, [rsp+170h+FastMutex]; FileNameInformation
0x1400290e2  mov     [rsp+170h+FastMutex], 0
0x1400290eb  test    rcx, rcx
0x1400290ee  jz      short loc_1400290FC
0x1400290f0  call    cs:__imp_FltReleaseFileNameInformation
0x1400290f7  nop     dword ptr [rax+rax+00h]
0x1400290fc  mov     eax, edi
0x1400290fe  jmp     loc_14002958F
0x140029103  xor     edx, edx; Val
0x140029105  lea     rcx, [rbp+70h+FileInformation]; void *
0x140029109  lea     r8d, [rdx+68h]; Size
0x14002910d  call    memset
0x140029112  mov     rdx, [rdi+48h]; FileObject
0x140029116  lea     r8, [rbp+70h+FileInformation]; FileInformation
0x14002911a  mov     rcx, [rsp+170h+Instance]; Instance
0x14002911f  mov     r9d, 68h ; 'h'; Length
0x140029125  mov     [rsp+170h+LengthReturned], 0; char *
0x14002912e  mov     [rsp+170h+FileInformationClass], 12h; FileInformationClass
0x140029136  call    cs:__imp_FltQueryInformationFile
0x14002913d  nop     dword ptr [rax+rax+00h]
0x140029142  mov     edi, eax
0x140029144  mov     eax, 80000000h
0x140029149  lea     ecx, [rdi+rax]
0x14002914c  test    eax, ecx
0x14002914e  jnz     short loc_140029184
0x140029150  cmp     edi, 80000005h
0x140029156  jz      short loc_140029184
0x140029158  lea     rax, aApiQueryingAll; "API: Querying all info"
0x14002915f  mov     r8, 44C000A031Ah; struct UnionFs::StackEventTracer *
0x140029169  lea     r9, aUnionfsUfsfile_7; "UnionFs::UfsFileCtx::GetUfsFileID"
0x140029170  mov     qword ptr [rsp+170h+FileInformationClass], rax; char *
0x140029175  mov     rdx, rsi; int
0x140029178  mov     ecx, edi; this
0x14002917a  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14002917f  jmp     loc_1400290D0
0x140029184  xorps   xmm0, xmm0
0x140029187  lea     rdx, [rsp+170h+var_110]; struct _UNICODE_STRING *
0x14002918c  mov     r8b, 1; bool
0x14002918f  mov     rcx, r12; this
0x140029192  movups  xmmword ptr [rsp+170h+var_110.Length], xmm0
0x140029197  call    ?GetNormalizedLayerRootPath@UfsLayerCtx@UnionFs@@QEBAGAEAU_UNICODE_STRING@@_N@Z; UnionFs::UfsLayerCtx::GetNormalizedLayerRootPath(_UNICODE_STRING &,bool)
0x14002919c  lea     rcx, [rsp+170h+Instance]
0x1400291a1  call    ??$make_unique@UFindAndStatResults@UnionFs@@$$V$0A@@utl@@YA?AV?$unique_ptr@UFindAndStatResults@UnionFs@@U?$default_delete@UFindAndStatResults@UnionFs@@@utl@@@0@XZ; utl::make_unique<UnionFs::FindAndStatResults,,0>(void)
0x1400291a6  mov     rdi, [rsp+170h+Instance]
0x1400291ab  test    rdi, rdi
0x1400291ae  jnz     short loc_1400291F0
0x1400291b0  lea     rax, aOriginAllocati_61; "ORIGIN: Allocating findAndStatResults"
0x1400291b7  mov     r8, 3F7000A032Ah; struct UnionFs::StackEventTracer *
0x1400291c1  lea     r9, aUnionfsUfsfile_7; "UnionFs::UfsFileCtx::GetUfsFileID"
0x1400291c8  mov     qword ptr [rsp+170h+FileInformationClass], rax; char *
0x1400291cd  mov     rdx, rsi; int
0x1400291d0  mov     ecx, 0C000009Ah; this
0x1400291d5  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400291da  test    rbx, rbx
0x1400291dd  jz      loc_140029398
0x1400291e3  mov     rcx, rbx; this
0x1400291e6  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1400291eb  jmp     loc_140029398
0x1400291f0  mov     rdx, [rsp+170h+FastMutex]
0x1400291f5  lea     r8, [rsp+170h+var_110]
0x1400291fa  add     rdx, 8
0x1400291fe  mov     [rsp+170h+LengthReturned], rsi; char *
0x140029203  mov     r9d, 1
0x140029209  mov     qword ptr [rsp+170h+FileInformationClass], rdi
0x14002920e  mov     rcx, r13
0x140029211  call    ?FindAndStatItemInLayers@UfsUnionCtx@UnionFs@@QEBAJAEBU_UNICODE_STRING@@0W4StatItemFlags@Utils@2@AEAUFindAndStatResults@2@AEAVStackEventTracer@2@@Z; UnionFs::UfsUnionCtx::FindAndStatItemInLayers(_UNICODE_STRING const &,_UNICODE_STRING const &,UnionFs::Utils::StatItemFlags,UnionFs::FindAndStatResults &,UnionFs::StackEventTracer &)
0x140029216  mov     r12d, eax
0x140029219  test    eax, eax
0x14002921b  jns     loc_1400292A1
0x140029221  lea     rax, aPushProbingFor; "PUSH: Probing for item in layers"
0x140029228  mov     r8, 428000A0333h; struct UnionFs::StackEventTracer *
0x140029232  lea     r9, aUnionfsUfsfile_7; "UnionFs::UfsFileCtx::GetUfsFileID"
0x140029239  mov     qword ptr [rsp+170h+FileInformationClass], rax; char *
0x14002923e  mov     rdx, rsi; int
0x140029241  mov     ecx, r12d; this
0x140029244  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140029249  test    rdi, rdi
0x14002924c  jz      short loc_14002926D
0x14002924e  mov     rcx, [rdi+58h]; this
0x140029252  test    rcx, rcx
0x140029255  jz      short loc_14002925C
0x140029257  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14002925c  xor     edx, edx; Tag
0x14002925e  mov     rcx, rdi; P
0x140029261  call    cs:__imp_ExFreePoolWithTag
0x140029268  nop     dword ptr [rax+rax+00h]
0x14002926d  test    rbx, rbx
0x140029270  jz      short loc_14002927A
0x140029272  mov     rcx, rbx; this
0x140029275  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14002927a  mov     rcx, [rsp+170h+FastMutex]; FileNameInformation
0x14002927f  mov     [rsp+170h+FastMutex], 0
0x140029288  test    rcx, rcx
0x14002928b  jz      short loc_140029299
0x14002928d  call    cs:__imp_FltReleaseFileNameInformation
0x140029294  nop     dword ptr [rax+rax+00h]
0x140029299  mov     eax, r12d
0x14002929c  jmp     loc_14002958F
0x1400292a1  mov     eax, 1
0x1400292a6  cmp     [rdi], ax
0x1400292a9  jnz     short loc_1400292BF
0x1400292ab  mov     rax, [rdi+10h]
0x1400292af  cmp     [rbp+70h+FileInformation], rax
0x1400292b3  jnz     short loc_1400292BF
0x1400292b5  mov     rdx, [rdi+8]
0x1400292b9  mov     r8, [rdi+50h]
0x1400292bd  jmp     short loc_1400292C8
0x1400292bf  mov     r8, qword ptr [rsp+170h+var_138]; struct UnionFs::UfsLayerCtx *
0x1400292c4  mov     rdx, qword ptr [rbp+70h+var_80]; union _LARGE_INTEGER
0x1400292c8  mov     r9, r13; struct UnionFs::UfsUnionCtx *
0x1400292cb  lea     rcx, [rsp+170h+var_110]; this
0x1400292d0  call    ??0UfsFileID@UnionFs@@QEAA@T_LARGE_INTEGER@@AEBVUfsLayerCtx@1@AEBVUfsUnionCtx@1@@Z; UnionFs::UfsFileID::UfsFileID(_LARGE_INTEGER,UnionFs::UfsLayerCtx const &,UnionFs::UfsUnionCtx const &)
0x1400292d5  lea     rdx, [rsp+170h+Instance]; struct UnionFs::UfsFileID *
0x1400292da  mov     rcx, r14; this
0x1400292dd  movups  xmm0, xmmword ptr [rax]
0x1400292e0  movups  xmm1, xmmword ptr [rax+10h]
0x1400292e4  movups  xmmword ptr [rsp+170h+Instance], xmm0
0x1400292e9  movups  [rsp+170h+var_120], xmm1
0x1400292ee  call    ?SetFileID@UfsFileCtx@UnionFs@@AEBAXAEBVUfsFileID@2@@Z; UnionFs::UfsFileCtx::SetFileID(UnionFs::UfsFileID const &)
0x1400292f3  movups  xmm0, xmmword ptr [r14+40h]
0x1400292f8  movups  xmmword ptr [r15], xmm0
0x1400292fc  movups  xmm1, xmmword ptr [r14+50h]
0x140029301  movups  xmmword ptr [r15+10h], xmm1
0x140029306  test    rdi, rdi
0x140029309  jz      short loc_14002932A
0x14002930b  mov     rcx, [rdi+58h]; this
0x14002930f  test    rcx, rcx
0x140029312  jz      short loc_140029319
0x140029314  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140029319  xor     edx, edx; Tag
0x14002931b  mov     rcx, rdi; P
0x14002931e  call    cs:__imp_ExFreePoolWithTag
0x140029325  nop     dword ptr [rax+rax+00h]
0x14002932a  test    rbx, rbx
0x14002932d  jz      short loc_140029337
0x14002932f  mov     rcx, rbx; this
0x140029332  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140029337  mov     r12, [rbp+70h+var_E0]
0x14002933b  mov     rax, [rsp+170h+FastMutex]
0x140029340  lea     rcx, [rbp+70h+DestinationString]
0x140029344  mov     r8d, 4C467346h
0x14002934a  movzx   ebx, word ptr [rax+8]
0x14002934e  sub     bx, [rax+18h]
0x140029352  movzx   edx, bx
0x140029355  call    ?MakeUniqueUnicodeString@FsFltWil@@YA?AV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@GKW4FSFLT_ALLOC_TYPE@@@Z; FsFltWil::MakeUniqueUnicodeString(ushort,ulong,FSFLT_ALLOC_TYPE)
0x14002935a  cmp     [rbp+70h+DestinationString.Buffer], 0
0x14002935f  jnz     loc_1400294C1
0x140029365  lea     rax, aOriginAllocati_38; "ORIGIN: Allocating normalized name for "...
0x14002936c  mov     r8, 46C000A0360h; struct UnionFs::StackEventTracer *
0x140029376  lea     r9, aUnionfsUfsfile_7; "UnionFs::UfsFileCtx::GetUfsFileID"
0x14002937d  mov     qword ptr [rsp+170h+FileInformationClass], rax; char *
0x140029382  mov     rdx, rsi; int
0x140029385  mov     ecx, 0C000009Ah; this
0x14002938a  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14002938f  lea     rcx, [rbp+70h+DestinationString]; UnicodeString
0x140029393  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140029398  mov     rcx, [rsp+170h+FastMutex]; FileNameInformation
0x14002939d  mov     [rsp+170h+FastMutex], 0
0x1400293a6  test    rcx, rcx
0x1400293a9  jz      short loc_1400293B7
0x1400293ab  call    cs:__imp_FltReleaseFileNameInformation
0x1400293b2  nop     dword ptr [rax+rax+00h]
0x1400293b7  mov     eax, 0C000009Ah
0x1400293bc  jmp     loc_14002958F
0x1400293c1  mov     rax, [rdi+48h]
0x1400293c5  lea     rcx, [rsp+170h+Instance]
0x1400293ca  mov     rbx, [rax+20h]
0x1400293ce  lea     rdx, [rbx+20h]
0x1400293d2  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x1400293d7  mov     rcx, [rsp+170h+Instance]; this
0x1400293dc  mov     rbx, [rbx+18h]
0x1400293e0  test    rcx, rcx
0x1400293e3  jz      short loc_1400293EA
0x1400293e5  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x1400293ea  lea     rdx, [rsp+170h+Instance]
0x1400293ef  mov     rcx, rdi
0x1400293f2  call    ?TryGetBackingLayer@UfsStreamHandleCtx@UnionFs@@QEBA?AV?$shared_ptr@VUfsLayerCtx@UnionFs@@@utl@@XZ; UnionFs::UfsStreamHandleCtx::TryGetBackingLayer(void)
0x1400293f7  mov     rdi, [rsp+170h+Instance]
0x1400293fc  lea     r8, [rsp+170h+var_138]; FileInformation
0x140029401  mov     qword ptr [rsp+170h+var_138], r12
0x140029406  mov     r9d, 8; Length
0x14002940c  mov     [rsp+170h+LengthReturned], r12; char *
0x140029411  mov     rdx, rbx; FileObject
0x140029414  mov     [rsp+170h+FileInformationClass], 6; FileInformationClass
0x14002941c  mov     rcx, [rdi+8]
0x140029420  mov     rcx, [rcx]; Instance
0x140029423  call    cs:__imp_FltQueryInformationFile
0x14002942a  nop     dword ptr [rax+rax+00h]
0x14002942f  mov     ebx, eax
0x140029431  test    eax, eax
0x140029433  jns     short loc_140029474
  ... truncated ...
```
