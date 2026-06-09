# MpQueryEaFromNetworkFileStubIfNeeded

- ea: `0x140066dc0`
- end: `0x1400679ce`
- name: `MpQueryEaFromNetworkFileStubIfNeeded`
- size: `3086`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops`

## callers

- `0x140066890`

## callees

- `0x1400026c0`
- `0x140003d20`
- `0x140004530`
- `0x140004e4c`
- `0x1400051bc`
- `0x140005228`
- `0x14000aa0c`
- `0x14000ae58`
- `0x14000b704`
- `0x14001053c`
- `0x1400106cc`
- `0x1400118d0`
- `0x140011900`
- `0x14004ff3c`
- `0x140050290`
- `0x140066dc0`
- `0x14007156c`
- `0x1400732c0`
- `0x140073684`
- `0x140089794`

## import_xrefs

- `ntoskrnl!_stricmp` at `0x140066f5e`
- `ntoskrnl!_stricmp` at `0x140066f7c`
- `ntoskrnl!_stricmp` at `0x140066f96`
- `ntoskrnl!_stricmp` at `0x140066f5e`
- `ntoskrnl!_stricmp` at `0x140066f7c`
- `ntoskrnl!_stricmp` at `0x140066f96`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14006762c`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14006762c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140067430`
- `ntoskrnl!ExFreePoolWithTag` at `0x140067970`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400679ab`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008cdfc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008ce37`
- `ntoskrnl!ExFreePoolWithTag` at `0x140067430`
- `ntoskrnl!ExFreePoolWithTag` at `0x140067970`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400679ab`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008cdfc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008ce37`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x140067938`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x14008cdb4`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x140067938`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x14008cdb4`
- `ntoskrnl!KeBugCheck` at `0x1400679c1`
- `ntoskrnl!KeBugCheck` at `0x14008cdcc`
- `ntoskrnl!KeBugCheck` at `0x1400679c1`
- `ntoskrnl!KeBugCheck` at `0x14008cdcc`
- `ntoskrnl!ObfDereferenceObject` at `0x140067905`
- `ntoskrnl!ObfDereferenceObject` at `0x14008cd81`
- `ntoskrnl!ObfDereferenceObject` at `0x140067905`
- `ntoskrnl!ObfDereferenceObject` at `0x14008cd81`
- `FLTMGR!FltGetFileNameInformation` at `0x1400670f0`
- `FLTMGR!FltGetFileNameInformation` at `0x140067183`
- `FLTMGR!FltGetFileNameInformation` at `0x1400670f0`
- `FLTMGR!FltGetFileNameInformation` at `0x140067183`
- `FLTMGR!FltGetFileSystemType` at `0x140066e87`
- `FLTMGR!FltGetFileSystemType` at `0x140066e87`
- `FLTMGR!FltClose` at `0x1400678ec`
- `FLTMGR!FltClose` at `0x14008cd68`
- `FLTMGR!FltClose` at `0x1400678ec`
- `FLTMGR!FltClose` at `0x14008cd68`
- `FLTMGR!FltQueryEaFile` at `0x1400677bd`
- `FLTMGR!FltQueryEaFile` at `0x1400677bd`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400671ae`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140067989`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14008ce15`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400671ae`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140067989`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14008ce15`

## pseudocode

```c
void __fastcall MpQueryEaFromNetworkFileStubIfNeeded(struct _KTHREAD *CallbackData, __int64 a2, _BYTE *a3)
{
  _BYTE *EaBuffer; // rdi
  void *v6; // r13
  int IsLoopbackByObj; // eax
  _DWORD *v8; // rsi
  const char *v9; // rsi
  int v10; // edx
  int v11; // r8d
  int NetworkRedirectionInfo; // eax
  struct _KTHREAD *v13; // r9
  __int64 v14; // rdx
  char v15; // r12
  PVOID v16; // rsi
  int File; // eax
  __int64 v18; // r8
  PVOID v19; // rsi
  int v20; // r8d
  PFLT_IO_PARAMETER_BLOCK v21; // rcx
  size_t Length; // rsi
  LARGE_INTEGER AllocationSize; // rcx
  _BYTE *v24; // rax
  PFLT_IO_PARAMETER_BLOCK v25; // rdx
  UCHAR OperationFlags; // r8
  ULONG *p_EaLength; // rax
  NTSTATUS v28; // eax
  char v29; // r11
  PFLT_IO_PARAMETER_BLOCK v30; // rdx
  int EaIndex; // [rsp+38h] [rbp-190h]
  int EaIndexa; // [rsp+38h] [rbp-190h]
  int v33; // [rsp+60h] [rbp-168h]
  int v34; // [rsp+60h] [rbp-168h]
  int v35; // [rsp+68h] [rbp-160h]
  int v36; // [rsp+68h] [rbp-160h]
  char v37; // [rsp+80h] [rbp-148h]
  char v38[3]; // [rsp+81h] [rbp-147h] BYREF
  NTSTATUS v39; // [rsp+84h] [rbp-144h]
  PVOID P; // [rsp+88h] [rbp-140h] BYREF
  PVOID v41; // [rsp+90h] [rbp-138h] BYREF
  _BYTE *v42; // [rsp+98h] [rbp-130h]
  int v43; // [rsp+A0h] [rbp-128h]
  _BYTE *v44; // [rsp+A8h] [rbp-120h]
  struct _KTHREAD *CurrentThread; // [rsp+B0h] [rbp-118h]
  void *v46; // [rsp+B8h] [rbp-110h]
  __int128 v47; // [rsp+C0h] [rbp-108h] BYREF
  struct _KTHREAD *v48; // [rsp+D0h] [rbp-F8h]
  struct _KTHREAD *v49; // [rsp+D8h] [rbp-F0h]
  struct _KTHREAD *v50; // [rsp+E0h] [rbp-E8h]
  struct _KTHREAD *v51; // [rsp+E8h] [rbp-E0h]
  struct _KTHREAD *v52; // [rsp+F0h] [rbp-D8h]
  struct _KTHREAD *v53; // [rsp+F8h] [rbp-D0h]
  struct _KTHREAD *v54; // [rsp+100h] [rbp-C8h]
  PVOID v55; // [rsp+108h] [rbp-C0h]
  struct _KTHREAD *v56; // [rsp+110h] [rbp-B8h]
  struct _KTHREAD *v57; // [rsp+118h] [rbp-B0h]
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+120h] [rbp-A8h] BYREF
  PFILE_OBJECT FileObject; // [rsp+128h] [rbp-A0h] BYREF
  HANDLE FileHandle; // [rsp+130h] [rbp-98h] BYREF
  __int64 v61[2]; // [rsp+138h] [rbp-90h] BYREF
  __int128 v62; // [rsp+148h] [rbp-80h]
  __int128 v63; // [rsp+158h] [rbp-70h]
  int v64; // [rsp+168h] [rbp-60h] BYREF
  ULONG LengthReturned; // [rsp+16Ch] [rbp-5Ch] BYREF
  __int128 v66; // [rsp+170h] [rbp-58h] BYREF

  v44 = a3;
  CurrentThread = CallbackData;
  v64 = 0;
  v38[0] = 0;
  v41 = 0;
  EaBuffer = 0;
  v42 = 0;
  v6 = 0;
  v46 = 0;
  FileHandle = 0;
  *(_OWORD *)v61 = 0;
  v62 = 0;
  *(_QWORD *)&v63 = 0;
  DWORD2(v63) = 0;
  v66 = 0;
  P = 0;
  FileNameInformation = 0;
  FileObject = 0;
  LengthReturned = 0;
  v37 = 0;
  *a3 = 0;
  if ( !*((_BYTE *)MpDlpData + 241)
    || FltGetFileSystemType(*(PVOID *)(a2 + 24), (PFLT_FILESYSTEM_TYPE)&v64) < 0
    || v64 != 13 )
  {
    return;
  }
  IsLoopbackByObj = MpIsLoopbackByObj(a2, 0, v38);
  if ( IsLoopbackByObj < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        22,
        WPP_ad635a2cae0e32a661f87ad0f41c83aa_Traceguids,
        KeGetCurrentThread(),
        IsLoopbackByObj);
    return;
  }
  if ( v38[0] && (*(_DWORD *)(MpData + 4108) & 4) == 0 )
    return;
  v8 = *(_DWORD **)(*((_QWORD *)CallbackData + 2) + 32LL);
  if ( v8 )
  {
    if ( *v8 )
      return;
    v9 = (char *)v8 + 5;
    if ( _stricmp(v9, "$Kernel.SEC.EndpointDlp") )
    {
      if ( _stricmp(v9, "$Kernel.SEC.MarkOfWeb") && _stricmp(v9, "$Kernel.SEC.ApplicationSource") )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        {
          _mm_lfence();
          CurrentThread = KeGetCurrentThread();
          WPP_SF_qsZ(
            WPP_GLOBAL_Control->AttachedDevice,
            v10,
            v11,
            (_DWORD)CurrentThread,
            (__int64)v9,
            *(_QWORD *)(a2 + 32) + 88LL);
        }
        return;
      }
    }
  }
  NetworkRedirectionInfo = MpDlpGetNetworkRedirectionInfo(&v41);
  v39 = NetworkRedirectionInfo;
  if ( NetworkRedirectionInfo < 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_84;
    v13 = KeGetCurrentThread();
    CurrentThread = v13;
    v14 = 25;
    goto LABEL_24;
  }
  if ( (MpFcKernelGetValue(283) & 1) != 0 )
  {
    v15 = 1;
  }
  else
  {
    v39 = FltGetFileNameInformation((PFLT_CALLBACK_DATA)CallbackData, 0x101u, &FileNameInformation);
    v15 = 0;
    if ( v39 < 0 )
    {
      if ( FileNameInformation )
      {
        FltReleaseFileNameInformation(FileNameInformation);
        FileNameInformation = 0;
      }
      v15 = 0;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        _mm_lfence();
        v48 = KeGetCurrentThread();
        WPP_SF_qZd(
          WPP_GLOBAL_Control->AttachedDevice,
          26,
          (unsigned int)WPP_ad635a2cae0e32a661f87ad0f41c83aa_Traceguids,
          (_DWORD)v48,
          *(_QWORD *)(a2 + 32) + 88LL,
          v39);
        EaBuffer = v42;
        v6 = v46;
      }
    }
  }
  if ( !FileNameInformation )
  {
    v39 = FltGetFileNameInformation((PFLT_CALLBACK_DATA)CallbackData, 0x102u, &FileNameInformation);
    if ( v39 < 0 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_84;
      _mm_lfence();
      v49 = KeGetCurrentThread();
      WPP_SF_qZd(
        WPP_GLOBAL_Control->AttachedDevice,
        27,
        (unsigned int)WPP_ad635a2cae0e32a661f87ad0f41c83aa_Traceguids,
        (_DWORD)v49,
        *(_QWORD *)(a2 + 32) + 88LL,
        v39);
      goto LABEL_83;
    }
  }
  v47 = 0;
  NetworkRedirectionInfo = MpDlpGetNetworkRedirectFileNameToHash(FileNameInformation);
  v39 = NetworkRedirectionInfo;
  if ( NetworkRedirectionInfo < 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_84;
    v13 = KeGetCurrentThread();
    v50 = v13;
    v14 = 28;
    goto LABEL_24;
  }
  NetworkRedirectionInfo = MpGetDlpStubFileNameForNetworkFile(&v47, v41, &P);
  v39 = NetworkRedirectionInfo;
  if ( NetworkRedirectionInfo < 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_84;
    v13 = KeGetCurrentThread();
    v51 = v13;
    v14 = 29;
    goto LABEL_24;
  }
  LODWORD(v61[0]) = 48;
  v61[1] = 0;
  DWORD2(v62) = 576;
  v16 = P;
  *(_QWORD *)&v62 = P;
  v63 = 0;
  File = MpFltCreateFileEx(
           *(_QWORD *)(MpData + 16),
           *(_QWORD *)v41,
           (int)&FileHandle,
           (int)&FileObject,
           0x100008u,
           (__int64)v61,
           (__int64)&v66,
           EaIndex,
           0x80u,
           7u,
           1u,
           0x40u,
           v33,
           v35,
           0);
  v18 = (unsigned int)File;
  v39 = File;
  if ( File >= 0 )
  {
LABEL_60:
    *v44 = 1;
    v21 = (PFLT_IO_PARAMETER_BLOCK)*((_QWORD *)CallbackData + 2);
    Length = v21->Parameters.Read.Length;
    v43 = Length;
    if ( (_DWORD)Length )
    {
      EaBuffer = v21->Parameters.Create.EaBuffer;
      v42 = EaBuffer;
      AllocationSize = v21->Parameters.Create.AllocationSize;
      if ( AllocationSize.QuadPart )
      {
        if ( (*(_BYTE *)(AllocationSize.QuadPart + 10) & 5) != 0 )
        {
          EaBuffer = *(_BYTE **)(AllocationSize.QuadPart + 24);
          v44 = EaBuffer;
          v24 = EaBuffer;
        }
        else
        {
          v24 = MmMapLockedPagesSpecifyCache(
                  (PMDL)AllocationSize.QuadPart,
                  0,
                  MmCached,
                  0,
                  0,
                  ExDefaultMdlProtection | 0x40000010u);
          EaBuffer = v24;
          v55 = v24;
          v44 = v24;
        }
        v42 = EaBuffer;
        if ( !v24 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          {
            v56 = KeGetCurrentThread();
            WPP_SF_qq(
              WPP_GLOBAL_Control->AttachedDevice,
              33,
              (unsigned int)WPP_ad635a2cae0e32a661f87ad0f41c83aa_Traceguids,
              (_DWORD)v56,
              *(_QWORD *)(*((_QWORD *)CallbackData + 2) + 64LL));
          }
          goto LABEL_84;
        }
      }
      if ( *((_BYTE *)CallbackData + 80) )
      {
        v6 = EaBuffer;
        v46 = EaBuffer;
        EaBuffer = (_BYTE *)MpAllocatePoolWithTag(1, Length, 1634029645);
        v42 = EaBuffer;
        if ( !EaBuffer )
        {
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          {
            goto LABEL_84;
          }
          _mm_lfence();
          v57 = KeGetCurrentThread();
          WPP_SF_qZ(
            WPP_GLOBAL_Control->AttachedDevice,
            34,
            (unsigned int)WPP_ad635a2cae0e32a661f87ad0f41c83aa_Traceguids,
            (_DWORD)v57,
            *(_QWORD *)(a2 + 32) + 88LL);
LABEL_83:
          EaBuffer = v42;
          goto LABEL_84;
        }
        v37 = 1;
      }
    }
    v25 = (PFLT_IO_PARAMETER_BLOCK)*((_QWORD *)CallbackData + 2);
    OperationFlags = v25->OperationFlags;
    p_EaLength = &v25->Parameters.Create.EaLength;
    if ( (OperationFlags & 4) == 0 )
      p_EaLength = 0;
    v28 = FltQueryEaFile(
            *(PFLT_INSTANCE *)v41,
            FileObject,
            EaBuffer,
            Length,
            (OperationFlags & 2) != 0,
            v25->Parameters.QueryEa.EaList,
            v25->Parameters.Read.ByteOffset.LowPart,
            p_EaLength,
            OperationFlags & 1,
            &LengthReturned);
    v39 = v28;
    *((_DWORD *)CallbackData + 6) = v28;
    v29 = LengthReturned;
    *((_QWORD *)CallbackData + 4) = LengthReturned;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    {
      v30 = (PFLT_IO_PARAMETER_BLOCK)*((_QWORD *)CallbackData + 2);
      WPP_SF_ZZDDDDDDDI(
        WPP_GLOBAL_Control->AttachedDevice,
        (_DWORD)v30,
        v30->OperationFlags,
        (_DWORD)FileNameInformation + 8,
        (__int64)P,
        v15,
        Length,
        v30->OperationFlags,
        v30->Parameters.Read.ByteOffset.LowPart,
        v30->Parameters.Create.EaLength,
        v28,
        v28,
        v29);
    }
    if ( (_DWORD)Length && v6 )
      memmove(v6, EaBuffer, Length);
    goto LABEL_84;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
  {
    v52 = KeGetCurrentThread();
    WPP_SF_qZZD(
      WPP_GLOBAL_Control->AttachedDevice,
      30,
      File,
      (_DWORD)v52,
      (__int64)v16,
      (__int64)&FileNameInformation->Name,
      File);
  }
  if ( P )
  {
    ExFreePoolWithTag(P, 0x666E504Du);
    P = 0;
  }
  NetworkRedirectionInfo = MpGetDlpDefaultStubFileName(v41, &P, v18);
  v39 = NetworkRedirectionInfo;
  if ( NetworkRedirectionInfo >= 0 )
  {
    LODWORD(v61[0]) = 48;
    v61[1] = 0;
    DWORD2(v62) = 576;
    v19 = P;
    *(_QWORD *)&v62 = P;
    v63 = 0;
    v20 = MpFltCreateFileEx(
            *(_QWORD *)(MpData + 16),
            *(_QWORD *)v41,
            (int)&FileHandle,
            (int)&FileObject,
            0x100008u,
            (__int64)v61,
            (__int64)&v66,
            EaIndexa,
            0x80u,
            7u,
            3u,
            0x40u,
            v34,
            v36,
            0);
    v39 = v20;
    if ( v20 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      {
        v54 = KeGetCurrentThread();
        WPP_SF_qZZD(
          WPP_GLOBAL_Control->AttachedDevice,
          32,
          v20,
          (_DWORD)v54,
          (__int64)v19,
          (__int64)&FileNameInformation->Name,
          v20);
      }
      goto LABEL_84;
    }
    goto LABEL_60;
  }
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
    goto LABEL_84;
  v13 = KeGetCurrentThread();
  v53 = v13;
  v14 = 31;
LABEL_24:
  WPP_SF_qD(
    WPP_GLOBAL_Control->AttachedDevice,
    v14,
    WPP_ad635a2cae0e32a661f87ad0f41c83aa_Traceguids,
    v13,
    NetworkRedirectionInfo);
LABEL_84:
  if ( FileHandle )
    FltClose(FileHandle);
  if ( FileObject )
  {
    ObfDereferenceObject(FileObject);
    if ( _InterlockedDecrement64(&ObTotalReferences) < 0 && *(int *)(MpData + 868) < 0 )
    {
      if ( KdRefreshDebuggerNotPresent() )
        KeBugCheck(1u);
      __debugbreak();
    }
  }
  if ( v41 )
    MpDlpReleaseNetworkRedirectionInfo(v41);
  if ( P )
    ExFreePoolWithTag(P, 0x666E504Du);
  if ( FileNameInformation )
    FltReleaseFileNameInformation(FileNameInformation);
  if ( v37 )
    ExFreePoolWithTag(EaBuffer, 0x6165504Du);
}

```

## disassembly

```asm
0x140066dc0  mov     r11, rsp
0x140066dc3  push    rbx
0x140066dc4  push    rsi
0x140066dc5  push    rdi
0x140066dc6  push    r12
0x140066dc8  push    r13
0x140066dca  push    r14
0x140066dcc  push    r15
0x140066dce  sub     rsp, 190h
0x140066dd5  mov     rax, cs:__security_cookie
0x140066ddc  xor     rax, rsp
0x140066ddf  mov     [rsp+1C8h+var_48], rax
0x140066de7  mov     [rsp+1C8h+var_120], r8
0x140066def  mov     r15, rdx
0x140066df2  mov     r14, rcx
0x140066df5  mov     [rsp+1C8h+var_118], rcx
0x140066dfd  xor     ebx, ebx
0x140066dff  mov     [r11-60h], ebx
0x140066e03  mov     [rsp+1C8h+var_147], bl
0x140066e0a  mov     [r11-138h], rbx
0x140066e11  mov     edi, ebx
0x140066e13  mov     [r11-130h], rbx
0x140066e1a  mov     r13d, ebx
0x140066e1d  mov     [r11-110h], rbx
0x140066e24  mov     [r11-98h], rbx
0x140066e2b  xor     ecx, ecx
0x140066e2d  xorps   xmm0, xmm0
0x140066e30  movups  xmmword ptr [rsp+1C8h+var_90], xmm0
0x140066e38  movups  xmmword ptr [r11-80h], xmm0
0x140066e3d  mov     [r11-70h], rcx
0x140066e41  mov     [r11-68h], ecx
0x140066e45  movups  xmmword ptr [r11-58h], xmm0
0x140066e4a  mov     [r11-140h], rbx
0x140066e51  mov     [r11-0A8h], rbx
0x140066e58  mov     [r11-0A0h], rbx
0x140066e5f  mov     [r11-5Ch], ebx
0x140066e63  mov     [rsp+1C8h+var_148], cl
0x140066e6a  mov     [r8], cl
0x140066e6d  mov     rax, cs:MpDlpData
0x140066e74  movzx   ecx, byte ptr [rax+0F1h]
0x140066e7b  test    cl, cl
0x140066e7d  jz      short loc_140066EFB
0x140066e7f  lea     rdx, [r11-60h]; FileSystemType
0x140066e83  mov     rcx, [r15+18h]; FltObject
0x140066e87  call    cs:__imp_FltGetFileSystemType
0x140066e8e  nop     dword ptr [rax+rax+00h]
0x140066e93  test    eax, eax
0x140066e95  js      short loc_140066EFB
0x140066e97  cmp     [rsp+1C8h+var_60], 0Dh
0x140066e9f  jnz     short loc_140066EFB
0x140066ea1  lea     r8, [rsp+1C8h+var_147]
0x140066ea9  xor     edx, edx
0x140066eab  mov     rcx, r15
0x140066eae  call    MpIsLoopbackByObj
0x140066eb3  test    eax, eax
0x140066eb5  jns     short loc_140066F1F
0x140066eb7  lea     rbx, WPP_GLOBAL_Control
0x140066ebe  mov     rcx, cs:WPP_GLOBAL_Control
0x140066ec5  cmp     rcx, rbx
0x140066ec8  jz      short loc_140066EFB
0x140066eca  mov     ecx, [rcx+2Ch]
0x140066ecd  test    cl, 1
0x140066ed0  jz      short loc_140066EFB
0x140066ed2  mov     r9, gs:188h
0x140066edb  mov     edx, 16h
0x140066ee0  mov     [rsp+1C8h+BugCheckOnFailure], eax
0x140066ee4  lea     r8, WPP_ad635a2cae0e32a661f87ad0f41c83aa_Traceguids
0x140066eeb  mov     rcx, cs:WPP_GLOBAL_Control
0x140066ef2  mov     rcx, [rcx+18h]
0x140066ef6  call    WPP_SF_qD
0x140066efb  mov     rcx, [rsp+1C8h+var_48]
0x140066f03  xor     rcx, rsp; StackCookie
0x140066f06  call    __security_check_cookie
0x140066f0b  add     rsp, 190h
0x140066f12  pop     r15
0x140066f14  pop     r14
0x140066f16  pop     r13
0x140066f18  pop     r12
0x140066f1a  pop     rdi
0x140066f1b  pop     rsi
0x140066f1c  pop     rbx
0x140066f1d  retn
0x140066f1f  cmp     [rsp+1C8h+var_147], bl
0x140066f26  jz      short loc_140066F3A
0x140066f28  mov     rax, cs:MpData
0x140066f2f  mov     ecx, [rax+100Ch]
0x140066f35  test    cl, 4
0x140066f38  jz      short loc_140066EFB
0x140066f3a  mov     rax, [r14+10h]
0x140066f3e  mov     rsi, [rax+20h]
0x140066f42  test    rsi, rsi
0x140066f45  jz      loc_140067041
0x140066f4b  cmp     dword ptr [rsi], 0
0x140066f4e  jnz     short loc_140066EFB
0x140066f50  add     rsi, 5
0x140066f54  lea     rdx, aKernelSecEndpo; "$Kernel.SEC.EndpointDlp"
0x140066f5b  mov     rcx, rsi; Str1
0x140066f5e  call    cs:__imp__stricmp
0x140066f65  nop     dword ptr [rax+rax+00h]
0x140066f6a  test    eax, eax
0x140066f6c  jz      loc_140066FFB
0x140066f72  lea     rdx, Str2; "$Kernel.SEC.MarkOfWeb"
0x140066f79  mov     rcx, rsi; Str1
0x140066f7c  call    cs:__imp__stricmp
0x140066f83  nop     dword ptr [rax+rax+00h]
0x140066f88  test    eax, eax
0x140066f8a  jz      short loc_140066FFB
0x140066f8c  lea     rdx, aKernelSecAppli; "$Kernel.SEC.ApplicationSource"
0x140066f93  mov     rcx, rsi; Str1
0x140066f96  call    cs:__imp__stricmp
0x140066f9d  nop     dword ptr [rax+rax+00h]
0x140066fa2  test    eax, eax
0x140066fa4  jz      short loc_140066FFB
0x140066fa6  lea     rbx, WPP_GLOBAL_Control
0x140066fad  mov     rax, cs:WPP_GLOBAL_Control
0x140066fb4  cmp     rax, rbx
0x140066fb7  jz      short loc_140066FF6
0x140066fb9  mov     eax, [rax+2Ch]
0x140066fbc  test    al, 4
0x140066fbe  jz      short loc_140066FF6
0x140066fc0  lfence
0x140066fc3  mov     r9, gs:188h
0x140066fcc  mov     [rsp+1C8h+var_118], r9
0x140066fd4  mov     rax, [r15+20h]
0x140066fd8  add     rax, 58h ; 'X'
0x140066fdc  mov     qword ptr [rsp+1C8h+Priority], rax
0x140066fe1  mov     qword ptr [rsp+1C8h+BugCheckOnFailure], rsi
0x140066fe6  mov     rcx, cs:WPP_GLOBAL_Control
0x140066fed  mov     rcx, [rcx+18h]
0x140066ff1  call    WPP_SF_qsZ
0x140066ff6  jmp     loc_140066EFB
0x140066ffb  jmp     short loc_140067041
0x140066ffd  lea     rcx, WPP_GLOBAL_Control
0x140067004  mov     rax, cs:WPP_GLOBAL_Control
0x14006700b  cmp     rax, rcx
0x14006700e  jz      short loc_14006703C
0x140067010  mov     eax, [rax+2Ch]
0x140067013  test    al, 1
0x140067015  jz      short loc_14006703C
0x140067017  mov     r9, gs:188h
0x140067020  mov     edx, 18h
0x140067025  lea     r8, WPP_ad635a2cae0e32a661f87ad0f41c83aa_Traceguids
0x14006702c  mov     rcx, cs:WPP_GLOBAL_Control
0x140067033  mov     rcx, [rcx+18h]
0x140067037  call    WPP_SF_q
0x14006703c  jmp     loc_140066EFB
0x140067041  lea     rcx, [rsp+1C8h+var_138]
0x140067049  call    MpDlpGetNetworkRedirectionInfo
0x14006704e  mov     [rsp+1C8h+var_144], eax
0x140067055  test    eax, eax
0x140067057  jns     short loc_1400670B2
0x140067059  lea     rbx, WPP_GLOBAL_Control
0x140067060  mov     rcx, cs:WPP_GLOBAL_Control
0x140067067  cmp     rcx, rbx
0x14006706a  jz      loc_1400678DF
0x140067070  mov     ecx, [rcx+2Ch]
0x140067073  test    cl, 1
0x140067076  jz      loc_1400678DF
0x14006707c  mov     r9, gs:188h
0x140067085  mov     [rsp+1C8h+var_118], r9
0x14006708d  mov     edx, 19h
0x140067092  mov     [rsp+1C8h+BugCheckOnFailure], eax
0x140067096  lea     r8, WPP_ad635a2cae0e32a661f87ad0f41c83aa_Traceguids
0x14006709d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400670a4  mov     rcx, [rcx+18h]
0x1400670a8  call    WPP_SF_qD
0x1400670ad  jmp     loc_1400678DF
0x1400670b2  mov     ecx, 11Bh
0x1400670b7  call    MpFcKernelGetValue
0x1400670bc  test    al, 1
0x1400670be  jz      loc_140067173
0x1400670c4  mov     r12d, 1
0x1400670ca  lea     rbx, WPP_GLOBAL_Control
0x1400670d1  cmp     [rsp+1C8h+FileNameInformation], 0
0x1400670da  jnz     loc_140067246
0x1400670e0  lea     r8, [rsp+1C8h+FileNameInformation]; FileNameInformation
0x1400670e8  mov     edx, 102h; NameOptions
0x1400670ed  mov     rcx, r14; CallbackData
0x1400670f0  call    cs:__imp_FltGetFileNameInformation
0x1400670f7  nop     dword ptr [rax+rax+00h]
0x1400670fc  mov     [rsp+1C8h+var_144], eax
0x140067103  test    eax, eax
0x140067105  jns     loc_140067246
0x14006710b  mov     rax, cs:WPP_GLOBAL_Control
0x140067112  cmp     rax, rbx
0x140067115  jz      loc_1400678DF
0x14006711b  mov     eax, [rax+2Ch]
0x14006711e  test    al, 1
0x140067120  jz      loc_1400678DF
0x140067126  lfence
0x140067129  mov     r9, gs:188h
0x140067132  mov     [rsp+1C8h+var_F0], r9
0x14006713a  mov     rcx, [r15+20h]
0x14006713e  add     rcx, 58h ; 'X'
0x140067142  mov     edx, 1Bh
0x140067147  mov     eax, [rsp+1C8h+var_144]
0x14006714e  mov     [rsp+1C8h+Priority], eax
0x140067152  mov     qword ptr [rsp+1C8h+BugCheckOnFailure], rcx
0x140067157  lea     r8, WPP_ad635a2cae0e32a661f87ad0f41c83aa_Traceguids
0x14006715e  mov     rcx, cs:WPP_GLOBAL_Control
0x140067165  mov     rcx, [rcx+18h]
0x140067169  call    WPP_SF_qZd
0x14006716e  jmp     loc_1400678D7
0x140067173  lea     r8, [rsp+1C8h+FileNameInformation]; FileNameInformation
0x14006717b  mov     edx, 101h; NameOptions
0x140067180  mov     rcx, r14; CallbackData
0x140067183  call    cs:__imp_FltGetFileNameInformation
0x14006718a  nop     dword ptr [rax+rax+00h]
0x14006718f  mov     [rsp+1C8h+var_144], eax
0x140067196  mov     r12d, ebx
0x140067199  test    eax, eax
0x14006719b  jns     loc_1400670CA
0x1400671a1  mov     rcx, [rsp+1C8h+FileNameInformation]; FileNameInformation
0x1400671a9  test    rcx, rcx
0x1400671ac  jz      short loc_1400671C2
0x1400671ae  call    cs:__imp_FltReleaseFileNameInformation
0x1400671b5  nop     dword ptr [rax+rax+00h]
0x1400671ba  mov     [rsp+1C8h+FileNameInformation], rbx
0x1400671c2  mov     r12d, ebx
0x1400671c5  lea     rbx, WPP_GLOBAL_Control
0x1400671cc  mov     rax, cs:WPP_GLOBAL_Control
0x1400671d3  cmp     rax, rbx
0x1400671d6  jz      loc_1400670D1
0x1400671dc  xor     esi, esi
0x1400671de  mov     eax, [rax+2Ch]
0x1400671e1  test    al, 1
0x1400671e3  jz      loc_1400670D1
0x1400671e9  lfence
0x1400671ec  mov     r9, gs:188h
0x1400671f5  mov     [rsp+1C8h+var_F8], r9
0x1400671fd  mov     rcx, [r15+20h]
0x140067201  add     rcx, 58h ; 'X'
0x140067205  mov     edx, 1Ah
0x14006720a  mov     eax, [rsp+1C8h+var_144]
0x140067211  mov     [rsp+1C8h+Priority], eax
0x140067215  mov     qword ptr [rsp+1C8h+BugCheckOnFailure], rcx
0x14006721a  lea     r8, WPP_ad635a2cae0e32a661f87ad0f41c83aa_Traceguids
0x140067221  mov     rcx, cs:WPP_GLOBAL_Control
0x140067228  mov     rcx, [rcx+18h]
0x14006722c  call    WPP_SF_qZd
0x140067231  mov     rdi, [rsp+1C8h+var_130]
0x140067239  mov     r13, [rsp+1C8h+var_110]
0x140067241  jmp     loc_1400670D1
0x140067246  xorps   xmm0, xmm0
0x140067249  movups  [rsp+1C8h+var_108], xmm0
0x140067251  lea     rdx, [rsp+1C8h+var_108]
0x140067259  mov     rcx, [rsp+1C8h+FileNameInformation]; FileNameInformation
0x140067261  call    MpDlpGetNetworkRedirectFileNameToHash
0x140067266  mov     [rsp+1C8h+var_144], eax
0x14006726d  test    eax, eax
0x14006726f  jns     short loc_1400672A8
0x140067271  mov     rcx, cs:WPP_GLOBAL_Control
0x140067278  cmp     rcx, rbx
0x14006727b  jz      loc_1400678DF
0x140067281  mov     ecx, [rcx+2Ch]
0x140067284  test    cl, 1
0x140067287  jz      loc_1400678DF
0x14006728d  mov     r9, gs:188h
0x140067296  mov     [rsp+1C8h+var_E8], r9
0x14006729e  mov     edx, 1Ch
0x1400672a3  jmp     loc_140067092
0x1400672a8  lea     r8, [rsp+1C8h+P]
0x1400672b0  mov     rdx, [rsp+1C8h+var_138]
0x1400672b8  lea     rcx, [rsp+1C8h+var_108]
0x1400672c0  call    MpGetDlpStubFileNameForNetworkFile
0x1400672c5  mov     [rsp+1C8h+var_144], eax
0x1400672cc  test    eax, eax
0x1400672ce  jns     short loc_140067307
0x1400672d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400672d7  cmp     rcx, rbx
0x1400672da  jz      loc_1400678DF
0x1400672e0  mov     ecx, [rcx+2Ch]
0x1400672e3  test    cl, 1
0x1400672e6  jz      loc_1400678DF
0x1400672ec  mov     r9, gs:188h
0x1400672f5  mov     [rsp+1C8h+var_E0], r9
0x1400672fd  mov     edx, 1Dh
0x140067302  jmp     loc_140067092
0x140067307  mov     dword ptr [rsp+1C8h+var_90], 30h ; '0'
0x140067312  xor     eax, eax
0x140067314  mov     [rsp+1C8h+var_90+8], rax
0x14006731c  mov     [rsp+1C8h+var_78], 240h
0x140067327  mov     rsi, [rsp+1C8h+P]
0x14006732f  mov     [rsp+1C8h+var_80], rsi
0x140067337  xorps   xmm0, xmm0
0x14006733a  movdqu  [rsp+1C8h+var_70], xmm0
0x140067343  mov     [rsp+1C8h+var_158], eax; ULONG
0x140067347  mov     [rsp+1C8h+var_170], 40h ; '@'; ULONG
0x14006734f  mov     [rsp+1C8h+var_178], 1; ULONG
0x140067357  mov     dword ptr [rsp+1C8h+LengthReturned], 7; ULONG
0x14006735f  mov     dword ptr [rsp+1C8h+RestartScan], 80h; ULONG
0x140067367  lea     rax, [rsp+1C8h+var_58]
0x14006736f  mov     qword ptr [rsp+1C8h+EaListLength], rax; __int64
0x140067374  lea     rax, [rsp+1C8h+var_90]
0x14006737c  mov     qword ptr [rsp+1C8h+Priority], rax; __int64
0x140067381  mov     [rsp+1C8h+BugCheckOnFailure], 100008h; ACCESS_MASK
0x140067389  lea     r9, [rsp+1C8h+FileObject]; int
0x140067391  lea     r8, [rsp+1C8h+FileHandle]; int
0x140067399  mov     rdx, [rsp+1C8h+var_138]
0x1400673a1  mov     rdx, [rdx]; int
  ... truncated ...
```
