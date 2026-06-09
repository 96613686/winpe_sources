# ReplaceDSMAIfPresent

- ea: `0x18000d974`
- end: `0x18000de03`
- name: `ReplaceDSMAIfPresent`
- size: `1167`
- prototype: `__int64 __fastcall(HANDLE hSourceHandle, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002ed98`

## callees

- `0x18000720c`
- `0x18000bde0`
- `0x18000c410`
- `0x18000d974`
- `0x180019fa0`
- `0x18001a0d4`
- `0x18001e7bc`
- `0x18002a714`
- `0x18002af7c`
- `0x18003150c`
- `0x18003b4c4`
- `0x180046e50`
- `0x180048010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000da55`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000da5e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000da55`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000da5e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000da08`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000da08`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000da83`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000da83`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000dd1c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000dd1c`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18000d9ba`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18000d9d2`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18000d9ea`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18000d9ba`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18000d9d2`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18000d9ea`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18000db04`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18000db04`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18000da2a`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18000da2a`

## string_xrefs

- `0x18000db4e`: `onecoreuap\internal\shell\inc\PlatformExtensionTools.h`
- `0x18000da3a`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18000da91`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18000dacb`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18000db66`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18000dbaa`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18000dbe9`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18000dc64`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18000dc90`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18000dd31`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18000dde1`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18000db1c`: `Windows.Internal.PlatformExtensions.UserSelection`

## pseudocode

```c
__int64 __fastcall ReplaceDSMAIfPresent(HANDLE hSourceHandle, _QWORD *a2)
{
  int v4; // eax
  int LastError; // ebx
  HANDLE CurrentProcess; // rbx
  HANDLE v7; // rax
  const char *v8; // r9
  int token_information; // eax
  void *v11; // rcx
  void *v12; // rdi
  __int64 v13; // r8
  int v14; // eax
  int v15; // eax
  __int64 v16; // rsi
  int v17; // eax
  __int64 v18; // rdx
  DWORD dwDesiredAccess; // [rsp+20h] [rbp-49h]
  DWORD dwDesiredAccessa; // [rsp+20h] [rbp-49h]
  __int64 v21; // [rsp+40h] [rbp-29h] BYREF
  HANDLE hObject; // [rsp+48h] [rbp-21h] BYREF
  __int64 v23; // [rsp+50h] [rbp-19h] BYREF
  void *Block; // [rsp+58h] [rbp-11h] BYREF
  __int64 v25; // [rsp+60h] [rbp-9h] BYREF
  __int64 v26; // [rsp+68h] [rbp-1h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp+7h] BYREF
  __int64 v28; // [rsp+88h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  Block = 0;
  hObject = 0;
  LODWORD(v21) = -1;
  RtlGetDeviceFamilyInfoEnum(0, &v21, 0);
  if ( (_DWORD)v21 != 16 )
  {
    LODWORD(v21) = -1;
    RtlGetDeviceFamilyInfoEnum(0, &v21, 0);
    if ( (_DWORD)v21 != 10 )
    {
      LODWORD(v21) = -1;
      RtlGetDeviceFamilyInfoEnum(0, &v21, 0);
      if ( (_DWORD)v21 != 5 )
      {
        if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          CloseHandle(hObject);
        return 0;
      }
    }
  }
  if ( *a2 )
  {
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &hObject,
      0);
    v4 = UMgrQueryUserToken(*a2, &hObject);
    LastError = v4;
    if ( v4 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1F5E,
        (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
        (const char *)(unsigned int)v4,
        dwDesiredAccess);
LABEL_11:
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
      return (unsigned int)LastError;
    }
  }
  else
  {
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &hObject,
      0);
    CurrentProcess = GetCurrentProcess();
    v7 = GetCurrentProcess();
    if ( !DuplicateHandle(v7, hSourceHandle, CurrentProcess, &hObject, 0, 0, 2u) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x1F62,
                    (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
                    v8);
      goto LABEL_11;
    }
  }
  token_information = wil::get_token_information_nothrow<_TOKEN_USER,0>(&Block, hObject);
  LastError = token_information;
  if ( token_information < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1F65,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)(unsigned int)token_information,
      dwDesiredAccess);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
    v11 = Block;
    if ( !Block )
      return (unsigned int)LastError;
LABEL_15:
    operator delete(v11);
    return (unsigned int)LastError;
  }
  v12 = Block;
  if ( !IsWellKnownSid(*(PSID *)Block, WinLocalAccountAndAdministratorSid|WinCreatorGroupSid) )
    goto LABEL_42;
  v21 = 0;
  v28 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.PlatformExtensions.UserSelection",
    0x32u,
    0x31u);
  v14 = Windows::Internal::PlatformExtensions::Details::TryActivateContractExtensionInternal(v28, 0, v13, &v21);
  LastError = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x299,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\PlatformExtensionTools.h",
      (const char *)(unsigned int)v14,
      dwDesiredAccess);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1F6A,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)(unsigned int)LastError,
      dwDesiredAccessa);
LABEL_19:
    wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(&v21);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
    if ( !v12 )
      return (unsigned int)LastError;
    v11 = v12;
    goto LABEL_15;
  }
  if ( v21 )
  {
    v23 = 0;
    v15 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v21 + 48LL))(v21, 0, 0, &v23);
    LastError = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1F6E,
        (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
        (const char *)(unsigned int)v15,
        dwDesiredAccess);
LABEL_25:
      wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(&v23);
      goto LABEL_19;
    }
    v16 = v23;
    v26 = 0;
    LastError = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>>(v23);
    if ( LastError < 0
      || (LastError = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v16 + 64LL))(v16, &v26), LastError < 0) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1F70,
        (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
        (const char *)(unsigned int)LastError,
        dwDesiredAccess);
      goto LABEL_46;
    }
    v25 = 0;
    v17 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v26 + 56LL))(v26, &v25);
    LastError = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1F73,
        (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
        (const char *)(unsigned int)v17,
        dwDesiredAccess);
LABEL_30:
      wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(&v25);
LABEL_46:
      wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(&v26);
      goto LABEL_25;
    }
    if ( !v25 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1F74,
        (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
        (const char *)0x80070057LL,
        dwDesiredAccess);
      wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(&v25);
      wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(&v26);
      wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(&v23);
      goto LABEL_33;
    }
    Block = 0;
    v28 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.System.Internal.UserManager",
      0x24u,
      0x23u);
    LastError = RoGetActivationFactory(v28, &GUID_100eb64b_b24c_4c38_8964_720d926d05a4, &Block);
    if ( LastError < 0 )
    {
      v18 = 8054;
LABEL_38:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v18,
        (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
        (const char *)(unsigned int)LastError,
        dwDesiredAccess);
      wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(&Block);
      goto LABEL_30;
    }
    LastError = (*(__int64 (__fastcall **)(void *, __int64, _QWORD *))(*(_QWORD *)Block + 136LL))(Block, v25, a2);
    if ( LastError < 0 )
    {
      v18 = 8055;
      goto LABEL_38;
    }
    wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(&Block);
    wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(&v25);
    wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(&v26);
    wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(&v23);
    wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(&v21);
LABEL_42:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
    if ( v12 )
      operator delete(v12);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1F6B,
    (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
    (const char *)0x80070057LL,
    dwDesiredAccess);
LABEL_33:
  wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(&v21);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
  if ( v12 )
    operator delete(v12);
  return 2147942487LL;
}

```

## disassembly

```asm
0x18000d974  mov     [rsp-8+arg_10], rbx
0x18000d979  push    rbp
0x18000d97a  push    rsi
0x18000d97b  push    rdi
0x18000d97c  push    r14
0x18000d97e  push    r15
0x18000d980  lea     rbp, [rsp-37h]
0x18000d985  sub     rsp, 0A0h
0x18000d98c  mov     rax, cs:__security_cookie
0x18000d993  xor     rax, rsp
0x18000d996  mov     [rbp+57h+var_30], rax
0x18000d99a  mov     r14, rdx
0x18000d99d  mov     rdi, rcx
0x18000d9a0  xor     r15d, r15d
0x18000d9a3  lea     rdx, [rbp+57h+var_80]
0x18000d9a7  or      ebx, 0FFFFFFFFh
0x18000d9aa  mov     [rbp+57h+Block], r15
0x18000d9ae  xor     ecx, ecx
0x18000d9b0  mov     [rbp+57h+hObject], r15
0x18000d9b4  xor     r8d, r8d
0x18000d9b7  mov     dword ptr [rbp+57h+var_80], ebx
0x18000d9ba  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x18000d9c0  cmp     dword ptr [rbp+57h+var_80], 10h
0x18000d9c4  jz      short loc_18000DA13
0x18000d9c6  xor     r8d, r8d
0x18000d9c9  mov     dword ptr [rbp+57h+var_80], ebx
0x18000d9cc  lea     rdx, [rbp+57h+var_80]
0x18000d9d0  xor     ecx, ecx
0x18000d9d2  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x18000d9d8  cmp     dword ptr [rbp+57h+var_80], 0Ah
0x18000d9dc  jz      short loc_18000DA13
0x18000d9de  xor     r8d, r8d
0x18000d9e1  mov     dword ptr [rbp+57h+var_80], ebx
0x18000d9e4  lea     rdx, [rbp+57h+var_80]
0x18000d9e8  xor     ecx, ecx
0x18000d9ea  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x18000d9f0  cmp     dword ptr [rbp+57h+var_80], 5
0x18000d9f4  jz      short loc_18000DA13
0x18000d9f6  mov     rcx, [rbp+57h+hObject]; hObject
0x18000d9fa  lea     rax, [rcx-1]
0x18000d9fe  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000da02  ja      loc_18000DDB8
0x18000da08  call    cs:__imp_CloseHandle
0x18000da0e  jmp     loc_18000DDB8
0x18000da13  xor     edx, edx
0x18000da15  lea     rcx, [rbp+57h+hObject]
0x18000da19  cmp     [r14], r15
0x18000da1c  jz      short loc_18000DA50
0x18000da1e  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18000da23  mov     rcx, [r14]
0x18000da26  lea     rdx, [rbp+57h+hObject]
0x18000da2a  call    cs:__imp_UMgrQueryUserToken
0x18000da30  mov     ebx, eax
0x18000da32  test    eax, eax
0x18000da34  jns     short loc_18000DAB4
0x18000da36  mov     rcx, [rbp+5Fh]; this
0x18000da3a  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18000da41  mov     r9d, eax; char *
0x18000da44  mov     edx, 1F5Eh; void *
0x18000da49  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000da4e  jmp     short loc_18000DAA4
0x18000da50  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18000da55  call    cs:__imp_GetCurrentProcess
0x18000da5b  mov     rbx, rax
0x18000da5e  call    cs:__imp_GetCurrentProcess
0x18000da64  mov     [rsp+0C0h+dwOptions], 2; dwOptions
0x18000da6c  lea     r9, [rbp+57h+hObject]; lpTargetHandle
0x18000da70  mov     rcx, rax; hSourceProcessHandle
0x18000da73  mov     [rsp+0C0h+bInheritHandle], r15d; bInheritHandle
0x18000da78  mov     r8, rbx; hTargetProcessHandle
0x18000da7b  mov     [rsp+0C0h+dwDesiredAccess], r15d; dwDesiredAccess
0x18000da80  mov     rdx, rdi; hSourceHandle
0x18000da83  call    cs:__imp_DuplicateHandle
0x18000da89  test    eax, eax
0x18000da8b  jnz     short loc_18000DAB4
0x18000da8d  mov     rcx, [rbp+5Fh]; this
0x18000da91  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18000da98  mov     edx, 1F62h; void *
0x18000da9d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000daa2  mov     ebx, eax
0x18000daa4  lea     rcx, [rbp+57h+hObject]
0x18000daa8  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000daad  mov     eax, ebx
0x18000daaf  jmp     loc_18000DDBA
0x18000dab4  mov     rdx, [rbp+57h+hObject]
0x18000dab8  lea     rcx, [rbp+57h+Block]
0x18000dabc  call    ??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)
0x18000dac1  mov     ebx, eax
0x18000dac3  test    eax, eax
0x18000dac5  jns     short loc_18000DAF8
0x18000dac7  mov     rcx, [rbp+5Fh]; this
0x18000dacb  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18000dad2  mov     r9d, eax; char *
0x18000dad5  mov     edx, 1F65h; void *
0x18000dada  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dadf  lea     rcx, [rbp+57h+hObject]
0x18000dae3  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000dae8  mov     rcx, [rbp+57h+Block]; Block
0x18000daec  test    rcx, rcx
0x18000daef  jz      short loc_18000DAAD
0x18000daf1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000daf6  jmp     short loc_18000DAAD
0x18000daf8  mov     rdi, [rbp+57h+Block]
0x18000dafc  mov     edx, 6Eh ; 'n'; WellKnownSidType
0x18000db01  mov     rcx, [rdi]; pSid
0x18000db04  call    cs:__imp_IsWellKnownSid
0x18000db0a  test    eax, eax
0x18000db0c  jz      loc_18000DDA2
0x18000db12  mov     r9d, 31h ; '1'; unsigned int
0x18000db18  mov     [rbp+57h+var_80], r15
0x18000db1c  lea     rdx, sourceString; "Windows.Internal.PlatformExtensions.Use"...
0x18000db23  mov     [rbp+57h+var_38], r15
0x18000db27  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18000db2b  lea     r8d, [r9+1]; unsigned int
0x18000db2f  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18000db34  mov     rcx, [rbp+57h+var_38]
0x18000db38  lea     r9, [rbp+57h+var_80]
0x18000db3c  mov     edx, r15d
0x18000db3f  call    ?TryActivateContractExtensionInternal@Details@PlatformExtensions@Internal@Windows@@YAJPEAUHSTRING__@@UWindowId@WindowManagement@ApplicationModel@34@AEBU_GUID@@PEAPEAX@Z; Windows::Internal::PlatformExtensions::Details::TryActivateContractExtensionInternal(HSTRING__ *,Windows::Internal::ApplicationModel::WindowManagement::WindowId,_GUID const &,void * *)
0x18000db44  mov     ebx, eax
0x18000db46  test    eax, eax
0x18000db48  jns     short loc_18000DB9D
0x18000db4a  mov     rcx, [rbp+5Fh]; this
0x18000db4e  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\Platf"...
0x18000db55  mov     r9d, eax; char *
0x18000db58  mov     edx, 299h; void *
0x18000db5d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000db62  mov     rcx, [rbp+5Fh]; this
0x18000db66  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18000db6d  mov     r9d, ebx; char *
0x18000db70  mov     edx, 1F6Ah; void *
0x18000db75  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000db7a  lea     rcx, [rbp+57h+var_80]
0x18000db7e  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(void)
0x18000db83  lea     rcx, [rbp+57h+hObject]
0x18000db87  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000db8c  test    rdi, rdi
0x18000db8f  jz      loc_18000DAAD
0x18000db95  mov     rcx, rdi
0x18000db98  jmp     loc_18000DAF1
0x18000db9d  mov     rcx, [rbp+57h+var_80]
0x18000dba1  test    rcx, rcx
0x18000dba4  jnz     short loc_18000DBC6
0x18000dba6  mov     rcx, [rbp+5Fh]; this
0x18000dbaa  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18000dbb1  mov     r9d, 80070057h; char *
0x18000dbb7  mov     edx, 1F6Bh; void *
0x18000dbbc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dbc1  jmp     loc_18000DCC2
0x18000dbc6  mov     [rbp+57h+var_70], r15
0x18000dbca  lea     r9, [rbp+57h+var_70]
0x18000dbce  mov     rax, [rcx]
0x18000dbd1  xor     r8d, r8d
0x18000dbd4  xor     edx, edx
0x18000dbd6  mov     rax, [rax+30h]
0x18000dbda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dbdf  mov     ebx, eax
0x18000dbe1  test    eax, eax
0x18000dbe3  jns     short loc_18000DC0B
0x18000dbe5  mov     rcx, [rbp+5Fh]; this
0x18000dbe9  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18000dbf0  mov     r9d, eax; char *
0x18000dbf3  mov     edx, 1F6Eh; void *
0x18000dbf8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dbfd  lea     rcx, [rbp+57h+var_70]
0x18000dc01  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(void)
0x18000dc06  jmp     loc_18000DB7A
0x18000dc0b  mov     rsi, [rbp+57h+var_70]
0x18000dc0f  mov     rcx, rsi
0x18000dc12  mov     [rbp+57h+var_58], r15
0x18000dc16  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *> *,tagCOWAIT_FLAGS,void *)
0x18000dc1b  mov     ebx, eax
0x18000dc1d  test    eax, eax
0x18000dc1f  js      loc_18000DDDD
0x18000dc25  mov     rax, [rsi]
0x18000dc28  lea     rdx, [rbp+57h+var_58]
0x18000dc2c  mov     rcx, rsi
0x18000dc2f  mov     rax, [rax+40h]
0x18000dc33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc38  mov     ebx, eax
0x18000dc3a  test    eax, eax
0x18000dc3c  js      loc_18000DDDD
0x18000dc42  mov     rcx, [rbp+57h+var_58]
0x18000dc46  lea     rdx, [rbp+57h+var_60]
0x18000dc4a  mov     [rbp+57h+var_60], r15
0x18000dc4e  mov     rax, [rcx]
0x18000dc51  mov     rax, [rax+38h]
0x18000dc55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc5a  mov     ebx, eax
0x18000dc5c  test    eax, eax
0x18000dc5e  jns     short loc_18000DC86
0x18000dc60  mov     rcx, [rbp+5Fh]; this
0x18000dc64  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18000dc6b  mov     r9d, eax; char *
0x18000dc6e  mov     edx, 1F73h; void *
0x18000dc73  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dc78  lea     rcx, [rbp+57h+var_60]
0x18000dc7c  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(void)
0x18000dc81  jmp     loc_18000DDF5
0x18000dc86  cmp     [rbp+57h+var_60], r15
0x18000dc8a  jnz     short loc_18000DCEB
0x18000dc8c  mov     rcx, [rbp+5Fh]; this
0x18000dc90  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18000dc97  mov     r9d, 80070057h; char *
0x18000dc9d  mov     edx, 1F74h; void *
0x18000dca2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dca7  lea     rcx, [rbp+57h+var_60]
0x18000dcab  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(void)
0x18000dcb0  lea     rcx, [rbp+57h+var_58]
0x18000dcb4  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(void)
0x18000dcb9  lea     rcx, [rbp+57h+var_70]
0x18000dcbd  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(void)
0x18000dcc2  lea     rcx, [rbp+57h+var_80]
0x18000dcc6  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(void)
0x18000dccb  lea     rcx, [rbp+57h+hObject]
0x18000dccf  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000dcd4  test    rdi, rdi
0x18000dcd7  jz      short loc_18000DCE1
0x18000dcd9  mov     rcx, rdi; Block
0x18000dcdc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000dce1  mov     eax, 80070057h
0x18000dce6  jmp     loc_18000DDBA
0x18000dceb  mov     r9d, 23h ; '#'; unsigned int
0x18000dcf1  mov     [rbp+57h+Block], r15
0x18000dcf5  lea     rdx, ?RuntimeClass_Windows_System_Internal_UserManager@@3QBGB; "Windows.System.Internal.UserManager"
0x18000dcfc  mov     [rbp+57h+var_38], r15
0x18000dd00  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18000dd04  lea     r8d, [r9+1]; unsigned int
0x18000dd08  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18000dd0d  mov     rcx, [rbp+57h+var_38]
0x18000dd11  lea     r8, [rbp+57h+Block]
0x18000dd15  lea     rdx, _GUID_100eb64b_b24c_4c38_8964_720d926d05a4
0x18000dd1c  call    cs:__imp_RoGetActivationFactory
0x18000dd22  mov     ebx, eax
0x18000dd24  test    eax, eax
0x18000dd26  jns     short loc_18000DD4E
0x18000dd28  mov     edx, 1F76h; void *
0x18000dd2d  mov     rcx, [rbp+5Fh]; this
0x18000dd31  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18000dd38  mov     r9d, ebx; char *
0x18000dd3b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dd40  lea     rcx, [rbp+57h+Block]
0x18000dd44  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(void)
0x18000dd49  jmp     loc_18000DC78
0x18000dd4e  mov     rcx, [rbp+57h+Block]
0x18000dd52  mov     r8, r14
0x18000dd55  mov     rdx, [rbp+57h+var_60]
0x18000dd59  mov     rax, [rcx]
0x18000dd5c  mov     rax, [rax+88h]
0x18000dd63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd68  mov     ebx, eax
0x18000dd6a  test    eax, eax
0x18000dd6c  jns     short loc_18000DD75
0x18000dd6e  mov     edx, 1F77h
0x18000dd73  jmp     short loc_18000DD2D
0x18000dd75  lea     rcx, [rbp+57h+Block]
0x18000dd79  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(void)
0x18000dd7e  lea     rcx, [rbp+57h+var_60]
0x18000dd82  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(void)
0x18000dd87  lea     rcx, [rbp+57h+var_58]
0x18000dd8b  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(void)
0x18000dd90  lea     rcx, [rbp+57h+var_70]
0x18000dd94  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(void)
0x18000dd99  lea     rcx, [rbp+57h+var_80]
0x18000dd9d  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(void)
0x18000dda2  lea     rcx, [rbp+57h+hObject]
0x18000dda6  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000ddab  test    rdi, rdi
0x18000ddae  jz      short loc_18000DDB8
0x18000ddb0  mov     rcx, rdi; Block
0x18000ddb3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000ddb8  xor     eax, eax
0x18000ddba  mov     rcx, [rbp+57h+var_30]
0x18000ddbe  xor     rcx, rsp; StackCookie
0x18000ddc1  call    __security_check_cookie
0x18000ddc6  mov     rbx, [rsp+0C0h+arg_10]
0x18000ddce  add     rsp, 0A0h
0x18000ddd5  pop     r15
0x18000ddd7  pop     r14
0x18000ddd9  pop     rdi
0x18000ddda  pop     rsi
0x18000dddb  pop     rbp
0x18000dddc  retn
0x18000dddd  mov     rcx, [rbp+5Fh]; this
0x18000dde1  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18000dde8  mov     r9d, ebx; char *
0x18000ddeb  mov     edx, 1F70h; void *
0x18000ddf0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ddf5  lea     rcx, [rbp+57h+var_58]
0x18000ddf9  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(void)
0x18000ddfe  jmp     loc_18000DBFD
```
