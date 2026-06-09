# winrt::Windows::Management::Update::implementation::GetSoftwareUpdate(winrt::hstring const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateInstallationType const &,winrt::hstring const &,winrt::hstring const &,winrt::hstring const &,winrt::Windows::Foundation::Uri const &,unsigned __int64,unsigned __int64,winrt::Windows::Management::Update::WindowsSoftwareUpdateVersion const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateVersion const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateAppPackageInfo const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateExecutionInfo const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateOptionalInfo const &,winrt::Windows::Foundation::IReference<winrt::guid> const &,winrt::hstring const &)

- ea: `0x18001d150`
- end: `0x18001d3bf`
- name: `?GetSoftwareUpdate@implementation@Update@Management@Windows@winrt@@YA?AUWindowsSoftwareUpdate@2345@AEBUhstring@5@AEBW4WindowsSoftwareUpdateInstallationType@2345@000AEBUUri@Foundation@45@_K3AEBUWindowsSoftwareUpdateVersion@2345@4AEBUWindowsSoftwareUpdateAppPackageInfo@2345@AEBUWindowsSoftwareUpdateExecutionInfo@2345@AEBUWindowsSoftwareUpdateOptionalInfo@2345@AEBU?$IReference@Uguid@winrt@@@Foundation@45@0@Z`
- size: `623`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180011460`
- `0x180011610`

## callees

- `0x180002880`
- `0x180017c3c`
- `0x1800184d0`
- `0x180019118`
- `0x18001d150`
- `0x18001d9e8`
- `0x18001da30`
- `0x18001e7a4`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18001d2d7`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18001d2d7`

## string_xrefs

- `0x18001d398`: `onecore\enduser\windowsupdate\muse\orchestrator\api\winrt\dll\windows.management.update.windowssoftwareupdate.cpp`
- `0x18001d3ad`: `onecore\enduser\windowsupdate\muse\orchestrator\api\winrt\dll\windows.management.update.windowssoftwareupdate.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 *__fastcall winrt::Windows::Management::Update::implementation::GetSoftwareUpdate(
        __int64 *a1,
        __int64 a2,
        unsigned int *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        _QWORD *a7,
        __int64 a8,
        __int64 a9,
        _QWORD *a10,
        _QWORD *a11,
        __int64 *a12,
        _QWORD *a13,
        _QWORD *a14,
        __int64 *a15,
        __int64 a16)
{
  _QWORD *v16; // rdx
  int v17; // eax
  HRESULT v18; // eax
  __int64 *v19; // rbx
  int v20; // eax
  int dwAuthnLevel; // [rsp+20h] [rbp-E0h]
  int dwAuthnLevela; // [rsp+20h] [rbp-E0h]
  IUnknown *pProxy; // [rsp+80h] [rbp-80h] BYREF
  __int64 v25; // [rsp+88h] [rbp-78h] BYREF
  __int64 *v26; // [rsp+90h] [rbp-70h]
  LPVOID v27; // [rsp+98h] [rbp-68h] BYREF
  int v28[2]; // [rsp+A0h] [rbp-60h]
  __int64 v29; // [rsp+B0h] [rbp-50h]
  _QWORD *v30; // [rsp+B8h] [rbp-48h]
  __int64 v31; // [rsp+C0h] [rbp-40h]
  __int64 v32; // [rsp+C8h] [rbp-38h]
  unsigned int *v33; // [rsp+D0h] [rbp-30h]
  __int64 v34; // [rsp+D8h] [rbp-28h]
  int v35; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v36; // [rsp+E8h] [rbp-18h]
  _QWORD v37[4]; // [rsp+F8h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  v32 = a4;
  v33 = a3;
  v34 = a2;
  v26 = a1;
  *(_QWORD *)v28 = a5;
  v31 = a6;
  v30 = a7;
  v29 = a8;
  v25 = a9;
  wil::CoCreateInstance<UpdateSessionOrchestrator,IMoUsoOrchestrator4,wil::err_exception_policy>(&v27);
  pProxy = 0;
  winrt::Windows::Management::Update::implementation::BuildUpdatePropertiesJsonString(
    (__int64)v37,
    v34,
    v33,
    v32,
    *(__int64 *)v28,
    v31,
    v30,
    v29,
    a9,
    a10,
    a11,
    a12,
    a13,
    a14,
    a15,
    a16);
  v16 = v37;
  if ( v37[3] > 7u )
    v16 = (_QWORD *)v37[0];
  v17 = (*(__int64 (__fastcall **)(LPVOID, _QWORD *, __int64 *, IUnknown **))(*(_QWORD *)v27 + 80LL))(
          v27,
          v16,
          &winrt::impl::guid_v<winrt::Windows::Management::Update::IWindowsSoftwareUpdate>,
          &pProxy);
  if ( v17 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x11C,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\api\\winrt\\dll\\windows.management.update.wind"
                    "owssoftwareupdate.cpp",
      (const char *)(unsigned int)v17,
      dwAuthnLevel);
  v18 = CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0);
  if ( v18 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x127,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\api\\winrt\\dll\\windows.management.update.wind"
                    "owssoftwareupdate.cpp",
      (const char *)(unsigned int)v18,
      dwAuthnLevela);
  if ( pProxy )
  {
    v25 = 0;
    v35 = 0;
    v36 = 0;
    v20 = ((__int64 (__fastcall *)(IUnknown *, __int64 *, __int64 *))pProxy->lpVtbl->QueryInterface)(
            pProxy,
            &winrt::impl::guid_v<winrt::Windows::Management::Update::IWindowsSoftwareUpdate>,
            &v25);
    if ( v20 < 0 )
      winrt::throw_hresult((unsigned int)v20, &v35);
    v19 = v26;
    *v26 = v25;
  }
  else
  {
    v19 = v26;
    *v26 = 0;
  }
  std::wstring::_Tidy_deallocate(v37);
  if ( pProxy )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&pProxy);
  if ( v27 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v27 + 16LL))(v27);
  return v19;
}

```

## disassembly

```asm
0x18001d150  push    rbp
0x18001d152  push    rbx
0x18001d153  push    rsi
0x18001d154  push    rdi
0x18001d155  push    r12
0x18001d157  push    r13
0x18001d159  push    r14
0x18001d15b  push    r15
0x18001d15d  lea     rbp, [rsp-28h]
0x18001d162  sub     rsp, 128h
0x18001d169  mov     rax, cs:__security_cookie
0x18001d170  xor     rax, rsp
0x18001d173  mov     [rbp+60h+var_48], rax
0x18001d177  mov     [rbp+60h+var_98], r9
0x18001d17b  mov     [rbp+60h+var_90], r8
0x18001d17f  mov     [rbp+60h+var_88], rdx
0x18001d183  mov     [rbp+60h+var_D0], rcx
0x18001d187  mov     qword ptr [rbp+60h+var_C0], rcx
0x18001d18b  mov     rax, [rbp+60h+arg_20]
0x18001d192  mov     qword ptr [rbp+60h+var_C0], rax
0x18001d196  mov     rax, [rbp+60h+arg_28]
0x18001d19d  mov     [rbp+60h+var_A0], rax
0x18001d1a1  mov     rax, [rbp+60h+arg_30]
0x18001d1a8  mov     [rbp+60h+var_A8], rax
0x18001d1ac  mov     rax, [rbp+60h+arg_38]
0x18001d1b3  mov     [rbp+60h+var_B0], rax
0x18001d1b7  mov     rax, [rbp+60h+arg_40]
0x18001d1be  mov     [rbp+60h+var_D8], rax
0x18001d1c2  mov     r13, [rbp+60h+arg_48]
0x18001d1c9  mov     r12, [rbp+60h+arg_50]
0x18001d1d0  mov     r15, [rbp+60h+arg_58]
0x18001d1d7  mov     r14, [rbp+60h+arg_60]
0x18001d1de  mov     rsi, [rbp+60h+arg_68]
0x18001d1e5  mov     rdi, [rbp+60h+arg_70]
0x18001d1ec  mov     rbx, [rbp+60h+arg_78]
0x18001d1f3  lea     rcx, [rbp+60h+var_C8]
0x18001d1f7  call    ??$CoCreateInstance@VUpdateSessionOrchestrator@@UIMoUsoOrchestrator4@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UIMoUsoOrchestrator4@@Uerr_exception_policy@wil@@@0@K@Z; wil::CoCreateInstance<UpdateSessionOrchestrator,IMoUsoOrchestrator4,wil::err_exception_policy>(ulong)
0x18001d1fc  nop
0x18001d1fd  and     [rbp+60h+pProxy], 0
0x18001d202  mov     [rsp+160h+var_E8], rbx
0x18001d207  mov     [rsp+160h+var_F0], rdi
0x18001d20c  mov     [rsp+160h+var_F8], rsi
0x18001d211  mov     [rsp+160h+var_100], r14
0x18001d216  mov     [rsp+160h+var_108], r15
0x18001d21b  mov     [rsp+160h+var_110], r12
0x18001d220  mov     [rsp+160h+var_118], r13
0x18001d225  mov     rax, [rbp+60h+var_D8]
0x18001d229  mov     [rsp+160h+var_120], rax
0x18001d22e  mov     rax, [rbp+60h+var_B0]
0x18001d232  mov     qword ptr [rsp+160h+dwCapabilities], rax
0x18001d237  mov     rax, [rbp+60h+var_A8]
0x18001d23b  mov     [rsp+160h+pAuthInfo], rax
0x18001d240  mov     rax, [rbp+60h+var_A0]
0x18001d244  mov     qword ptr [rsp+160h+dwImpLevel], rax
0x18001d249  mov     rax, qword ptr [rbp+60h+var_C0]
0x18001d24d  mov     qword ptr [rsp+160h+dwAuthnLevel], rax; int
0x18001d252  mov     r9, [rbp+60h+var_98]
0x18001d256  mov     r8, [rbp+60h+var_90]
0x18001d25a  mov     rdx, [rbp+60h+var_88]
0x18001d25e  lea     rcx, [rbp+60h+var_68]
0x18001d262  call    ?BuildUpdatePropertiesJsonString@implementation@Update@Management@Windows@winrt@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBUhstring@5@AEBW4WindowsSoftwareUpdateInstallationType@2345@000AEBUUri@Foundation@45@_K3AEBUWindowsSoftwareUpdateVersion@2345@4AEBUWindowsSoftwareUpdateAppPackageInfo@2345@AEBUWindowsSoftwareUpdateExecutionInfo@2345@AEBUWindowsSoftwareUpdateOptionalInfo@2345@AEBU?$IReference@Uguid@winrt@@@Foundation@45@0@Z; winrt::Windows::Management::Update::implementation::BuildUpdatePropertiesJsonString(winrt::hstring const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateInstallationType const &,winrt::hstring const &,winrt::hstring const &,winrt::hstring const &,winrt::Windows::Foundation::Uri const &,unsigned __int64,unsigned __int64,winrt::Windows::Management::Update::WindowsSoftwareUpdateVersion const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateVersion const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateAppPackageInfo const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateExecutionInfo const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateOptionalInfo const &,winrt::Windows::Foundation::IReference<winrt::guid> const &,winrt::hstring const &)
0x18001d267  nop
0x18001d268  mov     rbx, [rbp+60h+var_C8]
0x18001d26c  mov     rax, [rbx]
0x18001d26f  mov     rdi, [rax+50h]
0x18001d273  xor     esi, esi
0x18001d275  cmp     [rbp+60h+pProxy], rsi
0x18001d279  jz      short loc_18001D284
0x18001d27b  lea     rcx, [rbp+60h+pProxy]
0x18001d27f  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001d284  lea     rdx, [rbp+60h+var_68]
0x18001d288  cmp     [rbp+60h+var_50], 7
0x18001d28d  cmova   rdx, [rbp+60h+var_68]
0x18001d292  lea     r9, [rbp+60h+pProxy]
0x18001d296  lea     r8, ??$guid_v@UIWindowsSoftwareUpdate@Update@Management@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Management::Update::IWindowsSoftwareUpdate>
0x18001d29d  mov     rcx, rbx
0x18001d2a0  mov     rax, rdi
0x18001d2a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d2a8  mov     rcx, [rbp+68h]; this
0x18001d2ac  test    eax, eax
0x18001d2ae  js      loc_18001D395
0x18001d2b4  mov     [rsp+160h+dwCapabilities], esi; dwCapabilities
0x18001d2b8  mov     [rsp+160h+pAuthInfo], rsi; pAuthInfo
0x18001d2bd  mov     [rsp+160h+dwImpLevel], 3; dwImpLevel
0x18001d2c5  mov     [rsp+160h+dwAuthnLevel], esi; int
0x18001d2c9  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x18001d2cd  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x18001d2d0  mov     r8d, edx; dwAuthzSvc
0x18001d2d3  mov     rcx, [rbp+60h+pProxy]; pProxy
0x18001d2d7  call    cs:__imp_CoSetProxyBlanket
0x18001d2de  nop     dword ptr [rax+rax+00h]
0x18001d2e3  mov     rcx, [rbp+68h]; this
0x18001d2e7  test    eax, eax
0x18001d2e9  js      loc_18001D3AA
0x18001d2ef  mov     rcx, [rbp+60h+pProxy]
0x18001d2f3  test    rcx, rcx
0x18001d2f6  jnz     short loc_18001D301
0x18001d2f8  mov     rbx, [rbp+60h+var_D0]
0x18001d2fc  mov     [rbx], rsi
0x18001d2ff  jmp     short loc_18001D335
0x18001d301  mov     [rbp+60h+var_D8], rsi
0x18001d305  mov     [rbp+60h+var_80], esi
0x18001d308  xorps   xmm0, xmm0
0x18001d30b  movdqu  [rbp+60h+var_78], xmm0
0x18001d310  mov     rax, [rcx]
0x18001d313  lea     r8, [rbp+60h+var_D8]
0x18001d317  lea     rdx, ??$guid_v@UIWindowsSoftwareUpdate@Update@Management@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Management::Update::IWindowsSoftwareUpdate>
0x18001d31e  mov     rax, [rax]
0x18001d321  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d326  test    eax, eax
0x18001d328  js      short loc_18001D389
0x18001d32a  mov     rax, [rbp+60h+var_D8]
0x18001d32e  mov     rbx, [rbp+60h+var_D0]
0x18001d332  mov     [rbx], rax
0x18001d335  lea     rcx, [rbp+60h+var_68]
0x18001d339  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001d33e  nop
0x18001d33f  cmp     [rbp+60h+pProxy], rsi
0x18001d343  jz      short loc_18001D34F
0x18001d345  lea     rcx, [rbp+60h+pProxy]
0x18001d349  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001d34e  nop
0x18001d34f  mov     rcx, [rbp+60h+var_C8]
0x18001d353  test    rcx, rcx
0x18001d356  jz      short loc_18001D365
0x18001d358  mov     rdx, [rcx]
0x18001d35b  mov     rax, [rdx+10h]
0x18001d35f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d364  nop
0x18001d365  mov     rax, rbx
0x18001d368  mov     rcx, [rbp+60h+var_48]
0x18001d36c  xor     rcx, rsp; StackCookie
0x18001d36f  call    __security_check_cookie
0x18001d374  add     rsp, 128h
0x18001d37b  pop     r15
0x18001d37d  pop     r14
0x18001d37f  pop     r13
0x18001d381  pop     r12
0x18001d383  pop     rdi
0x18001d384  pop     rsi
0x18001d385  pop     rbx
0x18001d386  pop     rbp
0x18001d387  retn
0x18001d389  lea     rdx, [rbp+60h+var_80]
0x18001d38d  mov     ecx, eax
0x18001d38f  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001d395  mov     r9d, eax; char *
0x18001d398  lea     r8, aOnecoreEnduser_0; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18001d39f  mov     edx, 11Ch; void *
0x18001d3a4  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001d3aa  mov     r9d, eax; char *
0x18001d3ad  lea     r8, aOnecoreEnduser_0; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18001d3b4  mov     edx, 127h; void *
0x18001d3b9  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
