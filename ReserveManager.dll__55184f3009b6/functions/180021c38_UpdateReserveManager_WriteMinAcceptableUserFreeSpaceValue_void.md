# UpdateReserveManager::WriteMinAcceptableUserFreeSpaceValue(void)

- ea: `0x180021c38`
- end: `0x180021dfc`
- name: `?WriteMinAcceptableUserFreeSpaceValue@UpdateReserveManager@@AEAAJXZ`
- size: `452`
- prototype: `__int64 __fastcall(UpdateReserveManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180015240`

## callees

- `0x180003870`
- `0x180008140`
- `0x18000fafc`
- `0x180021c38`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021c78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021cd7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021c78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021cd7`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x180021c6e`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x180021c6e`
- `api-ms-win-core-registry-l2-1-0!RegSetKeyValueW` at `0x180021d59`
- `api-ms-win-core-registry-l2-1-0!RegSetKeyValueW` at `0x180021d59`

## string_xrefs

- `0x180021c87`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x180021d65`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x180021d93`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x180021ca5`: `EnsureBOOL(::GetDiskFreeSpaceExW(m_WindowsDirPath, nullptr, &TotalNumberOfBytesOnDisk, nullptr))`
- `0x180021c9a`: `UpdateReserveManager::WriteMinAcceptableUserFreeSpaceValue`
- `0x180021d78`: `UpdateReserveManager::WriteMinAcceptableUserFreeSpaceValue`
- `0x180021dad`: `UpdateReserveManager::WriteMinAcceptableUserFreeSpaceValue`
- `0x180021d83`: `::RegSetKeyValueW(m_SoftwareKey, L"Microsoft\\Windows\\CurrentVersion\\ReserveManager", L"PostUpgradeFreeSpace", ( 4ul ), &MinAcceptableUserFreeSpace, DwordDataMax)`

## pseudocode

```c
__int64 __fastcall UpdateReserveManager::WriteMinAcceptableUserFreeSpaceValue(UpdateReserveManager *this)
{
  int LastError; // ebx
  const char *v3; // rax
  ULONGLONG v5; // rcx
  const char *v6; // [rsp+30h] [rbp-40h] BYREF
  const char *v7; // [rsp+38h] [rbp-38h]
  __int64 v8; // [rsp+40h] [rbp-30h]
  const char *v9; // [rsp+48h] [rbp-28h]
  int Data; // [rsp+50h] [rbp-20h] BYREF
  union _ULARGE_INTEGER TotalNumberOfBytes; // [rsp+58h] [rbp-18h] BYREF
  __int64 v12; // [rsp+60h] [rbp-10h]

  TotalNumberOfBytes.QuadPart = 0;
  if ( GetDiskFreeSpaceExW((LPCWSTR)this + 68, 0, &TotalNumberOfBytes, 0) )
  {
    v12 = 0;
    if ( !is_mul_ok(TotalNumberOfBytes.QuadPart, 2u) )
    {
      v8 = 4314;
      v6 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
      v7 = "UpdateReserveManager::WriteMinAcceptableUserFreeSpaceValue";
      v9 = "::ULongLongMult(TotalNumberOfBytesOnDisk.QuadPart, 2, &TwoPercentVolumeSizeInMb)";
      RtlReportErrorOrigination(&v6, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, 2147942934LL);
      return 2147942934LL;
    }
    v5 = 2 * TotalNumberOfBytes.QuadPart / 0x6400000;
    if ( v5 >= 0xC00 )
      LODWORD(v5) = 3072;
    Data = v5;
    LastError = RegSetKeyValueW(
                  *((HKEY *)this + 13),
                  L"Microsoft\\Windows\\CurrentVersion\\ReserveManager",
                  L"PostUpgradeFreeSpace",
                  4u,
                  &Data,
                  4u);
    if ( !LastError )
      return 0;
    v8 = 4326;
    v6 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
    v7 = "UpdateReserveManager::WriteMinAcceptableUserFreeSpaceValue";
    v3 = "::RegSetKeyValueW(m_SoftwareKey, L\"Microsoft\\\\Windows\\\\CurrentVersion\\\\ReserveManager\", L\"PostUpgradeF"
         "reeSpace\", ( 4ul ), &MinAcceptableUserFreeSpace, DwordDataMax)";
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
    v8 = 4311;
    v6 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
    v7 = "UpdateReserveManager::WriteMinAcceptableUserFreeSpaceValue";
    v3 = "EnsureBOOL(::GetDiskFreeSpaceExW(m_WindowsDirPath, nullptr, &TotalNumberOfBytesOnDisk, nullptr))";
  }
  v9 = v3;
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  RtlReportErrorOrigination(&v6, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, (unsigned int)LastError);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180021c38  mov     [rsp-8+arg_8], rbx
0x180021c3d  push    rbp
0x180021c3e  mov     rbp, rsp
0x180021c41  sub     rsp, 70h
0x180021c45  mov     rax, cs:__security_cookie
0x180021c4c  xor     rax, rsp
0x180021c4f  mov     [rbp+var_8], rax
0x180021c53  mov     rbx, rcx
0x180021c56  mov     qword ptr [rbp+TotalNumberOfBytes], 0
0x180021c5e  add     rcx, 88h; lpDirectoryName
0x180021c65  lea     r8, [rbp+TotalNumberOfBytes]; lpTotalNumberOfBytes
0x180021c69  xor     r9d, r9d; lpTotalNumberOfFreeBytes
0x180021c6c  xor     edx, edx; lpFreeBytesAvailableToCaller
0x180021c6e  call    cs:__imp_GetDiskFreeSpaceExW
0x180021c74  test    eax, eax
0x180021c76  jnz     short loc_180021CE9
0x180021c78  call    cs:__imp_GetLastError
0x180021c7e  test    eax, eax
0x180021c80  jnz     short loc_180021CD7
0x180021c82  mov     ebx, 36FDh
0x180021c87  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x180021c8e  mov     [rbp+var_30], 10D7h
0x180021c96  mov     [rbp+var_40], rax
0x180021c9a  lea     rax, aUpdatereservem_49; "UpdateReserveManager::WriteMinAcceptabl"...
0x180021ca1  mov     [rbp+var_38], rax
0x180021ca5  lea     rax, aEnsureboolGetd; "EnsureBOOL(::GetDiskFreeSpaceExW(m_Wind"...
0x180021cac  mov     [rbp+var_28], rax
0x180021cb0  test    ebx, ebx
0x180021cb2  jle     short loc_180021CBD
0x180021cb4  movzx   ebx, bx
0x180021cb7  or      ebx, 80070000h
0x180021cbd  mov     r8d, ebx
0x180021cc0  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x180021cc7  lea     rcx, [rbp+var_40]
0x180021ccb  call    RtlReportErrorOrigination
0x180021cd0  mov     eax, ebx
0x180021cd2  jmp     loc_180021DD7
0x180021cd7  call    cs:__imp_GetLastError
0x180021cdd  mov     ebx, eax
0x180021cdf  test    eax, eax
0x180021ce1  jz      loc_180021DF1
0x180021ce7  jmp     short loc_180021C87
0x180021ce9  mov     eax, 2
0x180021cee  mov     [rbp+var_10], 0
0x180021cf6  mul     qword ptr [rbp+TotalNumberOfBytes]
0x180021cfa  mov     rcx, rax
0x180021cfd  test    rdx, rdx
0x180021d00  jnz     loc_180021D93
0x180021d06  mov     rax, 47AE147AE147AE15h
0x180021d10  mul     rcx
0x180021d13  mov     eax, 0C00h
0x180021d18  sub     rcx, rdx
0x180021d1b  shr     rcx, 1
0x180021d1e  add     rcx, rdx
0x180021d21  shr     rcx, 6
0x180021d25  shr     rcx, 14h
0x180021d29  cmp     rcx, rax
0x180021d2c  jb      short loc_180021D30
0x180021d2e  mov     ecx, eax
0x180021d30  mov     r9d, 4; dwType
0x180021d36  mov     [rbp+Data], ecx
0x180021d39  mov     rcx, [rbx+68h]; hKey
0x180021d3d  lea     rax, [rbp+Data]
0x180021d41  mov     [rsp+70h+cbData], r9d; cbData
0x180021d46  lea     r8, aPostupgradefre; "PostUpgradeFreeSpace"
0x180021d4d  lea     rdx, aMicrosoftWindo_2; "Microsoft\\Windows\\CurrentVersion\\Res"...
0x180021d54  mov     [rsp+70h+lpData], rax; lpData
0x180021d59  call    cs:__imp_RegSetKeyValueW
0x180021d5f  mov     ebx, eax
0x180021d61  test    eax, eax
0x180021d63  jz      short loc_180021D8F
0x180021d65  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x180021d6c  mov     [rbp+var_30], 10E6h
0x180021d74  mov     [rbp+var_40], rax
0x180021d78  lea     rax, aUpdatereservem_49; "UpdateReserveManager::WriteMinAcceptabl"...
0x180021d7f  mov     [rbp+var_38], rax
0x180021d83  lea     rax, aRegsetkeyvalue_6; "::RegSetKeyValueW(m_SoftwareKey, L\"Mic"...
0x180021d8a  jmp     loc_180021CAC
0x180021d8f  xor     eax, eax
0x180021d91  jmp     short loc_180021DD7
0x180021d93  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x180021d9a  mov     [rbp+var_30], 10DAh
0x180021da2  mov     [rbp+var_40], rax
0x180021da6  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x180021dad  lea     rax, aUpdatereservem_49; "UpdateReserveManager::WriteMinAcceptabl"...
0x180021db4  mov     r8d, 80070216h
0x180021dba  mov     [rbp+var_38], rax
0x180021dbe  lea     rcx, [rbp+var_40]
0x180021dc2  lea     rax, aUlonglongmultT; "::ULongLongMult(TotalNumberOfBytesOnDis"...
0x180021dc9  mov     [rbp+var_28], rax
0x180021dcd  call    RtlReportErrorOrigination
0x180021dd2  mov     eax, 80070216h
0x180021dd7  mov     rcx, [rbp+var_8]
0x180021ddb  xor     rcx, rsp; StackCookie
0x180021dde  call    __security_check_cookie
0x180021de3  mov     rbx, [rsp+70h+arg_8]
0x180021deb  add     rsp, 70h
0x180021def  pop     rbp
0x180021df0  retn
0x180021df1  mov     ecx, 0C00000E5h; int
0x180021df6  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
