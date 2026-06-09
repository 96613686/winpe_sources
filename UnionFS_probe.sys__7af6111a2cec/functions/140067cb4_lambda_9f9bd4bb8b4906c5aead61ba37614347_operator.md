# _lambda_9f9bd4bb8b4906c5aead61ba37614347_::operator()

- ea: `0x140067cb4`
- end: `0x1400683c6`
- name: `_lambda_9f9bd4bb8b4906c5aead61ba37614347_::operator()`
- size: `1810`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14006c1fc`

## callees

- `0x140001008`
- `0x1400055d0`
- `0x140006168`
- `0x14000f7fc`
- `0x140011198`
- `0x14002349c`
- `0x14003ce70`
- `0x1400424ec`
- `0x1400430fc`
- `0x140043474`
- `0x140056a50`
- `0x140056afc`
- `0x140067cb4`
- `0x140075fd8`
- `0x140079a24`
- `0x140079da0`
- `0x14007af90`
- `0x14007b7d0`

## import_xrefs

- `ntoskrnl!ExReInitializeRundownProtectionCacheAware` at `0x14006806f`
- `ntoskrnl!ExReInitializeRundownProtectionCacheAware` at `0x14006806f`
- `ntoskrnl!KeResetEvent` at `0x140067e92`
- `ntoskrnl!KeResetEvent` at `0x140067e92`
- `ntoskrnl!PsGetHostSilo` at `0x140067ef1`
- `ntoskrnl!PsGetHostSilo` at `0x140067ef1`
- `ntoskrnl!ObfReferenceObject` at `0x1400681df`
- `ntoskrnl!ObfReferenceObject` at `0x1400681df`
- `ntoskrnl!KeSetEvent` at `0x140068087`
- `ntoskrnl!KeSetEvent` at `0x140068146`
- `ntoskrnl!KeSetEvent` at `0x140068087`
- `ntoskrnl!KeSetEvent` at `0x140068146`
- `ntoskrnl!ObfDereferenceObject` at `0x140067ffe`
- `ntoskrnl!ObfDereferenceObject` at `0x140068047`
- `ntoskrnl!ObfDereferenceObject` at `0x140068236`
- `ntoskrnl!ObfDereferenceObject` at `0x140067ffe`
- `ntoskrnl!ObfDereferenceObject` at `0x140068047`
- `ntoskrnl!ObfDereferenceObject` at `0x140068236`
- `ntoskrnl!ExRundownCompletedCacheAware` at `0x140067eb8`
- `ntoskrnl!ExRundownCompletedCacheAware` at `0x140067eb8`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x140067ea5`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x140067ea5`
- `ntoskrnl!ExReleaseResourceLite` at `0x140068161`
- `ntoskrnl!ExReleaseResourceLite` at `0x140068374`
- `ntoskrnl!ExReleaseResourceLite` at `0x140068161`
- `ntoskrnl!ExReleaseResourceLite` at `0x140068374`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006816d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140068380`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006816d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140068380`
- `FLTMGR!FltCreateFileEx2` at `0x140067fd4`
- `FLTMGR!FltCreateFileEx2` at `0x140067fd4`
- `FLTMGR!FltClose` at `0x14006805c`
- `FLTMGR!FltClose` at `0x14006805c`
- `FLTMGR!FltReferenceContext` at `0x140067e7b`
- `FLTMGR!FltReferenceContext` at `0x140067e7b`
- `FLTMGR!FltReleaseContext` at `0x14006809b`
- `FLTMGR!FltReleaseContext` at `0x14006809b`

## string_xrefs

- `0x140067dfa`: `PUSH: Cache lookup`
- `0x140067e01`: `UnionFs::Utils::CopyItemPriv::<lambda_9f9bd4bb8b4906c5aead61ba37614347>::operator ()`
- `0x140067e5b`: `UnionFs::Utils::CopyItemPriv::<lambda_9f9bd4bb8b4906c5aead61ba37614347>::operator ()`
- `0x1400680ed`: `UnionFs::Utils::CopyItemPriv::<lambda_9f9bd4bb8b4906c5aead61ba37614347>::operator ()`
- `0x140068257`: `UnionFs::Utils::CopyItemPriv::<lambda_9f9bd4bb8b4906c5aead61ba37614347>::operator ()`
- `0x1400682a1`: `UnionFs::Utils::CopyItemPriv::<lambda_9f9bd4bb8b4906c5aead61ba37614347>::operator ()`
- `0x1400682e9`: `UnionFs::Utils::CopyItemPriv::<lambda_9f9bd4bb8b4906c5aead61ba37614347>::operator ()`
- `0x140067dea`: `Failed to lookup cache entry for Soft tombstone.`
- `0x140068012`: `API: Opening scratch backing file`
- `0x1400682a8`: `Tombstone entry in CopyItem.`

## pseudocode

```c
void __fastcall lambda_9f9bd4bb8b4906c5aead61ba37614347_::operator()(__int64 a1)
{
  int v2; // r8d
  int v3; // r9d
  _BYTE *v4; // rax
  _BYTE **v5; // r14
  _QWORD *v6; // rdx
  struct _ERESOURCE *v7; // rbx
  __int64 v8; // r15
  volatile signed __int32 *v9; // r14
  _DWORD *v10; // rcx
  __int64 v11; // r9
  __int64 v12; // rcx
  int v13; // r15d
  __int64 v14; // r13
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 *v17; // rax
  __int64 HostSilo; // rax
  __int64 v19; // rax
  void *v20; // rcx
  _DWORD *v21; // rax
  int v22; // edx
  ULONG CreateOptions; // eax
  struct _FLT_INSTANCE *v24; // rdx
  NTSTATUS v25; // edi
  PVOID v26; // r8
  PVOID v27; // rcx
  int v28; // ecx
  __int64 v29; // rcx
  __int64 v30; // rcx
  struct _ERESOURCE **v31; // rax
  struct _ERESOURCE *v32; // rcx
  __int64 v33; // rax
  __int64 v34; // rcx
  __int64 v35; // rdi
  unsigned __int64 *v36; // rdx
  PVOID **v37; // rcx
  PVOID *v38; // r12
  struct _FLT_INSTANCE *v39; // rdi
  int v40; // edi
  int v41; // eax
  const char *v42; // rcx
  __int64 v43; // r8
  struct _FILE_OBJECT *v44; // rdx
  char *ObjectAttributes; // [rsp+28h] [rbp-D8h]
  const char *ObjectAttributesa; // [rsp+28h] [rbp-D8h]
  PVOID Object; // [rsp+80h] [rbp-80h] BYREF
  void *FileHandle; // [rsp+88h] [rbp-78h] BYREF
  FsFltWil::Details *v49; // [rsp+90h] [rbp-70h] BYREF
  _BYTE **v50; // [rsp+98h] [rbp-68h] BYREF
  PVOID v51; // [rsp+A0h] [rbp-60h] BYREF
  PVOID *p_Object; // [rsp+A8h] [rbp-58h] BYREF
  PFILE_OBJECT FileObject; // [rsp+B0h] [rbp-50h] BYREF
  char v54; // [rsp+B8h] [rbp-48h]
  char v55[16]; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v56; // [rsp+D0h] [rbp-30h]
  struct _ERESOURCE *v57; // [rsp+E0h] [rbp-20h]
  __int64 v58; // [rsp+E8h] [rbp-18h]
  __int128 v59; // [rsp+F0h] [rbp-10h]
  struct _IO_DRIVER_CREATE_CONTEXT DriverContext; // [rsp+100h] [rbp+0h] BYREF
  __int64 v61; // [rsp+120h] [rbp+20h]
  struct _OBJECT_ATTRIBUTES v62; // [rsp+128h] [rbp+28h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+158h] [rbp+58h] BYREF
  struct _FILE_OBJECT v64; // [rsp+168h] [rbp+68h] BYREF

  UnionFs::StackEventTracer::StackEventTracer((UnionFs::StackEventTracer *)&v64, 0x63500211BA1uLL);
  v4 = *(_BYTE **)a1;
  v5 = (_BYTE **)(a1 + 8);
  v50 = (_BYTE **)(a1 + 8);
  if ( *v4 )
  {
    v50 = (_BYTE **)(a1 + 8);
  }
  else if ( !**v5 )
  {
    goto LABEL_78;
  }
  v6 = *(_QWORD **)(a1 + 16);
  v7 = 0;
  v8 = v6[2];
  if ( v8 )
  {
    v9 = (volatile signed __int32 *)v6[3];
    if ( v9 )
      _InterlockedIncrement(v9 + 2);
    goto LABEL_25;
  }
  v10 = *(_DWORD **)(a1 + 24);
  if ( !**v5 || (v11 = 10, (*v10 & 0x20) != 0) )
    v11 = 2;
  if ( (*v10 & 1) == 0 )
    v11 = (unsigned int)v11 | 1;
  v57 = 0;
  *(_OWORD *)v55 = 0;
  v56 = 0;
  v59 = 0;
  v58 = 0;
  if ( *(_DWORD *)(*v6 + 28LL) == 2 )
    v12 = *(_QWORD *)(*(_QWORD *)(*v6 + 32LL) + 16LL);
  else
    v12 = *((_QWORD *)UnionFs::g_FilterState + 10);
  ObjectAttributes = v55;
  v13 = UnionFs::UfsPathCache::LookupEntryPriv(v12, *(_QWORD *)(a1 + 32), **(_QWORD **)(a1 + 40), v11, 0);
  if ( v13 >= 0 )
  {
    v8 = 0;
    v9 = 0;
    if ( *(_DWORD *)&v55[4] == 1 )
    {
      v9 = (volatile signed __int32 *)*((_QWORD *)&v56 + 1);
      v8 = v56;
      if ( *((_QWORD *)&v56 + 1) )
        _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v56 + 1) + 8LL));
      v7 = v57;
      v57 = 0;
    }
    UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)v55);
LABEL_25:
    if ( v8 )
    {
      if ( **(_BYTE **)a1 )
      {
        FltReferenceContext(*(PFLT_CONTEXT *)(v8 + 72));
        v14 = *(_QWORD *)(v8 + 72);
        KeResetEvent((PRKEVENT)(v14 + 136));
        ExWaitForRundownProtectionReleaseCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v14 + 128));
        ExRundownCompletedCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v14 + 128));
        v61 = 1;
        memset(&DriverContext, 0, sizeof(DriverContext));
        DriverContext.Size = 40;
        v17 = *(__int64 **)(*(_QWORD *)(a1 + 16) + 8LL);
        if ( v17 )
          HostSilo = *v17;
        else
          HostSilo = PsGetHostSilo(v16, v15);
        v61 = HostSilo;
        v19 = *(_QWORD *)(a1 + 16);
        memset(&v62, 0, sizeof(v62));
        v62.Length = 48;
        FileObject = 0;
        v20 = *(void **)(v19 + 40);
        v62.ObjectName = *(PUNICODE_STRING *)(a1 + 64);
        v21 = *(_DWORD **)(a1 + 72);
        v62.RootDirectory = v20;
        v62.Attributes = 576;
        *(_OWORD *)&v62.SecurityDescriptor = 0;
        LODWORD(v20) = *v21;
        v22 = *v21 & 0x204041;
        Object = 0;
        FileHandle = 0;
        p_Object = &Object;
        CreateOptions = v22 | 0x20;
        v54 = 1;
        if ( ((unsigned __int8)v20 & 1) == 0 )
          CreateOptions = v22;
        v24 = *(struct _FLT_INSTANCE **)(a1 + 32);
        IoStatusBlock = 0;
        v25 = FltCreateFileEx2(
                *(PFLT_FILTER *)UnionFs::g_FilterState,
                v24,
                &FileHandle,
                &FileObject,
                0xA0000000,
                &v62,
                &IoStatusBlock,
                0,
                0,
                7u,
                1u,
                CreateOptions,
                0,
                0,
                0x808u,
                &DriverContext);
        if ( v54 )
        {
          v26 = *p_Object;
          *p_Object = FileObject;
          if ( v26 )
            ObfDereferenceObject(v26);
        }
        if ( v25 >= 0 )
        {
          v35 = **(_QWORD **)(a1 + 16);
          FsFltWil::AcquirePushLockShared(&v49, v35 + 72);
          v37 = *(PVOID ***)(v35 + 48);
          v38 = v37[1];
          p_Object = *v37;
          FileObject = (PFILE_OBJECT)v38;
          if ( v38 )
            _InterlockedIncrement((volatile signed __int32 *)v38 + 2);
          if ( v49 )
            FsFltWil::Details::ReleasePushLockShared(v49, v36);
          v39 = *(struct _FLT_INSTANCE **)(a1 + 32);
          ObfReferenceObject(*(PVOID *)(v8 + 64));
          v51 = *(PVOID *)(v8 + 64);
          v49 = (FsFltWil::Details *)v51;
          v40 = UnionFs::Utils::ReplaceFileBacking(v14, v39, (int)&FileHandle, (int)&Object, &v64);
          if ( v51 )
            ObfDereferenceObject(v51);
          if ( v40 < 0 )
            UnionFs::ProcessTraceStatusPushLocation(
              (UnionFs *)(unsigned int)v40,
              (int)&v64,
              (struct UnionFs::StackEventTracer *)0x44800211C5ELL,
              (unsigned __int64)"UnionFs::Utils::CopyItemPriv::<lambda_9f9bd4bb8b4906c5aead61ba37614347>::operator ()",
              "PUSH: Replacing SFO backing",
              ObjectAttributes);
          if ( v38 )
            utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v38);
        }
        else
        {
          UnionFs::ProcessTraceStatusFromApi(
            (UnionFs *)(unsigned int)v25,
            (int)&v64,
            (struct UnionFs::StackEventTracer *)0x4B800211C48LL,
            (unsigned __int64)"UnionFs::Utils::CopyItemPriv::<lambda_9f9bd4bb8b4906c5aead61ba37614347>::operator ()",
            "API: Opening scratch backing file",
            ObjectAttributesa);
        }
        v27 = Object;
        Object = 0;
        if ( v27 )
          ObfDereferenceObject(v27);
        if ( FileHandle )
          FltClose(FileHandle);
        ExReInitializeRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v14 + 128));
        KeSetEvent((PRKEVENT)(v14 + 136), 0, 0);
        if ( v14 )
          FltReleaseContext((PFLT_CONTEXT)v14);
      }
      if ( **v50 )
      {
        v28 = **(_DWORD **)(a1 + 24);
        if ( (v28 & 0x20) == 0 )
        {
          if ( *(_WORD *)(v8 + 162) )
          {
            if ( (unsigned int)dword_14009E178 > 4 )
            {
              LODWORD(v50) = 7288;
              v51 = "onecore\\base\\fs\\unionfs\\sys\\unionfsproc.cpp";
              v49 = (FsFltWil::Details *)"UnionFs::Utils::CopyItemPriv::<lambda_9f9bd4bb8b4906c5aead61ba37614347>::operator ()";
              p_Object = (PVOID *)"Tombstone entry in CopyItem.";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                v28,
                (unsigned int)byte_14009A04D,
                v2,
                v3,
                (__int64)&p_Object,
                (__int64)&v49,
                (__int64)&v51,
                (__int64)&v50);
            }
            v41 = UnionFs::UfsPathCachePayload::RevertSoftTombstone(
                    (UnionFs::UfsPathCachePayload *)v8,
                    (struct UnionFs::StackEventTracer *)&v64);
            if ( v41 < 0 )
            {
              v42 = "PUSH: Reverting soft tombstone";
              v43 = 0x63700211C7FLL;
              v44 = &v64;
              goto LABEL_73;
            }
          }
          else
          {
            UnionFs::UfsPathCachePayload::InvalidateNoRevertSoftTombstone(v8, 0x60A00211C71LL);
            UnionFs::UfsPathCachePayload::RevertSoftTombstone((UnionFs::UfsPathCachePayload *)v8);
          }
        }
      }
    }
    v29 = **(_QWORD **)(a1 + 88);
    if ( !v29 )
      goto LABEL_74;
    if ( *(_BYTE *)(v29 + 8) )
      *(_BYTE *)(v29 + 8) = 0;
    *(_BYTE *)(*(_QWORD *)(v29 + 200) + 296LL) = 1;
    v30 = *((_QWORD *)UnionFs::g_FilterState + 16);
    if ( !_InterlockedExchangeAdd((volatile signed __int32 *)(v30 + 8), 1u) )
      KeSetEvent((PRKEVENT)(v30 + 16), 0, 0);
    v31 = *(struct _ERESOURCE ***)(a1 + 96);
    v32 = *v31;
    *v31 = 0;
    if ( v32 )
    {
      ExReleaseResourceLite(v32);
      KeLeaveCriticalRegion();
    }
    v33 = **(_QWORD **)(a1 + 16);
    v34 = *(_DWORD *)(v33 + 28) == 2
        ? *(_QWORD *)(*(_QWORD *)(v33 + 32) + 24LL)
        : *((_QWORD *)UnionFs::g_FilterState + 11);
    ObjectAttributes = 0;
    v41 = UnionFs::UfsEaTable::DeleteEaEntry(v34, *(_QWORD *)(a1 + 32), **(_QWORD **)(a1 + 40), *(_QWORD *)(a1 + 56), 0);
    if ( v41 >= 0 )
      goto LABEL_74;
    v44 = *(struct _FILE_OBJECT **)(a1 + 56);
    v42 = "PUSH: Deleting EA entries";
    v43 = 0x63D00211C91LL;
LABEL_73:
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v41,
      (int)v44,
      (struct UnionFs::StackEventTracer *)v43,
      (unsigned __int64)"UnionFs::Utils::CopyItemPriv::<lambda_9f9bd4bb8b4906c5aead61ba37614347>::operator ()",
      v42,
      ObjectAttributes);
LABEL_74:
    if ( v7 )
    {
      ExReleaseResourceLite(v7);
      KeLeaveCriticalRegion();
    }
    if ( v9 )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v9);
    goto LABEL_78;
  }
  if ( **v5 )
    MicrosoftTelemetryAssertTriggeredMsgKM("Failed to lookup cache entry for Soft tombstone.");
  UnionFs::ProcessTraceStatusPushLocation(
    (UnionFs *)(unsigned int)v13,
    *(_QWORD *)(a1 + 56),
    (struct UnionFs::StackEventTracer *)0x60900211BD6LL,
    (unsigned __int64)"UnionFs::Utils::CopyItemPriv::<lambda_9f9bd4bb8b4906c5aead61ba37614347>::operator ()",
    "PUSH: Cache lookup",
    v55);
  UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)v55);
LABEL_78:
  UnionFs::StackEventTracer::~StackEventTracer((UnionFs::StackEventTracer *)&v64);
}

```

## disassembly

```asm
0x140067cb4  push    rbp
0x140067cb6  push    rbx
0x140067cb7  push    rsi
0x140067cb8  push    rdi
0x140067cb9  push    r12
0x140067cbb  push    r13
0x140067cbd  push    r14
0x140067cbf  push    r15
0x140067cc1  lea     rbp, [rsp-368h]
0x140067cc9  sub     rsp, 468h
0x140067cd0  mov     rax, cs:__security_cookie
0x140067cd7  xor     rax, rsp
0x140067cda  mov     [rbp+3A0h+var_48], rax
0x140067ce1  mov     rsi, rcx
0x140067ce4  mov     rdx, 63500211BA1h; unsigned __int64
0x140067cee  lea     rcx, [rbp+3A0h+var_338]; this
0x140067cf2  call    ??0StackEventTracer@UnionFs@@QEAA@_K@Z; UnionFs::StackEventTracer::StackEventTracer(unsigned __int64)
0x140067cf7  mov     rax, [rsi]
0x140067cfa  lea     r14, [rsi+8]
0x140067cfe  xor     r13d, r13d
0x140067d01  mov     [rbp+3A0h+var_408], r14
0x140067d05  cmp     [rax], r13b
0x140067d08  jnz     short loc_140067D18
0x140067d0a  mov     rax, [r14]
0x140067d0d  cmp     [rax], r13b
0x140067d10  jz      loc_140068399
0x140067d16  jmp     short loc_140067D1C
0x140067d18  mov     [rbp+3A0h+var_408], r14
0x140067d1c  mov     rdx, [rsi+10h]
0x140067d20  mov     rbx, r13
0x140067d23  mov     edi, 1
0x140067d28  mov     r15, [rdx+10h]
0x140067d2c  test    r15, r15
0x140067d2f  jz      short loc_140067D48
0x140067d31  mov     r14, [rdx+18h]
0x140067d35  test    r14, r14
0x140067d38  jz      loc_140067E5B
0x140067d3e  lock inc dword ptr [r14+8]
0x140067d43  jmp     loc_140067E5B
0x140067d48  mov     rax, [r14]
0x140067d4b  mov     rcx, [rsi+18h]
0x140067d4f  cmp     [rax], r13b
0x140067d52  jz      short loc_140067D60
0x140067d54  mov     eax, [rcx]
0x140067d56  mov     r9d, 0Ah
0x140067d5c  test    al, 20h
0x140067d5e  jz      short loc_140067D66
0x140067d60  mov     r9d, 2
0x140067d66  mov     eax, [rcx]
0x140067d68  test    dil, al
0x140067d6b  jnz     short loc_140067D70
0x140067d6d  or      r9d, edi
0x140067d70  xorps   xmm0, xmm0
0x140067d73  mov     [rbp+3A0h+var_3C0], r13
0x140067d77  movdqa  xmmword ptr [rbp+3A0h+var_3E0], xmm0
0x140067d7c  xorps   xmm1, xmm1
0x140067d7f  movdqa  [rbp+3A0h+var_3D0], xmm1
0x140067d84  movdqa  [rbp+3A0h+var_3B0], xmm0
0x140067d89  mov     [rbp+3A0h+var_3B8], r13
0x140067d8d  mov     rax, [rdx]
0x140067d90  cmp     dword ptr [rax+1Ch], 2
0x140067d94  jnz     short loc_140067DA0
0x140067d96  mov     rax, [rax+20h]
0x140067d9a  mov     rcx, [rax+10h]
0x140067d9e  jmp     short loc_140067DAB
0x140067da0  mov     rax, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140067da7  mov     rcx, [rax+50h]
0x140067dab  mov     rax, [rsi+30h]
0x140067daf  mov     r8, [rsi+28h]
0x140067db3  mov     rdx, [rsi+20h]
0x140067db7  mov     [rsp+4A0h+AllocationSize], rax
0x140067dbc  lea     rax, [rbp+3A0h+var_338]
0x140067dc0  mov     [rsp+4A0h+IoStatusBlock], rax
0x140067dc5  lea     rax, [rbp+3A0h+var_3E0]
0x140067dc9  mov     r8, [r8]
0x140067dcc  mov     [rsp+4A0h+ObjectAttributes], rax; char *
0x140067dd1  mov     [rsp+4A0h+DesiredAccess], r13d
0x140067dd6  call    ?LookupEntryPriv@UfsPathCache@UnionFs@@AEAAJAEBU_FLT_INSTANCE@@AEBVUfsPathName@2@W4LookupEntryFlags@2@W4PrivateLookupEntryFlags@2@AEAULookupEntryResults@2@AEAVStackEventTracer@2@PEBU_FLT_CALLBACK_DATA@@@Z; UnionFs::UfsPathCache::LookupEntryPriv(_FLT_INSTANCE const &,UnionFs::UfsPathName const &,UnionFs::LookupEntryFlags,UnionFs::PrivateLookupEntryFlags,UnionFs::LookupEntryResults &,UnionFs::StackEventTracer &,_FLT_CALLBACK_DATA const *)
0x140067ddb  mov     r15d, eax
0x140067dde  test    eax, eax
0x140067de0  jns     short loc_140067E2D
0x140067de2  mov     rcx, [r14]
0x140067de5  cmp     [rcx], r13b
0x140067de8  jz      short loc_140067DF6
0x140067dea  lea     rcx, aFailedToLookup; "Failed to lookup cache entry for Soft t"...
0x140067df1  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140067df6  mov     rdx, [rsi+38h]; int
0x140067dfa  lea     rax, aPushCacheLooku; "PUSH: Cache lookup"
0x140067e01  lea     r9, aUnionfsUtilsCo_9; "UnionFs::Utils::CopyItemPriv::<lambda_9"...
0x140067e08  mov     qword ptr [rsp+4A0h+DesiredAccess], rax; char *
0x140067e0d  mov     r8, 60900211BD6h; struct UnionFs::StackEventTracer *
0x140067e17  mov     ecx, r15d; this
0x140067e1a  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140067e1f  lea     rcx, [rbp+3A0h+var_3E0]; this
0x140067e23  call    ??1LookupEntryResults@UnionFs@@QEAA@XZ; UnionFs::LookupEntryResults::~LookupEntryResults(void)
0x140067e28  jmp     loc_140068399
0x140067e2d  mov     r15, r13
0x140067e30  mov     r14, r13
0x140067e33  cmp     dword ptr [rbp+3A0h+var_3E0+4], edi
0x140067e36  jnz     short loc_140067E52
0x140067e38  mov     r14, qword ptr [rbp+3A0h+var_3D0+8]
0x140067e3c  mov     r15, qword ptr [rbp+3A0h+var_3D0]
0x140067e40  test    r14, r14
0x140067e43  jz      short loc_140067E4A
0x140067e45  lock inc dword ptr [r14+8]
0x140067e4a  mov     rbx, [rbp+3A0h+var_3C0]
0x140067e4e  mov     [rbp+3A0h+var_3C0], r13
0x140067e52  lea     rcx, [rbp+3A0h+var_3E0]; this
0x140067e56  call    ??1LookupEntryResults@UnionFs@@QEAA@XZ; UnionFs::LookupEntryResults::~LookupEntryResults(void)
0x140067e5b  lea     r12, aUnionfsUtilsCo_9; "UnionFs::Utils::CopyItemPriv::<lambda_9"...
0x140067e62  test    r15, r15
0x140067e65  jz      loc_1400680F9
0x140067e6b  mov     rax, [rsi]
0x140067e6e  cmp     [rax], r13b
0x140067e71  jz      loc_1400680AA
0x140067e77  mov     rcx, [r15+48h]; Context
0x140067e7b  call    cs:__imp_FltReferenceContext
0x140067e82  nop     dword ptr [rax+rax+00h]
0x140067e87  mov     r13, [r15+48h]
0x140067e8b  lea     rcx, [r13+88h]; Event
0x140067e92  call    cs:__imp_KeResetEvent
0x140067e99  nop     dword ptr [rax+rax+00h]
0x140067e9e  mov     rcx, [r13+80h]; RunRef
0x140067ea5  call    cs:__imp_ExWaitForRundownProtectionReleaseCacheAware
0x140067eac  nop     dword ptr [rax+rax+00h]
0x140067eb1  mov     rcx, [r13+80h]; RunRefCacheAware
0x140067eb8  call    cs:__imp_ExRundownCompletedCacheAware
0x140067ebf  nop     dword ptr [rax+rax+00h]
0x140067ec4  xorps   xmm0, xmm0
0x140067ec7  mov     [rbp+3A0h+var_380], rdi
0x140067ecb  mov     eax, 28h ; '('
0x140067ed0  xor     r8d, r8d
0x140067ed3  movups  xmmword ptr [rbp+3A0h+var_3A0.Size], xmm0
0x140067ed7  mov     [rbp+3A0h+var_3A0.Size], ax
0x140067edb  mov     rax, [rsi+10h]
0x140067edf  movups  xmmword ptr [rbp+3A0h+var_3A0.DeviceObjectHint], xmm0
0x140067ee3  mov     rax, [rax+8]
0x140067ee7  test    rax, rax
0x140067eea  jz      short loc_140067EF1
0x140067eec  mov     rax, [rax]
0x140067eef  jmp     short loc_140067F00
0x140067ef1  call    cs:__imp_PsGetHostSilo
0x140067ef8  nop     dword ptr [rax+rax+00h]
0x140067efd  xor     r8d, r8d
0x140067f00  mov     [rbp+3A0h+var_380], rax
0x140067f04  lea     r9, [rbp+3A0h+FileObject]; FileObject
0x140067f08  mov     rax, [rsi+10h]
0x140067f0c  xorps   xmm0, xmm0
0x140067f0f  movups  xmmword ptr [rbp+3A0h+var_378.Length], xmm0
0x140067f13  mov     [rbp+3A0h+var_378.Length], 30h ; '0'
0x140067f1a  movups  xmmword ptr [rbp+3A0h+var_378.ObjectName], xmm0
0x140067f1e  mov     [rbp+3A0h+FileObject], r8
0x140067f22  movups  xmmword ptr [rbp+3A0h+var_378.SecurityDescriptor], xmm0
0x140067f26  mov     rcx, [rax+28h]
0x140067f2a  mov     rax, [rsi+40h]
0x140067f2e  mov     [rbp+3A0h+var_378.ObjectName], rax
0x140067f32  mov     rax, [rsi+48h]
0x140067f36  mov     [rbp+3A0h+var_378.RootDirectory], rcx
0x140067f3a  mov     [rbp+3A0h+var_378.Attributes], 240h
0x140067f41  movdqu  xmmword ptr [rbp+3A0h+var_378.SecurityDescriptor], xmm0
0x140067f46  mov     ecx, [rax]
0x140067f48  mov     edx, ecx
0x140067f4a  and     edx, 204041h
0x140067f50  mov     [rbp+3A0h+Object], r8
0x140067f54  lea     rax, [rbp+3A0h+Object]
0x140067f58  mov     [rbp+3A0h+FileHandle], r8
0x140067f5c  mov     [rbp+3A0h+var_3F8], rax
0x140067f60  mov     eax, edx
0x140067f62  or      eax, 20h
0x140067f65  mov     [rbp+3A0h+var_3E8], dil
0x140067f69  test    dil, cl
0x140067f6c  lea     rcx, [rbp+3A0h+var_3A0]
0x140067f70  mov     [rsp+4A0h+DriverContext], rcx; DriverContext
0x140067f75  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140067f7c  cmovz   eax, edx
0x140067f7f  mov     rdx, [rsi+20h]; Instance
0x140067f83  mov     [rsp+4A0h+Flags], 808h; Flags
0x140067f8b  mov     [rsp+4A0h+EaLength], r8d; EaLength
0x140067f90  mov     [rsp+4A0h+EaBuffer], r8; EaBuffer
0x140067f95  mov     [rsp+4A0h+CreateOptions], eax; CreateOptions
0x140067f99  lea     rax, [rbp+3A0h+var_348]
0x140067f9d  mov     [rsp+4A0h+CreateDisposition], edi; CreateDisposition
0x140067fa1  mov     [rsp+4A0h+ShareAccess], 7; ShareAccess
0x140067fa9  mov     [rsp+4A0h+FileAttributes], r8d; FileAttributes
0x140067fae  mov     [rsp+4A0h+AllocationSize], r8; AllocationSize
0x140067fb3  lea     r8, [rbp+3A0h+FileHandle]; FileHandle
0x140067fb7  mov     [rsp+4A0h+IoStatusBlock], rax; IoStatusBlock
0x140067fbc  lea     rax, [rbp+3A0h+var_378]
0x140067fc0  movups  xmmword ptr [rbp+3A0h+var_348], xmm0
0x140067fc4  mov     rcx, [rcx]; Filter
0x140067fc7  mov     [rsp+4A0h+ObjectAttributes], rax; char *
0x140067fcc  mov     [rsp+4A0h+DesiredAccess], 0A0000000h; DesiredAccess
0x140067fd4  call    cs:__imp_FltCreateFileEx2
0x140067fdb  nop     dword ptr [rax+rax+00h]
0x140067fe0  cmp     [rbp+3A0h+var_3E8], 0
0x140067fe4  mov     edi, eax
0x140067fe6  jz      short loc_14006800A
0x140067fe8  mov     rdx, [rbp+3A0h+var_3F8]
0x140067fec  mov     rcx, [rbp+3A0h+FileObject]
0x140067ff0  mov     r8, [rdx]
0x140067ff3  mov     [rdx], rcx
0x140067ff6  test    r8, r8
0x140067ff9  jz      short loc_14006800A
0x140067ffb  mov     rcx, r8; Object
0x140067ffe  call    cs:__imp_ObfDereferenceObject
0x140068005  nop     dword ptr [rax+rax+00h]
0x14006800a  test    edi, edi
0x14006800c  jns     loc_140068197
0x140068012  lea     rax, aApiOpeningScra_0; "API: Opening scratch backing file"
0x140068019  mov     r9, r12; unsigned __int64
0x14006801c  mov     r8, 4B800211C48h; struct UnionFs::StackEventTracer *
0x140068026  mov     qword ptr [rsp+4A0h+DesiredAccess], rax; char *
0x14006802b  lea     rdx, [rbp+3A0h+var_338]; int
0x14006802f  mov     ecx, edi; this
0x140068031  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140068036  mov     rcx, [rbp+3A0h+Object]; Object
0x14006803a  mov     [rbp+3A0h+Object], 0
0x140068042  test    rcx, rcx
0x140068045  jz      short loc_140068053
0x140068047  call    cs:__imp_ObfDereferenceObject
0x14006804e  nop     dword ptr [rax+rax+00h]
0x140068053  mov     rcx, [rbp+3A0h+FileHandle]; FileHandle
0x140068057  test    rcx, rcx
0x14006805a  jz      short loc_140068068
0x14006805c  call    cs:__imp_FltClose
0x140068063  nop     dword ptr [rax+rax+00h]
0x140068068  mov     rcx, [r13+80h]; RunRefCacheAware
0x14006806f  call    cs:__imp_ExReInitializeRundownProtectionCacheAware
0x140068076  nop     dword ptr [rax+rax+00h]
0x14006807b  xor     r8d, r8d; Wait
0x14006807e  lea     rcx, [r13+88h]; Event
0x140068085  xor     edx, edx; Increment
0x140068087  call    cs:__imp_KeSetEvent
0x14006808e  nop     dword ptr [rax+rax+00h]
0x140068093  test    r13, r13
0x140068096  jz      short loc_1400680A7
0x140068098  mov     rcx, r13; Context
0x14006809b  call    cs:__imp_FltReleaseContext
0x1400680a2  nop     dword ptr [rax+rax+00h]
0x1400680a7  xor     r13d, r13d
0x1400680aa  mov     rax, [rbp+3A0h+var_408]
0x1400680ae  mov     rax, [rax]
0x1400680b1  cmp     [rax], r13b
0x1400680b4  jz      short loc_1400680ED
0x1400680b6  mov     rax, [rsi+18h]
0x1400680ba  mov     ecx, [rax]
0x1400680bc  test    cl, 20h
0x1400680bf  jnz     short loc_1400680ED
0x1400680c1  movzx   eax, word ptr [r15+0A2h]
0x1400680c9  nop
0x1400680ca  test    ax, ax
0x1400680cd  jnz     loc_140068284
0x1400680d3  mov     rdx, 60A00211C71h
0x1400680dd  mov     rcx, r15
0x1400680e0  call    ?InvalidateNoRevertSoftTombstone@UfsPathCachePayload@UnionFs@@AEAAXT_TAGGED_SOURCE@@@Z; UnionFs::UfsPathCachePayload::InvalidateNoRevertSoftTombstone(_TAGGED_SOURCE)
0x1400680e5  mov     rcx, r15; this
0x1400680e8  call    ?RevertSoftTombstone@UfsPathCachePayload@UnionFs@@AEAA_NXZ; UnionFs::UfsPathCachePayload::RevertSoftTombstone(void)
0x1400680ed  lea     r12, aUnionfsUtilsCo_9; "UnionFs::Utils::CopyItemPriv::<lambda_9"...
0x1400680f4  mov     edi, 1
0x1400680f9  mov     rax, [rsi+58h]
0x1400680fd  mov     rcx, [rax]
0x140068100  test    rcx, rcx
0x140068103  jz      loc_14006836C
0x140068109  mov     al, [rcx+8]
0x14006810c  nop
0x14006810d  test    al, al
0x14006810f  jz      short loc_140068116
0x140068111  nop
0x140068112  mov     [rcx+8], r13b
0x140068116  mov     rax, [rcx+0C8h]
0x14006811d  mov     [rax+128h], dil
0x140068124  mov     rax, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14006812b  mov     rcx, [rax+80h]
0x140068132  nop
0x140068133  lock xadd [rcx+8], edi
0x140068138  nop
0x140068139  test    edi, edi
0x14006813b  jnz     short loc_140068152
0x14006813d  add     rcx, 10h; Event
0x140068141  xor     r8d, r8d; Wait
0x140068144  xor     edx, edx; Increment
0x140068146  call    cs:__imp_KeSetEvent
0x14006814d  nop     dword ptr [rax+rax+00h]
0x140068152  mov     rax, [rsi+60h]
0x140068156  mov     rcx, [rax]; Resource
0x140068159  mov     [rax], r13
0x14006815c  test    rcx, rcx
0x14006815f  jz      short loc_140068179
0x140068161  call    cs:__imp_ExReleaseResourceLite
0x140068168  nop     dword ptr [rax+rax+00h]
0x14006816d  call    cs:__imp_KeLeaveCriticalRegion
0x140068174  nop     dword ptr [rax+rax+00h]
0x140068179  mov     rax, [rsi+10h]
0x14006817d  mov     rax, [rax]
0x140068180  cmp     dword ptr [rax+1Ch], 2
0x140068184  jnz     loc_14006831B
0x14006818a  mov     rax, [rax+20h]
0x14006818e  mov     rcx, [rax+18h]
0x140068192  jmp     loc_140068326
0x140068197  mov     rax, [rsi+10h]
  ... truncated ...
```
