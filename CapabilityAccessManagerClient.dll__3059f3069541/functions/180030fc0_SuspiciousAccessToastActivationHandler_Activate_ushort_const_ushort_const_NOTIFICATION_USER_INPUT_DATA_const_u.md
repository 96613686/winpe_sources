# SuspiciousAccessToastActivationHandler::Activate(ushort const *,ushort const *,NOTIFICATION_USER_INPUT_DATA const *,ulong)

- ea: `0x180030fc0`
- end: `0x180031326`
- name: `?Activate@SuspiciousAccessToastActivationHandler@@UEAAJPEBG0PEBUNOTIFICATION_USER_INPUT_DATA@@K@Z`
- size: `870`
- prototype: `__int64 __fastcall(SuspiciousAccessToastActivationHandler *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const struct NOTIFICATION_USER_INPUT_DATA *, unsigned int)`
- caller_count: `0`
- callee_count: `17`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003c80`
- `0x18000a248`
- `0x18000c6c8`
- `0x18000e21c`
- `0x18000f9e4`
- `0x180011e44`
- `0x18001b444`
- `0x1800205b8`
- `0x18002392c`
- `0x180023c34`
- `0x180028580`
- `0x180028ddc`
- `0x18002f3cc`
- `0x180030f6c`
- `0x180030fc0`
- `0x18003132c`
- `0x180039010`

## import_xrefs

- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180031149`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180031149`
- `msvcp_win!?_Xinvalid_argument@std@@YAXPEBD@Z` at `0x180031136`
- `msvcp_win!?_Xinvalid_argument@std@@YAXPEBD@Z` at `0x180031136`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x180031122`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x180031122`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800310f5`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800310f5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800311a8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800311a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003118f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003118f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800311cb`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800311cb`

## string_xrefs

- `0x180031188`: `Windows.Internal.CapabilityAccess.UsageHistory.CapabilityUsageHistoryAnnotator`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall SuspiciousAccessToastActivationHandler::Activate(
        SuspiciousAccessToastActivationHandler *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const struct NOTIFICATION_USER_INPUT_DATA *a4)
{
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // r9
  __int64 v7; // rax
  __int64 i; // r8
  __int64 v9; // rax
  __int64 v10; // rbx
  __int64 v11; // rax
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // rdx
  __int64 v16; // rdi
  __int64 v17; // r8
  __int64 v18; // r9
  unsigned int v19; // ebx
  unsigned int v20; // r15d
  __int64 v21; // rbx
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // r9
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // r9
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 v30; // r9
  _DWORD *v31; // rdi
  __int64 v32; // rdx
  __int64 v33; // r8
  __int64 v34; // r9
  const wchar_t *v35; // rbx
  int v36; // eax
  __int64 v37; // rdx
  __int64 v38; // r8
  __int64 v39; // r9
  int v40; // r12d
  const unsigned __int16 *v41; // r13
  HSTRING v42; // rbx
  int ActivationFactory; // eax
  __int64 v44; // rdx
  __int64 v45; // r14
  __int64 (__fastcall *v46)(__int64, _QWORD, __int64, __int64); // rsi
  __int64 v47; // rdi
  __int64 v48; // rbx
  __int64 v49; // rax
  int v51; // [rsp+20h] [rbp-E0h]
  __int64 v52; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v53; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t *EndPtr; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v55; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v56[3]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v57; // [rsp+78h] [rbp-88h] BYREF
  __int64 v58; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v59[16]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v60; // [rsp+98h] [rbp-68h]
  HSTRING string; // [rsp+A8h] [rbp-58h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v63[32]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v64[32]; // [rsp+E8h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  std::wstring::wstring((__int64)v59, (__int64)a3);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::ConsentPromptLockEntry>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::ConsentPromptLockEntry>>>>>>(v56);
  v7 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v59, v4, v5, v6);
  for ( i = 0; ; i = v10 )
  {
    v16 = std::_Traits_find_not_ch<std::char_traits<unsigned short>>(v7, v60, i);
    if ( v16 == -1 )
      break;
    v9 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v59, v15, v17, v18);
    v10 = std::_Traits_find_ch<std::char_traits<unsigned short>>(v9, v60, v16);
    v11 = std::wstring::substr(v59, &string, v16, v10 - v16);
    std::vector<std::wstring>::emplace_back<std::wstring>(v56, v11);
    std::wstring::_Tidy_deallocate(&string);
    v7 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v59, v12, v13, v14);
  }
  if ( v56[1] - v56[0] != 192 )
  {
    v19 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12D,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\toasthelper.cpp",
      (const char *)0x8000FFFFLL,
      v51);
LABEL_19:
    std::vector<std::wstring>::_Tidy(v56);
    std::wstring::_Tidy_deallocate(v59);
    return v19;
  }
  v20 = (unsigned int)std::wstring::compare(v56[0], L"Expected") != 0 ? 1 : 3;
  v21 = v56[0];
  v58 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v56[0] + 32LL, v22, v23, v24);
  v55 = (unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v21 + 64, v25, v26, v27);
  v57 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v21 + 96, v28, v29, v30);
  v31 = (_DWORD *)_o__errno();
  v35 = (const wchar_t *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v21 + 128, v32, v33, v34);
  EndPtr = 0;
  *v31 = 0;
  v36 = wcstol(v35, &EndPtr, 10);
  if ( v35 == EndPtr )
  {
    std::_Xinvalid_argument("invalid stoi argument");
    __debugbreak();
  }
  if ( *v31 == 34 )
  {
    std::_Xout_of_range("stoi argument out of range");
    __debugbreak();
  }
  v40 = (v36 != 1) + 1;
  v41 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(
                                    v56[0] + 160LL,
                                    v37,
                                    v38,
                                    v39);
  v53 = 0;
  v52 = 0;
  if ( WindowsCreateStringReference(
         L"Windows.Internal.CapabilityAccess.UsageHistory.CapabilityUsageHistoryAnnotator",
         0x4Eu,
         &hstringHeader,
         &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v42 = string;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v52);
  ActivationFactory = RoGetActivationFactory(v42, &GUID_34361fc1_c278_4f20_9b8c_851544977b90, &v52);
  v19 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v44 = 312;
LABEL_18:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v44,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\toasthelper.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v51);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v52);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v53);
    goto LABEL_19;
  }
  v45 = v52;
  v46 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64))(*(_QWORD *)v52 + 48LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v53);
  v47 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(&string, &v57) + 24);
  v48 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(v63, &v55) + 24);
  v49 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v64, &v58);
  v51 = v40;
  ActivationFactory = v46(v45, *(_QWORD *)(v49 + 24), v48, v47);
  v19 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v44 = 314;
    goto LABEL_18;
  }
  ActivationFactory = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v53 + 48LL))(v53, v20);
  v19 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v44 = 317;
    goto LABEL_18;
  }
  CapabilityAccessTelemetry::LogUserAnnotatedLabel(v41, v55, v20 >> 1);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v52);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v53);
  std::vector<std::wstring>::_Tidy(v56);
  std::wstring::_Tidy_deallocate(v59);
  return 0;
}

```

## disassembly

```asm
0x180030fc0  push    rbp
0x180030fc2  push    rbx
0x180030fc3  push    rsi
0x180030fc4  push    rdi
0x180030fc5  push    r12
0x180030fc7  push    r13
0x180030fc9  push    r14
0x180030fcb  push    r15
0x180030fcd  lea     rbp, [rsp-18h]
0x180030fd2  sub     rsp, 118h
0x180030fd9  mov     rax, cs:__security_cookie
0x180030fe0  xor     rax, rsp
0x180030fe3  mov     [rbp+50h+var_48], rax
0x180030fe7  mov     rdx, r8
0x180030fea  lea     rcx, [rbp+50h+var_C8]
0x180030fee  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180030ff3  nop
0x180030ff4  lea     rcx, [rsp+150h+var_F0]
0x180030ff9  call    ??$?0AEBV?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VConsentPromptLockEntry@Private@CapabilityAccess@Internal@Windows@@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VConsentPromptLockEntry@Private@CapabilityAccess@Internal@Windows@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@AEBV?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VConsentPromptLockEntry@Private@CapabilityAccess@Internal@Windows@@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::ConsentPromptLockEntry>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::ConsentPromptLockEntry>>>>>>(std::allocator<std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::ConsentPromptLockEntry>> const &)
0x180030ffe  nop
0x180030fff  lea     rcx, [rbp+50h+var_C8]
0x180031003  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180031008  xor     r8d, r8d
0x18003100b  jmp     short loc_180031062
0x18003100d  lea     rcx, [rbp+50h+var_C8]
0x180031011  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180031016  mov     rcx, rax
0x180031019  mov     r8, rdi
0x18003101c  mov     rdx, [rbp+50h+var_B8]
0x180031020  call    ??$_Traits_find_ch@U?$char_traits@G@std@@@std@@YA_KQEBG_K1G@Z; std::_Traits_find_ch<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x180031025  mov     rbx, rax
0x180031028  mov     r9, rax
0x18003102b  sub     r9, rdi
0x18003102e  mov     r8, rdi
0x180031031  lea     rdx, [rbp+50h+string]
0x180031035  lea     rcx, [rbp+50h+var_C8]
0x180031039  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x18003103e  nop
0x18003103f  mov     rdx, rax
0x180031042  lea     rcx, [rsp+150h+var_F0]
0x180031047  call    ??$emplace_back@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::emplace_back<std::wstring>(std::wstring &&)
0x18003104c  nop
0x18003104d  lea     rcx, [rbp+50h+string]
0x180031051  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180031056  lea     rcx, [rbp+50h+var_C8]
0x18003105a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003105f  mov     r8, rbx
0x180031062  mov     rdx, [rbp+50h+var_B8]
0x180031066  mov     rcx, rax
0x180031069  call    ??$_Traits_find_not_ch@U?$char_traits@G@std@@@std@@YA_KQEBG_K1G@Z; std::_Traits_find_not_ch<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x18003106e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180031072  mov     rdi, rax
0x180031075  jnz     short loc_18003100D
0x180031077  mov     rcx, [rsp+150h+var_F0]
0x18003107c  mov     rax, [rsp+150h+var_E8]
0x180031081  sub     rax, rcx
0x180031084  cmp     rax, 0C0h
0x18003108a  jz      short loc_1800310AE
0x18003108c  mov     rcx, [rbp+58h]; this
0x180031090  mov     ebx, 8000FFFFh
0x180031095  mov     r9d, ebx; char *
0x180031098  lea     r8, aOnecoreBaseDev_9; "onecore\\base\\devices\\cam\\core\\toas"...
0x18003109f  mov     edx, 12Dh; void *
0x1800310a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800310a9  jmp     loc_1800312AE
0x1800310ae  lea     rdx, aExpected; "Expected"
0x1800310b5  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHQEBG@Z; std::wstring::compare(ushort const * const)
0x1800310ba  neg     eax
0x1800310bc  sbb     r15d, r15d
0x1800310bf  and     r15d, 0FFFFFFFEh
0x1800310c3  add     r15d, 3
0x1800310c7  mov     rbx, [rsp+150h+var_F0]
0x1800310cc  lea     rcx, [rbx+20h]
0x1800310d0  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800310d5  mov     [rbp+50h+var_D0], rax
0x1800310d9  lea     rcx, [rbx+40h]
0x1800310dd  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800310e2  mov     [rsp+150h+var_F8], rax
0x1800310e7  lea     rcx, [rbx+60h]
0x1800310eb  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800310f0  mov     [rsp+150h+var_D8], rax
0x1800310f5  call    cs:__imp__o__errno
0x1800310fb  mov     rdi, rax
0x1800310fe  lea     rcx, [rbx+80h]
0x180031105  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003110a  mov     rbx, rax
0x18003110d  xor     esi, esi
0x18003110f  mov     [rsp+150h+EndPtr], rsi
0x180031114  mov     [rdi], esi
0x180031116  lea     r8d, [rsi+0Ah]; Radix
0x18003111a  lea     rdx, [rsp+150h+EndPtr]; EndPtr
0x18003111f  mov     rcx, rax; String
0x180031122  call    cs:__imp_wcstol
0x180031128  cmp     rbx, [rsp+150h+EndPtr]
0x18003112d  jnz     short loc_18003113D
0x18003112f  lea     rcx, aInvalidStoiArg; "invalid stoi argument"
0x180031136  call    cs:__imp_?_Xinvalid_argument@std@@YAXPEBD@Z; std::_Xinvalid_argument(char const *)
0x18003113c  int     3; Trap to Debugger
0x18003113d  cmp     dword ptr [rdi], 22h ; '"'
0x180031140  jnz     short loc_180031150
0x180031142  lea     rcx, aStoiArgumentOu; "stoi argument out of range"
0x180031149  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x18003114f  int     3; Trap to Debugger
0x180031150  mov     r12d, esi
0x180031153  cmp     eax, 1
0x180031156  setnz   r12b
0x18003115a  inc     r12d
0x18003115d  mov     rcx, [rsp+150h+var_F0]
0x180031162  add     rcx, 0A0h
0x180031169  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003116e  mov     r13, rax
0x180031171  mov     [rsp+150h+var_108], rsi
0x180031176  mov     [rsp+150h+var_110], rsi
0x18003117b  lea     r9, [rbp+50h+string]; string
0x18003117f  lea     r8, [rbp+50h+hstringHeader]; hstringHeader
0x180031183  mov     edx, 4Eh ; 'N'; length
0x180031188  lea     rcx, ?RuntimeClass_Windows_Internal_CapabilityAccess_UsageHistory_CapabilityUsageHistoryAnnotator@@3QBGB; "Windows.Internal.CapabilityAccess.Usage"...
0x18003118f  call    cs:__imp_WindowsCreateStringReference
0x180031195  test    eax, eax
0x180031197  jns     short loc_1800311AE
0x180031199  xor     r9d, r9d; lpArguments
0x18003119c  xor     r8d, r8d; nNumberOfArguments
0x18003119f  lea     edx, [r9+1]; dwExceptionFlags
0x1800311a3  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800311a8  call    cs:__imp_RaiseException
0x1800311ae  mov     rbx, [rbp+50h+string]
0x1800311b2  lea     rcx, [rsp+150h+var_110]
0x1800311b7  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800311bc  lea     r8, [rsp+150h+var_110]
0x1800311c1  lea     rdx, _GUID_34361fc1_c278_4f20_9b8c_851544977b90
0x1800311c8  mov     rcx, rbx
0x1800311cb  call    cs:__imp_RoGetActivationFactory
0x1800311d1  mov     ebx, eax
0x1800311d3  test    eax, eax
0x1800311d5  jns     short loc_1800311E1
0x1800311d7  mov     edx, 138h
0x1800311dc  jmp     loc_180031284
0x1800311e1  mov     r14, [rsp+150h+var_110]
0x1800311e6  mov     rax, [r14]
0x1800311e9  mov     rsi, [rax+30h]
0x1800311ed  lea     rcx, [rsp+150h+var_108]
0x1800311f2  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800311f7  lea     rdx, [rsp+150h+var_D8]
0x1800311fc  lea     rcx, [rbp+50h+string]
0x180031200  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180031205  nop
0x180031206  mov     rdi, [rax+18h]
0x18003120a  lea     rdx, [rsp+150h+var_F8]
0x18003120f  lea     rcx, [rbp+50h+var_88]
0x180031213  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180031218  nop
0x180031219  mov     rbx, [rax+18h]
0x18003121d  lea     rdx, [rbp+50h+var_D0]
0x180031221  lea     rcx, [rbp+50h+var_68]
0x180031225  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18003122a  nop
0x18003122b  lea     rcx, [rsp+150h+var_108]
0x180031230  mov     [rsp+150h+var_120], rcx
0x180031235  mov     [rsp+150h+var_128], 0
0x18003123e  mov     [rsp+150h+var_130], r12d; int
0x180031243  mov     r9, rdi
0x180031246  mov     r8, rbx
0x180031249  mov     rdx, [rax+18h]
0x18003124d  mov     rcx, r14
0x180031250  mov     rax, rsi
0x180031253  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031258  mov     ebx, eax
0x18003125a  test    eax, eax
0x18003125c  jns     short loc_180031265
0x18003125e  mov     edx, 13Ah
0x180031263  jmp     short loc_180031284
0x180031265  mov     rcx, [rsp+150h+var_108]
0x18003126a  mov     rax, [rcx]
0x18003126d  mov     edx, r15d
0x180031270  mov     rax, [rax+30h]
0x180031274  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031279  mov     ebx, eax
0x18003127b  test    eax, eax
0x18003127d  jns     short loc_1800312C6
0x18003127f  mov     edx, 13Dh; void *
0x180031284  mov     r9d, eax; char *
0x180031287  lea     r8, aOnecoreBaseDev_9; "onecore\\base\\devices\\cam\\core\\toas"...
0x18003128e  mov     rcx, [rbp+58h]; this
0x180031292  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031297  nop
0x180031298  lea     rcx, [rsp+150h+var_110]
0x18003129d  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800312a2  nop
0x1800312a3  lea     rcx, [rsp+150h+var_108]
0x1800312a8  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800312ad  nop
0x1800312ae  lea     rcx, [rsp+150h+var_F0]
0x1800312b3  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800312b8  nop
0x1800312b9  lea     rcx, [rbp+50h+var_C8]
0x1800312bd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800312c2  mov     eax, ebx
0x1800312c4  jmp     short loc_180031306
0x1800312c6  shr     r15d, 1
0x1800312c9  mov     r8d, r15d; int
0x1800312cc  mov     rdx, [rsp+150h+var_F8]; unsigned __int16 *
0x1800312d1  mov     rcx, r13; unsigned __int16 *
0x1800312d4  call    ?LogUserAnnotatedLabel@CapabilityAccessTelemetry@@SAXPEBG0H@Z; CapabilityAccessTelemetry::LogUserAnnotatedLabel(ushort const *,ushort const *,int)
0x1800312d9  nop
0x1800312da  lea     rcx, [rsp+150h+var_110]
0x1800312df  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800312e4  nop
0x1800312e5  lea     rcx, [rsp+150h+var_108]
0x1800312ea  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800312ef  nop
0x1800312f0  lea     rcx, [rsp+150h+var_F0]
0x1800312f5  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800312fa  nop
0x1800312fb  lea     rcx, [rbp+50h+var_C8]
0x1800312ff  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180031304  xor     eax, eax
0x180031306  mov     rcx, [rbp+50h+var_48]
0x18003130a  xor     rcx, rsp; StackCookie
0x18003130d  call    __security_check_cookie
0x180031312  add     rsp, 118h
0x180031319  pop     r15
0x18003131b  pop     r14
0x18003131d  pop     r13
0x18003131f  pop     r12
0x180031321  pop     rdi
0x180031322  pop     rsi
0x180031323  pop     rbx
0x180031324  pop     rbp
0x180031325  retn
```
