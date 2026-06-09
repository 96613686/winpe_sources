# UpdateReserveManager::GetScenarioIdOfFile(wchar_t const * const,IUpdateReserveManager::ScenarioId *)

- ea: `0x180017380`
- end: `0x1800176a6`
- name: `?GetScenarioIdOfFile@UpdateReserveManager@@UEAAJQEB_WPEAW4ScenarioId@IUpdateReserveManager@@@Z`
- size: `806`
- prototype: `__int64 __fastcall(UpdateReserveManager *__hidden this, LPCWSTR lpFileName, enum IUpdateReserveManager::ScenarioId *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, loader_planting, installer_update`

## callees

- `0x180003870`
- `0x180008140`
- `0x18000fafc`
- `0x180015ad0`
- `0x1800172a8`
- `0x180017380`
- `0x18001a8f0`
- `0x1800248e0`

## import_xrefs

- `ntdll!NtClose` at `0x1800174db`
- `ntdll!NtClose` at `0x1800175a8`
- `ntdll!NtClose` at `0x1800175fd`
- `ntdll!NtClose` at `0x180017637`
- `ntdll!NtClose` at `0x1800174db`
- `ntdll!NtClose` at `0x1800175a8`
- `ntdll!NtClose` at `0x1800175fd`
- `ntdll!NtClose` at `0x180017637`
- `ntdll!NtQueryInformationFile` at `0x180017542`
- `ntdll!NtQueryInformationFile` at `0x180017542`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800173e8`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180017417`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800174fe`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800175cb`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180017620`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001765a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800173e8`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180017417`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800174fe`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800175cb`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180017620`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001765a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001746c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001768a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001746c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001768a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001744f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001744f`

## string_xrefs

- `0x18001747f`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x180017552`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x18001748b`: `UpdateReserveManager::GetScenarioIdOfFile`
- `0x18001755e`: `UpdateReserveManager::GetScenarioIdOfFile`

## pseudocode

```c
__int64 __fastcall UpdateReserveManager::GetScenarioIdOfFile(
        UpdateReserveManager *this,
        LPCWSTR lpFileName,
        enum IUpdateReserveManager::ScenarioId *a3)
{
  int v6; // eax
  unsigned int v7; // ebx
  __int64 result; // rax
  int v9; // ebx
  const char *v10; // r9
  char *FileW; // rbx
  DWORD LastError; // edi
  int v13; // ecx
  unsigned int v14; // edi
  int ScenarioIdForReserve; // edi
  HANDLE *v16; // [rsp+40h] [rbp-88h] BYREF
  char v17; // [rsp+48h] [rbp-80h]
  const char *v18; // [rsp+50h] [rbp-78h] BYREF
  const char *v19; // [rsp+58h] [rbp-70h]
  __int64 v20; // [rsp+60h] [rbp-68h]
  const char *v21; // [rsp+68h] [rbp-60h]
  __int64 v22; // [rsp+70h] [rbp-58h]
  char *v23; // [rsp+78h] [rbp-50h]
  enum _STORAGE_RESERVE_ID FileInformation; // [rsp+80h] [rbp-48h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+88h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  v22 = -2;
  v16 = (HANDLE *)((char *)this + 1192);
  v17 = 0;
  v6 = AutoMutexLocker::Lock((AutoMutexLocker *)&v16, (unsigned int)lpFileName);
  v7 = v6;
  if ( v6 >= 0 )
  {
    try
    {
      v9 = UpdateReserveManager::EnsureNotInSafeMode(this);
      if ( v9 >= 0 )
      {
        FileW = (char *)CreateFileW(lpFileName, 0x80000000, 7u, 0, 3u, 0x2000000u, 0);
        v23 = FileW;
        if ( ((unsigned __int64)(FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
        {
          IoStatusBlock = 0;
          FileInformation = StorageReserveIdNone;
          v13 = NtQueryInformationFile(FileW, &IoStatusBlock, &FileInformation, 4u, FileRenameInformation|0x40);
          if ( v13 >= 0 )
          {
            ScenarioIdForReserve = UpdateReserveManager::GetScenarioIdForReserve(this, FileInformation, a3);
            if ( ScenarioIdForReserve >= 0 )
            {
              if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL && NtClose(FileW) < 0 )
                __fastfail(7u);
              if ( v17 && *v16 )
                ReleaseMutex(*v16);
              result = 0;
            }
            else
            {
              if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL && NtClose(FileW) < 0 )
                __fastfail(7u);
              if ( v17 && *v16 )
                ReleaseMutex(*v16);
              result = (unsigned int)ScenarioIdForReserve;
            }
          }
          else
          {
            v18 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
            v19 = "UpdateReserveManager::GetScenarioIdOfFile";
            v20 = 839;
            v21 = "::NtQueryInformationFile(FileHandle, &IoStatusBlock, &QueryIdInfo, sizeof(FILE_STORAGE_RESERVE_ID_INFO"
                  "RMATION), FileStorageReserveIdInformation)";
            v14 = ConvertNtStatusToHResult(v13);
            RtlReportErrorOrigination(&v18, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, v14);
            if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL && NtClose(FileW) < 0 )
              __fastfail(7u);
            if ( v17 && *v16 )
              ReleaseMutex(*v16);
            result = v14;
          }
        }
        else
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
          v18 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
          v19 = "UpdateReserveManager::GetScenarioIdOfFile";
          v20 = 830;
          v21 = "FileHandle.IsValid()";
          if ( (int)LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          RtlReportErrorOrigination(&v18, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, LastError);
          if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL && NtClose(FileW) < 0 )
            __fastfail(7u);
          if ( v17 && *v16 )
            ReleaseMutex(*v16);
          result = LastError;
        }
      }
      else
      {
        if ( v17 && *v16 )
          ReleaseMutex(*v16);
        result = (unsigned int)v9;
      }
    }
    catch ( ... )
    {
      return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                             retaddr,
                             (void *)0x34D,
                             (unsigned int)"onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp",
                             v10);
    }
  }
  else
  {
    if ( v17 )
    {
      if ( *v16 )
        ReleaseMutex(*v16);
    }
    return v7;
  }
  return result;
}

```

## disassembly

```asm
0x180017380  push    rbx
0x180017382  push    rsi
0x180017383  push    rdi
0x180017384  push    r12
0x180017386  push    r14
0x180017388  sub     rsp, 0A0h
0x18001738f  mov     [rsp+0C8h+var_58], 0FFFFFFFFFFFFFFFEh
0x180017398  mov     rax, cs:__security_cookie
0x18001739f  xor     rax, rsp
0x1800173a2  mov     [rsp+0C8h+var_30], rax
0x1800173aa  mov     r14, r8
0x1800173ad  mov     rsi, rdx
0x1800173b0  mov     rdi, rcx
0x1800173b3  lea     rax, [rcx+4A8h]
0x1800173ba  mov     [rsp+0C8h+var_88], rax
0x1800173bf  mov     [rsp+0C8h+var_80], 0
0x1800173c4  lea     rcx, [rsp+0C8h+var_88]; this
0x1800173c9  call    ?Lock@AutoMutexLocker@@QEAAJK@Z; AutoMutexLocker::Lock(ulong)
0x1800173ce  mov     ebx, eax
0x1800173d0  test    eax, eax
0x1800173d2  jns     short loc_1800173F5
0x1800173d4  cmp     [rsp+0C8h+var_80], 0
0x1800173d9  jz      short loc_1800173EE
0x1800173db  mov     rcx, [rsp+0C8h+var_88]
0x1800173e0  mov     rcx, [rcx]; hMutex
0x1800173e3  test    rcx, rcx
0x1800173e6  jz      short loc_1800173EE
0x1800173e8  call    cs:__imp_ReleaseMutex
0x1800173ee  mov     eax, ebx
0x1800173f0  jmp     loc_18001766B
0x1800173f5  mov     rcx, rdi; this
0x1800173f8  call    ?EnsureNotInSafeMode@UpdateReserveManager@@AEAAJXZ; UpdateReserveManager::EnsureNotInSafeMode(void)
0x1800173fd  mov     ebx, eax
0x1800173ff  test    eax, eax
0x180017401  jns     short loc_180017424
0x180017403  cmp     [rsp+0C8h+var_80], 0
0x180017408  jz      short loc_18001741D
0x18001740a  mov     rcx, [rsp+0C8h+var_88]
0x18001740f  mov     rcx, [rcx]; hMutex
0x180017412  test    rcx, rcx
0x180017415  jz      short loc_18001741D
0x180017417  call    cs:__imp_ReleaseMutex
0x18001741d  mov     eax, ebx
0x18001741f  jmp     loc_18001766B
0x180017424  mov     [rsp+0C8h+hTemplateFile], 0; hTemplateFile
0x18001742d  mov     [rsp+0C8h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x180017435  mov     [rsp+0C8h+dwCreationDisposition], 3; dwCreationDisposition
0x18001743d  xor     r9d, r9d; lpSecurityAttributes
0x180017440  lea     r12d, [r9+7]
0x180017444  mov     r8d, r12d; dwShareMode
0x180017447  mov     edx, 80000000h; dwDesiredAccess
0x18001744c  mov     rcx, rsi; lpFileName
0x18001744f  call    cs:__imp_CreateFileW
0x180017455  mov     rbx, rax
0x180017458  mov     [rsp+0C8h+var_50], rax
0x18001745d  inc     rax
0x180017460  test    rax, 0FFFFFFFFFFFFFFFEh
0x180017466  jnz     loc_18001750B
0x18001746c  call    cs:__imp_GetLastError
0x180017472  test    eax, eax
0x180017474  jnz     loc_18001768A
0x18001747a  mov     edi, 36FDh
0x18001747f  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x180017486  mov     [rsp+0C8h+var_78], rax
0x18001748b  lea     rax, aUpdatereservem_29; "UpdateReserveManager::GetScenarioIdOfFi"...
0x180017492  mov     [rsp+0C8h+var_70], rax
0x180017497  mov     [rsp+0C8h+var_68], 33Eh
0x1800174a0  lea     rax, aFilehandleIsva; "FileHandle.IsValid()"
0x1800174a7  mov     [rsp+0C8h+var_60], rax
0x1800174ac  test    edi, edi
0x1800174ae  jle     short loc_1800174B9
0x1800174b0  movzx   edi, di
0x1800174b3  or      edi, 80070000h
0x1800174b9  mov     r8d, edi
0x1800174bc  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x1800174c3  lea     rcx, [rsp+0C8h+var_78]
0x1800174c8  call    RtlReportErrorOrigination
0x1800174cd  nop
0x1800174ce  lea     rax, [rbx-1]
0x1800174d2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800174d6  ja      short loc_1800174EA
0x1800174d8  mov     rcx, rbx; Handle
0x1800174db  call    cs:__imp_NtClose
0x1800174e1  test    eax, eax
0x1800174e3  jns     short loc_1800174EA
0x1800174e5  mov     rcx, r12
0x1800174e8  int     29h; Win8: RtlFailFast(ecx)
0x1800174ea  cmp     [rsp+0C8h+var_80], 0
0x1800174ef  jz      short loc_180017504
0x1800174f1  mov     rcx, [rsp+0C8h+var_88]
0x1800174f6  mov     rcx, [rcx]; hMutex
0x1800174f9  test    rcx, rcx
0x1800174fc  jz      short loc_180017504
0x1800174fe  call    cs:__imp_ReleaseMutex
0x180017504  mov     eax, edi
0x180017506  jmp     loc_18001766B
0x18001750b  xorps   xmm0, xmm0
0x18001750e  movups  xmmword ptr [rsp+0C8h+IoStatusBlock], xmm0
0x180017516  mov     [rsp+0C8h+FileInformation], 0
0x180017521  mov     [rsp+0C8h+dwCreationDisposition], 4Ah ; 'J'; FileInformationClass
0x180017529  mov     r9d, 4; Length
0x18001752f  lea     r8, [rsp+0C8h+FileInformation]; FileInformation
0x180017537  lea     rdx, [rsp+0C8h+IoStatusBlock]; IoStatusBlock
0x18001753f  mov     rcx, rbx; FileHandle
0x180017542  call    cs:__imp_NtQueryInformationFile
0x180017548  mov     ecx, eax; Status
0x18001754a  test    eax, eax
0x18001754c  jns     loc_1800175D8
0x180017552  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x180017559  mov     [rsp+0C8h+var_78], rax
0x18001755e  lea     rax, aUpdatereservem_29; "UpdateReserveManager::GetScenarioIdOfFi"...
0x180017565  mov     [rsp+0C8h+var_70], rax
0x18001756a  mov     [rsp+0C8h+var_68], 347h
0x180017573  lea     rax, aNtqueryinforma; "::NtQueryInformationFile(FileHandle, &I"...
0x18001757a  mov     [rsp+0C8h+var_60], rax
0x18001757f  call    ConvertNtStatusToHResult
0x180017584  mov     edi, eax
0x180017586  mov     r8d, eax
0x180017589  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x180017590  lea     rcx, [rsp+0C8h+var_78]
0x180017595  call    RtlReportErrorOrigination
0x18001759a  nop
0x18001759b  lea     rcx, [rbx-1]
0x18001759f  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1800175a3  ja      short loc_1800175B7
0x1800175a5  mov     rcx, rbx; Handle
0x1800175a8  call    cs:__imp_NtClose
0x1800175ae  test    eax, eax
0x1800175b0  jns     short loc_1800175B7
0x1800175b2  mov     rcx, r12
0x1800175b5  int     29h; Win8: RtlFailFast(ecx)
0x1800175b7  cmp     [rsp+0C8h+var_80], 0
0x1800175bc  jz      short loc_1800175D1
0x1800175be  mov     rax, [rsp+0C8h+var_88]
0x1800175c3  mov     rcx, [rax]; hMutex
0x1800175c6  test    rcx, rcx
0x1800175c9  jz      short loc_1800175D1
0x1800175cb  call    cs:__imp_ReleaseMutex
0x1800175d1  mov     eax, edi
0x1800175d3  jmp     loc_18001766B
0x1800175d8  mov     r8, r14; enum IUpdateReserveManager::ScenarioId *
0x1800175db  mov     edx, [rsp+0C8h+FileInformation]; enum _STORAGE_RESERVE_ID
0x1800175e2  mov     rcx, rdi; this
0x1800175e5  call    ?GetScenarioIdForReserve@UpdateReserveManager@@AEAAJW4_STORAGE_RESERVE_ID@@PEAW4ScenarioId@IUpdateReserveManager@@@Z; UpdateReserveManager::GetScenarioIdForReserve(_STORAGE_RESERVE_ID,IUpdateReserveManager::ScenarioId *)
0x1800175ea  mov     edi, eax
0x1800175ec  test    eax, eax
0x1800175ee  jns     short loc_18001762A
0x1800175f0  lea     rcx, [rbx-1]
0x1800175f4  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1800175f8  ja      short loc_18001760C
0x1800175fa  mov     rcx, rbx; Handle
0x1800175fd  call    cs:__imp_NtClose
0x180017603  test    eax, eax
0x180017605  jns     short loc_18001760C
0x180017607  mov     rcx, r12
0x18001760a  int     29h; Win8: RtlFailFast(ecx)
0x18001760c  cmp     [rsp+0C8h+var_80], 0
0x180017611  jz      short loc_180017626
0x180017613  mov     rax, [rsp+0C8h+var_88]
0x180017618  mov     rcx, [rax]; hMutex
0x18001761b  test    rcx, rcx
0x18001761e  jz      short loc_180017626
0x180017620  call    cs:__imp_ReleaseMutex
0x180017626  mov     eax, edi
0x180017628  jmp     short loc_18001766B
0x18001762a  lea     rax, [rbx-1]
0x18001762e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180017632  ja      short loc_180017646
0x180017634  mov     rcx, rbx; Handle
0x180017637  call    cs:__imp_NtClose
0x18001763d  test    eax, eax
0x18001763f  jns     short loc_180017646
0x180017641  mov     rcx, r12
0x180017644  int     29h; Win8: RtlFailFast(ecx)
0x180017646  cmp     [rsp+0C8h+var_80], 0
0x18001764b  jz      short loc_180017660
0x18001764d  mov     rax, [rsp+0C8h+var_88]
0x180017652  mov     rcx, [rax]; hMutex
0x180017655  test    rcx, rcx
0x180017658  jz      short loc_180017660
0x18001765a  call    cs:__imp_ReleaseMutex
0x180017660  xor     eax, eax
0x180017662  jmp     short loc_18001766B
0x180017664  mov     eax, [rsp+0C8h+FileInformation]
0x18001766b  mov     rcx, [rsp+0C8h+var_30]
0x180017673  xor     rcx, rsp; StackCookie
0x180017676  call    __security_check_cookie
0x18001767b  add     rsp, 0A0h
0x180017682  pop     r14
0x180017684  pop     r12
0x180017686  pop     rdi
0x180017687  pop     rsi
0x180017688  pop     rbx
0x180017689  retn
0x18001768a  call    cs:__imp_GetLastError
0x180017690  mov     edi, eax
0x180017692  test    eax, eax
0x180017694  jnz     loc_18001747F
0x18001769a  mov     ecx, 0C00000E5h; int
0x18001769f  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
