# UnionFs::Utils::CopyHardLinks(_FLT_CALLBACK_DATA const &,_FLT_INSTANCE const &,_FILE_OBJECT const &,_FLT_INSTANCE const &,_FILE_OBJECT const &,UnionFs::UfsUnionCtx const &,UnionFs::Utils::CopyItemFlags,bool,UnionFs::StackEventTracer &)

- ea: `0x14006b78c`
- end: `0x14006be92`
- name: `?CopyHardLinks@Utils@UnionFs@@YAJAEBU_FLT_CALLBACK_DATA@@AEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@12AEBVUfsUnionCtx@2@W4CopyItemFlags@12@_NAEAVStackEventTracer@2@@Z`
- size: `1798`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, reparse_path, installer_update`

## callers

- `0x14006c3ec`

## callees

- `0x14001c820`
- `0x14003cdec`
- `0x140046690`
- `0x140056bd0`
- `0x140056c44`
- `0x140056c7c`
- `0x1400620ac`
- `0x1400677e4`
- `0x140067bb8`
- `0x1400685bc`
- `0x14006b78c`
- `0x14006e54c`
- `0x140079d8c`
- `0x14007bc40`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14006b83b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006b8de`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006ba2e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006baa9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006baec`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006bb1b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006bb49`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006bb7c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006bbdd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006bc0b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006bc3e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006bd59`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006bd87`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006bdba`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006be08`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006be35`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006be67`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006b83b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006b8de`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006ba2e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006baa9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006baec`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006bb1b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006bb49`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006bb7c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006bbdd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006bc0b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006bc3e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006bd59`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006bd87`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006bdba`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006be08`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006be35`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006be67`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006bcf6`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006bdd7`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006bcf6`
- `ntoskrnl!ExReleaseResourceLite` at `0x14006bdd7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006bd02`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006bde3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006bd02`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006bde3`
- `FLTMGR!FltSetInformationFile` at `0x14006b99a`
- `FLTMGR!FltSetInformationFile` at `0x14006b99a`

## string_xrefs

- `0x14006b7ee`: `PUSH: Getting hard link paths`
- `0x14006bcd6`: `UnionFs::UfsEaTable::DeleteEaEntryWithMultipleNames`
- `0x14006ba71`: `ORIGIN: Pushing link name`
- `0x14006b7ff`: `UnionFs::Utils::CopyHardLinks`
- `0x14006b89a`: `UnionFs::Utils::CopyHardLinks`
- `0x14006ba58`: `UnionFs::Utils::CopyHardLinks`
- `0x14006ba82`: `UnionFs::Utils::CopyHardLinks`
- `0x14006bacb`: `UnionFs::Utils::CopyHardLinks`
- `0x14006bba1`: `UnionFs::Utils::CopyHardLinks`
- `0x14006bd1f`: `UnionFs::Utils::CopyHardLinks`
- `0x14006bb90`: `ORIGIN: Allocating file link buffer`
- `0x14006b889`: `PUSH: Removing link names`
- `0x14006ba47`: `PUSH: Path invalidation`
- `0x14006baba`: `API: Setting hard link`

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
      (struct UnionFs::StackEventTracer *)0x64300211E46LL,
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
      (struct UnionFs::StackEventTracer *)0x3A500211E55LL,
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
        (struct UnionFs::StackEventTracer *)0x3A900211EEALL,
        (unsigned __int64)"UnionFs::Utils::CopyHardLinks",
        "ORIGIN: Allocating file link buffer",
        v36);
LABEL_42:
      v45 = 0;
      lambda_d0ebc0232045179cce8cceee9eafce0e_::operator()((__int64)v44);
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
        (struct UnionFs::StackEventTracer *)0x3AA00211EFELL,
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
          (struct UnionFs::StackEventTracer *)0x3CB00211F05LL,
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
        (struct UnionFs::StackEventTracer *)0x3B500211F13LL,
        (unsigned __int64)"UnionFs::Utils::CopyHardLinks",
        "PUSH: Path invalidation",
        v36);
LABEL_29:
      if ( v21 )
        ExFreePoolWithTag(v21, 0);
      v45 = 0;
      lambda_d0ebc0232045179cce8cceee9eafce0e_::operator()((__int64)v44);
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
          (struct UnionFs::StackEventTracer *)0x64B00211F1FLL,
          (unsigned __int64)"UnionFs::Utils::CopyHardLinks",
          "PUSH: Deleting EA entries",
          v38);
        v45 = 0;
        lambda_d0ebc0232045179cce8cceee9eafce0e_::operator()((__int64)v44);
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
0x14006b78c  mov     rax, rsp
0x14006b78f  mov     [rax+20h], r9
0x14006b793  push    rbp
0x14006b794  push    rbx
0x14006b795  push    rsi
0x14006b796  push    rdi
0x14006b797  push    r12
0x14006b799  push    r13
0x14006b79b  push    r14
0x14006b79d  push    r15
0x14006b79f  lea     rbp, [rax-47h]
0x14006b7a3  sub     rsp, 0C8h
0x14006b7aa  mov     r14, [rbp+3Fh+arg_40]
0x14006b7b1  mov     rbx, r8
0x14006b7b4  movaps  xmmword ptr [rax-58h], xmm6
0x14006b7b8  lea     r8, [rbp+3Fh+P]
0x14006b7bc  movdqa  xmm6, cs:__xmm@ffffffffffffffffffffffffffffffff
0x14006b7c4  mov     rax, rdx
0x14006b7c7  mov     r12, r9
0x14006b7ca  mov     rsi, rcx
0x14006b7cd  or      r15, 0FFFFFFFFFFFFFFFFh
0x14006b7d1  mov     rcx, rax; Instance
0x14006b7d4  mov     r9, r14
0x14006b7d7  mov     [rbp+3Fh+var_98], r15
0x14006b7db  mov     rdx, rbx; FileObject
0x14006b7de  movdqu  xmmword ptr [rbp+3Fh+P], xmm6
0x14006b7e3  call    ?GetHardLinkPaths@Utils@UnionFs@@YAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@AEAV?$vector@V?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@V?$allocator@V?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@@2@@utl@@AEAVStackEventTracer@2@_N@Z; UnionFs::Utils::GetHardLinkPaths(_FLT_INSTANCE const &,_FILE_OBJECT const &,utl::vector<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>,utl::allocator<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>> &,UnionFs::StackEventTracer &,bool)
0x14006b7e8  mov     edi, eax
0x14006b7ea  test    eax, eax
0x14006b7ec  jns     short loc_14006B84E
0x14006b7ee  lea     rax, aPushGettingHar; "PUSH: Getting hard link paths"
0x14006b7f5  mov     r8, 64300211E46h; struct UnionFs::StackEventTracer *
0x14006b7ff  lea     r9, aUnionfsUtilsCo_9; "UnionFs::Utils::CopyHardLinks"
0x14006b806  mov     qword ptr [rsp+100h+FileInformationClass], rax; char *
0x14006b80b  mov     rdx, r14; int
0x14006b80e  mov     ecx, edi; this
0x14006b810  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006b815  mov     rbx, [rbp+3Fh+P]
0x14006b819  cmp     rbx, r15
0x14006b81c  jz      short loc_14006B847
0x14006b81e  mov     r8, [rbp+3Fh+P+8]
0x14006b822  mov     rdx, rbx
0x14006b825  sub     r8, rbx
0x14006b828  sar     r8, 3
0x14006b82c  call    ??$_RangeDestroyApc@V?$allocator@V?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@@utl@@@utl@@YAXAEAV?$allocator@V?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@@0@PEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@0@_K@Z; utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>>(utl::allocator<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>> &,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> *,unsigned __int64)
0x14006b831  test    rbx, rbx
0x14006b834  jz      short loc_14006B847
0x14006b836  xor     edx, edx; Tag
0x14006b838  mov     rcx, rbx; P
0x14006b83b  call    cs:__imp_ExFreePoolWithTag
0x14006b842  nop     dword ptr [rax+rax+00h]
0x14006b847  mov     eax, edi
0x14006b849  jmp     loc_14006BE75
0x14006b84e  mov     r13, [rbp+3Fh+arg_28]
0x14006b852  lea     rax, [rbp+3Fh+var_70]
0x14006b856  mov     [rsp+30h], r14; UnionFs::StackEventTracer *
0x14006b85b  mov     r9, rbx; int
0x14006b85e  mov     [rsp+100h+var_D8], rax; char *
0x14006b863  mov     r8, r12; int
0x14006b866  lea     rax, [rbp+3Fh+P]
0x14006b86a  mov     [rbp+3Fh+var_60], r15
0x14006b86e  mov     rdx, rsi; int
0x14006b871  mov     qword ptr [rsp+100h+FileInformationClass], rax; __int64
0x14006b876  mov     rcx, r13; int
0x14006b879  movdqu  xmmword ptr [rbp+3Fh+var_70], xmm6
0x14006b87e  call    ?MapHardLinkNamesAndPrepareScratch@UfsUnionCtx@UnionFs@@QEBAJAEBU_FLT_CALLBACK_DATA@@AEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@AEBV?$vector@V?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@V?$allocator@V?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@@2@@utl@@AEAV67@AEAVStackEventTracer@2@@Z; UnionFs::UfsUnionCtx::MapHardLinkNamesAndPrepareScratch(_FLT_CALLBACK_DATA const &,_FLT_INSTANCE const &,_FILE_OBJECT const &,utl::vector<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>,utl::allocator<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>> const &,utl::vector<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>,utl::allocator<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>> &,UnionFs::StackEventTracer &)
0x14006b883  mov     edi, eax
0x14006b885  test    eax, eax
0x14006b887  jns     short loc_14006B8EF
0x14006b889  lea     rax, aPushRemovingLi; "PUSH: Removing link names"
0x14006b890  mov     r8, 3A500211E55h; struct UnionFs::StackEventTracer *
0x14006b89a  lea     r9, aUnionfsUtilsCo_9; "UnionFs::Utils::CopyHardLinks"
0x14006b8a1  mov     qword ptr [rsp+100h+FileInformationClass], rax; char *
0x14006b8a6  mov     rdx, r14; int
0x14006b8a9  mov     ecx, edi; this
0x14006b8ab  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006b8b0  mov     rbx, [rbp+3Fh+var_70]
0x14006b8b4  cmp     rbx, r15
0x14006b8b7  jz      loc_14006B815
0x14006b8bd  mov     r8, [rbp+3Fh+var_70+8]
0x14006b8c1  mov     rdx, rbx
0x14006b8c4  sub     r8, rbx
0x14006b8c7  sar     r8, 3
0x14006b8cb  call    ??$_RangeDestroyApc@V?$allocator@V?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@@utl@@@utl@@YAXAEAV?$allocator@V?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@@0@PEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@0@_K@Z; utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>>(utl::allocator<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>> &,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> *,unsigned __int64)
0x14006b8d0  test    rbx, rbx
0x14006b8d3  jz      loc_14006B815
0x14006b8d9  xor     edx, edx; Tag
0x14006b8db  mov     rcx, rbx; P
0x14006b8de  call    cs:__imp_ExFreePoolWithTag
0x14006b8e5  nop     dword ptr [rax+rax+00h]
0x14006b8ea  jmp     loc_14006B815
0x14006b8ef  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x14006b8f7  lea     rax, [rsp+100h+var_C8+8]
0x14006b8fc  mov     rsi, [rbp+3Fh+var_70]
0x14006b900  mov     rbx, [rbp+3Fh+var_70+8]
0x14006b904  mov     rdi, rsi
0x14006b907  movdqu  xmmword ptr [rsp+100h+var_C8+8], xmm0
0x14006b90d  mov     [rbp+3Fh+var_88], rax
0x14006b911  mov     [rbp+3Fh+var_B0], r15
0x14006b915  mov     [rbp+3Fh+var_80], r12
0x14006b919  mov     [rbp+3Fh+var_78], 1
0x14006b91d  cmp     rdi, rbx
0x14006b920  jz      loc_14006BC54
0x14006b926  mov     rax, [rdi]
0x14006b929  lea     rcx, [rbp+3Fh+FileInformation]
0x14006b92d  movzx   edx, word ptr [rax]
0x14006b930  add     rdx, 18h
0x14006b934  call    ??$make_unique_pool@$$BY0A@W4byte@gsl@@$0BAA@$0HBGMEGFF@$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@W4byte@gsl@@U?$default_delete@$$BY0A@W4byte@gsl@@@utl@@@0@_K@Z; utl::make_unique_pool<gsl::byte [0],256,1902921301,0>(unsigned __int64)
0x14006b939  mov     r15, [rbp+3Fh+FileInformation]
0x14006b93d  test    r15, r15
0x14006b940  jz      loc_14006BB90
0x14006b946  mov     rax, [rdi]
0x14006b949  lea     rcx, [r15+14h]; void *
0x14006b94d  movups  xmm0, xmmword ptr [rax]
0x14006b950  movd    eax, xmm0
0x14006b954  movups  xmmword ptr [rbp+3Fh+var_70], xmm0
0x14006b958  psrldq  xmm0, 8
0x14006b95d  movzx   r8d, ax; Size
0x14006b961  movq    rdx, xmm0; Src
0x14006b966  call    memmove
0x14006b96b  mov     rdx, [rbp+3Fh+FileObject]; FileObject
0x14006b96f  mov     r8, r15; FileInformation
0x14006b972  mov     byte ptr [r15], 0
0x14006b976  mov     rcx, r12; Instance
0x14006b979  mov     qword ptr [r15+8], 0
0x14006b981  movzx   eax, word ptr [rbp+3Fh+var_70]
0x14006b985  mov     [r15+10h], eax
0x14006b989  movzx   r9d, word ptr [rbp+3Fh+var_70]
0x14006b98e  add     r9d, 18h; Length
0x14006b992  mov     [rsp+100h+FileInformationClass], 0Bh; FileInformationClass
0x14006b99a  call    cs:__imp_FltSetInformationFile
0x14006b9a1  nop     dword ptr [rax+rax+00h]
0x14006b9a6  mov     r12d, eax
0x14006b9a9  test    eax, eax
0x14006b9ab  js      loc_14006BABA
0x14006b9b1  lea     rax, [rbp+3Fh+var_70]
0x14006b9b5  mov     [rbp+3Fh+var_58], rax
0x14006b9b9  mov     rax, [rbp+3Fh+var_B8]
0x14006b9bd  cmp     rax, [rbp+3Fh+var_B0]
0x14006b9c1  jz      short loc_14006B9D1
0x14006b9c3  lea     rcx, [rbp+3Fh+var_70]
0x14006b9c7  mov     [rax], rcx
0x14006b9ca  add     [rbp+3Fh+var_B8], 8
0x14006b9cf  jmp     short loc_14006B9E7
0x14006b9d1  lea     rdx, [rbp+3Fh+var_58]
0x14006b9d5  lea     rcx, [rsp+100h+var_C8+8]
0x14006b9da  call    ??$_PushBackOne2@PEAU_UNICODE_STRING@@@?$vector@PEAU_UNICODE_STRING@@V?$allocator@PEAU_UNICODE_STRING@@@utl@@@utl@@AEAA_N$$QEAPEAU_UNICODE_STRING@@@Z; utl::vector<_UNICODE_STRING *,utl::allocator<_UNICODE_STRING *>>::_PushBackOne2<_UNICODE_STRING *>(_UNICODE_STRING * &&)
0x14006b9df  test    al, al
0x14006b9e1  jz      loc_14006BA71
0x14006b9e7  cmp     dword ptr [r13+1Ch], 2
0x14006b9ec  jnz     short loc_14006B9F8
0x14006b9ee  mov     rax, [r13+20h]
0x14006b9f2  mov     rcx, [rax+10h]
0x14006b9f6  jmp     short loc_14006BA03
0x14006b9f8  mov     rax, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14006b9ff  mov     rcx, [rax+50h]; this
0x14006ba03  mov     al, [rbp+3Fh+arg_30]
0x14006ba06  mov     r9, r14; struct UnionFs::StackEventTracer *
0x14006ba09  mov     r8, [rdi]; struct UnionFs::UfsPathName *
0x14006ba0c  not     al
0x14006ba0e  mov     rdx, [rbp+3Fh+arg_18]; struct _FLT_INSTANCE *
0x14006ba12  and     al, 1
0x14006ba14  mov     byte ptr [rsp+100h+FileInformationClass], al; bool
0x14006ba18  call    ?InvalidatePath@UfsPathCache@UnionFs@@QEAAJAEBU_FLT_INSTANCE@@AEBVUfsPathName@2@AEAVStackEventTracer@2@_N@Z; UnionFs::UfsPathCache::InvalidatePath(_FLT_INSTANCE const &,UnionFs::UfsPathName const &,UnionFs::StackEventTracer &,bool)
0x14006ba1d  mov     r12d, eax
0x14006ba20  test    eax, eax
0x14006ba22  js      short loc_14006BA47
0x14006ba24  test    r15, r15
0x14006ba27  jz      short loc_14006BA3A
0x14006ba29  xor     edx, edx; Tag
0x14006ba2b  mov     rcx, r15; P
0x14006ba2e  call    cs:__imp_ExFreePoolWithTag
0x14006ba35  nop     dword ptr [rax+rax+00h]
0x14006ba3a  mov     r12, [rbp+3Fh+arg_18]
0x14006ba3e  add     rdi, 8
0x14006ba42  jmp     loc_14006B91D
0x14006ba47  lea     rax, aPushPathInvali; "PUSH: Path invalidation"
0x14006ba4e  mov     r8, 3B500211F13h; struct UnionFs::StackEventTracer *
0x14006ba58  lea     r9, aUnionfsUtilsCo_9; "UnionFs::Utils::CopyHardLinks"
0x14006ba5f  mov     qword ptr [rsp+100h+FileInformationClass], rax; char *
0x14006ba64  mov     rdx, r14; int
0x14006ba67  mov     ecx, r12d; this
0x14006ba6a  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006ba6f  jmp     short loc_14006BAE2
0x14006ba71  lea     rax, aOriginPushingL; "ORIGIN: Pushing link name"
0x14006ba78  mov     r8, 3CB00211F05h; struct UnionFs::StackEventTracer *
0x14006ba82  lea     r9, aUnionfsUtilsCo_9; "UnionFs::Utils::CopyHardLinks"
0x14006ba89  mov     qword ptr [rsp+100h+FileInformationClass], rax; char *
0x14006ba8e  mov     rdx, r14; int
0x14006ba91  mov     ecx, 0C000009Ah; this
0x14006ba96  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006ba9b  test    r15, r15
0x14006ba9e  jz      loc_14006BBBA
0x14006baa4  xor     edx, edx; Tag
0x14006baa6  mov     rcx, r15; P
0x14006baa9  call    cs:__imp_ExFreePoolWithTag
0x14006bab0  nop     dword ptr [rax+rax+00h]
0x14006bab5  jmp     loc_14006BBBA
0x14006baba  lea     rax, aApiSettingHard; "API: Setting hard link"
0x14006bac1  mov     r8, 3AA00211EFEh; struct UnionFs::StackEventTracer *
0x14006bacb  lea     r9, aUnionfsUtilsCo_9; "UnionFs::Utils::CopyHardLinks"
0x14006bad2  mov     qword ptr [rsp+100h+FileInformationClass], rax; char *
0x14006bad7  mov     rdx, r14; int
0x14006bada  mov     ecx, r12d; this
0x14006badd  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006bae2  test    r15, r15
0x14006bae5  jz      short loc_14006BAF8
0x14006bae7  xor     edx, edx; Tag
0x14006bae9  mov     rcx, r15; P
0x14006baec  call    cs:__imp_ExFreePoolWithTag
0x14006baf3  nop     dword ptr [rax+rax+00h]
0x14006baf8  lea     rcx, [rbp+3Fh+var_88]
0x14006bafc  mov     [rbp+3Fh+var_78], 0
0x14006bb00  call    _lambda_d0ebc0232045179cce8cceee9eafce0e___operator__
0x14006bb05  mov     rcx, [rsp+100h+var_C8+8]; P
0x14006bb0a  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14006bb0e  jz      short loc_14006BB27
0x14006bb10  mov     [rbp+3Fh+var_B8], rcx
0x14006bb14  test    rcx, rcx
0x14006bb17  jz      short loc_14006BB27
0x14006bb19  xor     edx, edx; Tag
0x14006bb1b  call    cs:__imp_ExFreePoolWithTag
0x14006bb22  nop     dword ptr [rax+rax+00h]
0x14006bb27  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x14006bb2b  jz      short loc_14006BB55
0x14006bb2d  sub     rbx, rsi
0x14006bb30  mov     rdx, rsi
0x14006bb33  sar     rbx, 3
0x14006bb37  mov     r8, rbx
0x14006bb3a  call    ??$_RangeDestroyApc@V?$allocator@V?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@@utl@@@utl@@YAXAEAV?$allocator@V?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@@0@PEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@0@_K@Z; utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>>(utl::allocator<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>> &,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> *,unsigned __int64)
0x14006bb3f  test    rsi, rsi
0x14006bb42  jz      short loc_14006BB55
0x14006bb44  xor     edx, edx; Tag
0x14006bb46  mov     rcx, rsi; P
0x14006bb49  call    cs:__imp_ExFreePoolWithTag
0x14006bb50  nop     dword ptr [rax+rax+00h]
0x14006bb55  mov     rbx, [rbp+3Fh+P]
0x14006bb59  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x14006bb5d  jz      short loc_14006BB88
0x14006bb5f  mov     r8, [rbp+3Fh+P+8]
0x14006bb63  mov     rdx, rbx
0x14006bb66  sub     r8, rbx
0x14006bb69  sar     r8, 3
0x14006bb6d  call    ??$_RangeDestroyApc@V?$allocator@V?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@@utl@@@utl@@YAXAEAV?$allocator@V?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@@0@PEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@0@_K@Z; utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>>(utl::allocator<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>> &,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> *,unsigned __int64)
0x14006bb72  test    rbx, rbx
0x14006bb75  jz      short loc_14006BB88
0x14006bb77  xor     edx, edx; Tag
0x14006bb79  mov     rcx, rbx; P
0x14006bb7c  call    cs:__imp_ExFreePoolWithTag
0x14006bb83  nop     dword ptr [rax+rax+00h]
0x14006bb88  mov     eax, r12d
0x14006bb8b  jmp     loc_14006BE75
0x14006bb90  lea     rax, aOriginAllocati_46; "ORIGIN: Allocating file link buffer"
0x14006bb97  mov     r8, 3A900211EEAh; struct UnionFs::StackEventTracer *
0x14006bba1  lea     r9, aUnionfsUtilsCo_9; "UnionFs::Utils::CopyHardLinks"
0x14006bba8  mov     qword ptr [rsp+100h+FileInformationClass], rax; char *
0x14006bbad  mov     rdx, r14; int
0x14006bbb0  mov     ecx, 0C000009Ah; this
0x14006bbb5  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006bbba  lea     rcx, [rbp+3Fh+var_88]
0x14006bbbe  mov     [rbp+3Fh+var_78], 0
0x14006bbc2  call    _lambda_d0ebc0232045179cce8cceee9eafce0e___operator__
0x14006bbc7  mov     rcx, [rsp+100h+var_C8+8]; P
0x14006bbcc  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14006bbd0  jz      short loc_14006BBE9
0x14006bbd2  mov     [rbp+3Fh+var_B8], rcx
0x14006bbd6  test    rcx, rcx
0x14006bbd9  jz      short loc_14006BBE9
0x14006bbdb  xor     edx, edx; Tag
0x14006bbdd  call    cs:__imp_ExFreePoolWithTag
0x14006bbe4  nop     dword ptr [rax+rax+00h]
0x14006bbe9  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x14006bbed  jz      short loc_14006BC17
0x14006bbef  sub     rbx, rsi
0x14006bbf2  mov     rdx, rsi
0x14006bbf5  sar     rbx, 3
0x14006bbf9  mov     r8, rbx
0x14006bbfc  call    ??$_RangeDestroyApc@V?$allocator@V?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@@utl@@@utl@@YAXAEAV?$allocator@V?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@@0@PEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@0@_K@Z; utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>>(utl::allocator<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>> &,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> *,unsigned __int64)
0x14006bc01  test    rsi, rsi
0x14006bc04  jz      short loc_14006BC17
0x14006bc06  xor     edx, edx; Tag
0x14006bc08  mov     rcx, rsi; P
0x14006bc0b  call    cs:__imp_ExFreePoolWithTag
0x14006bc12  nop     dword ptr [rax+rax+00h]
0x14006bc17  mov     rbx, [rbp+3Fh+P]
0x14006bc1b  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x14006bc1f  jz      short loc_14006BC4A
0x14006bc21  mov     r8, [rbp+3Fh+P+8]
0x14006bc25  mov     rdx, rbx
0x14006bc28  sub     r8, rbx
0x14006bc2b  sar     r8, 3
0x14006bc2f  call    ??$_RangeDestroyApc@V?$allocator@V?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@@utl@@@utl@@YAXAEAV?$allocator@V?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@@0@PEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@0@_K@Z; utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>>(utl::allocator<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>> &,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> *,unsigned __int64)
0x14006bc34  test    rbx, rbx
0x14006bc37  jz      short loc_14006BC4A
0x14006bc39  xor     edx, edx; Tag
0x14006bc3b  mov     rcx, rbx; P
0x14006bc3e  call    cs:__imp_ExFreePoolWithTag
0x14006bc45  nop     dword ptr [rax+rax+00h]
0x14006bc4a  mov     eax, 0C000009Ah
0x14006bc4f  jmp     loc_14006BE75
  ... truncated ...
```
