# ReplaceDSMAIfPresent

- ea: `0x180010f3c`
- end: `0x180011384`
- name: `ReplaceDSMAIfPresent`
- size: `1096`
- prototype: `__int64 __fastcall(HANDLE hSourceHandle)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002b828`

## callees

- `0x180007c78`
- `0x18000c790`
- `0x18000f8b0`
- `0x180010f3c`
- `0x18001800c`
- `0x180018150`
- `0x18001b0c4`
- `0x180027cb8`
- `0x18002870c`
- `0x18002e37c`
- `0x1800380c0`
- `0x180042950`
- `0x180043010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x1800110fe`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x1800110fe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001103d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001104c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001103d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001104c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010fde`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010fde`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180011077`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180011077`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001129d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001129d`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180010f82`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180010fa0`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180010fbe`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180010f82`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180010fa0`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180010fbe`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180011008`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180011008`

## string_xrefs

- `0x180011022`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18001108b`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x1800110c5`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180011180`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x1800111b7`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180011203`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180011246`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x1800112df`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18001114e`: `onecoreuap\internal\shell\inc\PlatformExtensionTools.h`
- `0x18001111c`: `Windows.Internal.PlatformExtensions.UserSelection`

## pseudocode

```c
__int64 __fastcall ReplaceDSMAIfPresent(HANDLE hSourceHandle, _QWORD *a2)
{
  int v5; // eax
  unsigned int LastError; // ebx
  HANDLE CurrentProcess; // rbx
  HANDLE v8; // rax
  const char *v9; // r9
  int token_information; // eax
  void *v11; // rbx
  __int64 v12; // r8
  int v13; // eax
  int v14; // edi
  __int64 v15; // rdx
  PSID v16; // rax
  int v17; // eax
  __int64 v18; // rsi
  __int64 v19; // rax
  int v20; // eax
  __int64 v21; // r9
  __int64 v22; // rdx
  int ActivationFactory; // eax
  __int64 v24; // rdx
  DWORD dwDesiredAccess; // [rsp+20h] [rbp-49h]
  __int64 v26; // [rsp+40h] [rbp-29h] BYREF
  HANDLE hObject; // [rsp+48h] [rbp-21h] BYREF
  __int64 v28; // [rsp+50h] [rbp-19h] BYREF
  __int64 *v29; // [rsp+58h] [rbp-11h] BYREF
  void *Block; // [rsp+60h] [rbp-9h] BYREF
  __int64 v31; // [rsp+68h] [rbp-1h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp+7h] BYREF
  __int64 v33; // [rsp+88h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  Block = 0;
  hObject = 0;
  LODWORD(v26) = -1;
  RtlGetDeviceFamilyInfoEnum(0, &v26, 0);
  if ( (_DWORD)v26 == 16
    || (LODWORD(v26) = -1, RtlGetDeviceFamilyInfoEnum(0, &v26, 0), (_DWORD)v26 == 10)
    || (LODWORD(v26) = -1, RtlGetDeviceFamilyInfoEnum(0, &v26, 0), (_DWORD)v26 == 5) )
  {
    if ( *a2 )
    {
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &hObject,
        0);
      v5 = UMgrQueryUserToken(*a2, &hObject);
      LastError = v5;
      if ( v5 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1C13,
          (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
          (const char *)(unsigned int)v5,
          dwDesiredAccess);
LABEL_12:
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
        return LastError;
      }
    }
    else
    {
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &hObject,
        0);
      CurrentProcess = GetCurrentProcess();
      v8 = GetCurrentProcess();
      if ( !DuplicateHandle(v8, hSourceHandle, CurrentProcess, &hObject, 0, 0, 2u) )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x1C17,
                      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
                      v9);
        goto LABEL_12;
      }
    }
    token_information = wil::get_token_information_nothrow<_TOKEN_USER,0>(&Block, hObject);
    LastError = token_information;
    if ( token_information < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1C1A,
        (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
        (const char *)(unsigned int)token_information,
        dwDesiredAccess);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
      if ( Block )
        operator delete(Block);
      return LastError;
    }
    v11 = Block;
    if ( IsWellKnownSid(*(PSID *)Block, WinLocalAccountAndAdministratorSid|WinCreatorGroupSid) )
    {
      Block = 0;
      v33 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.Internal.PlatformExtensions.UserSelection",
        0x32u,
        0x31u);
      v13 = Windows::Internal::PlatformExtensions::Details::TryActivateContractExtensionInternal(v33, 0, v12, &Block);
      v14 = v13;
      if ( v13 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x299,
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\PlatformExtensionTools.h",
          (const char *)(unsigned int)v13,
          dwDesiredAccess);
        v15 = 7199;
LABEL_22:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v15,
          (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
          (const char *)(unsigned int)v14,
          dwDesiredAccess);
LABEL_42:
        wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(&Block);
LABEL_45:
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
        operator delete(v11);
        return (unsigned int)v14;
      }
      if ( !Block )
      {
        v14 = -2147024809;
        v15 = 7200;
        goto LABEL_22;
      }
      v16 = *(PSID *)Block;
      v26 = 0;
      v17 = (*((__int64 (__fastcall **)(void *, _QWORD, _QWORD, __int64 *))v16 + 6))(Block, 0, 0, &v26);
      v14 = v17;
      if ( v17 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1C23,
          (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
          (const char *)(unsigned int)v17,
          dwDesiredAccess);
LABEL_41:
        wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(&v26);
        goto LABEL_42;
      }
      v18 = v26;
      v29 = 0;
      v14 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>>(v26);
      if ( v14 >= 0 )
        v14 = (*(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v18 + 64LL))(v18, &v29);
      if ( v14 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1C25,
          (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
          (const char *)(unsigned int)v14,
          dwDesiredAccess);
LABEL_40:
        wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(&v29);
        goto LABEL_41;
      }
      v19 = *v29;
      v28 = 0;
      v20 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v19 + 56))(v29, &v28);
      v14 = v20;
      if ( v20 < 0 )
      {
        v21 = (unsigned int)v20;
        v22 = 7208;
LABEL_31:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v22,
          (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
          (const char *)v21,
          dwDesiredAccess);
LABEL_39:
        wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(&v28);
        goto LABEL_40;
      }
      if ( !v28 )
      {
        v14 = -2147024809;
        v22 = 7209;
        v21 = 2147942487LL;
        goto LABEL_31;
      }
      v31 = 0;
      v33 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.System.Internal.UserManager",
        0x24u,
        0x23u);
      ActivationFactory = RoGetActivationFactory(v33, &GUID_100eb64b_b24c_4c38_8964_720d926d05a4, &v31);
      v14 = ActivationFactory;
      if ( ActivationFactory < 0 )
      {
        v24 = 7211;
LABEL_38:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v24,
          (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
          (const char *)(unsigned int)ActivationFactory,
          dwDesiredAccess);
        wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(&v31);
        goto LABEL_39;
      }
      ActivationFactory = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD *))(*(_QWORD *)v31 + 136LL))(v31, v28, a2);
      v14 = ActivationFactory;
      if ( ActivationFactory < 0 )
      {
        v24 = 7212;
        goto LABEL_38;
      }
      wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(&v31);
      wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(&v28);
      wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(&v29);
      wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(&v26);
      wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(&Block);
    }
    v14 = 0;
    goto LABEL_45;
  }
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  return 0;
}

```

## disassembly

```asm
0x180010f3c  mov     [rsp-8+arg_10], rbx
0x180010f41  push    rbp
0x180010f42  push    rsi
0x180010f43  push    rdi
0x180010f44  push    r14
0x180010f46  push    r15
0x180010f48  lea     rbp, [rsp-37h]
0x180010f4d  sub     rsp, 0A0h
0x180010f54  mov     rax, cs:__security_cookie
0x180010f5b  xor     rax, rsp
0x180010f5e  mov     [rbp+57h+var_30], rax
0x180010f62  mov     r14, rdx
0x180010f65  mov     rdi, rcx
0x180010f68  xor     r15d, r15d
0x180010f6b  lea     rdx, [rbp+57h+var_80]
0x180010f6f  or      ebx, 0FFFFFFFFh
0x180010f72  mov     [rbp+57h+Block], r15
0x180010f76  xor     ecx, ecx
0x180010f78  mov     [rbp+57h+hObject], r15
0x180010f7c  xor     r8d, r8d
0x180010f7f  mov     dword ptr [rbp+57h+var_80], ebx
0x180010f82  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x180010f89  nop     dword ptr [rax+rax+00h]
0x180010f8e  cmp     dword ptr [rbp+57h+var_80], 10h
0x180010f92  jz      short loc_180010FF1
0x180010f94  xor     r8d, r8d
0x180010f97  mov     dword ptr [rbp+57h+var_80], ebx
0x180010f9a  lea     rdx, [rbp+57h+var_80]
0x180010f9e  xor     ecx, ecx
0x180010fa0  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x180010fa7  nop     dword ptr [rax+rax+00h]
0x180010fac  cmp     dword ptr [rbp+57h+var_80], 0Ah
0x180010fb0  jz      short loc_180010FF1
0x180010fb2  xor     r8d, r8d
0x180010fb5  mov     dword ptr [rbp+57h+var_80], ebx
0x180010fb8  lea     rdx, [rbp+57h+var_80]
0x180010fbc  xor     ecx, ecx
0x180010fbe  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x180010fc5  nop     dword ptr [rax+rax+00h]
0x180010fca  cmp     dword ptr [rbp+57h+var_80], 5
0x180010fce  jz      short loc_180010FF1
0x180010fd0  mov     rcx, [rbp+57h+hObject]; hObject
0x180010fd4  lea     rax, [rcx-1]
0x180010fd8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180010fdc  ja      short loc_180010FEA
0x180010fde  call    cs:__imp_CloseHandle
0x180010fe5  nop     dword ptr [rax+rax+00h]
0x180010fea  xor     eax, eax
0x180010fec  jmp     loc_180011360
0x180010ff1  xor     edx, edx
0x180010ff3  lea     rcx, [rbp+57h+hObject]
0x180010ff7  cmp     [r14], r15
0x180010ffa  jz      short loc_180011038
0x180010ffc  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180011001  mov     rcx, [r14]
0x180011004  lea     rdx, [rbp+57h+hObject]
0x180011008  call    cs:__imp_UMgrQueryUserToken
0x18001100f  nop     dword ptr [rax+rax+00h]
0x180011014  mov     ebx, eax
0x180011016  test    eax, eax
0x180011018  jns     loc_1800110AE
0x18001101e  mov     rcx, [rbp+5Fh]; this
0x180011022  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x180011029  mov     r9d, eax; char *
0x18001102c  mov     edx, 1C13h; void *
0x180011031  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011036  jmp     short loc_18001109E
0x180011038  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18001103d  call    cs:__imp_GetCurrentProcess
0x180011044  nop     dword ptr [rax+rax+00h]
0x180011049  mov     rbx, rax
0x18001104c  call    cs:__imp_GetCurrentProcess
0x180011053  nop     dword ptr [rax+rax+00h]
0x180011058  mov     [rsp+0C0h+dwOptions], 2; dwOptions
0x180011060  lea     r9, [rbp+57h+hObject]; lpTargetHandle
0x180011064  mov     rcx, rax; hSourceProcessHandle
0x180011067  mov     [rsp+0C0h+bInheritHandle], r15d; bInheritHandle
0x18001106c  mov     r8, rbx; hTargetProcessHandle
0x18001106f  mov     [rsp+0C0h+dwDesiredAccess], r15d; dwDesiredAccess
0x180011074  mov     rdx, rdi; hSourceHandle
0x180011077  call    cs:__imp_DuplicateHandle
0x18001107e  nop     dword ptr [rax+rax+00h]
0x180011083  test    eax, eax
0x180011085  jnz     short loc_1800110AE
0x180011087  mov     rcx, [rbp+5Fh]; this
0x18001108b  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x180011092  mov     edx, 1C17h; void *
0x180011097  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001109c  mov     ebx, eax
0x18001109e  lea     rcx, [rbp+57h+hObject]
0x1800110a2  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800110a7  mov     eax, ebx
0x1800110a9  jmp     loc_180011360
0x1800110ae  mov     rdx, [rbp+57h+hObject]
0x1800110b2  lea     rcx, [rbp+57h+Block]
0x1800110b6  call    ??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)
0x1800110bb  mov     ebx, eax
0x1800110bd  test    eax, eax
0x1800110bf  jns     short loc_1800110F2
0x1800110c1  mov     rcx, [rbp+5Fh]; this
0x1800110c5  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x1800110cc  mov     r9d, eax; char *
0x1800110cf  mov     edx, 1C1Ah; void *
0x1800110d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800110d9  lea     rcx, [rbp+57h+hObject]
0x1800110dd  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800110e2  mov     rcx, [rbp+57h+Block]; Block
0x1800110e6  test    rcx, rcx
0x1800110e9  jz      short loc_1800110A7
0x1800110eb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800110f0  jmp     short loc_1800110A7
0x1800110f2  mov     rbx, [rbp+57h+Block]
0x1800110f6  mov     edx, 6Eh ; 'n'; WellKnownSidType
0x1800110fb  mov     rcx, [rbx]; pSid
0x1800110fe  call    cs:__imp_IsWellKnownSid
0x180011105  nop     dword ptr [rax+rax+00h]
0x18001110a  test    eax, eax
0x18001110c  jz      loc_18001134A
0x180011112  mov     r9d, 31h ; '1'; unsigned int
0x180011118  mov     [rbp+57h+Block], r15
0x18001111c  lea     rdx, sourceString; "Windows.Internal.PlatformExtensions.Use"...
0x180011123  mov     [rbp+57h+var_38], r15
0x180011127  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18001112b  lea     r8d, [r9+1]; unsigned int
0x18001112f  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180011134  mov     rcx, [rbp+57h+var_38]
0x180011138  lea     r9, [rbp+57h+Block]
0x18001113c  mov     edx, r15d
0x18001113f  call    ?TryActivateContractExtensionInternal@Details@PlatformExtensions@Internal@Windows@@YAJPEAUHSTRING__@@UWindowId@WindowManagement@ApplicationModel@34@AEBU_GUID@@PEAPEAX@Z; Windows::Internal::PlatformExtensions::Details::TryActivateContractExtensionInternal(HSTRING__ *,Windows::Internal::ApplicationModel::WindowManagement::WindowId,_GUID const &,void * *)
0x180011144  mov     edi, eax
0x180011146  test    eax, eax
0x180011148  jns     short loc_180011169
0x18001114a  mov     rcx, [rbp+5Fh]; this
0x18001114e  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\Platf"...
0x180011155  mov     r9d, eax; char *
0x180011158  mov     edx, 299h; void *
0x18001115d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011162  mov     edx, 1C1Fh
0x180011167  jmp     short loc_18001117C
0x180011169  mov     rcx, [rbp+57h+Block]
0x18001116d  test    rcx, rcx
0x180011170  jnz     short loc_180011194
0x180011172  mov     edi, 80070057h
0x180011177  mov     edx, 1C20h; void *
0x18001117c  mov     rcx, [rbp+5Fh]; this
0x180011180  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x180011187  mov     r9d, edi; char *
0x18001118a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001118f  jmp     loc_180011312
0x180011194  mov     rax, [rcx]
0x180011197  lea     r9, [rbp+57h+var_80]
0x18001119b  xor     r8d, r8d
0x18001119e  mov     [rbp+57h+var_80], r15
0x1800111a2  xor     edx, edx
0x1800111a4  mov     rax, [rax+30h]
0x1800111a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800111ad  mov     edi, eax
0x1800111af  test    eax, eax
0x1800111b1  jns     short loc_1800111D0
0x1800111b3  mov     rcx, [rbp+5Fh]; this
0x1800111b7  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x1800111be  mov     r9d, eax; char *
0x1800111c1  mov     edx, 1C23h; void *
0x1800111c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800111cb  jmp     loc_180011309
0x1800111d0  mov     rsi, [rbp+57h+var_80]
0x1800111d4  mov     rcx, rsi
0x1800111d7  mov     [rbp+57h+var_68], r15
0x1800111db  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *> *,tagCOWAIT_FLAGS,void *)
0x1800111e0  mov     edi, eax
0x1800111e2  test    eax, eax
0x1800111e4  js      short loc_1800111FB
0x1800111e6  mov     rax, [rsi]
0x1800111e9  lea     rdx, [rbp+57h+var_68]
0x1800111ed  mov     rcx, rsi
0x1800111f0  mov     rax, [rax+40h]
0x1800111f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800111f9  mov     edi, eax
0x1800111fb  test    edi, edi
0x1800111fd  jns     short loc_18001121C
0x1800111ff  mov     rcx, [rbp+5Fh]; this
0x180011203  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x18001120a  mov     r9d, edi; char *
0x18001120d  mov     edx, 1C25h; void *
0x180011212  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011217  jmp     loc_180011300
0x18001121c  mov     rcx, [rbp+57h+var_68]
0x180011220  lea     rdx, [rbp+57h+var_70]
0x180011224  mov     rax, [rcx]
0x180011227  mov     [rbp+57h+var_70], r15
0x18001122b  mov     rax, [rax+38h]
0x18001122f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011234  mov     edi, eax
0x180011236  test    eax, eax
0x180011238  jns     short loc_180011257
0x18001123a  mov     r9d, eax; char *
0x18001123d  mov     edx, 1C28h; void *
0x180011242  mov     rcx, [rbp+5Fh]; this
0x180011246  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x18001124d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011252  jmp     loc_1800112F7
0x180011257  cmp     [rbp+57h+var_70], r15
0x18001125b  jnz     short loc_18001126C
0x18001125d  mov     edi, 80070057h
0x180011262  mov     edx, 1C29h
0x180011267  mov     r9d, edi
0x18001126a  jmp     short loc_180011242
0x18001126c  mov     r9d, 23h ; '#'; unsigned int
0x180011272  mov     [rbp+57h+var_58], r15
0x180011276  lea     rdx, ?RuntimeClass_Windows_System_Internal_UserManager@@3QBGB; "Windows.System.Internal.UserManager"
0x18001127d  mov     [rbp+57h+var_38], r15
0x180011281  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180011285  lea     r8d, [r9+1]; unsigned int
0x180011289  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001128e  mov     rcx, [rbp+57h+var_38]
0x180011292  lea     r8, [rbp+57h+var_58]
0x180011296  lea     rdx, _GUID_100eb64b_b24c_4c38_8964_720d926d05a4
0x18001129d  call    cs:__imp_RoGetActivationFactory
0x1800112a4  nop     dword ptr [rax+rax+00h]
0x1800112a9  mov     edi, eax
0x1800112ab  test    eax, eax
0x1800112ad  jns     short loc_1800112B6
0x1800112af  mov     edx, 1C2Bh
0x1800112b4  jmp     short loc_1800112DB
0x1800112b6  mov     rcx, [rbp+57h+var_58]
0x1800112ba  mov     r8, r14
0x1800112bd  mov     rdx, [rbp+57h+var_70]
0x1800112c1  mov     rax, [rcx]
0x1800112c4  mov     rax, [rax+88h]
0x1800112cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800112d0  mov     edi, eax
0x1800112d2  test    eax, eax
0x1800112d4  jns     short loc_18001131D
0x1800112d6  mov     edx, 1C2Ch; void *
0x1800112db  mov     rcx, [rbp+5Fh]; this
0x1800112df  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x1800112e6  mov     r9d, eax; char *
0x1800112e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800112ee  lea     rcx, [rbp+57h+var_58]
0x1800112f2  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(void)
0x1800112f7  lea     rcx, [rbp+57h+var_70]
0x1800112fb  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(void)
0x180011300  lea     rcx, [rbp+57h+var_68]
0x180011304  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(void)
0x180011309  lea     rcx, [rbp+57h+var_80]
0x18001130d  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(void)
0x180011312  lea     rcx, [rbp+57h+Block]
0x180011316  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(void)
0x18001131b  jmp     short loc_18001134D
0x18001131d  lea     rcx, [rbp+57h+var_58]
0x180011321  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(void)
0x180011326  lea     rcx, [rbp+57h+var_70]
0x18001132a  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(void)
0x18001132f  lea     rcx, [rbp+57h+var_68]
0x180011333  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(void)
0x180011338  lea     rcx, [rbp+57h+var_80]
0x18001133c  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(void)
0x180011341  lea     rcx, [rbp+57h+Block]
0x180011345  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(void)
0x18001134a  mov     edi, r15d
0x18001134d  lea     rcx, [rbp+57h+hObject]
0x180011351  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180011356  mov     rcx, rbx; Block
0x180011359  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001135e  mov     eax, edi
0x180011360  mov     rcx, [rbp+57h+var_30]
0x180011364  xor     rcx, rsp; StackCookie
0x180011367  call    __security_check_cookie
0x18001136c  mov     rbx, [rsp+0C0h+arg_10]
0x180011374  add     rsp, 0A0h
0x18001137b  pop     r15
0x18001137d  pop     r14
0x18001137f  pop     rdi
0x180011380  pop     rsi
0x180011381  pop     rbp
0x180011382  retn
```
