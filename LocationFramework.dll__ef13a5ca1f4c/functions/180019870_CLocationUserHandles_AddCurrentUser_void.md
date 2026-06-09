# CLocationUserHandles::AddCurrentUser(void)

- ea: `0x180019870`
- end: `0x180019ba4`
- name: `?AddCurrentUser@CLocationUserHandles@@UEAAJXZ`
- size: `820`
- prototype: `__int64 __fastcall(CLocationUserHandles *__hidden this)`
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180012194`
- `0x180018228`
- `0x180019870`
- `0x18001e170`
- `0x18001efe0`
- `0x18001f09c`
- `0x18001f334`
- `0x180050b54`
- `0x180084ac8`
- `0x18009c310`
- `0x1800a98c0`
- `0x1800aa5ac`
- `0x1800d3cb8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019aea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019aea`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800199bb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800199bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800199eb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800199f9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800199eb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800199f9`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180019a25`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180019a25`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180019a92`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180019a92`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800199a1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800199a1`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18001989f`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18001989f`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180019a7f`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180019b08`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180019a7f`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180019b08`

## string_xrefs

- `0x1800198c8`: `impersonate.Status()`
- `0x180019b48`: `!(wil::verify_bool(token.GetEffectiveToken((0x00020000L) | (0x0008) | (0x0004) | (0x0002))))`
- `0x180019b15`: `!(wil::verify_bool(token.GetStatistics(&tokenStatistics)))`
- `0x180019b73`: `!(wil::verify_bool(token.GetUser(&userSid)))`
- `0x180019a37`: `!(wil::verify_bool(DuplicateHandle( GetCurrentProcess(), token.GetHandle(), GetCurrentProcess(), &duplicatedHandle, 0, 0, 0x00000002)))`

## pseudocode

```c
__int64 __fastcall CLocationUserHandles::AddCurrentUser(CLocationUserHandles *this)
{
  HRESULT v2; // eax
  unsigned int LastError; // ebx
  __int64 *v5; // rbx
  HANDLE CurrentProcess; // rax
  HANDLE v7; // rdi
  void *v8; // rbx
  HANDLE v9; // rax
  const char *v10; // rax
  __int64 v11; // rdx
  wil::details *bInheritHandle; // [rsp+28h] [rbp-D8h]
  const char *bInheritHandlea; // [rsp+28h] [rbp-D8h]
  DWORD dwOptions; // [rsp+30h] [rbp-D0h]
  char *v15; // [rsp+40h] [rbp-C0h] BYREF
  char v16; // [rsp+48h] [rbp-B8h]
  HANDLE TargetHandle; // [rsp+50h] [rbp-B0h] BYREF
  DWORD ReturnLength; // [rsp+58h] [rbp-A8h] BYREF
  void **v19; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE TokenHandle[2]; // [rsp+68h] [rbp-98h]
  __int64 v21; // [rsp+78h] [rbp-88h]
  _OWORD TokenInformation[3]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v23; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v24[8]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE pSid2[120]; // [rsp+C8h] [rbp-38h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+178h] [rbp+78h]

  v2 = CoImpersonateClient();
  LastError = v2;
  if ( v2 < 0 )
  {
    if ( v2 != -2147417833 )
    {
      LODWORD(bInheritHandle) = v2;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)0x10,
        (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\framework\\locationuserhandles.cpp",
        "CLocationUserHandles::AddCurrentUser",
        "impersonate.Status()",
        bInheritHandle,
        dwOptions);
    }
    return LastError;
  }
  v21 = 0;
  v19 = &ATL::CAccessToken::`vftable';
  *(_OWORD *)TokenHandle = 0;
  if ( !ATL::CAccessToken::GetEffectiveToken((ATL::CAccessToken *)&v19, 0x2000Eu) )
  {
    LastError = wil::details::in1diag5::Return_GetLastError(
                  retaddr,
                  (void *)0x14,
                  (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\framework\\locationuserhandles.cpp",
                  "CLocationUserHandles::AddCurrentUser",
                  "!(wil::verify_bool(token.GetEffectiveToken((0x00020000L) | (0x0008) | (0x0004) | (0x0002))))",
                  (const char *)bInheritHandle);
LABEL_13:
    v19 = &ATL::CAccessToken::`vftable';
    ATL::CAccessToken::Clear((ATL::CAccessToken *)&v19);
    CoRevertToSelf();
    return LastError;
  }
  memset_0(v24, 0, 0x78u);
  ATL::CSid::CSid((ATL::CSid *)v24);
  if ( !ATL::CAccessToken::GetInfoConvert<ATL::CSid,_TOKEN_USER>((__int64)&v19, (__int64)v24) )
  {
    v10 = "!(wil::verify_bool(token.GetUser(&userSid)))";
    v11 = 23;
LABEL_20:
    LastError = wil::details::in1diag5::Return_GetLastError(
                  retaddr,
                  (void *)v11,
                  (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\framework\\locationuserhandles.cpp",
                  "CLocationUserHandles::AddCurrentUser",
                  v10,
                  (const char *)bInheritHandle);
LABEL_12:
    ATL::CSid::~CSid((ATL::CSid *)v24);
    goto LABEL_13;
  }
  v23 = 0;
  ReturnLength = 0;
  memset(TokenInformation, 0, sizeof(TokenInformation));
  if ( !GetTokenInformation(TokenHandle[0], TokenStatistics, TokenInformation, 0x38u, &ReturnLength) )
  {
    v10 = "!(wil::verify_bool(token.GetStatistics(&tokenStatistics)))";
    v11 = 27;
    goto LABEL_20;
  }
  v15 = (char *)this + 64;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  v5 = (__int64 *)*((_QWORD *)this + 13);
  v16 = 1;
  ReturnLength = 1;
  while ( 1 )
  {
    v5 = (__int64 *)*v5;
    if ( v5 == *((__int64 **)this + 13) )
      break;
    if ( EqualSid(v5 + 4, pSid2) )
    {
      if ( v23 == v5[18] )
      {
        ++*((_DWORD *)v5 + 38);
        goto LABEL_18;
      }
      ReturnLength = *((_DWORD *)v5 + 38) + 1;
      std::list<AccessTokenItem>::erase((char *)this + 104, &TargetHandle, v5);
      break;
    }
  }
  TargetHandle = 0;
  CurrentProcess = GetCurrentProcess();
  v7 = TokenHandle[0];
  v8 = CurrentProcess;
  v9 = GetCurrentProcess();
  if ( !DuplicateHandle(v9, v7, v8, &TargetHandle, 0, 0, 2u) )
  {
    LastError = wil::details::in1diag5::Return_GetLastError(
                  retaddr,
                  (void *)0x3E,
                  (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\framework\\locationuserhandles.cpp",
                  "CLocationUserHandles::AddCurrentUser",
                  "!(wil::verify_bool(DuplicateHandle( GetCurrentProcess(), token.GetHandle(), GetCurrentProcess(), &dupl"
                  "icatedHandle, 0, 0, 0x00000002)))",
                  bInheritHandlea);
    ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(&v15);
    goto LABEL_12;
  }
  std::list<AccessTokenItem>::emplace_front<void * &,ATL::CSid &,_LUID &,unsigned long &>(
    (_DWORD)this + 104,
    (unsigned int)&TargetHandle,
    (unsigned int)v24,
    (unsigned int)&v23,
    (__int64)&ReturnLength);
LABEL_18:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  ATL::CSid::~CSid((ATL::CSid *)v24);
  v19 = &ATL::CAccessToken::`vftable';
  ATL::CAccessToken::Clear((ATL::CAccessToken *)&v19);
  CoRevertToSelf();
  return 0;
}

```

## disassembly

```asm
0x180019870  mov     [rsp-8+arg_8], rbx
0x180019875  mov     [rsp-8+arg_10], rsi
0x18001987a  push    rbp
0x18001987b  push    rdi
0x18001987c  push    r12
0x18001987e  push    r13
0x180019880  push    r14
0x180019882  lea     rbp, [rsp-50h]
0x180019887  sub     rsp, 150h
0x18001988e  mov     rax, cs:__security_cookie
0x180019895  xor     rax, rsp
0x180019898  mov     [rbp+70h+var_30], rax
0x18001989c  mov     rsi, rcx
0x18001989f  call    cs:__imp_CoImpersonateClient
0x1800198a5  mov     ebx, eax
0x1800198a7  test    eax, eax
0x1800198a9  jns     short loc_180019908
0x1800198ab  cmp     eax, 80010117h
0x1800198b0  jz      short loc_1800198DE
0x1800198b2  mov     rcx, [rbp+78h]; this
0x1800198b6  lea     r9, aClocationuserh; "CLocationUserHandles::AddCurrentUser"
0x1800198bd  mov     dword ptr [rsp+170h+bInheritHandle], eax; wil::details *
0x1800198c1  lea     r8, aOnecoreuapDriv_40; "onecoreuap\\drivers\\mobilepc\\location"...
0x1800198c8  lea     rax, aImpersonateSta; "impersonate.Status()"
0x1800198cf  mov     edx, 10h; void *
0x1800198d4  mov     [rsp+170h+ReturnLength], rax; char *
0x1800198d9  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x1800198de  mov     eax, ebx
0x1800198e0  mov     rcx, [rbp+70h+var_30]
0x1800198e4  xor     rcx, rsp; StackCookie
0x1800198e7  call    __security_check_cookie
0x1800198ec  lea     r11, [rsp+170h+var_20]
0x1800198f4  mov     rbx, [r11+38h]
0x1800198f8  mov     rsi, [r11+40h]
0x1800198fc  mov     rsp, r11
0x1800198ff  pop     r14
0x180019901  pop     r13
0x180019903  pop     r12
0x180019905  pop     rdi
0x180019906  pop     rbp
0x180019907  retn
0x180019908  xorps   xmm0, xmm0
0x18001990b  mov     [rsp+170h+var_F8], 0
0x180019914  lea     r13, ??_7CAccessToken@ATL@@6B@; const ATL::CAccessToken::`vftable'
0x18001991b  mov     edx, 2000Eh; unsigned int
0x180019920  lea     rcx, [rsp+170h+var_110]; this
0x180019925  mov     [rsp+170h+var_110], r13
0x18001992a  movdqu  xmmword ptr [rsp+170h+TokenHandle], xmm0
0x180019930  call    ?GetEffectiveToken@CAccessToken@ATL@@QEAA_NK@Z; ATL::CAccessToken::GetEffectiveToken(ulong)
0x180019935  test    al, al
0x180019937  jz      loc_180019B44
0x18001993d  xor     edx, edx; Val
0x18001993f  lea     rcx, [rbp+70h+var_B0]; void *
0x180019943  lea     r8d, [rdx+78h]; Size
0x180019947  call    memset_0
0x18001994c  lea     rcx, [rbp+70h+var_B0]; this
0x180019950  call    ??0CSid@ATL@@QEAA@XZ; ATL::CSid::CSid(void)
0x180019955  lea     rdx, [rbp+70h+var_B0]
0x180019959  lea     rcx, [rsp+170h+var_110]
0x18001995e  call    ??$GetInfoConvert@VCSid@ATL@@U_TOKEN_USER@@@CAccessToken@ATL@@IEBA_NPEAVCSid@1@W4_TOKEN_INFORMATION_CLASS@@PEAU_TOKEN_USER@@@Z; ATL::CAccessToken::GetInfoConvert<ATL::CSid,_TOKEN_USER>(ATL::CSid *,_TOKEN_INFORMATION_CLASS,_TOKEN_USER *)
0x180019963  test    al, al
0x180019965  jz      loc_180019B73
0x18001996b  mov     rcx, [rsp+170h+TokenHandle]; TokenHandle
0x180019970  lea     r8, [rbp+70h+TokenInformation]; TokenInformation
0x180019974  xor     eax, eax
0x180019976  xorps   xmm0, xmm0
0x180019979  mov     r9d, 38h ; '8'; TokenInformationLength
0x18001997f  mov     [rbp+70h+var_C0], rax
0x180019983  mov     [rsp+170h+var_118], eax
0x180019987  lea     rax, [rsp+170h+var_118]
0x18001998c  movups  [rbp+70h+TokenInformation], xmm0
0x180019990  mov     [rsp+170h+ReturnLength], rax; ReturnLength
0x180019995  lea     edx, [r9-2Eh]; TokenInformationClass
0x180019999  movups  [rbp+70h+var_E0], xmm0
0x18001999d  movups  [rbp+70h+var_D0], xmm0
0x1800199a1  call    cs:__imp_GetTokenInformation
0x1800199a7  test    eax, eax
0x1800199a9  jz      loc_180019B15
0x1800199af  lea     r14, [rsi+40h]
0x1800199b3  mov     rcx, r14; lpCriticalSection
0x1800199b6  mov     [rsp+170h+var_130], r14
0x1800199bb  call    cs:__imp_EnterCriticalSection
0x1800199c1  mov     rbx, [rsi+68h]
0x1800199c5  mov     r12d, 1
0x1800199cb  mov     [rsp+170h+var_128], r12b
0x1800199d0  mov     [rsp+170h+var_118], r12d
0x1800199d5  mov     rbx, [rbx]
0x1800199d8  cmp     rbx, [rsi+68h]
0x1800199dc  jnz     loc_180019A8A
0x1800199e2  mov     [rsp+170h+TargetHandle], 0
0x1800199eb  call    cs:__imp_GetCurrentProcess
0x1800199f1  mov     rdi, [rsp+170h+TokenHandle]
0x1800199f6  mov     rbx, rax
0x1800199f9  call    cs:__imp_GetCurrentProcess
0x1800199ff  mov     [rsp+170h+dwOptions], 2; dwOptions
0x180019a07  lea     r9, [rsp+170h+TargetHandle]; lpTargetHandle
0x180019a0c  mov     rcx, rax; hSourceProcessHandle
0x180019a0f  mov     dword ptr [rsp+170h+bInheritHandle], 0; char *
0x180019a17  mov     r8, rbx; hTargetProcessHandle
0x180019a1a  mov     dword ptr [rsp+170h+ReturnLength], 0; dwDesiredAccess
0x180019a22  mov     rdx, rdi; hSourceHandle
0x180019a25  call    cs:__imp_DuplicateHandle
0x180019a2b  test    eax, eax
0x180019a2d  jnz     loc_180019AC7
0x180019a33  mov     rcx, [rbp+78h]; this
0x180019a37  lea     rax, aWilVerifyBoolD; "!(wil::verify_bool(DuplicateHandle( Get"...
0x180019a3e  lea     r9, aClocationuserh; "CLocationUserHandles::AddCurrentUser"
0x180019a45  mov     [rsp+170h+ReturnLength], rax; char *
0x180019a4a  lea     r8, aOnecoreuapDriv_40; "onecoreuap\\drivers\\mobilepc\\location"...
0x180019a51  mov     edx, 3Eh ; '>'; void *
0x180019a56  call    ?Return_GetLastError@in1diag5@details@wil@@YAJPEAXIPEBD11@Z; wil::details::in1diag5::Return_GetLastError(void *,uint,char const *,char const *,char const *)
0x180019a5b  lea     rcx, [rsp+170h+var_130]
0x180019a60  mov     ebx, eax
0x180019a62  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x180019a67  lea     rcx, [rbp+70h+var_B0]; this
0x180019a6b  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x180019a70  lea     rcx, [rsp+170h+var_110]; this
0x180019a75  mov     [rsp+170h+var_110], r13
0x180019a7a  call    ?Clear@CAccessToken@ATL@@MEAAXXZ; ATL::CAccessToken::Clear(void)
0x180019a7f  call    cs:__imp_CoRevertToSelf
0x180019a85  jmp     loc_1800198DE
0x180019a8a  lea     rcx, [rbx+20h]; pSid1
0x180019a8e  lea     rdx, [rbp+70h+pSid2]; pSid2
0x180019a92  call    cs:__imp_EqualSid
0x180019a98  test    eax, eax
0x180019a9a  jz      loc_1800199D5
0x180019aa0  mov     eax, [rbx+94h]
0x180019aa6  cmp     dword ptr [rbp+70h+var_C0+4], eax
0x180019aa9  jnz     loc_180019B81
0x180019aaf  mov     eax, [rbx+90h]
0x180019ab5  cmp     dword ptr [rbp+70h+var_C0], eax
0x180019ab8  jnz     loc_180019B81
0x180019abe  add     [rbx+98h], r12d
0x180019ac5  jmp     short loc_180019AE7
0x180019ac7  lea     rax, [rsp+170h+var_118]
0x180019acc  lea     r9, [rbp+70h+var_C0]
0x180019ad0  mov     [rsp+170h+ReturnLength], rax
0x180019ad5  lea     r8, [rbp+70h+var_B0]
0x180019ad9  lea     rdx, [rsp+170h+TargetHandle]
0x180019ade  lea     rcx, [rsi+68h]
0x180019ae2  call    ??$emplace_front@AEAPEAXAEAVCSid@ATL@@AEAU_LUID@@AEAK@?$list@UAccessTokenItem@@V?$allocator@UAccessTokenItem@@@std@@@std@@QEAAAEAUAccessTokenItem@@AEAPEAXAEAVCSid@ATL@@AEAU_LUID@@AEAK@Z; std::list<AccessTokenItem>::emplace_front<void * &,ATL::CSid &,_LUID &,ulong &>(void * &,ATL::CSid &,_LUID &,ulong &)
0x180019ae7  mov     rcx, r14; lpCriticalSection
0x180019aea  call    cs:__imp_LeaveCriticalSection
0x180019af0  lea     rcx, [rbp+70h+var_B0]; this
0x180019af4  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x180019af9  lea     rcx, [rsp+170h+var_110]; this
0x180019afe  mov     [rsp+170h+var_110], r13
0x180019b03  call    ?Clear@CAccessToken@ATL@@MEAAXXZ; ATL::CAccessToken::Clear(void)
0x180019b08  call    cs:__imp_CoRevertToSelf
0x180019b0e  xor     eax, eax
0x180019b10  jmp     loc_1800198E0
0x180019b15  lea     rax, aWilVerifyBoolT_1; "!(wil::verify_bool(token.GetStatistics("...
0x180019b1c  mov     edx, 1Bh; void *
0x180019b21  mov     rcx, [rbp+78h]; this
0x180019b25  lea     r9, aClocationuserh; "CLocationUserHandles::AddCurrentUser"
0x180019b2c  lea     r8, aOnecoreuapDriv_40; "onecoreuap\\drivers\\mobilepc\\location"...
0x180019b33  mov     [rsp+170h+ReturnLength], rax; char *
0x180019b38  call    ?Return_GetLastError@in1diag5@details@wil@@YAJPEAXIPEBD11@Z; wil::details::in1diag5::Return_GetLastError(void *,uint,char const *,char const *,char const *)
0x180019b3d  mov     ebx, eax
0x180019b3f  jmp     loc_180019A67
0x180019b44  mov     rcx, [rbp+78h]; this
0x180019b48  lea     rax, aWilVerifyBoolT_0; "!(wil::verify_bool(token.GetEffectiveTo"...
0x180019b4f  lea     r9, aClocationuserh; "CLocationUserHandles::AddCurrentUser"
0x180019b56  mov     [rsp+170h+ReturnLength], rax; char *
0x180019b5b  lea     r8, aOnecoreuapDriv_40; "onecoreuap\\drivers\\mobilepc\\location"...
0x180019b62  mov     edx, 14h; void *
0x180019b67  call    ?Return_GetLastError@in1diag5@details@wil@@YAJPEAXIPEBD11@Z; wil::details::in1diag5::Return_GetLastError(void *,uint,char const *,char const *,char const *)
0x180019b6c  mov     ebx, eax
0x180019b6e  jmp     loc_180019A70
0x180019b73  lea     rax, aWilVerifyBoolT; "!(wil::verify_bool(token.GetUser(&userS"...
0x180019b7a  mov     edx, 17h
0x180019b7f  jmp     short loc_180019B21
0x180019b81  mov     eax, [rbx+98h]
0x180019b87  lea     rdx, [rsp+170h+TargetHandle]
0x180019b8c  add     eax, r12d
0x180019b8f  lea     rcx, [rsi+68h]
0x180019b93  mov     r8, rbx
0x180019b96  mov     [rsp+170h+var_118], eax
0x180019b9a  call    ?erase@?$list@UAccessTokenItem@@V?$allocator@UAccessTokenItem@@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@UAccessTokenItem@@@std@@@std@@@2@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@UAccessTokenItem@@@std@@@std@@@2@@Z; std::list<AccessTokenItem>::erase(std::_List_const_iterator<std::_List_val<std::_List_simple_types<AccessTokenItem>>>)
0x180019b9f  jmp     loc_1800199E2
```
