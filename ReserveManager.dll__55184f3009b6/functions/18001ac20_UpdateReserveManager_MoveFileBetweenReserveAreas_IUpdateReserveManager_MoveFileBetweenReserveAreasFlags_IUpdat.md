# UpdateReserveManager::MoveFileBetweenReserveAreas(IUpdateReserveManager::MoveFileBetweenReserveAreasFlags,IUpdateReserveManager::ScenarioId,void * const)

- ea: `0x18001ac20`
- end: `0x18001afe9`
- name: `?MoveFileBetweenReserveAreas@UpdateReserveManager@@UEAAJW4MoveFileBetweenReserveAreasFlags@IUpdateReserveManager@@W4ScenarioId@3@QEAX@Z`
- size: `969`
- prototype: `__int64 __fastcall(UpdateReserveManager *, unsigned int, unsigned int, void *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x180020778`

## callees

- `0x180003870`
- `0x180008140`
- `0x18000fafc`
- `0x180015ad0`
- `0x180016fb8`
- `0x180019da8`
- `0x18001a8f0`
- `0x18001ac20`
- `0x1800248e0`

## import_xrefs

- `ntdll!NtSetInformationFile` at `0x18001af0b`
- `ntdll!NtSetInformationFile` at `0x18001af0b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001ac9a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001acc9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001ad0c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001ad79`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001ae3c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001ae6c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001aec8`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001af74`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001af92`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001ac9a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001acc9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001ad0c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001ad79`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001ae3c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001ae6c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001aec8`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001af74`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001af92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001adc6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001afcd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001adc6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001afcd`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x18001adb8`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x18001adb8`

## string_xrefs

- `0x18001ad20`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x18001add9`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x18001af17`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x18001ad2c`: `UpdateReserveManager::MoveFileBetweenReserveAreas`
- `0x18001ade5`: `UpdateReserveManager::MoveFileBetweenReserveAreas`
- `0x18001af23`: `UpdateReserveManager::MoveFileBetweenReserveAreas`

## pseudocode

```c
__int64 __fastcall UpdateReserveManager::MoveFileBetweenReserveAreas(
        UpdateReserveManager *a1,
        unsigned int a2,
        unsigned int a3,
        void *a4)
{
  char v6; // r14
  int v8; // eax
  unsigned int v9; // ebx
  __int64 result; // rax
  int v11; // ebx
  const char *v12; // r9
  int v13; // ebx
  DWORD LastError; // ebx
  int v15; // r15d
  int ReserveIdForScenario; // ebx
  int v17; // ecx
  unsigned int v18; // ebx
  bool v19; // [rsp+30h] [rbp-C8h] BYREF
  HANDLE *v20; // [rsp+38h] [rbp-C0h] BYREF
  char v21; // [rsp+40h] [rbp-B8h]
  unsigned int v22; // [rsp+48h] [rbp-B0h] BYREF
  const char *v23; // [rsp+50h] [rbp-A8h] BYREF
  const char *v24; // [rsp+58h] [rbp-A0h]
  __int64 v25; // [rsp+60h] [rbp-98h]
  const char *v26; // [rsp+68h] [rbp-90h]
  __int64 v27; // [rsp+70h] [rbp-88h]
  unsigned __int64 v28; // [rsp+78h] [rbp-80h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+80h] [rbp-78h] BYREF
  struct _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+90h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  v27 = -2;
  v6 = a2;
  v20 = (HANDLE *)((char *)a1 + 1192);
  v21 = 0;
  v8 = AutoMutexLocker::Lock((AutoMutexLocker *)&v20, a2);
  v9 = v8;
  if ( v8 < 0 )
  {
    if ( v21 )
    {
      if ( *v20 )
        ReleaseMutex(*v20);
    }
    return v9;
  }
  try
  {
    v11 = UpdateReserveManager::EnsureNotInSafeMode(a1);
    if ( v11 >= 0 )
    {
      if ( (v6 & 2) == 0 )
      {
        v19 = 0;
        v13 = IsHandleToNonEmptyDirectory(a4, &v19);
        if ( v13 < 0 )
        {
          if ( v21 && *v20 )
            ReleaseMutex(*v20);
          return (unsigned int)v13;
        }
        if ( v19 )
        {
          v23 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
          v24 = "UpdateReserveManager::MoveFileBetweenReserveAreas";
          v25 = 709;
          v26 = "((SCODE) (((unsigned long)(1)<<31) | ((unsigned long)(15)<<16) | ((unsigned long)(0x974))) )";
          RtlReportErrorOrigination(&v23, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, 2148469108LL);
          if ( v21 && *v20 )
            ReleaseMutex(*v20);
          return 2148469108LL;
        }
      }
      memset(&FileInformation, 0, sizeof(FileInformation));
      if ( GetFileInformationByHandle(a4, &FileInformation) )
      {
        if ( FileInformation.nNumberOfLinks > 1 && a3 )
        {
          if ( v21 && *v20 )
            ReleaseMutex(*v20);
          return 0;
        }
        else
        {
          v28 = 0;
          v15 = ((v6 & 1) != 0 ? 3 : 0) | 0xC;
          if ( (v6 & 4) == 0 )
            v15 = (v6 & 1) != 0 ? 3 : 0;
          v22 = 0;
          ReserveIdForScenario = UpdateReserveManager::GetReserveIdForScenario(a1, a3, &v22);
          if ( ReserveIdForScenario >= 0 )
          {
            IoStatusBlock = 0;
            v28 = __PAIR64__(v15, v22);
            v17 = NtSetInformationFile(a4, &IoStatusBlock, &v28, 8u, FileRenameInformation|0x40);
            if ( v17 >= 0 )
            {
              if ( v21 && *v20 )
                ReleaseMutex(*v20);
              return 0;
            }
            else
            {
              v23 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
              v24 = "UpdateReserveManager::MoveFileBetweenReserveAreas";
              v25 = 750;
              v26 = "::NtSetInformationFile(FileHandle, &IoStatusBlock, &SetIdInfo, sizeof(FILE_SET_STORAGE_RESERVE_ID_IN"
                    "FORMATION_EX), FileStorageReserveIdInformation)";
              v18 = ConvertNtStatusToHResult(v17);
              RtlReportErrorOrigination(&v23, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, v18);
              if ( v21 && *v20 )
                ReleaseMutex(*v20);
              return v18;
            }
          }
          else
          {
            if ( v21 && *v20 )
              ReleaseMutex(*v20);
            return (unsigned int)ReserveIdForScenario;
          }
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
        v23 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
        v24 = "UpdateReserveManager::MoveFileBetweenReserveAreas";
        v25 = 719;
        v26 = "GetFileInformationByHandle(FileHandle, &FileInfo)";
        if ( (int)LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        RtlReportErrorOrigination(&v23, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, LastError);
        if ( v21 && *v20 )
          ReleaseMutex(*v20);
        return LastError;
      }
    }
    if ( v21 && *v20 )
      ReleaseMutex(*v20);
    result = (unsigned int)v11;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x2F2,
                           (unsigned int)"onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp",
                           v12);
  }
  return result;
}

```

## disassembly

```asm
0x18001ac20  mov     rax, rsp
0x18001ac23  push    rdi
0x18001ac24  push    r12
0x18001ac26  push    r13
0x18001ac28  push    r14
0x18001ac2a  push    r15
0x18001ac2c  sub     rsp, 0D0h
0x18001ac33  mov     [rsp+0F8h+var_88], 0FFFFFFFFFFFFFFFEh
0x18001ac3c  mov     [rax+10h], rbx
0x18001ac40  mov     [rax+18h], rsi
0x18001ac44  mov     rax, cs:__security_cookie
0x18001ac4b  xor     rax, rsp
0x18001ac4e  mov     [rsp+0F8h+var_30], rax
0x18001ac56  mov     rdi, r9
0x18001ac59  mov     r12d, r8d
0x18001ac5c  mov     r14d, edx
0x18001ac5f  mov     rsi, rcx
0x18001ac62  lea     rax, [rcx+4A8h]
0x18001ac69  mov     [rsp+0F8h+var_C0], rax
0x18001ac6e  xor     r13d, r13d
0x18001ac71  mov     [rsp+0F8h+var_B8], r13b
0x18001ac76  lea     rcx, [rsp+0F8h+var_C0]; this
0x18001ac7b  call    ?Lock@AutoMutexLocker@@QEAAJK@Z; AutoMutexLocker::Lock(ulong)
0x18001ac80  mov     ebx, eax
0x18001ac82  test    eax, eax
0x18001ac84  jns     short loc_18001ACA7
0x18001ac86  cmp     [rsp+0F8h+var_B8], r13b
0x18001ac8b  jz      short loc_18001ACA0
0x18001ac8d  mov     rcx, [rsp+0F8h+var_C0]
0x18001ac92  mov     rcx, [rcx]; hMutex
0x18001ac95  test    rcx, rcx
0x18001ac98  jz      short loc_18001ACA0
0x18001ac9a  call    cs:__imp_ReleaseMutex
0x18001aca0  mov     eax, ebx
0x18001aca2  jmp     loc_18001AFA0
0x18001aca7  mov     rcx, rsi; this
0x18001acaa  call    ?EnsureNotInSafeMode@UpdateReserveManager@@AEAAJXZ; UpdateReserveManager::EnsureNotInSafeMode(void)
0x18001acaf  mov     ebx, eax
0x18001acb1  test    eax, eax
0x18001acb3  jns     short loc_18001ACD6
0x18001acb5  cmp     [rsp+0F8h+var_B8], r13b
0x18001acba  jz      short loc_18001ACCF
0x18001acbc  mov     rcx, [rsp+0F8h+var_C0]
0x18001acc1  mov     rcx, [rcx]; hMutex
0x18001acc4  test    rcx, rcx
0x18001acc7  jz      short loc_18001ACCF
0x18001acc9  call    cs:__imp_ReleaseMutex
0x18001accf  mov     eax, ebx
0x18001acd1  jmp     loc_18001AFA0
0x18001acd6  test    r14b, 2
0x18001acda  jnz     loc_18001AD89
0x18001ace0  mov     [rsp+0F8h+var_C8], r13b
0x18001ace5  lea     rdx, [rsp+0F8h+var_C8]; bool *
0x18001acea  mov     rcx, rdi; hFile
0x18001aced  call    ?IsHandleToNonEmptyDirectory@@YAJPEAXPEA_N@Z; IsHandleToNonEmptyDirectory(void *,bool *)
0x18001acf2  mov     ebx, eax
0x18001acf4  test    eax, eax
0x18001acf6  jns     short loc_18001AD19
0x18001acf8  cmp     [rsp+0F8h+var_B8], r13b
0x18001acfd  jz      short loc_18001AD12
0x18001acff  mov     rcx, [rsp+0F8h+var_C0]
0x18001ad04  mov     rcx, [rcx]; hMutex
0x18001ad07  test    rcx, rcx
0x18001ad0a  jz      short loc_18001AD12
0x18001ad0c  call    cs:__imp_ReleaseMutex
0x18001ad12  mov     eax, ebx
0x18001ad14  jmp     loc_18001AFA0
0x18001ad19  cmp     [rsp+0F8h+var_C8], r13b
0x18001ad1e  jz      short loc_18001AD89
0x18001ad20  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x18001ad27  mov     [rsp+0F8h+var_A8], rax
0x18001ad2c  lea     rax, aUpdatereservem_1; "UpdateReserveManager::MoveFileBetweenRe"...
0x18001ad33  mov     [rsp+0F8h+var_A0], rax
0x18001ad38  mov     [rsp+0F8h+var_98], 2C5h
0x18001ad41  lea     rax, aScodeUnsignedL_2; "((SCODE) (((unsigned long)(1)<<31) | (("...
0x18001ad48  mov     [rsp+0F8h+var_90], rax
0x18001ad4d  mov     r8d, 800F0974h
0x18001ad53  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x18001ad5a  lea     rcx, [rsp+0F8h+var_A8]
0x18001ad5f  call    RtlReportErrorOrigination
0x18001ad64  nop
0x18001ad65  cmp     [rsp+0F8h+var_B8], r13b
0x18001ad6a  jz      short loc_18001AD7F
0x18001ad6c  mov     rax, [rsp+0F8h+var_C0]
0x18001ad71  mov     rcx, [rax]; hMutex
0x18001ad74  test    rcx, rcx
0x18001ad77  jz      short loc_18001AD7F
0x18001ad79  call    cs:__imp_ReleaseMutex
0x18001ad7f  mov     eax, 800F0974h
0x18001ad84  jmp     loc_18001AFA0
0x18001ad89  xorps   xmm0, xmm0
0x18001ad8c  xor     eax, eax
0x18001ad8e  movups  xmmword ptr [rsp+0F8h+FileInformation.dwFileAttributes], xmm0
0x18001ad96  movups  xmmword ptr [rsp+0F8h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x18001ad9e  movups  xmmword ptr [rsp+0F8h+FileInformation.nFileSizeHigh], xmm0
0x18001ada6  mov     [rsp+0F8h+FileInformation.nFileIndexLow], eax
0x18001adad  lea     rdx, [rsp+0F8h+FileInformation]; lpFileInformation
0x18001adb5  mov     rcx, rdi; hFile
0x18001adb8  call    cs:__imp_GetFileInformationByHandle
0x18001adbe  test    eax, eax
0x18001adc0  jnz     loc_18001AE49
0x18001adc6  call    cs:__imp_GetLastError
0x18001adcc  test    eax, eax
0x18001adce  jnz     loc_18001AFCD
0x18001add4  mov     ebx, 36FDh
0x18001add9  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x18001ade0  mov     [rsp+0F8h+var_A8], rax
0x18001ade5  lea     rax, aUpdatereservem_1; "UpdateReserveManager::MoveFileBetweenRe"...
0x18001adec  mov     [rsp+0F8h+var_A0], rax
0x18001adf1  mov     [rsp+0F8h+var_98], 2CFh
0x18001adfa  lea     rax, aGetfileinforma_0; "GetFileInformationByHandle(FileHandle, "...
0x18001ae01  mov     [rsp+0F8h+var_90], rax
0x18001ae06  test    ebx, ebx
0x18001ae08  jle     short loc_18001AE13
0x18001ae0a  movzx   ebx, bx
0x18001ae0d  or      ebx, 80070000h
0x18001ae13  mov     r8d, ebx
0x18001ae16  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x18001ae1d  lea     rcx, [rsp+0F8h+var_A8]
0x18001ae22  call    RtlReportErrorOrigination
0x18001ae27  nop
0x18001ae28  cmp     [rsp+0F8h+var_B8], r13b
0x18001ae2d  jz      short loc_18001AE42
0x18001ae2f  mov     rcx, [rsp+0F8h+var_C0]
0x18001ae34  mov     rcx, [rcx]; hMutex
0x18001ae37  test    rcx, rcx
0x18001ae3a  jz      short loc_18001AE42
0x18001ae3c  call    cs:__imp_ReleaseMutex
0x18001ae42  mov     eax, ebx
0x18001ae44  jmp     loc_18001AFA0
0x18001ae49  cmp     [rsp+0F8h+FileInformation.nNumberOfLinks], 1
0x18001ae51  jbe     short loc_18001AE79
0x18001ae53  test    r12d, r12d
0x18001ae56  jz      short loc_18001AE79
0x18001ae58  cmp     [rsp+0F8h+var_B8], r13b
0x18001ae5d  jz      short loc_18001AE72
0x18001ae5f  mov     rax, [rsp+0F8h+var_C0]
0x18001ae64  mov     rcx, [rax]; hMutex
0x18001ae67  test    rcx, rcx
0x18001ae6a  jz      short loc_18001AE72
0x18001ae6c  call    cs:__imp_ReleaseMutex
0x18001ae72  xor     eax, eax
0x18001ae74  jmp     loc_18001AFA0
0x18001ae79  mov     [rsp+0F8h+var_80], r13
0x18001ae7e  mov     al, r14b
0x18001ae81  and     al, 1
0x18001ae83  neg     al
0x18001ae85  sbb     edx, edx
0x18001ae87  and     edx, 3
0x18001ae8a  mov     r15d, edx
0x18001ae8d  or      r15d, 0Ch
0x18001ae91  test    r14b, 4
0x18001ae95  cmovz   r15d, edx
0x18001ae99  mov     [rsp+0F8h+var_B0], r13d
0x18001ae9e  lea     r8, [rsp+0F8h+var_B0]
0x18001aea3  mov     edx, r12d
0x18001aea6  mov     rcx, rsi
0x18001aea9  call    ?GetReserveIdForScenario@UpdateReserveManager@@AEAAJW4ScenarioId@IUpdateReserveManager@@PEAW4_STORAGE_RESERVE_ID@@@Z; UpdateReserveManager::GetReserveIdForScenario(IUpdateReserveManager::ScenarioId,_STORAGE_RESERVE_ID *)
0x18001aeae  mov     ebx, eax
0x18001aeb0  test    eax, eax
0x18001aeb2  jns     short loc_18001AED5
0x18001aeb4  cmp     [rsp+0F8h+var_B8], r13b
0x18001aeb9  jz      short loc_18001AECE
0x18001aebb  mov     rcx, [rsp+0F8h+var_C0]
0x18001aec0  mov     rcx, [rcx]; hMutex
0x18001aec3  test    rcx, rcx
0x18001aec6  jz      short loc_18001AECE
0x18001aec8  call    cs:__imp_ReleaseMutex
0x18001aece  mov     eax, ebx
0x18001aed0  jmp     loc_18001AFA0
0x18001aed5  xorps   xmm0, xmm0
0x18001aed8  movups  xmmword ptr [rsp+0F8h+IoStatusBlock], xmm0
0x18001aee0  mov     dword ptr [rsp+0F8h+var_80+4], r15d
0x18001aee5  mov     eax, [rsp+0F8h+var_B0]
0x18001aee9  mov     dword ptr [rsp+0F8h+var_80], eax
0x18001aeed  mov     [rsp+0F8h+FileInformationClass], 4Ah ; 'J'; FileInformationClass
0x18001aef5  mov     r9d, 8; Length
0x18001aefb  lea     r8, [rsp+0F8h+var_80]; FileInformation
0x18001af00  lea     rdx, [rsp+0F8h+IoStatusBlock]; IoStatusBlock
0x18001af08  mov     rcx, rdi; FileHandle
0x18001af0b  call    cs:__imp_NtSetInformationFile
0x18001af11  mov     ecx, eax; Status
0x18001af13  test    eax, eax
0x18001af15  jns     short loc_18001AF7E
0x18001af17  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x18001af1e  mov     [rsp+0F8h+var_A8], rax
0x18001af23  lea     rax, aUpdatereservem_1; "UpdateReserveManager::MoveFileBetweenRe"...
0x18001af2a  mov     [rsp+0F8h+var_A0], rax
0x18001af2f  mov     [rsp+0F8h+var_98], 2EEh
0x18001af38  lea     rax, aNtsetinformati; "::NtSetInformationFile(FileHandle, &IoS"...
0x18001af3f  mov     [rsp+0F8h+var_90], rax
0x18001af44  call    ConvertNtStatusToHResult
0x18001af49  mov     ebx, eax
0x18001af4b  mov     r8d, eax
0x18001af4e  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x18001af55  lea     rcx, [rsp+0F8h+var_A8]
0x18001af5a  call    RtlReportErrorOrigination
0x18001af5f  nop
0x18001af60  cmp     [rsp+0F8h+var_B8], r13b
0x18001af65  jz      short loc_18001AF7A
0x18001af67  mov     rcx, [rsp+0F8h+var_C0]
0x18001af6c  mov     rcx, [rcx]; hMutex
0x18001af6f  test    rcx, rcx
0x18001af72  jz      short loc_18001AF7A
0x18001af74  call    cs:__imp_ReleaseMutex
0x18001af7a  mov     eax, ebx
0x18001af7c  jmp     short loc_18001AFA0
0x18001af7e  cmp     [rsp+0F8h+var_B8], r13b
0x18001af83  jz      short loc_18001AF98
0x18001af85  mov     rax, [rsp+0F8h+var_C0]
0x18001af8a  mov     rcx, [rax]; hMutex
0x18001af8d  test    rcx, rcx
0x18001af90  jz      short loc_18001AF98
0x18001af92  call    cs:__imp_ReleaseMutex
0x18001af98  xor     eax, eax
0x18001af9a  jmp     short loc_18001AFA0
0x18001af9c  mov     eax, [rsp+0F8h+var_B0]
0x18001afa0  mov     rcx, [rsp+0F8h+var_30]
0x18001afa8  xor     rcx, rsp; StackCookie
0x18001afab  call    __security_check_cookie
0x18001afb0  lea     r11, [rsp+0F8h+var_28]
0x18001afb8  mov     rbx, [r11+38h]
0x18001afbc  mov     rsi, [r11+40h]
0x18001afc0  mov     rsp, r11
0x18001afc3  pop     r15
0x18001afc5  pop     r14
0x18001afc7  pop     r13
0x18001afc9  pop     r12
0x18001afcb  pop     rdi
0x18001afcc  retn
0x18001afcd  call    cs:__imp_GetLastError
0x18001afd3  mov     ebx, eax
0x18001afd5  test    eax, eax
0x18001afd7  jnz     loc_18001ADD9
0x18001afdd  mov     ecx, 0C00000E5h; int
0x18001afe2  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
