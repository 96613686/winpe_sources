# MSATokenBroker::GetDeviceTicket(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180051ed8`
- end: `0x1800525de`
- name: `?GetDeviceTicket@MSATokenBroker@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z`
- size: `1798`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800862f0`

## callees

- `0x1800060a0`
- `0x180006ee0`
- `0x180007ec1`
- `0x180008d50`
- `0x180009a80`
- `0x18000ecc0`
- `0x18002ca60`
- `0x18002eb3c`
- `0x180035e0c`
- `0x180050540`
- `0x180051ed8`
- `0x1800ae010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180051f4b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180051feb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180052037`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180051f4b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180051feb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180052037`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180052198`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180052223`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180052198`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180052223`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800521c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800521c4`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180052008`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180052008`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180051f6a`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180051f6a`

## string_xrefs

- `0x180051f44`: `Windows.Internal.Security.WebAuthentication.AuthenticationManager`
- `0x180051fe4`: `Windows.Security.Authentication.OnlineId.OnlineIdServiceTicketRequest`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
__int128 *__fastcall MSATokenBroker::GetDeviceTicket(__int128 *a1, _QWORD *a2)
{
  HRESULT v4; // eax
  int v5; // edx
  unsigned int v6; // r8d
  int v7; // ebx
  HRESULT v8; // eax
  int v9; // edx
  unsigned int v10; // r8d
  int ActivationFactory; // ebx
  _QWORD *v12; // r14
  __int64 v13; // rbx
  HRESULT v14; // eax
  int v15; // edx
  unsigned int v16; // r8d
  __int64 (__fastcall *v17)(_QWORD *, PVOID, HSTRING, __int64 *); // r15
  HSTRING v18; // rbx
  HSTRING_HEADER *v19; // rax
  int v20; // ebx
  int v21; // ebx
  HRESULT v22; // edx
  int v23; // ebx
  __int64 v24; // r8
  int (__fastcall ***v25)(_QWORD, GUID *, __int64 *); // rdi
  int v26; // ebx
  __int64 v27; // rbx
  __int64 (__fastcall *v28)(__int64, __int64 *); // rdi
  __int64 v29; // rcx
  int v30; // ebx
  __int64 v31; // rbx
  __int64 (__fastcall *v32)(__int64, _QWORD, __int64 *); // rdi
  __int64 v33; // rcx
  int v34; // ebx
  __int64 v35; // rdi
  __int64 (__fastcall *v36)(__int64, HSTRING *); // rbx
  int v37; // ebx
  PCWSTR StringRawBuffer; // rax
  unsigned __int64 v39; // r8
  __int64 v40; // rcx
  __int64 v41; // rcx
  __int64 v42; // rcx
  int (__fastcall ***v43)(_QWORD, GUID *, __int64 *); // rcx
  _QWORD *v44; // rcx
  __int64 v45; // rcx
  __int64 v46; // rcx
  __int64 v48; // [rsp+30h] [rbp-89h] BYREF
  HSTRING v49; // [rsp+38h] [rbp-81h] BYREF
  __int64 v50; // [rsp+40h] [rbp-79h] BYREF
  __int64 v51; // [rsp+48h] [rbp-71h] BYREF
  __int64 v52; // [rsp+50h] [rbp-69h] BYREF
  __int64 v53; // [rsp+58h] [rbp-61h] BYREF
  int (__fastcall ***v54)(_QWORD, GUID *, __int64 *); // [rsp+60h] [rbp-59h] BYREF
  _QWORD *v55; // [rsp+68h] [rbp-51h] BYREF
  __int128 v56; // [rsp+80h] [rbp-39h] BYREF
  __m128i si128; // [rsp+90h] [rbp-29h]
  HSTRING_HEADER pExceptionObject; // [rsp+A0h] [rbp-19h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+C8h] [rbp+Fh] BYREF
  HSTRING string; // [rsp+E0h] [rbp+27h] BYREF

  v48 = 0;
  v52 = 0;
  v55 = 0;
  v54 = 0;
  v53 = 0;
  v51 = 0;
  v50 = 0;
  v49 = 0;
  string = 0;
  v4 = WindowsCreateStringReference(
         L"Windows.Internal.Security.WebAuthentication.AuthenticationManager",
         0x41u,
         &hstringHeader,
         &string);
  if ( v4 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v4, v5, v6);
    __debugbreak();
  }
  v48 = 0;
  *(_QWORD *)&v56 = 0;
  v7 = RoActivateInstance(string, &v56);
  if ( v7 >= 0 )
  {
    if ( !memcmp_0(&GUID_eb2c0c45_76f9_4a0a_bb73_fcf47d73a4eb, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
    {
      v48 = v56;
    }
    else
    {
      v7 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))v56)(
             v56,
             &GUID_eb2c0c45_76f9_4a0a_bb73_fcf47d73a4eb,
             &v48);
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v56 + 16LL))(v56);
    }
  }
  if ( v7 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        37,
        WPP_d559cce52a1433e229f26c816596a62e_Traceguids,
        (unsigned int)v7);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)&pExceptionObject, v7);
    throw (ErrorCodeException *)&pExceptionObject;
  }
  string = 0;
  v8 = WindowsCreateStringReference(
         L"Windows.Security.Authentication.OnlineId.OnlineIdServiceTicketRequest",
         0x45u,
         &hstringHeader,
         &string);
  if ( v8 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v8, v9, v10);
    __debugbreak();
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_bebb0a08_9e73_4077_9614_08614c0bc245, &v55);
  if ( ActivationFactory < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        38,
        WPP_d559cce52a1433e229f26c816596a62e_Traceguids,
        (unsigned int)ActivationFactory);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)&pExceptionObject, ActivationFactory);
    throw (ErrorCodeException *)&pExceptionObject;
  }
  v12 = v55;
  v13 = *v55;
  string = 0;
  v14 = WindowsCreateStringReference(L"MBI_SSL", 7u, &hstringHeader, &string);
  if ( v14 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v14, v15, v16);
    __debugbreak();
  }
  v17 = *(__int64 (__fastcall **)(_QWORD *, PVOID, HSTRING, __int64 *))(v13 + 48);
  v18 = string;
  if ( a2[3] > 7u )
    a2 = (_QWORD *)*a2;
  *(_QWORD *)&v56 = a2;
  v19 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&pExceptionObject, (const WCHAR **)&v56, v16);
  v20 = v17(v12, v19[1].Reserved.Reserved1, v18, &v52);
  if ( v20 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        39,
        WPP_d559cce52a1433e229f26c816596a62e_Traceguids,
        (unsigned int)v20);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)&pExceptionObject, v20);
    throw (ErrorCodeException *)&pExceptionObject;
  }
  v56 = xmmword_1800BA718;
  v21 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v48 + 72LL))(v48, &v56);
  if ( v21 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        40,
        WPP_d559cce52a1433e229f26c816596a62e_Traceguids,
        (unsigned int)v21);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)&pExceptionObject, v21);
    throw (ErrorCodeException *)&pExceptionObject;
  }
  v23 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v48 + 56LL))(v48, v52, &v54);
  if ( v23 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        41,
        WPP_d559cce52a1433e229f26c816596a62e_Traceguids,
        (unsigned int)v23);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)&pExceptionObject, v23);
    throw (ErrorCodeException *)&pExceptionObject;
  }
  v25 = v54;
  v26 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>>(
          v54,
          v22,
          v24);
  if ( v26 < 0
    || (v26 = ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64 *))(*v25)[8])(v25, &v53),
        v26 < 0) )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        42,
        WPP_d559cce52a1433e229f26c816596a62e_Traceguids,
        (unsigned int)v26);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)&pExceptionObject, v26);
    throw (ErrorCodeException *)&pExceptionObject;
  }
  v27 = v53;
  v28 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v53 + 48LL);
  v29 = v51;
  if ( v51 )
  {
    v51 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  }
  v30 = v28(v27, &v51);
  if ( v30 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        43,
        WPP_d559cce52a1433e229f26c816596a62e_Traceguids,
        (unsigned int)v30);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)&pExceptionObject, v30);
    throw (ErrorCodeException *)&pExceptionObject;
  }
  v31 = v51;
  v32 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v51 + 48LL);
  v33 = v50;
  if ( v50 )
  {
    v50 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
  }
  v34 = v32(v31, 0, &v50);
  if ( v34 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        44,
        WPP_d559cce52a1433e229f26c816596a62e_Traceguids,
        (unsigned int)v34);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)&pExceptionObject, v34);
    throw (ErrorCodeException *)&pExceptionObject;
  }
  v35 = v50;
  v36 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v50 + 48LL);
  WindowsDeleteString(v49);
  v49 = 0;
  v37 = v36(v35, &v49);
  if ( v37 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        45,
        WPP_d559cce52a1433e229f26c816596a62e_Traceguids,
        (unsigned int)v37);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)&pExceptionObject, v37);
    throw (ErrorCodeException *)&pExceptionObject;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(v49, 0);
  v56 = 0;
  si128 = 0;
  v39 = -1;
  do
    ++v39;
  while ( StringRawBuffer[v39] );
  std::wstring::_Construct<1,unsigned short const *>((char **)&v56, StringRawBuffer, v39);
  *a1 = v56;
  a1[1] = (__int128)si128;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v56) = 0;
  std::wstring::~wstring((char **)&v56);
  WindowsDeleteString(v49);
  v49 = 0;
  v40 = v50;
  if ( v50 )
  {
    v50 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
  }
  v41 = v51;
  if ( v51 )
  {
    v51 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
  }
  v42 = v53;
  if ( v53 )
  {
    v53 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
  }
  v43 = v54;
  if ( v54 )
  {
    v54 = 0;
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v43)[2])(v43);
  }
  v44 = v55;
  if ( v55 )
  {
    v55 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v44 + 16LL))(v44);
  }
  v45 = v52;
  if ( v52 )
  {
    v52 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
  }
  v46 = v48;
  if ( v48 )
  {
    v48 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
  }
  return a1;
}

```

## disassembly

```asm
0x180051ed8  mov     [rsp-8+arg_10], rbx
0x180051edd  mov     [rsp-8+arg_18], rsi
0x180051ee2  push    rbp
0x180051ee3  push    rdi
0x180051ee4  push    r12
0x180051ee6  push    r14
0x180051ee8  push    r15
0x180051eea  lea     rbp, [rsp-37h]
0x180051eef  sub     rsp, 0F0h
0x180051ef6  mov     rax, cs:__security_cookie
0x180051efd  xor     rax, rsp
0x180051f00  mov     [rbp+57h+var_28], rax
0x180051f04  mov     rdi, rdx
0x180051f07  mov     rsi, rcx
0x180051f0a  mov     [rbp+57h+var_C0], rcx
0x180051f0e  xor     r12d, r12d
0x180051f11  mov     [rsp+110h+var_E0], r12
0x180051f16  mov     [rbp+57h+var_C0], r12
0x180051f1a  mov     [rbp+57h+var_A8], r12
0x180051f1e  mov     [rbp+57h+var_B0], r12
0x180051f22  mov     [rbp+57h+var_B8], r12
0x180051f26  mov     [rbp+57h+var_C8], r12
0x180051f2a  mov     [rbp+57h+var_D0], r12
0x180051f2e  mov     [rsp+110h+var_D8], r12
0x180051f33  mov     [rbp+57h+string], r12
0x180051f37  lea     r9, [rbp+57h+string]; string
0x180051f3b  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180051f3f  lea     edx, [r12+41h]; length
0x180051f44  lea     rcx, ?RuntimeClass_Windows_Internal_Security_WebAuthentication_AuthenticationManager@@3QBGB; "Windows.Internal.Security.WebAuthentica"...
0x180051f4b  call    cs:__imp_WindowsCreateStringReference
0x180051f51  test    eax, eax
0x180051f53  js      loc_1800523AB
0x180051f59  mov     [rsp+110h+var_E0], r12
0x180051f5e  mov     qword ptr [rbp+57h+var_90], r12
0x180051f62  lea     rdx, [rbp+57h+var_90]
0x180051f66  mov     rcx, [rbp+57h+string]
0x180051f6a  call    cs:__imp_RoActivateInstance
0x180051f70  mov     ebx, eax
0x180051f72  test    eax, eax
0x180051f74  js      short loc_180051FCB
0x180051f76  lea     r8d, [r12+10h]; Size
0x180051f7b  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x180051f82  lea     rcx, _GUID_eb2c0c45_76f9_4a0a_bb73_fcf47d73a4eb; Buf1
0x180051f89  call    memcmp_0
0x180051f8e  test    eax, eax
0x180051f90  jnz     short loc_180051F9D
0x180051f92  mov     rax, qword ptr [rbp+57h+var_90]
0x180051f96  mov     [rsp+110h+var_E0], rax
0x180051f9b  jmp     short loc_180051FCB
0x180051f9d  mov     rcx, qword ptr [rbp+57h+var_90]
0x180051fa1  mov     rax, [rcx]
0x180051fa4  lea     r8, [rsp+110h+var_E0]
0x180051fa9  lea     rdx, _GUID_eb2c0c45_76f9_4a0a_bb73_fcf47d73a4eb
0x180051fb0  mov     rax, [rax]
0x180051fb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051fb8  mov     ebx, eax
0x180051fba  mov     rcx, qword ptr [rbp+57h+var_90]
0x180051fbe  mov     rax, [rcx]
0x180051fc1  mov     rax, [rax+10h]
0x180051fc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051fca  nop
0x180051fcb  test    ebx, ebx
0x180051fcd  js      loc_1800523B3
0x180051fd3  mov     [rbp+57h+string], r12
0x180051fd7  lea     r9, [rbp+57h+string]; string
0x180051fdb  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180051fdf  mov     edx, 45h ; 'E'; length
0x180051fe4  lea     rcx, ?RuntimeClass_Windows_Security_Authentication_OnlineId_OnlineIdServiceTicketRequest@@3QBGB; "Windows.Security.Authentication.OnlineI"...
0x180051feb  call    cs:__imp_WindowsCreateStringReference
0x180051ff1  test    eax, eax
0x180051ff3  js      loc_180052400
0x180051ff9  lea     r8, [rbp+57h+var_A8]
0x180051ffd  lea     rdx, _GUID_bebb0a08_9e73_4077_9614_08614c0bc245
0x180052004  mov     rcx, [rbp+57h+string]
0x180052008  call    cs:__imp_RoGetActivationFactory
0x18005200e  mov     ebx, eax
0x180052010  test    eax, eax
0x180052012  js      loc_180052408
0x180052018  mov     r14, [rbp+57h+var_A8]
0x18005201c  mov     rbx, [r14]
0x18005201f  mov     [rbp+57h+string], r12
0x180052023  lea     r9, [rbp+57h+string]; string
0x180052027  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18005202b  mov     edx, 7; length
0x180052030  lea     rcx, aMbiSsl; "MBI_SSL"
0x180052037  call    cs:__imp_WindowsCreateStringReference
0x18005203d  test    eax, eax
0x18005203f  js      loc_180052455
0x180052045  mov     r15, [rbx+30h]
0x180052049  mov     rbx, [rbp+57h+string]
0x18005204d  cmp     qword ptr [rdi+18h], 7
0x180052052  jbe     short loc_180052057
0x180052054  mov     rdi, [rdi]
0x180052057  mov     qword ptr [rbp+57h+var_90], rdi
0x18005205b  lea     rdx, [rbp+57h+var_90]
0x18005205f  lea     rcx, [rbp+57h+pExceptionObject]
0x180052063  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180052068  nop
0x180052069  lea     r9, [rbp+57h+var_C0]
0x18005206d  mov     r8, rbx
0x180052070  mov     rdx, [rax+18h]
0x180052074  mov     rcx, r14
0x180052077  mov     rax, r15
0x18005207a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005207f  mov     ebx, eax
0x180052081  test    eax, eax
0x180052083  js      loc_18005245D
0x180052089  mov     rcx, [rsp+110h+var_E0]
0x18005208e  movups  xmm0, cs:xmmword_1800BA718
0x180052095  movdqu  [rbp+57h+var_90], xmm0
0x18005209a  mov     rax, [rcx]
0x18005209d  lea     rdx, [rbp+57h+var_90]
0x1800520a1  mov     rax, [rax+48h]
0x1800520a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800520aa  mov     ebx, eax
0x1800520ac  test    eax, eax
0x1800520ae  js      loc_1800524AA
0x1800520b4  mov     rcx, [rsp+110h+var_E0]
0x1800520b9  mov     rax, [rcx]
0x1800520bc  lea     r8, [rbp+57h+var_B0]
0x1800520c0  mov     rdx, [rbp+57h+var_C0]
0x1800520c4  mov     rax, [rax+38h]
0x1800520c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800520cd  mov     ebx, eax
0x1800520cf  test    eax, eax
0x1800520d1  js      loc_1800524F7
0x1800520d7  mov     rdi, [rbp+57h+var_B0]
0x1800520db  mov     rcx, rdi
0x1800520de  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::Security::WebAuthentication::UserHostIdentity *> *,tagCOWAIT_FLAGS,void *)
0x1800520e3  mov     ebx, eax
0x1800520e5  test    eax, eax
0x1800520e7  js      loc_18005235E
0x1800520ed  mov     rax, [rdi]
0x1800520f0  lea     rdx, [rbp+57h+var_B8]
0x1800520f4  mov     rcx, rdi
0x1800520f7  mov     rax, [rax+40h]
0x1800520fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052100  mov     ebx, eax
0x180052102  test    eax, eax
0x180052104  js      loc_18005235E
0x18005210a  mov     rbx, [rbp+57h+var_B8]
0x18005210e  mov     rax, [rbx]
0x180052111  mov     rdi, [rax+30h]
0x180052115  mov     rcx, [rbp+57h+var_C8]
0x180052119  test    rcx, rcx
0x18005211c  jz      short loc_18005212F
0x18005211e  mov     [rbp+57h+var_C8], r12
0x180052122  mov     rax, [rcx]
0x180052125  mov     rax, [rax+10h]
0x180052129  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005212e  nop
0x18005212f  lea     rdx, [rbp+57h+var_C8]
0x180052133  mov     rcx, rbx
0x180052136  mov     rax, rdi
0x180052139  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005213e  mov     ebx, eax
0x180052140  test    eax, eax
0x180052142  js      loc_180052544
0x180052148  mov     rbx, [rbp+57h+var_C8]
0x18005214c  mov     rax, [rbx]
0x18005214f  mov     rdi, [rax+30h]
0x180052153  mov     rcx, [rbp+57h+var_D0]
0x180052157  test    rcx, rcx
0x18005215a  jz      short loc_18005216D
0x18005215c  mov     [rbp+57h+var_D0], r12
0x180052160  mov     rax, [rcx]
0x180052163  mov     rax, [rax+10h]
0x180052167  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005216c  nop
0x18005216d  lea     r8, [rbp+57h+var_D0]
0x180052171  xor     edx, edx
0x180052173  mov     rcx, rbx
0x180052176  mov     rax, rdi
0x180052179  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005217e  mov     ebx, eax
0x180052180  test    eax, eax
0x180052182  js      loc_180052591
0x180052188  mov     rdi, [rbp+57h+var_D0]
0x18005218c  mov     rax, [rdi]
0x18005218f  mov     rbx, [rax+30h]
0x180052193  mov     rcx, [rsp+110h+var_D8]; string
0x180052198  call    cs:__imp_WindowsDeleteString
0x18005219e  mov     [rsp+110h+var_D8], r12
0x1800521a3  lea     rdx, [rsp+110h+var_D8]
0x1800521a8  mov     rcx, rdi
0x1800521ab  mov     rax, rbx
0x1800521ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800521b3  mov     ebx, eax
0x1800521b5  test    eax, eax
0x1800521b7  js      loc_180052311
0x1800521bd  xor     edx, edx; length
0x1800521bf  mov     rcx, [rsp+110h+var_D8]; string
0x1800521c4  call    cs:__imp_WindowsGetStringRawBuffer
0x1800521ca  xorps   xmm0, xmm0
0x1800521cd  movups  [rbp+57h+var_90], xmm0
0x1800521d1  xorps   xmm1, xmm1
0x1800521d4  movdqu  [rbp+57h+var_80], xmm1
0x1800521d9  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800521dd  inc     r8
0x1800521e0  cmp     [rax+r8*2], r12w
0x1800521e5  jnz     short loc_1800521DD
0x1800521e7  mov     rdx, rax
0x1800521ea  lea     rcx, [rbp+57h+var_90]
0x1800521ee  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800521f3  movups  xmm0, [rbp+57h+var_90]
0x1800521f7  movups  xmmword ptr [rsi], xmm0
0x1800521fa  movups  xmm1, [rbp+57h+var_80]
0x1800521fe  movups  xmmword ptr [rsi+10h], xmm1
0x180052202  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x18005220a  movdqu  [rbp+57h+var_80], xmm0
0x18005220f  mov     word ptr [rbp+57h+var_90], r12w
0x180052214  lea     rcx, [rbp+57h+var_90]
0x180052218  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005221d  nop
0x18005221e  mov     rcx, [rsp+110h+var_D8]; string
0x180052223  call    cs:__imp_WindowsDeleteString
0x180052229  mov     [rsp+110h+var_D8], r12
0x18005222e  mov     rcx, [rbp+57h+var_D0]
0x180052232  test    rcx, rcx
0x180052235  jz      short loc_180052248
0x180052237  mov     [rbp+57h+var_D0], r12
0x18005223b  mov     rax, [rcx]
0x18005223e  mov     rax, [rax+10h]
0x180052242  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052247  nop
0x180052248  mov     rcx, [rbp+57h+var_C8]
0x18005224c  test    rcx, rcx
0x18005224f  jz      short loc_180052262
0x180052251  mov     [rbp+57h+var_C8], r12
0x180052255  mov     rax, [rcx]
0x180052258  mov     rax, [rax+10h]
0x18005225c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052261  nop
0x180052262  mov     rcx, [rbp+57h+var_B8]
0x180052266  test    rcx, rcx
0x180052269  jz      short loc_18005227C
0x18005226b  mov     [rbp+57h+var_B8], r12
0x18005226f  mov     rax, [rcx]
0x180052272  mov     rax, [rax+10h]
0x180052276  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005227b  nop
0x18005227c  mov     rcx, [rbp+57h+var_B0]
0x180052280  test    rcx, rcx
0x180052283  jz      short loc_180052296
0x180052285  mov     [rbp+57h+var_B0], r12
0x180052289  mov     rax, [rcx]
0x18005228c  mov     rax, [rax+10h]
0x180052290  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052295  nop
0x180052296  mov     rcx, [rbp+57h+var_A8]
0x18005229a  test    rcx, rcx
0x18005229d  jz      short loc_1800522B0
0x18005229f  mov     [rbp+57h+var_A8], r12
0x1800522a3  mov     rax, [rcx]
0x1800522a6  mov     rax, [rax+10h]
0x1800522aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800522af  nop
0x1800522b0  mov     rcx, [rbp+57h+var_C0]
0x1800522b4  test    rcx, rcx
0x1800522b7  jz      short loc_1800522CA
0x1800522b9  mov     [rbp+57h+var_C0], r12
0x1800522bd  mov     rax, [rcx]
0x1800522c0  mov     rax, [rax+10h]
0x1800522c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800522c9  nop
0x1800522ca  mov     rcx, [rsp+110h+var_E0]
0x1800522cf  test    rcx, rcx
0x1800522d2  jz      short loc_1800522E6
0x1800522d4  mov     [rsp+110h+var_E0], r12
0x1800522d9  mov     rdx, [rcx]
0x1800522dc  mov     rax, [rdx+10h]
0x1800522e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800522e5  nop
0x1800522e6  mov     rax, rsi
0x1800522e9  mov     rcx, [rbp+57h+var_28]
0x1800522ed  xor     rcx, rsp; StackCookie
0x1800522f0  call    __security_check_cookie
0x1800522f5  lea     r11, [rsp+110h+var_20]
0x1800522fd  mov     rbx, [r11+40h]
0x180052301  mov     rsi, [r11+48h]
0x180052305  mov     rsp, r11
0x180052308  pop     r15
0x18005230a  pop     r14
0x18005230c  pop     r12
0x18005230e  pop     rdi
0x18005230f  pop     rbp
0x180052310  retn
0x180052311  lea     rax, WPP_GLOBAL_Control
0x180052318  mov     rcx, cs:WPP_GLOBAL_Control
0x18005231f  cmp     rcx, rax
0x180052322  jz      short loc_180052342
0x180052324  test    byte ptr [rcx+1Ch], 1
0x180052328  jz      short loc_180052342
0x18005232a  mov     edx, 2Dh ; '-'
0x18005232f  mov     r9d, ebx
0x180052332  lea     r8, WPP_d559cce52a1433e229f26c816596a62e_Traceguids
0x180052339  mov     rcx, [rcx+10h]
0x18005233d  call    WPP_SF_d
0x180052342  mov     edx, ebx; int
0x180052344  lea     rcx, [rbp+57h+pExceptionObject]; this
  ... truncated ...
```
