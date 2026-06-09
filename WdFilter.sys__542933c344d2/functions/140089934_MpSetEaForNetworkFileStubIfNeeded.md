# MpSetEaForNetworkFileStubIfNeeded

- ea: `0x140089934`
- end: `0x14008a1a4`
- name: `MpSetEaForNetworkFileStubIfNeeded`
- size: `2160`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops`

## callers

- `0x140047ad0`

## callees

- `0x140003d20`
- `0x140004530`
- `0x140004e4c`
- `0x1400051bc`
- `0x140005228`
- `0x14000aa0c`
- `0x14000b704`
- `0x140011890`
- `0x1400118d0`
- `0x140050290`
- `0x14007156c`
- `0x1400732c0`
- `0x140073684`
- `0x1400794b8`
- `0x140089794`
- `0x140089934`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140089f7e`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140089f7e`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x14008a11a`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x14008d1f8`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x14008a11a`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x14008d1f8`
- `ntoskrnl!KeBugCheck` at `0x14008a197`
- `ntoskrnl!KeBugCheck` at `0x14008d210`
- `ntoskrnl!KeBugCheck` at `0x14008a197`
- `ntoskrnl!KeBugCheck` at `0x14008d210`
- `ntoskrnl!ObfDereferenceObject` at `0x14008a0ea`
- `ntoskrnl!ObfDereferenceObject` at `0x14008d1c8`
- `ntoskrnl!ObfDereferenceObject` at `0x14008a0ea`
- `ntoskrnl!ObfDereferenceObject` at `0x14008d1c8`
- `FLTMGR!FltGetFileNameInformation` at `0x140089b90`
- `FLTMGR!FltGetFileNameInformation` at `0x140089c55`
- `FLTMGR!FltGetFileNameInformation` at `0x140089b90`
- `FLTMGR!FltGetFileNameInformation` at `0x140089c55`
- `FLTMGR!FltWriteFile` at `0x140089ed6`
- `FLTMGR!FltWriteFile` at `0x140089ed6`
- `FLTMGR!FltGetFileSystemType` at `0x140089a52`
- `FLTMGR!FltGetFileSystemType` at `0x140089a52`
- `FLTMGR!FltClose` at `0x14008a138`
- `FLTMGR!FltClose` at `0x14008d229`
- `FLTMGR!FltClose` at `0x14008a138`
- `FLTMGR!FltClose` at `0x14008d229`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140089bb8`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14008a181`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14008d26b`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140089bb8`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14008a181`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14008d26b`

## pseudocode

```c
__int64 __fastcall MpSetEaForNetworkFileStubIfNeeded(PFLT_CALLBACK_DATA CallbackData, __int64 a2, _BYTE *a3)
{
  int IsLoopbackByObj; // eax
  NTSTATUS NetworkRedirectionInfo; // ebx
  struct _KTHREAD *CurrentThread; // r9
  __int64 v10; // rdx
  struct _KTHREAD *v11; // r9
  __int64 v12; // rax
  int v13; // edx
  __int64 v14; // rsi
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  PVOID EaList; // rdx
  LARGE_INTEGER v17; // rcx
  PVOID v18; // rax
  ULONG Length; // esi
  int v20; // r8d
  int CallbackRoutine; // [rsp+38h] [rbp-170h]
  int v22; // [rsp+60h] [rbp-148h]
  int v23; // [rsp+68h] [rbp-140h]
  NTSTATUS v24; // [rsp+80h] [rbp-128h]
  char v25[4]; // [rsp+84h] [rbp-124h] BYREF
  __int64 v26; // [rsp+88h] [rbp-120h] BYREF
  PVOID P; // [rsp+90h] [rbp-118h] BYREF
  ULONG v28; // [rsp+98h] [rbp-110h]
  PVOID v29; // [rsp+A0h] [rbp-108h]
  PVOID v30; // [rsp+A8h] [rbp-100h]
  __int128 v31; // [rsp+B0h] [rbp-F8h] BYREF
  struct _KTHREAD *v32; // [rsp+C0h] [rbp-E8h]
  struct _KTHREAD *v33; // [rsp+C8h] [rbp-E0h]
  struct _KTHREAD *v34; // [rsp+D0h] [rbp-D8h]
  struct _KTHREAD *v35; // [rsp+D8h] [rbp-D0h]
  struct _KTHREAD *v36; // [rsp+E0h] [rbp-C8h]
  struct _KTHREAD *v37; // [rsp+E8h] [rbp-C0h]
  struct _KTHREAD *v38; // [rsp+F0h] [rbp-B8h]
  PVOID v39; // [rsp+F8h] [rbp-B0h]
  struct _KTHREAD *v40; // [rsp+100h] [rbp-A8h]
  struct _KTHREAD *v41; // [rsp+108h] [rbp-A0h]
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+110h] [rbp-98h] BYREF
  PFILE_OBJECT FileObject; // [rsp+118h] [rbp-90h] BYREF
  HANDLE FileHandle; // [rsp+120h] [rbp-88h] BYREF
  __int128 v45; // [rsp+128h] [rbp-80h] BYREF
  __int128 v46; // [rsp+138h] [rbp-70h]
  __int128 v47; // [rsp+148h] [rbp-60h]
  enum _FLT_FILESYSTEM_TYPE FileSystemType; // [rsp+158h] [rbp-50h] BYREF
  union _LARGE_INTEGER ByteOffset; // [rsp+160h] [rbp-48h] BYREF
  __int128 v50; // [rsp+168h] [rbp-40h] BYREF

  FileSystemType = FLT_FSTYPE_UNKNOWN;
  v25[0] = 0;
  FileNameInformation = 0;
  FileHandle = 0;
  FileObject = 0;
  v45 = 0;
  v46 = 0;
  v47 = 0;
  v50 = 0;
  v26 = 0;
  ByteOffset.QuadPart = 0;
  P = 0;
  *a3 = 0;
  if ( !*(_QWORD *)(MpData + 152) )
    return 3221225659LL;
  if ( !*((_BYTE *)MpDlpData + 241) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        37,
        WPP_ad635a2cae0e32a661f87ad0f41c83aa_Traceguids,
        KeGetCurrentThread());
    return 0;
  }
  if ( FltGetFileSystemType(*(PVOID *)(a2 + 24), &FileSystemType) < 0 || FileSystemType != FLT_FSTYPE_MUP )
    return 0;
  IsLoopbackByObj = MpIsLoopbackByObj(a2, 0, v25);
  NetworkRedirectionInfo = IsLoopbackByObj;
  if ( IsLoopbackByObj >= 0 )
  {
    if ( !v25[0] || (MpFcKernelGetValue(283) & 4) != 0 )
    {
      NetworkRedirectionInfo = MpDlpGetNetworkRedirectionInfo(&P);
      if ( NetworkRedirectionInfo < 0 )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          goto LABEL_68;
        CurrentThread = KeGetCurrentThread();
        v32 = CurrentThread;
        v10 = 39;
        goto LABEL_21;
      }
      if ( (MpFcKernelGetValue(283) & 1) == 0 )
      {
        v24 = FltGetFileNameInformation(CallbackData, 0x101u, &FileNameInformation);
        if ( v24 < 0 )
        {
          if ( FileNameInformation )
          {
            FltReleaseFileNameInformation(FileNameInformation);
            FileNameInformation = 0;
          }
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          {
            _mm_lfence();
            v33 = KeGetCurrentThread();
            WPP_SF_qZd(
              WPP_GLOBAL_Control->AttachedDevice,
              40,
              (unsigned int)WPP_ad635a2cae0e32a661f87ad0f41c83aa_Traceguids,
              (_DWORD)v33,
              *(_QWORD *)(a2 + 32) + 88LL,
              v24);
          }
        }
      }
      if ( !FileNameInformation )
      {
        NetworkRedirectionInfo = FltGetFileNameInformation(CallbackData, 0x102u, &FileNameInformation);
        if ( NetworkRedirectionInfo < 0 )
        {
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          {
            goto LABEL_68;
          }
          _mm_lfence();
          v11 = KeGetCurrentThread();
          v34 = v11;
          v12 = *(_QWORD *)(a2 + 32) + 88LL;
          v13 = 41;
          goto LABEL_34;
        }
      }
      v31 = 0;
      NetworkRedirectionInfo = MpDlpGetNetworkRedirectFileNameToHash(FileNameInformation);
      if ( NetworkRedirectionInfo >= 0 )
      {
        NetworkRedirectionInfo = MpGetDlpStubFileNameForNetworkFile(&v31, P, &v26);
        if ( NetworkRedirectionInfo >= 0 )
        {
          LODWORD(v45) = 48;
          *((_QWORD *)&v45 + 1) = 0;
          DWORD2(v46) = 576;
          v14 = v26;
          *(_QWORD *)&v46 = v26;
          v47 = 0;
          NetworkRedirectionInfo = MpFltCreateFileEx(
                                     *(_QWORD *)(MpData + 16),
                                     *(_QWORD *)P,
                                     (int)&FileHandle,
                                     (int)&FileObject,
                                     0x100012u,
                                     (__int64)&v45,
                                     (__int64)&v50,
                                     CallbackRoutine,
                                     0x80u,
                                     7u,
                                     3u,
                                     0x40u,
                                     v22,
                                     v23,
                                     0);
          if ( NetworkRedirectionInfo < 0 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
            {
              v37 = KeGetCurrentThread();
              WPP_SF_qZd(
                WPP_GLOBAL_Control->AttachedDevice,
                44,
                (unsigned int)WPP_ad635a2cae0e32a661f87ad0f41c83aa_Traceguids,
                (_DWORD)v37,
                v14,
                NetworkRedirectionInfo);
            }
            goto LABEL_68;
          }
          NetworkRedirectionInfo = FltWriteFile(
                                     *(PFLT_INSTANCE *)P,
                                     FileObject,
                                     &ByteOffset,
                                     FileNameInformation->Name.Length,
                                     FileNameInformation->Name.Buffer,
                                     0,
                                     0,
                                     0,
                                     0);
          if ( NetworkRedirectionInfo >= 0 )
          {
            Iopb = CallbackData->Iopb;
            EaList = Iopb->Parameters.QueryEa.EaList;
            v29 = EaList;
            v17 = Iopb->Parameters.Read.ByteOffset;
            if ( v17.QuadPart )
            {
              if ( (*(_BYTE *)(v17.QuadPart + 10) & 5) != 0 )
              {
                EaList = *(PVOID *)(v17.QuadPart + 24);
                v30 = EaList;
                v18 = EaList;
              }
              else
              {
                v18 = MmMapLockedPagesSpecifyCache(
                        (PMDL)v17.QuadPart,
                        0,
                        MmCached,
                        0,
                        0,
                        ExDefaultMdlProtection | 0x40000010u);
                EaList = v18;
                v39 = v18;
                v30 = v18;
              }
              v29 = EaList;
              if ( !v18 )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
                {
                  v40 = KeGetCurrentThread();
                  WPP_SF_qq(
                    WPP_GLOBAL_Control->AttachedDevice,
                    46,
                    (unsigned int)WPP_ad635a2cae0e32a661f87ad0f41c83aa_Traceguids,
                    (_DWORD)v40,
                    CallbackData->Iopb->Parameters.Read.ByteOffset.QuadPart);
                }
                goto LABEL_68;
              }
            }
            Length = CallbackData->Iopb->Parameters.Read.Length;
            v28 = Length;
            NetworkRedirectionInfo = (*(__int64 (__fastcall **)(PFILE_OBJECT, PVOID, _QWORD))(MpData + 152))(
                                       FileObject,
                                       EaList,
                                       Length);
            if ( NetworkRedirectionInfo >= 0 )
            {
              *a3 = 1;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
              {
                *(_QWORD *)&v31 = KeGetCurrentThread();
                WPP_SF_qZZD(
                  WPP_GLOBAL_Control->AttachedDevice,
                  48,
                  v20,
                  v31,
                  v26,
                  (__int64)&FileNameInformation->Name,
                  Length);
              }
              NetworkRedirectionInfo = 0;
              goto LABEL_68;
            }
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
            {
LABEL_68:
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
              if ( FileHandle )
                FltClose(FileHandle);
              if ( P )
                MpDlpReleaseNetworkRedirectionInfo(P);
              if ( v26 )
                MpFreeWithTag(v26, 1718505549);
              if ( FileNameInformation )
                FltReleaseFileNameInformation(FileNameInformation);
              return (unsigned int)NetworkRedirectionInfo;
            }
            v11 = KeGetCurrentThread();
            v41 = v11;
            v13 = 47;
          }
          else
          {
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
            {
              goto LABEL_68;
            }
            v11 = KeGetCurrentThread();
            v38 = v11;
            v13 = 45;
          }
          v12 = v26;
LABEL_34:
          WPP_SF_qZd(
            WPP_GLOBAL_Control->AttachedDevice,
            v13,
            (unsigned int)WPP_ad635a2cae0e32a661f87ad0f41c83aa_Traceguids,
            (_DWORD)v11,
            v12,
            NetworkRedirectionInfo);
          goto LABEL_68;
        }
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          goto LABEL_68;
        CurrentThread = KeGetCurrentThread();
        v36 = CurrentThread;
        v10 = 43;
      }
      else
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          goto LABEL_68;
        CurrentThread = KeGetCurrentThread();
        v35 = CurrentThread;
        v10 = 42;
      }
LABEL_21:
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        v10,
        WPP_ad635a2cae0e32a661f87ad0f41c83aa_Traceguids,
        CurrentThread,
        NetworkRedirectionInfo);
      goto LABEL_68;
    }
    return 0;
  }
  _mm_lfence();
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    WPP_SF_qD(
      WPP_GLOBAL_Control->AttachedDevice,
      38,
      WPP_ad635a2cae0e32a661f87ad0f41c83aa_Traceguids,
      KeGetCurrentThread(),
      IsLoopbackByObj);
  return (unsigned int)NetworkRedirectionInfo;
}

```

## disassembly

```asm
0x140089934  mov     r11, rsp
0x140089937  mov     [r11+20h], rbx
0x14008993b  push    rsi
0x14008993c  push    rdi
0x14008993d  push    r12
0x14008993f  push    r14
0x140089941  push    r15
0x140089943  sub     rsp, 180h
0x14008994a  mov     rax, cs:__security_cookie
0x140089951  xor     rax, rsp
0x140089954  mov     [rsp+1A8h+var_30], rax
0x14008995c  mov     r15, r8
0x14008995f  mov     rsi, rdx
0x140089962  mov     r14, rcx
0x140089965  xor     r12d, r12d
0x140089968  mov     [r11-50h], r12d
0x14008996c  mov     [r11-124h], r12b
0x140089973  mov     [r11-98h], r12
0x14008997a  mov     [r11-88h], r12
0x140089981  mov     [r11-90h], r12
0x140089988  xorps   xmm0, xmm0
0x14008998b  movups  xmmword ptr [r11-80h], xmm0
0x140089990  movups  xmmword ptr [r11-70h], xmm0
0x140089995  movups  xmmword ptr [r11-60h], xmm0
0x14008999a  movups  xmmword ptr [r11-40h], xmm0
0x14008999f  mov     [r11-120h], r12
0x1400899a6  mov     [r11-48h], r12
0x1400899aa  mov     [r11-118h], r12
0x1400899b1  mov     [r8], r12b
0x1400899b4  mov     rax, cs:MpData
0x1400899bb  cmp     [rax+98h], r12
0x1400899c2  jnz     short loc_1400899CB
0x1400899c4  mov     eax, 0C00000BBh
0x1400899c9  jmp     short loc_140089A1D
0x1400899cb  mov     rax, cs:MpDlpData
0x1400899d2  mov     cl, [rax+0F1h]
0x1400899d8  test    cl, cl
0x1400899da  jnz     short loc_140089A46
0x1400899dc  lea     rdi, WPP_GLOBAL_Control
0x1400899e3  mov     rax, cs:WPP_GLOBAL_Control
0x1400899ea  cmp     rax, rdi
0x1400899ed  jz      short loc_140089A1B
0x1400899ef  mov     eax, [rax+2Ch]
0x1400899f2  test    al, 4
0x1400899f4  jz      short loc_140089A1B
0x1400899f6  mov     r9, gs:188h
0x1400899ff  mov     edx, 25h ; '%'
0x140089a04  lea     r8, WPP_ad635a2cae0e32a661f87ad0f41c83aa_Traceguids
0x140089a0b  mov     rcx, cs:WPP_GLOBAL_Control
0x140089a12  mov     rcx, [rcx+18h]
0x140089a16  call    WPP_SF_q
0x140089a1b  xor     eax, eax
0x140089a1d  mov     rcx, [rsp+1A8h+var_30]
0x140089a25  xor     rcx, rsp; StackCookie
0x140089a28  call    __security_check_cookie
0x140089a2d  mov     rbx, [rsp+1A8h+arg_18]
0x140089a35  add     rsp, 180h
0x140089a3c  pop     r15
0x140089a3e  pop     r14
0x140089a40  pop     r12
0x140089a42  pop     rdi
0x140089a43  pop     rsi
0x140089a44  retn
0x140089a46  lea     rdx, [rsp+1A8h+FileSystemType]; FileSystemType
0x140089a4e  mov     rcx, [rsi+18h]; FltObject
0x140089a52  call    cs:__imp_FltGetFileSystemType
0x140089a59  nop     dword ptr [rax+rax+00h]
0x140089a5e  test    eax, eax
0x140089a60  js      short loc_140089A1B
0x140089a62  cmp     [rsp+1A8h+FileSystemType], 0Dh
0x140089a6a  jnz     short loc_140089A1B
0x140089a6c  lea     r8, [rsp+1A8h+var_124]
0x140089a74  xor     edx, edx
0x140089a76  mov     rcx, rsi
0x140089a79  call    MpIsLoopbackByObj
0x140089a7e  mov     ebx, eax
0x140089a80  mov     [rsp+1A8h+var_128], eax
0x140089a87  test    eax, eax
0x140089a89  jns     short loc_140089AE0
0x140089a8b  lfence
0x140089a8e  lea     rdi, WPP_GLOBAL_Control
0x140089a95  mov     rcx, cs:WPP_GLOBAL_Control
0x140089a9c  cmp     rcx, rdi
0x140089a9f  jz      short loc_140089AD9
0x140089aa1  mov     ecx, [rcx+2Ch]
0x140089aa4  test    cl, 1
0x140089aa7  jz      short loc_140089AD9
0x140089aa9  mov     r9, gs:188h
0x140089ab2  mov     edx, 26h ; '&'
0x140089ab7  mov     eax, [rsp+1A8h+var_128]
0x140089abe  mov     dword ptr [rsp+1A8h+Buffer], eax
0x140089ac2  lea     r8, WPP_ad635a2cae0e32a661f87ad0f41c83aa_Traceguids
0x140089ac9  mov     rcx, cs:WPP_GLOBAL_Control
0x140089ad0  mov     rcx, [rcx+18h]
0x140089ad4  call    WPP_SF_qD
0x140089ad9  mov     eax, ebx
0x140089adb  jmp     loc_140089A1D
0x140089ae0  cmp     [rsp+1A8h+var_124], r12b
0x140089ae8  jz      short loc_140089AFC
0x140089aea  mov     ecx, 11Bh
0x140089aef  call    MpFcKernelGetValue
0x140089af4  test    al, 4
0x140089af6  jz      loc_140089A1B
0x140089afc  lea     rcx, [rsp+1A8h+P]
0x140089b04  call    MpDlpGetNetworkRedirectionInfo
0x140089b09  mov     ebx, eax
0x140089b0b  mov     [rsp+1A8h+var_128], eax
0x140089b12  test    eax, eax
0x140089b14  jns     short loc_140089B6E
0x140089b16  lea     rdi, WPP_GLOBAL_Control
0x140089b1d  mov     rax, cs:WPP_GLOBAL_Control
0x140089b24  cmp     rax, rdi
0x140089b27  jz      loc_14008A0DD
0x140089b2d  mov     eax, [rax+2Ch]
0x140089b30  test    al, 1
0x140089b32  jz      loc_14008A0DD
0x140089b38  mov     r9, gs:188h
0x140089b41  mov     [rsp+1A8h+var_E8], r9
0x140089b49  mov     edx, 27h ; '''
0x140089b4e  mov     dword ptr [rsp+1A8h+Buffer], ebx
0x140089b52  lea     r8, WPP_ad635a2cae0e32a661f87ad0f41c83aa_Traceguids
0x140089b59  mov     rcx, cs:WPP_GLOBAL_Control
0x140089b60  mov     rcx, [rcx+18h]
0x140089b64  call    WPP_SF_qD
0x140089b69  jmp     loc_14008A0DD
0x140089b6e  mov     ecx, 11Bh
0x140089b73  call    MpFcKernelGetValue
0x140089b78  test    al, 1
0x140089b7a  jnz     loc_140089C30
0x140089b80  lea     r8, [rsp+1A8h+FileNameInformation]; FileNameInformation
0x140089b88  mov     edx, 101h; NameOptions
0x140089b8d  mov     rcx, r14; CallbackData
0x140089b90  call    cs:__imp_FltGetFileNameInformation
0x140089b97  nop     dword ptr [rax+rax+00h]
0x140089b9c  mov     [rsp+1A8h+var_128], eax
0x140089ba3  test    eax, eax
0x140089ba5  jns     loc_140089C30
0x140089bab  mov     rcx, [rsp+1A8h+FileNameInformation]; FileNameInformation
0x140089bb3  test    rcx, rcx
0x140089bb6  jz      short loc_140089BCC
0x140089bb8  call    cs:__imp_FltReleaseFileNameInformation
0x140089bbf  nop     dword ptr [rax+rax+00h]
0x140089bc4  mov     [rsp+1A8h+FileNameInformation], r12
0x140089bcc  lea     rdi, WPP_GLOBAL_Control
0x140089bd3  mov     rax, cs:WPP_GLOBAL_Control
0x140089bda  cmp     rax, rdi
0x140089bdd  jz      short loc_140089C37
0x140089bdf  mov     eax, [rax+2Ch]
0x140089be2  test    al, 1
0x140089be4  jz      short loc_140089C37
0x140089be6  lfence
0x140089be9  mov     r9, gs:188h
0x140089bf2  mov     [rsp+1A8h+var_E0], r9
0x140089bfa  mov     rcx, [rsi+20h]
0x140089bfe  add     rcx, 58h ; 'X'
0x140089c02  mov     edx, 28h ; '('
0x140089c07  mov     eax, [rsp+1A8h+var_128]
0x140089c0e  mov     [rsp+1A8h+Flags], eax
0x140089c12  mov     [rsp+1A8h+Buffer], rcx
0x140089c17  lea     r8, WPP_ad635a2cae0e32a661f87ad0f41c83aa_Traceguids
0x140089c1e  mov     rcx, cs:WPP_GLOBAL_Control
0x140089c25  mov     rcx, [rcx+18h]
0x140089c29  call    WPP_SF_qZd
0x140089c2e  jmp     short loc_140089C37
0x140089c30  lea     rdi, WPP_GLOBAL_Control
0x140089c37  cmp     [rsp+1A8h+FileNameInformation], r12
0x140089c3f  jnz     loc_140089CD6
0x140089c45  lea     r8, [rsp+1A8h+FileNameInformation]; FileNameInformation
0x140089c4d  mov     edx, 102h; NameOptions
0x140089c52  mov     rcx, r14; CallbackData
0x140089c55  call    cs:__imp_FltGetFileNameInformation
0x140089c5c  nop     dword ptr [rax+rax+00h]
0x140089c61  mov     ebx, eax
0x140089c63  mov     [rsp+1A8h+var_128], eax
0x140089c6a  test    eax, eax
0x140089c6c  jns     short loc_140089CD6
0x140089c6e  mov     rax, cs:WPP_GLOBAL_Control
0x140089c75  cmp     rax, rdi
0x140089c78  jz      loc_14008A0DD
0x140089c7e  mov     eax, [rax+2Ch]
0x140089c81  test    al, 1
0x140089c83  jz      loc_14008A0DD
0x140089c89  lfence
0x140089c8c  mov     r9, gs:188h
0x140089c95  mov     [rsp+1A8h+var_D8], r9
0x140089c9d  mov     rax, [rsi+20h]
0x140089ca1  add     rax, 58h ; 'X'
0x140089ca5  mov     edx, 29h ; ')'
0x140089caa  mov     ebx, [rsp+1A8h+var_128]
0x140089cb1  mov     [rsp+1A8h+Flags], ebx
0x140089cb5  mov     [rsp+1A8h+Buffer], rax
0x140089cba  lea     r8, WPP_ad635a2cae0e32a661f87ad0f41c83aa_Traceguids
0x140089cc1  mov     rcx, cs:WPP_GLOBAL_Control
0x140089cc8  mov     rcx, [rcx+18h]
0x140089ccc  call    WPP_SF_qZd
0x140089cd1  jmp     loc_14008A0DD
0x140089cd6  xorps   xmm0, xmm0
0x140089cd9  movups  [rsp+1A8h+var_F8], xmm0
0x140089ce1  lea     rdx, [rsp+1A8h+var_F8]
0x140089ce9  mov     rcx, [rsp+1A8h+FileNameInformation]; FileNameInformation
0x140089cf1  call    MpDlpGetNetworkRedirectFileNameToHash
0x140089cf6  mov     ebx, eax
0x140089cf8  mov     [rsp+1A8h+var_128], eax
0x140089cff  test    eax, eax
0x140089d01  jns     short loc_140089D39
0x140089d03  mov     rax, cs:WPP_GLOBAL_Control
0x140089d0a  cmp     rax, rdi
0x140089d0d  jz      loc_14008A0DD
0x140089d13  mov     eax, [rax+2Ch]
0x140089d16  test    al, 1
0x140089d18  jz      loc_14008A0DD
0x140089d1e  mov     r9, gs:188h
0x140089d27  mov     [rsp+1A8h+var_D0], r9
0x140089d2f  mov     edx, 2Ah ; '*'
0x140089d34  jmp     loc_140089B4E
0x140089d39  lea     r8, [rsp+1A8h+var_120]
0x140089d41  mov     rdx, [rsp+1A8h+P]
0x140089d49  lea     rcx, [rsp+1A8h+var_F8]
0x140089d51  call    MpGetDlpStubFileNameForNetworkFile
0x140089d56  mov     ebx, eax
0x140089d58  mov     [rsp+1A8h+var_128], eax
0x140089d5f  test    eax, eax
0x140089d61  jns     short loc_140089D99
0x140089d63  mov     rax, cs:WPP_GLOBAL_Control
0x140089d6a  cmp     rax, rdi
0x140089d6d  jz      loc_14008A0DD
0x140089d73  mov     eax, [rax+2Ch]
0x140089d76  test    al, 1
0x140089d78  jz      loc_14008A0DD
0x140089d7e  mov     r9, gs:188h
0x140089d87  mov     [rsp+1A8h+var_C8], r9
0x140089d8f  mov     edx, 2Bh ; '+'
0x140089d94  jmp     loc_140089B4E
0x140089d99  mov     dword ptr [rsp+1A8h+var_80], 30h ; '0'
0x140089da4  mov     [rsp+1A8h+var_78], r12
0x140089dac  mov     [rsp+1A8h+var_68], 240h
0x140089db7  mov     rsi, [rsp+1A8h+var_120]
0x140089dbf  mov     [rsp+1A8h+var_70], rsi
0x140089dc7  xorps   xmm0, xmm0
0x140089dca  movdqu  [rsp+1A8h+var_60], xmm0
0x140089dd3  mov     [rsp+1A8h+var_138], r12d; ULONG
0x140089dd8  mov     [rsp+1A8h+var_150], 40h ; '@'; ULONG
0x140089de0  mov     [rsp+1A8h+var_158], 3; ULONG
0x140089de8  mov     [rsp+1A8h+var_160], 7; ULONG
0x140089df0  mov     dword ptr [rsp+1A8h+CallbackContext], 80h; ULONG
0x140089df8  lea     rax, [rsp+1A8h+var_40]
0x140089e00  mov     [rsp+1A8h+BytesWritten], rax; __int64
0x140089e05  lea     rax, [rsp+1A8h+var_80]
0x140089e0d  mov     qword ptr [rsp+1A8h+Flags], rax; __int64
0x140089e12  mov     dword ptr [rsp+1A8h+Buffer], 100012h; ACCESS_MASK
0x140089e1a  lea     r9, [rsp+1A8h+FileObject]; int
0x140089e22  lea     r8, [rsp+1A8h+FileHandle]; int
0x140089e2a  mov     rdx, [rsp+1A8h+P]
0x140089e32  mov     rdx, [rdx]; int
0x140089e35  mov     rcx, cs:MpData
0x140089e3c  mov     rcx, [rcx+10h]; int
0x140089e40  call    MpFltCreateFileEx
0x140089e45  mov     ebx, eax
0x140089e47  mov     [rsp+1A8h+var_128], eax
0x140089e4e  test    eax, eax
0x140089e50  jns     short loc_140089E91
0x140089e52  mov     rax, cs:WPP_GLOBAL_Control
0x140089e59  cmp     rax, rdi
0x140089e5c  jz      loc_14008A0DD
0x140089e62  mov     eax, [rax+2Ch]
0x140089e65  test    al, 1
0x140089e67  jz      loc_14008A0DD
0x140089e6d  mov     r9, gs:188h
0x140089e76  mov     [rsp+1A8h+var_C0], r9
0x140089e7e  mov     edx, 2Ch ; ','
0x140089e83  mov     [rsp+1A8h+Flags], ebx
0x140089e87  mov     [rsp+1A8h+Buffer], rsi
0x140089e8c  jmp     loc_140089CBA
0x140089e91  mov     rax, [rsp+1A8h+FileNameInformation]
0x140089e99  movzx   r9d, word ptr [rax+8]; Length
0x140089e9e  mov     [rsp+1A8h+CallbackContext], r12; CallbackContext
0x140089ea3  mov     [rsp+1A8h+CallbackRoutine], r12; CallbackRoutine
0x140089ea8  mov     [rsp+1A8h+BytesWritten], r12; BytesWritten
0x140089ead  mov     [rsp+1A8h+Flags], r12d; Flags
0x140089eb2  mov     rax, [rax+10h]
0x140089eb6  mov     [rsp+1A8h+Buffer], rax; Buffer
0x140089ebb  lea     r8, [rsp+1A8h+ByteOffset]; ByteOffset
0x140089ec3  mov     rdx, [rsp+1A8h+FileObject]; FileObject
0x140089ecb  mov     rcx, [rsp+1A8h+P]
0x140089ed3  mov     rcx, [rcx]; InitiatingInstance
0x140089ed6  call    cs:__imp_FltWriteFile
0x140089edd  nop     dword ptr [rax+rax+00h]
0x140089ee2  mov     ebx, eax
0x140089ee4  mov     [rsp+1A8h+var_128], eax
0x140089eeb  test    eax, eax
0x140089eed  jns     short loc_140089F2D
0x140089eef  mov     rax, cs:WPP_GLOBAL_Control
0x140089ef6  cmp     rax, rdi
0x140089ef9  jz      loc_14008A0DD
0x140089eff  mov     eax, [rax+2Ch]
0x140089f02  test    al, 1
0x140089f04  jz      loc_14008A0DD
0x140089f0a  mov     r9, gs:188h
0x140089f13  mov     [rsp+1A8h+var_B8], r9
0x140089f1b  mov     edx, 2Dh ; '-'
  ... truncated ...
```
