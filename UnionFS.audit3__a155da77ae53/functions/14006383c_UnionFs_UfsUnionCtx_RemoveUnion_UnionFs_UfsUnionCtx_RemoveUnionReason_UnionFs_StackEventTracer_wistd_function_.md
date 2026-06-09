# UnionFs::UfsUnionCtx::RemoveUnion(UnionFs::UfsUnionCtx::RemoveUnionReason,UnionFs::StackEventTracer &,wistd::function<long (UnionFs::UfsUnionCtx &,bool *,UnionFs::StackEventTracer &)>)

- ea: `0x14006383c`
- end: `0x1400644e8`
- name: `?RemoveUnion@UfsUnionCtx@UnionFs@@QEAAJW4RemoveUnionReason@12@AEAVStackEventTracer@2@V?$function@$$A6AJAEAVUfsUnionCtx@UnionFs@@PEA_NAEAVStackEventTracer@2@@Z@wistd@@@Z`
- size: `3244`
- prototype: `__int64 __fastcall(struct UnionFs::UfsUnionCtx *)`
- caller_count: `4`
- callee_count: `19`
- tags: `registry_config`

## callers

- `0x14000867c`
- `0x14000e53c`
- `0x14002a420`
- `0x140062fd4`

## callees

- `0x140001754`
- `0x140001b64`
- `0x1400031a0`
- `0x140009620`
- `0x14000f81c`
- `0x140028628`
- `0x14003d2a8`
- `0x140052508`
- `0x140056974`
- `0x140056c7c`
- `0x14005d580`
- `0x14005faa0`
- `0x14005feb4`
- `0x1400634c4`
- `0x14006383c`
- `0x140079cfc`
- `0x14007a094`
- `0x14007baf0`
- `0x14007bbd0`

## import_xrefs

- `ntoskrnl!KeReleaseSemaphore` at `0x140063a34`
- `ntoskrnl!KeReleaseSemaphore` at `0x140063b26`
- `ntoskrnl!KeReleaseSemaphore` at `0x140063fd7`
- `ntoskrnl!KeReleaseSemaphore` at `0x1400640ad`
- `ntoskrnl!KeReleaseSemaphore` at `0x140064458`
- `ntoskrnl!KeReleaseSemaphore` at `0x140063a34`
- `ntoskrnl!KeReleaseSemaphore` at `0x140063b26`
- `ntoskrnl!KeReleaseSemaphore` at `0x140063fd7`
- `ntoskrnl!KeReleaseSemaphore` at `0x1400640ad`
- `ntoskrnl!KeReleaseSemaphore` at `0x140064458`
- `ntoskrnl!KeWaitForSingleObject` at `0x14006388f`
- `ntoskrnl!KeWaitForSingleObject` at `0x14006388f`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x140063a50`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x140063a50`

## string_xrefs

- `0x1400638a8`: `UnionFs::UfsUnionCtx::RemoveUnion`
- `0x140063977`: `UnionFs::UfsUnionCtx::RemoveUnion`
- `0x140063aa3`: `UnionFs::UfsUnionCtx::RemoveUnion`
- `0x140063b4e`: `UnionFs::UfsUnionCtx::RemoveUnion`
- `0x140063b91`: `UnionFs::UfsUnionCtx::RemoveUnion`
- `0x140063c37`: `UnionFs::UfsUnionCtx::RemoveUnion`
- `0x140063cbd`: `UnionFs::UfsUnionCtx::RemoveUnion`
- `0x140063d00`: `UnionFs::UfsUnionCtx::RemoveUnion`
- `0x140063d90`: `UnionFs::UfsUnionCtx::RemoveUnion`
- `0x140063dda`: `UnionFs::UfsUnionCtx::RemoveUnion`
- `0x140063e1d`: `UnionFs::UfsUnionCtx::RemoveUnion`
- `0x140063eb0`: `UnionFs::UfsUnionCtx::RemoveUnion`
- `0x140063f4b`: `UnionFs::UfsUnionCtx::RemoveUnion`
- `0x14006404c`: `UnionFs::UfsUnionCtx::RemoveUnion`
- `0x1400640d7`: `UnionFs::UfsUnionCtx::RemoveUnion`
- `0x140064119`: `UnionFs::UfsUnionCtx::RemoveUnion`
- `0x14006419b`: `UnionFs::UfsUnionCtx::RemoveUnion`
- `0x140064210`: `UnionFs::UfsUnionCtx::RemoveUnion`
- `0x140064252`: `UnionFs::UfsUnionCtx::RemoveUnion`
- `0x1400642c0`: `UnionFs::UfsUnionCtx::RemoveUnion`
- `0x140063a89`: `PUSH: RemoveUnionFromScratchMapping`
- `0x1400639d8`: `Union already removed`
- `0x140063f3a`: `PUSH: Handling union configuration`
- `0x140064185`: `PUSH: Clearing path cache`
- `0x140064058`: `RemoveUnion exiting before tearing down path cache`

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
  int *v23; // rdx
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
    tlgWriteTransfer_EtwWriteTransfer(&dword_14009E178, &dword_140099254, 0, 0, 8);
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
        (unsigned int)&word_1400995CE,
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
          (unsigned int)&word_140099366,
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
        (unsigned int)byte_1400994C9,
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
        v23 = (int *)&unk_140099520;
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
          (unsigned int)byte_14009981D,
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
            (unsigned int)byte_140099ACB,
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
        v23 = (int *)byte_140099615;
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
              (unsigned int)&dword_140099B6C,
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
              (unsigned int)word_140099A2A,
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
            (unsigned int)&dword_14009977C,
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
          (unsigned int)&byte_140099577,
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
            (unsigned int)byte_1400999D3,
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
          (unsigned int)&dword_14009919C,
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
        (unsigned int)byte_140099725,
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
    v23 = &dword_140099A74;
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
0x14006383c  mov     [rsp-8+arg_8], rbx
0x140063841  push    rbp
0x140063842  push    rsi
0x140063843  push    rdi
0x140063844  push    r12
0x140063846  push    r13
0x140063848  push    r14
0x14006384a  push    r15
0x14006384c  lea     rbp, [rsp-40h]
0x140063851  sub     rsp, 140h
0x140063858  mov     rax, cs:__security_cookie
0x14006385f  xor     rax, rsp
0x140063862  mov     [rbp+70h+var_40], rax
0x140063866  lea     r12, [rcx+138h]
0x14006386d  mov     dword ptr [rsp+170h+var_F8], edx
0x140063871  mov     r15, r9
0x140063874  mov     rbx, r8
0x140063877  mov     edi, edx
0x140063879  mov     rsi, rcx
0x14006387c  xor     r13d, r13d
0x14006387f  mov     rcx, r12; Object
0x140063882  xor     r9d, r9d; Alertable
0x140063885  mov     [rsp+170h+Timeout], r13; Timeout
0x14006388a  xor     r8d, r8d; WaitMode
0x14006388d  xor     edx, edx; WaitReason
0x14006388f  call    cs:__imp_KeWaitForSingleObject
0x140063896  nop     dword ptr [rax+rax+00h]
0x14006389b  mov     eax, cs:dword_14009E178
0x1400638a1  lea     r9, aOnecoreBaseFsU_7; "onecore\\base\\fs\\unionfs\\sys\\unionc"...
0x1400638a8  lea     rdx, aUnionfsUfsunio_22; "UnionFs::UfsUnionCtx::RemoveUnion"
0x1400638af  mov     r8d, 100h
0x1400638b5  cmp     eax, 4
0x1400638b8  jbe     loc_14006398B
0x1400638be  mov     rcx, cs:qword_14009E190
0x1400638c5  mov     rax, cs:qword_14009E188
0x1400638cc  test    r8, rax
0x1400638cf  jz      loc_14006398B
0x1400638d5  mov     rax, rcx
0x1400638d8  and     rax, r8
0x1400638db  cmp     rax, rcx
0x1400638de  jnz     loc_14006398B
0x1400638e4  lea     rax, [rsp+170h+var_120]
0x1400638e9  mov     [rbp+70h+var_80], r9
0x1400638ed  mov     [rbp+70h+var_50], rax
0x1400638f1  lea     rcx, dword_14009E178
0x1400638f8  lea     rax, [rsi+8]
0x1400638fc  mov     [rbp+70h+var_90], rdx
0x140063900  mov     [rbp+70h+var_60], rax
0x140063904  lea     rdx, dword_140099254
0x14006390b  lea     rax, [rsp+170h+var_118]
0x140063910  mov     dword ptr [rsp+170h+var_120], edi
0x140063914  mov     [rbp+70h+var_70], rax
0x140063918  xor     r9d, r9d
0x14006391b  lea     rax, aRemovingUnion; "Removing union"
0x140063922  mov     dword ptr [rsp+170h+var_118], 285h
0x14006392a  mov     [rbp+70h+var_A0], rax
0x14006392e  xor     r8d, r8d
0x140063931  lea     rax, [rbp+70h+var_C0]
0x140063935  mov     [rbp+70h+var_48], 4
0x14006393d  mov     [rsp+170h+var_148], rax; char *
0x140063942  mov     dword ptr [rsp+170h+Timeout], 8
0x14006394a  mov     [rbp+70h+var_58], 10h
0x140063952  mov     [rbp+70h+var_68], 4
0x14006395a  mov     [rbp+70h+var_78], 29h ; ')'
0x140063962  mov     [rbp+70h+var_88], 22h ; '"'
0x14006396a  mov     [rbp+70h+var_98], 0Fh
0x140063972  call    _tlgWriteTransfer_EtwWriteTransfer
0x140063977  lea     rdx, aUnionfsUfsunio_22; "UnionFs::UfsUnionCtx::RemoveUnion"
0x14006397e  mov     r8d, 100h
0x140063984  lea     r9, aOnecoreBaseFsU_7; "onecore\\base\\fs\\unionfs\\sys\\unionc"...
0x14006398b  mov     eax, [rsi+18h]
0x14006398e  test    al, 10h
0x140063990  jz      loc_140063A49
0x140063996  mov     eax, cs:dword_14009E178
0x14006399c  cmp     eax, 4
0x14006399f  jbe     loc_140063A28
0x1400639a5  mov     rcx, cs:qword_14009E190
0x1400639ac  mov     rax, cs:qword_14009E188
0x1400639b3  test    r8, rax
0x1400639b6  jz      short loc_140063A28
0x1400639b8  mov     rax, rcx
0x1400639bb  and     rax, r8
0x1400639be  cmp     rax, rcx
0x1400639c1  jnz     short loc_140063A28
0x1400639c3  lea     rax, [rsi+8]
0x1400639c7  mov     qword ptr [rsp+170h+var_118], rdx
0x1400639cc  mov     [rsp+170h+var_F8], rax
0x1400639d1  lea     rdx, word_1400995CE
0x1400639d8  lea     rax, aUnionAlreadyRe; "Union already removed"
0x1400639df  mov     dword ptr [rsp+170h+var_120], 28Ch
0x1400639e7  mov     [rsp+170h+var_108], rax
0x1400639ec  lea     rax, [rsp+170h+var_F8]
0x1400639f1  mov     [rsp+170h+var_130], rax
0x1400639f6  lea     rax, [rsp+170h+var_120]
0x1400639fb  mov     [rsp+170h+var_138], rax
0x140063a00  lea     rax, [rsp+170h+var_110]
0x140063a05  mov     [rsp+170h+var_140], rax
0x140063a0a  lea     rax, [rsp+170h+var_118]
0x140063a0f  mov     [rsp+170h+var_148], rax
0x140063a14  lea     rax, [rsp+170h+var_108]
0x140063a19  mov     [rsp+170h+Timeout], rax
0x140063a1e  mov     qword ptr [rsp+170h+var_110], r9
0x140063a23  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x140063a28  xor     r9d, r9d; Wait
0x140063a2b  xor     edx, edx; Increment
0x140063a2d  mov     rcx, r12; Semaphore
0x140063a30  lea     r8d, [r9+1]; Adjustment
0x140063a34  call    cs:__imp_KeReleaseSemaphore
0x140063a3b  nop     dword ptr [rax+rax+00h]
0x140063a40  mov     rcx, [r15+70h]
0x140063a44  jmp     loc_1400644AD
0x140063a49  mov     rcx, [rsi+130h]; RunRef
0x140063a50  call    cs:__imp_ExWaitForRundownProtectionReleaseCacheAware
0x140063a57  nop     dword ptr [rax+rax+00h]
0x140063a5c  mov     r14d, 1
0x140063a62  nop
0x140063a63  mov     [rsi+78h], r13b
0x140063a67  cmp     edi, r14d
0x140063a6a  jz      short loc_140063A71
0x140063a6c  cmp     edi, 2
0x140063a6f  jnz     short loc_140063A74
0x140063a71  mov     r13b, r14b
0x140063a74  mov     rdx, rbx; struct UnionFs::StackEventTracer *
0x140063a77  mov     rcx, rsi; this
0x140063a7a  call    ?RemoveScratchFromMappingTable@UfsUnionCtx@UnionFs@@QEAAJAEAVStackEventTracer@2@@Z; UnionFs::UfsUnionCtx::RemoveScratchFromMappingTable(UnionFs::StackEventTracer &)
0x140063a7f  mov     edi, eax
0x140063a81  test    eax, eax
0x140063a83  jns     loc_140063BE1
0x140063a89  lea     rax, aPushRemoveunio; "PUSH: RemoveUnionFromScratchMapping"
0x140063a90  mov     rdx, rbx; int
0x140063a93  mov     [rsp+170h+Timeout], rax; char *
0x140063a98  mov     ecx, edi; this
0x140063a9a  test    r13b, r13b
0x140063a9d  jnz     loc_140063B4E
0x140063aa3  lea     r13, aUnionfsUfsunio_22; "UnionFs::UfsUnionCtx::RemoveUnion"
0x140063aaa  mov     r8, 2EA002002AAh; struct UnionFs::StackEventTracer *
0x140063ab4  mov     r9, r13; unsigned __int64
0x140063ab7  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140063abc  mov     eax, cs:dword_14009E178
0x140063ac2  cmp     eax, 4
0x140063ac5  jbe     short loc_140063B1B
0x140063ac7  lea     rax, [rsi+8]
0x140063acb  mov     dword ptr [rsp+170h+var_120], 2EAh
0x140063ad3  mov     [rsp+170h+var_108], rax
0x140063ad8  lea     rdx, word_140099366
0x140063adf  mov     eax, 2AAh
0x140063ae4  mov     [rsp+170h+var_F8], r13
0x140063ae9  mov     word ptr [rsp+170h+var_118], ax
0x140063aee  lea     rax, [rsp+170h+var_108]
0x140063af3  mov     [rsp+170h+var_138], rax
0x140063af8  lea     rax, [rsp+170h+var_118]
0x140063afd  mov     [rsp+170h+var_140], rax
0x140063b02  lea     rax, [rsp+170h+var_120]
0x140063b07  mov     [rsp+170h+var_148], rax
0x140063b0c  lea     rax, [rsp+170h+var_F8]
0x140063b11  mov     [rsp+170h+Timeout], rax
0x140063b16  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByRef<16> const &)
0x140063b1b  xor     r9d, r9d; Wait
0x140063b1e  mov     r8d, r14d; Adjustment
0x140063b21  xor     edx, edx; Increment
0x140063b23  mov     rcx, r12; Semaphore
0x140063b26  call    cs:__imp_KeReleaseSemaphore
0x140063b2d  nop     dword ptr [rax+rax+00h]
0x140063b32  mov     rcx, [r15+70h]
0x140063b36  test    rcx, rcx
0x140063b39  jz      short loc_140063B47
0x140063b3b  mov     rax, [rcx]
0x140063b3e  mov     rax, [rax+18h]
0x140063b42  call    _guard_dispatch_icall
0x140063b47  mov     eax, edi
0x140063b49  jmp     loc_1400644C0
0x140063b4e  lea     r9, aUnionfsUfsunio_22; "UnionFs::UfsUnionCtx::RemoveUnion"
0x140063b55  mov     r8, 0C2002002B2h; struct UnionFs::StackEventTracer *
0x140063b5f  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140063b64  mov     eax, cs:dword_14009E178
0x140063b6a  cmp     eax, 4
0x140063b6d  jbe     short loc_140063BCA
0x140063b6f  lea     rax, [rsi+8]
0x140063b73  mov     dword ptr [rsp+170h+var_120], 0C2h
0x140063b7b  mov     [rsp+170h+var_108], rax
0x140063b80  lea     rdx, byte_1400994C9
0x140063b87  mov     eax, 2B2h
0x140063b8c  mov     word ptr [rsp+170h+var_118], ax
0x140063b91  lea     rax, aUnionfsUfsunio_22; "UnionFs::UfsUnionCtx::RemoveUnion"
0x140063b98  mov     qword ptr [rsp+170h+var_110], rax
0x140063b9d  lea     rax, [rsp+170h+var_108]
0x140063ba2  mov     [rsp+170h+var_138], rax
0x140063ba7  lea     rax, [rsp+170h+var_118]
0x140063bac  mov     [rsp+170h+var_140], rax
0x140063bb1  lea     rax, [rsp+170h+var_120]
0x140063bb6  mov     [rsp+170h+var_148], rax; char *
0x140063bbb  lea     rax, [rsp+170h+var_110]
0x140063bc0  mov     [rsp+170h+Timeout], rax
0x140063bc5  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByRef<16> const &)
0x140063bca  mov     rcx, rbx; this
0x140063bcd  call    ?LogError@StackEventTracer@UnionFs@@AEAAXXZ; UnionFs::StackEventTracer::LogError(void)
0x140063bd2  xor     eax, eax
0x140063bd4  mov     dword ptr [rbx], 0
0x140063bda  mov     [rbx+224h], ax
0x140063be1  mov     eax, [rbp+70h+var_E7]
0x140063be4  lea     rcx, [rsp+170h+var_118]; bool *
0x140063be9  mov     [rbp+70h+var_D7], eax
0x140063bec  mov     rdx, rbx; struct UnionFs::StackEventTracer *
0x140063bef  movzx   eax, [rbp+70h+var_E3]
0x140063bf3  mov     [rbp+70h+var_D3], ax
0x140063bf7  mov     al, [rbp+70h+var_E1]
0x140063bfa  mov     [rbp+70h+var_D1], al
0x140063bfd  mov     [rbp+70h+var_E0], rsi
0x140063c01  mov     [rbp+70h+var_D8], r13b
0x140063c05  mov     [rbp+70h+var_D0], r14b
0x140063c09  mov     [rsp+170h+var_118], 0
0x140063c0e  call    ?ProcessSubtreeCollapseList@UfsPathCache@UnionFs@@SAJPEA_NAEAVStackEventTracer@2@@Z; UnionFs::UfsPathCache::ProcessSubtreeCollapseList(bool *,UnionFs::StackEventTracer &)
0x140063c13  mov     edi, eax
0x140063c15  test    eax, eax
0x140063c17  jns     loc_140063D50
0x140063c1d  lea     rax, aPushProcessing; "PUSH: Processing subtree collapse list"
0x140063c24  mov     rdx, rbx; int
0x140063c27  mov     [rsp+170h+Timeout], rax; char *
0x140063c2c  mov     ecx, edi; this
0x140063c2e  test    r13b, r13b
0x140063c31  jnz     loc_140063CBD
0x140063c37  lea     r13, aUnionfsUfsunio_22; "UnionFs::UfsUnionCtx::RemoveUnion"
0x140063c3e  mov     r8, 0BD002002DAh; struct UnionFs::StackEventTracer *
0x140063c48  mov     r9, r13; unsigned __int64
0x140063c4b  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140063c50  mov     eax, cs:dword_14009E178
0x140063c56  cmp     eax, 4
0x140063c59  jbe     short loc_140063CAF
0x140063c5b  lea     rax, [rsi+8]
0x140063c5f  mov     dword ptr [rsp+170h+var_120], 0BDh
0x140063c67  mov     [rsp+170h+var_108], rax
0x140063c6c  lea     rdx, dword_140099A74
0x140063c73  mov     eax, 2DAh
0x140063c78  mov     word ptr [rsp+170h+var_118], ax
0x140063c7d  lea     rax, [rsp+170h+var_108]
0x140063c82  mov     [rsp+170h+var_138], rax
0x140063c87  lea     rax, [rsp+170h+var_118]
0x140063c8c  mov     [rsp+170h+var_140], rax
0x140063c91  lea     rax, [rsp+170h+var_120]
0x140063c96  mov     [rsp+170h+var_148], rax
0x140063c9b  lea     rax, [rsp+170h+var_F8]
0x140063ca0  mov     [rsp+170h+Timeout], rax
0x140063ca5  mov     [rsp+170h+var_F8], r13
0x140063caa  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByRef<16> const &)
0x140063caf  lea     rcx, [rbp+70h+var_E0]
0x140063cb3  call    wil__details__lambda_call__lambda_c592c24616f63ef314213e1d278e4fcd______lambda_call__lambda_c592c24616f63ef314213e1d278e4fcd___
0x140063cb8  jmp     loc_140063B1B
0x140063cbd  lea     r9, aUnionfsUfsunio_22; "UnionFs::UfsUnionCtx::RemoveUnion"
0x140063cc4  mov     r8, 1E5002002E2h; struct UnionFs::StackEventTracer *
0x140063cce  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140063cd3  mov     eax, cs:dword_14009E178
0x140063cd9  cmp     eax, 4
0x140063cdc  jbe     short loc_140063D39
0x140063cde  lea     rax, [rsi+8]
0x140063ce2  mov     dword ptr [rsp+170h+var_120], 1E5h
0x140063cea  mov     [rsp+170h+var_108], rax
0x140063cef  lea     rdx, byte_140099725
0x140063cf6  mov     eax, 2E2h
0x140063cfb  mov     word ptr [rsp+170h+var_118], ax
0x140063d00  lea     rax, aUnionfsUfsunio_22; "UnionFs::UfsUnionCtx::RemoveUnion"
0x140063d07  mov     qword ptr [rsp+170h+var_110], rax
0x140063d0c  lea     rax, [rsp+170h+var_108]
0x140063d11  mov     [rsp+170h+var_138], rax
0x140063d16  lea     rax, [rsp+170h+var_118]
0x140063d1b  mov     [rsp+170h+var_140], rax
0x140063d20  lea     rax, [rsp+170h+var_120]
0x140063d25  mov     [rsp+170h+var_148], rax; char *
0x140063d2a  lea     rax, [rsp+170h+var_110]
0x140063d2f  mov     [rsp+170h+Timeout], rax
0x140063d34  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByRef<16> const &)
0x140063d39  mov     rcx, rbx; this
0x140063d3c  call    ?LogError@StackEventTracer@UnionFs@@AEAAXXZ; UnionFs::StackEventTracer::LogError(void)
0x140063d41  xor     eax, eax
0x140063d43  mov     dword ptr [rbx], 0
0x140063d49  mov     [rbx+224h], ax
0x140063d50  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140063d57  lea     r8, [rsp+170h+var_118]; bool *
0x140063d5c  mov     r9, rbx; struct UnionFs::StackEventTracer *
0x140063d5f  mov     [rsp+170h+var_118], 0
0x140063d64  mov     rdx, rsi; struct UnionFs::UfsUnionCtx *
0x140063d67  mov     rcx, [rcx+78h]; this
0x140063d6b  call    ?PersistPayloadsForUnion@UfsPersistenceManager@UnionFs@@QEBAJAEAVUfsUnionCtx@2@PEA_NAEAVStackEventTracer@2@@Z; UnionFs::UfsPersistenceManager::PersistPayloadsForUnion(UnionFs::UfsUnionCtx &,bool *,UnionFs::StackEventTracer &)
0x140063d70  mov     edi, eax
0x140063d72  test    eax, eax
0x140063d74  jns     loc_140063E6D
0x140063d7a  lea     rax, aPushPersisting_0; "PUSH: Persisting tombstones for union"
0x140063d81  mov     rdx, rbx; int
0x140063d84  mov     [rsp+170h+Timeout], rax; char *
0x140063d89  mov     ecx, edi; this
0x140063d8b  test    r13b, r13b
0x140063d8e  jnz     short loc_140063DDA
0x140063d90  lea     r13, aUnionfsUfsunio_22; "UnionFs::UfsUnionCtx::RemoveUnion"
0x140063d97  mov     r8, 2EB002002EFh; struct UnionFs::StackEventTracer *
0x140063da1  mov     r9, r13; unsigned __int64
0x140063da4  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140063da9  mov     eax, cs:dword_14009E178
0x140063daf  cmp     eax, 4
0x140063db2  jbe     loc_140063CAF
0x140063db8  lea     rax, [rsi+8]
0x140063dbc  mov     dword ptr [rsp+170h+var_120], 2EBh
  ... truncated ...
```
