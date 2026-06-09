# BasicUiaUtils::CreateSecurityDescriptorForProcess(void *,void * *)

- ea: `0x180029720`
- end: `0x180029915`
- name: `?CreateSecurityDescriptorForProcess@BasicUiaUtils@@SAJPEAXPEAPEAX@Z`
- size: `501`
- prototype: `signed int __fastcall(HANDLE TokenHandle, void **)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800294d0`

## callees

- `0x180006edc`
- `0x1800245f0`
- `0x180024794`
- `0x180029720`
- `0x180043680`
- `0x180043a50`
- `0x180049dbc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029778`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029810`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002988d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800298eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029778`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029810`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002988d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800298eb`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002976a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800297e7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002976a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800297e7`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180029806`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180029806`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180029883`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180029883`

## string_xrefs

- `0x1800297a6`: `onecore\windows\accessibletech\common\basicuiautils.cpp`
- `0x180029853`: `onecore\windows\accessibletech\common\basicuiautils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
signed int __fastcall BasicUiaUtils::CreateSecurityDescriptorForProcess(HANDLE TokenHandle, void **a2)
{
  signed int result; // eax
  void **v5; // rdi
  unsigned int v6; // ebx
  unsigned __int64 v7; // rdx
  void **v8; // rcx
  void *v9; // rcx
  signed int v10; // eax
  int v11; // eax
  signed int v12; // eax
  unsigned __int64 v13; // rdx
  signed int LastError; // eax
  int ReturnLength; // [rsp+20h] [rbp-E0h]
  int ReturnLengtha; // [rsp+20h] [rbp-E0h]
  DWORD TokenInformationLength; // [rsp+30h] [rbp-D0h] BYREF
  LPWSTR StringSid; // [rsp+38h] [rbp-C8h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR StringSecurityDescriptor[256]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  TokenInformationLength = 0;
  if ( GetTokenInformation(TokenHandle, TokenIntegrityLevel, 0, 0, &TokenInformationLength) )
    return 0;
  result = GetLastError();
  if ( result == 122 )
  {
    v5 = (void **)operator new[](TokenInformationLength, (const struct std::nothrow_t *)std::nothrow);
    if ( !v5 )
    {
      v6 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x10B,
        (unsigned int)"onecore\\windows\\accessibletech\\common\\basicuiautils.cpp",
        (const char *)0x8007000ELL,
        ReturnLength);
      v8 = 0;
LABEL_5:
      operator delete(v8, v7);
      return v6;
    }
    if ( !GetTokenInformation(TokenHandle, TokenIntegrityLevel, v5, TokenInformationLength, &TokenInformationLength) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v6 = LastError;
      goto LABEL_23;
    }
    v9 = *v5;
    StringSid = 0;
    if ( !ConvertSidToStringSidW(v9, &StringSid) )
    {
      v10 = GetLastError();
      v6 = v10;
      if ( v10 > 0 )
        v6 = (unsigned __int16)v10 | 0x80070000;
      goto LABEL_16;
    }
    v11 = StringCchPrintfW(StringSecurityDescriptor, 0x100u, L"S:(ML;;NW;;;%ws)D:(A;;FRFWGA;;;WD)", StringSid);
    v6 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x120,
        (unsigned int)"onecore\\windows\\accessibletech\\common\\basicuiautils.cpp",
        (const char *)(unsigned int)v11,
        ReturnLengtha);
LABEL_16:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
LABEL_23:
      v8 = v5;
      goto LABEL_5;
    }
    SecurityDescriptor = 0;
    if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(StringSecurityDescriptor, 1u, &SecurityDescriptor, 0) )
    {
      v12 = GetLastError();
      if ( v12 > 0 )
        v12 = (unsigned __int16)v12 | 0x80070000;
      v6 = v12;
      goto LABEL_16;
    }
    *a2 = SecurityDescriptor;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
    operator delete(v5, v13);
    return 0;
  }
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180029720  mov     [rsp-8+arg_10], rbx
0x180029725  push    rbp
0x180029726  push    rsi
0x180029727  push    rdi
0x180029728  lea     rbp, [rsp-160h]
0x180029730  sub     rsp, 260h
0x180029737  mov     rax, cs:__security_cookie
0x18002973e  xor     rax, rsp
0x180029741  mov     [rbp+170h+var_20], rax
0x180029748  xor     r9d, r9d; TokenInformationLength
0x18002974b  mov     [rsp+270h+TokenInformationLength], 0
0x180029753  mov     rsi, rdx
0x180029756  lea     rax, [rsp+270h+TokenInformationLength]
0x18002975b  xor     r8d, r8d; TokenInformation
0x18002975e  mov     qword ptr [rsp+270h+ReturnLength], rax; int
0x180029763  mov     rbx, rcx
0x180029766  lea     edx, [r9+19h]; TokenInformationClass
0x18002976a  call    cs:__imp_GetTokenInformation
0x180029770  test    eax, eax
0x180029772  jnz     loc_1800298C7
0x180029778  call    cs:__imp_GetLastError
0x18002977e  cmp     eax, 7Ah ; 'z'
0x180029781  jnz     loc_180029907
0x180029787  mov     ecx, [rsp+270h+TokenInformationLength]; unsigned __int64
0x18002978b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180029792  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180029797  mov     rdi, rax
0x18002979a  test    rax, rax
0x18002979d  jnz     short loc_1800297CD
0x18002979f  mov     rcx, [rbp+178h]; this
0x1800297a6  lea     r8, aOnecoreWindows_6; "onecore\\windows\\accessibletech\\commo"...
0x1800297ad  mov     ebx, 8007000Eh
0x1800297b2  mov     edx, 10Bh; void *
0x1800297b7  mov     r9d, ebx; char *
0x1800297ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800297bf  xor     ecx, ecx; void *
0x1800297c1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800297c6  mov     eax, ebx
0x1800297c8  jmp     loc_1800298C9
0x1800297cd  mov     r9d, [rsp+270h+TokenInformationLength]; TokenInformationLength
0x1800297d2  lea     rax, [rsp+270h+TokenInformationLength]
0x1800297d7  mov     r8, rdi; TokenInformation
0x1800297da  mov     qword ptr [rsp+270h+ReturnLength], rax; int
0x1800297df  mov     edx, 19h; TokenInformationClass
0x1800297e4  mov     rcx, rbx; TokenHandle
0x1800297e7  call    cs:__imp_GetTokenInformation
0x1800297ed  test    eax, eax
0x1800297ef  jz      loc_1800298EB
0x1800297f5  mov     rcx, [rdi]; Sid
0x1800297f8  lea     rdx, [rsp+270h+StringSid]; StringSid
0x1800297fd  mov     [rsp+270h+StringSid], 0
0x180029806  call    cs:__imp_ConvertSidToStringSidW
0x18002980c  test    eax, eax
0x18002980e  jnz     short loc_18002982B
0x180029810  call    cs:__imp_GetLastError
0x180029816  mov     ebx, eax
0x180029818  test    eax, eax
0x18002981a  jle     loc_1800298A1
0x180029820  movzx   ebx, ax
0x180029823  or      ebx, 80070000h
0x180029829  jmp     short loc_1800298A1
0x18002982b  mov     r9, [rsp+270h+StringSid]
0x180029830  lea     r8, aSMlNwWsDAFrfwg; "S:(ML;;NW;;;%ws)D:(A;;FRFWGA;;;WD)"
0x180029837  mov     edx, 100h; unsigned __int64
0x18002983c  lea     rcx, [rsp+270h+StringSecurityDescriptor]; unsigned __int16 *
0x180029841  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180029846  mov     ebx, eax
0x180029848  test    eax, eax
0x18002984a  jns     short loc_180029869
0x18002984c  mov     rcx, [rbp+178h]; this
0x180029853  lea     r8, aOnecoreWindows_6; "onecore\\windows\\accessibletech\\commo"...
0x18002985a  mov     r9d, eax; char *
0x18002985d  mov     edx, 120h; void *
0x180029862  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029867  jmp     short loc_1800298A1
0x180029869  xor     r9d, r9d; SecurityDescriptorSize
0x18002986c  mov     [rsp+270h+SecurityDescriptor], 0
0x180029875  lea     r8, [rsp+270h+SecurityDescriptor]; SecurityDescriptor
0x18002987a  lea     rcx, [rsp+270h+StringSecurityDescriptor]; StringSecurityDescriptor
0x18002987f  lea     edx, [r9+1]; StringSDRevision
0x180029883  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180029889  test    eax, eax
0x18002988b  jnz     short loc_1800298AD
0x18002988d  call    cs:__imp_GetLastError
0x180029893  test    eax, eax
0x180029895  jle     short loc_18002989F
0x180029897  movzx   eax, ax
0x18002989a  or      eax, 80070000h
0x18002989f  mov     ebx, eax
0x1800298a1  lea     rcx, [rsp+270h+StringSid]
0x1800298a6  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800298ab  jmp     short loc_1800298FF
0x1800298ad  mov     rax, [rsp+270h+SecurityDescriptor]
0x1800298b2  lea     rcx, [rsp+270h+StringSid]
0x1800298b7  mov     [rsi], rax
0x1800298ba  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800298bf  mov     rcx, rdi; void *
0x1800298c2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800298c7  xor     eax, eax
0x1800298c9  mov     rcx, [rbp+170h+var_20]
0x1800298d0  xor     rcx, rsp; StackCookie
0x1800298d3  call    __security_check_cookie
0x1800298d8  mov     rbx, [rsp+270h+arg_10]
0x1800298e0  add     rsp, 260h
0x1800298e7  pop     rdi
0x1800298e8  pop     rsi
0x1800298e9  pop     rbp
0x1800298ea  retn
0x1800298eb  call    cs:__imp_GetLastError
0x1800298f1  test    eax, eax
0x1800298f3  jle     short loc_1800298FD
0x1800298f5  movzx   eax, ax
0x1800298f8  or      eax, 80070000h
0x1800298fd  mov     ebx, eax
0x1800298ff  mov     rcx, rdi
0x180029902  jmp     loc_1800297C1
0x180029907  test    eax, eax
0x180029909  jle     short loc_1800298C9
0x18002990b  movzx   eax, ax
0x18002990e  or      eax, 80070000h
0x180029913  jmp     short loc_1800298C9
```
