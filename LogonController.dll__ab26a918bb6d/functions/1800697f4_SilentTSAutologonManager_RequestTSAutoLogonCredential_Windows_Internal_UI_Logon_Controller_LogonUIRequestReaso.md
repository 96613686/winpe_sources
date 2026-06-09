# SilentTSAutologonManager::RequestTSAutoLogonCredential(Windows::Internal::UI::Logon::Controller::LogonUIRequestReason,Windows::Internal::UI::Logon::Controller::LogonUIFlags,Windows::Internal::UI::Logon::Controller::IUserSettingManager *,IInspectable *,Windows::Internal::UI::Logon::CredProvData::IDisplayStateProvider *,ushort const *,Windows::Internal::UI::Logon::CredProvData::ICredentialSerialization * *)

- ea: `0x1800697f4`
- end: `0x180069b3b`
- name: `?RequestTSAutoLogonCredential@SilentTSAutologonManager@@QEAAJW4LogonUIRequestReason@Controller@Logon@UI@Internal@Windows@@W4LogonUIFlags@34567@PEAUIUserSettingManager@34567@PEAUIInspectable@@PEAUIDisplayStateProvider@CredProvData@4567@PEBGPEAPEAUICredentialSerialization@CredProvData@4567@@Z`
- size: `839`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180021730`

## callees

- `0x18000cd1c`
- `0x18000df10`
- `0x180026e70`
- `0x1800314f8`
- `0x180033f8c`
- `0x18003c56c`
- `0x18005d488`
- `0x18005db5c`
- `0x18005f1f8`
- `0x180060e24`
- `0x1800697f4`
- `0x180069b44`
- `0x18007f6ac`
- `0x1800819b8`
- `0x18009d010`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x180069ad0`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180069ad0`
- `KERNEL32!GetLastError` at `0x180069a2b`
- `KERNEL32!GetLastError` at `0x180069a2b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800698d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800698d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800698b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800698b4`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall SilentTSAutologonManager::RequestTSAutoLogonCredential(
        HSTRING a1,
        int a2,
        int a3,
        __int64 a4,
        __int64 a5,
        _QWORD *a6,
        const WCHAR *sourceString,
        _QWORD *length)
{
  _QWORD *v10; // r12
  int event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // ebx
  __int64 v12; // rdx
  PSRWLOCK v14; // rsi
  unsigned __int64 v15; // rcx
  HSTRING Ptr; // rcx
  int v17; // eax
  signed int LastError; // eax
  int v19; // [rsp+28h] [rbp-69h]
  __int64 v20; // [rsp+38h] [rbp-59h] BYREF
  __int64 v21; // [rsp+40h] [rbp-51h] BYREF
  HSTRING string; // [rsp+48h] [rbp-49h] BYREF
  PSRWLOCK SRWLock; // [rsp+50h] [rbp-41h] BYREF
  _QWORD v24[2]; // [rsp+58h] [rbp-39h] BYREF
  __int64 v25; // [rsp+68h] [rbp-29h] BYREF
  __int64 v26; // [rsp+70h] [rbp-21h] BYREF
  _QWORD *v27; // [rsp+78h] [rbp-19h] BYREF
  PSRWLOCK v28; // [rsp+80h] [rbp-11h] BYREF
  int v29; // [rsp+88h] [rbp-9h]
  int v30; // [rsp+8Ch] [rbp-5h]
  wil::details::in1diag3 *retaddr; // [rsp+D0h] [rbp+3Fh]

  v10 = length;
  *length = 0;
  event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = SilentTSAutologonManager::EnsureCredentialThreadStarted((SilentTSAutologonManager *)a1);
  if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
  {
    v12 = 299;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\silenttsautologonmanager.cpp",
      (const char *)(unsigned int)event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
      v19);
    return (unsigned int)event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  }
  event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(a1 + 26, 0);
  if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
  {
    v12 = 300;
    goto LABEL_3;
  }
  CreateRefCountedObj<Windows::Internal::String,>(&SRWLock);
  v14 = SRWLock;
  if ( sourceString )
  {
    LODWORD(length) = 0;
    string = 0;
    v15 = -1;
    do
      ++v15;
    while ( sourceString[v15] );
    event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = ULongLongToULong(v15, (unsigned int *)&length);
    if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0
      || (event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = WindowsCreateString(sourceString, (UINT32)length, &string),
          event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x131,
        (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\silenttsautologonmanager.cpp",
        (const char *)(unsigned int)event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
        v19);
      if ( v14 )
        (*((void (__fastcall **)(PSRWLOCK))v14->Ptr + 2))(v14);
      return (unsigned int)event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
    }
    Ptr = (HSTRING)v14[1].Ptr;
    v14[1].Ptr = string;
    WindowsDeleteString(Ptr);
  }
  string = a1;
  Microsoft::WRL::ComPtr<SilentTSAutologonManager>::InternalAddRef(&string);
  v21 = a4;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v21);
  v20 = a5;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v20);
  length = a6;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&length);
  v24[0] = a1;
  Microsoft::WRL::ComPtr<SilentTSAutologonManager>::InternalAddRef(v24);
  v24[1] = a1;
  v25 = a4;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v25);
  v26 = a5;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v26);
  v27 = a6;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v27);
  v28 = v14;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v28);
  v29 = a2;
  v30 = a3;
  v17 = DispatchEvent__lambda_00a03976a6977d1b53c6c79cf41425ac_(*((_QWORD *)a1 + 20), v24);
  event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x13E,
      (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\silenttsautologonmanager.cpp",
      (const char *)(unsigned int)v17,
      v19);
    lambda_00a03976a6977d1b53c6c79cf41425ac_::__lambda_00a03976a6977d1b53c6c79cf41425ac_(v24);
    Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&length);
    Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&v20);
    Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&v21);
    Microsoft::WRL::ComPtr<SilentTSAutologonManager>::InternalRelease(&string);
    if ( v14 )
      (*((void (__fastcall **)(PSRWLOCK))v14->Ptr + 2))(v14);
    return (unsigned int)event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  }
  if ( !(unsigned __int8)_wait___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_NKH_Z(
                           a1 + 26,
                           300000) )
  {
    LastError = GetLastError();
    event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = LastError;
    if ( LastError > 0 )
      event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = (unsigned __int16)LastError | 0x80070000;
    if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x145,
        (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\silenttsautologonmanager.cpp",
        (const char *)(unsigned int)event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
        v19);
      lambda_00a03976a6977d1b53c6c79cf41425ac_::__lambda_00a03976a6977d1b53c6c79cf41425ac_(v24);
      Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&length);
      Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&v20);
      Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&v21);
      Microsoft::WRL::ComPtr<SilentTSAutologonManager>::InternalRelease(&string);
      if ( v14 )
        (*((void (__fastcall **)(PSRWLOCK))v14->Ptr + 2))(v14);
      return (unsigned int)event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
    }
  }
  Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, a1 + 20);
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(a1 + 30);
  *v10 = *((_QWORD *)a1 + 15);
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  lambda_00a03976a6977d1b53c6c79cf41425ac_::__lambda_00a03976a6977d1b53c6c79cf41425ac_(v24);
  Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&length);
  Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&v20);
  Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&v21);
  Microsoft::WRL::ComPtr<SilentTSAutologonManager>::InternalRelease(&string);
  if ( v14 )
    (*((void (__fastcall **)(PSRWLOCK))v14->Ptr + 2))(v14);
  return 0;
}

```

## disassembly

```asm
0x1800697f4  mov     rax, rsp
0x1800697f7  mov     [rax+8], rbx
0x1800697fb  mov     [rax+18h], r8d
0x1800697ff  mov     [rax+10h], edx
0x180069802  push    rbp
0x180069803  push    rsi
0x180069804  push    rdi
0x180069805  push    r12
0x180069807  push    r13
0x180069809  push    r14
0x18006980b  push    r15
0x18006980d  lea     rbp, [rax-3Fh]
0x180069811  sub     rsp, 90h
0x180069818  mov     r13, r9
0x18006981b  mov     r14, rcx
0x18006981e  xor     edi, edi
0x180069820  mov     r12, [rbp+37h+length]
0x180069824  mov     [r12], rdi
0x180069828  call    ?EnsureCredentialThreadStarted@SilentTSAutologonManager@@AEAAJXZ; SilentTSAutologonManager::EnsureCredentialThreadStarted(void)
0x18006982d  mov     ebx, eax
0x18006982f  test    eax, eax
0x180069831  jns     short loc_180069852
0x180069833  mov     edx, 12Bh; void *
0x180069838  lea     r8, aPcshellShellAu_1; "pcshell\\shell\\auth\\authux\\controlle"...
0x18006983f  mov     r9d, ebx; char *
0x180069842  mov     rcx, [rbp+3Fh]; this
0x180069846  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006984b  mov     eax, ebx
0x18006984d  jmp     loc_180069B20
0x180069852  xor     edx, edx
0x180069854  lea     rcx, [r14+68h]
0x180069858  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18006985d  mov     ebx, eax
0x18006985f  test    eax, eax
0x180069861  jns     short loc_18006986A
0x180069863  mov     edx, 12Ch
0x180069868  jmp     short loc_180069838
0x18006986a  lea     rcx, [rbp+37h+SRWLock]
0x18006986e  call    ??$CreateRefCountedObj@VString@Internal@Windows@@$$V@@YA?AV?$ComPtr@V?$CRefCountedObject@VString@Internal@Windows@@@@@WRL@Microsoft@@XZ; CreateRefCountedObj<Windows::Internal::String,>(void)
0x180069873  nop
0x180069874  mov     rsi, [rbp+37h+SRWLock]
0x180069878  mov     rdi, [rbp+37h+sourceString]
0x18006987c  xor     eax, eax
0x18006987e  test    rdi, rdi
0x180069881  jz      short loc_1800698D6
0x180069883  mov     dword ptr [rbp+37h+length], eax
0x180069886  mov     [rbp+37h+string], rax
0x18006988a  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18006988e  inc     rcx; unsigned __int64
0x180069891  cmp     [rdi+rcx*2], ax
0x180069895  jnz     short loc_18006988E
0x180069897  lea     rdx, [rbp+37h+length]; unsigned int *
0x18006989b  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1800698a0  mov     ebx, eax
0x1800698a2  test    eax, eax
0x1800698a4  js      loc_1800699E6
0x1800698aa  lea     r8, [rbp+37h+string]; string
0x1800698ae  mov     edx, dword ptr [rbp+37h+length]; length
0x1800698b1  mov     rcx, rdi; sourceString
0x1800698b4  call    cs:__imp_WindowsCreateString
0x1800698ba  mov     ebx, eax
0x1800698bc  test    eax, eax
0x1800698be  js      loc_1800699E6
0x1800698c4  mov     rcx, [rsi+8]; string
0x1800698c8  mov     rax, [rbp+37h+string]
0x1800698cc  mov     [rsi+8], rax
0x1800698d0  call    cs:__imp_WindowsDeleteString
0x1800698d6  mov     [rbp+37h+string], r14
0x1800698da  lea     rcx, [rbp+37h+string]
0x1800698de  call    ?InternalAddRef@?$ComPtr@VSilentTSAutologonManager@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<SilentTSAutologonManager>::InternalAddRef(void)
0x1800698e3  nop
0x1800698e4  mov     [rbp+37h+var_88], r13
0x1800698e8  lea     rcx, [rbp+37h+var_88]
0x1800698ec  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x1800698f1  nop
0x1800698f2  mov     rdi, [rbp+37h+arg_20]
0x1800698f6  mov     [rbp+37h+var_90], rdi
0x1800698fa  lea     rcx, [rbp+37h+var_90]
0x1800698fe  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x180069903  nop
0x180069904  mov     rbx, [rbp+37h+arg_28]
0x180069908  mov     [rbp+37h+length], rbx
0x18006990c  lea     rcx, [rbp+37h+length]
0x180069910  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x180069915  nop
0x180069916  mov     [rbp+37h+var_70], r14
0x18006991a  lea     rcx, [rbp+37h+var_70]
0x18006991e  call    ?InternalAddRef@?$ComPtr@VSilentTSAutologonManager@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<SilentTSAutologonManager>::InternalAddRef(void)
0x180069923  mov     [rbp+37h+var_68], r14
0x180069927  mov     [rbp+37h+var_60], r13
0x18006992b  lea     rcx, [rbp+37h+var_60]
0x18006992f  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x180069934  mov     [rbp+37h+var_58], rdi
0x180069938  lea     rcx, [rbp+37h+var_58]
0x18006993c  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x180069941  mov     [rbp+37h+var_50], rbx
0x180069945  lea     rcx, [rbp+37h+var_50]
0x180069949  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x18006994e  mov     [rbp+37h+var_48], rsi
0x180069952  lea     rcx, [rbp+37h+var_48]
0x180069956  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x18006995b  mov     eax, [rbp+37h+arg_8]
0x18006995e  mov     [rbp+37h+var_40], eax
0x180069961  mov     eax, [rbp+37h+arg_10]
0x180069964  mov     [rbp+37h+var_3C], eax
0x180069967  lea     rdx, [rbp+37h+var_70]
0x18006996b  mov     rcx, [r14+0A0h]
0x180069972  call    DispatchEvent__lambda_00a03976a6977d1b53c6c79cf41425ac___; DispatchEvent__lambda_00a03976a6977d1b53c6c79cf41425ac_
0x180069977  mov     ebx, eax
0x180069979  test    eax, eax
0x18006997b  jns     loc_180069A19
0x180069981  mov     rcx, [rbp+3Fh]; this
0x180069985  mov     r9d, eax; char *
0x180069988  lea     r8, aPcshellShellAu_1; "pcshell\\shell\\auth\\authux\\controlle"...
0x18006998f  mov     edx, 13Eh; void *
0x180069994  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180069999  nop
0x18006999a  lea     rcx, [rbp+37h+var_70]
0x18006999e  call    _lambda_00a03976a6977d1b53c6c79cf41425ac_____lambda_00a03976a6977d1b53c6c79cf41425ac_
0x1800699a3  nop
0x1800699a4  lea     rcx, [rbp+37h+length]
0x1800699a8  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x1800699ad  nop
0x1800699ae  lea     rcx, [rbp+37h+var_90]
0x1800699b2  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x1800699b7  nop
0x1800699b8  lea     rcx, [rbp+37h+var_88]
0x1800699bc  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x1800699c1  nop
0x1800699c2  lea     rcx, [rbp+37h+string]
0x1800699c6  call    ?InternalRelease@?$ComPtr@VSilentTSAutologonManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SilentTSAutologonManager>::InternalRelease(void)
0x1800699cb  nop
0x1800699cc  test    rsi, rsi
0x1800699cf  jz      short loc_1800699E1
0x1800699d1  mov     rax, [rsi]
0x1800699d4  mov     rcx, rsi
0x1800699d7  mov     rax, [rax+10h]
0x1800699db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800699e0  nop
0x1800699e1  jmp     loc_18006984B
0x1800699e6  mov     rcx, [rbp+3Fh]; this
0x1800699ea  mov     r9d, ebx; char *
0x1800699ed  lea     r8, aPcshellShellAu_1; "pcshell\\shell\\auth\\authux\\controlle"...
0x1800699f4  mov     edx, 131h; void *
0x1800699f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800699fe  nop
0x1800699ff  test    rsi, rsi
0x180069a02  jz      short loc_180069A14
0x180069a04  mov     rax, [rsi]
0x180069a07  mov     rcx, rsi
0x180069a0a  mov     rax, [rax+10h]
0x180069a0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069a13  nop
0x180069a14  jmp     loc_18006984B
0x180069a19  mov     edx, 493E0h
0x180069a1e  lea     rcx, [r14+68h]
0x180069a22  call    ?wait@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA_NKH@Z
0x180069a27  test    al, al
0x180069a29  jnz     short loc_180069AA9
0x180069a2b  call    cs:__imp_GetLastError
0x180069a31  mov     ebx, eax
0x180069a33  test    eax, eax
0x180069a35  jle     short loc_180069A40
0x180069a37  movzx   ebx, ax
0x180069a3a  or      ebx, 80070000h
0x180069a40  test    ebx, ebx
0x180069a42  jns     short loc_180069AA9
0x180069a44  mov     rcx, [rbp+3Fh]; this
0x180069a48  mov     r9d, ebx; char *
0x180069a4b  lea     r8, aPcshellShellAu_1; "pcshell\\shell\\auth\\authux\\controlle"...
0x180069a52  mov     edx, 145h; void *
0x180069a57  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180069a5c  nop
0x180069a5d  lea     rcx, [rbp+37h+var_70]
0x180069a61  call    _lambda_00a03976a6977d1b53c6c79cf41425ac_____lambda_00a03976a6977d1b53c6c79cf41425ac_
0x180069a66  nop
0x180069a67  lea     rcx, [rbp+37h+length]
0x180069a6b  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x180069a70  nop
0x180069a71  lea     rcx, [rbp+37h+var_90]
0x180069a75  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x180069a7a  nop
0x180069a7b  lea     rcx, [rbp+37h+var_88]
0x180069a7f  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x180069a84  nop
0x180069a85  lea     rcx, [rbp+37h+string]
0x180069a89  call    ?InternalRelease@?$ComPtr@VSilentTSAutologonManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SilentTSAutologonManager>::InternalRelease(void)
0x180069a8e  nop
0x180069a8f  test    rsi, rsi
0x180069a92  jz      short loc_180069AA4
0x180069a94  mov     rcx, [rsi]
0x180069a97  mov     rax, [rcx+10h]
0x180069a9b  mov     rcx, rsi
0x180069a9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069aa3  nop
0x180069aa4  jmp     loc_18006984B
0x180069aa9  lea     rdx, [r14+50h]
0x180069aad  lea     rcx, [rbp+37h+SRWLock]
0x180069ab1  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x180069ab6  lea     rcx, [r14+78h]
0x180069aba  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x180069abf  mov     rax, [r14+78h]
0x180069ac3  mov     [r12], rax
0x180069ac7  mov     rcx, [rbp+37h+SRWLock]; SRWLock
0x180069acb  test    rcx, rcx
0x180069ace  jz      short loc_180069AD7
0x180069ad0  call    cs:__imp_ReleaseSRWLockExclusive
0x180069ad6  nop
0x180069ad7  lea     rcx, [rbp+37h+var_70]
0x180069adb  call    _lambda_00a03976a6977d1b53c6c79cf41425ac_____lambda_00a03976a6977d1b53c6c79cf41425ac_
0x180069ae0  nop
0x180069ae1  lea     rcx, [rbp+37h+length]
0x180069ae5  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x180069aea  nop
0x180069aeb  lea     rcx, [rbp+37h+var_90]
0x180069aef  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x180069af4  nop
0x180069af5  lea     rcx, [rbp+37h+var_88]
0x180069af9  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x180069afe  nop
0x180069aff  lea     rcx, [rbp+37h+string]
0x180069b03  call    ?InternalRelease@?$ComPtr@VSilentTSAutologonManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SilentTSAutologonManager>::InternalRelease(void)
0x180069b08  nop
0x180069b09  test    rsi, rsi
0x180069b0c  jz      short loc_180069B1E
0x180069b0e  mov     rax, [rsi]
0x180069b11  mov     rcx, rsi
0x180069b14  mov     rax, [rax+10h]
0x180069b18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069b1d  nop
0x180069b1e  xor     eax, eax
0x180069b20  mov     rbx, [rsp+0C0h+arg_0]
0x180069b28  add     rsp, 90h
0x180069b2f  pop     r15
0x180069b31  pop     r14
0x180069b33  pop     r13
0x180069b35  pop     r12
0x180069b37  pop     rdi
0x180069b38  pop     rsi
0x180069b39  pop     rbp
0x180069b3a  retn
```
