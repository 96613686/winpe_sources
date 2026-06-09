# ReplaceDSMAIfPresent

- ea: `0x18001107c`
- end: `0x1800114c4`
- name: `ReplaceDSMAIfPresent`
- size: `1096`
- prototype: `__int64 __fastcall(HANDLE hSourceHandle)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002a1d8`

## callees

- `0x180007c78`
- `0x18000c790`
- `0x18000f9e0`
- `0x18001107c`
- `0x1800182bc`
- `0x180018400`
- `0x18001b494`
- `0x180026678`
- `0x1800270cc`
- `0x18002cd5c`
- `0x180038760`
- `0x1800444e0`
- `0x180045010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18001123e`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18001123e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001117d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001118c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001117d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001118c`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800111b7`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800111b7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001111e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001111e`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800113dd`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800113dd`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x1800110c2`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x1800110e0`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x1800110fe`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x1800110c2`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x1800110e0`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x1800110fe`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180011148`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180011148`

## string_xrefs

- `0x180011162`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x1800111cb`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180011205`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x1800112c0`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x1800112f7`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180011343`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180011386`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18001141f`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18001128e`: `onecoreuap\internal\shell\inc\PlatformExtensionTools.h`
- `0x18001125c`: `Windows.Internal.PlatformExtensions.UserSelection`

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
          (void *)0x1CE0,
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
                      (void *)0x1CE4,
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
        (void *)0x1CE7,
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
        v15 = 7404;
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
        v15 = 7405;
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
          (void *)0x1CF0,
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
          (void *)0x1CF2,
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
        v22 = 7413;
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
        v22 = 7414;
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
        v24 = 7416;
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
        v24 = 7417;
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
0x18001107c  mov     [rsp-8+arg_10], rbx
0x180011081  push    rbp
0x180011082  push    rsi
0x180011083  push    rdi
0x180011084  push    r14
0x180011086  push    r15
0x180011088  lea     rbp, [rsp-37h]
0x18001108d  sub     rsp, 0A0h
0x180011094  mov     rax, cs:__security_cookie
0x18001109b  xor     rax, rsp
0x18001109e  mov     [rbp+57h+var_30], rax
0x1800110a2  mov     r14, rdx
0x1800110a5  mov     rdi, rcx
0x1800110a8  xor     r15d, r15d
0x1800110ab  lea     rdx, [rbp+57h+var_80]
0x1800110af  or      ebx, 0FFFFFFFFh
0x1800110b2  mov     [rbp+57h+Block], r15
0x1800110b6  xor     ecx, ecx
0x1800110b8  mov     [rbp+57h+hObject], r15
0x1800110bc  xor     r8d, r8d
0x1800110bf  mov     dword ptr [rbp+57h+var_80], ebx
0x1800110c2  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x1800110c9  nop     dword ptr [rax+rax+00h]
0x1800110ce  cmp     dword ptr [rbp+57h+var_80], 10h
0x1800110d2  jz      short loc_180011131
0x1800110d4  xor     r8d, r8d
0x1800110d7  mov     dword ptr [rbp+57h+var_80], ebx
0x1800110da  lea     rdx, [rbp+57h+var_80]
0x1800110de  xor     ecx, ecx
0x1800110e0  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x1800110e7  nop     dword ptr [rax+rax+00h]
0x1800110ec  cmp     dword ptr [rbp+57h+var_80], 0Ah
0x1800110f0  jz      short loc_180011131
0x1800110f2  xor     r8d, r8d
0x1800110f5  mov     dword ptr [rbp+57h+var_80], ebx
0x1800110f8  lea     rdx, [rbp+57h+var_80]
0x1800110fc  xor     ecx, ecx
0x1800110fe  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x180011105  nop     dword ptr [rax+rax+00h]
0x18001110a  cmp     dword ptr [rbp+57h+var_80], 5
0x18001110e  jz      short loc_180011131
0x180011110  mov     rcx, [rbp+57h+hObject]; hObject
0x180011114  lea     rax, [rcx-1]
0x180011118  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001111c  ja      short loc_18001112A
0x18001111e  call    cs:__imp_CloseHandle
0x180011125  nop     dword ptr [rax+rax+00h]
0x18001112a  xor     eax, eax
0x18001112c  jmp     loc_1800114A0
0x180011131  xor     edx, edx
0x180011133  lea     rcx, [rbp+57h+hObject]
0x180011137  cmp     [r14], r15
0x18001113a  jz      short loc_180011178
0x18001113c  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180011141  mov     rcx, [r14]
0x180011144  lea     rdx, [rbp+57h+hObject]
0x180011148  call    cs:__imp_UMgrQueryUserToken
0x18001114f  nop     dword ptr [rax+rax+00h]
0x180011154  mov     ebx, eax
0x180011156  test    eax, eax
0x180011158  jns     loc_1800111EE
0x18001115e  mov     rcx, [rbp+5Fh]; this
0x180011162  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180011169  mov     r9d, eax; char *
0x18001116c  mov     edx, 1CE0h; void *
0x180011171  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011176  jmp     short loc_1800111DE
0x180011178  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18001117d  call    cs:__imp_GetCurrentProcess
0x180011184  nop     dword ptr [rax+rax+00h]
0x180011189  mov     rbx, rax
0x18001118c  call    cs:__imp_GetCurrentProcess
0x180011193  nop     dword ptr [rax+rax+00h]
0x180011198  mov     [rsp+0C0h+dwOptions], 2; dwOptions
0x1800111a0  lea     r9, [rbp+57h+hObject]; lpTargetHandle
0x1800111a4  mov     rcx, rax; hSourceProcessHandle
0x1800111a7  mov     [rsp+0C0h+bInheritHandle], r15d; bInheritHandle
0x1800111ac  mov     r8, rbx; hTargetProcessHandle
0x1800111af  mov     [rsp+0C0h+dwDesiredAccess], r15d; dwDesiredAccess
0x1800111b4  mov     rdx, rdi; hSourceHandle
0x1800111b7  call    cs:__imp_DuplicateHandle
0x1800111be  nop     dword ptr [rax+rax+00h]
0x1800111c3  test    eax, eax
0x1800111c5  jnz     short loc_1800111EE
0x1800111c7  mov     rcx, [rbp+5Fh]; this
0x1800111cb  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x1800111d2  mov     edx, 1CE4h; void *
0x1800111d7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800111dc  mov     ebx, eax
0x1800111de  lea     rcx, [rbp+57h+hObject]
0x1800111e2  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800111e7  mov     eax, ebx
0x1800111e9  jmp     loc_1800114A0
0x1800111ee  mov     rdx, [rbp+57h+hObject]
0x1800111f2  lea     rcx, [rbp+57h+Block]
0x1800111f6  call    ??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)
0x1800111fb  mov     ebx, eax
0x1800111fd  test    eax, eax
0x1800111ff  jns     short loc_180011232
0x180011201  mov     rcx, [rbp+5Fh]; this
0x180011205  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18001120c  mov     r9d, eax; char *
0x18001120f  mov     edx, 1CE7h; void *
0x180011214  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011219  lea     rcx, [rbp+57h+hObject]
0x18001121d  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180011222  mov     rcx, [rbp+57h+Block]; Block
0x180011226  test    rcx, rcx
0x180011229  jz      short loc_1800111E7
0x18001122b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180011230  jmp     short loc_1800111E7
0x180011232  mov     rbx, [rbp+57h+Block]
0x180011236  mov     edx, 6Eh ; 'n'; WellKnownSidType
0x18001123b  mov     rcx, [rbx]; pSid
0x18001123e  call    cs:__imp_IsWellKnownSid
0x180011245  nop     dword ptr [rax+rax+00h]
0x18001124a  test    eax, eax
0x18001124c  jz      loc_18001148A
0x180011252  mov     r9d, 31h ; '1'; unsigned int
0x180011258  mov     [rbp+57h+Block], r15
0x18001125c  lea     rdx, sourceString; "Windows.Internal.PlatformExtensions.Use"...
0x180011263  mov     [rbp+57h+var_38], r15
0x180011267  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18001126b  lea     r8d, [r9+1]; unsigned int
0x18001126f  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180011274  mov     rcx, [rbp+57h+var_38]
0x180011278  lea     r9, [rbp+57h+Block]
0x18001127c  mov     edx, r15d
0x18001127f  call    ?TryActivateContractExtensionInternal@Details@PlatformExtensions@Internal@Windows@@YAJPEAUHSTRING__@@UWindowId@WindowManagement@ApplicationModel@34@AEBU_GUID@@PEAPEAX@Z; Windows::Internal::PlatformExtensions::Details::TryActivateContractExtensionInternal(HSTRING__ *,Windows::Internal::ApplicationModel::WindowManagement::WindowId,_GUID const &,void * *)
0x180011284  mov     edi, eax
0x180011286  test    eax, eax
0x180011288  jns     short loc_1800112A9
0x18001128a  mov     rcx, [rbp+5Fh]; this
0x18001128e  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\Platf"...
0x180011295  mov     r9d, eax; char *
0x180011298  mov     edx, 299h; void *
0x18001129d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800112a2  mov     edx, 1CECh
0x1800112a7  jmp     short loc_1800112BC
0x1800112a9  mov     rcx, [rbp+57h+Block]
0x1800112ad  test    rcx, rcx
0x1800112b0  jnz     short loc_1800112D4
0x1800112b2  mov     edi, 80070057h
0x1800112b7  mov     edx, 1CEDh; void *
0x1800112bc  mov     rcx, [rbp+5Fh]; this
0x1800112c0  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x1800112c7  mov     r9d, edi; char *
0x1800112ca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800112cf  jmp     loc_180011452
0x1800112d4  mov     rax, [rcx]
0x1800112d7  lea     r9, [rbp+57h+var_80]
0x1800112db  xor     r8d, r8d
0x1800112de  mov     [rbp+57h+var_80], r15
0x1800112e2  xor     edx, edx
0x1800112e4  mov     rax, [rax+30h]
0x1800112e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800112ed  mov     edi, eax
0x1800112ef  test    eax, eax
0x1800112f1  jns     short loc_180011310
0x1800112f3  mov     rcx, [rbp+5Fh]; this
0x1800112f7  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x1800112fe  mov     r9d, eax; char *
0x180011301  mov     edx, 1CF0h; void *
0x180011306  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001130b  jmp     loc_180011449
0x180011310  mov     rsi, [rbp+57h+var_80]
0x180011314  mov     rcx, rsi
0x180011317  mov     [rbp+57h+var_68], r15
0x18001131b  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *> *,tagCOWAIT_FLAGS,void *)
0x180011320  mov     edi, eax
0x180011322  test    eax, eax
0x180011324  js      short loc_18001133B
0x180011326  mov     rax, [rsi]
0x180011329  lea     rdx, [rbp+57h+var_68]
0x18001132d  mov     rcx, rsi
0x180011330  mov     rax, [rax+40h]
0x180011334  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011339  mov     edi, eax
0x18001133b  test    edi, edi
0x18001133d  jns     short loc_18001135C
0x18001133f  mov     rcx, [rbp+5Fh]; this
0x180011343  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18001134a  mov     r9d, edi; char *
0x18001134d  mov     edx, 1CF2h; void *
0x180011352  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011357  jmp     loc_180011440
0x18001135c  mov     rcx, [rbp+57h+var_68]
0x180011360  lea     rdx, [rbp+57h+var_70]
0x180011364  mov     rax, [rcx]
0x180011367  mov     [rbp+57h+var_70], r15
0x18001136b  mov     rax, [rax+38h]
0x18001136f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011374  mov     edi, eax
0x180011376  test    eax, eax
0x180011378  jns     short loc_180011397
0x18001137a  mov     r9d, eax; char *
0x18001137d  mov     edx, 1CF5h; void *
0x180011382  mov     rcx, [rbp+5Fh]; this
0x180011386  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18001138d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011392  jmp     loc_180011437
0x180011397  cmp     [rbp+57h+var_70], r15
0x18001139b  jnz     short loc_1800113AC
0x18001139d  mov     edi, 80070057h
0x1800113a2  mov     edx, 1CF6h
0x1800113a7  mov     r9d, edi
0x1800113aa  jmp     short loc_180011382
0x1800113ac  mov     r9d, 23h ; '#'; unsigned int
0x1800113b2  mov     [rbp+57h+var_58], r15
0x1800113b6  lea     rdx, ?RuntimeClass_Windows_System_Internal_UserManager@@3QBGB; "Windows.System.Internal.UserManager"
0x1800113bd  mov     [rbp+57h+var_38], r15
0x1800113c1  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800113c5  lea     r8d, [r9+1]; unsigned int
0x1800113c9  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800113ce  mov     rcx, [rbp+57h+var_38]
0x1800113d2  lea     r8, [rbp+57h+var_58]
0x1800113d6  lea     rdx, _GUID_100eb64b_b24c_4c38_8964_720d926d05a4
0x1800113dd  call    cs:__imp_RoGetActivationFactory
0x1800113e4  nop     dword ptr [rax+rax+00h]
0x1800113e9  mov     edi, eax
0x1800113eb  test    eax, eax
0x1800113ed  jns     short loc_1800113F6
0x1800113ef  mov     edx, 1CF8h
0x1800113f4  jmp     short loc_18001141B
0x1800113f6  mov     rcx, [rbp+57h+var_58]
0x1800113fa  mov     r8, r14
0x1800113fd  mov     rdx, [rbp+57h+var_70]
0x180011401  mov     rax, [rcx]
0x180011404  mov     rax, [rax+88h]
0x18001140b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011410  mov     edi, eax
0x180011412  test    eax, eax
0x180011414  jns     short loc_18001145D
0x180011416  mov     edx, 1CF9h; void *
0x18001141b  mov     rcx, [rbp+5Fh]; this
0x18001141f  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180011426  mov     r9d, eax; char *
0x180011429  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001142e  lea     rcx, [rbp+57h+var_58]
0x180011432  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(void)
0x180011437  lea     rcx, [rbp+57h+var_70]
0x18001143b  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(void)
0x180011440  lea     rcx, [rbp+57h+var_68]
0x180011444  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(void)
0x180011449  lea     rcx, [rbp+57h+var_80]
0x18001144d  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(void)
0x180011452  lea     rcx, [rbp+57h+Block]
0x180011456  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(void)
0x18001145b  jmp     short loc_18001148D
0x18001145d  lea     rcx, [rbp+57h+var_58]
0x180011461  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(void)
0x180011466  lea     rcx, [rbp+57h+var_70]
0x18001146a  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(void)
0x18001146f  lea     rcx, [rbp+57h+var_68]
0x180011473  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(void)
0x180011478  lea     rcx, [rbp+57h+var_80]
0x18001147c  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(void)
0x180011481  lea     rcx, [rbp+57h+Block]
0x180011485  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(void)
0x18001148a  mov     edi, r15d
0x18001148d  lea     rcx, [rbp+57h+hObject]
0x180011491  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180011496  mov     rcx, rbx; Block
0x180011499  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001149e  mov     eax, edi
0x1800114a0  mov     rcx, [rbp+57h+var_30]
0x1800114a4  xor     rcx, rsp; StackCookie
0x1800114a7  call    __security_check_cookie
0x1800114ac  mov     rbx, [rsp+0C0h+arg_10]
0x1800114b4  add     rsp, 0A0h
0x1800114bb  pop     r15
0x1800114bd  pop     r14
0x1800114bf  pop     rdi
0x1800114c0  pop     rsi
0x1800114c1  pop     rbp
0x1800114c2  retn
```
