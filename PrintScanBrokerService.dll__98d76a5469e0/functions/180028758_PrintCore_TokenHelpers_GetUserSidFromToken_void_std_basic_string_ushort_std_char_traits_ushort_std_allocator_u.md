# PrintCore::TokenHelpers::GetUserSidFromToken(void *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180028758`
- end: `0x1800288d2`
- name: `?GetUserSidFromToken@TokenHelpers@PrintCore@@SAJPEAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `378`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `5`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180028624`
- `0x1800291d0`
- `0x180031f84`
- `0x180033894`
- `0x180035798`

## callees

- `0x1800102f8`
- `0x18001cfd4`
- `0x18001d0a0`
- `0x180023a20`
- `0x180027020`
- `0x180028758`
- `0x18002b28c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800287cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800287cc`
- `KERNELBASE!LocalAlloc` at `0x180028804`
- `KERNELBASE!LocalAlloc` at `0x180028804`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180028795`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002882c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180028795`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002882c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800288bb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800288bb`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180028869`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180028869`

## string_xrefs

- `0x1800287bb`: `OneCoreUap\Internal\Printscan\inc\TokenHelpers.h`
- `0x1800287ed`: `OneCoreUap\Internal\Printscan\inc\TokenHelpers.h`
- `0x180028846`: `OneCoreUap\Internal\Printscan\inc\TokenHelpers.h`
- `0x180028883`: `OneCoreUap\Internal\Printscan\inc\TokenHelpers.h`
- `0x1800287dd`: `GetTokenInformation (size) failed!`
- `0x1800287a5`: `GetTokenInformation succeeded with an empty buffer!`
- `0x180028874`: `ConvertSidToStringSid failed!`
- `0x180028837`: `GetTokenInformation (token) failed!`

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
  __int64 v10; // rcx
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
    v9 = ConvertSidToStringSidW(*v7, &StringSid);
    wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
      retaddr,
      (void *)0xB2,
      (unsigned int)"OneCoreUap\\Internal\\Printscan\\inc\\TokenHelpers.h",
      (const char *)v9,
      (int)"ConvertSidToStringSid failed!",
      v15);
    std::_WChar_traits<unsigned short>::length(StringSid);
    std::wstring::_Assign<unsigned short>(v2, v10);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
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
0x180028758  push    rbx
0x18002875a  push    rsi
0x18002875b  push    rdi; char *
0x18002875c  sub     rsp, 30h
0x180028760  mov     rbx, rdx
0x180028763  mov     rsi, rcx
0x180028766  mov     qword ptr [rdx+10h], 0
0x18002876e  cmp     qword ptr [rdx+18h], 7
0x180028773  jbe     short loc_180028778
0x180028775  mov     rdx, [rdx]
0x180028778  xor     eax, eax
0x18002877a  mov     [rdx], ax
0x18002877d  mov     [rsp+48h+TokenInformationLength], eax
0x180028781  lea     rax, [rsp+48h+TokenInformationLength]
0x180028786  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18002878b  xor     r9d, r9d; TokenInformationLength
0x18002878e  xor     r8d, r8d; TokenInformation
0x180028791  lea     edx, [r9+1]; TokenInformationClass
0x180028795  call    cs:__imp_GetTokenInformation
0x18002879b  test    eax, eax
0x18002879d  setnz   al
0x1800287a0  mov     rcx, [rsp+48h]; this
0x1800287a5  lea     rdx, aGettokeninform; "GetTokenInformation succeeded with an e"...
0x1800287ac  mov     [rsp+48h+var_20], rdx; char *
0x1800287b1  mov     byte ptr [rsp+48h+ReturnLength], al; char
0x1800287b5  mov     r9d, 8000FFFFh; char *
0x1800287bb  lea     r8, aOnecoreuapInte_2; "OneCoreUap\\Internal\\Printscan\\inc\\T"...
0x1800287c2  mov     edx, 0AAh; void *
0x1800287c7  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1800287cc  call    cs:__imp_GetLastError
0x1800287d2  cmp     eax, 7Ah ; 'z'
0x1800287d5  setnz   al
0x1800287d8  mov     rcx, [rsp+48h]; this
0x1800287dd  lea     rdx, aGettokeninform_0; "GetTokenInformation (size) failed!"
0x1800287e4  mov     [rsp+48h+ReturnLength], rdx; bool
0x1800287e9  movzx   r9d, al; char *
0x1800287ed  lea     r8, aOnecoreuapInte_2; "OneCoreUap\\Internal\\Printscan\\inc\\T"...
0x1800287f4  mov     edx, 0ACh; void *
0x1800287f9  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x1800287fe  mov     edx, [rsp+48h+TokenInformationLength]; uBytes
0x180028802  xor     ecx, ecx; uFlags
0x180028804  call    cs:__imp_LocalAlloc
0x18002880a  mov     rdi, rax
0x18002880d  mov     [rsp+48h+arg_18], rax
0x180028812  lea     rax, [rsp+48h+TokenInformationLength]
0x180028817  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18002881c  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x180028821  mov     r8, rdi; TokenInformation
0x180028824  mov     edx, 1; TokenInformationClass
0x180028829  mov     rcx, rsi; TokenHandle
0x18002882c  call    cs:__imp_GetTokenInformation
0x180028832  mov     rcx, [rsp+48h]; this
0x180028837  lea     rdx, aGettokeninform_1; "GetTokenInformation (token) failed!"
0x18002883e  mov     [rsp+48h+ReturnLength], rdx; int
0x180028843  mov     r9d, eax; char *
0x180028846  lea     r8, aOnecoreuapInte_2; "OneCoreUap\\Internal\\Printscan\\inc\\T"...
0x18002884d  mov     edx, 0AFh; void *
0x180028852  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x180028857  nop
0x180028858  mov     [rsp+48h+StringSid], 0
0x180028861  lea     rdx, [rsp+48h+StringSid]; StringSid
0x180028866  mov     rcx, [rdi]; Sid
0x180028869  call    cs:__imp_ConvertSidToStringSidW
0x18002886f  mov     rcx, [rsp+48h]; this
0x180028874  lea     rdx, aConvertsidtost; "ConvertSidToStringSid failed!"
0x18002887b  mov     [rsp+48h+ReturnLength], rdx; int
0x180028880  mov     r9d, eax; char *
0x180028883  lea     r8, aOnecoreuapInte_2; "OneCoreUap\\Internal\\Printscan\\inc\\T"...
0x18002888a  mov     edx, 0B2h; void *
0x18002888f  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x180028894  mov     rcx, [rsp+48h+StringSid]
0x180028899  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18002889e  mov     r8, rax
0x1800288a1  mov     rdx, rcx
0x1800288a4  mov     rcx, rbx
0x1800288a7  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800288ac  nop
0x1800288ad  lea     rcx, [rsp+48h+StringSid]
0x1800288b2  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800288b7  nop
0x1800288b8  mov     rcx, rdi; hMem
0x1800288bb  call    cs:__imp_LocalFree
0x1800288c1  xor     eax, eax
0x1800288c3  jmp     short loc_1800288C9
0x1800288c5  mov     eax, [rsp+48h+TokenInformationLength]
0x1800288c9  add     rsp, 30h
0x1800288cd  pop     rdi
0x1800288ce  pop     rsi
0x1800288cf  pop     rbx
0x1800288d0  retn
```
