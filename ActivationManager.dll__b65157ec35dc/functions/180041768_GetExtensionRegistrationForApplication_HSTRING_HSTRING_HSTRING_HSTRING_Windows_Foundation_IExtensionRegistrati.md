# GetExtensionRegistrationForApplication(HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ * *,Windows::Foundation::IExtensionRegistration * *)

- ea: `0x180041768`
- end: `0x180041c98`
- name: `?GetExtensionRegistrationForApplication@@YAJPEAUHSTRING__@@00PEAPEAU1@PEAPEAUIExtensionRegistration@Foundation@Windows@@@Z`
- size: `1328`
- prototype: `int(HSTRING, HSTRING, HSTRING, HSTRING *, struct Windows::Foundation::IExtensionRegistration **)`
- caller_count: `3`
- callee_count: `31`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18006b040`
- `0x18006bcf8`
- `0x180071540`

## callees

- `0x18000b5c0`
- `0x180010ab0`
- `0x180011328`
- `0x1800263e4`
- `0x18002efd4`
- `0x180041768`
- `0x1800445ac`
- `0x1800462d4`
- `0x18004670c`
- `0x180048edc`
- `0x18004ab34`
- `0x18004c9e8`
- `0x18004f77c`
- `0x18005ae90`
- `0x180067e64`
- `0x1800707b8`
- `0x180071bec`
- `0x180073504`
- `0x18007e3cc`
- `0x18007e4d8`
- `0x18007e59c`
- `0x18007e600`
- `0x18007e624`
- `0x18007eb7c`
- `0x18007ebac`
- `0x18007ec10`
- `0x18007ec78`
- `0x18007ed50`
- `0x18007ef70`
- `0x18007eff8`
- `0x18007f33c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041bba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041c36`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041bba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041c36`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800417ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800417bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800417cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800417ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800417bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800417cb`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18004186d`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18004186d`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x180041a61`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x180041a61`

## string_xrefs

- `0x180041a76`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\extensionhelpers.cpp`
- `0x180041b77`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\extensionhelpers.cpp`
- `0x180041b98`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\extensionhelpers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9 #try_helpers=1
__int64 __fastcall GetExtensionRegistrationForApplication(
        HSTRING a1,
        HSTRING a2,
        HSTRING a3,
        HSTRING *a4,
        struct Windows::Foundation::IExtensionRegistration **a5)
{
  const WCHAR *StringRawBuffer; // r15
  const WCHAR *v9; // r14
  __int64 v10; // rax
  __int64 v11; // rbx
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  _QWORD *v15; // rax
  volatile signed __int32 *v16; // rax
  void *v17; // rcx
  unsigned int v19; // eax
  unsigned int v20; // ebx
  __int64 v21; // rax
  struct Windows::Foundation::IExtensionRegistration *v22; // rax
  __int64 v23; // rax
  int v24; // eax
  HSTRING v25; // rax
  unsigned int v26; // [rsp+20h] [rbp-1C8h]
  __int64 v27; // [rsp+30h] [rbp-1B8h] BYREF
  UINT32 packageFamilyNameLength; // [rsp+38h] [rbp-1B0h] BYREF
  HSTRING string; // [rsp+40h] [rbp-1A8h] BYREF
  __int64 v30; // [rsp+48h] [rbp-1A0h] BYREF
  struct Windows::Foundation::IExtensionRegistration *v31; // [rsp+50h] [rbp-198h] BYREF
  PCWSTR psz1; // [rsp+58h] [rbp-190h] BYREF
  _BYTE v33[16]; // [rsp+60h] [rbp-188h] BYREF
  void **v34; // [rsp+70h] [rbp-178h] BYREF
  _QWORD v35[3]; // [rsp+78h] [rbp-170h] BYREF
  int v36; // [rsp+90h] [rbp-158h]
  __int64 v37; // [rsp+98h] [rbp-150h]
  char v38; // [rsp+A0h] [rbp-148h]
  LPVOID pv; // [rsp+A8h] [rbp-140h] BYREF
  _QWORD v40[4]; // [rsp+B0h] [rbp-138h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+D0h] [rbp-118h] BYREF
  int v42; // [rsp+F0h] [rbp-F8h]
  volatile signed __int32 *v43; // [rsp+108h] [rbp-E0h]
  WCHAR packageFamilyName[72]; // [rsp+110h] [rbp-D8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+0h]

  *a5 = 0;
  if ( a4 )
    *a4 = 0;
  psz1 = WindowsGetStringRawBuffer(a1, 0);
  StringRawBuffer = WindowsGetStringRawBuffer(a3, 0);
  v9 = WindowsGetStringRawBuffer(a2, 0);
  v27 = 0;
  v34 = &tip2::test_watcher<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>>::`vftable';
  v35[0] = 0;
  v35[1] = &v34;
  v35[2] = 0;
  v36 = 0;
  v37 = 0;
  v38 = 0;
  tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>,>(&pv);
  v10 = tip2::tip_test<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>>::ensure_data(&v27);
  tip2::test_data_control<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>>::test_data_control<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>>(
    &v30,
    v10);
  v11 = v30;
  *(_DWORD *)(v11 + 276) = GetProfile((unsigned int *)(v30 + 272));
  *(_BYTE *)(v11 + 280) = IsTempProfilePostBootReminderSet();
  *(_BYTE *)(v11 + 281) = IsAuditMode();
  *(_BYTE *)(v11 + 282) = GetSystemMetrics(67) != 0;
  *(_BYTE *)(v11 + 283) = IsRunningOnLocalSystem();
  v12 = std::wstring::wstring(v40, psz1);
  std::wstring::operator=(v11 + 352, v12);
  std::wstring::_Tidy_deallocate(v40);
  v13 = std::wstring::wstring(v40, StringRawBuffer);
  std::wstring::operator=(v11 + 320, v13);
  std::wstring::_Tidy_deallocate(v40);
  v14 = std::wstring::wstring(v40, v9);
  std::wstring::operator=(v11 + 288, v14);
  std::wstring::_Tidy_deallocate(v40);
  tip2::test_data_control<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>>::close(&v30);
  if ( v27 && (*(_QWORD *)(v27 + 248) || (*(_DWORD *)(v27 + 72) & 0x100) != 0) )
    wil::com_ptr_t<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>,wil::err_returncode_policy>::reset(&v27);
  v15 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>>::ensure_data(&v27);
  tip2::details::shared_data<0,0,0>::start(*v15 + 8LL, v40);
  hstringHeader.Reserved.Reserved1 = &tip2::test_watcher<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>>::`vftable';
  wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(
    (wil::details::ThreadFailureCallbackHolder *)&hstringHeader.Reserved.Reserved2[8],
    (struct wil::details::IFailureCallback *)&hstringHeader,
    0,
    1);
  v16 = (volatile signed __int32 *)v27;
  v43 = (volatile signed __int32 *)v27;
  if ( v27 )
  {
    _InterlockedIncrement((volatile signed __int32 *)(v27 + 384));
    v16 = v43;
  }
  v17 = pv;
  pv = (LPVOID)v16;
  if ( v16 )
    _InterlockedIncrement(v16 + 96);
  if ( v17 )
    tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>::Release(v17);
  wil::details::ThreadFailureCallbackHolder::SetWatching((wil::details::ThreadFailureCallbackHolder *)v35, v42 != 0);
  tip2::test_watcher<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>>::~test_watcher<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>>(&hstringHeader);
  if ( GetExtensionRegistrationWithLaunchContractOptimization(psz1, v9, StringRawBuffer, a4, a5) < 0 )
  {
    packageFamilyNameLength = 65;
    v19 = PackageFamilyNameFromFullName(v9, &packageFamilyNameLength, packageFamilyName);
    if ( v19 )
    {
      v20 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0xE5,
              (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\extensionhelpers.cpp",
              (const char *)v19,
              v26);
      tip2::test_data_control<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>>::~test_data_control<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>>(&v30);
      tip2::test_watcher<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>>::~test_watcher<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>>(&v34);
      wil::com_ptr_t<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>,wil::err_returncode_policy>(&v27);
      return v20;
    }
    else
    {
      v31 = 0;
      string = 0;
      ExtensionDatabaseProvider::ExtensionDatabaseProvider((ExtensionDatabaseProvider *)v33);
      v21 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, packageFamilyName);
      v40[0] = &psz1;
      v40[1] = &string;
      v40[2] = &v31;
      ExtensionDatabaseProvider::ForEachExtension__lambda_e24eda09eb2914c928cc254bae637d2f___(
        v33,
        a3,
        *(_QWORD *)(v21 + 24),
        v40);
      v22 = v31;
      if ( v31 )
      {
        v31 = 0;
        *a5 = v22;
        if ( a4 )
        {
          v25 = string;
          string = 0;
          *a4 = v25;
        }
        if ( v27 )
          tip2::details::shared_data<0,0,0>::complete_without_lock(v27 + 8);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v33);
        WindowsDeleteString(string);
        string = 0;
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v31);
        tip2::test_data_control<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>>::~test_data_control<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>>(&v30);
        tip2::test_watcher<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>>::~test_watcher<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>>(&v34);
        wil::com_ptr_t<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>,wil::err_returncode_policy>(&v27);
        return 0;
      }
      else
      {
        v23 = tip2::tip_test<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>>::ensure_data(&v27);
        tip2::test_data_control<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>>::test_data_control<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>>(
          v40,
          v23);
        *(_BYTE *)(v40[0] + 284LL) = 1;
        tip2::test_data_control<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>>::~test_data_control<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>>(v40);
        v24 = SetPackageStatusMachineRegisterOnRepair(a2);
        if ( v24 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0xFB,
            (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\extensionhelpers.cpp",
            (const char *)(unsigned int)v24,
            v26);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xFC,
          (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\extensionhelpers.cpp",
          (const char *)0x80270254LL,
          v26);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v33);
        WindowsDeleteString(string);
        string = 0;
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v31);
        tip2::test_data_control<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>>::~test_data_control<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>>(&v30);
        tip2::test_watcher<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>>::~test_watcher<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>>(&v34);
        wil::com_ptr_t<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>,wil::err_returncode_policy>(&v27);
        return 2150040148LL;
      }
    }
  }
  else
  {
    if ( v27 )
      tip2::details::shared_data<0,0,0>::complete_without_lock(v27 + 8);
    tip2::test_data_control<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>>::~test_data_control<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>>(&v30);
    tip2::test_watcher<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>>::~test_watcher<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>>(&v34);
    wil::com_ptr_t<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>,wil::err_returncode_policy>(&v27);
    return 0;
  }
}

```

## disassembly

```asm
0x180041768  push    rbx
0x18004176a  push    rsi
0x18004176b  push    rdi
0x18004176c  push    r12
0x18004176e  push    r13
0x180041770  push    r14
0x180041772  push    r15
0x180041774  sub     rsp, 1B0h
0x18004177b  mov     rax, cs:__security_cookie
0x180041782  xor     rax, rsp
0x180041785  mov     [rsp+1E8h+var_48], rax
0x18004178d  mov     rdi, r9
0x180041790  mov     r13, r8
0x180041793  mov     r12, rdx
0x180041796  mov     rsi, [rsp+1E8h+arg_20]
0x18004179e  xor     ebx, ebx
0x1800417a0  mov     [rsi], rbx
0x1800417a3  test    r9, r9
0x1800417a6  jz      short loc_1800417AB
0x1800417a8  mov     [r9], rbx
0x1800417ab  xor     edx, edx; length
0x1800417ad  call    cs:__imp_WindowsGetStringRawBuffer
0x1800417b3  mov     [rsp+1E8h+psz1], rax
0x1800417b8  xor     edx, edx; length
0x1800417ba  mov     rcx, r13; string
0x1800417bd  call    cs:__imp_WindowsGetStringRawBuffer
0x1800417c3  mov     r15, rax
0x1800417c6  xor     edx, edx; length
0x1800417c8  mov     rcx, r12; string
0x1800417cb  call    cs:__imp_WindowsGetStringRawBuffer
0x1800417d1  mov     r14, rax
0x1800417d4  mov     [rsp+1E8h+var_1B8], rbx
0x1800417d9  lea     rax, ??_7?$test_watcher@V?$merged_data@U_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest@@U1@@details@tip2@@@tip2@@6B@; const tip2::test_watcher<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>>::`vftable'
0x1800417e0  mov     [rsp+1E8h+var_178], rax
0x1800417e5  mov     [rsp+1E8h+var_170], rbx
0x1800417ea  lea     rax, [rsp+1E8h+var_178]
0x1800417ef  mov     [rsp+1E8h+var_168], rax
0x1800417f7  mov     [rsp+1E8h+var_160], rbx
0x1800417ff  mov     [rsp+1E8h+var_158], ebx
0x180041806  mov     [rsp+1E8h+var_150], rbx
0x18004180e  mov     [rsp+1E8h+var_148], bl
0x180041815  lea     rcx, [rsp+1E8h+pv]
0x18004181d  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest@@U1@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>,>(void)
0x180041822  nop
0x180041823  lea     rcx, [rsp+1E8h+var_1B8]
0x180041828  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>>::ensure_data(void)
0x18004182d  mov     rdx, rax
0x180041830  lea     rcx, [rsp+1E8h+var_1A0]
0x180041835  call    ??0?$test_data_control@V?$merged_data@U_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest@@U1@@details@tip2@@@tip2@@IEAA@AEBV?$com_ptr_t@V?$merged_data@U_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@@Z; tip2::test_data_control<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>>::test_data_control<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>>(wil::com_ptr_t<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>,wil::err_returncode_policy> const &)
0x18004183a  nop
0x18004183b  mov     rbx, [rsp+1E8h+var_1A0]
0x180041840  lea     rcx, [rbx+110h]; unsigned int *
0x180041847  call    ?GetProfile@@YAJAEAK@Z; GetProfile(ulong &)
0x18004184c  mov     [rbx+114h], eax
0x180041852  call    ?IsTempProfilePostBootReminderSet@@YA_NXZ; IsTempProfilePostBootReminderSet(void)
0x180041857  mov     [rbx+118h], al
0x18004185d  call    ?IsAuditMode@@YA_NXZ; IsAuditMode(void)
0x180041862  mov     [rbx+119h], al
0x180041868  mov     ecx, 43h ; 'C'; nIndex
0x18004186d  call    cs:__imp_GetSystemMetrics
0x180041873  test    eax, eax
0x180041875  setnz   al
0x180041878  mov     [rbx+11Ah], al
0x18004187e  call    ?IsRunningOnLocalSystem@@YA_NXZ; IsRunningOnLocalSystem(void)
0x180041883  mov     [rbx+11Bh], al
0x180041889  mov     rdx, [rsp+1E8h+psz1]
0x18004188e  lea     rcx, [rsp+1E8h+var_138]
0x180041896  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004189b  lea     rcx, [rbx+160h]
0x1800418a2  mov     rdx, rax
0x1800418a5  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800418aa  lea     rcx, [rsp+1E8h+var_138]
0x1800418b2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800418b7  mov     rdx, r15
0x1800418ba  lea     rcx, [rsp+1E8h+var_138]
0x1800418c2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800418c7  lea     rcx, [rbx+140h]
0x1800418ce  mov     rdx, rax
0x1800418d1  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800418d6  lea     rcx, [rsp+1E8h+var_138]
0x1800418de  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800418e3  mov     rdx, r14
0x1800418e6  lea     rcx, [rsp+1E8h+var_138]
0x1800418ee  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800418f3  lea     rcx, [rbx+120h]
0x1800418fa  mov     rdx, rax
0x1800418fd  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180041902  lea     rcx, [rsp+1E8h+var_138]
0x18004190a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004190f  lea     rcx, [rsp+1E8h+var_1A0]
0x180041914  call    ?close@?$test_data_control@V?$merged_data@U_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::test_data_control<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>>::close(void)
0x180041919  mov     rax, [rsp+1E8h+var_1B8]
0x18004191e  xor     ebx, ebx
0x180041920  test    rax, rax
0x180041923  jz      short loc_180041941
0x180041925  cmp     [rax+0F8h], rbx
0x18004192c  jnz     short loc_180041937
0x18004192e  test    dword ptr [rax+48h], 100h
0x180041935  jz      short loc_180041941
0x180041937  lea     rcx, [rsp+1E8h+var_1B8]
0x18004193c  call    ?reset@?$com_ptr_t@V?$merged_data@U_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>,wil::err_returncode_policy>::reset(void)
0x180041941  lea     rcx, [rsp+1E8h+var_1B8]
0x180041946  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>>::ensure_data(void)
0x18004194b  mov     rcx, [rax]
0x18004194e  add     rcx, 8
0x180041952  lea     rdx, [rsp+1E8h+var_138]
0x18004195a  call    ?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,0>::start(void)
0x18004195f  lea     rax, ??_7?$test_watcher@V?$merged_data@U_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest@@U1@@details@tip2@@@tip2@@6B@; const tip2::test_watcher<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>>::`vftable'
0x180041966  mov     qword ptr [rsp+1E8h+hstringHeader.Reserved], rax
0x18004196e  mov     r9b, 1; bool
0x180041971  xor     r8d, r8d; struct wil::CallContextInfo *
0x180041974  lea     rdx, [rsp+1E8h+hstringHeader]; struct wil::details::IFailureCallback *
0x18004197c  lea     rcx, [rsp+1E8h+hstringHeader.Reserved+8]; this
0x180041984  call    ??0ThreadFailureCallbackHolder@details@wil@@QEAA@PEAUIFailureCallback@12@PEAUCallContextInfo@2@_N@Z; wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(wil::details::IFailureCallback *,wil::CallContextInfo *,bool)
0x180041989  mov     rax, [rsp+1E8h+var_1B8]
0x18004198e  mov     [rsp+1E8h+var_E0], rax
0x180041996  test    rax, rax
0x180041999  jz      short loc_1800419AA
0x18004199b  lock inc dword ptr [rax+180h]
0x1800419a2  mov     rax, [rsp+1E8h+var_E0]
0x1800419aa  mov     rcx, [rsp+1E8h+pv]; pv
0x1800419b2  mov     [rsp+1E8h+pv], rax
0x1800419ba  test    rax, rax
0x1800419bd  jz      short loc_1800419C6
0x1800419bf  lock inc dword ptr [rax+180h]
0x1800419c6  test    rcx, rcx
0x1800419c9  jz      short loc_1800419D0
0x1800419cb  call    ?Release@?$merged_data@U_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>::Release(void)
0x1800419d0  cmp     [rsp+1E8h+var_F8], ebx
0x1800419d7  setnz   dl; bool
0x1800419da  lea     rcx, [rsp+1E8h+var_170]; this
0x1800419df  call    ?SetWatching@ThreadFailureCallbackHolder@details@wil@@QEAAX_N@Z; wil::details::ThreadFailureCallbackHolder::SetWatching(bool)
0x1800419e4  nop
0x1800419e5  lea     rcx, [rsp+1E8h+hstringHeader]
0x1800419ed  call    ??1?$test_watcher@V?$merged_data@U_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>>::~test_watcher<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>>(void)
0x1800419f2  mov     qword ptr [rsp+1E8h+var_1C8], rsi; int
0x1800419f7  mov     r9, rdi; HSTRING *
0x1800419fa  mov     r8, r15; lpString1
0x1800419fd  mov     rdx, r14; sourceString
0x180041a00  mov     rcx, [rsp+1E8h+psz1]; psz1
0x180041a05  call    ?GetExtensionRegistrationWithLaunchContractOptimization@@YAJPEBG00PEAPEAUHSTRING__@@PEAPEAUIExtensionRegistration@Foundation@Windows@@@Z; GetExtensionRegistrationWithLaunchContractOptimization(ushort const *,ushort const *,ushort const *,HSTRING__ * *,Windows::Foundation::IExtensionRegistration * *)
0x180041a0a  test    eax, eax
0x180041a0c  js      short loc_180041A49
0x180041a0e  mov     rcx, [rsp+1E8h+var_1B8]
0x180041a13  test    rcx, rcx
0x180041a16  jz      short loc_180041A22
0x180041a18  add     rcx, 8
0x180041a1c  call    ?complete_without_lock@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::complete_without_lock(void)
0x180041a21  nop
0x180041a22  lea     rcx, [rsp+1E8h+var_1A0]
0x180041a27  call    ??1?$test_data_control@V?$merged_data@U_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>>::~test_data_control<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>>(void)
0x180041a2c  nop
0x180041a2d  lea     rcx, [rsp+1E8h+var_178]
0x180041a32  call    ??1?$test_watcher@V?$merged_data@U_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>>::~test_watcher<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>>(void)
0x180041a37  nop
0x180041a38  lea     rcx, [rsp+1E8h+var_1B8]
0x180041a3d  call    ??1?$com_ptr_t@V?$merged_data@U_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>,wil::err_returncode_policy>(void)
0x180041a42  xor     eax, eax
0x180041a44  jmp     loc_180041C74
0x180041a49  mov     [rsp+1E8h+packageFamilyNameLength], 41h ; 'A'
0x180041a51  lea     r8, [rsp+1E8h+packageFamilyName]; packageFamilyName
0x180041a59  lea     rdx, [rsp+1E8h+packageFamilyNameLength]; packageFamilyNameLength
0x180041a5e  mov     rcx, r14; packageFullName
0x180041a61  call    cs:__imp_PackageFamilyNameFromFullName
0x180041a67  test    eax, eax
0x180041a69  jz      short loc_180041AB0
0x180041a6b  mov     rcx, [rsp+1E8h]; this
0x180041a73  mov     r9d, eax; char *
0x180041a76  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180041a7d  mov     edx, 0E5h; void *
0x180041a82  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180041a87  mov     ebx, eax
0x180041a89  lea     rcx, [rsp+1E8h+var_1A0]
0x180041a8e  call    ??1?$test_data_control@V?$merged_data@U_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>>::~test_data_control<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>>(void)
0x180041a93  nop
0x180041a94  lea     rcx, [rsp+1E8h+var_178]
0x180041a99  call    ??1?$test_watcher@V?$merged_data@U_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>>::~test_watcher<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>>(void)
0x180041a9e  nop
0x180041a9f  lea     rcx, [rsp+1E8h+var_1B8]
0x180041aa4  call    ??1?$com_ptr_t@V?$merged_data@U_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>,wil::err_returncode_policy>(void)
0x180041aa9  mov     eax, ebx
0x180041aab  jmp     loc_180041C74
0x180041ab0  mov     [rsp+1E8h+var_198], rbx
0x180041ab5  mov     [rsp+1E8h+string], rbx
0x180041aba  lea     rcx, [rsp+1E8h+var_188]; this
0x180041abf  call    ??0ExtensionDatabaseProvider@@QEAA@XZ; ExtensionDatabaseProvider::ExtensionDatabaseProvider(void)
0x180041ac4  nop
0x180041ac5  lea     rdx, [rsp+1E8h+packageFamilyName]; sourceString
0x180041acd  lea     rcx, [rsp+1E8h+hstringHeader]; hstringHeader
0x180041ad5  call    ??$?0$0EB@@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEAY0EB@G@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort (&)[65])
0x180041ada  nop
0x180041adb  lea     rcx, [rsp+1E8h+psz1]
0x180041ae0  mov     [rsp+1E8h+var_138], rcx
0x180041ae8  lea     rcx, [rsp+1E8h+string]
0x180041aed  mov     [rsp+1E8h+var_130], rcx
0x180041af5  lea     rcx, [rsp+1E8h+var_198]
0x180041afa  mov     [rsp+1E8h+var_128], rcx
0x180041b02  lea     r9, [rsp+1E8h+var_138]
0x180041b0a  mov     r8, [rax+18h]
0x180041b0e  mov     rdx, r13
0x180041b11  lea     rcx, [rsp+1E8h+var_188]
0x180041b16  call    ExtensionDatabaseProvider__ForEachExtension__lambda_e24eda09eb2914c928cc254bae637d2f___
0x180041b1b  nop
0x180041b1c  mov     rax, [rsp+1E8h+var_198]
0x180041b21  test    rax, rax
0x180041b24  jnz     loc_180041BF8
0x180041b2a  lea     rcx, [rsp+1E8h+var_1B8]
0x180041b2f  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>>::ensure_data(void)
0x180041b34  mov     rdx, rax
0x180041b37  lea     rcx, [rsp+1E8h+var_138]
0x180041b3f  call    ??0?$test_data_control@V?$merged_data@U_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest@@U1@@details@tip2@@@tip2@@IEAA@AEBV?$com_ptr_t@V?$merged_data@U_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@@Z; tip2::test_data_control<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>>::test_data_control<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>>(wil::com_ptr_t<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>,wil::err_returncode_policy> const &)
0x180041b44  mov     rax, [rsp+1E8h+var_138]
0x180041b4c  mov     byte ptr [rax+11Ch], 1
0x180041b53  lea     rcx, [rsp+1E8h+var_138]
0x180041b5b  call    ??1?$test_data_control@V?$merged_data@U_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>>::~test_data_control<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>>(void)
0x180041b60  mov     rcx, r12; HSTRING
0x180041b63  call    ?SetPackageStatusMachineRegisterOnRepair@@YAJPEAUHSTRING__@@@Z; SetPackageStatusMachineRegisterOnRepair(HSTRING__ *)
0x180041b68  mov     rcx, [rsp+1E8h]; this
0x180041b70  test    eax, eax
0x180041b72  jns     short loc_180041B88
0x180041b74  mov     r9d, eax; char *
0x180041b77  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180041b7e  mov     edx, 0FBh; void *
0x180041b83  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180041b88  mov     rcx, [rsp+1E8h]; this
0x180041b90  mov     ebx, 80270254h
0x180041b95  mov     r9d, ebx; char *
0x180041b98  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180041b9f  mov     edx, 0FCh; void *
0x180041ba4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041ba9  nop
0x180041baa  lea     rcx, [rsp+1E8h+var_188]
0x180041baf  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180041bb4  nop
0x180041bb5  mov     rcx, [rsp+1E8h+string]; string
0x180041bba  call    cs:__imp_WindowsDeleteString
0x180041bc0  mov     [rsp+1E8h+string], 0
0x180041bc9  lea     rcx, [rsp+1E8h+var_198]
0x180041bce  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180041bd3  nop
0x180041bd4  lea     rcx, [rsp+1E8h+var_1A0]
0x180041bd9  call    ??1?$test_data_control@V?$merged_data@U_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>>::~test_data_control<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>>(void)
0x180041bde  nop
0x180041bdf  lea     rcx, [rsp+1E8h+var_178]
0x180041be4  call    ??1?$test_watcher@V?$merged_data@U_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>>::~test_watcher<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>>(void)
0x180041be9  nop
0x180041bea  lea     rcx, [rsp+1E8h+var_1B8]
0x180041bef  call    ??1?$com_ptr_t@V?$merged_data@U_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>,wil::err_returncode_policy>(void)
0x180041bf4  mov     eax, ebx
0x180041bf6  jmp     short loc_180041C74
0x180041bf8  mov     [rsp+1E8h+var_198], rbx
0x180041bfd  mov     [rsi], rax
0x180041c00  test    rdi, rdi
0x180041c03  jz      short loc_180041C12
0x180041c05  mov     rax, [rsp+1E8h+string]
0x180041c0a  mov     [rsp+1E8h+string], rbx
0x180041c0f  mov     [rdi], rax
0x180041c12  mov     rcx, [rsp+1E8h+var_1B8]
0x180041c17  test    rcx, rcx
0x180041c1a  jz      short loc_180041C26
0x180041c1c  add     rcx, 8
0x180041c20  call    ?complete_without_lock@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::complete_without_lock(void)
0x180041c25  nop
0x180041c26  lea     rcx, [rsp+1E8h+var_188]
0x180041c2b  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180041c30  nop
0x180041c31  mov     rcx, [rsp+1E8h+string]; string
0x180041c36  call    cs:__imp_WindowsDeleteString
0x180041c3c  mov     [rsp+1E8h+string], rbx
0x180041c41  lea     rcx, [rsp+1E8h+var_198]
0x180041c46  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180041c4b  nop
0x180041c4c  lea     rcx, [rsp+1E8h+var_1A0]
0x180041c51  call    ??1?$test_data_control@V?$merged_data@U_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>>::~test_data_control<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>>(void)
0x180041c56  nop
0x180041c57  lea     rcx, [rsp+1E8h+var_178]
0x180041c5c  call    ??1?$test_watcher@V?$merged_data@U_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>>::~test_watcher<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>>(void)
0x180041c61  nop
0x180041c62  lea     rcx, [rsp+1E8h+var_1B8]
0x180041c67  call    ??1?$com_ptr_t@V?$merged_data@U_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest,_tip_SetMachineRegisterRepairOnExtensionActivationFailurePath2TipTest>,wil::err_returncode_policy>(void)
0x180041c6c  xor     eax, eax
0x180041c6e  jmp     short loc_180041C74
0x180041c70  mov     eax, [rsp+1E8h+packageFamilyNameLength]
0x180041c74  mov     rcx, [rsp+1E8h+var_48]
0x180041c7c  xor     rcx, rsp; StackCookie
0x180041c7f  call    __security_check_cookie
0x180041c84  add     rsp, 1B0h
0x180041c8b  pop     r15
0x180041c8d  pop     r14
0x180041c8f  pop     r13
0x180041c91  pop     r12
0x180041c93  pop     rdi
0x180041c94  pop     rsi
0x180041c95  pop     rbx
0x180041c96  retn
```
