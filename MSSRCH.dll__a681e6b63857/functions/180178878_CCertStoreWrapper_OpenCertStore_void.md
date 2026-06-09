# CCertStoreWrapper::OpenCertStore(void *)

- ea: `0x180178878`
- end: `0x180178a9e`
- name: `?OpenCertStore@CCertStoreWrapper@@QEAAJPEAX@Z`
- size: `550`
- prototype: `int(CCertStoreWrapper *__hidden this, void *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180178cf0`

## callees

- `0x18000ee60`
- `0x18000f880`
- `0x180026b58`
- `0x1800cae14`
- `0x1800e95f0`
- `0x1800eb1b0`
- `0x1800f8f24`
- `0x1801249ec`
- `0x180178728`
- `0x180178878`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801788c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801788c6`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1801789f3`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180178a25`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180178a64`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1801789f3`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180178a25`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180178a64`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1801788bc`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180178947`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1801788bc`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180178947`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180178987`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180178987`
- `CRYPT32!CertOpenStore` at `0x1801789ce`
- `CRYPT32!CertOpenStore` at `0x1801789ce`

## string_xrefs

- `0x180178a02`: `onecoreuap\base\appmodel\Search\common\include\smartcls_common.hxx`
- `0x180178a34`: `onecoreuap\base\appmodel\Search\common\include\smartcls_common.hxx`
- `0x180178a73`: `onecoreuap\base\appmodel\Search\common\include\smartcls_common.hxx`
- `0x1801788d6`: `onecoreuap\base\appmodel\search\mssrch\gather\gthrsvc\certstoremonitorthread.cxx`
- `0x180178919`: `onecoreuap\base\appmodel\search\mssrch\gather\gthrsvc\certstoremonitorthread.cxx`
- `0x180178954`: `onecoreuap\base\appmodel\search\mssrch\gather\gthrsvc\certstoremonitorthread.cxx`
- `0x1801789e2`: `onecoreuap\base\appmodel\search\mssrch\gather\gthrsvc\certstoremonitorthread.cxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CCertStoreWrapper::OpenCertStore(CCertStoreWrapper *this, void *a2)
{
  const char *v4; // r9
  PSID *v6; // rbx
  unsigned int LastError; // ebx
  const char *v8; // r9
  __int64 v9; // rdx
  BOOL v10; // ebx
  CSmartImpersonator *v11; // rcx
  HCERTSTORE v12; // rax
  const char *v13; // r9
  const char *v14; // r9
  const char *v15; // r9
  int ReturnLength; // [rsp+20h] [rbp-48h]
  CCertStoreWrapper *v17; // [rsp+30h] [rbp-38h] BYREF
  LPWSTR StringSid; // [rsp+38h] [rbp-30h] BYREF
  char v19; // [rsp+40h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  DWORD TokenInformationLength; // [rsp+70h] [rbp+8h] BYREF
  __int64 v22; // [rsp+78h] [rbp+10h]
  PSID *v23; // [rsp+80h] [rbp+18h] BYREF

  if ( a2 == (void *)-1LL )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( *((_QWORD *)this + 1) )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  TokenInformationLength = 0;
  if ( !GetTokenInformation(a2, TokenUser, 0, 0, &TokenInformationLength) && GetLastError() != 122 )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x1A,
             (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\certstoremonitorthread.cxx",
             v4);
  v6 = (PSID *)operator new[](TokenInformationLength, (const struct std::nothrow_t *)&std::nothrow);
  v23 = v6;
  if ( !v6 )
  {
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\certstoremonitorthread.cxx",
      (const char *)0x8007000ELL,
      ReturnLength);
LABEL_18:
    std::unique_ptr<enum gsl::byte [0]>::~unique_ptr<enum gsl::byte [0]>(&v23);
    return LastError;
  }
  if ( !GetTokenInformation(a2, TokenUser, v6, TokenInformationLength, &TokenInformationLength) )
  {
    v9 = 35;
LABEL_12:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v9,
                  (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\certstoremonitorthread.cxx",
                  v8);
    goto LABEL_18;
  }
  v17 = this;
  StringSid = 0;
  v19 = 1;
  v10 = ConvertSidToStringSidW(*v6, &StringSid);
  wil::details::out_param_t<wistd::unique_ptr<wchar_t,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<wchar_t,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&v17);
  if ( !v10 )
  {
    v9 = 37;
    goto LABEL_12;
  }
  try
  {
    v22 = 0;
    CSmartImpersonator::ImpersonateLoggedOnUser(v11, a2);
    v12 = CertOpenStore((LPCSTR)0xA, 0, 0, 0x10000u, L"MY");
  }
  catch ( ... )
  {
    indexer::result::details::result_from_caught_exception<1>(
      retaddr,
      48,
      "onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\certstoremonitorthread.cxx");
  }
  *((_QWORD *)this + 1) = v12;
  if ( !v12 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x33,
                  (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\certstoremonitorthread.cxx",
                  v13);
    if ( !RevertToSelf() )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x1F5,
        (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\smartcls_common.hxx",
        v14);
    goto LABEL_18;
  }
  if ( !RevertToSelf() )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1F5,
      (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\smartcls_common.hxx",
      v15);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    (char *)this + 16,
    a2);
  std::unique_ptr<enum gsl::byte [0]>::~unique_ptr<enum gsl::byte [0]>(&v23);
  return 0;
}

```

## disassembly

```asm
0x180178878  push    rbx
0x18017887a  push    rsi
0x18017887b  push    rdi
0x18017887c  sub     rsp, 50h
0x180178880  mov     rdi, rdx
0x180178883  mov     rsi, rcx
0x180178886  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x18017888a  jnz     short loc_180178891
0x18017888c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180178891  cmp     qword ptr [rsi+8], 0
0x180178896  jz      short loc_18017889D
0x180178898  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18017889d  mov     [rsp+68h+TokenInformationLength], 0
0x1801788a5  lea     rax, [rsp+68h+TokenInformationLength]
0x1801788aa  mov     qword ptr [rsp+68h+ReturnLength], rax; int
0x1801788af  xor     r9d, r9d; TokenInformationLength
0x1801788b2  xor     r8d, r8d; TokenInformation
0x1801788b5  lea     edx, [r9+1]; TokenInformationClass
0x1801788b9  mov     rcx, rdi; TokenHandle
0x1801788bc  call    cs:__imp_GetTokenInformation
0x1801788c2  test    eax, eax
0x1801788c4  jnz     short loc_1801788EC
0x1801788c6  call    cs:__imp_GetLastError
0x1801788cc  cmp     eax, 7Ah ; 'z'
0x1801788cf  jz      short loc_1801788EC
0x1801788d1  mov     rcx, [rsp+68h]; this
0x1801788d6  lea     r8, aOnecoreuapBase_213; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1801788dd  mov     edx, 1Ah; void *
0x1801788e2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801788e7  jmp     loc_180178A96
0x1801788ec  mov     ecx, [rsp+68h+TokenInformationLength]; unsigned __int64
0x1801788f0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1801788f7  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1801788fc  mov     rbx, rax
0x1801788ff  mov     [rsp+68h+arg_10], rax
0x180178907  test    rax, rax
0x18017890a  jnz     short loc_18017892D
0x18017890c  mov     rcx, [rsp+68h]; this
0x180178911  mov     ebx, 8007000Eh
0x180178916  mov     r9d, ebx; char *
0x180178919  lea     r8, aOnecoreuapBase_213; "onecoreuap\\base\\appmodel\\search\\mss"...
0x180178920  lea     edx, [rax+1Eh]; void *
0x180178923  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180178928  jmp     loc_180178A14
0x18017892d  lea     rax, [rsp+68h+TokenInformationLength]
0x180178932  mov     qword ptr [rsp+68h+ReturnLength], rax; ReturnLength
0x180178937  mov     r9d, [rsp+68h+TokenInformationLength]; TokenInformationLength
0x18017893c  mov     r8, rbx; TokenInformation
0x18017893f  mov     edx, 1; TokenInformationClass
0x180178944  mov     rcx, rdi; TokenHandle
0x180178947  call    cs:__imp_GetTokenInformation
0x18017894d  test    eax, eax
0x18017894f  jnz     short loc_18017896C
0x180178951  lea     edx, [rax+23h]; void *
0x180178954  lea     r8, aOnecoreuapBase_213; "onecoreuap\\base\\appmodel\\search\\mss"...
0x18017895b  mov     rcx, [rsp+68h]; this
0x180178960  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180178965  mov     ebx, eax
0x180178967  jmp     loc_180178A14
0x18017896c  mov     [rsp+68h+var_38], rsi
0x180178971  mov     [rsp+68h+StringSid], 0
0x18017897a  mov     [rsp+68h+var_28], 1
0x18017897f  lea     rdx, [rsp+68h+StringSid]; StringSid
0x180178984  mov     rcx, [rbx]; Sid
0x180178987  call    cs:__imp_ConvertSidToStringSidW
0x18017898d  mov     ebx, eax
0x18017898f  lea     rcx, [rsp+68h+var_38]
0x180178994  call    ??1?$out_param_t@V?$unique_ptr@_WU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<wchar_t,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<wchar_t,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x180178999  test    ebx, ebx
0x18017899b  jnz     short loc_1801789A2
0x18017899d  lea     edx, [rbx+25h]
0x1801789a0  jmp     short loc_180178954
0x1801789a2  mov     [rsp+68h+arg_8], 0
0x1801789ab  mov     rdx, rdi; void *
0x1801789ae  call    ?ImpersonateLoggedOnUser@CSmartImpersonator@@QEAAXPEAX@Z; CSmartImpersonator::ImpersonateLoggedOnUser(void *)
0x1801789b3  nop
0x1801789b4  lea     rax, aMy; "MY"
0x1801789bb  mov     qword ptr [rsp+68h+ReturnLength], rax; pvPara
0x1801789c0  mov     r9d, 10000h; dwFlags
0x1801789c6  xor     r8d, r8d; hCryptProv
0x1801789c9  xor     edx, edx; dwEncodingType
0x1801789cb  lea     ecx, [rdx+0Ah]; lpszStoreProvider
0x1801789ce  call    cs:__imp_CertOpenStore
0x1801789d4  mov     [rsi+8], rax
0x1801789d8  test    rax, rax
0x1801789db  jnz     short loc_180178A25
0x1801789dd  mov     rcx, [rsp+68h]; this
0x1801789e2  lea     r8, aOnecoreuapBase_213; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1801789e9  lea     edx, [rax+33h]; void *
0x1801789ec  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801789f1  mov     ebx, eax
0x1801789f3  call    cs:__imp_RevertToSelf
0x1801789f9  test    eax, eax
0x1801789fb  jnz     short loc_180178A14
0x1801789fd  mov     rcx, [rsp+68h]; this
0x180178a02  lea     r8, aOnecoreuapBase_200; "onecoreuap\\base\\appmodel\\Search\\com"...
0x180178a09  mov     edx, 1F5h; void *
0x180178a0e  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180178a14  lea     rcx, [rsp+68h+arg_10]
0x180178a1c  call    ??1?$unique_ptr@$$BY0A@W4byte@gsl@@U?$default_delete@$$BY0A@W4byte@gsl@@@std@@@std@@QEAA@XZ; std::unique_ptr<gsl::byte [0]>::~unique_ptr<gsl::byte [0]>(void)
0x180178a21  mov     eax, ebx
0x180178a23  jmp     short loc_180178A96
0x180178a25  call    cs:__imp_RevertToSelf
0x180178a2b  test    eax, eax
0x180178a2d  jnz     short loc_180178A46
0x180178a2f  mov     rcx, [rsp+68h]; this
0x180178a34  lea     r8, aOnecoreuapBase_200; "onecoreuap\\base\\appmodel\\Search\\com"...
0x180178a3b  mov     edx, 1F5h; void *
0x180178a40  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180178a46  lea     rcx, [rsi+10h]
0x180178a4a  mov     rdx, rdi
0x180178a4d  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180178a52  nop
0x180178a53  lea     rcx, [rsp+68h+arg_10]
0x180178a5b  call    ??1?$unique_ptr@$$BY0A@W4byte@gsl@@U?$default_delete@$$BY0A@W4byte@gsl@@@std@@@std@@QEAA@XZ; std::unique_ptr<gsl::byte [0]>::~unique_ptr<gsl::byte [0]>(void)
0x180178a60  xor     eax, eax
0x180178a62  jmp     short loc_180178A96
0x180178a64  call    cs:__imp_RevertToSelf
0x180178a6a  test    eax, eax
0x180178a6c  jnz     short loc_180178A85
0x180178a6e  mov     rcx, [rsp+68h]; this
0x180178a73  lea     r8, aOnecoreuapBase_200; "onecoreuap\\base\\appmodel\\Search\\com"...
0x180178a7a  mov     edx, 1F5h; void *
0x180178a7f  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180178a85  lea     rcx, [rsp+68h+arg_10]
0x180178a8d  call    ??1?$unique_ptr@$$BY0A@W4byte@gsl@@U?$default_delete@$$BY0A@W4byte@gsl@@@std@@@std@@QEAA@XZ; std::unique_ptr<gsl::byte [0]>::~unique_ptr<gsl::byte [0]>(void)
0x180178a92  mov     eax, dword ptr [rsp+68h+arg_8]
0x180178a96  add     rsp, 50h
0x180178a9a  pop     rdi
0x180178a9b  pop     rsi
0x180178a9c  pop     rbx
0x180178a9d  retn
```
