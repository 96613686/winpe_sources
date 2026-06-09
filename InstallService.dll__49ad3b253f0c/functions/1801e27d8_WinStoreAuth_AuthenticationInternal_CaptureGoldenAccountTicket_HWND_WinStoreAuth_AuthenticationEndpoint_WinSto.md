# WinStoreAuth::AuthenticationInternal::CaptureGoldenAccountTicket(HWND__ *,WinStoreAuth::AuthenticationEndpoint,WinStoreAuth::PromptType,Windows::System::IUser *,HSTRING__ * *,HSTRING__ * *,WinStoreAuth::AccountProviderType &,Windows::Security::Authentication::Web::Core::IWebTokenRequestResult * *)

- ea: `0x1801e27d8`
- end: `0x1801e2ae5`
- name: `?CaptureGoldenAccountTicket@AuthenticationInternal@WinStoreAuth@@YAJPEAUHWND__@@W4AuthenticationEndpoint@2@W4PromptType@2@PEAUIUser@System@Windows@@PEAPEAUHSTRING__@@4AEAW4AccountProviderType@2@PEAPEAUIWebTokenRequestResult@Core@Web@Authentication@Security@8@@Z`
- size: `781`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1801877e8`
- `0x1801e8568`
- `0x1801e8768`

## callees

- `0x1800101f4`
- `0x180010b74`
- `0x180012b48`
- `0x18007306c`
- `0x1801e27d8`
- `0x1801e33d0`
- `0x1801e3680`
- `0x1801ec208`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e293a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e2952`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e29e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e29fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e2a77`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e2a8f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e293a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e2952`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e29e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e29fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e2a77`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e2a8f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801e2970`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801e2a1a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801e2aad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801e2970`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801e2a1a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801e2aad`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WinStoreAuth::AuthenticationInternal::CaptureGoldenAccountTicket(
        __int64 a1,
        struct Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics **a2,
        __int64 a3,
        __int64 a4,
        _QWORD *a5,
        unsigned __int64 a6,
        _DWORD *a7,
        _QWORD *a8)
{
  _QWORD *v9; // r12
  _QWORD *v10; // r13
  __int64 v11; // r14
  int TokenBroker; // eax
  __int64 v13; // rdx
  __int64 v14; // rcx
  unsigned int v15; // ebx
  int v16; // eax
  void *v17; // rcx
  int v18; // esi
  int v19; // r8d
  int v20; // r9d
  int Tickets; // eax
  int v22; // r15d
  HSTRING *v23; // rbx
  unsigned __int64 v24; // r14
  unsigned __int64 k; // rsi
  _QWORD *v26; // rbx
  _QWORD *v27; // rcx
  __int64 v28; // rax
  __int64 v29; // rax
  HSTRING *v30; // rbx
  unsigned __int64 v31; // r14
  unsigned __int64 j; // rsi
  _QWORD *v33; // rbx
  HSTRING *v34; // rbx
  unsigned __int64 v35; // r15
  unsigned __int64 i; // r14
  _QWORD *v37; // rbx
  int v39; // [rsp+20h] [rbp-48h]
  int v40; // [rsp+20h] [rbp-48h]
  LPVOID pv; // [rsp+50h] [rbp-18h] BYREF
  unsigned __int64 v42; // [rsp+58h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+40h]
  __int64 v44; // [rsp+B0h] [rbp+48h] BYREF

  v44 = a1;
  v9 = a5;
  *a5 = 0;
  v10 = (_QWORD *)a6;
  *(_QWORD *)a6 = 0;
  *a7 = 0;
  v11 = (__int64)a8;
  *a8 = 0;
  a5 = 0;
  TokenBroker = WinStoreAuth::AuthenticationInternal::CreateTokenBroker((WinStoreAuth::AuthenticationInternal *)&a5, a2);
  v15 = TokenBroker;
  if ( TokenBroker >= 0 )
  {
    v44 = 0;
    v16 = WinStoreAuth::AuthenticationInternal::CreateGoldenAccountTokenRequest(v14, v13, a4, &v44);
    v15 = v16;
    if ( v16 >= 0 )
    {
      v42 = 0;
      pv = 0;
      a6 = 0;
      v18 = ULongLongMult(1u, 0x18u, &a6);
      if ( v18 < 0 || (v18 = CTCoAllocPolicy::Alloc(v17, 1u, a6, &pv), v18 < 0) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA13,
          (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
          (const char *)(unsigned int)v18,
          v39);
        v34 = (HSTRING *)pv;
        if ( pv )
        {
          v35 = v42;
          for ( i = 0; i < v35; v34 = (HSTRING *)pv )
          {
            WindowsDeleteString(v34[3 * i + 1]);
            v34[3 * i + 1] = 0;
            v37 = pv;
            WindowsDeleteString(*((HSTRING *)pv + 3 * i + 2));
            v37[3 * i++ + 2] = 0;
          }
          CoTaskMemFree(v34);
          pv = 0;
        }
        v42 = 0;
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v44);
        v15 = v18;
      }
      else
      {
        Tickets = WinStoreAuth::AuthenticationInternal::SendTokenRequestAndGetTickets(
                    (unsigned int)&a5,
                    (unsigned int)&v44,
                    v19,
                    v20,
                    0,
                    (__int64)pv,
                    1,
                    (__int64)&v42,
                    a4,
                    v11);
        v22 = Tickets;
        if ( Tickets >= 0 )
        {
          v27 = pv;
          *a7 = *(_DWORD *)pv;
          v28 = v27[1];
          v27[1] = 0;
          *v9 = v28;
          v29 = *((_QWORD *)pv + 2);
          *((_QWORD *)pv + 2) = 0;
          *v10 = v29;
          v30 = (HSTRING *)pv;
          if ( pv )
          {
            v31 = v42;
            for ( j = 0; j < v31; v30 = (HSTRING *)pv )
            {
              WindowsDeleteString(v30[3 * j + 1]);
              v30[3 * j + 1] = 0;
              v33 = pv;
              WindowsDeleteString(*((HSTRING *)pv + 3 * j + 2));
              v33[3 * j++ + 2] = 0;
            }
            CoTaskMemFree(v30);
            pv = 0;
          }
          v42 = 0;
          Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v44);
          v15 = 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xA14,
            (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
            (const char *)(unsigned int)Tickets,
            v40);
          v23 = (HSTRING *)pv;
          if ( pv )
          {
            v24 = v42;
            for ( k = 0; k < v24; v23 = (HSTRING *)pv )
            {
              WindowsDeleteString(v23[3 * k + 1]);
              v23[3 * k + 1] = 0;
              v26 = pv;
              WindowsDeleteString(*((HSTRING *)pv + 3 * k + 2));
              v26[3 * k++ + 2] = 0;
            }
            CoTaskMemFree(v23);
            pv = 0;
          }
          v42 = 0;
          Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v44);
          v15 = v22;
        }
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA10,
        (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
        (const char *)(unsigned int)v16,
        v39);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v44);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA0D,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)TokenBroker,
      v39);
  }
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&a5);
  return v15;
}

```

## disassembly

```asm
0x1801e27d8  mov     [rsp-40h+arg_0], rcx
0x1801e27dd  push    rbp
0x1801e27de  push    rbx
0x1801e27df  push    rsi
0x1801e27e0  push    rdi
0x1801e27e1  push    r12
0x1801e27e3  push    r13
0x1801e27e5  push    r14
0x1801e27e7  push    r15
0x1801e27e9  mov     rbp, rsp
0x1801e27ec  sub     rsp, 68h
0x1801e27f0  mov     rdi, r9
0x1801e27f3  xor     r15d, r15d
0x1801e27f6  mov     r12, [rbp+arg_20]
0x1801e27fa  mov     [r12], r15
0x1801e27fe  mov     r13, [rbp+arg_28]
0x1801e2802  mov     [r13+0], r15
0x1801e2806  mov     rax, [rbp+arg_30]
0x1801e280a  mov     [rax], r15d
0x1801e280d  mov     r14, [rbp+arg_38]
0x1801e2814  mov     [r14], r15
0x1801e2817  mov     [rbp+arg_20], r15
0x1801e281b  lea     rcx, [rbp+arg_20]; this
0x1801e281f  call    ?CreateTokenBroker@AuthenticationInternal@WinStoreAuth@@YAJPEAPEAUIWebAuthenticationCoreManagerStatics@Core@Web@Authentication@Security@Windows@@@Z; WinStoreAuth::AuthenticationInternal::CreateTokenBroker(Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics * *)
0x1801e2824  mov     ebx, eax
0x1801e2826  test    eax, eax
0x1801e2828  jns     short loc_1801E2847
0x1801e282a  mov     rcx, [rbp+40h]; this
0x1801e282e  mov     r9d, eax; char *
0x1801e2831  lea     r8, aOnecoreuapEndu_8; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x1801e2838  mov     edx, 0A0Dh; void *
0x1801e283d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e2842  jmp     loc_1801E2AC9
0x1801e2847  mov     [rbp+arg_0], r15
0x1801e284b  lea     r9, [rbp+arg_0]
0x1801e284f  mov     r8, rdi
0x1801e2852  call    ?CreateGoldenAccountTokenRequest@AuthenticationInternal@WinStoreAuth@@YAJW4AuthenticationEndpoint@2@W4PromptType@2@PEAUIUser@System@Windows@@PEAPEAUIWebTokenRequest@Core@Web@Authentication@Security@7@@Z; WinStoreAuth::AuthenticationInternal::CreateGoldenAccountTokenRequest(WinStoreAuth::AuthenticationEndpoint,WinStoreAuth::PromptType,Windows::System::IUser *,Windows::Security::Authentication::Web::Core::IWebTokenRequest * *)
0x1801e2857  mov     ebx, eax
0x1801e2859  test    eax, eax
0x1801e285b  jns     short loc_1801E2884
0x1801e285d  mov     rcx, [rbp+40h]; this
0x1801e2861  mov     r9d, eax; char *
0x1801e2864  lea     r8, aOnecoreuapEndu_8; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x1801e286b  mov     edx, 0A10h; void *
0x1801e2870  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e2875  nop
0x1801e2876  lea     rcx, [rbp+arg_0]
0x1801e287a  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1801e287f  jmp     loc_1801E2AC9
0x1801e2884  mov     [rbp+var_10], r15
0x1801e2888  mov     [rbp+pv], r15
0x1801e288c  mov     [rbp+arg_28], r15
0x1801e2890  lea     r8, [rbp+arg_28]; unsigned __int64 *
0x1801e2894  mov     edx, 18h; unsigned __int64
0x1801e2899  lea     ebx, [rdx-17h]
0x1801e289c  mov     ecx, ebx; unsigned __int64
0x1801e289e  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1801e28a3  mov     esi, eax
0x1801e28a5  test    eax, eax
0x1801e28a7  js      loc_1801E2A40
0x1801e28ad  lea     r9, [rbp+pv]; void **
0x1801e28b1  mov     r8, [rbp+arg_28]; unsigned __int64
0x1801e28b5  mov     edx, ebx; unsigned int
0x1801e28b7  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x1801e28bc  mov     esi, eax
0x1801e28be  test    eax, eax
0x1801e28c0  js      loc_1801E2A40
0x1801e28c6  mov     [rsp+68h+var_20], r14
0x1801e28cb  mov     [rsp+68h+var_28], rdi
0x1801e28d0  lea     rax, [rbp+var_10]
0x1801e28d4  mov     [rsp+68h+var_30], rax
0x1801e28d9  mov     [rsp+68h+var_38], rbx
0x1801e28de  mov     rax, [rbp+pv]
0x1801e28e2  mov     [rsp+68h+var_40], rax
0x1801e28e7  mov     qword ptr [rsp+68h+var_48], r15; int
0x1801e28ec  lea     rdx, [rbp+arg_0]
0x1801e28f0  lea     rcx, [rbp+arg_20]
0x1801e28f4  call    ?SendTokenRequestAndGetTickets@AuthenticationInternal@WinStoreAuth@@YAJAEBV?$ComPtr@UIWebAuthenticationCoreManagerStatics@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@AEBV?$ComPtr@UIWebTokenRequest@Core@Web@Authentication@Security@Windows@@@45@W4PromptType@2@PEAUHWND__@@PEAUIWebAccount@Credentials@Security@Windows@@PEAUTicketHolder@2@_KPEA_KPEAUIUser@System@Windows@@PEAPEAUIWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Z; WinStoreAuth::AuthenticationInternal::SendTokenRequestAndGetTickets(Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics> const &,Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebTokenRequest> const &,WinStoreAuth::PromptType,HWND__ *,Windows::Security::Credentials::IWebAccount *,WinStoreAuth::TicketHolder *,unsigned __int64,unsigned __int64 *,Windows::System::IUser *,Windows::Security::Authentication::Web::Core::IWebTokenRequestResult * *)
0x1801e28f9  mov     r15d, eax
0x1801e28fc  test    eax, eax
0x1801e28fe  jns     loc_1801E2997
0x1801e2904  mov     rcx, [rbp+40h]; this
0x1801e2908  mov     r9d, eax; char *
0x1801e290b  lea     r8, aOnecoreuapEndu_8; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x1801e2912  mov     edx, 0A14h; void *
0x1801e2917  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e291c  nop
0x1801e291d  mov     rbx, [rbp+pv]
0x1801e2921  test    rbx, rbx
0x1801e2924  jz      short loc_1801E297E
0x1801e2926  mov     r14, [rbp+var_10]
0x1801e292a  xor     esi, esi
0x1801e292c  test    r14, r14
0x1801e292f  jz      short loc_1801E296D
0x1801e2931  lea     rdi, [rsi+rsi*2]
0x1801e2935  mov     rcx, [rbx+rdi*8+8]; string
0x1801e293a  call    cs:__imp_WindowsDeleteString
0x1801e2940  mov     qword ptr [rbx+rdi*8+8], 0
0x1801e2949  mov     rbx, [rbp+pv]
0x1801e294d  mov     rcx, [rbx+rdi*8+10h]; string
0x1801e2952  call    cs:__imp_WindowsDeleteString
0x1801e2958  mov     qword ptr [rbx+rdi*8+10h], 0
0x1801e2961  inc     rsi
0x1801e2964  mov     rbx, [rbp+pv]
0x1801e2968  cmp     rsi, r14
0x1801e296b  jb      short loc_1801E2931
0x1801e296d  mov     rcx, rbx; pv
0x1801e2970  call    cs:__imp_CoTaskMemFree
0x1801e2976  mov     [rbp+pv], 0
0x1801e297e  mov     [rbp+var_10], 0
0x1801e2986  lea     rcx, [rbp+arg_0]
0x1801e298a  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1801e298f  mov     ebx, r15d
0x1801e2992  jmp     loc_1801E2AC9
0x1801e2997  mov     rcx, [rbp+pv]
0x1801e299b  mov     eax, [rcx]
0x1801e299d  mov     rdx, [rbp+arg_30]
0x1801e29a1  mov     [rdx], eax
0x1801e29a3  mov     rax, [rcx+8]
0x1801e29a7  mov     qword ptr [rcx+8], 0
0x1801e29af  mov     [r12], rax
0x1801e29b3  mov     rcx, [rbp+pv]
0x1801e29b7  mov     rax, [rcx+10h]
0x1801e29bb  mov     qword ptr [rcx+10h], 0
0x1801e29c3  mov     [r13+0], rax
0x1801e29c7  mov     rbx, [rbp+pv]
0x1801e29cb  test    rbx, rbx
0x1801e29ce  jz      short loc_1801E2A28
0x1801e29d0  mov     r14, [rbp+var_10]
0x1801e29d4  xor     esi, esi
0x1801e29d6  test    r14, r14
0x1801e29d9  jz      short loc_1801E2A17
0x1801e29db  lea     rdi, [rsi+rsi*2]
0x1801e29df  mov     rcx, [rbx+rdi*8+8]; string
0x1801e29e4  call    cs:__imp_WindowsDeleteString
0x1801e29ea  mov     qword ptr [rbx+rdi*8+8], 0
0x1801e29f3  mov     rbx, [rbp+pv]
0x1801e29f7  mov     rcx, [rbx+rdi*8+10h]; string
0x1801e29fc  call    cs:__imp_WindowsDeleteString
0x1801e2a02  mov     qword ptr [rbx+rdi*8+10h], 0
0x1801e2a0b  inc     rsi
0x1801e2a0e  mov     rbx, [rbp+pv]
0x1801e2a12  cmp     rsi, r14
0x1801e2a15  jb      short loc_1801E29DB
0x1801e2a17  mov     rcx, rbx; pv
0x1801e2a1a  call    cs:__imp_CoTaskMemFree
0x1801e2a20  mov     [rbp+pv], 0
0x1801e2a28  mov     [rbp+var_10], 0
0x1801e2a30  lea     rcx, [rbp+arg_0]
0x1801e2a34  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1801e2a39  xor     ebx, ebx
0x1801e2a3b  jmp     loc_1801E2AC9
0x1801e2a40  mov     rcx, [rbp+40h]; this
0x1801e2a44  mov     r9d, esi; char *
0x1801e2a47  lea     r8, aOnecoreuapEndu_8; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x1801e2a4e  mov     edx, 0A13h; void *
0x1801e2a53  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e2a58  nop
0x1801e2a59  mov     rbx, [rbp+pv]
0x1801e2a5d  test    rbx, rbx
0x1801e2a60  jz      short loc_1801E2ABA
0x1801e2a62  mov     r15, [rbp+var_10]
0x1801e2a66  xor     r14d, r14d
0x1801e2a69  test    r15, r15
0x1801e2a6c  jz      short loc_1801E2AAA
0x1801e2a6e  lea     rdi, [r14+r14*2]
0x1801e2a72  mov     rcx, [rbx+rdi*8+8]; string
0x1801e2a77  call    cs:__imp_WindowsDeleteString
0x1801e2a7d  mov     qword ptr [rbx+rdi*8+8], 0
0x1801e2a86  mov     rbx, [rbp+pv]
0x1801e2a8a  mov     rcx, [rbx+rdi*8+10h]; string
0x1801e2a8f  call    cs:__imp_WindowsDeleteString
0x1801e2a95  mov     qword ptr [rbx+rdi*8+10h], 0
0x1801e2a9e  inc     r14
0x1801e2aa1  mov     rbx, [rbp+pv]
0x1801e2aa5  cmp     r14, r15
0x1801e2aa8  jb      short loc_1801E2A6E
0x1801e2aaa  mov     rcx, rbx; pv
0x1801e2aad  call    cs:__imp_CoTaskMemFree
0x1801e2ab3  xor     r15d, r15d
0x1801e2ab6  mov     [rbp+pv], r15
0x1801e2aba  mov     [rbp+var_10], r15
0x1801e2abe  lea     rcx, [rbp+arg_0]
0x1801e2ac2  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1801e2ac7  mov     ebx, esi
0x1801e2ac9  lea     rcx, [rbp+arg_20]
0x1801e2acd  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1801e2ad2  mov     eax, ebx
0x1801e2ad4  add     rsp, 68h
0x1801e2ad8  pop     r15
0x1801e2ada  pop     r14
0x1801e2adc  pop     r13
0x1801e2ade  pop     r12
0x1801e2ae0  pop     rdi
0x1801e2ae1  pop     rsi
0x1801e2ae2  pop     rbx
0x1801e2ae3  pop     rbp
0x1801e2ae4  retn
```
