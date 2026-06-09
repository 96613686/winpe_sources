# UnionFs::UfsUnionCtx::RemoveUnion(UnionFs::UfsUnionCtx::RemoveUnionReason,UnionFs::StackEventTracer &,wistd::function<long (UnionFs::UfsUnionCtx &,bool *,UnionFs::StackEventTracer &)>)

- ea: `0x1400636bc`
- end: `0x140064368`
- name: `?RemoveUnion@UfsUnionCtx@UnionFs@@QEAAJW4RemoveUnionReason@12@AEAVStackEventTracer@2@V?$function@$$A6AJAEAVUfsUnionCtx@UnionFs@@PEA_NAEAVStackEventTracer@2@@Z@wistd@@@Z`
- size: `3244`
- prototype: `__int64 __fastcall(struct UnionFs::UfsUnionCtx *)`
- caller_count: `4`
- callee_count: `19`
- tags: `registry_config`

## callers

- `0x1400086b0`
- `0x14000e56c`
- `0x14002a380`
- `0x140062e54`

## callees

- `0x140001754`
- `0x140001b64`
- `0x1400031a0`
- `0x140009650`
- `0x14000f7fc`
- `0x140028588`
- `0x14003d188`
- `0x140052388`
- `0x1400567f4`
- `0x140056afc`
- `0x14005d400`
- `0x14005f920`
- `0x14005fd34`
- `0x140063344`
- `0x1400636bc`
- `0x1400799dc`
- `0x140079d74`
- `0x14007b7d0`
- `0x14007b8b0`

## import_xrefs

- `ntoskrnl!KeReleaseSemaphore` at `0x1400638b4`
- `ntoskrnl!KeReleaseSemaphore` at `0x1400639a6`
- `ntoskrnl!KeReleaseSemaphore` at `0x140063e57`
- `ntoskrnl!KeReleaseSemaphore` at `0x140063f2d`
- `ntoskrnl!KeReleaseSemaphore` at `0x1400642d8`
- `ntoskrnl!KeReleaseSemaphore` at `0x1400638b4`
- `ntoskrnl!KeReleaseSemaphore` at `0x1400639a6`
- `ntoskrnl!KeReleaseSemaphore` at `0x140063e57`
- `ntoskrnl!KeReleaseSemaphore` at `0x140063f2d`
- `ntoskrnl!KeReleaseSemaphore` at `0x1400642d8`
- `ntoskrnl!KeWaitForSingleObject` at `0x14006370f`
- `ntoskrnl!KeWaitForSingleObject` at `0x14006370f`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x1400638d0`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x1400638d0`

## string_xrefs

- `0x140063728`: `UnionFs::UfsUnionCtx::RemoveUnion`
- `0x1400637f7`: `UnionFs::UfsUnionCtx::RemoveUnion`
- `0x140063923`: `UnionFs::UfsUnionCtx::RemoveUnion`
- `0x1400639ce`: `UnionFs::UfsUnionCtx::RemoveUnion`
- `0x140063a11`: `UnionFs::UfsUnionCtx::RemoveUnion`
- `0x140063ab7`: `UnionFs::UfsUnionCtx::RemoveUnion`
- `0x140063b3d`: `UnionFs::UfsUnionCtx::RemoveUnion`
- `0x140063b80`: `UnionFs::UfsUnionCtx::RemoveUnion`
- `0x140063c10`: `UnionFs::UfsUnionCtx::RemoveUnion`
- `0x140063c5a`: `UnionFs::UfsUnionCtx::RemoveUnion`
- `0x140063c9d`: `UnionFs::UfsUnionCtx::RemoveUnion`
- `0x140063d30`: `UnionFs::UfsUnionCtx::RemoveUnion`
- `0x140063dcb`: `UnionFs::UfsUnionCtx::RemoveUnion`
- `0x140063ecc`: `UnionFs::UfsUnionCtx::RemoveUnion`
- `0x140063f57`: `UnionFs::UfsUnionCtx::RemoveUnion`
- `0x140063f99`: `UnionFs::UfsUnionCtx::RemoveUnion`
- `0x14006401b`: `UnionFs::UfsUnionCtx::RemoveUnion`
- `0x140064090`: `UnionFs::UfsUnionCtx::RemoveUnion`
- `0x1400640d2`: `UnionFs::UfsUnionCtx::RemoveUnion`
- `0x140064140`: `UnionFs::UfsUnionCtx::RemoveUnion`
- `0x140063858`: `Union already removed`
- `0x140063909`: `PUSH: RemoveUnionFromScratchMapping`
- `0x140063ed8`: `RemoveUnion exiting before tearing down path cache`
- `0x140063dba`: `PUSH: Handling union configuration`
- `0x140064005`: `PUSH: Clearing path cache`

## pseudocode

```c
__int64 __fastcall UnionFs::UfsUnionCtx::RemoveUnion(
        struct UnionFs::UfsUnionCtx *a1,
        int a2,
        struct UnionFs::StackEventTracer *a3,
        __int64 a4)
{
  struct _KSEMAPHORE *v4; // r12
  char v9; // r13
  __int64 v10; // rcx
  int v11; // edi
  int v12; // ecx
  int v13; // r8d
  int v14; // r9d
  __int64 v15; // rcx
  int v17; // ecx
  int v18; // r8d
  int v19; // r9d
  int v20; // ecx
  int v21; // r8d
  int v22; // r9d
  char *v23; // rdx
  __int16 v24; // ax
  int v25; // ecx
  int v26; // r8d
  int v27; // r9d
  int v28; // ecx
  int v29; // r8d
  int v30; // r9d
  int v31; // eax
  __int64 *v32; // r15
  __int64 v33; // rcx
  int v34; // r8d
  int v35; // r9d
  int v36; // r8d
  int v37; // r9d
  int v38; // ecx
  int v39; // r8d
  int v40; // r9d
  int v41; // ecx
  int v42; // r8d
  int v43; // r9d
  int v44; // ecx
  int v45; // r8d
  int v46; // r9d
  int v47; // ecx
  int v48; // r8d
  int v49; // r9d
  int v50; // ecx
  int v51; // r8d
  int v52; // r9d
  unsigned __int64 *v53; // rdx
  __int64 v54; // rbx
  __int64 v55; // rdi
  __int64 v56; // rcx
  __int64 v57; // rdi
  __int64 v58; // rbx
  __int64 v59; // rbx
  utl::_RefCountBase *v60; // rcx
  UnionFs::UnionFsFilter *v61; // rcx
  UnionFs::UnionFsFilter *v62; // rcx
  unsigned __int64 *v63; // rdx
  const char *v64; // [rsp+28h] [rbp-D8h]
  char v65[8]; // [rsp+50h] [rbp-B0h] BYREF
  bool v66[8]; // [rsp+58h] [rbp-A8h] BYREF
  char v67[8]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v68[2]; // [rsp+68h] [rbp-98h] BYREF
  const char *v69; // [rsp+78h] [rbp-88h] BYREF
  FsFltWil::Details *v70; // [rsp+80h] [rbp-80h] BYREF
  int v71; // [rsp+89h] [rbp-77h]
  __int16 v72; // [rsp+8Dh] [rbp-73h]
  char v73; // [rsp+8Fh] [rbp-71h]
  struct UnionFs::UfsUnionCtx *v74; // [rsp+90h] [rbp-70h] BYREF
  char v75; // [rsp+98h] [rbp-68h]
  int v76; // [rsp+99h] [rbp-67h]
  __int16 v77; // [rsp+9Dh] [rbp-63h]
  char v78; // [rsp+9Fh] [rbp-61h]
  char v79; // [rsp+A0h] [rbp-60h]
  char v80; // [rsp+B0h] [rbp-50h] BYREF
  const char *v81; // [rsp+D0h] [rbp-30h]
  __int64 v82; // [rsp+D8h] [rbp-28h]
  const char *v83; // [rsp+E0h] [rbp-20h]
  __int64 v84; // [rsp+E8h] [rbp-18h]
  const char *v85; // [rsp+F0h] [rbp-10h]
  __int64 v86; // [rsp+F8h] [rbp-8h]
  bool *v87; // [rsp+100h] [rbp+0h]
  __int64 v88; // [rsp+108h] [rbp+8h]
  char *v89; // [rsp+110h] [rbp+10h]
  __int64 v90; // [rsp+118h] [rbp+18h]
  char *v91; // [rsp+120h] [rbp+20h]
  __int64 v92; // [rsp+128h] [rbp+28h]

  v4 = (struct _KSEMAPHORE *)((char *)a1 + 312);
  LODWORD(v69) = a2;
  v9 = 0;
  KeWaitForSingleObject((char *)a1 + 312, Executive, 0, 0, 0);
  if ( (unsigned int)dword_14009E178 > 4
    && (qword_14009E188 & 0x100) != 0
    && (qword_14009E190 & 0x100) == qword_14009E190 )
  {
    v85 = "onecore\\base\\fs\\unionfs\\sys\\unionctx.cpp";
    v91 = v65;
    v83 = "UnionFs::UfsUnionCtx::RemoveUnion";
    v89 = (char *)a1 + 8;
    *(_DWORD *)v65 = a2;
    v87 = v66;
    *(_DWORD *)v66 = 645;
    v81 = "Removing union";
    v92 = 4;
    v64 = &v80;
    v90 = 16;
    v88 = 4;
    v86 = 41;
    v84 = 34;
    v82 = 15;
    tlgWriteTransfer_EtwWriteTransfer(&dword_14009E178, &dword_1400991D4, 0, 0, 8);
  }
  if ( (*((_DWORD *)a1 + 6) & 0x10) != 0 )
  {
    if ( (unsigned int)dword_14009E178 > 4
      && (qword_14009E188 & 0x100) != 0
      && (qword_14009E190 & 0x100) == qword_14009E190 )
    {
      *(_QWORD *)v66 = "UnionFs::UfsUnionCtx::RemoveUnion";
      v69 = (char *)a1 + 8;
      *(_DWORD *)v65 = 652;
      v68[0] = "Union already removed";
      *(_QWORD *)v67 = "onecore\\base\\fs\\unionfs\\sys\\unionctx.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
        qword_14009E190,
        (unsigned int)&word_14009954E,
        256,
        (unsigned int)"onecore\\base\\fs\\unionfs\\sys\\unionctx.cpp",
        (__int64)v68,
        (__int64)v66,
        (__int64)v67,
        (__int64)v65,
        (__int64)&v69);
    }
    KeReleaseSemaphore(v4, 0, 1, 0);
    v10 = *(_QWORD *)(a4 + 112);
    goto LABEL_90;
  }
  ExWaitForRundownProtectionReleaseCacheAware(*((PEX_RUNDOWN_REF_CACHE_AWARE *)a1 + 38));
  *((_BYTE *)a1 + 120) = 0;
  if ( a2 == 1 || a2 == 2 )
    v9 = 1;
  v11 = UnionFs::UfsUnionCtx::RemoveScratchFromMappingTable(a1, a3);
  if ( v11 < 0 )
  {
    if ( !v9 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v11,
        (int)a3,
        (struct UnionFs::StackEventTracer *)0x2EA002002AALL,
        (unsigned __int64)"UnionFs::UfsUnionCtx::RemoveUnion",
        "PUSH: RemoveUnionFromScratchMapping",
        v64);
      if ( (unsigned int)dword_14009E178 > 4 )
      {
        *(_DWORD *)v65 = 746;
        v68[0] = (char *)a1 + 8;
        v69 = "UnionFs::UfsUnionCtx::RemoveUnion";
        *(_WORD *)v66 = 682;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByRef<16>>(
          v12,
          (unsigned int)&word_1400992E6,
          v13,
          v14,
          (__int64)&v69,
          (__int64)v65,
          (__int64)v66,
          (__int64)v68);
      }
      goto LABEL_18;
    }
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v11,
      (int)a3,
      (struct UnionFs::StackEventTracer *)0xC2002002B2LL,
      (unsigned __int64)"UnionFs::UfsUnionCtx::RemoveUnion",
      "PUSH: RemoveUnionFromScratchMapping",
      v64);
    if ( (unsigned int)dword_14009E178 > 4 )
    {
      *(_DWORD *)v65 = 194;
      v68[0] = (char *)a1 + 8;
      *(_WORD *)v66 = 690;
      *(_QWORD *)v67 = "UnionFs::UfsUnionCtx::RemoveUnion";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByRef<16>>(
        v17,
        (unsigned int)&unk_1400994A0,
        v18,
        v19,
        (__int64)v67,
        (__int64)v65,
        (__int64)v66,
        (__int64)v68);
    }
    UnionFs::StackEventTracer::LogError(a3);
    *(_DWORD *)a3 = 0;
    *((_WORD *)a3 + 274) = 0;
  }
  v76 = v71;
  v77 = v72;
  v78 = v73;
  v74 = a1;
  v75 = v9;
  v79 = 1;
  v66[0] = 0;
  v11 = UnionFs::UfsPathCache::ProcessSubtreeCollapseList(v66, a3);
  if ( v11 >= 0 )
  {
LABEL_34:
    v66[0] = 0;
    v11 = UnionFs::UfsPersistenceManager::PersistPayloadsForUnion(
            *((UnionFs::UfsPersistenceManager **)UnionFs::g_FilterState + 15),
            a1,
            v66,
            a3);
    if ( v11 < 0 )
    {
      if ( !v9 )
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)v11,
          (int)a3,
          (struct UnionFs::StackEventTracer *)0x2EB002002EFLL,
          (unsigned __int64)"UnionFs::UfsUnionCtx::RemoveUnion",
          "PUSH: Persisting tombstones for union",
          v64);
        if ( (unsigned int)dword_14009E178 <= 4 )
          goto LABEL_30;
        *(_DWORD *)v65 = 747;
        v68[0] = (char *)a1 + 8;
        v23 = byte_140099449;
        v24 = 751;
        goto LABEL_29;
      }
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v11,
        (int)a3,
        (struct UnionFs::StackEventTracer *)0xC3002002F7LL,
        (unsigned __int64)"UnionFs::UfsUnionCtx::RemoveUnion",
        "PUSH: Persisting tombstones for union",
        v64);
      if ( (unsigned int)dword_14009E178 > 4 )
      {
        *(_DWORD *)v65 = 195;
        v68[0] = (char *)a1 + 8;
        *(_WORD *)v66 = 759;
        *(_QWORD *)v67 = "UnionFs::UfsUnionCtx::RemoveUnion";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByRef<16>>(
          v28,
          (unsigned int)&byte_1400997E7,
          v29,
          v30,
          (__int64)v67,
          (__int64)v65,
          (__int64)v66,
          (__int64)v68);
      }
      UnionFs::StackEventTracer::LogError(a3);
      *(_DWORD *)a3 = 0;
      *((_WORD *)a3 + 274) = 0;
    }
    v66[0] = 0;
    v31 = UnionFs::UfsPersistenceManager::PersistPayloadsForUnion(
            *((UnionFs::UfsPersistenceManager **)UnionFs::g_FilterState + 16),
            a1,
            v66,
            a3);
    v11 = v31;
    if ( v9 )
    {
      if ( v31 < 0 )
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)v31,
          (int)a3,
          (struct UnionFs::StackEventTracer *)0x6770020030BLL,
          (unsigned __int64)"UnionFs::UfsUnionCtx::RemoveUnion",
          "PUSH: Persisting EA payloads for union",
          v64);
        if ( (unsigned int)dword_14009E178 > 4 )
        {
          *(_DWORD *)v67 = 1655;
          v70 = (struct UnionFs::UfsUnionCtx *)((char *)a1 + 8);
          *(_WORD *)v65 = 779;
          v68[0] = "UnionFs::UfsUnionCtx::RemoveUnion";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByRef<16>>(
            v38,
            (unsigned int)byte_140099A4B,
            v39,
            v40,
            (__int64)v68,
            (__int64)v67,
            (__int64)v65,
            (__int64)&v70);
        }
        UnionFs::StackEventTracer::LogError(a3);
        *(_DWORD *)a3 = 0;
        *((_WORD *)a3 + 274) = 0;
      }
      v32 = (__int64 *)(a4 + 112);
    }
    else
    {
      if ( v31 < 0 )
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)v31,
          (int)a3,
          (struct UnionFs::StackEventTracer *)0x67400200303LL,
          (unsigned __int64)"UnionFs::UfsUnionCtx::RemoveUnion",
          "PUSH: Persisting EA payloads for union",
          v64);
        if ( (unsigned int)dword_14009E178 <= 4 )
          goto LABEL_30;
        *(_DWORD *)v65 = 1652;
        v68[0] = (char *)a1 + 8;
        v23 = byte_1400995ED;
        v24 = 771;
        goto LABEL_29;
      }
      v32 = (__int64 *)(a4 + 112);
      v33 = *v32;
      if ( *v32 )
      {
        v66[0] = 0;
        v68[0] = v66;
        v11 = (*(__int64 (__fastcall **)(__int64, struct UnionFs::UfsUnionCtx *, _QWORD *, struct UnionFs::StackEventTracer *))(*(_QWORD *)v33 + 32LL))(
                v33,
                a1,
                v68,
                a3);
        if ( v11 < 0 )
        {
          UnionFs::ProcessTraceStatusPushLocation(
            (UnionFs *)(unsigned int)v11,
            (int)a3,
            (struct UnionFs::StackEventTracer *)0xA000200318LL,
            (unsigned __int64)"UnionFs::UfsUnionCtx::RemoveUnion",
            "PUSH: Handling union configuration",
            v64);
          if ( (unsigned int)dword_14009E178 > 4 )
          {
            *(_DWORD *)v67 = 160;
            v68[0] = (char *)a1 + 8;
            v69 = "UnionFs::UfsUnionCtx::RemoveUnion";
            *(_WORD *)v65 = 792;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByRef<16>>(
              dword_14009E178,
              (unsigned int)&dword_140099AEC,
              v36,
              v37,
              (__int64)&v69,
              (__int64)v67,
              (__int64)v65,
              (__int64)v68);
          }
LABEL_49:
          wil::details::lambda_call__lambda_c592c24616f63ef314213e1d278e4fcd___::_lambda_call__lambda_c592c24616f63ef314213e1d278e4fcd___(&v74);
          KeReleaseSemaphore(v4, 0, 1, 0);
          v15 = *v32;
          goto LABEL_19;
        }
        if ( v66[0] )
        {
          if ( (unsigned int)dword_14009E178 > 3
            && (qword_14009E188 & 0x100) != 0
            && (qword_14009E190 & 0x100) == qword_14009E190 )
          {
            *(_DWORD *)v67 = 799;
            v68[0] = (char *)a1 + 8;
            v69 = "onecore\\base\\fs\\unionfs\\sys\\unionctx.cpp";
            *(_QWORD *)v65 = "UnionFs::UfsUnionCtx::RemoveUnion";
            v70 = (FsFltWil::Details *)"RemoveUnion exiting before tearing down path cache";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
              qword_14009E190,
              (unsigned int)byte_140099A01,
              v34,
              v35,
              (__int64)&v70,
              (__int64)v65,
              (__int64)&v69,
              (__int64)v67,
              (__int64)v68);
          }
          wil::details::lambda_call__lambda_c592c24616f63ef314213e1d278e4fcd___::_lambda_call__lambda_c592c24616f63ef314213e1d278e4fcd___(&v74);
          KeReleaseSemaphore(v4, 0, 1, 0);
          goto LABEL_89;
        }
      }
    }
    v79 = 0;
    v11 = UnionFs::UfsUnionCtx::ClearPathCacheForUnion(a1, a3);
    if ( v11 < 0 )
    {
      if ( !v9 )
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)v11,
          (int)a3,
          (struct UnionFs::StackEventTracer *)0x2CC00200331LL,
          (unsigned __int64)"UnionFs::UfsUnionCtx::RemoveUnion",
          "PUSH: Clearing path cache",
          v64);
        if ( (unsigned int)dword_14009E178 > 4 )
        {
          *(_DWORD *)v67 = 716;
          v70 = (struct UnionFs::UfsUnionCtx *)((char *)a1 + 8);
          v68[0] = "UnionFs::UfsUnionCtx::RemoveUnion";
          *(_WORD *)v65 = 817;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByRef<16>>(
            v41,
            (unsigned int)&dword_1400996FC,
            v42,
            v43,
            (__int64)v68,
            (__int64)v67,
            (__int64)v65,
            (__int64)&v70);
        }
        goto LABEL_49;
      }
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v11,
        (int)a3,
        (struct UnionFs::StackEventTracer *)0xC400200339LL,
        (unsigned __int64)"UnionFs::UfsUnionCtx::RemoveUnion",
        "PUSH: Clearing path cache",
        v64);
      if ( (unsigned int)dword_14009E178 > 4 )
      {
        *(_DWORD *)v67 = 196;
        v70 = (struct UnionFs::UfsUnionCtx *)((char *)a1 + 8);
        *(_WORD *)v65 = 825;
        v68[0] = "UnionFs::UfsUnionCtx::RemoveUnion";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByRef<16>>(
          v44,
          (unsigned int)&byte_1400994F7,
          v45,
          v46,
          (__int64)v68,
          (__int64)v67,
          (__int64)v65,
          (__int64)&v70);
      }
      UnionFs::StackEventTracer::LogError(a3);
      *(_DWORD *)a3 = 0;
      *((_WORD *)a3 + 274) = 0;
    }
    v11 = UnionFs::UfsUnionCtx::ClearEaTableForUnion(a1, a3);
    if ( v11 < 0 )
    {
      if ( !v9 )
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)v11,
          (int)a3,
          (struct UnionFs::StackEventTracer *)0x65400200344LL,
          (unsigned __int64)"UnionFs::UfsUnionCtx::RemoveUnion",
          "PUSH: Clearing EA Table",
          v64);
        if ( (unsigned int)dword_14009E178 > 4 )
        {
          *(_DWORD *)v67 = 1620;
          v70 = (struct UnionFs::UfsUnionCtx *)((char *)a1 + 8);
          v68[0] = "UnionFs::UfsUnionCtx::RemoveUnion";
          *(_WORD *)v65 = 836;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByRef<16>>(
            v47,
            (unsigned int)byte_140099953,
            v48,
            v49,
            (__int64)v68,
            (__int64)v67,
            (__int64)v65,
            (__int64)&v70);
        }
        goto LABEL_49;
      }
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v11,
        (int)a3,
        (struct UnionFs::StackEventTracer *)0x53D0020034CLL,
        (unsigned __int64)"UnionFs::UfsUnionCtx::RemoveUnion",
        "PUSH: Clearing EA Table",
        v64);
      if ( (unsigned int)dword_14009E178 > 4 )
      {
        *(_DWORD *)v67 = 1341;
        v70 = (struct UnionFs::UfsUnionCtx *)((char *)a1 + 8);
        v68[0] = "UnionFs::UfsUnionCtx::RemoveUnion";
        *(_WORD *)v65 = 844;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByRef<16>>(
          v50,
          (unsigned int)&dword_14009911C,
          v51,
          v52,
          (__int64)v68,
          (__int64)v67,
          (__int64)v65,
          (__int64)&v70);
      }
      UnionFs::StackEventTracer::LogError(a3);
      *(_DWORD *)a3 = 0;
      *((_WORD *)a3 + 274) = 0;
    }
    FsFltWil::AcquirePushLockExclusive(&v70, (char *)a1 + 72);
    v54 = *((_QWORD *)a1 + 6);
    v55 = *((_QWORD *)a1 + 7);
    while ( v54 != v55 )
    {
      v56 = *(_QWORD *)(*(_QWORD *)v54 + 8LL);
      _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)a1 + 8LL));
      v68[1] = *(_QWORD *)a1;
      v68[0] = a1;
      UnionFs::UfsInstanceCtx::ForgetDependentUnion(v56, v68);
      v54 += 16;
    }
    v57 = *((_QWORD *)a1 + 6);
    v58 = *((_QWORD *)a1 + 7) - v57;
    *((_QWORD *)a1 + 7) = v57;
    v59 = v58 >> 4;
    while ( v59 )
    {
      --v59;
      v60 = *(utl::_RefCountBase **)(v57 + 16 * v59 + 8);
      if ( v60 )
        utl::_RefCountBase::_DecStrong(v60);
    }
    if ( v70 )
      FsFltWil::Details::ReleasePushLockExclusive(v70, v53);
    *((_DWORD *)a1 + 6) |= 0x10u;
    KeReleaseSemaphore(v4, 0, 1, 0);
    if ( (_DWORD)v69 == 2 )
    {
      UnionFs::UnionFsFilter::DeleteUnionFromGlobalMapLocked(v61, (const struct _GUID *)((char *)a1 + 8));
    }
    else
    {
      FsFltWil::AcquirePushLockExclusive(&v70, (char *)UnionFs::g_FilterState + 64);
      UnionFs::UnionFsFilter::DeleteUnionFromGlobalMapLocked(v62, (const struct _GUID *)((char *)a1 + 8));
      if ( v70 )
        FsFltWil::Details::ReleasePushLockExclusive(v70, v63);
    }
    wil::details::lambda_call__lambda_c592c24616f63ef314213e1d278e4fcd___::_lambda_call__lambda_c592c24616f63ef314213e1d278e4fcd___(&v74);
LABEL_89:
    v10 = *v32;
LABEL_90:
    if ( v10 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 24LL))(v10);
    return 0;
  }
  if ( v9 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v11,
      (int)a3,
      (struct UnionFs::StackEventTracer *)0x1E5002002E2LL,
      (unsigned __int64)"UnionFs::UfsUnionCtx::RemoveUnion",
      "PUSH: Processing subtree collapse list",
      v64);
    if ( (unsigned int)dword_14009E178 > 4 )
    {
      *(_DWORD *)v65 = 485;
      v68[0] = (char *)a1 + 8;
      *(_WORD *)v66 = 738;
      *(_QWORD *)v67 = "UnionFs::UfsUnionCtx::RemoveUnion";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByRef<16>>(
        v25,
        (unsigned int)byte_1400996A5,
        v26,
        v27,
        (__int64)v67,
        (__int64)v65,
        (__int64)v66,
        (__int64)v68);
    }
    UnionFs::StackEventTracer::LogError(a3);
    *(_DWORD *)a3 = 0;
    *((_WORD *)a3 + 274) = 0;
    goto LABEL_34;
  }
  UnionFs::ProcessTraceStatusPushLocation(
    (UnionFs *)(unsigned int)v11,
    (int)a3,
    (struct UnionFs::StackEventTracer *)0xBD002002DALL,
    (unsigned __int64)"UnionFs::UfsUnionCtx::RemoveUnion",
    "PUSH: Processing subtree collapse list",
    v64);
  if ( (unsigned int)dword_14009E178 > 4 )
  {
    *(_DWORD *)v65 = 189;
    v68[0] = (char *)a1 + 8;
    v23 = (char *)word_1400999AA;
    v24 = 730;
LABEL_29:
    *(_WORD *)v66 = v24;
    v69 = "UnionFs::UfsUnionCtx::RemoveUnion";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByRef<16>>(
      v20,
      (_DWORD)v23,
      v21,
      v22,
      (__int64)&v69,
      (__int64)v65,
      (__int64)v66,
      (__int64)v68);
  }
LABEL_30:
  wil::details::lambda_call__lambda_c592c24616f63ef314213e1d278e4fcd___::_lambda_call__lambda_c592c24616f63ef314213e1d278e4fcd___(&v74);
LABEL_18:
  KeReleaseSemaphore(v4, 0, 1, 0);
  v15 = *(_QWORD *)(a4 + 112);
LABEL_19:
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 24LL))(v15);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1400636bc  mov     [rsp-8+arg_8], rbx
0x1400636c1  push    rbp
0x1400636c2  push    rsi
0x1400636c3  push    rdi
0x1400636c4  push    r12
0x1400636c6  push    r13
0x1400636c8  push    r14
0x1400636ca  push    r15
0x1400636cc  lea     rbp, [rsp-40h]
0x1400636d1  sub     rsp, 140h
0x1400636d8  mov     rax, cs:__security_cookie
0x1400636df  xor     rax, rsp
0x1400636e2  mov     [rbp+70h+var_40], rax
0x1400636e6  lea     r12, [rcx+138h]
0x1400636ed  mov     dword ptr [rsp+170h+var_F8], edx
0x1400636f1  mov     r15, r9
0x1400636f4  mov     rbx, r8
0x1400636f7  mov     edi, edx
0x1400636f9  mov     rsi, rcx
0x1400636fc  xor     r13d, r13d
0x1400636ff  mov     rcx, r12; Object
0x140063702  xor     r9d, r9d; Alertable
0x140063705  mov     [rsp+170h+Timeout], r13; Timeout
0x14006370a  xor     r8d, r8d; WaitMode
0x14006370d  xor     edx, edx; WaitReason
0x14006370f  call    cs:__imp_KeWaitForSingleObject
0x140063716  nop     dword ptr [rax+rax+00h]
0x14006371b  mov     eax, cs:dword_14009E178
0x140063721  lea     r9, aOnecoreBaseFsU_7; "onecore\\base\\fs\\unionfs\\sys\\unionc"...
0x140063728  lea     rdx, aUnionfsUfsunio_22; "UnionFs::UfsUnionCtx::RemoveUnion"
0x14006372f  mov     r8d, 100h
0x140063735  cmp     eax, 4
0x140063738  jbe     loc_14006380B
0x14006373e  mov     rcx, cs:qword_14009E190
0x140063745  mov     rax, cs:qword_14009E188
0x14006374c  test    r8, rax
0x14006374f  jz      loc_14006380B
0x140063755  mov     rax, rcx
0x140063758  and     rax, r8
0x14006375b  cmp     rax, rcx
0x14006375e  jnz     loc_14006380B
0x140063764  lea     rax, [rsp+170h+var_120]
0x140063769  mov     [rbp+70h+var_80], r9
0x14006376d  mov     [rbp+70h+var_50], rax
0x140063771  lea     rcx, dword_14009E178
0x140063778  lea     rax, [rsi+8]
0x14006377c  mov     [rbp+70h+var_90], rdx
0x140063780  mov     [rbp+70h+var_60], rax
0x140063784  lea     rdx, dword_1400991D4
0x14006378b  lea     rax, [rsp+170h+var_118]
0x140063790  mov     dword ptr [rsp+170h+var_120], edi
0x140063794  mov     [rbp+70h+var_70], rax
0x140063798  xor     r9d, r9d
0x14006379b  lea     rax, aRemovingUnion; "Removing union"
0x1400637a2  mov     dword ptr [rsp+170h+var_118], 285h
0x1400637aa  mov     [rbp+70h+var_A0], rax
0x1400637ae  xor     r8d, r8d
0x1400637b1  lea     rax, [rbp+70h+var_C0]
0x1400637b5  mov     [rbp+70h+var_48], 4
0x1400637bd  mov     [rsp+170h+var_148], rax; char *
0x1400637c2  mov     dword ptr [rsp+170h+Timeout], 8
0x1400637ca  mov     [rbp+70h+var_58], 10h
0x1400637d2  mov     [rbp+70h+var_68], 4
0x1400637da  mov     [rbp+70h+var_78], 29h ; ')'
0x1400637e2  mov     [rbp+70h+var_88], 22h ; '"'
0x1400637ea  mov     [rbp+70h+var_98], 0Fh
0x1400637f2  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400637f7  lea     rdx, aUnionfsUfsunio_22; "UnionFs::UfsUnionCtx::RemoveUnion"
0x1400637fe  mov     r8d, 100h
0x140063804  lea     r9, aOnecoreBaseFsU_7; "onecore\\base\\fs\\unionfs\\sys\\unionc"...
0x14006380b  mov     eax, [rsi+18h]
0x14006380e  test    al, 10h
0x140063810  jz      loc_1400638C9
0x140063816  mov     eax, cs:dword_14009E178
0x14006381c  cmp     eax, 4
0x14006381f  jbe     loc_1400638A8
0x140063825  mov     rcx, cs:qword_14009E190
0x14006382c  mov     rax, cs:qword_14009E188
0x140063833  test    r8, rax
0x140063836  jz      short loc_1400638A8
0x140063838  mov     rax, rcx
0x14006383b  and     rax, r8
0x14006383e  cmp     rax, rcx
0x140063841  jnz     short loc_1400638A8
0x140063843  lea     rax, [rsi+8]
0x140063847  mov     qword ptr [rsp+170h+var_118], rdx
0x14006384c  mov     [rsp+170h+var_F8], rax
0x140063851  lea     rdx, word_14009954E
0x140063858  lea     rax, aUnionAlreadyRe; "Union already removed"
0x14006385f  mov     dword ptr [rsp+170h+var_120], 28Ch
0x140063867  mov     [rsp+170h+var_108], rax
0x14006386c  lea     rax, [rsp+170h+var_F8]
0x140063871  mov     [rsp+170h+var_130], rax
0x140063876  lea     rax, [rsp+170h+var_120]
0x14006387b  mov     [rsp+170h+var_138], rax
0x140063880  lea     rax, [rsp+170h+var_110]
0x140063885  mov     [rsp+170h+var_140], rax
0x14006388a  lea     rax, [rsp+170h+var_118]
0x14006388f  mov     [rsp+170h+var_148], rax
0x140063894  lea     rax, [rsp+170h+var_108]
0x140063899  mov     [rsp+170h+Timeout], rax
0x14006389e  mov     qword ptr [rsp+170h+var_110], r9
0x1400638a3  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x1400638a8  xor     r9d, r9d; Wait
0x1400638ab  xor     edx, edx; Increment
0x1400638ad  mov     rcx, r12; Semaphore
0x1400638b0  lea     r8d, [r9+1]; Adjustment
0x1400638b4  call    cs:__imp_KeReleaseSemaphore
0x1400638bb  nop     dword ptr [rax+rax+00h]
0x1400638c0  mov     rcx, [r15+70h]
0x1400638c4  jmp     loc_14006432D
0x1400638c9  mov     rcx, [rsi+130h]; RunRef
0x1400638d0  call    cs:__imp_ExWaitForRundownProtectionReleaseCacheAware
0x1400638d7  nop     dword ptr [rax+rax+00h]
0x1400638dc  mov     r14d, 1
0x1400638e2  nop
0x1400638e3  mov     [rsi+78h], r13b
0x1400638e7  cmp     edi, r14d
0x1400638ea  jz      short loc_1400638F1
0x1400638ec  cmp     edi, 2
0x1400638ef  jnz     short loc_1400638F4
0x1400638f1  mov     r13b, r14b
0x1400638f4  mov     rdx, rbx; struct UnionFs::StackEventTracer *
0x1400638f7  mov     rcx, rsi; this
0x1400638fa  call    ?RemoveScratchFromMappingTable@UfsUnionCtx@UnionFs@@QEAAJAEAVStackEventTracer@2@@Z; UnionFs::UfsUnionCtx::RemoveScratchFromMappingTable(UnionFs::StackEventTracer &)
0x1400638ff  mov     edi, eax
0x140063901  test    eax, eax
0x140063903  jns     loc_140063A61
0x140063909  lea     rax, aPushRemoveunio; "PUSH: RemoveUnionFromScratchMapping"
0x140063910  mov     rdx, rbx; int
0x140063913  mov     [rsp+170h+Timeout], rax; char *
0x140063918  mov     ecx, edi; this
0x14006391a  test    r13b, r13b
0x14006391d  jnz     loc_1400639CE
0x140063923  lea     r13, aUnionfsUfsunio_22; "UnionFs::UfsUnionCtx::RemoveUnion"
0x14006392a  mov     r8, 2EA002002AAh; struct UnionFs::StackEventTracer *
0x140063934  mov     r9, r13; unsigned __int64
0x140063937  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006393c  mov     eax, cs:dword_14009E178
0x140063942  cmp     eax, 4
0x140063945  jbe     short loc_14006399B
0x140063947  lea     rax, [rsi+8]
0x14006394b  mov     dword ptr [rsp+170h+var_120], 2EAh
0x140063953  mov     [rsp+170h+var_108], rax
0x140063958  lea     rdx, word_1400992E6
0x14006395f  mov     eax, 2AAh
0x140063964  mov     [rsp+170h+var_F8], r13
0x140063969  mov     word ptr [rsp+170h+var_118], ax
0x14006396e  lea     rax, [rsp+170h+var_108]
0x140063973  mov     [rsp+170h+var_138], rax
0x140063978  lea     rax, [rsp+170h+var_118]
0x14006397d  mov     [rsp+170h+var_140], rax
0x140063982  lea     rax, [rsp+170h+var_120]
0x140063987  mov     [rsp+170h+var_148], rax
0x14006398c  lea     rax, [rsp+170h+var_F8]
0x140063991  mov     [rsp+170h+Timeout], rax
0x140063996  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByRef<16> const &)
0x14006399b  xor     r9d, r9d; Wait
0x14006399e  mov     r8d, r14d; Adjustment
0x1400639a1  xor     edx, edx; Increment
0x1400639a3  mov     rcx, r12; Semaphore
0x1400639a6  call    cs:__imp_KeReleaseSemaphore
0x1400639ad  nop     dword ptr [rax+rax+00h]
0x1400639b2  mov     rcx, [r15+70h]
0x1400639b6  test    rcx, rcx
0x1400639b9  jz      short loc_1400639C7
0x1400639bb  mov     rax, [rcx]
0x1400639be  mov     rax, [rax+18h]
0x1400639c2  call    _guard_dispatch_icall
0x1400639c7  mov     eax, edi
0x1400639c9  jmp     loc_140064340
0x1400639ce  lea     r9, aUnionfsUfsunio_22; "UnionFs::UfsUnionCtx::RemoveUnion"
0x1400639d5  mov     r8, 0C2002002B2h; struct UnionFs::StackEventTracer *
0x1400639df  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400639e4  mov     eax, cs:dword_14009E178
0x1400639ea  cmp     eax, 4
0x1400639ed  jbe     short loc_140063A4A
0x1400639ef  lea     rax, [rsi+8]
0x1400639f3  mov     dword ptr [rsp+170h+var_120], 0C2h
0x1400639fb  mov     [rsp+170h+var_108], rax
0x140063a00  lea     rdx, unk_1400994A0
0x140063a07  mov     eax, 2B2h
0x140063a0c  mov     word ptr [rsp+170h+var_118], ax
0x140063a11  lea     rax, aUnionfsUfsunio_22; "UnionFs::UfsUnionCtx::RemoveUnion"
0x140063a18  mov     qword ptr [rsp+170h+var_110], rax
0x140063a1d  lea     rax, [rsp+170h+var_108]
0x140063a22  mov     [rsp+170h+var_138], rax
0x140063a27  lea     rax, [rsp+170h+var_118]
0x140063a2c  mov     [rsp+170h+var_140], rax
0x140063a31  lea     rax, [rsp+170h+var_120]
0x140063a36  mov     [rsp+170h+var_148], rax; char *
0x140063a3b  lea     rax, [rsp+170h+var_110]
0x140063a40  mov     [rsp+170h+Timeout], rax
0x140063a45  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByRef<16> const &)
0x140063a4a  mov     rcx, rbx; this
0x140063a4d  call    ?LogError@StackEventTracer@UnionFs@@AEAAXXZ; UnionFs::StackEventTracer::LogError(void)
0x140063a52  xor     eax, eax
0x140063a54  mov     dword ptr [rbx], 0
0x140063a5a  mov     [rbx+224h], ax
0x140063a61  mov     eax, [rbp+70h+var_E7]
0x140063a64  lea     rcx, [rsp+170h+var_118]; bool *
0x140063a69  mov     [rbp+70h+var_D7], eax
0x140063a6c  mov     rdx, rbx; struct UnionFs::StackEventTracer *
0x140063a6f  movzx   eax, [rbp+70h+var_E3]
0x140063a73  mov     [rbp+70h+var_D3], ax
0x140063a77  mov     al, [rbp+70h+var_E1]
0x140063a7a  mov     [rbp+70h+var_D1], al
0x140063a7d  mov     [rbp+70h+var_E0], rsi
0x140063a81  mov     [rbp+70h+var_D8], r13b
0x140063a85  mov     [rbp+70h+var_D0], r14b
0x140063a89  mov     [rsp+170h+var_118], 0
0x140063a8e  call    ?ProcessSubtreeCollapseList@UfsPathCache@UnionFs@@SAJPEA_NAEAVStackEventTracer@2@@Z; UnionFs::UfsPathCache::ProcessSubtreeCollapseList(bool *,UnionFs::StackEventTracer &)
0x140063a93  mov     edi, eax
0x140063a95  test    eax, eax
0x140063a97  jns     loc_140063BD0
0x140063a9d  lea     rax, aPushProcessing; "PUSH: Processing subtree collapse list"
0x140063aa4  mov     rdx, rbx; int
0x140063aa7  mov     [rsp+170h+Timeout], rax; char *
0x140063aac  mov     ecx, edi; this
0x140063aae  test    r13b, r13b
0x140063ab1  jnz     loc_140063B3D
0x140063ab7  lea     r13, aUnionfsUfsunio_22; "UnionFs::UfsUnionCtx::RemoveUnion"
0x140063abe  mov     r8, 0BD002002DAh; struct UnionFs::StackEventTracer *
0x140063ac8  mov     r9, r13; unsigned __int64
0x140063acb  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140063ad0  mov     eax, cs:dword_14009E178
0x140063ad6  cmp     eax, 4
0x140063ad9  jbe     short loc_140063B2F
0x140063adb  lea     rax, [rsi+8]
0x140063adf  mov     dword ptr [rsp+170h+var_120], 0BDh
0x140063ae7  mov     [rsp+170h+var_108], rax
0x140063aec  lea     rdx, word_1400999AA
0x140063af3  mov     eax, 2DAh
0x140063af8  mov     word ptr [rsp+170h+var_118], ax
0x140063afd  lea     rax, [rsp+170h+var_108]
0x140063b02  mov     [rsp+170h+var_138], rax
0x140063b07  lea     rax, [rsp+170h+var_118]
0x140063b0c  mov     [rsp+170h+var_140], rax
0x140063b11  lea     rax, [rsp+170h+var_120]
0x140063b16  mov     [rsp+170h+var_148], rax
0x140063b1b  lea     rax, [rsp+170h+var_F8]
0x140063b20  mov     [rsp+170h+Timeout], rax
0x140063b25  mov     [rsp+170h+var_F8], r13
0x140063b2a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByRef<16> const &)
0x140063b2f  lea     rcx, [rbp+70h+var_E0]
0x140063b33  call    wil__details__lambda_call__lambda_c592c24616f63ef314213e1d278e4fcd______lambda_call__lambda_c592c24616f63ef314213e1d278e4fcd___
0x140063b38  jmp     loc_14006399B
0x140063b3d  lea     r9, aUnionfsUfsunio_22; "UnionFs::UfsUnionCtx::RemoveUnion"
0x140063b44  mov     r8, 1E5002002E2h; struct UnionFs::StackEventTracer *
0x140063b4e  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140063b53  mov     eax, cs:dword_14009E178
0x140063b59  cmp     eax, 4
0x140063b5c  jbe     short loc_140063BB9
0x140063b5e  lea     rax, [rsi+8]
0x140063b62  mov     dword ptr [rsp+170h+var_120], 1E5h
0x140063b6a  mov     [rsp+170h+var_108], rax
0x140063b6f  lea     rdx, byte_1400996A5
0x140063b76  mov     eax, 2E2h
0x140063b7b  mov     word ptr [rsp+170h+var_118], ax
0x140063b80  lea     rax, aUnionfsUfsunio_22; "UnionFs::UfsUnionCtx::RemoveUnion"
0x140063b87  mov     qword ptr [rsp+170h+var_110], rax
0x140063b8c  lea     rax, [rsp+170h+var_108]
0x140063b91  mov     [rsp+170h+var_138], rax
0x140063b96  lea     rax, [rsp+170h+var_118]
0x140063b9b  mov     [rsp+170h+var_140], rax
0x140063ba0  lea     rax, [rsp+170h+var_120]
0x140063ba5  mov     [rsp+170h+var_148], rax; char *
0x140063baa  lea     rax, [rsp+170h+var_110]
0x140063baf  mov     [rsp+170h+Timeout], rax
0x140063bb4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByRef<16> const &)
0x140063bb9  mov     rcx, rbx; this
0x140063bbc  call    ?LogError@StackEventTracer@UnionFs@@AEAAXXZ; UnionFs::StackEventTracer::LogError(void)
0x140063bc1  xor     eax, eax
0x140063bc3  mov     dword ptr [rbx], 0
0x140063bc9  mov     [rbx+224h], ax
0x140063bd0  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140063bd7  lea     r8, [rsp+170h+var_118]; bool *
0x140063bdc  mov     r9, rbx; struct UnionFs::StackEventTracer *
0x140063bdf  mov     [rsp+170h+var_118], 0
0x140063be4  mov     rdx, rsi; struct UnionFs::UfsUnionCtx *
0x140063be7  mov     rcx, [rcx+78h]; this
0x140063beb  call    ?PersistPayloadsForUnion@UfsPersistenceManager@UnionFs@@QEBAJAEAVUfsUnionCtx@2@PEA_NAEAVStackEventTracer@2@@Z; UnionFs::UfsPersistenceManager::PersistPayloadsForUnion(UnionFs::UfsUnionCtx &,bool *,UnionFs::StackEventTracer &)
0x140063bf0  mov     edi, eax
0x140063bf2  test    eax, eax
0x140063bf4  jns     loc_140063CED
0x140063bfa  lea     rax, aPushPersisting_0; "PUSH: Persisting tombstones for union"
0x140063c01  mov     rdx, rbx; int
0x140063c04  mov     [rsp+170h+Timeout], rax; char *
0x140063c09  mov     ecx, edi; this
0x140063c0b  test    r13b, r13b
0x140063c0e  jnz     short loc_140063C5A
0x140063c10  lea     r13, aUnionfsUfsunio_22; "UnionFs::UfsUnionCtx::RemoveUnion"
0x140063c17  mov     r8, 2EB002002EFh; struct UnionFs::StackEventTracer *
0x140063c21  mov     r9, r13; unsigned __int64
0x140063c24  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140063c29  mov     eax, cs:dword_14009E178
0x140063c2f  cmp     eax, 4
0x140063c32  jbe     loc_140063B2F
0x140063c38  lea     rax, [rsi+8]
0x140063c3c  mov     dword ptr [rsp+170h+var_120], 2EBh
  ... truncated ...
```
