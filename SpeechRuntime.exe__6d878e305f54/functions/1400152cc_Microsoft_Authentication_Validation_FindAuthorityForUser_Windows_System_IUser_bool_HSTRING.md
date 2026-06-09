# Microsoft::Authentication::Validation::FindAuthorityForUser(Windows::System::IUser *,bool *,HSTRING__ * *)

- ea: `0x1400152cc`
- end: `0x1400154cf`
- name: `?FindAuthorityForUser@Validation@Authentication@Microsoft@@SAJPEAUIUser@System@Windows@@PEA_NPEAPEAUHSTRING__@@@Z`
- size: `515`
- prototype: `__int64 __fastcall(struct Windows::System::IUser *, bool *, HSTRING *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x140017f60`

## callees

- `0x140002d30`
- `0x14000aab8`
- `0x14000c32c`
- `0x14000e030`
- `0x14000e848`
- `0x1400152cc`
- `0x14001563c`
- `0x1400159a4`
- `0x140031010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1400154c8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1400154c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x140015400`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x140015400`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400153bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14001544a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14001549a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400153bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14001544a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14001549a`

## string_xrefs

- `0x140015435`: `onecoreuap\enduser\NUI\OneCore\common\include\EnterpriseAttached.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Microsoft::Authentication::Validation::FindAuthorityForUser(
        struct Windows::System::IUser *a1,
        bool *a2,
        HSTRING *a3)
{
  int ProviderForUser; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdx
  struct Windows::Security::Credentials::IWebAccountProvider *v8; // rbx
  __int64 (__fastcall *v9)(struct Windows::Security::Credentials::IWebAccountProvider *, GUID *, __int64 *); // rdi
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, HSTRING *); // rbx
  HRESULT v12; // eax
  int v14; // [rsp+20h] [rbp-39h] BYREF
  HSTRING string; // [rsp+28h] [rbp-31h] BYREF
  INT32 result; // [rsp+30h] [rbp-29h] BYREF
  __int64 v17; // [rsp+38h] [rbp-21h] BYREF
  struct Windows::Security::Credentials::IWebAccountProvider *v18; // [rsp+40h] [rbp-19h] BYREF
  HSTRING_HEADER v19; // [rsp+48h] [rbp-11h] BYREF
  HSTRING v20; // [rsp+60h] [rbp+7h]
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp+Fh] BYREF
  HSTRING string2; // [rsp+80h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  *a2 = 0;
  string2 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"organizations", 0xEu, 0xDu);
  v20 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v19, L"https://login.windows.local", 0x1Cu, 0x1Bu);
  v18 = 0;
  v17 = 0;
  string = 0;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v18);
  ProviderForUser = Microsoft::Authentication::Validation::FindProviderForUser(a1, v20, 0, &v18);
  v6 = ProviderForUser;
  if ( ProviderForUser < 0 )
  {
    v7 = 47;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\enduser\\NUI\\OneCore\\common\\include\\EnterpriseAttached.h",
      (const char *)(unsigned int)ProviderForUser,
      v14);
    WindowsDeleteString(string);
    string = 0;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v17);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v18);
    return v6;
  }
  v8 = v18;
  if ( v18 )
  {
    v9 = **(__int64 (__fastcall ***)(struct Windows::Security::Credentials::IWebAccountProvider *, GUID *, __int64 *))v18;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v17);
    ProviderForUser = v9(v8, &GUID_4a01eb05_4e42_41d4_b518_e008a5163614, &v17);
    v6 = ProviderForUser;
    if ( ProviderForUser < 0 )
    {
      v7 = 50;
      goto LABEL_14;
    }
    v10 = v17;
    v11 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v17 + 56LL);
    WindowsDeleteString(string);
    string = 0;
    ProviderForUser = v11(v10, &string);
    v6 = ProviderForUser;
    if ( ProviderForUser < 0 )
    {
      v7 = 51;
      goto LABEL_14;
    }
  }
  else
  {
    Microsoft::WRL::Wrappers::HString::Set((Microsoft::WRL::Wrappers::HString *)&string, 0, 0);
  }
  result = 0;
  v12 = WindowsCompareStringOrdinal(string, string2, &result);
  if ( v12 < 0 )
  {
    RaiseException(v12, 1u, 0, 0);
    JUMPOUT(0x1400154CELL);
  }
  if ( result )
    *a2 = 1;
  LOBYTE(v14) = 0;
  ProviderForUser = Microsoft::Authentication::Validation::FindLinkedAccountsForUser(a1, (bool *)&v14);
  v6 = ProviderForUser;
  if ( ProviderForUser < 0 )
  {
    v7 = 72;
    goto LABEL_14;
  }
  if ( (_BYTE)v14 )
    *a2 = 0;
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v17);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v18);
  return 0;
}

```

## disassembly

```asm
0x1400152cc  mov     [rsp-8+arg_10], rbx
0x1400152d1  push    rbp
0x1400152d2  push    rsi
0x1400152d3  push    rdi
0x1400152d4  push    r14
0x1400152d6  push    r15
0x1400152d8  lea     rbp, [rsp-37h]
0x1400152dd  sub     rsp, 90h
0x1400152e4  mov     rax, cs:__security_cookie
0x1400152eb  xor     rax, rsp
0x1400152ee  mov     [rbp+57h+var_28], rax
0x1400152f2  mov     rsi, rdx
0x1400152f5  mov     r14, rcx
0x1400152f8  xor     r15d, r15d
0x1400152fb  mov     [rdx], r15b
0x1400152fe  mov     [rbp+57h+string2], r15
0x140015302  lea     r9d, [r15+0Dh]; unsigned int
0x140015306  lea     r8d, [r15+0Eh]; unsigned int
0x14001530a  lea     rdx, aOrganizations; "organizations"
0x140015311  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x140015315  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x14001531a  nop
0x14001531b  mov     [rbp+57h+var_50], r15
0x14001531f  lea     r9d, [r15+1Bh]; unsigned int
0x140015323  lea     r8d, [r15+1Ch]; unsigned int
0x140015327  lea     rdx, aHttpsLoginWind; "https://login.windows.local"
0x14001532e  lea     rcx, [rbp+57h+var_68]; hstringHeader
0x140015332  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x140015337  nop
0x140015338  mov     [rbp+57h+var_70], r15
0x14001533c  mov     [rbp+57h+var_78], r15
0x140015340  mov     [rbp+57h+string], r15
0x140015344  lea     rcx, [rbp+57h+var_70]
0x140015348  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x14001534d  lea     r9, [rbp+57h+var_70]; struct Windows::Security::Credentials::IWebAccountProvider **
0x140015351  xor     r8d, r8d; HSTRING
0x140015354  mov     rdx, [rbp+57h+var_50]; HSTRING
0x140015358  mov     rcx, r14; struct Windows::System::IUser *
0x14001535b  call    ?FindProviderForUser@Validation@Authentication@Microsoft@@CAJPEAUIUser@System@Windows@@PEAUHSTRING__@@1PEAPEAUIWebAccountProvider@Credentials@Security@6@@Z; Microsoft::Authentication::Validation::FindProviderForUser(Windows::System::IUser *,HSTRING__ *,HSTRING__ *,Windows::Security::Credentials::IWebAccountProvider * *)
0x140015360  mov     ebx, eax
0x140015362  test    eax, eax
0x140015364  jns     short loc_14001536F
0x140015366  lea     edx, [r15+2Fh]
0x14001536a  jmp     loc_140015432
0x14001536f  mov     rbx, [rbp+57h+var_70]
0x140015373  test    rbx, rbx
0x140015376  jz      short loc_1400153E2
0x140015378  mov     rax, [rbx]
0x14001537b  mov     rdi, [rax]
0x14001537e  lea     rcx, [rbp+57h+var_78]
0x140015382  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x140015387  lea     r8, [rbp+57h+var_78]
0x14001538b  lea     rdx, _GUID_4a01eb05_4e42_41d4_b518_e008a5163614
0x140015392  mov     rcx, rbx
0x140015395  mov     rax, rdi
0x140015398  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001539d  mov     ebx, eax
0x14001539f  test    eax, eax
0x1400153a1  jns     short loc_1400153AD
0x1400153a3  mov     edx, 32h ; '2'
0x1400153a8  jmp     loc_140015432
0x1400153ad  mov     rdi, [rbp+57h+var_78]
0x1400153b1  mov     rax, [rdi]
0x1400153b4  mov     rbx, [rax+38h]
0x1400153b8  mov     rcx, [rbp+57h+string]; string
0x1400153bc  call    cs:__imp_WindowsDeleteString
0x1400153c2  mov     [rbp+57h+string], r15
0x1400153c6  lea     rdx, [rbp+57h+string]
0x1400153ca  mov     rcx, rdi
0x1400153cd  mov     rax, rbx
0x1400153d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400153d5  mov     ebx, eax
0x1400153d7  test    eax, eax
0x1400153d9  jns     short loc_1400153F0
0x1400153db  mov     edx, 33h ; '3'
0x1400153e0  jmp     short loc_140015432
0x1400153e2  xor     r8d, r8d; unsigned int
0x1400153e5  xor     edx, edx; unsigned __int16 *
0x1400153e7  lea     rcx, [rbp+57h+string]; this
0x1400153eb  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x1400153f0  mov     [rbp+57h+result], r15d
0x1400153f4  lea     r8, [rbp+57h+result]; result
0x1400153f8  mov     rdx, [rbp+57h+string2]; string2
0x1400153fc  mov     rcx, [rbp+57h+string]; string1
0x140015400  call    cs:__imp_WindowsCompareStringOrdinal
0x140015406  test    eax, eax
0x140015408  js      loc_1400154BC
0x14001540e  cmp     [rbp+57h+result], r15d
0x140015412  jz      short loc_140015417
0x140015414  mov     byte ptr [rsi], 1
0x140015417  mov     byte ptr [rbp+57h+var_90], r15b
0x14001541b  lea     rdx, [rbp+57h+var_90]; bool *
0x14001541f  mov     rcx, r14; struct Windows::System::IUser *
0x140015422  call    ?FindLinkedAccountsForUser@Validation@Authentication@Microsoft@@CAJPEAUIUser@System@Windows@@PEA_N@Z; Microsoft::Authentication::Validation::FindLinkedAccountsForUser(Windows::System::IUser *,bool *)
0x140015427  mov     ebx, eax
0x140015429  test    eax, eax
0x14001542b  jns     short loc_14001548D
0x14001542d  mov     edx, 48h ; 'H'; void *
0x140015432  mov     r9d, eax; char *
0x140015435  lea     r8, aOnecoreuapEndu_59; "onecoreuap\\enduser\\NUI\\OneCore\\comm"...
0x14001543c  mov     rcx, [rbp+5Fh]; this
0x140015440  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140015445  nop
0x140015446  mov     rcx, [rbp+57h+string]; string
0x14001544a  call    cs:__imp_WindowsDeleteString
0x140015450  mov     [rbp+57h+string], r15
0x140015454  lea     rcx, [rbp+57h+var_78]
0x140015458  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x14001545d  nop
0x14001545e  lea     rcx, [rbp+57h+var_70]
0x140015462  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x140015467  nop
0x140015468  mov     eax, ebx
0x14001546a  mov     rcx, [rbp+57h+var_28]
0x14001546e  xor     rcx, rsp; StackCookie
0x140015471  call    __security_check_cookie
0x140015476  mov     rbx, [rsp+0B0h+arg_10]
0x14001547e  add     rsp, 90h
0x140015485  pop     r15
0x140015487  pop     r14
0x140015489  pop     rdi
0x14001548a  pop     rsi
0x14001548b  pop     rbp
0x14001548c  retn
0x14001548d  cmp     byte ptr [rbp+57h+var_90], r15b
0x140015491  jz      short loc_140015496
0x140015493  mov     [rsi], r15b
0x140015496  mov     rcx, [rbp+57h+string]; string
0x14001549a  call    cs:__imp_WindowsDeleteString
0x1400154a0  mov     [rbp+57h+string], r15
0x1400154a4  lea     rcx, [rbp+57h+var_78]
0x1400154a8  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1400154ad  nop
0x1400154ae  lea     rcx, [rbp+57h+var_70]
0x1400154b2  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1400154b7  nop
0x1400154b8  xor     eax, eax
0x1400154ba  jmp     short loc_14001546A
0x1400154bc  xor     r9d, r9d; lpArguments
0x1400154bf  xor     r8d, r8d; nNumberOfArguments
0x1400154c2  lea     edx, [r9+1]; dwExceptionFlags
0x1400154c6  mov     ecx, eax; dwExceptionCode
0x1400154c8  call    cs:__imp_RaiseException
```
