# ServiceManager::ClearMapData(void)

- ea: `0x180013870`
- end: `0x180013dc2`
- name: `?ClearMapData@ServiceManager@@AEAAJXZ`
- size: `1362`
- prototype: `__int64 __fastcall(RTL_CONDITION_VARIABLE *this)`
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, reparse_path, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180012f00`

## callees

- `0x180003410`
- `0x180003f7c`
- `0x180009bb4`
- `0x180009d0c`
- `0x180009db4`
- `0x180011b94`
- `0x180012220`
- `0x180012cf0`
- `0x180013684`
- `0x180013870`
- `0x180014c00`
- `0x180015ed0`
- `0x1800186a0`
- `0x18001874c`
- `0x180018804`
- `0x1800188bc`
- `0x180018974`
- `0x18001dad0`
- `0x1800201d8`
- `0x1800228ec`
- `0x1800229b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013a98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013b7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013bb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013a98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013b7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013bb8`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180013c64`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180013c64`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveBackslash` at `0x180013a66`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveBackslash` at `0x180013a66`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180013baa`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180013baa`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180013b73`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180013b73`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180013a8d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180013ae7`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180013a8d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180013ae7`
- `MosStorage!MosStorageGetCurrentLocation` at `0x1800139a3`
- `MosStorage!MosStorageGetCurrentLocation` at `0x1800139a3`
- `MosStorage!MosStorageGetDataDirectory` at `0x180013a4a`
- `MosStorage!MosStorageGetDataDirectory` at `0x180013a4a`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x1800139c2`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x180013c11`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x180013c46`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x1800139c2`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x180013c11`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x180013c46`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x180013a2a`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x180013b4e`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x180013a2a`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x180013b4e`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x180013952`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x180013a7e`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x180013d8b`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x180013952`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x180013a7e`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x180013d8b`

## string_xrefs

- `0x180013943`: `ServiceManager::ClearMapData`
- `0x1800139a9`: `ServiceManager::ClearMapData`
- `0x180013d7f`: `ServiceManager::ClearMapData`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall ServiceManager::ClearMapData(RTL_CONDITION_VARIABLE *this)
{
  int v2; // esi
  int v3; // edi
  RTL_CONDITION_VARIABLE *v4; // r15
  int *v5; // r12
  int CurrentLocation; // eax
  unsigned __int64 v7; // rdx
  unsigned __int8 v8; // cl
  bool v9; // di
  OfflineMapsTelemetry *v10; // rax
  int DataDirectory; // eax
  int v12; // r8d
  int v13; // eax
  int LastError; // eax
  int v15; // r8d
  DWORD FileAttributesW; // eax
  int v17; // edi
  DWORD v18; // eax
  int updated; // eax
  int v20; // eax
  unsigned __int64 v21; // rdx
  unsigned __int8 v22; // cl
  int v23; // esi
  int v24; // esi
  bool v25; // bl
  OfflineMapsTelemetry *v26; // rax
  bool v27; // bl
  OfflineMapsTelemetry *v28; // rax
  bool v29; // bl
  OfflineMapsTelemetry *v30; // rax
  bool v31; // bl
  OfflineMapsTelemetry *v32; // rax
  char v34; // [rsp+30h] [rbp-D0h]
  _DWORD v35[2]; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v36[2]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v37[16]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v38[4]; // [rsp+60h] [rbp-A0h] BYREF
  int v39; // [rsp+64h] [rbp-9Ch]
  unsigned int v40; // [rsp+274h] [rbp+174h]
  unsigned int v41; // [rsp+6C0h] [rbp+5C0h]
  WCHAR pszPath[264]; // [rsp+6D0h] [rbp+5D0h] BYREF

  memset_0(pszPath, 0, 0x208u);
  memset_0(v38, 0, 0x670u);
  CriticalSectionWithConditionVariable::Lock(&this[425], v37);
  if ( this[440].Ptr != (PVOID)0x700000005LL )
  {
    v3 = ZTraceReportOrigination(-2147467260, "ServiceManager::ClearMapData", 1010, this);
    RelockableGate::~RelockableGate((RelockableGate *)v37);
    return (unsigned int)v3;
  }
  v2 = 0;
  v34 = 0;
  v35[0] = 0;
  v35[1] = 5;
  v36[0] = v35;
  v36[1] = v36;
  if ( (unsigned __int8)ClientsTracker::HasClientsOf(&this[477], v36) && !LOBYTE(this[539].Ptr) )
  {
    v3 = ZTraceReportOrigination(-2080374784, "ServiceManager::ClearMapData", 1014, this);
    RelockableGate::~RelockableGate((RelockableGate *)v37);
    v4 = this + 442;
    v5 = (int *)&this[442].Ptr + 1;
    goto LABEL_49;
  }
  RelockableGate::~RelockableGate((RelockableGate *)v37);
  v4 = this + 442;
  LODWORD(this[442].Ptr) = 5;
  v5 = (int *)&this[442].Ptr + 1;
  HIDWORD(this[442].Ptr) = 0;
  ServiceManager::FireOdmlStateChange((ServiceManager *)this);
  CurrentLocation = MosStorageGetCurrentLocation((struct _STORAGE_DEVICE_DATA *)v38);
  if ( CurrentLocation < 0 )
    ZTraceReportIgnore(CurrentLocation, "ServiceManager::ClearMapData", 1019, this);
  v9 = v39 != 0;
  if ( OfflineMapsTelemetry::IsEnabled(v8, v7) )
  {
    v10 = OfflineMapsTelemetry::Instance();
    OfflineMapsTelemetry::OfflineDeleteAllStart_(v10, v9, v40, v41);
  }
  v2 = 1;
  DataDirectory = ServiceManager::AttachClient(this, 3, 1, 0, 0);
  if ( DataDirectory < 0 )
  {
    v12 = 1022;
LABEL_11:
    v13 = ZTraceReportPropagation(DataDirectory, "ServiceManager::ClearMapData", v12, this);
LABEL_12:
    v3 = v13;
    goto LABEL_49;
  }
  v34 = 1;
  DataDirectory = MosStorageGetDataDirectory(pszPath, 0x104u);
  if ( DataDirectory < 0 )
  {
    v12 = 1025;
    goto LABEL_11;
  }
  LastError = PathCchRemoveBackslash(pszPath, 0x104u);
  if ( LastError < 0 )
  {
    v15 = 1029;
LABEL_17:
    v13 = ZTraceReportOrigination(LastError, "ServiceManager::ClearMapData", v15, this);
    goto LABEL_12;
  }
  FileAttributesW = GetFileAttributesW(pszPath);
  if ( FileAttributesW == -1 )
  {
    LastError = GetLastError();
    if ( LastError )
    {
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      LastError = -2143748092;
    }
    v15 = 1032;
    goto LABEL_17;
  }
  if ( (FileAttributesW & 0x10) == 0 )
  {
    if ( (FileAttributesW & 1) != 0 && !SetFileAttributesW(pszPath, FileAttributesW & 0xFFFFFFFE) )
    {
      LastError = GetLastError();
      if ( LastError )
      {
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        LastError = -2143748092;
      }
      v15 = 1051;
      goto LABEL_17;
    }
    if ( !DeleteFileW(pszPath) )
    {
      LastError = GetLastError();
      if ( LastError )
      {
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        LastError = -2143748092;
      }
      v15 = 1055;
      goto LABEL_17;
    }
    goto LABEL_31;
  }
  CallingStateTracker::CallingStateTracker(v35);
  v2 = 2;
  if ( !pszPath[0] )
  {
    v17 = -2147418113;
LABEL_34:
    v3 = ZTraceReportPropagation(v17, "ServiceManager::ClearMapData", 1041, this);
    CallingStateTracker::~CallingStateTracker((CallingStateTracker *)v35);
    goto LABEL_49;
  }
  v17 = 0;
  v18 = GetFileAttributesW(pszPath);
  if ( v18 != -1 && (v18 & 0x400) == 0 )
    v17 = RecursiveScanDirectory(
            pszPath,
            0,
            (int (__high *const)(enum DIRECTORY_SCAN_STATE, const unsigned __int16 *, struct _WIN32_FIND_DATAW *, void *))&ForceDelete,
            0);
  if ( v17 < 0 )
    goto LABEL_34;
  CallingStateTracker::~CallingStateTracker((CallingStateTracker *)v35);
LABEL_31:
  DataDirectory = ServiceManager::CleanupRegistryState((ServiceManager *)this);
  if ( DataDirectory < 0 )
  {
    v12 = 1059;
    goto LABEL_11;
  }
  v3 = 0;
LABEL_49:
  CriticalSectionWithConditionVariable::Lock(&this[425], v36);
  if ( LOBYTE(this[539].Ptr) )
  {
    updated = ServiceManager::UpdateMapsRepairAttempts((ServiceManager *)this);
    if ( updated < 0 )
      ZTraceReportIgnore(updated, "ServiceManager::ClearMapData", 1069, this);
  }
  if ( v34 )
  {
    v2 = 3;
    v20 = ServiceManager::DetachClient(this, 3, 0);
    v3 = v20;
    if ( v20 < 0 )
      ZTraceReportIgnore(v20, "ServiceManager::ClearMapData", 1077, this);
  }
  this[440].Ptr = 0;
  RelockableGate::~RelockableGate((RelockableGate *)v36);
  WakeAllConditionVariable(this + 430);
  if ( v3 < 0 )
  {
    LODWORD(v4->Ptr) = 1;
    *v5 = v3;
    ServiceManager::FireOdmlStateChange((ServiceManager *)this);
  }
  v23 = v2 - 1;
  if ( v23 )
  {
    v24 = v23 - 1;
    if ( v24 )
    {
      if ( v24 == 1 )
      {
        if ( v3 >= 0 )
        {
          v27 = v39 != 0;
          if ( OfflineMapsTelemetry::IsEnabled(v22, v21) )
          {
            v28 = OfflineMapsTelemetry::Instance();
            OfflineMapsTelemetry::OfflineDeleteAllComplete_(v28, v27, v40, v41);
          }
        }
        else
        {
          v25 = v39 != 0;
          if ( OfflineMapsTelemetry::IsEnabled(v22, v21) )
          {
            v26 = OfflineMapsTelemetry::Instance();
            OfflineMapsTelemetry::OfflineDeleteAllFailedToDetachDeleteAllClient_(v26, v25, v40, v41, v3);
          }
        }
      }
    }
    else
    {
      v29 = v39 != 0;
      if ( OfflineMapsTelemetry::IsEnabled(v22, v21) )
      {
        v30 = OfflineMapsTelemetry::Instance();
        OfflineMapsTelemetry::OfflineDeleteAllFailedClearData_(v30, v29, v40, v41, v3);
      }
    }
  }
  else
  {
    v31 = v39 != 0;
    if ( OfflineMapsTelemetry::IsEnabled(v22, v21) )
    {
      v32 = OfflineMapsTelemetry::Instance();
      OfflineMapsTelemetry::OfflineDeleteAllFailedToAttachDeleteAllClient_(v32, v31, v40, v41, v3);
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180013870  push    rbp
0x180013872  push    rbx
0x180013873  push    rsi
0x180013874  push    rdi
0x180013875  push    r12
0x180013877  push    r13
0x180013879  push    r14
0x18001387b  push    r15
0x18001387d  lea     rbp, [rsp-7F8h]
0x180013885  sub     rsp, 8F8h
0x18001388c  mov     rax, cs:__security_cookie
0x180013893  xor     rax, rsp
0x180013896  mov     [rbp+830h+var_50], rax
0x18001389d  mov     rbx, rcx
0x1800138a0  xor     edx, edx; Val
0x1800138a2  mov     r8d, 208h; Size
0x1800138a8  lea     rcx, [rbp+830h+pszPath]; void *
0x1800138af  call    memset_0
0x1800138b4  xor     edx, edx; Val
0x1800138b6  mov     r8d, 670h; Size
0x1800138bc  lea     rcx, [rsp+930h+var_8D0]; void *
0x1800138c1  call    memset_0
0x1800138c6  lea     r13, [rbx+0D48h]
0x1800138cd  lea     rdx, [rsp+930h+var_8E0]
0x1800138d2  mov     rcx, r13
0x1800138d5  call    ?Lock@CriticalSectionWithConditionVariable@@QEAA?AVRelockableGate@@XZ; CriticalSectionWithConditionVariable::Lock(void)
0x1800138da  nop
0x1800138db  mov     edi, 5
0x1800138e0  cmp     [rbx+0DC0h], edi
0x1800138e6  jnz     loc_180013D76
0x1800138ec  cmp     dword ptr [rbx+0DC4h], 7
0x1800138f3  jnz     loc_180013D76
0x1800138f9  xor     esi, esi
0x1800138fb  mov     [rsp+930h+var_900], sil
0x180013900  mov     [rsp+930h+var_8F8], esi
0x180013904  mov     [rsp+930h+var_8F4], edi
0x180013908  lea     rax, [rsp+930h+var_8F8]
0x18001390d  mov     [rsp+930h+var_8F0], rax
0x180013912  lea     rax, [rsp+930h+var_8F0]
0x180013917  mov     [rsp+930h+var_8E8], rax
0x18001391c  lea     rcx, [rbx+0EE8h]
0x180013923  lea     rdx, [rsp+930h+var_8F0]
0x180013928  call    ?HasClientsOf@ClientsTracker@@QEAA_NAEBV?$initializer_list@W4MapsClientType@@@std@@@Z; ClientsTracker::HasClientsOf(std::initializer_list<MapsClientType> const &)
0x18001392d  test    al, al
0x18001392f  jz      short loc_180013977
0x180013931  cmp     [rbx+10D8h], sil
0x180013938  jnz     short loc_180013977
0x18001393a  mov     r9, rbx
0x18001393d  mov     r8d, 3F6h
0x180013943  lea     r14, aServicemanager_79; "ServiceManager::ClearMapData"
0x18001394a  mov     rdx, r14
0x18001394d  mov     ecx, 84000000h
0x180013952  call    cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x180013958  mov     edi, eax
0x18001395a  lea     rcx, [rsp+930h+var_8E0]; this
0x18001395f  call    ??1RelockableGate@@QEAA@XZ; RelockableGate::~RelockableGate(void)
0x180013964  lea     r15, [rbx+0DD0h]
0x18001396b  lea     r12, [rbx+0DD4h]
0x180013972  jmp     loc_180013BE0
0x180013977  lea     rcx, [rsp+930h+var_8E0]; this
0x18001397c  call    ??1RelockableGate@@QEAA@XZ; RelockableGate::~RelockableGate(void)
0x180013981  lea     r15, [rbx+0DD0h]
0x180013988  mov     [r15], edi
0x18001398b  lea     r12, [rbx+0DD4h]
0x180013992  mov     [r12], esi
0x180013996  mov     rcx, rbx; this
0x180013999  call    ?FireOdmlStateChange@ServiceManager@@AEAAXXZ; ServiceManager::FireOdmlStateChange(void)
0x18001399e  lea     rcx, [rsp+930h+var_8D0]
0x1800139a3  call    cs:__imp_?MosStorageGetCurrentLocation@@YAJPEAU_STORAGE_DEVICE_DATA@@@Z; MosStorageGetCurrentLocation(_STORAGE_DEVICE_DATA *)
0x1800139a9  lea     r14, aServicemanager_79; "ServiceManager::ClearMapData"
0x1800139b0  test    eax, eax
0x1800139b2  jns     short loc_1800139C8
0x1800139b4  mov     r9, rbx
0x1800139b7  mov     r8d, 3FBh
0x1800139bd  mov     rdx, r14
0x1800139c0  mov     ecx, eax
0x1800139c2  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x1800139c8  cmp     [rsp+930h+var_8CC], esi
0x1800139cc  setnz   dil
0x1800139d0  call    ?IsEnabled@OfflineMapsTelemetry@@SA_NE_K@Z; OfflineMapsTelemetry::IsEnabled(uchar,unsigned __int64)
0x1800139d5  test    al, al
0x1800139d7  jz      short loc_1800139F7
0x1800139d9  call    ?Instance@OfflineMapsTelemetry@@KAPEAV1@XZ; OfflineMapsTelemetry::Instance(void)
0x1800139de  mov     r9d, [rbp+830h+var_270]; unsigned int
0x1800139e5  mov     r8d, [rbp+830h+var_6BC]; unsigned int
0x1800139ec  mov     dl, dil; bool
0x1800139ef  mov     rcx, rax; this
0x1800139f2  call    ?OfflineDeleteAllStart_@OfflineMapsTelemetry@@QEAAX_NII@Z; OfflineMapsTelemetry::OfflineDeleteAllStart_(bool,uint,uint)
0x1800139f7  mov     edi, 1
0x1800139fc  mov     esi, edi
0x1800139fe  mov     qword ptr [rsp+930h+var_910], 0
0x180013a07  xor     r9d, r9d
0x180013a0a  mov     r8d, edi
0x180013a0d  lea     edx, [rdi+2]
0x180013a10  mov     rcx, rbx
0x180013a13  call    ?AttachClient@ServiceManager@@UEAAJW4MapsClientType@@W4__MIDL___MIDL_itf_moshostapi_0000_0000_0001@@KPEAX@Z; ServiceManager::AttachClient(MapsClientType,__MIDL___MIDL_itf_moshostapi_0000_0000_0001,ulong,void *)
0x180013a18  test    eax, eax
0x180013a1a  jns     short loc_180013A37
0x180013a1c  mov     r8d, 3FEh
0x180013a22  mov     r9, rbx
0x180013a25  mov     rdx, r14
0x180013a28  mov     ecx, eax
0x180013a2a  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x180013a30  mov     edi, eax
0x180013a32  jmp     loc_180013BE0
0x180013a37  mov     [rsp+930h+var_900], dil
0x180013a3c  mov     edi, 104h
0x180013a41  mov     edx, edi
0x180013a43  lea     rcx, [rbp+830h+pszPath]
0x180013a4a  call    cs:__imp_?MosStorageGetDataDirectory@@YAJPEAGK@Z; MosStorageGetDataDirectory(ushort *,ulong)
0x180013a50  test    eax, eax
0x180013a52  jns     short loc_180013A5C
0x180013a54  mov     r8d, 401h
0x180013a5a  jmp     short loc_180013A22
0x180013a5c  mov     rdx, rdi; cchPath
0x180013a5f  lea     rcx, [rbp+830h+pszPath]; pszPath
0x180013a66  call    cs:__imp_PathCchRemoveBackslash
0x180013a6c  test    eax, eax
0x180013a6e  jns     short loc_180013A86
0x180013a70  mov     r8d, 405h
0x180013a76  mov     r9, rbx
0x180013a79  mov     rdx, r14
0x180013a7c  mov     ecx, eax
0x180013a7e  call    cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x180013a84  jmp     short loc_180013A30
0x180013a86  lea     rcx, [rbp+830h+pszPath]; lpFileName
0x180013a8d  call    cs:__imp_GetFileAttributesW
0x180013a93  cmp     eax, 0FFFFFFFFh
0x180013a96  jnz     short loc_180013ABB
0x180013a98  call    cs:__imp_GetLastError
0x180013a9e  test    eax, eax
0x180013aa0  jz      short loc_180013AAE
0x180013aa2  jle     short loc_180013AB3
0x180013aa4  movzx   eax, ax
0x180013aa7  or      eax, 80070000h
0x180013aac  jmp     short loc_180013AB3
0x180013aae  mov     eax, 80390004h
0x180013ab3  mov     r8d, 408h
0x180013ab9  jmp     short loc_180013A76
0x180013abb  test    al, 10h
0x180013abd  jz      loc_180013B62
0x180013ac3  lea     rcx, [rsp+930h+var_8F8]
0x180013ac8  call    ??0CallingStateTracker@@QEAA@W4CallingState@@@Z; CallingStateTracker::CallingStateTracker(CallingState)
0x180013acd  nop
0x180013ace  mov     esi, 2
0x180013ad3  xor     eax, eax
0x180013ad5  cmp     ax, [rbp+830h+pszPath]
0x180013adc  jz      short loc_180013B3B
0x180013ade  xor     edi, edi
0x180013ae0  lea     rcx, [rbp+830h+pszPath]; lpFileName
0x180013ae7  call    cs:__imp_GetFileAttributesW
0x180013aed  cmp     eax, 0FFFFFFFFh
0x180013af0  jz      short loc_180013B12
0x180013af2  bt      eax, 0Ah
0x180013af6  jb      short loc_180013B12
0x180013af8  xor     r9d, r9d; void *
0x180013afb  lea     r8, ForceDelete; int (__high *)(enum DIRECTORY_SCAN_STATE, const unsigned __int16 *, struct _WIN32_FIND_DATAW *, void *)
0x180013b02  xor     edx, edx; int
0x180013b04  lea     rcx, [rbp+830h+pszPath]; unsigned __int16 *
0x180013b0b  call    ?RecursiveScanDirectory@@YAJPEBGHQ6AJW4DIRECTORY_SCAN_STATE@@0PEAU_WIN32_FIND_DATAW@@PEAX@Z3@Z; RecursiveScanDirectory(ushort const *,int,long (*const)(DIRECTORY_SCAN_STATE,ushort const *,_WIN32_FIND_DATAW *,void *),void *)
0x180013b10  mov     edi, eax
0x180013b12  test    edi, edi
0x180013b14  js      short loc_180013B40
0x180013b16  lea     rcx, [rsp+930h+var_8F8]; this
0x180013b1b  call    ??1CallingStateTracker@@QEAA@XZ; CallingStateTracker::~CallingStateTracker(void)
0x180013b20  mov     rcx, rbx; this
0x180013b23  call    ?CleanupRegistryState@ServiceManager@@AEAAJXZ; ServiceManager::CleanupRegistryState(void)
0x180013b28  test    eax, eax
0x180013b2a  jns     loc_180013BDE
0x180013b30  mov     r8d, 423h
0x180013b36  jmp     loc_180013A22
0x180013b3b  mov     edi, 8000FFFFh
0x180013b40  mov     r9, rbx
0x180013b43  mov     r8d, 411h
0x180013b49  mov     rdx, r14
0x180013b4c  mov     ecx, edi
0x180013b4e  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x180013b54  mov     edi, eax
0x180013b56  lea     rcx, [rsp+930h+var_8F8]; this
0x180013b5b  call    ??1CallingStateTracker@@QEAA@XZ; CallingStateTracker::~CallingStateTracker(void)
0x180013b60  jmp     short loc_180013BE0
0x180013b62  test    sil, al
0x180013b65  jz      short loc_180013BA3
0x180013b67  and     eax, 0FFFFFFFEh
0x180013b6a  mov     edx, eax; dwFileAttributes
0x180013b6c  lea     rcx, [rbp+830h+pszPath]; lpFileName
0x180013b73  call    cs:__imp_SetFileAttributesW
0x180013b79  test    eax, eax
0x180013b7b  jnz     short loc_180013BA3
0x180013b7d  call    cs:__imp_GetLastError
0x180013b83  test    eax, eax
0x180013b85  jz      short loc_180013B93
0x180013b87  jle     short loc_180013B98
0x180013b89  movzx   eax, ax
0x180013b8c  or      eax, 80070000h
0x180013b91  jmp     short loc_180013B98
0x180013b93  mov     eax, 80390004h
0x180013b98  mov     r8d, 41Bh
0x180013b9e  jmp     loc_180013A76
0x180013ba3  lea     rcx, [rbp+830h+pszPath]; lpFileName
0x180013baa  call    cs:__imp_DeleteFileW
0x180013bb0  test    eax, eax
0x180013bb2  jnz     loc_180013B20
0x180013bb8  call    cs:__imp_GetLastError
0x180013bbe  test    eax, eax
0x180013bc0  jz      short loc_180013BCE
0x180013bc2  jle     short loc_180013BD3
0x180013bc4  movzx   eax, ax
0x180013bc7  or      eax, 80070000h
0x180013bcc  jmp     short loc_180013BD3
0x180013bce  mov     eax, 80390004h
0x180013bd3  mov     r8d, 41Fh
0x180013bd9  jmp     loc_180013A76
0x180013bde  xor     edi, edi
0x180013be0  lea     rdx, [rsp+930h+var_8F0]
0x180013be5  mov     rcx, r13
0x180013be8  call    ?Lock@CriticalSectionWithConditionVariable@@QEAA?AVRelockableGate@@XZ; CriticalSectionWithConditionVariable::Lock(void)
0x180013bed  nop
0x180013bee  cmp     byte ptr [rbx+10D8h], 0
0x180013bf5  jz      short loc_180013C17
0x180013bf7  mov     rcx, rbx; this
0x180013bfa  call    ?UpdateMapsRepairAttempts@ServiceManager@@AEAAJXZ; ServiceManager::UpdateMapsRepairAttempts(void)
0x180013bff  test    eax, eax
0x180013c01  jns     short loc_180013C17
0x180013c03  mov     r9, rbx
0x180013c06  mov     r8d, 42Dh
0x180013c0c  mov     rdx, r14
0x180013c0f  mov     ecx, eax
0x180013c11  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x180013c17  cmp     [rsp+930h+var_900], 0
0x180013c1c  jz      short loc_180013C4C
0x180013c1e  mov     eax, 3
0x180013c23  mov     esi, eax
0x180013c25  xor     r8d, r8d
0x180013c28  mov     edx, eax
0x180013c2a  mov     rcx, rbx
0x180013c2d  call    ?DetachClient@ServiceManager@@UEAAJW4MapsClientType@@K@Z; ServiceManager::DetachClient(MapsClientType,ulong)
0x180013c32  mov     edi, eax
0x180013c34  test    eax, eax
0x180013c36  jns     short loc_180013C4C
0x180013c38  mov     r9, rbx
0x180013c3b  mov     r8d, 435h
0x180013c41  mov     rdx, r14
0x180013c44  mov     ecx, eax
0x180013c46  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x180013c4c  xor     r14d, r14d
0x180013c4f  mov     [rbx+0DC0h], r14
0x180013c56  lea     rcx, [rsp+930h+var_8F0]; this
0x180013c5b  call    ??1RelockableGate@@QEAA@XZ; RelockableGate::~RelockableGate(void)
0x180013c60  lea     rcx, [r13+28h]; ConditionVariable
0x180013c64  call    cs:__imp_WakeAllConditionVariable
0x180013c6a  test    edi, edi
0x180013c6c  jns     short loc_180013C81
0x180013c6e  mov     dword ptr [r15], 1
0x180013c75  mov     [r12], edi
0x180013c79  mov     rcx, rbx; this
0x180013c7c  call    ?FireOdmlStateChange@ServiceManager@@AEAAXXZ; ServiceManager::FireOdmlStateChange(void)
0x180013c81  sub     esi, 1
0x180013c84  jz      loc_180013D42
0x180013c8a  sub     esi, 1
0x180013c8d  jz      short loc_180013D0E
0x180013c8f  cmp     esi, 1
0x180013c92  jnz     loc_180013D9D
0x180013c98  test    edi, edi
0x180013c9a  jns     short loc_180013CD7
0x180013c9c  cmp     [rsp+930h+var_8CC], r14d
0x180013ca1  setnz   bl
0x180013ca4  call    ?IsEnabled@OfflineMapsTelemetry@@SA_NE_K@Z; OfflineMapsTelemetry::IsEnabled(uchar,unsigned __int64)
0x180013ca9  test    al, al
0x180013cab  jz      loc_180013D9D
0x180013cb1  call    ?Instance@OfflineMapsTelemetry@@KAPEAV1@XZ; OfflineMapsTelemetry::Instance(void)
0x180013cb6  mov     [rsp+930h+var_910], edi; int
0x180013cba  mov     r9d, [rbp+830h+var_270]; unsigned int
0x180013cc1  mov     r8d, [rbp+830h+var_6BC]; unsigned int
0x180013cc8  mov     dl, bl; bool
0x180013cca  mov     rcx, rax; this
0x180013ccd  call    ?OfflineDeleteAllFailedToDetachDeleteAllClient_@OfflineMapsTelemetry@@QEAAX_NIIJ@Z; OfflineMapsTelemetry::OfflineDeleteAllFailedToDetachDeleteAllClient_(bool,uint,uint,long)
0x180013cd2  jmp     loc_180013D9D
0x180013cd7  cmp     [rsp+930h+var_8CC], r14d
0x180013cdc  setnz   bl
0x180013cdf  call    ?IsEnabled@OfflineMapsTelemetry@@SA_NE_K@Z; OfflineMapsTelemetry::IsEnabled(uchar,unsigned __int64)
0x180013ce4  test    al, al
0x180013ce6  jz      loc_180013D9D
0x180013cec  call    ?Instance@OfflineMapsTelemetry@@KAPEAV1@XZ; OfflineMapsTelemetry::Instance(void)
0x180013cf1  mov     r9d, [rbp+830h+var_270]; unsigned int
0x180013cf8  mov     r8d, [rbp+830h+var_6BC]; unsigned int
0x180013cff  mov     dl, bl; bool
0x180013d01  mov     rcx, rax; this
0x180013d04  call    ?OfflineDeleteAllComplete_@OfflineMapsTelemetry@@QEAAX_NII@Z; OfflineMapsTelemetry::OfflineDeleteAllComplete_(bool,uint,uint)
0x180013d09  jmp     loc_180013D9D
0x180013d0e  cmp     [rsp+930h+var_8CC], r14d
0x180013d13  setnz   bl
0x180013d16  call    ?IsEnabled@OfflineMapsTelemetry@@SA_NE_K@Z; OfflineMapsTelemetry::IsEnabled(uchar,unsigned __int64)
0x180013d1b  test    al, al
0x180013d1d  jz      short loc_180013D9D
0x180013d1f  call    ?Instance@OfflineMapsTelemetry@@KAPEAV1@XZ; OfflineMapsTelemetry::Instance(void)
0x180013d24  mov     [rsp+930h+var_910], edi; int
0x180013d28  mov     r9d, [rbp+830h+var_270]; unsigned int
0x180013d2f  mov     r8d, [rbp+830h+var_6BC]; unsigned int
0x180013d36  mov     dl, bl; bool
  ... truncated ...
```
