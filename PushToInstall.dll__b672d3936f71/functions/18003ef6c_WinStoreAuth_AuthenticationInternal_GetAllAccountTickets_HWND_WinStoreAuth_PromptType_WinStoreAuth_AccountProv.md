# WinStoreAuth::AuthenticationInternal::GetAllAccountTickets(HWND__ *,WinStoreAuth::PromptType,WinStoreAuth::AccountProviderType,bool,WinStoreAuth::TicketHolder * *,unsigned __int64 *,Windows::Foundation::Collections::IVector<IInspectable *> * *,bool)

- ea: `0x18003ef6c`
- end: `0x18003f2f4`
- name: `?GetAllAccountTickets@AuthenticationInternal@WinStoreAuth@@YAJPEAUHWND__@@W4PromptType@2@W4AccountProviderType@2@_NPEAPEAUTicketHolder@2@PEA_KPEAPEAU?$IVector@PEAUIInspectable@@@Collections@Foundation@Windows@@3@Z`
- size: `904`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180035e4c`
- `0x180036174`

## callees

- `0x18000d7a0`
- `0x180010b84`
- `0x180021734`
- `0x1800398a8`
- `0x18003a3e0`
- `0x18003d17c`
- `0x18003da10`
- `0x18003dcbc`
- `0x18003ebd8`
- `0x18003ef6c`
- `0x18003f6c4`
- `0x1800418e4`
- `0x180042640`
- `0x18004f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f0d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f0e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f127`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f150`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f165`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f1b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f1e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f21a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f258`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f0d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f0e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f127`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f150`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f165`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f1b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f1e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f21a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f258`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall WinStoreAuth::AuthenticationInternal::GetAllAccountTickets(
        __int64 a1,
        __int64 a2,
        int a3,
        char a4,
        HSTRING string,
        struct WinStoreAuth::TicketHolder ***a6,
        __int64 *a7)
{
  HSTRING v9; // r12
  struct WinStoreAuth::TicketHolder ***v10; // r14
  void *v11; // rax
  int v12; // edx
  IMalloc *v13; // rcx
  __int64 v14; // rax
  int v15; // ebx
  unsigned __int64 v16; // r8
  __int64 v17; // rcx
  int v18; // edi
  int AccountTicketsFromTokenBroker; // eax
  UINT32 v20; // edx
  int v21; // ebx
  HSTRING v22; // rcx
  int AADFromRegistry; // eax
  WinStoreAuth::AuthenticationInternal *v24; // rcx
  void *v25; // rbx
  HSTRING *v26; // r8
  int AllXTokens; // eax
  __int64 v28; // rcx
  HSTRING *v29; // rbx
  int XToken; // eax
  __int64 v31; // rcx
  void *v32; // rbx
  HSTRING *v33; // rdx
  int XboxLiveAccountId; // eax
  __int64 v35; // rcx
  struct WinStoreAuth::TicketHolder **v36; // rcx
  __int64 v37; // rcx
  __int64 v38; // rcx
  int v40; // [rsp+20h] [rbp-38h]
  int v41; // [rsp+20h] [rbp-38h]
  int v42; // [rsp+20h] [rbp-38h]
  void *v43; // [rsp+40h] [rbp-18h] BYREF
  struct WinStoreAuth::TicketHolder **v44; // [rsp+48h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+40h]
  __int64 v46; // [rsp+A0h] [rbp+48h] BYREF

  v43 = 0;
  v44 = 0;
  v9 = string;
  *(_QWORD *)string = 0;
  v10 = a6;
  *a6 = 0;
  v46 = 0;
  v11 = operator new(0x70u, (const struct std::nothrow_t *)std::nothrow);
  if ( v11
    && (v14 = Windows::Foundation::Collections::Internal::Impl::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<IInspectable *>>::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<IInspectable *>>(v11)) != 0 )
  {
    v15 = 0;
    v46 = v14;
  }
  else
  {
    v15 = -2147024882;
  }
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2D1,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)v15,
      v40);
    v17 = v46;
    if ( v46 )
    {
      v46 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
    goto LABEL_42;
  }
  v18 = 0;
  if ( !a4 && (a3 & 8) == 0 )
  {
    AccountTicketsFromTokenBroker = WinStoreAuth::GetAccountTicketsFromTokenBroker((int)v13, v12, a3, (int)&v46, &v43);
    v21 = AccountTicketsFromTokenBroker;
    v22 = (HSTRING)retaddr;
    if ( AccountTicketsFromTokenBroker < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x2EF,
        (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
        (const char *)(unsigned int)AccountTicketsFromTokenBroker,
        v41);
    if ( (a3 & 2) != 0 )
    {
      AADFromRegistry = WinStoreAuth::GetAADFromRegistry(v22, v20, &v46, (__int64 *)&v43);
      v18 = AADFromRegistry;
      if ( AADFromRegistry < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x2F3,
          (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
          (const char *)(unsigned int)AADFromRegistry,
          v41);
    }
    goto LABEL_32;
  }
  v43 = 0;
  string = 0;
  if ( !is_mul_ok(1u, 0x18u) )
  {
    v15 = -2147024362;
LABEL_40:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2DB,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)v15,
      v40);
    v38 = v46;
    if ( v46 )
    {
      v46 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
    }
    goto LABEL_42;
  }
  v15 = CTCoAllocPolicy::Alloc(v13, (1 * (unsigned __int128)0x18uLL) >> 64, 0x18u, &v43);
  if ( v15 < 0 )
    goto LABEL_40;
  string = 0;
  if ( WinStoreAuth::AuthenticationInternal::IsPlatformXbox(v24) )
  {
    WindowsDeleteString(string);
    string = 0;
    v25 = v43;
    WindowsDeleteString(*((HSTRING *)v43 + 1));
    *((_QWORD *)v25 + 1) = 0;
    AllXTokens = WinStoreAuth::AuthenticationInternal::GetAllXTokens((HSTRING *)v25 + 1, &string, v26);
    v15 = AllXTokens;
    if ( AllXTokens < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2E1,
        (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
        (const char *)(unsigned int)AllXTokens,
        v40);
      WindowsDeleteString(string);
      string = 0;
      v28 = v46;
      if ( v46 )
      {
        v46 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
      }
      goto LABEL_42;
    }
LABEL_31:
    v21 = 0;
    *(_DWORD *)v43 = 8;
    v44 = (struct WinStoreAuth::TicketHolder **)1;
    WindowsDeleteString(string);
LABEL_32:
    v36 = v44;
    if ( v44 )
    {
      *(_QWORD *)v9 = v43;
      *v10 = v36;
      v43 = 0;
      v44 = 0;
    }
    v37 = v46;
    v46 = 0;
    *a7 = v37;
    if ( *v10 )
    {
      v15 = 0;
    }
    else
    {
      if ( v21 < 0 )
        v18 = v21;
      v15 = v18;
    }
    goto LABEL_42;
  }
  WindowsDeleteString(string);
  string = 0;
  v29 = (HSTRING *)((char *)v43 + 8);
  WindowsDeleteString(*((HSTRING *)v43 + 1));
  *v29 = 0;
  XToken = WinStoreAuth::AuthenticationInternal::GetXToken(0, 0, 0, 0, 0, v29, &string);
  v15 = XToken;
  if ( XToken >= 0 )
  {
    v32 = v43;
    WindowsDeleteString(*((HSTRING *)v43 + 2));
    *((_QWORD *)v32 + 2) = 0;
    XboxLiveAccountId = WinStoreAuth::AuthenticationInternal::FetchXboxLiveAccountId((HSTRING *)v32 + 2, v33);
    v15 = XboxLiveAccountId;
    if ( XboxLiveAccountId >= 0 )
      goto LABEL_31;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2E7,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)XboxLiveAccountId,
      v42);
    WindowsDeleteString(string);
    string = 0;
    v35 = v46;
    if ( v46 )
    {
      v46 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2E6,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)XToken,
      v42);
    WindowsDeleteString(string);
    string = 0;
    v31 = v46;
    if ( v46 )
    {
      v46 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    }
  }
LABEL_42:
  WinStoreAuth::AuthenticationInternal::FreeTicketHolderArray((WinStoreAuth::AuthenticationInternal *)&v43, v44, v16);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18003ef6c  mov     [rsp-40h+arg_0], rcx
0x18003ef71  push    rbp
0x18003ef72  push    rbx
0x18003ef73  push    rsi
0x18003ef74  push    rdi
0x18003ef75  push    r12
0x18003ef77  push    r13
0x18003ef79  push    r14
0x18003ef7b  push    r15
0x18003ef7d  mov     rbp, rsp
0x18003ef80  sub     rsp, 58h
0x18003ef84  mov     r15b, r9b
0x18003ef87  mov     esi, r8d
0x18003ef8a  xor     r13d, r13d
0x18003ef8d  mov     [rbp+var_18], r13
0x18003ef91  mov     [rbp+var_10], r13
0x18003ef95  mov     r12, [rbp+string]
0x18003ef99  mov     [r12], r13
0x18003ef9d  mov     r14, [rbp+arg_28]
0x18003efa1  mov     [r14], r13
0x18003efa4  mov     [rbp+arg_0], r13
0x18003efa8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003efaf  lea     ecx, [r13+70h]; unsigned __int64
0x18003efb3  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003efb8  test    rax, rax
0x18003efbb  jz      short loc_18003EFD4
0x18003efbd  mov     rcx, rax
0x18003efc0  call    ??0?$Vector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@U?$DefaultVectorOptions@PEAUIInspectable@@@3456@@Impl@Internal@Collections@Foundation@Windows@@QEAA@AEBU?$DefaultEqualityPredicate@PEAUIInspectable@@@2345@Upermission@012345@@Z; Windows::Foundation::Collections::Internal::Impl::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<IInspectable *>>::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<IInspectable *>>(Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *> const &,Windows::Foundation::Collections::Internal::Impl::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<IInspectable *>>::permission)
0x18003efc5  nop
0x18003efc6  test    rax, rax
0x18003efc9  jz      short loc_18003EFD4
0x18003efcb  mov     ebx, r13d
0x18003efce  mov     [rbp+arg_0], rax
0x18003efd2  jmp     short loc_18003EFD9
0x18003efd4  mov     ebx, 8007000Eh
0x18003efd9  test    ebx, ebx
0x18003efdb  jns     short loc_18003F015
0x18003efdd  mov     rcx, [rbp+40h]; this
0x18003efe1  mov     r9d, ebx; char *
0x18003efe4  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003efeb  mov     edx, 2D1h; void *
0x18003eff0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003eff5  nop
0x18003eff6  mov     rcx, [rbp+arg_0]
0x18003effa  test    rcx, rcx
0x18003effd  jz      short loc_18003F010
0x18003efff  mov     [rbp+arg_0], r13
0x18003f003  mov     rax, [rcx]
0x18003f006  mov     rax, [rax+10h]
0x18003f00a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f00f  nop
0x18003f010  jmp     loc_18003F2D4
0x18003f015  mov     edi, r13d
0x18003f018  test    r15b, r15b
0x18003f01b  jnz     short loc_18003F094
0x18003f01d  test    sil, 8
0x18003f021  jnz     short loc_18003F094
0x18003f023  lea     rax, [rbp+var_18]
0x18003f027  mov     [rsp+58h+var_38], rax; int
0x18003f02c  lea     r9, [rbp+arg_0]; int
0x18003f030  mov     r8d, esi; int
0x18003f033  call    ?GetAccountTicketsFromTokenBroker@WinStoreAuth@@YAJPEAUHWND__@@W4PromptType@1@W4AccountProviderType@1@AEBV?$ComPtr@V?$Vector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@U?$DefaultVectorOptions@PEAUIInspectable@@@3456@@Impl@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@AEAUTicketsHolder@1@@Z; WinStoreAuth::GetAccountTicketsFromTokenBroker(HWND__ *,WinStoreAuth::PromptType,WinStoreAuth::AccountProviderType,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::Impl::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<IInspectable *>>> const &,WinStoreAuth::TicketsHolder &)
0x18003f038  mov     ebx, eax
0x18003f03a  mov     rcx, [rbp+40h]; this
0x18003f03e  test    eax, eax
0x18003f040  jns     short loc_18003F056
0x18003f042  mov     r9d, eax; char *
0x18003f045  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003f04c  mov     edx, 2EFh; void *
0x18003f051  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003f056  test    sil, 2
0x18003f05a  jz      loc_18003F25E
0x18003f060  lea     r9, [rbp+var_18]
0x18003f064  lea     r8, [rbp+arg_0]
0x18003f068  call    ?GetAADFromRegistry@WinStoreAuth@@YAJPEAUHWND__@@W4PromptType@1@AEBV?$ComPtr@V?$Vector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@U?$DefaultVectorOptions@PEAUIInspectable@@@3456@@Impl@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@AEAUTicketsHolder@1@@Z; WinStoreAuth::GetAADFromRegistry(HWND__ *,WinStoreAuth::PromptType,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::Impl::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<IInspectable *>>> const &,WinStoreAuth::TicketsHolder &)
0x18003f06d  mov     edi, eax
0x18003f06f  mov     rcx, [rbp+40h]; this
0x18003f073  test    eax, eax
0x18003f075  jns     loc_18003F25E
0x18003f07b  mov     r9d, eax; char *
0x18003f07e  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003f085  mov     edx, 2F3h; void *
0x18003f08a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003f08f  jmp     loc_18003F25E
0x18003f094  mov     [rbp+var_18], r13
0x18003f098  mov     [rbp+string], r13
0x18003f09c  mov     esi, 1
0x18003f0a1  lea     eax, [rsi+17h]
0x18003f0a4  mul     rsi
0x18003f0a7  test    rdx, rdx
0x18003f0aa  jnz     loc_18003F29C
0x18003f0b0  lea     r9, [rbp+var_18]; void **
0x18003f0b4  mov     r8, rax; unsigned __int64
0x18003f0b7  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18003f0bc  mov     ebx, eax
0x18003f0be  test    eax, eax
0x18003f0c0  js      loc_18003F2A1
0x18003f0c6  mov     [rbp+string], r13
0x18003f0ca  call    ?IsPlatformXbox@AuthenticationInternal@WinStoreAuth@@YA_NXZ; WinStoreAuth::AuthenticationInternal::IsPlatformXbox(void)
0x18003f0cf  mov     rcx, [rbp+string]; string
0x18003f0d3  test    al, al
0x18003f0d5  jz      short loc_18003F150
0x18003f0d7  call    cs:__imp_WindowsDeleteString
0x18003f0dd  mov     [rbp+string], r13
0x18003f0e1  mov     rbx, [rbp+var_18]
0x18003f0e5  mov     rcx, [rbx+8]; string
0x18003f0e9  call    cs:__imp_WindowsDeleteString
0x18003f0ef  mov     [rbx+8], r13
0x18003f0f3  lea     rdx, [rbp+string]; HSTRING *
0x18003f0f7  lea     rcx, [rbx+8]; string
0x18003f0fb  call    ?GetAllXTokens@AuthenticationInternal@WinStoreAuth@@YAJPEAPEAUHSTRING__@@0@Z; WinStoreAuth::AuthenticationInternal::GetAllXTokens(HSTRING__ * *,HSTRING__ * *)
0x18003f100  mov     ebx, eax
0x18003f102  test    eax, eax
0x18003f104  jns     loc_18003F243
0x18003f10a  mov     rcx, [rbp+40h]; this
0x18003f10e  mov     r9d, eax; char *
0x18003f111  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003f118  mov     edx, 2E1h; void *
0x18003f11d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f122  nop
0x18003f123  mov     rcx, [rbp+string]; string
0x18003f127  call    cs:__imp_WindowsDeleteString
0x18003f12d  mov     [rbp+string], r13
0x18003f131  mov     rcx, [rbp+arg_0]
0x18003f135  test    rcx, rcx
0x18003f138  jz      short loc_18003F14B
0x18003f13a  mov     [rbp+arg_0], r13
0x18003f13e  mov     rax, [rcx]
0x18003f141  mov     rax, [rax+10h]
0x18003f145  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f14a  nop
0x18003f14b  jmp     loc_18003F2D4
0x18003f150  call    cs:__imp_WindowsDeleteString
0x18003f156  mov     [rbp+string], r13
0x18003f15a  mov     rbx, [rbp+var_18]
0x18003f15e  add     rbx, 8
0x18003f162  mov     rcx, [rbx]; string
0x18003f165  call    cs:__imp_WindowsDeleteString
0x18003f16b  mov     [rbx], r13
0x18003f16e  lea     rax, [rbp+string]
0x18003f172  mov     [rsp+58h+var_28], rax
0x18003f177  mov     [rsp+58h+var_30], rbx
0x18003f17c  mov     [rsp+58h+var_38], r13; int
0x18003f181  xor     r9d, r9d
0x18003f184  xor     r8d, r8d
0x18003f187  xor     edx, edx
0x18003f189  xor     ecx, ecx
0x18003f18b  call    ?GetXToken@AuthenticationInternal@WinStoreAuth@@YAJPEAUHWND__@@W4PromptType@2@PEAUHSTRING__@@2PEAUIUser@System@Windows@@PEAPEAU5@4@Z; WinStoreAuth::AuthenticationInternal::GetXToken(HWND__ *,WinStoreAuth::PromptType,HSTRING__ *,HSTRING__ *,Windows::System::IUser *,HSTRING__ * *,HSTRING__ * *)
0x18003f190  mov     ebx, eax
0x18003f192  test    eax, eax
0x18003f194  jns     short loc_18003F1DC
0x18003f196  mov     rcx, [rbp+40h]; this
0x18003f19a  mov     r9d, eax; char *
0x18003f19d  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003f1a4  mov     edx, 2E6h; void *
0x18003f1a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f1ae  nop
0x18003f1af  mov     rcx, [rbp+string]; string
0x18003f1b3  call    cs:__imp_WindowsDeleteString
0x18003f1b9  mov     [rbp+string], r13
0x18003f1bd  mov     rcx, [rbp+arg_0]
0x18003f1c1  test    rcx, rcx
0x18003f1c4  jz      short loc_18003F1D7
0x18003f1c6  mov     [rbp+arg_0], r13
0x18003f1ca  mov     rax, [rcx]
0x18003f1cd  mov     rax, [rax+10h]
0x18003f1d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f1d6  nop
0x18003f1d7  jmp     loc_18003F2D4
0x18003f1dc  mov     rbx, [rbp+var_18]
0x18003f1e0  mov     rcx, [rbx+10h]; string
0x18003f1e4  call    cs:__imp_WindowsDeleteString
0x18003f1ea  mov     [rbx+10h], r13
0x18003f1ee  lea     rcx, [rbx+10h]; string
0x18003f1f2  call    ?FetchXboxLiveAccountId@AuthenticationInternal@WinStoreAuth@@YAJPEAPEAUHSTRING__@@@Z; WinStoreAuth::AuthenticationInternal::FetchXboxLiveAccountId(HSTRING__ * *)
0x18003f1f7  mov     ebx, eax
0x18003f1f9  test    eax, eax
0x18003f1fb  jns     short loc_18003F243
0x18003f1fd  mov     rcx, [rbp+40h]; this
0x18003f201  mov     r9d, eax; char *
0x18003f204  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003f20b  mov     edx, 2E7h; void *
0x18003f210  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f215  nop
0x18003f216  mov     rcx, [rbp+string]; string
0x18003f21a  call    cs:__imp_WindowsDeleteString
0x18003f220  mov     [rbp+string], r13
0x18003f224  mov     rcx, [rbp+arg_0]
0x18003f228  test    rcx, rcx
0x18003f22b  jz      short loc_18003F23E
0x18003f22d  mov     [rbp+arg_0], r13
0x18003f231  mov     rax, [rcx]
0x18003f234  mov     rax, [rax+10h]
0x18003f238  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f23d  nop
0x18003f23e  jmp     loc_18003F2D4
0x18003f243  mov     ebx, r13d
0x18003f246  mov     rax, [rbp+var_18]
0x18003f24a  mov     dword ptr [rax], 8
0x18003f250  mov     [rbp+var_10], rsi
0x18003f254  mov     rcx, [rbp+string]; string
0x18003f258  call    cs:__imp_WindowsDeleteString
0x18003f25e  mov     rcx, [rbp+var_10]
0x18003f262  test    rcx, rcx
0x18003f265  jz      short loc_18003F27A
0x18003f267  mov     rax, [rbp+var_18]
0x18003f26b  mov     [r12], rax
0x18003f26f  mov     [r14], rcx
0x18003f272  mov     [rbp+var_18], r13
0x18003f276  mov     [rbp+var_10], r13
0x18003f27a  mov     rcx, [rbp+arg_0]
0x18003f27e  mov     [rbp+arg_0], r13
0x18003f282  mov     rax, [rbp+arg_30]
0x18003f286  mov     [rax], rcx
0x18003f289  cmp     [r14], r13
0x18003f28c  jnz     short loc_18003F297
0x18003f28e  test    ebx, ebx
0x18003f290  cmovs   edi, ebx
0x18003f293  mov     ebx, edi
0x18003f295  jmp     short loc_18003F2D4
0x18003f297  mov     ebx, r13d
0x18003f29a  jmp     short loc_18003F2D4
0x18003f29c  mov     ebx, 80070216h
0x18003f2a1  mov     rcx, [rbp+40h]; this
0x18003f2a5  mov     r9d, ebx; char *
0x18003f2a8  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003f2af  mov     edx, 2DBh; void *
0x18003f2b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f2b9  nop
0x18003f2ba  mov     rcx, [rbp+arg_0]
0x18003f2be  test    rcx, rcx
0x18003f2c1  jz      short loc_18003F2D4
0x18003f2c3  mov     [rbp+arg_0], r13
0x18003f2c7  mov     rax, [rcx]
0x18003f2ca  mov     rax, [rax+10h]
0x18003f2ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f2d3  nop
0x18003f2d4  mov     rdx, [rbp+var_10]; struct WinStoreAuth::TicketHolder **
0x18003f2d8  lea     rcx, [rbp+var_18]; this
0x18003f2dc  call    ?FreeTicketHolderArray@AuthenticationInternal@WinStoreAuth@@YAXPEAPEAUTicketHolder@2@_K@Z; WinStoreAuth::AuthenticationInternal::FreeTicketHolderArray(WinStoreAuth::TicketHolder * *,unsigned __int64)
0x18003f2e1  mov     eax, ebx
0x18003f2e3  add     rsp, 58h
0x18003f2e7  pop     r15
0x18003f2e9  pop     r14
0x18003f2eb  pop     r13
0x18003f2ed  pop     r12
0x18003f2ef  pop     rdi
0x18003f2f0  pop     rsi
0x18003f2f1  pop     rbx
0x18003f2f2  pop     rbp
0x18003f2f3  retn
```
