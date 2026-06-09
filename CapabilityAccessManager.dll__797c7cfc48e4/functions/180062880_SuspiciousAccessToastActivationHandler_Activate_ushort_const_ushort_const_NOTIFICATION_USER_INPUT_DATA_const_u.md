# SuspiciousAccessToastActivationHandler::Activate(ushort const *,ushort const *,NOTIFICATION_USER_INPUT_DATA const *,ulong)

- ea: `0x180062880`
- end: `0x180062be6`
- name: `?Activate@SuspiciousAccessToastActivationHandler@@UEAAJPEBG0PEBUNOTIFICATION_USER_INPUT_DATA@@K@Z`
- size: `870`
- prototype: `__int64 __fastcall(SuspiciousAccessToastActivationHandler *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const struct NOTIFICATION_USER_INPUT_DATA *, unsigned int)`
- caller_count: `0`
- callee_count: `17`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800094c0`
- `0x18001649c`
- `0x18001ab9c`
- `0x18001c3b4`
- `0x18001d914`
- `0x18001f5f4`
- `0x180029408`
- `0x18002d280`
- `0x18003afa0`
- `0x18003b54c`
- `0x1800465b0`
- `0x1800467c8`
- `0x180058854`
- `0x180062568`
- `0x180062880`
- `0x18006318c`
- `0x1800c7010`

## import_xrefs

- `msvcp_win!?_Xinvalid_argument@std@@YAXPEBD@Z` at `0x1800629f6`
- `msvcp_win!?_Xinvalid_argument@std@@YAXPEBD@Z` at `0x1800629f6`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180062a09`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180062a09`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x1800629e2`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x1800629e2`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800629b5`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800629b5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180062a68`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180062a68`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180062a8b`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180062a8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180062a4f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180062a4f`

## string_xrefs

- `0x180062a48`: `Windows.Internal.CapabilityAccess.UsageHistory.CapabilityUsageHistoryAnnotator`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall SuspiciousAccessToastActivationHandler::Activate(
        SuspiciousAccessToastActivationHandler *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const struct NOTIFICATION_USER_INPUT_DATA *a4)
{
  __int64 v4; // rax
  __int64 i; // r8
  __int64 v6; // rax
  __int64 v7; // rbx
  __int64 v8; // rax
  __int64 v9; // rdi
  unsigned int v10; // ebx
  unsigned int v11; // r15d
  __int64 v12; // rbx
  _DWORD *v13; // rdi
  const wchar_t *v14; // rbx
  int v15; // eax
  int v16; // r12d
  const unsigned __int16 *v17; // r13
  HSTRING v18; // rbx
  int ActivationFactory; // eax
  __int64 v20; // rdx
  __int64 v21; // r14
  __int64 (__fastcall *v22)(__int64, _QWORD, __int64, __int64); // rsi
  __int64 v23; // rdi
  __int64 v24; // rbx
  __int64 v25; // rax
  int v27; // [rsp+20h] [rbp-E0h]
  __int64 v28; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v29; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t *EndPtr; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v31; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v32[3]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v33; // [rsp+78h] [rbp-88h] BYREF
  __int64 v34; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v35[16]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v36; // [rsp+98h] [rbp-68h]
  HSTRING string; // [rsp+A8h] [rbp-58h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v39[32]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v40[32]; // [rsp+E8h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  std::wstring::wstring(v35, a3);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::ConsentPromptLockEntry>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::ConsentPromptLockEntry>>>>>>(v32);
  v4 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v35);
  for ( i = 0; ; i = v7 )
  {
    v9 = std::_Traits_find_not_ch<std::char_traits<unsigned short>>(v4, v36, i);
    if ( v9 == -1 )
      break;
    v6 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v35);
    v7 = std::_Traits_find_ch<std::char_traits<unsigned short>>(v6, v36, v9);
    v8 = std::wstring::substr(v35, &string, v9, v7 - v9);
    std::vector<std::wstring>::emplace_back<std::wstring>(v32, v8);
    std::wstring::_Tidy_deallocate(&string);
    v4 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v35);
  }
  if ( v32[1] - v32[0] != 192 )
  {
    v10 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12D,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\toasthelper.cpp",
      (const char *)0x8000FFFFLL,
      v27);
LABEL_19:
    std::vector<std::wstring>::_Tidy(v32);
    std::wstring::_Tidy_deallocate(v35);
    return v10;
  }
  v11 = (unsigned int)std::wstring::compare(v32[0], L"Expected") != 0 ? 1 : 3;
  v12 = v32[0];
  v34 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v32[0] + 32LL);
  v31 = (unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v12 + 64);
  v33 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v12 + 96);
  v13 = (_DWORD *)_o__errno();
  v14 = (const wchar_t *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v12 + 128);
  EndPtr = 0;
  *v13 = 0;
  v15 = wcstol(v14, &EndPtr, 10);
  if ( v14 == EndPtr )
  {
    std::_Xinvalid_argument("invalid stoi argument");
    __debugbreak();
  }
  if ( *v13 == 34 )
  {
    std::_Xout_of_range("stoi argument out of range");
    __debugbreak();
  }
  v16 = (v15 != 1) + 1;
  v17 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v32[0] + 160LL);
  v29 = 0;
  v28 = 0;
  if ( WindowsCreateStringReference(
         L"Windows.Internal.CapabilityAccess.UsageHistory.CapabilityUsageHistoryAnnotator",
         0x4Eu,
         &hstringHeader,
         &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v18 = string;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
  ActivationFactory = RoGetActivationFactory(v18, &GUID_34361fc1_c278_4f20_9b8c_851544977b90, &v28);
  v10 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v20 = 312;
LABEL_18:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\toasthelper.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v27);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
    goto LABEL_19;
  }
  v21 = v28;
  v22 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64))(*(_QWORD *)v28 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
  v23 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(&string, &v33) + 24);
  v24 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(v39, &v31) + 24);
  v25 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v40, &v34);
  v27 = v16;
  ActivationFactory = v22(v21, *(_QWORD *)(v25 + 24), v24, v23);
  v10 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v20 = 314;
    goto LABEL_18;
  }
  ActivationFactory = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v29 + 48LL))(v29, v11);
  v10 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v20 = 317;
    goto LABEL_18;
  }
  CapabilityAccessTelemetry::LogUserAnnotatedLabel(v17, v31, v11 >> 1);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
  std::vector<std::wstring>::_Tidy(v32);
  std::wstring::_Tidy_deallocate(v35);
  return 0;
}

```

## disassembly

```asm
0x180062880  push    rbp
0x180062882  push    rbx
0x180062883  push    rsi
0x180062884  push    rdi
0x180062885  push    r12
0x180062887  push    r13
0x180062889  push    r14
0x18006288b  push    r15
0x18006288d  lea     rbp, [rsp-18h]
0x180062892  sub     rsp, 118h
0x180062899  mov     rax, cs:__security_cookie
0x1800628a0  xor     rax, rsp
0x1800628a3  mov     [rbp+50h+var_48], rax
0x1800628a7  mov     rdx, r8
0x1800628aa  lea     rcx, [rbp+50h+var_C8]
0x1800628ae  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800628b3  nop
0x1800628b4  lea     rcx, [rsp+150h+var_F0]
0x1800628b9  call    ??$?0AEBV?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VConsentPromptLockEntry@Private@CapabilityAccess@Internal@Windows@@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VConsentPromptLockEntry@Private@CapabilityAccess@Internal@Windows@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@AEBV?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VConsentPromptLockEntry@Private@CapabilityAccess@Internal@Windows@@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::ConsentPromptLockEntry>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::ConsentPromptLockEntry>>>>>>(std::allocator<std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::ConsentPromptLockEntry>> const &)
0x1800628be  nop
0x1800628bf  lea     rcx, [rbp+50h+var_C8]
0x1800628c3  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800628c8  xor     r8d, r8d
0x1800628cb  jmp     short loc_180062922
0x1800628cd  lea     rcx, [rbp+50h+var_C8]
0x1800628d1  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800628d6  mov     rcx, rax
0x1800628d9  mov     r8, rdi
0x1800628dc  mov     rdx, [rbp+50h+var_B8]
0x1800628e0  call    ??$_Traits_find_ch@U?$char_traits@G@std@@@std@@YA_KQEBG_K1G@Z; std::_Traits_find_ch<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x1800628e5  mov     rbx, rax
0x1800628e8  mov     r9, rax
0x1800628eb  sub     r9, rdi
0x1800628ee  mov     r8, rdi
0x1800628f1  lea     rdx, [rbp+50h+string]
0x1800628f5  lea     rcx, [rbp+50h+var_C8]
0x1800628f9  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x1800628fe  nop
0x1800628ff  mov     rdx, rax
0x180062902  lea     rcx, [rsp+150h+var_F0]
0x180062907  call    ??$emplace_back@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::emplace_back<std::wstring>(std::wstring &&)
0x18006290c  nop
0x18006290d  lea     rcx, [rbp+50h+string]
0x180062911  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180062916  lea     rcx, [rbp+50h+var_C8]
0x18006291a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18006291f  mov     r8, rbx
0x180062922  mov     rdx, [rbp+50h+var_B8]
0x180062926  mov     rcx, rax
0x180062929  call    ??$_Traits_find_not_ch@U?$char_traits@G@std@@@std@@YA_KQEBG_K1G@Z; std::_Traits_find_not_ch<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x18006292e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180062932  mov     rdi, rax
0x180062935  jnz     short loc_1800628CD
0x180062937  mov     rcx, [rsp+150h+var_F0]
0x18006293c  mov     rax, [rsp+150h+var_E8]
0x180062941  sub     rax, rcx
0x180062944  cmp     rax, 0C0h
0x18006294a  jz      short loc_18006296E
0x18006294c  mov     rcx, [rbp+58h]; this
0x180062950  mov     ebx, 8000FFFFh
0x180062955  mov     r9d, ebx; char *
0x180062958  lea     r8, aOnecoreBaseDev_42; "onecore\\base\\devices\\cam\\core\\toas"...
0x18006295f  mov     edx, 12Dh; void *
0x180062964  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180062969  jmp     loc_180062B6E
0x18006296e  lea     rdx, aExpected; "Expected"
0x180062975  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHQEBG@Z; std::wstring::compare(ushort const * const)
0x18006297a  neg     eax
0x18006297c  sbb     r15d, r15d
0x18006297f  and     r15d, 0FFFFFFFEh
0x180062983  add     r15d, 3
0x180062987  mov     rbx, [rsp+150h+var_F0]
0x18006298c  lea     rcx, [rbx+20h]
0x180062990  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180062995  mov     [rbp+50h+var_D0], rax
0x180062999  lea     rcx, [rbx+40h]
0x18006299d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800629a2  mov     [rsp+150h+var_F8], rax
0x1800629a7  lea     rcx, [rbx+60h]
0x1800629ab  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800629b0  mov     [rsp+150h+var_D8], rax
0x1800629b5  call    cs:__imp__o__errno
0x1800629bb  mov     rdi, rax
0x1800629be  lea     rcx, [rbx+80h]
0x1800629c5  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800629ca  mov     rbx, rax
0x1800629cd  xor     esi, esi
0x1800629cf  mov     [rsp+150h+EndPtr], rsi
0x1800629d4  mov     [rdi], esi
0x1800629d6  lea     r8d, [rsi+0Ah]; Radix
0x1800629da  lea     rdx, [rsp+150h+EndPtr]; EndPtr
0x1800629df  mov     rcx, rax; String
0x1800629e2  call    cs:__imp_wcstol
0x1800629e8  cmp     rbx, [rsp+150h+EndPtr]
0x1800629ed  jnz     short loc_1800629FD
0x1800629ef  lea     rcx, aInvalidStoiArg; "invalid stoi argument"
0x1800629f6  call    cs:__imp_?_Xinvalid_argument@std@@YAXPEBD@Z; std::_Xinvalid_argument(char const *)
0x1800629fc  int     3; Trap to Debugger
0x1800629fd  cmp     dword ptr [rdi], 22h ; '"'
0x180062a00  jnz     short loc_180062A10
0x180062a02  lea     rcx, aStoiArgumentOu; "stoi argument out of range"
0x180062a09  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x180062a0f  int     3; Trap to Debugger
0x180062a10  mov     r12d, esi
0x180062a13  cmp     eax, 1
0x180062a16  setnz   r12b
0x180062a1a  inc     r12d
0x180062a1d  mov     rcx, [rsp+150h+var_F0]
0x180062a22  add     rcx, 0A0h
0x180062a29  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180062a2e  mov     r13, rax
0x180062a31  mov     [rsp+150h+var_108], rsi
0x180062a36  mov     [rsp+150h+var_110], rsi
0x180062a3b  lea     r9, [rbp+50h+string]; string
0x180062a3f  lea     r8, [rbp+50h+hstringHeader]; hstringHeader
0x180062a43  mov     edx, 4Eh ; 'N'; length
0x180062a48  lea     rcx, ?RuntimeClass_Windows_Internal_CapabilityAccess_UsageHistory_CapabilityUsageHistoryAnnotator@@3QBGB; "Windows.Internal.CapabilityAccess.Usage"...
0x180062a4f  call    cs:__imp_WindowsCreateStringReference
0x180062a55  test    eax, eax
0x180062a57  jns     short loc_180062A6E
0x180062a59  xor     r9d, r9d; lpArguments
0x180062a5c  xor     r8d, r8d; nNumberOfArguments
0x180062a5f  lea     edx, [r9+1]; dwExceptionFlags
0x180062a63  mov     ecx, 0C000000Dh; dwExceptionCode
0x180062a68  call    cs:__imp_RaiseException
0x180062a6e  mov     rbx, [rbp+50h+string]
0x180062a72  lea     rcx, [rsp+150h+var_110]
0x180062a77  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180062a7c  lea     r8, [rsp+150h+var_110]
0x180062a81  lea     rdx, _GUID_34361fc1_c278_4f20_9b8c_851544977b90
0x180062a88  mov     rcx, rbx
0x180062a8b  call    cs:__imp_RoGetActivationFactory
0x180062a91  mov     ebx, eax
0x180062a93  test    eax, eax
0x180062a95  jns     short loc_180062AA1
0x180062a97  mov     edx, 138h
0x180062a9c  jmp     loc_180062B44
0x180062aa1  mov     r14, [rsp+150h+var_110]
0x180062aa6  mov     rax, [r14]
0x180062aa9  mov     rsi, [rax+30h]
0x180062aad  lea     rcx, [rsp+150h+var_108]
0x180062ab2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180062ab7  lea     rdx, [rsp+150h+var_D8]
0x180062abc  lea     rcx, [rbp+50h+string]
0x180062ac0  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180062ac5  nop
0x180062ac6  mov     rdi, [rax+18h]
0x180062aca  lea     rdx, [rsp+150h+var_F8]
0x180062acf  lea     rcx, [rbp+50h+var_88]
0x180062ad3  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180062ad8  nop
0x180062ad9  mov     rbx, [rax+18h]
0x180062add  lea     rdx, [rbp+50h+var_D0]
0x180062ae1  lea     rcx, [rbp+50h+var_68]
0x180062ae5  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180062aea  nop
0x180062aeb  lea     rcx, [rsp+150h+var_108]
0x180062af0  mov     [rsp+150h+var_120], rcx
0x180062af5  mov     [rsp+150h+var_128], 0
0x180062afe  mov     [rsp+150h+var_130], r12d; int
0x180062b03  mov     r9, rdi
0x180062b06  mov     r8, rbx
0x180062b09  mov     rdx, [rax+18h]
0x180062b0d  mov     rcx, r14
0x180062b10  mov     rax, rsi
0x180062b13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062b18  mov     ebx, eax
0x180062b1a  test    eax, eax
0x180062b1c  jns     short loc_180062B25
0x180062b1e  mov     edx, 13Ah
0x180062b23  jmp     short loc_180062B44
0x180062b25  mov     rcx, [rsp+150h+var_108]
0x180062b2a  mov     rax, [rcx]
0x180062b2d  mov     edx, r15d
0x180062b30  mov     rax, [rax+30h]
0x180062b34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062b39  mov     ebx, eax
0x180062b3b  test    eax, eax
0x180062b3d  jns     short loc_180062B86
0x180062b3f  mov     edx, 13Dh; void *
0x180062b44  mov     r9d, eax; char *
0x180062b47  lea     r8, aOnecoreBaseDev_42; "onecore\\base\\devices\\cam\\core\\toas"...
0x180062b4e  mov     rcx, [rbp+58h]; this
0x180062b52  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180062b57  nop
0x180062b58  lea     rcx, [rsp+150h+var_110]
0x180062b5d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180062b62  nop
0x180062b63  lea     rcx, [rsp+150h+var_108]
0x180062b68  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180062b6d  nop
0x180062b6e  lea     rcx, [rsp+150h+var_F0]
0x180062b73  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180062b78  nop
0x180062b79  lea     rcx, [rbp+50h+var_C8]
0x180062b7d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180062b82  mov     eax, ebx
0x180062b84  jmp     short loc_180062BC6
0x180062b86  shr     r15d, 1
0x180062b89  mov     r8d, r15d; int
0x180062b8c  mov     rdx, [rsp+150h+var_F8]; unsigned __int16 *
0x180062b91  mov     rcx, r13; unsigned __int16 *
0x180062b94  call    ?LogUserAnnotatedLabel@CapabilityAccessTelemetry@@SAXPEBG0H@Z; CapabilityAccessTelemetry::LogUserAnnotatedLabel(ushort const *,ushort const *,int)
0x180062b99  nop
0x180062b9a  lea     rcx, [rsp+150h+var_110]
0x180062b9f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180062ba4  nop
0x180062ba5  lea     rcx, [rsp+150h+var_108]
0x180062baa  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180062baf  nop
0x180062bb0  lea     rcx, [rsp+150h+var_F0]
0x180062bb5  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180062bba  nop
0x180062bbb  lea     rcx, [rbp+50h+var_C8]
0x180062bbf  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180062bc4  xor     eax, eax
0x180062bc6  mov     rcx, [rbp+50h+var_48]
0x180062bca  xor     rcx, rsp; StackCookie
0x180062bcd  call    __security_check_cookie
0x180062bd2  add     rsp, 118h
0x180062bd9  pop     r15
0x180062bdb  pop     r14
0x180062bdd  pop     r13
0x180062bdf  pop     r12
0x180062be1  pop     rdi
0x180062be2  pop     rsi
0x180062be3  pop     rbx
0x180062be4  pop     rbp
0x180062be5  retn
```
