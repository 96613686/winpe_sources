# SystemSettings::WorkAccess::WorkAccountList::IsDefaultSignInAccount(Windows::Security::Credentials::IWebAccount *,bool *)

- ea: `0x18001d274`
- end: `0x18001d530`
- name: `?IsDefaultSignInAccount@WorkAccountList@WorkAccess@SystemSettings@@AEAAJPEAUIWebAccount@Credentials@Security@Windows@@PEA_N@Z`
- size: `700`
- prototype: `__int64 __fastcall(SystemSettings::WorkAccess::WorkAccountList *__hidden this, struct Windows::Security::Credentials::IWebAccount *, bool *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001d088`
- `0x18001d5c0`

## callees

- `0x1800076ac`
- `0x1800096ec`
- `0x180019970`
- `0x18001c00c`
- `0x18001d274`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d3e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d42a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d43e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d462`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d4c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d4db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d3e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d42a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d43e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d462`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d4c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001d4db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x18001d49e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x18001d49e`

## string_xrefs

- `0x18001d2a8`: `shellcommon\shell\settingshandlers\workaccess\lib\workaccountlist.cpp`
- `0x18001d2f8`: `shellcommon\shell\settingshandlers\workaccess\lib\workaccountlist.cpp`
- `0x18001d396`: `shellcommon\shell\settingshandlers\workaccess\lib\workaccountlist.cpp`
- `0x18001d419`: `shellcommon\shell\settingshandlers\workaccess\lib\workaccountlist.cpp`
- `0x18001d4f8`: `shellcommon\shell\settingshandlers\workaccess\lib\workaccountlist.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall SystemSettings::WorkAccess::WorkAccountList::IsDefaultSignInAccount(
        SystemSettings::WorkAccess::WorkAccountList *this,
        struct Windows::Security::Credentials::IWebAccount *a2,
        bool *a3)
{
  int v6; // eax
  int DefaultSignInAccount; // ebx
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, __int64 *); // rbx
  int v10; // eax
  __int64 v11; // rdi
  __int64 v12; // rbx
  __int64 v13; // rdx
  __int64 (__fastcall *v14)(__int64, __int64 *); // rdi
  int v15; // eax
  __int64 (__fastcall *v16)(struct Windows::Security::Credentials::IWebAccount *, HSTRING *); // rbx
  HRESULT v17; // eax
  __int64 v18; // rdx
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, HSTRING *); // rbx
  HSTRING string1; // [rsp+20h] [rbp-20h] BYREF
  __int64 v23; // [rsp+28h] [rbp-18h] BYREF
  __int64 v24; // [rsp+30h] [rbp-10h] BYREF
  __int64 v25; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  INT32 result; // [rsp+80h] [rbp+40h] BYREF
  HSTRING string; // [rsp+88h] [rbp+48h] BYREF

  *a3 = 0;
  v6 = SystemSettings::WorkAccess::WorkAccountList::EnsureTokenBrokerInternalStatics(this);
  DefaultSignInAccount = v6;
  if ( v6 >= 0 )
  {
    v25 = 0;
    v8 = *((_QWORD *)this + 38);
    v9 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v8 + 232LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
    v10 = v9(v8, &v25);
    DefaultSignInAccount = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2AA,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\workaccountlist.cpp",
        (const char *)(unsigned int)v10,
        (int)string1);
LABEL_25:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
      return (unsigned int)DefaultSignInAccount;
    }
    v23 = 0;
    v11 = v25;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
    DefaultSignInAccount = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>>(v11);
    if ( DefaultSignInAccount < 0
      || (DefaultSignInAccount = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v11 + 64LL))(v11, &v23),
          DefaultSignInAccount < 0) )
    {
      v13 = 685;
      goto LABEL_23;
    }
    v12 = v23;
    if ( !v23 )
    {
      DefaultSignInAccount = -2147467259;
      v13 = 686;
LABEL_23:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\workaccountlist.cpp",
        (const char *)(unsigned int)DefaultSignInAccount,
        (int)string1);
      goto LABEL_24;
    }
    v24 = 0;
    v14 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v23 + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
    v15 = v14(v12, &v24);
    DefaultSignInAccount = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2B1,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\workaccountlist.cpp",
        (const char *)(unsigned int)v15,
        (int)string1);
LABEL_11:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
LABEL_24:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
      goto LABEL_25;
    }
    if ( !v24 )
    {
LABEL_13:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
      DefaultSignInAccount = 0;
      goto LABEL_25;
    }
    string1 = 0;
    string = 0;
    v16 = *(__int64 (__fastcall **)(struct Windows::Security::Credentials::IWebAccount *, HSTRING *))(*(_QWORD *)a2 + 56LL);
    WindowsDeleteString(0);
    string1 = 0;
    v17 = v16(a2, &string1);
    DefaultSignInAccount = v17;
    if ( v17 >= 0 )
    {
      v19 = v24;
      v20 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v24 + 56LL);
      WindowsDeleteString(string);
      string = 0;
      v17 = v20(v19, &string);
      DefaultSignInAccount = v17;
      if ( v17 >= 0 )
      {
        result = 0;
        v17 = WindowsCompareStringOrdinal(string1, string, &result);
        DefaultSignInAccount = v17;
        if ( v17 >= 0 )
        {
          *a3 = result == 0;
          WindowsDeleteString(string);
          string = 0;
          WindowsDeleteString(string1);
          string1 = 0;
          goto LABEL_13;
        }
        v18 = 698;
      }
      else
      {
        v18 = 695;
      }
    }
    else
    {
      v18 = 694;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\workaccountlist.cpp",
      (const char *)(unsigned int)v17,
      (int)string1);
    WindowsDeleteString(string);
    string = 0;
    WindowsDeleteString(string1);
    string1 = 0;
    goto LABEL_11;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2A6,
    (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\workaccountlist.cpp",
    (const char *)(unsigned int)v6,
    (int)string1);
  return (unsigned int)DefaultSignInAccount;
}

```

## disassembly

```asm
0x18001d274  mov     [rsp-28h+arg_0], rbx
0x18001d279  push    rbp
0x18001d27a  push    rsi
0x18001d27b  push    rdi
0x18001d27c  push    r14
0x18001d27e  push    r15
0x18001d280  mov     rbp, rsp
0x18001d283  sub     rsp, 40h
0x18001d287  mov     rsi, r8
0x18001d28a  mov     r14, rdx
0x18001d28d  mov     rdi, rcx
0x18001d290  xor     r15d, r15d
0x18001d293  mov     [r8], r15b
0x18001d296  call    ?EnsureTokenBrokerInternalStatics@WorkAccountList@WorkAccess@SystemSettings@@AEAAJXZ; SystemSettings::WorkAccess::WorkAccountList::EnsureTokenBrokerInternalStatics(void)
0x18001d29b  mov     ebx, eax
0x18001d29d  test    eax, eax
0x18001d29f  jns     short loc_18001D2BE
0x18001d2a1  mov     rcx, [rbp+28h]; this
0x18001d2a5  mov     r9d, eax; char *
0x18001d2a8  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\settingshandlers\\w"...
0x18001d2af  mov     edx, 2A6h; void *
0x18001d2b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d2b9  jmp     loc_18001D51C
0x18001d2be  mov     [rbp+var_8], r15
0x18001d2c2  mov     rdi, [rdi+130h]
0x18001d2c9  mov     rax, [rdi]
0x18001d2cc  mov     rbx, [rax+0E8h]
0x18001d2d3  lea     rcx, [rbp+var_8]
0x18001d2d7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001d2dc  lea     rdx, [rbp+var_8]
0x18001d2e0  mov     rcx, rdi
0x18001d2e3  mov     rax, rbx
0x18001d2e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d2eb  mov     ebx, eax
0x18001d2ed  test    eax, eax
0x18001d2ef  jns     short loc_18001D30E
0x18001d2f1  mov     rcx, [rbp+28h]; this
0x18001d2f5  mov     r9d, eax; char *
0x18001d2f8  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\settingshandlers\\w"...
0x18001d2ff  mov     edx, 2AAh; void *
0x18001d304  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d309  jmp     loc_18001D513
0x18001d30e  mov     [rbp+var_18], r15
0x18001d312  mov     rdi, [rbp+var_8]
0x18001d316  lea     rcx, [rbp+var_18]
0x18001d31a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001d31f  mov     rcx, rdi
0x18001d322  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *> *,tagCOWAIT_FLAGS,void *)
0x18001d327  mov     ebx, eax
0x18001d329  test    eax, eax
0x18001d32b  js      loc_18001D4F0
0x18001d331  mov     rax, [rdi]
0x18001d334  lea     rdx, [rbp+var_18]
0x18001d338  mov     rcx, rdi
0x18001d33b  mov     rax, [rax+40h]
0x18001d33f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d344  mov     ebx, eax
0x18001d346  test    eax, eax
0x18001d348  js      loc_18001D4F0
0x18001d34e  mov     rbx, [rbp+var_18]
0x18001d352  test    rbx, rbx
0x18001d355  jnz     short loc_18001D366
0x18001d357  mov     ebx, 80004005h
0x18001d35c  mov     edx, 2AEh
0x18001d361  jmp     loc_18001D4F5
0x18001d366  mov     [rbp+var_10], r15
0x18001d36a  mov     rax, [rbx]
0x18001d36d  mov     rdi, [rax+30h]
0x18001d371  lea     rcx, [rbp+var_10]
0x18001d375  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001d37a  lea     rdx, [rbp+var_10]
0x18001d37e  mov     rcx, rbx
0x18001d381  mov     rax, rdi
0x18001d384  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d389  mov     ebx, eax
0x18001d38b  test    eax, eax
0x18001d38d  jns     short loc_18001D3B6
0x18001d38f  mov     rcx, [rbp+28h]; this
0x18001d393  mov     r9d, eax; char *
0x18001d396  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\settingshandlers\\w"...
0x18001d39d  mov     edx, 2B1h; void *
0x18001d3a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d3a7  nop
0x18001d3a8  lea     rcx, [rbp+var_10]
0x18001d3ac  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001d3b1  jmp     loc_18001D509
0x18001d3b6  cmp     [rbp+var_10], r15
0x18001d3ba  jnz     short loc_18001D3D7
0x18001d3bc  lea     rcx, [rbp+var_10]
0x18001d3c0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001d3c5  nop
0x18001d3c6  lea     rcx, [rbp+var_18]
0x18001d3ca  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001d3cf  mov     ebx, r15d
0x18001d3d2  jmp     loc_18001D513
0x18001d3d7  mov     [rbp+string1], r15
0x18001d3db  mov     [rbp+string], r15
0x18001d3df  mov     rax, [r14]
0x18001d3e2  mov     rbx, [rax+38h]
0x18001d3e6  xor     ecx, ecx; string
0x18001d3e8  call    cs:__imp_WindowsDeleteString
0x18001d3ef  nop     dword ptr [rax+rax+00h]
0x18001d3f4  mov     [rbp+string1], r15
0x18001d3f8  lea     rdx, [rbp+string1]
0x18001d3fc  mov     rcx, r14
0x18001d3ff  mov     rax, rbx
0x18001d402  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d407  mov     ebx, eax
0x18001d409  test    eax, eax
0x18001d40b  jns     short loc_18001D453
0x18001d40d  mov     edx, 2B6h; void *
0x18001d412  mov     rcx, [rbp+28h]; this
0x18001d416  mov     r9d, eax; char *
0x18001d419  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\settingshandlers\\w"...
0x18001d420  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d425  nop
0x18001d426  mov     rcx, [rbp+string]; string
0x18001d42a  call    cs:__imp_WindowsDeleteString
0x18001d431  nop     dword ptr [rax+rax+00h]
0x18001d436  mov     [rbp+string], r15
0x18001d43a  mov     rcx, [rbp+string1]; string
0x18001d43e  call    cs:__imp_WindowsDeleteString
0x18001d445  nop     dword ptr [rax+rax+00h]
0x18001d44a  mov     [rbp+string1], r15
0x18001d44e  jmp     loc_18001D3A8
0x18001d453  mov     rdi, [rbp+var_10]
0x18001d457  mov     rax, [rdi]
0x18001d45a  mov     rbx, [rax+38h]
0x18001d45e  mov     rcx, [rbp+string]; string
0x18001d462  call    cs:__imp_WindowsDeleteString
0x18001d469  nop     dword ptr [rax+rax+00h]
0x18001d46e  mov     [rbp+string], r15
0x18001d472  lea     rdx, [rbp+string]
0x18001d476  mov     rcx, rdi
0x18001d479  mov     rax, rbx
0x18001d47c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d481  mov     ebx, eax
0x18001d483  test    eax, eax
0x18001d485  jns     short loc_18001D48E
0x18001d487  mov     edx, 2B7h
0x18001d48c  jmp     short loc_18001D412
0x18001d48e  mov     [rbp+result], r15d
0x18001d492  lea     r8, [rbp+result]; result
0x18001d496  mov     rdx, [rbp+string]; string2
0x18001d49a  mov     rcx, [rbp+string1]; string1
0x18001d49e  call    cs:__imp_WindowsCompareStringOrdinal
0x18001d4a5  nop     dword ptr [rax+rax+00h]
0x18001d4aa  mov     ebx, eax
0x18001d4ac  test    eax, eax
0x18001d4ae  jns     short loc_18001D4BA
0x18001d4b0  mov     edx, 2BAh
0x18001d4b5  jmp     loc_18001D412
0x18001d4ba  cmp     [rbp+result], r15d
0x18001d4be  setz    al
0x18001d4c1  mov     [rsi], al
0x18001d4c3  mov     rcx, [rbp+string]; string
0x18001d4c7  call    cs:__imp_WindowsDeleteString
0x18001d4ce  nop     dword ptr [rax+rax+00h]
0x18001d4d3  mov     [rbp+string], r15
0x18001d4d7  mov     rcx, [rbp+string1]; string
0x18001d4db  call    cs:__imp_WindowsDeleteString
0x18001d4e2  nop     dword ptr [rax+rax+00h]
0x18001d4e7  mov     [rbp+string1], r15
0x18001d4eb  jmp     loc_18001D3BC
0x18001d4f0  mov     edx, 2ADh; void *
0x18001d4f5  mov     r9d, ebx; char *
0x18001d4f8  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\settingshandlers\\w"...
0x18001d4ff  mov     rcx, [rbp+28h]; this
0x18001d503  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d508  nop
0x18001d509  lea     rcx, [rbp+var_18]
0x18001d50d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001d512  nop
0x18001d513  lea     rcx, [rbp+var_8]
0x18001d517  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001d51c  mov     eax, ebx
0x18001d51e  mov     rbx, [rsp+40h+arg_0]
0x18001d523  add     rsp, 40h
0x18001d527  pop     r15
0x18001d529  pop     r14
0x18001d52b  pop     rdi
0x18001d52c  pop     rsi
0x18001d52d  pop     rbp
0x18001d52e  retn
```
