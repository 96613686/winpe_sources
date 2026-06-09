# Windows::Internal::AI::Agents::Mcp::Implementation::McpAccessManager::RequestConsentResponse(unsigned __int64,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,Windows::Storage::Streams::IRandomAccessStream *,Windows::Storage::Streams::IRandomAccessStream *,HSTRING__ *,std::vector<Windows::Internal::AI::Agents::Mcp::Implementation::InternalMcpResourceRequestInfo,std::allocator<Windows::Internal::AI::Agents::Mcp::Implementation::InternalMcpResourceRequestInfo>> const &)

- ea: `0x1800b4abc`
- end: `0x1800b4da4`
- name: `?RequestConsentResponse@McpAccessManager@Implementation@Mcp@Agents@AI@Internal@Windows@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KAEBV89@PEAUIRandomAccessStream@Streams@Storage@7@2PEAUHSTRING__@@AEBV?$vector@UInternalMcpResourceRequestInfo@Implementation@Mcp@Agents@AI@Internal@Windows@@V?$allocator@UInternalMcpResourceRequestInfo@Implementation@Mcp@Agents@AI@Internal@Windows@@@std@@@9@@Z`
- size: `744`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800b46d8`

## callees

- `0x1800094c0`
- `0x18001649c`
- `0x18002392c`
- `0x180029408`
- `0x18002f240`
- `0x18003f62c`
- `0x180096d60`
- `0x1800b45dc`
- `0x1800b4670`
- `0x1800b4abc`
- `0x1800c7010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b4b5c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b4b5c`
- `combase!__imp_RoGetActivationFactoryAsUser` at `0x1800b4b74`
- `combase!__imp_RoGetActivationFactoryAsUser` at `0x1800b4b74`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b4b99`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b4b99`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b4cdc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b4cdc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b4b43`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b4b43`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContextFromSid` at `0x1800b4b1a`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContextFromSid` at `0x1800b4b1a`

## string_xrefs

- `0x1800b4b3c`: `Windows.Internal.AI.Agents.Mcp.McpConsentExperience`
- `0x1800b4d50`: `onecore\base\devices\cam\core\mcpaccessmanager.cpp`
- `0x1800b4d68`: `onecore\base\devices\cam\core\mcpaccessmanager.cpp`
- `0x1800b4d7d`: `onecore\base\devices\cam\core\mcpaccessmanager.cpp`
- `0x1800b4d92`: `onecore\base\devices\cam\core\mcpaccessmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
_QWORD *__fastcall Windows::Internal::AI::Agents::Mcp::Implementation::McpAccessManager::RequestConsentResponse(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 *a7)
{
  __int64 v10; // r14
  __int64 v11; // rax
  int v12; // eax
  __int64 v13; // rbx
  int ActivationFactoryAsUser; // eax
  _QWORD *v15; // rax
  unsigned int v16; // edx
  __int64 v17; // rcx
  __int64 v18; // rbx
  __int64 v19; // rdi
  const WCHAR *v20; // rax
  const WCHAR *v21; // rax
  HSTRING v22; // rcx
  __int64 v23; // rdx
  HSTRING v24; // rcx
  __int64 v25; // rdi
  __int64 (__fastcall *v26)(__int64, __int64, __int64, __int64); // rbx
  int v27; // eax
  PCWSTR StringRawBuffer; // rax
  __int64 v29; // rcx
  int v31; // [rsp+20h] [rbp-B1h]
  int v32; // [rsp+20h] [rbp-B1h]
  _QWORD *v33; // [rsp+50h] [rbp-81h] BYREF
  unsigned __int64 v34; // [rsp+58h] [rbp-79h] BYREF
  HSTRING v35; // [rsp+60h] [rbp-71h] BYREF
  __int64 v36; // [rsp+68h] [rbp-69h] BYREF
  HSTRING v37; // [rsp+70h] [rbp-61h] BYREF
  HSTRING v38; // [rsp+78h] [rbp-59h] BYREF
  __int64 v39; // [rsp+80h] [rbp-51h] BYREF
  _QWORD *v40; // [rsp+88h] [rbp-49h] BYREF
  int v41[2]; // [rsp+98h] [rbp-39h]
  HSTRING string; // [rsp+A0h] [rbp-31h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+A8h] [rbp-29h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+47h]

  v40 = a1;
  *(_QWORD *)v41 = a6;
  v10 = 0;
  v36 = 0;
  v39 = 0;
  v11 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a3);
  v12 = UMgrQueryUserContextFromSid(v11, &v39);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x12A,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\mcpaccessmanager.cpp",
      (const char *)(unsigned int)v12,
      v31);
  v13 = v39;
  if ( WindowsCreateStringReference(
         L"Windows.Internal.AI.Agents.Mcp.McpConsentExperience",
         0x33u,
         &hstringHeader,
         &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  ActivationFactoryAsUser = RoGetActivationFactoryAsUser(string, v13, &GUID_c53275b4_e8ea_5549_9af1_7355e5da6d97, &v36);
  if ( ActivationFactoryAsUser < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x12F,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\mcpaccessmanager.cpp",
      (const char *)(unsigned int)ActivationFactoryAsUser,
      v31);
  v34 = (a7[1] - *a7) >> 6;
  v15 = CoTaskMemAlloc(16 * v34);
  v40 = v15;
  if ( !v15 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x13A,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\mcpaccessmanager.cpp",
      (const char *)0x8007000ELL,
      v31);
  v33 = v15;
  v16 = 0;
  if ( v34 )
  {
    while ( 1 )
    {
      v17 = 2LL * v16;
      v15[v17] = 0;
      v33[v17 + 1] = 0;
      if ( ++v16 >= v34 )
        break;
      v15 = v33;
    }
  }
  string = (HSTRING)&v34;
  hstringHeader.Reserved.Reserved1 = &v33;
  hstringHeader.Reserved.Reserved2[8] = 1;
  v18 = *a7;
  v19 = a7[1];
  while ( v18 != v19 )
  {
    v20 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v18);
    wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(
      &v38,
      v20);
    v21 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v18 + 32);
    wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(
      &v37,
      v21);
    v22 = v38;
    v38 = 0;
    v23 = 2 * v10;
    v33[v23] = v22;
    v24 = v37;
    v37 = 0;
    v33[v23 + 1] = v24;
    ++v10;
    Windows::Internal::String::~String((Windows::Internal::String *)&v37);
    Windows::Internal::String::~String((Windows::Internal::String *)&v38);
    v18 += 64;
  }
  v35 = 0;
  v25 = v36;
  v26 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64))(*(_QWORD *)v36 + 48LL);
  wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
    &v35,
    0);
  v32 = v41[0];
  v27 = v26(v25, a2, a4, a5);
  if ( v27 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x172,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\mcpaccessmanager.cpp",
      (const char *)(unsigned int)v27,
      v32);
  StringRawBuffer = WindowsGetStringRawBuffer(v35, 0);
  std::wstring::wstring(a1, StringRawBuffer);
  Windows::Internal::String::~String((Windows::Internal::String *)&v35);
  hstringHeader.Reserved.Reserved2[8] = 0;
  lambda_203f8f962703fd3224a46f22c24ee921_::operator()(&string);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v40);
  v29 = v36;
  if ( v36 )
  {
    v36 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  }
  return a1;
}

```

## disassembly

```asm
0x1800b4abc  push    rbp
0x1800b4abe  push    rbx
0x1800b4abf  push    rsi
0x1800b4ac0  push    rdi
0x1800b4ac1  push    r12
0x1800b4ac3  push    r13
0x1800b4ac5  push    r14
0x1800b4ac7  push    r15
0x1800b4ac9  lea     rbp, [rsp-7]
0x1800b4ace  sub     rsp, 0D8h
0x1800b4ad5  mov     rax, cs:__security_cookie
0x1800b4adc  xor     rax, rsp
0x1800b4adf  mov     [rbp+3Fh+var_50], rax
0x1800b4ae3  mov     r12, r9
0x1800b4ae6  mov     r15, rdx
0x1800b4ae9  mov     rsi, rcx
0x1800b4aec  mov     rdi, [rbp+3Fh+arg_30]
0x1800b4af0  mov     [rbp+3Fh+var_88], rcx
0x1800b4af4  mov     r13, [rbp+3Fh+arg_20]
0x1800b4af8  mov     rax, [rbp+3Fh+arg_28]
0x1800b4afc  mov     qword ptr [rbp+3Fh+var_78], rax
0x1800b4b00  xor     r14d, r14d
0x1800b4b03  mov     [rbp+3Fh+var_A8], r14
0x1800b4b07  mov     [rbp+3Fh+var_90], r14
0x1800b4b0b  mov     rcx, r8
0x1800b4b0e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800b4b13  lea     rdx, [rbp+3Fh+var_90]
0x1800b4b17  mov     rcx, rax
0x1800b4b1a  call    cs:__imp_UMgrQueryUserContextFromSid
0x1800b4b20  mov     rcx, [rbp+47h]; this
0x1800b4b24  test    eax, eax
0x1800b4b26  js      loc_1800B4D7A
0x1800b4b2c  mov     rbx, [rbp+3Fh+var_90]
0x1800b4b30  lea     r9, [rbp+3Fh+string]; string
0x1800b4b34  lea     r8, [rbp+3Fh+hstringHeader]; hstringHeader
0x1800b4b38  lea     edx, [r14+33h]; length
0x1800b4b3c  lea     rcx, ?RuntimeClass_Windows_Internal_AI_Agents_Mcp_McpConsentExperience@@3QBGB; "Windows.Internal.AI.Agents.Mcp.McpConse"...
0x1800b4b43  call    cs:__imp_WindowsCreateStringReference
0x1800b4b49  test    eax, eax
0x1800b4b4b  jns     short loc_1800B4B62
0x1800b4b4d  xor     r9d, r9d; lpArguments
0x1800b4b50  xor     r8d, r8d; nNumberOfArguments
0x1800b4b53  lea     edx, [r14+1]; dwExceptionFlags
0x1800b4b57  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800b4b5c  call    cs:__imp_RaiseException
0x1800b4b62  lea     r9, [rbp+3Fh+var_A8]
0x1800b4b66  lea     r8, _GUID_c53275b4_e8ea_5549_9af1_7355e5da6d97
0x1800b4b6d  mov     rdx, rbx
0x1800b4b70  mov     rcx, [rbp+3Fh+string]
0x1800b4b74  call    cs:__imp_RoGetActivationFactoryAsUser
0x1800b4b7a  mov     rcx, [rbp+47h]; this
0x1800b4b7e  test    eax, eax
0x1800b4b80  js      loc_1800B4D8F
0x1800b4b86  mov     rcx, [rdi+8]
0x1800b4b8a  sub     rcx, [rdi]
0x1800b4b8d  sar     rcx, 6
0x1800b4b91  mov     [rbp+3Fh+var_B8], rcx
0x1800b4b95  shl     rcx, 4; cb
0x1800b4b99  call    cs:__imp_CoTaskMemAlloc
0x1800b4b9f  mov     [rbp+3Fh+var_88], rax
0x1800b4ba3  mov     rcx, [rbp+47h]; this
0x1800b4ba7  test    rax, rax
0x1800b4baa  jz      loc_1800B4D62
0x1800b4bb0  mov     [rsp+110h+var_C0], rax
0x1800b4bb5  mov     edx, r14d
0x1800b4bb8  cmp     [rbp+3Fh+var_B8], r14
0x1800b4bbc  jbe     short loc_1800B4BE2
0x1800b4bbe  mov     ecx, edx
0x1800b4bc0  add     rcx, rcx
0x1800b4bc3  mov     [rax+rcx*8], r14
0x1800b4bc7  mov     rax, [rsp+110h+var_C0]
0x1800b4bcc  mov     [rax+rcx*8+8], r14
0x1800b4bd1  inc     edx
0x1800b4bd3  mov     eax, edx
0x1800b4bd5  cmp     rax, [rbp+3Fh+var_B8]
0x1800b4bd9  jnb     short loc_1800B4BE2
0x1800b4bdb  mov     rax, [rsp+110h+var_C0]
0x1800b4be0  jmp     short loc_1800B4BBE
0x1800b4be2  lea     rax, [rbp+3Fh+var_B8]
0x1800b4be6  mov     [rbp+3Fh+string], rax
0x1800b4bea  lea     rax, [rsp+110h+var_C0]
0x1800b4bef  mov     qword ptr [rbp+3Fh+hstringHeader.Reserved], rax
0x1800b4bf3  mov     byte ptr [rbp+3Fh+hstringHeader.Reserved+8], 1
0x1800b4bf7  mov     rbx, [rdi]
0x1800b4bfa  mov     rdi, [rdi+8]
0x1800b4bfe  jmp     short loc_1800B4C75
0x1800b4c00  mov     rcx, rbx
0x1800b4c03  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800b4c08  mov     rdx, rax; sourceString
0x1800b4c0b  lea     rcx, [rbp+3Fh+var_98]; string
0x1800b4c0f  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800b4c14  nop
0x1800b4c15  lea     rcx, [rbx+20h]
0x1800b4c19  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800b4c1e  mov     rdx, rax; sourceString
0x1800b4c21  lea     rcx, [rbp+3Fh+var_A0]; string
0x1800b4c25  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800b4c2a  mov     rcx, [rbp+3Fh+var_98]
0x1800b4c2e  mov     [rbp+3Fh+var_98], 0
0x1800b4c36  mov     rdx, r14
0x1800b4c39  add     rdx, rdx
0x1800b4c3c  mov     rax, [rsp+110h+var_C0]
0x1800b4c41  mov     [rax+rdx*8], rcx
0x1800b4c45  mov     rcx, [rbp+3Fh+var_A0]
0x1800b4c49  mov     [rbp+3Fh+var_A0], 0
0x1800b4c51  mov     rax, [rsp+110h+var_C0]
0x1800b4c56  mov     [rax+rdx*8+8], rcx
0x1800b4c5b  inc     r14
0x1800b4c5e  lea     rcx, [rbp+3Fh+var_A0]; this
0x1800b4c62  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800b4c67  nop
0x1800b4c68  lea     rcx, [rbp+3Fh+var_98]; this
0x1800b4c6c  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800b4c71  add     rbx, 40h ; '@'
0x1800b4c75  cmp     rbx, rdi
0x1800b4c78  jnz     short loc_1800B4C00
0x1800b4c7a  xor     r14d, r14d
0x1800b4c7d  mov     [rbp+3Fh+var_B0], r14
0x1800b4c81  mov     rdi, [rbp+3Fh+var_A8]
0x1800b4c85  mov     rax, [rdi]
0x1800b4c88  mov     rbx, [rax+30h]
0x1800b4c8c  xor     edx, edx
0x1800b4c8e  lea     rcx, [rbp+3Fh+var_B0]
0x1800b4c92  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x1800b4c97  mov     r10, [rsp+110h+var_C0]
0x1800b4c9c  lea     rax, [rbp+3Fh+var_B0]
0x1800b4ca0  mov     [rsp+110h+var_D8], rax
0x1800b4ca5  mov     [rsp+110h+var_E0], r10
0x1800b4caa  mov     eax, dword ptr [rbp+3Fh+var_B8]
0x1800b4cad  mov     [rsp+110h+var_E8], eax
0x1800b4cb1  mov     rax, qword ptr [rbp+3Fh+var_78]
0x1800b4cb5  mov     qword ptr [rsp+110h+var_F0], rax; int
0x1800b4cba  mov     r9, r13
0x1800b4cbd  mov     r8, r12
0x1800b4cc0  mov     rdx, r15
0x1800b4cc3  mov     rcx, rdi
0x1800b4cc6  mov     rax, rbx
0x1800b4cc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4cce  mov     rcx, [rbp+47h]; this
0x1800b4cd2  test    eax, eax
0x1800b4cd4  js      short loc_1800B4D4D
0x1800b4cd6  xor     edx, edx; length
0x1800b4cd8  mov     rcx, [rbp+3Fh+var_B0]; string
0x1800b4cdc  call    cs:__imp_WindowsGetStringRawBuffer
0x1800b4ce2  mov     rdx, rax
0x1800b4ce5  mov     rcx, rsi
0x1800b4ce8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800b4ced  nop
0x1800b4cee  lea     rcx, [rbp+3Fh+var_B0]; this
0x1800b4cf2  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800b4cf7  nop
0x1800b4cf8  mov     byte ptr [rbp+3Fh+hstringHeader.Reserved+8], r14b
0x1800b4cfc  lea     rcx, [rbp+3Fh+string]
0x1800b4d00  call    _lambda_203f8f962703fd3224a46f22c24ee921___operator__
0x1800b4d05  nop
0x1800b4d06  lea     rcx, [rbp+3Fh+var_88]
0x1800b4d0a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800b4d0f  nop
0x1800b4d10  mov     rcx, [rbp+3Fh+var_A8]
0x1800b4d14  test    rcx, rcx
0x1800b4d17  jz      short loc_1800B4D2A
0x1800b4d19  mov     [rbp+3Fh+var_A8], r14
0x1800b4d1d  mov     rdx, [rcx]
0x1800b4d20  mov     rax, [rdx+10h]
0x1800b4d24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4d29  nop
0x1800b4d2a  mov     rax, rsi
0x1800b4d2d  mov     rcx, [rbp+3Fh+var_50]
0x1800b4d31  xor     rcx, rsp; StackCookie
0x1800b4d34  call    __security_check_cookie
0x1800b4d39  add     rsp, 0D8h
0x1800b4d40  pop     r15
0x1800b4d42  pop     r14
0x1800b4d44  pop     r13
0x1800b4d46  pop     r12
0x1800b4d48  pop     rdi
0x1800b4d49  pop     rsi
0x1800b4d4a  pop     rbx
0x1800b4d4b  pop     rbp
0x1800b4d4c  retn
0x1800b4d4d  mov     r9d, eax; char *
0x1800b4d50  lea     r8, aOnecoreBaseDev_53; "onecore\\base\\devices\\cam\\core\\mcpa"...
0x1800b4d57  mov     edx, 172h; void *
0x1800b4d5c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b4d62  mov     r9d, 8007000Eh; char *
0x1800b4d68  lea     r8, aOnecoreBaseDev_53; "onecore\\base\\devices\\cam\\core\\mcpa"...
0x1800b4d6f  mov     edx, 13Ah; void *
0x1800b4d74  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b4d7a  mov     r9d, eax; char *
0x1800b4d7d  lea     r8, aOnecoreBaseDev_53; "onecore\\base\\devices\\cam\\core\\mcpa"...
0x1800b4d84  mov     edx, 12Ah; void *
0x1800b4d89  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b4d8f  mov     r9d, eax; char *
0x1800b4d92  lea     r8, aOnecoreBaseDev_53; "onecore\\base\\devices\\cam\\core\\mcpa"...
0x1800b4d99  mov     edx, 12Fh; void *
0x1800b4d9e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
