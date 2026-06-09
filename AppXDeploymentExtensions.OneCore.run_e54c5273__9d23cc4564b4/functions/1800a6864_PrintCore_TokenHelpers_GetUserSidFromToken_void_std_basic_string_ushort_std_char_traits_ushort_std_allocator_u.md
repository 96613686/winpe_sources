# PrintCore::TokenHelpers::GetUserSidFromToken(void *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1800a6864`
- end: `0x1800a69f2`
- name: `?GetUserSidFromToken@TokenHelpers@PrintCore@@SAJPEAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `398`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18018f310`

## callees

- `0x180067050`
- `0x180080b84`
- `0x1800a6864`
- `0x1800a69f8`
- `0x1800a6a3c`
- `0x1800a6a88`
- `0x1800a6ac8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a68dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a68dc`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800a68a5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800a693c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800a68a5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800a693c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a69d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a69d5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800a6914`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800a6914`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800a6980`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800a6980`

## string_xrefs

- `0x1800a68cb`: `OneCoreUap\Internal\Printscan\inc\TokenHelpers.h`
- `0x1800a68fd`: `OneCoreUap\Internal\Printscan\inc\TokenHelpers.h`
- `0x1800a6956`: `OneCoreUap\Internal\Printscan\inc\TokenHelpers.h`
- `0x1800a699a`: `OneCoreUap\Internal\Printscan\inc\TokenHelpers.h`
- `0x1800a68ed`: `GetTokenInformation (size) failed!`
- `0x1800a68b5`: `GetTokenInformation succeeded with an empty buffer!`
- `0x1800a698b`: `ConvertSidToStringSid failed!`
- `0x1800a6947`: `GetTokenInformation (token) failed!`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall PrintCore::TokenHelpers::GetUserSidFromToken(HANDLE TokenHandle, _QWORD *a2)
{
  _QWORD *v2; // rbx
  BOOL TokenInformation; // eax
  char v5; // al
  DWORD LastError; // eax
  PSID *v7; // rdi
  unsigned int v8; // eax
  unsigned int v9; // eax
  __int64 v10; // r8
  const char *v11; // r9
  __int64 result; // rax
  char *v13; // [rsp+28h] [rbp-20h]
  char *v14; // [rsp+28h] [rbp-20h]
  char *v15; // [rsp+28h] [rbp-20h]
  const char *v16; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  DWORD TokenInformationLength; // [rsp+58h] [rbp+10h] BYREF
  LPWSTR StringSid; // [rsp+60h] [rbp+18h] BYREF
  PSID *v20; // [rsp+68h] [rbp+20h]

  v2 = a2;
  a2[2] = 0;
  if ( a2[3] > 7u )
    a2 = (_QWORD *)*a2;
  *(_WORD *)a2 = 0;
  TokenInformationLength = 0;
  TokenInformation = GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength);
  v5 = TokenInformation;
  try
  {
    wil::details::in1diag3::Throw_HrIfMsg(
      retaddr,
      (void *)0xAA,
      (unsigned int)"OneCoreUap\\Internal\\Printscan\\inc\\TokenHelpers.h",
      (const char *)0x8000FFFFLL,
      v5,
      (bool)"GetTokenInformation succeeded with an empty buffer!",
      v16);
    LastError = GetLastError();
    wil::details::in1diag3::Throw_GetLastErrorIfMsg(
      retaddr,
      (void *)0xAC,
      (unsigned int)"OneCoreUap\\Internal\\Printscan\\inc\\TokenHelpers.h",
      (const char *)(LastError != 122),
      (bool)"GetTokenInformation (size) failed!",
      v13);
    v7 = (PSID *)LocalAlloc(0, TokenInformationLength);
    v20 = v7;
    v8 = GetTokenInformation(TokenHandle, TokenUser, v7, TokenInformationLength, &TokenInformationLength);
    wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
      retaddr,
      (void *)0xAF,
      (unsigned int)"OneCoreUap\\Internal\\Printscan\\inc\\TokenHelpers.h",
      (const char *)v8,
      (int)"GetTokenInformation (token) failed!",
      v14);
    StringSid = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &StringSid,
      0);
    v9 = ConvertSidToStringSidW(*v7, &StringSid);
    wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
      retaddr,
      (void *)0xB2,
      (unsigned int)"OneCoreUap\\Internal\\Printscan\\inc\\TokenHelpers.h",
      (const char *)v9,
      (int)"ConvertSidToStringSid failed!",
      v15);
    v10 = -1;
    do
      ++v10;
    while ( StringSid[v10] );
    std::wstring::_Assign<unsigned short>(v2, StringSid);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&StringSid);
    LocalFree(v7);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xB7,
                           (unsigned int)"OneCoreUap\\Internal\\Printscan\\inc\\TokenHelpers.h",
                           v11);
  }
  return result;
}

```

## disassembly

```asm
0x1800a6864  mov     [rsp+arg_0], rbx
0x1800a6869  push    rsi
0x1800a686a  push    rdi
0x1800a686b  push    r14; char *
0x1800a686d  sub     rsp, 30h
0x1800a6871  mov     rbx, rdx
0x1800a6874  mov     rsi, rcx
0x1800a6877  xor     r14d, r14d
0x1800a687a  mov     [rdx+10h], r14
0x1800a687e  cmp     qword ptr [rdx+18h], 7
0x1800a6883  jbe     short loc_1800A6888
0x1800a6885  mov     rdx, [rdx]
0x1800a6888  mov     [rdx], r14w
0x1800a688c  mov     [rsp+48h+TokenInformationLength], r14d
0x1800a6891  lea     rax, [rsp+48h+TokenInformationLength]
0x1800a6896  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x1800a689b  xor     r9d, r9d; TokenInformationLength
0x1800a689e  xor     r8d, r8d; TokenInformation
0x1800a68a1  lea     edx, [r9+1]; TokenInformationClass
0x1800a68a5  call    cs:__imp_GetTokenInformation
0x1800a68ab  test    eax, eax
0x1800a68ad  setnz   al
0x1800a68b0  mov     rcx, [rsp+48h]; this
0x1800a68b5  lea     rdx, aGettokeninform_0; "GetTokenInformation succeeded with an e"...
0x1800a68bc  mov     [rsp+48h+var_20], rdx; char *
0x1800a68c1  mov     byte ptr [rsp+48h+ReturnLength], al; char
0x1800a68c5  mov     r9d, 8000FFFFh; char *
0x1800a68cb  lea     r8, aOnecoreuapInte_1; "OneCoreUap\\Internal\\Printscan\\inc\\T"...
0x1800a68d2  mov     edx, 0AAh; void *
0x1800a68d7  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1800a68dc  call    cs:__imp_GetLastError
0x1800a68e2  cmp     eax, 7Ah ; 'z'
0x1800a68e5  setnz   al
0x1800a68e8  mov     rcx, [rsp+48h]; this
0x1800a68ed  lea     rdx, aGettokeninform_1; "GetTokenInformation (size) failed!"
0x1800a68f4  mov     [rsp+48h+ReturnLength], rdx; bool
0x1800a68f9  movzx   r9d, al; char *
0x1800a68fd  lea     r8, aOnecoreuapInte_1; "OneCoreUap\\Internal\\Printscan\\inc\\T"...
0x1800a6904  mov     edx, 0ACh; void *
0x1800a6909  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x1800a690e  mov     edx, [rsp+48h+TokenInformationLength]; uBytes
0x1800a6912  xor     ecx, ecx; uFlags
0x1800a6914  call    cs:__imp_LocalAlloc
0x1800a691a  mov     rdi, rax
0x1800a691d  mov     [rsp+48h+arg_18], rax
0x1800a6922  lea     rax, [rsp+48h+TokenInformationLength]
0x1800a6927  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x1800a692c  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x1800a6931  mov     r8, rdi; TokenInformation
0x1800a6934  mov     edx, 1; TokenInformationClass
0x1800a6939  mov     rcx, rsi; TokenHandle
0x1800a693c  call    cs:__imp_GetTokenInformation
0x1800a6942  mov     rcx, [rsp+48h]; this
0x1800a6947  lea     rdx, aGettokeninform_3; "GetTokenInformation (token) failed!"
0x1800a694e  mov     [rsp+48h+ReturnLength], rdx; int
0x1800a6953  mov     r9d, eax; char *
0x1800a6956  lea     r8, aOnecoreuapInte_1; "OneCoreUap\\Internal\\Printscan\\inc\\T"...
0x1800a695d  mov     edx, 0AFh; void *
0x1800a6962  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x1800a6967  mov     [rsp+48h+StringSid], r14
0x1800a696c  xor     edx, edx
0x1800a696e  lea     rcx, [rsp+48h+StringSid]
0x1800a6973  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800a6978  lea     rdx, [rsp+48h+StringSid]; StringSid
0x1800a697d  mov     rcx, [rdi]; Sid
0x1800a6980  call    cs:__imp_ConvertSidToStringSidW
0x1800a6986  mov     rcx, [rsp+48h]; this
0x1800a698b  lea     rdx, aConvertsidtost; "ConvertSidToStringSid failed!"
0x1800a6992  mov     [rsp+48h+ReturnLength], rdx; int
0x1800a6997  mov     r9d, eax; char *
0x1800a699a  lea     r8, aOnecoreuapInte_1; "OneCoreUap\\Internal\\Printscan\\inc\\T"...
0x1800a69a1  mov     edx, 0B2h; void *
0x1800a69a6  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x1800a69ab  mov     rdx, [rsp+48h+StringSid]
0x1800a69b0  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800a69b4  inc     r8
0x1800a69b7  cmp     [rdx+r8*2], r14w
0x1800a69bc  jnz     short loc_1800A69B4
0x1800a69be  mov     rcx, rbx
0x1800a69c1  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800a69c6  nop
0x1800a69c7  lea     rcx, [rsp+48h+StringSid]
0x1800a69cc  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800a69d1  nop
0x1800a69d2  mov     rcx, rdi; hMem
0x1800a69d5  call    cs:__imp_LocalFree
0x1800a69db  xor     eax, eax
0x1800a69dd  jmp     short loc_1800A69E3
0x1800a69df  mov     eax, [rsp+48h+TokenInformationLength]
0x1800a69e3  mov     rbx, [rsp+48h+arg_0]
0x1800a69e8  add     rsp, 30h
0x1800a69ec  pop     r14
0x1800a69ee  pop     rdi
0x1800a69ef  pop     rsi
0x1800a69f0  retn
```
