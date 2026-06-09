# CFilterPoolBase::Init(wchar_t const *)

- ea: `0x18019e76c`
- end: `0x18019ea77`
- name: `?Init@CFilterPoolBase@@QEAAJPEB_W@Z`
- size: `779`
- prototype: `int(CFilterPoolBase *__hidden this, const wchar_t *)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800195b8`
- `0x18017d66c`

## callees

- `0x180022710`
- `0x180026b58`
- `0x18002751c`
- `0x180056610`
- `0x18008dafc`
- `0x1800e2374`
- `0x1801249ec`
- `0x18019e76c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019e87c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019e87c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18019e832`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18019e832`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18019e844`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18019e844`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18019ea02`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18019ea02`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18019e816`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18019ea16`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18019e816`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18019ea16`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18019e9a7`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18019e9a7`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18019ea34`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18019ea34`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18019e9ce`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18019e9f6`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18019e9ce`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18019e9f6`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18019e8d7`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18019e939`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18019e970`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18019e8d7`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18019e939`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18019e970`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18019e924`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18019e924`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18019e876`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18019e8bf`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18019e876`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18019e8bf`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18019e95e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18019e95e`

## pseudocode

```c
__int64 __fastcall CFilterPoolBase::Init(CFilterPoolBase *this, const wchar_t *a2)
{
  __int64 result; // rax
  HANDLE CurrentProcess; // rax
  DWORD v6; // r14d
  void *v7; // rax
  DWORD LengthSid; // ebx
  void *v9; // rax
  DWORD v10; // eax
  bool v11; // zf
  DWORD v12; // ebx
  struct _ACL *v13; // rax
  BOOL v14; // ebx
  int ReturnLength; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+28h]
  DWORD TokenInformationLength; // [rsp+60h] [rbp+30h] BYREF
  PSID Sid; // [rsp+70h] [rbp+40h] BYREF
  void *TokenHandle; // [rsp+78h] [rbp+48h] BYREF

  CEventSem::Set((CFilterPoolBase *)((char *)this + 512));
  CEventSem::Set((CFilterPoolBase *)((char *)this + 520));
  CEventSem::Set((CFilterPoolBase *)((char *)this + 528));
  CEventSem::Set((CFilterPoolBase *)((char *)this + 536));
  TokenInformationLength = 0;
  CLMString::operator=((char *)this + 48, L"Global\\UsGthrFltPipe");
  CLMString::Append((CFilterPoolBase *)((char *)this + 48), a2, 0xFFFFFFFF);
  CLMString::operator=((char *)this + 208, L"Global\\UsGthrCtrlFltPipe");
  CLMString::Append((CFilterPoolBase *)((char *)this + 208), a2, 0xFFFFFFFF);
  if ( !InitializeSecurityDescriptor((char *)this + 576, 1u) )
    return ResultFromLastError();
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
    return ResultFromLastError();
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    (char *)this + 560,
    TokenHandle);
  GetTokenInformation(*((HANDLE *)this + 70), TokenUser, 0, 0, &TokenInformationLength);
  if ( GetLastError() != 122 )
    return ResultFromLastError();
  v6 = TokenInformationLength;
  v7 = operator new[](TokenInformationLength, (const struct std::nothrow_t *)&std::nothrow);
  *((_QWORD *)this + 68) = v7;
  if ( v7 )
  {
    if ( !GetTokenInformation(*((HANDLE *)this + 70), TokenUser, v7, v6, &TokenInformationLength) )
      return ResultFromLastError();
    LengthSid = GetLengthSid(**((PSID **)this + 68));
    v9 = operator new[](LengthSid, (const struct std::nothrow_t *)&std::nothrow);
    *((_QWORD *)this + 69) = v9;
    if ( !v9 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x7A3,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\fltrpool.cxx",
        (const char *)0x8007000ELL,
        ReturnLength);
    if ( !CopySid(LengthSid, v9, **((PSID **)this + 68)) )
      return ResultFromLastError();
    v10 = GetLengthSid(*((PSID *)this + 69));
    v11 = *((_DWORD *)this + 177) == 0;
    Sid = 0;
    v12 = v10 + 16;
    if ( !v11 )
    {
      if ( !ConvertStringSidToSidW(*((LPCWSTR *)this + 87), &Sid) )
        return ResultFromLastError();
      v12 += GetLengthSid(Sid) + 8;
    }
    v13 = (struct _ACL *)operator new[](v12, (const struct std::nothrow_t *)&std::nothrow);
    *((_QWORD *)this + 71) = v13;
    if ( v13 )
    {
      if ( InitializeAcl(v13, v12, 2u) )
      {
        if ( AddAccessAllowedAce(*((PACL *)this + 71), 2u, 0x1F01FFu, *((PSID *)this + 69)) )
        {
          if ( !*((_DWORD *)this + 177)
            || (v14 = AddAccessAllowedAce(*((PACL *)this + 71), 2u, 0x1F01FFu, Sid), LocalFree(Sid), v14) )
          {
            if ( InitializeSecurityDescriptor((char *)this + 576, 1u)
              && SetSecurityDescriptorDacl((char *)this + 576, 1, *((PACL *)this + 71), 0) )
            {
              *((_DWORD *)this + 154) = 24;
              result = 0;
              *((_QWORD *)this + 78) = (char *)this + 576;
              *((_DWORD *)this + 158) = 0;
              return result;
            }
          }
        }
      }
      return ResultFromLastError();
    }
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x18019e76c  mov     [rsp-28h+arg_8], rbx
0x18019e771  push    rbp
0x18019e772  push    rsi
0x18019e773  push    rdi
0x18019e774  push    r13
0x18019e776  push    r14
0x18019e778  mov     rbp, rsp
0x18019e77b  sub     rsp, 30h
0x18019e77f  mov     rsi, rcx
0x18019e782  mov     rdi, rdx
0x18019e785  add     rcx, 200h; this
0x18019e78c  call    ?Set@CEventSem@@QEAAXXZ; CEventSem::Set(void)
0x18019e791  lea     rcx, [rsi+208h]; this
0x18019e798  call    ?Set@CEventSem@@QEAAXXZ; CEventSem::Set(void)
0x18019e79d  lea     rcx, [rsi+210h]; this
0x18019e7a4  call    ?Set@CEventSem@@QEAAXXZ; CEventSem::Set(void)
0x18019e7a9  lea     rcx, [rsi+218h]; this
0x18019e7b0  call    ?Set@CEventSem@@QEAAXXZ; CEventSem::Set(void)
0x18019e7b5  lea     rdx, aGlobalUsgthrfl; "Global\\UsGthrFltPipe"
0x18019e7bc  mov     [rbp+TokenInformationLength], 0
0x18019e7c3  lea     rcx, [rsi+30h]
0x18019e7c7  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x18019e7cc  or      r14d, 0FFFFFFFFh
0x18019e7d0  lea     rcx, [rsi+30h]; this
0x18019e7d4  mov     r8d, r14d; unsigned int
0x18019e7d7  mov     rdx, rdi; wchar_t *
0x18019e7da  call    ?Append@CLMString@@QEAAHPEB_WI@Z; CLMString::Append(wchar_t const *,uint)
0x18019e7df  lea     rbx, [rsi+0D0h]
0x18019e7e6  mov     rcx, rbx
0x18019e7e9  lea     rdx, aGlobalUsgthrct; "Global\\UsGthrCtrlFltPipe"
0x18019e7f0  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x18019e7f5  mov     r8d, r14d; unsigned int
0x18019e7f8  mov     rdx, rdi; wchar_t *
0x18019e7fb  mov     rcx, rbx; this
0x18019e7fe  call    ?Append@CLMString@@QEAAHPEB_WI@Z; CLMString::Append(wchar_t const *,uint)
0x18019e803  lea     rdi, [rsi+240h]
0x18019e80a  mov     r13d, 1
0x18019e810  mov     edx, r13d; dwRevision
0x18019e813  mov     rcx, rdi; pSecurityDescriptor
0x18019e816  call    cs:__imp_InitializeSecurityDescriptor
0x18019e81c  test    eax, eax
0x18019e81e  jnz     short loc_18019E82A
0x18019e820  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18019e825  jmp     loc_18019EA66
0x18019e82a  mov     [rbp+TokenHandle], 0
0x18019e832  call    cs:__imp_GetCurrentProcess
0x18019e838  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18019e83c  mov     edx, 8; DesiredAccess
0x18019e841  mov     rcx, rax; ProcessHandle
0x18019e844  call    cs:__imp_OpenProcessToken
0x18019e84a  test    eax, eax
0x18019e84c  jz      short loc_18019E820
0x18019e84e  mov     rdx, [rbp+TokenHandle]
0x18019e852  lea     rbx, [rsi+230h]
0x18019e859  mov     rcx, rbx
0x18019e85c  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18019e861  mov     rcx, [rbx]; TokenHandle
0x18019e864  lea     rax, [rbp+TokenInformationLength]
0x18019e868  xor     r9d, r9d; TokenInformationLength
0x18019e86b  mov     qword ptr [rsp+30h+ReturnLength], rax; ReturnLength
0x18019e870  xor     r8d, r8d; TokenInformation
0x18019e873  mov     edx, r13d; TokenInformationClass
0x18019e876  call    cs:__imp_GetTokenInformation
0x18019e87c  call    cs:__imp_GetLastError
0x18019e882  cmp     eax, 7Ah ; 'z'
0x18019e885  jnz     short loc_18019E820
0x18019e887  mov     r14d, [rbp+TokenInformationLength]
0x18019e88b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18019e892  mov     ecx, r14d; unsigned __int64
0x18019e895  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18019e89a  mov     [rsi+220h], rax
0x18019e8a1  test    rax, rax
0x18019e8a4  jz      loc_18019EA61
0x18019e8aa  lea     rcx, [rbp+TokenInformationLength]
0x18019e8ae  mov     r9d, r14d; TokenInformationLength
0x18019e8b1  mov     qword ptr [rsp+30h+ReturnLength], rcx; int
0x18019e8b6  mov     r8, rax; TokenInformation
0x18019e8b9  mov     rcx, [rbx]; TokenHandle
0x18019e8bc  mov     edx, r13d; TokenInformationClass
0x18019e8bf  call    cs:__imp_GetTokenInformation
0x18019e8c5  test    eax, eax
0x18019e8c7  jz      loc_18019E820
0x18019e8cd  mov     rcx, [rsi+220h]
0x18019e8d4  mov     rcx, [rcx]; pSid
0x18019e8d7  call    cs:__imp_GetLengthSid
0x18019e8dd  mov     ecx, eax; unsigned __int64
0x18019e8df  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18019e8e6  mov     ebx, eax
0x18019e8e8  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18019e8ed  mov     [rsi+228h], rax
0x18019e8f4  test    rax, rax
0x18019e8f7  jnz     short loc_18019E915
0x18019e8f9  mov     rcx, [rbp+28h]; this
0x18019e8fd  lea     r8, aOnecoreuapBase_245; "onecoreuap\\base\\appmodel\\search\\mss"...
0x18019e904  mov     r9d, 8007000Eh; char *
0x18019e90a  mov     edx, 7A3h; void *
0x18019e90f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18019e915  mov     r8, [rsi+220h]
0x18019e91c  mov     rdx, rax; pDestinationSid
0x18019e91f  mov     ecx, ebx; nDestinationSidLength
0x18019e921  mov     r8, [r8]; pSourceSid
0x18019e924  call    cs:__imp_CopySid
0x18019e92a  test    eax, eax
0x18019e92c  jz      loc_18019E820
0x18019e932  mov     rcx, [rsi+228h]; pSid
0x18019e939  call    cs:__imp_GetLengthSid
0x18019e93f  cmp     dword ptr [rsi+2C4h], 0
0x18019e946  mov     [rbp+Sid], 0
0x18019e94e  lea     ebx, [rax+10h]
0x18019e951  jbe     short loc_18019E97B
0x18019e953  mov     rcx, [rsi+2B8h]; StringSid
0x18019e95a  lea     rdx, [rbp+Sid]; Sid
0x18019e95e  call    cs:__imp_ConvertStringSidToSidW
0x18019e964  test    eax, eax
0x18019e966  jz      loc_18019E820
0x18019e96c  mov     rcx, [rbp+Sid]; pSid
0x18019e970  call    cs:__imp_GetLengthSid
0x18019e976  add     ebx, 8
0x18019e979  add     ebx, eax
0x18019e97b  mov     ecx, ebx; unsigned __int64
0x18019e97d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18019e984  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18019e989  mov     [rsi+238h], rax
0x18019e990  test    rax, rax
0x18019e993  jz      loc_18019EA61
0x18019e999  mov     r14d, 2
0x18019e99f  mov     edx, ebx; nAclLength
0x18019e9a1  mov     r8d, r14d; dwAclRevision
0x18019e9a4  mov     rcx, rax; pAcl
0x18019e9a7  call    cs:__imp_InitializeAcl
0x18019e9ad  test    eax, eax
0x18019e9af  jz      loc_18019E820
0x18019e9b5  mov     r9, [rsi+228h]; pSid
0x18019e9bc  mov     ebx, 1F01FFh
0x18019e9c1  mov     rcx, [rsi+238h]; pAcl
0x18019e9c8  mov     r8d, ebx; AccessMask
0x18019e9cb  mov     edx, r14d; dwAceRevision
0x18019e9ce  call    cs:__imp_AddAccessAllowedAce
0x18019e9d4  test    eax, eax
0x18019e9d6  jz      loc_18019E820
0x18019e9dc  cmp     dword ptr [rsi+2C4h], 0
0x18019e9e3  jbe     short loc_18019EA10
0x18019e9e5  mov     r9, [rbp+Sid]; pSid
0x18019e9e9  mov     r8d, ebx; AccessMask
0x18019e9ec  mov     rcx, [rsi+238h]; pAcl
0x18019e9f3  mov     edx, r14d; dwAceRevision
0x18019e9f6  call    cs:__imp_AddAccessAllowedAce
0x18019e9fc  mov     rcx, [rbp+Sid]; hMem
0x18019ea00  mov     ebx, eax
0x18019ea02  call    cs:__imp_LocalFree
0x18019ea08  test    ebx, ebx
0x18019ea0a  jz      loc_18019E820
0x18019ea10  mov     edx, r13d; dwRevision
0x18019ea13  mov     rcx, rdi; pSecurityDescriptor
0x18019ea16  call    cs:__imp_InitializeSecurityDescriptor
0x18019ea1c  test    eax, eax
0x18019ea1e  jz      loc_18019E820
0x18019ea24  mov     r8, [rsi+238h]; pDacl
0x18019ea2b  xor     r9d, r9d; bDaclDefaulted
0x18019ea2e  mov     edx, r13d; bDaclPresent
0x18019ea31  mov     rcx, rdi; pSecurityDescriptor
0x18019ea34  call    cs:__imp_SetSecurityDescriptorDacl
0x18019ea3a  test    eax, eax
0x18019ea3c  jz      loc_18019E820
0x18019ea42  mov     dword ptr [rsi+268h], 18h
0x18019ea4c  xor     eax, eax
0x18019ea4e  mov     [rsi+270h], rdi
0x18019ea55  mov     dword ptr [rsi+278h], 0
0x18019ea5f  jmp     short loc_18019EA66
0x18019ea61  mov     eax, 8007000Eh
0x18019ea66  mov     rbx, [rsp+30h+arg_8]
0x18019ea6b  add     rsp, 30h
0x18019ea6f  pop     r14
0x18019ea71  pop     r13
0x18019ea73  pop     rdi
0x18019ea74  pop     rsi
0x18019ea75  pop     rbp
0x18019ea76  retn
```
