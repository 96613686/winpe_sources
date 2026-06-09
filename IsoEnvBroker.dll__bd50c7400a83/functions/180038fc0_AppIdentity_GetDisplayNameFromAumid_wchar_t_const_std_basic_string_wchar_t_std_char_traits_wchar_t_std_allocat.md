# AppIdentity::GetDisplayNameFromAumid(wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x180038fc0`
- end: `0x180039763`
- name: `?GetDisplayNameFromAumid@AppIdentity@@CAJPEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `1955`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18003976c`

## callees

- `0x180002520`
- `0x180002a54`
- `0x1800050cd`
- `0x18000a464`
- `0x180010148`
- `0x180010240`
- `0x180013270`
- `0x1800138a8`
- `0x180028aa0`
- `0x180038fc0`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003906c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039090`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003906c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039090`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003907f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003907f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180039124`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180039258`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800393b4`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180039124`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180039258`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800393b4`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18003902c`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18003902c`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180038ff1`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180038ff1`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18003904d`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18003904d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039564`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039654`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039564`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039654`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180039107`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800391ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003923b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180039397`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180039107`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800391ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003923b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180039397`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800395fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800395fa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039077`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800390ae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800396e8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039077`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800390ae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800396e8`

## string_xrefs

- `0x180039719`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x18003972e`: `onecore\internal\sdk\inc\wil\opensource/wil/result_macros.h`
- `0x180039137`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\appidentity.cpp`
- `0x1800391dc`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\appidentity.cpp`
- `0x18003926b`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\appidentity.cpp`
- `0x18003930c`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\appidentity.cpp`
- `0x1800393cb`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\appidentity.cpp`
- `0x180039481`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\appidentity.cpp`
- `0x180039549`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\appidentity.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
__int64 __fastcall AppIdentity::GetDisplayNameFromAumid(const WCHAR *a1, __int64 a2)
{
  HRESULT v3; // eax
  wil::details::in1diag3 *v4; // rcx
  int token_information; // eax
  PSID *v6; // rsi
  BOOL v7; // r13d
  __int64 v8; // r12
  _QWORD *Reserved1; // rdi
  void *v10; // r14
  DWORD LastError; // ebx
  signed int v12; // eax
  unsigned int v13; // ebx
  HRESULT v15; // eax
  int v16; // edx
  unsigned int v17; // r8d
  int ActivationFactory; // eax
  unsigned int v19; // r8d
  __int64 *v20; // rbx
  __int64 v21; // rdi
  unsigned __int64 v22; // r14
  unsigned __int64 v23; // rdx
  HRESULT v24; // eax
  int v25; // edx
  unsigned int v26; // r8d
  int v27; // eax
  HRESULT v28; // eax
  int v29; // edx
  unsigned int v30; // r8d
  int v31; // eax
  unsigned int v32; // r8d
  __int64 v33; // rdi
  __int64 (__fastcall *v34)(__int64, __int64, PVOID, __int64 *); // rbx
  HSTRING_HEADER *v35; // rax
  int v36; // eax
  HRESULT v37; // eax
  int v38; // edx
  unsigned int v39; // r8d
  int v40; // eax
  __int64 v41; // rax
  int v42; // eax
  __int64 v43; // rax
  int v44; // eax
  PCWSTR StringRawBuffer; // rax
  __int64 v46; // r8
  char *v47; // rdi
  int v48; // [rsp+20h] [rbp-79h]
  HLOCAL hMem; // [rsp+30h] [rbp-69h] BYREF
  __int64 v50; // [rsp+38h] [rbp-61h] BYREF
  __int64 *v51; // [rsp+40h] [rbp-59h] BYREF
  __int64 v52; // [rsp+48h] [rbp-51h] BYREF
  __int64 v53; // [rsp+50h] [rbp-49h] BYREF
  __int64 *v54; // [rsp+58h] [rbp-41h] BYREF
  __int64 *v55; // [rsp+60h] [rbp-39h] BYREF
  HSTRING v56; // [rsp+68h] [rbp-31h] BYREF
  void *Block; // [rsp+70h] [rbp-29h] BYREF
  const WCHAR *v58; // [rsp+80h] [rbp-19h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+90h] [rbp-9h] BYREF
  HSTRING string; // [rsp+A8h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v58 = a1;
  v3 = CoImpersonateClient();
  v4 = retaddr;
  if ( v3 < 0 )
LABEL_122:
    wil::details::in1diag3::_FailFast_Hr(
      v4,
      (void *)0x14AA,
      (int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
      (const char *)(unsigned int)v3,
      v48);
  Block = 0;
  token_information = wil::get_token_information_nothrow<_TOKEN_USER,0>(&Block, -5);
  if ( token_information < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x1C9B,
      (int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/result_macros.h",
      (const char *)(unsigned int)token_information,
      v48);
  v6 = (PSID *)Block;
  CoRevertToSelf();
  hMem = 0;
  hstringHeader.Reserved.Reserved1 = &hMem;
  *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = 0;
  hstringHeader.Reserved.Reserved2[16] = 1;
  v7 = ConvertSidToStringSidW(*v6, (LPWSTR *)&hstringHeader.Reserved.Reserved2[8]);
  if ( hstringHeader.Reserved.Reserved2[16] )
  {
    v8 = *(_QWORD *)&hstringHeader.Reserved.Reserved2[8];
    Reserved1 = hstringHeader.Reserved.Reserved1;
    v10 = *(void **)hstringHeader.Reserved.Reserved1;
    if ( *(_QWORD *)hstringHeader.Reserved.Reserved1 )
    {
      LastError = GetLastError();
      LocalFree(v10);
      SetLastError(LastError);
    }
    *Reserved1 = v8;
  }
  if ( !v7 )
  {
    v12 = GetLastError();
    v13 = v12;
    if ( v12 > 0 )
      v13 = (unsigned __int16)v12 | 0x80070000;
LABEL_10:
    if ( hMem )
      LocalFree(hMem);
    if ( v6 )
      operator delete(v6);
    return v13;
  }
  v51 = 0;
  string = 0;
  v15 = WindowsCreateStringReference(L"Windows.Internal.StateRepository.User", 0x25u, &hstringHeader, &string);
  if ( v15 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v15, v16, v17);
    goto LABEL_125;
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_84103ccb_2fd7_4d6c_962e_5d8582b4c720, &v51);
  v13 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7B,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\appidentity.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v48);
    if ( v51 )
      (*(void (__fastcall **)(__int64 *))(*v51 + 16))(v51);
    goto LABEL_10;
  }
  v50 = 0;
  v20 = v51;
  v21 = *v51;
  v50 = 0;
  string = 0;
  v22 = -1;
  v23 = -1;
  do
    ++v23;
  while ( *((_WORD *)hMem + v23) );
  if ( v23 > 0xFFFFFFFF )
    goto LABEL_121;
  if ( (int)v23 + 1 < (unsigned int)v23 )
  {
LABEL_125:
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v23, v19);
    __debugbreak();
  }
  v24 = WindowsCreateStringReference((PCWSTR)hMem, v23, &hstringHeader, &string);
  if ( v24 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v24, v25, v26);
    goto LABEL_127;
  }
  v27 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, __int64 *))(v21 + 80))(v20, string, &v50);
  v13 = v27;
  if ( v27 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7E,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\appidentity.cpp",
      (const char *)(unsigned int)v27,
      v48);
    if ( v50 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
    if ( v51 )
      (*(void (__fastcall **)(__int64 *))(*v51 + 16))(v51);
    goto LABEL_10;
  }
  v53 = 0;
  string = 0;
  v28 = WindowsCreateStringReference(L"Windows.Internal.StateRepository.Application", 0x2Cu, &hstringHeader, &string);
  if ( v28 < 0 )
  {
LABEL_127:
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v28, v29, v30);
    JUMPOUT(0x180039762LL);
  }
  v31 = RoGetActivationFactory(string, &GUID_07adcc9a_e505_48c2_b471_45af8561f6af, &v53);
  v13 = v31;
  if ( v31 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x83,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\appidentity.cpp",
      (const char *)(unsigned int)v31,
      v48);
    if ( v53 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
    if ( v50 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
    if ( v51 )
      (*(void (__fastcall **)(__int64 *))(*v51 + 16))(v51);
    goto LABEL_10;
  }
  v52 = 0;
  v33 = v53;
  v34 = *(__int64 (__fastcall **)(__int64, __int64, PVOID, __int64 *))(*(_QWORD *)v53 + 240LL);
  v52 = 0;
  v35 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v58, v32);
  v36 = v34(v33, v50, v35[1].Reserved.Reserved1, &v52);
  v13 = v36;
  if ( v36 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x86,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\appidentity.cpp",
      (const char *)(unsigned int)v36,
      v48);
    if ( v52 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
    if ( v53 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
    if ( v50 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
    if ( v51 )
      (*(void (__fastcall **)(__int64 *))(*v51 + 16))(v51);
    goto LABEL_10;
  }
  v55 = 0;
  string = 0;
  v37 = WindowsCreateStringReference(
          L"Windows.Internal.StateRepository.ApplicationResourceResolver",
          0x3Cu,
          &hstringHeader,
          &string);
  if ( v37 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v37, v38, v39);
LABEL_121:
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v23, v19);
    goto LABEL_122;
  }
  v40 = RoGetActivationFactory(string, &GUID_84463b2a_c88e_4597_b41f_17d3bf6486e9, &v55);
  v13 = v40;
  if ( v40 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8B,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\appidentity.cpp",
      (const char *)(unsigned int)v40,
      v48);
    if ( v55 )
      (*(void (__fastcall **)(__int64 *))(*v55 + 16))(v55);
    if ( v52 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
    if ( v53 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
    if ( v50 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
    if ( v51 )
      (*(void (__fastcall **)(__int64 *))(*v51 + 16))(v51);
    goto LABEL_10;
  }
  v54 = 0;
  v41 = *v55;
  v54 = 0;
  v42 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64 **))(v41 + 48))(v55, v52, &v54);
  v13 = v42;
  if ( v42 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8E,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\appidentity.cpp",
      (const char *)(unsigned int)v42,
      v48);
    if ( v54 )
      (*(void (__fastcall **)(__int64 *))(*v54 + 16))(v54);
    if ( v55 )
      (*(void (__fastcall **)(__int64 *))(*v55 + 16))(v55);
    if ( v52 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
    if ( v53 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
    if ( v50 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
    if ( v51 )
      (*(void (__fastcall **)(__int64 *))(*v51 + 16))(v51);
    goto LABEL_10;
  }
  v56 = 0;
  v43 = *v54;
  v56 = 0;
  v44 = (*(__int64 (__fastcall **)(__int64 *, HSTRING *))(v43 + 48))(v54, &v56);
  v13 = v44;
  if ( v44 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x92,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\appidentity.cpp",
      (const char *)(unsigned int)v44,
      v48);
    if ( v56 )
      WindowsDeleteString(v56);
    if ( v54 )
      (*(void (__fastcall **)(__int64 *))(*v54 + 16))(v54);
    if ( v55 )
      (*(void (__fastcall **)(__int64 *))(*v55 + 16))(v55);
    if ( v52 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
    if ( v53 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
    if ( v50 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
    if ( v51 )
      (*(void (__fastcall **)(__int64 *))(*v51 + 16))(v51);
    goto LABEL_10;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(v56, 0);
  do
    ++v22;
  while ( StringRawBuffer[v22] );
  if ( v22 > *(_QWORD *)(a2 + 24) )
  {
    ____Reallocate_for_V_lambda_1___1_____Assign__W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV23_QEB_W_K_Z_PEB_W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign__W_01_AEAAAEAV01_QEB_W0_Z_PEB_W_Z(
      (char **)a2,
      v22,
      v46,
      StringRawBuffer);
  }
  else
  {
    if ( *(_QWORD *)(a2 + 24) <= 7u )
      v47 = (char *)a2;
    else
      v47 = *(char **)a2;
    *(_QWORD *)(a2 + 16) = v22;
    memmove_0(v47, StringRawBuffer, 2 * v22);
    *(_WORD *)&v47[2 * v22] = 0;
  }
  if ( v56 )
    WindowsDeleteString(v56);
  if ( v54 )
    (*(void (__fastcall **)(__int64 *))(*v54 + 16))(v54);
  if ( v55 )
    (*(void (__fastcall **)(__int64 *))(*v55 + 16))(v55);
  if ( v52 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
  if ( v53 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
  if ( v50 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
  if ( v51 )
    (*(void (__fastcall **)(__int64 *))(*v51 + 16))(v51);
  if ( hMem )
    LocalFree(hMem);
  if ( v6 )
    operator delete(v6);
  return 0;
}

```

## disassembly

```asm
0x180038fc0  mov     [rsp-8+arg_10], rbx
0x180038fc5  push    rbp
0x180038fc6  push    rsi
0x180038fc7  push    rdi
0x180038fc8  push    r12
0x180038fca  push    r13
0x180038fcc  push    r14
0x180038fce  push    r15
0x180038fd0  lea     rbp, [rsp-27h]
0x180038fd5  sub     rsp, 0C0h
0x180038fdc  mov     rax, cs:__security_cookie
0x180038fe3  xor     rax, rsp
0x180038fe6  mov     [rbp+57h+var_40], rax
0x180038fea  mov     r15, rdx
0x180038fed  mov     [rbp+57h+var_70], rcx
0x180038ff1  call    cs:__imp_CoImpersonateClient
0x180038ff7  mov     rcx, [rbp+5Fh]
0x180038ffb  xor     r12d, r12d
0x180038ffe  test    eax, eax
0x180039000  js      loc_180039716
0x180039006  mov     [rbp+57h+Block], r12
0x18003900a  lea     rdx, [r12-5]
0x18003900f  lea     rcx, [rbp+57h+Block]
0x180039013  call    ??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)
0x180039018  mov     rcx, [rbp+5Fh]; this
0x18003901c  test    eax, eax
0x18003901e  js      loc_18003972B
0x180039024  mov     rsi, [rbp+57h+Block]
0x180039028  mov     [rbp+57h+Block], rsi
0x18003902c  call    cs:__imp_CoRevertToSelf
0x180039032  mov     [rbp+57h+hMem], r12
0x180039036  lea     rax, [rbp+57h+hMem]
0x18003903a  mov     qword ptr [rbp+57h+hstringHeader.Reserved], rax
0x18003903e  mov     qword ptr [rbp+57h+hstringHeader.Reserved+8], r12
0x180039042  mov     byte ptr [rbp+57h+hstringHeader.Reserved+10h], 1
0x180039046  lea     rdx, [rbp+57h+hstringHeader.Reserved+8]; StringSid
0x18003904a  mov     rcx, [rsi]; Sid
0x18003904d  call    cs:__imp_ConvertSidToStringSidW
0x180039053  mov     r13d, eax
0x180039056  cmp     byte ptr [rbp+57h+hstringHeader.Reserved+10h], r12b
0x18003905a  jz      short loc_18003908B
0x18003905c  mov     r12, qword ptr [rbp+57h+hstringHeader.Reserved+8]
0x180039060  mov     rdi, qword ptr [rbp+57h+hstringHeader.Reserved]
0x180039064  mov     r14, [rdi]
0x180039067  test    r14, r14
0x18003906a  jz      short loc_180039085
0x18003906c  call    cs:__imp_GetLastError
0x180039072  mov     ebx, eax
0x180039074  mov     rcx, r14; hMem
0x180039077  call    cs:__imp_LocalFree
0x18003907d  mov     ecx, ebx; dwErrCode
0x18003907f  call    cs:__imp_SetLastError
0x180039085  mov     [rdi], r12
0x180039088  xor     r12d, r12d
0x18003908b  test    r13d, r13d
0x18003908e  jnz     short loc_1800390EB
0x180039090  call    cs:__imp_GetLastError
0x180039096  mov     ebx, eax
0x180039098  test    eax, eax
0x18003909a  jle     short loc_1800390A5
0x18003909c  movzx   ebx, ax
0x18003909f  or      ebx, 80070000h
0x1800390a5  mov     rcx, [rbp+57h+hMem]; hMem
0x1800390a9  test    rcx, rcx
0x1800390ac  jz      short loc_1800390B5
0x1800390ae  call    cs:__imp_LocalFree
0x1800390b4  nop
0x1800390b5  test    rsi, rsi
0x1800390b8  jz      short loc_1800390C2
0x1800390ba  mov     rcx, rsi; Block
0x1800390bd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800390c2  mov     eax, ebx
0x1800390c4  mov     rcx, [rbp+57h+var_40]
0x1800390c8  xor     rcx, rsp; StackCookie
0x1800390cb  call    __security_check_cookie
0x1800390d0  mov     rbx, [rsp+0F0h+arg_10]
0x1800390d8  add     rsp, 0C0h
0x1800390df  pop     r15
0x1800390e1  pop     r14
0x1800390e3  pop     r13
0x1800390e5  pop     r12
0x1800390e7  pop     rdi
0x1800390e8  pop     rsi
0x1800390e9  pop     rbp
0x1800390ea  retn
0x1800390eb  mov     [rbp+57h+var_B0], r12
0x1800390ef  mov     [rbp+57h+string], r12
0x1800390f3  lea     r9, [rbp+57h+string]; string
0x1800390f7  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800390fb  mov     edx, 25h ; '%'; length
0x180039100  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_User@@3QB_WB; "Windows.Internal.StateRepository.User"
0x180039107  call    cs:__imp_WindowsCreateStringReference
0x18003910d  test    eax, eax
0x18003910f  js      loc_180039740
0x180039115  lea     r8, [rbp+57h+var_B0]
0x180039119  lea     rdx, _GUID_84103ccb_2fd7_4d6c_962e_5d8582b4c720
0x180039120  mov     rcx, [rbp+57h+string]
0x180039124  call    cs:__imp_RoGetActivationFactory
0x18003912a  mov     ebx, eax
0x18003912c  test    eax, eax
0x18003912e  jns     short loc_180039164
0x180039130  mov     rcx, [rbp+5Fh]; this
0x180039134  mov     r9d, eax; char *
0x180039137  lea     r8, aOnecoreuapWind_0; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18003913e  mov     edx, 7Bh ; '{'; void *
0x180039143  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039148  nop
0x180039149  mov     rcx, [rbp+57h+var_B0]
0x18003914d  test    rcx, rcx
0x180039150  jz      short loc_18003915F
0x180039152  mov     rax, [rcx]
0x180039155  mov     rax, [rax+10h]
0x180039159  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003915e  nop
0x18003915f  jmp     loc_1800390A5
0x180039164  mov     [rbp+57h+var_B8], r12
0x180039168  mov     rbx, [rbp+57h+var_B0]
0x18003916c  mov     rdi, [rbx]
0x18003916f  mov     [rbp+57h+var_B8], r12
0x180039173  mov     [rbp+57h+string], r12
0x180039177  mov     rcx, [rbp+57h+hMem]; sourceString
0x18003917b  or      r14, 0FFFFFFFFFFFFFFFFh
0x18003917f  mov     rdx, r14
0x180039182  inc     rdx; length
0x180039185  cmp     [rcx+rdx*2], r12w
0x18003918a  jnz     short loc_180039182
0x18003918c  mov     eax, 0FFFFFFFFh
0x180039191  cmp     rdx, rax
0x180039194  ja      loc_18003970B
0x18003919a  lea     eax, [rdx+1]
0x18003919d  cmp     eax, edx
0x18003919f  jb      loc_180039748
0x1800391a5  lea     r9, [rbp+57h+string]; string
0x1800391a9  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800391ad  call    cs:__imp_WindowsCreateStringReference
0x1800391b3  test    eax, eax
0x1800391b5  js      loc_180039753
0x1800391bb  lea     r8, [rbp+57h+var_B8]
0x1800391bf  mov     rdx, [rbp+57h+string]
0x1800391c3  mov     rcx, rbx
0x1800391c6  mov     rax, [rdi+50h]
0x1800391ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800391cf  mov     ebx, eax
0x1800391d1  test    eax, eax
0x1800391d3  jns     short loc_18003921F
0x1800391d5  mov     rcx, [rbp+5Fh]; this
0x1800391d9  mov     r9d, eax; char *
0x1800391dc  lea     r8, aOnecoreuapWind_0; "onecoreuap\\windows\\core\\isoenvbroker"...
0x1800391e3  mov     edx, 7Eh ; '~'; void *
0x1800391e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800391ed  nop
0x1800391ee  mov     rcx, [rbp+57h+var_B8]
0x1800391f2  test    rcx, rcx
0x1800391f5  jz      short loc_180039204
0x1800391f7  mov     rax, [rcx]
0x1800391fa  mov     rax, [rax+10h]
0x1800391fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039203  nop
0x180039204  mov     rcx, [rbp+57h+var_B0]
0x180039208  test    rcx, rcx
0x18003920b  jz      short loc_18003921A
0x18003920d  mov     rax, [rcx]
0x180039210  mov     rax, [rax+10h]
0x180039214  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039219  nop
0x18003921a  jmp     loc_1800390A5
0x18003921f  mov     [rbp+57h+var_A0], r12
0x180039223  mov     [rbp+57h+string], r12
0x180039227  lea     r9, [rbp+57h+string]; string
0x18003922b  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18003922f  mov     edx, 2Ch ; ','; length
0x180039234  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_Application@@3QB_WB; "Windows.Internal.StateRepository.Applic"...
0x18003923b  call    cs:__imp_WindowsCreateStringReference
0x180039241  test    eax, eax
0x180039243  js      loc_18003975B
0x180039249  lea     r8, [rbp+57h+var_A0]
0x18003924d  lea     rdx, _GUID_07adcc9a_e505_48c2_b471_45af8561f6af
0x180039254  mov     rcx, [rbp+57h+string]
0x180039258  call    cs:__imp_RoGetActivationFactory
0x18003925e  mov     ebx, eax
0x180039260  test    eax, eax
0x180039262  jns     short loc_1800392C4
0x180039264  mov     rcx, [rbp+5Fh]; this
0x180039268  mov     r9d, eax; char *
0x18003926b  lea     r8, aOnecoreuapWind_0; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180039272  mov     edx, 83h; void *
0x180039277  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003927c  nop
0x18003927d  mov     rcx, [rbp+57h+var_A0]
0x180039281  test    rcx, rcx
0x180039284  jz      short loc_180039293
0x180039286  mov     rax, [rcx]
0x180039289  mov     rax, [rax+10h]
0x18003928d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039292  nop
0x180039293  mov     rcx, [rbp+57h+var_B8]
0x180039297  test    rcx, rcx
0x18003929a  jz      short loc_1800392A9
0x18003929c  mov     rax, [rcx]
0x18003929f  mov     rax, [rax+10h]
0x1800392a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800392a8  nop
0x1800392a9  mov     rcx, [rbp+57h+var_B0]
0x1800392ad  test    rcx, rcx
0x1800392b0  jz      short loc_1800392BF
0x1800392b2  mov     rax, [rcx]
0x1800392b5  mov     rax, [rax+10h]
0x1800392b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800392be  nop
0x1800392bf  jmp     loc_1800390A5
0x1800392c4  mov     [rbp+57h+var_A8], r12
0x1800392c8  mov     rdi, [rbp+57h+var_A0]
0x1800392cc  mov     rax, [rdi]
0x1800392cf  mov     rbx, [rax+0F0h]
0x1800392d6  mov     [rbp+57h+var_A8], r12
0x1800392da  lea     rdx, [rbp+57h+var_70]
0x1800392de  lea     rcx, [rbp+57h+hstringHeader]
0x1800392e2  call    ??$?0PEB_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEB_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t const * const &,Microsoft::WRL::Details::Dummy)
0x1800392e7  nop
0x1800392e8  lea     r9, [rbp+57h+var_A8]
0x1800392ec  mov     r8, [rax+18h]
0x1800392f0  mov     rdx, [rbp+57h+var_B8]
0x1800392f4  mov     rcx, rdi
0x1800392f7  mov     rax, rbx
0x1800392fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800392ff  mov     ebx, eax
0x180039301  test    eax, eax
0x180039303  jns     short loc_18003937B
0x180039305  mov     rcx, [rbp+5Fh]; this
0x180039309  mov     r9d, eax; char *
0x18003930c  lea     r8, aOnecoreuapWind_0; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180039313  mov     edx, 86h; void *
0x180039318  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003931d  nop
0x18003931e  mov     rcx, [rbp+57h+var_A8]
0x180039322  test    rcx, rcx
0x180039325  jz      short loc_180039334
0x180039327  mov     rax, [rcx]
0x18003932a  mov     rax, [rax+10h]
0x18003932e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039333  nop
0x180039334  mov     rcx, [rbp+57h+var_A0]
0x180039338  test    rcx, rcx
0x18003933b  jz      short loc_18003934A
0x18003933d  mov     rax, [rcx]
0x180039340  mov     rax, [rax+10h]
0x180039344  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039349  nop
0x18003934a  mov     rcx, [rbp+57h+var_B8]
0x18003934e  test    rcx, rcx
0x180039351  jz      short loc_180039360
0x180039353  mov     rax, [rcx]
0x180039356  mov     rax, [rax+10h]
0x18003935a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003935f  nop
0x180039360  mov     rcx, [rbp+57h+var_B0]
0x180039364  test    rcx, rcx
0x180039367  jz      short loc_180039376
0x180039369  mov     rax, [rcx]
0x18003936c  mov     rax, [rax+10h]
0x180039370  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039375  nop
0x180039376  jmp     loc_1800390A5
0x18003937b  mov     [rbp+57h+var_90], r12
0x18003937f  mov     [rbp+57h+string], r12
0x180039383  lea     r9, [rbp+57h+string]; string
0x180039387  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18003938b  mov     edx, 3Ch ; '<'; length
0x180039390  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_ApplicationResourceResolver@@3QB_WB; "Windows.Internal.StateRepository.Applic"...
0x180039397  call    cs:__imp_WindowsCreateStringReference
0x18003939d  test    eax, eax
0x18003939f  js      loc_180039703
0x1800393a5  lea     r8, [rbp+57h+var_90]
0x1800393a9  lea     rdx, _GUID_84463b2a_c88e_4597_b41f_17d3bf6486e9
0x1800393b0  mov     rcx, [rbp+57h+string]
0x1800393b4  call    cs:__imp_RoGetActivationFactory
0x1800393ba  mov     ebx, eax
0x1800393bc  test    eax, eax
0x1800393be  jns     loc_180039450
0x1800393c4  mov     rcx, [rbp+5Fh]; this
0x1800393c8  mov     r9d, eax; char *
0x1800393cb  lea     r8, aOnecoreuapWind_0; "onecoreuap\\windows\\core\\isoenvbroker"...
0x1800393d2  mov     edx, 8Bh; void *
0x1800393d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800393dc  nop
0x1800393dd  mov     rcx, [rbp+57h+var_90]
0x1800393e1  test    rcx, rcx
0x1800393e4  jz      short loc_1800393F3
0x1800393e6  mov     rax, [rcx]
0x1800393e9  mov     rax, [rax+10h]
0x1800393ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800393f2  nop
0x1800393f3  mov     rcx, [rbp+57h+var_A8]
0x1800393f7  test    rcx, rcx
0x1800393fa  jz      short loc_180039409
0x1800393fc  mov     rax, [rcx]
0x1800393ff  mov     rax, [rax+10h]
0x180039403  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039408  nop
0x180039409  mov     rcx, [rbp+57h+var_A0]
  ... truncated ...
```
