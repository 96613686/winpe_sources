# UpdateReserveManager::PrepareTIForReserveInitialization(IUpdateReserveManager::PrepareTIForReserveInitializationFlags)

- ea: `0x18001bd30`
- end: `0x18001c233`
- name: `?PrepareTIForReserveInitialization@UpdateReserveManager@@UEAAJW4PrepareTIForReserveInitializationFlags@IUpdateReserveManager@@@Z`
- size: `1283`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x180003870`
- `0x180008140`
- `0x18000fafc`
- `0x180010ea4`
- `0x180010fe0`
- `0x18001a8f0`
- `0x18001bd30`
- `0x18001c23c`
- `0x18001e228`
- `0x18001fdb8`
- `0x18001ff90`
- `0x1800248e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001bd9f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001be26`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001bedc`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001bf9e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001c052`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001c0ea`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001c14d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001c1b1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001c1ed`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001bd9f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001be26`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001bedc`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001bf9e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001c052`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001c0ea`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001c14d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001c1b1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001c1ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bf1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c161`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bf1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c161`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x18001bf0f`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x18001bf0f`
- `api-ms-win-core-registry-l2-1-0!RegSetKeyValueW` at `0x18001bfd4`
- `api-ms-win-core-registry-l2-1-0!RegSetKeyValueW` at `0x18001bfd4`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyValueW` at `0x18001be48`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyValueW` at `0x18001c06d`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyValueW` at `0x18001be48`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyValueW` at `0x18001c06d`

## string_xrefs

- `0x18001be61`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x18001bf30`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x18001bfe4`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x18001c07e`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x18001be70`: `UpdateReserveManager::PrepareTIForReserveInitialization`
- `0x18001bf3c`: `UpdateReserveManager::PrepareTIForReserveInitialization`
- `0x18001bff0`: `UpdateReserveManager::PrepareTIForReserveInitialization`
- `0x18001c08a`: `UpdateReserveManager::PrepareTIForReserveInitialization`
- `0x18001be33`: `TiAttemptedInitialization`
- `0x18001bf51`: `EnsureBOOL(::GetDiskFreeSpaceExW(m_WindowsDirPath, nullptr, nullptr, &FreeUserSpace))`
- `0x18001c005`: `::RegSetKeyValueW(m_SoftwareKey, L"Microsoft\\Windows\\CurrentVersion\\ReserveManager", L"UserFreeSpaceMarker", ( 11ul ), &FreeUserSpace.QuadPart, sizeof(FreeUserSpace.QuadPart))`

## pseudocode

```c
__int64 __fastcall UpdateReserveManager::PrepareTIForReserveInitialization(__int64 a1, unsigned int a2)
{
  signed int v4; // eax
  unsigned int v5; // ebx
  __int64 result; // rax
  NTSTATUS v7; // eax
  unsigned int v8; // ebx
  const char *v9; // r9
  LSTATUS v10; // eax
  unsigned int v11; // ebx
  DWORD LastError; // ebx
  int v13; // ebx
  LSTATUS v14; // eax
  unsigned int v15; // ebx
  bool v16; // si
  int v17; // ebx
  int started; // ebx
  bool v19; // [rsp+30h] [rbp-98h] BYREF
  HANDLE *v20; // [rsp+38h] [rbp-90h] BYREF
  char v21; // [rsp+40h] [rbp-88h]
  const char *v22; // [rsp+48h] [rbp-80h] BYREF
  const char *v23; // [rsp+50h] [rbp-78h]
  __int64 v24; // [rsp+58h] [rbp-70h]
  const char *v25; // [rsp+60h] [rbp-68h]
  __int64 v26; // [rsp+68h] [rbp-60h]
  HANDLE v27; // [rsp+70h] [rbp-58h] BYREF
  char v28; // [rsp+78h] [rbp-50h]
  union _ULARGE_INTEGER TotalNumberOfFreeBytes; // [rsp+80h] [rbp-48h] BYREF
  __int64 v30; // [rsp+88h] [rbp-40h]
  __int64 v31; // [rsp+90h] [rbp-38h]
  const char *v32; // [rsp+98h] [rbp-30h]
  _DWORD v33[2]; // [rsp+A0h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  v26 = -2;
  v20 = (HANDLE *)(a1 + 1192);
  v21 = 0;
  v4 = AutoMutexLocker::Lock(&v20);
  v5 = v4;
  if ( v4 < 0 )
  {
    if ( v21 )
    {
      if ( *v20 )
        ReleaseMutex(*v20);
    }
    return v5;
  }
  v33[0] = 17;
  v33[1] = 18;
  v27 = 0;
  v28 = 0;
  TotalNumberOfFreeBytes.QuadPart = (ULONGLONG)v33;
  v30 = 2;
  try
  {
    v7 = RtlSystemUtil::PrivilegeAcquisition::Acquire((__int64)&v27, (__int64)&TotalNumberOfFreeBytes);
    if ( v7 >= 0 )
    {
      v10 = RegDeleteKeyValueW(
              *(HKEY *)(a1 + 104),
              L"Microsoft\\Windows\\CurrentVersion\\ReserveManager",
              L"TiAttemptedInitialization");
      v11 = v10;
      if ( v10 == 2 || !v10 )
      {
        if ( (a2 & 1) != 0 )
        {
          TotalNumberOfFreeBytes.QuadPart = 0;
          if ( !GetDiskFreeSpaceExW((LPCWSTR)(a1 + 136), 0, 0, &TotalNumberOfFreeBytes) )
          {
            if ( GetLastError() )
            {
              LastError = GetLastError();
              if ( !LastError )
                INTERNAL_ERROR_ACTION(-1073741595);
            }
            else
            {
              LastError = 14077;
            }
            v22 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
            v23 = "UpdateReserveManager::PrepareTIForReserveInitialization";
            v24 = 1281;
            v25 = "EnsureBOOL(::GetDiskFreeSpaceExW(m_WindowsDirPath, nullptr, nullptr, &FreeUserSpace))";
            if ( (int)LastError > 0 )
              LastError = (unsigned __int16)LastError | 0x80070000;
            RtlReportErrorOrigination(&v22, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, LastError);
            RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(&v27);
            if ( v21 && *v20 )
              ReleaseMutex(*v20);
            return LastError;
          }
          v13 = RegSetKeyValueW(
                  *(HKEY *)(a1 + 104),
                  L"Microsoft\\Windows\\CurrentVersion\\ReserveManager",
                  L"UserFreeSpaceMarker",
                  0xBu,
                  &TotalNumberOfFreeBytes,
                  8u);
          if ( v13 )
          {
            v22 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
            v23 = "UpdateReserveManager::PrepareTIForReserveInitialization";
            v24 = 1288;
            v25 = "::RegSetKeyValueW(m_SoftwareKey, L\"Microsoft\\\\Windows\\\\CurrentVersion\\\\ReserveManager\", L\"Use"
                  "rFreeSpaceMarker\", ( 11ul ), &FreeUserSpace.QuadPart, sizeof(FreeUserSpace.QuadPart))";
            if ( v13 > 0 )
              v13 = (unsigned __int16)v13 | 0x80070000;
            RtlReportErrorOrigination(&v22, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, (unsigned int)v13);
            RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(&v27);
            if ( v21 && *v20 )
              ReleaseMutex(*v20);
            return (unsigned int)v13;
          }
        }
        else
        {
          v14 = RegDeleteKeyValueW(
                  *(HKEY *)(a1 + 104),
                  L"Microsoft\\Windows\\CurrentVersion\\ReserveManager",
                  L"UserFreeSpaceMarker");
          v15 = v14;
          if ( v14 != 2 && v14 )
          {
            v22 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
            v23 = "UpdateReserveManager::PrepareTIForReserveInitialization";
            v24 = 1297;
            v25 = "RetValue";
            if ( v14 > 0 )
              v15 = (unsigned __int16)v14 | 0x80070000;
            RtlReportErrorOrigination(&v22, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, v15);
            RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(&v27);
            if ( v21 && *v20 )
              ReleaseMutex(*v20);
            return v15;
          }
        }
        v16 = 0;
        v19 = 0;
        if ( (a2 & 2) == 0 )
        {
          if ( *(_BYTE *)(a1 + 1176) || *(_BYTE *)(a1 + 1177) )
          {
            started = UpdateReserveManager::SetTIAutoStartValue((UpdateReserveManager *)a1);
            if ( started < 0
              || (started = UpdateReserveManager::SetWinlogonEventsValue((UpdateReserveManager *)a1), started < 0) )
            {
              RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(&v27);
              if ( v21 && *v20 )
                ReleaseMutex(*v20);
              return (unsigned int)started;
            }
          }
          else
          {
            v17 = UpdateReserveManager::PrepareTIForWinlogonOnline((UpdateReserveManager *)a1, &v19);
            if ( v17 < 0 )
            {
              RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(&v27);
              if ( v21 && *v20 )
                ReleaseMutex(*v20);
              return (unsigned int)v17;
            }
            v16 = v19;
          }
        }
        CUpdateReserveManagerDiagnostics::ReportPrepareTIForReserveInitialization((const char *)(a1 + 1200), v16, a2);
        RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(&v27);
        if ( v21 && *v20 )
          ReleaseMutex(*v20);
        return 0;
      }
      TotalNumberOfFreeBytes.QuadPart = (ULONGLONG)"onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
      v30 = (__int64)"UpdateReserveManager::PrepareTIForReserveInitialization";
      v31 = 1274;
      v32 = "RetValue";
      if ( v10 > 0 )
        v11 = (unsigned __int16)v10 | 0x80070000;
      RtlReportErrorOrigination(&TotalNumberOfFreeBytes, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, v11);
      RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(&v27);
      if ( v21 && *v20 )
        ReleaseMutex(*v20);
      result = v11;
    }
    else
    {
      v8 = ConvertNtStatusToHResult(v7);
      RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(&v27);
      if ( v21 && *v20 )
        ReleaseMutex(*v20);
      result = v8;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x527,
                           (unsigned int)"onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp",
                           v9);
  }
  return result;
}

```

## disassembly

```asm
0x18001bd30  mov     rax, rsp
0x18001bd33  push    rdi
0x18001bd34  push    r14
0x18001bd36  push    r15
0x18001bd38  sub     rsp, 0B0h
0x18001bd3f  mov     qword ptr [rax-60h], 0FFFFFFFFFFFFFFFEh
0x18001bd47  mov     [rax+18h], rbx
0x18001bd4b  mov     [rax+20h], rsi
0x18001bd4f  mov     rax, cs:__security_cookie
0x18001bd56  xor     rax, rsp
0x18001bd59  mov     [rsp+0C8h+var_20], rax
0x18001bd61  mov     r14d, edx
0x18001bd64  mov     rdi, rcx
0x18001bd67  lea     rax, [rcx+4A8h]
0x18001bd6e  mov     [rsp+0C8h+var_90], rax
0x18001bd73  xor     r15d, r15d
0x18001bd76  mov     [rsp+0C8h+var_88], r15b
0x18001bd7b  lea     rcx, [rsp+0C8h+var_90]; this
0x18001bd80  call    ?Lock@AutoMutexLocker@@QEAAJK@Z; AutoMutexLocker::Lock(ulong)
0x18001bd85  mov     ebx, eax
0x18001bd87  test    eax, eax
0x18001bd89  jns     short loc_18001BDAC
0x18001bd8b  cmp     [rsp+0C8h+var_88], r15b
0x18001bd90  jz      short loc_18001BDA5
0x18001bd92  mov     rcx, [rsp+0C8h+var_90]
0x18001bd97  mov     rcx, [rcx]; hMutex
0x18001bd9a  test    rcx, rcx
0x18001bd9d  jz      short loc_18001BDA5
0x18001bd9f  call    cs:__imp_ReleaseMutex
0x18001bda5  mov     eax, ebx
0x18001bda7  jmp     loc_18001C1FE
0x18001bdac  mov     [rsp+0C8h+var_28], 11h
0x18001bdb7  mov     [rsp+0C8h+var_24], 12h
0x18001bdc2  mov     [rsp+0C8h+var_58], r15
0x18001bdc7  mov     [rsp+0C8h+var_50], r15b
0x18001bdcc  lea     rax, [rsp+0C8h+var_28]
0x18001bdd4  mov     qword ptr [rsp+0C8h+TotalNumberOfFreeBytes], rax
0x18001bddc  mov     [rsp+0C8h+var_40], 2
0x18001bde8  lea     rdx, [rsp+0C8h+TotalNumberOfFreeBytes]
0x18001bdf0  lea     rcx, [rsp+0C8h+var_58]
0x18001bdf5  call    ?Acquire@PrivilegeAcquisition@RtlSystemUtil@@QEAAJAEBU?$Vector@$$CBJ@Windows@@@Z; RtlSystemUtil::PrivilegeAcquisition::Acquire(Windows::Vector<long const> const &)
0x18001bdfa  test    eax, eax
0x18001bdfc  jns     short loc_18001BE33
0x18001bdfe  mov     ecx, eax; Status
0x18001be00  call    ConvertNtStatusToHResult
0x18001be05  mov     ebx, eax
0x18001be07  lea     rcx, [rsp+0C8h+var_58]; this
0x18001be0c  call    ??1PrivilegeAcquisition@RtlSystemUtil@@QEAA@XZ; RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(void)
0x18001be11  nop
0x18001be12  cmp     [rsp+0C8h+var_88], r15b
0x18001be17  jz      short loc_18001BE2C
0x18001be19  mov     rcx, [rsp+0C8h+var_90]
0x18001be1e  mov     rcx, [rcx]; hMutex
0x18001be21  test    rcx, rcx
0x18001be24  jz      short loc_18001BE2C
0x18001be26  call    cs:__imp_ReleaseMutex
0x18001be2c  mov     eax, ebx
0x18001be2e  jmp     loc_18001C1FE
0x18001be33  lea     r8, aTiattemptedini; "TiAttemptedInitialization"
0x18001be3a  lea     rsi, aMicrosoftWindo_2; "Microsoft\\Windows\\CurrentVersion\\Res"...
0x18001be41  mov     rdx, rsi; lpSubKey
0x18001be44  mov     rcx, [rdi+68h]; hKey
0x18001be48  call    cs:__imp_RegDeleteKeyValueW
0x18001be4e  mov     ebx, eax
0x18001be50  cmp     eax, 2
0x18001be53  jz      loc_18001BEE9
0x18001be59  test    eax, eax
0x18001be5b  jz      loc_18001BEE9
0x18001be61  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x18001be68  mov     qword ptr [rsp+0C8h+TotalNumberOfFreeBytes], rax
0x18001be70  lea     rax, aUpdatereservem_40; "UpdateReserveManager::PrepareTIForReser"...
0x18001be77  mov     [rsp+0C8h+var_40], rax
0x18001be7f  mov     [rsp+0C8h+var_38], 4FAh
0x18001be8b  lea     rax, aRetvalue; "RetValue"
0x18001be92  mov     [rsp+0C8h+var_30], rax
0x18001be9a  jle     short loc_18001BEA5
0x18001be9c  movzx   ebx, bx
0x18001be9f  or      ebx, 80070000h
0x18001bea5  mov     r8d, ebx
0x18001bea8  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x18001beaf  lea     rcx, [rsp+0C8h+TotalNumberOfFreeBytes]
0x18001beb7  call    RtlReportErrorOrigination
0x18001bebc  nop
0x18001bebd  lea     rcx, [rsp+0C8h+var_58]; this
0x18001bec2  call    ??1PrivilegeAcquisition@RtlSystemUtil@@QEAA@XZ; RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(void)
0x18001bec7  nop
0x18001bec8  cmp     [rsp+0C8h+var_88], r15b
0x18001becd  jz      short loc_18001BEE2
0x18001becf  mov     rcx, [rsp+0C8h+var_90]
0x18001bed4  mov     rcx, [rcx]; hMutex
0x18001bed7  test    rcx, rcx
0x18001beda  jz      short loc_18001BEE2
0x18001bedc  call    cs:__imp_ReleaseMutex
0x18001bee2  mov     eax, ebx
0x18001bee4  jmp     loc_18001C1FE
0x18001bee9  test    r14b, 1
0x18001beed  jz      loc_18001C05F
0x18001bef3  mov     qword ptr [rsp+0C8h+TotalNumberOfFreeBytes], r15
0x18001befb  lea     rcx, [rdi+88h]; lpDirectoryName
0x18001bf02  lea     r9, [rsp+0C8h+TotalNumberOfFreeBytes]; lpTotalNumberOfFreeBytes
0x18001bf0a  xor     r8d, r8d; lpTotalNumberOfBytes
0x18001bf0d  xor     edx, edx; lpFreeBytesAvailableToCaller
0x18001bf0f  call    cs:__imp_GetDiskFreeSpaceExW
0x18001bf15  test    eax, eax
0x18001bf17  jnz     loc_18001BFAB
0x18001bf1d  call    cs:__imp_GetLastError
0x18001bf23  test    eax, eax
0x18001bf25  jnz     loc_18001C161
0x18001bf2b  mov     ebx, 36FDh
0x18001bf30  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x18001bf37  mov     [rsp+0C8h+var_80], rax
0x18001bf3c  lea     rax, aUpdatereservem_40; "UpdateReserveManager::PrepareTIForReser"...
0x18001bf43  mov     [rsp+0C8h+var_78], rax
0x18001bf48  mov     [rsp+0C8h+var_70], 501h
0x18001bf51  lea     rax, aEnsureboolGetd_1; "EnsureBOOL(::GetDiskFreeSpaceExW(m_Wind"...
0x18001bf58  mov     [rsp+0C8h+var_68], rax
0x18001bf5d  test    ebx, ebx
0x18001bf5f  jle     short loc_18001BF6A
0x18001bf61  movzx   ebx, bx
0x18001bf64  or      ebx, 80070000h
0x18001bf6a  mov     r8d, ebx
0x18001bf6d  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x18001bf74  lea     rcx, [rsp+0C8h+var_80]
0x18001bf79  call    RtlReportErrorOrigination
0x18001bf7e  nop
0x18001bf7f  lea     rcx, [rsp+0C8h+var_58]; this
0x18001bf84  call    ??1PrivilegeAcquisition@RtlSystemUtil@@QEAA@XZ; RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(void)
0x18001bf89  nop
0x18001bf8a  cmp     [rsp+0C8h+var_88], r15b
0x18001bf8f  jz      short loc_18001BFA4
0x18001bf91  mov     rcx, [rsp+0C8h+var_90]
0x18001bf96  mov     rcx, [rcx]; hMutex
0x18001bf99  test    rcx, rcx
0x18001bf9c  jz      short loc_18001BFA4
0x18001bf9e  call    cs:__imp_ReleaseMutex
0x18001bfa4  mov     eax, ebx
0x18001bfa6  jmp     loc_18001C1FE
0x18001bfab  mov     [rsp+0C8h+cbData], 8; cbData
0x18001bfb3  lea     rax, [rsp+0C8h+TotalNumberOfFreeBytes]
0x18001bfbb  mov     [rsp+0C8h+lpData], rax; lpData
0x18001bfc0  mov     r9d, 0Bh; dwType
0x18001bfc6  lea     r8, aUserfreespacem; "UserFreeSpaceMarker"
0x18001bfcd  mov     rdx, rsi; lpSubKey
0x18001bfd0  mov     rcx, [rdi+68h]; hKey
0x18001bfd4  call    cs:__imp_RegSetKeyValueW
0x18001bfda  mov     ebx, eax
0x18001bfdc  test    eax, eax
0x18001bfde  jz      loc_18001C0F7
0x18001bfe4  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x18001bfeb  mov     [rsp+0C8h+var_80], rax
0x18001bff0  lea     rax, aUpdatereservem_40; "UpdateReserveManager::PrepareTIForReser"...
0x18001bff7  mov     [rsp+0C8h+var_78], rax
0x18001bffc  mov     [rsp+0C8h+var_70], 508h
0x18001c005  lea     rax, aRegsetkeyvalue_7; "::RegSetKeyValueW(m_SoftwareKey, L\"Mic"...
0x18001c00c  mov     [rsp+0C8h+var_68], rax
0x18001c011  test    ebx, ebx
0x18001c013  jle     short loc_18001C01E
0x18001c015  movzx   ebx, bx
0x18001c018  or      ebx, 80070000h
0x18001c01e  mov     r8d, ebx
0x18001c021  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x18001c028  lea     rcx, [rsp+0C8h+var_80]
0x18001c02d  call    RtlReportErrorOrigination
0x18001c032  nop
0x18001c033  lea     rcx, [rsp+0C8h+var_58]; this
0x18001c038  call    ??1PrivilegeAcquisition@RtlSystemUtil@@QEAA@XZ; RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(void)
0x18001c03d  nop
0x18001c03e  cmp     [rsp+0C8h+var_88], r15b
0x18001c043  jz      short loc_18001C058
0x18001c045  mov     rcx, [rsp+0C8h+var_90]
0x18001c04a  mov     rcx, [rcx]; hMutex
0x18001c04d  test    rcx, rcx
0x18001c050  jz      short loc_18001C058
0x18001c052  call    cs:__imp_ReleaseMutex
0x18001c058  mov     eax, ebx
0x18001c05a  jmp     loc_18001C1FE
0x18001c05f  lea     r8, aUserfreespacem; "UserFreeSpaceMarker"
0x18001c066  mov     rdx, rsi; lpSubKey
0x18001c069  mov     rcx, [rdi+68h]; hKey
0x18001c06d  call    cs:__imp_RegDeleteKeyValueW
0x18001c073  mov     ebx, eax
0x18001c075  cmp     eax, 2
0x18001c078  jz      short loc_18001C0F7
0x18001c07a  test    eax, eax
0x18001c07c  jz      short loc_18001C0F7
0x18001c07e  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x18001c085  mov     [rsp+0C8h+var_80], rax
0x18001c08a  lea     rax, aUpdatereservem_40; "UpdateReserveManager::PrepareTIForReser"...
0x18001c091  mov     [rsp+0C8h+var_78], rax
0x18001c096  mov     [rsp+0C8h+var_70], 511h
0x18001c09f  lea     rax, aRetvalue; "RetValue"
0x18001c0a6  mov     [rsp+0C8h+var_68], rax
0x18001c0ab  jle     short loc_18001C0B6
0x18001c0ad  movzx   ebx, bx
0x18001c0b0  or      ebx, 80070000h
0x18001c0b6  mov     r8d, ebx
0x18001c0b9  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x18001c0c0  lea     rcx, [rsp+0C8h+var_80]
0x18001c0c5  call    RtlReportErrorOrigination
0x18001c0ca  nop
0x18001c0cb  lea     rcx, [rsp+0C8h+var_58]; this
0x18001c0d0  call    ??1PrivilegeAcquisition@RtlSystemUtil@@QEAA@XZ; RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(void)
0x18001c0d5  nop
0x18001c0d6  cmp     [rsp+0C8h+var_88], r15b
0x18001c0db  jz      short loc_18001C0F0
0x18001c0dd  mov     rcx, [rsp+0C8h+var_90]
0x18001c0e2  mov     rcx, [rcx]; hMutex
0x18001c0e5  test    rcx, rcx
0x18001c0e8  jz      short loc_18001C0F0
0x18001c0ea  call    cs:__imp_ReleaseMutex
0x18001c0f0  mov     eax, ebx
0x18001c0f2  jmp     loc_18001C1FE
0x18001c0f7  mov     sil, r15b
0x18001c0fa  mov     [rsp+0C8h+var_98], r15b
0x18001c0ff  test    r14b, 2
0x18001c103  jnz     loc_18001C1BB
0x18001c109  cmp     [rdi+498h], r15b
0x18001c110  jnz     short loc_18001C176
0x18001c112  cmp     [rdi+499h], r15b
0x18001c119  jnz     short loc_18001C176
0x18001c11b  lea     rdx, [rsp+0C8h+var_98]; bool *
0x18001c120  mov     rcx, rdi; this
0x18001c123  call    ?PrepareTIForWinlogonOnline@UpdateReserveManager@@AEAAJPEA_N@Z; UpdateReserveManager::PrepareTIForWinlogonOnline(bool *)
0x18001c128  mov     ebx, eax
0x18001c12a  test    eax, eax
0x18001c12c  jns     short loc_18001C15A
0x18001c12e  lea     rcx, [rsp+0C8h+var_58]; this
0x18001c133  call    ??1PrivilegeAcquisition@RtlSystemUtil@@QEAA@XZ; RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(void)
0x18001c138  nop
0x18001c139  cmp     [rsp+0C8h+var_88], r15b
0x18001c13e  jz      short loc_18001C153
0x18001c140  mov     rcx, [rsp+0C8h+var_90]
0x18001c145  mov     rcx, [rcx]; hMutex
0x18001c148  test    rcx, rcx
0x18001c14b  jz      short loc_18001C153
0x18001c14d  call    cs:__imp_ReleaseMutex
0x18001c153  mov     eax, ebx
0x18001c155  jmp     loc_18001C1FE
0x18001c15a  mov     sil, [rsp+0C8h+var_98]
0x18001c15f  jmp     short loc_18001C1BB
0x18001c161  call    cs:__imp_GetLastError
0x18001c167  mov     ebx, eax
0x18001c169  test    eax, eax
0x18001c16b  jz      loc_18001C227
0x18001c171  jmp     loc_18001BF30
0x18001c176  mov     rcx, rdi; this
0x18001c179  call    ?SetTIAutoStartValue@UpdateReserveManager@@AEAAJXZ; UpdateReserveManager::SetTIAutoStartValue(void)
0x18001c17e  mov     ebx, eax
0x18001c180  test    eax, eax
0x18001c182  js      short loc_18001C192
0x18001c184  mov     rcx, rdi; this
0x18001c187  call    ?SetWinlogonEventsValue@UpdateReserveManager@@AEAAJXZ; UpdateReserveManager::SetWinlogonEventsValue(void)
0x18001c18c  mov     ebx, eax
0x18001c18e  test    eax, eax
0x18001c190  jns     short loc_18001C1BB
0x18001c192  lea     rcx, [rsp+0C8h+var_58]; this
0x18001c197  call    ??1PrivilegeAcquisition@RtlSystemUtil@@QEAA@XZ; RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(void)
0x18001c19c  nop
0x18001c19d  cmp     [rsp+0C8h+var_88], r15b
0x18001c1a2  jz      short loc_18001C1B7
0x18001c1a4  mov     rcx, [rsp+0C8h+var_90]
0x18001c1a9  mov     rcx, [rcx]; hMutex
0x18001c1ac  test    rcx, rcx
0x18001c1af  jz      short loc_18001C1B7
0x18001c1b1  call    cs:__imp_ReleaseMutex
0x18001c1b7  mov     eax, ebx
0x18001c1b9  jmp     short loc_18001C1FE
0x18001c1bb  lea     rcx, [rdi+4B0h]; char *
0x18001c1c2  mov     r8d, r14d; unsigned int
0x18001c1c5  mov     dl, sil; bool
0x18001c1c8  call    ?ReportPrepareTIForReserveInitialization@CUpdateReserveManagerDiagnostics@@SAXPEBD_NK@Z; CUpdateReserveManagerDiagnostics::ReportPrepareTIForReserveInitialization(char const *,bool,ulong)
0x18001c1cd  nop
0x18001c1ce  lea     rcx, [rsp+0C8h+var_58]; this
0x18001c1d3  call    ??1PrivilegeAcquisition@RtlSystemUtil@@QEAA@XZ; RtlSystemUtil::PrivilegeAcquisition::~PrivilegeAcquisition(void)
0x18001c1d8  nop
0x18001c1d9  cmp     [rsp+0C8h+var_88], r15b
0x18001c1de  jz      short loc_18001C1F3
0x18001c1e0  mov     rax, [rsp+0C8h+var_90]
0x18001c1e5  mov     rcx, [rax]; hMutex
0x18001c1e8  test    rcx, rcx
0x18001c1eb  jz      short loc_18001C1F3
0x18001c1ed  call    cs:__imp_ReleaseMutex
0x18001c1f3  xor     eax, eax
0x18001c1f5  jmp     short loc_18001C1FE
0x18001c1f7  mov     eax, [rsp+0C8h+var_28]
0x18001c1fe  mov     rcx, [rsp+0C8h+var_20]
0x18001c206  xor     rcx, rsp; StackCookie
0x18001c209  call    __security_check_cookie
0x18001c20e  lea     r11, [rsp+0C8h+var_18]
0x18001c216  mov     rbx, [r11+30h]
0x18001c21a  mov     rsi, [r11+38h]
0x18001c21e  mov     rsp, r11
0x18001c221  pop     r15
0x18001c223  pop     r14
0x18001c225  pop     rdi
0x18001c226  retn
0x18001c227  mov     ecx, 0C00000E5h; int
0x18001c22c  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
