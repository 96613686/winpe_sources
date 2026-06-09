# McpAccessManagerStatics::RequestAccessForUserAsyncInternal(unsigned __int64,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,HSTRING__ *,HSTRING__ *,Windows::Storage::Streams::IRandomAccessStream *,Windows::Storage::Streams::IRandomAccessStream *,HSTRING__ *,uint,Windows::Internal::AI::Agents::Mcp::McpResourceRequestInfo *,Windows::Foundation::IAsyncOperation<Windows::Internal::AI::Agents::Mcp::McpAccessStatus> * *)

- ea: `0x18009d554`
- end: `0x18009d9bc`
- name: `?RequestAccessForUserAsyncInternal@McpAccessManagerStatics@@QEAAX_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHSTRING__@@2PEAUIRandomAccessStream@Streams@Storage@Windows@@32IPEAUMcpResourceRequestInfo@Mcp@Agents@AI@Internal@8@PEAPEAU?$IAsyncOperation@W4McpAccessStatus@Mcp@Agents@AI@Internal@Windows@@@Foundation@8@@Z`
- size: `1128`
- prototype: ``
- caller_count: `2`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18009d3c0`
- `0x18009d9d0`

## callees

- `0x1800094c0`
- `0x180009528`
- `0x180016450`
- `0x18001649c`
- `0x18001c3b4`
- `0x18002392c`
- `0x1800259c4`
- `0x18002f93c`
- `0x18003f4a0`
- `0x180040d7c`
- `0x180043610`
- `0x180099afc`
- `0x180099dc0`
- `0x180099f20`
- `0x18009a110`
- `0x18009a2b4`
- `0x18009a710`
- `0x18009d554`
- `0x18009e4b0`
- `0x1800b81b0`
- `0x1800c7010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009d68a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009d6a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009d6ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009d704`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009d797`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009d68a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009d6a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009d6ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009d704`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009d797`

## string_xrefs

- `0x18009d863`: `Windows.Foundation.IAsyncOperation`1<Windows.Internal.AI.Agents.Mcp.McpAccessStatus>`
- `0x18009d917`: `onecore\base\devices\cam\winrt\mcp\management\mcpaccessmanagerstatics.cpp`
- `0x18009d92f`: `onecore\base\devices\cam\winrt\mcp\management\mcpaccessmanagerstatics.cpp`
- `0x18009d947`: `onecore\base\devices\cam\winrt\mcp\management\mcpaccessmanagerstatics.cpp`
- `0x18009d95f`: `onecore\base\devices\cam\winrt\mcp\management\mcpaccessmanagerstatics.cpp`
- `0x18009d977`: `onecore\base\devices\cam\winrt\mcp\management\mcpaccessmanagerstatics.cpp`
- `0x18009d98f`: `onecore\base\devices\cam\winrt\mcp\management\mcpaccessmanagerstatics.cpp`
- `0x18009d9a7`: `onecore\base\devices\cam\winrt\mcp\management\mcpaccessmanagerstatics.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall McpAccessManagerStatics::RequestAccessForUserAsyncInternal(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        HSTRING a4,
        HSTRING string,
        void *a6,
        __int64 a7,
        HSTRING a8,
        unsigned int a9,
        __int64 a10,
        _QWORD *a11)
{
  _QWORD *v13; // r14
  HSTRING v14; // r15
  char v15; // r12
  unsigned int v16; // r15d
  __int64 v17; // r14
  PCWSTR StringRawBuffer; // rax
  PCWSTR v19; // rax
  PCWSTR v20; // rax
  PCWSTR v21; // rax
  void **v22; // rax
  __int64 UserSidStringFromToken; // rax
  PCWSTR v24; // rax
  __int64 v25; // rax
  void *v26; // rax
  int v27; // r9d
  int v28; // eax
  int v30; // [rsp+28h] [rbp-E0h]
  int v31; // [rsp+28h] [rbp-E0h]
  void *v32; // [rsp+58h] [rbp-B0h] BYREF
  _BYTE v33[12]; // [rsp+60h] [rbp-A8h] BYREF
  __int128 v34; // [rsp+70h] [rbp-98h] BYREF
  __int64 v35; // [rsp+80h] [rbp-88h]
  __int64 v36; // [rsp+88h] [rbp-80h]
  _BYTE v37[32]; // [rsp+98h] [rbp-70h] BYREF
  _BYTE v38[32]; // [rsp+B8h] [rbp-50h] BYREF
  _BYTE v39[32]; // [rsp+D8h] [rbp-30h] BYREF
  _BYTE v40[32]; // [rsp+F8h] [rbp-10h] BYREF
  _BYTE v41[176]; // [rsp+118h] [rbp+10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+200h] [rbp+F8h]
  __int64 v43; // [rsp+210h] [rbp+108h] BYREF

  v43 = a2;
  v36 = a3;
  v13 = a11;
  v32 = a11;
  if ( !a11 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xCE,
      (unsigned int)"onecore\\base\\devices\\cam\\winrt\\mcp\\management\\mcpaccessmanagerstatics.cpp",
      (const char *)0x80004003LL,
      v30);
  if ( !a4 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xCF,
      (unsigned int)"onecore\\base\\devices\\cam\\winrt\\mcp\\management\\mcpaccessmanagerstatics.cpp",
      (const char *)0x80070057LL,
      v30);
  v14 = string;
  if ( !string )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xD0,
      (unsigned int)"onecore\\base\\devices\\cam\\winrt\\mcp\\management\\mcpaccessmanagerstatics.cpp",
      (const char *)0x80070057LL,
      v30);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID61095237>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID61095237>::GetImpl'::`2'::impl)
    && !a9 )
  {
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xD4,
      (unsigned int)"onecore\\base\\devices\\cam\\winrt\\mcp\\management\\mcpaccessmanagerstatics.cpp",
      (const char *)0x80070057LL,
      v30);
  }
  *v13 = 0;
  v15 = Windows::Internal::CapabilityAccess::WinRT::CallerValidation::AccessCheckForRPCCaller((Windows::Internal::CapabilityAccess::WinRT::CallerValidation *)4);
  if ( v15 )
  {
    if ( !*(_QWORD *)(a3 + 16) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xE0,
        (unsigned int)"onecore\\base\\devices\\cam\\winrt\\mcp\\management\\mcpaccessmanagerstatics.cpp",
        (const char *)0x80070057LL,
        v30);
  }
  else if ( !Windows::Internal::CapabilityAccess::WinRT::CallerValidation::AccessCheckForRPCCaller((Windows::Internal::CapabilityAccess::WinRT::CallerValidation *)8)
         && !Windows::Internal::CapabilityAccess::WinRT::CallerValidation::AccessCheckForRPCCaller((Windows::Internal::CapabilityAccess::WinRT::CallerValidation *)2) )
  {
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xE8,
      (unsigned int)"onecore\\base\\devices\\cam\\winrt\\mcp\\management\\mcpaccessmanagerstatics.cpp",
      (const char *)0x80070005LL,
      v30);
  }
  v34 = 0;
  v35 = 0;
  *(_DWORD *)v33 = 0;
  if ( a9 )
  {
    v16 = *(_DWORD *)v33;
    v17 = a10;
    do
    {
      StringRawBuffer = WindowsGetStringRawBuffer(*(HSTRING *)(v17 + 16LL * v16), 0);
      std::wstring::wstring(v37, StringRawBuffer);
      v19 = WindowsGetStringRawBuffer(*(HSTRING *)(v17 + 16LL * v16 + 8), 0);
      std::wstring::wstring(v38, v19);
      std::vector<Windows::Internal::AI::Agents::Mcp::Implementation::InternalMcpResourceRequestInfo>::emplace_back<Windows::Internal::AI::Agents::Mcp::Implementation::InternalMcpResourceRequestInfo &>(
        (__int64 *)&v34,
        (const struct Windows::Internal::AI::Agents::Mcp::Implementation::InternalMcpResourceRequestInfo *)v37);
      std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>(v37);
      ++v16;
    }
    while ( v16 < a9 );
    LODWORD(v13) = (_DWORD)v32;
    v14 = string;
  }
  v20 = WindowsGetStringRawBuffer(a4, 0);
  std::wstring::wstring(v40, v20);
  v21 = WindowsGetStringRawBuffer(v14, 0);
  std::wstring::wstring(v39, v21);
  if ( !v15 )
  {
    v22 = Windows::Internal::CapabilityAccess::Private::GetCallerTokenFromComCall(&v32);
    UserSidStringFromToken = Windows::Internal::CapabilityAccess::Private::GetUserSidStringFromToken(v37, v22);
    std::wstring::operator=(a3, UserSidStringFromToken);
    std::wstring::_Tidy_deallocate(v37);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v32);
  }
  v32 = a6;
  if ( a6 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)a6 + 8LL))(a6);
  *(_QWORD *)v33 = a7;
  if ( a7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a7 + 8LL))(a7);
  v24 = WindowsGetStringRawBuffer(a8, 0);
  v25 = std::wstring::wstring(v37, v24);
  lambda_1172c6193ea301d2c24c8d4d5b548c49_::_lambda_1172c6193ea301d2c24c8d4d5b548c49__0(
    (unsigned int)v41,
    (unsigned int)v40,
    (unsigned int)v39,
    a3,
    (__int64)&v32,
    (__int64)v33,
    v25,
    (__int64)&v34,
    (__int64)&v43);
  std::wstring::_Tidy_deallocate(v37);
  if ( *(_QWORD *)v33 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v33 + 16LL))(*(_QWORD *)v33);
  if ( v32 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v32 + 16LL))(v32);
  *(_DWORD *)v33 = 3;
  *(_QWORD *)&v33[4] = 128;
  v26 = operator new(0xC8u, (const struct std::nothrow_t *)&std::nothrow);
  v32 = v26;
  if ( v26 )
    v26 = (void *)Windows::Internal::COperationLambdaVar_0__lambda_1172c6193ea301d2c24c8d4d5b548c49__Windows::Internal::CBasicResult_enum_Windows::Internal::AI::Agents::Mcp::McpAccessStatus_4___::COperationLambdaVar_0__lambda_1172c6193ea301d2c24c8d4d5b548c49__Windows::Internal::CBasicResult_enum_Windows::Internal::AI::Agents::Mcp::McpAccessStatus_4_____lambda_1172c6193ea301d2c24c8d4d5b548c49___(
                    v26,
                    v41);
  v28 = Windows::Internal::MakeAsyncHelper<Windows::Foundation::IAsyncOperation<enum Windows::Internal::AI::Agents::Mcp::McpAccessStatus>,Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Internal::AI::Agents::Mcp::McpAccessStatus>,Windows::Internal::INilDelegate,Windows::Internal::CBasicResult<enum Windows::Internal::AI::Agents::Mcp::McpAccessStatus,4>,Windows::Internal::ComTaskPoolHandler,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>(
          (_DWORD)v13,
          (unsigned int)v33,
          (unsigned int)L"Windows.Foundation.IAsyncOperation`1<Windows.Internal.AI.Agents.Mcp.McpAccessStatus>",
          v27,
          (__int64)v26);
  if ( v28 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x136,
      (unsigned int)"onecore\\base\\devices\\cam\\winrt\\mcp\\management\\mcpaccessmanagerstatics.cpp",
      (const char *)(unsigned int)v28,
      v31);
  lambda_1172c6193ea301d2c24c8d4d5b548c49_::__lambda_1172c6193ea301d2c24c8d4d5b548c49_(v41);
  std::wstring::_Tidy_deallocate(v39);
  std::wstring::_Tidy_deallocate(v40);
  if ( (_QWORD)v34 )
  {
    std::_Destroy_range<std::allocator<Windows::Internal::AI::Agents::Mcp::Implementation::InternalMcpResourceRequestInfo>>(
      v34,
      *((__int64 *)&v34 + 1));
    std::_Deallocate<16>((void *)v34, (v35 - v34) & 0xFFFFFFFFFFFFFFC0uLL);
    v34 = 0;
    v35 = 0;
  }
  return std::wstring::_Tidy_deallocate(a3);
}

```

## disassembly

```asm
0x18009d554  mov     rax, rsp
0x18009d557  mov     [rax+8], rbx
0x18009d55b  mov     [rax+20h], rdi
0x18009d55f  mov     [rax+10h], rdx
0x18009d563  push    rbp
0x18009d564  push    r12
0x18009d566  push    r13
0x18009d568  push    r14
0x18009d56a  push    r15
0x18009d56c  lea     rbp, [rax-0F8h]
0x18009d573  sub     rsp, 1D0h
0x18009d57a  mov     rax, cs:__security_cookie
0x18009d581  xor     rax, rsp
0x18009d584  mov     [rbp+0F0h+var_30], rax
0x18009d58b  mov     r13, r9
0x18009d58e  mov     rdi, r8
0x18009d591  mov     [rbp+0F0h+var_170], r8
0x18009d595  mov     r14, [rbp+0F0h+arg_50]
0x18009d59c  mov     [rsp+1F0h+var_1A0], r14
0x18009d5a1  mov     rcx, [rbp+0F8h]; this
0x18009d5a8  test    r14, r14
0x18009d5ab  jz      loc_18009D941
0x18009d5b1  mov     rcx, [rbp+0F8h]; this
0x18009d5b8  test    r9, r9
0x18009d5bb  jz      loc_18009D959
0x18009d5c1  mov     rcx, [rbp+0F8h]; this
0x18009d5c8  mov     r15, [rbp+0F0h+string]
0x18009d5cf  test    r15, r15
0x18009d5d2  jz      loc_18009D971
0x18009d5d8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID61095237@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID61095237@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID61095237> `wil::Feature<__WilFeatureTraits_Feature_ID61095237>::GetImpl(void)'::`2'::impl
0x18009d5df  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID61095237@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID61095237>::__private_IsEnabled(void)
0x18009d5e4  test    al, al
0x18009d5e6  jz      short loc_18009D5FC
0x18009d5e8  mov     rcx, [rbp+0F8h]; this
0x18009d5ef  cmp     [rbp+0F0h+arg_40], 0
0x18009d5f6  jz      loc_18009D989
0x18009d5fc  mov     qword ptr [r14], 0
0x18009d603  mov     ecx, 4; this
0x18009d608  call    ?AccessCheckForRPCCaller@CallerValidation@WinRT@CapabilityAccess@Internal@Windows@@YA_NI@Z; Windows::Internal::CapabilityAccess::WinRT::CallerValidation::AccessCheckForRPCCaller(uint)
0x18009d60d  mov     r12b, al
0x18009d610  test    al, al
0x18009d612  jz      short loc_18009D628
0x18009d614  mov     rcx, [rbp+0F8h]; this
0x18009d61b  cmp     qword ptr [rdi+10h], 0
0x18009d620  jz      loc_18009D929
0x18009d626  jmp     short loc_18009D64F
0x18009d628  mov     ecx, 8; this
0x18009d62d  call    ?AccessCheckForRPCCaller@CallerValidation@WinRT@CapabilityAccess@Internal@Windows@@YA_NI@Z; Windows::Internal::CapabilityAccess::WinRT::CallerValidation::AccessCheckForRPCCaller(uint)
0x18009d632  test    al, al
0x18009d634  jnz     short loc_18009D64F
0x18009d636  mov     rbx, [rbp+0F8h]
0x18009d63d  mov     ecx, 2; this
0x18009d642  call    ?AccessCheckForRPCCaller@CallerValidation@WinRT@CapabilityAccess@Internal@Windows@@YA_NI@Z; Windows::Internal::CapabilityAccess::WinRT::CallerValidation::AccessCheckForRPCCaller(uint)
0x18009d647  test    al, al
0x18009d649  jz      loc_18009D9A1
0x18009d64f  xorps   xmm0, xmm0
0x18009d652  movdqu  [rsp+1F0h+var_190+8], xmm0
0x18009d658  mov     [rsp+1F0h+var_178], 0
0x18009d661  mov     dword ptr [rsp+1F0h+var_198], 0
0x18009d669  cmp     [rbp+0F0h+arg_40], 0
0x18009d670  jbe     short loc_18009D6E7
0x18009d672  mov     r15d, dword ptr [rsp+1F0h+var_198]
0x18009d677  mov     r14, [rbp+0F0h+arg_48]
0x18009d67e  mov     ebx, r15d
0x18009d681  add     rbx, rbx
0x18009d684  xor     edx, edx; length
0x18009d686  mov     rcx, [r14+rbx*8]; string
0x18009d68a  call    cs:__imp_WindowsGetStringRawBuffer
0x18009d690  mov     rdx, rax
0x18009d693  lea     rcx, [rbp+0F0h+var_160]
0x18009d697  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18009d69c  nop
0x18009d69d  xor     edx, edx; length
0x18009d69f  mov     rcx, [r14+rbx*8+8]; string
0x18009d6a4  call    cs:__imp_WindowsGetStringRawBuffer
0x18009d6aa  mov     rdx, rax
0x18009d6ad  lea     rcx, [rbp+0F0h+var_140]
0x18009d6b1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18009d6b6  nop
0x18009d6b7  lea     rdx, [rbp+0F0h+var_160]
0x18009d6bb  lea     rcx, [rsp+1F0h+var_190+8]
0x18009d6c0  call    ??$emplace_back@AEAUInternalMcpResourceRequestInfo@Implementation@Mcp@Agents@AI@Internal@Windows@@@?$vector@UInternalMcpResourceRequestInfo@Implementation@Mcp@Agents@AI@Internal@Windows@@V?$allocator@UInternalMcpResourceRequestInfo@Implementation@Mcp@Agents@AI@Internal@Windows@@@std@@@std@@QEAAAEAUInternalMcpResourceRequestInfo@Implementation@Mcp@Agents@AI@Internal@Windows@@AEAU2345678@@Z; std::vector<Windows::Internal::AI::Agents::Mcp::Implementation::InternalMcpResourceRequestInfo>::emplace_back<Windows::Internal::AI::Agents::Mcp::Implementation::InternalMcpResourceRequestInfo &>(Windows::Internal::AI::Agents::Mcp::Implementation::InternalMcpResourceRequestInfo &)
0x18009d6c5  nop
0x18009d6c6  lea     rcx, [rbp+0F0h+var_160]
0x18009d6ca  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@QEAA@XZ; std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>(void)
0x18009d6cf  inc     r15d
0x18009d6d2  cmp     r15d, [rbp+0F0h+arg_40]
0x18009d6d9  jb      short loc_18009D67E
0x18009d6db  mov     r14, [rsp+1F0h+var_1A0]
0x18009d6e0  mov     r15, [rbp+0F0h+string]
0x18009d6e7  xor     edx, edx; length
0x18009d6e9  mov     rcx, r13; string
0x18009d6ec  call    cs:__imp_WindowsGetStringRawBuffer
0x18009d6f2  mov     rdx, rax
0x18009d6f5  lea     rcx, [rbp+0F0h+var_100]
0x18009d6f9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18009d6fe  nop
0x18009d6ff  xor     edx, edx; length
0x18009d701  mov     rcx, r15; string
0x18009d704  call    cs:__imp_WindowsGetStringRawBuffer
0x18009d70a  mov     rdx, rax
0x18009d70d  lea     rcx, [rbp+0F0h+var_120]
0x18009d711  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18009d716  nop
0x18009d717  test    r12b, r12b
0x18009d71a  jnz     short loc_18009D752
0x18009d71c  lea     rcx, [rsp+1F0h+var_1A0]
0x18009d721  call    ?GetCallerTokenFromComCall@Private@CapabilityAccess@Internal@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ; Windows::Internal::CapabilityAccess::Private::GetCallerTokenFromComCall(void)
0x18009d726  nop
0x18009d727  mov     rdx, rax
0x18009d72a  lea     rcx, [rbp+0F0h+var_160]
0x18009d72e  call    ?GetUserSidStringFromToken@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z; Windows::Internal::CapabilityAccess::Private::GetUserSidStringFromToken(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> const &)
0x18009d733  mov     rdx, rax
0x18009d736  mov     rcx, rdi
0x18009d739  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18009d73e  lea     rcx, [rbp+0F0h+var_160]
0x18009d742  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009d747  nop
0x18009d748  lea     rcx, [rsp+1F0h+var_1A0]
0x18009d74d  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18009d752  mov     rcx, [rbp+0F0h+arg_28]
0x18009d759  mov     [rsp+1F0h+var_1A0], rcx
0x18009d75e  test    rcx, rcx
0x18009d761  jz      short loc_18009D770
0x18009d763  mov     rax, [rcx]
0x18009d766  mov     rax, [rax+8]
0x18009d76a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d76f  nop
0x18009d770  mov     rcx, [rbp+0F0h+arg_30]
0x18009d777  mov     [rsp+1F0h+var_198], rcx
0x18009d77c  test    rcx, rcx
0x18009d77f  jz      short loc_18009D78E
0x18009d781  mov     rax, [rcx]
0x18009d784  mov     rax, [rax+8]
0x18009d788  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d78d  nop
0x18009d78e  xor     edx, edx; length
0x18009d790  mov     rcx, [rbp+0F0h+arg_38]; string
0x18009d797  call    cs:__imp_WindowsGetStringRawBuffer
0x18009d79d  mov     rdx, rax
0x18009d7a0  lea     rcx, [rbp+0F0h+var_160]
0x18009d7a4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18009d7a9  lea     rcx, [rbp+0F0h+arg_8]
0x18009d7b0  mov     [rsp+1F0h+var_1B0], rcx
0x18009d7b5  lea     rcx, [rsp+1F0h+var_190+8]
0x18009d7ba  mov     [rsp+1F0h+var_1B8], rcx
0x18009d7bf  mov     [rsp+1F0h+var_1C0], rax
0x18009d7c4  lea     rax, [rsp+1F0h+var_198]
0x18009d7c9  mov     [rsp+1F0h+var_1C8], rax
0x18009d7ce  lea     rax, [rsp+1F0h+var_1A0]
0x18009d7d3  mov     qword ptr [rsp+1F0h+var_1D0], rax
0x18009d7d8  mov     r9, rdi
0x18009d7db  lea     r8, [rbp+0F0h+var_120]
0x18009d7df  lea     rdx, [rbp+0F0h+var_100]
0x18009d7e3  lea     rcx, [rbp+0F0h+var_E0]
0x18009d7e7  call    _lambda_1172c6193ea301d2c24c8d4d5b548c49____lambda_1172c6193ea301d2c24c8d4d5b548c49__0
0x18009d7ec  nop
0x18009d7ed  lea     rcx, [rbp+0F0h+var_160]
0x18009d7f1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009d7f6  nop
0x18009d7f7  mov     rcx, [rsp+1F0h+var_198]
0x18009d7fc  test    rcx, rcx
0x18009d7ff  jz      short loc_18009D80E
0x18009d801  mov     rax, [rcx]
0x18009d804  mov     rax, [rax+10h]
0x18009d808  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d80d  nop
0x18009d80e  mov     rcx, [rsp+1F0h+var_1A0]
0x18009d813  test    rcx, rcx
0x18009d816  jz      short loc_18009D825
0x18009d818  mov     rax, [rcx]
0x18009d81b  mov     rax, [rax+10h]
0x18009d81f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d824  nop
0x18009d825  mov     dword ptr [rsp+1F0h+var_198], 3
0x18009d82d  mov     [rsp+1F0h+var_198+4], 80h
0x18009d836  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18009d83d  mov     ecx, 0C8h; unsigned __int64
0x18009d842  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18009d847  mov     [rsp+1F0h+var_1A0], rax
0x18009d84c  test    rax, rax
0x18009d84f  jz      short loc_18009D85E
0x18009d851  lea     rdx, [rbp+0F0h+var_E0]
0x18009d855  mov     rcx, rax
0x18009d858  call    Windows__Internal__COperationLambdaVar_0__lambda_1172c6193ea301d2c24c8d4d5b548c49__Windows__Internal__CBasicResult_enum_Windows__Internal__AI__Agents__Mcp__McpAccessStatus_4_____COperationLambdaVar_0__lambda_1172c6193ea301d2c24c8d4d5b548c49__Windows__Internal__CBasicResult_enum_Windows__Internal__AI__Agents__Mcp__McpAccessStatus_4_____lambda_1172c6193ea301d2c24c8d4d5b548c49___
0x18009d85d  nop
0x18009d85e  mov     qword ptr [rsp+1F0h+var_1D0], rax; int
0x18009d863  lea     r8, aWindowsFoundat_8; "Windows.Foundation.IAsyncOperation`1<Wi"...
0x18009d86a  lea     rdx, [rsp+1F0h+var_198]
0x18009d86f  mov     rcx, r14
0x18009d872  call    ??$MakeAsyncHelper@U?$IAsyncOperation@W4McpAccessStatus@Mcp@Agents@AI@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@W4McpAccessStatus@Mcp@Agents@AI@Internal@Windows@@@23@UINilDelegate@Internal@3@V?$CBasicResult@W4McpAccessStatus@Mcp@Agents@AI@Internal@Windows@@$03@63@VComTaskPoolHandler@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@YAJPEAPEAU?$IAsyncOperation@W4McpAccessStatus@Mcp@Agents@AI@Internal@Windows@@@Foundation@1@$$QEAVComTaskPoolHandler@01@QEBGW4TrustLevel@@PEAV?$AsyncCallbackBase@V?$CBasicResult@W4McpAccessStatus@Mcp@Agents@AI@Internal@Windows@@$03@Internal@Windows@@@01@@Z; Windows::Internal::MakeAsyncHelper<Windows::Foundation::IAsyncOperation<Windows::Internal::AI::Agents::Mcp::McpAccessStatus>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::AI::Agents::Mcp::McpAccessStatus>,Windows::Internal::INilDelegate,Windows::Internal::CBasicResult<Windows::Internal::AI::Agents::Mcp::McpAccessStatus,4>,Windows::Internal::ComTaskPoolHandler,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>(Windows::Foundation::IAsyncOperation<Windows::Internal::AI::Agents::Mcp::McpAccessStatus> * *,Windows::Internal::ComTaskPoolHandler &&,ushort const * const,TrustLevel,Windows::Internal::AsyncCallbackBase<Windows::Internal::CBasicResult<Windows::Internal::AI::Agents::Mcp::McpAccessStatus,4>> *)
0x18009d877  mov     rcx, [rbp+0F8h]; this
0x18009d87e  test    eax, eax
0x18009d880  js      loc_18009D914
0x18009d886  lea     rcx, [rbp+0F0h+var_E0]
0x18009d88a  call    _lambda_1172c6193ea301d2c24c8d4d5b548c49_____lambda_1172c6193ea301d2c24c8d4d5b548c49_
0x18009d88f  nop
0x18009d890  lea     rcx, [rbp+0F0h+var_120]
0x18009d894  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009d899  nop
0x18009d89a  lea     rcx, [rbp+0F0h+var_100]
0x18009d89e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009d8a3  nop
0x18009d8a4  mov     rcx, qword ptr [rsp+1F0h+var_190+8]
0x18009d8a9  test    rcx, rcx
0x18009d8ac  jz      short loc_18009D8E0
0x18009d8ae  mov     rdx, [rsp+1F0h+var_180]
0x18009d8b3  call    ??$_Destroy_range@V?$allocator@UInternalMcpResourceRequestInfo@Implementation@Mcp@Agents@AI@Internal@Windows@@@std@@@std@@YAXPEAUInternalMcpResourceRequestInfo@Implementation@Mcp@Agents@AI@Internal@Windows@@QEAU1234567@AEAV?$allocator@UInternalMcpResourceRequestInfo@Implementation@Mcp@Agents@AI@Internal@Windows@@@0@@Z; std::_Destroy_range<std::allocator<Windows::Internal::AI::Agents::Mcp::Implementation::InternalMcpResourceRequestInfo>>(Windows::Internal::AI::Agents::Mcp::Implementation::InternalMcpResourceRequestInfo *,Windows::Internal::AI::Agents::Mcp::Implementation::InternalMcpResourceRequestInfo * const,std::allocator<Windows::Internal::AI::Agents::Mcp::Implementation::InternalMcpResourceRequestInfo> &)
0x18009d8b8  mov     rcx, qword ptr [rsp+1F0h+var_190+8]
0x18009d8bd  mov     rdx, [rsp+1F0h+var_178]
0x18009d8c2  sub     rdx, rcx
0x18009d8c5  and     rdx, 0FFFFFFFFFFFFFFC0h
0x18009d8c9  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18009d8ce  xorps   xmm0, xmm0
0x18009d8d1  movdqu  [rsp+1F0h+var_190+8], xmm0
0x18009d8d7  mov     [rsp+1F0h+var_178], 0
0x18009d8e0  mov     rcx, rdi
0x18009d8e3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009d8e8  mov     rcx, [rbp+0F0h+var_30]
0x18009d8ef  xor     rcx, rsp; StackCookie
0x18009d8f2  call    __security_check_cookie
0x18009d8f7  lea     r11, [rsp+1F0h+var_20]
0x18009d8ff  mov     rbx, [r11+30h]
0x18009d903  mov     rdi, [r11+48h]
0x18009d907  mov     rsp, r11
0x18009d90a  pop     r15
0x18009d90c  pop     r14
0x18009d90e  pop     r13
0x18009d910  pop     r12
0x18009d912  pop     rbp
0x18009d913  retn
0x18009d914  mov     r9d, eax; char *
0x18009d917  lea     r8, aOnecoreBaseDev_20; "onecore\\base\\devices\\cam\\winrt\\mcp"...
0x18009d91e  mov     edx, 136h; void *
0x18009d923  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009d929  mov     r9d, 80070057h; char *
0x18009d92f  lea     r8, aOnecoreBaseDev_20; "onecore\\base\\devices\\cam\\winrt\\mcp"...
0x18009d936  mov     edx, 0E0h; void *
0x18009d93b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009d941  mov     r9d, 80004003h; char *
0x18009d947  lea     r8, aOnecoreBaseDev_20; "onecore\\base\\devices\\cam\\winrt\\mcp"...
0x18009d94e  mov     edx, 0CEh; void *
0x18009d953  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009d959  mov     r9d, 80070057h; char *
0x18009d95f  lea     r8, aOnecoreBaseDev_20; "onecore\\base\\devices\\cam\\winrt\\mcp"...
0x18009d966  mov     edx, 0CFh; void *
0x18009d96b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009d971  mov     r9d, 80070057h; char *
0x18009d977  lea     r8, aOnecoreBaseDev_20; "onecore\\base\\devices\\cam\\winrt\\mcp"...
0x18009d97e  mov     edx, 0D0h; void *
0x18009d983  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009d989  mov     r9d, 80070057h; char *
0x18009d98f  lea     r8, aOnecoreBaseDev_20; "onecore\\base\\devices\\cam\\winrt\\mcp"...
0x18009d996  mov     edx, 0D4h; void *
0x18009d99b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009d9a1  mov     r9d, 80070005h; char *
0x18009d9a7  lea     r8, aOnecoreBaseDev_20; "onecore\\base\\devices\\cam\\winrt\\mcp"...
0x18009d9ae  mov     edx, 0E8h; void *
0x18009d9b3  mov     rcx, rbx; this
0x18009d9b6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
