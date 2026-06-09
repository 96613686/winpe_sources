# Windows::Internal::AssignedAccess::UserInfoHelper::GetUserSidFromToken(void *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1800506e0`
- end: `0x180050803`
- name: `?GetUserSidFromToken@UserInfoHelper@AssignedAccess@Internal@Windows@@SAJPEAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `291`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180023e30`
- `0x180050658`

## callees

- `0x18000b694`
- `0x18002074c`
- `0x1800221e0`
- `0x18002b244`
- `0x18004eca0`
- `0x18004fec0`
- `0x1800506e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005071c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005071c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180050712`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180050767`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180050712`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180050767`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18005079b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18005079b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Internal::AssignedAccess::UserInfoHelper::GetUserSidFromToken(
        HANDLE TokenHandle,
        __int64 a2)
{
  const char *v4; // r9
  const char *v6; // r9
  unsigned int LastError; // ebx
  const char *v8; // r9
  unsigned __int64 v9; // rax
  __int64 v10; // rcx
  LPVOID TokenInformation[4]; // [rsp+30h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]
  DWORD TokenInformationLength; // [rsp+70h] [rbp+20h] BYREF
  LPWSTR StringSid; // [rsp+78h] [rbp+28h] BYREF

  TokenInformationLength = 0;
  if ( !GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) && GetLastError() != 122 )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x30,
             (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\userinfohelper.cpp",
             v4);
  std::vector<unsigned char>::vector<unsigned char>(TokenInformation, TokenInformationLength);
  if ( GetTokenInformation(TokenHandle, TokenUser, TokenInformation[0], TokenInformationLength, &TokenInformationLength) )
  {
    StringSid = 0;
    if ( ConvertSidToStringSidW(*(PSID *)TokenInformation[0], &StringSid) )
    {
      v9 = std::_WChar_traits<unsigned short>::length(StringSid);
      std::wstring::_Assign<unsigned short>(a2, v10, v9);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
      LastError = 0;
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x38,
                    (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\userinfohelper.cpp",
                    v8);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
    }
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x34,
                  (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\userinfohelper.cpp",
                  v6);
  }
  std::vector<unsigned char>::_Tidy(TokenInformation);
  return LastError;
}

```

## disassembly

```asm
0x1800506e0  mov     [rsp-8+arg_0], rbx
0x1800506e5  mov     [rsp-8+arg_8], rdi
0x1800506ea  push    rbp
0x1800506eb  mov     rbp, rsp
0x1800506ee  sub     rsp, 50h
0x1800506f2  mov     rdi, rdx
0x1800506f5  mov     rbx, rcx
0x1800506f8  mov     [rbp+TokenInformationLength], 0
0x1800506ff  lea     rax, [rbp+TokenInformationLength]
0x180050703  mov     [rsp+50h+ReturnLength], rax; ReturnLength
0x180050708  xor     r9d, r9d; TokenInformationLength
0x18005070b  xor     r8d, r8d; TokenInformation
0x18005070e  lea     edx, [r9+1]; TokenInformationClass
0x180050712  call    cs:__imp_GetTokenInformation
0x180050718  test    eax, eax
0x18005071a  jnz     short loc_180050741
0x18005071c  call    cs:__imp_GetLastError
0x180050722  cmp     eax, 7Ah ; 'z'
0x180050725  jz      short loc_180050741
0x180050727  mov     rcx, [rbp+8]; this
0x18005072b  lea     r8, aOnecoreuapBase_94; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180050732  mov     edx, 30h ; '0'; void *
0x180050737  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005073c  jmp     loc_1800507F3
0x180050741  mov     edx, [rbp+TokenInformationLength]
0x180050744  lea     rcx, [rbp+TokenInformation]
0x180050748  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x18005074d  nop
0x18005074e  lea     rax, [rbp+TokenInformationLength]
0x180050752  mov     [rsp+50h+ReturnLength], rax; ReturnLength
0x180050757  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18005075b  mov     r8, [rbp+TokenInformation]; TokenInformation
0x18005075f  mov     edx, 1; TokenInformationClass
0x180050764  mov     rcx, rbx; TokenHandle
0x180050767  call    cs:__imp_GetTokenInformation
0x18005076d  test    eax, eax
0x18005076f  jnz     short loc_180050788
0x180050771  mov     rcx, [rbp+8]; this
0x180050775  lea     r8, aOnecoreuapBase_94; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18005077c  lea     edx, [rax+34h]; void *
0x18005077f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180050784  mov     ebx, eax
0x180050786  jmp     short loc_1800507E8
0x180050788  mov     rcx, [rbp+TokenInformation]
0x18005078c  mov     [rbp+StringSid], 0
0x180050794  lea     rdx, [rbp+StringSid]; StringSid
0x180050798  mov     rcx, [rcx]; Sid
0x18005079b  call    cs:__imp_ConvertSidToStringSidW
0x1800507a1  test    eax, eax
0x1800507a3  jnz     short loc_1800507C5
0x1800507a5  mov     rcx, [rbp+8]; this
0x1800507a9  lea     r8, aOnecoreuapBase_94; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x1800507b0  lea     edx, [rax+38h]; void *
0x1800507b3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800507b8  mov     ebx, eax
0x1800507ba  lea     rcx, [rbp+StringSid]
0x1800507be  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800507c3  jmp     short loc_1800507E8
0x1800507c5  mov     rcx, [rbp+StringSid]
0x1800507c9  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x1800507ce  mov     r8, rax
0x1800507d1  mov     rdx, rcx
0x1800507d4  mov     rcx, rdi
0x1800507d7  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800507dc  nop
0x1800507dd  lea     rcx, [rbp+StringSid]
0x1800507e1  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800507e6  xor     ebx, ebx
0x1800507e8  lea     rcx, [rbp+TokenInformation]
0x1800507ec  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800507f1  mov     eax, ebx
0x1800507f3  mov     rbx, [rsp+50h+arg_0]
0x1800507f8  mov     rdi, [rsp+50h+arg_8]
0x1800507fd  add     rsp, 50h
0x180050801  pop     rbp
0x180050802  retn
```
