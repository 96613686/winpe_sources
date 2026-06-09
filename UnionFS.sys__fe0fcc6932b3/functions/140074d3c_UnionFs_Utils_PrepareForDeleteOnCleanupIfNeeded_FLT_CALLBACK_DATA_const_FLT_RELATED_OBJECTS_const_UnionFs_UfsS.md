# UnionFs::Utils::PrepareForDeleteOnCleanupIfNeeded(_FLT_CALLBACK_DATA const &,_FLT_RELATED_OBJECTS const &,UnionFs::UfsStreamHandleCtx &,UnionFs::UfsFileCtx &,UnionFs::UfsUnionCtx &,utl::unique_ptr<UnionFs::CleanupContext,utl::default_delete<UnionFs::CleanupContext>> &,UnionFs::StackEventTracer &)

- ea: `0x140074d3c`
- end: `0x1400751d5`
- name: `?PrepareForDeleteOnCleanupIfNeeded@Utils@UnionFs@@YAJAEBU_FLT_CALLBACK_DATA@@AEBU_FLT_RELATED_OBJECTS@@AEAVUfsStreamHandleCtx@2@AEAVUfsFileCtx@2@AEAVUfsUnionCtx@2@AEAV?$unique_ptr@UCleanupContext@UnionFs@@U?$default_delete@UCleanupContext@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z`
- size: `1177`
- prototype: `__int64 __fastcall(struct _FLT_CALLBACK_DATA *, const struct _FLT_CALLBACK_DATA *, struct _FLT_RELATED_OBJECTS *, const struct UnionFs::UfsStreamHandleCtx *, __int64, UnionFs::CleanupContext **, UnionFs::StackEventTracer *)`
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, loader_planting, installer_update`

## callers

- `0x14002d6d0`
- `0x140058008`

## callees

- `0x14000f81c`
- `0x1400111b8`
- `0x14002b4c8`
- `0x14002be84`
- `0x14003cea8`
- `0x140056974`
- `0x140056bd0`
- `0x140056c44`
- `0x140056c7c`
- `0x140067de0`
- `0x14006e394`
- `0x14007078c`
- `0x140070a30`
- `0x140074d3c`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x140075182`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140075182`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140075020`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140075020`
- `FLTMGR!FltSetInformationFile` at `0x140074dda`
- `FLTMGR!FltSetInformationFile` at `0x140074dda`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140074ea1`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140074f7d`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14007512f`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400751b2`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140074ea1`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140074f7d`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14007512f`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400751b2`
- `FLTMGR!FltReferenceContext` at `0x140075080`
- `FLTMGR!FltReferenceContext` at `0x140075080`

## string_xrefs

- `0x140074da5`: `UnionFs::Utils::PrepareForDeleteOnCleanupIfNeeded`
- `0x140074e02`: `UnionFs::Utils::PrepareForDeleteOnCleanupIfNeeded`
- `0x140074e7e`: `UnionFs::Utils::PrepareForDeleteOnCleanupIfNeeded`
- `0x140074f49`: `UnionFs::Utils::PrepareForDeleteOnCleanupIfNeeded`
- `0x140074fc9`: `UnionFs::Utils::PrepareForDeleteOnCleanupIfNeeded`
- `0x1400750f2`: `UnionFs::Utils::PrepareForDeleteOnCleanupIfNeeded`
- `0x140074d94`: `PUSH: Failed to prepare delete-on-close handle for delete.`
- `0x140074f38`: `PUSH: Looking up cache entry`
- `0x140074df8`: `API: Un-setting delete-on-close.`

## pseudocode

```c
__int64 __fastcall UnionFs::Utils::PrepareForDeleteOnCleanupIfNeeded(
        struct _FLT_CALLBACK_DATA *a1,
        const struct _FLT_CALLBACK_DATA *a2,
        struct _FLT_RELATED_OBJECTS *a3,
        const struct UnionFs::UfsStreamHandleCtx *a4,
        __int64 a5,
        UnionFs::CleanupContext **a6,
        UnionFs::StackEventTracer *a7)
{
  UnionFs::StackEventTracer *v7; // rbx
  int FileNameInformation; // edi
  struct _FILE_OBJECT *Information; // rdx
  struct _FLT_INSTANCE *Pointer; // rcx
  NTSTATUS v15; // esi
  struct _FLT_FILE_NAME_INFORMATION *v17; // rcx
  int v18; // edi
  __int64 v19; // r13
  PVOID v20; // rdx
  int v21; // r9d
  struct _FLT_FILE_NAME_INFORMATION *v22; // rcx
  _QWORD *v23; // rdi
  __int64 v24; // rsi
  utl::_RefCountBase *v25; // rcx
  utl::_RefCountBase *v26; // r8
  __int64 v27; // rdx
  utl::_RefCountBase *v28; // rcx
  utl::_RefCountBase *v29; // rax
  const char *v30; // rax
  __int64 v31; // r8
  struct _FLT_FILE_NAME_INFORMATION *v32; // rcx
  UnionFs::CleanupContext *v33; // rbx
  struct _FLT_FILE_NAME_INFORMATION *v34; // rcx
  char *v35; // [rsp+28h] [rbp-A9h]
  char *v36; // [rsp+28h] [rbp-A9h]
  char *v37; // [rsp+28h] [rbp-A9h]
  struct _FLT_CALLBACK_DATA *v38; // [rsp+40h] [rbp-91h] BYREF
  __int64 v39; // [rsp+48h] [rbp-89h]
  __int64 v40; // [rsp+50h] [rbp-81h]
  __int128 v41; // [rsp+60h] [rbp-71h] BYREF
  utl::_RefCountBase *v42[2]; // [rsp+70h] [rbp-61h] BYREF
  __int64 v43; // [rsp+80h] [rbp-51h]
  __int64 v44; // [rsp+88h] [rbp-49h]
  __int128 v45; // [rsp+90h] [rbp-41h]
  UnionFs::CleanupContext *v46; // [rsp+A0h] [rbp-31h] BYREF
  _QWORD v47[13]; // [rsp+A8h] [rbp-29h] BYREF
  struct _FLT_FILE_NAME_INFORMATION *FileInformation; // [rsp+130h] [rbp+5Fh] BYREF

  v7 = a7;
  if ( (*(_DWORD *)&a3->Size & 4) != 0 && !*((_BYTE *)a4 + 56) )
  {
    FileNameInformation = UnionFs::Utils::MarkFileAsDeleteCandidateIfInLayer(
                            a1,
                            a2,
                            a3,
                            a4,
                            a7,
                            (struct UnionFs::StackEventTracer *)v35);
    if ( FileNameInformation < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)FileNameInformation,
        (int)v7,
        (struct UnionFs::StackEventTracer *)0x2FE00211FC0LL,
        (unsigned __int64)"UnionFs::Utils::PrepareForDeleteOnCleanupIfNeeded",
        "PUSH: Failed to prepare delete-on-close handle for delete.",
        v35);
      Information = (struct _FILE_OBJECT *)a2->IoStatus.Information;
      Pointer = (struct _FLT_INSTANCE *)a2->IoStatus.Pointer;
      LODWORD(FileInformation) = 8;
      v15 = FltSetInformationFile(Pointer, Information, &FileInformation, 4u, (FILE_INFORMATION_CLASS)64);
      if ( v15 < 0 )
      {
        UnionFs::StackEventTracer::LogError(v7);
        *(_DWORD *)v7 = 0;
        *((_WORD *)v7 + 274) = 0;
        UnionFs::ProcessTraceStatusFromApi(
          (UnionFs *)(unsigned int)v15,
          (int)v7,
          (struct UnionFs::StackEventTracer *)0x30900211FD5LL,
          (unsigned __int64)"UnionFs::Utils::PrepareForDeleteOnCleanupIfNeeded",
          "API: Un-setting delete-on-close.",
          v36);
        return (unsigned int)v15;
      }
      return (unsigned int)FileNameInformation;
    }
  }
  if ( !*((_BYTE *)a4 + 56) )
    return 0;
  FileInformation = 0;
  v38 = a1;
  v39 = 0;
  v40 = 0;
  FileNameInformation = UnionFs::Utils::GetFileNameInformation(&v38, 16778241, &FileInformation, v7);
  if ( FileNameInformation < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)FileNameInformation,
      (int)v7,
      (struct UnionFs::StackEventTracer *)0x2DE00211FF4LL,
      (unsigned __int64)"UnionFs::Utils::PrepareForDeleteOnCleanupIfNeeded",
      "PUSH: Looking up name",
      v35);
    v17 = FileInformation;
    FileInformation = 0;
    goto LABEL_10;
  }
  v18 = a5;
  if ( *(_DWORD *)(a5 + 28) == 2 )
    v19 = *(_QWORD *)(*(_QWORD *)(a5 + 32) + 16LL);
  else
    v19 = *((_QWORD *)UnionFs::g_FilterState + 10);
  v20 = a2->IoStatus.Pointer;
  v21 = *(_DWORD *)(a2->IoStatus.Information + 80);
  v41 = 0;
  *(_OWORD *)v42 = 0;
  v43 = 0;
  v44 = 0;
  v45 = 0;
  v15 = UnionFs::UfsPathCache::LookupEntry(v19, v20, FileInformation, ((v21 & 0x20000) == 0) | 2u, &v41);
  if ( v15 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v15,
      (int)v7,
      (struct UnionFs::StackEventTracer *)0x2FF00212008LL,
      (unsigned __int64)"UnionFs::Utils::PrepareForDeleteOnCleanupIfNeeded",
      "PUSH: Looking up cache entry",
      (const char *)v7);
    UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)&v41);
    v22 = FileInformation;
    FileInformation = 0;
    if ( v22 )
      FltReleaseFileNameInformation(v22);
    return (unsigned int)v15;
  }
  FileNameInformation = UnionFs::Utils::MarkFileAsSoftTombstone(
                          (int)a2->IoStatus.Pointer,
                          v18,
                          (int)FileInformation,
                          6,
                          (__int64)v42,
                          (char *)v7);
  if ( FileNameInformation < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)FileNameInformation,
      (int)v7,
      (struct UnionFs::StackEventTracer *)0x2D400212015LL,
      (unsigned __int64)"UnionFs::Utils::PrepareForDeleteOnCleanupIfNeeded",
      "PUSH: Could not place soft tombstone",
      v37);
    UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)&v41);
    v17 = FileInformation;
    FileInformation = 0;
LABEL_10:
    if ( v17 )
      FltReleaseFileNameInformation(v17);
    return (unsigned int)FileNameInformation;
  }
  v23 = 0;
  LOBYTE(v39) = 1;
  v38 = (struct _FLT_CALLBACK_DATA *)&v41;
  v24 = 8;
  if ( *((_BYTE *)a4 + 96) )
  {
    v23 = ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 1088));
    if ( !v23 )
    {
      v30 = "ORIGIN: Allocating CollapseContext";
      v31 = 0x3520021202DLL;
      goto LABEL_38;
    }
    v25 = v42[1];
    v26 = v42[0];
    if ( v42[1] )
    {
      v27 = (__int64)v42[1] + 8;
      _InterlockedIncrement((volatile signed __int32 *)v42[1] + 2);
    }
    else
    {
      v27 = 8;
    }
    *v23 = a2->IoStatus.Pointer;
    v23[1] = v19;
    v23[2] = v26;
    v23[3] = v25;
    if ( v25 )
      _InterlockedIncrement((volatile signed __int32 *)v27);
    *((_OWORD *)v23 + 2) = 0;
    if ( v25 )
      utl::_RefCountBase::_DecStrong(v25);
  }
  FltReferenceContext(a3);
  v28 = v42[1];
  v29 = v42[0];
  if ( v42[1] )
  {
    v24 = (__int64)v42[1] + 8;
    _InterlockedIncrement((volatile signed __int32 *)v42[1] + 2);
  }
  v47[0] = v29;
  v47[1] = v28;
  if ( v28 )
    _InterlockedIncrement((volatile signed __int32 *)v24);
  v47[2] = v23;
  v47[3] = a3;
  if ( v28 )
    utl::_RefCountBase::_DecStrong(v28);
  utl::make_unique<UnionFs::CleanupContext,UnionFs::CleanupContext,0>(&v46, v47);
  UnionFs::CleanupContext::~CleanupContext((UnionFs::CleanupContext *)v47);
  if ( v46 )
  {
    LOBYTE(v39) = 0;
    v33 = *a6;
    *a6 = v46;
    if ( v33 )
    {
      UnionFs::CleanupContext::~CleanupContext(v33);
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 800), v33);
    }
    wil::details::lambda_call__lambda_e6bdf39cdf6c17d197b59323a22c4106___::_lambda_call__lambda_e6bdf39cdf6c17d197b59323a22c4106___(&v38);
    UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)&v41);
    v34 = FileInformation;
    FileInformation = 0;
    if ( v34 )
      FltReleaseFileNameInformation(v34);
    return 0;
  }
  v30 = "ORIGIN: Allocating cleanup context";
  v31 = 0x3100021203ALL;
LABEL_38:
  UnionFs::ProcessTraceStatusOrigin(
    (UnionFs *)0xC000009ALL,
    (int)v7,
    (struct UnionFs::StackEventTracer *)v31,
    (unsigned __int64)"UnionFs::Utils::PrepareForDeleteOnCleanupIfNeeded",
    v30,
    v37);
  wil::details::lambda_call__lambda_e6bdf39cdf6c17d197b59323a22c4106___::_lambda_call__lambda_e6bdf39cdf6c17d197b59323a22c4106___(&v38);
  UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)&v41);
  v32 = FileInformation;
  FileInformation = 0;
  if ( v32 )
    FltReleaseFileNameInformation(v32);
  return 3221225626LL;
}

```

## disassembly

```asm
0x140074d3c  push    rbp
0x140074d3e  push    rbx
0x140074d3f  push    rsi
0x140074d40  push    rdi
0x140074d41  push    r12
0x140074d43  push    r13
0x140074d45  push    r14
0x140074d47  push    r15
0x140074d49  lea     rbp, [rsp-7]
0x140074d4e  sub     rsp, 0D8h
0x140074d55  mov     eax, [r8]
0x140074d58  xor     r13d, r13d
0x140074d5b  mov     rbx, [rbp+3Fh+arg_30]
0x140074d5f  mov     r14, r9
0x140074d62  mov     r12, r8
0x140074d65  mov     r15, rdx
0x140074d68  mov     rsi, rcx
0x140074d6b  test    al, 4
0x140074d6d  jz      loc_140074E31
0x140074d73  mov     al, [r9+38h]
0x140074d77  nop
0x140074d78  test    al, al
0x140074d7a  jnz     loc_140074E31
0x140074d80  mov     qword ptr [rsp+110h+FileInformationClass], rbx; struct UnionFs::UfsFileCtx *
0x140074d85  call    ?MarkFileAsDeleteCandidateIfInLayer@Utils@UnionFs@@YAJAEBU_FLT_CALLBACK_DATA@@AEBU_FLT_RELATED_OBJECTS@@AEBVUfsStreamHandleCtx@2@AEAVUfsFileCtx@2@AEAVStackEventTracer@2@@Z; UnionFs::Utils::MarkFileAsDeleteCandidateIfInLayer(_FLT_CALLBACK_DATA const &,_FLT_RELATED_OBJECTS const &,UnionFs::UfsStreamHandleCtx const &,UnionFs::UfsFileCtx &,UnionFs::StackEventTracer &)
0x140074d8a  mov     edi, eax
0x140074d8c  test    eax, eax
0x140074d8e  jns     loc_140074E31
0x140074d94  lea     rax, aPushFailedToPr; "PUSH: Failed to prepare delete-on-close"...
0x140074d9b  mov     r8, 2FE00211FC0h; struct UnionFs::StackEventTracer *
0x140074da5  lea     r9, aUnionfsUtilsPr_2; "UnionFs::Utils::PrepareForDeleteOnClean"...
0x140074dac  mov     qword ptr [rsp+110h+FileInformationClass], rax; char *
0x140074db1  mov     rdx, rbx; int
0x140074db4  mov     ecx, edi; this
0x140074db6  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140074dbb  mov     rdx, [r15+20h]; FileObject
0x140074dbf  lea     esi, [r13+8]
0x140074dc3  mov     rcx, [r15+18h]; Instance
0x140074dc7  lea     r9d, [r13+4]; Length
0x140074dcb  lea     r8, [rbp+3Fh+FileInformation]; FileInformation
0x140074dcf  mov     dword ptr [rbp+3Fh+FileInformation], esi
0x140074dd2  mov     [rsp+110h+FileInformationClass], 40h ; '@'; FileInformationClass
0x140074dda  call    cs:__imp_FltSetInformationFile
0x140074de1  nop     dword ptr [rax+rax+00h]
0x140074de6  mov     esi, eax
0x140074de8  test    eax, eax
0x140074dea  jns     loc_140074EAD
0x140074df0  mov     rcx, rbx; this
0x140074df3  call    ?LogError@StackEventTracer@UnionFs@@AEAAXXZ; UnionFs::StackEventTracer::LogError(void)
0x140074df8  lea     rax, aApiUnSettingDe; "API: Un-setting delete-on-close."
0x140074dff  mov     [rbx], r13d
0x140074e02  lea     r9, aUnionfsUtilsPr_2; "UnionFs::Utils::PrepareForDeleteOnClean"...
0x140074e09  mov     qword ptr [rsp+110h+FileInformationClass], rax; char *
0x140074e0e  mov     r8, 30900211FD5h; struct UnionFs::StackEventTracer *
0x140074e18  mov     [rbx+224h], r13w
0x140074e20  mov     rdx, rbx; int
0x140074e23  mov     ecx, esi; this
0x140074e25  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140074e2a  mov     eax, esi
0x140074e2c  jmp     loc_1400751C0
0x140074e31  mov     al, [r14+38h]
0x140074e35  nop
0x140074e36  test    al, al
0x140074e38  jz      loc_1400751BE
0x140074e3e  mov     r9, rbx
0x140074e41  mov     [rbp+3Fh+FileInformation], r13
0x140074e45  lea     r8, [rbp+3Fh+FileInformation]
0x140074e49  mov     [rsp+110h+var_D0], rsi
0x140074e4e  mov     edx, 1000401h
0x140074e53  mov     [rsp+110h+var_C8], r13
0x140074e58  lea     rcx, [rsp+110h+var_D0]
0x140074e5d  mov     [rsp+110h+var_C0], r13
0x140074e62  call    ?GetFileNameInformation@Utils@UnionFs@@YAJUNameInfoParams@12@KAEAV?$unique_ptr@U_FLT_FILE_NAME_INFORMATION@@U?$function_deleter@P6AXPEAU_FLT_FILE_NAME_INFORMATION@@@Z$1?FltReleaseFileNameInformation@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@@Z; UnionFs::Utils::GetFileNameInformation(UnionFs::Utils::NameInfoParams,ulong,wistd::unique_ptr<_FLT_FILE_NAME_INFORMATION,wil::function_deleter<void (*)(_FLT_FILE_NAME_INFORMATION *),&FltReleaseFileNameInformation(_FLT_FILE_NAME_INFORMATION *)>> &,UnionFs::StackEventTracer &)
0x140074e67  mov     edi, eax
0x140074e69  test    eax, eax
0x140074e6b  jns     short loc_140074EB4
0x140074e6d  lea     rax, aPushLookingUpN; "PUSH: Looking up name"
0x140074e74  mov     r8, 2DE00211FF4h; struct UnionFs::StackEventTracer *
0x140074e7e  lea     r9, aUnionfsUtilsPr_2; "UnionFs::Utils::PrepareForDeleteOnClean"...
0x140074e85  mov     qword ptr [rsp+110h+FileInformationClass], rax; char *
0x140074e8a  mov     rdx, rbx; int
0x140074e8d  mov     ecx, edi; this
0x140074e8f  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140074e94  mov     rcx, [rbp+3Fh+FileInformation]; FileNameInformation
0x140074e98  mov     [rbp+3Fh+FileInformation], r13
0x140074e9c  test    rcx, rcx
0x140074e9f  jz      short loc_140074EAD
0x140074ea1  call    cs:__imp_FltReleaseFileNameInformation
0x140074ea8  nop     dword ptr [rax+rax+00h]
0x140074ead  mov     eax, edi
0x140074eaf  jmp     loc_1400751C0
0x140074eb4  mov     rdi, [rbp+3Fh+arg_20]
0x140074eb8  cmp     dword ptr [rdi+1Ch], 2
0x140074ebc  jnz     short loc_140074EC8
0x140074ebe  mov     rax, [rdi+20h]
0x140074ec2  mov     r13, [rax+10h]
0x140074ec6  jmp     short loc_140074ED3
0x140074ec8  mov     rax, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140074ecf  mov     r13, [rax+50h]
0x140074ed3  mov     rax, [r15+20h]
0x140074ed7  xorps   xmm0, xmm0
0x140074eda  mov     r8, [rbp+3Fh+FileInformation]
0x140074ede  xorps   xmm1, xmm1
0x140074ee1  mov     rdx, [r15+18h]
0x140074ee5  mov     rcx, r13
0x140074ee8  mov     [rsp+110h+var_E0], rsi
0x140074eed  mov     r9d, [rax+50h]
0x140074ef1  lea     rax, [rbp+3Fh+var_B0]
0x140074ef5  shr     r9d, 11h
0x140074ef9  not     r9d
0x140074efc  mov     [rsp+110h+var_E8], rbx; char *
0x140074f01  and     r9d, 1
0x140074f05  movdqa  [rbp+3Fh+var_B0], xmm0
0x140074f0a  or      r9d, 2
0x140074f0e  movdqa  xmmword ptr [rbp+3Fh+var_A0], xmm1
0x140074f13  mov     [rbp+3Fh+var_90], 0
0x140074f1b  mov     [rbp+3Fh+var_88], 0
0x140074f23  movdqa  [rbp+3Fh+var_80], xmm0
0x140074f28  mov     qword ptr [rsp+110h+FileInformationClass], rax
0x140074f2d  call    ?LookupEntry@UfsPathCache@UnionFs@@QEAAJAEBU_FLT_INSTANCE@@AEAU_FLT_FILE_NAME_INFORMATION@@W4LookupEntryFlags@2@AEAULookupEntryResults@2@AEAVStackEventTracer@2@PEBU_FLT_CALLBACK_DATA@@@Z; UnionFs::UfsPathCache::LookupEntry(_FLT_INSTANCE const &,_FLT_FILE_NAME_INFORMATION &,UnionFs::LookupEntryFlags,UnionFs::LookupEntryResults &,UnionFs::StackEventTracer &,_FLT_CALLBACK_DATA const *)
0x140074f32  mov     esi, eax
0x140074f34  test    eax, eax
0x140074f36  jns     short loc_140074F8E
0x140074f38  lea     rax, aPushLookingUpC; "PUSH: Looking up cache entry"
0x140074f3f  mov     r8, 2FF00212008h; struct UnionFs::StackEventTracer *
0x140074f49  lea     r9, aUnionfsUtilsPr_2; "UnionFs::Utils::PrepareForDeleteOnClean"...
0x140074f50  mov     qword ptr [rsp+110h+FileInformationClass], rax; char *
0x140074f55  mov     rdx, rbx; int
0x140074f58  mov     ecx, esi; this
0x140074f5a  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140074f5f  lea     rcx, [rbp+3Fh+var_B0]; this
0x140074f63  call    ??1LookupEntryResults@UnionFs@@QEAA@XZ; UnionFs::LookupEntryResults::~LookupEntryResults(void)
0x140074f68  mov     rcx, [rbp+3Fh+FileInformation]; FileNameInformation
0x140074f6c  mov     [rbp+3Fh+FileInformation], 0
0x140074f74  test    rcx, rcx
0x140074f77  jz      loc_140074E2A
0x140074f7d  call    cs:__imp_FltReleaseFileNameInformation
0x140074f84  nop     dword ptr [rax+rax+00h]
0x140074f89  jmp     loc_140074E2A
0x140074f8e  mov     r8, [rbp+3Fh+FileInformation]; int
0x140074f92  lea     rax, [rbp+3Fh+var_A0]
0x140074f96  mov     rcx, [r15+18h]; int
0x140074f9a  mov     r9d, 6; int
0x140074fa0  mov     [rsp+110h+var_E8], rbx; char *
0x140074fa5  mov     rdx, rdi; int
0x140074fa8  mov     qword ptr [rsp+110h+FileInformationClass], rax; __int64
0x140074fad  call    ?MarkFileAsSoftTombstone@Utils@UnionFs@@YAJAEBU_FLT_INSTANCE@@AEAVUfsUnionCtx@2@AEAU_FLT_FILE_NAME_INFORMATION@@W4SoftTombstoneReason@2@AEAV?$shared_ptr@VUfsPathCachePayload@UnionFs@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::Utils::MarkFileAsSoftTombstone(_FLT_INSTANCE const &,UnionFs::UfsUnionCtx &,_FLT_FILE_NAME_INFORMATION &,UnionFs::SoftTombstoneReason,utl::shared_ptr<UnionFs::UfsPathCachePayload> &,UnionFs::StackEventTracer &)
0x140074fb2  mov     edi, eax
0x140074fb4  test    eax, eax
0x140074fb6  jns     short loc_140074FF9
0x140074fb8  lea     rax, aPushCouldNotPl; "PUSH: Could not place soft tombstone"
0x140074fbf  mov     r8, 2D400212015h; struct UnionFs::StackEventTracer *
0x140074fc9  lea     r9, aUnionfsUtilsPr_2; "UnionFs::Utils::PrepareForDeleteOnClean"...
0x140074fd0  mov     qword ptr [rsp+110h+FileInformationClass], rax; char *
0x140074fd5  mov     rdx, rbx; int
0x140074fd8  mov     ecx, edi; this
0x140074fda  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140074fdf  lea     rcx, [rbp+3Fh+var_B0]; this
0x140074fe3  call    ??1LookupEntryResults@UnionFs@@QEAA@XZ; UnionFs::LookupEntryResults::~LookupEntryResults(void)
0x140074fe8  mov     rcx, [rbp+3Fh+FileInformation]
0x140074fec  mov     [rbp+3Fh+FileInformation], 0
0x140074ff4  jmp     loc_140074E9C
0x140074ff9  xor     edi, edi
0x140074ffb  mov     byte ptr [rsp+110h+var_C8], 1
0x140075000  lea     rax, [rbp+3Fh+var_B0]
0x140075004  mov     [rsp+110h+var_D0], rax
0x140075009  lea     esi, [rdi+8]
0x14007500c  cmp     [r14+60h], dil
0x140075010  jz      short loc_14007507D
0x140075012  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140075019  add     rcx, 440h; Lookaside
0x140075020  call    cs:__imp_ExAllocateFromLookasideListEx
0x140075027  nop     dword ptr [rax+rax+00h]
0x14007502c  mov     rdi, rax
0x14007502f  test    rax, rax
0x140075032  jz      loc_140075142
0x140075038  mov     rcx, [rbp+3Fh+var_A0+8]; this
0x14007503c  mov     r8, [rbp+3Fh+var_A0]
0x140075040  test    rcx, rcx
0x140075043  jz      short loc_14007504E
0x140075045  lea     rdx, [rcx+8]
0x140075049  lock inc dword ptr [rdx]
0x14007504c  jmp     short loc_140075051
0x14007504e  mov     rdx, rsi
0x140075051  mov     rax, [r15+18h]
0x140075055  mov     [rdi], rax
0x140075058  mov     [rdi+8], r13
0x14007505c  mov     [rdi+10h], r8
0x140075060  mov     [rdi+18h], rcx
0x140075064  test    rcx, rcx
0x140075067  jz      short loc_14007506C
0x140075069  lock inc dword ptr [rdx]
0x14007506c  xorps   xmm0, xmm0
0x14007506f  movups  xmmword ptr [rdi+20h], xmm0
0x140075073  test    rcx, rcx
0x140075076  jz      short loc_14007507D
0x140075078  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14007507d  mov     rcx, r12; Context
0x140075080  call    cs:__imp_FltReferenceContext
0x140075087  nop     dword ptr [rax+rax+00h]
0x14007508c  mov     rcx, [rbp+3Fh+var_A0+8]; this
0x140075090  mov     rax, [rbp+3Fh+var_A0]
0x140075094  test    rcx, rcx
0x140075097  jz      short loc_1400750A0
0x140075099  lea     rsi, [rcx+8]
0x14007509d  lock inc dword ptr [rsi]
0x1400750a0  mov     [rbp+3Fh+var_68], rax
0x1400750a4  mov     [rbp+3Fh+var_60], rcx
0x1400750a8  test    rcx, rcx
0x1400750ab  jz      short loc_1400750B0
0x1400750ad  lock inc dword ptr [rsi]
0x1400750b0  mov     [rbp+3Fh+var_58], rdi
0x1400750b4  mov     [rbp+3Fh+var_50], r12
0x1400750b8  test    rcx, rcx
0x1400750bb  jz      short loc_1400750C2
0x1400750bd  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1400750c2  lea     rdx, [rbp+3Fh+var_68]
0x1400750c6  lea     rcx, [rbp+3Fh+var_70]
0x1400750ca  call    ??$make_unique@UCleanupContext@UnionFs@@U12@$0A@@utl@@YA?AV?$unique_ptr@UCleanupContext@UnionFs@@U?$default_delete@UCleanupContext@UnionFs@@@utl@@@0@$$QEAUCleanupContext@UnionFs@@@Z; utl::make_unique<UnionFs::CleanupContext,UnionFs::CleanupContext,0>(UnionFs::CleanupContext &&)
0x1400750cf  lea     rcx, [rbp+3Fh+var_68]; this
0x1400750d3  call    ??1CleanupContext@UnionFs@@QEAA@XZ; UnionFs::CleanupContext::~CleanupContext(void)
0x1400750d8  mov     rax, [rbp+3Fh+var_70]
0x1400750dc  test    rax, rax
0x1400750df  jnz     short loc_140075155
0x1400750e1  lea     rax, aOriginAllocati_64; "ORIGIN: Allocating cleanup context"
0x1400750e8  mov     r8, 3100021203Ah; struct UnionFs::StackEventTracer *
0x1400750f2  lea     r9, aUnionfsUtilsPr_2; "UnionFs::Utils::PrepareForDeleteOnClean"...
0x1400750f9  mov     qword ptr [rsp+110h+FileInformationClass], rax; char *
0x1400750fe  mov     rdx, rbx; int
0x140075101  mov     ecx, 0C000009Ah; this
0x140075106  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14007510b  lea     rcx, [rsp+110h+var_D0]
0x140075110  call    wil__details__lambda_call__lambda_e6bdf39cdf6c17d197b59323a22c4106______lambda_call__lambda_e6bdf39cdf6c17d197b59323a22c4106___
0x140075115  lea     rcx, [rbp+3Fh+var_B0]; this
0x140075119  call    ??1LookupEntryResults@UnionFs@@QEAA@XZ; UnionFs::LookupEntryResults::~LookupEntryResults(void)
0x14007511e  mov     rcx, [rbp+3Fh+FileInformation]; FileNameInformation
0x140075122  mov     [rbp+3Fh+FileInformation], 0
0x14007512a  test    rcx, rcx
0x14007512d  jz      short loc_14007513B
0x14007512f  call    cs:__imp_FltReleaseFileNameInformation
0x140075136  nop     dword ptr [rax+rax+00h]
0x14007513b  mov     eax, 0C000009Ah
0x140075140  jmp     short loc_1400751C0
0x140075142  lea     rax, aOriginAllocati_53; "ORIGIN: Allocating CollapseContext"
0x140075149  mov     r8, 3520021202Dh
0x140075153  jmp     short loc_1400750F2
0x140075155  mov     rcx, [rbp+3Fh+arg_28]
0x140075159  mov     byte ptr [rsp+110h+var_C8], 0
0x14007515e  mov     rbx, [rcx]
0x140075161  mov     [rcx], rax
0x140075164  test    rbx, rbx
0x140075167  jz      short loc_14007518E
0x140075169  mov     rcx, rbx; this
0x14007516c  call    ??1CleanupContext@UnionFs@@QEAA@XZ; UnionFs::CleanupContext::~CleanupContext(void)
0x140075171  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140075178  mov     rdx, rbx; Entry
0x14007517b  add     rcx, 320h; Lookaside
0x140075182  call    cs:__imp_ExFreeToLookasideListEx
0x140075189  nop     dword ptr [rax+rax+00h]
0x14007518e  lea     rcx, [rsp+110h+var_D0]
0x140075193  call    wil__details__lambda_call__lambda_e6bdf39cdf6c17d197b59323a22c4106______lambda_call__lambda_e6bdf39cdf6c17d197b59323a22c4106___
0x140075198  lea     rcx, [rbp+3Fh+var_B0]; this
0x14007519c  call    ??1LookupEntryResults@UnionFs@@QEAA@XZ; UnionFs::LookupEntryResults::~LookupEntryResults(void)
0x1400751a1  mov     rcx, [rbp+3Fh+FileInformation]; FileNameInformation
0x1400751a5  mov     [rbp+3Fh+FileInformation], 0
0x1400751ad  test    rcx, rcx
0x1400751b0  jz      short loc_1400751BE
0x1400751b2  call    cs:__imp_FltReleaseFileNameInformation
0x1400751b9  nop     dword ptr [rax+rax+00h]
0x1400751be  xor     eax, eax
0x1400751c0  add     rsp, 0D8h
0x1400751c7  pop     r15
0x1400751c9  pop     r14
0x1400751cb  pop     r13
0x1400751cd  pop     r12
0x1400751cf  pop     rdi
0x1400751d0  pop     rsi
0x1400751d1  pop     rbx
0x1400751d2  pop     rbp
0x1400751d3  retn
```
