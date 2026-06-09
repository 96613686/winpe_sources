# CfUpdateSyncProviderStatus

- ea: `0x180007cf0`
- end: `0x180008568`
- name: `CfUpdateSyncProviderStatus`
- size: `2168`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001070`
- `0x180001a80`
- `0x1800022ee`
- `0x180007cf0`
- `0x18000ad68`
- `0x18000b218`
- `0x18000b6c8`
- `0x180011338`
- `0x180011e18`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x180007e2c`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800081b6`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800081e1`
- `ntdll!RtlReleaseSRWLockShared` at `0x180007e2c`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800081b6`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800081e1`
- `ntdll!RtlAcquireSRWLockShared` at `0x180007dba`
- `ntdll!RtlAcquireSRWLockShared` at `0x180007fa0`
- `ntdll!RtlAcquireSRWLockShared` at `0x1800081d8`
- `ntdll!RtlAcquireSRWLockShared` at `0x180007dba`
- `ntdll!RtlAcquireSRWLockShared` at `0x180007fa0`
- `ntdll!RtlAcquireSRWLockShared` at `0x1800081d8`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180007e3a`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180007f30`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800081bf`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180007e3a`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180007f30`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800081bf`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180007e9b`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180007f5b`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800081cf`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180007e9b`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180007f5b`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800081cf`
- `ntdll!RtlNtStatusToDosError` at `0x1800082af`
- `ntdll!RtlNtStatusToDosError` at `0x180008333`
- `ntdll!RtlNtStatusToDosError` at `0x1800083b8`
- `ntdll!RtlNtStatusToDosError` at `0x18000843c`
- `ntdll!RtlNtStatusToDosError` at `0x1800082af`
- `ntdll!RtlNtStatusToDosError` at `0x180008333`
- `ntdll!RtlNtStatusToDosError` at `0x1800083b8`
- `ntdll!RtlNtStatusToDosError` at `0x18000843c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007da1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007da1`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180007d4f`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180007d4f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007e78`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007eac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800081ee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000852b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007e78`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007eac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800081ee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000852b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007ec2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008206`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007ec2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008206`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007e87`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008539`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007e87`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008539`
- `FLTLIB!FilterSendMessage` at `0x18000848e`
- `FLTLIB!FilterSendMessage` at `0x18000848e`

## string_xrefs

- `0x18000834d`: `SetCldMsgCommand Failed`
- `0x180007ef0`: `HeapAlloc for newThreadStatus failed`
- `0x18000822b`: `HeapAlloc for CldCmdUpdateProviderStatus Failed`

## pseudocode

```c
__int64 __fastcall CfUpdateSyncProviderStatus(__int64 a1, int a2)
{
  __int64 v2; // rbx
  unsigned int v3; // r12d
  _DWORD *v4; // rsi
  int v5; // edi
  int v6; // r13d
  const wchar_t *v7; // rcx
  int v8; // r13d
  __int64 v9; // r12
  __int64 v10; // r14
  _QWORD *v11; // rcx
  DWORD v12; // ebx
  _QWORD *v13; // r15
  DWORD *v14; // rdi
  _QWORD *v15; // rdi
  _QWORD *v16; // r13
  _QWORD *v17; // rcx
  _QWORD *v18; // rax
  HANDLE ProcessHeap; // rax
  HANDLE v20; // rax
  _DWORD *v21; // rax
  _DWORD *v22; // r15
  _QWORD *v23; // rcx
  unsigned int v24; // r12d
  __int64 v25; // r14
  __int64 v26; // rdi
  __int64 v27; // rdx
  const WCHAR *v28; // rax
  __int64 v29; // rcx
  int v30; // ecx
  const WCHAR *v31; // rcx
  __int64 v32; // rax
  int v33; // eax
  __int64 v34; // rdx
  const WCHAR *v35; // rax
  __int64 v36; // rcx
  int v37; // ecx
  const WCHAR *v38; // rcx
  __int64 v39; // rax
  int v40; // eax
  HANDLE v41; // rax
  NTSTATUS v42; // r14d
  NTSTATUS v43; // ecx
  __int64 v44; // rcx
  __int64 v45; // rax
  unsigned int v46; // ecx
  signed int v47; // eax
  NTSTATUS v48; // ecx
  __int64 v49; // rcx
  __int64 v50; // rax
  signed int v51; // eax
  NTSTATUS v52; // ecx
  __int64 v53; // rcx
  __int64 v54; // rax
  signed int v55; // eax
  __int64 v56; // rcx
  __int64 v57; // rax
  signed int v58; // eax
  HRESULT v59; // eax
  __int64 v60; // rbx
  const WCHAR *v61; // rdx
  const WCHAR *v62; // r9
  HANDLE v63; // rax
  unsigned int v65; // [rsp+40h] [rbp-C0h]
  int v67; // [rsp+48h] [rbp-B8h] BYREF
  DWORD CurrentThreadId; // [rsp+4Ch] [rbp-B4h] BYREF
  DWORD BytesReturned; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v70; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v71; // [rsp+60h] [rbp-A0h]
  unsigned __int64 UnbiasedTime; // [rsp+68h] [rbp-98h] BYREF
  __int64 v73; // [rsp+70h] [rbp-90h]
  _DWORD *v74; // [rsp+78h] [rbp-88h]
  int v75; // [rsp+80h] [rbp-80h] BYREF
  const wchar_t *v76; // [rsp+88h] [rbp-78h]
  __int64 v77; // [rsp+90h] [rbp-70h]
  int v78; // [rsp+98h] [rbp-68h]
  unsigned int v79; // [rsp+9Ch] [rbp-64h]
  char v80; // [rsp+A0h] [rbp-60h]
  _BYTE v81[32]; // [rsp+E0h] [rbp-20h] BYREF
  const WCHAR *v82; // [rsp+100h] [rbp+0h]
  int v83; // [rsp+108h] [rbp+8h]
  int v84; // [rsp+10Ch] [rbp+Ch]
  const WCHAR *v85; // [rsp+110h] [rbp+10h]
  int v86; // [rsp+118h] [rbp+18h]
  int v87; // [rsp+11Ch] [rbp+1Ch]
  DWORD *p_CurrentThreadId; // [rsp+120h] [rbp+20h]
  __int64 v89; // [rsp+128h] [rbp+28h]
  int *v90; // [rsp+130h] [rbp+30h]
  __int64 v91; // [rsp+138h] [rbp+38h]
  __int64 *v92; // [rsp+140h] [rbp+40h]
  __int64 v93; // [rsp+148h] [rbp+48h]

  v2 = a1;
  v73 = a1;
  UnbiasedTime = 0;
  v65 = 0;
  BytesReturned = 0;
  v3 = 0;
  memset_0(&v75, 0, 0x58u);
  QueryUnbiasedInterruptTime(&UnbiasedTime);
  v71 = CfpReferenceSyncRoot(v2);
  if ( !v71 )
  {
    v6 = a2;
    goto LABEL_66;
  }
  v74 = 0;
  v4 = 0;
  v80 = 1;
  v5 = GlobalPortInit(0);
  if ( v5 <= -1 )
  {
    v6 = a2;
    v7 = L"GlobalPortInit Failed";
    goto LABEL_113;
  }
  v67 = 0;
  v8 = 0;
  v9 = v71 + 168;
  CurrentThreadId = GetCurrentThreadId();
  v70 = v71 + 168;
  RtlAcquireSRWLockShared(v71 + 168);
  v10 = v71 + 152;
  v11 = *(_QWORD **)(v71 + 152);
  if ( *(_QWORD *)v10 == v10 )
    goto LABEL_13;
  v12 = CurrentThreadId;
  do
  {
    v13 = (_QWORD *)*v11;
    v14 = (DWORD *)(v11 - 1);
    if ( *((_DWORD *)v11 - 2) == v12 )
    {
      v67 = 1;
      if ( a2 >= 0 )
        *((_DWORD *)v11 - 1) = a2;
      else
        v14[1] = *((_DWORD *)v11 - 1) & ~a2;
    }
    else if ( (unsigned int)CfpIsThreadTerminated(*v14) )
    {
      v8 = 1;
      goto LABEL_11;
    }
    if ( v14 )
      LODWORD(v4) = v14[1] | (unsigned int)v4;
LABEL_11:
    v11 = v13;
  }
  while ( v13 != (_QWORD *)v10 );
  v2 = v73;
  v9 = v70;
  v65 = (unsigned int)v4;
  v4 = v74;
LABEL_13:
  RtlReleaseSRWLockShared(v9);
  if ( v8 )
  {
    RtlAcquireSRWLockExclusive(v9);
    v15 = *(_QWORD **)v10;
    if ( *(_QWORD *)v10 != v10 )
    {
      do
      {
        v16 = (_QWORD *)*v15;
        if ( (unsigned int)CfpIsThreadTerminated(*((_DWORD *)v15 - 2)) )
        {
          v17 = (_QWORD *)*v15;
          if ( *(_QWORD **)(*v15 + 8LL) != v15 )
            goto LABEL_30;
          v18 = (_QWORD *)v15[1];
          if ( (_QWORD *)*v18 != v15 )
            goto LABEL_30;
          *v18 = v17;
          v17[1] = v18;
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v15 - 1);
        }
        v15 = v16;
      }
      while ( v16 != (_QWORD *)v10 );
    }
    RtlReleaseSRWLockExclusive(v9);
  }
  if ( v67 )
  {
    v24 = v65;
    v6 = a2;
  }
  else
  {
    v20 = GetProcessHeap();
    v21 = HeapAlloc(v20, 8u, 0x18u);
    v22 = v21;
    v5 = v21 == 0 ? 8 : 0;
    v6 = a2;
    if ( !v21 )
      v5 |= 0x80070000;
    if ( v5 <= -1 )
    {
      v7 = L"HeapAlloc for newThreadStatus failed";
      goto LABEL_113;
    }
    v21[1] = a2;
    *v21 = CurrentThreadId;
    RtlAcquireSRWLockExclusive(v9);
    v23 = *(_QWORD **)v10;
    if ( *(_QWORD *)(*(_QWORD *)v10 + 8LL) != v10 )
LABEL_30:
      __fastfail(3u);
    *((_QWORD *)v22 + 1) = v23;
    *((_QWORD *)v22 + 2) = v10;
    v23[1] = v22 + 2;
    *(_QWORD *)v10 = v22 + 2;
    RtlReleaseSRWLockExclusive(v9);
    v24 = v22[1] | v65;
  }
  if ( v24 <= 1 )
    v3 = 1;
  else
    v3 = v24 & 0xFFFFFFFE;
  v25 = v71;
  v65 = v3;
  v26 = v71 + 144;
  RtlAcquireSRWLockShared(v71 + 144);
  if ( v3 != *(_DWORD *)(v71 + 140) )
  {
    if ( (unsigned int)dword_1800281A0 > 5
      && (qword_1800281B0 & 0x400000000000LL) != 0
      && (qword_1800281B8 & 0x400000000000LL) == qword_1800281B8 )
    {
      v27 = *(_QWORD *)(v71 + 16);
      v28 = (const WCHAR *)(v27 + 28);
      if ( v27 == -28 )
      {
        v28 = &SourceString;
        v30 = 2;
      }
      else
      {
        v29 = -1;
        do
          ++v29;
        while ( v28[v29] );
        v30 = 2 * v29 + 2;
      }
      v83 = v30;
      v31 = (const WCHAR *)(v27 + 540);
      v82 = v28;
      v84 = 0;
      if ( v27 == -540 )
      {
        v31 = &SourceString;
        v33 = 2;
      }
      else
      {
        v32 = -1;
        do
          ++v32;
        while ( v31[v32] );
        v33 = 2 * v32 + 2;
      }
      v86 = v33;
      v85 = v31;
      p_CurrentThreadId = &CurrentThreadId;
      v67 = *(_DWORD *)(v71 + 140);
      v87 = 0;
      v90 = &v67;
      v92 = &v70;
      CurrentThreadId = v3;
      v89 = 4;
      v91 = 4;
      v70 = 0x1000000;
      v93 = 8;
      tlgWriteTransfer_EventWriteTransfer(&dword_1800281A0, &dword_18002188C, 0, 0, 7, v81);
    }
    if ( dword_1800281A0 )
    {
      v34 = *(_QWORD *)(v25 + 16);
      v35 = (const WCHAR *)(v34 + 28);
      if ( v34 == -28 )
      {
        v35 = &SourceString;
        v37 = 2;
      }
      else
      {
        v36 = -1;
        do
          ++v36;
        while ( v35[v36] );
        v37 = 2 * v36 + 2;
      }
      v83 = v37;
      v38 = (const WCHAR *)(v34 + 540);
      v82 = v35;
      v84 = 0;
      if ( v34 == -540 )
      {
        v38 = &SourceString;
        v40 = 2;
      }
      else
      {
        v39 = -1;
        do
          ++v39;
        while ( v38[v39] );
        v40 = 2 * v39 + 2;
      }
      v86 = v40;
      v85 = v38;
      p_CurrentThreadId = &CurrentThreadId;
      v67 = *(_DWORD *)(v25 + 140);
      v87 = 0;
      v90 = &v67;
      CurrentThreadId = v3;
      v89 = 4;
      v91 = 4;
      tlgWriteTransfer_EventWriteTransfer(&dword_1800281A0, byte_18002182B, 0, 0, 6, v81);
    }
    RtlReleaseSRWLockShared(v26);
    RtlAcquireSRWLockExclusive(v26);
    *(_DWORD *)(v25 + 140) = v3;
    RtlReleaseSRWLockExclusive(v26);
    RtlAcquireSRWLockShared(v26);
  }
  RtlReleaseSRWLockShared(v26);
LABEL_66:
  v41 = GetProcessHeap();
  v4 = HeapAlloc(v41, 8u, 0xDCu);
  v5 = v4 == 0 ? 8 : 0;
  if ( !v4 )
    v5 |= 0x80070000;
  if ( v5 > -1 )
  {
    *(_QWORD *)v4 = 1886219331;
    v4[2] = 200;
    v4[3] = 1507328;
    memset_0(v4 + 4, 0, 0xB8u);
    v42 = -1073741811;
    if ( *((_WORD *)v4 + 7) )
    {
      v44 = (unsigned int)v4[2];
      if ( ((v44 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 1 <= 0xDC )
      {
        v46 = (v44 + 3) & 0xFFFFFFFC;
        v45 = v46;
        v4[2] = v46;
        v4[5] = v46;
        v43 = 0;
        v4[4] = 65543;
        *((_BYTE *)v4 + v45) = 1;
        ++v4[2];
      }
      else
      {
        v43 = -1073741789;
      }
    }
    else
    {
      v43 = -1073741811;
    }
    v47 = RtlNtStatusToDosError(v43);
    v5 = v47;
    if ( v47 > 0 )
      v5 = (unsigned __int16)v47 | 0x80070000;
    if ( v5 > -1 )
    {
      if ( *((_WORD *)v4 + 7) > 1u )
      {
        v49 = (unsigned int)v4[2];
        if ( ((v49 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 2 <= 0xDC )
        {
          v50 = ((_DWORD)v49 + 3) & 0xFFFFFFFC;
          v4[2] = v50;
          if ( *((_WORD *)v4 + 12) )
            *((_WORD *)v4 + 6) |= 1u;
          v4[6] = 131080;
          v48 = 0;
          v4[7] = v50;
          *(_WORD *)((char *)v4 + v50) = 6;
          v4[2] += 2;
        }
        else
        {
          v48 = -1073741789;
        }
      }
      else
      {
        v48 = -1073741811;
      }
      v51 = RtlNtStatusToDosError(v48);
      v5 = v51;
      if ( v51 > 0 )
        v5 = (unsigned __int16)v51 | 0x80070000;
      if ( v5 > -1 )
      {
        if ( *((_WORD *)v4 + 7) > 4u )
        {
          v53 = (unsigned int)v4[2];
          if ( ((v53 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 8 <= 0xDC )
          {
            v54 = ((_DWORD)v53 + 3) & 0xFFFFFFFC;
            v4[2] = v54;
            if ( *((_WORD *)v4 + 24) )
              *((_WORD *)v4 + 6) |= 1u;
            v4[12] = 524294;
            v52 = 0;
            v4[13] = v54;
            *(_QWORD *)((char *)v4 + v54) = v2;
            v4[2] += 8;
          }
          else
          {
            v52 = -1073741789;
          }
        }
        else
        {
          v52 = -1073741811;
        }
        v55 = RtlNtStatusToDosError(v52);
        v5 = v55;
        if ( v55 > 0 )
          v5 = (unsigned __int16)v55 | 0x80070000;
        if ( v5 > -1 )
        {
          if ( *((_WORD *)v4 + 7) > 0xDu )
          {
            v56 = (unsigned int)v4[2];
            if ( ((v56 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 4 <= 0xDC )
            {
              v57 = ((_DWORD)v56 + 3) & 0xFFFFFFFC;
              v4[2] = v57;
              if ( *((_WORD *)v4 + 60) )
                *((_WORD *)v4 + 6) |= 1u;
              v4[30] = 262154;
              v42 = 0;
              v4[31] = v57;
              *(_DWORD *)((char *)v4 + v57) = v3;
              v4[2] += 4;
            }
            else
            {
              v42 = -1073741789;
            }
          }
          v58 = RtlNtStatusToDosError(v42);
          v5 = v58;
          if ( v58 > 0 )
            v5 = (unsigned __int16)v58 | 0x80070000;
          if ( v5 > -1 )
          {
            v4[1] = 0;
            *((_WORD *)v4 + 6) &= ~2u;
            v59 = FilterSendMessage(hPort, v4, 0xDCu, 0, 0, &BytesReturned);
            v7 = L"FilterSendMessage Failed";
            v5 = v59;
            if ( v59 > -1 )
              v7 = 0;
          }
          else
          {
            v7 = L"SetCldDsMsgProviderStatus Failed";
          }
        }
        else
        {
          v7 = L"SetCldDsMsgSyncRootKey Failed";
        }
      }
      else
      {
        v7 = L"SetCldMsgCommand Failed";
      }
    }
    else
    {
      v7 = L"SetVersion Failed";
    }
  }
  else
  {
    v7 = L"HeapAlloc for CldCmdUpdateProviderStatus Failed";
  }
LABEL_113:
  v77 = v2;
  v60 = v71;
  v76 = v7;
  v78 = v6;
  v79 = v65;
  if ( v71 )
  {
    v61 = (const WCHAR *)((*(_QWORD *)(v71 + 16) + 540LL) & -(__int64)(*(_QWORD *)(v71 + 16) != 0));
    v62 = (const WCHAR *)((*(_QWORD *)(v71 + 16) + 28LL) & -(__int64)(*(_QWORD *)(v71 + 16) != 0));
  }
  else
  {
    v62 = 0;
    v61 = 0;
  }
  TlmLogApiReliability(0xDu, 0, 0, v62, v61, UnbiasedTime, &v75, v5);
  if ( v60 )
    CfpReleaseSyncRoot(v60);
  if ( v4 )
  {
    v63 = GetProcessHeap();
    HeapFree(v63, 0, v4);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180007cf0  mov     [rsp-8+arg_10], rbx
0x180007cf5  push    rbp
0x180007cf6  push    rsi
0x180007cf7  push    rdi
0x180007cf8  push    r12
0x180007cfa  push    r13
0x180007cfc  push    r14
0x180007cfe  push    r15
0x180007d00  lea     rbp, [rsp-60h]
0x180007d05  sub     rsp, 160h
0x180007d0c  mov     rax, cs:__security_cookie
0x180007d13  xor     rax, rsp
0x180007d16  mov     [rbp+90h+var_40], rax
0x180007d1a  xor     r15d, r15d
0x180007d1d  mov     [rsp+190h+var_14C], edx
0x180007d21  mov     rbx, rcx
0x180007d24  mov     [rsp+190h+var_120], rcx
0x180007d29  xor     edx, edx; Val
0x180007d2b  mov     [rsp+190h+UnbiasedTime], r15
0x180007d30  lea     rcx, [rbp+90h+var_110]; void *
0x180007d34  mov     [rsp+190h+var_150], r15d
0x180007d39  lea     r8d, [r15+58h]; Size
0x180007d3d  mov     [rsp+190h+BytesReturned], r15d
0x180007d42  mov     r12d, r15d
0x180007d45  call    memset_0
0x180007d4a  lea     rcx, [rsp+190h+UnbiasedTime]; UnbiasedTime
0x180007d4f  call    cs:__imp_QueryUnbiasedInterruptTime
0x180007d55  mov     rcx, rbx
0x180007d58  call    CfpReferenceSyncRoot
0x180007d5d  mov     [rsp+190h+var_130], rax
0x180007d62  mov     r14, rax
0x180007d65  test    rax, rax
0x180007d68  jz      loc_1800081E9
0x180007d6e  xor     ecx, ecx
0x180007d70  mov     [rsp+190h+var_118], r15
0x180007d75  mov     esi, r15d
0x180007d78  mov     [rbp+90h+var_F0], 1
0x180007d7c  call    GlobalPortInit
0x180007d81  mov     edi, eax
0x180007d83  cmp     eax, 0FFFFFFFFh
0x180007d86  jg      short loc_180007D99
0x180007d88  mov     r13d, [rsp+190h+var_14C]
0x180007d8d  lea     rcx, aGlobalportinit; "GlobalPortInit Failed"
0x180007d94  jmp     loc_1800084A4
0x180007d99  mov     [rsp+190h+var_148], r15d
0x180007d9e  mov     r13d, r15d
0x180007da1  call    cs:__imp_GetCurrentThreadId
0x180007da7  lea     r12, [r14+0A8h]
0x180007dae  mov     [rsp+190h+var_144], eax
0x180007db2  mov     rcx, r12
0x180007db5  mov     [rsp+190h+var_138], r12
0x180007dba  call    cs:__imp_RtlAcquireSRWLockShared
0x180007dc0  add     r14, 98h
0x180007dc7  mov     rcx, [r14]
0x180007dca  cmp     rcx, r14
0x180007dcd  jz      short loc_180007E29
0x180007dcf  mov     ebx, [rsp+190h+var_144]
0x180007dd3  mov     r12d, [rsp+190h+var_14C]
0x180007dd8  mov     r15, [rcx]
0x180007ddb  lea     rdi, [rcx-8]
0x180007ddf  cmp     [rdi], ebx
0x180007de1  jnz     loc_180007F08
0x180007de7  mov     [rsp+190h+var_148], 1
0x180007def  test    r12d, r12d
0x180007df2  jns     loc_180007EFF
0x180007df8  mov     eax, r12d
0x180007dfb  not     eax
0x180007dfd  and     eax, [rcx-4]
0x180007e00  mov     [rdi+4], eax
0x180007e03  test    rdi, rdi
0x180007e06  jz      short loc_180007E0B
0x180007e08  or      esi, [rdi+4]
0x180007e0b  mov     rcx, r15
0x180007e0e  cmp     r15, r14
0x180007e11  jnz     short loc_180007DD8
0x180007e13  mov     rbx, [rsp+190h+var_120]
0x180007e18  xor     r15d, r15d
0x180007e1b  mov     r12, [rsp+190h+var_138]
0x180007e20  mov     [rsp+190h+var_150], esi
0x180007e24  mov     rsi, [rsp+190h+var_118]
0x180007e29  mov     rcx, r12
0x180007e2c  call    cs:__imp_RtlReleaseSRWLockShared
0x180007e32  test    r13d, r13d
0x180007e35  jz      short loc_180007EA1
0x180007e37  mov     rcx, r12
0x180007e3a  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180007e40  mov     rdi, [r14]
0x180007e43  cmp     rdi, r14
0x180007e46  jz      short loc_180007E98
0x180007e48  mov     ecx, [rdi-8]; dwThreadId
0x180007e4b  mov     r13, [rdi]
0x180007e4e  call    CfpIsThreadTerminated
0x180007e53  test    eax, eax
0x180007e55  jz      short loc_180007E8D
0x180007e57  mov     rcx, [rdi]
0x180007e5a  cmp     [rcx+8], rdi
0x180007e5e  jnz     loc_180007F3F
0x180007e64  mov     rax, [rdi+8]
0x180007e68  cmp     [rax], rdi
0x180007e6b  jnz     loc_180007F3F
0x180007e71  mov     [rax], rcx
0x180007e74  mov     [rcx+8], rax
0x180007e78  call    cs:__imp_GetProcessHeap
0x180007e7e  lea     r8, [rdi-8]; lpMem
0x180007e82  xor     edx, edx; dwFlags
0x180007e84  mov     rcx, rax; hHeap
0x180007e87  call    cs:__imp_HeapFree
0x180007e8d  mov     rdi, r13
0x180007e90  cmp     r13, r14
0x180007e93  jnz     short loc_180007E48
0x180007e95  xor     r15d, r15d
0x180007e98  mov     rcx, r12
0x180007e9b  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180007ea1  cmp     [rsp+190h+var_148], r15d
0x180007ea6  jnz     loc_180007F6F
0x180007eac  call    cs:__imp_GetProcessHeap
0x180007eb2  mov     r8d, 18h; dwBytes
0x180007eb8  mov     rcx, rax; hHeap
0x180007ebb  lea     r13d, [r8-10h]
0x180007ebf  mov     edx, r13d; dwFlags
0x180007ec2  call    cs:__imp_HeapAlloc
0x180007ec8  mov     rcx, rax
0x180007ecb  mov     r15, rax
0x180007ece  neg     rcx
0x180007ed1  sbb     edi, edi
0x180007ed3  not     edi
0x180007ed5  and     edi, r13d
0x180007ed8  mov     r13d, [rsp+190h+var_14C]
0x180007edd  mov     ecx, edi
0x180007edf  or      ecx, 80070000h
0x180007ee5  test    rax, rax
0x180007ee8  cmovz   edi, ecx
0x180007eeb  cmp     edi, 0FFFFFFFFh
0x180007eee  jg      short loc_180007F22
0x180007ef0  lea     rcx, aHeapallocForNe; "HeapAlloc for newThreadStatus failed"
0x180007ef7  xor     r15d, r15d
0x180007efa  jmp     loc_1800084A4
0x180007eff  mov     [rcx-4], r12d
0x180007f03  jmp     loc_180007E03
0x180007f08  mov     ecx, [rdi]; dwThreadId
0x180007f0a  call    CfpIsThreadTerminated
0x180007f0f  test    eax, eax
0x180007f11  jz      loc_180007E03
0x180007f17  mov     r13d, 1
0x180007f1d  jmp     loc_180007E0B
0x180007f22  mov     [rax+4], r13d
0x180007f26  mov     rcx, r12
0x180007f29  mov     eax, [rsp+190h+var_144]
0x180007f2d  mov     [r15], eax
0x180007f30  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180007f36  mov     rcx, [r14]
0x180007f39  cmp     [rcx+8], r14
0x180007f3d  jz      short loc_180007F46
0x180007f3f  mov     ecx, 3
0x180007f44  int     29h; Win8: RtlFailFast(ecx)
0x180007f46  lea     rax, [r15+8]
0x180007f4a  mov     [rax], rcx
0x180007f4d  mov     [rax+8], r14
0x180007f51  mov     [rcx+8], rax
0x180007f55  mov     rcx, r12
0x180007f58  mov     [r14], rax
0x180007f5b  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180007f61  mov     r12d, [rsp+190h+var_150]
0x180007f66  or      r12d, [r15+4]
0x180007f6a  xor     r15d, r15d
0x180007f6d  jmp     short loc_180007F79
0x180007f6f  mov     r12d, [rsp+190h+var_150]
0x180007f74  mov     r13d, [rsp+190h+var_14C]
0x180007f79  mov     eax, 1
0x180007f7e  cmp     r12d, eax
0x180007f81  jbe     short loc_180007F89
0x180007f83  and     r12d, 0FFFFFFFEh
0x180007f87  jmp     short loc_180007F8C
0x180007f89  mov     r12d, eax
0x180007f8c  mov     r14, [rsp+190h+var_130]
0x180007f91  mov     [rsp+190h+var_150], r12d
0x180007f96  lea     rdi, [r14+90h]
0x180007f9d  mov     rcx, rdi
0x180007fa0  call    cs:__imp_RtlAcquireSRWLockShared
0x180007fa6  cmp     r12d, [r14+8Ch]
0x180007fad  jz      loc_1800081DE
0x180007fb3  mov     eax, cs:dword_1800281A0
0x180007fb9  lea     rsi, SourceString
0x180007fc0  cmp     eax, 5
0x180007fc3  jbe     loc_1800080DC
0x180007fc9  mov     rcx, cs:qword_1800281B8
0x180007fd0  mov     rdx, 400000000000h
0x180007fda  mov     rax, cs:qword_1800281B0
0x180007fe1  test    rdx, rax
0x180007fe4  jz      loc_1800080DC
0x180007fea  mov     rax, rcx
0x180007fed  and     rax, rdx
0x180007ff0  cmp     rax, rcx
0x180007ff3  jnz     loc_1800080DC
0x180007ff9  mov     rdx, [r14+10h]
0x180007ffd  lea     rax, [rdx+1Ch]
0x180008001  test    rax, rax
0x180008004  jz      short loc_18000801D
0x180008006  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000800a  inc     rcx
0x18000800d  cmp     [rax+rcx*2], r15w
0x180008012  jnz     short loc_18000800A
0x180008014  lea     ecx, ds:2[rcx*2]
0x18000801b  jmp     short loc_180008025
0x18000801d  mov     rax, rsi
0x180008020  mov     ecx, 2
0x180008025  mov     [rbp+90h+var_88], ecx
0x180008028  lea     rcx, [rdx+21Ch]
0x18000802f  mov     [rbp+90h+var_90], rax
0x180008033  mov     [rbp+90h+var_84], r15d
0x180008037  test    rcx, rcx
0x18000803a  jz      short loc_180008053
0x18000803c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008040  inc     rax
0x180008043  cmp     [rcx+rax*2], r15w
0x180008048  jnz     short loc_180008040
0x18000804a  lea     eax, ds:2[rax*2]
0x180008051  jmp     short loc_18000805B
0x180008053  mov     rcx, rsi
0x180008056  mov     eax, 2
0x18000805b  mov     [rbp+90h+var_78], eax
0x18000805e  lea     rdx, dword_18002188C
0x180008065  lea     rax, [rsp+190h+var_144]
0x18000806a  mov     [rbp+90h+var_80], rcx
0x18000806e  mov     [rbp+90h+var_70], rax
0x180008072  lea     rcx, dword_1800281A0
0x180008079  mov     eax, [r14+8Ch]
0x180008080  xor     r9d, r9d
0x180008083  mov     [rsp+190h+var_148], eax
0x180008087  xor     r8d, r8d
0x18000808a  lea     rax, [rsp+190h+var_148]
0x18000808f  mov     [rbp+90h+var_74], r15d
0x180008093  mov     [rbp+90h+var_60], rax
0x180008097  lea     rax, [rsp+190h+var_138]
0x18000809c  mov     [rbp+90h+var_50], rax
0x1800080a0  lea     rax, [rbp+90h+var_B0]
0x1800080a4  mov     [rsp+190h+lpBytesReturned], rax
0x1800080a9  mov     [rsp+190h+dwOutBufferSize], 7
0x1800080b1  mov     [rsp+190h+var_144], r12d
0x1800080b6  mov     [rbp+90h+var_68], 4
0x1800080be  mov     [rbp+90h+var_58], 4
0x1800080c6  mov     [rsp+190h+var_138], 1000000h
0x1800080cf  mov     [rbp+90h+var_48], 8
0x1800080d7  call    _tlgWriteTransfer_EventWriteTransfer
0x1800080dc  mov     eax, cs:dword_1800281A0
0x1800080e2  test    eax, eax
0x1800080e4  jz      loc_1800081B3
0x1800080ea  mov     rdx, [r14+10h]
0x1800080ee  lea     rax, [rdx+1Ch]
0x1800080f2  test    rax, rax
0x1800080f5  jz      short loc_18000810E
0x1800080f7  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800080fb  inc     rcx
0x1800080fe  cmp     [rax+rcx*2], r15w
0x180008103  jnz     short loc_1800080FB
0x180008105  lea     ecx, ds:2[rcx*2]
0x18000810c  jmp     short loc_180008116
0x18000810e  mov     rax, rsi
0x180008111  mov     ecx, 2
0x180008116  mov     [rbp+90h+var_88], ecx
0x180008119  lea     rcx, [rdx+21Ch]
0x180008120  mov     [rbp+90h+var_90], rax
0x180008124  mov     [rbp+90h+var_84], r15d
0x180008128  test    rcx, rcx
0x18000812b  jz      short loc_180008144
0x18000812d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008131  inc     rax
0x180008134  cmp     [rcx+rax*2], r15w
0x180008139  jnz     short loc_180008131
0x18000813b  lea     eax, ds:2[rax*2]
0x180008142  jmp     short loc_18000814C
0x180008144  mov     rcx, rsi
0x180008147  mov     eax, 2
0x18000814c  mov     [rbp+90h+var_78], eax
0x18000814f  lea     rdx, byte_18002182B
0x180008156  lea     rax, [rsp+190h+var_144]
0x18000815b  mov     [rbp+90h+var_80], rcx
0x18000815f  mov     [rbp+90h+var_70], rax
0x180008163  lea     rcx, dword_1800281A0
0x18000816a  mov     eax, [r14+8Ch]
0x180008171  xor     r9d, r9d
0x180008174  mov     [rsp+190h+var_148], eax
0x180008178  xor     r8d, r8d
0x18000817b  lea     rax, [rsp+190h+var_148]
0x180008180  mov     [rbp+90h+var_74], r15d
0x180008184  mov     [rbp+90h+var_60], rax
0x180008188  lea     rax, [rbp+90h+var_B0]
0x18000818c  mov     [rsp+190h+lpBytesReturned], rax
0x180008191  mov     [rsp+190h+dwOutBufferSize], 6
0x180008199  mov     [rsp+190h+var_144], r12d
0x18000819e  mov     [rbp+90h+var_68], 4
0x1800081a6  mov     [rbp+90h+var_58], 4
0x1800081ae  call    _tlgWriteTransfer_EventWriteTransfer
0x1800081b3  mov     rcx, rdi
0x1800081b6  call    cs:__imp_RtlReleaseSRWLockShared
0x1800081bc  mov     rcx, rdi
0x1800081bf  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800081c5  mov     rcx, rdi
0x1800081c8  mov     [r14+8Ch], r12d
0x1800081cf  call    cs:__imp_RtlReleaseSRWLockExclusive
  ... truncated ...
```
