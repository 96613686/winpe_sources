# Windows::Internal::AssignedAccess::UserSessionHelper::LookupUserSession(ushort const *,bool &,ulong &,unsigned __int64 &)

- ea: `0x18004f4d4`
- end: `0x18004f793`
- name: `?LookupUserSession@UserSessionHelper@AssignedAccess@Internal@Windows@@SAJPEBGAEA_NAEAKAEA_K@Z`
- size: `703`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool *, unsigned int *, unsigned __int64 *)`
- caller_count: `4`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18001b090`
- `0x18005008c`
- `0x180084b7c`
- `0x180084e6c`

## callees

- `0x180006640`
- `0x180008e90`
- `0x180009a74`
- `0x180009d58`
- `0x18000b694`
- `0x18000b6b4`
- `0x18000f62c`
- `0x180010c98`
- `0x18002001c`
- `0x18004ecc0`
- `0x18004f4d4`
- `0x18004f79c`
- `0x1800502d0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18004f69e`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18004f6de`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18004f69e`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18004f6de`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x18004f605`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x18004f658`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x18004f605`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x18004f658`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsW` at `0x18004f583`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsW` at `0x18004f583`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x18004f628`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x18004f628`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Internal::AssignedAccess::UserSessionHelper::LookupUserSession(
        const unsigned __int16 *a1,
        bool *a2,
        unsigned int *a3,
        unsigned __int64 *a4)
{
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // rdx
  __int64 v11; // r8
  int AccountInfoFromSid; // eax
  unsigned int LastError; // ebx
  const char *v14; // r9
  DWORD i; // ebx
  PVOID v17; // rdi
  const WCHAR *v18; // rax
  LPCWCH v19; // rdx
  const WCHAR *v20; // rax
  LPCWCH v21; // rdx
  int v22; // eax
  int pCount; // [rsp+20h] [rbp-89h]
  PVOID pMemory; // [rsp+50h] [rbp-59h] BYREF
  PWTS_SESSION_INFOW ppSessionInfo; // [rsp+58h] [rbp-51h] BYREF
  DWORD v26; // [rsp+60h] [rbp-49h] BYREF
  LPWSTR ppBuffer; // [rsp+68h] [rbp-41h] BYREF
  DWORD pBytesReturned; // [rsp+70h] [rbp-39h] BYREF
  DWORD v29; // [rsp+74h] [rbp-35h] BYREF
  _BYTE v30[8]; // [rsp+78h] [rbp-31h] BYREF
  _BYTE v31[32]; // [rsp+80h] [rbp-29h] BYREF
  _BYTE v32[32]; // [rsp+A0h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  *a2 = 0;
  *a3 = -1;
  *a4 = 0;
  if ( (unsigned __int8)IsWTSEnumerateSessionsWPresent() )
  {
    std::wstring::wstring(v32, v8, v9);
    std::wstring::wstring(v31, v10, v11);
    AccountInfoFromSid = Windows::Internal::AssignedAccess::UserInfoHelper::GetAccountInfoFromSid(a1, v32, v31);
    LastError = AccountInfoFromSid;
    if ( AccountInfoFromSid < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x24,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\usersessionhelper.cpp",
        (const char *)(unsigned int)AccountInfoFromSid,
        pCount);
LABEL_6:
      std::wstring::_Tidy_deallocate(v31);
      std::wstring::_Tidy_deallocate(v32);
      return LastError;
    }
    v26 = 0;
    ppSessionInfo = 0;
    if ( !WTSEnumerateSessionsW(0, 0, 1u, &ppSessionInfo, &v26) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x2A,
                    (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\usersessionhelper.cpp",
                    v14);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppSessionInfo);
      goto LABEL_6;
    }
    for ( i = 0; i < v26; ++i )
    {
      pBytesReturned = 0;
      pMemory = 0;
      v29 = 0;
      ppBuffer = 0;
      if ( WTSQuerySessionInformationW(0, ppSessionInfo[i].SessionId, WTSUserName, &ppBuffer, &pBytesReturned) )
      {
        v17 = pMemory;
        if ( pMemory )
        {
          wil::last_error_context::last_error_context((wil::last_error_context *)v30);
          WTSFreeMemory(v17);
          wil::last_error_context::~last_error_context((wil::last_error_context *)v30);
        }
        pMemory = 0;
        if ( WTSQuerySessionInformationW(0, ppSessionInfo[i].SessionId, WTSDomainName, (LPWSTR *)&pMemory, &v29) )
        {
          v18 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v32);
          if ( CompareStringEx(&LocaleName, 1u, v18, -1, v19, -1, 0, 0, 0) == 2 )
          {
            v20 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v31);
            if ( CompareStringEx(&LocaleName, 1u, v20, -1, v21, -1, 0, 0, 0) == 2 )
            {
              *a2 = 1;
              *a3 = ppSessionInfo[i].SessionId;
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pMemory);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppBuffer);
              break;
            }
          }
        }
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pMemory);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppBuffer);
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppSessionInfo);
    std::wstring::_Tidy_deallocate(v31);
    std::wstring::_Tidy_deallocate(v32);
  }
  else
  {
    v22 = Windows::Internal::AssignedAccess::UserSessionHelper::LookupUserSessionForSharedSessionSku(a1, a2, a3, a4);
    LastError = v22;
    if ( v22 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6B,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\usersessionhelper.cpp",
        (const char *)(unsigned int)v22,
        pCount);
      return LastError;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18004f4d4  push    rbp
0x18004f4d6  push    rbx
0x18004f4d7  push    rsi
0x18004f4d8  push    rdi
0x18004f4d9  push    r12
0x18004f4db  push    r14
0x18004f4dd  push    r15
0x18004f4df  lea     rbp, [rsp-27h]
0x18004f4e4  sub     rsp, 0D0h
0x18004f4eb  mov     rax, cs:__security_cookie
0x18004f4f2  xor     rax, rsp
0x18004f4f5  mov     [rbp+57h+var_40], rax
0x18004f4f9  mov     rdi, r9
0x18004f4fc  mov     r14, r8
0x18004f4ff  mov     rsi, rdx
0x18004f502  mov     rbx, rcx
0x18004f505  xor     r12d, r12d
0x18004f508  mov     [rdx], r12b
0x18004f50b  mov     dword ptr [r8], 0FFFFFFFFh
0x18004f512  mov     [r9], r12
0x18004f515  call    IsWTSEnumerateSessionsWPresent
0x18004f51a  test    al, al
0x18004f51c  jz      loc_18004F75F
0x18004f522  lea     rcx, [rbp+57h+var_60]
0x18004f526  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18004f52b  nop
0x18004f52c  lea     rcx, [rbp+57h+var_80]
0x18004f530  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18004f535  nop
0x18004f536  lea     r8, [rbp+57h+var_80]
0x18004f53a  lea     rdx, [rbp+57h+var_60]
0x18004f53e  mov     rcx, rbx
0x18004f541  call    ?GetAccountInfoFromSid@UserInfoHelper@AssignedAccess@Internal@Windows@@SAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1@Z; Windows::Internal::AssignedAccess::UserInfoHelper::GetAccountInfoFromSid(ushort const *,std::wstring &,std::wstring &)
0x18004f546  mov     ebx, eax
0x18004f548  test    eax, eax
0x18004f54a  jns     short loc_18004F566
0x18004f54c  mov     rcx, [rbp+5Fh]; this
0x18004f550  mov     r9d, eax; char *
0x18004f553  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18004f55a  lea     edx, [r12+24h]; void *
0x18004f55f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004f564  jmp     short loc_18004F5AC
0x18004f566  mov     [rbp+57h+var_A0], r12d
0x18004f56a  mov     [rbp+57h+ppSessionInfo], r12
0x18004f56e  lea     rax, [rbp+57h+var_A0]
0x18004f572  mov     [rsp+100h+pCount], rax; pCount
0x18004f577  lea     r9, [rbp+57h+ppSessionInfo]; ppSessionInfo
0x18004f57b  xor     edx, edx; Reserved
0x18004f57d  xor     ecx, ecx; hServer
0x18004f57f  lea     r8d, [rdx+1]; Version
0x18004f583  call    cs:__imp_WTSEnumerateSessionsW
0x18004f589  test    eax, eax
0x18004f58b  jnz     short loc_18004F5C6
0x18004f58d  mov     rcx, [rbp+5Fh]; this
0x18004f591  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18004f598  lea     edx, [rax+2Ah]; void *
0x18004f59b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004f5a0  mov     ebx, eax
0x18004f5a2  lea     rcx, [rbp+57h+ppSessionInfo]
0x18004f5a6  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?WTSFreeMemory@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18004f5ab  nop
0x18004f5ac  lea     rcx, [rbp+57h+var_80]
0x18004f5b0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004f5b5  nop
0x18004f5b6  lea     rcx, [rbp+57h+var_60]
0x18004f5ba  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004f5bf  mov     eax, ebx
0x18004f5c1  jmp     loc_18004F741
0x18004f5c6  mov     ebx, r12d
0x18004f5c9  cmp     ebx, [rbp+57h+var_A0]
0x18004f5cc  jnb     loc_18004F722
0x18004f5d2  mov     [rbp+57h+pBytesReturned], r12d
0x18004f5d6  mov     [rbp+57h+pMemory], r12
0x18004f5da  mov     [rbp+57h+var_8C], r12d
0x18004f5de  mov     [rbp+57h+ppBuffer], r12
0x18004f5e2  mov     eax, ebx
0x18004f5e4  lea     r15, [rax+rax*2]
0x18004f5e8  lea     rax, [rbp+57h+pBytesReturned]
0x18004f5ec  mov     [rsp+100h+pCount], rax; pBytesReturned
0x18004f5f1  lea     r9, [rbp+57h+ppBuffer]; ppBuffer
0x18004f5f5  mov     r8d, 5; WTSInfoClass
0x18004f5fb  mov     rdx, [rbp+57h+ppSessionInfo]
0x18004f5ff  mov     edx, [rdx+r15*8]; SessionId
0x18004f603  xor     ecx, ecx; hServer
0x18004f605  call    cs:__imp_WTSQuerySessionInformationW
0x18004f60b  test    eax, eax
0x18004f60d  jz      loc_18004F6E9
0x18004f613  mov     rdi, [rbp+57h+pMemory]
0x18004f617  test    rdi, rdi
0x18004f61a  jz      short loc_18004F637
0x18004f61c  lea     rcx, [rbp+57h+var_88]; this
0x18004f620  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18004f625  mov     rcx, rdi; pMemory
0x18004f628  call    cs:__imp_WTSFreeMemory
0x18004f62e  lea     rcx, [rbp+57h+var_88]; this
0x18004f632  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18004f637  mov     [rbp+57h+pMemory], r12
0x18004f63b  lea     rax, [rbp+57h+var_8C]
0x18004f63f  mov     [rsp+100h+pCount], rax; pBytesReturned
0x18004f644  lea     r9, [rbp+57h+pMemory]; ppBuffer
0x18004f648  mov     r8d, 7; WTSInfoClass
0x18004f64e  mov     rdx, [rbp+57h+ppSessionInfo]
0x18004f652  mov     edx, [rdx+r15*8]; SessionId
0x18004f656  xor     ecx, ecx; hServer
0x18004f658  call    cs:__imp_WTSQuerySessionInformationW
0x18004f65e  test    eax, eax
0x18004f660  jz      loc_18004F6E9
0x18004f666  mov     rdx, [rbp+57h+ppBuffer]
0x18004f66a  lea     rcx, [rbp+57h+var_60]
0x18004f66e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004f673  mov     r8, rax; lpString1
0x18004f676  mov     [rsp+100h+lParam], r12; lParam
0x18004f67b  mov     [rsp+100h+lpReserved], r12; lpReserved
0x18004f680  mov     [rsp+100h+lpVersionInformation], r12; lpVersionInformation
0x18004f685  or      edi, 0FFFFFFFFh
0x18004f688  mov     [rsp+100h+cchCount2], edi; cchCount2
0x18004f68c  mov     [rsp+100h+pCount], rdx; lpString2
0x18004f691  mov     r9d, edi; cchCount1
0x18004f694  lea     edx, [rdi+2]; dwCmpFlags
0x18004f697  lea     rcx, LocaleName; lpLocaleName
0x18004f69e  call    cs:__imp_CompareStringEx
0x18004f6a4  cmp     eax, 2
0x18004f6a7  jnz     short loc_18004F6E9
0x18004f6a9  mov     rdx, [rbp+57h+pMemory]
0x18004f6ad  lea     rcx, [rbp+57h+var_80]
0x18004f6b1  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004f6b6  mov     r8, rax; lpString1
0x18004f6b9  mov     [rsp+100h+lParam], r12; lParam
0x18004f6be  mov     [rsp+100h+lpReserved], r12; lpReserved
0x18004f6c3  mov     [rsp+100h+lpVersionInformation], r12; lpVersionInformation
0x18004f6c8  mov     [rsp+100h+cchCount2], edi; cchCount2
0x18004f6cc  mov     [rsp+100h+pCount], rdx; lpString2
0x18004f6d1  mov     r9d, edi; cchCount1
0x18004f6d4  lea     edx, [rdi+2]; dwCmpFlags
0x18004f6d7  lea     rcx, LocaleName; lpLocaleName
0x18004f6de  call    cs:__imp_CompareStringEx
0x18004f6e4  cmp     eax, 2
0x18004f6e7  jz      short loc_18004F702
0x18004f6e9  lea     rcx, [rbp+57h+pMemory]
0x18004f6ed  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?WTSFreeMemory@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18004f6f2  lea     rcx, [rbp+57h+ppBuffer]
0x18004f6f6  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?WTSFreeMemory@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18004f6fb  inc     ebx
0x18004f6fd  jmp     loc_18004F5C9
0x18004f702  mov     byte ptr [rsi], 1
0x18004f705  mov     rax, [rbp+57h+ppSessionInfo]
0x18004f709  mov     ecx, [rax+r15*8]
0x18004f70d  mov     [r14], ecx
0x18004f710  lea     rcx, [rbp+57h+pMemory]
0x18004f714  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?WTSFreeMemory@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18004f719  lea     rcx, [rbp+57h+ppBuffer]
0x18004f71d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?WTSFreeMemory@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18004f722  lea     rcx, [rbp+57h+ppSessionInfo]
0x18004f726  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?WTSFreeMemory@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&WTSFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18004f72b  nop
0x18004f72c  lea     rcx, [rbp+57h+var_80]
0x18004f730  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004f735  nop
0x18004f736  lea     rcx, [rbp+57h+var_60]
0x18004f73a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004f73f  xor     eax, eax
0x18004f741  mov     rcx, [rbp+57h+var_40]
0x18004f745  xor     rcx, rsp; StackCookie
0x18004f748  call    __security_check_cookie
0x18004f74d  add     rsp, 0D0h
0x18004f754  pop     r15
0x18004f756  pop     r14
0x18004f758  pop     r12
0x18004f75a  pop     rdi
0x18004f75b  pop     rsi
0x18004f75c  pop     rbx
0x18004f75d  pop     rbp
0x18004f75e  retn
0x18004f75f  mov     r9, rdi; unsigned __int64 *
0x18004f762  mov     r8, r14; unsigned int *
0x18004f765  mov     rdx, rsi; bool *
0x18004f768  mov     rcx, rbx; lpString2
0x18004f76b  call    ?LookupUserSessionForSharedSessionSku@UserSessionHelper@AssignedAccess@Internal@Windows@@CAJPEBGAEA_NAEAKAEA_K@Z; Windows::Internal::AssignedAccess::UserSessionHelper::LookupUserSessionForSharedSessionSku(ushort const *,bool &,ulong &,unsigned __int64 &)
0x18004f770  mov     ebx, eax
0x18004f772  test    eax, eax
0x18004f774  jns     short loc_18004F73F
0x18004f776  mov     rcx, [rbp+5Fh]; this
0x18004f77a  mov     r9d, eax; char *
0x18004f77d  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18004f784  mov     edx, 6Bh ; 'k'; void *
0x18004f789  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004f78e  jmp     loc_18004F5BF
```
