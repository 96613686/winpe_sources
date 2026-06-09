# AppxAllUserStore::CleanupPackageFromPerMachineStore(HKEY__ *,ushort const *,Common::Array<AppxAllUserStore::_MainPackageInfo,Common::ContainerOperations<AppxAllUserStore::_MainPackageInfo,AppxAllUserStore::_MainPackageInfo>,Common::NoKey,Common::ContainerOperations<Common::NoKey,AppxAllUserStore::_MainPackageInfo>,Common::ArrayOperations<AppxAllUserStore::_MainPackageInfo,Common::NoKey>> *)

- ea: `0x18003a4b8`
- end: `0x18003a87c`
- name: `?CleanupPackageFromPerMachineStore@AppxAllUserStore@@YAJPEAUHKEY__@@PEBGPEAV?$Array@U_MainPackageInfo@AppxAllUserStore@@V?$ContainerOperations@U_MainPackageInfo@AppxAllUserStore@@U12@@Common@@VNoKey@4@V?$ContainerOperations@VNoKey@Common@@U_MainPackageInfo@AppxAllUserStore@@@4@V?$ArrayOperations@U_MainPackageInfo@AppxAllUserStore@@VNoKey@Common@@@4@@Common@@@Z`
- size: `964`
- prototype: `__int64 __fastcall(HKEY hKey, struct Common::StringBuffer *)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800110cc`

## callees

- `0x180002b1c`
- `0x1800036d4`
- `0x180004920`
- `0x180004968`
- `0x180004b4c`
- `0x180006d40`
- `0x18000bf10`
- `0x18000d6a0`
- `0x18000ed34`
- `0x180016924`
- `0x180017f50`
- `0x18001baf4`
- `0x18001f738`
- `0x180036498`
- `0x18003a4b8`
- `0x18003ad58`
- `0x1800468a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a573`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a573`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18003a569`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18003a569`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x18003a803`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x18003a803`

## string_xrefs

- `0x18003a695`: `Deleted`
- `0x18003a51b`: `\DeletedAllUserPackages`
- `0x18003a811`: `Could not move package to the single instance store deleted folder.`

## pseudocode

```c
__int64 __fastcall AppxAllUserStore::CleanupPackageFromPerMachineStore(HKEY hKey, struct Common::StringBuffer *a2)
{
  int SystemSisFullPath; // eax
  signed int LastErrorMsg; // ebx
  bool *v6; // r8
  __int64 v7; // rdx
  int v8; // eax
  unsigned __int64 v9; // r9
  signed int LastError; // eax
  int appended; // eax
  int v12; // eax
  struct Common::StringBuffer *v13; // r9
  int AllUserChildStorePath; // eax
  int v15; // eax
  const unsigned __int16 *v16; // rdx
  __int64 v17; // rcx
  struct Common::StringBuffer *v18; // r9
  int v19; // eax
  __int64 v20; // rdx
  int v21; // eax
  __int64 v22; // rcx
  LPCWSTR v23; // r8
  __int64 *v24; // rdx
  unsigned int v25; // eax
  __int64 v26; // r9
  int v27; // eax
  unsigned int v29; // [rsp+20h] [rbp-99h]
  char *v30; // [rsp+20h] [rbp-99h]
  char *v31; // [rsp+28h] [rbp-91h]
  HKEY phkResult; // [rsp+50h] [rbp-69h] BYREF
  HKEY v33; // [rsp+58h] [rbp-61h] BYREF
  LPCWSTR v34[2]; // [rsp+60h] [rbp-59h] BYREF
  int v35; // [rsp+70h] [rbp-49h]
  LPCWSTR lpSubKey[2]; // [rsp+78h] [rbp-41h] BYREF
  int v37; // [rsp+88h] [rbp-31h]
  LPCWSTR lpExistingFileName[2]; // [rsp+90h] [rbp-29h] BYREF
  int v39; // [rsp+A0h] [rbp-19h]
  LPCWSTR lpPathName[2]; // [rsp+A8h] [rbp-11h] BYREF
  int v41; // [rsp+B8h] [rbp-1h]
  __int128 v42; // [rsp+C0h] [rbp+7h] BYREF
  int v43; // [rsp+D0h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]
  unsigned __int16 v45; // [rsp+138h] [rbp+7Fh] BYREF

  v42 = 0;
  v43 = 0;
  SystemSisFullPath = Common::Deployment::Configuration::GetSystemSisFullPath(
                        (Common::Deployment::Configuration *)&v42,
                        a2);
  LastErrorMsg = SystemSisFullPath;
  if ( SystemSisFullPath >= 0 )
  {
    v41 = 0;
    *(_OWORD *)lpPathName = 0;
    LastErrorMsg = Common::PathHelpers::CombinePaths(
                     (const struct Common::COMMON_STRING *)&v42,
                     L"\\DeletedAllUserPackages",
                     (struct Common::StringBuffer *)lpPathName);
    if ( LastErrorMsg < 0 )
    {
      v7 = 3584;
LABEL_13:
      v9 = (unsigned int)LastErrorMsg;
      goto LABEL_14;
    }
    LOBYTE(v45) = 0;
    v8 = Common::DirectoryExists((Common *)lpPathName[1], &v45, v6);
    LastErrorMsg = v8;
    if ( v8 < 0 )
    {
      v9 = (unsigned int)v8;
      v7 = 3588;
LABEL_14:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)v7,
        (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\logonutilities.cpp",
        (const char *)v9,
        v29);
LABEL_47:
      Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpPathName);
      goto LABEL_48;
    }
    if ( !(_BYTE)v45 && !CreateDirectoryW(lpPathName[1], 0) )
    {
      LastError = GetLastError();
      LastErrorMsg = LastError;
      if ( LastError > 0 )
        LastErrorMsg = (unsigned __int16)LastError | 0x80070000;
      if ( LastErrorMsg < 0 )
      {
        v7 = 3594;
        goto LABEL_13;
      }
    }
    appended = Common::PathHelpers::AppendPathSegment(
                 (struct Common::StringBuffer *)lpPathName,
                 (const unsigned __int16 *)a2);
    LastErrorMsg = appended;
    if ( appended < 0 )
    {
      v9 = (unsigned int)appended;
      v7 = 3598;
      goto LABEL_14;
    }
    v39 = 0;
    *(_OWORD *)lpExistingFileName = 0;
    v12 = Common::PathHelpers::CombinePaths(
            (const struct Common::COMMON_STRING *)&v42,
            (const unsigned __int16 *)a2,
            (struct Common::StringBuffer *)lpExistingFileName);
    LastErrorMsg = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xE12,
        (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\logonutilities.cpp",
        (const char *)(unsigned int)v12,
        v29);
LABEL_46:
      Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpExistingFileName);
      goto LABEL_47;
    }
    v37 = 0;
    *(_OWORD *)lpSubKey = 0;
    AllUserChildStorePath = AppxAllUserStore::GetAllUserChildStorePath(
                              (AppxAllUserStore *)L"Applications",
                              0,
                              (bool)lpSubKey,
                              v13);
    LastErrorMsg = AllUserChildStorePath;
    if ( AllUserChildStorePath < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xE16,
        (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\logonutilities.cpp",
        (const char *)(unsigned int)AllUserChildStorePath,
        v29);
LABEL_45:
      Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpSubKey);
      goto LABEL_46;
    }
    phkResult = 0;
    v15 = Common::RegistryKey::Open(&phkResult, hKey, lpSubKey[1], 0x2001Fu);
    LastErrorMsg = v15;
    if ( v15 < 0 )
    {
      if ( Microsoft_Windows_AppXDeployment_ServerEnableBits < 0 )
        McTemplateU0zd_EventWriteTransfer(v17, AppxAllUserStoreOpenKeyError, lpSubKey[1], (unsigned int)v15);
      goto LABEL_44;
    }
    v35 = 0;
    LOBYTE(v16) = 1;
    *(_OWORD *)v34 = 0;
    v19 = AppxAllUserStore::GetAllUserChildStorePath((AppxAllUserStore *)L"Deleted", v16, (bool)v34, v18);
    LastErrorMsg = v19;
    if ( v19 < 0 )
    {
      v20 = 3618;
LABEL_26:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)v20,
        (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\logonutilities.cpp",
        (const char *)(unsigned int)v19,
        v29);
LABEL_43:
      Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v34);
LABEL_44:
      Common::RegistryKey::~RegistryKey((Common::RegistryKey *)&phkResult);
      goto LABEL_45;
    }
    v19 = Common::PathHelpers::AppendPathSegment((struct Common::StringBuffer *)v34, L"Applications");
    LastErrorMsg = v19;
    if ( v19 < 0 )
    {
      v20 = 3619;
      goto LABEL_26;
    }
    v19 = Common::PathHelpers::AppendPathSegment((struct Common::StringBuffer *)v34, (const unsigned __int16 *)a2);
    LastErrorMsg = v19;
    if ( v19 < 0 )
    {
      v20 = 3620;
      goto LABEL_26;
    }
    v33 = 0;
    v21 = Common::RegistryKey::Create(
            &v33,
            HKEY_LOCAL_MACHINE,
            v34[1],
            0xF001Fu,
            v29,
            (struct _SECURITY_ATTRIBUTES *const)v31,
            0);
    LastErrorMsg = v21;
    if ( v21 >= 0 )
    {
      v21 = Common::RegistryKey::CopyTree(
              (Common::RegistryKey *)&phkResult,
              (const unsigned __int16 *)a2,
              (struct Common::AutoHandleHKEY *)&v33);
      LastErrorMsg = v21;
      if ( v21 >= 0 )
      {
        v25 = Common::RegistryKey::DeleteSubKeyTree((Common::RegistryKey *)&phkResult, (const unsigned __int16 *)a2);
        wil::details::in1diag3::Log_IfFailedMsg(
          retaddr,
          (void *)0xE3B,
          (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\logonutilities.cpp",
          (const char *)v25,
          (__int64)"Error while deleting deselected entry %ws from per-machine store.",
          (const char *)a2);
        LOBYTE(v26) = 1;
        LOBYTE(v30) = 0;
        v27 = AppxAllUserStore::AddPackageToDynamicPackageArray(0xFFFFFFFFLL, a2, &v33, v26);
        LastErrorMsg = v27;
        if ( v27 >= 0 )
        {
          if ( !MoveFileW(lpExistingFileName[1], lpPathName[1]) )
            LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                             retaddr,
                             (void *)0xE4C,
                             (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\logonutilities.cpp",
                             "Could not move package to the single instance store deleted folder.",
                             v30);
        }
        else
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0xE47,
            (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\logonutilities.cpp",
            (const char *)(unsigned int)v27,
            (int)v30);
        }
        goto LABEL_42;
      }
      if ( Microsoft_Windows_AppXDeployment_ServerEnableBits < 0 )
      {
        v23 = (LPCWSTR)a2;
        v24 = AppxAllUserStoreCopyRegTreeError;
        goto LABEL_34;
      }
    }
    else if ( Microsoft_Windows_AppXDeployment_ServerEnableBits < 0 )
    {
      v23 = v34[1];
      v24 = AppxAllUserStoreCreateKeyError;
LABEL_34:
      McTemplateU0zd_EventWriteTransfer(v22, v24, v23, (unsigned int)v21);
    }
LABEL_42:
    Common::RegistryKey::~RegistryKey((Common::RegistryKey *)&v33);
    goto LABEL_43;
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0xDFD,
    (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\logonutilities.cpp",
    (const char *)(unsigned int)SystemSisFullPath,
    v29);
LABEL_48:
  Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&v42);
  return (unsigned int)LastErrorMsg;
}

```

## disassembly

```asm
0x18003a4b8  push    rbp
0x18003a4ba  push    rbx
0x18003a4bb  push    rsi
0x18003a4bc  push    rdi
0x18003a4bd  push    r14
0x18003a4bf  push    r15
0x18003a4c1  lea     rbp, [rsp-2Fh]
0x18003a4c6  sub     rsp, 0E8h
0x18003a4cd  mov     rsi, rcx
0x18003a4d0  xorps   xmm0, xmm0
0x18003a4d3  xor     r15d, r15d
0x18003a4d6  lea     rcx, [rbp+57h+var_50]; this
0x18003a4da  movups  [rbp+57h+var_50], xmm0
0x18003a4de  mov     [rbp+57h+var_40], r15d
0x18003a4e2  mov     r14, r8
0x18003a4e5  mov     rdi, rdx
0x18003a4e8  call    ?GetSystemSisFullPath@Configuration@Deployment@Common@@YAJPEAVStringBuffer@3@@Z; Common::Deployment::Configuration::GetSystemSisFullPath(Common::StringBuffer *)
0x18003a4ed  mov     ebx, eax
0x18003a4ef  test    eax, eax
0x18003a4f1  jns     short loc_18003A510
0x18003a4f3  mov     rcx, [rbp+5Fh]; this
0x18003a4f7  lea     r8, aOnecoreAdminAp_8; "onecore\\admin\\appmodel\\appxalluserst"...
0x18003a4fe  mov     r9d, eax; char *
0x18003a501  mov     edx, 0DFDh; void *
0x18003a506  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003a50b  jmp     loc_18003A861
0x18003a510  xorps   xmm0, xmm0
0x18003a513  mov     [rbp+57h+var_58], r15d
0x18003a517  lea     r8, [rbp+57h+lpPathName]; struct Common::StringBuffer *
0x18003a51b  lea     rdx, aDeletedalluser; "\\DeletedAllUserPackages"
0x18003a522  lea     rcx, [rbp+57h+var_50]; struct Common::COMMON_STRING *
0x18003a526  movups  xmmword ptr [rbp+57h+lpPathName], xmm0
0x18003a52a  call    ?CombinePaths@PathHelpers@Common@@SAJPEBUCOMMON_STRING@2@PEBGPEAVStringBuffer@2@@Z; Common::PathHelpers::CombinePaths(Common::COMMON_STRING const *,ushort const *,Common::StringBuffer *)
0x18003a52f  mov     ebx, eax
0x18003a531  test    eax, eax
0x18003a533  jns     short loc_18003A53C
0x18003a535  mov     edx, 0E00h
0x18003a53a  jmp     short loc_18003A591
0x18003a53c  mov     rcx, [rbp+57h+lpPathName+8]; this
0x18003a540  lea     rdx, [rbp+57h+arg_18]; unsigned __int16 *
0x18003a544  mov     byte ptr [rbp+57h+arg_18], r15b
0x18003a548  call    ?DirectoryExists@Common@@YAJPEBGPEA_N@Z; Common::DirectoryExists(ushort const *,bool *)
0x18003a54d  mov     ebx, eax
0x18003a54f  test    eax, eax
0x18003a551  jns     short loc_18003A55D
0x18003a553  mov     r9d, eax
0x18003a556  mov     edx, 0E04h
0x18003a55b  jmp     short loc_18003A594
0x18003a55d  cmp     byte ptr [rbp+57h+arg_18], r15b
0x18003a561  jnz     short loc_18003A5A9
0x18003a563  mov     rcx, [rbp+57h+lpPathName+8]; lpPathName
0x18003a567  xor     edx, edx; lpSecurityAttributes
0x18003a569  call    cs:__imp_CreateDirectoryW
0x18003a56f  test    eax, eax
0x18003a571  jnz     short loc_18003A5A9
0x18003a573  call    cs:__imp_GetLastError
0x18003a579  mov     ebx, eax
0x18003a57b  test    eax, eax
0x18003a57d  jle     short loc_18003A588
0x18003a57f  movzx   ebx, ax
0x18003a582  or      ebx, 80070000h
0x18003a588  test    ebx, ebx
0x18003a58a  jns     short loc_18003A5A9
0x18003a58c  mov     edx, 0E0Ah; void *
0x18003a591  mov     r9d, ebx; char *
0x18003a594  mov     rcx, [rbp+5Fh]; this
0x18003a598  lea     r8, aOnecoreAdminAp_8; "onecore\\admin\\appmodel\\appxalluserst"...
0x18003a59f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003a5a4  jmp     loc_18003A858
0x18003a5a9  mov     rdx, rdi; unsigned __int16 *
0x18003a5ac  lea     rcx, [rbp+57h+lpPathName]; struct Common::StringBuffer *
0x18003a5b0  call    ?AppendPathSegment@PathHelpers@Common@@SAJPEAVStringBuffer@2@PEBG@Z; Common::PathHelpers::AppendPathSegment(Common::StringBuffer *,ushort const *)
0x18003a5b5  mov     ebx, eax
0x18003a5b7  test    eax, eax
0x18003a5b9  jns     short loc_18003A5C5
0x18003a5bb  mov     r9d, eax
0x18003a5be  mov     edx, 0E0Eh
0x18003a5c3  jmp     short loc_18003A594
0x18003a5c5  xorps   xmm0, xmm0
0x18003a5c8  mov     [rbp+57h+var_70], r15d
0x18003a5cc  lea     r8, [rbp+57h+lpExistingFileName]; struct Common::StringBuffer *
0x18003a5d0  mov     rdx, rdi; unsigned __int16 *
0x18003a5d3  lea     rcx, [rbp+57h+var_50]; struct Common::COMMON_STRING *
0x18003a5d7  movups  xmmword ptr [rbp+57h+lpExistingFileName], xmm0
0x18003a5db  call    ?CombinePaths@PathHelpers@Common@@SAJPEBUCOMMON_STRING@2@PEBGPEAVStringBuffer@2@@Z; Common::PathHelpers::CombinePaths(Common::COMMON_STRING const *,ushort const *,Common::StringBuffer *)
0x18003a5e0  mov     ebx, eax
0x18003a5e2  test    eax, eax
0x18003a5e4  jns     short loc_18003A603
0x18003a5e6  mov     rcx, [rbp+5Fh]; this
0x18003a5ea  lea     r8, aOnecoreAdminAp_8; "onecore\\admin\\appmodel\\appxalluserst"...
0x18003a5f1  mov     r9d, eax; char *
0x18003a5f4  mov     edx, 0E12h; void *
0x18003a5f9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003a5fe  jmp     loc_18003A84F
0x18003a603  xorps   xmm0, xmm0
0x18003a606  mov     [rbp+57h+var_88], r15d
0x18003a60a  lea     r8, [rbp+57h+lpSubKey]; bool
0x18003a60e  xor     edx, edx; unsigned __int16 *
0x18003a610  lea     rcx, ?allUserApplicationsString@AppxAllUserStore@@3QBGB; "Applications"
0x18003a617  movups  xmmword ptr [rbp+57h+lpSubKey], xmm0
0x18003a61b  call    ?GetAllUserChildStorePath@AppxAllUserStore@@YAJPEBG_NPEAVStringBuffer@Common@@@Z; AppxAllUserStore::GetAllUserChildStorePath(ushort const *,bool,Common::StringBuffer *)
0x18003a620  mov     ebx, eax
0x18003a622  test    eax, eax
0x18003a624  jns     short loc_18003A643
0x18003a626  mov     rcx, [rbp+5Fh]; this
0x18003a62a  lea     r8, aOnecoreAdminAp_8; "onecore\\admin\\appmodel\\appxalluserst"...
0x18003a631  mov     r9d, eax; char *
0x18003a634  mov     edx, 0E16h; void *
0x18003a639  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003a63e  jmp     loc_18003A846
0x18003a643  mov     r8, [rbp+57h+lpSubKey+8]; lpSubKey
0x18003a647  lea     rcx, [rbp+57h+phkResult]; phkResult
0x18003a64b  mov     r9d, 2001Fh; samDesired
0x18003a651  mov     [rbp+57h+phkResult], r15
0x18003a655  mov     rdx, rsi; hKey
0x18003a658  call    ?Open@RegistryKey@Common@@QEAAJQEAUHKEY__@@PEBGK@Z; Common::RegistryKey::Open(HKEY__ * const,ushort const *,ulong)
0x18003a65d  mov     ebx, eax
0x18003a65f  test    eax, eax
0x18003a661  jns     short loc_18003A688
0x18003a663  cmp     cs:Microsoft_Windows_AppXDeployment_ServerEnableBits, r15b
0x18003a66a  jge     loc_18003A83D
0x18003a670  mov     r8, [rbp+57h+lpSubKey+8]
0x18003a674  lea     rdx, AppxAllUserStoreOpenKeyError
0x18003a67b  mov     r9d, eax
0x18003a67e  call    McTemplateU0zd_EventWriteTransfer
0x18003a683  jmp     loc_18003A83D
0x18003a688  xorps   xmm0, xmm0
0x18003a68b  mov     [rbp+57h+var_A0], r15d
0x18003a68f  lea     r8, [rbp+57h+var_B0]; bool
0x18003a693  mov     dl, 1; unsigned __int16 *
0x18003a695  lea     rcx, ?deletedApplicationsString@AppxAllUserStore@@3QBGB; "Deleted"
0x18003a69c  movups  xmmword ptr [rbp+57h+var_B0], xmm0
0x18003a6a0  call    ?GetAllUserChildStorePath@AppxAllUserStore@@YAJPEBG_NPEAVStringBuffer@Common@@@Z; AppxAllUserStore::GetAllUserChildStorePath(ushort const *,bool,Common::StringBuffer *)
0x18003a6a5  mov     ebx, eax
0x18003a6a7  test    eax, eax
0x18003a6a9  jns     short loc_18003A6C8
0x18003a6ab  mov     edx, 0E22h; void *
0x18003a6b0  mov     rcx, [rbp+5Fh]; this
0x18003a6b4  lea     r8, aOnecoreAdminAp_8; "onecore\\admin\\appmodel\\appxalluserst"...
0x18003a6bb  mov     r9d, eax; char *
0x18003a6be  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003a6c3  jmp     loc_18003A834
0x18003a6c8  lea     rdx, ?allUserApplicationsString@AppxAllUserStore@@3QBGB; "Applications"
0x18003a6cf  lea     rcx, [rbp+57h+var_B0]; struct Common::StringBuffer *
0x18003a6d3  call    ?AppendPathSegment@PathHelpers@Common@@SAJPEAVStringBuffer@2@PEBG@Z; Common::PathHelpers::AppendPathSegment(Common::StringBuffer *,ushort const *)
0x18003a6d8  mov     ebx, eax
0x18003a6da  test    eax, eax
0x18003a6dc  jns     short loc_18003A6E5
0x18003a6de  mov     edx, 0E23h
0x18003a6e3  jmp     short loc_18003A6B0
0x18003a6e5  mov     rdx, rdi; unsigned __int16 *
0x18003a6e8  lea     rcx, [rbp+57h+var_B0]; struct Common::StringBuffer *
0x18003a6ec  call    ?AppendPathSegment@PathHelpers@Common@@SAJPEAVStringBuffer@2@PEBG@Z; Common::PathHelpers::AppendPathSegment(Common::StringBuffer *,ushort const *)
0x18003a6f1  mov     ebx, eax
0x18003a6f3  test    eax, eax
0x18003a6f5  jns     short loc_18003A6FE
0x18003a6f7  mov     edx, 0E24h
0x18003a6fc  jmp     short loc_18003A6B0
0x18003a6fe  mov     r8, [rbp+57h+var_B0+8]; lpSubKey
0x18003a702  lea     rcx, [rbp+57h+var_B8]; phkResult
0x18003a706  mov     r9d, 0F001Fh; samDesired
0x18003a70c  mov     [rbp+57h+var_B8], r15
0x18003a710  mov     rdx, 0FFFFFFFF80000002h; hKey
0x18003a717  mov     [rsp+110h+var_E0], r15; LPDWORD
0x18003a71c  call    ?Create@RegistryKey@Common@@QEAAJQEAUHKEY__@@PEBGKKQEAU_SECURITY_ATTRIBUTES@@PEAK@Z; Common::RegistryKey::Create(HKEY__ * const,ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES * const,ulong *)
0x18003a721  mov     ebx, eax
0x18003a723  test    eax, eax
0x18003a725  jns     short loc_18003A74C
0x18003a727  cmp     cs:Microsoft_Windows_AppXDeployment_ServerEnableBits, r15b
0x18003a72e  jge     loc_18003A82B
0x18003a734  mov     r8, [rbp+57h+var_B0+8]
0x18003a738  lea     rdx, AppxAllUserStoreCreateKeyError
0x18003a73f  mov     r9d, eax
0x18003a742  call    McTemplateU0zd_EventWriteTransfer
0x18003a747  jmp     loc_18003A82B
0x18003a74c  lea     r8, [rbp+57h+var_B8]; struct Common::AutoHandleHKEY *
0x18003a750  mov     rdx, rdi; unsigned __int16 *
0x18003a753  lea     rcx, [rbp+57h+phkResult]; this
0x18003a757  call    ?CopyTree@RegistryKey@Common@@QEAAJPEBGAEAVAutoHandleHKEY@2@@Z; Common::RegistryKey::CopyTree(ushort const *,Common::AutoHandleHKEY &)
0x18003a75c  mov     ebx, eax
0x18003a75e  test    eax, eax
0x18003a760  jns     short loc_18003A77B
0x18003a762  cmp     cs:Microsoft_Windows_AppXDeployment_ServerEnableBits, r15b
0x18003a769  jge     loc_18003A82B
0x18003a76f  mov     r8, rdi
0x18003a772  lea     rdx, AppxAllUserStoreCopyRegTreeError
0x18003a779  jmp     short loc_18003A73F
0x18003a77b  mov     rdx, rdi; unsigned __int16 *
0x18003a77e  lea     rcx, [rbp+57h+phkResult]; this
0x18003a782  call    ?DeleteSubKeyTree@RegistryKey@Common@@QEAAJPEBG@Z; Common::RegistryKey::DeleteSubKeyTree(ushort const *)
0x18003a787  mov     rcx, [rbp+5Fh]; this
0x18003a78b  lea     rdx, aErrorWhileDele_0; "Error while deleting deselected entry %"...
0x18003a792  mov     [rsp+110h+var_E8], rdi; char *
0x18003a797  lea     r8, aOnecoreAdminAp_8; "onecore\\admin\\appmodel\\appxalluserst"...
0x18003a79e  mov     [rsp+110h+var_F0], rdx; __int64
0x18003a7a3  mov     r9d, eax; char *
0x18003a7a6  mov     edx, 0E3Bh; void *
0x18003a7ab  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18003a7b0  mov     [rsp+110h+var_D0], r14
0x18003a7b5  lea     r8, [rbp+57h+var_B8]
0x18003a7b9  mov     [rsp+110h+var_D8], r15
0x18003a7be  mov     r9b, 1
0x18003a7c1  mov     [rsp+110h+var_E0], r15
0x18003a7c6  mov     rdx, rdi
0x18003a7c9  mov     byte ptr [rsp+110h+var_E8], r15b
0x18003a7ce  or      ecx, 0FFFFFFFFh
0x18003a7d1  mov     byte ptr [rsp+110h+var_F0], r15b; char *
0x18003a7d6  call    ?AddPackageToDynamicPackageArray@AppxAllUserStore@@YAJW4SetupPhase@1@PEBGPEAVRegistryKey@Common@@_N3311PEAV?$Array@U_MainPackageInfo@AppxAllUserStore@@V?$ContainerOperations@U_MainPackageInfo@AppxAllUserStore@@U12@@Common@@VNoKey@4@V?$ContainerOperations@VNoKey@Common@@U_MainPackageInfo@AppxAllUserStore@@@4@V?$ArrayOperations@U_MainPackageInfo@AppxAllUserStore@@VNoKey@Common@@@4@@4@@Z; AppxAllUserStore::AddPackageToDynamicPackageArray(AppxAllUserStore::SetupPhase,ushort const *,Common::RegistryKey *,bool,bool,bool,ushort const *,ushort const *,Common::Array<AppxAllUserStore::_MainPackageInfo,Common::ContainerOperations<AppxAllUserStore::_MainPackageInfo,AppxAllUserStore::_MainPackageInfo>,Common::NoKey,Common::ContainerOperations<Common::NoKey,AppxAllUserStore::_MainPackageInfo>,Common::ArrayOperations<AppxAllUserStore::_MainPackageInfo,Common::NoKey>> *)
0x18003a7db  mov     ebx, eax
0x18003a7dd  test    eax, eax
0x18003a7df  jns     short loc_18003A7FB
0x18003a7e1  mov     rcx, [rbp+5Fh]; this
0x18003a7e5  lea     r8, aOnecoreAdminAp_8; "onecore\\admin\\appmodel\\appxalluserst"...
0x18003a7ec  mov     r9d, eax; char *
0x18003a7ef  mov     edx, 0E47h; void *
0x18003a7f4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003a7f9  jmp     short loc_18003A82B
0x18003a7fb  mov     rdx, [rbp+57h+lpPathName+8]; lpNewFileName
0x18003a7ff  mov     rcx, [rbp+57h+lpExistingFileName+8]; lpExistingFileName
0x18003a803  call    cs:__imp_MoveFileW
0x18003a809  test    eax, eax
0x18003a80b  jnz     short loc_18003A82B
0x18003a80d  mov     rcx, [rbp+5Fh]; this
0x18003a811  lea     r9, aCouldNotMovePa; "Could not move package to the single in"...
0x18003a818  lea     r8, aOnecoreAdminAp_8; "onecore\\admin\\appmodel\\appxalluserst"...
0x18003a81f  mov     edx, 0E4Ch; void *
0x18003a824  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x18003a829  mov     ebx, eax
0x18003a82b  lea     rcx, [rbp+57h+var_B8]; this
0x18003a82f  call    ??1RegistryKey@Common@@QEAA@XZ; Common::RegistryKey::~RegistryKey(void)
0x18003a834  lea     rcx, [rbp+57h+var_B0]; this
0x18003a838  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18003a83d  lea     rcx, [rbp+57h+phkResult]; this
0x18003a841  call    ??1RegistryKey@Common@@QEAA@XZ; Common::RegistryKey::~RegistryKey(void)
0x18003a846  lea     rcx, [rbp+57h+lpSubKey]; this
0x18003a84a  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18003a84f  lea     rcx, [rbp+57h+lpExistingFileName]; this
0x18003a853  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18003a858  lea     rcx, [rbp+57h+lpPathName]; this
0x18003a85c  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18003a861  lea     rcx, [rbp+57h+var_50]; this
0x18003a865  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18003a86a  mov     eax, ebx
0x18003a86c  add     rsp, 0E8h
0x18003a873  pop     r15
0x18003a875  pop     r14
0x18003a877  pop     rdi
0x18003a878  pop     rsi
0x18003a879  pop     rbx
0x18003a87a  pop     rbp
0x18003a87b  retn
```
