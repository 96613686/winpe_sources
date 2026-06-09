# winrt::Windows::Management::Update::implementation::GetSoftwareUpdateProviderStatus(winrt::hstring const &,winrt::hstring const &)

- ea: `0x1800236ec`
- end: `0x180023891`
- name: `?GetSoftwareUpdateProviderStatus@implementation@Update@Management@Windows@winrt@@YA?AUWindowsSoftwareUpdateProviderStatus@2345@AEBUhstring@5@0@Z`
- size: `421`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002333c`

## callees

- `0x1800028f0`
- `0x180016fe4`
- `0x180017800`
- `0x18001c7d4`
- `0x18001d50c`
- `0x1800236ec`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800237b8`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800237b8`

## string_xrefs

- `0x18002386a`: `onecore\enduser\windowsupdate\muse\orchestrator\api\winrt\dll\windows.management.update.windowssoftwareupdateproviderstatus.cpp`
- `0x18002387f`: `onecore\enduser\windowsupdate\muse\orchestrator\api\winrt\dll\windows.management.update.windowssoftwareupdateproviderstatus.cpp`

## pseudocode

```c
_QWORD *__fastcall winrt::Windows::Management::Update::implementation::GetSoftwareUpdateProviderStatus(
        _QWORD *a1,
        __int64 a2,
        __int64 a3)
{
  int *v6; // rdx
  int *v7; // r8
  int v8; // eax
  HRESULT v9; // eax
  int dwAuthnLevel; // [rsp+20h] [rbp-29h]
  IUnknown *pProxy; // [rsp+40h] [rbp-9h] BYREF
  _QWORD *v13; // [rsp+48h] [rbp-1h] BYREF
  __int128 v14; // [rsp+78h] [rbp+2Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  v13 = a1;
  wil::CoCreateInstance<UpdateSessionOrchestrator,IMoUsoOrchestrator4,wil::err_exception_policy>(&v13);
  pProxy = 0;
  v14 = winrt::impl::guid_v<winrt::Windows::Management::Update::IWindowsSoftwareUpdateProviderStatus>;
  v6 = &dword_18002EB94;
  if ( *(_QWORD *)a3 )
    v7 = *(int **)(*(_QWORD *)a3 + 16LL);
  else
    v7 = &dword_18002EB94;
  if ( *(_QWORD *)a2 )
    v6 = *(int **)(*(_QWORD *)a2 + 16LL);
  v8 = (*(__int64 (__fastcall **)(_QWORD *, int *, int *, __int128 *))(*v13 + 72LL))(v13, v6, v7, &v14);
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
    (*(void (__fastcall **)(_QWORD *))(*v13 + 16LL))(v13);
  return a1;
}

```

## disassembly

```asm
0x1800236ec  mov     [rsp-8+arg_18], rbx
0x1800236f1  push    rbp
0x1800236f2  push    rsi
0x1800236f3  push    rdi
0x1800236f4  lea     rbp, [rsp-47h]
0x1800236f9  sub     rsp, 90h
0x180023700  mov     rax, cs:__security_cookie
0x180023707  xor     rax, rsp
0x18002370a  mov     [rbp+57h+var_18], rax
0x18002370e  mov     rbx, r8
0x180023711  mov     rsi, rdx
0x180023714  mov     rdi, rcx
0x180023717  mov     [rbp+57h+var_58], rcx
0x18002371b  lea     rcx, [rbp+57h+var_58]
0x18002371f  call    ??$CoCreateInstance@VUpdateSessionOrchestrator@@UIMoUsoOrchestrator4@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UIMoUsoOrchestrator4@@Uerr_exception_policy@wil@@@0@K@Z; wil::CoCreateInstance<UpdateSessionOrchestrator,IMoUsoOrchestrator4,wil::err_exception_policy>(ulong)
0x180023724  nop
0x180023725  mov     [rbp+57h+pProxy], 0
0x18002372d  movups  xmm0, cs:??$guid_v@UIWindowsSoftwareUpdateProviderStatus@Update@Management@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Management::Update::IWindowsSoftwareUpdateProviderStatus>
0x180023734  movdqu  [rbp+57h+var_28], xmm0
0x180023739  mov     rcx, [rbp+57h+var_58]
0x18002373d  mov     rax, [rcx]
0x180023740  mov     r10, [rax+48h]
0x180023744  mov     r8, [rbx]
0x180023747  lea     rdx, dword_18002EB94
0x18002374e  test    r8, r8
0x180023751  jz      short loc_180023759
0x180023753  mov     r8, [r8+10h]
0x180023757  jmp     short loc_18002375C
0x180023759  mov     r8, rdx
0x18002375c  mov     rax, [rsi]
0x18002375f  test    rax, rax
0x180023762  jz      short loc_180023768
0x180023764  mov     rdx, [rax+10h]
0x180023768  lea     rax, [rbp+57h+pProxy]
0x18002376c  mov     qword ptr [rsp+0A0h+dwAuthnLevel], rax; int
0x180023771  lea     r9, [rbp+57h+var_28]
0x180023775  mov     rax, r10
0x180023778  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002377d  mov     rcx, [rbp+5Fh]; this
0x180023781  test    eax, eax
0x180023783  js      loc_180023867
0x180023789  mov     [rsp+0A0h+dwCapabilities], 0; dwCapabilities
0x180023791  mov     [rsp+0A0h+pAuthInfo], 0; pAuthInfo
0x18002379a  mov     [rsp+0A0h+dwImpLevel], 3; dwImpLevel
0x1800237a2  mov     [rsp+0A0h+dwAuthnLevel], 0; int
0x1800237aa  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x1800237ae  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x1800237b1  mov     r8d, edx; dwAuthzSvc
0x1800237b4  mov     rcx, [rbp+57h+pProxy]; pProxy
0x1800237b8  call    cs:__imp_CoSetProxyBlanket
0x1800237be  mov     rcx, [rbp+5Fh]; this
0x1800237c2  test    eax, eax
0x1800237c4  js      loc_18002387C
0x1800237ca  mov     rcx, [rbp+57h+pProxy]
0x1800237ce  test    rcx, rcx
0x1800237d1  jnz     short loc_1800237D8
0x1800237d3  mov     [rdi], rcx
0x1800237d6  jmp     short loc_180023814
0x1800237d8  mov     [rbp+57h+var_50], 0
0x1800237e0  mov     [rbp+57h+var_40], 0
0x1800237e7  xorps   xmm0, xmm0
0x1800237ea  movdqu  [rbp+57h+var_38], xmm0
0x1800237ef  mov     rax, [rcx]
0x1800237f2  lea     r8, [rbp+57h+var_50]
0x1800237f6  lea     rdx, ??$guid_v@UIWindowsSoftwareUpdateProviderStatus@Update@Management@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Management::Update::IWindowsSoftwareUpdateProviderStatus>
0x1800237fd  mov     rax, [rax]
0x180023800  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023805  test    eax, eax
0x180023807  js      short loc_18002385B
0x180023809  mov     rax, [rbp+57h+var_50]
0x18002380d  mov     [rdi], rax
0x180023810  mov     rcx, [rbp+57h+pProxy]
0x180023814  test    rcx, rcx
0x180023817  jz      short loc_180023823
0x180023819  lea     rcx, [rbp+57h+pProxy]
0x18002381d  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180023822  nop
0x180023823  mov     rcx, [rbp+57h+var_58]
0x180023827  test    rcx, rcx
0x18002382a  jz      short loc_180023839
0x18002382c  mov     rdx, [rcx]
0x18002382f  mov     rax, [rdx+10h]
0x180023833  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023838  nop
0x180023839  mov     rax, rdi
0x18002383c  mov     rcx, [rbp+57h+var_18]
0x180023840  xor     rcx, rsp; StackCookie
0x180023843  call    __security_check_cookie
0x180023848  mov     rbx, [rsp+0A0h+arg_18]
0x180023850  add     rsp, 90h
0x180023857  pop     rdi
0x180023858  pop     rsi
0x180023859  pop     rbp
0x18002385a  retn
0x18002385b  lea     rdx, [rbp+57h+var_40]
0x18002385f  mov     ecx, eax
0x180023861  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180023867  mov     r9d, eax; char *
0x18002386a  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180023871  mov     edx, 27h ; '''; void *
0x180023876  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002387c  mov     r9d, eax; char *
0x18002387f  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180023886  mov     edx, 32h ; '2'; void *
0x18002388b  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
