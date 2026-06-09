# OwningUser2::GetForUser(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::shared_ptr<OwningUser2> &)

- ea: `0x18005c4a8`
- end: `0x18005c77a`
- name: `?GetForUser@OwningUser2@@SAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV?$shared_ptr@VOwningUser2@@@3@@Z`
- size: `722`
- prototype: `__int64 __fastcall(char *)`
- caller_count: `3`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180057c30`
- `0x180057f40`
- `0x180058654`

## callees

- `0x180002520`
- `0x180002a54`
- `0x1800030d0`
- `0x18000a464`
- `0x180010240`
- `0x180013270`
- `0x1800366b4`
- `0x18005c2ac`
- `0x18005c4a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c5ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c5ed`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005c600`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005c600`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18005c52b`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18005c52b`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18005c4ea`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18005c4ea`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18005c5cb`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18005c5cb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c5f8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c64a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c71e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c5f8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c64a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c71e`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18005c6bc`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18005c6bc`

## string_xrefs

- `0x18005c768`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x18005c753`: `onecore\internal\sdk\inc\wil\opensource/wil/result_macros.h`
- `0x18005c6d0`: `Invalid SID '%ws' to lookup user.`
- `0x18005c61a`: `Invalid SID '%ws' for user.`
- `0x18005c54c`: `onecoreuap\windows\core\isoenvbroker\lib\v2\owninguser.cpp`
- `0x18005c575`: `onecoreuap\windows\core\isoenvbroker\lib\v2\owninguser.cpp`
- `0x18005c626`: `onecoreuap\windows\core\isoenvbroker\lib\v2\owninguser.cpp`
- `0x18005c6fe`: `onecoreuap\windows\core\isoenvbroker\lib\v2\owninguser.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall OwningUser2::GetForUser(char *a1)
{
  char *v1; // rdi
  HRESULT v2; // eax
  int token_information; // eax
  void **v4; // rbx
  int v5; // eax
  unsigned int v6; // edi
  BOOL v8; // r13d
  PSID v9; // r12
  HLOCAL *v10; // rsi
  HLOCAL v11; // r14
  DWORD LastError; // ebx
  const char *v13; // r9
  __int64 v14; // rdx
  unsigned int LastErrorMsg; // ebx
  int v16; // eax
  int ReferencedDomainName; // [rsp+20h] [rbp-E0h]
  int ReferencedDomainNamea; // [rsp+20h] [rbp-E0h]
  int ReferencedDomainNameb; // [rsp+20h] [rbp-E0h]
  HLOCAL hMem; // [rsp+40h] [rbp-C0h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cchReferencedDomainName; // [rsp+4Ch] [rbp-B4h] BYREF
  DWORD cchName; // [rsp+50h] [rbp-B0h] BYREF
  void *Block; // [rsp+58h] [rbp-A8h] BYREF
  HLOCAL *p_hMem; // [rsp+60h] [rbp-A0h]
  PSID Sid; // [rsp+68h] [rbp-98h] BYREF
  char v27; // [rsp+70h] [rbp-90h]
  WCHAR v28[8]; // [rsp+78h] [rbp-88h] BYREF
  __int128 v29; // [rsp+88h] [rbp-78h]
  __int16 v30; // [rsp+98h] [rbp-68h]
  WCHAR Name[264]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2F8h] [rbp+1F8h]

  v1 = a1;
  if ( !*((_QWORD *)a1 + 2) )
  {
    v2 = CoImpersonateClient();
    if ( v2 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x14AA,
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
        (const char *)(unsigned int)v2,
        ReferencedDomainName);
    Block = 0;
    token_information = wil::get_token_information_nothrow<_TOKEN_USER,0>(&Block, -5);
    if ( token_information < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x1C9B,
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/result_macros.h",
        (const char *)(unsigned int)token_information,
        ReferencedDomainName);
    v4 = (void **)Block;
    CoRevertToSelf();
    v5 = OwningUser2::GetForSid(*v4);
    v6 = v5;
    if ( v5 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x97,
        (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\v2\\owninguser.cpp",
        (const char *)(unsigned int)v5,
        ReferencedDomainName);
      if ( v4 )
        operator delete(v4);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE6,
        (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\v2\\owninguser.cpp",
        (const char *)v6,
        ReferencedDomainNamea);
      return v6;
    }
    if ( v4 )
      operator delete(v4);
    return 0;
  }
  hMem = 0;
  p_hMem = &hMem;
  Sid = 0;
  v27 = 1;
  if ( *((_QWORD *)a1 + 3) > 7u )
    a1 = *(char **)a1;
  v8 = ConvertStringSidToSidW((LPCWSTR)a1, &Sid);
  if ( v27 )
  {
    v9 = Sid;
    v10 = p_hMem;
    v11 = *p_hMem;
    if ( *p_hMem )
    {
      LastError = GetLastError();
      LocalFree(v11);
      SetLastError(LastError);
    }
    *v10 = v9;
  }
  if ( !v8 )
  {
    if ( *((_QWORD *)v1 + 3) > 7u )
      v1 = *(char **)v1;
    v13 = "Invalid SID '%ws' for user.";
    v14 = 243;
LABEL_20:
    LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                     retaddr,
                     (void *)v14,
                     (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\v2\\owninguser.cpp",
                     v13,
                     v1);
    goto LABEL_21;
  }
  memset_0(Name, 0, 0x204u);
  cchName = 257;
  *(_OWORD *)v28 = 0;
  v29 = 0;
  v30 = 0;
  cchReferencedDomainName = 16;
  peUse = 0;
  if ( !LookupAccountSidW(0, hMem, Name, &cchName, v28, &cchReferencedDomainName, &peUse) )
  {
    if ( *((_QWORD *)v1 + 3) > 7u )
      v1 = *(char **)v1;
    v13 = "Invalid SID '%ws' to lookup user.";
    v14 = 261;
    goto LABEL_20;
  }
  v16 = OwningUser2::GetForSid(hMem);
  LastErrorMsg = v16;
  if ( v16 >= 0 )
  {
    if ( hMem )
      LocalFree(hMem);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x107,
    (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\v2\\owninguser.cpp",
    (const char *)(unsigned int)v16,
    ReferencedDomainNameb);
LABEL_21:
  if ( hMem )
    LocalFree(hMem);
  return LastErrorMsg;
}

```

## disassembly

```asm
0x18005c4a8  mov     [rsp-8+arg_10], rbx
0x18005c4ad  push    rbp
0x18005c4ae  push    rsi
0x18005c4af  push    rdi
0x18005c4b0  push    r12
0x18005c4b2  push    r13
0x18005c4b4  push    r14
0x18005c4b6  push    r15
0x18005c4b8  lea     rbp, [rsp-1C0h]
0x18005c4c0  sub     rsp, 2C0h
0x18005c4c7  mov     rax, cs:__security_cookie
0x18005c4ce  xor     rax, rsp
0x18005c4d1  mov     [rbp+1F0h+var_40], rax
0x18005c4d8  mov     r15, rdx
0x18005c4db  mov     rdi, rcx
0x18005c4de  xor     esi, esi
0x18005c4e0  cmp     [rcx+10h], rsi
0x18005c4e4  jnz     loc_18005C5A3
0x18005c4ea  call    cs:__imp_CoImpersonateClient
0x18005c4f0  mov     rcx, [rbp+1F8h]; this
0x18005c4f7  test    eax, eax
0x18005c4f9  js      loc_18005C765
0x18005c4ff  mov     [rsp+2F0h+Block], rsi
0x18005c504  lea     rdx, [rsi-5]
0x18005c508  lea     rcx, [rsp+2F0h+Block]
0x18005c50d  call    ??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)
0x18005c512  mov     rcx, [rbp+1F8h]; this
0x18005c519  test    eax, eax
0x18005c51b  js      loc_18005C750
0x18005c521  mov     rbx, [rsp+2F0h+Block]
0x18005c526  mov     [rsp+2F0h+Block], rbx
0x18005c52b  call    cs:__imp_CoRevertToSelf
0x18005c531  mov     rdx, r15
0x18005c534  mov     rcx, [rbx]; void *
0x18005c537  call    ?GetForSid@OwningUser2@@SAJPEAXAEAV?$shared_ptr@VOwningUser2@@@std@@@Z; OwningUser2::GetForSid(void *,std::shared_ptr<OwningUser2> &)
0x18005c53c  mov     edi, eax
0x18005c53e  test    eax, eax
0x18005c540  jns     short loc_18005C58D
0x18005c542  mov     rcx, [rbp+1F8h]; this
0x18005c549  mov     r9d, eax; char *
0x18005c54c  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18005c553  mov     edx, 97h; void *
0x18005c558  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c55d  nop
0x18005c55e  test    rbx, rbx
0x18005c561  jz      short loc_18005C56B
0x18005c563  mov     rcx, rbx; Block
0x18005c566  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18005c56b  mov     rcx, [rbp+1F8h]; this
0x18005c572  mov     r9d, edi; char *
0x18005c575  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18005c57c  mov     edx, 0E6h; void *
0x18005c581  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c586  mov     eax, edi
0x18005c588  jmp     loc_18005C726
0x18005c58d  test    rbx, rbx
0x18005c590  jz      loc_18005C724
0x18005c596  mov     rcx, rbx; Block
0x18005c599  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18005c59e  jmp     loc_18005C724
0x18005c5a3  mov     [rsp+2F0h+hMem], rsi
0x18005c5a8  lea     rax, [rsp+2F0h+hMem]
0x18005c5ad  mov     [rsp+2F0h+var_290], rax
0x18005c5b2  mov     [rsp+2F0h+Sid], rsi
0x18005c5b7  mov     [rsp+2F0h+var_280], 1
0x18005c5bc  cmp     qword ptr [rcx+18h], 7
0x18005c5c1  jbe     short loc_18005C5C6
0x18005c5c3  mov     rcx, [rcx]; StringSid
0x18005c5c6  lea     rdx, [rsp+2F0h+Sid]; Sid
0x18005c5cb  call    cs:__imp_ConvertStringSidToSidW
0x18005c5d1  mov     r13d, eax
0x18005c5d4  cmp     [rsp+2F0h+var_280], sil
0x18005c5d9  jz      short loc_18005C60B
0x18005c5db  mov     r12, [rsp+2F0h+Sid]
0x18005c5e0  mov     rsi, [rsp+2F0h+var_290]
0x18005c5e5  mov     r14, [rsi]
0x18005c5e8  test    r14, r14
0x18005c5eb  jz      short loc_18005C606
0x18005c5ed  call    cs:__imp_GetLastError
0x18005c5f3  mov     ebx, eax
0x18005c5f5  mov     rcx, r14; hMem
0x18005c5f8  call    cs:__imp_LocalFree
0x18005c5fe  mov     ecx, ebx; dwErrCode
0x18005c600  call    cs:__imp_SetLastError
0x18005c606  mov     [rsi], r12
0x18005c609  xor     esi, esi
0x18005c60b  test    r13d, r13d
0x18005c60e  jnz     short loc_18005C657
0x18005c610  cmp     qword ptr [rdi+18h], 7
0x18005c615  jbe     short loc_18005C61A
0x18005c617  mov     rdi, [rdi]
0x18005c61a  lea     r9, aInvalidSidWsFo; "Invalid SID '%ws' for user."
0x18005c621  mov     edx, 0F3h; void *
0x18005c626  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18005c62d  mov     [rsp+2F0h+ReferencedDomainName], rdi; char *
0x18005c632  mov     rcx, [rbp+1F8h]; this
0x18005c639  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x18005c63e  mov     ebx, eax
0x18005c640  mov     rcx, [rsp+2F0h+hMem]; hMem
0x18005c645  test    rcx, rcx
0x18005c648  jz      short loc_18005C650
0x18005c64a  call    cs:__imp_LocalFree
0x18005c650  mov     eax, ebx
0x18005c652  jmp     loc_18005C726
0x18005c657  xor     edx, edx; Val
0x18005c659  mov     r8d, 204h; Size
0x18005c65f  lea     rcx, [rbp+1F0h+Name]; void *
0x18005c663  call    memset_0
0x18005c668  mov     [rsp+2F0h+cchName], 101h
0x18005c670  xorps   xmm0, xmm0
0x18005c673  xor     eax, eax
0x18005c675  movups  xmmword ptr [rsp+2F0h+var_278], xmm0
0x18005c67a  movups  [rbp+1F0h+var_268], xmm0
0x18005c67e  mov     [rbp+1F0h+var_258], ax
0x18005c682  mov     [rsp+2F0h+var_2A4], 10h
0x18005c68a  mov     [rsp+2F0h+var_2A8], esi
0x18005c68e  lea     rax, [rsp+2F0h+var_2A8]
0x18005c693  mov     [rsp+2F0h+peUse], rax; peUse
0x18005c698  lea     rax, [rsp+2F0h+var_2A4]
0x18005c69d  mov     [rsp+2F0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18005c6a2  lea     rax, [rsp+2F0h+var_278]
0x18005c6a7  mov     [rsp+2F0h+ReferencedDomainName], rax; int
0x18005c6ac  lea     r9, [rsp+2F0h+cchName]; cchName
0x18005c6b1  lea     r8, [rbp+1F0h+Name]; Name
0x18005c6b5  mov     rdx, [rsp+2F0h+hMem]; Sid
0x18005c6ba  xor     ecx, ecx; lpSystemName
0x18005c6bc  call    cs:__imp_LookupAccountSidW
0x18005c6c2  test    eax, eax
0x18005c6c4  jnz     short loc_18005C6E1
0x18005c6c6  cmp     qword ptr [rdi+18h], 7
0x18005c6cb  jbe     short loc_18005C6D0
0x18005c6cd  mov     rdi, [rdi]
0x18005c6d0  lea     r9, aInvalidSidWsTo; "Invalid SID '%ws' to lookup user."
0x18005c6d7  mov     edx, 105h
0x18005c6dc  jmp     loc_18005C626
0x18005c6e1  mov     rdx, r15
0x18005c6e4  mov     rcx, [rsp+2F0h+hMem]; void *
0x18005c6e9  call    ?GetForSid@OwningUser2@@SAJPEAXAEAV?$shared_ptr@VOwningUser2@@@std@@@Z; OwningUser2::GetForSid(void *,std::shared_ptr<OwningUser2> &)
0x18005c6ee  mov     ebx, eax
0x18005c6f0  test    eax, eax
0x18005c6f2  jns     short loc_18005C714
0x18005c6f4  mov     rcx, [rbp+1F8h]; this
0x18005c6fb  mov     r9d, eax; char *
0x18005c6fe  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18005c705  mov     edx, 107h; void *
0x18005c70a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c70f  jmp     loc_18005C640
0x18005c714  mov     rcx, [rsp+2F0h+hMem]; hMem
0x18005c719  test    rcx, rcx
0x18005c71c  jz      short loc_18005C724
0x18005c71e  call    cs:__imp_LocalFree
0x18005c724  xor     eax, eax
0x18005c726  mov     rcx, [rbp+1F0h+var_40]
0x18005c72d  xor     rcx, rsp; StackCookie
0x18005c730  call    __security_check_cookie
0x18005c735  mov     rbx, [rsp+2F0h+arg_10]
0x18005c73d  add     rsp, 2C0h
0x18005c744  pop     r15
0x18005c746  pop     r14
0x18005c748  pop     r13
0x18005c74a  pop     r12
0x18005c74c  pop     rdi
0x18005c74d  pop     rsi
0x18005c74e  pop     rbp
0x18005c74f  retn
0x18005c750  mov     r9d, eax; char *
0x18005c753  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18005c75a  mov     edx, 1C9Bh; void *
0x18005c75f  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18005c765  mov     r9d, eax; char *
0x18005c768  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18005c76f  mov     edx, 14AAh; void *
0x18005c774  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
