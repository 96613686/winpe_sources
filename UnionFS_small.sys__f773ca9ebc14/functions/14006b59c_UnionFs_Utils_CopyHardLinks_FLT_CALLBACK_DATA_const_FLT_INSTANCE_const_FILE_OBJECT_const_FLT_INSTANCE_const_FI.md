# UnionFs::Utils::CopyHardLinks(_FLT_CALLBACK_DATA const &,_FLT_INSTANCE const &,_FILE_OBJECT const &,_FLT_INSTANCE const &,_FILE_OBJECT const &,UnionFs::UfsUnionCtx const &,UnionFs::Utils::CopyItemFlags,bool,UnionFs::StackEventTracer &)

- ea: `0x14006b59c`
- end: `0x14006bca2`
- name: `?CopyHardLinks@Utils@UnionFs@@YAJAEBU_FLT_CALLBACK_DATA@@AEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@12AEBVUfsUnionCtx@2@W4CopyItemFlags@12@_NAEAVStackEventTracer@2@@Z`
- size: `1798`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, reparse_path, loader_planting, installer_update`

## callers

- `0x14006c1fc`

## callees

- `0x14001c780`
- `0x14003cccc`
- `0x140046510`
- `0x140056a50`
- `0x140056ac4`
- `0x140056afc`
- `0x140061f2c`
- `0x140067664`
- `0x140067a38`
- `0x1400683cc`
- `0x14006b59c`
- `0x14006e35c`
- `0x140079a6c`
- `0x14007b900`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14006b64b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006b6ee`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006b83e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006b8b9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006b8fc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006b92b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006b959`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006b98c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006b9ed`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006ba1b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006ba4e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006bb69`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006bb97`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006bbca`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006bc18`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006bc45`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006bc77`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006b64b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006b6ee`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006b83e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006b8b9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006b8fc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006b92b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006b959`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006b98c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006b9ed`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006ba1b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006ba4e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006bb69`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006bb97`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006bbca`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006bc18`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006bc45`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006bc77`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006bb06`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006bbe7`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006bb06`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006bbe7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006bb12`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006bbf3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006bb12`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006bbf3`
- `FLTMGR!FltSetInformationFile` at `0x14006b7aa`
- `FLTMGR!FltSetInformationFile` at `0x14006b7aa`

## string_xrefs

- `0x14006b5fe`: `PUSH: Getting hard link paths`
- `0x14006bae6`: `UnionFs::UfsEaTable::DeleteEaEntryWithMultipleNames`
- `0x14006b881`: `ORIGIN: Pushing link name`
- `0x14006b60f`: `UnionFs::Utils::CopyHardLinks`
- `0x14006b6aa`: `UnionFs::Utils::CopyHardLinks`
- `0x14006b868`: `UnionFs::Utils::CopyHardLinks`
- `0x14006b892`: `UnionFs::Utils::CopyHardLinks`
- `0x14006b8db`: `UnionFs::Utils::CopyHardLinks`
- `0x14006b9b1`: `UnionFs::Utils::CopyHardLinks`
- `0x14006bb2f`: `UnionFs::Utils::CopyHardLinks`
- `0x14006b9a0`: `ORIGIN: Allocating file link buffer`
- `0x14006b699`: `PUSH: Removing link names`
- `0x14006b857`: `PUSH: Path invalidation`
- `0x14006b8ca`: `API: Setting hard link`

## pseudocode

```c
__int64 __fastcall UnionFs::Utils::CopyHardLinks(
        struct _FLT_CALLBACK_DATA *a1,
        struct _FLT_INSTANCE *a2,
        struct _FILE_OBJECT *a3,
        const struct _FLT_INSTANCE *a4,
        struct _FILE_OBJECT *FileObject,
        __int64 a6,
        char a7,
        char a8,
        struct UnionFs::StackEventTracer *a9)
{
  __m128i si128; // xmm6
  struct _FLT_INSTANCE *v11; // r12
  int HardLinkPaths; // edi
  __int64 v14; // rcx
  PVOID v15; // rbx
  PVOID v17; // rbx
  _BYTE *v18; // rsi
  _BYTE *v19; // rbx
  const struct UnionFs::UfsPathName **v20; // rdi
  _QWORD *v21; // r15
  NTSTATUS v22; // r12d
  UnionFs::UfsPathCache *v23; // rcx
  PVOID v24; // rcx
  PVOID v25; // rbx
  PVOID v26; // rcx
  PVOID v27; // rbx
  UnionFs::UfsPathTable *v28; // r13
  const char **i; // rdi
  unsigned int v30; // r15d
  PVOID v31; // rcx
  PVOID v32; // rbx
  PVOID v33; // rcx
  PVOID v34; // rbx
  char *v35; // [rsp+30h] [rbp-99h]
  char *v36; // [rsp+30h] [rbp-99h]
  char *v37; // [rsp+30h] [rbp-99h]
  char *v38; // [rsp+30h] [rbp-99h]
  PVOID v39[2]; // [rsp+48h] [rbp-81h] BYREF
  __int64 v40; // [rsp+58h] [rbp-71h]
  PVOID P[2]; // [rsp+60h] [rbp-69h] BYREF
  __int64 v42; // [rsp+70h] [rbp-59h]
  PVOID FileInformation; // [rsp+78h] [rbp-51h] BYREF
  _QWORD v44[2]; // [rsp+80h] [rbp-49h] BYREF
  char v45; // [rsp+90h] [rbp-39h]
  PVOID v46[2]; // [rsp+98h] [rbp-31h] BYREF
  __int64 v47; // [rsp+A8h] [rbp-21h]
  _QWORD v48[11]; // [rsp+B0h] [rbp-19h] BYREF

  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v11 = a4;
  v42 = -1;
  *(__m128i *)P = si128;
  HardLinkPaths = UnionFs::Utils::GetHardLinkPaths(a2, a3, (struct _FILE_OBJECT *)P, a9);
  if ( HardLinkPaths < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)HardLinkPaths,
      (int)a9,
      (struct UnionFs::StackEventTracer *)0x64300211E10LL,
      (unsigned __int64)"UnionFs::Utils::CopyHardLinks",
      "PUSH: Getting hard link paths",
      v35);
LABEL_3:
    v15 = P[0];
    if ( P[0] != (PVOID)-1LL )
    {
      utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>>(
        v14,
        P[0],
        ((char *)P[1] - (char *)P[0]) >> 3);
      if ( v15 )
        ExFreePoolWithTag(v15, 0);
    }
    return (unsigned int)HardLinkPaths;
  }
  v47 = -1;
  *(__m128i *)v46 = si128;
  HardLinkPaths = UnionFs::UfsUnionCtx::MapHardLinkNamesAndPrepareScratch(
                    (UnionFs::UfsUnionCtx *)a6,
                    a1,
                    v11,
                    (__int64)a3,
                    (__int64)P,
                    (__int64 *)v46,
                    a9);
  if ( HardLinkPaths < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)HardLinkPaths,
      (int)a9,
      (struct UnionFs::StackEventTracer *)0x3A500211E1FLL,
      (unsigned __int64)"UnionFs::Utils::CopyHardLinks",
      "PUSH: Removing link names",
      v36);
    v17 = v46[0];
    if ( v46[0] != (PVOID)-1LL )
    {
      utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>>(
        v14,
        v46[0],
        ((char *)v46[1] - (char *)v46[0]) >> 3);
      if ( v17 )
        ExFreePoolWithTag(v17, 0);
    }
    goto LABEL_3;
  }
  v18 = v46[0];
  v19 = v46[1];
  v20 = (const struct UnionFs::UfsPathName **)v46[0];
  *(__m128i *)v39 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v44[0] = v39;
  v40 = -1;
  v44[1] = v11;
  v45 = 1;
  while ( v20 != (const struct UnionFs::UfsPathName **)v19 )
  {
    utl::make_unique_pool<enum gsl::byte [0],256,1902921301,0>(&FileInformation, *(unsigned __int16 *)*v20 + 24LL);
    v21 = FileInformation;
    if ( !FileInformation )
    {
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC000009ALL,
        (int)a9,
        (struct UnionFs::StackEventTracer *)0x3A900211EB4LL,
        (unsigned __int64)"UnionFs::Utils::CopyHardLinks",
        "ORIGIN: Allocating file link buffer",
        v36);
LABEL_42:
      v45 = 0;
      lambda_d07897a6db9635dde06c57e4c17e80c6_::operator()((__int64)v44);
      v26 = v39[0];
      if ( v39[0] != (PVOID)-1LL )
      {
        v39[1] = v39[0];
        if ( v39[0] )
          ExFreePoolWithTag(v39[0], 0);
      }
      if ( v18 != (_BYTE *)-1LL )
      {
        utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>>(
          v26,
          v18,
          (v19 - v18) >> 3);
        if ( v18 )
          ExFreePoolWithTag(v18, 0);
      }
      v27 = P[0];
      if ( P[0] != (PVOID)-1LL )
      {
        utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>>(
          v26,
          P[0],
          ((char *)P[1] - (char *)P[0]) >> 3);
        if ( v27 )
          ExFreePoolWithTag(v27, 0);
      }
      return 3221225626LL;
    }
    *(_OWORD *)v46 = *(_OWORD *)*v20;
    memmove(
      (char *)FileInformation + 20,
      (const void *)_mm_srli_si128(*(__m128i *)v46, 8).m128i_i64[0],
      (unsigned __int16)_mm_cvtsi128_si32(*(__m128i *)v46));
    *(_BYTE *)v21 = 0;
    v21[1] = 0;
    *((_DWORD *)v21 + 4) = LOWORD(v46[0]);
    v22 = FltSetInformationFile(v11, FileObject, v21, LOWORD(v46[0]) + 24, FileLinkInformation);
    if ( v22 < 0 )
    {
      UnionFs::ProcessTraceStatusFromApi(
        (UnionFs *)(unsigned int)v22,
        (int)a9,
        (struct UnionFs::StackEventTracer *)0x3AA00211EC8LL,
        (unsigned __int64)"UnionFs::Utils::CopyHardLinks",
        "API: Setting hard link",
        v36);
      goto LABEL_29;
    }
    v48[0] = v46;
    if ( v39[1] == (PVOID)v40 )
    {
      if ( !(unsigned __int8)utl::vector<_UNICODE_STRING *,utl::allocator<_UNICODE_STRING *>>::_PushBackOne2<_UNICODE_STRING *>(
                               v39,
                               v48) )
      {
        UnionFs::ProcessTraceStatusOrigin(
          (UnionFs *)0xC000009ALL,
          (int)a9,
          (struct UnionFs::StackEventTracer *)0x3CB00211ECFLL,
          (unsigned __int64)"UnionFs::Utils::CopyHardLinks",
          "ORIGIN: Pushing link name",
          v36);
        if ( v21 )
          ExFreePoolWithTag(v21, 0);
        goto LABEL_42;
      }
    }
    else
    {
      *(_QWORD *)v39[1] = v46;
      v39[1] = (char *)v39[1] + 8;
    }
    if ( *(_DWORD *)(a6 + 28) == 2 )
      v23 = *(UnionFs::UfsPathCache **)(*(_QWORD *)(a6 + 32) + 16LL);
    else
      v23 = (UnionFs::UfsPathCache *)*((_QWORD *)UnionFs::g_FilterState + 10);
    v22 = UnionFs::UfsPathCache::InvalidatePath(v23, a4, *v20, a9, (a7 & 1) == 0);
    if ( v22 < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v22,
        (int)a9,
        (struct UnionFs::StackEventTracer *)0x3B500211EDDLL,
        (unsigned __int64)"UnionFs::Utils::CopyHardLinks",
        "PUSH: Path invalidation",
        v36);
LABEL_29:
      if ( v21 )
        ExFreePoolWithTag(v21, 0);
      v45 = 0;
      lambda_d07897a6db9635dde06c57e4c17e80c6_::operator()((__int64)v44);
      v24 = v39[0];
      if ( v39[0] != (PVOID)-1LL )
      {
        v39[1] = v39[0];
        if ( v39[0] )
          ExFreePoolWithTag(v39[0], 0);
      }
      if ( v18 != (_BYTE *)-1LL )
      {
        utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>>(
          v24,
          v18,
          (v19 - v18) >> 3);
        if ( v18 )
          ExFreePoolWithTag(v18, 0);
      }
      v25 = P[0];
      if ( P[0] != (PVOID)-1LL )
      {
        utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>>(
          v24,
          P[0],
          ((char *)P[1] - (char *)P[0]) >> 3);
        if ( v25 )
          ExFreePoolWithTag(v25, 0);
      }
      return (unsigned int)v22;
    }
    if ( v21 )
      ExFreePoolWithTag(v21, 0);
    v11 = a4;
    ++v20;
  }
  if ( a8 )
  {
    if ( *(_DWORD *)(a6 + 28) == 2 )
      v28 = *(UnionFs::UfsPathTable **)(*(_QWORD *)(a6 + 32) + 24LL);
    else
      v28 = (UnionFs::UfsPathTable *)*((_QWORD *)UnionFs::g_FilterState + 11);
    FsFltWil::AcquireResourceExclusive(&FileInformation, (char *)v28 + 32);
    for ( i = (const char **)v18; i != (const char **)v19; ++i )
    {
      v30 = UnionFs::UfsPathTable::Delete(v28, (__int64)v11, *i, (__int64)a9, 1, 0);
      if ( (v30 & 0x80000000) != 0 )
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)v30,
          (int)a9,
          (struct UnionFs::StackEventTracer *)0x5A90008011BLL,
          (unsigned __int64)"UnionFs::UfsEaTable::DeleteEaEntryWithMultipleNames",
          "PUSH: Deleting EA Entry",
          v37);
        if ( FileInformation )
        {
          ExReleaseResourceLite((PERESOURCE)FileInformation);
          KeLeaveCriticalRegion();
        }
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)v30,
          (int)a9,
          (struct UnionFs::StackEventTracer *)0x64B00211EE9LL,
          (unsigned __int64)"UnionFs::Utils::CopyHardLinks",
          "PUSH: Deleting EA entries",
          v38);
        v45 = 0;
        lambda_d07897a6db9635dde06c57e4c17e80c6_::operator()((__int64)v44);
        v31 = v39[0];
        if ( v39[0] != (PVOID)-1LL )
        {
          v39[1] = v39[0];
          if ( v39[0] )
            ExFreePoolWithTag(v39[0], 0);
        }
        if ( v18 != (_BYTE *)-1LL )
        {
          utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>>(
            v31,
            v18,
            (v19 - v18) >> 3);
          if ( v18 )
            ExFreePoolWithTag(v18, 0);
        }
        v32 = P[0];
        if ( P[0] != (PVOID)-1LL )
        {
          utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>>(
            v31,
            P[0],
            ((char *)P[1] - (char *)P[0]) >> 3);
          if ( v32 )
            ExFreePoolWithTag(v32, 0);
        }
        return v30;
      }
    }
    if ( FileInformation )
    {
      ExReleaseResourceLite((PERESOURCE)FileInformation);
      KeLeaveCriticalRegion();
    }
  }
  v33 = v39[0];
  if ( v39[0] != (PVOID)-1LL )
  {
    v39[1] = v39[0];
    if ( v39[0] )
      ExFreePoolWithTag(v39[0], 0);
  }
  if ( v18 != (_BYTE *)-1LL )
  {
    utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>>(
      v33,
      v18,
      (v19 - v18) >> 3);
    if ( v18 )
      ExFreePoolWithTag(v18, 0);
  }
  v34 = P[0];
  if ( P[0] != (PVOID)-1LL )
  {
    utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>>(
      v33,
      P[0],
      ((char *)P[1] - (char *)P[0]) >> 3);
    if ( v34 )
      ExFreePoolWithTag(v34, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x14006b59c  mov     rax, rsp
0x14006b59f  mov     [rax+20h], r9
0x14006b5a3  push    rbp
0x14006b5a4  push    rbx
0x14006b5a5  push    rsi
0x14006b5a6  push    rdi
0x14006b5a7  push    r12
0x14006b5a9  push    r13
0x14006b5ab  push    r14
0x14006b5ad  push    r15
0x14006b5af  lea     rbp, [rax-47h]
0x14006b5b3  sub     rsp, 0C8h
0x14006b5ba  mov     r14, [rbp+3Fh+arg_40]
0x14006b5c1  mov     rbx, r8
0x14006b5c4  movaps  xmmword ptr [rax-58h], xmm6
0x14006b5c8  lea     r8, [rbp+3Fh+P]
0x14006b5cc  movdqa  xmm6, cs:__xmm@ffffffffffffffffffffffffffffffff
0x14006b5d4  mov     rax, rdx
0x14006b5d7  mov     r12, r9
0x14006b5da  mov     rsi, rcx
0x14006b5dd  or      r15, 0FFFFFFFFFFFFFFFFh
0x14006b5e1  mov     rcx, rax; Instance
0x14006b5e4  mov     r9, r14
0x14006b5e7  mov     [rbp+3Fh+var_98], r15
0x14006b5eb  mov     rdx, rbx; FileObject
0x14006b5ee  movdqu  xmmword ptr [rbp+3Fh+P], xmm6
0x14006b5f3  call    ?GetHardLinkPaths@Utils@UnionFs@@YAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@AEAV?$vector@V?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@V?$allocator@V?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@@2@@utl@@AEAVStackEventTracer@2@_N@Z; UnionFs::Utils::GetHardLinkPaths(_FLT_INSTANCE const &,_FILE_OBJECT const &,utl::vector<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>,utl::allocator<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>> &,UnionFs::StackEventTracer &,bool)
0x14006b5f8  mov     edi, eax
0x14006b5fa  test    eax, eax
0x14006b5fc  jns     short loc_14006B65E
0x14006b5fe  lea     rax, aPushGettingHar; "PUSH: Getting hard link paths"
0x14006b605  mov     r8, 64300211E10h; struct UnionFs::StackEventTracer *
0x14006b60f  lea     r9, aUnionfsUtilsCo_10; "UnionFs::Utils::CopyHardLinks"
0x14006b616  mov     qword ptr [rsp+100h+FileInformationClass], rax; char *
0x14006b61b  mov     rdx, r14; int
0x14006b61e  mov     ecx, edi; this
0x14006b620  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006b625  mov     rbx, [rbp+3Fh+P]
0x14006b629  cmp     rbx, r15
0x14006b62c  jz      short loc_14006B657
0x14006b62e  mov     r8, [rbp+3Fh+P+8]
0x14006b632  mov     rdx, rbx
0x14006b635  sub     r8, rbx
0x14006b638  sar     r8, 3
0x14006b63c  call    ??$_RangeDestroyApc@V?$allocator@V?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@@utl@@@utl@@YAXAEAV?$allocator@V?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@@0@PEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@0@_K@Z; utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>>(utl::allocator<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>> &,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> *,unsigned __int64)
0x14006b641  test    rbx, rbx
0x14006b644  jz      short loc_14006B657
0x14006b646  xor     edx, edx; Tag
0x14006b648  mov     rcx, rbx; P
0x14006b64b  call    cs:__imp_ExFreePoolWithTag
0x14006b652  nop     dword ptr [rax+rax+00h]
0x14006b657  mov     eax, edi
0x14006b659  jmp     loc_14006BC85
0x14006b65e  mov     r13, [rbp+3Fh+arg_28]
0x14006b662  lea     rax, [rbp+3Fh+var_70]
0x14006b666  mov     [rsp+30h], r14; UnionFs::StackEventTracer *
0x14006b66b  mov     r9, rbx; int
0x14006b66e  mov     [rsp+100h+var_D8], rax; char *
0x14006b673  mov     r8, r12; int
0x14006b676  lea     rax, [rbp+3Fh+P]
0x14006b67a  mov     [rbp+3Fh+var_60], r15
0x14006b67e  mov     rdx, rsi; int
0x14006b681  mov     qword ptr [rsp+100h+FileInformationClass], rax; __int64
0x14006b686  mov     rcx, r13; int
0x14006b689  movdqu  xmmword ptr [rbp+3Fh+var_70], xmm6
0x14006b68e  call    ?MapHardLinkNamesAndPrepareScratch@UfsUnionCtx@UnionFs@@QEBAJAEBU_FLT_CALLBACK_DATA@@AEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@AEBV?$vector@V?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@V?$allocator@V?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@@2@@utl@@AEAV67@AEAVStackEventTracer@2@@Z; UnionFs::UfsUnionCtx::MapHardLinkNamesAndPrepareScratch(_FLT_CALLBACK_DATA const &,_FLT_INSTANCE const &,_FILE_OBJECT const &,utl::vector<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>,utl::allocator<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>> const &,utl::vector<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>,utl::allocator<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>> &,UnionFs::StackEventTracer &)
0x14006b693  mov     edi, eax
0x14006b695  test    eax, eax
0x14006b697  jns     short loc_14006B6FF
0x14006b699  lea     rax, aPushRemovingLi; "PUSH: Removing link names"
0x14006b6a0  mov     r8, 3A500211E1Fh; struct UnionFs::StackEventTracer *
0x14006b6aa  lea     r9, aUnionfsUtilsCo_10; "UnionFs::Utils::CopyHardLinks"
0x14006b6b1  mov     qword ptr [rsp+100h+FileInformationClass], rax; char *
0x14006b6b6  mov     rdx, r14; int
0x14006b6b9  mov     ecx, edi; this
0x14006b6bb  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006b6c0  mov     rbx, [rbp+3Fh+var_70]
0x14006b6c4  cmp     rbx, r15
0x14006b6c7  jz      loc_14006B625
0x14006b6cd  mov     r8, [rbp+3Fh+var_70+8]
0x14006b6d1  mov     rdx, rbx
0x14006b6d4  sub     r8, rbx
0x14006b6d7  sar     r8, 3
0x14006b6db  call    ??$_RangeDestroyApc@V?$allocator@V?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@@utl@@@utl@@YAXAEAV?$allocator@V?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@@0@PEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@0@_K@Z; utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>>(utl::allocator<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>> &,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> *,unsigned __int64)
0x14006b6e0  test    rbx, rbx
0x14006b6e3  jz      loc_14006B625
0x14006b6e9  xor     edx, edx; Tag
0x14006b6eb  mov     rcx, rbx; P
0x14006b6ee  call    cs:__imp_ExFreePoolWithTag
0x14006b6f5  nop     dword ptr [rax+rax+00h]
0x14006b6fa  jmp     loc_14006B625
0x14006b6ff  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x14006b707  lea     rax, [rsp+100h+var_C8+8]
0x14006b70c  mov     rsi, [rbp+3Fh+var_70]
0x14006b710  mov     rbx, [rbp+3Fh+var_70+8]
0x14006b714  mov     rdi, rsi
0x14006b717  movdqu  xmmword ptr [rsp+100h+var_C8+8], xmm0
0x14006b71d  mov     [rbp+3Fh+var_88], rax
0x14006b721  mov     [rbp+3Fh+var_B0], r15
0x14006b725  mov     [rbp+3Fh+var_80], r12
0x14006b729  mov     [rbp+3Fh+var_78], 1
0x14006b72d  cmp     rdi, rbx
0x14006b730  jz      loc_14006BA64
0x14006b736  mov     rax, [rdi]
0x14006b739  lea     rcx, [rbp+3Fh+FileInformation]
0x14006b73d  movzx   edx, word ptr [rax]
0x14006b740  add     rdx, 18h
0x14006b744  call    ??$make_unique_pool@$$BY0A@W4byte@gsl@@$0BAA@$0HBGMEGFF@$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@W4byte@gsl@@U?$default_delete@$$BY0A@W4byte@gsl@@@utl@@@0@_K@Z; utl::make_unique_pool<gsl::byte [0],256,1902921301,0>(unsigned __int64)
0x14006b749  mov     r15, [rbp+3Fh+FileInformation]
0x14006b74d  test    r15, r15
0x14006b750  jz      loc_14006B9A0
0x14006b756  mov     rax, [rdi]
0x14006b759  lea     rcx, [r15+14h]; void *
0x14006b75d  movups  xmm0, xmmword ptr [rax]
0x14006b760  movd    eax, xmm0
0x14006b764  movups  xmmword ptr [rbp+3Fh+var_70], xmm0
0x14006b768  psrldq  xmm0, 8
0x14006b76d  movzx   r8d, ax; Size
0x14006b771  movq    rdx, xmm0; Src
0x14006b776  call    memmove
0x14006b77b  mov     rdx, [rbp+3Fh+FileObject]; FileObject
0x14006b77f  mov     r8, r15; FileInformation
0x14006b782  mov     byte ptr [r15], 0
0x14006b786  mov     rcx, r12; Instance
0x14006b789  mov     qword ptr [r15+8], 0
0x14006b791  movzx   eax, word ptr [rbp+3Fh+var_70]
0x14006b795  mov     [r15+10h], eax
0x14006b799  movzx   r9d, word ptr [rbp+3Fh+var_70]
0x14006b79e  add     r9d, 18h; Length
0x14006b7a2  mov     [rsp+100h+FileInformationClass], 0Bh; FileInformationClass
0x14006b7aa  call    cs:__imp_FltSetInformationFile
0x14006b7b1  nop     dword ptr [rax+rax+00h]
0x14006b7b6  mov     r12d, eax
0x14006b7b9  test    eax, eax
0x14006b7bb  js      loc_14006B8CA
0x14006b7c1  lea     rax, [rbp+3Fh+var_70]
0x14006b7c5  mov     [rbp+3Fh+var_58], rax
0x14006b7c9  mov     rax, [rbp+3Fh+var_B8]
0x14006b7cd  cmp     rax, [rbp+3Fh+var_B0]
0x14006b7d1  jz      short loc_14006B7E1
0x14006b7d3  lea     rcx, [rbp+3Fh+var_70]
0x14006b7d7  mov     [rax], rcx
0x14006b7da  add     [rbp+3Fh+var_B8], 8
0x14006b7df  jmp     short loc_14006B7F7
0x14006b7e1  lea     rdx, [rbp+3Fh+var_58]
0x14006b7e5  lea     rcx, [rsp+100h+var_C8+8]
0x14006b7ea  call    ??$_PushBackOne2@PEAU_UNICODE_STRING@@@?$vector@PEAU_UNICODE_STRING@@V?$allocator@PEAU_UNICODE_STRING@@@utl@@@utl@@AEAA_N$$QEAPEAU_UNICODE_STRING@@@Z; utl::vector<_UNICODE_STRING *,utl::allocator<_UNICODE_STRING *>>::_PushBackOne2<_UNICODE_STRING *>(_UNICODE_STRING * &&)
0x14006b7ef  test    al, al
0x14006b7f1  jz      loc_14006B881
0x14006b7f7  cmp     dword ptr [r13+1Ch], 2
0x14006b7fc  jnz     short loc_14006B808
0x14006b7fe  mov     rax, [r13+20h]
0x14006b802  mov     rcx, [rax+10h]
0x14006b806  jmp     short loc_14006B813
0x14006b808  mov     rax, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14006b80f  mov     rcx, [rax+50h]; this
0x14006b813  mov     al, [rbp+3Fh+arg_30]
0x14006b816  mov     r9, r14; struct UnionFs::StackEventTracer *
0x14006b819  mov     r8, [rdi]; struct UnionFs::UfsPathName *
0x14006b81c  not     al
0x14006b81e  mov     rdx, [rbp+3Fh+arg_18]; struct _FLT_INSTANCE *
0x14006b822  and     al, 1
0x14006b824  mov     byte ptr [rsp+100h+FileInformationClass], al; bool
0x14006b828  call    ?InvalidatePath@UfsPathCache@UnionFs@@QEAAJAEBU_FLT_INSTANCE@@AEBVUfsPathName@2@AEAVStackEventTracer@2@_N@Z; UnionFs::UfsPathCache::InvalidatePath(_FLT_INSTANCE const &,UnionFs::UfsPathName const &,UnionFs::StackEventTracer &,bool)
0x14006b82d  mov     r12d, eax
0x14006b830  test    eax, eax
0x14006b832  js      short loc_14006B857
0x14006b834  test    r15, r15
0x14006b837  jz      short loc_14006B84A
0x14006b839  xor     edx, edx; Tag
0x14006b83b  mov     rcx, r15; P
0x14006b83e  call    cs:__imp_ExFreePoolWithTag
0x14006b845  nop     dword ptr [rax+rax+00h]
0x14006b84a  mov     r12, [rbp+3Fh+arg_18]
0x14006b84e  add     rdi, 8
0x14006b852  jmp     loc_14006B72D
0x14006b857  lea     rax, aPushPathInvali; "PUSH: Path invalidation"
0x14006b85e  mov     r8, 3B500211EDDh; struct UnionFs::StackEventTracer *
0x14006b868  lea     r9, aUnionfsUtilsCo_10; "UnionFs::Utils::CopyHardLinks"
0x14006b86f  mov     qword ptr [rsp+100h+FileInformationClass], rax; char *
0x14006b874  mov     rdx, r14; int
0x14006b877  mov     ecx, r12d; this
0x14006b87a  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006b87f  jmp     short loc_14006B8F2
0x14006b881  lea     rax, aOriginPushingL; "ORIGIN: Pushing link name"
0x14006b888  mov     r8, 3CB00211ECFh; struct UnionFs::StackEventTracer *
0x14006b892  lea     r9, aUnionfsUtilsCo_10; "UnionFs::Utils::CopyHardLinks"
0x14006b899  mov     qword ptr [rsp+100h+FileInformationClass], rax; char *
0x14006b89e  mov     rdx, r14; int
0x14006b8a1  mov     ecx, 0C000009Ah; this
0x14006b8a6  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006b8ab  test    r15, r15
0x14006b8ae  jz      loc_14006B9CA
0x14006b8b4  xor     edx, edx; Tag
0x14006b8b6  mov     rcx, r15; P
0x14006b8b9  call    cs:__imp_ExFreePoolWithTag
0x14006b8c0  nop     dword ptr [rax+rax+00h]
0x14006b8c5  jmp     loc_14006B9CA
0x14006b8ca  lea     rax, aApiSettingHard; "API: Setting hard link"
0x14006b8d1  mov     r8, 3AA00211EC8h; struct UnionFs::StackEventTracer *
0x14006b8db  lea     r9, aUnionfsUtilsCo_10; "UnionFs::Utils::CopyHardLinks"
0x14006b8e2  mov     qword ptr [rsp+100h+FileInformationClass], rax; char *
0x14006b8e7  mov     rdx, r14; int
0x14006b8ea  mov     ecx, r12d; this
0x14006b8ed  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006b8f2  test    r15, r15
0x14006b8f5  jz      short loc_14006B908
0x14006b8f7  xor     edx, edx; Tag
0x14006b8f9  mov     rcx, r15; P
0x14006b8fc  call    cs:__imp_ExFreePoolWithTag
0x14006b903  nop     dword ptr [rax+rax+00h]
0x14006b908  lea     rcx, [rbp+3Fh+var_88]
0x14006b90c  mov     [rbp+3Fh+var_78], 0
0x14006b910  call    _lambda_d07897a6db9635dde06c57e4c17e80c6___operator__
0x14006b915  mov     rcx, [rsp+100h+var_C8+8]; P
0x14006b91a  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14006b91e  jz      short loc_14006B937
0x14006b920  mov     [rbp+3Fh+var_B8], rcx
0x14006b924  test    rcx, rcx
0x14006b927  jz      short loc_14006B937
0x14006b929  xor     edx, edx; Tag
0x14006b92b  call    cs:__imp_ExFreePoolWithTag
0x14006b932  nop     dword ptr [rax+rax+00h]
0x14006b937  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x14006b93b  jz      short loc_14006B965
0x14006b93d  sub     rbx, rsi
0x14006b940  mov     rdx, rsi
0x14006b943  sar     rbx, 3
0x14006b947  mov     r8, rbx
0x14006b94a  call    ??$_RangeDestroyApc@V?$allocator@V?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@@utl@@@utl@@YAXAEAV?$allocator@V?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@@0@PEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@0@_K@Z; utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>>(utl::allocator<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>> &,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> *,unsigned __int64)
0x14006b94f  test    rsi, rsi
0x14006b952  jz      short loc_14006B965
0x14006b954  xor     edx, edx; Tag
0x14006b956  mov     rcx, rsi; P
0x14006b959  call    cs:__imp_ExFreePoolWithTag
0x14006b960  nop     dword ptr [rax+rax+00h]
0x14006b965  mov     rbx, [rbp+3Fh+P]
0x14006b969  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x14006b96d  jz      short loc_14006B998
0x14006b96f  mov     r8, [rbp+3Fh+P+8]
0x14006b973  mov     rdx, rbx
0x14006b976  sub     r8, rbx
0x14006b979  sar     r8, 3
0x14006b97d  call    ??$_RangeDestroyApc@V?$allocator@V?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@@utl@@@utl@@YAXAEAV?$allocator@V?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@@0@PEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@0@_K@Z; utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>>(utl::allocator<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>> &,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> *,unsigned __int64)
0x14006b982  test    rbx, rbx
0x14006b985  jz      short loc_14006B998
0x14006b987  xor     edx, edx; Tag
0x14006b989  mov     rcx, rbx; P
0x14006b98c  call    cs:__imp_ExFreePoolWithTag
0x14006b993  nop     dword ptr [rax+rax+00h]
0x14006b998  mov     eax, r12d
0x14006b99b  jmp     loc_14006BC85
0x14006b9a0  lea     rax, aOriginAllocati_45; "ORIGIN: Allocating file link buffer"
0x14006b9a7  mov     r8, 3A900211EB4h; struct UnionFs::StackEventTracer *
0x14006b9b1  lea     r9, aUnionfsUtilsCo_10; "UnionFs::Utils::CopyHardLinks"
0x14006b9b8  mov     qword ptr [rsp+100h+FileInformationClass], rax; char *
0x14006b9bd  mov     rdx, r14; int
0x14006b9c0  mov     ecx, 0C000009Ah; this
0x14006b9c5  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006b9ca  lea     rcx, [rbp+3Fh+var_88]
0x14006b9ce  mov     [rbp+3Fh+var_78], 0
0x14006b9d2  call    _lambda_d07897a6db9635dde06c57e4c17e80c6___operator__
0x14006b9d7  mov     rcx, [rsp+100h+var_C8+8]; P
0x14006b9dc  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14006b9e0  jz      short loc_14006B9F9
0x14006b9e2  mov     [rbp+3Fh+var_B8], rcx
0x14006b9e6  test    rcx, rcx
0x14006b9e9  jz      short loc_14006B9F9
0x14006b9eb  xor     edx, edx; Tag
0x14006b9ed  call    cs:__imp_ExFreePoolWithTag
0x14006b9f4  nop     dword ptr [rax+rax+00h]
0x14006b9f9  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x14006b9fd  jz      short loc_14006BA27
0x14006b9ff  sub     rbx, rsi
0x14006ba02  mov     rdx, rsi
0x14006ba05  sar     rbx, 3
0x14006ba09  mov     r8, rbx
0x14006ba0c  call    ??$_RangeDestroyApc@V?$allocator@V?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@@utl@@@utl@@YAXAEAV?$allocator@V?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@@0@PEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@0@_K@Z; utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>>(utl::allocator<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>> &,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> *,unsigned __int64)
0x14006ba11  test    rsi, rsi
0x14006ba14  jz      short loc_14006BA27
0x14006ba16  xor     edx, edx; Tag
0x14006ba18  mov     rcx, rsi; P
0x14006ba1b  call    cs:__imp_ExFreePoolWithTag
0x14006ba22  nop     dword ptr [rax+rax+00h]
0x14006ba27  mov     rbx, [rbp+3Fh+P]
0x14006ba2b  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x14006ba2f  jz      short loc_14006BA5A
0x14006ba31  mov     r8, [rbp+3Fh+P+8]
0x14006ba35  mov     rdx, rbx
0x14006ba38  sub     r8, rbx
0x14006ba3b  sar     r8, 3
0x14006ba3f  call    ??$_RangeDestroyApc@V?$allocator@V?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@@utl@@@utl@@YAXAEAV?$allocator@V?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@@0@PEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@0@_K@Z; utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>>(utl::allocator<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>> &,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> *,unsigned __int64)
0x14006ba44  test    rbx, rbx
0x14006ba47  jz      short loc_14006BA5A
0x14006ba49  xor     edx, edx; Tag
0x14006ba4b  mov     rcx, rbx; P
0x14006ba4e  call    cs:__imp_ExFreePoolWithTag
0x14006ba55  nop     dword ptr [rax+rax+00h]
0x14006ba5a  mov     eax, 0C000009Ah
0x14006ba5f  jmp     loc_14006BC85
  ... truncated ...
```
