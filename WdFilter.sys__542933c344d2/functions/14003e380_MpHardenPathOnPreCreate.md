# MpHardenPathOnPreCreate

- ea: `0x14003e380`
- end: `0x14003ee80`
- name: `MpHardenPathOnPreCreate`
- size: `2816`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14003c990`

## callees

- `0x140002450`
- `0x1400051bc`
- `0x14000b5d4`
- `0x14000fcfc`
- `0x1400118d0`
- `0x140030060`
- `0x14003e380`
- `0x14003ee80`
- `0x140040388`
- `0x1400471ac`
- `0x1400704f8`
- `0x140072f34`
- `0x1400777a8`
- `0x14008ab44`

## import_xrefs

- `ntoskrnl!PsGetProcessId` at `0x14003e449`
- `ntoskrnl!PsGetProcessId` at `0x14003e449`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x14003e9b5`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x14003e9b5`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x14003e99f`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x14003e99f`
- `ntoskrnl!KeQueryTimeIncrement` at `0x14003ea51`
- `ntoskrnl!KeQueryTimeIncrement` at `0x14003eba4`
- `ntoskrnl!KeQueryTimeIncrement` at `0x14003ea51`
- `ntoskrnl!KeQueryTimeIncrement` at `0x14003eba4`
- `ntoskrnl!PsInitialSystemProcess` at `0x14003e400`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x14003e437`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x14003e437`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003e4df`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003edfa`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003e4df`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003edfa`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003e4d3`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003edee`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003e4d3`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003edee`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14003e47a`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14003e47a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003e468`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003e468`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14003ed42`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14003edac`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14003ed42`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14003edac`
- `FLTMGR!FltGetFileNameInformation` at `0x14003e74f`
- `FLTMGR!FltGetFileNameInformation` at `0x14003eb34`
- `FLTMGR!FltGetFileNameInformation` at `0x14003e74f`
- `FLTMGR!FltGetFileNameInformation` at `0x14003eb34`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14003e637`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14003ee6f`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14003e637`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14003ee6f`

## string_xrefs

- `0x14003edcb`: `[Mini-filter] Denied access to file  [%wZ] from process [%wZ][Pid:%u] on Pre-Create. Reason: %ws.`

## pseudocode

```c
__int64 __fastcall MpHardenPathOnPreCreate(struct _FLT_CALLBACK_DATA *a1, __int64 a2, __int64 a3, unsigned __int64 *a4)
{
  __int64 v4; // r12
  NTSTATUS IsLoopbackByName; // ebx
  volatile signed __int32 *v7; // r14
  struct _KPROCESS *RequestorProcess; // rdi
  LONGLONG TimeQuadPart; // r15
  unsigned __int64 ProcessId; // rsi
  char *v11; // rbx
  _QWORD *v12; // r8
  _QWORD *i; // rax
  volatile signed __int32 *v14; // rdi
  int v15; // esi
  _DWORD *v16; // rdx
  struct _FLT_CALLBACK_DATA *v17; // r15
  PFLT_IO_PARAMETER_BLOCK v18; // rax
  char v19; // bl
  bool v20; // cl
  PFLT_IO_PARAMETER_BLOCK v21; // rcx
  bool v22; // dl
  UCHAR MajorFunction; // al
  char v24; // al
  bool v25; // al
  char v26; // si
  int v28; // eax
  bool v29; // r13
  PFLT_IO_PARAMETER_BLOCK v30; // rax
  ULONG Options; // r8d
  unsigned __int64 v32; // rcx
  PFLT_IO_PARAMETER_BLOCK v33; // rcx
  unsigned __int8 v34; // si
  __int64 v35; // rax
  PCUNICODE_STRING v36; // r15
  int v37; // r14d
  unsigned __int8 v38; // al
  char IsAMPath; // si
  int v40; // r9d
  char v41; // r13
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  ULONG_PTR v43; // rdx
  PACCESS_TOKEN v44; // rax
  struct _KTHREAD *Thread; // r9
  __int64 v46; // rdx
  unsigned __int64 v47; // rbx
  ULONG TimeIncrement; // eax
  enum _SECURITY_IMPERSONATION_LEVEL v49; // ecx
  unsigned __int64 v50; // rbx
  ULONG v51; // eax
  DWORD LowPart; // ecx
  const wchar_t *v53; // rsi
  const wchar_t *v54; // r14
  __int64 v55; // r15
  char CurrentProcessId; // al
  int v57; // r8d
  unsigned int v58; // eax
  int v59; // [rsp+30h] [rbp-61h]
  int v61; // [rsp+50h] [rbp-41h]
  PCUNICODE_STRING String2; // [rsp+70h] [rbp-21h] BYREF
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+78h] [rbp-19h] BYREF
  unsigned __int64 v67; // [rsp+80h] [rbp-11h] BYREF
  PFLT_FILE_NAME_INFORMATION v68; // [rsp+88h] [rbp-9h] BYREF
  unsigned __int8 EffectiveOnly; // [rsp+90h] [rbp-1h] BYREF
  unsigned __int8 CopyOnOpen[3]; // [rsp+91h] [rbp+0h] BYREF
  enum _SECURITY_IMPERSONATION_LEVEL ImpersonationLevel; // [rsp+94h] [rbp+3h] BYREF

  v4 = 0;
  IsLoopbackByName = 0;
  FileNameInformation = 0;
  v68 = 0;
  String2 = 0;
  v67 = 0;
  v61 = *(_DWORD *)(MpData + 868) & 0x4000;
  v7 = 0;
  RequestorProcess = (struct _KPROCESS *)MpGetRequestorProcess(a1);
  if ( !RequestorProcess
    || PsInitialSystemProcess == RequestorProcess
    || RequestorProcess == *(struct _KPROCESS **)(MpData + 232) )
  {
    goto LABEL_28;
  }
  TimeQuadPart = PsGetProcessCreateTimeQuadPart(RequestorProcess);
  ProcessId = (unsigned __int64)PsGetProcessId(RequestorProcess);
  if ( !ProcessId )
  {
LABEL_166:
    IsLoopbackByName = -1073741275;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_28;
    v17 = a1;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      _mm_lfence();
      Thread = a1->Thread;
      v46 = 100;
LABEL_169:
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        v46,
        WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids,
        Thread,
        IsLoopbackByName);
    }
    goto LABEL_26;
  }
  v11 = (char *)MpProcessTable;
  KeEnterCriticalRegion();
  ExAcquireResourceSharedLite((PERESOURCE)(v11 + 8), 1u);
  v12 = (_QWORD *)(*((_QWORD *)MpProcessTable + 48) + 16 * ((ProcessId >> 2) & 0x7F));
  for ( i = (_QWORD *)*v12; ; i = (_QWORD *)*i )
  {
    if ( i == v12 )
    {
      ExReleaseResourceLite((PERESOURCE)((char *)MpProcessTable + 8));
      KeLeaveCriticalRegion();
      goto LABEL_166;
    }
    v14 = (volatile signed __int32 *)(i - 1);
    if ( ProcessId == i[2] && TimeQuadPart == *((_QWORD *)v14 + 4) )
      break;
  }
  _InterlockedIncrement(v14 + 12);
  ExReleaseResourceLite((PERESOURCE)((char *)MpProcessTable + 8));
  KeLeaveCriticalRegion();
  v15 = *(_DWORD *)(a3 + 120);
  if ( *(_DWORD *)(MpData + 2444)
    || (v16 = (_DWORD *)MpData, !*(_QWORD *)(MpData + 232))
    && (v47 = MEMORY[0xFFFFF78000000320],
        TimeIncrement = KeQueryTimeIncrement(),
        v16 = (_DWORD *)MpData,
        *(_QWORD *)(MpData + 4032) + 0x861C46800uLL / TimeIncrement < v47)
    || (v16[978] & 1) != 0 )
  {
    v17 = a1;
LABEL_36:
    v26 = 0;
    goto LABEL_37;
  }
  v17 = a1;
  if ( !v16[1043] )
  {
    Iopb = a1->Iopb;
    if ( !Iopb->MajorFunction && (Iopb->Parameters.Create.Options & 1) != 0 )
      goto LABEL_36;
  }
  v18 = a1->Iopb;
  v19 = 0;
  v20 = 0;
  if ( v18->MajorFunction == 13 )
  {
    LowPart = v18->Parameters.Read.ByteOffset.LowPart;
    if ( LowPart == 590039 || LowPart == 590043 )
      v20 = 1;
  }
  if ( (v16[1013] & 1) != 0 && v20 )
  {
    CopyOnOpen[0] = 0;
    EffectiveOnly = 0;
    ImpersonationLevel = SecurityAnonymous;
    v44 = PsReferenceImpersonationToken(KeGetCurrentThread(), CopyOnOpen, &EffectiveOnly, &ImpersonationLevel);
    if ( v44 )
    {
      v19 = 1;
      PsDereferenceImpersonationToken(v44);
    }
  }
  v21 = a1->Iopb;
  v22 = 0;
  MajorFunction = v21->MajorFunction;
  if ( MajorFunction )
  {
    if ( MajorFunction == 13 && v21->Parameters.Read.ByteOffset.LowPart == 623112 )
    {
      v24 = 1;
      goto LABEL_20;
    }
  }
  else
  {
    v22 = (v21->OperationFlags & 2) != 0;
  }
  v24 = 0;
LABEL_20:
  v25 = dword_140026A20 && *((_DWORD *)v14 + 60) == 21 && v24;
  if ( !v19 && !v22 && !v25 )
  {
    if ( !v14 )
      goto LABEL_36;
    if ( *(_DWORD *)(MpData + 2444) )
      goto LABEL_36;
    v43 = MpData;
    if ( !*(_QWORD *)(MpData + 232) )
    {
      v50 = MEMORY[0xFFFFF78000000320];
      v51 = KeQueryTimeIncrement();
      v43 = MpData;
      if ( *(_QWORD *)(MpData + 4032) + 0x861C46800uLL / v51 < v50 )
        goto LABEL_36;
    }
    if ( (*((_DWORD *)v14 + 60) != 21 || *(_QWORD *)(v43 + 232)) && (v14[72] & 0x10) != 0 )
      goto LABEL_36;
  }
  if ( v15 == 13 )
    v26 = 1;
  else
    v26 = *(_BYTE *)(a3 + 80) & 1;
LABEL_37:
  if ( (*(_DWORD *)(MpData + 864) & 8) != 0 )
  {
    if ( (v14[13] & 8) != 0 )
    {
      v29 = 0;
    }
    else
    {
      v28 = *((_DWORD *)v14 + 14);
      v29 = (v28 & 0x20000) != 0 && (v28 & 0x100000) == 0;
    }
  }
  else
  {
    v29 = 0;
  }
  if ( v26 || (v7 = v14, IsLoopbackByName = 0, v29) )
  {
    v30 = v17->Iopb;
    Options = v30->Parameters.Create.Options;
    if ( HIBYTE(Options) == 1
      && (Options & 0x1000) == 0
      && (*(_DWORD *)(v30->Parameters.WMI.ProviderId + 16) & 0x2000000) == 0
      && v26 )
    {
      *a4 |= 0x10u;
    }
    if ( *(_DWORD *)(MpData + 4112)
      && ((HIBYTE(Options) - 1) & 0xFFFFFFFD) == 0
      && (Options & 0x1000) == 0
      && (*(_DWORD *)(v17->Iopb->Parameters.WMI.ProviderId + 16) & 0x2000000) == 0
      && v29 )
    {
      *a4 |= 0x8000u;
    }
    v32 = *a4;
    v7 = v14;
    IsLoopbackByName = 0;
    if ( (*a4 & 0x8010) != 0x8010 && ((v32 & 0x10) == 0 || v29) )
    {
      if ( (v32 & 0x8000) == 0 || (v7 = v14, IsLoopbackByName = 0, v26) )
      {
        IsLoopbackByName = 0;
        *a4 = v32 & 0xFFFFFFFFFFFF7FEFuLL;
        if ( *(_DWORD *)(a3 + 120) != 13 )
          goto LABEL_49;
        EffectiveOnly = 0;
        IsLoopbackByName = FltGetFileNameInformation(v17, 0x102u, &v68);
        if ( IsLoopbackByName < 0 )
        {
          v7 = v14;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          {
            _mm_lfence();
            Thread = KeGetCurrentThread();
            v46 = 101;
            goto LABEL_169;
          }
        }
        else
        {
          IsLoopbackByName = MpIsLoopbackByName(a2, v68, &EffectiveOnly, &String2, &v67);
          if ( IsLoopbackByName >= 0 )
          {
            *a4 |= 0x1000u;
            if ( !EffectiveOnly )
            {
              v7 = v14;
              if ( !v29 || !(unsigned __int8)MpFgIsProtectingRemoteFolders() )
                goto LABEL_28;
            }
LABEL_49:
            if ( String2
              || (IsLoopbackByName = FltGetFileNameInformation(v17, 0x101u, &FileNameInformation), IsLoopbackByName >= 0) )
            {
              if ( v26 )
              {
                if ( v61 )
                {
                  v33 = v17->Iopb;
                  if ( (v33->Parameters.Create.Options & 1) != 0 || (v33->OperationFlags & 4) != 0 )
                    LOBYTE(v4) = 1;
                  v34 = 0;
                  v35 = String2 ? 0LL : a3;
                  v36 = String2;
                  v37 = (int)FileNameInformation;
                  if ( MpFsHardeningData && v14 && (FileNameInformation || String2) )
                  {
                    ImpersonationLevel = SecurityAnonymous;
                    v38 = FsHardeningMatch(FileNameInformation, String2, v35, v59, (__int64)&ImpersonationLevel);
                    if ( v38 )
                    {
                      v49 = ImpersonationLevel;
                      if ( (ImpersonationLevel & 1) != 0 )
                        v34 = v38;
                      if ( (ImpersonationLevel & 2) != 0 )
                      {
                        LOBYTE(v49) = 1;
                        MpTraceFsHardeningNotification(v49, v34, *((_QWORD *)v14 + 16), v37, (__int64)v36, v4);
                      }
                    }
                    else
                    {
                      v34 = 1;
                    }
                  }
                  else
                  {
                    v34 = 0;
                  }
                  v17 = a1;
                  IsAMPath = v34 == 0;
                  v4 = 0;
                }
                else
                {
                  IsAMPath = MpIsAMPath(v14, FileNameInformation);
                }
                if ( IsAMPath )
                {
                  v17->IoStatus.Status = -1073741790;
                  IsLoopbackByName = 1835009;
                  v17->IoStatus.Information = 0;
                  v41 = 0;
LABEL_149:
                  v53 = L"CFA";
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
                  {
                    if ( v41 )
                    {
                      v54 = L"CFA";
                    }
                    else
                    {
                      v54 = L"DynamicFsHardening";
                      if ( !v61 )
                        v54 = L"FsHardening";
                    }
                    if ( v14 )
                      v55 = *((_QWORD *)v14 + 16);
                    else
                      v55 = 0;
                    CurrentProcessId = (unsigned __int8)PsGetCurrentProcessId();
                    WPP_SF_ZZDS(
                      WPP_GLOBAL_Control->AttachedDevice,
                      105,
                      v57,
                      &a1->Iopb->TargetFileObject->FileName,
                      v55,
                      CurrentProcessId,
                      (__int64)v54);
                    v17 = a1;
                  }
                  if ( !v41 )
                  {
                    v53 = L"DynamicFsHardening";
                    if ( !v61 )
                      v53 = L"FsHardening";
                  }
                  if ( v14 )
                    v4 = *((_QWORD *)v14 + 16);
                  v58 = (unsigned int)PsGetCurrentProcessId();
                  MpLogPrintfW(
                    L"[Mini-filter] Denied access to file  [%wZ] from process [%wZ][Pid:%u] on Pre-Create. Reason: %ws.",
                    &v17->Iopb->TargetFileObject->FileName,
                    v4,
                    v58,
                    v53);
                  v7 = v14;
                  goto LABEL_28;
                }
              }
              v7 = v14;
              if ( v29 )
              {
                v40 = (int)String2;
                if ( !String2 )
                  v40 = (_DWORD)FileNameInformation + 8;
                v41 = MpApplyFolderGuard((_DWORD)v17, a2, (_DWORD)v14, v40, 0);
                if ( v41 )
                {
                  MpRemoveWriteAccess(v17);
                  goto LABEL_149;
                }
              }
            }
            else if ( IsLoopbackByName == -1073741612 || IsLoopbackByName == -1073741766 )
            {
              v7 = v14;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
              {
                _mm_lfence();
                Thread = KeGetCurrentThread();
                v46 = 103;
                goto LABEL_169;
              }
            }
            else
            {
              v7 = v14;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
              {
                _mm_lfence();
                Thread = KeGetCurrentThread();
                v46 = 104;
                goto LABEL_169;
              }
            }
            goto LABEL_26;
          }
          v7 = v14;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          {
            _mm_lfence();
            Thread = KeGetCurrentThread();
            v46 = 102;
            goto LABEL_169;
          }
        }
LABEL_26:
        if ( IsLoopbackByName == -1073741536 || IsLoopbackByName == -1073741749 )
        {
          v17->IoStatus.Status = IsLoopbackByName;
          IsLoopbackByName = 1835009;
          v17->IoStatus.Information = 0;
        }
      }
    }
  }
LABEL_28:
  a4[1] = (unsigned __int64)String2;
  a4[2] = v67;
  if ( v7 )
    MpReleaseProcessContext(v7);
  if ( FileNameInformation )
    FltReleaseFileNameInformation(FileNameInformation);
  if ( v68 )
    FltReleaseFileNameInformation(v68);
  return (unsigned int)IsLoopbackByName;
}

```

## disassembly

```asm
0x14003e380  mov     r11, rsp
0x14003e383  push    rbp
0x14003e384  push    rbx
0x14003e385  lea     rbp, [r11-5Fh]
0x14003e389  sub     rsp, 0D8h
0x14003e390  mov     rax, cs:__security_cookie
0x14003e397  xor     rax, rsp
0x14003e39a  mov     [rbp+57h+var_50], rax
0x14003e39e  mov     rax, cs:MpData
0x14003e3a5  mov     [r11-20h], rdi
0x14003e3a9  mov     [r11-28h], r12
0x14003e3ad  xor     r12d, r12d
0x14003e3b0  mov     [r11-30h], r13
0x14003e3b4  mov     ebx, r12d
0x14003e3b7  mov     [rbp+57h+FileNameInformation], r12
0x14003e3bb  mov     r13, r8
0x14003e3be  mov     [rbp+57h+var_60], r12
0x14003e3c2  mov     [rbp+57h+String2], r12
0x14003e3c6  mov     [rbp+57h+var_68], r12
0x14003e3ca  mov     eax, [rax+364h]
0x14003e3d0  and     eax, 4000h
0x14003e3d5  mov     [r11-38h], r14
0x14003e3d9  mov     [rbp+57h+var_98], eax
0x14003e3dc  mov     r14d, r12d
0x14003e3df  mov     [rbp+57h+var_90], r9
0x14003e3e3  mov     [rbp+57h+var_80], r8
0x14003e3e7  mov     [rbp+57h+var_88], rdx
0x14003e3eb  mov     [rbp+57h+CallbackData], rcx
0x14003e3ef  call    MpGetRequestorProcess
0x14003e3f4  mov     rdi, rax
0x14003e3f7  test    rax, rax
0x14003e3fa  jz      loc_14003E5F5
0x14003e400  mov     rax, cs:__imp_PsInitialSystemProcess
0x14003e407  cmp     [rax], rdi
0x14003e40a  jz      loc_14003E5F5
0x14003e410  mov     rax, cs:MpData
0x14003e417  cmp     rdi, [rax+0E8h]
0x14003e41e  jz      loc_14003E5F5
0x14003e424  mov     [rsp+0D0h], rsi
0x14003e42c  mov     rcx, rdi; Process
0x14003e42f  mov     [rsp+0E0h+var_38], r15
0x14003e437  call    cs:__imp_PsGetProcessCreateTimeQuadPart
0x14003e43e  nop     dword ptr [rax+rax+00h]
0x14003e443  mov     rcx, rdi; Process
0x14003e446  mov     r15, rax
0x14003e449  call    cs:__imp_PsGetProcessId
0x14003e450  nop     dword ptr [rax+rax+00h]
0x14003e455  mov     rsi, rax
0x14003e458  test    rax, rax
0x14003e45b  jz      loc_14003EE06
0x14003e461  mov     rbx, cs:MpProcessTable
0x14003e468  call    cs:__imp_KeEnterCriticalRegion
0x14003e46f  nop     dword ptr [rax+rax+00h]
0x14003e474  mov     dl, 1; Wait
0x14003e476  lea     rcx, [rbx+8]; Resource
0x14003e47a  call    cs:__imp_ExAcquireResourceSharedLite
0x14003e481  nop     dword ptr [rax+rax+00h]
0x14003e486  mov     rax, cs:MpProcessTable
0x14003e48d  mov     r8, rsi
0x14003e490  shr     r8, 2
0x14003e494  and     r8d, 7Fh
0x14003e498  shl     r8, 4
0x14003e49c  add     r8, [rax+180h]
0x14003e4a3  mov     rax, [r8]
0x14003e4a6  cmp     rax, r8
0x14003e4a9  jz      loc_14003EDE3
0x14003e4af  cmp     rsi, [rax+10h]
0x14003e4b3  lea     rdi, [rax-8]
0x14003e4b7  jz      short loc_14003E4BE
0x14003e4b9  mov     rax, [rax]
0x14003e4bc  jmp     short loc_14003E4A6
0x14003e4be  cmp     r15, [rdi+20h]
0x14003e4c2  jnz     short loc_14003E4B9
0x14003e4c4  lock inc dword ptr [rdi+30h]
0x14003e4c8  mov     rcx, cs:MpProcessTable
0x14003e4cf  add     rcx, 8; Resource
0x14003e4d3  call    cs:__imp_ExReleaseResourceLite
0x14003e4da  nop     dword ptr [rax+rax+00h]
0x14003e4df  call    cs:__imp_KeLeaveCriticalRegion
0x14003e4e6  nop     dword ptr [rax+rax+00h]
0x14003e4eb  mov     rax, cs:MpData
0x14003e4f2  mov     esi, [r13+78h]
0x14003e4f6  mov     ecx, [rax+98Ch]
0x14003e4fc  test    ecx, ecx
0x14003e4fe  jnz     loc_14003E673
0x14003e504  mov     rdx, cs:MpData
0x14003e50b  mov     r8, 0FFFFF78000000320h
0x14003e515  mov     r14, 861C46800h
0x14003e51f  cmp     [rdx+0E8h], r12
0x14003e526  jz      loc_14003EA4E
0x14003e52c  mov     eax, [rdx+0F48h]
0x14003e532  test    al, 1
0x14003e534  jnz     loc_14003E673
0x14003e53a  mov     r15, [rbp+57h+CallbackData]
0x14003e53e  cmp     [rdx+104Ch], r12d
0x14003e545  jz      loc_14003E89A
0x14003e54b  mov     rax, [r15+10h]
0x14003e54f  xor     bl, bl
0x14003e551  cmp     byte ptr [rax+4], 0Dh
0x14003e555  jz      loc_14003EBDE
0x14003e55b  xor     cl, cl
0x14003e55d  mov     eax, [rdx+0FD4h]
0x14003e563  test    al, 1
0x14003e565  jnz     loc_14003E978
0x14003e56b  mov     rcx, [r15+10h]
0x14003e56f  xor     dl, dl
0x14003e571  movzx   eax, byte ptr [rcx+4]
0x14003e575  test    al, al
0x14003e577  jz      loc_14003E9DE
0x14003e57d  cmp     al, 0Dh
0x14003e57f  jz      loc_14003EBFC
0x14003e585  xor     al, al
0x14003e587  cmp     cs:dword_140026A20, r12d
0x14003e58e  jz      short loc_14003E59D
0x14003e590  cmp     dword ptr [rdi+0F0h], 15h
0x14003e597  jz      loc_14003EC10
0x14003e59d  xor     al, al
0x14003e59f  test    bl, bl
0x14003e5a1  jz      loc_14003E8F4
0x14003e5a7  cmp     esi, 0Dh
0x14003e5aa  jnz     loc_14003E8E6
0x14003e5b0  mov     sil, 1
0x14003e5b3  jmp     loc_14003E67A
0x14003e5b8  movzx   ecx, r13b
0x14003e5bc  test    sil, sil
0x14003e5bf  jnz     loc_14003ECF0
0x14003e5c5  test    cl, cl
0x14003e5c7  jnz     loc_14003ECF0
0x14003e5cd  cmp     ebx, 0C0000120h
0x14003e5d3  jz      loc_14003EE5D
0x14003e5d9  cmp     ebx, 0C000004Bh
0x14003e5df  jz      loc_14003EE5D
0x14003e5e5  mov     rsi, [rsp+0D0h]
0x14003e5ed  mov     r15, [rsp+0E0h+var_38]
0x14003e5f5  mov     rdi, [rbp+57h+var_90]
0x14003e5f9  mov     rax, [rbp+57h+String2]
0x14003e5fd  mov     r13, [rsp+0E0h+var_28]
0x14003e605  mov     r12, [rsp+0E0h+var_20]
0x14003e60d  mov     [rdi+8], rax
0x14003e611  mov     rax, [rbp+57h+var_68]
0x14003e615  mov     [rdi+10h], rax
0x14003e619  mov     rdi, [rsp+0E0h+var_18]
0x14003e621  test    r14, r14
0x14003e624  jnz     short loc_14003E669
0x14003e626  mov     rcx, [rbp+57h+FileNameInformation]; FileNameInformation
0x14003e62a  mov     r14, [rsp+0E0h+var_30]
0x14003e632  test    rcx, rcx
0x14003e635  jz      short loc_14003E643
0x14003e637  call    cs:__imp_FltReleaseFileNameInformation
0x14003e63e  nop     dword ptr [rax+rax+00h]
0x14003e643  mov     rcx, [rbp+57h+var_60]; FileNameInformation
0x14003e647  test    rcx, rcx
0x14003e64a  jnz     loc_14003EE6F
0x14003e650  mov     eax, ebx
0x14003e652  mov     rcx, [rbp+57h+var_50]
0x14003e656  xor     rcx, rsp; StackCookie
0x14003e659  call    __security_check_cookie
0x14003e65e  add     rsp, 0D8h
0x14003e665  pop     rbx
0x14003e666  pop     rbp
0x14003e667  retn
0x14003e669  mov     rcx, r14
0x14003e66c  call    MpReleaseProcessContext
0x14003e671  jmp     short loc_14003E626
0x14003e673  mov     r15, [rbp+57h+CallbackData]
0x14003e677  xor     sil, sil
0x14003e67a  mov     rax, cs:MpData
0x14003e681  mov     ecx, [rax+360h]
0x14003e687  test    cl, 8
0x14003e68a  jz      loc_14003EC31
0x14003e690  mov     eax, [rdi+34h]
0x14003e693  test    al, 8
0x14003e695  jnz     loc_14003E9F7
0x14003e69b  mov     eax, [rdi+38h]
0x14003e69e  bt      eax, 11h
0x14003e6a2  jb      loc_14003E9D0
0x14003e6a8  xor     r13b, r13b
0x14003e6ab  test    sil, sil
0x14003e6ae  jz      loc_14003E956
0x14003e6b4  mov     rax, [r15+10h]
0x14003e6b8  mov     rbx, [rbp+57h+var_90]
0x14003e6bc  mov     r8d, [rax+20h]
0x14003e6c0  mov     edx, r8d
0x14003e6c3  shr     edx, 18h
0x14003e6c6  cmp     edx, 1
0x14003e6c9  jz      loc_14003E8B8
0x14003e6cf  mov     rax, cs:MpData
0x14003e6d6  cmp     [rax+1010h], r12d
0x14003e6dd  jz      short loc_14003E6ED
0x14003e6df  lea     eax, [rdx-1]
0x14003e6e2  test    eax, 0FFFFFFFDh
0x14003e6e7  jz      loc_14003E865
0x14003e6ed  mov     rcx, [rbx]
0x14003e6f0  mov     r14, rdi
0x14003e6f3  mov     rax, rcx
0x14003e6f6  mov     ebx, r12d
0x14003e6f9  and     eax, 8010h
0x14003e6fe  cmp     rax, 8010h
0x14003e704  jz      loc_14003E5E5
0x14003e70a  test    cl, 10h
0x14003e70d  jnz     loc_14003E96A
0x14003e713  bt      rcx, 0Fh
0x14003e718  jb      loc_14003EC39
0x14003e71e  mov     r14, [rbp+57h+var_90]
0x14003e722  and     rcx, 0FFFFFFFFFFFF7FEFh
0x14003e729  mov     rax, [rbp+57h+var_80]
0x14003e72d  mov     ebx, r12d
0x14003e730  mov     [r14], rcx
0x14003e733  cmp     dword ptr [rax+78h], 0Dh
0x14003e737  jz      loc_14003EB25
0x14003e73d  cmp     [rbp+57h+String2], r12
0x14003e741  jnz     short loc_14003E765
0x14003e743  lea     r8, [rbp+57h+FileNameInformation]; FileNameInformation
0x14003e747  mov     edx, 101h; NameOptions
0x14003e74c  mov     rcx, r15; CallbackData
0x14003e74f  call    cs:__imp_FltGetFileNameInformation
0x14003e756  nop     dword ptr [rax+rax+00h]
0x14003e75b  mov     ebx, eax
0x14003e75d  test    eax, eax
0x14003e75f  js      loc_14003E9FF
0x14003e765  test    sil, sil
0x14003e768  jz      loc_14003EBD6
0x14003e76e  cmp     [rbp+57h+var_98], r12d
0x14003e772  jz      loc_14003EA8D
0x14003e778  mov     rcx, [r15+10h]
0x14003e77c  mov     eax, [rcx+20h]
0x14003e77f  test    al, 1
0x14003e781  jz      loc_14003E856
0x14003e787  mov     r12b, 1
0x14003e78a  xor     esi, esi
0x14003e78c  cmp     [rbp+57h+String2], rsi
0x14003e790  jnz     loc_14003ECC3
0x14003e796  mov     rax, [rbp+57h+var_88]
0x14003e79a  mov     r9, [rax+18h]
0x14003e79e  mov     rax, [rbp+57h+var_80]
0x14003e7a2  cmp     cs:MpFsHardeningData, 0
0x14003e7aa  mov     r15, [rbp+57h+String2]
0x14003e7ae  mov     r14, [rbp+57h+FileNameInformation]
0x14003e7b2  jz      loc_14003E9EF
0x14003e7b8  test    rdi, rdi
0x14003e7bb  jz      loc_14003E9EF
0x14003e7c1  test    r14, r14
0x14003e7c4  jz      loc_14003ECCE
0x14003e7ca  mov     r8, [rbp+57h+var_68]
0x14003e7ce  lea     rcx, [rbp+57h+ImpersonationLevel]
0x14003e7d2  mov     qword ptr [rsp+0E0h+var_B8+8], rcx; __int64
0x14003e7d7  mov     rdx, r15; String2
0x14003e7da  mov     rcx, r14; FileNameInformation
0x14003e7dd  mov     [rbp+57h+ImpersonationLevel], esi
0x14003e7e0  mov     [rsp+0E0h+var_C0], rax; __int64
0x14003e7e5  call    FsHardeningMatch
0x14003e7ea  test    al, al
0x14003e7ec  jnz     loc_14003EAA5
0x14003e7f2  mov     sil, 1
0x14003e7f5  mov     r15, [rbp+57h+CallbackData]
0x14003e7f9  test    sil, sil
0x14003e7fc  setz    sil
0x14003e800  xor     r12d, r12d
0x14003e803  test    sil, sil
0x14003e806  jnz     loc_14003ECDC
0x14003e80c  mov     r14, rdi
0x14003e80f  test    r13b, r13b
0x14003e812  jz      loc_14003E5CD
0x14003e818  mov     r9, [rbp+57h+String2]
0x14003e81c  test    r9, r9
0x14003e81f  jnz     short loc_14003E829
0x14003e821  mov     r9, [rbp+57h+FileNameInformation]
0x14003e825  add     r9, 8
0x14003e829  mov     rdx, [rbp+57h+var_88]
0x14003e82d  mov     r8, rdi
0x14003e830  mov     rcx, r15
0x14003e833  mov     byte ptr [rsp+0E0h+var_C0], 0
0x14003e838  call    MpApplyFolderGuard
0x14003e83d  movzx   r13d, al
0x14003e841  test    al, al
0x14003e843  jz      loc_14003E5B8
0x14003e849  mov     rcx, r15; Data
0x14003e84c  call    MpRemoveWriteAccess
0x14003e851  jmp     loc_14003E5B8
0x14003e856  test    byte ptr [rcx+6], 4
0x14003e85a  jz      loc_14003E78A
0x14003e860  jmp     loc_14003E787
0x14003e865  bt      r8d, 0Ch
0x14003e86a  jb      loc_14003E6ED
0x14003e870  mov     rax, [r15+10h]
0x14003e874  mov     rcx, [rax+18h]
0x14003e878  test    dword ptr [rcx+10h], 2000000h
0x14003e87f  jnz     loc_14003E6ED
0x14003e885  test    r13b, r13b
0x14003e888  jz      loc_14003E6ED
0x14003e88e  or      qword ptr [rbx], 8000h
0x14003e895  jmp     loc_14003E6ED
0x14003e89a  mov     rax, [r15+10h]
0x14003e89e  cmp     [rax+4], r12b
0x14003e8a2  jnz     loc_14003E54B
0x14003e8a8  mov     eax, [rax+20h]
0x14003e8ab  test    al, 1
0x14003e8ad  jnz     loc_14003E677
0x14003e8b3  jmp     loc_14003E54B
0x14003e8b8  bt      r8d, 0Ch
  ... truncated ...
```
