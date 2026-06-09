# NtfsFileLevelTrim

- ea: `0x14023370c`
- end: `0x140234fee`
- name: `NtfsFileLevelTrim`
- size: `6370`
- prototype: `__int64 __fastcall(PVOID Context, PIRP Irp)`
- caller_count: `1`
- callee_count: `24`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1401f58e0`

## callees

- `0x140007ea0`
- `0x1400082b0`
- `0x14000c290`
- `0x14000cb00`
- `0x14000e220`
- `0x14000e670`
- `0x1400100b0`
- `0x140012e70`
- `0x140021590`
- `0x1400410a8`
- `0x140059740`
- `0x14012c23c`
- `0x14012d1a0`
- `0x1401403d0`
- `0x140160c30`
- `0x140160ee0`
- `0x140162110`
- `0x1401623c0`
- `0x140181bb0`
- `0x1401be3e8`
- `0x1401c0130`
- `0x14023370c`
- `0x140234ff4`
- `0x140235020`

## import_xrefs

- `ntoskrnl!IoGetRequestorProcess` at `0x140234410`
- `ntoskrnl!IoGetRequestorProcess` at `0x140234410`
- `ntoskrnl!ExSetResourceOwnerPointerEx` at `0x140234ede`
- `ntoskrnl!ExSetResourceOwnerPointerEx` at `0x1402b6f57`
- `ntoskrnl!ExSetResourceOwnerPointerEx` at `0x140234ede`
- `ntoskrnl!ExSetResourceOwnerPointerEx` at `0x1402b6f57`
- `ntoskrnl!FsRtlFastCheckLockForWrite` at `0x14023443e`
- `ntoskrnl!FsRtlFastCheckLockForWrite` at `0x14023443e`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140234e57`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140234f14`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402b6e9b`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402b6f8e`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140234e57`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140234f14`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402b6e9b`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402b6f8e`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140233c58`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140234148`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1402349e1`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140233c58`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140234148`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1402349e1`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x140234080`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x140234080`
- `HAL!KeQueryPerformanceCounter` at `0x140233806`
- `HAL!KeQueryPerformanceCounter` at `0x140234d2c`
- `HAL!KeQueryPerformanceCounter` at `0x1402b6d72`
- `HAL!KeQueryPerformanceCounter` at `0x140233806`
- `HAL!KeQueryPerformanceCounter` at `0x140234d2c`
- `HAL!KeQueryPerformanceCounter` at `0x1402b6d72`

## pseudocode

```c
__int64 __fastcall NtfsFileLevelTrim(_BYTE *Context, PIRP Irp, __int64 a3, __int64 a4)
{
  PIRP v4; // rsi
  _BYTE *v5; // r13
  _QWORD *p_Type; // rax
  __int64 v7; // r14
  __int64 v8; // rbx
  __int64 v9; // r15
  int v10; // eax
  unsigned int v11; // r14d
  __int64 v12; // r8
  LARGE_INTEGER PerformanceCounter; // rdi
  LARGE_INTEGER v14; // r9
  int v15; // ecx
  unsigned int v16; // ebx
  __int64 v17; // r8
  unsigned int Options; // r8d
  ULONG v20; // eax
  int v21; // ebx
  unsigned __int64 v22; // rcx
  _QWORD *v23; // rax
  __int64 v24; // r9
  _QWORD *v25; // r14
  __int64 v26; // r8
  struct _IRP *v27; // rax
  __int64 v28; // rdx
  __int64 v29; // rax
  char v30; // al
  __int64 v31; // rcx
  __int64 v32; // r8
  __int64 v33; // r9
  int v34; // edx
  __int64 v35; // rax
  char PurgeKernelEAState; // al
  __int64 v37; // r8
  __int16 v38; // r8
  __int16 v39; // ax
  int v40; // eax
  signed int v41; // r14d
  __int64 v42; // r8
  __int64 v43; // rbx
  NTSTATUS v44; // eax
  _WORD *v45; // rax
  __int64 v46; // rsi
  __int16 v47; // ax
  ULONG v48; // eax
  ULONG *v49; // rcx
  __int64 v50; // r11
  union _LARGE_INTEGER v51; // rax
  union _LARGE_INTEGER v52; // r8
  __int64 v53; // r9
  __int64 v54; // rdx
  unsigned __int64 QuadPart; // rcx
  __int64 v56; // r8
  unsigned __int64 v57; // rdx
  unsigned __int64 v58; // r10
  union _LARGE_INTEGER v59; // rdx
  ULONG v60; // ebx
  FILE_LOCK *v61; // rsi
  PEPROCESS RequestorProcess; // rax
  union _LARGE_INTEGER v63; // rax
  union _LARGE_INTEGER v64; // rcx
  __int16 v65; // cx
  __int64 v66; // r8
  union _LARGE_INTEGER v67; // r10
  union _LARGE_INTEGER v68; // r8
  union _LARGE_INTEGER v69; // rdx
  __int64 v70; // rbx
  __int16 v71; // ax
  char v72; // al
  int v73; // r9d
  char v74; // cl
  __int64 v75; // r8
  PVOID v76; // rax
  _DWORD *v77; // rax
  unsigned __int64 v78; // rcx
  LONGLONG v79; // r11
  union _LARGE_INTEGER v80; // r9
  unsigned __int64 v81; // rdx
  unsigned __int64 v82; // rcx
  __int64 v83; // rax
  _DWORD *v84; // rdx
  int v85; // edi
  LONGLONG v86; // rax
  char *v87; // rdx
  unsigned __int64 v88; // r11
  unsigned __int64 v89; // rdi
  unsigned __int64 v90; // rdx
  unsigned __int64 v91; // r11
  unsigned __int64 v92; // rdx
  __int64 v93; // rax
  unsigned __int64 v94; // r11
  unsigned __int64 v95; // rdx
  __int64 v96; // rcx
  __int64 v97; // rcx
  __int64 v98; // r11
  unsigned __int64 v99; // rax
  __int64 v100; // rdx
  unsigned int i; // ecx
  int v102; // edx
  PVOID v103; // rdi
  char v104; // [rsp+58h] [rbp-120h]
  union _LARGE_INTEGER StartingByte; // [rsp+60h] [rbp-118h] BYREF
  union _LARGE_INTEGER Length; // [rsp+68h] [rbp-110h] BYREF
  __int64 v107; // [rsp+70h] [rbp-108h] BYREF
  __int64 v108; // [rsp+78h] [rbp-100h]
  PVOID Entry; // [rsp+80h] [rbp-F8h] BYREF
  int v110[2]; // [rsp+88h] [rbp-F0h]
  PVOID Src; // [rsp+90h] [rbp-E8h]
  __int64 v112; // [rsp+98h] [rbp-E0h]
  int v113; // [rsp+A0h] [rbp-D8h]
  ULONG v114; // [rsp+A4h] [rbp-D4h]
  PVOID FileObject; // [rsp+A8h] [rbp-D0h]
  ULONG *MasterIrp; // [rsp+B0h] [rbp-C8h]
  __int64 v117; // [rsp+B8h] [rbp-C0h] BYREF
  unsigned __int64 v118; // [rsp+C0h] [rbp-B8h]
  __int64 v119; // [rsp+C8h] [rbp-B0h]
  unsigned __int64 v120; // [rsp+D0h] [rbp-A8h]
  union _LARGE_INTEGER v121; // [rsp+D8h] [rbp-A0h]
  unsigned __int64 v122; // [rsp+E0h] [rbp-98h]
  __int64 v123; // [rsp+E8h] [rbp-90h]
  union _LARGE_INTEGER v124; // [rsp+F0h] [rbp-88h] BYREF
  LONGLONG v125; // [rsp+F8h] [rbp-80h]
  union _LARGE_INTEGER v126; // [rsp+100h] [rbp-78h] BYREF
  __int64 v127; // [rsp+108h] [rbp-70h]
  __int64 v128; // [rsp+110h] [rbp-68h]
  union _LARGE_INTEGER v129; // [rsp+118h] [rbp-60h]
  _DWORD *v130; // [rsp+120h] [rbp-58h]
  int v131; // [rsp+128h] [rbp-50h]
  LARGE_INTEGER v132; // [rsp+130h] [rbp-48h]
  __int64 v133; // [rsp+138h] [rbp-40h]
  struct _IO_STACK_LOCATION *CurrentStackLocation; // [rsp+190h] [rbp+18h]
  union _LARGE_INTEGER v136; // [rsp+190h] [rbp+18h]
  bool v137; // [rsp+190h] [rbp+18h]
  __int16 v138; // [rsp+198h] [rbp+20h]
  __int16 v139; // [rsp+198h] [rbp+20h]

  v4 = Irp;
  v5 = Context;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  p_Type = &CurrentStackLocation->FileObject->Type;
  FileObject = p_Type;
  Entry = 0;
  v7 = p_Type[3];
  *(_QWORD *)v110 = v7;
  if ( v7 )
  {
    v8 = p_Type[4];
    if ( !v8 )
    {
LABEL_6:
      v11 = -1073741811;
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(Context, 3221225485LL, 1209034);
      LOBYTE(a4) = v4 != 0;
      NtfsExtendedCompleteRequestInternal(v5, v4, 3221225485LL, a4, 0);
      if ( !NtfsStatusDebugFlags )
        return v11;
      v12 = 1209035;
LABEL_311:
      NtfsStatusTraceAndDebugInternal(0, v11, v12);
      return v11;
    }
    v9 = *(_QWORD *)(v7 + 192);
    v112 = *(_QWORD *)(v7 + 184);
    v10 = *(unsigned __int8 *)(v8 + 88);
  }
  else
  {
    v9 = 0;
    v8 = 0;
    v112 = 0;
    v10 = 1;
  }
  v128 = v9;
  if ( v10 != 2 )
    goto LABEL_6;
  PerformanceCounter = KeQueryPerformanceCounter(0);
  ++*(_QWORD *)(v9 + 9712);
  v15 = *(_DWORD *)(v9 + 4);
  if ( (v15 & 0xA000021) != 1 )
  {
    if ( (v15 & 0x20) != 0 )
    {
      ++*(_QWORD *)(v9 + 9728);
      v11 = -1073741431;
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(v5, 3221225865LL, 1209061);
      LOBYTE(v14.LowPart) = v4 != 0;
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD))NtfsExtendedCompleteRequestInternal)(
        v5,
        v4,
        3221225865LL,
        (LARGE_INTEGER)v14.QuadPart,
        0);
      if ( !NtfsStatusDebugFlags )
        return v11;
      v12 = 1209062;
      goto LABEL_311;
    }
    if ( (v15 & 0x8000001) != 1 )
    {
      ++*(_QWORD *)(v9 + 9728);
      v11 = -1073741202;
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(v5, 3221226094LL, 1209075);
      LOBYTE(v14.LowPart) = v4 != 0;
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD))NtfsExtendedCompleteRequestInternal)(
        v5,
        v4,
        3221226094LL,
        (LARGE_INTEGER)v14.QuadPart,
        0);
      if ( !NtfsStatusDebugFlags )
        return v11;
      v12 = 1209076;
      goto LABEL_311;
    }
    if ( (v15 & 0x2000000) != 0 )
    {
      ++*(_QWORD *)(v9 + 9728);
      v16 = -1073741662;
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(v5, 3221225634LL, 1209087);
      LOBYTE(v14.LowPart) = v4 != 0;
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD))NtfsExtendedCompleteRequestInternal)(
        v5,
        v4,
        3221225634LL,
        (LARGE_INTEGER)v14.QuadPart,
        0);
      if ( !NtfsStatusDebugFlags )
        return v16;
      v17 = 1209088;
      goto LABEL_22;
    }
  }
  v133 = v7;
  if ( (*(_DWORD *)(v7 + 512) & 0x1000000) != 0 )
  {
    ++*(_QWORD *)(v9 + 9728);
    v16 = -1073741816;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(v5, 3221225480LL, 1209096);
    LOBYTE(v14.LowPart) = v4 != 0;
    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD))NtfsExtendedCompleteRequestInternal)(
      v5,
      v4,
      3221225480LL,
      (LARGE_INTEGER)v14.QuadPart,
      0);
    if ( !NtfsStatusDebugFlags )
      return v16;
    v17 = 1209097;
    goto LABEL_22;
  }
  if ( v8 && (*(_DWORD *)(v8 + 4) & 0x2000) != 0 )
  {
    ++*(_QWORD *)(v9 + 9728);
    v11 = -1073741811;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(v5, 3221225485LL, 1209110);
    LOBYTE(v14.LowPart) = v4 != 0;
    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD))NtfsExtendedCompleteRequestInternal)(
      v5,
      v4,
      3221225485LL,
      (LARGE_INTEGER)v14.QuadPart,
      0);
    if ( !NtfsStatusDebugFlags )
      return v11;
    v12 = 1209111;
    goto LABEL_311;
  }
  if ( (*(_WORD *)(v7 + 460) & 0x40FF) != 0 )
  {
    ++*(_QWORD *)(v9 + 9728);
    v11 = -1073741811;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(v5, 3221225485LL, 1209122);
    LOBYTE(v14.LowPart) = v4 != 0;
    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD))NtfsExtendedCompleteRequestInternal)(
      v5,
      v4,
      3221225485LL,
      (LARGE_INTEGER)v14.QuadPart,
      0);
    if ( !NtfsStatusDebugFlags )
      return v11;
    v12 = 1209123;
    goto LABEL_311;
  }
  Options = CurrentStackLocation->Parameters.Create.Options;
  if ( Options < 0x18 )
  {
    ++*(_QWORD *)(v9 + 9728);
    v11 = -1073741811;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(v5, 3221225485LL, 1209134);
    LOBYTE(v14.LowPart) = v4 != 0;
    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD))NtfsExtendedCompleteRequestInternal)(
      v5,
      v4,
      3221225485LL,
      (LARGE_INTEGER)v14.QuadPart,
      0);
    if ( !NtfsStatusDebugFlags )
      return v11;
    v12 = 1209135;
    goto LABEL_311;
  }
  MasterIrp = (ULONG *)v4->AssociatedIrp.MasterIrp;
  v20 = MasterIrp[1];
  v21 = 0;
  if ( !v20
    || (v22 = 16LL * (v20 - 1), v22 > 0xFFFFFFFF)
    || (int)v22 + 24 < (unsigned int)v22
    || Options < (int)v22 + 24 )
  {
LABEL_307:
    ++*(_QWORD *)(v9 + 9728);
    v11 = -1073741811;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(v5, 3221225485LL, 1209156);
    LOBYTE(v14.LowPart) = v4 != 0;
    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD))NtfsExtendedCompleteRequestInternal)(
      v5,
      v4,
      3221225485LL,
      (LARGE_INTEGER)v14.QuadPart,
      v21);
    if ( !NtfsStatusDebugFlags )
      return v11;
    v12 = 1209157;
    goto LABEL_311;
  }
  if ( CurrentStackLocation->Parameters.Read.Length - 1 <= 2 )
  {
    ++*(_QWORD *)(v9 + 9728);
    v11 = -1073741811;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(v5, 3221225485LL, 1209170);
    LOBYTE(v14.LowPart) = v4 != 0;
    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD))NtfsExtendedCompleteRequestInternal)(
      v5,
      v4,
      3221225485LL,
      (LARGE_INTEGER)v14.QuadPart,
      0);
    if ( !NtfsStatusDebugFlags )
      return v11;
    v12 = 1209171;
    goto LABEL_311;
  }
  if ( *(_BYTE *)(v9 + 5521) )
  {
    ++*(_QWORD *)(v9 + 9728);
    if ( (*(_DWORD *)(v9 + 24) & 0x40000) != 0 )
    {
      LOBYTE(v14.LowPart) = v4 != 0;
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD))NtfsExtendedCompleteRequestInternal)(
        v5,
        v4,
        0,
        (LARGE_INTEGER)v14.QuadPart,
        1);
      return 0;
    }
    v16 = -1073741637;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(v5, 3221225659LL, 1209196);
    LOBYTE(v14.LowPart) = v4 != 0;
    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD))NtfsExtendedCompleteRequestInternal)(
      v5,
      v4,
      3221225659LL,
      (LARGE_INTEGER)v14.QuadPart,
      0);
    if ( !NtfsStatusDebugFlags )
      return v16;
    v17 = 1209197;
LABEL_22:
    NtfsStatusTraceAndDebugInternal(0, v16, v17);
    return v16;
  }
  v23 = ExAllocateFromLookasideListEx(&NtfsFileLevelTrimContextLookasideList);
  v25 = v23;
  v108 = (__int64)v23;
  if ( !v23 )
  {
    ++*(_QWORD *)(v9 + 9728);
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(v5, 3221225626LL, 1209211);
    LOBYTE(v24) = v4 != 0;
    NtfsExtendedCompleteRequestInternal(v5, v4, 3221225626LL, v24, 0);
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(0, 3221225626LL, 1209212);
    return 3221225626LL;
  }
  v118 = 0;
  v122 = 0;
  v127 = 0;
  v119 = 0;
  Src = 0;
  v26 = 0;
  v113 = 0;
  v132 = PerformanceCounter;
  *(_WORD *)v23 = 1862;
  v23[1] = v9;
  v23[2] = v4;
  v23[6] = 1;
  *((_DWORD *)v23 + 14) = 0;
  v23[3] = 0;
  v23[4] = 0;
  if ( CurrentStackLocation->Parameters.Read.Length )
    v27 = v4->AssociatedIrp.MasterIrp;
  else
    v27 = 0;
  v25[5] = v27;
  *(_QWORD *)(v9 + 9736) += MasterIrp[1];
  v130 = 0;
  LODWORD(v107) = 0;
  v117 = 0;
  if ( **((_QWORD **)FileObject + 5) )
    goto LABEL_96;
  if ( (*(_DWORD *)(*(_QWORD *)v110 + 200LL) & 0x10) != 0 )
  {
    v28 = *(_QWORD *)(*(_QWORD *)v110 + 184LL);
    v29 = *(_QWORD *)(v28 + 328);
    if ( (!v29 || !*(_QWORD *)(v29 + 24)) && (*(_DWORD *)(v28 + 4) & 0x20020100) == 0x20000000 )
      goto LABEL_96;
  }
  LOBYTE(v26) = v5[12] & 1;
  v30 = NtfsAcquirePagingShared(v5, v112, v26, 0);
  v33 = 0;
  if ( !v30 )
    NtfsRaiseStatusInternal((_DWORD)v5, -1073741608, 0, 0, 1209296);
  if ( **((_QWORD **)FileObject + 5) != v33 )
    goto LABEL_94;
  v31 = *(_QWORD *)v110;
  v34 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)v110 + 184LL) + 4LL);
  if ( (*(_DWORD *)(*(_QWORD *)v110 + 200LL) & 0x10) == 0 )
    goto LABEL_90;
  v32 = *(_QWORD *)(*(_QWORD *)v110 + 184LL);
  v35 = *(_QWORD *)(v32 + 328);
  if ( v35 )
  {
    if ( *(_QWORD *)(v35 + 24) != v33 )
      goto LABEL_90;
  }
  if ( (v34 & 0x20100) != 0 )
    goto LABEL_90;
  if ( (v34 & 0x20000000) != 0 )
  {
LABEL_94:
    NtfsReleasePagingResourcePriv(v31, v112, v32, v33);
    LOBYTE(v37) = v5[12] & 1;
    if ( (unsigned __int8)NtfsAcquirePagingResourceExclusive(v5, v112, v37) )
    {
LABEL_98:
      v31 = *(_QWORD *)v110;
      goto LABEL_99;
    }
    NtfsRaiseStatusInternal((_DWORD)v5, -1073741608, 0, 0, 1209306);
LABEL_96:
    LOBYTE(v26) = v5[12] & 1;
    if ( !(unsigned __int8)NtfsAcquirePagingResourceExclusive(v5, v112, v26) )
      NtfsRaiseStatusInternal((_DWORD)v5, -1073741608, 0, 0, 1209289);
    goto LABEL_98;
  }
  if ( (v34 & 0x10000000) == 0 )
  {
    PurgeKernelEAState = NtfsGetPurgeKernelEAState(*(_QWORD *)(*(_QWORD *)v110 + 184LL));
    v33 = 0;
    if ( !PurgeKernelEAState )
    {
      v31 = *(_QWORD *)v110;
      goto LABEL_90;
    }
    goto LABEL_94;
  }
LABEL_90:
  if ( *(_DWORD *)(v31 + 448) != (_DWORD)v33 || (LOBYTE(v21) = v33, (*(_WORD *)(v31 + 460) & 0x80FF) != 0) )
    LOBYTE(v21) = 2;
LABEL_99:
  v25[3] = *(_QWORD *)(v112 + 112);
  v25[4] = KeGetCurrentThread();
  v38 = *(_WORD *)(v31 + 460);
  v39 = (unsigned __int16)v38 >> 15;
  LOBYTE(v21) = v21 & 0xFB;
  LOBYTE(v39) = v21 | (4 * (v38 < 0));
  v138 = v39;
  if ( ((v21 & 2) != 0 || (v39 & 4) != 0) && (*((_DWORD *)v5 + 3) & 1) == 0 )
  {
    NtfsRaiseStatusInternal((_DWORD)v5, -1073741608, 0, 0, 1209340);
    goto LABEL_307;
  }
  v40 = *(_DWORD *)(v31 + 512);
  if ( (v40 & 0x4000000) != 0 )
  {
    v41 = -1073741431;
    if ( !NtfsStatusDebugFlags )
    {
LABEL_106:
      v43 = v108;
      *(_DWORD *)(v108 + 56) = v41;
      goto LABEL_267;
    }
    v42 = 1209350;
LABEL_105:
    NtfsStatusTraceAndDebugInternal(0, (unsigned int)v41, v42);
    goto LABEL_106;
  }
  if ( (v40 & 0x40) != 0 )
  {
    v41 = -1073741533;
    if ( !NtfsStatusDebugFlags )
      goto LABEL_106;
    v42 = 1209361;
    goto LABEL_105;
  }
  if ( (v40 & 0x10000) != 0 )
    v41 = -1073741202;
  else
    v41 = (v40 & 0x1000000) != 0 ? 0xC0000008 : 0;
  if ( v41 < 0 )
  {
    if ( !NtfsStatusDebugFlags )
      goto LABEL_106;
    v42 = 1209372;
    goto LABEL_105;
  }
  if ( (v38 & 0x40FF) != 0 )
  {
    v41 = -1073741811;
    if ( !NtfsStatusDebugFlags )
      goto LABEL_106;
    v42 = 1209386;
    goto LABEL_105;
  }
  v44 = FsRtlCheckOplockEx((POPLOCK)(v31 + 88), v4, 0, v5, NtfsOplockComplete, NtfsPrePostIrp);
  v41 = v44;
  if ( v44 < 0 )
  {
    if ( !NtfsStatusDebugFlags
      || (unsigned int)v44 >= 0xFFFFFFED
      || v44 == -1073741802
      || v44 == -1073741807
      || (unsigned int)(v44 + 2147483643) <= 1
      || v44 == -1073741608 )
    {
      goto LABEL_106;
    }
    v42 = 1209409;
    goto LABEL_105;
  }
  if ( v44 == 259 )
  {
    v43 = v108;
    *(_QWORD *)(v108 + 16) = 0;
    v5 = 0;
    goto LABEL_267;
  }
  if ( (*(_DWORD *)(*(_QWORD *)v110 + 200LL) & 8) != 0 )
  {
    v41 = 0;
    v43 = v108;
    goto LABEL_267;
  }
  if ( (v138 & 2) != 0 )
  {
    v45 = ExAllocateFromLookasideListEx(&NtfsDeviceManageDataSetAttributesLookasideList);
    Src = v45;
    if ( !v45 )
    {
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(0, 3221225626LL, 1209458);
      v41 = -1073741670;
      goto LABEL_106;
    }
    *v45 = 1863;
    v43 = v108;
    *((_QWORD *)v45 + 1) = v108;
    *((_DWORD *)v45 + 4) = 0;
  }
  else
  {
    v43 = v108;
  }
  v46 = *(_QWORD *)v110;
  NtfsPostUsnChangeWithOverrideOption((_DWORD)v5, v110[0], 1, 0, 0, 0, 0);
  NtfsCheckpointCurrentTransaction(v5);
  *(_QWORD *)(v43 + 32) |= 3uLL;
  HIBYTE(v47) = HIBYTE(v138);
  LOBYTE(v47) = v138 | 1;
  v138 = v47;
  v48 = 0;
  v49 = MasterIrp;
  while ( 1 )
  {
    v114 = v48;
    if ( v48 >= v49[1] )
      goto LABEL_256;
    v50 = 2LL * v48;
    v51 = *(union _LARGE_INTEGER *)&v49[4 * v48 + 2];
    StartingByte = v51;
    v52 = *(union _LARGE_INTEGER *)&v49[2 * v50 + 4];
    Length = v52;
    v53 = 0;
    v123 = 0;
    if ( v52.QuadPart < 0x1000000000000000uLL )
    {
      v118 += v52.QuadPart;
    }
    else
    {
      v122 += v52.QuadPart;
      v127 = v122;
      if ( v122 < v52.QuadPart )
      {
        v122 = -1;
        v127 = -1;
      }
    }
    v54 = v51.LowPart & 0xFFF;
    if ( (v51.LowPart & 0xFFF) != 0 )
    {
      v53 = v51.LowPart & 0xFFF;
      v123 = v53;
      QuadPart = 4096 - v54 + v51.QuadPart;
      if ( QuadPart < v51.QuadPart )
      {
        StartingByte.QuadPart = -1;
        v41 = -1073741675;
        QuadPart = -1;
      }
      else
      {
        StartingByte.QuadPart = 4096 - v54 + v51.QuadPart;
        v41 = 0;
      }
      if ( v41 < 0 )
      {
        if ( *(int *)(v43 + 56) < 0 )
          goto LABEL_266;
        if ( NtfsStatusDebugFlags )
        {
          v56 = 1209566;
          goto LABEL_152;
        }
        goto LABEL_153;
      }
      if ( v52.QuadPart < (unsigned __int64)(4096 - v54) )
      {
        Length.QuadPart = 0;
        v52.QuadPart = 0;
      }
      else
      {
        v52.QuadPart = v54 + v52.QuadPart - 4096;
        Length = v52;
        v53 = 4096;
        v123 = 4096;
      }
    }
    else
    {
      QuadPart = v51.QuadPart;
    }
    v57 = *(_QWORD *)(v46 + 24);
    if ( QuadPart >= v57 )
    {
LABEL_254:
      v49 = MasterIrp;
      goto LABEL_255;
    }
    v58 = -1;
    if ( v52.QuadPart + QuadPart >= QuadPart )
      v58 = v52.QuadPart + QuadPart;
    v41 = v52.QuadPart + QuadPart < QuadPart ? 0xC0000095 : 0;
    if ( v52.QuadPart + QuadPart < QuadPart )
    {
      if ( *(int *)(v43 + 56) < 0 )
        goto LABEL_266;
      if ( NtfsStatusDebugFlags )
      {
        v56 = 1209607;
LABEL_152:
        NtfsStatusTraceAndDebugInternal(0, (unsigned int)v41, v56);
      }
LABEL_153:
      *(_DWORD *)(v43 + 56) = v41;
      goto LABEL_266;
    }
    if ( v58 <= v57 )
    {
      v59 = v52;
    }
    else
    {
      v59.QuadPart = v57 - QuadPart;
      Length = v59;
    }
    v49 = MasterIrp;
    if ( *(_QWORD *)&MasterIrp[2 * v50 + 4] != -1 )
    {
      v53 += v59.LowPart & 0xFFF;
      v123 = v53;
    }
    Length.QuadPart = v59.QuadPart & 0xFFFFFFFFFFFFF000uLL;
    if ( (v59.QuadPart & 0xFFFFFFFFFFFFF000uLL) != 0 )
      break;
LABEL_255:
    v48 = v114 + 1;
  }
  if ( v53 )
  {
    ++*(_QWORD *)(v9 + 9760);
    *(_QWORD *)(v9 + 9768) += v53;
  }
  if ( *(_QWORD *)(v46 + 584) )
  {
    v60 = *v49;
    v61 = *(FILE_LOCK **)(v46 + 584);
    RequestorProcess = IoGetRequestorProcess(Irp);
    if ( !FsRtlFastCheckLockForWrite(v61, &StartingByte, &Length, v60, FileObject, RequestorProcess) )
    {
      v41 = -1073741740;
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(0, 3221225556LL, 1209671);
      v43 = v108;
      LODWORD(v46) = v110[0];
      if ( *(int *)(v108 + 56) >= 0 )
        *(_DWORD *)(v108 + 56) = -1073741740;
LABEL_256:
      if ( !(_DWORD)v107 )
        goto LABEL_266;
      v41 = NtfsSendTrimRequestToStorage((int)v5, v9, v46, (int)&Entry, (__int64)&v117, (__int64)&v107, v43, Src, 0);
      if ( v41 >= 0
        || !NtfsStatusDebugFlags
        || (unsigned int)v41 >= 0xFFFFFFED
        || v41 == -1073741802
        || v41 == -1073741807
        || (unsigned int)(v41 + 2147483643) <= 1
        || v41 == -1073741608 )
      {
        goto LABEL_266;
      }
      v66 = 1210166;
LABEL_265:
      NtfsStatusTraceAndDebugInternal(0, (unsigned int)v41, v66);
      goto LABEL_266;
    }
    v43 = v108;
    v46 = *(_QWORD *)v110;
  }
  NtfsPostUsnChangeWithOverrideOption((_DWORD)v5, v46, 1, 0, StartingByte.QuadPart, Length.QuadPart, 0);
  if ( **((_QWORD **)FileObject + 5) )
  {
    v124 = StartingByte;
    v63 = Length;
    v64 = Length;
    v136 = Length;
    while ( 1 )
    {
      if ( !v64.QuadPart )
        goto LABEL_191;
      if ( v64.QuadPart > 0xFFFFF000uLL )
        v63.QuadPart = 4294963200LL;
      v120 = v63.QuadPart;
      if ( !(unsigned __int8)NtfsPurgeCacheSection(v5, v46, &v124, v63.LowPart, 2) )
        break;
      v124.QuadPart += (unsigned int)v120;
      v64.QuadPart = v136.QuadPart - (unsigned int)v120;
      v136 = v64;
      v63.QuadPart = v64.LowPart;
    }
    v41 = -1073740747;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(0, 3221226549LL, 1209730);
    if ( *(int *)(v43 + 56) < 0 )
      goto LABEL_266;
    goto LABEL_153;
  }
LABEL_191:
  NtfsPreloadAllocationInternal(
    (_DWORD)v5,
    (StartingByte.QuadPart + Length.QuadPart + *(unsigned int *)(v9 + 480)) >> *(_BYTE *)(v9 + 488),
    0);
  LOBYTE(v65) = v138;
  if ( (v138 & 2) != 0 )
  {
    if ( Entry )
    {
      if ( (unsigned int)(1024 - *((_DWORD *)Entry + 5)) < 16
                                                         * ((unsigned int)(v107 + 1)
                                                          + 2
                                                          * (unsigned __int64)(unsigned int)(*((_DWORD *)Src + 4) + 1))
                                                         + 40 )
      {
        v41 = NtfsSendTrimRequestToStorage((int)v5, v9, v46, (int)&Entry, (__int64)&v117, (__int64)&v107, v43, Src, 0);
        if ( v41 < 0 )
        {
          if ( !NtfsStatusDebugFlags
            || (unsigned int)v41 >= 0xFFFFFFED
            || v41 == -1073741802
            || v41 == -1073741807
            || (unsigned int)(v41 + 2147483643) <= 1
            || v41 == -1073741608 )
          {
            goto LABEL_266;
          }
          v66 = 1209805;
          goto LABEL_265;
        }
      }
    }
    NtfsAcquireRange(
      (_DWORD)v5,
      v46,
      StartingByte.LowPart,
      Length.LowPart,
      v113 | 0x14,
      (__int64)Src + 32 * *((unsigned int *)Src + 4) + 24);
    v113 = 32;
    v131 = 32;
    ++*((_DWORD *)Src + 4);
    LOBYTE(v65) = v138;
  }
  v67.QuadPart = 0;
  v104 = 0;
  v68 = Length;
  while ( 1 )
  {
LABEL_204:
    if ( !v68.QuadPart )
    {
      if ( v104 )
      {
        ++*(_DWORD *)(v43 + 52);
      }
      else if ( (v65 & 2) != 0 )
      {
        v87 = (char *)Src;
        --*((_DWORD *)Src + 4);
        NtfsReleaseRangeInternal(&v87[32 * *((unsigned int *)v87 + 4) + 24]);
      }
      goto LABEL_254;
    }
    v129 = v67;
    v126 = v67;
    v137 = (v65 & 4) != 0;
    if ( (v65 & 4) == 0 )
      break;
    v69.QuadPart = *(unsigned int *)(v46 + 452);
    if ( ((v69.LowPart - 1) & StartingByte.LowPart) != 0 || v68.QuadPart < (unsigned __int64)v69.QuadPart )
      break;
    v70 = v68.LowPart & -v69.LowPart;
    NtfsAcquireExclusiveScbEx(v5, v46, 0);
    HIBYTE(v71) = HIBYTE(v138);
    LOBYTE(v71) = v138 | 8;
    v139 = v71;
    NtfsDeleteAllocation((_DWORD)v5, (v70 + StartingByte.QuadPart - 1) >> *(_BYTE *)(v9 + 488), 1, 1);
    NtfsCheckpointCurrentTransaction(v5);
    NtfsReleaseFcbEx(v5, *(_QWORD *)(v46 + 184), 0);
    HIBYTE(v65) = HIBYTE(v139);
    LOBYTE(v65) = v139 & 0xF7;
    v138 = v65;
    StartingByte.QuadPart += v70;
    v68.QuadPart = Length.QuadPart - v70;
    Length.QuadPart -= v70;
    v43 = v108;
    v67.QuadPart = 0;
  }
  v72 = NtfsLookupAllocation((_DWORD)v5, (__int64)&v126);
  v74 = *(_BYTE *)(v9 + 488);
  v67.QuadPart = 0;
  if ( !v72 )
  {
    if ( *(__int16 *)(v46 + 460) >= 0 )
    {
      v85 = v112;
      v43 = v112 + 8;
      v46 = 0x10E001276E3LL;
      NtfsAttachCorruption_BadOrOrphanFRS((_DWORD)v5, 2, 1210083, v73, v112 + 8, v112, 0);
      NtfsAttachRepairInfoPriv(v5, 256, 0, 0x10E001276E3LL);
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(v5, 3221225730LL, 1210083);
      NtfsRaiseStatusInternal((_DWORD)v5, -1073741566, v43, v85, 1210083);
    }
    v86 = v126.QuadPart << v74;
    if ( v126.QuadPart << v74 >= (unsigned __int64)Length.QuadPart )
    {
      StartingByte.QuadPart += Length.QuadPart;
      v68 = v67;
      Length = v67;
    }
    else
    {
      v68.QuadPart = Length.QuadPart - v86;
      Length.QuadPart -= v86;
      StartingByte.QuadPart += v86;
    }
    goto LABEL_249;
  }
  v125 = v129.QuadPart << v74;
  v121.QuadPart = v126.QuadPart << v74;
  v120 = StartingByte.QuadPart % (unsigned __int64)*(unsigned int *)(v9 + 356);
  if ( !Entry )
    goto LABEL_224;
  if ( (v138 & 2) != 0 )
    v75 = 32LL * *((unsigned int *)Src + 4) + 40;
  else
    v75 = 16;
  if ( (unsigned int)(1024 - *((_DWORD *)Entry + 5)) >= v75 + 16 * (unsigned __int64)(unsigned int)(v107 + 1)
    || (v41 = NtfsSendTrimRequestToStorage((int)v5, v9, v46, (int)&Entry, (__int64)&v117, (__int64)&v107, v43, Src, 1),
        v67.QuadPart = 0,
        v41 >= 0) )
  {
    if ( Entry )
    {
LABEL_231:
      v78 = v120;
      v79 = v125;
      v80 = v121;
      if ( v120 )
      {
        v79 = v120 + v125;
        v125 += v120;
        v80.QuadPart = v121.QuadPart - v120;
        v121.QuadPart -= v120;
      }
      if ( v137 )
      {
        v81 = (unsigned int)-*(_DWORD *)(v46 + 452);
        v82 = v81 & (StartingByte.QuadPart + (unsigned int)(*(_DWORD *)(v46 + 452) - 1));
        if ( v82 < (v81 & (Length.QuadPart + StartingByte.QuadPart)) )
        {
          v80.QuadPart = v82 - StartingByte.QuadPart;
          v121.QuadPart = v82 - StartingByte.QuadPart;
        }
        v67.QuadPart = 0;
        v78 = v120;
      }
      if ( v80.QuadPart >= (unsigned __int64)Length.QuadPart )
      {
        v80 = Length;
        v68.QuadPart = 0;
        Length.QuadPart = 0;
      }
      else
      {
        v68.QuadPart = Length.QuadPart - v80.QuadPart;
        Length.QuadPart -= v80.QuadPart;
      }
      StartingByte.QuadPart += v80.QuadPart;
      if ( v80.QuadPart )
      {
        v83 = 2LL * (unsigned int)v107;
        v84 = v130;
        *(_QWORD *)&v130[2 * v83] = v79;
        *(union _LARGE_INTEGER *)&v84[2 * v83 + 2] = v80;
        v117 += v80.QuadPart;
        v119 += v80.QuadPart;
        LODWORD(v107) = v107 + 1;
        v104 = 1;
        ++*(_QWORD *)(v9 + 9776);
        *(_QWORD *)(v9 + 9784) += v78;
        v68 = Length;
      }
LABEL_249:
      LOBYTE(v65) = v138;
      goto LABEL_204;
    }
LABEL_224:
    v76 = ExAllocateFromLookasideListEx(&NtfsDeviceManageDataSetAttributesLookasideList);
    Entry = v76;
    if ( !v76 )
    {
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(0, 3221225626LL, 1209959);
      v41 = -1073741670;
      goto LABEL_153;
    }
    memset(v76, 0, 0x400u);
    v77 = Entry;
    *(_DWORD *)Entry = 28;
    v77[1] = 1;
    if ( (*(_DWORD *)(v112 + 4) & 4) != 0 )
      v77[2] |= 0x40000000u;
    v77[5] = 32;
    v130 = v77 + 8;
    v67.QuadPart = 0;
    goto LABEL_231;
  }
  if ( NtfsStatusDebugFlags
    && (unsigned int)v41 < 0xFFFFFFED
    && v41 != -1073741802
    && v41 != -1073741807
    && (unsigned int)(v41 + 2147483643) > 1
    && v41 != -1073741608 )
  {
    v66 = 1209939;
    goto LABEL_265;
  }
LABEL_266:
  v4 = Irp;
LABEL_267:
  KeQueryPerformanceCounter(0);
  v88 = v118;
  *(_QWORD *)(v9 + 9744) += v118;
  v89 = v122;
  *(_QWORD *)(v9 + 9752) += v122;
  *(_QWORD *)(v9 + 9792) += v119;
  v90 = v89;
  if ( !v89 )
    v90 = v88;
  NtfsTelemetryBucketizeFileLevelTrimSize(1, v90, v9 + 9800);
  v92 = v89;
  if ( !v89 )
    v92 = v91;
  v93 = NtfsTelemetryBucketizeFileLevelTrimSize(v91, v92, v9 + 9896);
  v95 = v89;
  if ( !v89 )
    v95 = v94;
  NtfsTelemetryBucketizeFileLevelTrimSize(v93, v95, v9 + 10088);
  NtfsTelemetryBucketizeFileLevelTrimSize(v96, v119, v9 + 9992);
  if ( !v89 )
    v89 = v118;
  v99 = NtfsTelemetryBucketizeFileLevelTrimSize(v97, v89, v98);
  v100 = 0;
  do
  {
    if ( v99 < FileLevelTrimLatencyBuckets[v100] )
      break;
    v100 = (unsigned int)(v100 + 1);
  }
  while ( (unsigned int)v100 < 0xE );
  if ( (unsigned int)v100 < 0xF )
    ++*(_QWORD *)(v9 + 8 * v100 + 10184);
  if ( (v138 & 8) != 0 )
    NtfsReleaseFcbEx(v5, *(_QWORD *)(*(_QWORD *)v110 + 184LL), 0);
  if ( Entry )
    ExFreeToLookasideListEx(&NtfsDeviceManageDataSetAttributesLookasideList, Entry);
  if ( v41 < 0 )
  {
    if ( v41 == -1073741608 || v41 == -1073741432 )
    {
      ++*(_QWORD *)(v9 + 9720);
    }
    else
    {
      ++*(_QWORD *)(v9 + 9728);
      for ( i = 0; i < 0xC; ++i )
      {
        v102 = *(_DWORD *)(v9 + 4LL * i + 10304);
        if ( v41 == v102 )
          goto LABEL_293;
        if ( !v102 )
        {
          *(_DWORD *)(v9 + 4LL * i + 10304) = v41;
LABEL_293:
          ++*(_QWORD *)(v9 + 8LL * i + 10352);
          break;
        }
      }
    }
  }
  if ( *(_QWORD *)(v43 + 16) )
    v4->Tail.Overlay.CurrentStackLocation->Control |= 1u;
  if ( (v138 & 1) != 0 )
    ExSetResourceOwnerPointerEx(*(PERESOURCE *)(v43 + 24), *(PVOID *)(v43 + 32), 1u);
  v103 = Src;
  if ( Src )
    v43 = (__int64)Src;
  NtfsAsyncFileLevelTrimCompletionRoutine(0, 0, v43);
  if ( v103 )
    ExFreeToLookasideListEx(&NtfsDeviceManageDataSetAttributesLookasideList, v103);
  if ( v5 )
    NtfsExtendedCompleteRequestInternal(v5, 0, 259, 0, 1);
  return 259;
}

```

## disassembly

```asm
0x14023370c  mov     [rsp+Irp], rdx
0x140233711  mov     [rsp+arg_0], rcx
0x140233716  push    rbx
0x140233717  push    rsi
0x140233718  push    rdi
0x140233719  push    r12
0x14023371b  push    r13
0x14023371d  push    r14
0x14023371f  push    r15
0x140233721  sub     rsp, 140h
0x140233728  mov     rsi, rdx
0x14023372b  mov     r13, rcx
0x14023372e  mov     rax, [rdx+0B8h]
0x140233735  mov     [rsp+178h+arg_10], rax
0x14023373d  mov     rax, [rax+30h]
0x140233741  mov     [rsp+178h+FileObject], rax
0x140233749  xor     edi, edi
0x14023374b  mov     [rsp+178h+Entry], rdi
0x140233753  mov     r14, [rax+18h]
0x140233757  mov     qword ptr [rsp+178h+var_F0], r14
0x14023375f  test    r14, r14
0x140233762  jz      short loc_14023378D
0x140233764  mov     rbx, [rax+20h]
0x140233768  test    rbx, rbx
0x14023376b  jz      short loc_1402337B1
0x14023376d  mov     r15, [r14+0C0h]
0x140233774  mov     rcx, [r14+0B8h]
0x14023377b  mov     [rsp+178h+var_E0], rcx
0x140233783  movzx   eax, byte ptr [rbx+58h]
0x140233787  lea     r12d, [rdi+1]
0x14023378b  jmp     short loc_1402337A4
0x14023378d  mov     r15, rdi
0x140233790  mov     rbx, rdi
0x140233793  mov     [rsp+178h+var_E0], rdi
0x14023379b  mov     r12d, 1
0x1402337a1  mov     eax, r12d
0x1402337a4  mov     [rsp+178h+var_68], r15
0x1402337ac  cmp     eax, 2
0x1402337af  jz      short loc_140233804
0x1402337b1  mov     al, cs:NtfsStatusDebugFlags
0x1402337b7  mov     r14d, 0C000000Dh
0x1402337bd  test    al, al
0x1402337bf  jz      short loc_1402337D2
0x1402337c1  mov     r8d, 1272CAh
0x1402337c7  mov     edx, r14d
0x1402337ca  mov     rcx, r13
0x1402337cd  call    NtfsStatusTraceAndDebugInternal
0x1402337d2  test    rsi, rsi
0x1402337d5  setnz   r9b
0x1402337d9  mov     dword ptr [rsp+178h+CompletionRoutine], edi
0x1402337dd  mov     r8d, r14d
0x1402337e0  mov     rdx, rsi
0x1402337e3  mov     rcx, r13
0x1402337e6  call    NtfsExtendedCompleteRequestInternal
0x1402337eb  mov     al, cs:NtfsStatusDebugFlags
0x1402337f1  test    al, al
0x1402337f3  jz      loc_140234FD7
0x1402337f9  mov     r8d, 1272CBh
0x1402337ff  jmp     loc_140234FCD
0x140233804  xor     ecx, ecx; PerformanceFrequency
0x140233806  call    cs:__imp_KeQueryPerformanceCounter
0x14023380d  nop     dword ptr [rax+rax+00h]
0x140233812  mov     rdi, rax
0x140233815  add     [r15+25F0h], r12
0x14023381c  mov     ecx, [r15+4]
0x140233820  mov     eax, ecx
0x140233822  and     eax, 0A000021h
0x140233827  cmp     eax, r12d
0x14023382a  jz      loc_140233964
0x140233830  test    cl, 20h
0x140233833  jz      short loc_140233891
0x140233835  add     [r15+2600h], r12
0x14023383c  mov     al, cs:NtfsStatusDebugFlags
0x140233842  xor     ebx, ebx
0x140233844  mov     r14d, 0C0000189h
0x14023384a  test    al, al
0x14023384c  jz      short loc_14023385F
0x14023384e  mov     r8d, 1272E5h
0x140233854  mov     edx, r14d
0x140233857  mov     rcx, r13
0x14023385a  call    NtfsStatusTraceAndDebugInternal
0x14023385f  test    rsi, rsi
0x140233862  setnz   r9b
0x140233866  mov     dword ptr [rsp+178h+CompletionRoutine], ebx
0x14023386a  mov     r8d, r14d
0x14023386d  mov     rdx, rsi
0x140233870  mov     rcx, r13
0x140233873  call    NtfsExtendedCompleteRequestInternal
0x140233878  mov     al, cs:NtfsStatusDebugFlags
0x14023387e  test    al, al
0x140233880  jz      loc_140234FD7
0x140233886  mov     r8d, 1272E6h
0x14023388c  jmp     loc_140234FCD
0x140233891  mov     eax, ecx
0x140233893  and     eax, 8000001h
0x140233898  cmp     eax, r12d
0x14023389b  jnz     short loc_140233908
0x14023389d  bt      ecx, 19h
0x1402338a1  jnb     loc_140233964
0x1402338a7  add     [r15+2600h], r12
0x1402338ae  mov     al, cs:NtfsStatusDebugFlags
0x1402338b4  xor     edi, edi
0x1402338b6  mov     ebx, 0C00000A2h
0x1402338bb  test    al, al
0x1402338bd  jz      short loc_1402338CF
0x1402338bf  mov     r8d, 1272FFh
0x1402338c5  mov     edx, ebx
0x1402338c7  mov     rcx, r13
0x1402338ca  call    NtfsStatusTraceAndDebugInternal
0x1402338cf  test    rsi, rsi
0x1402338d2  setnz   r9b
0x1402338d6  mov     dword ptr [rsp+178h+CompletionRoutine], edi
0x1402338da  mov     r8d, ebx
0x1402338dd  mov     rdx, rsi
0x1402338e0  mov     rcx, r13
0x1402338e3  call    NtfsExtendedCompleteRequestInternal
0x1402338e8  mov     cl, cs:NtfsStatusDebugFlags
0x1402338ee  test    cl, cl
0x1402338f0  jz      short loc_140233901
0x1402338f2  mov     r8d, 127300h
0x1402338f8  mov     edx, ebx
0x1402338fa  xor     ecx, ecx
0x1402338fc  call    NtfsStatusTraceAndDebugInternal
0x140233901  mov     eax, ebx
0x140233903  jmp     loc_140234FDA
0x140233908  add     [r15+2600h], r12
0x14023390f  mov     al, cs:NtfsStatusDebugFlags
0x140233915  xor     ebx, ebx
0x140233917  mov     r14d, 0C000026Eh
0x14023391d  test    al, al
0x14023391f  jz      short loc_140233932
0x140233921  mov     r8d, 1272F3h
0x140233927  mov     edx, r14d
0x14023392a  mov     rcx, r13
0x14023392d  call    NtfsStatusTraceAndDebugInternal
0x140233932  test    rsi, rsi
0x140233935  setnz   r9b
0x140233939  mov     dword ptr [rsp+178h+CompletionRoutine], ebx
0x14023393d  mov     r8d, r14d
0x140233940  mov     rdx, rsi
0x140233943  mov     rcx, r13
0x140233946  call    NtfsExtendedCompleteRequestInternal
0x14023394b  mov     al, cs:NtfsStatusDebugFlags
0x140233951  test    al, al
0x140233953  jz      loc_140234FD7
0x140233959  mov     r8d, 1272F4h
0x14023395f  jmp     loc_140234FCD
0x140233964  mov     [rsp+178h+var_40], r14
0x14023396c  test    dword ptr [r14+200h], 1000000h
0x140233977  jz      short loc_1402339D3
0x140233979  add     [r15+2600h], r12
0x140233980  mov     al, cs:NtfsStatusDebugFlags
0x140233986  xor     edi, edi
0x140233988  mov     ebx, 0C0000008h
0x14023398d  test    al, al
0x14023398f  jz      short loc_1402339A1
0x140233991  mov     r8d, 127308h
0x140233997  mov     edx, ebx
0x140233999  mov     rcx, r13
0x14023399c  call    NtfsStatusTraceAndDebugInternal
0x1402339a1  test    rsi, rsi
0x1402339a4  setnz   r9b
0x1402339a8  mov     dword ptr [rsp+178h+CompletionRoutine], edi
0x1402339ac  mov     r8d, ebx
0x1402339af  mov     rdx, rsi
0x1402339b2  mov     rcx, r13
0x1402339b5  call    NtfsExtendedCompleteRequestInternal
0x1402339ba  mov     cl, cs:NtfsStatusDebugFlags
0x1402339c0  test    cl, cl
0x1402339c2  jz      loc_140233901
0x1402339c8  mov     r8d, 127309h
0x1402339ce  jmp     loc_1402338F8
0x1402339d3  xor     ecx, ecx
0x1402339d5  test    rbx, rbx
0x1402339d8  jz      short loc_140233A3F
0x1402339da  test    dword ptr [rbx+4], 2000h
0x1402339e1  jz      short loc_140233A3F
0x1402339e3  add     [r15+2600h], r12
0x1402339ea  mov     al, cs:NtfsStatusDebugFlags
0x1402339f0  mov     r14d, 0C000000Dh
0x1402339f6  test    al, al
0x1402339f8  jz      short loc_140233A0D
0x1402339fa  mov     r8d, 127316h
0x140233a00  mov     edx, r14d
0x140233a03  mov     rcx, r13
0x140233a06  call    NtfsStatusTraceAndDebugInternal
0x140233a0b  xor     ecx, ecx
0x140233a0d  test    rsi, rsi
0x140233a10  setnz   r9b
0x140233a14  mov     dword ptr [rsp+178h+CompletionRoutine], ecx
0x140233a18  mov     r8d, r14d
0x140233a1b  mov     rdx, rsi
0x140233a1e  mov     rcx, r13
0x140233a21  call    NtfsExtendedCompleteRequestInternal
0x140233a26  mov     al, cs:NtfsStatusDebugFlags
0x140233a2c  test    al, al
0x140233a2e  jz      loc_140234FD7
0x140233a34  mov     r8d, 127317h
0x140233a3a  jmp     loc_140234FCD
0x140233a3f  mov     edx, 40FFh
0x140233a44  test    [r14+1CCh], dx
0x140233a4c  jz      short loc_140233AAA
0x140233a4e  add     [r15+2600h], r12
0x140233a55  mov     al, cs:NtfsStatusDebugFlags
0x140233a5b  mov     r14d, 0C000000Dh
0x140233a61  test    al, al
0x140233a63  jz      short loc_140233A78
0x140233a65  mov     r8d, 127322h
0x140233a6b  mov     edx, r14d
0x140233a6e  mov     rcx, r13
0x140233a71  call    NtfsStatusTraceAndDebugInternal
0x140233a76  xor     ecx, ecx
0x140233a78  test    rsi, rsi
0x140233a7b  setnz   r9b
0x140233a7f  mov     dword ptr [rsp+178h+CompletionRoutine], ecx
0x140233a83  mov     r8d, r14d
0x140233a86  mov     rdx, rsi
0x140233a89  mov     rcx, r13
0x140233a8c  call    NtfsExtendedCompleteRequestInternal
0x140233a91  mov     al, cs:NtfsStatusDebugFlags
0x140233a97  test    al, al
0x140233a99  jz      loc_140234FD7
0x140233a9f  mov     r8d, 127323h
0x140233aa5  jmp     loc_140234FCD
0x140233aaa  mov     rdx, [rsp+178h+arg_10]
0x140233ab2  mov     r8d, [rdx+10h]
0x140233ab6  cmp     r8d, 18h
0x140233aba  jnb     short loc_140233B18
0x140233abc  add     [r15+2600h], r12
0x140233ac3  mov     al, cs:NtfsStatusDebugFlags
0x140233ac9  mov     r14d, 0C000000Dh
0x140233acf  test    al, al
0x140233ad1  jz      short loc_140233AE6
0x140233ad3  mov     r8d, 12732Eh
0x140233ad9  mov     edx, r14d
0x140233adc  mov     rcx, r13
0x140233adf  call    NtfsStatusTraceAndDebugInternal
0x140233ae4  xor     ecx, ecx
0x140233ae6  test    rsi, rsi
0x140233ae9  setnz   r9b
0x140233aed  mov     dword ptr [rsp+178h+CompletionRoutine], ecx
0x140233af1  mov     r8d, r14d
0x140233af4  mov     rdx, rsi
0x140233af7  mov     rcx, r13
0x140233afa  call    NtfsExtendedCompleteRequestInternal
0x140233aff  mov     al, cs:NtfsStatusDebugFlags
0x140233b05  test    al, al
0x140233b07  jz      loc_140234FD7
0x140233b0d  mov     r8d, 12732Fh
0x140233b13  jmp     loc_140234FCD
0x140233b18  mov     rax, [rsi+18h]
0x140233b1c  mov     [rsp+178h+var_C8], rax
0x140233b24  mov     eax, [rax+4]
0x140233b27  xor     ebx, ebx
0x140233b29  test    eax, eax
0x140233b2b  jz      loc_140234F7C
0x140233b31  lea     ecx, [rax-1]
0x140233b34  shl     rcx, 4
0x140233b38  mov     eax, 0FFFFFFFFh
0x140233b3d  cmp     rcx, rax
0x140233b40  ja      loc_140234F7C
0x140233b46  lea     eax, [rcx+18h]
0x140233b49  cmp     eax, ecx
0x140233b4b  jb      loc_140234F7C
0x140233b51  cmp     r8d, eax
0x140233b54  jb      loc_140234F7C
0x140233b5a  mov     eax, [rdx+8]
0x140233b5d  sub     eax, r12d
0x140233b60  cmp     eax, 2
0x140233b63  ja      short loc_140233BBF
0x140233b65  add     [r15+2600h], r12
0x140233b6c  mov     al, cs:NtfsStatusDebugFlags
0x140233b72  mov     r14d, 0C000000Dh
0x140233b78  test    al, al
0x140233b7a  jz      short loc_140233B8D
0x140233b7c  mov     r8d, 127352h
0x140233b82  mov     edx, r14d
0x140233b85  mov     rcx, r13
0x140233b88  call    NtfsStatusTraceAndDebugInternal
0x140233b8d  test    rsi, rsi
0x140233b90  setnz   r9b
0x140233b94  mov     dword ptr [rsp+178h+CompletionRoutine], ebx
0x140233b98  mov     r8d, r14d
0x140233b9b  mov     rdx, rsi
0x140233b9e  mov     rcx, r13
0x140233ba1  call    NtfsExtendedCompleteRequestInternal
0x140233ba6  mov     al, cs:NtfsStatusDebugFlags
0x140233bac  test    al, al
0x140233bae  jz      loc_140234FD7
0x140233bb4  mov     r8d, 127353h
0x140233bba  jmp     loc_140234FCD
0x140233bbf  cmp     [r15+1591h], bl
0x140233bc6  jz      loc_140233C51
0x140233bcc  add     [r15+2600h], r12
0x140233bd3  test    dword ptr [r15+18h], 40000h
0x140233bdb  mov     al, cs:NtfsStatusDebugFlags
0x140233be1  jz      short loc_140233C04
0x140233be3  test    rsi, rsi
0x140233be6  setnz   r9b
0x140233bea  mov     dword ptr [rsp+178h+CompletionRoutine], r12d
  ... truncated ...
```
