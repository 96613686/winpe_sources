# ImpersonationHelper::GetActiveUserTokenFromUserManager(void * *)

- ea: `0x18002b1f4`
- end: `0x18002b4f9`
- name: `?GetActiveUserTokenFromUserManager@ImpersonationHelper@@CAJPEAPEAX@Z`
- size: `773`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002a6b0`
- `0x180089914`
- `0x1800a77e0`

## callees

- `0x180004b80`
- `0x18000b19c`
- `0x18000cc8c`
- `0x18001146c`
- `0x18002aad4`
- `0x18002b1f4`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002b262`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002b2d0`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002b262`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002b2d0`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18002b423`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18002b423`

## string_xrefs

- `0x18002b275`: `onecore\base\flighting\flightSettings\broker\libs\inc\ImpersonationHelper.h`
- `0x18002b2e3`: `onecore\base\flighting\flightSettings\broker\libs\inc\ImpersonationHelper.h`
- `0x18002b331`: `onecore\base\flighting\flightSettings\broker\libs\inc\ImpersonationHelper.h`
- `0x18002b49b`: `onecore\base\flighting\flightSettings\broker\libs\inc\ImpersonationHelper.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall ImpersonationHelper::GetActiveUserTokenFromUserManager(void **a1)
{
  __int64 v2; // rbx
  int ActivationFactory; // eax
  int v4; // ebx
  __int64 v5; // rbx
  int v6; // eax
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, __int64 *); // rbx
  int v9; // eax
  __int64 v10; // rdi
  int v11; // eax
  unsigned __int64 v12; // r9
  __int64 v13; // rdx
  unsigned int i; // esi
  __int64 v15; // rdi
  int (__fastcall *v16)(__int64, _QWORD, __int64 *); // rbx
  __int64 v18; // [rsp+20h] [rbp-60h] BYREF
  __int64 v19; // [rsp+28h] [rbp-58h] BYREF
  __int64 v20; // [rsp+30h] [rbp-50h] BYREF
  __int64 v21; // [rsp+38h] [rbp-48h] BYREF
  unsigned int v22; // [rsp+40h] [rbp-40h] BYREF
  __int64 v23; // [rsp+48h] [rbp-38h] BYREF
  __int64 v24; // [rsp+50h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-28h] BYREF
  __int64 v26; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  v21 = 0;
  v26 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.System.Internal.UserManager",
    0x24u,
    0x23u);
  v2 = v26;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v21);
  ActivationFactory = RoGetActivationFactory(v2, &GUID_100eb64b_b24c_4c38_8964_720d926d05a4, &v21);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x111,
      (unsigned int)"onecore\\base\\flighting\\flightSettings\\broker\\libs\\inc\\ImpersonationHelper.h",
      (const char *)(unsigned int)ActivationFactory,
      v18);
LABEL_23:
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v21);
    return (unsigned int)v4;
  }
  v18 = 0;
  v26 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Windows.System.User", 0x14u, 0x13u);
  v5 = v26;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v18);
  v6 = RoGetActivationFactory(v5, &GUID_155eb23b_242a_45e0_a2e9_3171fc6a7fdd, &v18);
  v4 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x114,
      (unsigned int)"onecore\\base\\flighting\\flightSettings\\broker\\libs\\inc\\ImpersonationHelper.h",
      (const char *)(unsigned int)v6,
      v18);
LABEL_22:
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v18);
    goto LABEL_23;
  }
  v20 = 0;
  v7 = v18;
  v8 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v18 + 56LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v20);
  v9 = v8(v7, &v20);
  v4 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x117,
      (unsigned int)"onecore\\base\\flighting\\flightSettings\\broker\\libs\\inc\\ImpersonationHelper.h",
      (const char *)(unsigned int)v9,
      v18);
LABEL_21:
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v20);
    goto LABEL_22;
  }
  v19 = 0;
  v10 = v20;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v19);
  v4 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>>(v10);
  if ( v4 < 0 || (v4 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v10 + 64LL))(v10, &v19), v4 < 0) )
  {
    v12 = (unsigned int)v4;
    v13 = 282;
    goto LABEL_20;
  }
  v22 = 0;
  v11 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v19 + 56LL))(v19, &v22);
  v4 = v11;
  if ( v11 < 0 )
  {
    v12 = (unsigned int)v11;
    v13 = 285;
LABEL_20:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\base\\flighting\\flightSettings\\broker\\libs\\inc\\ImpersonationHelper.h",
      (const char *)v12,
      v18);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v19);
    goto LABEL_21;
  }
  for ( i = 0; i < v22; ++i )
  {
    v23 = 0;
    v15 = v19;
    v16 = *(int (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v19 + 48LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v23);
    if ( v16(v15, i, &v23) >= 0 )
    {
      v24 = 0;
      if ( (*(int (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v21 + 136LL))(v21, v23, &v24) >= 0
        && (int)UMgrQueryUserToken(v24, a1) >= 0 )
      {
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v23);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v19);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v20);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v18);
        v4 = 0;
        goto LABEL_23;
      }
    }
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v23);
  }
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v19);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v20);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v18);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v21);
  return 2148268548LL;
}

```

## disassembly

```asm
0x18002b1f4  mov     [rsp-18h+arg_8], rbx
0x18002b1f9  mov     [rsp-18h+arg_10], rsi
0x18002b1fe  push    rbp
0x18002b1ff  push    rdi
0x18002b200  push    r14
0x18002b202  mov     rbp, rsp
0x18002b205  sub     rsp, 80h
0x18002b20c  mov     rax, cs:__security_cookie
0x18002b213  xor     rax, rsp
0x18002b216  mov     [rbp+var_8], rax
0x18002b21a  mov     r14, rcx
0x18002b21d  mov     [rbp+var_48], 0
0x18002b225  mov     [rbp+var_10], 0
0x18002b22d  mov     r9d, 23h ; '#'; unsigned int
0x18002b233  lea     r8d, [r9+1]; unsigned int
0x18002b237  lea     rdx, ?RuntimeClass_Windows_System_Internal_UserManager@@3QBGB; "Windows.System.Internal.UserManager"
0x18002b23e  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x18002b242  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18002b247  mov     rbx, [rbp+var_10]
0x18002b24b  lea     rcx, [rbp+var_48]
0x18002b24f  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002b254  lea     r8, [rbp+var_48]
0x18002b258  lea     rdx, _GUID_100eb64b_b24c_4c38_8964_720d926d05a4
0x18002b25f  mov     rcx, rbx
0x18002b262  call    cs:__imp_RoGetActivationFactory
0x18002b268  mov     ebx, eax
0x18002b26a  test    eax, eax
0x18002b26c  jns     short loc_18002B28B
0x18002b26e  mov     rcx, [rbp+18h]; this
0x18002b272  mov     r9d, eax; char *
0x18002b275  lea     r8, aOnecoreBaseFli_0; "onecore\\base\\flighting\\flightSetting"...
0x18002b27c  mov     edx, 111h; void *
0x18002b281  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b286  jmp     loc_18002B4CA
0x18002b28b  mov     [rbp+var_60], 0
0x18002b293  mov     [rbp+var_10], 0
0x18002b29b  mov     r9d, 13h; unsigned int
0x18002b2a1  lea     r8d, [r9+1]; unsigned int
0x18002b2a5  lea     rdx, ?RuntimeClass_Windows_System_User@@3QBGB; "Windows.System.User"
0x18002b2ac  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x18002b2b0  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18002b2b5  mov     rbx, [rbp+var_10]
0x18002b2b9  lea     rcx, [rbp+var_60]
0x18002b2bd  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002b2c2  lea     r8, [rbp+var_60]
0x18002b2c6  lea     rdx, _GUID_155eb23b_242a_45e0_a2e9_3171fc6a7fdd
0x18002b2cd  mov     rcx, rbx
0x18002b2d0  call    cs:__imp_RoGetActivationFactory
0x18002b2d6  mov     ebx, eax
0x18002b2d8  test    eax, eax
0x18002b2da  jns     short loc_18002B2F9
0x18002b2dc  mov     rcx, [rbp+18h]; this
0x18002b2e0  mov     r9d, eax; char *
0x18002b2e3  lea     r8, aOnecoreBaseFli_0; "onecore\\base\\flighting\\flightSetting"...
0x18002b2ea  mov     edx, 114h; void *
0x18002b2ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b2f4  jmp     loc_18002B4C0
0x18002b2f9  mov     [rbp+var_50], 0
0x18002b301  mov     rdi, [rbp+var_60]
0x18002b305  mov     rax, [rdi]
0x18002b308  mov     rbx, [rax+38h]
0x18002b30c  lea     rcx, [rbp+var_50]
0x18002b310  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002b315  lea     rdx, [rbp+var_50]
0x18002b319  mov     rcx, rdi
0x18002b31c  mov     rax, rbx
0x18002b31f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b324  mov     ebx, eax
0x18002b326  test    eax, eax
0x18002b328  jns     short loc_18002B347
0x18002b32a  mov     rcx, [rbp+18h]; this
0x18002b32e  mov     r9d, eax; char *
0x18002b331  lea     r8, aOnecoreBaseFli_0; "onecore\\base\\flighting\\flightSetting"...
0x18002b338  mov     edx, 117h; void *
0x18002b33d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b342  jmp     loc_18002B4B6
0x18002b347  mov     [rbp+var_58], 0
0x18002b34f  mov     rdi, [rbp+var_50]
0x18002b353  lea     rcx, [rbp+var_58]
0x18002b357  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002b35c  mov     rcx, rdi
0x18002b35f  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *> *,tagCOWAIT_FLAGS,void *)
0x18002b364  mov     ebx, eax
0x18002b366  test    eax, eax
0x18002b368  js      loc_18002B493
0x18002b36e  mov     rax, [rdi]
0x18002b371  lea     rdx, [rbp+var_58]
0x18002b375  mov     rcx, rdi
0x18002b378  mov     rax, [rax+40h]
0x18002b37c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b381  mov     ebx, eax
0x18002b383  test    eax, eax
0x18002b385  js      loc_18002B493
0x18002b38b  mov     [rbp+var_40], 0
0x18002b392  mov     rcx, [rbp+var_58]
0x18002b396  mov     rax, [rcx]
0x18002b399  lea     rdx, [rbp+var_40]
0x18002b39d  mov     rax, [rax+38h]
0x18002b3a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b3a6  mov     ebx, eax
0x18002b3a8  test    eax, eax
0x18002b3aa  jns     short loc_18002B3B9
0x18002b3ac  mov     r9d, eax
0x18002b3af  mov     edx, 11Dh
0x18002b3b4  jmp     loc_18002B49B
0x18002b3b9  xor     esi, esi
0x18002b3bb  cmp     esi, [rbp+var_40]
0x18002b3be  jnb     loc_18002B465
0x18002b3c4  mov     [rbp+var_38], 0
0x18002b3cc  mov     rdi, [rbp+var_58]
0x18002b3d0  mov     rax, [rdi]
0x18002b3d3  mov     rbx, [rax+30h]
0x18002b3d7  lea     rcx, [rbp+var_38]
0x18002b3db  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002b3e0  lea     r8, [rbp+var_38]
0x18002b3e4  mov     edx, esi
0x18002b3e6  mov     rcx, rdi
0x18002b3e9  mov     rax, rbx
0x18002b3ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b3f1  test    eax, eax
0x18002b3f3  js      short loc_18002B42D
0x18002b3f5  mov     [rbp+var_30], 0
0x18002b3fd  mov     rcx, [rbp+var_48]
0x18002b401  mov     rax, [rcx]
0x18002b404  lea     r8, [rbp+var_30]
0x18002b408  mov     rdx, [rbp+var_38]
0x18002b40c  mov     rax, [rax+88h]
0x18002b413  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b418  test    eax, eax
0x18002b41a  js      short loc_18002B42D
0x18002b41c  mov     rdx, r14
0x18002b41f  mov     rcx, [rbp+var_30]
0x18002b423  call    cs:__imp_UMgrQueryUserToken
0x18002b429  test    eax, eax
0x18002b42b  jns     short loc_18002B43A
0x18002b42d  lea     rcx, [rbp+var_38]
0x18002b431  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002b436  inc     esi
0x18002b438  jmp     short loc_18002B3BB
0x18002b43a  lea     rcx, [rbp+var_38]
0x18002b43e  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002b443  nop
0x18002b444  lea     rcx, [rbp+var_58]
0x18002b448  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002b44d  nop
0x18002b44e  lea     rcx, [rbp+var_50]
0x18002b452  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002b457  nop
0x18002b458  lea     rcx, [rbp+var_60]
0x18002b45c  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002b461  xor     ebx, ebx
0x18002b463  jmp     short loc_18002B4CA
0x18002b465  lea     rcx, [rbp+var_58]
0x18002b469  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002b46e  nop
0x18002b46f  lea     rcx, [rbp+var_50]
0x18002b473  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002b478  nop
0x18002b479  lea     rcx, [rbp+var_60]
0x18002b47d  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002b482  nop
0x18002b483  lea     rcx, [rbp+var_48]
0x18002b487  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002b48c  mov     eax, 800BFA04h
0x18002b491  jmp     short loc_18002B4D5
0x18002b493  mov     r9d, ebx; char *
0x18002b496  mov     edx, 11Ah; void *
0x18002b49b  lea     r8, aOnecoreBaseFli_0; "onecore\\base\\flighting\\flightSetting"...
0x18002b4a2  mov     rcx, [rbp+18h]; this
0x18002b4a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b4ab  nop
0x18002b4ac  lea     rcx, [rbp+var_58]
0x18002b4b0  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002b4b5  nop
0x18002b4b6  lea     rcx, [rbp+var_50]
0x18002b4ba  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002b4bf  nop
0x18002b4c0  lea     rcx, [rbp+var_60]
0x18002b4c4  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002b4c9  nop
0x18002b4ca  lea     rcx, [rbp+var_48]
0x18002b4ce  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002b4d3  mov     eax, ebx
0x18002b4d5  mov     rcx, [rbp+var_8]
0x18002b4d9  xor     rcx, rsp; StackCookie
0x18002b4dc  call    __security_check_cookie
0x18002b4e1  lea     r11, [rsp+80h+var_s0]
0x18002b4e9  mov     rbx, [r11+28h]
0x18002b4ed  mov     rsi, [r11+30h]
0x18002b4f1  mov     rsp, r11
0x18002b4f4  pop     r14
0x18002b4f6  pop     rdi
0x18002b4f7  pop     rbp
0x18002b4f8  retn
```
