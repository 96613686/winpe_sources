# McpConsentManagerStatics::GetConsentsForServer(HSTRING__ *,HSTRING__ *,uint *,Windows::Internal::AI::Agents::Mcp::McpConsentKeyValue * *)

- ea: `0x1800992f0`
- end: `0x180099724`
- name: `?GetConsentsForServer@McpConsentManagerStatics@@UEAAJPEAUHSTRING__@@0PEAIPEAPEAUMcpConsentKeyValue@Mcp@Agents@AI@Internal@Windows@@@Z`
- size: `1076`
- prototype: `int(McpConsentManagerStatics *__hidden this, HSTRING, HSTRING, unsigned int *, struct Windows::Internal::AI::Agents::Mcp::McpConsentKeyValue **)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800094c0`
- `0x180016450`
- `0x18001649c`
- `0x18001c3b4`
- `0x18002392c`
- `0x180029408`
- `0x18002f240`
- `0x18003f4a0`
- `0x180040d7c`
- `0x180043610`
- `0x18009862c`
- `0x1800992f0`
- `0x1800b77c0`
- `0x1800b81b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800994a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800994a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800994fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180099525`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180099555`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18009958f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800994fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180099525`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180099555`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18009958f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180099391`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009940a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180099391`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009940a`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall McpConsentManagerStatics::GetConsentsForServer(
        McpConsentManagerStatics *this,
        HSTRING a2,
        HSTRING a3,
        unsigned int *a4,
        struct Windows::Internal::AI::Agents::Mcp::McpConsentKeyValue **a5)
{
  unsigned int v8; // edx
  PCWSTR StringRawBuffer; // rax
  __int64 UserSidStringFromToken; // rdi
  int v11; // ebx
  unsigned int v12; // edx
  __int64 v13; // rax
  PCWSTR v14; // rax
  char v15; // bl
  const char *v16; // r9
  Windows::Internal::AI::Agents::Mcp::Implementation::InternalMcpConsentKey *v17; // rdx
  Windows::Internal::AI::Agents::Mcp::Implementation::InternalMcpConsentKey *v18; // rcx
  struct Windows::Internal::AI::Agents::Mcp::McpConsentKeyValue *v19; // r15
  __int64 v20; // rdi
  UINT32 *v21; // rbx
  UINT32 *v22; // r12
  char *v23; // rsi
  const WCHAR *v24; // rax
  HRESULT String; // eax
  const WCHAR *v26; // rax
  HRESULT v27; // eax
  const WCHAR *v28; // rax
  HRESULT v29; // eax
  const WCHAR *v30; // rax
  HRESULT v31; // eax
  __int64 result; // rax
  int v33[2]; // [rsp+20h] [rbp-C8h] BYREF
  Windows::Internal::AI::Agents::Mcp::Implementation::InternalMcpConsentKey *v34; // [rsp+28h] [rbp-C0h] BYREF
  Windows::Internal::AI::Agents::Mcp::Implementation::InternalMcpConsentKey *v35; // [rsp+30h] [rbp-B8h]
  __int64 v36; // [rsp+38h] [rbp-B0h]
  _BYTE v37[8]; // [rsp+40h] [rbp-A8h] BYREF
  struct Windows::Internal::AI::Agents::Mcp::McpConsentKeyValue **v38; // [rsp+48h] [rbp-A0h]
  _BYTE v39[32]; // [rsp+50h] [rbp-98h] BYREF
  _BYTE v40[32]; // [rsp+70h] [rbp-78h] BYREF
  _BYTE v41[32]; // [rsp+90h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  try
  {
    v38 = a5;
    v33[0] = 0;
    if ( !a3 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xE2,
        (unsigned int)"onecore\\base\\devices\\cam\\winrt\\mcp\\management\\mcpconsentmanagerstatics.cpp",
        (const char *)0x80070057LL,
        v33[0]);
    if ( !a4 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xE3,
        (unsigned int)"onecore\\base\\devices\\cam\\winrt\\mcp\\management\\mcpconsentmanagerstatics.cpp",
        (const char *)0x80004003LL,
        v33[0]);
    if ( !a5 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xE4,
        (unsigned int)"onecore\\base\\devices\\cam\\winrt\\mcp\\management\\mcpconsentmanagerstatics.cpp",
        (const char *)0x80004003LL,
        v33[0]);
    if ( Windows::Internal::CapabilityAccess::WinRT::CallerValidation::AccessCheckForRPCCaller(
           (Windows::Internal::CapabilityAccess::WinRT::CallerValidation *)4,
           (unsigned int)a2) )
    {
      if ( !a2 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xED,
          (unsigned int)"onecore\\base\\devices\\cam\\winrt\\mcp\\management\\mcpconsentmanagerstatics.cpp",
          (const char *)0x80070057LL,
          v33[0]);
      StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
      UserSidStringFromToken = std::wstring::wstring(v41, StringRawBuffer);
      v11 = 1;
    }
    else
    {
      if ( !Windows::Internal::CapabilityAccess::WinRT::CallerValidation::AccessCheckForRPCCaller(
              (Windows::Internal::CapabilityAccess::WinRT::CallerValidation *)8,
              v8)
        && !Windows::Internal::CapabilityAccess::WinRT::CallerValidation::AccessCheckForRPCCaller(
              (Windows::Internal::CapabilityAccess::WinRT::CallerValidation *)3,
              v12) )
      {
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xF9,
          (unsigned int)"onecore\\base\\devices\\cam\\winrt\\mcp\\management\\mcpconsentmanagerstatics.cpp",
          (const char *)0x80070005LL,
          v33[0]);
      }
      v13 = Windows::Internal::CapabilityAccess::Private::GetCallerTokenFromComCall(v37);
      v33[0] = 2;
      UserSidStringFromToken = Windows::Internal::CapabilityAccess::Private::GetUserSidStringFromToken(v40, v13);
      v11 = 6;
    }
    v33[0] = v11;
    v14 = WindowsGetStringRawBuffer(a3, 0);
    std::wstring::wstring(v39, v14);
    Windows::Internal::AI::Agents::Mcp::Implementation::McpConsentStore::GetConsentsForServer(
      &v34,
      v39,
      UserSidStringFromToken);
    v15 = v11 | 8;
    std::wstring::_Tidy_deallocate(v39);
    if ( (v15 & 4) != 0 )
    {
      v15 &= ~4u;
      std::wstring::_Tidy_deallocate(v40);
    }
    if ( (v15 & 2) != 0 )
    {
      v15 &= ~2u;
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v37);
    }
    if ( (v15 & 1) != 0 )
      std::wstring::_Tidy_deallocate(v41);
    v17 = v35;
    v18 = v34;
    if ( v34 != v35 )
    {
      v19 = (struct Windows::Internal::AI::Agents::Mcp::McpConsentKeyValue *)CoTaskMemAlloc(
                                                                               0xA5A5A5A5A5A5A5A8uLL
                                                                             * ((v35 - v34) >> 3));
      *(_QWORD *)v33 = v19;
      if ( !v19 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x114,
          (unsigned int)"onecore\\base\\devices\\cam\\winrt\\mcp\\management\\mcpconsentmanagerstatics.cpp",
          (const char *)0x8007000ELL,
          0);
      v20 = 0;
      v21 = (UINT32 *)v34;
      v22 = (UINT32 *)v35;
      while ( v21 != v22 )
      {
        v23 = (char *)v19 + 40 * v20;
        *((_DWORD *)v23 + 8) = v21[32];
        v24 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v21);
        String = WindowsCreateString(v24, v21[4], (HSTRING *)v23);
        if ( String < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x135,
            (unsigned int)"onecore\\base\\devices\\cam\\winrt\\mcp\\management\\mcpconsentmanagerstatics.cpp",
            (const char *)(unsigned int)String,
            v33[0]);
        v26 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v21 + 8);
        v27 = WindowsCreateString(v26, v21[12], (HSTRING *)v23 + 1);
        if ( v27 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x13B,
            (unsigned int)"onecore\\base\\devices\\cam\\winrt\\mcp\\management\\mcpconsentmanagerstatics.cpp",
            (const char *)(unsigned int)v27,
            v33[0]);
        if ( *((_QWORD *)v21 + 10) )
        {
          v28 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v21 + 16);
          v29 = WindowsCreateString(v28, v21[20], (HSTRING *)v23 + 2);
          if ( v29 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x143,
              (unsigned int)"onecore\\base\\devices\\cam\\winrt\\mcp\\management\\mcpconsentmanagerstatics.cpp",
              (const char *)(unsigned int)v29,
              v33[0]);
        }
        else
        {
          *((_QWORD *)v23 + 2) = 0;
        }
        if ( *((_QWORD *)v21 + 14) )
        {
          v30 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v21 + 24);
          v31 = WindowsCreateString(v30, v21[28], (HSTRING *)v23 + 3);
          if ( v31 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x150,
              (unsigned int)"onecore\\base\\devices\\cam\\winrt\\mcp\\management\\mcpconsentmanagerstatics.cpp",
              (const char *)(unsigned int)v31,
              v33[0]);
        }
        else
        {
          *((_QWORD *)v23 + 3) = 0;
        }
        ++v20;
        v21 += 34;
      }
      *(_QWORD *)v33 = 0;
      *v38 = v19;
      *a4 = v20;
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v33);
      v17 = v35;
      v18 = v34;
    }
    if ( v18 )
    {
      std::_Destroy_range<std::allocator<Windows::Internal::CapabilityAccess::Extensions::Storage::APIWrappers::MCP::McpConsent>>(
        v18,
        v17);
      std::_Deallocate<16>(v34, 8 * ((v36 - (__int64)v34) >> 3));
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x165,
                           (unsigned int)"onecore\\base\\devices\\cam\\winrt\\mcp\\management\\mcpconsentmanagerstatics.cpp",
                           v16);
  }
  return result;
}

```

## disassembly

```asm
0x1800992f0  mov     [rsp+arg_0], rbx
0x1800992f5  mov     [rsp+arg_8], rsi
0x1800992fa  push    rdi
0x1800992fb  push    r12
0x1800992fd  push    r13
0x1800992ff  push    r14
0x180099301  push    r15
0x180099303  sub     rsp, 0C0h
0x18009930a  mov     rax, cs:__security_cookie
0x180099311  xor     rax, rsp
0x180099314  mov     [rsp+0E8h+var_38], rax
0x18009931c  mov     r13, r9
0x18009931f  mov     rsi, r8
0x180099322  mov     rbx, rdx
0x180099325  mov     rax, [rsp+0E8h+arg_20]
0x18009932d  mov     [rsp+0E8h+var_A0], rax
0x180099332  mov     [rsp+0E8h+var_C8], 0; int
0x18009933a  mov     rcx, [rsp+0E8h]; this
0x180099342  test    r8, r8
0x180099345  jz      loc_180099647
0x18009934b  mov     rcx, [rsp+0E8h]; this
0x180099353  test    r13, r13
0x180099356  jz      loc_18009965E
0x18009935c  mov     rcx, [rsp+0E8h]; this
0x180099364  test    rax, rax
0x180099367  jz      loc_180099675
0x18009936d  mov     ecx, 4; this
0x180099372  call    ?AccessCheckForRPCCaller@CallerValidation@WinRT@CapabilityAccess@Internal@Windows@@YA_NI@Z; Windows::Internal::CapabilityAccess::WinRT::CallerValidation::AccessCheckForRPCCaller(uint)
0x180099377  test    al, al
0x180099379  jz      short loc_1800993B1
0x18009937b  mov     rcx, [rsp+0E8h]; this
0x180099383  test    rbx, rbx
0x180099386  jz      loc_18009968C
0x18009938c  xor     edx, edx; length
0x18009938e  mov     rcx, rbx; string
0x180099391  call    cs:__imp_WindowsGetStringRawBuffer
0x180099397  mov     rdx, rax
0x18009939a  lea     rcx, [rsp+0E8h+var_58]
0x1800993a2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800993a7  mov     rdi, rax
0x1800993aa  mov     ebx, 1
0x1800993af  jmp     short loc_180099401
0x1800993b1  mov     ecx, 8; this
0x1800993b6  call    ?AccessCheckForRPCCaller@CallerValidation@WinRT@CapabilityAccess@Internal@Windows@@YA_NI@Z; Windows::Internal::CapabilityAccess::WinRT::CallerValidation::AccessCheckForRPCCaller(uint)
0x1800993bb  test    al, al
0x1800993bd  jnz     short loc_1800993D9
0x1800993bf  mov     ecx, 3; this
0x1800993c4  call    ?AccessCheckForRPCCaller@CallerValidation@WinRT@CapabilityAccess@Internal@Windows@@YA_NI@Z; Windows::Internal::CapabilityAccess::WinRT::CallerValidation::AccessCheckForRPCCaller(uint)
0x1800993c9  mov     rcx, [rsp+0E8h]; this
0x1800993d1  test    al, al
0x1800993d3  jz      loc_1800996A3
0x1800993d9  lea     rcx, [rsp+0E8h+var_A8]
0x1800993de  call    ?GetCallerTokenFromComCall@Private@CapabilityAccess@Internal@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ; Windows::Internal::CapabilityAccess::Private::GetCallerTokenFromComCall(void)
0x1800993e3  nop
0x1800993e4  mov     [rsp+0E8h+var_C8], 2
0x1800993ec  mov     rdx, rax
0x1800993ef  lea     rcx, [rsp+0E8h+var_78]
0x1800993f4  call    ?GetUserSidStringFromToken@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z; Windows::Internal::CapabilityAccess::Private::GetUserSidStringFromToken(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> const &)
0x1800993f9  mov     rdi, rax
0x1800993fc  mov     ebx, 6
0x180099401  mov     [rsp+0E8h+var_C8], ebx
0x180099405  xor     edx, edx; length
0x180099407  mov     rcx, rsi; string
0x18009940a  call    cs:__imp_WindowsGetStringRawBuffer
0x180099410  mov     rdx, rax
0x180099413  lea     rcx, [rsp+0E8h+var_98]
0x180099418  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18009941d  nop
0x18009941e  mov     r8, rdi
0x180099421  lea     rdx, [rsp+0E8h+var_98]
0x180099426  lea     rcx, [rsp+0E8h+var_C0]
0x18009942b  call    ?GetConsentsForServer@McpConsentStore@Implementation@Mcp@Agents@AI@Internal@Windows@@SA?AV?$vector@UInternalMcpConsentKeyValue@Implementation@Mcp@Agents@AI@Internal@Windows@@V?$allocator@UInternalMcpConsentKeyValue@Implementation@Mcp@Agents@AI@Internal@Windows@@@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@9@0@Z; Windows::Internal::AI::Agents::Mcp::Implementation::McpConsentStore::GetConsentsForServer(std::wstring const &,std::wstring const &)
0x180099430  or      ebx, 8
0x180099433  lea     rcx, [rsp+0E8h+var_98]
0x180099438  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009943d  nop
0x18009943e  test    bl, 4
0x180099441  jz      short loc_180099451
0x180099443  and     ebx, 0FFFFFFFBh
0x180099446  lea     rcx, [rsp+0E8h+var_78]
0x18009944b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180099450  nop
0x180099451  test    bl, 2
0x180099454  jz      short loc_180099464
0x180099456  and     ebx, 0FFFFFFFDh
0x180099459  lea     rcx, [rsp+0E8h+var_A8]
0x18009945e  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180099463  nop
0x180099464  test    bl, 1
0x180099467  jz      short loc_180099476
0x180099469  lea     rcx, [rsp+0E8h+var_58]
0x180099471  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180099476  mov     rdx, [rsp+0E8h+var_B8]
0x18009947b  mov     rcx, [rsp+0E8h+var_C0]
0x180099480  mov     r14, 0F0F0F0F0F0F0F0F1h
0x18009948a  cmp     rcx, rdx
0x18009948d  jz      loc_1800995E7
0x180099493  sub     rdx, rcx
0x180099496  sar     rdx, 3
0x18009949a  imul    rdx, r14
0x18009949e  lea     rcx, [rdx+rdx*4]
0x1800994a2  shl     rcx, 3; cb
0x1800994a6  call    cs:__imp_CoTaskMemAlloc
0x1800994ac  mov     r15, rax
0x1800994af  mov     qword ptr [rsp+0E8h+var_C8], rax; int
0x1800994b4  mov     rcx, [rsp+0E8h]; this
0x1800994bc  test    rax, rax
0x1800994bf  jz      loc_1800996BB
0x1800994c5  xor     edi, edi
0x1800994c7  mov     rbx, [rsp+0E8h+var_C0]
0x1800994cc  mov     r12, [rsp+0E8h+var_B8]
0x1800994d1  cmp     rbx, r12
0x1800994d4  jz      loc_1800995BE
0x1800994da  lea     rax, [rdi+rdi*4]
0x1800994de  lea     rsi, [r15+rax*8]
0x1800994e2  mov     eax, [rbx+80h]
0x1800994e8  mov     [rsi+20h], eax
0x1800994eb  mov     rcx, rbx
0x1800994ee  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800994f3  mov     r8, rsi; string
0x1800994f6  mov     edx, [rbx+10h]; length
0x1800994f9  mov     rcx, rax; sourceString
0x1800994fc  call    cs:__imp_WindowsCreateString
0x180099502  mov     rcx, [rsp+0E8h]; this
0x18009950a  test    eax, eax
0x18009950c  js      loc_1800996D2
0x180099512  lea     rcx, [rbx+20h]
0x180099516  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18009951b  lea     r8, [rsi+8]; string
0x18009951f  mov     edx, [rbx+30h]; length
0x180099522  mov     rcx, rax; sourceString
0x180099525  call    cs:__imp_WindowsCreateString
0x18009952b  mov     rcx, [rsp+0E8h]; this
0x180099533  test    eax, eax
0x180099535  js      loc_1800996E6
0x18009953b  cmp     qword ptr [rbx+50h], 0
0x180099540  jbe     short loc_18009956D
0x180099542  lea     rcx, [rbx+40h]
0x180099546  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18009954b  lea     r8, [rsi+10h]; string
0x18009954f  mov     edx, [rbx+50h]; length
0x180099552  mov     rcx, rax; sourceString
0x180099555  call    cs:__imp_WindowsCreateString
0x18009955b  mov     rcx, [rsp+0E8h]; this
0x180099563  test    eax, eax
0x180099565  js      loc_1800996FA
0x18009956b  jmp     short loc_180099575
0x18009956d  mov     qword ptr [rsi+10h], 0
0x180099575  cmp     qword ptr [rbx+70h], 0
0x18009957a  jbe     short loc_1800995A7
0x18009957c  lea     rcx, [rbx+60h]
0x180099580  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180099585  lea     r8, [rsi+18h]; string
0x180099589  mov     edx, [rbx+70h]; length
0x18009958c  mov     rcx, rax; sourceString
0x18009958f  call    cs:__imp_WindowsCreateString
0x180099595  mov     rcx, [rsp+0E8h]; this
0x18009959d  test    eax, eax
0x18009959f  js      loc_18009970E
0x1800995a5  jmp     short loc_1800995AF
0x1800995a7  mov     qword ptr [rsi+18h], 0
0x1800995af  inc     rdi
0x1800995b2  add     rbx, 88h
0x1800995b9  jmp     loc_1800994D1
0x1800995be  mov     qword ptr [rsp+0E8h+var_C8], 0
0x1800995c7  mov     rax, [rsp+0E8h+var_A0]
0x1800995cc  mov     [rax], r15
0x1800995cf  mov     [r13+0], edi
0x1800995d3  lea     rcx, [rsp+0E8h+var_C8]
0x1800995d8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800995dd  mov     rdx, [rsp+0E8h+var_B8]
0x1800995e2  mov     rcx, [rsp+0E8h+var_C0]; this
0x1800995e7  test    rcx, rcx
0x1800995ea  jz      short loc_180099612
0x1800995ec  call    ??$_Destroy_range@V?$allocator@UMcpConsent@MCP@APIWrappers@Storage@Extensions@CapabilityAccess@Internal@Windows@@@std@@@std@@YAXPEAUMcpConsent@MCP@APIWrappers@Storage@Extensions@CapabilityAccess@Internal@Windows@@QEAU12345678@AEAV?$allocator@UMcpConsent@MCP@APIWrappers@Storage@Extensions@CapabilityAccess@Internal@Windows@@@0@@Z; std::_Destroy_range<std::allocator<Windows::Internal::CapabilityAccess::Extensions::Storage::APIWrappers::MCP::McpConsent>>(Windows::Internal::CapabilityAccess::Extensions::Storage::APIWrappers::MCP::McpConsent *,Windows::Internal::CapabilityAccess::Extensions::Storage::APIWrappers::MCP::McpConsent * const,std::allocator<Windows::Internal::CapabilityAccess::Extensions::Storage::APIWrappers::MCP::McpConsent> &)
0x1800995f1  mov     rcx, [rsp+0E8h+var_C0]
0x1800995f6  mov     rax, [rsp+0E8h+var_B0]
0x1800995fb  sub     rax, rcx
0x1800995fe  sar     rax, 3
0x180099602  imul    rax, r14
0x180099606  imul    rdx, rax, 88h
0x18009960d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180099612  xor     eax, eax
0x180099614  jmp     short loc_18009961A
0x180099616  mov     eax, [rsp+0E8h+var_C8]
0x18009961a  mov     rcx, [rsp+0E8h+var_38]
0x180099622  xor     rcx, rsp; StackCookie
0x180099625  call    __security_check_cookie
0x18009962a  lea     r11, [rsp+0E8h+var_28]
0x180099632  mov     rbx, [r11+30h]
0x180099636  mov     rsi, [r11+38h]
0x18009963a  mov     rsp, r11
0x18009963d  pop     r15
0x18009963f  pop     r14
0x180099641  pop     r13
0x180099643  pop     r12
0x180099645  pop     rdi
0x180099646  retn
0x180099647  mov     r9d, 80070057h; char *
0x18009964d  lea     r8, aOnecoreBaseDev_45; "onecore\\base\\devices\\cam\\winrt\\mcp"...
0x180099654  mov     edx, 0E2h; void *
0x180099659  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009965e  mov     r9d, 80004003h; char *
0x180099664  lea     r8, aOnecoreBaseDev_45; "onecore\\base\\devices\\cam\\winrt\\mcp"...
0x18009966b  mov     edx, 0E3h; void *
0x180099670  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180099675  mov     r9d, 80004003h; char *
0x18009967b  lea     r8, aOnecoreBaseDev_45; "onecore\\base\\devices\\cam\\winrt\\mcp"...
0x180099682  mov     edx, 0E4h; void *
0x180099687  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009968c  mov     r9d, 80070057h; char *
0x180099692  lea     r8, aOnecoreBaseDev_45; "onecore\\base\\devices\\cam\\winrt\\mcp"...
0x180099699  mov     edx, 0EDh; void *
0x18009969e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800996a3  mov     r9d, 80070005h; char *
0x1800996a9  lea     r8, aOnecoreBaseDev_45; "onecore\\base\\devices\\cam\\winrt\\mcp"...
0x1800996b0  mov     edx, 0F9h; void *
0x1800996b5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800996bb  mov     r9d, 8007000Eh; char *
0x1800996c1  lea     r8, aOnecoreBaseDev_45; "onecore\\base\\devices\\cam\\winrt\\mcp"...
0x1800996c8  mov     edx, 114h; void *
0x1800996cd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800996d2  mov     r9d, eax; char *
0x1800996d5  lea     r8, aOnecoreBaseDev_45; "onecore\\base\\devices\\cam\\winrt\\mcp"...
0x1800996dc  mov     edx, 135h; void *
0x1800996e1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800996e6  mov     r9d, eax; char *
0x1800996e9  lea     r8, aOnecoreBaseDev_45; "onecore\\base\\devices\\cam\\winrt\\mcp"...
0x1800996f0  mov     edx, 13Bh; void *
0x1800996f5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800996fa  mov     r9d, eax; char *
0x1800996fd  lea     r8, aOnecoreBaseDev_45; "onecore\\base\\devices\\cam\\winrt\\mcp"...
0x180099704  mov     edx, 143h; void *
0x180099709  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009970e  mov     r9d, eax; char *
0x180099711  lea     r8, aOnecoreBaseDev_45; "onecore\\base\\devices\\cam\\winrt\\mcp"...
0x180099718  mov     edx, 150h; void *
0x18009971d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
