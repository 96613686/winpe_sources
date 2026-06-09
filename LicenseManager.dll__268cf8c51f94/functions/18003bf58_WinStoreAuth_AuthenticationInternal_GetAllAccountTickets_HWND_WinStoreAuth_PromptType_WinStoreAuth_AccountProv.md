# WinStoreAuth::AuthenticationInternal::GetAllAccountTickets(HWND__ *,WinStoreAuth::PromptType,WinStoreAuth::AccountProviderType,bool,WinStoreAuth::TicketHolder * *,unsigned __int64 *,Windows::Foundation::Collections::IVector<IInspectable *> * *,bool)

- ea: `0x18003bf58`
- end: `0x18003c276`
- name: `?GetAllAccountTickets@AuthenticationInternal@WinStoreAuth@@YAJPEAUHWND__@@W4PromptType@2@W4AccountProviderType@2@_NPEAPEAUTicketHolder@2@PEA_KPEAPEAU?$IVector@PEAUIInspectable@@@Collections@Foundation@Windows@@3@Z`
- size: `798`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012e10`

## callees

- `0x180004738`
- `0x18000aba8`
- `0x18002b3f0`
- `0x180037440`
- `0x18003bf58`
- `0x18003c27c`
- `0x18003c298`
- `0x180044c08`
- `0x180061c04`
- `0x180068944`
- `0x18006a520`
- `0x18007633c`
- `0x18008a17c`
- `0x1800a54ec`
- `0x1800a5984`
- `0x1800a6df0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c0aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c0bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c0fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c109`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c11e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c15e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c196`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c0aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c0bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c0fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c109`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c11e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c15e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c196`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall WinStoreAuth::AuthenticationInternal::GetAllAccountTickets(
        HSTRING a1,
        __int64 a2,
        int a3,
        __int64 a4,
        HSTRING string,
        unsigned __int64 a6,
        HSTRING *a7)
{
  HSTRING v8; // r12
  _QWORD *v9; // r15
  int v10; // ebx
  unsigned __int64 v11; // r8
  void *v12; // rax
  HSTRING v13; // rdi
  int v14; // edx
  int v15; // ecx
  __int64 v16; // rdx
  int v17; // r14d
  void *v18; // rcx
  WinStoreAuth::AuthenticationInternal *v19; // rcx
  void *v20; // rbx
  HSTRING *v21; // r8
  int AllXTokens; // eax
  __int64 v23; // rdx
  HSTRING *v24; // rbx
  void *v25; // rbx
  HSTRING *v26; // rdx
  int v27; // edi
  int AccountTicketsFromTokenBroker; // eax
  UINT32 v29; // edx
  HSTRING v30; // rcx
  int AADFromRegistry; // eax
  struct WinStoreAuth::TicketHolder **v32; // rcx
  HSTRING v33; // rcx
  int v35; // [rsp+20h] [rbp-38h]
  int v36; // [rsp+20h] [rbp-38h]
  void *v37; // [rsp+40h] [rbp-18h] BYREF
  struct WinStoreAuth::TicketHolder **v38; // [rsp+48h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+40h]
  HSTRING v40; // [rsp+A0h] [rbp+48h] BYREF

  v40 = a1;
  v37 = 0;
  v38 = 0;
  v8 = string;
  *(_QWORD *)string = 0;
  v9 = (_QWORD *)a6;
  *(_QWORD *)a6 = 0;
  if ( a3 != 4 )
  {
    v40 = 0;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v40);
    v40 = 0;
    string = 0;
    v12 = operator new(0x70u, (const struct std::nothrow_t *)std::nothrow);
    a6 = (unsigned __int64)v12;
    v13 = 0;
    if ( v12 )
    {
      v13 = (HSTRING)Windows::Foundation::Collections::Internal::Impl::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<IInspectable *>>::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<IInspectable *>>(v12);
      string = v13;
      a6 = 0;
    }
    Microsoft::WRL::Details::MakeAllocator<UserSigninChangeWatcher>::~MakeAllocator<UserSigninChangeWatcher>(&a6);
    if ( v13 )
    {
      v10 = 0;
      string = 0;
      v40 = v13;
    }
    else
    {
      v10 = -2147024882;
    }
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&string);
    if ( v10 < 0 )
    {
      v16 = 721;
LABEL_10:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v16,
        (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
        (const char *)(unsigned int)v10,
        v35);
LABEL_11:
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v40);
      goto LABEL_37;
    }
    v17 = 0;
    if ( (a3 & 8) != 0 )
    {
      v37 = 0;
      a6 = 0;
      v10 = ULongLongMult(1u, 0x18u, &a6);
      if ( v10 < 0 || (v10 = CTCoAllocPolicy::Alloc(v18, 1u, a6, &v37), v10 < 0) )
      {
        v16 = 731;
        goto LABEL_10;
      }
      string = 0;
      if ( WinStoreAuth::AuthenticationInternal::IsPlatformXbox(v19) )
      {
        WindowsDeleteString(string);
        string = 0;
        v20 = v37;
        WindowsDeleteString(*((HSTRING *)v37 + 1));
        *((_QWORD *)v20 + 1) = 0;
        AllXTokens = WinStoreAuth::AuthenticationInternal::GetAllXTokens((HSTRING *)v20 + 1, &string, v21);
        v10 = AllXTokens;
        if ( AllXTokens < 0 )
        {
          v23 = 737;
LABEL_18:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v23,
            (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
            (const char *)(unsigned int)AllXTokens,
            v35);
          WindowsDeleteString(string);
          string = 0;
          goto LABEL_11;
        }
      }
      else
      {
        WindowsDeleteString(string);
        string = 0;
        v24 = (HSTRING *)((char *)v37 + 8);
        WindowsDeleteString(*((HSTRING *)v37 + 1));
        *v24 = 0;
        AllXTokens = WinStoreAuth::AuthenticationInternal::GetXToken(0, 0, 0, 0, 0, v24, &string);
        v10 = AllXTokens;
        if ( AllXTokens < 0 )
        {
          v23 = 742;
          goto LABEL_18;
        }
        v25 = v37;
        WindowsDeleteString(*((HSTRING *)v37 + 2));
        *((_QWORD *)v25 + 2) = 0;
        AllXTokens = WinStoreAuth::AuthenticationInternal::FetchXboxLiveAccountId((HSTRING *)v25 + 2, v26);
        v10 = AllXTokens;
        if ( AllXTokens < 0 )
        {
          v23 = 743;
          goto LABEL_18;
        }
      }
      v27 = 0;
      *(_DWORD *)v37 = 8;
      v38 = (struct WinStoreAuth::TicketHolder **)1;
      WindowsDeleteString(string);
    }
    else
    {
      AccountTicketsFromTokenBroker = WinStoreAuth::GetAccountTicketsFromTokenBroker(v15, v14, a3, (int)&v40, &v37);
      v27 = AccountTicketsFromTokenBroker;
      v30 = (HSTRING)retaddr;
      if ( AccountTicketsFromTokenBroker < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x2EF,
          (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
          (const char *)(unsigned int)AccountTicketsFromTokenBroker,
          v36);
      if ( (a3 & 2) != 0 )
      {
        AADFromRegistry = WinStoreAuth::GetAADFromRegistry(v30, v29, &v40, &v37);
        v17 = AADFromRegistry;
        if ( AADFromRegistry < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x2F3,
            (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
            (const char *)(unsigned int)AADFromRegistry,
            v36);
      }
    }
    v32 = v38;
    if ( v38 )
    {
      *(_QWORD *)v8 = v37;
      *v9 = v32;
      v37 = 0;
      v38 = 0;
    }
    v33 = v40;
    v40 = 0;
    *a7 = v33;
    if ( *v9 )
    {
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v40);
      v10 = 0;
      goto LABEL_37;
    }
    v10 = v17;
    if ( v27 < 0 )
      v10 = v27;
    goto LABEL_11;
  }
  v10 = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2CD,
    (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
    (const char *)0x80070057LL,
    v35);
LABEL_37:
  WinStoreAuth::AuthenticationInternal::FreeTicketHolderArray((WinStoreAuth::AuthenticationInternal *)&v37, v38, v11);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18003bf58  mov     [rsp-40h+arg_0], rcx
0x18003bf5d  push    rbp
0x18003bf5e  push    rbx
0x18003bf5f  push    rsi
0x18003bf60  push    rdi
0x18003bf61  push    r12
0x18003bf63  push    r13
0x18003bf65  push    r14
0x18003bf67  push    r15
0x18003bf69  mov     rbp, rsp
0x18003bf6c  sub     rsp, 58h
0x18003bf70  mov     esi, r8d
0x18003bf73  xor     r13d, r13d
0x18003bf76  mov     [rbp+var_18], r13
0x18003bf7a  mov     [rbp+var_10], r13
0x18003bf7e  mov     r12, [rbp+string]
0x18003bf82  mov     [r12], r13
0x18003bf86  mov     r15, [rbp+arg_28]
0x18003bf8a  mov     [r15], r13
0x18003bf8d  cmp     r8d, 4
0x18003bf91  jnz     short loc_18003BFB5
0x18003bf93  mov     rcx, [rbp+40h]; this
0x18003bf97  mov     ebx, 80070057h
0x18003bf9c  mov     r9d, ebx; char *
0x18003bf9f  lea     r8, aOnecoreuapEndu_4; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003bfa6  mov     edx, 2CDh; void *
0x18003bfab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003bfb0  jmp     loc_18003C256
0x18003bfb5  mov     [rbp+arg_0], r13
0x18003bfb9  lea     rcx, [rbp+arg_0]
0x18003bfbd  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003bfc2  mov     [rbp+arg_0], r13
0x18003bfc6  mov     [rbp+string], r13
0x18003bfca  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003bfd1  mov     ecx, 70h ; 'p'; unsigned __int64
0x18003bfd6  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003bfdb  mov     [rbp+arg_28], rax
0x18003bfdf  mov     rdi, r13
0x18003bfe2  test    rax, rax
0x18003bfe5  jz      short loc_18003BFFA
0x18003bfe7  mov     rcx, rax
0x18003bfea  call    ??0?$Vector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@U?$DefaultVectorOptions@PEAUIInspectable@@@3456@@Impl@Internal@Collections@Foundation@Windows@@QEAA@AEBU?$DefaultEqualityPredicate@PEAUIInspectable@@@2345@Upermission@012345@@Z; Windows::Foundation::Collections::Internal::Impl::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<IInspectable *>>::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<IInspectable *>>(Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *> const &,Windows::Foundation::Collections::Internal::Impl::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<IInspectable *>>::permission)
0x18003bfef  mov     rdi, rax
0x18003bff2  mov     [rbp+string], rax
0x18003bff6  mov     [rbp+arg_28], r13
0x18003bffa  lea     rcx, [rbp+arg_28]
0x18003bffe  call    ??1?$MakeAllocator@VUserSigninChangeWatcher@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<UserSigninChangeWatcher>::~MakeAllocator<UserSigninChangeWatcher>(void)
0x18003c003  test    rdi, rdi
0x18003c006  jz      short loc_18003C015
0x18003c008  mov     ebx, r13d
0x18003c00b  mov     [rbp+string], r13
0x18003c00f  mov     [rbp+arg_0], rdi
0x18003c013  jmp     short loc_18003C01A
0x18003c015  mov     ebx, 8007000Eh
0x18003c01a  lea     rcx, [rbp+string]
0x18003c01e  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003c023  test    ebx, ebx
0x18003c025  jns     short loc_18003C04E
0x18003c027  mov     edx, 2D1h; void *
0x18003c02c  lea     r8, aOnecoreuapEndu_4; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003c033  mov     r9d, ebx; char *
0x18003c036  mov     rcx, [rbp+40h]; this
0x18003c03a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c03f  nop
0x18003c040  lea     rcx, [rbp+arg_0]
0x18003c044  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003c049  jmp     loc_18003C256
0x18003c04e  mov     r14d, r13d
0x18003c051  test    sil, 8
0x18003c055  jz      loc_18003C1A8
0x18003c05b  mov     [rbp+var_18], r13
0x18003c05f  mov     [rbp+arg_28], r13
0x18003c063  lea     r8, [rbp+arg_28]; unsigned __int64 *
0x18003c067  mov     edx, 18h; unsigned __int64
0x18003c06c  lea     esi, [rdx-17h]
0x18003c06f  mov     ecx, esi; unsigned __int64
0x18003c071  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18003c076  mov     ebx, eax
0x18003c078  test    eax, eax
0x18003c07a  js      loc_18003C19E
0x18003c080  lea     r9, [rbp+var_18]; void **
0x18003c084  mov     r8, [rbp+arg_28]; unsigned __int64
0x18003c088  mov     edx, esi; unsigned int
0x18003c08a  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18003c08f  mov     ebx, eax
0x18003c091  test    eax, eax
0x18003c093  js      loc_18003C19E
0x18003c099  mov     [rbp+string], r13
0x18003c09d  call    ?IsPlatformXbox@AuthenticationInternal@WinStoreAuth@@YA_NXZ; WinStoreAuth::AuthenticationInternal::IsPlatformXbox(void)
0x18003c0a2  mov     rcx, [rbp+string]; string
0x18003c0a6  test    al, al
0x18003c0a8  jz      short loc_18003C109
0x18003c0aa  call    cs:__imp_WindowsDeleteString
0x18003c0b0  mov     [rbp+string], r13
0x18003c0b4  mov     rbx, [rbp+var_18]
0x18003c0b8  mov     rcx, [rbx+8]; string
0x18003c0bc  call    cs:__imp_WindowsDeleteString
0x18003c0c2  mov     [rbx+8], r13
0x18003c0c6  lea     rdx, [rbp+string]; HSTRING *
0x18003c0ca  lea     rcx, [rbx+8]; string
0x18003c0ce  call    ?GetAllXTokens@AuthenticationInternal@WinStoreAuth@@YAJPEAPEAUHSTRING__@@0@Z; WinStoreAuth::AuthenticationInternal::GetAllXTokens(HSTRING__ * *,HSTRING__ * *)
0x18003c0d3  mov     ebx, eax
0x18003c0d5  test    eax, eax
0x18003c0d7  jns     loc_18003C181
0x18003c0dd  mov     edx, 2E1h; void *
0x18003c0e2  mov     rcx, [rbp+40h]; this
0x18003c0e6  mov     r9d, eax; char *
0x18003c0e9  lea     r8, aOnecoreuapEndu_4; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003c0f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c0f5  nop
0x18003c0f6  mov     rcx, [rbp+string]; string
0x18003c0fa  call    cs:__imp_WindowsDeleteString
0x18003c100  mov     [rbp+string], r13
0x18003c104  jmp     loc_18003C040
0x18003c109  call    cs:__imp_WindowsDeleteString
0x18003c10f  mov     [rbp+string], r13
0x18003c113  mov     rbx, [rbp+var_18]
0x18003c117  add     rbx, 8
0x18003c11b  mov     rcx, [rbx]; string
0x18003c11e  call    cs:__imp_WindowsDeleteString
0x18003c124  mov     [rbx], r13
0x18003c127  lea     rax, [rbp+string]
0x18003c12b  mov     [rsp+58h+var_28], rax
0x18003c130  mov     [rsp+58h+var_30], rbx
0x18003c135  mov     [rsp+58h+var_38], r13
0x18003c13a  xor     r9d, r9d
0x18003c13d  xor     r8d, r8d
0x18003c140  xor     edx, edx
0x18003c142  xor     ecx, ecx
0x18003c144  call    ?GetXToken@AuthenticationInternal@WinStoreAuth@@YAJPEAUHWND__@@W4PromptType@2@PEAUHSTRING__@@2PEAUIUser@System@Windows@@PEAPEAU5@4@Z; WinStoreAuth::AuthenticationInternal::GetXToken(HWND__ *,WinStoreAuth::PromptType,HSTRING__ *,HSTRING__ *,Windows::System::IUser *,HSTRING__ * *,HSTRING__ * *)
0x18003c149  mov     ebx, eax
0x18003c14b  test    eax, eax
0x18003c14d  jns     short loc_18003C156
0x18003c14f  mov     edx, 2E6h
0x18003c154  jmp     short loc_18003C0E2
0x18003c156  mov     rbx, [rbp+var_18]
0x18003c15a  mov     rcx, [rbx+10h]; string
0x18003c15e  call    cs:__imp_WindowsDeleteString
0x18003c164  mov     [rbx+10h], r13
0x18003c168  lea     rcx, [rbx+10h]; string
0x18003c16c  call    ?FetchXboxLiveAccountId@AuthenticationInternal@WinStoreAuth@@YAJPEAPEAUHSTRING__@@@Z; WinStoreAuth::AuthenticationInternal::FetchXboxLiveAccountId(HSTRING__ * *)
0x18003c171  mov     ebx, eax
0x18003c173  test    eax, eax
0x18003c175  jns     short loc_18003C181
0x18003c177  mov     edx, 2E7h
0x18003c17c  jmp     loc_18003C0E2
0x18003c181  mov     edi, r13d
0x18003c184  mov     rax, [rbp+var_18]
0x18003c188  mov     dword ptr [rax], 8
0x18003c18e  mov     [rbp+var_10], rsi
0x18003c192  mov     rcx, [rbp+string]; string
0x18003c196  call    cs:__imp_WindowsDeleteString
0x18003c19c  jmp     short loc_18003C20D
0x18003c19e  mov     edx, 2DBh
0x18003c1a3  jmp     loc_18003C02C
0x18003c1a8  lea     rax, [rbp+var_18]
0x18003c1ac  mov     [rsp+58h+var_38], rax; int
0x18003c1b1  lea     r9, [rbp+arg_0]; int
0x18003c1b5  mov     r8d, esi; int
0x18003c1b8  call    ?GetAccountTicketsFromTokenBroker@WinStoreAuth@@YAJPEAUHWND__@@W4PromptType@1@W4AccountProviderType@1@AEBV?$ComPtr@V?$Vector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@U?$DefaultVectorOptions@PEAUIInspectable@@@3456@@Impl@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@AEAUTicketsHolder@1@@Z; WinStoreAuth::GetAccountTicketsFromTokenBroker(HWND__ *,WinStoreAuth::PromptType,WinStoreAuth::AccountProviderType,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::Impl::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<IInspectable *>>> const &,WinStoreAuth::TicketsHolder &)
0x18003c1bd  mov     edi, eax
0x18003c1bf  mov     rcx, [rbp+40h]; this
0x18003c1c3  test    eax, eax
0x18003c1c5  jns     short loc_18003C1DB
0x18003c1c7  mov     r9d, eax; char *
0x18003c1ca  lea     r8, aOnecoreuapEndu_4; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003c1d1  mov     edx, 2EFh; void *
0x18003c1d6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003c1db  test    sil, 2
0x18003c1df  jz      short loc_18003C20D
0x18003c1e1  lea     r9, [rbp+var_18]
0x18003c1e5  lea     r8, [rbp+arg_0]
0x18003c1e9  call    ?GetAADFromRegistry@WinStoreAuth@@YAJPEAUHWND__@@W4PromptType@1@AEBV?$ComPtr@V?$Vector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@U?$DefaultVectorOptions@PEAUIInspectable@@@3456@@Impl@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@AEAUTicketsHolder@1@@Z; WinStoreAuth::GetAADFromRegistry(HWND__ *,WinStoreAuth::PromptType,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::Impl::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<IInspectable *>>> const &,WinStoreAuth::TicketsHolder &)
0x18003c1ee  mov     r14d, eax
0x18003c1f1  mov     rcx, [rbp+40h]; this
0x18003c1f5  test    eax, eax
0x18003c1f7  jns     short loc_18003C20D
0x18003c1f9  mov     r9d, eax; char *
0x18003c1fc  lea     r8, aOnecoreuapEndu_4; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003c203  mov     edx, 2F3h; void *
0x18003c208  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003c20d  mov     rcx, [rbp+var_10]
0x18003c211  test    rcx, rcx
0x18003c214  jz      short loc_18003C229
0x18003c216  mov     rax, [rbp+var_18]
0x18003c21a  mov     [r12], rax
0x18003c21e  mov     [r15], rcx
0x18003c221  mov     [rbp+var_18], r13
0x18003c225  mov     [rbp+var_10], r13
0x18003c229  mov     rcx, [rbp+arg_0]
0x18003c22d  mov     [rbp+arg_0], r13
0x18003c231  mov     rax, [rbp+arg_30]
0x18003c235  mov     [rax], rcx
0x18003c238  cmp     [r15], r13
0x18003c23b  jnz     short loc_18003C24A
0x18003c23d  mov     ebx, r14d
0x18003c240  test    edi, edi
0x18003c242  cmovs   ebx, edi
0x18003c245  jmp     loc_18003C040
0x18003c24a  lea     rcx, [rbp+arg_0]
0x18003c24e  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003c253  mov     ebx, r13d
0x18003c256  mov     rdx, [rbp+var_10]; struct WinStoreAuth::TicketHolder **
0x18003c25a  lea     rcx, [rbp+var_18]; this
0x18003c25e  call    ?FreeTicketHolderArray@AuthenticationInternal@WinStoreAuth@@YAXPEAPEAUTicketHolder@2@_K@Z; WinStoreAuth::AuthenticationInternal::FreeTicketHolderArray(WinStoreAuth::TicketHolder * *,unsigned __int64)
0x18003c263  mov     eax, ebx
0x18003c265  add     rsp, 58h
0x18003c269  pop     r15
0x18003c26b  pop     r14
0x18003c26d  pop     r13
0x18003c26f  pop     r12
0x18003c271  pop     rdi
0x18003c272  pop     rsi
0x18003c273  pop     rbx
0x18003c274  pop     rbp
0x18003c275  retn
```
