# McpConsentManagerStatics::GetConsentsForClient(HSTRING__ *,HSTRING__ *,uint *,Windows::Internal::AI::Agents::Mcp::McpConsentKeyValue * *)

- ea: `0x180098eb0`
- end: `0x1800992e4`
- name: `?GetConsentsForClient@McpConsentManagerStatics@@UEAAJPEAUHSTRING__@@0PEAIPEAPEAUMcpConsentKeyValue@Mcp@Agents@AI@Internal@Windows@@@Z`
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
- `0x180098eb0`
- `0x1800b71cc`
- `0x1800b81b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180099066`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180099066`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800990bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800990e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180099115`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18009914f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800990bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800990e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180099115`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18009914f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180098f51`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180098fca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180098f51`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180098fca`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall McpConsentManagerStatics::GetConsentsForClient(
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
  Windows::Internal::AI::Agents::Mcp::Implementation::InternalMcpConsentKey *v17; // rcx
  struct Windows::Internal::AI::Agents::Mcp::McpConsentKeyValue *v18; // r15
  __int64 v19; // rdi
  UINT32 *v20; // rbx
  UINT32 *v21; // r12
  char *v22; // rsi
  const WCHAR *v23; // rax
  HRESULT String; // eax
  const WCHAR *v25; // rax
  HRESULT v26; // eax
  const WCHAR *v27; // rax
  HRESULT v28; // eax
  const WCHAR *v29; // rax
  HRESULT v30; // eax
  __int64 result; // rax
  int v32[2]; // [rsp+20h] [rbp-C8h] BYREF
  Windows::Internal::AI::Agents::Mcp::Implementation::InternalMcpConsentKey *v33; // [rsp+28h] [rbp-C0h] BYREF
  Windows::Internal::AI::Agents::Mcp::Implementation::InternalMcpConsentKey *v34; // [rsp+30h] [rbp-B8h]
  __int64 v35; // [rsp+38h] [rbp-B0h]
  _BYTE v36[8]; // [rsp+40h] [rbp-A8h] BYREF
  struct Windows::Internal::AI::Agents::Mcp::McpConsentKeyValue **v37; // [rsp+48h] [rbp-A0h]
  _BYTE v38[32]; // [rsp+50h] [rbp-98h] BYREF
  _BYTE v39[32]; // [rsp+70h] [rbp-78h] BYREF
  _BYTE v40[32]; // [rsp+90h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  try
  {
    v37 = a5;
    v32[0] = 0;
    if ( !a3 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x16D,
        (unsigned int)"onecore\\base\\devices\\cam\\winrt\\mcp\\management\\mcpconsentmanagerstatics.cpp",
        (const char *)0x80070057LL,
        v32[0]);
    if ( !a4 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x16E,
        (unsigned int)"onecore\\base\\devices\\cam\\winrt\\mcp\\management\\mcpconsentmanagerstatics.cpp",
        (const char *)0x80004003LL,
        v32[0]);
    if ( !a5 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x16F,
        (unsigned int)"onecore\\base\\devices\\cam\\winrt\\mcp\\management\\mcpconsentmanagerstatics.cpp",
        (const char *)0x80004003LL,
        v32[0]);
    if ( Windows::Internal::CapabilityAccess::WinRT::CallerValidation::AccessCheckForRPCCaller(
           (Windows::Internal::CapabilityAccess::WinRT::CallerValidation *)4,
           (unsigned int)a2) )
    {
      if ( !a2 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x178,
          (unsigned int)"onecore\\base\\devices\\cam\\winrt\\mcp\\management\\mcpconsentmanagerstatics.cpp",
          (const char *)0x80070057LL,
          v32[0]);
      StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
      UserSidStringFromToken = std::wstring::wstring(v40, StringRawBuffer);
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
          (void *)0x184,
          (unsigned int)"onecore\\base\\devices\\cam\\winrt\\mcp\\management\\mcpconsentmanagerstatics.cpp",
          (const char *)0x80070005LL,
          v32[0]);
      }
      v13 = Windows::Internal::CapabilityAccess::Private::GetCallerTokenFromComCall(v36);
      v32[0] = 2;
      UserSidStringFromToken = Windows::Internal::CapabilityAccess::Private::GetUserSidStringFromToken(v39, v13);
      v11 = 6;
    }
    v32[0] = v11;
    v14 = WindowsGetStringRawBuffer(a3, 0);
    std::wstring::wstring(v38, v14);
    Windows::Internal::AI::Agents::Mcp::Implementation::McpConsentStore::GetConsentsForClient(
      &v33,
      v38,
      UserSidStringFromToken);
    v15 = v11 | 8;
    std::wstring::_Tidy_deallocate(v38);
    if ( (v15 & 4) != 0 )
    {
      v15 &= ~4u;
      std::wstring::_Tidy_deallocate(v39);
    }
    if ( (v15 & 2) != 0 )
    {
      v15 &= ~2u;
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v36);
    }
    if ( (v15 & 1) != 0 )
      std::wstring::_Tidy_deallocate(v40);
    v17 = v33;
    if ( v33 != v34 )
    {
      v18 = (struct Windows::Internal::AI::Agents::Mcp::McpConsentKeyValue *)CoTaskMemAlloc(
                                                                               0xA5A5A5A5A5A5A5A8uLL
                                                                             * ((v34 - v33) >> 3));
      *(_QWORD *)v32 = v18;
      if ( !v18 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x19F,
          (unsigned int)"onecore\\base\\devices\\cam\\winrt\\mcp\\management\\mcpconsentmanagerstatics.cpp",
          (const char *)0x8007000ELL,
          0);
      v19 = 0;
      v20 = (UINT32 *)v33;
      v21 = (UINT32 *)v34;
      while ( v20 != v21 )
      {
        v22 = (char *)v18 + 40 * v19;
        *((_DWORD *)v22 + 8) = v20[32];
        v23 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v20);
        String = WindowsCreateString(v23, v20[4], (HSTRING *)v22);
        if ( String < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x1C0,
            (unsigned int)"onecore\\base\\devices\\cam\\winrt\\mcp\\management\\mcpconsentmanagerstatics.cpp",
            (const char *)(unsigned int)String,
            v32[0]);
        v25 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v20 + 8);
        v26 = WindowsCreateString(v25, v20[12], (HSTRING *)v22 + 1);
        if ( v26 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x1C6,
            (unsigned int)"onecore\\base\\devices\\cam\\winrt\\mcp\\management\\mcpconsentmanagerstatics.cpp",
            (const char *)(unsigned int)v26,
            v32[0]);
        if ( *((_QWORD *)v20 + 10) )
        {
          v27 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v20 + 16);
          v28 = WindowsCreateString(v27, v20[20], (HSTRING *)v22 + 2);
          if ( v28 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x1CE,
              (unsigned int)"onecore\\base\\devices\\cam\\winrt\\mcp\\management\\mcpconsentmanagerstatics.cpp",
              (const char *)(unsigned int)v28,
              v32[0]);
        }
        else
        {
          *((_QWORD *)v22 + 2) = 0;
        }
        if ( *((_QWORD *)v20 + 14) )
        {
          v29 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v20 + 24);
          v30 = WindowsCreateString(v29, v20[28], (HSTRING *)v22 + 3);
          if ( v30 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x1DB,
              (unsigned int)"onecore\\base\\devices\\cam\\winrt\\mcp\\management\\mcpconsentmanagerstatics.cpp",
              (const char *)(unsigned int)v30,
              v32[0]);
        }
        else
        {
          *((_QWORD *)v22 + 3) = 0;
        }
        ++v19;
        v20 += 34;
      }
      *(_QWORD *)v32 = 0;
      *v37 = v18;
      *a4 = v19;
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v32);
      v17 = v33;
    }
    if ( v17 )
    {
      std::_Destroy_range<std::allocator<Windows::Internal::CapabilityAccess::Extensions::Storage::APIWrappers::MCP::McpConsent>>(v17);
      std::_Deallocate<16>(v33, 8 * ((v35 - (__int64)v33) >> 3));
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x1F0,
                           (unsigned int)"onecore\\base\\devices\\cam\\winrt\\mcp\\management\\mcpconsentmanagerstatics.cpp",
                           v16);
  }
  return result;
}

```

## disassembly

```asm
0x180098eb0  mov     [rsp+arg_0], rbx
0x180098eb5  mov     [rsp+arg_8], rsi
0x180098eba  push    rdi
0x180098ebb  push    r12
0x180098ebd  push    r13
0x180098ebf  push    r14
0x180098ec1  push    r15
0x180098ec3  sub     rsp, 0C0h
0x180098eca  mov     rax, cs:__security_cookie
0x180098ed1  xor     rax, rsp
0x180098ed4  mov     [rsp+0E8h+var_38], rax
0x180098edc  mov     r13, r9
0x180098edf  mov     rsi, r8
0x180098ee2  mov     rbx, rdx
0x180098ee5  mov     rax, [rsp+0E8h+arg_20]
0x180098eed  mov     [rsp+0E8h+var_A0], rax
0x180098ef2  mov     [rsp+0E8h+var_C8], 0; int
0x180098efa  mov     rcx, [rsp+0E8h]; this
0x180098f02  test    r8, r8
0x180098f05  jz      loc_180099207
0x180098f0b  mov     rcx, [rsp+0E8h]; this
0x180098f13  test    r13, r13
0x180098f16  jz      loc_18009921E
0x180098f1c  mov     rcx, [rsp+0E8h]; this
0x180098f24  test    rax, rax
0x180098f27  jz      loc_180099235
0x180098f2d  mov     ecx, 4; this
0x180098f32  call    ?AccessCheckForRPCCaller@CallerValidation@WinRT@CapabilityAccess@Internal@Windows@@YA_NI@Z; Windows::Internal::CapabilityAccess::WinRT::CallerValidation::AccessCheckForRPCCaller(uint)
0x180098f37  test    al, al
0x180098f39  jz      short loc_180098F71
0x180098f3b  mov     rcx, [rsp+0E8h]; this
0x180098f43  test    rbx, rbx
0x180098f46  jz      loc_18009924C
0x180098f4c  xor     edx, edx; length
0x180098f4e  mov     rcx, rbx; string
0x180098f51  call    cs:__imp_WindowsGetStringRawBuffer
0x180098f57  mov     rdx, rax
0x180098f5a  lea     rcx, [rsp+0E8h+var_58]
0x180098f62  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180098f67  mov     rdi, rax
0x180098f6a  mov     ebx, 1
0x180098f6f  jmp     short loc_180098FC1
0x180098f71  mov     ecx, 8; this
0x180098f76  call    ?AccessCheckForRPCCaller@CallerValidation@WinRT@CapabilityAccess@Internal@Windows@@YA_NI@Z; Windows::Internal::CapabilityAccess::WinRT::CallerValidation::AccessCheckForRPCCaller(uint)
0x180098f7b  test    al, al
0x180098f7d  jnz     short loc_180098F99
0x180098f7f  mov     ecx, 3; this
0x180098f84  call    ?AccessCheckForRPCCaller@CallerValidation@WinRT@CapabilityAccess@Internal@Windows@@YA_NI@Z; Windows::Internal::CapabilityAccess::WinRT::CallerValidation::AccessCheckForRPCCaller(uint)
0x180098f89  mov     rcx, [rsp+0E8h]; this
0x180098f91  test    al, al
0x180098f93  jz      loc_180099263
0x180098f99  lea     rcx, [rsp+0E8h+var_A8]
0x180098f9e  call    ?GetCallerTokenFromComCall@Private@CapabilityAccess@Internal@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ; Windows::Internal::CapabilityAccess::Private::GetCallerTokenFromComCall(void)
0x180098fa3  nop
0x180098fa4  mov     [rsp+0E8h+var_C8], 2
0x180098fac  mov     rdx, rax
0x180098faf  lea     rcx, [rsp+0E8h+var_78]
0x180098fb4  call    ?GetUserSidStringFromToken@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z; Windows::Internal::CapabilityAccess::Private::GetUserSidStringFromToken(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> const &)
0x180098fb9  mov     rdi, rax
0x180098fbc  mov     ebx, 6
0x180098fc1  mov     [rsp+0E8h+var_C8], ebx
0x180098fc5  xor     edx, edx; length
0x180098fc7  mov     rcx, rsi; string
0x180098fca  call    cs:__imp_WindowsGetStringRawBuffer
0x180098fd0  mov     rdx, rax
0x180098fd3  lea     rcx, [rsp+0E8h+var_98]
0x180098fd8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180098fdd  nop
0x180098fde  mov     r8, rdi
0x180098fe1  lea     rdx, [rsp+0E8h+var_98]
0x180098fe6  lea     rcx, [rsp+0E8h+var_C0]
0x180098feb  call    ?GetConsentsForClient@McpConsentStore@Implementation@Mcp@Agents@AI@Internal@Windows@@SA?AV?$vector@UInternalMcpConsentKeyValue@Implementation@Mcp@Agents@AI@Internal@Windows@@V?$allocator@UInternalMcpConsentKeyValue@Implementation@Mcp@Agents@AI@Internal@Windows@@@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@9@0@Z; Windows::Internal::AI::Agents::Mcp::Implementation::McpConsentStore::GetConsentsForClient(std::wstring const &,std::wstring const &)
0x180098ff0  or      ebx, 8
0x180098ff3  lea     rcx, [rsp+0E8h+var_98]
0x180098ff8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180098ffd  nop
0x180098ffe  test    bl, 4
0x180099001  jz      short loc_180099011
0x180099003  and     ebx, 0FFFFFFFBh
0x180099006  lea     rcx, [rsp+0E8h+var_78]
0x18009900b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180099010  nop
0x180099011  test    bl, 2
0x180099014  jz      short loc_180099024
0x180099016  and     ebx, 0FFFFFFFDh
0x180099019  lea     rcx, [rsp+0E8h+var_A8]
0x18009901e  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180099023  nop
0x180099024  test    bl, 1
0x180099027  jz      short loc_180099036
0x180099029  lea     rcx, [rsp+0E8h+var_58]
0x180099031  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180099036  mov     rdx, [rsp+0E8h+var_B8]
0x18009903b  mov     rcx, [rsp+0E8h+var_C0]
0x180099040  mov     r14, 0F0F0F0F0F0F0F0F1h
0x18009904a  cmp     rcx, rdx
0x18009904d  jz      loc_1800991A7
0x180099053  sub     rdx, rcx
0x180099056  sar     rdx, 3
0x18009905a  imul    rdx, r14
0x18009905e  lea     rcx, [rdx+rdx*4]
0x180099062  shl     rcx, 3; cb
0x180099066  call    cs:__imp_CoTaskMemAlloc
0x18009906c  mov     r15, rax
0x18009906f  mov     qword ptr [rsp+0E8h+var_C8], rax; int
0x180099074  mov     rcx, [rsp+0E8h]; this
0x18009907c  test    rax, rax
0x18009907f  jz      loc_18009927B
0x180099085  xor     edi, edi
0x180099087  mov     rbx, [rsp+0E8h+var_C0]
0x18009908c  mov     r12, [rsp+0E8h+var_B8]
0x180099091  cmp     rbx, r12
0x180099094  jz      loc_18009917E
0x18009909a  lea     rax, [rdi+rdi*4]
0x18009909e  lea     rsi, [r15+rax*8]
0x1800990a2  mov     eax, [rbx+80h]
0x1800990a8  mov     [rsi+20h], eax
0x1800990ab  mov     rcx, rbx
0x1800990ae  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800990b3  mov     r8, rsi; string
0x1800990b6  mov     edx, [rbx+10h]; length
0x1800990b9  mov     rcx, rax; sourceString
0x1800990bc  call    cs:__imp_WindowsCreateString
0x1800990c2  mov     rcx, [rsp+0E8h]; this
0x1800990ca  test    eax, eax
0x1800990cc  js      loc_180099292
0x1800990d2  lea     rcx, [rbx+20h]
0x1800990d6  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800990db  lea     r8, [rsi+8]; string
0x1800990df  mov     edx, [rbx+30h]; length
0x1800990e2  mov     rcx, rax; sourceString
0x1800990e5  call    cs:__imp_WindowsCreateString
0x1800990eb  mov     rcx, [rsp+0E8h]; this
0x1800990f3  test    eax, eax
0x1800990f5  js      loc_1800992A6
0x1800990fb  cmp     qword ptr [rbx+50h], 0
0x180099100  jbe     short loc_18009912D
0x180099102  lea     rcx, [rbx+40h]
0x180099106  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18009910b  lea     r8, [rsi+10h]; string
0x18009910f  mov     edx, [rbx+50h]; length
0x180099112  mov     rcx, rax; sourceString
0x180099115  call    cs:__imp_WindowsCreateString
0x18009911b  mov     rcx, [rsp+0E8h]; this
0x180099123  test    eax, eax
0x180099125  js      loc_1800992BA
0x18009912b  jmp     short loc_180099135
0x18009912d  mov     qword ptr [rsi+10h], 0
0x180099135  cmp     qword ptr [rbx+70h], 0
0x18009913a  jbe     short loc_180099167
0x18009913c  lea     rcx, [rbx+60h]
0x180099140  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180099145  lea     r8, [rsi+18h]; string
0x180099149  mov     edx, [rbx+70h]; length
0x18009914c  mov     rcx, rax; sourceString
0x18009914f  call    cs:__imp_WindowsCreateString
0x180099155  mov     rcx, [rsp+0E8h]; this
0x18009915d  test    eax, eax
0x18009915f  js      loc_1800992CE
0x180099165  jmp     short loc_18009916F
0x180099167  mov     qword ptr [rsi+18h], 0
0x18009916f  inc     rdi
0x180099172  add     rbx, 88h
0x180099179  jmp     loc_180099091
0x18009917e  mov     qword ptr [rsp+0E8h+var_C8], 0
0x180099187  mov     rax, [rsp+0E8h+var_A0]
0x18009918c  mov     [rax], r15
0x18009918f  mov     [r13+0], edi
0x180099193  lea     rcx, [rsp+0E8h+var_C8]
0x180099198  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18009919d  mov     rdx, [rsp+0E8h+var_B8]
0x1800991a2  mov     rcx, [rsp+0E8h+var_C0]; this
0x1800991a7  test    rcx, rcx
0x1800991aa  jz      short loc_1800991D2
0x1800991ac  call    ??$_Destroy_range@V?$allocator@UMcpConsent@MCP@APIWrappers@Storage@Extensions@CapabilityAccess@Internal@Windows@@@std@@@std@@YAXPEAUMcpConsent@MCP@APIWrappers@Storage@Extensions@CapabilityAccess@Internal@Windows@@QEAU12345678@AEAV?$allocator@UMcpConsent@MCP@APIWrappers@Storage@Extensions@CapabilityAccess@Internal@Windows@@@0@@Z; std::_Destroy_range<std::allocator<Windows::Internal::CapabilityAccess::Extensions::Storage::APIWrappers::MCP::McpConsent>>(Windows::Internal::CapabilityAccess::Extensions::Storage::APIWrappers::MCP::McpConsent *,Windows::Internal::CapabilityAccess::Extensions::Storage::APIWrappers::MCP::McpConsent * const,std::allocator<Windows::Internal::CapabilityAccess::Extensions::Storage::APIWrappers::MCP::McpConsent> &)
0x1800991b1  mov     rcx, [rsp+0E8h+var_C0]
0x1800991b6  mov     rax, [rsp+0E8h+var_B0]
0x1800991bb  sub     rax, rcx
0x1800991be  sar     rax, 3
0x1800991c2  imul    rax, r14
0x1800991c6  imul    rdx, rax, 88h
0x1800991cd  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800991d2  xor     eax, eax
0x1800991d4  jmp     short loc_1800991DA
0x1800991d6  mov     eax, [rsp+0E8h+var_C8]
0x1800991da  mov     rcx, [rsp+0E8h+var_38]
0x1800991e2  xor     rcx, rsp; StackCookie
0x1800991e5  call    __security_check_cookie
0x1800991ea  lea     r11, [rsp+0E8h+var_28]
0x1800991f2  mov     rbx, [r11+30h]
0x1800991f6  mov     rsi, [r11+38h]
0x1800991fa  mov     rsp, r11
0x1800991fd  pop     r15
0x1800991ff  pop     r14
0x180099201  pop     r13
0x180099203  pop     r12
0x180099205  pop     rdi
0x180099206  retn
0x180099207  mov     r9d, 80070057h; char *
0x18009920d  lea     r8, aOnecoreBaseDev_45; "onecore\\base\\devices\\cam\\winrt\\mcp"...
0x180099214  mov     edx, 16Dh; void *
0x180099219  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009921e  mov     r9d, 80004003h; char *
0x180099224  lea     r8, aOnecoreBaseDev_45; "onecore\\base\\devices\\cam\\winrt\\mcp"...
0x18009922b  mov     edx, 16Eh; void *
0x180099230  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180099235  mov     r9d, 80004003h; char *
0x18009923b  lea     r8, aOnecoreBaseDev_45; "onecore\\base\\devices\\cam\\winrt\\mcp"...
0x180099242  mov     edx, 16Fh; void *
0x180099247  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009924c  mov     r9d, 80070057h; char *
0x180099252  lea     r8, aOnecoreBaseDev_45; "onecore\\base\\devices\\cam\\winrt\\mcp"...
0x180099259  mov     edx, 178h; void *
0x18009925e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180099263  mov     r9d, 80070005h; char *
0x180099269  lea     r8, aOnecoreBaseDev_45; "onecore\\base\\devices\\cam\\winrt\\mcp"...
0x180099270  mov     edx, 184h; void *
0x180099275  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009927b  mov     r9d, 8007000Eh; char *
0x180099281  lea     r8, aOnecoreBaseDev_45; "onecore\\base\\devices\\cam\\winrt\\mcp"...
0x180099288  mov     edx, 19Fh; void *
0x18009928d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180099292  mov     r9d, eax; char *
0x180099295  lea     r8, aOnecoreBaseDev_45; "onecore\\base\\devices\\cam\\winrt\\mcp"...
0x18009929c  mov     edx, 1C0h; void *
0x1800992a1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800992a6  mov     r9d, eax; char *
0x1800992a9  lea     r8, aOnecoreBaseDev_45; "onecore\\base\\devices\\cam\\winrt\\mcp"...
0x1800992b0  mov     edx, 1C6h; void *
0x1800992b5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800992ba  mov     r9d, eax; char *
0x1800992bd  lea     r8, aOnecoreBaseDev_45; "onecore\\base\\devices\\cam\\winrt\\mcp"...
0x1800992c4  mov     edx, 1CEh; void *
0x1800992c9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800992ce  mov     r9d, eax; char *
0x1800992d1  lea     r8, aOnecoreBaseDev_45; "onecore\\base\\devices\\cam\\winrt\\mcp"...
0x1800992d8  mov     edx, 1DBh; void *
0x1800992dd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
