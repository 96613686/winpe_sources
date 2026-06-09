# TieringPinnedSession::GetPinnedFilesListForDiskOptimizer(_STORAGE_TIER_CLASS,ulong,_TE_ENUM_INTERNAL_RESUME_KEY *,int *,long *,__MIDL___MIDL_itf_tieringengine_0000_0000_0005 * *)

- ea: `0x140022878`
- end: `0x1400237c1`
- name: `?GetPinnedFilesListForDiskOptimizer@TieringPinnedSession@@QEAAJW4_STORAGE_TIER_CLASS@@KPEAU_TE_ENUM_INTERNAL_RESUME_KEY@@PEAHPEAJPEAPEAU__MIDL___MIDL_itf_tieringengine_0000_0000_0005@@@Z`
- size: `3913`
- prototype: `__int64 __fastcall(TieringPinnedSession *this, enum _STORAGE_TIER_CLASS, unsigned int, struct _TE_ENUM_INTERNAL_RESUME_KEY *, int *, int *, struct __MIDL___MIDL_itf_tieringengine_0000_0000_0005 **)`
- caller_count: `1`
- callee_count: `20`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x14003ddd4`

## callees

- `0x14000136c`
- `0x140002323`
- `0x140002db0`
- `0x140004a68`
- `0x140004ef0`
- `0x140005420`
- `0x140009a04`
- `0x140009c08`
- `0x14000b7f8`
- `0x140017e78`
- `0x14001cd80`
- `0x14001f744`
- `0x140021018`
- `0x1400210c8`
- `0x140022878`
- `0x140025af0`
- `0x140025dd0`
- `0x140025e94`
- `0x14002d844`
- `0x14003fbb0`

## import_xrefs

- `msvcrt!free` at `0x140023049`
- `msvcrt!free` at `0x14002361e`
- `msvcrt!free` at `0x140023049`
- `msvcrt!free` at `0x14002361e`
- `ntdll!NtOpenFile` at `0x140022b9c`
- `ntdll!NtOpenFile` at `0x140022b9c`
- `ntdll!RtlGetThreadErrorMode` at `0x140022b2b`
- `ntdll!RtlGetThreadErrorMode` at `0x140022b2b`
- `ntdll!RtlSetThreadErrorMode` at `0x140022b3a`
- `ntdll!RtlSetThreadErrorMode` at `0x140022e24`
- `ntdll!RtlSetThreadErrorMode` at `0x14002363e`
- `ntdll!RtlSetThreadErrorMode` at `0x140022b3a`
- `ntdll!RtlSetThreadErrorMode` at `0x140022e24`
- `ntdll!RtlSetThreadErrorMode` at `0x14002363e`
- `ntdll!NtClose` at `0x140022e0f`
- `ntdll!NtClose` at `0x14002362d`
- `ntdll!NtClose` at `0x140022e0f`
- `ntdll!NtClose` at `0x14002362d`
- `ntdll!RtlCompareMemory` at `0x1400229d2`
- `ntdll!RtlCompareMemory` at `0x140022fac`
- `ntdll!RtlCompareMemory` at `0x1400229d2`
- `ntdll!RtlCompareMemory` at `0x140022fac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400234d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400234d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140022da7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140022da7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14002294b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140022965`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400232a5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400232bf`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14002294b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140022965`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400232a5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400232bf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140022c09`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140022d5c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140022c09`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140022d5c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140022b25`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140022b25`
- `ESENT!JetMove` at `0x140022c94`
- `ESENT!JetMove` at `0x140022e76`
- `ESENT!JetMove` at `0x140022c94`
- `ESENT!JetMove` at `0x140022e76`
- `ESENT!JetMakeKey` at `0x1400229fa`
- `ESENT!JetMakeKey` at `0x1400229fa`
- `ESENT!JetSeek` at `0x140022aca`
- `ESENT!JetSeek` at `0x140022aca`

## pseudocode

```c
__int64 __fastcall TieringPinnedSession::GetPinnedFilesListForDiskOptimizer(
        TieringPinnedSession *this,
        enum _STORAGE_TIER_CLASS a2,
        unsigned int a3,
        struct _TE_ENUM_INTERNAL_RESUME_KEY *a4,
        int *a5,
        int *a6,
        struct __MIDL___MIDL_itf_tieringengine_0000_0000_0005 **a7)
{
  __int64 *ThreadLocalStoragePointer; // rax
  __int64 v11; // rcx
  struct _FILE_PLACEMENT *v12; // r13
  unsigned int v13; // esi
  __int64 *v14; // rax
  __int64 v15; // rbx
  int v16; // r9d
  __int128 v17; // xmm0
  unsigned int v18; // ebx
  __int128 v19; // xmm1
  SIZE_T v20; // rax
  JET_TABLEID v21; // rdx
  JET_SESID v22; // rcx
  JET_ERR Key; // eax
  JET_ERR v24; // r8d
  int v25; // eax
  _QWORD *v26; // rcx
  int v27; // edx
  JET_ERR v28; // eax
  RTL_SRWLOCK **v29; // rcx
  enum _STORAGE_TIER_CLASS Ptr_high; // eax
  RTL_SRWLOCK *v31; // rbx
  ULONG ThreadErrorMode; // eax
  NTSTATUS v33; // eax
  char v34; // cl
  bool v35; // sf
  struct _UNICODE_STRING **v36; // rax
  struct _UNICODE_STRING *v37; // rcx
  NTSTATUS v38; // eax
  _QWORD *v39; // rcx
  __int64 v40; // rdx
  JET_ERR v41; // eax
  JET_ERR v42; // r8d
  int v43; // eax
  __int64 v44; // r15
  unsigned int v45; // eax
  unsigned int v46; // eax
  struct __MIDL___MIDL_itf_tieringengine_0000_0000_0005 *v47; // rax
  unsigned int v48; // r12d
  unsigned int v49; // eax
  unsigned int v50; // edx
  __int64 v51; // r8
  __int64 v52; // r9
  unsigned int CurrentPinnedRecord; // eax
  int v54; // eax
  _QWORD *v55; // r10
  SIZE_T v56; // rax
  bool v57; // zf
  CTieredVolume **v58; // rcx
  CTieredVolume *v59; // rcx
  struct _FILE_PLACEMENT *v60; // r15
  unsigned int v61; // r12d
  unsigned int v62; // r13d
  unsigned __int64 v63; // rcx
  char v64; // al
  bool v65; // zf
  _OWORD *v66; // r8
  __int64 v67; // rax
  __int64 v68; // rax
  __int64 *v69; // rax
  __int64 v70; // r15
  _BYTE *v71; // rcx
  int v72; // eax
  int *v73; // r15
  __int64 v74; // rax
  LPVOID *v75; // rbx
  int *v76; // rax
  enum _STORAGE_TIER_CLASS v77; // ebx
  _QWORD *v78; // rcx
  unsigned __int16 *v79; // rax
  unsigned int v81; // eax
  __int64 v82; // r8
  int v83; // r9d
  unsigned int v84; // eax
  __int64 v85; // r10
  void **v86; // [rsp+58h] [rbp-A8h]
  unsigned __int8 v87; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int8 v88; // [rsp+61h] [rbp-9Fh] BYREF
  char v89; // [rsp+62h] [rbp-9Eh]
  enum _STORAGE_TIER_CLASS v90; // [rsp+64h] [rbp-9Ch]
  unsigned __int64 v91; // [rsp+68h] [rbp-98h]
  unsigned int v92; // [rsp+70h] [rbp-90h]
  unsigned int v93; // [rsp+74h] [rbp-8Ch]
  enum _STORAGE_TIER_CLASS v94; // [rsp+78h] [rbp-88h] BYREF
  struct _FILE_PLACEMENT *v95; // [rsp+80h] [rbp-80h] BYREF
  char v96[8]; // [rsp+88h] [rbp-78h] BYREF
  int FileExtentsByFileId; // [rsp+90h] [rbp-70h]
  int v98; // [rsp+98h] [rbp-68h] BYREF
  int v99; // [rsp+9Ch] [rbp-64h] BYREF
  ULONG OldMode; // [rsp+A0h] [rbp-60h] BYREF
  char v101; // [rsp+A4h] [rbp-5Ch]
  int v102; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int v103; // [rsp+ACh] [rbp-54h] BYREF
  void *FileHandle; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v105; // [rsp+B8h] [rbp-48h] BYREF
  LPVOID *v106; // [rsp+C0h] [rbp-40h] BYREF
  _OWORD *v107; // [rsp+C8h] [rbp-38h]
  int *v108; // [rsp+D0h] [rbp-30h]
  int *v109; // [rsp+D8h] [rbp-28h]
  unsigned __int64 v110; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int64 v111; // [rsp+E8h] [rbp-18h] BYREF
  unsigned __int64 v112; // [rsp+F0h] [rbp-10h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+F8h] [rbp-8h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+128h] [rbp+28h] BYREF
  __int128 Source2; // [rsp+138h] [rbp+38h] BYREF
  __int128 Source1; // [rsp+148h] [rbp+48h] BYREF
  __int128 v117; // [rsp+158h] [rbp+58h]
  __int64 v118; // [rsp+168h] [rbp+68h]

  v108 = a6;
  ThreadLocalStoragePointer = (__int64 *)NtCurrentTeb()->ThreadLocalStoragePointer;
  v90 = a2;
  v105 = (__int64)a4;
  v11 = *ThreadLocalStoragePointer;
  v109 = a5;
  v106 = (LPVOID *)a7;
  *(_QWORD *)(v11 + 8) = "TieringPinnedSession::GetPinnedFilesListForDiskOptimizer";
  CHResultImp::CHResultImp((CHResultImp *)v96);
  v118 = 0;
  v12 = 0;
  Source1 = 0;
  v95 = 0;
  v117 = 0;
  *v108 = 0;
  v13 = 0;
  *a5 = 1;
  v14 = (__int64 *)*((_QWORD *)this + 5);
  FileExtentsByFileId = 0;
  v15 = *v14;
  if ( *(_WORD *)(*v14 + 165)
    || WaitForSingleObject(*(HANDLE *)(v15 + 768), 0) != 258
    || WaitForSingleObject(*(HANDLE *)(v15 + 760), 0) != 258 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_Z(*((_QWORD *)WPP_GLOBAL_Control + 2), 252, &WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids, v15 + 672);
    }
    v84 = ATL::AtlHresultFromWin32(87);
    v18 = v84;
    FileExtentsByFileId = v84;
    if ( (_UNKNOWN **)v85 != &WPP_GLOBAL_Control && (*(_BYTE *)(v85 + 28) & 1) != 0 && *(_BYTE *)(v85 + 25) >= 2u )
      WPP_SF_Sd(
        *(_QWORD *)(v85 + 16),
        10,
        (unsigned int)&WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids,
        *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
        v84);
    goto LABEL_216;
  }
  v16 = *(_DWORD *)(**((_QWORD **)this + 5) + 184LL);
  if ( ((v16 - 1) & 0xFFFFFFFA) != 0 || v16 == 5 )
  {
    v81 = ATL::AtlHresultFromWin32(1003);
    v18 = v81;
    FileExtentsByFileId = v81;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_DSd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        (unsigned int)&WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids,
        v83,
        *(_QWORD *)(v82 + 112),
        v81);
    }
    goto LABEL_216;
  }
  v17 = *(_OWORD *)a4;
  v18 = 0;
  v19 = *((_OWORD *)a4 + 1);
  v91 = 0;
  Source1 = v17;
  v118 = *((_QWORD *)a4 + 4);
  v117 = v19;
  v20 = RtlCompareMemory((char *)&Source1 + 8, &NullGuid, 0x10u);
  v21 = *((_QWORD *)this + 3);
  v22 = *((_QWORD *)this + 1);
  if ( v20 != 16 )
  {
    Key = JetMakeKey(v22, v21, (char *)&Source1 + 8, 0x10u, 1u);
    v24 = Key;
    if ( Key )
    {
      if ( Key == -529 || Key == -1092 || Key == -1808 )
      {
        v18 = ATL::AtlHresultFromWin32(112);
      }
      else if ( Key == -1011 )
      {
        v18 = -2147024882;
      }
      else
      {
        v25 = -Key;
        if ( v25 < 0 )
          LOWORD(v25) = v24;
        v18 = v24 & 0x8E5E0000 | (unsigned __int16)v25 | 0xE5E0000;
      }
      FileExtentsByFileId = v18;
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_216;
      }
      v27 = 12;
      goto LABEL_21;
    }
    v28 = JetSeek(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 8u);
    LOBYTE(v24) = v28;
    if ( ((v28 + 1603) & 0xFFFFFFFD) != 0 )
    {
      if ( v28 )
      {
        if ( v28 != 1039 )
        {
          v26 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_216;
          }
          v27 = 14;
LABEL_21:
          WPP_SF_iiSd(
            v26[2],
            v27,
            (unsigned int)&WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids,
            v117,
            SBYTE8(Source1),
            *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
            v24);
LABEL_216:
          CHResultImp::~CHResultImp((CHResultImp *)v96);
          return v18;
        }
      }
      else
      {
        v91 = *((_QWORD *)&v117 + 1);
      }
      goto LABEL_25;
    }
    v39 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
LABEL_203:
      FileExtentsByFileId = 0;
      CHResultImp::~CHResultImp((CHResultImp *)v96);
      return 0;
    }
    v40 = 13;
LABEL_202:
    WPP_SF_S(v39[2], v40, &WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids, *(_QWORD *)(*((_QWORD *)this + 5) + 112LL));
    goto LABEL_203;
  }
  v41 = JetMove(v22, v21, 0x80000000, 0);
  v42 = v41;
  if ( ((v41 + 1603) & 0xFFFFFFFD) == 0 )
  {
    v39 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      goto LABEL_203;
    }
    v40 = 15;
    goto LABEL_202;
  }
  if ( v41 )
  {
    if ( v41 == -529 || v41 == -1092 || v41 == -1808 )
    {
      v18 = ATL::AtlHresultFromWin32(112);
    }
    else if ( v41 == -1011 )
    {
      v18 = -2147024882;
    }
    else
    {
      v43 = -v41;
      if ( v43 < 0 )
        LOWORD(v43) = v42;
      v18 = v42 & 0x8E5E0000 | (unsigned __int16)v43 | 0xE5E0000;
    }
    FileExtentsByFileId = v18;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        16,
        (unsigned int)&WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids,
        *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
        v42);
    }
    goto LABEL_216;
  }
LABEL_25:
  v29 = (RTL_SRWLOCK **)*((_QWORD *)this + 5);
  Ptr_high = HIDWORD((*v29)[39].Ptr);
  v101 = 0;
  FileHandle = 0;
  IoStatusBlock = 0;
  v31 = *v29 + 3;
  v94 = Ptr_high;
  AcquireSRWLockShared(v31);
  ThreadErrorMode = RtlGetThreadErrorMode();
  v33 = RtlSetThreadErrorMode(ThreadErrorMode | 0x10, &OldMode);
  v34 = v101;
  v35 = v33 < 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  v36 = (struct _UNICODE_STRING **)*((_QWORD *)this + 5);
  if ( !v35 )
    v34 = 1;
  ObjectAttributes.RootDirectory = 0;
  v101 = v34;
  v37 = *v36 + 9;
  *(_QWORD *)&ObjectAttributes.Attributes = 192;
  ObjectAttributes.ObjectName = v37;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v38 = NtOpenFile(&FileHandle, 0x100080u, &ObjectAttributes, &IoStatusBlock, 7u, 0x21u);
  if ( v38 < 0 )
  {
    v13 = v38 | 0x10000000;
    FileExtentsByFileId = v38 | 0x10000000;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Zd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        (unsigned int)&WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids,
        **((_DWORD **)this + 5) + 144,
        v38);
    }
    if ( v31 )
      ReleaseSRWLockShared(v31);
    goto LABEL_193;
  }
  if ( v31 )
    ReleaseSRWLockShared(v31);
  v44 = 10000;
  if ( a3 < 0x2710 )
    v44 = a3;
  v45 = *(_DWORD *)(**((_QWORD **)this + 5) + 240LL) + *(_DWORD *)(**((_QWORD **)this + 5) + 232LL);
  if ( v45 < 0x3E8 )
    v45 = 1000;
  v46 = v45 + 1;
  if ( (unsigned int)v44 >= v46 )
    v44 = v46;
  v93 = v44;
  v47 = (struct __MIDL___MIDL_itf_tieringengine_0000_0000_0005 *)CoTaskMemAlloc(40 * v44);
  *a7 = v47;
  if ( !v47 )
  {
    v18 = -2147024882;
    FileExtentsByFileId = -2147024882;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_DSd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        (unsigned int)&WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids,
        v44,
        *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
        14);
    }
    if ( FileHandle )
      NtClose(FileHandle);
    if ( v101 )
      RtlSetThreadErrorMode(OldMode, 0);
    goto LABEL_216;
  }
  v48 = 0;
  v89 = 0;
  v92 = 0;
  memset_0(v47, 0, 40 * v44);
  v107 = *v106;
  while ( 1 )
  {
    if ( v89 )
    {
      v49 = JetMove(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 1, 0);
      v52 = v49;
      if ( ((v49 + 1603) & 0xFFFFFFFD) == 0 )
      {
        v55 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_S(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            19,
            &WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids,
            *(_QWORD *)(*((_QWORD *)this + 5) + 112LL));
          v55 = WPP_GLOBAL_Control;
        }
        v13 = 0;
        FileExtentsByFileId = 0;
        goto LABEL_170;
      }
      if ( v49 )
      {
        if ( v49 == -529 || v49 == -1092 || v49 == -1808 )
        {
          v13 = ATL::AtlHresultFromWin32(112);
        }
        else if ( v49 == -1011 )
        {
          v13 = -2147024882;
        }
        else
        {
          v72 = -v49;
          if ( (int)v52 > 0 )
            LOWORD(v72) = v52;
          v13 = v52 & 0x8E5E0000 | (unsigned __int16)v72 | 0xE5E0000;
        }
        FileExtentsByFileId = v13;
        v55 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids, v52);
          v55 = WPP_GLOBAL_Control;
        }
LABEL_170:
        if ( v48 < (unsigned int)v44 )
          goto LABEL_178;
LABEL_171:
        v73 = v109;
        v13 = 0;
        FileExtentsByFileId = 0;
        *v109 = 1;
LABEL_180:
        v55 = WPP_GLOBAL_Control;
        goto LABEL_182;
      }
    }
    else
    {
      v89 = 1;
    }
    v87 = 0;
    v88 = 0;
    Source2 = 0;
    CurrentPinnedRecord = TieringPinnedSession::GetCurrentPinnedRecord(
                            this,
                            (struct TE_FILE_ID_128 *)&Source2,
                            &v87,
                            &v88);
    v52 = CurrentPinnedRecord;
    switch ( CurrentPinnedRecord )
    {
      case 0xFFFFFC07:
        goto LABEL_137;
      case 0u:
        v56 = RtlCompareMemory(&NullGuid, &Source2, 0x10u);
        v50 = 1;
        if ( v56 == 16 || (v88 & 1) != 0 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_iiDSd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              25,
              (unsigned int)&WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids,
              DWORD2(Source2),
              Source2,
              v88,
              *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
              v13);
          }
          goto LABEL_156;
        }
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_iiLDSd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v87,
            v51,
            DWORD2(Source2),
            Source2,
            v87,
            v90,
            *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
            v13);
          v50 = 1;
        }
        if ( v90 == StorageTierClassPerformance )
        {
          v57 = (v87 & 1) == 0;
        }
        else
        {
          if ( v90 != StorageTierClassCapacity )
            goto LABEL_156;
          v57 = (v87 & 2) == 0;
        }
        if ( !v57 )
        {
          if ( v12 )
          {
            free(v12);
            v12 = 0;
            v95 = 0;
          }
          v58 = (CTieredVolume **)*((_QWORD *)this + 5);
          v112 = (unsigned __int64)v12;
          v59 = *v58;
          v110 = (unsigned __int64)v12;
          v111 = (unsigned __int64)v12;
          v103 = (unsigned int)v12;
          v99 = (int)v12;
          v98 = (int)v12;
          v102 = (int)v12;
          FileExtentsByFileId = CTieredVolume::GetFileExtentsByFileId(
                                  v59,
                                  FileHandle,
                                  (const struct TE_FILE_ID_128 *)&Source2,
                                  &v99,
                                  &v102,
                                  &v98,
                                  &v112,
                                  &v111,
                                  &v110,
                                  &v103,
                                  &v95,
                                  v86);
          v13 = FileExtentsByFileId;
          if ( FileExtentsByFileId >= 0 && v102 == (_DWORD)v12 )
          {
            v60 = v95;
            v61 = (unsigned int)v12;
            v62 = v103;
            v63 = v91;
            if ( v103 )
            {
              v50 = v92;
              v52 = 1;
              v51 = (unsigned int)v90;
              do
              {
                if ( v50 >= v93 )
                  break;
                v64 = *((_BYTE *)v60 + 24);
                if ( v64 && *(_QWORD *)v60 >= v63 )
                {
                  if ( (_DWORD)v51 == 2 )
                    v65 = v64 == 16;
                  else
                    v65 = v64 == 32;
                  if ( !v65 )
                  {
                    v66 = v107;
                    *v107 = Source2;
                    *((_QWORD *)v66 + 2) = *(_QWORD *)v60;
                    v67 = *((_QWORD *)v60 + 2) * (unsigned int)v94;
                    *((_WORD *)v66 + 16) = 16;
                    *((_QWORD *)v66 + 3) = v67;
                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                    {
                      WPP_SF_iiiiSd(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        23,
                        (unsigned int)&WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids,
                        DWORD2(Source2),
                        Source2,
                        *(_QWORD *)v60,
                        *((_QWORD *)v60 + 2),
                        *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
                        v13);
                      v50 = v92;
                      v52 = 1;
                      v66 = v107;
                    }
                    if ( v90 == StorageTierClassPerformance )
                    {
                      *((_DWORD *)v66 + 9) = 2;
                      *(_QWORD *)(**((_QWORD **)this + 5) + 264LL) += *((_QWORD *)v60 + 2);
                    }
                    else
                    {
                      *((_DWORD *)v66 + 9) = 1;
                      *(_QWORD *)(**((_QWORD **)this + 5) + 272LL) += *((_QWORD *)v60 + 2);
                    }
                    v92 = ++v50;
                    v107 = (_OWORD *)((char *)v66 + 40);
                    v51 = (unsigned int)v90;
                    *v108 = v50;
                  }
                  v63 = *(_QWORD *)v60 + *((_QWORD *)v60 + 2) * (unsigned int)v94;
                }
                v60 = (struct _FILE_PLACEMENT *)((char *)v60 + 32);
                ++v61;
              }
              while ( v61 < v62 );
            }
            v48 = v92;
            LODWORD(v44) = v93;
          }
          else
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_iiSd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                24,
                (unsigned int)&WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids,
                DWORD2(Source2),
                Source2,
                *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
                FileExtentsByFileId);
            }
            v63 = v91;
          }
          v12 = v95;
          goto LABEL_136;
        }
LABEL_156:
        v63 = v91;
LABEL_136:
        v68 = v105;
        v91 = 0;
        *(_OWORD *)(v105 + 8) = Source2;
        *(_QWORD *)(v68 + 24) = v63;
        *(_DWORD *)(v68 + 32) = 1;
        goto LABEL_137;
      case 0xFFFFFDEF:
      case 0xFFFFFBBC:
      case 0xFFFFF8F0:
        v13 = ATL::AtlHresultFromWin32(112);
        break;
      case 0xFFFFFC0D:
        v13 = -2147024882;
        break;
      default:
        v54 = -CurrentPinnedRecord;
        if ( v54 < 0 )
          LOWORD(v54) = v52;
        v13 = v52 & 0x8E5E0000 | (unsigned __int16)v54 | 0xE5E0000;
        break;
    }
    FileExtentsByFileId = v13;
    v55 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids, v52);
LABEL_137:
      v55 = WPP_GLOBAL_Control;
    }
    if ( v48 >= (unsigned int)v44 )
      goto LABEL_171;
    v69 = (__int64 *)*((_QWORD *)this + 5);
    v70 = *v69;
    if ( *(_BYTE *)(*v69 + 165) || *(_BYTE *)(v70 + 166) )
      goto LABEL_173;
    if ( WaitForSingleObject(*(HANDLE *)(v70 + 768), 0) != 258 || WaitForSingleObject(*(HANDLE *)(v70 + 760), 0) != 258 )
      break;
    v71 = (_BYTE *)*((_QWORD *)this + 5);
    if ( *(_DWORD *)(*(_QWORD *)v71 + 184LL) == 2 )
    {
      LODWORD(v44) = v93;
      if ( !v71[77] || !v71[76] )
        continue;
    }
    goto LABEL_177;
  }
  v55 = WPP_GLOBAL_Control;
LABEL_173:
  if ( v55 != &WPP_GLOBAL_Control && (*((_BYTE *)v55 + 28) & 1) != 0 && *((_BYTE *)v55 + 25) >= 5u )
  {
    WPP_SF_Z(v55[2], 252, &WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids, v70 + 672);
LABEL_177:
    v55 = WPP_GLOBAL_Control;
  }
LABEL_178:
  if ( !v48 )
  {
    v74 = v105;
    v75 = v106;
    *(_OWORD *)(v105 + 8) = 0;
    *(_QWORD *)(v74 + 24) = 0;
    *(_DWORD *)(v74 + 32) = 0;
    CoTaskMemFree(*v75);
    v73 = v109;
    v76 = v108;
    *v75 = 0;
    *v73 = 0;
    *v76 = 0;
    goto LABEL_180;
  }
  v73 = v109;
LABEL_182:
  if ( v55 == &WPP_GLOBAL_Control || (*((_BYTE *)v55 + 28) & 1) == 0 )
  {
    v77 = v90;
  }
  else
  {
    v77 = v90;
    if ( *((_BYTE *)v55 + 25) >= 4u )
      WPP_SF_DLiiS(v55[2], v50, v51, v48, v90, v117, SBYTE8(Source1), *(_QWORD *)(*((_QWORD *)this + 5) + 112LL));
  }
  if ( (unsigned int)dword_14004C098 > 4
    && (qword_14004C0A8 & 0x200000000000LL) != 0
    && (qword_14004C0B0 & 0x200000000000LL) == qword_14004C0B0 )
  {
    v78 = (_QWORD *)*((_QWORD *)this + 5);
    v112 = v78[14];
    v111 = *((_QWORD *)&Source1 + 1);
    v110 = v117;
    v99 = *v73;
    v98 = v48;
    v94 = v77;
    v79 = (unsigned __int16 *)(*v78 + 696LL);
    v105 = 0x1000000;
    v106 = (LPVOID *)v79;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
      (__int64)v78,
      (__int64)&unk_140046480,
      v51,
      v52,
      (__int64)&v105,
      (unsigned __int16 **)&v106,
      (__int64)&v94,
      (__int64)&v98,
      (__int64)&v99,
      (__int64)&v110,
      (__int64)&v111,
      (__int64 **)&v112);
  }
  if ( v12 )
    free(v12);
LABEL_193:
  if ( FileHandle )
    NtClose(FileHandle);
  if ( v101 )
    RtlSetThreadErrorMode(OldMode, 0);
  CHResultImp::~CHResultImp((CHResultImp *)v96);
  return v13;
}

```

## disassembly

```asm
0x140022878  mov     [rsp-8+arg_8], rbx
0x14002287d  push    rbp
0x14002287e  push    rsi
0x14002287f  push    rdi
0x140022880  push    r12
0x140022882  push    r13
0x140022884  push    r14
0x140022886  push    r15
0x140022888  lea     rbp, [rsp-80h]
0x14002288d  sub     rsp, 180h
0x140022894  mov     rax, cs:__security_cookie
0x14002289b  xor     rax, rsp
0x14002289e  mov     [rbp+0B0h+var_40], rax
0x1400228a2  mov     rax, [rbp+0B0h+arg_28]
0x1400228a9  mov     r14, rcx
0x1400228ac  mov     rbx, [rbp+0B0h+arg_20]
0x1400228b3  mov     r15, r9
0x1400228b6  mov     r12, [rbp+0B0h+arg_30]
0x1400228bd  mov     edi, r8d
0x1400228c0  mov     [rbp+0B0h+var_E0], rax
0x1400228c4  mov     rax, gs:58h
0x1400228cd  mov     [rsp+1B0h+var_14C], edx
0x1400228d1  mov     edx, 8
0x1400228d6  mov     [rbp+0B0h+var_F8], r9
0x1400228da  mov     rcx, [rax]
0x1400228dd  lea     rax, aTieringpinneds_2; "TieringPinnedSession::GetPinnedFilesLis"...
0x1400228e4  mov     [rbp+0B0h+var_D8], rbx
0x1400228e8  mov     [rbp+0B0h+var_F0], r12
0x1400228ec  mov     [rdx+rcx], rax
0x1400228f0  lea     rcx, [rbp+0B0h+var_128]; this
0x1400228f4  call    ??0CHResultImp@@QEAA@XZ; CHResultImp::CHResultImp(void)
0x1400228f9  xor     ecx, ecx
0x1400228fb  xor     eax, eax
0x1400228fd  mov     [rbp+0B0h+var_48], rax
0x140022901  xorps   xmm0, xmm0
0x140022904  mov     rax, [rbp+0B0h+var_E0]
0x140022908  mov     r13d, ecx
0x14002290b  movups  [rbp+0B0h+Source1], xmm0
0x14002290f  lea     edx, [rcx+1]
0x140022912  mov     [rbp+0B0h+var_130], rcx
0x140022916  movups  [rbp+0B0h+var_58], xmm0
0x14002291a  mov     [rax], ecx
0x14002291c  mov     esi, ecx
0x14002291e  mov     [rbx], edx
0x140022920  mov     rax, [r14+28h]
0x140022924  mov     [rbp+0B0h+var_120], ecx
0x140022927  mov     rbx, [rax]
0x14002292a  cmp     [rbx+0A5h], cl
0x140022930  jnz     loc_140023709
0x140022936  cmp     [rbx+0A6h], cl
0x14002293c  jnz     loc_140023709
0x140022942  mov     rcx, [rbx+300h]; hHandle
0x140022949  xor     edx, edx; dwMilliseconds
0x14002294b  call    cs:__imp_WaitForSingleObject
0x140022951  cmp     eax, 102h
0x140022956  jnz     loc_140023704
0x14002295c  mov     rcx, [rbx+2F8h]; hHandle
0x140022963  xor     edx, edx; dwMilliseconds
0x140022965  call    cs:__imp_WaitForSingleObject
0x14002296b  cmp     eax, 102h
0x140022970  jnz     loc_140023704
0x140022976  mov     r8, [r14+28h]
0x14002297a  mov     rax, [r8]
0x14002297d  mov     r9d, [rax+0B8h]
0x140022984  lea     eax, [r9-1]
0x140022988  test    eax, 0FFFFFFFAh
0x14002298d  jnz     loc_1400236A3
0x140022993  cmp     r9d, 5
0x140022997  jz      loc_1400236A3
0x14002299d  movups  xmm0, xmmword ptr [r15]
0x1400229a1  xor     ebx, ebx
0x1400229a3  lea     rdx, ?NullGuid@@3U_GUID@@A; Source2
0x1400229aa  movups  xmm1, xmmword ptr [r15+10h]
0x1400229af  lea     rcx, [rbp+0B0h+Source1+8]; Source1
0x1400229b3  mov     [rsp+1B0h+var_148], rbx
0x1400229b8  movups  [rbp+0B0h+Source1], xmm0
0x1400229bc  movsd   xmm0, qword ptr [r15+20h]
0x1400229c2  lea     r15d, [r13+10h]
0x1400229c6  mov     r8d, r15d; Length
0x1400229c9  movsd   [rbp+0B0h+var_48], xmm0
0x1400229ce  movups  [rbp+0B0h+var_58], xmm1
0x1400229d2  call    cs:__imp_RtlCompareMemory
0x1400229d8  mov     rdx, [r14+18h]; tableid
0x1400229dc  mov     rcx, [r14+8]; sesid
0x1400229e0  cmp     rax, r15
0x1400229e3  jz      loc_140022C8B
0x1400229e9  lea     r15d, [r13+1]
0x1400229ed  lea     r9d, [r13+10h]; cbData
0x1400229f1  mov     [rsp+1B0h+grbit], r15d; grbit
0x1400229f6  lea     r8, [rbp+0B0h+Source1+8]; pvData
0x1400229fa  call    cs:__imp_JetMakeKey
0x140022a00  mov     r8d, eax
0x140022a03  test    eax, eax
0x140022a05  jz      loc_140022ABC
0x140022a0b  cmp     eax, 0FFFFFDEFh
0x140022a10  jz      short loc_140022A49
0x140022a12  cmp     eax, 0FFFFFBBCh
0x140022a17  jz      short loc_140022A49
0x140022a19  cmp     eax, 0FFFFF8F0h
0x140022a1e  jz      short loc_140022A49
0x140022a20  cmp     eax, 0FFFFFC0Dh
0x140022a25  jnz     short loc_140022A2E
0x140022a27  mov     ebx, 8007000Eh
0x140022a2c  jmp     short loc_140022A55
0x140022a2e  neg     eax
0x140022a30  cmovs   eax, r8d
0x140022a34  movzx   ebx, ax
0x140022a37  mov     eax, r8d
0x140022a3a  and     eax, 8E5E0000h
0x140022a3f  or      ebx, eax
0x140022a41  or      ebx, 0E5E0000h
0x140022a47  jmp     short loc_140022A55
0x140022a49  mov     ecx, 70h ; 'p'; unsigned int
0x140022a4e  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x140022a53  mov     ebx, eax
0x140022a55  mov     [rbp+0B0h+var_120], ebx
0x140022a58  mov     rcx, cs:WPP_GLOBAL_Control
0x140022a5f  lea     rdi, WPP_GLOBAL_Control
0x140022a66  cmp     rcx, rdi
0x140022a69  jz      loc_14002378F
0x140022a6f  test    [rcx+1Ch], r15b
0x140022a73  jz      loc_14002378F
0x140022a79  cmp     byte ptr [rcx+19h], 2
0x140022a7d  jb      loc_14002378F
0x140022a83  mov     edx, 0Ch
0x140022a88  mov     rax, [r14+28h]
0x140022a8c  mov     r9, qword ptr [rbp+0B0h+var_58]
0x140022a90  mov     rcx, [rcx+10h]
0x140022a94  mov     dword ptr [rsp+1B0h+var_180], r8d
0x140022a99  lea     r8, WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids
0x140022aa0  mov     rax, [rax+70h]
0x140022aa4  mov     qword ptr [rsp+1B0h+OpenOptions], rax
0x140022aa9  mov     rax, qword ptr [rbp+0B0h+Source1+8]
0x140022aad  mov     qword ptr [rsp+1B0h+grbit], rax
0x140022ab2  call    WPP_SF_iiSd
0x140022ab7  jmp     loc_14002378F
0x140022abc  mov     rdx, [r14+18h]; tableid
0x140022ac0  mov     r8d, 8; grbit
0x140022ac6  mov     rcx, [r14+8]; sesid
0x140022aca  call    cs:__imp_JetSeek
0x140022ad0  mov     r8d, eax
0x140022ad3  lea     ecx, [rax+643h]
0x140022ad9  test    ecx, 0FFFFFFFDh
0x140022adf  jz      loc_140022C56
0x140022ae5  test    eax, eax
0x140022ae7  jnz     loc_140022C14
0x140022aed  mov     r15, qword ptr [rbp+0B0h+var_58+8]
0x140022af1  mov     [rsp+1B0h+var_148], r15
0x140022af6  mov     r15d, 1
0x140022afc  mov     rcx, [r14+28h]
0x140022b00  xorps   xmm0, xmm0
0x140022b03  mov     rax, [rcx]
0x140022b06  mov     eax, [rax+13Ch]
0x140022b0c  mov     [rbp+0B0h+var_10C], bl
0x140022b0f  mov     [rbp+0B0h+FileHandle], rbx
0x140022b13  movups  xmmword ptr [rbp+0B0h+IoStatusBlock], xmm0
0x140022b17  mov     rbx, [rcx]
0x140022b1a  add     rbx, 18h
0x140022b1e  mov     [rsp+1B0h+var_138], eax
0x140022b22  mov     rcx, rbx; SRWLock
0x140022b25  call    cs:__imp_AcquireSRWLockShared
0x140022b2b  call    cs:__imp_RtlGetThreadErrorMode
0x140022b31  or      eax, 10h
0x140022b34  lea     rdx, [rbp+0B0h+OldMode]; OldMode
0x140022b38  mov     ecx, eax; NewMode
0x140022b3a  call    cs:__imp_RtlSetThreadErrorMode
0x140022b40  movzx   ecx, [rbp+0B0h+var_10C]
0x140022b44  lea     r9, [rbp+0B0h+IoStatusBlock]; IoStatusBlock
0x140022b48  test    eax, eax
0x140022b4a  mov     qword ptr [rbp+0B0h+ObjectAttributes.Length], 30h ; '0'
0x140022b52  mov     rax, [r14+28h]
0x140022b56  lea     r8, [rbp+0B0h+ObjectAttributes]; ObjectAttributes
0x140022b5a  cmovns  ecx, r15d
0x140022b5e  mov     [rbp+0B0h+ObjectAttributes.RootDirectory], rsi
0x140022b62  mov     [rbp+0B0h+var_10C], cl
0x140022b65  xorps   xmm0, xmm0
0x140022b68  mov     [rsp+1B0h+OpenOptions], 21h ; '!'; OpenOptions
0x140022b70  mov     edx, 100080h; DesiredAccess
0x140022b75  mov     rcx, [rax]
0x140022b78  add     rcx, 90h
0x140022b7f  mov     qword ptr [rbp+0B0h+ObjectAttributes.Attributes], 0C0h
0x140022b87  mov     [rbp+0B0h+ObjectAttributes.ObjectName], rcx
0x140022b8b  lea     rcx, [rbp+0B0h+FileHandle]; FileHandle
0x140022b8f  movdqu  xmmword ptr [rbp+0B0h+ObjectAttributes.SecurityDescriptor], xmm0
0x140022b94  mov     [rsp+1B0h+grbit], 7; ShareAccess
0x140022b9c  call    cs:__imp_NtOpenFile
0x140022ba2  mov     r8d, eax
0x140022ba5  test    eax, eax
0x140022ba7  jns     loc_140022D54
0x140022bad  mov     esi, eax
0x140022baf  bts     esi, 1Ch
0x140022bb3  mov     [rbp+0B0h+var_120], esi
0x140022bb6  mov     rcx, cs:WPP_GLOBAL_Control
0x140022bbd  lea     rdi, WPP_GLOBAL_Control
0x140022bc4  cmp     rcx, rdi
0x140022bc7  jz      short loc_140022BFD
0x140022bc9  test    [rcx+1Ch], r15b
0x140022bcd  jz      short loc_140022BFD
0x140022bcf  cmp     byte ptr [rcx+19h], 2
0x140022bd3  jb      short loc_140022BFD
0x140022bd5  mov     rax, [r14+28h]
0x140022bd9  mov     edx, 11h
0x140022bde  mov     rcx, [rcx+10h]
0x140022be2  mov     [rsp+1B0h+grbit], r8d
0x140022be7  lea     r8, WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids
0x140022bee  mov     r9, [rax]
0x140022bf1  add     r9, 90h
0x140022bf8  call    WPP_SF_Zd
0x140022bfd  test    rbx, rbx
0x140022c00  jz      loc_140023624
0x140022c06  mov     rcx, rbx; SRWLock
0x140022c09  call    cs:__imp_ReleaseSRWLockShared
0x140022c0f  jmp     loc_140023624
0x140022c14  cmp     r8d, 40Fh
0x140022c1b  jz      loc_140022AFC
0x140022c21  mov     rcx, cs:WPP_GLOBAL_Control
0x140022c28  lea     rdi, WPP_GLOBAL_Control
0x140022c2f  cmp     rcx, rdi
0x140022c32  jz      loc_14002378F
0x140022c38  test    [rcx+1Ch], r15b
0x140022c3c  jz      loc_14002378F
0x140022c42  cmp     byte ptr [rcx+19h], 2
0x140022c46  jb      loc_14002378F
0x140022c4c  mov     edx, 0Eh
0x140022c51  jmp     loc_140022A88
0x140022c56  mov     rcx, cs:WPP_GLOBAL_Control
0x140022c5d  lea     rdi, WPP_GLOBAL_Control
0x140022c64  cmp     rcx, rdi
0x140022c67  jz      loc_140023690
0x140022c6d  test    [rcx+1Ch], r15b
0x140022c71  jz      loc_140023690
0x140022c77  cmp     byte ptr [rcx+19h], 4
0x140022c7b  jb      loc_140023690
0x140022c81  mov     edx, 0Dh
0x140022c86  jmp     loc_140023678
0x140022c8b  xor     r9d, r9d; grbit
0x140022c8e  mov     r8d, 80000000h; cRow
0x140022c94  call    cs:__imp_JetMove
0x140022c9a  mov     r8d, eax
0x140022c9d  lea     ecx, [rax+643h]
0x140022ca3  test    ecx, 0FFFFFFFDh
0x140022ca9  jz      loc_140023654
0x140022caf  test    eax, eax
0x140022cb1  jz      loc_140022AF6
0x140022cb7  cmp     eax, 0FFFFFDEFh
0x140022cbc  jz      short loc_140022CF5
0x140022cbe  cmp     eax, 0FFFFFBBCh
0x140022cc3  jz      short loc_140022CF5
0x140022cc5  cmp     eax, 0FFFFF8F0h
0x140022cca  jz      short loc_140022CF5
0x140022ccc  cmp     eax, 0FFFFFC0Dh
0x140022cd1  jnz     short loc_140022CDA
0x140022cd3  mov     ebx, 8007000Eh
0x140022cd8  jmp     short loc_140022D01
0x140022cda  neg     eax
0x140022cdc  cmovs   eax, r8d
0x140022ce0  movzx   ebx, ax
0x140022ce3  mov     eax, r8d
0x140022ce6  and     eax, 8E5E0000h
0x140022ceb  or      ebx, eax
0x140022ced  or      ebx, 0E5E0000h
0x140022cf3  jmp     short loc_140022D01
0x140022cf5  mov     ecx, 70h ; 'p'; unsigned int
0x140022cfa  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x140022cff  mov     ebx, eax
0x140022d01  mov     [rbp+0B0h+var_120], ebx
0x140022d04  mov     rcx, cs:WPP_GLOBAL_Control
0x140022d0b  lea     rdi, WPP_GLOBAL_Control
0x140022d12  cmp     rcx, rdi
0x140022d15  jz      loc_14002378F
0x140022d1b  test    byte ptr [rcx+1Ch], 1
0x140022d1f  jz      loc_14002378F
0x140022d25  cmp     byte ptr [rcx+19h], 2
0x140022d29  jb      loc_14002378F
0x140022d2f  mov     r9, [r14+28h]
0x140022d33  mov     edx, r15d
0x140022d36  mov     rcx, [rcx+10h]
0x140022d3a  mov     [rsp+1B0h+grbit], r8d
0x140022d3f  lea     r8, WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids
0x140022d46  mov     r9, [r9+70h]
0x140022d4a  call    WPP_SF_Sd
0x140022d4f  jmp     loc_14002378F
0x140022d54  test    rbx, rbx
0x140022d57  jz      short loc_140022D62
0x140022d59  mov     rcx, rbx; SRWLock
0x140022d5c  call    cs:__imp_ReleaseSRWLockShared
0x140022d62  mov     rax, [r14+28h]
0x140022d66  mov     r15d, 2710h
0x140022d6c  cmp     edi, r15d
0x140022d6f  cmovb   r15d, edi
0x140022d73  mov     rax, [rax]
0x140022d76  mov     ecx, [rax+0F0h]
0x140022d7c  mov     eax, [rax+0E8h]
0x140022d82  add     eax, ecx
0x140022d84  mov     ecx, 3E8h
0x140022d89  cmp     eax, ecx
0x140022d8b  cmovb   eax, ecx
0x140022d8e  inc     eax
0x140022d90  cmp     r15d, eax
0x140022d93  cmovnb  r15d, eax
  ... truncated ...
```
