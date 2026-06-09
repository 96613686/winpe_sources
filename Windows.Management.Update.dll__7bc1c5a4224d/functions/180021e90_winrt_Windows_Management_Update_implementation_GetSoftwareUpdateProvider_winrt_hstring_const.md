# winrt::Windows::Management::Update::implementation::GetSoftwareUpdateProvider(winrt::hstring const &)

- ea: `0x180021e90`
- end: `0x180022028`
- name: `?GetSoftwareUpdateProvider@implementation@Update@Management@Windows@winrt@@YA?AUWindowsSoftwareUpdateProvider@2345@AEBUhstring@5@@Z`
- size: `408`
- prototype: `_QWORD *__fastcall(_QWORD *, winrt::Windows::Management::Update::implementation *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180012fc0`

## callees

- `0x1800028f0`
- `0x180016fe4`
- `0x180017800`
- `0x18001c7d4`
- `0x18001d50c`
- `0x180021e90`
- `0x1800220ac`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180021f4d`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180021f4d`

## string_xrefs

- `0x180022001`: `onecore\enduser\windowsupdate\muse\orchestrator\api\winrt\dll\windows.management.update.windowssoftwareupdateprovider.cpp`
- `0x180022016`: `onecore\enduser\windowsupdate\muse\orchestrator\api\winrt\dll\windows.management.update.windowssoftwareupdateprovider.cpp`

## pseudocode

```c
_QWORD *__fastcall winrt::Windows::Management::Update::implementation::GetSoftwareUpdateProvider(
        _QWORD *a1,
        winrt::Windows::Management::Update::implementation *a2)
{
  int *v4; // rdx
  int v5; // eax
  HRESULT v6; // eax
  IUnknown *v7; // rcx
  int v8; // eax
  DWORD dwAuthnLevel; // [rsp+20h] [rbp-19h]
  DWORD dwAuthnLevela; // [rsp+20h] [rbp-19h]
  IUnknown *pProxy; // [rsp+40h] [rbp+7h] BYREF
  _QWORD *v13; // [rsp+48h] [rbp+Fh] BYREF
  __int64 v14; // [rsp+50h] [rbp+17h] BYREF
  int v15; // [rsp+60h] [rbp+27h] BYREF
  __int128 v16; // [rsp+68h] [rbp+2Fh]
  __int128 v17; // [rsp+78h] [rbp+3Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+5Fh]

  v13 = a1;
  winrt::Windows::Management::Update::implementation::ValidateFolderPath(a2, a2);
  wil::CoCreateInstance<UpdateSessionOrchestrator,IMoUsoOrchestrator4,wil::err_exception_policy>(&v13);
  pProxy = 0;
  v17 = winrt::impl::guid_v<winrt::Windows::Management::Update::IWindowsSoftwareUpdateProvider>;
  if ( *(_QWORD *)a2 )
    v4 = *(int **)(*(_QWORD *)a2 + 16LL);
  else
    v4 = &dword_18002EB94;
  v5 = (*(__int64 (__fastcall **)(_QWORD *, int *, __int128 *, IUnknown **))(*v13 + 64LL))(v13, v4, &v17, &pProxy);
  if ( v5 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x35,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\api\\winrt\\dll\\windows.management.update.wind"
                    "owssoftwareupdateprovider.cpp",
      (const char *)(unsigned int)v5,
      dwAuthnLevel);
  v6 = CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0);
  if ( v6 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x40,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\api\\winrt\\dll\\windows.management.update.wind"
                    "owssoftwareupdateprovider.cpp",
      (const char *)(unsigned int)v6,
      dwAuthnLevela);
  v7 = pProxy;
  if ( pProxy )
  {
    v14 = 0;
    v15 = 0;
    v16 = 0;
    v8 = ((__int64 (__fastcall *)(IUnknown *, __int128 *, __int64 *))pProxy->lpVtbl->QueryInterface)(
           pProxy,
           &winrt::impl::guid_v<winrt::Windows::Management::Update::IWindowsSoftwareUpdateProvider>,
           &v14);
    if ( v8 < 0 )
      winrt::throw_hresult((unsigned int)v8, &v15);
    *a1 = v14;
    v7 = pProxy;
  }
  else
  {
    *a1 = 0;
  }
  if ( v7 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&pProxy);
  if ( v13 )
    (*(void (__fastcall **)(_QWORD *))(*v13 + 16LL))(v13);
  return a1;
}

```

## disassembly

```asm
0x180021e90  mov     [rsp-8+arg_10], rbx
0x180021e95  mov     [rsp-8+arg_18], rdi
0x180021e9a  push    rbp
0x180021e9b  lea     rbp, [rsp-57h]
0x180021ea0  sub     rsp, 90h
0x180021ea7  mov     rax, cs:__security_cookie
0x180021eae  xor     rax, rsp
0x180021eb1  mov     [rbp+57h+var_8], rax
0x180021eb5  mov     rbx, rdx
0x180021eb8  mov     rdi, rcx
0x180021ebb  mov     [rbp+57h+var_48], rcx
0x180021ebf  mov     rcx, rdx; this
0x180021ec2  call    ?ValidateFolderPath@implementation@Update@Management@Windows@winrt@@YAXAEBUhstring@5@@Z; winrt::Windows::Management::Update::implementation::ValidateFolderPath(winrt::hstring const &)
0x180021ec7  lea     rcx, [rbp+57h+var_48]
0x180021ecb  call    ??$CoCreateInstance@VUpdateSessionOrchestrator@@UIMoUsoOrchestrator4@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UIMoUsoOrchestrator4@@Uerr_exception_policy@wil@@@0@K@Z; wil::CoCreateInstance<UpdateSessionOrchestrator,IMoUsoOrchestrator4,wil::err_exception_policy>(ulong)
0x180021ed0  nop
0x180021ed1  mov     [rbp+57h+pProxy], 0
0x180021ed9  movups  xmm0, cs:??$guid_v@UIWindowsSoftwareUpdateProvider@Update@Management@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Management::Update::IWindowsSoftwareUpdateProvider>
0x180021ee0  movdqu  [rbp+57h+var_18], xmm0
0x180021ee5  mov     rcx, [rbp+57h+var_48]
0x180021ee9  mov     rax, [rcx]
0x180021eec  mov     rdx, [rbx]
0x180021eef  test    rdx, rdx
0x180021ef2  jz      short loc_180021EFA
0x180021ef4  mov     rdx, [rdx+10h]
0x180021ef8  jmp     short loc_180021F01
0x180021efa  lea     rdx, dword_18002EB94
0x180021f01  lea     r9, [rbp+57h+pProxy]
0x180021f05  lea     r8, [rbp+57h+var_18]
0x180021f09  mov     rax, [rax+40h]
0x180021f0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021f12  mov     rcx, [rbp+5Fh]; this
0x180021f16  test    eax, eax
0x180021f18  js      loc_180021FFE
0x180021f1e  mov     [rsp+90h+dwCapabilities], 0; dwCapabilities
0x180021f26  mov     [rsp+90h+pAuthInfo], 0; pAuthInfo
0x180021f2f  mov     [rsp+90h+dwImpLevel], 3; dwImpLevel
0x180021f37  mov     [rsp+90h+dwAuthnLevel], 0; int
0x180021f3f  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x180021f43  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x180021f46  mov     r8d, edx; dwAuthzSvc
0x180021f49  mov     rcx, [rbp+57h+pProxy]; pProxy
0x180021f4d  call    cs:__imp_CoSetProxyBlanket
0x180021f53  mov     rcx, [rbp+5Fh]; this
0x180021f57  test    eax, eax
0x180021f59  js      loc_180022013
0x180021f5f  mov     rcx, [rbp+57h+pProxy]
0x180021f63  test    rcx, rcx
0x180021f66  jnz     short loc_180021F6D
0x180021f68  mov     [rdi], rcx
0x180021f6b  jmp     short loc_180021FA9
0x180021f6d  mov     [rbp+57h+var_40], 0
0x180021f75  mov     [rbp+57h+var_30], 0
0x180021f7c  xorps   xmm0, xmm0
0x180021f7f  movdqu  [rbp+57h+var_28], xmm0
0x180021f84  mov     rax, [rcx]
0x180021f87  lea     r8, [rbp+57h+var_40]
0x180021f8b  lea     rdx, ??$guid_v@UIWindowsSoftwareUpdateProvider@Update@Management@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Management::Update::IWindowsSoftwareUpdateProvider>
0x180021f92  mov     rax, [rax]
0x180021f95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021f9a  test    eax, eax
0x180021f9c  js      short loc_180021FF2
0x180021f9e  mov     rax, [rbp+57h+var_40]
0x180021fa2  mov     [rdi], rax
0x180021fa5  mov     rcx, [rbp+57h+pProxy]
0x180021fa9  test    rcx, rcx
0x180021fac  jz      short loc_180021FB8
0x180021fae  lea     rcx, [rbp+57h+pProxy]
0x180021fb2  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180021fb7  nop
0x180021fb8  mov     rcx, [rbp+57h+var_48]
0x180021fbc  test    rcx, rcx
0x180021fbf  jz      short loc_180021FCE
0x180021fc1  mov     rdx, [rcx]
0x180021fc4  mov     rax, [rdx+10h]
0x180021fc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021fcd  nop
0x180021fce  mov     rax, rdi
0x180021fd1  mov     rcx, [rbp+57h+var_8]
0x180021fd5  xor     rcx, rsp; StackCookie
0x180021fd8  call    __security_check_cookie
0x180021fdd  lea     r11, [rsp+90h+var_s0]
0x180021fe5  mov     rbx, [r11+20h]
0x180021fe9  mov     rdi, [r11+28h]
0x180021fed  mov     rsp, r11
0x180021ff0  pop     rbp
0x180021ff1  retn
0x180021ff2  lea     rdx, [rbp+57h+var_30]
0x180021ff6  mov     ecx, eax
0x180021ff8  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180021ffe  mov     r9d, eax; char *
0x180022001  lea     r8, aOnecoreEnduser_2; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180022008  mov     edx, 35h ; '5'; void *
0x18002200d  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180022013  mov     r9d, eax; char *
0x180022016  lea     r8, aOnecoreEnduser_2; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18002201d  mov     edx, 40h ; '@'; void *
0x180022022  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
