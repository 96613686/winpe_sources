# AccessibilityBackupRestoreHandler::RestoreAnimationEffectsSettings(void)

- ea: `0x1800e678c`
- end: `0x1800e692e`
- name: `?RestoreAnimationEffectsSettings@AccessibilityBackupRestoreHandler@@AEAAXXZ`
- size: `418`
- prototype: `void __fastcall(AccessibilityBackupRestoreHandler *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800e6490`

## callees

- `0x18000c6e0`
- `0x1800162a4`
- `0x18001d234`
- `0x18008cedc`
- `0x1800e584c`
- `0x1800e5ce8`
- `0x1800e6714`
- `0x1800e678c`
- `0x1800e787c`
- `0x18012d010`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x1800e682b`
- `KERNEL32!CompareStringOrdinal` at `0x1800e682b`
- `ADVAPI32!RegGetValueW` at `0x1800e67ec`
- `ADVAPI32!RegGetValueW` at `0x1800e67ec`

## string_xrefs

- `0x1800e68fc`: `pcshell\shell\cloudrestorelauncher\cloudbackuprestore\accessibilitybackuprestorehandler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall AccessibilityBackupRestoreHandler::RestoreAnimationEffectsSettings(LPCWSTR *this)
{
  int ValueW; // eax
  const char *v3; // r9
  bool v4; // sf
  int v5; // eax
  bool v6; // di
  __int64 v7; // rdx
  unsigned int v8; // eax
  const char *v9; // r9
  DWORD v10; // [rsp+40h] [rbp-68h] BYREF
  _BYTE v11[8]; // [rsp+48h] [rbp-60h] BYREF
  __int64 v12; // [rsp+50h] [rbp-58h] BYREF
  int v13; // [rsp+58h] [rbp-50h] BYREF
  __int128 v14; // [rsp+60h] [rbp-48h]
  WCHAR String1[16]; // [rsp+70h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  v10 = 32;
  ValueW = RegGetValueW(HKEY_CURRENT_USER, this[50], this[51], 2u, 0, String1, &v10);
  v4 = ValueW < 0;
  if ( ValueW )
  {
    String1[0] = 0;
    v4 = ValueW < 0;
    if ( ValueW > 0 )
    {
      ValueW = (unsigned __int16)ValueW | 0x80070000;
      v4 = ValueW < 0;
    }
  }
  if ( v4 )
  {
    if ( ValueW == -2147024894 )
    {
      *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_AccessibilitySettingsRestoreTipTest,_tip_AccessibilitySettingsRestoreTipTest>>::data(
                              this + 43,
                              v11)
               + 273LL) = 1;
      tip2::test_data_control<tip2::details::merged_data<_tip_AccessibilitySettingsRestoreTipTest,_tip_AccessibilitySettingsRestoreTipTest>>::~test_data_control<tip2::details::merged_data<_tip_AccessibilitySettingsRestoreTipTest,_tip_AccessibilitySettingsRestoreTipTest>>(v11);
    }
    else
    {
      wil::details::in1diag3::_Log_GetLastError(
        retaddr,
        (void *)0x22F,
        (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\accessibilitybackuprestorehandler.cpp",
        v3);
    }
  }
  else
  {
    v5 = CompareStringOrdinal(String1, -1, L"0", -1, 1);
    try
    {
      v6 = v5 != 2;
      winrt::Windows::UI::ViewManagement::Core::UISettingsController::RequestDefaultAsync();
      winrt::impl::wait_get<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::UI::ViewManagement::Core::UISettingsController>>((winrt *)&v12);
      v13 = 0;
      v14 = 0;
      LOBYTE(v7) = v6;
      v8 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v12 + 56LL))(v12, v7);
      winrt::check_hresult(&v10, v8, &v13);
      _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)&v12);
      _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)v11);
      *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_AccessibilitySettingsRestoreTipTest,_tip_AccessibilitySettingsRestoreTipTest>>::data(
                              this + 43,
                              v11)
               + 273LL) = 1;
      tip2::test_data_control<tip2::details::merged_data<_tip_AccessibilitySettingsRestoreTipTest,_tip_AccessibilitySettingsRestoreTipTest>>::~test_data_control<tip2::details::merged_data<_tip_AccessibilitySettingsRestoreTipTest,_tip_AccessibilitySettingsRestoreTipTest>>(v11);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x227,
        (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\accessibilitybackuprestorehandler.cpp",
        v9);
    }
  }
}

```

## disassembly

```asm
0x1800e678c  mov     r11, rsp
0x1800e678f  mov     [r11+10h], rbx
0x1800e6793  push    rdi
0x1800e6794  sub     rsp, 0A0h
0x1800e679b  mov     rax, cs:__security_cookie
0x1800e67a2  xor     rax, rsp
0x1800e67a5  mov     [rsp+0A8h+var_18], rax
0x1800e67ad  mov     rbx, rcx
0x1800e67b0  mov     [rsp+0A8h+var_68], 20h ; ' '
0x1800e67b8  lea     rax, [r11-68h]
0x1800e67bc  mov     [r11-78h], rax
0x1800e67c0  lea     rax, [r11-38h]
0x1800e67c4  mov     [r11-80h], rax
0x1800e67c8  mov     [rsp+0A8h+pdwType], 0; pdwType
0x1800e67d1  mov     r9d, 2; dwFlags
0x1800e67d7  mov     r8, [rcx+198h]; lpValue
0x1800e67de  mov     rdx, [rcx+190h]; lpSubKey
0x1800e67e5  mov     rcx, 0FFFFFFFF80000001h; hkey
0x1800e67ec  call    cs:__imp_RegGetValueW
0x1800e67f2  test    eax, eax
0x1800e67f4  jz      short loc_1800E680B
0x1800e67f6  xor     ecx, ecx
0x1800e67f8  mov     [rsp+0A8h+String1], cx
0x1800e67fd  test    eax, eax
0x1800e67ff  jle     short loc_1800E680B
0x1800e6801  movzx   eax, ax
0x1800e6804  or      eax, 80070000h
0x1800e6809  test    eax, eax
0x1800e680b  js      loc_1800E68C6
0x1800e6811  mov     dword ptr [rsp+0A8h+pdwType], 1; bIgnoreCase
0x1800e6819  or      edx, 0FFFFFFFFh; cchCount1
0x1800e681c  mov     r9d, edx; cchCount2
0x1800e681f  lea     r8, a0; "0"
0x1800e6826  lea     rcx, [rsp+0A8h+String1]; lpString1
0x1800e682b  call    cs:__imp_CompareStringOrdinal
0x1800e6831  nop
0x1800e6832  cmp     eax, 2
0x1800e6835  setnz   dil
0x1800e6839  lea     rcx, [rsp+0A8h+var_60]
0x1800e683e  call    ?RequestDefaultAsync@UISettingsController@Core@ViewManagement@UI@Windows@winrt@@SA@XZ; winrt::Windows::UI::ViewManagement::Core::UISettingsController::RequestDefaultAsync(void)
0x1800e6843  nop
0x1800e6844  mov     rdx, rax
0x1800e6847  lea     rcx, [rsp+0A8h+var_58]; this
0x1800e684c  call    ??$wait_get@U?$IAsyncOperation@UUISettingsController@Core@ViewManagement@UI@Windows@winrt@@@Foundation@Windows@winrt@@@impl@winrt@@YA?A_PAEBU?$IAsyncOperation@UUISettingsController@Core@ViewManagement@UI@Windows@winrt@@@Foundation@Windows@1@@Z
0x1800e6851  nop
0x1800e6852  mov     rcx, [rsp+0A8h+var_58]
0x1800e6857  mov     [rsp+0A8h+var_50], 0
0x1800e685f  xorps   xmm0, xmm0
0x1800e6862  movdqu  [rsp+0A8h+var_48], xmm0
0x1800e6868  mov     rax, [rcx]
0x1800e686b  mov     dl, dil
0x1800e686e  mov     rax, [rax+38h]
0x1800e6872  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e6877  lea     r8, [rsp+0A8h+var_50]
0x1800e687c  mov     edx, eax
0x1800e687e  lea     rcx, [rsp+0A8h+var_68]
0x1800e6883  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800e6888  nop
0x1800e6889  lea     rcx, [rsp+0A8h+var_58]; this
0x1800e688e  call    ??1_lambda_12ef4a55c56a96ec7ad58335194b061f_@@QEAA@XZ; _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_(void)
0x1800e6893  nop
0x1800e6894  lea     rcx, [rsp+0A8h+var_60]; this
0x1800e6899  call    ??1_lambda_12ef4a55c56a96ec7ad58335194b061f_@@QEAA@XZ; _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_(void)
0x1800e689e  lea     rcx, [rbx+158h]
0x1800e68a5  lea     rdx, [rsp+0A8h+var_60]
0x1800e68aa  call    ?data@?$tip_test@V?$merged_data@U_tip_AccessibilitySettingsRestoreTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_AccessibilitySettingsRestoreTipTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_AccessibilitySettingsRestoreTipTest,_tip_AccessibilitySettingsRestoreTipTest>>::data(void)
0x1800e68af  mov     rcx, [rax]
0x1800e68b2  mov     byte ptr [rcx+111h], 1
0x1800e68b9  lea     rcx, [rsp+0A8h+var_60]
0x1800e68be  call    ??1?$test_data_control@V?$merged_data@U_tip_AccessibilitySettingsRestoreTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_AccessibilitySettingsRestoreTipTest,_tip_AccessibilitySettingsRestoreTipTest>>::~test_data_control<tip2::details::merged_data<_tip_AccessibilitySettingsRestoreTipTest,_tip_AccessibilitySettingsRestoreTipTest>>(void)
0x1800e68c3  nop
0x1800e68c4  jmp     short loc_1800E690D
0x1800e68c6  cmp     eax, 80070002h
0x1800e68cb  jnz     short loc_1800E68F4
0x1800e68cd  lea     rcx, [rbx+158h]
0x1800e68d4  lea     rdx, [rsp+0A8h+var_60]
0x1800e68d9  call    ?data@?$tip_test@V?$merged_data@U_tip_AccessibilitySettingsRestoreTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_AccessibilitySettingsRestoreTipTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_AccessibilitySettingsRestoreTipTest,_tip_AccessibilitySettingsRestoreTipTest>>::data(void)
0x1800e68de  mov     rcx, [rax]
0x1800e68e1  mov     byte ptr [rcx+111h], 1
0x1800e68e8  lea     rcx, [rsp+0A8h+var_60]
0x1800e68ed  call    ??1?$test_data_control@V?$merged_data@U_tip_AccessibilitySettingsRestoreTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_AccessibilitySettingsRestoreTipTest,_tip_AccessibilitySettingsRestoreTipTest>>::~test_data_control<tip2::details::merged_data<_tip_AccessibilitySettingsRestoreTipTest,_tip_AccessibilitySettingsRestoreTipTest>>(void)
0x1800e68f2  jmp     short loc_1800E690D
0x1800e68f4  mov     rcx, [rsp+0A8h]; this
0x1800e68fc  lea     r8, aPcshellShellCl_32; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x1800e6903  mov     edx, 22Fh; void *
0x1800e6908  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x1800e690d  mov     rcx, [rsp+0A8h+var_18]
0x1800e6915  xor     rcx, rsp; StackCookie
0x1800e6918  call    __security_check_cookie
0x1800e691d  mov     rbx, [rsp+0A8h+arg_8]
0x1800e6925  add     rsp, 0A0h
0x1800e692c  pop     rdi
0x1800e692d  retn
```
