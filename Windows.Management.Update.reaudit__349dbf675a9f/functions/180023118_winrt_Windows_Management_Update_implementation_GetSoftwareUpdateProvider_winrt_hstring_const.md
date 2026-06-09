# winrt::Windows::Management::Update::implementation::GetSoftwareUpdateProvider(winrt::hstring const &)

- ea: `0x180023118`
- end: `0x1800232ab`
- name: `?GetSoftwareUpdateProvider@implementation@Update@Management@Windows@winrt@@YA?AUWindowsSoftwareUpdateProvider@2345@AEBUhstring@5@@Z`
- size: `403`
- prototype: `_QWORD *__fastcall(_QWORD *, winrt::Windows::Management::Update::implementation *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180013ba0`

## callees

- `0x180002880`
- `0x180017c3c`
- `0x1800184d0`
- `0x18001d9e8`
- `0x18001e7a4`
- `0x180023118`
- `0x180023334`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800231c9`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800231c9`

## string_xrefs

- `0x180023284`: `onecore\enduser\windowsupdate\muse\orchestrator\api\winrt\dll\windows.management.update.windowssoftwareupdateprovider.cpp`
- `0x180023299`: `onecore\enduser\windowsupdate\muse\orchestrator\api\winrt\dll\windows.management.update.windowssoftwareupdateprovider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall winrt::Windows::Management::Update::implementation::GetSoftwareUpdateProvider(
        _QWORD *a1,
        winrt::Windows::Management::Update::implementation *a2)
{
  const unsigned __int16 *v4; // rdx
  int v5; // eax
  HRESULT v6; // eax
  IUnknown *v7; // rax
  int v8; // eax
  int v10; // [rsp+20h] [rbp-19h]
  int v11; // [rsp+20h] [rbp-19h]
  IUnknown *pProxy; // [rsp+40h] [rbp+7h] BYREF
  LPVOID v13; // [rsp+48h] [rbp+Fh] BYREF
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
    v4 = *(const unsigned __int16 **)(*(_QWORD *)a2 + 16LL);
  else
    v4 = &dword_180030C44;
  v5 = (*(__int64 (__fastcall **)(LPVOID, const unsigned __int16 *, __int128 *, IUnknown **))(*(_QWORD *)v13 + 64LL))(
         v13,
         v4,
         &v17,
         &pProxy);
  if ( v5 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x35,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\api\\winrt\\dll\\windows.management.update.wind"
                    "owssoftwareupdateprovider.cpp",
      (const char *)(unsigned int)v5,
      v10);
  v6 = CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0);
  if ( v6 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x40,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\api\\winrt\\dll\\windows.management.update.wind"
                    "owssoftwareupdateprovider.cpp",
      (const char *)(unsigned int)v6,
      v11);
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
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v13 + 16LL))(v13);
  return a1;
}

```

## disassembly

```asm
0x180023118  mov     [rsp-8+arg_10], rbx
0x18002311d  mov     [rsp-8+arg_18], rdi
0x180023122  push    rbp
0x180023123  lea     rbp, [rsp-57h]
0x180023128  sub     rsp, 90h
0x18002312f  mov     rax, cs:__security_cookie
0x180023136  xor     rax, rsp
0x180023139  mov     [rbp+57h+var_8], rax
0x18002313d  mov     rbx, rdx
0x180023140  mov     rdi, rcx
0x180023143  mov     [rbp+57h+var_48], rcx
0x180023147  mov     rcx, rdx; this
0x18002314a  call    ?ValidateFolderPath@implementation@Update@Management@Windows@winrt@@YAXAEBUhstring@5@@Z; winrt::Windows::Management::Update::implementation::ValidateFolderPath(winrt::hstring const &)
0x18002314f  lea     rcx, [rbp+57h+var_48]
0x180023153  call    ??$CoCreateInstance@VUpdateSessionOrchestrator@@UIMoUsoOrchestrator4@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UIMoUsoOrchestrator4@@Uerr_exception_policy@wil@@@0@K@Z; wil::CoCreateInstance<UpdateSessionOrchestrator,IMoUsoOrchestrator4,wil::err_exception_policy>(ulong)
0x180023158  nop
0x180023159  and     [rbp+57h+pProxy], 0
0x18002315e  movups  xmm0, cs:??$guid_v@UIWindowsSoftwareUpdateProvider@Update@Management@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Management::Update::IWindowsSoftwareUpdateProvider>
0x180023165  movdqu  [rbp+57h+var_18], xmm0
0x18002316a  mov     rcx, [rbp+57h+var_48]
0x18002316e  mov     rax, [rcx]
0x180023171  mov     rdx, [rbx]
0x180023174  test    rdx, rdx
0x180023177  jz      short loc_18002317F
0x180023179  mov     rdx, [rdx+10h]
0x18002317d  jmp     short loc_180023186
0x18002317f  lea     rdx, dword_180030C44
0x180023186  lea     r9, [rbp+57h+pProxy]
0x18002318a  lea     r8, [rbp+57h+var_18]
0x18002318e  mov     rax, [rax+40h]
0x180023192  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023197  mov     rcx, [rbp+5Fh]; this
0x18002319b  test    eax, eax
0x18002319d  js      loc_180023281
0x1800231a3  and     [rsp+90h+var_58], 0
0x1800231a8  and     [rsp+90h+var_60], 0
0x1800231ae  mov     [rsp+90h+dwImpLevel], 3; dwImpLevel
0x1800231b6  and     [rsp+90h+var_70], 0
0x1800231bb  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x1800231bf  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x1800231c2  mov     r8d, edx; dwAuthzSvc
0x1800231c5  mov     rcx, [rbp+57h+pProxy]; pProxy
0x1800231c9  call    cs:__imp_CoSetProxyBlanket
0x1800231d0  nop     dword ptr [rax+rax+00h]
0x1800231d5  mov     rcx, [rbp+5Fh]; this
0x1800231d9  test    eax, eax
0x1800231db  js      loc_180023296
0x1800231e1  mov     rax, [rbp+57h+pProxy]
0x1800231e5  test    rax, rax
0x1800231e8  jnz     short loc_1800231EF
0x1800231ea  and     [rdi], rax
0x1800231ed  jmp     short loc_18002322B
0x1800231ef  and     [rbp+57h+var_40], 0
0x1800231f4  and     [rbp+57h+var_30], 0
0x1800231f8  xorps   xmm0, xmm0
0x1800231fb  movdqu  [rbp+57h+var_28], xmm0
0x180023200  mov     rcx, [rax]
0x180023203  mov     r9, [rcx]
0x180023206  lea     r8, [rbp+57h+var_40]
0x18002320a  lea     rdx, ??$guid_v@UIWindowsSoftwareUpdateProvider@Update@Management@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Management::Update::IWindowsSoftwareUpdateProvider>
0x180023211  mov     rcx, rax
0x180023214  mov     rax, r9
0x180023217  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002321c  test    eax, eax
0x18002321e  js      short loc_180023275
0x180023220  mov     rax, [rbp+57h+var_40]
0x180023224  mov     [rdi], rax
0x180023227  mov     rax, [rbp+57h+pProxy]
0x18002322b  test    rax, rax
0x18002322e  jz      short loc_18002323A
0x180023230  lea     rcx, [rbp+57h+pProxy]
0x180023234  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180023239  nop
0x18002323a  mov     rcx, [rbp+57h+var_48]
0x18002323e  test    rcx, rcx
0x180023241  jz      short loc_180023250
0x180023243  mov     rdx, [rcx]
0x180023246  mov     rax, [rdx+10h]
0x18002324a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002324f  nop
0x180023250  mov     rax, rdi
0x180023253  mov     rcx, [rbp+57h+var_8]
0x180023257  xor     rcx, rsp; StackCookie
0x18002325a  call    __security_check_cookie
0x18002325f  lea     r11, [rsp+90h+var_s0]
0x180023267  mov     rbx, [r11+20h]
0x18002326b  mov     rdi, [r11+28h]
0x18002326f  mov     rsp, r11
0x180023272  pop     rbp
0x180023273  retn
0x180023275  lea     rdx, [rbp+57h+var_30]
0x180023279  mov     ecx, eax
0x18002327b  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180023281  mov     r9d, eax; char *
0x180023284  lea     r8, aOnecoreEnduser_2; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18002328b  mov     edx, 35h ; '5'; void *
0x180023290  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180023296  mov     r9d, eax; char *
0x180023299  lea     r8, aOnecoreEnduser_2; "onecore\\enduser\\windowsupdate\\muse\\"...
0x1800232a0  mov     edx, 40h ; '@'; void *
0x1800232a5  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
