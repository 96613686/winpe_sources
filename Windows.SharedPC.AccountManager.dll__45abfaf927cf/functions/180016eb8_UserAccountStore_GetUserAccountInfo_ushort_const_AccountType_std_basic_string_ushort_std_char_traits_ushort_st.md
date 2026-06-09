# UserAccountStore::GetUserAccountInfo(ushort const *,AccountType &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180016eb8`
- end: `0x1800170e5`
- name: `?GetUserAccountInfo@UserAccountStore@@AEAAXPEBGAEAW4AccountType@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `557`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180017a30`
- `0x180019500`

## callees

- `0x180003530`
- `0x180003fc0`
- `0x18000a1bc`
- `0x18000a548`
- `0x18000cd50`
- `0x18000cea0`
- `0x18001138c`
- `0x180011a6c`
- `0x180016eb8`
- `0x1800198b0`
- `0x180023228`
- `0x180023584`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180016f09`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180016f09`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180017087`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180017087`
- `api-ms-win-security-lsalookup-l1-1-2!LsaLookupUserAccountType` at `0x180016f3e`
- `api-ms-win-security-lsalookup-l1-1-2!LsaLookupUserAccountType` at `0x180016f3e`

## string_xrefs

- `0x180016f1a`: `shellcommon\shell\sharedpc\accountmanager\lib\accounts\useraccountstore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall UserAccountStore::GetUserAccountInfo(__int64 a1, const WCHAR *a2, int *a3, __int64 a4)
{
  const char *v7; // r9
  int v8; // eax
  void *v9; // rdx
  unsigned int v10; // r8d
  WCHAR *v11; // rcx
  char v12; // bl
  bool v13; // zf
  int v14; // eax
  __int64 v15; // rax
  int ReferencedDomainName; // [rsp+20h] [rbp-E0h]
  enum _SID_NAME_USE peUse; // [rsp+40h] [rbp-C0h] BYREF
  int v19; // [rsp+44h] [rbp-BCh] BYREF
  PSID Sid; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cchReferencedDomainName; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cchName; // [rsp+54h] [rbp-ACh] BYREF
  _BYTE v23[32]; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR v24[20]; // [rsp+78h] [rbp-88h] BYREF
  WCHAR Name[264]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2E8h] [rbp+1E8h]

  peUse = 0;
  *a3 = 0;
  Sid = 0;
  if ( !ConvertStringSidToSidW(a2, &Sid) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x137,
      (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\accounts\\useraccountstore.cpp",
      v7);
  v19 = 0;
  v8 = LsaLookupUserAccountType(Sid, &v19);
  if ( v8 < 0 )
    wil::details::in1diag3::_Log_NtStatus(retaddr, v9, v10, (const char *)(unsigned int)v8, ReferencedDomainName);
  if ( v19 != 1 )
  {
    if ( v19 == 2 || v19 == 3 )
    {
      *a3 = 3;
      return wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Sid);
    }
    if ( v19 != 5 )
      goto LABEL_23;
    std::wstring::wstring((__int64)v23, (__int64)a2);
    *a3 = 2 * (unsigned __int8)IsWCOSUserModelSpecialAccount(1, v23) + 2;
    v11 = (WCHAR *)v23;
    goto LABEL_18;
  }
  std::wstring::wstring((__int64)v24, (__int64)a2);
  v12 = 1;
  peUse = SidTypeUser;
  if ( (unsigned __int8)IsWCOSUserModelSpecialAccount(6, v24)
    || (std::wstring::wstring((__int64)v23, (__int64)a2),
        v12 = 3,
        peUse = SidTypeDomain,
        v13 = (unsigned __int8)IsCandidateUserSpecialAccount(v23) == 0,
        v14 = 1,
        !v13) )
  {
    v14 = 4;
  }
  *a3 = v14;
  if ( (v12 & 2) != 0 )
  {
    v12 &= ~2u;
    std::wstring::_Tidy_deallocate((__int64)v23);
  }
  if ( (v12 & 1) != 0 )
  {
    v11 = v24;
LABEL_18:
    std::wstring::_Tidy_deallocate((__int64)v11);
  }
  if ( *a3 == 1 )
  {
    memset_0(Name, 0, 0x202u);
    cchName = 257;
    peUse = 0;
    cchReferencedDomainName = 16;
    if ( !LookupAccountSidW(0, Sid, Name, &cchName, v24, &cchReferencedDomainName, &peUse) )
    {
      *a3 = 0;
      return wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Sid);
    }
    if ( peUse == SidTypeUser )
    {
      v15 = std::_WChar_traits<unsigned short>::length(Name);
      std::wstring::_Assign<unsigned short>(a4, Name, v15);
      return wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Sid);
    }
LABEL_23:
    *a3 = 4;
  }
  return wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Sid);
}

```

## disassembly

```asm
0x180016eb8  push    rbp
0x180016eba  push    rbx
0x180016ebb  push    rdi
0x180016ebc  push    r14
0x180016ebe  push    r15
0x180016ec0  lea     rbp, [rsp-1C0h]
0x180016ec8  sub     rsp, 2C0h
0x180016ecf  mov     rax, cs:__security_cookie
0x180016ed6  xor     rax, rsp
0x180016ed9  mov     [rbp+1E0h+var_30], rax
0x180016ee0  mov     r15, r9
0x180016ee3  mov     rdi, r8
0x180016ee6  mov     r14, rdx
0x180016ee9  mov     [rsp+2E0h+var_2A0], 0
0x180016ef1  mov     dword ptr [r8], 0
0x180016ef8  mov     [rsp+2E0h+Sid], 0
0x180016f01  lea     rdx, [rsp+2E0h+Sid]; Sid
0x180016f06  mov     rcx, r14; StringSid
0x180016f09  call    cs:__imp_ConvertStringSidToSidW
0x180016f0f  mov     rcx, [rbp+1E8h]; this
0x180016f16  test    eax, eax
0x180016f18  jnz     short loc_180016F2C
0x180016f1a  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\sharedpc\\accountma"...
0x180016f21  mov     edx, 137h; void *
0x180016f26  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180016f2c  mov     [rsp+2E0h+var_29C], 0
0x180016f34  lea     rdx, [rsp+2E0h+var_29C]
0x180016f39  mov     rcx, [rsp+2E0h+Sid]
0x180016f3e  call    cs:__imp_LsaLookupUserAccountType
0x180016f44  mov     rcx, [rbp+1E8h]; this
0x180016f4b  test    eax, eax
0x180016f4d  jns     short loc_180016F57
0x180016f4f  mov     r9d, eax; char *
0x180016f52  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x180016f57  mov     ecx, [rsp+2E0h+var_29C]
0x180016f5b  sub     ecx, 1
0x180016f5e  jz      short loc_180016FAE
0x180016f60  sub     ecx, 1
0x180016f63  jz      short loc_180016FA3
0x180016f65  sub     ecx, 1
0x180016f68  jz      short loc_180016FA3
0x180016f6a  cmp     ecx, 2
0x180016f6d  jnz     loc_18001709C
0x180016f73  mov     rdx, r14
0x180016f76  lea     rcx, [rsp+2E0h+var_288]
0x180016f7b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180016f80  nop
0x180016f81  lea     rdx, [rsp+2E0h+var_288]
0x180016f86  mov     ecx, 1
0x180016f8b  call    ?IsWCOSUserModelSpecialAccount@@YA_NW4SpecialAccountTypes@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; IsWCOSUserModelSpecialAccount(SpecialAccountTypes,std::wstring const &)
0x180016f90  movzx   eax, al
0x180016f93  lea     eax, ds:2[rax*2]
0x180016f9a  mov     [rdi], eax
0x180016f9c  lea     rcx, [rsp+2E0h+var_288]
0x180016fa1  jmp     short loc_180017022
0x180016fa3  mov     dword ptr [rdi], 3
0x180016fa9  jmp     loc_1800170BD
0x180016fae  mov     rdx, r14
0x180016fb1  lea     rcx, [rsp+2E0h+var_268]
0x180016fb6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180016fbb  nop
0x180016fbc  mov     ebx, 1
0x180016fc1  mov     [rsp+2E0h+var_2A0], ebx
0x180016fc5  lea     rdx, [rsp+2E0h+var_268]
0x180016fca  lea     ecx, [rbx+5]
0x180016fcd  call    ?IsWCOSUserModelSpecialAccount@@YA_NW4SpecialAccountTypes@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; IsWCOSUserModelSpecialAccount(SpecialAccountTypes,std::wstring const &)
0x180016fd2  test    al, al
0x180016fd4  jnz     short loc_180016FFE
0x180016fd6  mov     rdx, r14
0x180016fd9  lea     rcx, [rsp+2E0h+var_288]
0x180016fde  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180016fe3  nop
0x180016fe4  mov     ebx, 3
0x180016fe9  mov     [rsp+2E0h+var_2A0], ebx
0x180016fed  lea     rcx, [rsp+2E0h+var_288]
0x180016ff2  call    ?IsCandidateUserSpecialAccount@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; IsCandidateUserSpecialAccount(std::wstring const &)
0x180016ff7  test    al, al
0x180016ff9  lea     eax, [rbx-2]
0x180016ffc  jz      short loc_180017003
0x180016ffe  mov     eax, 4
0x180017003  mov     [rdi], eax
0x180017005  test    bl, 2
0x180017008  jz      short loc_180017018
0x18001700a  and     ebx, 0FFFFFFFDh
0x18001700d  lea     rcx, [rsp+2E0h+var_288]
0x180017012  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180017017  nop
0x180017018  test    bl, 1
0x18001701b  jz      short loc_180017027
0x18001701d  lea     rcx, [rsp+2E0h+var_268]
0x180017022  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180017027  cmp     dword ptr [rdi], 1
0x18001702a  jnz     loc_1800170BD
0x180017030  xor     edx, edx; Val
0x180017032  mov     r8d, 202h; Size
0x180017038  lea     rcx, [rbp+1E0h+Name]; void *
0x18001703c  call    memset_0
0x180017041  mov     [rsp+2E0h+cchName], 101h
0x180017049  mov     [rsp+2E0h+var_2A0], 0
0x180017051  mov     [rsp+2E0h+var_290], 10h
0x180017059  lea     rax, [rsp+2E0h+var_2A0]
0x18001705e  mov     [rsp+2E0h+peUse], rax; peUse
0x180017063  lea     rax, [rsp+2E0h+var_290]
0x180017068  mov     [rsp+2E0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18001706d  lea     rax, [rsp+2E0h+var_268]
0x180017072  mov     [rsp+2E0h+ReferencedDomainName], rax; ReferencedDomainName
0x180017077  lea     r9, [rsp+2E0h+cchName]; cchName
0x18001707c  lea     r8, [rbp+1E0h+Name]; Name
0x180017080  mov     rdx, [rsp+2E0h+Sid]; Sid
0x180017085  xor     ecx, ecx; lpSystemName
0x180017087  call    cs:__imp_LookupAccountSidW
0x18001708d  test    eax, eax
0x18001708f  jnz     short loc_180017095
0x180017091  mov     [rdi], eax
0x180017093  jmp     short loc_1800170BD
0x180017095  cmp     [rsp+2E0h+var_2A0], 1
0x18001709a  jz      short loc_1800170A4
0x18001709c  mov     dword ptr [rdi], 4
0x1800170a2  jmp     short loc_1800170BD
0x1800170a4  lea     rcx, [rbp+1E0h+Name]
0x1800170a8  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x1800170ad  mov     r8, rax
0x1800170b0  lea     rdx, [rbp+1E0h+Name]
0x1800170b4  mov     rcx, r15
0x1800170b7  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800170bc  nop
0x1800170bd  lea     rcx, [rsp+2E0h+Sid]
0x1800170c2  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800170c7  mov     rcx, [rbp+1E0h+var_30]
0x1800170ce  xor     rcx, rsp; StackCookie
0x1800170d1  call    __security_check_cookie
0x1800170d6  add     rsp, 2C0h
0x1800170dd  pop     r15
0x1800170df  pop     r14
0x1800170e1  pop     rdi
0x1800170e2  pop     rbx
0x1800170e3  pop     rbp
0x1800170e4  retn
```
