# CLocationUserHandles::RemoveCurrentUser(void)

- ea: `0x180019bb0`
- end: `0x180019dd6`
- name: `?RemoveCurrentUser@CLocationUserHandles@@UEAAJXZ`
- size: `550`
- prototype: `__int64 __fastcall(CLocationUserHandles *__hidden this)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180018228`
- `0x180019bb0`
- `0x18001e170`
- `0x18001efe0`
- `0x18001f09c`
- `0x18001f334`
- `0x180050b54`
- `0x18005efdc`
- `0x180084ac8`
- `0x18009c310`
- `0x1800a98c0`
- `0x1800aa5ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019cfa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019cfa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019c6c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019c6c`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180019c88`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180019c88`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180019bd6`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180019bd6`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180019d19`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180019d95`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180019d19`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180019d95`

## string_xrefs

- `0x180019c03`: `impersonate.Status()`
- `0x180019bf1`: `CLocationUserHandles::RemoveCurrentUser`
- `0x180019ca4`: `CLocationUserHandles::RemoveCurrentUser`
- `0x180019d31`: `CLocationUserHandles::RemoveCurrentUser`
- `0x180019d67`: `CLocationUserHandles::RemoveCurrentUser`
- `0x180019d60`: `!(wil::verify_bool(token.GetEffectiveToken((0x00020000L) | (0x0008) | (0x0004) | (0x0002))))`
- `0x180019d2a`: `!(wil::verify_bool(token.GetUser(&userSid)))`

## pseudocode

```c
__int64 __fastcall CLocationUserHandles::RemoveCurrentUser(CLocationUserHandles *this)
{
  HRESULT v2; // eax
  unsigned int LastError; // ebx
  __int64 *v5; // rbx
  wil::details *v7; // [rsp+28h] [rbp-D8h]
  int v8; // [rsp+30h] [rbp-D0h]
  const char *v9; // [rsp+40h] [rbp-C0h] BYREF
  void **v10; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v11; // [rsp+50h] [rbp-B0h]
  __int64 v12; // [rsp+60h] [rbp-A0h]
  _BYTE v13[8]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE pSid2[120]; // [rsp+78h] [rbp-88h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+138h] [rbp+38h]

  v2 = CoImpersonateClient();
  LastError = v2;
  if ( v2 < 0 )
  {
    if ( v2 != -2147417833 )
    {
      LODWORD(v7) = v2;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)0x4A,
        (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\framework\\locationuserhandles.cpp",
        "CLocationUserHandles::RemoveCurrentUser",
        "impersonate.Status()",
        v7,
        v8);
    }
    return LastError;
  }
  v12 = 0;
  v10 = &ATL::CAccessToken::`vftable';
  v11 = 0;
  if ( !ATL::CAccessToken::GetEffectiveToken((ATL::CAccessToken *)&v10, 0x2000Eu) )
  {
    LastError = wil::details::in1diag5::Return_GetLastError(
                  retaddr,
                  (void *)0x4E,
                  (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\framework\\locationuserhandles.cpp",
                  "CLocationUserHandles::RemoveCurrentUser",
                  "!(wil::verify_bool(token.GetEffectiveToken((0x00020000L) | (0x0008) | (0x0004) | (0x0002))))",
                  (const char *)v7);
    goto LABEL_14;
  }
  memset_0(v13, 0, 0x78u);
  ATL::CSid::CSid((ATL::CSid *)v13);
  if ( !ATL::CAccessToken::GetInfoConvert<ATL::CSid,_TOKEN_USER>((__int64)&v10, (__int64)v13) )
  {
    LastError = wil::details::in1diag5::Return_GetLastError(
                  retaddr,
                  (void *)0x51,
                  (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\framework\\locationuserhandles.cpp",
                  "CLocationUserHandles::RemoveCurrentUser",
                  "!(wil::verify_bool(token.GetUser(&userSid)))",
                  (const char *)v7);
    ATL::CSid::~CSid((ATL::CSid *)v13);
LABEL_14:
    v10 = &ATL::CAccessToken::`vftable';
    ATL::CAccessToken::Clear((ATL::CAccessToken *)&v10);
    CoRevertToSelf();
    return LastError;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  v5 = (__int64 *)*((_QWORD *)this + 13);
  while ( 1 )
  {
    v5 = (__int64 *)*v5;
    if ( v5 == *((__int64 **)this + 13) )
      break;
    if ( EqualSid(v5 + 4, pSid2) )
    {
      LODWORD(v7) = -2147418113;
      wil::details::in1diag5::Log_HrIfMsg(
        retaddr,
        (void *)0x5A,
        (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\framework\\locationuserhandles.cpp",
        "CLocationUserHandles::RemoveCurrentUser",
        "iterator->refCount == 0",
        (const char *)v7,
        *((_DWORD *)v5 + 38) == 0,
        (bool)"Ref count is 0",
        v9);
      if ( (*((_DWORD *)v5 + 38))-- == 1 )
        std::list<AccessTokenItem>::erase((char *)this + 104, &v9, v5);
      break;
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  ATL::CSid::~CSid((ATL::CSid *)v13);
  v10 = &ATL::CAccessToken::`vftable';
  ATL::CAccessToken::Clear((ATL::CAccessToken *)&v10);
  CoRevertToSelf();
  return 0;
}

```

## disassembly

```asm
0x180019bb0  push    rbp
0x180019bb2  push    rbx
0x180019bb3  push    rsi
0x180019bb4  push    rdi
0x180019bb5  push    r14
0x180019bb7  push    r15
0x180019bb9  lea     rbp, [rsp-8]
0x180019bbe  sub     rsp, 108h
0x180019bc5  mov     rax, cs:__security_cookie
0x180019bcc  xor     rax, rsp
0x180019bcf  mov     [rbp+30h+var_40], rax
0x180019bd3  mov     rdi, rcx
0x180019bd6  call    cs:__imp_CoImpersonateClient
0x180019bdc  mov     ebx, eax
0x180019bde  test    eax, eax
0x180019be0  jns     loc_180019DA0
0x180019be6  cmp     eax, 80010117h
0x180019beb  jz      short loc_180019C19
0x180019bed  mov     rcx, [rbp+38h]; this
0x180019bf1  lea     r9, aClocationuserh_1; "CLocationUserHandles::RemoveCurrentUser"
0x180019bf8  mov     dword ptr [rsp+130h+var_108], eax; wil::details *
0x180019bfc  lea     r8, aOnecoreuapDriv_40; "onecoreuap\\drivers\\mobilepc\\location"...
0x180019c03  lea     rax, aImpersonateSta; "impersonate.Status()"
0x180019c0a  mov     edx, 4Ah ; 'J'; void *
0x180019c0f  mov     [rsp+130h+var_110], rax; char *
0x180019c14  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180019c19  mov     eax, ebx
0x180019c1b  mov     rcx, [rbp+30h+var_40]
0x180019c1f  xor     rcx, rsp; StackCookie
0x180019c22  call    __security_check_cookie
0x180019c27  add     rsp, 108h
0x180019c2e  pop     r15
0x180019c30  pop     r14
0x180019c32  pop     rdi
0x180019c33  pop     rsi
0x180019c34  pop     rbx
0x180019c35  pop     rbp
0x180019c36  retn
0x180019c37  xor     edx, edx; Val
0x180019c39  lea     rcx, [rsp+130h+var_C0]; void *
0x180019c3e  lea     r8d, [rdx+78h]; Size
0x180019c42  call    memset_0
0x180019c47  lea     rcx, [rsp+130h+var_C0]; this
0x180019c4c  call    ??0CSid@ATL@@QEAA@XZ; ATL::CSid::CSid(void)
0x180019c51  lea     rdx, [rsp+130h+var_C0]
0x180019c56  lea     rcx, [rsp+130h+var_E8]
0x180019c5b  call    ??$GetInfoConvert@VCSid@ATL@@U_TOKEN_USER@@@CAccessToken@ATL@@IEBA_NPEAVCSid@1@W4_TOKEN_INFORMATION_CLASS@@PEAU_TOKEN_USER@@@Z; ATL::CAccessToken::GetInfoConvert<ATL::CSid,_TOKEN_USER>(ATL::CSid *,_TOKEN_INFORMATION_CLASS,_TOKEN_USER *)
0x180019c60  test    al, al
0x180019c62  jz      loc_180019D26
0x180019c68  lea     rcx, [rdi+40h]; lpCriticalSection
0x180019c6c  call    cs:__imp_EnterCriticalSection
0x180019c72  mov     rbx, [rdi+68h]
0x180019c76  mov     rbx, [rbx]
0x180019c79  cmp     rbx, [rdi+68h]
0x180019c7d  jz      short loc_180019CF6
0x180019c7f  lea     rcx, [rbx+20h]; pSid1
0x180019c83  lea     rdx, [rsp+130h+pSid2]; pSid2
0x180019c88  call    cs:__imp_EqualSid
0x180019c8e  test    eax, eax
0x180019c90  jz      short loc_180019C76
0x180019c92  cmp     dword ptr [rbx+98h], 0
0x180019c99  lea     rdx, aRefCountIs0; "Ref count is 0"
0x180019ca0  mov     rcx, [rbp+38h]; this
0x180019ca4  lea     r9, aClocationuserh_1; "CLocationUserHandles::RemoveCurrentUser"
0x180019cab  mov     qword ptr [rsp+130h+var_F8], rdx; bool
0x180019cb0  lea     r8, aOnecoreuapDriv_40; "onecoreuap\\drivers\\mobilepc\\location"...
0x180019cb7  setz    al
0x180019cba  mov     edx, 5Ah ; 'Z'; void *
0x180019cbf  mov     [rsp+130h+var_100], al; char
0x180019cc3  lea     rax, aIteratorRefcou; "iterator->refCount == 0"
0x180019cca  mov     dword ptr [rsp+130h+var_108], 8000FFFFh; char *
0x180019cd2  mov     [rsp+130h+var_110], rax; char *
0x180019cd7  call    ?Log_HrIfMsg@in1diag5@details@wil@@YA_NPEAXIPEBD11J_N1ZZ; wil::details::in1diag5::Log_HrIfMsg(void *,uint,char const *,char const *,char const *,long,bool,char const *,...)
0x180019cdc  add     dword ptr [rbx+98h], 0FFFFFFFFh
0x180019ce3  jnz     short loc_180019CF6
0x180019ce5  mov     r8, rbx
0x180019ce8  lea     rdx, [rsp+130h+var_F0]
0x180019ced  lea     rcx, [rdi+68h]
0x180019cf1  call    ?erase@?$list@UAccessTokenItem@@V?$allocator@UAccessTokenItem@@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@UAccessTokenItem@@@std@@@std@@@2@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@UAccessTokenItem@@@std@@@std@@@2@@Z; std::list<AccessTokenItem>::erase(std::_List_const_iterator<std::_List_val<std::_List_simple_types<AccessTokenItem>>>)
0x180019cf6  lea     rcx, [rdi+40h]; lpCriticalSection
0x180019cfa  call    cs:__imp_LeaveCriticalSection
0x180019d00  lea     rcx, [rsp+130h+var_C0]; this
0x180019d05  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x180019d0a  lea     rcx, [rsp+130h+var_E8]; this
0x180019d0f  mov     [rsp+130h+var_E8], r14
0x180019d14  call    ?Clear@CAccessToken@ATL@@MEAAXXZ; ATL::CAccessToken::Clear(void)
0x180019d19  call    cs:__imp_CoRevertToSelf
0x180019d1f  xor     eax, eax
0x180019d21  jmp     loc_180019C1B
0x180019d26  mov     rcx, [rbp+38h]; this
0x180019d2a  lea     rax, aWilVerifyBoolT; "!(wil::verify_bool(token.GetUser(&userS"...
0x180019d31  lea     r9, aClocationuserh_1; "CLocationUserHandles::RemoveCurrentUser"
0x180019d38  mov     [rsp+130h+var_110], rax; char *
0x180019d3d  lea     r8, aOnecoreuapDriv_40; "onecoreuap\\drivers\\mobilepc\\location"...
0x180019d44  mov     edx, 51h ; 'Q'; void *
0x180019d49  call    ?Return_GetLastError@in1diag5@details@wil@@YAJPEAXIPEBD11@Z; wil::details::in1diag5::Return_GetLastError(void *,uint,char const *,char const *,char const *)
0x180019d4e  lea     rcx, [rsp+130h+var_C0]; this
0x180019d53  mov     ebx, eax
0x180019d55  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x180019d5a  jmp     short loc_180019D86
0x180019d5c  mov     rcx, [rbp+38h]; this
0x180019d60  lea     rax, aWilVerifyBoolT_0; "!(wil::verify_bool(token.GetEffectiveTo"...
0x180019d67  lea     r9, aClocationuserh_1; "CLocationUserHandles::RemoveCurrentUser"
0x180019d6e  mov     [rsp+130h+var_110], rax; char *
0x180019d73  lea     r8, aOnecoreuapDriv_40; "onecoreuap\\drivers\\mobilepc\\location"...
0x180019d7a  mov     edx, 4Eh ; 'N'; void *
0x180019d7f  call    ?Return_GetLastError@in1diag5@details@wil@@YAJPEAXIPEBD11@Z; wil::details::in1diag5::Return_GetLastError(void *,uint,char const *,char const *,char const *)
0x180019d84  mov     ebx, eax
0x180019d86  lea     rcx, [rsp+130h+var_E8]; this
0x180019d8b  mov     [rsp+130h+var_E8], r14
0x180019d90  call    ?Clear@CAccessToken@ATL@@MEAAXXZ; ATL::CAccessToken::Clear(void)
0x180019d95  call    cs:__imp_CoRevertToSelf
0x180019d9b  jmp     loc_180019C19
0x180019da0  xorps   xmm0, xmm0
0x180019da3  mov     [rsp+130h+var_D0], 0
0x180019dac  lea     r14, ??_7CAccessToken@ATL@@6B@; const ATL::CAccessToken::`vftable'
0x180019db3  mov     edx, 2000Eh; unsigned int
0x180019db8  lea     rcx, [rsp+130h+var_E8]; this
0x180019dbd  mov     [rsp+130h+var_E8], r14
0x180019dc2  movdqu  [rsp+130h+var_E0], xmm0
0x180019dc8  call    ?GetEffectiveToken@CAccessToken@ATL@@QEAA_NK@Z; ATL::CAccessToken::GetEffectiveToken(ulong)
0x180019dcd  test    al, al
0x180019dcf  jz      short loc_180019D5C
0x180019dd1  jmp     loc_180019C37
```
