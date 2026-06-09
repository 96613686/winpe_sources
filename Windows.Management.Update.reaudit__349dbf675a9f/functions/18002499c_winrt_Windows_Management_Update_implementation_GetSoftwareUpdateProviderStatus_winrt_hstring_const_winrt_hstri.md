# winrt::Windows::Management::Update::implementation::GetSoftwareUpdateProviderStatus(winrt::hstring const &,winrt::hstring const &)

- ea: `0x18002499c`
- end: `0x180024b3c`
- name: `?GetSoftwareUpdateProviderStatus@implementation@Update@Management@Windows@winrt@@YA?AUWindowsSoftwareUpdateProviderStatus@2345@AEBUhstring@5@0@Z`
- size: `416`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180024600`

## callees

- `0x180002880`
- `0x180017c3c`
- `0x1800184d0`
- `0x18001d9e8`
- `0x18001e7a4`
- `0x18002499c`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180024a5c`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180024a5c`

## string_xrefs

- `0x180024b15`: `onecore\enduser\windowsupdate\muse\orchestrator\api\winrt\dll\windows.management.update.windowssoftwareupdateproviderstatus.cpp`
- `0x180024b2a`: `onecore\enduser\windowsupdate\muse\orchestrator\api\winrt\dll\windows.management.update.windowssoftwareupdateproviderstatus.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall winrt::Windows::Management::Update::implementation::GetSoftwareUpdateProviderStatus(
        _QWORD *a1,
        __int64 a2,
        __int64 a3)
{
  const unsigned __int16 *v6; // rdx
  const unsigned __int16 *v7; // r8
  int v8; // eax
  HRESULT v9; // eax
  int dwAuthnLevel; // [rsp+20h] [rbp-29h]
  IUnknown *pProxy; // [rsp+40h] [rbp-9h] BYREF
  LPVOID v13; // [rsp+48h] [rbp-1h] BYREF
  __int128 v14; // [rsp+78h] [rbp+2Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  v13 = a1;
  wil::CoCreateInstance<UpdateSessionOrchestrator,IMoUsoOrchestrator4,wil::err_exception_policy>(&v13);
  pProxy = 0;
  v14 = winrt::impl::uncloaked_iids<winrt::impl::interface_list<winrt::Windows::Management::Update::WindowsSoftwareUpdateProviderStatus>>::value;
  v6 = &dword_180030C44;
  if ( *(_QWORD *)a3 )
    v7 = *(const unsigned __int16 **)(*(_QWORD *)a3 + 16LL);
  else
    v7 = &dword_180030C44;
  if ( *(_QWORD *)a2 )
    v6 = *(const unsigned __int16 **)(*(_QWORD *)a2 + 16LL);
  v8 = (*(__int64 (__fastcall **)(LPVOID, const unsigned __int16 *, const unsigned __int16 *, __int128 *))(*(_QWORD *)v13 + 72LL))(
         v13,
         v6,
         v7,
         &v14);
  if ( v8 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x27,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\api\\winrt\\dll\\windows.management.update.wind"
                    "owssoftwareupdateproviderstatus.cpp",
      (const char *)(unsigned int)v8,
      (int)&pProxy);
  v9 = CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0);
  if ( v9 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x32,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\api\\winrt\\dll\\windows.management.update.wind"
                    "owssoftwareupdateproviderstatus.cpp",
      (const char *)(unsigned int)v9,
      dwAuthnLevel);
  *a1 = 0;
  if ( v13 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v13 + 16LL))(v13);
  return a1;
}

```

## disassembly

```asm
0x18002499c  mov     [rsp-8+arg_18], rbx
0x1800249a1  push    rbp
0x1800249a2  push    rsi
0x1800249a3  push    rdi
0x1800249a4  lea     rbp, [rsp-47h]
0x1800249a9  sub     rsp, 90h
0x1800249b0  mov     rax, cs:__security_cookie
0x1800249b7  xor     rax, rsp
0x1800249ba  mov     [rbp+57h+var_18], rax
0x1800249be  mov     rbx, r8
0x1800249c1  mov     rsi, rdx
0x1800249c4  mov     rdi, rcx
0x1800249c7  mov     [rbp+57h+var_58], rcx
0x1800249cb  lea     rcx, [rbp+57h+var_58]
0x1800249cf  call    ??$CoCreateInstance@VUpdateSessionOrchestrator@@UIMoUsoOrchestrator4@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UIMoUsoOrchestrator4@@Uerr_exception_policy@wil@@@0@K@Z; wil::CoCreateInstance<UpdateSessionOrchestrator,IMoUsoOrchestrator4,wil::err_exception_policy>(ulong)
0x1800249d4  nop
0x1800249d5  and     [rbp+57h+pProxy], 0
0x1800249da  movups  xmm0, cs:?value@?$uncloaked_iids@U?$interface_list@UWindowsSoftwareUpdateProviderStatus@Update@Management@Windows@winrt@@@impl@winrt@@@impl@winrt@@2V?$array@Uguid@winrt@@$00@std@@B; std::array<winrt::guid,1> const winrt::impl::uncloaked_iids<winrt::impl::interface_list<winrt::Windows::Management::Update::WindowsSoftwareUpdateProviderStatus>>::value
0x1800249e1  movdqu  [rbp+57h+var_28], xmm0
0x1800249e6  mov     rcx, [rbp+57h+var_58]
0x1800249ea  mov     rax, [rcx]
0x1800249ed  mov     r10, [rax+48h]
0x1800249f1  mov     r8, [rbx]
0x1800249f4  lea     rdx, dword_180030C44
0x1800249fb  test    r8, r8
0x1800249fe  jz      short loc_180024A06
0x180024a00  mov     r8, [r8+10h]
0x180024a04  jmp     short loc_180024A09
0x180024a06  mov     r8, rdx
0x180024a09  mov     rax, [rsi]
0x180024a0c  test    rax, rax
0x180024a0f  jz      short loc_180024A15
0x180024a11  mov     rdx, [rax+10h]
0x180024a15  lea     rax, [rbp+57h+pProxy]
0x180024a19  mov     qword ptr [rsp+0A0h+dwAuthnLevel], rax; int
0x180024a1e  lea     r9, [rbp+57h+var_28]
0x180024a22  mov     rax, r10
0x180024a25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024a2a  mov     rcx, [rbp+5Fh]; this
0x180024a2e  test    eax, eax
0x180024a30  js      loc_180024B12
0x180024a36  and     [rsp+0A0h+var_68], 0
0x180024a3b  and     [rsp+0A0h+var_70], 0
0x180024a41  mov     [rsp+0A0h+dwImpLevel], 3; dwImpLevel
0x180024a49  and     [rsp+0A0h+dwAuthnLevel], 0
0x180024a4e  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x180024a52  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x180024a55  mov     r8d, edx; dwAuthzSvc
0x180024a58  mov     rcx, [rbp+57h+pProxy]; pProxy
0x180024a5c  call    cs:__imp_CoSetProxyBlanket
0x180024a63  nop     dword ptr [rax+rax+00h]
0x180024a68  mov     rcx, [rbp+5Fh]; this
0x180024a6c  test    eax, eax
0x180024a6e  js      loc_180024B27
0x180024a74  mov     rax, [rbp+57h+pProxy]
0x180024a78  test    rax, rax
0x180024a7b  jnz     short loc_180024A82
0x180024a7d  and     [rdi], rax
0x180024a80  jmp     short loc_180024ABE
0x180024a82  and     [rbp+57h+var_50], 0
0x180024a87  and     [rbp+57h+var_40], 0
0x180024a8b  xorps   xmm0, xmm0
0x180024a8e  movdqu  [rbp+57h+var_38], xmm0
0x180024a93  mov     rcx, [rax]
0x180024a96  mov     r9, [rcx]
0x180024a99  lea     r8, [rbp+57h+var_50]
0x180024a9d  lea     rdx, ?value@?$uncloaked_iids@U?$interface_list@UWindowsSoftwareUpdateProviderStatus@Update@Management@Windows@winrt@@@impl@winrt@@@impl@winrt@@2V?$array@Uguid@winrt@@$00@std@@B; std::array<winrt::guid,1> const winrt::impl::uncloaked_iids<winrt::impl::interface_list<winrt::Windows::Management::Update::WindowsSoftwareUpdateProviderStatus>>::value
0x180024aa4  mov     rcx, rax
0x180024aa7  mov     rax, r9
0x180024aaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024aaf  test    eax, eax
0x180024ab1  js      short loc_180024B06
0x180024ab3  mov     rax, [rbp+57h+var_50]
0x180024ab7  mov     [rdi], rax
0x180024aba  mov     rax, [rbp+57h+pProxy]
0x180024abe  test    rax, rax
0x180024ac1  jz      short loc_180024ACD
0x180024ac3  lea     rcx, [rbp+57h+pProxy]
0x180024ac7  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180024acc  nop
0x180024acd  mov     rcx, [rbp+57h+var_58]
0x180024ad1  test    rcx, rcx
0x180024ad4  jz      short loc_180024AE3
0x180024ad6  mov     rdx, [rcx]
0x180024ad9  mov     rax, [rdx+10h]
0x180024add  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024ae2  nop
0x180024ae3  mov     rax, rdi
0x180024ae6  mov     rcx, [rbp+57h+var_18]
0x180024aea  xor     rcx, rsp; StackCookie
0x180024aed  call    __security_check_cookie
0x180024af2  mov     rbx, [rsp+0A0h+arg_18]
0x180024afa  add     rsp, 90h
0x180024b01  pop     rdi
0x180024b02  pop     rsi
0x180024b03  pop     rbp
0x180024b04  retn
0x180024b06  lea     rdx, [rbp+57h+var_40]
0x180024b0a  mov     ecx, eax
0x180024b0c  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180024b12  mov     r9d, eax; char *
0x180024b15  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180024b1c  mov     edx, 27h ; '''; void *
0x180024b21  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180024b27  mov     r9d, eax; char *
0x180024b2a  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180024b31  mov     edx, 32h ; '2'; void *
0x180024b36  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
