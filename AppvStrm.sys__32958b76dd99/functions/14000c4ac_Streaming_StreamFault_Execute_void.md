# Streaming::StreamFault::Execute(void)

- ea: `0x14000c4ac`
- end: `0x14000cf6b`
- name: `?Execute@StreamFault@Streaming@@QEAAJXZ`
- size: `2751`
- prototype: `__int64 __fastcall(Streaming::StreamFault *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14000e7f8`

## callees

- `0x14000bfe4`
- `0x14000c2ac`
- `0x14000c4ac`
- `0x14000d054`
- `0x14000d254`
- `0x14000d5a8`
- `0x14000f078`
- `0x14000f1a4`
- `0x1400115cc`
- `0x1400147fc`
- `0x140014b00`
- `0x1400153c4`
- `0x140015b30`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000c751`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c90e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c751`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c90e`
- `ntoskrnl!ExAllocatePool2` at `0x14000c68d`
- `ntoskrnl!ExAllocatePool2` at `0x14000c6fa`
- `ntoskrnl!ExAllocatePool2` at `0x14000c83f`
- `ntoskrnl!ExAllocatePool2` at `0x14000c8c6`
- `ntoskrnl!ExAllocatePool2` at `0x14000c68d`
- `ntoskrnl!ExAllocatePool2` at `0x14000c6fa`
- `ntoskrnl!ExAllocatePool2` at `0x14000c83f`
- `ntoskrnl!ExAllocatePool2` at `0x14000c8c6`

## string_xrefs

- `0x14000cbbd`: `StreamFault::Execute() - Stream Fault Buffer UpdateUserBuffer returned error status: 0x%08X.  Freeing MDL.`
- `0x14000c948`: `StreamFault::Execute() - StreamFaultWriter added to queue for file: %s, offset: %lld, length: %ld, status: 0x%08X.`
- `0x14000ca1f`: `StreamFault::Execute() - StreamFaultWriter was not added to queue for file: %s, offset: %lld, length: %ld; status: 0x%08X.  Block may not be written.`

## pseudocode

```c
__int64 __fastcall Streaming::StreamFault::Execute(Streaming::StreamFault *this)
{
  __int64 v1; // r10
  const wchar_t *v2; // rbx
  Streaming::StreamFault *v3; // r11
  __int64 v4; // rdx
  int v5; // r14d
  unsigned int v6; // r15d
  const wchar_t *v7; // r8
  const wchar_t *v8; // rcx
  __int64 v9; // r10
  __int64 v10; // r8
  StreamFaultBuffer *v11; // r13
  volatile signed __int32 *v12; // rdi
  int v13; // edx
  __int64 v14; // r15
  unsigned int v15; // ebx
  __int64 v16; // r14
  unsigned int v17; // eax
  unsigned int v18; // eax
  __int64 v19; // rsi
  __int64 *NullTerminated; // rax
  int v21; // eax
  volatile signed __int32 *v22; // rsi
  int v23; // r12d
  __int64 Pool2; // rcx
  __int64 v25; // rax
  __int64 v26; // rax
  volatile signed __int32 *v27; // rsi
  volatile signed __int32 *v28; // r14
  __int64 v29; // r13
  __int64 v30; // rax
  StreamFaultBuffer *v31; // r12
  __int64 v32; // rcx
  Streaming::StreamFaultWriter *v33; // r15
  volatile signed __int32 *v34; // rsi
  __int64 v35; // r10
  const void *v36; // r9
  Streaming::StreamFault *v37; // rbx
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 v40; // rdx
  __int64 v41; // rbx
  _QWORD *v42; // rax
  unsigned int v43; // r13d
  const wchar_t *v44; // r12
  volatile signed __int32 *v45; // rbx
  volatile signed __int32 *v46; // rbx
  __int64 v47; // rbx
  _QWORD *v48; // rax
  volatile signed __int32 *v49; // rbx
  __int64 v50; // rcx
  volatile signed __int32 *v51; // rbx
  _QWORD *v52; // rax
  __int64 v53; // rcx
  volatile signed __int32 *v54; // rbx
  volatile signed __int32 *v55; // rbx
  volatile signed __int32 *v57; // rbx
  _QWORD *v58; // rax
  __int64 v59; // rcx
  volatile signed __int32 *v60; // rbx
  volatile signed __int32 *v61; // rbx
  _QWORD *CurrentActivityID; // rax
  __int64 v63; // rcx
  volatile signed __int32 *v64; // rbx
  volatile signed __int32 *v65; // rbx
  __int64 v66; // [rsp+28h] [rbp-B1h]
  __int64 v67; // [rsp+30h] [rbp-A9h]
  int updated; // [rsp+40h] [rbp-99h] BYREF
  const wchar_t *v69; // [rsp+48h] [rbp-91h] BYREF
  __int128 v70; // [rsp+50h] [rbp-89h] BYREF
  StreamFaultBuffer *v71; // [rsp+60h] [rbp-79h]
  __int64 v72; // [rsp+68h] [rbp-71h]
  __int64 v73; // [rsp+70h] [rbp-69h]
  unsigned int v74[2]; // [rsp+78h] [rbp-61h]
  char v75[8]; // [rsp+80h] [rbp-59h] BYREF
  volatile signed __int32 *v76; // [rsp+88h] [rbp-51h]
  __int64 v77; // [rsp+90h] [rbp-49h]
  char *i; // [rsp+98h] [rbp-41h]
  _QWORD v79[2]; // [rsp+A0h] [rbp-39h] BYREF
  char v80[8]; // [rsp+B0h] [rbp-29h] BYREF
  volatile signed __int32 *v81; // [rsp+B8h] [rbp-21h]
  char v82[8]; // [rsp+C0h] [rbp-19h] BYREF
  volatile signed __int32 *v83; // [rsp+C8h] [rbp-11h]
  char v84[8]; // [rsp+D0h] [rbp-9h] BYREF
  volatile signed __int32 *v85; // [rsp+D8h] [rbp-1h]
  char v86[8]; // [rsp+E0h] [rbp+7h] BYREF
  volatile signed __int32 *v87; // [rsp+E8h] [rbp+Fh]
  bool v89; // [rsp+148h] [rbp+6Fh] BYREF
  unsigned int v90; // [rsp+150h] [rbp+77h] BYREF
  int v91; // [rsp+158h] [rbp+7Fh]

  v1 = *((unsigned int *)this + 8);
  v2 = (const wchar_t *)*((_QWORD *)this + 3);
  v3 = this;
  v4 = *(_QWORD *)this;
  v5 = 0;
  v6 = 0;
  v91 = 0;
  *(_QWORD *)v74 = v1;
  v7 = *(const wchar_t **)(v4 + 80);
  if ( (__int64)((char *)v2 + v1) > (__int64)v7 )
  {
    v1 = (unsigned int)((_DWORD)v7 - (_DWORD)v2);
    *(_QWORD *)v74 = v1;
  }
  v8 = v2;
  if ( (__int64)v2 % 0x10000 )
    v8 = (const wchar_t *)((char *)v2 - (__int64)v2 % 0x10000);
  v9 = (__int64)v2 + v1 - (_QWORD)v8;
  v73 = v9;
  if ( v9 % 0x10000 )
  {
    if ( (const wchar_t *)((char *)v8 + v9) != v7 )
    {
      v10 = (char *)v7 - (char *)v8;
      v9 = v9 - v9 % 0x10000 + 0x10000;
      if ( v10 < v9 )
        v9 = v10;
    }
    v73 = v9;
  }
  v69 = v8;
  v11 = 0;
  v12 = 0;
  v71 = 0;
  v77 = (unsigned int)v9;
  if ( (_DWORD)v9 )
  {
    v13 = 0;
    v14 = (__int64)v3 + 48;
    v72 = 0;
    v15 = (_DWORD)v2 - (_DWORD)v8;
    for ( i = (char *)v3 + 48; ; v14 = (__int64)i )
    {
      v16 = *((_QWORD *)v3 + 12);
      v89 = 0;
      v17 = v9 - v13;
      v70 = 0;
      if ( (unsigned int)(v9 - v13) > 0x100000 )
        v17 = 0x100000;
      v90 = v17;
      v18 = *((_DWORD *)v3 + 16) >> 1;
      if ( v18 <= 0xFFFF && (_WORD)v18 )
        v19 = *((_QWORD *)v3 + 9);
      else
        LODWORD(v19) = 0;
      NullTerminated = (__int64 *)Streaming::Utils::GetNullTerminated(v80, *(_QWORD *)v3 + 32LL);
      v21 = Streaming::staging_operations::stream_fault(
              *NullTerminated,
              (__int64 *)&v69,
              &v90,
              v19,
              v16,
              v14,
              &v89,
              &v70);
      v22 = v81;
      v23 = v21;
      if ( v81 )
      {
        if ( _InterlockedExchangeAdd(v81 + 2, 0xFFFFFFFF) == 1 )
        {
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v22 + 8LL))(v22);
          if ( _InterlockedExchangeAdd(v22 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v22 + 16LL))(v22);
        }
      }
      if ( v11 && v12 && *((_DWORD *)v12 + 2) )
        goto LABEL_45;
      v6 = 0;
      updated = 0;
      Pool2 = ExAllocatePool2(64, 48, 1718838899);
      if ( Pool2 )
      {
        v25 = StreamFaultBuffer::StreamFaultBuffer(
                Pool2,
                (struct _FLT_CALLBACK_DATA_QUEUE *)(*((_QWORD *)this + 1) + 104LL),
                *((void **)this + 5),
                (__int64)this + 16,
                *(_QWORD *)this + 16LL,
                v74[0],
                &updated);
        v6 = updated;
        v11 = (StreamFaultBuffer *)v25;
      }
      else
      {
        v11 = 0;
      }
      v71 = v11;
      v26 = ExAllocatePool2(256, 24, 1715758931);
      v27 = (volatile signed __int32 *)v26;
      if ( !v26 )
        break;
      *(_QWORD *)(v26 + 16) = v11;
      *(_DWORD *)(v26 + 8) = 1;
      *(_DWORD *)(v26 + 12) = 1;
      *(_QWORD *)v26 = &kernel_std::detail::sp_counted_impl_p<StreamFaultBuffer>::`vftable';
      if ( !*(_DWORD *)(v26 + 8) )
        goto LABEL_36;
LABEL_37:
      v28 = v12;
      v12 = v27;
      if ( v28 )
      {
        if ( _InterlockedExchangeAdd(v28 + 2, 0xFFFFFFFF) == 1 )
        {
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v28 + 8LL))(v28);
          if ( _InterlockedExchangeAdd(v28 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v28 + 16LL))(v28);
        }
      }
      if ( !v11 || !v27 || !*((_DWORD *)v27 + 2) )
      {
        CurrentActivityID = (_QWORD *)Streaming::Utils::GetCurrentActivityID(v75);
        LogWrite(4, *CurrentActivityID, L"StreamFault::Execute() - Stream Fault Buffer reset failed.  Freeing MDL.");
        v64 = v76;
        if ( v76 )
        {
          if ( _InterlockedExchangeAdd(v76 + 2, 0xFFFFFFFF) == 1 )
          {
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v64 + 8LL))(v64);
            if ( _InterlockedExchangeAdd(v64 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v64 + 16LL))(v64);
          }
        }
        Streaming::MDLCache::FreeMDL(v63, &v70);
        v65 = (volatile signed __int32 *)*((_QWORD *)&v70 + 1);
        if ( *((_QWORD *)&v70 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v70 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v65 + 8LL))(v65);
            if ( _InterlockedExchangeAdd(v65 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v65 + 16LL))(v65);
          }
        }
        if ( v27 )
        {
          if ( _InterlockedExchangeAdd(v27 + 2, 0xFFFFFFFF) == 1 )
          {
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v27 + 8LL))(v27);
            if ( _InterlockedExchangeAdd(v27 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v27 + 16LL))(v27);
          }
        }
        return 3221225626LL;
      }
      if ( (v6 & 0x80000000) != 0 )
      {
        v58 = (_QWORD *)Streaming::Utils::GetCurrentActivityID(v75);
        LogWrite(
          4,
          *v58,
          L"StreamFault::Execute() - Stream Fault Buffer returned error status: 0x%08X.  Freeing MDL.",
          v6);
        v60 = v76;
        if ( v76 )
        {
          if ( _InterlockedExchangeAdd(v76 + 2, 0xFFFFFFFF) == 1 )
          {
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v60 + 8LL))(v60);
            if ( _InterlockedExchangeAdd(v60 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v60 + 16LL))(v60);
          }
        }
        Streaming::MDLCache::FreeMDL(v59, &v70);
        v61 = (volatile signed __int32 *)*((_QWORD *)&v70 + 1);
        if ( *((_QWORD *)&v70 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v70 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v61 + 8LL))(v61);
            if ( _InterlockedExchangeAdd(v61 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v61 + 16LL))(v61);
          }
        }
        if ( _InterlockedExchangeAdd(v27 + 2, 0xFFFFFFFF) != 1 )
          return v6;
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v27 + 8LL))(v27);
        if ( _InterlockedExchangeAdd(v27 + 3, 0xFFFFFFFF) != 1 )
          return v6;
LABEL_149:
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 16LL))(v12);
        return v6;
      }
LABEL_45:
      if ( v23 < 0 )
      {
        StreamFaultBuffer::Complete(v11, v23, 0);
        v57 = (volatile signed __int32 *)*((_QWORD *)&v70 + 1);
        if ( *((_QWORD *)&v70 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v70 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v57 + 8LL))(v57);
            if ( _InterlockedExchangeAdd(v57 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v57 + 16LL))(v57);
          }
        }
        if ( v12 )
        {
          if ( _InterlockedExchangeAdd(v12 + 2, 0xFFFFFFFF) == 1 )
          {
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
            if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 16LL))(v12);
          }
        }
        return (unsigned int)v23;
      }
      v29 = v70;
      v30 = *(_QWORD *)(v70 + 24);
      if ( !v30 )
        v30 = *(_QWORD *)(v70 + 32);
      v31 = v71;
      updated = StreamFaultBuffer::UpdateUserBuffer(v71, (void *)(v30 + v15), v90 - v15);
      v5 = updated;
      if ( updated < 0 )
      {
        v52 = (_QWORD *)Streaming::Utils::GetCurrentActivityID(v75);
        LogWrite(
          4,
          *v52,
          L"StreamFault::Execute() - Stream Fault Buffer UpdateUserBuffer returned error status: 0x%08X.  Freeing MDL.",
          (unsigned int)v5);
        v54 = v76;
        if ( v76 )
        {
          if ( _InterlockedExchangeAdd(v76 + 2, 0xFFFFFFFF) == 1 )
          {
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v54 + 8LL))(v54);
            if ( _InterlockedExchangeAdd(v54 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v54 + 16LL))(v54);
          }
        }
        Streaming::MDLCache::FreeMDL(v53, &v70);
        StreamFaultBuffer::Complete(v31, v5, 0);
        v55 = (volatile signed __int32 *)*((_QWORD *)&v70 + 1);
        if ( *((_QWORD *)&v70 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v70 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v55 + 8LL))(v55);
            if ( _InterlockedExchangeAdd(v55 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v55 + 16LL))(v55);
          }
        }
        goto LABEL_106;
      }
      v33 = 0;
      v34 = 0;
      if ( *((_BYTE *)Streaming::gStrmFltData + 48) || v89 )
      {
        v44 = v69;
        v43 = v90;
        goto LABEL_79;
      }
      v35 = ExAllocatePool2(64, 72, 2003199603);
      if ( v35 )
      {
        v36 = *(const void **)(v29 + 24);
        if ( !v36 )
          v36 = *(const void **)(v29 + 32);
        v37 = this;
        v38 = Streaming::StreamFaultWriter::StreamFaultWriter(
                v35,
                (PFLT_CONTEXT *)this,
                *(struct _FLT_INSTANCE **)(*((_QWORD *)this + 1) + 16LL),
                v36,
                &v69,
                &v90,
                (**(_DWORD **)(*(_QWORD *)v31 + 16LL) & 2u) << 24,
                &updated);
        v5 = updated;
        v33 = (Streaming::StreamFaultWriter *)v38;
      }
      else
      {
        v37 = this;
      }
      v39 = ExAllocatePool2(256, 24, 1715758931);
      v34 = (volatile signed __int32 *)v39;
      if ( !v39 )
      {
        if ( v33 )
        {
          Streaming::StreamFaultWriter::~StreamFaultWriter(v33);
          ExFreePoolWithTag(v33, 0);
        }
        v34 = 0;
LABEL_62:
        v33 = 0;
        goto LABEL_63;
      }
      *(_QWORD *)(v39 + 16) = v33;
      *(_DWORD *)(v39 + 8) = 1;
      *(_DWORD *)(v39 + 12) = 1;
      *(_QWORD *)v39 = &kernel_std::detail::sp_counted_impl_p<Streaming::StreamFaultWriter>::`vftable';
      if ( !*(_DWORD *)(v39 + 8) )
        goto LABEL_62;
LABEL_63:
      v40 = *(_QWORD *)v37 + 64LL;
      if ( v5 < 0 )
      {
        v47 = *(_QWORD *)Streaming::Utils::GetNullTerminated(v75, v40);
        v48 = (_QWORD *)Streaming::Utils::GetCurrentActivityID(v86);
        v43 = v90;
        v44 = v69;
        LODWORD(v67) = v5;
        LODWORD(v66) = v90;
        LogWrite(
          1,
          *v48,
          L"StreamFault::Execute() - StreamFaultWriter was not added to queue for file: %s, offset: %lld, length: %ld; sta"
           "tus: 0x%08X.  Block may not be written.",
          v47,
          v69,
          v66,
          v67);
        v49 = v87;
        if ( v87 )
        {
          if ( _InterlockedExchangeAdd(v87 + 2, 0xFFFFFFFF) == 1 )
          {
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v49 + 8LL))(v49);
            if ( _InterlockedExchangeAdd(v49 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v49 + 16LL))(v49);
          }
        }
        v46 = v76;
      }
      else
      {
        v41 = *(_QWORD *)Streaming::Utils::GetNullTerminated(v84, v40);
        v42 = (_QWORD *)Streaming::Utils::GetCurrentActivityID(v82);
        v43 = v90;
        v44 = v69;
        LODWORD(v67) = v5;
        LODWORD(v66) = v90;
        LogWrite(
          3,
          *v42,
          L"StreamFault::Execute() - StreamFaultWriter added to queue for file: %s, offset: %lld, length: %ld, status: 0x%08X.",
          v41,
          v69,
          v66,
          v67);
        v45 = v83;
        if ( v83 )
        {
          if ( _InterlockedExchangeAdd(v83 + 2, 0xFFFFFFFF) == 1 )
          {
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v45 + 8LL))(v45);
            if ( _InterlockedExchangeAdd(v45 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v45 + 16LL))(v45);
          }
        }
        v46 = v85;
      }
      if ( v46 )
      {
        if ( _InterlockedExchangeAdd(v46 + 2, 0xFFFFFFFF) == 1 )
        {
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v46 + 8LL))(v46);
          if ( _InterlockedExchangeAdd(v46 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v46 + 16LL))(v46);
        }
      }
LABEL_79:
      Streaming::MDLCache::FreeMDL(v32, &v70);
      v72 += v43;
      v69 = (const wchar_t *)((char *)v44 + v43);
      if ( !*((_BYTE *)Streaming::gStrmFltData + 48) && !v89 )
      {
        if ( v5 >= 0 )
        {
          if ( v33 )
          {
            v79[0] = v33;
            v79[1] = v34;
            v50 = *(_QWORD *)(*((_QWORD *)this + 1) + 256LL);
            if ( v34 )
              _InterlockedIncrement(v34 + 2);
            Streaming::StreamFaultWriterWorker::Process(v50, v79);
          }
          else
          {
            v91 = -1073741670;
          }
        }
        else
        {
          v91 = v5;
        }
      }
      if ( v34 )
      {
        if ( _InterlockedExchangeAdd(v34 + 2, 0xFFFFFFFF) == 1 )
        {
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v34 + 8LL))(v34);
          if ( _InterlockedExchangeAdd(v34 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v34 + 16LL))(v34);
        }
      }
      v51 = (volatile signed __int32 *)*((_QWORD *)&v70 + 1);
      if ( *((_QWORD *)&v70 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v70 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v51 + 8LL))(v51);
          if ( _InterlockedExchangeAdd(v51 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v51 + 16LL))(v51);
        }
      }
      v13 = v72;
      v11 = v71;
      if ( v72 >= v77 )
      {
        v6 = v91;
        goto LABEL_145;
      }
      LODWORD(v9) = v73;
      v15 = 0;
      v3 = this;
    }
    if ( v11 )
    {
      if ( *(_QWORD *)v11 )
        StreamFaultBuffer::Complete(v11, -1073741595, 0);
      ExFreePoolWithTag(v11, 0);
    }
    v27 = 0;
LABEL_36:
    v11 = 0;
    v71 = 0;
    goto LABEL_37;
  }
LABEL_145:
  StreamFaultBuffer::Complete(v11, v5, v74[0]);
  if ( v5 >= 0 )
  {
    if ( v12 )
    {
      if ( _InterlockedExchangeAdd(v12 + 2, 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
        if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
          goto LABEL_149;
      }
    }
    return v6;
  }
LABEL_106:
  if ( v12 )
  {
    if ( _InterlockedExchangeAdd(v12 + 2, 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
      if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 16LL))(v12);
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14000c4ac  mov     [rsp-8+arg_0], rcx
0x14000c4b1  push    rbp
0x14000c4b2  push    rbx
0x14000c4b3  push    rsi
0x14000c4b4  push    rdi
0x14000c4b5  push    r12
0x14000c4b7  push    r13
0x14000c4b9  push    r14
0x14000c4bb  push    r15
0x14000c4bd  lea     rbp, [rsp-1Fh]
0x14000c4c2  sub     rsp, 0F8h
0x14000c4c9  mov     r10d, [rcx+20h]
0x14000c4cd  xor     r12d, r12d
0x14000c4d0  mov     rbx, [rcx+18h]
0x14000c4d4  mov     r11, rcx
0x14000c4d7  mov     rdx, [rcx]
0x14000c4da  mov     r14d, r12d
0x14000c4dd  mov     r15d, r12d
0x14000c4e0  mov     [rbp+57h+arg_18], r12d
0x14000c4e4  mov     qword ptr [rbp+57h+var_B8], r10
0x14000c4e8  lea     rax, [rbx+r10]
0x14000c4ec  mov     r8, [rdx+50h]
0x14000c4f0  cmp     rax, r8
0x14000c4f3  jle     short loc_14000C4FF
0x14000c4f5  mov     r10d, r8d
0x14000c4f8  sub     r10d, ebx
0x14000c4fb  mov     qword ptr [rbp+57h+var_B8], r10
0x14000c4ff  mov     edi, 0FFFFh
0x14000c504  mov     rax, rbx
0x14000c507  cqo
0x14000c509  mov     rcx, rbx
0x14000c50c  and     rdx, rdi
0x14000c50f  add     rax, rdx
0x14000c512  and     rax, rdi
0x14000c515  sub     rax, rdx
0x14000c518  jz      short loc_14000C51D
0x14000c51a  sub     rcx, rax
0x14000c51d  sub     r10, rcx
0x14000c520  mov     r9, rcx
0x14000c523  add     r10, rbx
0x14000c526  sar     r9, 20h
0x14000c52a  mov     rax, r10
0x14000c52d  mov     [rbp+57h+var_C0], r10
0x14000c531  cqo
0x14000c533  and     rdx, rdi
0x14000c536  add     rax, rdx
0x14000c539  and     rax, rdi
0x14000c53c  sub     rax, rdx
0x14000c53f  mov     rdx, rax
0x14000c542  jz      short loc_14000C565
0x14000c544  lea     rax, [r10+rcx]
0x14000c548  cmp     rax, r8
0x14000c54b  jz      short loc_14000C561
0x14000c54d  sub     r10, rdx
0x14000c550  sub     r8, rcx
0x14000c553  add     r10, 10000h
0x14000c55a  cmp     r8, r10
0x14000c55d  cmovl   r10, r8
0x14000c561  mov     [rbp+57h+var_C0], r10
0x14000c565  or      esi, 0FFFFFFFFh
0x14000c568  mov     eax, r10d
0x14000c56b  mov     dword ptr [rsp+130h+var_E8], ecx
0x14000c56f  mov     r13, r12
0x14000c572  mov     dword ptr [rsp+130h+var_E8+4], r9d
0x14000c577  mov     rdi, r12
0x14000c57a  mov     [rbp+57h+var_D0], r12
0x14000c57e  mov     [rbp+57h+var_A0], rax
0x14000c582  test    r10d, r10d
0x14000c585  jz      loc_14000CF02
0x14000c58b  mov     rdx, r12
0x14000c58e  lea     r15, [r11+30h]
0x14000c592  mov     [rbp+57h+var_C8], rdx
0x14000c596  sub     ebx, ecx
0x14000c598  mov     [rbp+57h+var_98], r15
0x14000c59c  mov     r14, [r11+60h]
0x14000c5a0  mov     ecx, 100000h
0x14000c5a5  mov     eax, r10d
0x14000c5a8  mov     [rbp+57h+arg_8], r12b
0x14000c5ac  sub     eax, edx
0x14000c5ae  xorps   xmm0, xmm0
0x14000c5b1  cmp     eax, ecx
0x14000c5b3  movdqu  [rsp+130h+var_E0], xmm0
0x14000c5b9  cmova   eax, ecx
0x14000c5bc  mov     [rbp+57h+arg_10], eax
0x14000c5bf  mov     eax, [r11+40h]
0x14000c5c3  shr     eax, 1
0x14000c5c5  cmp     eax, 0FFFFh
0x14000c5ca  ja      short loc_14000C5D7
0x14000c5cc  test    ax, ax
0x14000c5cf  jz      short loc_14000C5D7
0x14000c5d1  mov     rsi, [r11+48h]
0x14000c5d5  jmp     short loc_14000C5DA
0x14000c5d7  mov     rsi, r12
0x14000c5da  mov     rdx, [r11]
0x14000c5dd  lea     rcx, [rbp+57h+var_80]
0x14000c5e1  add     rdx, 20h ; ' '
0x14000c5e5  call    ?GetNullTerminated@Utils@Streaming@@YA?AV?$shared_ptr@_W@kernel_std@@PEBU_UNICODE_STRING@@@Z; Streaming::Utils::GetNullTerminated(_UNICODE_STRING const *)
0x14000c5ea  lea     rcx, [rsp+130h+var_E0]
0x14000c5ef  mov     r9, rsi
0x14000c5f2  mov     [rsp+130h+var_F8], rcx
0x14000c5f7  lea     r8, [rbp+57h+arg_10]
0x14000c5fb  lea     rcx, [rbp+57h+arg_8]
0x14000c5ff  mov     [rsp+130h+var_100], rcx
0x14000c604  lea     rdx, [rsp+130h+var_E8]
0x14000c609  mov     rcx, [rax]
0x14000c60c  mov     [rsp+130h+var_108], r15
0x14000c611  mov     [rsp+130h+var_110], r14
0x14000c616  call    ?stream_fault@staging_operations@Streaming@@YAJPEB_WAEB_JAEBK0QEAXAEBU_GUID@@AEA_NAEAV?$shared_ptr@Vkmdl@kernel@shared@appv@@@kernel_std@@@Z; Streaming::staging_operations::stream_fault(wchar_t const *,__int64 const &,ulong const &,wchar_t const *,void * const,_GUID const &,bool &,kernel_std::shared_ptr<appv::shared::kernel::kmdl> &)
0x14000c61b  mov     rsi, [rbp+57h+var_78]
0x14000c61f  mov     r12d, eax
0x14000c622  test    rsi, rsi
0x14000c625  jz      short loc_14000C663
0x14000c627  or      r14d, 0FFFFFFFFh
0x14000c62b  mov     eax, r14d
0x14000c62e  lock xadd [rsi+8], eax
0x14000c633  add     eax, r14d
0x14000c636  jnz     short loc_14000C663
0x14000c638  mov     rax, [rsi]
0x14000c63b  mov     rcx, rsi
0x14000c63e  mov     rax, [rax+8]
0x14000c642  call    _guard_dispatch_icall
0x14000c647  mov     eax, r14d
0x14000c64a  lock xadd [rsi+0Ch], eax
0x14000c64f  add     eax, r14d
0x14000c652  jnz     short loc_14000C663
0x14000c654  mov     rax, [rsi]
0x14000c657  mov     rcx, rsi
0x14000c65a  mov     rax, [rax+10h]
0x14000c65e  call    _guard_dispatch_icall
0x14000c663  test    r13, r13
0x14000c666  jz      short loc_14000C678
0x14000c668  test    rdi, rdi
0x14000c66b  jz      short loc_14000C678
0x14000c66d  mov     eax, [rdi+8]
0x14000c670  test    eax, eax
0x14000c672  jnz     loc_14000C7D1
0x14000c678  xor     r15d, r15d
0x14000c67b  mov     r8d, 66736673h
0x14000c681  mov     [rsp+130h+var_F0], r15d
0x14000c686  lea     edx, [r15+30h]
0x14000c68a  lea     ecx, [rdx+10h]
0x14000c68d  call    cs:__imp_ExAllocatePool2
0x14000c694  nop     dword ptr [rax+rax+00h]
0x14000c699  mov     rcx, rax
0x14000c69c  test    rax, rax
0x14000c69f  jz      short loc_14000C6E3
0x14000c6a1  mov     r8, [rbp+57h+arg_0]
0x14000c6a5  lea     r10, [rsp+130h+var_F0]
0x14000c6aa  mov     [rsp+130h+var_100], r10
0x14000c6af  mov     r10, qword ptr [rbp+57h+var_B8]
0x14000c6b3  mov     dword ptr [rsp+130h+var_108], r10d
0x14000c6b8  mov     rax, [r8]
0x14000c6bb  lea     r9, [r8+10h]
0x14000c6bf  mov     rdx, [r8+8]
0x14000c6c3  add     rax, 10h
0x14000c6c7  mov     r8, [r8+28h]
0x14000c6cb  add     rdx, 68h ; 'h'
0x14000c6cf  mov     [rsp+130h+var_110], rax
0x14000c6d4  call    ??0StreamFaultBuffer@@QEAA@PEAU_FLT_CALLBACK_DATA_QUEUE@@PEAU_IO_CSQ_IRP_CONTEXT@@AEAV?$auto_ptr@U_FILE_OBJECT@@UObjectDelete@kernel@shared@appv@@@kernel@shared@appv@@AEAV?$managed_unicode_string@UUnicodeString_allocator@kernel@shared@appv@@@456@KAEAJ@Z; StreamFaultBuffer::StreamFaultBuffer(_FLT_CALLBACK_DATA_QUEUE *,_IO_CSQ_IRP_CONTEXT *,appv::shared::kernel::auto_ptr<_FILE_OBJECT,appv::shared::kernel::ObjectDelete> &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator> &,ulong,long &)
0x14000c6d9  mov     r15d, [rsp+130h+var_F0]
0x14000c6de  mov     r13, rax
0x14000c6e1  jmp     short loc_14000C6E6
0x14000c6e3  xor     r13d, r13d
0x14000c6e6  mov     edx, 18h
0x14000c6eb  mov     [rbp+57h+var_D0], r13
0x14000c6ef  mov     ecx, 100h
0x14000c6f4  mov     r8d, 66446753h
0x14000c6fa  call    cs:__imp_ExAllocatePool2
0x14000c701  nop     dword ptr [rax+rax+00h]
0x14000c706  mov     rsi, rax
0x14000c709  test    rax, rax
0x14000c70c  jz      short loc_14000C730
0x14000c70e  mov     eax, 1
0x14000c713  mov     [rsi+10h], r13
0x14000c717  mov     [rsi+8], eax
0x14000c71a  mov     [rsi+0Ch], eax
0x14000c71d  lea     rax, ??_7?$sp_counted_impl_p@VStreamFaultBuffer@@@detail@kernel_std@@6B@; const kernel_std::detail::sp_counted_impl_p<StreamFaultBuffer>::`vftable'
0x14000c724  mov     [rsi], rax
0x14000c727  mov     eax, [rsi+8]
0x14000c72a  test    eax, eax
0x14000c72c  jnz     short loc_14000C766
0x14000c72e  jmp     short loc_14000C75F
0x14000c730  test    r13, r13
0x14000c733  jz      short loc_14000C75D
0x14000c735  cmp     qword ptr [r13+0], 0
0x14000c73a  jz      short loc_14000C74C
0x14000c73c  xor     r8d, r8d; unsigned int
0x14000c73f  mov     edx, 0C00000E5h; int
0x14000c744  mov     rcx, r13; this
0x14000c747  call    ?Complete@StreamFaultBuffer@@QEAAXJK@Z; StreamFaultBuffer::Complete(long,ulong)
0x14000c74c  xor     edx, edx; Tag
0x14000c74e  mov     rcx, r13; P
0x14000c751  call    cs:__imp_ExFreePoolWithTag
0x14000c758  nop     dword ptr [rax+rax+00h]
0x14000c75d  xor     esi, esi
0x14000c75f  xor     r13d, r13d
0x14000c762  mov     [rbp+57h+var_D0], r13
0x14000c766  mov     r14, rdi
0x14000c769  mov     rdi, rsi
0x14000c76c  test    r14, r14
0x14000c76f  jz      short loc_14000C7AB
0x14000c771  or      eax, 0FFFFFFFFh
0x14000c774  lock xadd [r14+8], eax
0x14000c77a  cmp     eax, 1
0x14000c77d  jnz     short loc_14000C7AB
0x14000c77f  mov     rax, [r14]
0x14000c782  mov     rcx, r14
0x14000c785  mov     rax, [rax+8]
0x14000c789  call    _guard_dispatch_icall
0x14000c78e  or      eax, 0FFFFFFFFh
0x14000c791  lock xadd [r14+0Ch], eax
0x14000c797  cmp     eax, 1
0x14000c79a  jnz     short loc_14000C7AB
0x14000c79c  mov     rax, [r14]
0x14000c79f  mov     rcx, r14
0x14000c7a2  mov     rax, [rax+10h]
0x14000c7a6  call    _guard_dispatch_icall
0x14000c7ab  test    r13, r13
0x14000c7ae  jz      loc_14000CE19
0x14000c7b4  test    rsi, rsi
0x14000c7b7  jz      loc_14000CE19
0x14000c7bd  mov     eax, [rsi+8]
0x14000c7c0  test    eax, eax
0x14000c7c2  jz      loc_14000CE19
0x14000c7c8  test    r15d, r15d
0x14000c7cb  js      loc_14000CD38
0x14000c7d1  test    r12d, r12d
0x14000c7d4  js      loc_14000CCA8
0x14000c7da  mov     r13, qword ptr [rsp+130h+var_E0]
0x14000c7df  mov     r8d, [rbp+57h+arg_10]
0x14000c7e3  sub     r8d, ebx; unsigned int
0x14000c7e6  mov     rax, [r13+18h]
0x14000c7ea  test    rax, rax
0x14000c7ed  jnz     short loc_14000C7F3
0x14000c7ef  mov     rax, [r13+20h]
0x14000c7f3  mov     r12, [rbp+57h+var_D0]
0x14000c7f7  mov     edx, ebx
0x14000c7f9  mov     rcx, r12; this
0x14000c7fc  add     rdx, rax; void *
0x14000c7ff  call    ?UpdateUserBuffer@StreamFaultBuffer@@QEAAJPEAXK@Z; StreamFaultBuffer::UpdateUserBuffer(void *,ulong)
0x14000c804  mov     [rsp+130h+var_F0], eax
0x14000c808  mov     r14d, eax
0x14000c80b  test    eax, eax
0x14000c80d  js      loc_14000CBB1
0x14000c813  mov     rax, cs:?gStrmFltData@Streaming@@3PEAUStrmGlobalData@1@EA; Streaming::StrmGlobalData * Streaming::gStrmFltData
0x14000c81a  xor     r15d, r15d
0x14000c81d  xor     esi, esi
0x14000c81f  cmp     [rax+30h], sil
0x14000c823  jnz     loc_14000CA94
0x14000c829  cmp     [rbp+57h+arg_8], sil
0x14000c82d  jnz     loc_14000CA94
0x14000c833  lea     edx, [rsi+48h]
0x14000c836  mov     r8d, 77666673h
0x14000c83c  lea     ecx, [rsi+40h]
0x14000c83f  call    cs:__imp_ExAllocatePool2
0x14000c846  nop     dword ptr [rax+rax+00h]
0x14000c84b  mov     r10, rax
0x14000c84e  test    rax, rax
0x14000c851  jz      short loc_14000C8B2
0x14000c853  mov     rax, [r12]
0x14000c857  mov     r9, [r13+18h]
0x14000c85b  mov     rcx, [rax+10h]
0x14000c85f  mov     eax, [rcx]
0x14000c861  and     eax, 2
0x14000c864  shl     eax, 18h
0x14000c867  test    r9, r9
0x14000c86a  jnz     short loc_14000C870
0x14000c86c  mov     r9, [r13+20h]
0x14000c870  mov     rbx, [rbp+57h+arg_0]
0x14000c874  lea     rcx, [rsp+130h+var_F0]
0x14000c879  mov     [rsp+130h+var_F8], rcx
0x14000c87e  mov     rdx, rbx
0x14000c881  mov     dword ptr [rsp+130h+var_100], eax
0x14000c885  mov     rcx, r10
0x14000c888  lea     rax, [rbp+57h+arg_10]
0x14000c88c  mov     r8, [rbx+8]
0x14000c890  mov     [rsp+130h+var_108], rax
0x14000c895  lea     rax, [rsp+130h+var_E8]
0x14000c89a  mov     [rsp+130h+var_110], rax
0x14000c89f  mov     r8, [r8+10h]
0x14000c8a3  call    ??0StreamFaultWriter@Streaming@@QEAA@AEAV?$auto_ptr@UStrmStreamContext@Context@Streaming@@UContextDelete@23@@kernel@shared@appv@@PEAU_FLT_INSTANCE@@PEAXAEA_JAEAKIAEAJ@Z; Streaming::StreamFaultWriter::StreamFaultWriter(appv::shared::kernel::auto_ptr<Streaming::Context::StrmStreamContext,Streaming::Context::ContextDelete> &,_FLT_INSTANCE *,void *,__int64 &,ulong &,uint,long &)
0x14000c8a8  mov     r14d, [rsp+130h+var_F0]
0x14000c8ad  mov     r15, rax
0x14000c8b0  jmp     short loc_14000C8B6
0x14000c8b2  mov     rbx, [rbp+57h+arg_0]
0x14000c8b6  mov     edx, 18h
0x14000c8bb  mov     ecx, 100h
0x14000c8c0  mov     r8d, 66446753h
0x14000c8c6  call    cs:__imp_ExAllocatePool2
0x14000c8cd  nop     dword ptr [rax+rax+00h]
0x14000c8d2  mov     rsi, rax
0x14000c8d5  test    rax, rax
0x14000c8d8  jz      short loc_14000C8FC
0x14000c8da  mov     eax, 1
0x14000c8df  mov     [rsi+10h], r15
0x14000c8e3  mov     [rsi+8], eax
0x14000c8e6  mov     [rsi+0Ch], eax
0x14000c8e9  lea     rax, ??_7?$sp_counted_impl_p@VStreamFaultWriter@Streaming@@@detail@kernel_std@@6B@; const kernel_std::detail::sp_counted_impl_p<Streaming::StreamFaultWriter>::`vftable'
0x14000c8f0  mov     [rsi], rax
0x14000c8f3  mov     eax, [rsi+8]
  ... truncated ...
```
