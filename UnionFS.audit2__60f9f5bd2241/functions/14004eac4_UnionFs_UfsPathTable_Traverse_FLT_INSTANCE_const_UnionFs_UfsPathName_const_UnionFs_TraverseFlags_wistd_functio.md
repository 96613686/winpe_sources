# UnionFs::UfsPathTable::Traverse(_FLT_INSTANCE const &,UnionFs::UfsPathName const &,UnionFs::TraverseFlags,wistd::function<long (UnionFs::UfsPathTierNode &,UnionFs::UfsPathTierNode *,UnionFs::UFS_TABLE_TRAVERSE_CTX &)> const &,UnionFs::StackEventTracer &)

- ea: `0x14004eac4`
- end: `0x14004f2e9`
- name: `?Traverse@UfsPathTable@UnionFs@@IEAAJAEBU_FLT_INSTANCE@@AEBVUfsPathName@2@W4TraverseFlags@2@AEBV?$function@$$A6AJAEAVUfsPathTierNode@UnionFs@@PEAV12@AEAUUFS_TABLE_TRAVERSE_CTX@2@@Z@wistd@@AEAVStackEventTracer@2@@Z`
- size: `2085`
- prototype: ``
- caller_count: `5`
- callee_count: `20`
- tags: `reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14001ff30`
- `0x140023c1c`
- `0x14003c50c`
- `0x14004e914`
- `0x14005be40`

## callees

- `0x14000227c`
- `0x14000f81c`
- `0x14003dc14`
- `0x14004eac4`
- `0x14004f62c`
- `0x14004f754`
- `0x14004fce0`
- `0x140056bd0`
- `0x140056c44`
- `0x140056c7c`
- `0x140079404`
- `0x140079d8c`
- `0x140079dd4`
- `0x140079e1c`
- `0x140079f68`
- `0x14007a02c`
- `0x14007a114`
- `0x14007b2b0`
- `0x14007baf0`
- `0x14007bbd0`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeToString` at `0x14004eddf`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14004eddf`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14004ebe4`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14004edff`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14004ebe4`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14004edff`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004ec53`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004f03d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004f0e4`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004f224`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004f298`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004ec53`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004f03d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004f0e4`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004f224`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004f298`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004ec5f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004f049`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004f0f0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004f230`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004f2a4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004ec5f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004f049`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004f0f0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004f230`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004f2a4`

## string_xrefs

- `0x14004f243`: `ORIGIN: Table already run down`
- `0x14004ec0a`: `UnionFs::UfsPathTable::Traverse`
- `0x14004ece6`: `UnionFs::UfsPathTable::Traverse`
- `0x14004ef02`: `UnionFs::UfsPathTable::Traverse`
- `0x14004efd1`: `UnionFs::UfsPathTable::Traverse`
- `0x14004f080`: `UnionFs::UfsPathTable::Traverse`
- `0x14004f11a`: `UnionFs::UfsPathTable::Traverse`
- `0x14004f1e2`: `UnionFs::UfsPathTable::Traverse`
- `0x14004f256`: `UnionFs::UfsPathTable::Traverse`
- `0x14004f1d1`: `ORIGIN: Traversal on volume with no paths.`
- `0x14004ebf9`: `API: Appending volume root to currentPath`
- `0x14004f06f`: `API: Appending \ to currentPath`
- `0x14004f05c`: `API: Appending path component to currentPath`
- `0x14004f109`: `ORIGIN: StartingPath is not in the table`

## pseudocode

```c
__int64 __fastcall UnionFs::UfsPathTable::Traverse(
        __int64 a1,
        __int64 a2,
        const char *a3,
        int a4,
        __int64 a5,
        __int64 a6)
{
  char v6; // r13
  struct _ERESOURCE *v10; // rbx
  __int64 v11; // rdx
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v12; // rdx
  __int64 *i; // rdi
  struct _UNICODE_STRING *v14; // r8
  unsigned __int16 v15; // r9
  bool v16; // al
  __int64 v17; // r14
  volatile signed __int32 *v18; // rsi
  NTSTATUS appended; // esi
  struct _UNICODE_STRING *v20; // rdx
  struct FsFltWil::Details::RundownRefCacheAware *v21; // rdx
  __int64 v23; // rcx
  struct _UNICODE_STRING *v24; // rdx
  UnionFs::UfsPathTree *v25; // r13
  utl::_RefCountBase *v26; // rcx
  struct UnionFs::UfsPathTierNode *Node; // rdi
  volatile signed __int32 *v28; // r15
  UnionFs::UfsPathTree *v29; // r8
  volatile signed __int32 *v30; // r14
  const char *v31; // r15
  int v32; // eax
  NTSTATUS v33; // r15d
  struct _UNICODE_STRING *v34; // r8
  bool v35; // al
  UnionFs::UfsPathTree *v36; // rcx
  volatile signed __int32 *v37; // rdx
  utl::_RefCountBase *v38; // rcx
  __int64 v39; // rcx
  struct _UNICODE_STRING *v40; // rdx
  int v41; // r9d
  struct FsFltWil::Details::RundownRefCacheAware *v42; // rdx
  const char *v43; // rax
  __int64 v44; // r8
  struct FsFltWil::Details::RundownRefCacheAware *v45; // rdx
  struct _UNICODE_STRING *v46; // rdx
  int v47; // r8d
  int v48; // r9d
  const struct _UNICODE_STRING *v49; // rax
  struct FsFltWil::Details::RundownRefCacheAware *v50; // rdx
  struct FsFltWil::Details::RundownRefCacheAware *v51; // rdx
  const char *v52; // [rsp+28h] [rbp-D8h]
  __int16 v53[2]; // [rsp+40h] [rbp-C0h] BYREF
  int v54; // [rsp+44h] [rbp-BCh] BYREF
  struct _ERESOURCE *v55; // [rsp+48h] [rbp-B8h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v57; // [rsp+60h] [rbp-A0h] BYREF
  const char *v58; // [rsp+70h] [rbp-90h] BYREF
  __int64 v59; // [rsp+78h] [rbp-88h]
  __int128 v60; // [rsp+80h] [rbp-80h] BYREF
  __int64 v61; // [rsp+90h] [rbp-70h] BYREF
  __int64 v62; // [rsp+98h] [rbp-68h]
  char v63; // [rsp+A0h] [rbp-60h]
  struct _UNICODE_STRING *p_Destination; // [rsp+A8h] [rbp-58h]
  __int128 v65; // [rsp+B0h] [rbp-50h]
  int v66; // [rsp+C0h] [rbp-40h]
  struct _UNICODE_STRING v67; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v68; // [rsp+148h] [rbp+48h]
  _QWORD v69[16]; // [rsp+150h] [rbp+50h] BYREF
  __int64 v70; // [rsp+1D0h] [rbp+D0h]

  v6 = a4;
  v54 = a4;
  v58 = a3;
  v59 = a5;
  v10 = 0;
  if ( (a4 & 8) == 0 )
  {
    v11 = a1 + 32;
    if ( (a4 & 4) != 0 )
      FsFltWil::AcquireResourceExclusive(&v55, v11);
    else
      FsFltWil::AcquireResourceShared(&v55, v11);
    v10 = v55;
  }
  v12 = *(struct _EX_RUNDOWN_REF_CACHE_AWARE **)(a1 + 136);
  v68 = 0;
  FsFltWil::AcquireRundownReference(v69, v12);
  if ( !v69[0] )
  {
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC0ED000ALL,
      a6,
      (struct UnionFs::StackEventTracer *)0x45200140B31LL,
      (unsigned __int64)"UnionFs::UfsPathTable::Traverse",
      "ORIGIN: Table already run down",
      v52);
    FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v69, v51);
    if ( v70 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v70 + 24LL))(v70);
    if ( v10 )
    {
      ExReleaseResourceLite(v10);
      KeLeaveCriticalRegion();
    }
    return 3236757514LL;
  }
  for ( i = *(__int64 **)(a1 + 8); ; i = (__int64 *)*i )
  {
    if ( i == (__int64 *)(a1 + 8) )
    {
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC0000225LL,
        a6,
        (struct UnionFs::StackEventTracer *)0x31C00140B44LL,
        (unsigned __int64)"UnionFs::UfsPathTable::Traverse",
        "ORIGIN: Traversal on volume with no paths.",
        v52);
LABEL_99:
      FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v69, v50);
      if ( v70 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v70 + 24LL))(v70);
      if ( v10 )
      {
        ExReleaseResourceLite(v10);
        KeLeaveCriticalRegion();
      }
      return 3221226021LL;
    }
    if ( *(_QWORD *)i[3] == a2 )
      break;
  }
  FsFltWil::MakeUniqueUnicodeString(&Destination, *((unsigned __int16 *)i + 16), 1279685446);
  v14 = (struct _UNICODE_STRING *)*((unsigned __int16 *)a3 + 12);
  v57 = *(_OWORD *)a3;
  v67 = 0;
  v16 = UnionFs::Utils::WalkPath((UnionFs::Utils *)&v57, &v67, v14, v15);
  v17 = i[2];
  v18 = 0;
  LOBYTE(v53[0]) = v16;
  if ( !v67.Length )
  {
    appended = RtlAppendUnicodeStringToString(&Destination, (PCUNICODE_STRING)(v17 + 32));
    if ( appended < 0 )
    {
      UnionFs::ProcessTraceStatusFromApi(
        (UnionFs *)(unsigned int)appended,
        a6,
        (struct UnionFs::StackEventTracer *)0x31D00140B5CLL,
        (unsigned __int64)"UnionFs::UfsPathTable::Traverse",
        "API: Appending volume root to currentPath",
        v52);
LABEL_14:
      FsFltWil::Details::FreeUnicodeString(&Destination, v20);
      FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v69, v21);
      if ( v70 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v70 + 24LL))(v70);
      if ( v10 )
      {
        ExReleaseResourceLite(v10);
        KeLeaveCriticalRegion();
      }
      return (unsigned int)appended;
    }
    if ( (v6 & 2) == 0 )
    {
      p_Destination = &Destination;
      v61 = v59;
      v62 = a6;
      v23 = *(_QWORD *)(v59 + 112);
      v63 = 0;
      v66 = 0;
      v55 = 0;
      v65 = 0;
      if ( !v23 )
        wistd::__throw_bad_function_call(0);
      appended = (*(__int64 (__fastcall **)(__int64, __int64, struct _ERESOURCE **, __int64 *))(*(_QWORD *)v23 + 32LL))(
                   v23,
                   v17,
                   &v55,
                   &v61);
      if ( appended < 0 )
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)appended,
          a6,
          (struct UnionFs::StackEventTracer *)0x31E00140B65LL,
          (unsigned __int64)"UnionFs::UfsPathTable::Traverse",
          "PUSH: TraverseCallback on volume root node",
          v52);
        goto LABEL_14;
      }
      if ( (unsigned int)(v66 - 1) <= 1 )
        goto LABEL_72;
    }
    v25 = *(UnionFs::UfsPathTree **)(v17 + 48);
    v18 = *(volatile signed __int32 **)(v17 + 56);
    if ( (*(_DWORD *)a1 & 2) == 0 )
    {
      if ( v18 )
        _InterlockedIncrement(v18 + 2);
      if ( !UnionFs::UfsPathTree::IsEmpty(v25) )
        MicrosoftTelemetryAssertTriggeredMsgKM("volumeRootNode->GetDescendantTree()->IsEmpty()");
      goto LABEL_29;
    }
    if ( v18 )
      _InterlockedIncrement(v18 + 2);
    if ( v25 )
    {
      Node = 0;
      v28 = v18;
LABEL_65:
      if ( !UnionFs::UfsPathTree::IsEmpty(v25) )
      {
        v61 = v59;
        v62 = a6;
        p_Destination = &Destination;
        v63 = v41;
        v65 = 0;
        v66 = v41;
        appended = UnionFs::UfsPathTree::WalkTree(v25, (struct UnionFs::UFS_TABLE_TRAVERSE_CTX *)&v61, Node);
        if ( appended < 0 )
        {
          UnionFs::ProcessTraceStatusPushLocation(
            (UnionFs *)(unsigned int)appended,
            a6,
            (struct UnionFs::StackEventTracer *)0x31F00140BE6LL,
            (unsigned __int64)"UnionFs::UfsPathTable::Traverse",
            "PUSH: Walking from starting location",
            v52);
          if ( v28 )
            utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v28);
          goto LABEL_14;
        }
      }
LABEL_69:
      if ( v28 )
      {
        v26 = (utl::_RefCountBase *)v28;
LABEL_71:
        utl::_RefCountBase::_DecStrong(v26);
      }
      goto LABEL_72;
    }
    v6 = v54;
  }
  v29 = *(UnionFs::UfsPathTree **)(v17 + 48);
  v30 = *(volatile signed __int32 **)(v17 + 56);
  v55 = (struct _ERESOURCE *)v29;
  if ( v30 )
    _InterlockedIncrement(v30 + 2);
  v31 = v58;
  v32 = v6 & 1;
  Node = 0;
  v54 = v32;
  while ( 2 )
  {
    *(_QWORD *)&v60 = Node;
    BYTE8(v57) = v32 != 0;
    *(_QWORD *)&v57 = &v67;
    *(_DWORD *)((char *)&v57 + 9) = 0;
    *(_WORD *)((char *)&v57 + 13) = 0;
    HIBYTE(v57) = 0;
    Node = UnionFs::UfsPathTree::FindNode(v29, (const struct UnionFs::UFS_COMPARE_KEY *)&v57);
    if ( !Node )
    {
      v57 = *(_OWORD *)(v31 + 40);
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC0000225LL,
        a6,
        (struct UnionFs::StackEventTracer *)0x17000140BD3LL,
        (unsigned __int64)"UnionFs::UfsPathTable::Traverse",
        "ORIGIN: StartingPath is not in the table",
        v52);
      if ( (unsigned int)dword_14009E178 > 2 )
      {
        v49 = (const struct _UNICODE_STRING *)&v57;
        v54 = 368;
        if ( !*((_QWORD *)&v57 + 1) )
          v49 = &FsTlEmptyUnicodeString;
        v58 = "UnionFs::UfsPathTable::Traverse";
        *(_QWORD *)&v60 = v49;
        v53[0] = 3027;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapBuffer<_UNICODE_STRING>>(
          (unsigned int)&FsTlEmptyUnicodeString,
          (unsigned int)&unk_140097BF0,
          v47,
          v48,
          (__int64)&v58,
          (__int64)&v54,
          (__int64)v53,
          (__int64)&v60);
      }
      if ( v30 )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v30);
      if ( v18 )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v18);
      FsFltWil::Details::FreeUnicodeString(&Destination, v46);
      goto LABEL_99;
    }
    v33 = RtlAppendUnicodeToString(&Destination, L"\\");
    if ( v33 < 0 )
    {
      v43 = "API: Appending \\ to currentPath";
      v44 = 0x18200140B96LL;
      goto LABEL_79;
    }
    v33 = RtlAppendUnicodeStringToString(&Destination, (PCUNICODE_STRING)Node + 2);
    if ( v33 < 0 )
    {
      v43 = "API: Appending path component to currentPath";
      v44 = 0x18600140B9CLL;
LABEL_79:
      UnionFs::ProcessTraceStatusFromApi(
        (UnionFs *)(unsigned int)v33,
        a6,
        (struct UnionFs::StackEventTracer *)v44,
        (unsigned __int64)"UnionFs::UfsPathTable::Traverse",
        v43,
        v52);
      goto LABEL_80;
    }
    if ( LOBYTE(v53[0]) )
    {
      v31 = v58;
      v34 = (struct _UNICODE_STRING *)*((unsigned __int16 *)v58 + 12);
      v60 = *(_OWORD *)v58;
      v35 = UnionFs::Utils::WalkPath((UnionFs::Utils *)&v60, &v67, v34, 0);
      v36 = (UnionFs::UfsPathTree *)*((_QWORD *)Node + 6);
      LOBYTE(v53[0]) = v35;
      if ( !v36 )
        goto LABEL_48;
      v37 = (volatile signed __int32 *)*((_QWORD *)Node + 7);
      if ( v37 )
        _InterlockedIncrement(v37 + 2);
      v29 = v36;
      v55 = (struct _ERESOURCE *)v36;
      v38 = (utl::_RefCountBase *)v30;
      v30 = v37;
      if ( v38 )
      {
        utl::_RefCountBase::_DecStrong(v38);
LABEL_48:
        v29 = (UnionFs::UfsPathTree *)v55;
      }
      v32 = v54;
      continue;
    }
    break;
  }
  if ( (*((_DWORD *)Node + 6) & 1) != 0 || (v6 & 2) != 0 )
    goto LABEL_58;
  v61 = v59;
  p_Destination = &Destination;
  v39 = *(_QWORD *)(v59 + 112);
  v62 = a6;
  v63 = 0;
  v66 = 0;
  v65 = 0;
  if ( !v39 )
    wistd::__throw_bad_function_call(0);
  v33 = (*(__int64 (__fastcall **)(__int64, struct UnionFs::UfsPathTierNode *, __int128 *, __int64 *))(*(_QWORD *)v39 + 32LL))(
          v39,
          Node,
          &v60,
          &v61);
  if ( v33 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v33,
      a6,
      (struct UnionFs::StackEventTracer *)0x16900140BACLL,
      (unsigned __int64)"UnionFs::UfsPathTable::Traverse",
      "PUSH: TraverseCallback on starting location",
      v52);
LABEL_80:
    if ( v30 )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v30);
    if ( v18 )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v18);
    FsFltWil::Details::FreeUnicodeString(&Destination, v40);
    FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v69, v45);
    if ( v70 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v70 + 24LL))(v70);
    if ( v10 )
    {
      ExReleaseResourceLite(v10);
      KeLeaveCriticalRegion();
    }
    return (unsigned int)v33;
  }
  if ( (unsigned int)(v66 - 1) > 1 )
  {
LABEL_58:
    v28 = (volatile signed __int32 *)*((_QWORD *)Node + 7);
    v25 = (UnionFs::UfsPathTree *)*((_QWORD *)Node + 6);
    if ( v28 )
      _InterlockedIncrement(v28 + 2);
    if ( v18 )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v18);
    if ( v30 )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v30);
    if ( v25 )
      goto LABEL_65;
    goto LABEL_69;
  }
  if ( v30 )
    utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v30);
LABEL_29:
  if ( v18 )
  {
    v26 = (utl::_RefCountBase *)v18;
    goto LABEL_71;
  }
LABEL_72:
  FsFltWil::Details::FreeUnicodeString(&Destination, v24);
  FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v69, v42);
  if ( v70 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v70 + 24LL))(v70);
  if ( v10 )
  {
    ExReleaseResourceLite(v10);
    KeLeaveCriticalRegion();
  }
  return 0;
}

```

## disassembly

```asm
0x14004eac4  mov     [rsp-8+arg_8], rbx
0x14004eac9  push    rbp
0x14004eaca  push    rsi
0x14004eacb  push    rdi
0x14004eacc  push    r12
0x14004eace  push    r13
0x14004ead0  push    r14
0x14004ead2  push    r15
0x14004ead4  lea     rbp, [rsp-0E0h]
0x14004eadc  sub     rsp, 1E0h
0x14004eae3  mov     rax, cs:__security_cookie
0x14004eaea  xor     rax, rsp
0x14004eaed  mov     [rbp+110h+var_38], rax
0x14004eaf4  mov     rax, [rbp+110h+arg_20]
0x14004eafb  xor     edi, edi
0x14004eafd  mov     r12, qword ptr [rbp+110h+arg_28]
0x14004eb04  mov     r13d, r9d
0x14004eb07  mov     [rsp+210h+var_1CC], r9d
0x14004eb0c  mov     r14, r8
0x14004eb0f  mov     [rsp+210h+var_1A0], r8
0x14004eb14  mov     rsi, rdx
0x14004eb17  mov     [rsp+210h+var_198], rax
0x14004eb1c  mov     r15, rcx
0x14004eb1f  mov     ebx, edi
0x14004eb21  test    r9b, 8
0x14004eb25  jnz     short loc_14004EB47
0x14004eb27  lea     rdx, [rcx+20h]
0x14004eb2b  lea     rcx, [rsp+210h+var_1C8]
0x14004eb30  test    r13b, 4
0x14004eb34  jz      short loc_14004EB3D
0x14004eb36  call    ?AcquireResourceExclusive@FsFltWil@@YA?AV?$unique_ptr@U_ERESOURCE@@U?$function_deleter@P6AXPEAU_ERESOURCE@@@Z$1?ReleaseResource@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEAU_ERESOURCE@@@Z; FsFltWil::AcquireResourceExclusive(_ERESOURCE &)
0x14004eb3b  jmp     short loc_14004EB42
0x14004eb3d  call    ?AcquireResourceShared@FsFltWil@@YA?AV?$unique_ptr@U_ERESOURCE@@U?$function_deleter@P6AXPEAU_ERESOURCE@@@Z$1?ReleaseResource@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEAU_ERESOURCE@@@Z; FsFltWil::AcquireResourceShared(_ERESOURCE &)
0x14004eb42  mov     rbx, [rsp+210h+var_1C8]
0x14004eb47  mov     rdx, [r15+88h]; RunRefCacheAware
0x14004eb4e  lea     r9, [rbp+110h+var_138]
0x14004eb52  mov     r8b, 1
0x14004eb55  mov     [rbp+110h+var_C8], rdi
0x14004eb59  lea     rcx, [rbp+110h+var_C0]; void *
0x14004eb5d  call    ?AcquireRundownReference@FsFltWil@@YA?AV?$unique_struct@URundownRefCacheAware@Details@FsFltWil@@P6AXPEAU123@@Z$1?ReleaseRundownProtectionCacheAware@23@YAX0@Z$$T$0A@@wil@@PEAU_EX_RUNDOWN_REF_CACHE_AWARE@@_NV?$function@$$A6AX_N@Z@wistd@@@Z; FsFltWil::AcquireRundownReference(_EX_RUNDOWN_REF_CACHE_AWARE *,bool,wistd::function<void (bool)>)
0x14004eb62  cmp     [rbp+110h+var_C0], rdi
0x14004eb66  jz      loc_14004F243
0x14004eb6c  lea     rax, [r15+8]
0x14004eb70  mov     rdi, [rax]
0x14004eb73  cmp     rdi, rax
0x14004eb76  jz      loc_14004F1D1
0x14004eb7c  mov     rcx, [rdi+18h]
0x14004eb80  cmp     [rcx], rsi
0x14004eb83  jz      short loc_14004EB8A
0x14004eb85  mov     rdi, [rdi]
0x14004eb88  jmp     short loc_14004EB73
0x14004eb8a  movzx   edx, word ptr [rdi+20h]
0x14004eb8e  lea     rcx, [rsp+210h+Destination]
0x14004eb93  mov     r8d, 4C467346h
0x14004eb99  call    ?MakeUniqueUnicodeString@FsFltWil@@YA?AV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@GKW4FSFLT_ALLOC_TYPE@@@Z; FsFltWil::MakeUniqueUnicodeString(ushort,ulong,FSFLT_ALLOC_TYPE)
0x14004eb9e  movups  xmm1, xmmword ptr [r14]
0x14004eba2  movzx   r8d, word ptr [r14+18h]; struct _UNICODE_STRING *
0x14004eba7  lea     rdx, [rbp+110h+var_148]; struct _UNICODE_STRING *
0x14004ebab  xorps   xmm0, xmm0
0x14004ebae  lea     rcx, [rsp+210h+var_1B0]; this
0x14004ebb3  movdqu  [rsp+210h+var_1B0], xmm1
0x14004ebb9  movups  xmmword ptr [rbp+110h+var_148.Length], xmm0
0x14004ebbd  call    ?WalkPath@Utils@UnionFs@@YA_NAEBU_UNICODE_STRING@@AEAU3@G@Z; UnionFs::Utils::WalkPath(_UNICODE_STRING const &,_UNICODE_STRING &,ushort)
0x14004ebc2  mov     r14, [rdi+10h]
0x14004ebc6  xor     r9d, r9d
0x14004ebc9  mov     esi, r9d
0x14004ebcc  mov     byte ptr [rsp+210h+var_1D0], al
0x14004ebd0  cmp     [rbp+110h+var_148.Length], r9w
0x14004ebd5  jnz     loc_14004ED6E
0x14004ebdb  lea     rdx, [r14+20h]; Source
0x14004ebdf  lea     rcx, [rsp+210h+Destination]; Destination
0x14004ebe4  call    cs:__imp_RtlAppendUnicodeStringToString
0x14004ebeb  nop     dword ptr [rax+rax+00h]
0x14004ebf0  xor     r9d, r9d
0x14004ebf3  mov     esi, eax
0x14004ebf5  test    eax, eax
0x14004ebf7  jns     short loc_14004EC72
0x14004ebf9  lea     rax, aApiAppendingVo; "API: Appending volume root to currentPa"...
0x14004ec00  mov     r8, 31D00140B5Ch; struct UnionFs::StackEventTracer *
0x14004ec0a  lea     r9, aUnionfsUfspath_63; "UnionFs::UfsPathTable::Traverse"
0x14004ec11  mov     [rsp+210h+var_1F0], rax; char *
0x14004ec16  mov     rdx, r12; int
0x14004ec19  mov     ecx, esi; this
0x14004ec1b  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14004ec20  lea     rcx, [rsp+210h+Destination]; UnicodeString
0x14004ec25  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14004ec2a  lea     rcx, [rbp+110h+var_C0]; this
0x14004ec2e  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
0x14004ec33  mov     rcx, [rbp+110h+var_40]
0x14004ec3a  test    rcx, rcx
0x14004ec3d  jz      short loc_14004EC4B
0x14004ec3f  mov     rax, [rcx]
0x14004ec42  mov     rax, [rax+18h]
0x14004ec46  call    _guard_dispatch_icall
0x14004ec4b  test    rbx, rbx
0x14004ec4e  jz      short loc_14004EC6B
0x14004ec50  mov     rcx, rbx; Resource
0x14004ec53  call    cs:__imp_ExReleaseResourceLite
0x14004ec5a  nop     dword ptr [rax+rax+00h]
0x14004ec5f  call    cs:__imp_KeLeaveCriticalRegion
0x14004ec66  nop     dword ptr [rax+rax+00h]
0x14004ec6b  mov     eax, esi
0x14004ec6d  jmp     loc_14004F2B2
0x14004ec72  test    r13b, 2
0x14004ec76  jnz     loc_14004ED0F
0x14004ec7c  mov     rax, [rsp+210h+var_198]
0x14004ec81  lea     rcx, [rsp+210h+Destination]
0x14004ec86  mov     [rbp+110h+var_168], rcx
0x14004ec8a  xorps   xmm0, xmm0
0x14004ec8d  mov     [rbp+110h+var_180], rax
0x14004ec91  mov     [rbp+110h+var_178], r12
0x14004ec95  mov     rcx, [rax+70h]; this
0x14004ec99  mov     [rbp+110h+var_170], r9b
0x14004ec9d  mov     [rbp+110h+var_150], r9d
0x14004eca1  mov     [rsp+210h+var_1C8], r9
0x14004eca6  movdqu  [rbp+110h+var_160], xmm0
0x14004ecab  test    rcx, rcx
0x14004ecae  jz      loc_14004F2E3
0x14004ecb4  mov     rax, [rcx]
0x14004ecb7  lea     r9, [rbp+110h+var_180]
0x14004ecbb  lea     r8, [rsp+210h+var_1C8]
0x14004ecc0  mov     rdx, r14
0x14004ecc3  mov     rax, [rax+20h]
0x14004ecc7  call    _guard_dispatch_icall
0x14004eccc  xor     r9d, r9d
0x14004eccf  mov     esi, eax
0x14004ecd1  test    eax, eax
0x14004ecd3  jns     short loc_14004ED01
0x14004ecd5  lea     rax, aPushTraverseca; "PUSH: TraverseCallback on volume root n"...
0x14004ecdc  mov     r8, 31E00140B65h; struct UnionFs::StackEventTracer *
0x14004ece6  lea     r9, aUnionfsUfspath_63; "UnionFs::UfsPathTable::Traverse"
0x14004eced  mov     [rsp+210h+var_1F0], rax; char *
0x14004ecf2  mov     rdx, r12; int
0x14004ecf5  mov     ecx, esi; this
0x14004ecf7  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14004ecfc  jmp     loc_14004EC20
0x14004ed01  mov     eax, [rbp+110h+var_150]
0x14004ed04  dec     eax
0x14004ed06  cmp     eax, 1
0x14004ed09  jbe     loc_14004F00A
0x14004ed0f  mov     eax, [r15]
0x14004ed12  mov     r13, [r14+30h]
0x14004ed16  mov     rsi, [r14+38h]
0x14004ed1a  test    al, 2
0x14004ed1c  jnz     short loc_14004ED50
0x14004ed1e  test    rsi, rsi
0x14004ed21  jz      short loc_14004ED27
0x14004ed23  lock inc dword ptr [rsi+8]
0x14004ed27  mov     rcx, r13; this
0x14004ed2a  call    ?IsEmpty@UfsPathTree@UnionFs@@QEAA_NXZ; UnionFs::UfsPathTree::IsEmpty(void)
0x14004ed2f  test    al, al
0x14004ed31  jnz     short loc_14004ED3F
0x14004ed33  lea     rcx, aVolumerootnode; "volumeRootNode->GetDescendantTree()->Is"...
0x14004ed3a  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x14004ed3f  test    rsi, rsi
0x14004ed42  jz      loc_14004F00A
0x14004ed48  mov     rcx, rsi
0x14004ed4b  jmp     loc_14004F005
0x14004ed50  test    rsi, rsi
0x14004ed53  jz      short loc_14004ED59
0x14004ed55  lock inc dword ptr [rsi+8]
0x14004ed59  test    r13, r13
0x14004ed5c  jz      short loc_14004ED69
0x14004ed5e  mov     rdi, r9
0x14004ed61  mov     r15, rsi
0x14004ed64  jmp     loc_14004EF79
0x14004ed69  mov     r13d, [rsp+210h+var_1CC]
0x14004ed6e  mov     r8, [r14+30h]
0x14004ed72  mov     r14, [r14+38h]
0x14004ed76  mov     [rsp+210h+var_1C8], r8
0x14004ed7b  test    r14, r14
0x14004ed7e  jz      short loc_14004ED85
0x14004ed80  lock inc dword ptr [r14+8]
0x14004ed85  mov     r15, [rsp+210h+var_1A0]
0x14004ed8a  mov     eax, r13d
0x14004ed8d  and     eax, 1
0x14004ed90  mov     rdi, r9
0x14004ed93  mov     [rsp+210h+var_1CC], eax
0x14004ed97  test    eax, eax
0x14004ed99  mov     qword ptr [rbp+110h+var_190], rdi
0x14004ed9d  lea     rcx, [rbp+110h+var_148]
0x14004eda1  setnz   byte ptr [rsp+210h+var_1B0+8]
0x14004eda6  mov     qword ptr [rsp+210h+var_1B0], rcx
0x14004edab  xor     eax, eax
0x14004edad  lea     rdx, [rsp+210h+var_1B0]; struct UnionFs::UFS_COMPARE_KEY *
0x14004edb2  mov     rcx, r8; this
0x14004edb5  mov     dword ptr [rsp+210h+var_1B0+9], eax
0x14004edb9  mov     word ptr [rsp+210h+var_1B0+0Dh], ax
0x14004edbe  mov     byte ptr [rsp+210h+var_1B0+0Fh], al
0x14004edc2  call    ?FindNode@UfsPathTree@UnionFs@@QEAAPEAVUfsPathTierNode@2@AEBUUFS_COMPARE_KEY@2@@Z; UnionFs::UfsPathTree::FindNode(UnionFs::UFS_COMPARE_KEY const &)
0x14004edc7  mov     rdi, rax
0x14004edca  test    rax, rax
0x14004edcd  jz      loc_14004F104
0x14004edd3  lea     rdx, Source; "\\"
0x14004edda  lea     rcx, [rsp+210h+Destination]; Destination
0x14004eddf  call    cs:__imp_RtlAppendUnicodeToString
0x14004ede6  nop     dword ptr [rax+rax+00h]
0x14004edeb  mov     r15d, eax
0x14004edee  test    eax, eax
0x14004edf0  js      loc_14004F06F
0x14004edf6  lea     rdx, [rdi+20h]; Source
0x14004edfa  lea     rcx, [rsp+210h+Destination]; Destination
0x14004edff  call    cs:__imp_RtlAppendUnicodeStringToString
0x14004ee06  nop     dword ptr [rax+rax+00h]
0x14004ee0b  xor     r9d, r9d; unsigned __int16
0x14004ee0e  mov     r15d, eax
0x14004ee11  test    eax, eax
0x14004ee13  js      loc_14004F05C
0x14004ee19  cmp     byte ptr [rsp+210h+var_1D0], r9b
0x14004ee1e  jz      short loc_14004EE80
0x14004ee20  mov     r15, [rsp+210h+var_1A0]
0x14004ee25  lea     rdx, [rbp+110h+var_148]; struct _UNICODE_STRING *
0x14004ee29  lea     rcx, [rbp+110h+var_190]; this
0x14004ee2d  movups  xmm0, xmmword ptr [r15]
0x14004ee31  movzx   r8d, word ptr [r15+18h]; struct _UNICODE_STRING *
0x14004ee36  movdqu  [rbp+110h+var_190], xmm0
0x14004ee3b  call    ?WalkPath@Utils@UnionFs@@YA_NAEBU_UNICODE_STRING@@AEAU3@G@Z; UnionFs::Utils::WalkPath(_UNICODE_STRING const &,_UNICODE_STRING &,ushort)
0x14004ee40  mov     rcx, [rdi+30h]
0x14004ee44  mov     byte ptr [rsp+210h+var_1D0], al
0x14004ee48  test    rcx, rcx
0x14004ee4b  jz      short loc_14004EE72
0x14004ee4d  mov     rdx, [rdi+38h]
0x14004ee51  test    rdx, rdx
0x14004ee54  jz      short loc_14004EE5A
0x14004ee56  lock inc dword ptr [rdx+8]
0x14004ee5a  mov     r8, rcx
0x14004ee5d  mov     [rsp+210h+var_1C8], rcx
0x14004ee62  mov     rcx, r14; this
0x14004ee65  mov     r14, rdx
0x14004ee68  test    rcx, rcx
0x14004ee6b  jz      short loc_14004EE77
0x14004ee6d  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14004ee72  mov     r8, [rsp+210h+var_1C8]
0x14004ee77  mov     eax, [rsp+210h+var_1CC]
0x14004ee7b  jmp     loc_14004ED97
0x14004ee80  mov     eax, [rdi+18h]
0x14004ee83  test    al, 1
0x14004ee85  jnz     loc_14004EF3E
0x14004ee8b  test    r13b, 2
0x14004ee8f  jnz     loc_14004EF3E
0x14004ee95  mov     rcx, [rsp+210h+var_198]
0x14004ee9a  lea     rax, [rsp+210h+Destination]
0x14004ee9f  mov     [rbp+110h+var_180], rcx
0x14004eea3  xorps   xmm0, xmm0
0x14004eea6  mov     [rbp+110h+var_168], rax
0x14004eeaa  mov     rax, qword ptr [rbp+110h+var_190]
0x14004eeae  mov     rcx, [rcx+70h]; this
0x14004eeb2  mov     [rbp+110h+var_178], r12
0x14004eeb6  mov     [rbp+110h+var_170], r9b
0x14004eeba  mov     [rbp+110h+var_150], r9d
0x14004eebe  mov     qword ptr [rbp+110h+var_190], rax
0x14004eec2  movdqu  [rbp+110h+var_160], xmm0
0x14004eec7  test    rcx, rcx
0x14004eeca  jz      loc_14004F2DD
0x14004eed0  mov     rax, [rcx]
0x14004eed3  lea     r9, [rbp+110h+var_180]
0x14004eed7  lea     r8, [rbp+110h+var_190]
0x14004eedb  mov     rdx, rdi
0x14004eede  mov     rax, [rax+20h]
0x14004eee2  call    _guard_dispatch_icall
0x14004eee7  xor     r9d, r9d
0x14004eeea  mov     r15d, eax
0x14004eeed  test    eax, eax
0x14004eeef  jns     short loc_14004EF1E
0x14004eef1  lea     rax, aPushTraverseca_0; "PUSH: TraverseCallback on starting loca"...
0x14004eef8  mov     r8, 16900140BACh; struct UnionFs::StackEventTracer *
0x14004ef02  lea     r9, aUnionfsUfspath_63; "UnionFs::UfsPathTable::Traverse"
0x14004ef09  mov     [rsp+210h+var_1F0], rax; char *
0x14004ef0e  mov     rdx, r12; int
0x14004ef11  mov     ecx, r15d; this
0x14004ef14  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14004ef19  jmp     loc_14004F097
0x14004ef1e  mov     eax, [rbp+110h+var_150]
0x14004ef21  dec     eax
0x14004ef23  cmp     eax, 1
0x14004ef26  ja      short loc_14004EF3E
0x14004ef28  test    r14, r14
0x14004ef2b  jz      loc_14004ED3F
0x14004ef31  mov     rcx, r14; this
0x14004ef34  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14004ef39  jmp     loc_14004ED3F
0x14004ef3e  mov     r15, [rdi+38h]
0x14004ef42  mov     r13, [rdi+30h]
0x14004ef46  test    r15, r15
0x14004ef49  jz      short loc_14004EF50
0x14004ef4b  lock inc dword ptr [r15+8]
0x14004ef50  test    rsi, rsi
0x14004ef53  jz      short loc_14004EF60
0x14004ef55  mov     rcx, rsi; this
0x14004ef58  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14004ef5d  xor     r9d, r9d
0x14004ef60  test    r14, r14
0x14004ef63  jz      short loc_14004EF70
0x14004ef65  mov     rcx, r14; this
0x14004ef68  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14004ef6d  xor     r9d, r9d
0x14004ef70  test    r13, r13
0x14004ef73  jz      loc_14004EFFD
0x14004ef79  mov     rcx, r13; this
0x14004ef7c  call    ?IsEmpty@UfsPathTree@UnionFs@@QEAA_NXZ; UnionFs::UfsPathTree::IsEmpty(void)
  ... truncated ...
```
