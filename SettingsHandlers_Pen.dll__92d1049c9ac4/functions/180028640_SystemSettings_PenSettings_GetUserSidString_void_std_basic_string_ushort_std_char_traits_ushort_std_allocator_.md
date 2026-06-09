# SystemSettings::PenSettings::GetUserSidString(void *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180028640`
- end: `0x1800287b8`
- name: `?GetUserSidString@PenSettings@SystemSettings@@YAJPEAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `376`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180022654`

## callees

- `0x1800035bc`
- `0x1800041b0`
- `0x18000a29c`
- `0x18000a2bc`
- `0x180010fa0`
- `0x18001acf8`
- `0x18001cff8`
- `0x1800206dc`
- `0x180028640`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800286c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800286c0`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002866d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002866d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180028694`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002870f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180028694`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002870f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180028747`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180028747`

## string_xrefs

- `0x1800286aa`: `shellcommon\shell\settingshandlers\pen\lib\penbuttoncustomization.cpp`
- `0x1800286d0`: `shellcommon\shell\settingshandlers\pen\lib\penbuttoncustomization.cpp`
- `0x18002871d`: `shellcommon\shell\settingshandlers\pen\lib\penbuttoncustomization.cpp`
- `0x180028755`: `shellcommon\shell\settingshandlers\pen\lib\penbuttoncustomization.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SystemSettings::PenSettings::GetUserSidString(void *a1, __int64 a2)
{
  const char *v3; // r9
  __int64 v4; // rdx
  unsigned int LastError; // ebx
  PSID *v6; // rdi
  const char *v7; // r9
  const char *v8; // r9
  __int64 v9; // rcx
  int ReturnLength; // [rsp+20h] [rbp-20h]
  void *TokenHandle[2]; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+8h]
  DWORD TokenInformationLength; // [rsp+60h] [rbp+20h] BYREF
  LPWSTR StringSid; // [rsp+68h] [rbp+28h] BYREF

  TokenInformationLength = 0;
  TokenHandle[0] = 0;
  if ( !OpenProcessToken(a1, 8u, TokenHandle) )
  {
    v4 = 105;
LABEL_7:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v4,
                  (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penbuttoncustomization.cpp",
                  v3);
    goto LABEL_14;
  }
  if ( GetTokenInformation(TokenHandle[0], TokenUser, 0, TokenInformationLength, &TokenInformationLength) )
  {
    LastError = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6A,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penbuttoncustomization.cpp",
      (const char *)0x8000FFFFLL,
      ReturnLength);
  }
  else
  {
    if ( GetLastError() != 122 )
    {
      v4 = 107;
      goto LABEL_7;
    }
    v6 = (PSID *)operator new[](TokenInformationLength);
    TokenHandle[1] = v6;
    if ( GetTokenInformation(TokenHandle[0], TokenUser, v6, TokenInformationLength, &TokenInformationLength) )
    {
      StringSid = 0;
      if ( ConvertSidToStringSidW(*v6, &StringSid) )
      {
        std::_WChar_traits<unsigned short>::length(StringSid);
        std::wstring::_Assign<unsigned short>(a2, v9);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
        operator delete(v6);
        LastError = 0;
        goto LABEL_14;
      }
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x73,
                    (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penbuttoncustomization.cpp",
                    v8);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x71,
                    (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penbuttoncustomization.cpp",
                    v7);
    }
    operator delete(v6);
  }
LABEL_14:
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(TokenHandle);
  return LastError;
}

```

## disassembly

```asm
0x180028640  mov     [rsp-8+arg_0], rbx
0x180028645  mov     [rsp-8+arg_8], rdi
0x18002864a  push    rbp
0x18002864b  mov     rbp, rsp
0x18002864e  sub     rsp, 40h
0x180028652  mov     rbx, rdx
0x180028655  mov     [rbp+TokenInformationLength], 0
0x18002865c  mov     [rbp+TokenHandle], 0
0x180028664  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180028668  mov     edx, 8; DesiredAccess
0x18002866d  call    cs:__imp_OpenProcessToken
0x180028673  test    eax, eax
0x180028675  jnz     short loc_18002867C
0x180028677  lea     edx, [rax+69h]
0x18002867a  jmp     short loc_1800286D0
0x18002867c  lea     rax, [rbp+TokenInformationLength]
0x180028680  mov     qword ptr [rsp+40h+ReturnLength], rax; int
0x180028685  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180028689  xor     r8d, r8d; TokenInformation
0x18002868c  lea     edx, [r8+1]; TokenInformationClass
0x180028690  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180028694  call    cs:__imp_GetTokenInformation
0x18002869a  test    eax, eax
0x18002869c  jz      short loc_1800286C0
0x18002869e  mov     rcx, [rbp+8]; this
0x1800286a2  mov     ebx, 8000FFFFh
0x1800286a7  mov     r9d, ebx; char *
0x1800286aa  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\settingshandlers\\p"...
0x1800286b1  mov     edx, 6Ah ; 'j'; void *
0x1800286b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800286bb  jmp     loc_18002879D
0x1800286c0  call    cs:__imp_GetLastError
0x1800286c6  cmp     eax, 7Ah ; 'z'
0x1800286c9  jz      short loc_1800286E7
0x1800286cb  mov     edx, 6Bh ; 'k'; void *
0x1800286d0  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\settingshandlers\\p"...
0x1800286d7  mov     rcx, [rbp+8]; this
0x1800286db  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800286e0  mov     ebx, eax
0x1800286e2  jmp     loc_18002879D
0x1800286e7  mov     ecx, [rbp+TokenInformationLength]; unsigned __int64
0x1800286ea  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800286ef  mov     rdi, rax
0x1800286f2  mov     [rbp+var_8], rax
0x1800286f6  lea     rax, [rbp+TokenInformationLength]
0x1800286fa  mov     qword ptr [rsp+40h+ReturnLength], rax; ReturnLength
0x1800286ff  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180028703  mov     r8, rdi; TokenInformation
0x180028706  mov     edx, 1; TokenInformationClass
0x18002870b  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18002870f  call    cs:__imp_GetTokenInformation
0x180028715  test    eax, eax
0x180028717  jnz     short loc_180028738
0x180028719  mov     rcx, [rbp+8]; this
0x18002871d  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\settingshandlers\\p"...
0x180028724  lea     edx, [rax+71h]; void *
0x180028727  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002872c  mov     ebx, eax
0x18002872e  mov     rcx, rdi; Block
0x180028731  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180028736  jmp     short loc_18002879D
0x180028738  mov     [rbp+StringSid], 0
0x180028740  lea     rdx, [rbp+StringSid]; StringSid
0x180028744  mov     rcx, [rdi]; Sid
0x180028747  call    cs:__imp_ConvertSidToStringSidW
0x18002874d  test    eax, eax
0x18002874f  jnz     short loc_180028771
0x180028751  mov     rcx, [rbp+8]; this
0x180028755  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\settingshandlers\\p"...
0x18002875c  lea     edx, [rax+73h]; void *
0x18002875f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180028764  mov     ebx, eax
0x180028766  lea     rcx, [rbp+StringSid]
0x18002876a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002876f  jmp     short loc_18002872E
0x180028771  mov     rcx, [rbp+StringSid]
0x180028775  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18002877a  mov     r8, rax
0x18002877d  mov     rdx, rcx
0x180028780  mov     rcx, rbx
0x180028783  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180028788  nop
0x180028789  lea     rcx, [rbp+StringSid]
0x18002878d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180028792  nop
0x180028793  mov     rcx, rdi; Block
0x180028796  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002879b  xor     ebx, ebx
0x18002879d  lea     rcx, [rbp+TokenHandle]
0x1800287a1  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800287a6  mov     eax, ebx
0x1800287a8  mov     rbx, [rsp+40h+arg_0]
0x1800287ad  mov     rdi, [rsp+40h+arg_8]
0x1800287b2  add     rsp, 40h
0x1800287b6  pop     rbp
0x1800287b7  retn
```
