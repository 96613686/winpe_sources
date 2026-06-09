# MpLoadImageNotifyRoutine

- ea: `0x140082380`
- end: `0x140083b94`
- name: `MpLoadImageNotifyRoutine`
- size: `6164`
- prototype: `void __stdcall(PUNICODE_STRING FullImageName, HANDLE ProcessId, PIMAGE_INFO ImageInfo)`
- caller_count: `0`
- callee_count: `25`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callees

- `0x1400018a4`
- `0x1400026c0`
- `0x140003950`
- `0x140003d20`
- `0x1400049dc`
- `0x1400051bc`
- `0x140005df8`
- `0x1400078a4`
- `0x140009b14`
- `0x140009bf0`
- `0x14000a760`
- `0x1400118d0`
- `0x140011900`
- `0x14002f9f0`
- `0x140030060`
- `0x140034b50`
- `0x140035e50`
- `0x140038370`
- `0x140056b50`
- `0x140056c20`
- `0x14005e280`
- `0x140064160`
- `0x14007c758`
- `0x1400800fc`
- `0x140082380`

## import_xrefs

- `ntoskrnl!KeReadStateSemaphore` at `0x140082f4c`
- `ntoskrnl!KeReadStateSemaphore` at `0x1400830b8`
- `ntoskrnl!KeReadStateSemaphore` at `0x1400835f9`
- `ntoskrnl!KeReadStateSemaphore` at `0x140083760`
- `ntoskrnl!KeReadStateSemaphore` at `0x140082f4c`
- `ntoskrnl!KeReadStateSemaphore` at `0x1400830b8`
- `ntoskrnl!KeReadStateSemaphore` at `0x1400835f9`
- `ntoskrnl!KeReadStateSemaphore` at `0x140083760`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x140082add`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x140082add`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x140082af2`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x140082af2`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400826c1`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400826c1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140082824`
- `ntoskrnl!ExFreePoolWithTag` at `0x140082eb0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400830e3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008355f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008378b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140083974`
- `ntoskrnl!ExFreePoolWithTag` at `0x140083a70`
- `ntoskrnl!ExFreePoolWithTag` at `0x140082824`
- `ntoskrnl!ExFreePoolWithTag` at `0x140082eb0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400830e3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008355f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008378b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140083974`
- `ntoskrnl!ExFreePoolWithTag` at `0x140083a70`
- `ntoskrnl!KeReleaseSemaphore` at `0x140083080`
- `ntoskrnl!KeReleaseSemaphore` at `0x140083728`
- `ntoskrnl!KeReleaseSemaphore` at `0x140083080`
- `ntoskrnl!KeReleaseSemaphore` at `0x140083728`
- `ntoskrnl!ObfDereferenceObject` at `0x140082b06`
- `ntoskrnl!ObfDereferenceObject` at `0x140082b06`
- `HAL!KeQueryPerformanceCounter` at `0x140082f94`
- `HAL!KeQueryPerformanceCounter` at `0x140082fee`
- `HAL!KeQueryPerformanceCounter` at `0x14008363f`
- `HAL!KeQueryPerformanceCounter` at `0x140083697`
- `HAL!KeQueryPerformanceCounter` at `0x140082f94`
- `HAL!KeQueryPerformanceCounter` at `0x140082fee`
- `HAL!KeQueryPerformanceCounter` at `0x14008363f`
- `HAL!KeQueryPerformanceCounter` at `0x140083697`
- `FLTMGR!FltSendMessage` at `0x14008271a`
- `FLTMGR!FltSendMessage` at `0x140082fd6`
- `FLTMGR!FltSendMessage` at `0x140083680`
- `FLTMGR!FltSendMessage` at `0x14008271a`
- `FLTMGR!FltSendMessage` at `0x140082fd6`
- `FLTMGR!FltSendMessage` at `0x140083680`
- `FLTMGR!FltReleaseContext` at `0x140083b11`
- `FLTMGR!FltReleaseContext` at `0x140083b11`
- `FLTMGR!FltCancellableWaitForSingleObject` at `0x140082dc8`
- `FLTMGR!FltCancellableWaitForSingleObject` at `0x140083478`
- `FLTMGR!FltCancellableWaitForSingleObject` at `0x140082dc8`
- `FLTMGR!FltCancellableWaitForSingleObject` at `0x140083478`

## pseudocode

```c
void __fastcall MpLoadImageNotifyRoutine(const UNICODE_STRING *FullImageName, HANDLE ProcessId, PIMAGE_INFO ImageInfo)
{
  unsigned int v3; // edi
  HANDLE QuadPart; // r15
  bool v7; // bl
  int ProcessContextById; // eax
  PEPROCESS v9; // r13
  bool v10; // r15
  int *v11; // rbx
  int v12; // ecx
  int v13; // eax
  __int64 v14; // rcx
  union _LARGE_INTEGER v15; // rbx
  union _LARGE_INTEGER *p_Process; // rax
  NTSTATUS v17; // edi
  __int64 v18; // r9
  int Length; // eax
  bool v20; // r14
  struct _FILE_OBJECT *v21; // rdi
  int StreamContextFromFileObject; // eax
  __int64 v23; // r8
  DWORD *v24; // rdx
  char v25; // al
  int v26; // ecx
  __int64 v27; // r12
  ULONG v28; // edi
  LONGLONG TimeQuadPart; // rdi
  __int64 v30; // rax
  unsigned int v31; // edi
  __int64 v32; // rdx
  __int64 v33; // rcx
  int v34; // eax
  WCHAR *v35; // rdx
  int v36; // eax
  int v37; // eax
  int v38; // eax
  int v39; // r15d
  int v40; // ecx
  volatile signed __int32 *v41; // rsi
  PDEVICE_OBJECT v42; // rax
  bool v43; // zf
  PDEVICE_OBJECT v44; // rax
  bool v45; // zf
  unsigned int v46; // ebx
  unsigned int v47; // edi
  __int64 PoolWithTag; // rax
  ULONG *v49; // r14
  NTSTATUS v50; // edi
  __int128 v51; // xmm0
  _DWORD *v52; // rdi
  __int64 v53; // r15
  union _LARGE_INTEGER v54; // rcx
  unsigned int v55; // ebx
  NTSTATUS v56; // eax
  __int64 v57; // r9
  struct _DEVICE_OBJECT *AttachedDevice; // rbx
  unsigned int StateSemaphore; // eax
  LARGE_INTEGER PerformanceCounter; // rbx
  LONGLONG v61; // r8
  struct _DEVICE_OBJECT *v62; // rbx
  unsigned int v63; // eax
  __int64 v64; // r8
  PDEVICE_OBJECT v65; // rax
  bool v66; // zf
  volatile signed __int32 *v67; // rsi
  unsigned int v68; // ebx
  unsigned int v69; // edi
  __int64 v70; // rax
  ULONG *v71; // r14
  __int128 v72; // xmm0
  _DWORD *v73; // rdi
  __int64 v74; // r15
  union _LARGE_INTEGER v75; // rcx
  NTSTATUS v76; // eax
  struct _DEVICE_OBJECT *v77; // rbx
  unsigned int v78; // eax
  LARGE_INTEGER v79; // rbx
  LONGLONG v80; // r8
  struct _DEVICE_OBJECT *v81; // rbx
  unsigned int v82; // eax
  __int64 v83; // r8
  int v84; // eax
  char v85; // [rsp+48h] [rbp-C0h]
  unsigned int v86; // [rsp+4Ch] [rbp-BCh]
  __int64 v87; // [rsp+50h] [rbp-B8h] BYREF
  PFLT_PORT *ClientPort; // [rsp+58h] [rbp-B0h]
  PFLT_PORT *ClientPort_8[2]; // [rsp+60h] [rbp-A8h] BYREF
  PFLT_CONTEXT Context; // [rsp+70h] [rbp-98h] BYREF
  union _LARGE_INTEGER Timeout; // [rsp+78h] [rbp-90h] BYREF
  PEPROCESS Process; // [rsp+80h] [rbp-88h] BYREF
  ULONG v93; // [rsp+88h] [rbp-80h] BYREF
  union _LARGE_INTEGER v94; // [rsp+90h] [rbp-78h] BYREF
  union _LARGE_INTEGER PerformanceFrequency; // [rsp+98h] [rbp-70h] BYREF
  ULONG ReplyLength; // [rsp+A0h] [rbp-68h] BYREF
  void *Src[2]; // [rsp+A8h] [rbp-60h] BYREF
  int v98; // [rsp+B8h] [rbp-50h] BYREF
  _OWORD v99[2]; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v100; // [rsp+E0h] [rbp-28h]
  int v101; // [rsp+E8h] [rbp-20h]
  _OWORD v102[2]; // [rsp+F0h] [rbp-18h] BYREF
  __int64 v103; // [rsp+110h] [rbp+8h]
  int v104; // [rsp+118h] [rbp+10h]
  _OWORD ReplyBuffer[7]; // [rsp+128h] [rbp+20h] BYREF

  v3 = 0;
  Timeout.QuadPart = (LONGLONG)ProcessId;
  v87 = 0;
  v86 = 128;
  QuadPart = ProcessId;
  v93 = 0;
  v98 = 0;
  PerformanceFrequency.LowPart = 0;
  Process = 0;
  Context = 0;
  if ( !FullImageName || !FullImageName->Buffer || !FullImageName->Length )
    return;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_8ebd71c5d5f53801838f519f7d1f4ffb_Traceguids, FullImageName);
  v7 = 0;
  ProcessContextById = MpGetProcessContextById(QuadPart, &Process);
  v9 = Process;
  if ( ProcessContextById >= 0 )
  {
    v10 = (*((_DWORD *)Process + 14) & 0x8000000) != 0;
    _InterlockedCompareExchange64((volatile signed __int64 *)Process + 31, (signed __int64)ImageInfo->ImageBase, 0);
    if ( MpDlpIsEnabled(0, v9) && *((_DWORD *)v9 + 57) != 2 )
    {
      v11 = &dword_14002659C;
      while ( (*(v11 - 1) & *(_DWORD *)(MpData + 864)) == 0
           || *((_WORD *)v11 - 10) && !(unsigned __int8)MpSuffixUnicodeString(&asc_140026588[16 * v3], FullImageName)
           || *v11 && (*((_DWORD *)MpDlpData + 10) & *v11) == 0 )
      {
        ++v3;
        v11 += 8;
        if ( v3 >= 4 )
          goto LABEL_19;
      }
      *((_DWORD *)v9 + 57) = qword_140026580[4 * (int)v3];
    }
LABEL_19:
    if ( (*((_DWORD *)v9 + 14) & 0x8000) != 0
      && ((unsigned __int8)MpSuffixUnicodeString(L"XZ", FullImageName)
       || (unsigned __int8)MpSuffixUnicodeString(L"XZ", FullImageName)) )
    {
      *((_DWORD *)v9 + 72) |= 2u;
    }
    v12 = *((_DWORD *)v9 + 13);
    if ( (v12 & 8) != 0 && (*((_DWORD *)v9 + 14) & 0x4000) != 0
      || (v12 & 1) != 0 && (*((_DWORD *)v9 + 14) & 0x4000) == 0 )
    {
      goto LABEL_289;
    }
    v7 = v10;
    if ( (*((_DWORD *)v9 + 14) & 0x800) != 0 && *(_QWORD *)(MpData + 320) )
    {
      if ( (unsigned __int8)MpSuffixUnicodeString(L"<>", FullImageName) )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          WPP_SF_q(
            WPP_GLOBAL_Control->AttachedDevice,
            30,
            WPP_8ebd71c5d5f53801838f519f7d1f4ffb_Traceguids,
            ImageInfo->ImageBase);
        *((_DWORD *)v9 + 13) |= 0x200u;
        *((_QWORD *)v9 + 14) = ImageInfo->ImageBase;
      }
      else
      {
        v13 = *((_DWORD *)v9 + 13);
        if ( (v13 & 0x200) != 0 )
        {
          v94.QuadPart = 0;
          *((_DWORD *)v9 + 13) = v13 & 0xFFFFFDFF;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          {
            WPP_SF_q(
              WPP_GLOBAL_Control->AttachedDevice,
              31,
              WPP_8ebd71c5d5f53801838f519f7d1f4ffb_Traceguids,
              *((_QWORD *)v9 + 14));
          }
          if ( (int)MpAsyncCreateNotification(&v94, 40) >= 0 )
          {
            v14 = *(unsigned int *)(MpData + 2432);
            v15 = v94;
            memset(ReplyBuffer, 0, sizeof(ReplyBuffer));
            ReplyLength = 112;
            Process = (PEPROCESS)(-10000 * v14);
            *(_DWORD *)(v94.QuadPart + 8) = 128;
            *(_DWORD *)(v15.QuadPart + 16) = 15;
            *(_DWORD *)(v15.QuadPart + 24) = *((_DWORD *)v9 + 6);
            *(_DWORD *)(v15.QuadPart + 28) = (unsigned int)PsGetCurrentThreadId();
            *(_QWORD *)(v15.QuadPart + 32) = *((_QWORD *)v9 + 14);
            p_Process = (union _LARGE_INTEGER *)&Process;
            if ( !Process )
              p_Process = 0;
            v17 = FltSendMessage(
                    *(PFLT_FILTER *)(MpData + 16),
                    (PFLT_PORT *)(MpData + 320),
                    (PVOID)(v15.QuadPart - 24),
                    0x40u,
                    ReplyBuffer,
                    &ReplyLength,
                    p_Process);
            if ( v17 >= 0 )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
              {
                _mm_lfence();
                WPP_SF_Di(
                  WPP_GLOBAL_Control->AttachedDevice,
                  33,
                  WPP_8ebd71c5d5f53801838f519f7d1f4ffb_Traceguids,
                  (unsigned int)v17,
                  Process);
              }
              if ( v17 == 258 )
              {
                if ( *(_BYTE *)(MpData + 4024) )
                {
                  _InterlockedIncrement((volatile signed __int32 *)(MpData + 620));
                  if ( *(_DWORD *)(MpData + 620) > (unsigned int)dword_1400269D0 )
                  {
                    LOBYTE(v18) = 1;
                    MpSendAsyncPanicModeMessage(1, 0, *(unsigned __int8 *)(MpData + 208), v18, 0);
                  }
                }
              }
            }
            else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                   && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
            {
              _mm_lfence();
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                32,
                WPP_8ebd71c5d5f53801838f519f7d1f4ffb_Traceguids,
                (unsigned int)v17);
            }
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v15.QuadPart + 12), 0xFFFFFFFF) == 1 )
              ExFreePoolWithTag((PVOID)(v15.QuadPart - 24), 0x6D61504Du);
            v7 = v10;
          }
        }
      }
    }
    QuadPart = (HANDLE)Timeout.QuadPart;
  }
  if ( (*(_DWORD *)(MpData + 868) & 2) == 0 || !*(_QWORD *)(MpData + 416) && !*(_QWORD *)(MpData + 432) )
    goto LABEL_289;
  if ( FullImageName->Buffer )
  {
    Length = FullImageName->Length;
    if ( (_WORD)Length )
    {
      v93 = 128;
      v86 = Length + 130;
    }
  }
  v20 = 0;
  v43 = (ImageInfo->Properties & 0x400) == 0;
  *(_OWORD *)ClientPort_8 = 0;
  Timeout.QuadPart = 0;
  if ( !v43 && *(_QWORD *)&ImageInfo[-1].ImageSectionNumber >= 0x38u )
  {
    v21 = *(struct _FILE_OBJECT **)&ImageInfo[1].Properties;
    Timeout.QuadPart = (LONGLONG)v21;
    StreamContextFromFileObject = MpGetStreamContextFromFileObject(v21, &Context);
    if ( StreamContextFromFileObject < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      {
        _mm_lfence();
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          34,
          WPP_8ebd71c5d5f53801838f519f7d1f4ffb_Traceguids,
          KeGetCurrentThread(),
          StreamContextFromFileObject);
      }
      v85 = 1;
LABEL_87:
      if ( v9 && (*((_DWORD *)v9 + 14) & 0x200) != 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          WPP_SF_Z(
            WPP_GLOBAL_Control->AttachedDevice,
            36,
            WPP_8ebd71c5d5f53801838f519f7d1f4ffb_Traceguids,
            FullImageName);
        v25 = 0;
        v85 = 0;
        goto LABEL_94;
      }
LABEL_93:
      v25 = 1;
      goto LABEL_94;
    }
    v23 = *((_QWORD *)Context + 1);
    v24 = (DWORD *)((char *)Context + 32);
    if ( Context != (PFLT_CONTEXT)-32LL && v23 )
    {
      if ( *v24 == 5 && (*(_DWORD *)(MpData + 868) & 0x8000) == 0 )
      {
        PerformanceFrequency.LowPart = 5;
LABEL_77:
        if ( (*((_DWORD *)Context + 12) & 0x8000) != 0 || v7 )
        {
          v20 = (*((_DWORD *)Context + 12) & 0x8000) != 0;
          _mm_lfence();
          MpGetPriorityInfo(0, v21, ClientPort_8);
        }
        goto LABEL_80;
      }
      if ( *((_DWORD *)Context + 9) == *(_DWORD *)(v23 + 144) )
      {
        PerformanceFrequency.LowPart = *v24;
        goto LABEL_77;
      }
    }
    PerformanceFrequency.LowPart = 0;
    goto LABEL_77;
  }
LABEL_80:
  v85 = 1;
  if ( PerformanceFrequency.LowPart != 2 )
    goto LABEL_87;
  if ( !v9 || (*((_DWORD *)v9 + 14) & 0x100) == 0 )
    goto LABEL_93;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 35, WPP_8ebd71c5d5f53801838f519f7d1f4ffb_Traceguids, FullImageName);
  v25 = 0;
  v85 = 0;
LABEL_94:
  if ( v20 || v7 || v25 )
  {
    v26 = MpAsyncCreateNotification(&v87, v86);
    if ( v26 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        _mm_lfence();
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          40,
          WPP_8ebd71c5d5f53801838f519f7d1f4ffb_Traceguids,
          KeGetCurrentThread(),
          v26);
      }
      goto LABEL_289;
    }
    v27 = v87;
    v28 = v93;
    if ( FullImageName->Length )
    {
      memmove((void *)(v87 + v93), FullImageName->Buffer, FullImageName->Length);
      *(_WORD *)(v27 + 2 * (((unsigned __int64)FullImageName->Length + 128) >> 1)) = 0;
    }
    *(_DWORD *)(v27 + 60) = FullImageName->Length + 2;
    *(_DWORD *)(v27 + 64) = v28;
    TimeQuadPart = 0;
    *(_DWORD *)(v27 + 36) = (_DWORD)QuadPart;
    if ( QuadPart )
    {
      Process = 0;
      if ( PsLookupProcessByProcessId(QuadPart, &Process) >= 0 )
      {
        TimeQuadPart = PsGetProcessCreateTimeQuadPart(Process);
        ObfDereferenceObject(Process);
      }
    }
    v30 = MpFileTimeToUlong64(TimeQuadPart);
    v31 = v86;
    *(_QWORD *)(v27 + 40) = v30;
    *(_DWORD *)(v27 + 8) = v86;
    *(_DWORD *)(v27 + 16) = 3;
    v34 = MpQuerySessionId(v33, v32, &v98);
    if ( v34 < 0
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      _mm_lfence();
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        37,
        WPP_8ebd71c5d5f53801838f519f7d1f4ffb_Traceguids,
        KeGetCurrentThread(),
        v34);
    }
    *(_DWORD *)(v27 + 68) = v98;
    *(_WORD *)(v27 + 48) = 0;
    *(_DWORD *)(v27 + 24) = 0;
    *(_QWORD *)(v27 + 28) = MpFileTimeToUlong64(0);
    if ( v9 )
      v36 = *((_DWORD *)v9 + 60);
    else
      v36 = (int)v35;
    *(_DWORD *)(v27 + 116) = v36;
    if ( v9 )
      v37 = *((_DWORD *)v9 + 14);
    else
      v37 = (int)v35;
    *(_DWORD *)(v27 + 120) = v37;
    if ( v9 )
      v38 = *((_DWORD *)v9 + 15);
    else
      v38 = (int)v35;
    *(_DWORD *)(v27 + 124) = v38;
    if ( !v20 && !v7 )
      goto LABEL_275;
    if ( !FullImageName->Length )
      goto LABEL_275;
    if ( FullImageName->Buffer == v35 )
      goto LABEL_275;
    v39 = *(_DWORD *)(v27 + 36);
    v87 = *(_QWORD *)(v27 + 40);
    *(_OWORD *)Src = 0;
    if ( (int)MpNormalizeNameUnsafe((PFILE_OBJECT)Timeout.QuadPart, FullImageName, (PUNICODE_STRING)Src) < 0 )
      goto LABEL_275;
    v40 = *(_DWORD *)(MpData + 3612);
    if ( v7 )
    {
      v41 = (volatile signed __int32 *)((char *)v9 + 56);
      if ( !v40 )
      {
        v42 = WPP_GLOBAL_Control;
        v43 = WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control;
        goto LABEL_190;
      }
      if ( v9 != (PEPROCESS)-56LL )
      {
        ClientPort = (PFLT_PORT *)(MpData + 320);
        if ( MpData == -320 )
        {
          v44 = WPP_GLOBAL_Control;
          v45 = WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control;
          goto LABEL_197;
        }
        v46 = LOWORD(Src[0]) + 10;
        v47 = LOWORD(Src[0]) + 58;
        PoolWithTag = MpAllocatePoolWithTag(1, v47, 1836273741);
        v49 = (ULONG *)PoolWithTag;
        if ( !PoolWithTag )
        {
          v50 = -1073741670;
LABEL_267:
          if ( Src[1] )
          {
            ExFreePoolWithTag(Src[1], 0x6E66504Du);
            Src[1] = 0;
          }
          LODWORD(Src[0]) = 0;
          if ( v50 >= 0 )
          {
            v31 = v86;
          }
          else
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
            {
              _mm_lfence();
              WPP_SF_qD(
                WPP_GLOBAL_Control->AttachedDevice,
                38,
                WPP_8ebd71c5d5f53801838f519f7d1f4ffb_Traceguids,
                KeGetCurrentThread(),
                v50);
            }
            v31 = v86;
          }
LABEL_275:
          if ( v85 )
          {
            _mm_lfence();
            v84 = MpAsyncSendNotification(v27, v31, 0, -1, (__int64)v9);
            if ( v84 < 0
              && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
            {
              _mm_lfence();
              WPP_SF_qD(
                WPP_GLOBAL_Control->AttachedDevice,
                39,
                WPP_8ebd71c5d5f53801838f519f7d1f4ffb_Traceguids,
                KeGetCurrentThread(),
                v84);
            }
          }
          if ( v27 )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v27 + 12), 0xFFFFFFFF) == 1 )
              ExFreePoolWithTag((PVOID)(v27 - 24), 0x6D61504Du);
          }
          else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                 && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
          {
            WPP_SF_q(
              WPP_GLOBAL_Control->AttachedDevice,
              28,
              WPP_5c114a40c3de3145ebb792b3b9433cba_Traceguids,
              KeGetCurrentThread());
          }
          goto LABEL_289;
        }
        v51 = *(_OWORD *)ClientPort_8;
        *(_DWORD *)(PoolWithTag + 4) = v47;
        v52 = (_DWORD *)(PoolWithTag + 48);
        *(_DWORD *)PoolWithTag = 197029;
        *(_DWORD *)(PoolWithTag + 24) = 5;
        *(_OWORD *)(PoolWithTag + 8) = v51;
        *(_DWORD *)(PoolWithTag + 28) = v39;
        *(_QWORD *)(PoolWithTag + 32) = v87;
        *(_DWORD *)(PoolWithTag + 40) = v46;
        if ( PoolWithTag != -48 && v46 >= 8 )
        {
          _mm_lfence();
          *v52 = LOWORD(Src[0]) + 2;
          v53 = LOWORD(Src[0]);
          if ( !memcpy_s((void *)(PoolWithTag + 56), v46 - 8, Src[1], LOWORD(Src[0])) )
            *(_WORD *)((char *)v52 + v53 + 8) = 0;
        }
        Timeout.QuadPart = 0;
        v54 = *(union _LARGE_INTEGER *)(MpData + 3616);
        if ( v54.QuadPart )
          v54.QuadPart = -v54.QuadPart;
        Timeout = v54;
        if ( !_InterlockedCompareExchange((volatile signed __int32 *)(MpData + 444), 0, 0) )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_08fcbcbc57df34e6eaa3c5bf09140d00_Traceguids);
          }
          v55 = -1073741823;
          goto LABEL_146;
        }
        v56 = FltCancellableWaitForSingleObject((PVOID)(MpData + 512), &Timeout, 0);
        v55 = v56;
        if ( v56 == 258 )
        {
          v55 = -1073741643;
LABEL_143:
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          {
            WPP_SF_Di(
              WPP_GLOBAL_Control->AttachedDevice,
              12,
              WPP_08fcbcbc57df34e6eaa3c5bf09140d00_Traceguids,
              v55,
              Timeout.QuadPart / 10000000);
          }
LABEL_146:
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          {
            WPP_SF_qD(
              WPP_GLOBAL_Control->AttachedDevice,
              17,
              WPP_08fcbcbc57df34e6eaa3c5bf09140d00_Traceguids,
              KeGetCurrentThread(),
              v55);
          }
          _InterlockedIncrement((volatile signed __int32 *)(MpData + 3488));
          _InterlockedExchange((volatile __int32 *)(MpData + 3524), -1073741670);
          ExFreePoolWithTag(v49, 0x6D73504Du);
          if ( v55 == -1073741643 )
          {
            if ( *(_BYTE *)(MpData + 4024) )
            {
              _InterlockedIncrement((volatile signed __int32 *)(MpData + 616));
              if ( *(_DWORD *)(MpData + 616) > (unsigned int)dword_1400269D0 )
              {
LABEL_152:
                LOBYTE(v57) = 1;
                MpSendAsyncPanicModeMessage(4, 0, *(unsigned __int8 *)(MpData + 208), v57, 0);
                v50 = -1073741643;
                goto LABEL_267;
              }
            }
          }
LABEL_226:
          v50 = v55;
          goto LABEL_267;
        }
        if ( v56 )
          goto LABEL_143;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        {
          AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
          StateSemaphore = KeReadStateSemaphore((PRKSEMAPHORE)(MpData + 512));
          WPP_SF_d(AttachedDevice, 13, WPP_08fcbcbc57df34e6eaa3c5bf09140d00_Traceguids, StateSemaphore);
        }
        Process = 0;
        ReplyLength = 44;
        v100 = 0;
        memset(v99, 0, sizeof(v99));
        v101 = 0;
        PerformanceCounter = KeQueryPerformanceCounter((PLARGE_INTEGER)&Process);
        v50 = FltSendMessage(*(PFLT_FILTER *)(MpData + 16), ClientPort, v49, v49[1], v99, &ReplyLength, &Timeout);
        if ( Process )
        {
          v61 = 1000 * (*(_QWORD *)&KeQueryPerformanceCounter(0) - PerformanceCounter.QuadPart) / (__int64)Process;
          if ( *(int *)(MpData + 3376) < 0 )
          {
            _InterlockedExchange64((volatile __int64 *)(MpData + 3368), 0);
            _InterlockedExchange((volatile __int32 *)(MpData + 3376), 0);
          }
          _InterlockedAdd64((volatile signed __int64 *)(MpData + 3368), v61);
          _InterlockedIncrement((volatile signed __int32 *)(MpData + 3376));
        }
        if ( v50 == 258 )
          v50 = -1073741643;
        KeReleaseSemaphore((PRKSEMAPHORE)(MpData + 512), 0, 1, 0);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        {
          v62 = WPP_GLOBAL_Control->AttachedDevice;
          v63 = KeReadStateSemaphore((PRKSEMAPHORE)(MpData + 512));
          WPP_SF_d(v62, 14, WPP_08fcbcbc57df34e6eaa3c5bf09140d00_Traceguids, v63);
        }
        ExFreePoolWithTag(v49, 0x6D73504Du);
        if ( v50 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          {
            WPP_SF_qDi(
              WPP_GLOBAL_Control->AttachedDevice,
              Timeout.QuadPart / 10000000,
              v64,
              KeGetCurrentThread(),
              v50,
              Timeout.QuadPart / 10000000);
          }
          if ( v50 == -1073741643 )
          {
            _InterlockedIncrement((volatile signed __int32 *)(MpData + 3560));
          }
          else
          {
            _InterlockedIncrement((volatile signed __int32 *)(MpData + 3488));
            _InterlockedExchange((volatile __int32 *)(MpData + 3524), v50);
          }
          goto LABEL_267;
        }
        if ( DWORD2(v99[0]) != 5 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          {
            WPP_SF_qDD(
              WPP_GLOBAL_Control->AttachedDevice,
              19,
              WPP_08fcbcbc57df34e6eaa3c5bf09140d00_Traceguids,
              KeGetCurrentThread(),
              DWORD2(v99[0]),
              5);
          }
          _InterlockedIncrement((volatile signed __int32 *)(MpData + 3596));
          v50 = -1073740764;
          goto LABEL_267;
        }
        _InterlockedIncrement((volatile signed __int32 *)(MpData + 3452));
        if ( (BYTE12(v99[0]) & 2) != 0 )
        {
          switch ( DWORD2(v99[0]) )
          {
            case 1:
              _InterlockedAnd(v41, 0xFFFF7FFF);
              break;
            case 2:
              _InterlockedAnd(v41, 0xFFDFFFFF);
              break;
            case 3:
              _InterlockedAnd(v41, 0xFFBFFFFF);
              break;
            case 5:
              _InterlockedAnd(v41, 0xF7FFFFFF);
              break;
            case 6:
              _InterlockedAnd(v41, 0xEFFFFFFF);
              break;
            case 7:
              _InterlockedAnd(v41, 0xDFFFFFFF);
              break;
            case 8:
              _InterlockedAnd(v41, 0xFFFFFFFB);
              break;
            default:
              break;
          }
        }
        if ( (BYTE12(v99[0]) & 1) == 0 )
        {
LABEL_265:
          v50 = 0;
          goto LABEL_267;
        }
        v65 = WPP_GLOBAL_Control;
        v66 = WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control;
LABEL_262:
        if ( !v66 && (HIDWORD(v65->Timer) & 2) != 0 )
          WPP_SF_q(
            WPP_GLOBAL_Control->AttachedDevice,
            20,
            WPP_08fcbcbc57df34e6eaa3c5bf09140d00_Traceguids,
            KeGetCurrentThread());
        goto LABEL_265;
      }
    }
    else
    {
      v67 = (volatile signed __int32 *)((char *)Context + 48);
      if ( !v40 )
      {
        v42 = WPP_GLOBAL_Control;
        v43 = WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control;
LABEL_190:
        if ( !v43 && (HIDWORD(v42->Timer) & 2) != 0 )
          WPP_SF_qD(
            WPP_GLOBAL_Control->AttachedDevice,
            15,
            WPP_08fcbcbc57df34e6eaa3c5bf09140d00_Traceguids,
            KeGetCurrentThread(),
            0);
        v50 = 0;
        goto LABEL_267;
      }
      if ( Context != (PFLT_CONTEXT)-48LL )
      {
        ClientPort = (PFLT_PORT *)(MpData + 320);
        if ( MpData == -320 )
        {
          v44 = WPP_GLOBAL_Control;
          v45 = WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control;
LABEL_197:
          if ( !v45 && (HIDWORD(v44->Timer) & 1) != 0 )
            WPP_SF_q(
              WPP_GLOBAL_Control->AttachedDevice,
              16,
              WPP_08fcbcbc57df34e6eaa3c5bf09140d00_Traceguids,
              KeGetCurrentThread());
          v50 = -1073741823;
          goto LABEL_267;
        }
        v68 = LOWORD(Src[0]) + 10;
        v69 = LOWORD(Src[0]) + 58;
        v70 = MpAllocatePoolWithTag(1, v69, 1836273741);
        v71 = (ULONG *)v70;
        if ( !v70 )
        {
          v50 = -1073741670;
          goto LABEL_267;
        }
        v72 = *(_OWORD *)ClientPort_8;
        *(_DWORD *)(v70 + 4) = v69;
        v73 = (_DWORD *)(v70 + 48);
        *(_DWORD *)v70 = 197029;
        *(_DWORD *)(v70 + 24) = 1;
        *(_OWORD *)(v70 + 8) = v72;
        *(_DWORD *)(v70 + 28) = v39;
        *(_QWORD *)(v70 + 32) = v87;
        *(_DWORD *)(v70 + 40) = v68;
        if ( v70 != -48 && v68 >= 8 )
        {
          _mm_lfence();
          *v73 = LOWORD(Src[0]) + 2;
          v74 = LOWORD(Src[0]);
          if ( !memcpy_s((void *)(v70 + 56), v68 - 8, Src[1], LOWORD(Src[0])) )
            *(_WORD *)((char *)v73 + v74 + 8) = 0;
        }
        v94.QuadPart = 0;
        v75 = *(union _LARGE_INTEGER *)(MpData + 3616);
        if ( v75.QuadPart )
          v75.QuadPart = -v75.QuadPart;
        v94 = v75;
        if ( _InterlockedCompareExchange((volatile signed __int32 *)(MpData + 444), 0, 0) )
        {
          v76 = FltCancellableWaitForSingleObject((PVOID)(MpData + 512), &v94, 0);
          v55 = v76;
          if ( v76 == 258 )
          {
            v55 = -1073741643;
          }
          else if ( !v76 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
            {
              v77 = WPP_GLOBAL_Control->AttachedDevice;
              v78 = KeReadStateSemaphore((PRKSEMAPHORE)(MpData + 512));
              WPP_SF_d(v77, 13, WPP_08fcbcbc57df34e6eaa3c5bf09140d00_Traceguids, v78);
            }
            PerformanceFrequency.QuadPart = 0;
            v93 = 44;
            v103 = 0;
            memset(v102, 0, sizeof(v102));
            v104 = 0;
            v79 = KeQueryPerformanceCounter(&PerformanceFrequency);
            v50 = FltSendMessage(*(PFLT_FILTER *)(MpData + 16), ClientPort, v71, v71[1], v102, &v93, &v94);
            if ( PerformanceFrequency.QuadPart )
            {
              v80 = 1000 * (*(_QWORD *)&KeQueryPerformanceCounter(0) - v79.QuadPart) / PerformanceFrequency.QuadPart;
              if ( *(int *)(MpData + 3312) < 0 )
              {
                _InterlockedExchange64((volatile __int64 *)(MpData + 3304), 0);
                _InterlockedExchange((volatile __int32 *)(MpData + 3312), 0);
              }
              _InterlockedAdd64((volatile signed __int64 *)(MpData + 3304), v80);
              _InterlockedIncrement((volatile signed __int32 *)(MpData + 3312));
            }
            if ( v50 == 258 )
              v50 = -1073741643;
            KeReleaseSemaphore((PRKSEMAPHORE)(MpData + 512), 0, 1, 0);
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
            {
              v81 = WPP_GLOBAL_Control->AttachedDevice;
              v82 = KeReadStateSemaphore((PRKSEMAPHORE)(MpData + 512));
              WPP_SF_d(v81, 14, WPP_08fcbcbc57df34e6eaa3c5bf09140d00_Traceguids, v82);
            }
            ExFreePoolWithTag(v71, 0x6D73504Du);
            if ( v50 )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
              {
                WPP_SF_qDi(
                  WPP_GLOBAL_Control->AttachedDevice,
                  v94.QuadPart / 10000000,
                  v83,
                  KeGetCurrentThread(),
                  v50,
                  v94.QuadPart / 10000000);
              }
              if ( v50 == -1073741643 )
              {
                _InterlockedIncrement((volatile signed __int32 *)(MpData + 3544));
              }
              else
              {
                _InterlockedIncrement((volatile signed __int32 *)(MpData + 3472));
                _InterlockedExchange((volatile __int32 *)(MpData + 3508), v50);
              }
              goto LABEL_267;
            }
            if ( DWORD2(v102[0]) != 1 )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
              {
                WPP_SF_qDD(
                  WPP_GLOBAL_Control->AttachedDevice,
                  19,
                  WPP_08fcbcbc57df34e6eaa3c5bf09140d00_Traceguids,
                  KeGetCurrentThread(),
                  DWORD2(v102[0]),
                  1);
              }
              _InterlockedIncrement((volatile signed __int32 *)(MpData + 3580));
              v50 = -1073740764;
              goto LABEL_267;
            }
            _InterlockedIncrement((volatile signed __int32 *)(MpData + 3436));
            if ( (BYTE12(v102[0]) & 2) != 0 )
            {
              switch ( DWORD2(v102[0]) )
              {
                case 1:
                  _InterlockedAnd(v67, 0xFFFF7FFF);
                  break;
                case 2:
                  _InterlockedAnd(v67, 0xFFDFFFFF);
                  break;
                case 3:
                  _InterlockedAnd(v67, 0xFFBFFFFF);
                  break;
                case 5:
                  _InterlockedAnd(v67, 0xF7FFFFFF);
                  break;
                case 6:
                  _InterlockedAnd(v67, 0xEFFFFFFF);
                  break;
                case 7:
                  _InterlockedAnd(v67, 0xDFFFFFFF);
                  break;
                case 8:
                  _InterlockedAnd(v67, 0xFFFFFFFB);
                  break;
                default:
                  break;
              }
            }
            if ( (BYTE12(v102[0]) & 1) == 0 )
              goto LABEL_265;
            v65 = WPP_GLOBAL_Control;
            v66 = WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control;
            goto LABEL_262;
          }
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          {
            WPP_SF_Di(
              WPP_GLOBAL_Control->AttachedDevice,
              12,
              WPP_08fcbcbc57df34e6eaa3c5bf09140d00_Traceguids,
              v55,
              v94.QuadPart / 10000000);
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_08fcbcbc57df34e6eaa3c5bf09140d00_Traceguids);
          }
          v55 = -1073741823;
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          WPP_SF_qD(
            WPP_GLOBAL_Control->AttachedDevice,
            17,
            WPP_08fcbcbc57df34e6eaa3c5bf09140d00_Traceguids,
            KeGetCurrentThread(),
            v55);
        _InterlockedIncrement((volatile signed __int32 *)(MpData + 3472));
        _InterlockedExchange((volatile __int32 *)(MpData + 3508), -1073741670);
        ExFreePoolWithTag(v71, 0x6D73504Du);
        if ( v55 == -1073741643 )
        {
          if ( *(_BYTE *)(MpData + 4024) )
          {
            _InterlockedIncrement((volatile signed __int32 *)(MpData + 616));
            if ( *(_DWORD *)(MpData + 616) > (unsigned int)dword_1400269D0 )
              goto LABEL_152;
          }
        }
        goto LABEL_226;
      }
    }
    v50 = -1073741811;
    goto LABEL_267;
  }
LABEL_289:
  if ( Context )
    FltReleaseContext(Context);
  if ( v9 )
    MpReleaseProcessContext(v9);
}

```

## disassembly

```asm
0x140082380  mov     r11, rsp
0x140082383  push    rbp
0x140082384  push    rsi
0x140082385  push    rdi
0x140082386  push    r12
0x140082388  push    r15
0x14008238a  lea     rbp, [r11-0D8h]
0x140082391  sub     rsp, 1B0h
0x140082398  mov     rax, cs:__security_cookie
0x14008239f  xor     rax, rsp
0x1400823a2  mov     [rbp+0D0h+var_40], rax
0x1400823a9  xor     edi, edi
0x1400823ab  mov     qword ptr [rsp+1D0h+Timeout], rdx
0x1400823b0  mov     [rsp+1D0h+var_188], rdi
0x1400823b5  mov     r12, r8
0x1400823b8  mov     dword ptr [rsp+1D0h+var_190+4], 80h
0x1400823c0  mov     r15, rdx
0x1400823c3  mov     [rbp+0D0h+var_150], edi
0x1400823c6  mov     rsi, rcx
0x1400823c9  mov     [rbp+0D0h+var_120], edi
0x1400823cc  mov     dword ptr [rbp+0D0h+PerformanceFrequency], edi
0x1400823cf  mov     [rsp+1D0h+Process], rdi
0x1400823d4  mov     [rsp+1D0h+Context], rdi
0x1400823d9  test    rcx, rcx
0x1400823dc  jz      loc_140083B32
0x1400823e2  cmp     [rcx+8], rdi
0x1400823e6  jz      loc_140083B32
0x1400823ec  cmp     [rcx], di
0x1400823ef  jz      loc_140083B32
0x1400823f5  mov     [r11+20h], rbx
0x1400823f9  mov     [r11-30h], r13
0x1400823fd  mov     [r11-38h], r14
0x140082401  mov     rcx, cs:WPP_GLOBAL_Control
0x140082408  lea     rax, WPP_GLOBAL_Control
0x14008240f  cmp     rcx, rax
0x140082412  jz      short loc_140082433
0x140082414  mov     eax, [rcx+2Ch]
0x140082417  test    al, 4
0x140082419  jz      short loc_140082433
0x14008241b  mov     rcx, [rcx+18h]
0x14008241f  lea     r8, WPP_8ebd71c5d5f53801838f519f7d1f4ffb_Traceguids
0x140082426  mov     edx, 1Dh
0x14008242b  mov     r9, rsi
0x14008242e  call    WPP_SF_Z
0x140082433  lea     rdx, [rsp+1D0h+Process]
0x140082438  mov     rcx, r15
0x14008243b  xor     bl, bl
0x14008243d  call    MpGetProcessContextById
0x140082442  mov     r13, [rsp+1D0h+Process]
0x140082447  mov     r14d, 0FFFFFFFFh
0x14008244d  test    eax, eax
0x14008244f  js      loc_140082839
0x140082455  mov     r15d, [r13+38h]
0x140082459  mov     rcx, [r12+8]
0x14008245e  shr     r15d, 1Bh
0x140082462  and     r15b, 1
0x140082466  xor     eax, eax
0x140082468  lock cmpxchg [r13+0F8h], rcx
0x140082471  mov     rdx, r13
0x140082474  xor     ecx, ecx
0x140082476  call    MpDlpIsEnabled
0x14008247b  test    al, al
0x14008247d  jz      loc_14008251D
0x140082483  cmp     dword ptr [r13+0E4h], 2
0x14008248b  jz      loc_14008251D
0x140082491  lea     rbx, dword_14002659C
0x140082498  lea     rdx, asc_140026588; "<>"
0x14008249f  nop
0x1400824a0  mov     rax, cs:MpData
0x1400824a7  mov     ecx, [rbx-4]
0x1400824aa  test    [rax+360h], ecx
0x1400824b0  jz      short loc_1400824EE
0x1400824b2  cmp     word ptr [rbx-14h], 0
0x1400824b7  movsxd  r14, edi
0x1400824ba  jz      short loc_1400824D2
0x1400824bc  mov     rcx, r14
0x1400824bf  shl     rcx, 5
0x1400824c3  add     rcx, rdx
0x1400824c6  mov     rdx, rsi
0x1400824c9  call    MpSuffixUnicodeString
0x1400824ce  test    al, al
0x1400824d0  jz      short loc_1400824E7
0x1400824d2  cmp     dword ptr [rbx], 0
0x1400824d5  jz      short loc_1400824FB
0x1400824d7  mov     rax, cs:MpDlpData
0x1400824de  mov     edx, [rbx]
0x1400824e0  mov     ecx, [rax+28h]
0x1400824e3  test    edx, ecx
0x1400824e5  jnz     short loc_1400824FB
0x1400824e7  lea     rdx, asc_140026588; "<>"
0x1400824ee  inc     edi
0x1400824f0  add     rbx, 20h ; ' '
0x1400824f4  cmp     edi, 4
0x1400824f7  jb      short loc_1400824A0
0x1400824f9  jmp     short loc_140082515
0x1400824fb  shl     r14, 5
0x1400824ff  lea     rax, cs:140000000h
0x140082506  mov     eax, [r14+rax+26580h]
0x14008250e  mov     [r13+0E4h], eax
0x140082515  mov     r14d, 0FFFFFFFFh
0x14008251b  xor     edi, edi
0x14008251d  test    dword ptr [r13+38h], 8000h
0x140082525  jz      short loc_140082555
0x140082527  mov     rdx, rsi
0x14008252a  lea     rcx, s_MicrosoftUevAppAgentModule; "XZ"
0x140082531  call    MpSuffixUnicodeString
0x140082536  test    al, al
0x140082538  jnz     short loc_14008254D
0x14008253a  mov     rdx, rsi
0x14008253d  lea     rcx, s_MicrosoftUevAppAgentModuleX86; "XZ"
0x140082544  call    MpSuffixUnicodeString
0x140082549  test    al, al
0x14008254b  jz      short loc_140082555
0x14008254d  or      dword ptr [r13+120h], 2
0x140082555  mov     ecx, [r13+34h]
0x140082559  test    cl, 8
0x14008255c  jz      short loc_14008256C
0x14008255e  test    dword ptr [r13+38h], 4000h
0x140082566  jnz     loc_140083AF7
0x14008256c  test    cl, 1
0x14008256f  jz      short loc_14008257F
0x140082571  test    dword ptr [r13+38h], 4000h
0x140082579  jz      loc_140083AF7
0x14008257f  test    dword ptr [r13+38h], 800h
0x140082587  movzx   ebx, r15b
0x14008258b  jz      loc_140082834
0x140082591  mov     rax, cs:MpData
0x140082598  cmp     qword ptr [rax+140h], 0
0x1400825a0  jz      loc_140082834
0x1400825a6  mov     rdx, rsi
0x1400825a9  lea     rcx, Wow64cpuModulePath; "<>"
0x1400825b0  call    MpSuffixUnicodeString
0x1400825b5  test    al, al
0x1400825b7  jz      short loc_140082603
0x1400825b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400825c0  lea     rax, WPP_GLOBAL_Control
0x1400825c7  cmp     rcx, rax
0x1400825ca  jz      short loc_1400825ED
0x1400825cc  mov     eax, [rcx+2Ch]
0x1400825cf  test    al, 4
0x1400825d1  jz      short loc_1400825ED
0x1400825d3  mov     r9, [r12+8]
0x1400825d8  lea     r8, WPP_8ebd71c5d5f53801838f519f7d1f4ffb_Traceguids
0x1400825df  mov     rcx, [rcx+18h]
0x1400825e3  mov     edx, 1Eh
0x1400825e8  call    WPP_SF_q
0x1400825ed  or      dword ptr [r13+34h], 200h
0x1400825f5  mov     rax, [r12+8]
0x1400825fa  mov     [r13+70h], rax
0x1400825fe  jmp     loc_140082834
0x140082603  mov     eax, [r13+34h]
0x140082607  bt      eax, 9
0x14008260b  jnb     loc_140082834
0x140082611  btr     eax, 9
0x140082615  mov     qword ptr [rbp+0D0h+var_148], rdi
0x140082619  mov     [r13+34h], eax
0x14008261d  mov     rcx, cs:WPP_GLOBAL_Control
0x140082624  lea     rax, WPP_GLOBAL_Control
0x14008262b  cmp     rcx, rax
0x14008262e  jz      short loc_140082650
0x140082630  mov     eax, [rcx+2Ch]
0x140082633  test    al, 4
0x140082635  jz      short loc_140082650
0x140082637  mov     r9, [r13+70h]
0x14008263b  lea     r8, WPP_8ebd71c5d5f53801838f519f7d1f4ffb_Traceguids
0x140082642  mov     rcx, [rcx+18h]
0x140082646  mov     edx, 1Fh
0x14008264b  call    WPP_SF_q
0x140082650  mov     edx, 28h ; '('
0x140082655  lea     rcx, [rbp+0D0h+var_148]
0x140082659  call    MpAsyncCreateNotification
0x14008265e  test    eax, eax
0x140082660  js      loc_140082834
0x140082666  mov     rax, cs:MpData
0x14008266d  xorps   xmm0, xmm0
0x140082670  mov     ecx, [rax+980h]
0x140082676  mov     rbx, qword ptr [rbp+0D0h+var_148]
0x14008267a  movups  [rbp+0D0h+var_B0], xmm0
0x14008267e  mov     [rbp+0D0h+var_138], 70h ; 'p'
0x140082685  movups  [rbp+0D0h+var_A0], xmm0
0x140082689  movups  [rbp+0D0h+var_90], xmm0
0x14008268d  movups  [rbp+0D0h+var_80], xmm0
0x140082691  movups  [rbp+0D0h+var_70], xmm0
0x140082695  movups  [rbp+0D0h+var_60], xmm0
0x140082699  movups  [rbp+0D0h+var_50], xmm0
0x1400826a0  imul    rcx, 0FFFFFFFFFFFFD8F0h
0x1400826a7  mov     [rsp+1D0h+Process], rcx
0x1400826ac  mov     dword ptr [rbx+8], 80h
0x1400826b3  mov     dword ptr [rbx+10h], 0Fh
0x1400826ba  mov     eax, [r13+18h]
0x1400826be  mov     [rbx+18h], eax
0x1400826c1  call    cs:__imp_PsGetCurrentThreadId
0x1400826c8  nop     dword ptr [rax+rax+00h]
0x1400826cd  mov     [rbx+1Ch], eax
0x1400826d0  lea     r8, [rbx-18h]; SenderBuffer
0x1400826d4  mov     rax, [r13+70h]
0x1400826d8  mov     r9d, 40h ; '@'; SenderBufferLength
0x1400826de  mov     [rbx+20h], rax
0x1400826e2  lea     rax, [rsp+1D0h+Process]
0x1400826e7  mov     rcx, cs:MpData
0x1400826ee  cmp     [rsp+1D0h+Process], 0
0x1400826f4  cmovz   rax, rdi
0x1400826f8  mov     [rsp+30h], rax; Timeout
0x1400826fd  lea     rdx, [rcx+140h]; ClientPort
0x140082704  mov     rcx, [rcx+10h]; Filter
0x140082708  lea     rax, [rbp+0D0h+var_138]
0x14008270c  mov     [rsp+1D0h+ReplyLength], rax; ReplyLength
0x140082711  lea     rax, [rbp+0D0h+var_B0]
0x140082715  mov     [rsp+1D0h+ReplyBuffer], rax; ReplyBuffer
0x14008271a  call    cs:__imp_FltSendMessage
0x140082721  nop     dword ptr [rax+rax+00h]
0x140082726  mov     edi, eax
0x140082728  test    eax, eax
0x14008272a  jns     short loc_140082776
0x14008272c  mov     rcx, cs:WPP_GLOBAL_Control
0x140082733  lea     rax, WPP_GLOBAL_Control
0x14008273a  cmp     rcx, rax
0x14008273d  jz      loc_14008280E
0x140082743  mov     ecx, [rcx+2Ch]
0x140082746  test    cl, 1
0x140082749  jz      loc_14008280E
0x14008274f  lfence
0x140082752  mov     rcx, cs:WPP_GLOBAL_Control
0x140082759  lea     r8, WPP_8ebd71c5d5f53801838f519f7d1f4ffb_Traceguids
0x140082760  mov     edx, 20h ; ' '
0x140082765  mov     r9d, edi
0x140082768  mov     rcx, [rcx+18h]
0x14008276c  call    WPP_SF_d
0x140082771  jmp     loc_14008280E
0x140082776  mov     rax, cs:WPP_GLOBAL_Control
0x14008277d  lea     rdx, WPP_GLOBAL_Control
0x140082784  cmp     rax, rdx
0x140082787  jz      short loc_1400827BC
0x140082789  mov     eax, [rax+2Ch]
0x14008278c  test    al, 4
0x14008278e  jz      short loc_1400827BC
0x140082790  lfence
0x140082793  mov     rcx, cs:WPP_GLOBAL_Control
0x14008279a  lea     r8, WPP_8ebd71c5d5f53801838f519f7d1f4ffb_Traceguids
0x1400827a1  mov     rax, [rsp+1D0h+Process]
0x1400827a6  mov     edx, 21h ; '!'
0x1400827ab  mov     r9d, edi
0x1400827ae  mov     [rsp+1D0h+ReplyBuffer], rax
0x1400827b3  mov     rcx, [rcx+18h]
0x1400827b7  call    WPP_SF_Di
0x1400827bc  cmp     edi, 102h
0x1400827c2  jnz     short loc_14008280E
0x1400827c4  mov     rax, cs:MpData
0x1400827cb  cmp     byte ptr [rax+0FB8h], 0
0x1400827d2  jz      short loc_14008280E
0x1400827d4  lock inc dword ptr [rax+26Ch]
0x1400827db  mov     r8, cs:MpData
0x1400827e2  mov     eax, cs:dword_1400269D0
0x1400827e8  cmp     [r8+26Ch], eax
0x1400827ef  jbe     short loc_14008280E
0x1400827f1  movzx   r8d, byte ptr [r8+0D0h]
0x1400827f9  xor     eax, eax
0x1400827fb  mov     r9b, 1
0x1400827fe  mov     dword ptr [rsp+1D0h+ReplyBuffer], eax
0x140082802  xor     edx, edx
0x140082804  mov     ecx, 1
0x140082809  call    MpSendAsyncPanicModeMessage
0x14008280e  mov     eax, r14d
0x140082811  lock xadd [rbx+0Ch], eax
0x140082816  cmp     eax, 1
0x140082819  jnz     short loc_140082830
0x14008281b  lea     rcx, [rbx-18h]; P
0x14008281f  mov     edx, 6D61504Dh; Tag
0x140082824  call    cs:__imp_ExFreePoolWithTag
0x14008282b  nop     dword ptr [rax+rax+00h]
0x140082830  movzx   ebx, r15b
0x140082834  mov     r15, qword ptr [rsp+1D0h+Timeout]
0x140082839  mov     rax, cs:MpData
0x140082840  mov     ecx, [rax+364h]
0x140082846  test    cl, 2
0x140082849  jz      loc_140083AF7
0x14008284f  mov     rax, cs:MpData
0x140082856  cmp     qword ptr [rax+1A0h], 0
0x14008285e  jnz     short loc_14008286E
0x140082860  cmp     qword ptr [rax+1B0h], 0
0x140082868  jz      loc_140083AF7
0x14008286e  cmp     qword ptr [rsi+8], 0
0x140082873  jz      short loc_14008288F
0x140082875  movzx   eax, word ptr [rsi]
0x140082878  xor     ecx, ecx
0x14008287a  cmp     cx, ax
0x14008287d  jz      short loc_14008288F
0x14008287f  add     eax, 82h
0x140082884  mov     [rbp+0D0h+var_150], 80h
0x14008288b  mov     dword ptr [rsp+1D0h+var_190+4], eax
0x14008288f  xor     eax, eax
0x140082891  xor     r14b, r14b
0x140082894  test    dword ptr [r12], 400h
0x14008289c  xorps   xmm0, xmm0
0x14008289f  movups  xmmword ptr [rsp+1D0h+ClientPort+8], xmm0
0x1400828a4  mov     qword ptr [rsp+1D0h+Timeout], rax
0x1400828a9  jz      loc_1400829A3
0x1400828af  cmp     qword ptr [r12-8], 38h ; '8'
0x1400828b5  jb      loc_1400829A3
0x1400828bb  mov     rdi, [r12+28h]
  ... truncated ...
```
