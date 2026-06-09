# FindAppsByExtension(ushort const *,Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::ApplicationExtension *> * *)

- ea: `0x18004e6f8`
- end: `0x18004e91e`
- name: `?FindAppsByExtension@@YAJPEBGPEAPEAU?$IVectorView@PEAVApplicationExtension@StateRepository@Internal@Windows@@@Collections@Foundation@Windows@@@Z`
- size: `550`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004ef9c`
- `0x18004f028`

## callees

- `0x180006eac`
- `0x180007f68`
- `0x18000e87c`
- `0x180011ffc`
- `0x18001908c`
- `0x18004df78`
- `0x18004e6f8`
- `0x180069730`
- `0x18006c010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18004e771`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18004e7df`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18004e771`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18004e7df`

## string_xrefs

- `0x18004e746`: `Windows.Internal.StateRepository.ApplicationExtension`
- `0x18004e784`: `onecoreuap\shell\accountscontrol\api\mailcontactscalendarsyncuiapilib\appextensionhelpers.cpp`
- `0x18004e7f2`: `onecoreuap\shell\accountscontrol\api\mailcontactscalendarsyncuiapilib\appextensionhelpers.cpp`
- `0x18004e848`: `onecoreuap\shell\accountscontrol\api\mailcontactscalendarsyncuiapilib\appextensionhelpers.cpp`
- `0x18004e8cb`: `onecoreuap\shell\accountscontrol\api\mailcontactscalendarsyncuiapilib\appextensionhelpers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall FindAppsByExtension(__int64 a1, _QWORD *a2)
{
  __int64 v3; // rbx
  int ActivationFactory; // eax
  unsigned int v5; // ebx
  __int64 v6; // rbx
  int v7; // eax
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, __int64 *); // rbx
  int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, __int64, _QWORD, _QWORD *); // rbx
  __int64 v14; // rax
  int v15; // eax
  int v17; // [rsp+20h] [rbp-39h]
  __int64 v18; // [rsp+30h] [rbp-29h] BYREF
  __int64 v19; // [rsp+38h] [rbp-21h] BYREF
  int v20; // [rsp+40h] [rbp-19h] BYREF
  _QWORD v21[3]; // [rsp+48h] [rbp-11h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp+7h] BYREF
  __int64 v23; // [rsp+78h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  v21[1] = L"Windows.UserDataAccountsProvider";
  *a2 = 0;
  v21[0] = 0;
  v23 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.StateRepository.ApplicationExtension",
    0x36u,
    0x35u);
  v3 = v23;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v21);
  ActivationFactory = RoGetActivationFactory(v3, &GUID_b94b62a2_4012_4b7e_a395_f21cc665fd12, v21);
  v5 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2E,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\appextensionhelpers.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v17);
    goto LABEL_14;
  }
  v18 = 0;
  v23 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.StateRepository.User",
    0x26u,
    0x25u);
  v6 = v23;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v18);
  v7 = RoGetActivationFactory(v6, &GUID_84103ccb_2fd7_4d6c_962e_5d8582b4c720, &v18);
  v5 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x31,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\appextensionhelpers.cpp",
      (const char *)(unsigned int)v7,
      v17);
LABEL_5:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v18);
    goto LABEL_14;
  }
  v19 = 0;
  v8 = v18;
  v9 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v18 + 104LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
  v10 = v9(v8, &v19);
  v5 = v10;
  if ( v10 < 0 )
  {
    v11 = 51;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\appextensionhelpers.cpp",
      (const char *)(unsigned int)v10,
      v17);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
    goto LABEL_5;
  }
  v12 = v21[0];
  v13 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD *))(*(_QWORD *)v21[0] + 160LL);
  v14 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader);
  v10 = v13(v12, v19, *(_QWORD *)(v14 + 24), a2);
  v5 = v10;
  if ( v10 < 0 )
  {
    v11 = 53;
    goto LABEL_8;
  }
  v20 = 0;
  v15 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)*a2 + 56LL))(*a2, &v20);
  if ( v15 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x38,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\appextensionhelpers.cpp",
      (const char *)(unsigned int)v15,
      v17);
  SyncPartnershipApiTelemetry::FindAppsByExtension<unsigned int &>(&v20);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v18);
  v5 = 0;
LABEL_14:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v21);
  return v5;
}

```

## disassembly

```asm
0x18004e6f8  push    rbp
0x18004e6fa  push    rbx
0x18004e6fb  push    rsi
0x18004e6fc  push    rdi
0x18004e6fd  lea     rbp, [rsp-3Fh]
0x18004e702  sub     rsp, 98h
0x18004e709  mov     rax, cs:__security_cookie
0x18004e710  xor     rax, rsp
0x18004e713  mov     [rbp+57h+var_30], rax
0x18004e717  mov     rsi, rdx
0x18004e71a  lea     rax, aWindowsUserdat; "Windows.UserDataAccountsProvider"
0x18004e721  mov     [rbp+57h+var_60], rax
0x18004e725  mov     qword ptr [rdx], 0
0x18004e72c  mov     [rbp+57h+var_68], 0
0x18004e734  mov     [rbp+57h+var_38], 0
0x18004e73c  mov     r9d, 35h ; '5'; unsigned int
0x18004e742  lea     r8d, [r9+1]; unsigned int
0x18004e746  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_ApplicationExtension@@3QBGB; "Windows.Internal.StateRepository.Applic"...
0x18004e74d  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18004e751  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18004e756  mov     rbx, [rbp+57h+var_38]
0x18004e75a  lea     rcx, [rbp+57h+var_68]
0x18004e75e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004e763  lea     r8, [rbp+57h+var_68]
0x18004e767  lea     rdx, _GUID_b94b62a2_4012_4b7e_a395_f21cc665fd12
0x18004e76e  mov     rcx, rbx
0x18004e771  call    cs:__imp_RoGetActivationFactory
0x18004e777  mov     ebx, eax
0x18004e779  test    eax, eax
0x18004e77b  jns     short loc_18004E79A
0x18004e77d  mov     rcx, [rbp+5Fh]; this
0x18004e781  mov     r9d, eax; char *
0x18004e784  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\accountscontrol\\api"...
0x18004e78b  mov     edx, 2Eh ; '.'; void *
0x18004e790  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e795  jmp     loc_18004E8FB
0x18004e79a  mov     [rbp+57h+var_80], 0
0x18004e7a2  mov     [rbp+57h+var_38], 0
0x18004e7aa  mov     r9d, 25h ; '%'; unsigned int
0x18004e7b0  lea     r8d, [r9+1]; unsigned int
0x18004e7b4  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_User@@3QBGB; "Windows.Internal.StateRepository.User"
0x18004e7bb  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18004e7bf  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18004e7c4  mov     rbx, [rbp+57h+var_38]
0x18004e7c8  lea     rcx, [rbp+57h+var_80]
0x18004e7cc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004e7d1  lea     r8, [rbp+57h+var_80]
0x18004e7d5  lea     rdx, _GUID_84103ccb_2fd7_4d6c_962e_5d8582b4c720
0x18004e7dc  mov     rcx, rbx
0x18004e7df  call    cs:__imp_RoGetActivationFactory
0x18004e7e5  mov     ebx, eax
0x18004e7e7  test    eax, eax
0x18004e7e9  jns     short loc_18004E812
0x18004e7eb  mov     rcx, [rbp+5Fh]; this
0x18004e7ef  mov     r9d, eax; char *
0x18004e7f2  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\accountscontrol\\api"...
0x18004e7f9  mov     edx, 31h ; '1'; void *
0x18004e7fe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e803  nop
0x18004e804  lea     rcx, [rbp+57h+var_80]
0x18004e808  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004e80d  jmp     loc_18004E8FB
0x18004e812  mov     [rbp+57h+var_78], 0
0x18004e81a  mov     rdi, [rbp+57h+var_80]
0x18004e81e  mov     rax, [rdi]
0x18004e821  mov     rbx, [rax+68h]
0x18004e825  lea     rcx, [rbp+57h+var_78]
0x18004e829  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004e82e  lea     rdx, [rbp+57h+var_78]
0x18004e832  mov     rcx, rdi
0x18004e835  mov     rax, rbx
0x18004e838  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e83d  mov     ebx, eax
0x18004e83f  test    eax, eax
0x18004e841  jns     short loc_18004E867
0x18004e843  mov     edx, 33h ; '3'; void *
0x18004e848  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\accountscontrol\\api"...
0x18004e84f  mov     r9d, eax; char *
0x18004e852  mov     rcx, [rbp+5Fh]; this
0x18004e856  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e85b  nop
0x18004e85c  lea     rcx, [rbp+57h+var_78]
0x18004e860  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004e865  jmp     short loc_18004E804
0x18004e867  mov     rdi, [rbp+57h+var_68]
0x18004e86b  mov     rax, [rdi]
0x18004e86e  mov     rbx, [rax+0A0h]
0x18004e875  lea     rdx, [rbp+57h+var_60]
0x18004e879  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18004e87d  call    ??$?0V?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBV?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@UDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>> const &,Microsoft::WRL::Details::Dummy)
0x18004e882  nop
0x18004e883  mov     r9, rsi
0x18004e886  mov     r8, [rax+18h]
0x18004e88a  mov     rdx, [rbp+57h+var_78]
0x18004e88e  mov     rcx, rdi
0x18004e891  mov     rax, rbx
0x18004e894  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e899  mov     ebx, eax
0x18004e89b  test    eax, eax
0x18004e89d  jns     short loc_18004E8A6
0x18004e89f  mov     edx, 35h ; '5'
0x18004e8a4  jmp     short loc_18004E848
0x18004e8a6  mov     [rbp+57h+var_70], 0
0x18004e8ad  mov     rcx, [rsi]
0x18004e8b0  mov     rax, [rcx]
0x18004e8b3  lea     rdx, [rbp+57h+var_70]
0x18004e8b7  mov     rax, [rax+38h]
0x18004e8bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e8c0  mov     rcx, [rbp+5Fh]; this
0x18004e8c4  test    eax, eax
0x18004e8c6  jns     short loc_18004E8DC
0x18004e8c8  mov     r9d, eax; char *
0x18004e8cb  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\accountscontrol\\api"...
0x18004e8d2  mov     edx, 38h ; '8'; void *
0x18004e8d7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004e8dc  lea     rcx, [rbp+57h+var_70]
0x18004e8e0  call    ??$FindAppsByExtension@AEAI@SyncPartnershipApiTelemetry@@SAXAEAI@Z; SyncPartnershipApiTelemetry::FindAppsByExtension<uint &>(uint &)
0x18004e8e5  nop
0x18004e8e6  lea     rcx, [rbp+57h+var_78]
0x18004e8ea  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004e8ef  nop
0x18004e8f0  lea     rcx, [rbp+57h+var_80]
0x18004e8f4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004e8f9  xor     ebx, ebx
0x18004e8fb  lea     rcx, [rbp+57h+var_68]
0x18004e8ff  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004e904  mov     eax, ebx
0x18004e906  mov     rcx, [rbp+57h+var_30]
0x18004e90a  xor     rcx, rsp; StackCookie
0x18004e90d  call    __security_check_cookie
0x18004e912  add     rsp, 98h
0x18004e919  pop     rdi
0x18004e91a  pop     rsi
0x18004e91b  pop     rbx
0x18004e91c  pop     rbp
0x18004e91d  retn
```
