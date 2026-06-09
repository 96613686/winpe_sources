# SystemSettings::WorkAccess::ConnectWorkSchoolAccountSetting::ShowLicenseUpgradeConfirmation(_GUID const &,HWND__ *)

- ea: `0x180027bd8`
- end: `0x18002818f`
- name: `?ShowLicenseUpgradeConfirmation@ConnectWorkSchoolAccountSetting@WorkAccess@SystemSettings@@AEAAJAEBU_GUID@@PEAUHWND__@@@Z`
- size: `1463`
- prototype: `__int64 __fastcall(SystemSettings::WorkAccess::ConnectWorkSchoolAccountSetting *__hidden this, const struct _GUID *, HWND)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180023db4`

## callees

- `0x180002a60`
- `0x180005490`
- `0x1800096ec`
- `0x18000c970`
- `0x18001197c`
- `0x18001c4d0`
- `0x180020584`
- `0x1800208f8`
- `0x180021048`
- `0x1800229d4`
- `0x180027bd8`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180027c3e`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180027e32`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180027c3e`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180027e32`

## string_xrefs

- `0x180027e12`: `Windows.UI.Popups.UICommand`
- `0x180027c57`: `shellcommon\shell\settingshandlers\workaccess\lib\connectworkschoolaccountsetting.cpp`
- `0x180027ddf`: `shellcommon\shell\settingshandlers\workaccess\lib\connectworkschoolaccountsetting.cpp`
- `0x180027e4b`: `shellcommon\shell\settingshandlers\workaccess\lib\connectworkschoolaccountsetting.cpp`
- `0x180027ea8`: `shellcommon\shell\settingshandlers\workaccess\lib\connectworkschoolaccountsetting.cpp`
- `0x180027f49`: `shellcommon\shell\settingshandlers\workaccess\lib\connectworkschoolaccountsetting.cpp`
- `0x180027ffd`: `shellcommon\shell\settingshandlers\workaccess\lib\connectworkschoolaccountsetting.cpp`
- `0x180028066`: `shellcommon\shell\settingshandlers\workaccess\lib\connectworkschoolaccountsetting.cpp`
- `0x1800280e5`: `shellcommon\shell\settingshandlers\workaccess\lib\connectworkschoolaccountsetting.cpp`
- `0x18002811b`: `shellcommon\shell\settingshandlers\workaccess\lib\connectworkschoolaccountsetting.cpp`
- `0x18002813e`: `shellcommon\shell\settingshandlers\workaccess\lib\connectworkschoolaccountsetting.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::WorkAccess::ConnectWorkSchoolAccountSetting::ShowLicenseUpgradeConfirmation(
        SystemSettings::WorkAccess::ConnectWorkSchoolAccountSetting *this,
        const struct _GUID *a2,
        HWND a3)
{
  int ActivationFactory; // eax
  unsigned __int16 v6; // r8
  int v7; // ebx
  int v8; // edi
  unsigned __int16 v9; // r8
  unsigned __int16 v10; // r8
  __int64 v11; // rsi
  __int64 (__fastcall *v12)(__int64, _QWORD, __int64, __int64 *); // rdi
  __int64 v13; // rbx
  __int64 v14; // rax
  int v15; // eax
  int v16; // eax
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, _QWORD, __int64 *); // rbx
  __int64 v19; // rax
  int v20; // eax
  unsigned __int64 v21; // r9
  __int64 v22; // rdx
  __int64 v23; // rdi
  __int64 (__fastcall *v24)(__int64, _QWORD); // rbx
  __int64 v25; // rax
  _QWORD *v26; // rax
  unsigned __int16 *v27; // rcx
  int v28; // eax
  __int64 v29; // rdx
  int v30; // eax
  __int64 v31; // rdx
  int v32; // eax
  int v34; // [rsp+20h] [rbp-E0h]
  int v35; // [rsp+20h] [rbp-E0h]
  int v36; // [rsp+20h] [rbp-E0h]
  int v37; // [rsp+20h] [rbp-E0h]
  unsigned __int16 v38; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v39; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v40; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v41; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v42; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v43; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v44; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v45[3]; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v46[3]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v47; // [rsp+98h] [rbp-68h] BYREF
  __int64 v48; // [rsp+A0h] [rbp-60h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v50; // [rsp+C0h] [rbp-40h]
  HSTRING_HEADER v51; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v52; // [rsp+E0h] [rbp-20h]
  _BYTE v53[32]; // [rsp+E8h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+38h]

  v48 = 0;
  v50 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.UI.Popups.MessageDialog",
    0x20u,
    0x1Fu);
  ActivationFactory = RoGetActivationFactory(v50, &GUID_2d161777_a66f_4ea5_bb87_793ffa4941f2, &v48);
  v7 = ActivationFactory;
  if ( ActivationFactory >= 0 )
  {
    memset(v45, 0, sizeof(v45));
    v7 = -2147467259;
    v8 = -2147467259;
    v42 = 0;
    v38 = 0;
    if ( Windows::Internal::ResourceString::FindAndSize(&_ImageBase, 0x71u, v6, (const unsigned __int16 **)&v42, &v38)
      && (v8 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                 v45,
                 v42,
                 v38),
          v8 >= 0) )
    {
      memset(v46, 0, sizeof(v46));
      v8 = -2147467259;
      v42 = 0;
      v38 = 0;
      if ( Windows::Internal::ResourceString::FindAndSize(&_ImageBase, 0x72u, v9, (const unsigned __int16 **)&v42, &v38) )
      {
        v8 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
               v46,
               v42,
               v38);
        if ( v8 >= 0 )
        {
          memset(&hstringHeader, 0, sizeof(hstringHeader));
          v42 = 0;
          v38 = 0;
          if ( !Windows::Internal::ResourceString::FindAndSize(
                  &_ImageBase,
                  0x73u,
                  v10,
                  (const unsigned __int16 **)&v42,
                  &v38)
            || (v7 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                       &hstringHeader,
                       v42,
                       v38),
                v7 < 0) )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x3C,
              (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\connectworkschoolaccountsetting.cpp",
              (const char *)(unsigned int)v7,
              v37);
            goto LABEL_43;
          }
          v39 = 0;
          v11 = v48;
          v12 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64 *))(*(_QWORD *)v48 + 56LL);
          v13 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v51, v45) + 24);
          v14 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v53, v46);
          v15 = v12(v11, *(_QWORD *)(v14 + 24), v13, &v39);
          v7 = v15;
          if ( v15 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x3F,
              (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\connectworkschoolaccountsetting.cpp",
              (const char *)(unsigned int)v15,
              v37);
LABEL_11:
            wil::com_ptr_t<IEnrollmentInfoEnumerator,wil::err_returncode_policy>::~com_ptr_t<IEnrollmentInfoEnumerator,wil::err_returncode_policy>(&v39);
LABEL_43:
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&hstringHeader);
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v46);
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v45);
            goto LABEL_47;
          }
          v41 = 0;
          v52 = 0;
          Microsoft::WRL::Wrappers::HStringReference::CreateReference(
            &v51,
            L"Windows.UI.Popups.UICommand",
            0x1Cu,
            0x1Bu);
          v16 = RoGetActivationFactory(v52, &GUID_a21a8189_26b0_4676_ae94_54041bc125e8, &v41);
          v7 = v16;
          if ( v16 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x44,
              (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\connectworkschoolaccountsetting.cpp",
              (const char *)(unsigned int)v16,
              v37);
LABEL_14:
            wil::com_ptr_t<IEnrollmentInfoEnumerator,wil::err_returncode_policy>::~com_ptr_t<IEnrollmentInfoEnumerator,wil::err_returncode_policy>(&v41);
            goto LABEL_11;
          }
          v40 = 0;
          v17 = v41;
          v18 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v41 + 48LL);
          v19 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v53, &hstringHeader);
          v20 = v18(v17, *(_QWORD *)(v19 + 24), &v40);
          v7 = v20;
          if ( v20 < 0 )
          {
            v21 = (unsigned int)v20;
            v22 = 71;
LABEL_17:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v22,
              (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\connectworkschoolaccountsetting.cpp",
              (const char *)v21,
              v37);
LABEL_18:
            wil::com_ptr_t<IEnrollmentInfoEnumerator,wil::err_returncode_policy>::~com_ptr_t<IEnrollmentInfoEnumerator,wil::err_returncode_policy>(&v40);
            goto LABEL_14;
          }
          v23 = v40;
          v24 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v40 + 72LL);
          v25 = lambda_aa8b5faaf664393c12820c0561572d67_::_lambda_aa8b5faaf664393c12820c0561572d67_(&v51, a2);
          v26 = (_QWORD *)Microsoft::WRL::Callback_Windows::UI::Popups::IUICommandInvokedHandler__lambda_aa8b5faaf664393c12820c0561572d67___(
                            &v42,
                            v25);
          v7 = v24(v23, *v26);
          v27 = v42;
          if ( v42 )
          {
            v42 = 0;
            (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v27 + 16LL))(v27);
          }
          if ( v7 < 0 )
          {
            v21 = (unsigned int)v7;
            v22 = 84;
            goto LABEL_17;
          }
          v43 = 0;
          v28 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v39 + 64LL))(v39, &v43);
          v7 = v28;
          if ( v28 < 0 )
          {
            v29 = 87;
LABEL_25:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v29,
              (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\connectworkschoolaccountsetting.cpp",
              (const char *)(unsigned int)v28,
              v37);
LABEL_26:
            wil::com_ptr_t<IEnrollmentInfoEnumerator,wil::err_returncode_policy>::~com_ptr_t<IEnrollmentInfoEnumerator,wil::err_returncode_policy>(&v43);
            goto LABEL_18;
          }
          v28 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v43 + 104LL))(v43, v40);
          v7 = v28;
          if ( v28 < 0 )
          {
            v29 = 88;
            goto LABEL_25;
          }
          v28 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v39 + 80LL))(v39, 0);
          v7 = v28;
          if ( v28 < 0 )
          {
            v29 = 91;
            goto LABEL_25;
          }
          v28 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v39 + 96LL))(v39, 0);
          v7 = v28;
          if ( v28 < 0 )
          {
            v29 = 92;
            goto LABEL_25;
          }
          v44 = 0;
          v30 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v39)(
                  v39,
                  &GUID_3e68d4bd_7135_4d10_8018_9fb6d9f33fa1,
                  &v44);
          v7 = v30;
          if ( v30 >= 0 )
          {
            v30 = (*(__int64 (__fastcall **)(__int64, HWND))(*(_QWORD *)v44 + 24LL))(v44, a3);
            v7 = v30;
            if ( v30 >= 0 )
            {
              v47 = 0;
              v32 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v39 + 120LL))(v39, &v47);
              v7 = v32;
              if ( v32 >= 0 )
              {
                wil::com_ptr_t<IEnrollmentInfoEnumerator,wil::err_returncode_policy>::~com_ptr_t<IEnrollmentInfoEnumerator,wil::err_returncode_policy>(&v47);
                wil::com_ptr_t<IEnrollmentInfoEnumerator,wil::err_returncode_policy>::~com_ptr_t<IEnrollmentInfoEnumerator,wil::err_returncode_policy>(&v44);
                wil::com_ptr_t<IEnrollmentInfoEnumerator,wil::err_returncode_policy>::~com_ptr_t<IEnrollmentInfoEnumerator,wil::err_returncode_policy>(&v43);
                wil::com_ptr_t<IEnrollmentInfoEnumerator,wil::err_returncode_policy>::~com_ptr_t<IEnrollmentInfoEnumerator,wil::err_returncode_policy>(&v40);
                wil::com_ptr_t<IEnrollmentInfoEnumerator,wil::err_returncode_policy>::~com_ptr_t<IEnrollmentInfoEnumerator,wil::err_returncode_policy>(&v41);
                wil::com_ptr_t<IEnrollmentInfoEnumerator,wil::err_returncode_policy>::~com_ptr_t<IEnrollmentInfoEnumerator,wil::err_returncode_policy>(&v39);
                Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&hstringHeader);
                Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v46);
                Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v45);
                v7 = 0;
                goto LABEL_47;
              }
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x68,
                (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\connectworkschoolaccountsetting.cpp",
                (const char *)(unsigned int)v32,
                v37);
              wil::com_ptr_t<IEnrollmentInfoEnumerator,wil::err_returncode_policy>::~com_ptr_t<IEnrollmentInfoEnumerator,wil::err_returncode_policy>(&v47);
              goto LABEL_36;
            }
            v31 = 100;
          }
          else
          {
            v31 = 99;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v31,
            (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\connectworkschoolaccountsetting.cpp",
            (const char *)(unsigned int)v30,
            v37);
LABEL_36:
          wil::com_ptr_t<IEnrollmentInfoEnumerator,wil::err_returncode_policy>::~com_ptr_t<IEnrollmentInfoEnumerator,wil::err_returncode_policy>(&v44);
          goto LABEL_26;
        }
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x39,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\connectworkschoolaccountsetting.cpp",
        (const char *)(unsigned int)v8,
        v36);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v46);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x36,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\connectworkschoolaccountsetting.cpp",
        (const char *)(unsigned int)v8,
        v35);
    }
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v45);
    v7 = v8;
    goto LABEL_47;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x33,
    (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\connectworkschoolaccountsetting.cpp",
    (const char *)(unsigned int)ActivationFactory,
    v34);
LABEL_47:
  wil::com_ptr_t<IEnrollmentInfoEnumerator,wil::err_returncode_policy>::~com_ptr_t<IEnrollmentInfoEnumerator,wil::err_returncode_policy>(&v48);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180027bd8  mov     [rsp-8+arg_0], rbx
0x180027bdd  mov     [rsp-8+arg_18], rsi
0x180027be2  push    rbp
0x180027be3  push    rdi
0x180027be4  push    r12
0x180027be6  push    r14
0x180027be8  push    r15
0x180027bea  lea     rbp, [rsp-10h]
0x180027bef  sub     rsp, 110h
0x180027bf6  mov     rax, cs:__security_cookie
0x180027bfd  xor     rax, rsp
0x180027c00  mov     [rbp+30h+var_28], rax
0x180027c04  mov     r15, r8
0x180027c07  mov     r14, rdx
0x180027c0a  xor     r12d, r12d
0x180027c0d  mov     [rbp+30h+var_90], r12
0x180027c11  mov     [rbp+30h+var_70], r12
0x180027c15  lea     r9d, [r12+1Fh]; unsigned int
0x180027c1a  lea     r8d, [r12+20h]; unsigned int
0x180027c1f  lea     rdx, ?RuntimeClass_Windows_UI_Popups_MessageDialog@@3QBGB; "Windows.UI.Popups.MessageDialog"
0x180027c26  lea     rcx, [rbp+30h+hstringHeader]; hstringHeader
0x180027c2a  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180027c2f  lea     r8, [rbp+30h+var_90]
0x180027c33  lea     rdx, _GUID_2d161777_a66f_4ea5_bb87_793ffa4941f2
0x180027c3a  mov     rcx, [rbp+30h+var_70]
0x180027c3e  call    cs:__imp_RoGetActivationFactory
0x180027c45  nop     dword ptr [rax+rax+00h]
0x180027c4a  mov     ebx, eax
0x180027c4c  test    eax, eax
0x180027c4e  jns     short loc_180027C6D
0x180027c50  mov     rcx, [rbp+38h]; this
0x180027c54  mov     r9d, eax; char *
0x180027c57  lea     r8, aShellcommonShe_0; "shellcommon\\shell\\settingshandlers\\w"...
0x180027c5e  lea     edx, [r12+33h]; void *
0x180027c63  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027c68  jmp     loc_18002815B
0x180027c6d  mov     [rsp+130h+var_C8], r12
0x180027c72  mov     [rsp+130h+var_C0], r12
0x180027c77  mov     [rsp+130h+var_B8], r12
0x180027c7c  mov     ebx, 80004005h
0x180027c81  mov     edi, ebx
0x180027c83  mov     [rsp+130h+var_E0], r12
0x180027c88  mov     [rsp+130h+var_100], r12w
0x180027c8e  lea     rax, [rsp+130h+var_100]
0x180027c93  mov     qword ptr [rsp+130h+var_110], rax; int
0x180027c98  lea     r9, [rsp+130h+var_E0]; unsigned __int16 **
0x180027c9d  mov     edx, 71h ; 'q'; unsigned int
0x180027ca2  lea     rsi, __ImageBase
0x180027ca9  mov     rcx, rsi; hModule
0x180027cac  call    ?FindAndSize@ResourceString@Internal@Windows@@SA_NPEAUHINSTANCE__@@IGPEAPEBGPEAG@Z; Windows::Internal::ResourceString::FindAndSize(HINSTANCE__ *,uint,ushort,ushort const * *,ushort *)
0x180027cb1  test    al, al
0x180027cb3  jz      loc_180028137
0x180027cb9  movzx   r8d, [rsp+130h+var_100]
0x180027cbf  mov     rdx, [rsp+130h+var_E0]
0x180027cc4  lea     rcx, [rsp+130h+var_C8]
0x180027cc9  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x180027cce  mov     edi, eax
0x180027cd0  test    eax, eax
0x180027cd2  js      loc_180028137
0x180027cd8  mov     [rbp+30h+var_B0], r12
0x180027cdc  mov     [rbp+30h+var_A8], r12
0x180027ce0  mov     [rbp+30h+var_A0], r12
0x180027ce4  mov     edi, ebx
0x180027ce6  mov     [rsp+130h+var_E0], r12
0x180027ceb  mov     [rsp+130h+var_100], r12w
0x180027cf1  lea     rax, [rsp+130h+var_100]
0x180027cf6  mov     qword ptr [rsp+130h+var_110], rax; int
0x180027cfb  lea     r9, [rsp+130h+var_E0]; unsigned __int16 **
0x180027d00  mov     edx, 72h ; 'r'; unsigned int
0x180027d05  mov     rcx, rsi; hModule
0x180027d08  call    ?FindAndSize@ResourceString@Internal@Windows@@SA_NPEAUHINSTANCE__@@IGPEAPEBGPEAG@Z; Windows::Internal::ResourceString::FindAndSize(HINSTANCE__ *,uint,ushort,ushort const * *,ushort *)
0x180027d0d  test    al, al
0x180027d0f  jz      loc_180028114
0x180027d15  movzx   r8d, [rsp+130h+var_100]
0x180027d1b  mov     rdx, [rsp+130h+var_E0]
0x180027d20  lea     rcx, [rbp+30h+var_B0]
0x180027d24  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x180027d29  mov     edi, eax
0x180027d2b  test    eax, eax
0x180027d2d  js      loc_180028114
0x180027d33  mov     qword ptr [rbp+30h+hstringHeader.Reserved], r12
0x180027d37  mov     qword ptr [rbp+30h+hstringHeader.Reserved+8], r12
0x180027d3b  mov     qword ptr [rbp+30h+hstringHeader.Reserved+10h], r12
0x180027d3f  mov     [rsp+130h+var_E0], r12
0x180027d44  mov     [rsp+130h+var_100], r12w
0x180027d4a  lea     rax, [rsp+130h+var_100]
0x180027d4f  mov     qword ptr [rsp+130h+var_110], rax; int
0x180027d54  lea     r9, [rsp+130h+var_E0]; unsigned __int16 **
0x180027d59  mov     edx, 73h ; 's'; unsigned int
0x180027d5e  mov     rcx, rsi; hModule
0x180027d61  call    ?FindAndSize@ResourceString@Internal@Windows@@SA_NPEAUHINSTANCE__@@IGPEAPEBGPEAG@Z; Windows::Internal::ResourceString::FindAndSize(HINSTANCE__ *,uint,ushort,ushort const * *,ushort *)
0x180027d66  test    al, al
0x180027d68  jz      loc_1800280DE
0x180027d6e  movzx   r8d, [rsp+130h+var_100]
0x180027d74  mov     rdx, [rsp+130h+var_E0]
0x180027d79  lea     rcx, [rbp+30h+hstringHeader]
0x180027d7d  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x180027d82  mov     ebx, eax
0x180027d84  test    eax, eax
0x180027d86  js      loc_1800280DE
0x180027d8c  mov     [rsp+130h+var_F8], r12
0x180027d91  mov     rsi, [rbp+30h+var_90]
0x180027d95  mov     rax, [rsi]
0x180027d98  mov     rdi, [rax+38h]
0x180027d9c  lea     rdx, [rsp+130h+var_C8]
0x180027da1  lea     rcx, [rbp+30h+var_68]
0x180027da5  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180027daa  mov     rbx, [rax+18h]
0x180027dae  lea     rdx, [rbp+30h+var_B0]
0x180027db2  lea     rcx, [rbp+30h+var_48]
0x180027db6  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180027dbb  lea     r9, [rsp+130h+var_F8]
0x180027dc0  mov     r8, rbx
0x180027dc3  mov     rdx, [rax+18h]
0x180027dc7  mov     rcx, rsi
0x180027dca  mov     rax, rdi
0x180027dcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027dd2  mov     ebx, eax
0x180027dd4  test    eax, eax
0x180027dd6  jns     short loc_180027DFF
0x180027dd8  mov     rcx, [rbp+38h]; this
0x180027ddc  mov     r9d, eax; char *
0x180027ddf  lea     r8, aShellcommonShe_0; "shellcommon\\shell\\settingshandlers\\w"...
0x180027de6  mov     edx, 3Fh ; '?'; void *
0x180027deb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027df0  lea     rcx, [rsp+130h+var_F8]
0x180027df5  call    ??1?$com_ptr_t@UIEnrollmentInfoEnumerator@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IEnrollmentInfoEnumerator,wil::err_returncode_policy>::~com_ptr_t<IEnrollmentInfoEnumerator,wil::err_returncode_policy>(void)
0x180027dfa  jmp     loc_1800280F6
0x180027dff  mov     [rsp+130h+var_E8], r12
0x180027e04  mov     [rbp+30h+var_50], r12
0x180027e08  mov     r9d, 1Bh; unsigned int
0x180027e0e  lea     r8d, [r9+1]; unsigned int
0x180027e12  lea     rdx, ?RuntimeClass_Windows_UI_Popups_UICommand@@3QBGB; "Windows.UI.Popups.UICommand"
0x180027e19  lea     rcx, [rbp+30h+var_68]; hstringHeader
0x180027e1d  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180027e22  lea     r8, [rsp+130h+var_E8]
0x180027e27  lea     rdx, _GUID_a21a8189_26b0_4676_ae94_54041bc125e8
0x180027e2e  mov     rcx, [rbp+30h+var_50]
0x180027e32  call    cs:__imp_RoGetActivationFactory
0x180027e39  nop     dword ptr [rax+rax+00h]
0x180027e3e  mov     ebx, eax
0x180027e40  test    eax, eax
0x180027e42  jns     short loc_180027E68
0x180027e44  mov     rcx, [rbp+38h]; this
0x180027e48  mov     r9d, eax; char *
0x180027e4b  lea     r8, aShellcommonShe_0; "shellcommon\\shell\\settingshandlers\\w"...
0x180027e52  mov     edx, 44h ; 'D'; void *
0x180027e57  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027e5c  lea     rcx, [rsp+130h+var_E8]
0x180027e61  call    ??1?$com_ptr_t@UIEnrollmentInfoEnumerator@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IEnrollmentInfoEnumerator,wil::err_returncode_policy>::~com_ptr_t<IEnrollmentInfoEnumerator,wil::err_returncode_policy>(void)
0x180027e66  jmp     short loc_180027DF0
0x180027e68  mov     [rsp+130h+var_F0], r12
0x180027e6d  mov     rdi, [rsp+130h+var_E8]
0x180027e72  mov     rax, [rdi]
0x180027e75  mov     rbx, [rax+30h]
0x180027e79  lea     rdx, [rbp+30h+hstringHeader]
0x180027e7d  lea     rcx, [rbp+30h+var_48]
0x180027e81  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180027e86  lea     r8, [rsp+130h+var_F0]
0x180027e8b  mov     rdx, [rax+18h]
0x180027e8f  mov     rcx, rdi
0x180027e92  mov     rax, rbx
0x180027e95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027e9a  mov     ebx, eax
0x180027e9c  test    eax, eax
0x180027e9e  jns     short loc_180027EC4
0x180027ea0  mov     r9d, eax; char *
0x180027ea3  mov     edx, 47h ; 'G'; void *
0x180027ea8  lea     r8, aShellcommonShe_0; "shellcommon\\shell\\settingshandlers\\w"...
0x180027eaf  mov     rcx, [rbp+38h]; this
0x180027eb3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027eb8  lea     rcx, [rsp+130h+var_F0]
0x180027ebd  call    ??1?$com_ptr_t@UIEnrollmentInfoEnumerator@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IEnrollmentInfoEnumerator,wil::err_returncode_policy>::~com_ptr_t<IEnrollmentInfoEnumerator,wil::err_returncode_policy>(void)
0x180027ec2  jmp     short loc_180027E5C
0x180027ec4  mov     rdi, [rsp+130h+var_F0]
0x180027ec9  mov     rax, [rdi]
0x180027ecc  mov     rbx, [rax+48h]
0x180027ed0  mov     rdx, r14
0x180027ed3  lea     rcx, [rbp+30h+var_68]
0x180027ed7  call    _lambda_aa8b5faaf664393c12820c0561572d67____lambda_aa8b5faaf664393c12820c0561572d67_
0x180027edc  mov     rdx, rax
0x180027edf  lea     rcx, [rsp+130h+var_E0]
0x180027ee4  call    Microsoft__WRL__Callback_Windows__UI__Popups__IUICommandInvokedHandler__lambda_aa8b5faaf664393c12820c0561572d67___
0x180027ee9  mov     rdx, [rax]
0x180027eec  mov     rcx, rdi
0x180027eef  mov     rax, rbx
0x180027ef2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027ef7  mov     ebx, eax
0x180027ef9  mov     rcx, [rsp+130h+var_E0]
0x180027efe  test    rcx, rcx
0x180027f01  jz      short loc_180027F15
0x180027f03  mov     [rsp+130h+var_E0], r12
0x180027f08  mov     rdx, [rcx]
0x180027f0b  mov     rax, [rdx+10h]
0x180027f0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027f14  nop
0x180027f15  test    ebx, ebx
0x180027f17  jns     short loc_180027F23
0x180027f19  mov     r9d, ebx
0x180027f1c  mov     edx, 54h ; 'T'
0x180027f21  jmp     short loc_180027EA8
0x180027f23  mov     [rsp+130h+var_D8], r12
0x180027f28  mov     rcx, [rsp+130h+var_F8]
0x180027f2d  mov     rax, [rcx]
0x180027f30  lea     rdx, [rsp+130h+var_D8]
0x180027f35  mov     rax, [rax+40h]
0x180027f39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027f3e  mov     ebx, eax
0x180027f40  test    eax, eax
0x180027f42  jns     short loc_180027F6B
0x180027f44  mov     edx, 57h ; 'W'; void *
0x180027f49  lea     r8, aShellcommonShe_0; "shellcommon\\shell\\settingshandlers\\w"...
0x180027f50  mov     r9d, eax; char *
0x180027f53  mov     rcx, [rbp+38h]; this
0x180027f57  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027f5c  lea     rcx, [rsp+130h+var_D8]
0x180027f61  call    ??1?$com_ptr_t@UIEnrollmentInfoEnumerator@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IEnrollmentInfoEnumerator,wil::err_returncode_policy>::~com_ptr_t<IEnrollmentInfoEnumerator,wil::err_returncode_policy>(void)
0x180027f66  jmp     loc_180027EB8
0x180027f6b  mov     rcx, [rsp+130h+var_D8]
0x180027f70  mov     rax, [rcx]
0x180027f73  mov     rdx, [rsp+130h+var_F0]
0x180027f78  mov     rax, [rax+68h]
0x180027f7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027f81  mov     ebx, eax
0x180027f83  test    eax, eax
0x180027f85  jns     short loc_180027F8E
0x180027f87  mov     edx, 58h ; 'X'
0x180027f8c  jmp     short loc_180027F49
0x180027f8e  mov     rcx, [rsp+130h+var_F8]
0x180027f93  mov     rax, [rcx]
0x180027f96  xor     edx, edx
0x180027f98  mov     rax, [rax+50h]
0x180027f9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027fa1  mov     ebx, eax
0x180027fa3  test    eax, eax
0x180027fa5  jns     short loc_180027FAE
0x180027fa7  mov     edx, 5Bh ; '['
0x180027fac  jmp     short loc_180027F49
0x180027fae  mov     rcx, [rsp+130h+var_F8]
0x180027fb3  mov     rax, [rcx]
0x180027fb6  xor     edx, edx
0x180027fb8  mov     rax, [rax+60h]
0x180027fbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027fc1  mov     ebx, eax
0x180027fc3  test    eax, eax
0x180027fc5  jns     short loc_180027FD1
0x180027fc7  mov     edx, 5Ch ; '\'
0x180027fcc  jmp     loc_180027F49
0x180027fd1  mov     [rsp+130h+var_D0], r12
0x180027fd6  mov     rcx, [rsp+130h+var_F8]
0x180027fdb  mov     rax, [rcx]
0x180027fde  lea     r8, [rsp+130h+var_D0]
0x180027fe3  lea     rdx, _GUID_3e68d4bd_7135_4d10_8018_9fb6d9f33fa1
0x180027fea  mov     rax, [rax]
0x180027fed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027ff2  mov     ebx, eax
0x180027ff4  test    eax, eax
0x180027ff6  jns     short loc_18002801F
0x180027ff8  mov     edx, 63h ; 'c'; void *
0x180027ffd  lea     r8, aShellcommonShe_0; "shellcommon\\shell\\settingshandlers\\w"...
0x180028004  mov     r9d, eax; char *
0x180028007  mov     rcx, [rbp+38h]; this
0x18002800b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028010  lea     rcx, [rsp+130h+var_D0]
0x180028015  call    ??1?$com_ptr_t@UIEnrollmentInfoEnumerator@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IEnrollmentInfoEnumerator,wil::err_returncode_policy>::~com_ptr_t<IEnrollmentInfoEnumerator,wil::err_returncode_policy>(void)
0x18002801a  jmp     loc_180027F5C
0x18002801f  mov     rcx, [rsp+130h+var_D0]
0x180028024  mov     rax, [rcx]
0x180028027  mov     rdx, r15
0x18002802a  mov     rax, [rax+18h]
0x18002802e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028033  mov     ebx, eax
0x180028035  test    eax, eax
0x180028037  jns     short loc_180028040
0x180028039  mov     edx, 64h ; 'd'
0x18002803e  jmp     short loc_180027FFD
0x180028040  mov     [rbp+30h+var_98], r12
0x180028044  mov     rcx, [rsp+130h+var_F8]
0x180028049  mov     rax, [rcx]
0x18002804c  lea     rdx, [rbp+30h+var_98]
0x180028050  mov     rax, [rax+78h]
0x180028054  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028059  mov     ebx, eax
0x18002805b  test    eax, eax
0x18002805d  jns     short loc_180028082
0x18002805f  mov     rcx, [rbp+38h]; this
0x180028063  mov     r9d, eax; char *
0x180028066  lea     r8, aShellcommonShe_0; "shellcommon\\shell\\settingshandlers\\w"...
0x18002806d  mov     edx, 68h ; 'h'; void *
0x180028072  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028077  lea     rcx, [rbp+30h+var_98]
0x18002807b  call    ??1?$com_ptr_t@UIEnrollmentInfoEnumerator@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IEnrollmentInfoEnumerator,wil::err_returncode_policy>::~com_ptr_t<IEnrollmentInfoEnumerator,wil::err_returncode_policy>(void)
0x180028080  jmp     short loc_180028010
0x180028082  lea     rcx, [rbp+30h+var_98]
0x180028086  call    ??1?$com_ptr_t@UIEnrollmentInfoEnumerator@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IEnrollmentInfoEnumerator,wil::err_returncode_policy>::~com_ptr_t<IEnrollmentInfoEnumerator,wil::err_returncode_policy>(void)
0x18002808b  lea     rcx, [rsp+130h+var_D0]
0x180028090  call    ??1?$com_ptr_t@UIEnrollmentInfoEnumerator@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IEnrollmentInfoEnumerator,wil::err_returncode_policy>::~com_ptr_t<IEnrollmentInfoEnumerator,wil::err_returncode_policy>(void)
0x180028095  lea     rcx, [rsp+130h+var_D8]
0x18002809a  call    ??1?$com_ptr_t@UIEnrollmentInfoEnumerator@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IEnrollmentInfoEnumerator,wil::err_returncode_policy>::~com_ptr_t<IEnrollmentInfoEnumerator,wil::err_returncode_policy>(void)
0x18002809f  lea     rcx, [rsp+130h+var_F0]
  ... truncated ...
```
