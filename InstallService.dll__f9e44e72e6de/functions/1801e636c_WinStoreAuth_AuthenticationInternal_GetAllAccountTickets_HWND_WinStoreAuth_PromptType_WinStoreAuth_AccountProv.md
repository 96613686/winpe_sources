# WinStoreAuth::AuthenticationInternal::GetAllAccountTickets(HWND__ *,WinStoreAuth::PromptType,WinStoreAuth::AccountProviderType,bool,Windows::Foundation::Collections::IVector<HSTRING__ *> * *,Windows::Foundation::Collections::IVector<IInspectable *> * *,bool)

- ea: `0x1801e636c`
- end: `0x1801e667f`
- name: `?GetAllAccountTickets@AuthenticationInternal@WinStoreAuth@@YAJPEAUHWND__@@W4PromptType@2@W4AccountProviderType@2@_NPEAPEAU?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@PEAPEAU?$IVector@PEAUIInspectable@@@789@3@Z`
- size: `787`
- prototype: `__int64 __fastcall(int, int, int, int, HSTRING string, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1801ecd94`

## callees

- `0x1800101f4`
- `0x180010b74`
- `0x1801e636c`
- `0x1801e6688`
- `0x1801eaef0`
- `0x1801eb2b0`
- `0x180215010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e63f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e6407`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e6487`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e6497`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e64d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e6520`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e6546`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e6578`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e6588`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e65b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e65e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e65f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e6640`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e6650`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e63f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e6407`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e6487`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e6497`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e64d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e6520`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e6546`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e6578`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e6588`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e65b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e65e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e65f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e6640`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e6650`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801e641d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801e64ad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801e6609`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801e6666`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801e641d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801e64ad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801e6609`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801e6666`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WinStoreAuth::AuthenticationInternal::GetAllAccountTickets(
        HSTRING a1,
        __int64 a2,
        int a3,
        char a4,
        HSTRING string,
        LPVOID **a6)
{
  HSTRING v6; // r12
  LPVOID **v7; // rax
  int AllAccountTickets; // eax
  unsigned int v9; // r14d
  HSTRING *v10; // rdi
  unsigned __int64 v11; // r15
  unsigned __int64 n; // rsi
  __int64 v14; // rcx
  int v15; // eax
  unsigned int v16; // esi
  HSTRING *v17; // rdi
  unsigned __int64 v18; // r15
  unsigned __int64 m; // r14
  unsigned int v20; // ebx
  unsigned __int64 v21; // rsi
  _QWORD *v22; // rdi
  int v23; // eax
  unsigned int v24; // r15d
  int v25; // eax
  unsigned __int64 j; // r14
  unsigned __int64 i; // r14
  HSTRING v28; // rax
  unsigned __int64 k; // r14
  int v30; // [rsp+20h] [rbp-38h]
  LPVOID pv; // [rsp+40h] [rbp-18h] BYREF
  unsigned __int64 v32; // [rsp+48h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+40h]
  HSTRING v34; // [rsp+A0h] [rbp+48h] BYREF

  v34 = a1;
  pv = 0;
  v32 = 0;
  v6 = string;
  *(_QWORD *)string = 0;
  v7 = a6;
  *a6 = 0;
  AllAccountTickets = WinStoreAuth::AuthenticationInternal::GetAllAccountTickets(
                        a1,
                        a2,
                        a3,
                        a4,
                        &pv,
                        (unsigned __int64)&v32,
                        v7);
  v9 = AllAccountTickets;
  if ( AllAccountTickets >= 0 )
  {
    v34 = 0;
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v34);
    v15 = Windows::Foundation::Collections::Internal::Impl::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>>::Make(
            v14,
            &v34);
    v16 = v15;
    if ( v15 >= 0 )
    {
      v20 = 0;
      v21 = v32;
      v22 = pv;
      while ( v20 < v21 )
      {
        string = 0;
        WindowsDeleteString(0);
        string = 0;
        v23 = WinStoreAuth::AuthenticationInternal::PrefixTicketForMDollar(
                LODWORD(v22[3 * v20]),
                v22[3 * v20 + 1],
                &string);
        v24 = v23;
        if ( v23 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1E5,
            (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
            (const char *)(unsigned int)v23,
            v30);
          WindowsDeleteString(string);
          string = 0;
          Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v34);
          if ( v22 )
          {
            for ( i = 0; i < v21; ++i )
            {
              WindowsDeleteString((HSTRING)v22[3 * i + 1]);
              v22[3 * i + 1] = 0;
              WindowsDeleteString((HSTRING)v22[3 * i + 2]);
              v22[3 * i + 2] = 0;
            }
LABEL_25:
            CoTaskMemFree(v22);
          }
          return v24;
        }
        v25 = (*(__int64 (__fastcall **)(HSTRING, HSTRING))(*(_QWORD *)v34 + 104LL))(v34, string);
        v24 = v25;
        if ( v25 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1E6,
            (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
            (const char *)(unsigned int)v25,
            v30);
          WindowsDeleteString(string);
          string = 0;
          Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v34);
          if ( v22 )
          {
            for ( j = 0; j < v21; ++j )
            {
              WindowsDeleteString((HSTRING)v22[3 * j + 1]);
              v22[3 * j + 1] = 0;
              WindowsDeleteString((HSTRING)v22[3 * j + 2]);
              v22[3 * j + 2] = 0;
            }
            goto LABEL_25;
          }
          return v24;
        }
        WindowsDeleteString(string);
        ++v20;
      }
      v28 = v34;
      v34 = 0;
      *(_QWORD *)v6 = v28;
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v34);
      if ( v22 )
      {
        for ( k = 0; k < v21; ++k )
        {
          WindowsDeleteString((HSTRING)v22[3 * k + 1]);
          v22[3 * k + 1] = 0;
          WindowsDeleteString((HSTRING)v22[3 * k + 2]);
          v22[3 * k + 2] = 0;
        }
        CoTaskMemFree(v22);
      }
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1E0,
        (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
        (const char *)(unsigned int)v15,
        v30);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v34);
      v17 = (HSTRING *)pv;
      if ( pv )
      {
        v18 = v32;
        for ( m = 0; m < v18; ++m )
        {
          WindowsDeleteString(v17[3 * m + 1]);
          v17[3 * m + 1] = 0;
          WindowsDeleteString(v17[3 * m + 2]);
          v17[3 * m + 2] = 0;
        }
        CoTaskMemFree(v17);
      }
      return v16;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1DD,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)AllAccountTickets,
      v30);
    v10 = (HSTRING *)pv;
    if ( pv )
    {
      v11 = v32;
      for ( n = 0; n < v11; ++n )
      {
        WindowsDeleteString(v10[3 * n + 1]);
        v10[3 * n + 1] = 0;
        WindowsDeleteString(v10[3 * n + 2]);
        v10[3 * n + 2] = 0;
      }
      CoTaskMemFree(v10);
    }
    return v9;
  }
}

```

## disassembly

```asm
0x1801e636c  mov     r11, rsp
0x1801e636f  mov     [r11+8], rcx
0x1801e6373  push    rbp
0x1801e6374  push    rbx
0x1801e6375  push    rsi
0x1801e6376  push    rdi
0x1801e6377  push    r12
0x1801e6379  push    r13
0x1801e637b  push    r14
0x1801e637d  push    r15
0x1801e637f  mov     rbp, rsp
0x1801e6382  sub     rsp, 58h
0x1801e6386  xor     r13d, r13d
0x1801e6389  mov     [rbp+pv], r13
0x1801e638d  mov     [rbp+var_10], r13
0x1801e6391  mov     r12, [rbp+string]
0x1801e6395  mov     [r12], r13
0x1801e6399  mov     rax, [rbp+arg_28]
0x1801e639d  mov     [rax], r13
0x1801e63a0  mov     [r11-68h], rax
0x1801e63a4  lea     rax, [rbp+var_10]
0x1801e63a8  mov     [r11-70h], rax
0x1801e63ac  lea     rax, [rbp+pv]
0x1801e63b0  mov     [r11-78h], rax
0x1801e63b4  call    ?GetAllAccountTickets@AuthenticationInternal@WinStoreAuth@@YAJPEAUHWND__@@W4PromptType@2@W4AccountProviderType@2@_NPEAPEAUTicketHolder@2@PEA_KPEAPEAU?$IVector@PEAUIInspectable@@@Collections@Foundation@Windows@@3@Z; WinStoreAuth::AuthenticationInternal::GetAllAccountTickets(HWND__ *,WinStoreAuth::PromptType,WinStoreAuth::AccountProviderType,bool,WinStoreAuth::TicketHolder * *,unsigned __int64 *,Windows::Foundation::Collections::IVector<IInspectable *> * *,bool)
0x1801e63b9  mov     r14d, eax
0x1801e63bc  test    eax, eax
0x1801e63be  jns     short loc_1801E642B
0x1801e63c0  mov     rcx, [rbp+40h]; this
0x1801e63c4  mov     r9d, eax; char *
0x1801e63c7  lea     r8, aOnecoreuapEndu_8; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x1801e63ce  mov     edx, 1DDh; void *
0x1801e63d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e63d8  nop
0x1801e63d9  mov     rdi, [rbp+pv]
0x1801e63dd  test    rdi, rdi
0x1801e63e0  jz      short loc_1801E6423
0x1801e63e2  mov     r15, [rbp+var_10]
0x1801e63e6  mov     esi, r13d
0x1801e63e9  test    r15, r15
0x1801e63ec  jz      short loc_1801E641A
0x1801e63ee  lea     rbx, [rsi+rsi*2]
0x1801e63f2  mov     rcx, [rdi+rbx*8+8]; string
0x1801e63f7  call    cs:__imp_WindowsDeleteString
0x1801e63fd  mov     [rdi+rbx*8+8], r13
0x1801e6402  mov     rcx, [rdi+rbx*8+10h]; string
0x1801e6407  call    cs:__imp_WindowsDeleteString
0x1801e640d  mov     [rdi+rbx*8+10h], r13
0x1801e6412  inc     rsi
0x1801e6415  cmp     rsi, r15
0x1801e6418  jb      short loc_1801E63EE
0x1801e641a  mov     rcx, rdi; pv
0x1801e641d  call    cs:__imp_CoTaskMemFree
0x1801e6423  mov     eax, r14d
0x1801e6426  jmp     loc_1801E666E
0x1801e642b  mov     [rbp+arg_0], r13
0x1801e642f  lea     rcx, [rbp+arg_0]
0x1801e6433  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1801e6438  lea     rdx, [rbp+arg_0]
0x1801e643c  call    ?Make@?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultVectorOptions@PEAUHSTRING__@@@3456@@Impl@Internal@Collections@Foundation@Windows@@SAJAEBU?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@PEAPEAV123456@@Z; Windows::Foundation::Collections::Internal::Impl::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>>::Make(Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *> const &,Windows::Foundation::Collections::Internal::Impl::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>> * *)
0x1801e6441  mov     esi, eax
0x1801e6443  test    eax, eax
0x1801e6445  jns     short loc_1801E64BA
0x1801e6447  mov     rcx, [rbp+40h]; this
0x1801e644b  mov     r9d, eax; char *
0x1801e644e  lea     r8, aOnecoreuapEndu_8; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x1801e6455  mov     edx, 1E0h; void *
0x1801e645a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e645f  lea     rcx, [rbp+arg_0]
0x1801e6463  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1801e6468  nop
0x1801e6469  mov     rdi, [rbp+pv]
0x1801e646d  test    rdi, rdi
0x1801e6470  jz      short loc_1801E64B3
0x1801e6472  mov     r15, [rbp+var_10]
0x1801e6476  mov     r14, r13
0x1801e6479  test    r15, r15
0x1801e647c  jz      short loc_1801E64AA
0x1801e647e  lea     rbx, [r14+r14*2]
0x1801e6482  mov     rcx, [rdi+rbx*8+8]; string
0x1801e6487  call    cs:__imp_WindowsDeleteString
0x1801e648d  mov     [rdi+rbx*8+8], r13
0x1801e6492  mov     rcx, [rdi+rbx*8+10h]; string
0x1801e6497  call    cs:__imp_WindowsDeleteString
0x1801e649d  mov     [rdi+rbx*8+10h], r13
0x1801e64a2  inc     r14
0x1801e64a5  cmp     r14, r15
0x1801e64a8  jb      short loc_1801E647E
0x1801e64aa  mov     rcx, rdi; pv
0x1801e64ad  call    cs:__imp_CoTaskMemFree
0x1801e64b3  mov     eax, esi
0x1801e64b5  jmp     loc_1801E666E
0x1801e64ba  mov     ebx, r13d
0x1801e64bd  mov     rsi, [rbp+var_10]
0x1801e64c1  mov     rdi, [rbp+pv]
0x1801e64c5  mov     r14d, ebx
0x1801e64c8  cmp     r14, rsi
0x1801e64cb  jnb     loc_1801E6614
0x1801e64d1  mov     [rbp+string], r13
0x1801e64d5  xor     ecx, ecx; string
0x1801e64d7  call    cs:__imp_WindowsDeleteString
0x1801e64dd  mov     [rbp+string], r13
0x1801e64e1  lea     rcx, [r14+r14*2]
0x1801e64e5  lea     r8, [rbp+string]
0x1801e64e9  mov     rdx, [rdi+rcx*8+8]
0x1801e64ee  mov     ecx, [rdi+rcx*8]
0x1801e64f1  call    ?PrefixTicketForMDollar@AuthenticationInternal@WinStoreAuth@@YAJW4AccountProviderType@2@PEAUHSTRING__@@PEAPEAU4@@Z; WinStoreAuth::AuthenticationInternal::PrefixTicketForMDollar(WinStoreAuth::AccountProviderType,HSTRING__ *,HSTRING__ * *)
0x1801e64f6  mov     r15d, eax
0x1801e64f9  test    eax, eax
0x1801e64fb  js      loc_1801E659D
0x1801e6501  mov     rcx, [rbp+arg_0]
0x1801e6505  mov     rax, [rcx]
0x1801e6508  mov     rdx, [rbp+string]
0x1801e650c  mov     rax, [rax+68h]
0x1801e6510  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e6515  mov     r15d, eax
0x1801e6518  test    eax, eax
0x1801e651a  js      short loc_1801E652A
0x1801e651c  mov     rcx, [rbp+string]; string
0x1801e6520  call    cs:__imp_WindowsDeleteString
0x1801e6526  inc     ebx
0x1801e6528  jmp     short loc_1801E64C5
0x1801e652a  mov     rcx, [rbp+40h]; this
0x1801e652e  mov     r9d, r15d; char *
0x1801e6531  lea     r8, aOnecoreuapEndu_8; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x1801e6538  mov     edx, 1E6h; void *
0x1801e653d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e6542  mov     rcx, [rbp+string]; string
0x1801e6546  call    cs:__imp_WindowsDeleteString
0x1801e654c  mov     [rbp+string], r13
0x1801e6550  lea     rcx, [rbp+arg_0]
0x1801e6554  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1801e6559  nop
0x1801e655a  test    rdi, rdi
0x1801e655d  jz      loc_1801E660F
0x1801e6563  mov     r14, r13
0x1801e6566  test    rsi, rsi
0x1801e6569  jz      loc_1801E6606
0x1801e656f  lea     rbx, [r14+r14*2]
0x1801e6573  mov     rcx, [rdi+rbx*8+8]; string
0x1801e6578  call    cs:__imp_WindowsDeleteString
0x1801e657e  mov     [rdi+rbx*8+8], r13
0x1801e6583  mov     rcx, [rdi+rbx*8+10h]; string
0x1801e6588  call    cs:__imp_WindowsDeleteString
0x1801e658e  mov     [rdi+rbx*8+10h], r13
0x1801e6593  inc     r14
0x1801e6596  cmp     r14, rsi
0x1801e6599  jb      short loc_1801E656F
0x1801e659b  jmp     short loc_1801E6606
0x1801e659d  mov     rcx, [rbp+40h]; this
0x1801e65a1  mov     r9d, r15d; char *
0x1801e65a4  lea     r8, aOnecoreuapEndu_8; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x1801e65ab  mov     edx, 1E5h; void *
0x1801e65b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e65b5  mov     rcx, [rbp+string]; string
0x1801e65b9  call    cs:__imp_WindowsDeleteString
0x1801e65bf  mov     [rbp+string], r13
0x1801e65c3  lea     rcx, [rbp+arg_0]
0x1801e65c7  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1801e65cc  nop
0x1801e65cd  test    rdi, rdi
0x1801e65d0  jz      short loc_1801E660F
0x1801e65d2  mov     r14, r13
0x1801e65d5  test    rsi, rsi
0x1801e65d8  jz      short loc_1801E6606
0x1801e65da  lea     rbx, [r14+r14*2]
0x1801e65de  mov     rcx, [rdi+rbx*8+8]; string
0x1801e65e3  call    cs:__imp_WindowsDeleteString
0x1801e65e9  mov     [rdi+rbx*8+8], r13
0x1801e65ee  mov     rcx, [rdi+rbx*8+10h]; string
0x1801e65f3  call    cs:__imp_WindowsDeleteString
0x1801e65f9  mov     [rdi+rbx*8+10h], r13
0x1801e65fe  inc     r14
0x1801e6601  cmp     r14, rsi
0x1801e6604  jb      short loc_1801E65DA
0x1801e6606  mov     rcx, rdi; pv
0x1801e6609  call    cs:__imp_CoTaskMemFree
0x1801e660f  mov     eax, r15d
0x1801e6612  jmp     short loc_1801E666E
0x1801e6614  mov     rax, [rbp+arg_0]
0x1801e6618  mov     [rbp+arg_0], r13
0x1801e661c  mov     [r12], rax
0x1801e6620  lea     rcx, [rbp+arg_0]
0x1801e6624  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1801e6629  nop
0x1801e662a  test    rdi, rdi
0x1801e662d  jz      short loc_1801E666C
0x1801e662f  mov     r14, r13
0x1801e6632  test    rsi, rsi
0x1801e6635  jz      short loc_1801E6663
0x1801e6637  lea     rbx, [r14+r14*2]
0x1801e663b  mov     rcx, [rdi+rbx*8+8]; string
0x1801e6640  call    cs:__imp_WindowsDeleteString
0x1801e6646  mov     [rdi+rbx*8+8], r13
0x1801e664b  mov     rcx, [rdi+rbx*8+10h]; string
0x1801e6650  call    cs:__imp_WindowsDeleteString
0x1801e6656  mov     [rdi+rbx*8+10h], r13
0x1801e665b  inc     r14
0x1801e665e  cmp     r14, rsi
0x1801e6661  jb      short loc_1801E6637
0x1801e6663  mov     rcx, rdi; pv
0x1801e6666  call    cs:__imp_CoTaskMemFree
0x1801e666c  xor     eax, eax
0x1801e666e  add     rsp, 58h
0x1801e6672  pop     r15
0x1801e6674  pop     r14
0x1801e6676  pop     r13
0x1801e6678  pop     r12
0x1801e667a  pop     rdi
0x1801e667b  pop     rsi
0x1801e667c  pop     rbx
0x1801e667d  pop     rbp
0x1801e667e  retn
```
