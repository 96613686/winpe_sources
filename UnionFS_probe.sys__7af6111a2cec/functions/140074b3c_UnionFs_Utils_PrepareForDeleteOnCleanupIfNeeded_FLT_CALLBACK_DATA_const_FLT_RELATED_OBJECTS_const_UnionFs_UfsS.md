# UnionFs::Utils::PrepareForDeleteOnCleanupIfNeeded(_FLT_CALLBACK_DATA const &,_FLT_RELATED_OBJECTS const &,UnionFs::UfsStreamHandleCtx &,UnionFs::UfsFileCtx &,UnionFs::UfsUnionCtx &,utl::unique_ptr<UnionFs::CleanupContext,utl::default_delete<UnionFs::CleanupContext>> &,UnionFs::StackEventTracer &)

- ea: `0x140074b3c`
- end: `0x140074fd5`
- name: `?PrepareForDeleteOnCleanupIfNeeded@Utils@UnionFs@@YAJAEBU_FLT_CALLBACK_DATA@@AEBU_FLT_RELATED_OBJECTS@@AEAVUfsStreamHandleCtx@2@AEAVUfsFileCtx@2@AEAVUfsUnionCtx@2@AEAV?$unique_ptr@UCleanupContext@UnionFs@@U?$default_delete@UCleanupContext@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z`
- size: `1177`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, installer_update`

## callers

- `0x14002d630`
- `0x140057e88`

## callees

- `0x14000f7fc`
- `0x140011198`
- `0x14002b428`
- `0x14002bde4`
- `0x14003cd88`
- `0x1400567f4`
- `0x140056a50`
- `0x140056ac4`
- `0x140056afc`
- `0x140067b10`
- `0x14006e1a4`
- `0x14007059c`
- `0x140070840`
- `0x140074b3c`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x140074f82`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140074f82`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140074e20`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140074e20`
- `FLTMGR!FltSetInformationFile` at `0x140074bda`
- `FLTMGR!FltSetInformationFile` at `0x140074bda`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140074ca1`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140074d7d`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140074f2f`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140074fb2`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140074ca1`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140074d7d`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140074f2f`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140074fb2`
- `FLTMGR!FltReferenceContext` at `0x140074e80`
- `FLTMGR!FltReferenceContext` at `0x140074e80`

## string_xrefs

- `0x140074ba5`: `UnionFs::Utils::PrepareForDeleteOnCleanupIfNeeded`
- `0x140074c02`: `UnionFs::Utils::PrepareForDeleteOnCleanupIfNeeded`
- `0x140074c7e`: `UnionFs::Utils::PrepareForDeleteOnCleanupIfNeeded`
- `0x140074d49`: `UnionFs::Utils::PrepareForDeleteOnCleanupIfNeeded`
- `0x140074dc9`: `UnionFs::Utils::PrepareForDeleteOnCleanupIfNeeded`
- `0x140074ef2`: `UnionFs::Utils::PrepareForDeleteOnCleanupIfNeeded`
- `0x140074b94`: `PUSH: Failed to prepare delete-on-close handle for delete.`
- `0x140074d38`: `PUSH: Looking up cache entry`
- `0x140074bf8`: `API: Un-setting delete-on-close.`

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
        (struct UnionFs::StackEventTracer *)0x2FE00211F8ALL,
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
          (struct UnionFs::StackEventTracer *)0x30900211F9FLL,
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
      (struct UnionFs::StackEventTracer *)0x2DE00211FBELL,
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
      (struct UnionFs::StackEventTracer *)0x2FF00211FD2LL,
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
      (struct UnionFs::StackEventTracer *)0x2D400211FDFLL,
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
      v31 = 0x35200211FF7LL;
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
    wil::details::lambda_call__lambda_1e576416755fa744973a896da959b341___::_lambda_call__lambda_1e576416755fa744973a896da959b341___(&v38);
    UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)&v41);
    v34 = FileInformation;
    FileInformation = 0;
    if ( v34 )
      FltReleaseFileNameInformation(v34);
    return 0;
  }
  v30 = "ORIGIN: Allocating cleanup context";
  v31 = 0x31000212004LL;
LABEL_38:
  UnionFs::ProcessTraceStatusOrigin(
    (UnionFs *)0xC000009ALL,
    (int)v7,
    (struct UnionFs::StackEventTracer *)v31,
    (unsigned __int64)"UnionFs::Utils::PrepareForDeleteOnCleanupIfNeeded",
    v30,
    v37);
  wil::details::lambda_call__lambda_1e576416755fa744973a896da959b341___::_lambda_call__lambda_1e576416755fa744973a896da959b341___(&v38);
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
0x140074b3c  push    rbp
0x140074b3e  push    rbx
0x140074b3f  push    rsi
0x140074b40  push    rdi
0x140074b41  push    r12
0x140074b43  push    r13
0x140074b45  push    r14
0x140074b47  push    r15
0x140074b49  lea     rbp, [rsp-7]
0x140074b4e  sub     rsp, 0D8h
0x140074b55  mov     eax, [r8]
0x140074b58  xor     r13d, r13d
0x140074b5b  mov     rbx, [rbp+3Fh+arg_30]
0x140074b5f  mov     r14, r9
0x140074b62  mov     r12, r8
0x140074b65  mov     r15, rdx
0x140074b68  mov     rsi, rcx
0x140074b6b  test    al, 4
0x140074b6d  jz      loc_140074C31
0x140074b73  mov     al, [r9+38h]
0x140074b77  nop
0x140074b78  test    al, al
0x140074b7a  jnz     loc_140074C31
0x140074b80  mov     qword ptr [rsp+110h+FileInformationClass], rbx; struct UnionFs::UfsFileCtx *
0x140074b85  call    ?MarkFileAsDeleteCandidateIfInLayer@Utils@UnionFs@@YAJAEBU_FLT_CALLBACK_DATA@@AEBU_FLT_RELATED_OBJECTS@@AEBVUfsStreamHandleCtx@2@AEAVUfsFileCtx@2@AEAVStackEventTracer@2@@Z; UnionFs::Utils::MarkFileAsDeleteCandidateIfInLayer(_FLT_CALLBACK_DATA const &,_FLT_RELATED_OBJECTS const &,UnionFs::UfsStreamHandleCtx const &,UnionFs::UfsFileCtx &,UnionFs::StackEventTracer &)
0x140074b8a  mov     edi, eax
0x140074b8c  test    eax, eax
0x140074b8e  jns     loc_140074C31
0x140074b94  lea     rax, aPushFailedToPr; "PUSH: Failed to prepare delete-on-close"...
0x140074b9b  mov     r8, 2FE00211F8Ah; struct UnionFs::StackEventTracer *
0x140074ba5  lea     r9, aUnionfsUtilsPr_2; "UnionFs::Utils::PrepareForDeleteOnClean"...
0x140074bac  mov     qword ptr [rsp+110h+FileInformationClass], rax; char *
0x140074bb1  mov     rdx, rbx; int
0x140074bb4  mov     ecx, edi; this
0x140074bb6  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140074bbb  mov     rdx, [r15+20h]; FileObject
0x140074bbf  lea     esi, [r13+8]
0x140074bc3  mov     rcx, [r15+18h]; Instance
0x140074bc7  lea     r9d, [r13+4]; Length
0x140074bcb  lea     r8, [rbp+3Fh+FileInformation]; FileInformation
0x140074bcf  mov     dword ptr [rbp+3Fh+FileInformation], esi
0x140074bd2  mov     [rsp+110h+FileInformationClass], 40h ; '@'; FileInformationClass
0x140074bda  call    cs:__imp_FltSetInformationFile
0x140074be1  nop     dword ptr [rax+rax+00h]
0x140074be6  mov     esi, eax
0x140074be8  test    eax, eax
0x140074bea  jns     loc_140074CAD
0x140074bf0  mov     rcx, rbx; this
0x140074bf3  call    ?LogError@StackEventTracer@UnionFs@@AEAAXXZ; UnionFs::StackEventTracer::LogError(void)
0x140074bf8  lea     rax, aApiUnSettingDe; "API: Un-setting delete-on-close."
0x140074bff  mov     [rbx], r13d
0x140074c02  lea     r9, aUnionfsUtilsPr_2; "UnionFs::Utils::PrepareForDeleteOnClean"...
0x140074c09  mov     qword ptr [rsp+110h+FileInformationClass], rax; char *
0x140074c0e  mov     r8, 30900211F9Fh; struct UnionFs::StackEventTracer *
0x140074c18  mov     [rbx+224h], r13w
0x140074c20  mov     rdx, rbx; int
0x140074c23  mov     ecx, esi; this
0x140074c25  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140074c2a  mov     eax, esi
0x140074c2c  jmp     loc_140074FC0
0x140074c31  mov     al, [r14+38h]
0x140074c35  nop
0x140074c36  test    al, al
0x140074c38  jz      loc_140074FBE
0x140074c3e  mov     r9, rbx
0x140074c41  mov     [rbp+3Fh+FileInformation], r13
0x140074c45  lea     r8, [rbp+3Fh+FileInformation]
0x140074c49  mov     [rsp+110h+var_D0], rsi
0x140074c4e  mov     edx, 1000401h
0x140074c53  mov     [rsp+110h+var_C8], r13
0x140074c58  lea     rcx, [rsp+110h+var_D0]
0x140074c5d  mov     [rsp+110h+var_C0], r13
0x140074c62  call    ?GetFileNameInformation@Utils@UnionFs@@YAJUNameInfoParams@12@KAEAV?$unique_ptr@U_FLT_FILE_NAME_INFORMATION@@U?$function_deleter@P6AXPEAU_FLT_FILE_NAME_INFORMATION@@@Z$1?FltReleaseFileNameInformation@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@@Z; UnionFs::Utils::GetFileNameInformation(UnionFs::Utils::NameInfoParams,ulong,wistd::unique_ptr<_FLT_FILE_NAME_INFORMATION,wil::function_deleter<void (*)(_FLT_FILE_NAME_INFORMATION *),&FltReleaseFileNameInformation(_FLT_FILE_NAME_INFORMATION *)>> &,UnionFs::StackEventTracer &)
0x140074c67  mov     edi, eax
0x140074c69  test    eax, eax
0x140074c6b  jns     short loc_140074CB4
0x140074c6d  lea     rax, aPushLookingUpN; "PUSH: Looking up name"
0x140074c74  mov     r8, 2DE00211FBEh; struct UnionFs::StackEventTracer *
0x140074c7e  lea     r9, aUnionfsUtilsPr_2; "UnionFs::Utils::PrepareForDeleteOnClean"...
0x140074c85  mov     qword ptr [rsp+110h+FileInformationClass], rax; char *
0x140074c8a  mov     rdx, rbx; int
0x140074c8d  mov     ecx, edi; this
0x140074c8f  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140074c94  mov     rcx, [rbp+3Fh+FileInformation]; FileNameInformation
0x140074c98  mov     [rbp+3Fh+FileInformation], r13
0x140074c9c  test    rcx, rcx
0x140074c9f  jz      short loc_140074CAD
0x140074ca1  call    cs:__imp_FltReleaseFileNameInformation
0x140074ca8  nop     dword ptr [rax+rax+00h]
0x140074cad  mov     eax, edi
0x140074caf  jmp     loc_140074FC0
0x140074cb4  mov     rdi, [rbp+3Fh+arg_20]
0x140074cb8  cmp     dword ptr [rdi+1Ch], 2
0x140074cbc  jnz     short loc_140074CC8
0x140074cbe  mov     rax, [rdi+20h]
0x140074cc2  mov     r13, [rax+10h]
0x140074cc6  jmp     short loc_140074CD3
0x140074cc8  mov     rax, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140074ccf  mov     r13, [rax+50h]
0x140074cd3  mov     rax, [r15+20h]
0x140074cd7  xorps   xmm0, xmm0
0x140074cda  mov     r8, [rbp+3Fh+FileInformation]
0x140074cde  xorps   xmm1, xmm1
0x140074ce1  mov     rdx, [r15+18h]
0x140074ce5  mov     rcx, r13
0x140074ce8  mov     [rsp+110h+var_E0], rsi
0x140074ced  mov     r9d, [rax+50h]
0x140074cf1  lea     rax, [rbp+3Fh+var_B0]
0x140074cf5  shr     r9d, 11h
0x140074cf9  not     r9d
0x140074cfc  mov     [rsp+110h+var_E8], rbx; char *
0x140074d01  and     r9d, 1
0x140074d05  movdqa  [rbp+3Fh+var_B0], xmm0
0x140074d0a  or      r9d, 2
0x140074d0e  movdqa  xmmword ptr [rbp+3Fh+var_A0], xmm1
0x140074d13  mov     [rbp+3Fh+var_90], 0
0x140074d1b  mov     [rbp+3Fh+var_88], 0
0x140074d23  movdqa  [rbp+3Fh+var_80], xmm0
0x140074d28  mov     qword ptr [rsp+110h+FileInformationClass], rax
0x140074d2d  call    ?LookupEntry@UfsPathCache@UnionFs@@QEAAJAEBU_FLT_INSTANCE@@AEAU_FLT_FILE_NAME_INFORMATION@@W4LookupEntryFlags@2@AEAULookupEntryResults@2@AEAVStackEventTracer@2@PEBU_FLT_CALLBACK_DATA@@@Z; UnionFs::UfsPathCache::LookupEntry(_FLT_INSTANCE const &,_FLT_FILE_NAME_INFORMATION &,UnionFs::LookupEntryFlags,UnionFs::LookupEntryResults &,UnionFs::StackEventTracer &,_FLT_CALLBACK_DATA const *)
0x140074d32  mov     esi, eax
0x140074d34  test    eax, eax
0x140074d36  jns     short loc_140074D8E
0x140074d38  lea     rax, aPushLookingUpC; "PUSH: Looking up cache entry"
0x140074d3f  mov     r8, 2FF00211FD2h; struct UnionFs::StackEventTracer *
0x140074d49  lea     r9, aUnionfsUtilsPr_2; "UnionFs::Utils::PrepareForDeleteOnClean"...
0x140074d50  mov     qword ptr [rsp+110h+FileInformationClass], rax; char *
0x140074d55  mov     rdx, rbx; int
0x140074d58  mov     ecx, esi; this
0x140074d5a  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140074d5f  lea     rcx, [rbp+3Fh+var_B0]; this
0x140074d63  call    ??1LookupEntryResults@UnionFs@@QEAA@XZ; UnionFs::LookupEntryResults::~LookupEntryResults(void)
0x140074d68  mov     rcx, [rbp+3Fh+FileInformation]; FileNameInformation
0x140074d6c  mov     [rbp+3Fh+FileInformation], 0
0x140074d74  test    rcx, rcx
0x140074d77  jz      loc_140074C2A
0x140074d7d  call    cs:__imp_FltReleaseFileNameInformation
0x140074d84  nop     dword ptr [rax+rax+00h]
0x140074d89  jmp     loc_140074C2A
0x140074d8e  mov     r8, [rbp+3Fh+FileInformation]; int
0x140074d92  lea     rax, [rbp+3Fh+var_A0]
0x140074d96  mov     rcx, [r15+18h]; int
0x140074d9a  mov     r9d, 6; int
0x140074da0  mov     [rsp+110h+var_E8], rbx; char *
0x140074da5  mov     rdx, rdi; int
0x140074da8  mov     qword ptr [rsp+110h+FileInformationClass], rax; __int64
0x140074dad  call    ?MarkFileAsSoftTombstone@Utils@UnionFs@@YAJAEBU_FLT_INSTANCE@@AEAVUfsUnionCtx@2@AEAU_FLT_FILE_NAME_INFORMATION@@W4SoftTombstoneReason@2@AEAV?$shared_ptr@VUfsPathCachePayload@UnionFs@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::Utils::MarkFileAsSoftTombstone(_FLT_INSTANCE const &,UnionFs::UfsUnionCtx &,_FLT_FILE_NAME_INFORMATION &,UnionFs::SoftTombstoneReason,utl::shared_ptr<UnionFs::UfsPathCachePayload> &,UnionFs::StackEventTracer &)
0x140074db2  mov     edi, eax
0x140074db4  test    eax, eax
0x140074db6  jns     short loc_140074DF9
0x140074db8  lea     rax, aPushCouldNotPl; "PUSH: Could not place soft tombstone"
0x140074dbf  mov     r8, 2D400211FDFh; struct UnionFs::StackEventTracer *
0x140074dc9  lea     r9, aUnionfsUtilsPr_2; "UnionFs::Utils::PrepareForDeleteOnClean"...
0x140074dd0  mov     qword ptr [rsp+110h+FileInformationClass], rax; char *
0x140074dd5  mov     rdx, rbx; int
0x140074dd8  mov     ecx, edi; this
0x140074dda  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140074ddf  lea     rcx, [rbp+3Fh+var_B0]; this
0x140074de3  call    ??1LookupEntryResults@UnionFs@@QEAA@XZ; UnionFs::LookupEntryResults::~LookupEntryResults(void)
0x140074de8  mov     rcx, [rbp+3Fh+FileInformation]
0x140074dec  mov     [rbp+3Fh+FileInformation], 0
0x140074df4  jmp     loc_140074C9C
0x140074df9  xor     edi, edi
0x140074dfb  mov     byte ptr [rsp+110h+var_C8], 1
0x140074e00  lea     rax, [rbp+3Fh+var_B0]
0x140074e04  mov     [rsp+110h+var_D0], rax
0x140074e09  lea     esi, [rdi+8]
0x140074e0c  cmp     [r14+60h], dil
0x140074e10  jz      short loc_140074E7D
0x140074e12  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140074e19  add     rcx, 440h; Lookaside
0x140074e20  call    cs:__imp_ExAllocateFromLookasideListEx
0x140074e27  nop     dword ptr [rax+rax+00h]
0x140074e2c  mov     rdi, rax
0x140074e2f  test    rax, rax
0x140074e32  jz      loc_140074F42
0x140074e38  mov     rcx, [rbp+3Fh+var_A0+8]; this
0x140074e3c  mov     r8, [rbp+3Fh+var_A0]
0x140074e40  test    rcx, rcx
0x140074e43  jz      short loc_140074E4E
0x140074e45  lea     rdx, [rcx+8]
0x140074e49  lock inc dword ptr [rdx]
0x140074e4c  jmp     short loc_140074E51
0x140074e4e  mov     rdx, rsi
0x140074e51  mov     rax, [r15+18h]
0x140074e55  mov     [rdi], rax
0x140074e58  mov     [rdi+8], r13
0x140074e5c  mov     [rdi+10h], r8
0x140074e60  mov     [rdi+18h], rcx
0x140074e64  test    rcx, rcx
0x140074e67  jz      short loc_140074E6C
0x140074e69  lock inc dword ptr [rdx]
0x140074e6c  xorps   xmm0, xmm0
0x140074e6f  movups  xmmword ptr [rdi+20h], xmm0
0x140074e73  test    rcx, rcx
0x140074e76  jz      short loc_140074E7D
0x140074e78  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140074e7d  mov     rcx, r12; Context
0x140074e80  call    cs:__imp_FltReferenceContext
0x140074e87  nop     dword ptr [rax+rax+00h]
0x140074e8c  mov     rcx, [rbp+3Fh+var_A0+8]; this
0x140074e90  mov     rax, [rbp+3Fh+var_A0]
0x140074e94  test    rcx, rcx
0x140074e97  jz      short loc_140074EA0
0x140074e99  lea     rsi, [rcx+8]
0x140074e9d  lock inc dword ptr [rsi]
0x140074ea0  mov     [rbp+3Fh+var_68], rax
0x140074ea4  mov     [rbp+3Fh+var_60], rcx
0x140074ea8  test    rcx, rcx
0x140074eab  jz      short loc_140074EB0
0x140074ead  lock inc dword ptr [rsi]
0x140074eb0  mov     [rbp+3Fh+var_58], rdi
0x140074eb4  mov     [rbp+3Fh+var_50], r12
0x140074eb8  test    rcx, rcx
0x140074ebb  jz      short loc_140074EC2
0x140074ebd  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140074ec2  lea     rdx, [rbp+3Fh+var_68]
0x140074ec6  lea     rcx, [rbp+3Fh+var_70]
0x140074eca  call    ??$make_unique@UCleanupContext@UnionFs@@U12@$0A@@utl@@YA?AV?$unique_ptr@UCleanupContext@UnionFs@@U?$default_delete@UCleanupContext@UnionFs@@@utl@@@0@$$QEAUCleanupContext@UnionFs@@@Z; utl::make_unique<UnionFs::CleanupContext,UnionFs::CleanupContext,0>(UnionFs::CleanupContext &&)
0x140074ecf  lea     rcx, [rbp+3Fh+var_68]; this
0x140074ed3  call    ??1CleanupContext@UnionFs@@QEAA@XZ; UnionFs::CleanupContext::~CleanupContext(void)
0x140074ed8  mov     rax, [rbp+3Fh+var_70]
0x140074edc  test    rax, rax
0x140074edf  jnz     short loc_140074F55
0x140074ee1  lea     rax, aOriginAllocati_63; "ORIGIN: Allocating cleanup context"
0x140074ee8  mov     r8, 31000212004h; struct UnionFs::StackEventTracer *
0x140074ef2  lea     r9, aUnionfsUtilsPr_2; "UnionFs::Utils::PrepareForDeleteOnClean"...
0x140074ef9  mov     qword ptr [rsp+110h+FileInformationClass], rax; char *
0x140074efe  mov     rdx, rbx; int
0x140074f01  mov     ecx, 0C000009Ah; this
0x140074f06  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140074f0b  lea     rcx, [rsp+110h+var_D0]
0x140074f10  call    wil__details__lambda_call__lambda_1e576416755fa744973a896da959b341______lambda_call__lambda_1e576416755fa744973a896da959b341___
0x140074f15  lea     rcx, [rbp+3Fh+var_B0]; this
0x140074f19  call    ??1LookupEntryResults@UnionFs@@QEAA@XZ; UnionFs::LookupEntryResults::~LookupEntryResults(void)
0x140074f1e  mov     rcx, [rbp+3Fh+FileInformation]; FileNameInformation
0x140074f22  mov     [rbp+3Fh+FileInformation], 0
0x140074f2a  test    rcx, rcx
0x140074f2d  jz      short loc_140074F3B
0x140074f2f  call    cs:__imp_FltReleaseFileNameInformation
0x140074f36  nop     dword ptr [rax+rax+00h]
0x140074f3b  mov     eax, 0C000009Ah
0x140074f40  jmp     short loc_140074FC0
0x140074f42  lea     rax, aOriginAllocati_52; "ORIGIN: Allocating CollapseContext"
0x140074f49  mov     r8, 35200211FF7h
0x140074f53  jmp     short loc_140074EF2
0x140074f55  mov     rcx, [rbp+3Fh+arg_28]
0x140074f59  mov     byte ptr [rsp+110h+var_C8], 0
0x140074f5e  mov     rbx, [rcx]
0x140074f61  mov     [rcx], rax
0x140074f64  test    rbx, rbx
0x140074f67  jz      short loc_140074F8E
0x140074f69  mov     rcx, rbx; this
0x140074f6c  call    ??1CleanupContext@UnionFs@@QEAA@XZ; UnionFs::CleanupContext::~CleanupContext(void)
0x140074f71  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140074f78  mov     rdx, rbx; Entry
0x140074f7b  add     rcx, 320h; Lookaside
0x140074f82  call    cs:__imp_ExFreeToLookasideListEx
0x140074f89  nop     dword ptr [rax+rax+00h]
0x140074f8e  lea     rcx, [rsp+110h+var_D0]
0x140074f93  call    wil__details__lambda_call__lambda_1e576416755fa744973a896da959b341______lambda_call__lambda_1e576416755fa744973a896da959b341___
0x140074f98  lea     rcx, [rbp+3Fh+var_B0]; this
0x140074f9c  call    ??1LookupEntryResults@UnionFs@@QEAA@XZ; UnionFs::LookupEntryResults::~LookupEntryResults(void)
0x140074fa1  mov     rcx, [rbp+3Fh+FileInformation]; FileNameInformation
0x140074fa5  mov     [rbp+3Fh+FileInformation], 0
0x140074fad  test    rcx, rcx
0x140074fb0  jz      short loc_140074FBE
0x140074fb2  call    cs:__imp_FltReleaseFileNameInformation
0x140074fb9  nop     dword ptr [rax+rax+00h]
0x140074fbe  xor     eax, eax
0x140074fc0  add     rsp, 0D8h
0x140074fc7  pop     r15
0x140074fc9  pop     r14
0x140074fcb  pop     r13
0x140074fcd  pop     r12
0x140074fcf  pop     rdi
0x140074fd0  pop     rsi
0x140074fd1  pop     rbx
0x140074fd2  pop     rbp
0x140074fd3  retn
```
