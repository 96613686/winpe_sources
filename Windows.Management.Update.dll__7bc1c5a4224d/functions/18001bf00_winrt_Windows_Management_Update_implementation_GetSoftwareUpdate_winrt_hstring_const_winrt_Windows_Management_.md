# winrt::Windows::Management::Update::implementation::GetSoftwareUpdate(winrt::hstring const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateInstallationType const &,winrt::hstring const &,winrt::hstring const &,winrt::hstring const &,winrt::Windows::Foundation::Uri const &,unsigned __int64,unsigned __int64,winrt::Windows::Management::Update::WindowsSoftwareUpdateVersion const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateVersion const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateAppPackageInfo const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateExecutionInfo const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateOptionalInfo const &,winrt::Windows::Foundation::IReference<winrt::guid> const &,winrt::hstring const &)

- ea: `0x18001bf00`
- end: `0x18001c16b`
- name: `?GetSoftwareUpdate@implementation@Update@Management@Windows@winrt@@YA?AUWindowsSoftwareUpdate@2345@AEBUhstring@5@AEBW4WindowsSoftwareUpdateInstallationType@2345@000AEBUUri@Foundation@45@_K3AEBUWindowsSoftwareUpdateVersion@2345@4AEBUWindowsSoftwareUpdateAppPackageInfo@2345@AEBUWindowsSoftwareUpdateExecutionInfo@2345@AEBUWindowsSoftwareUpdateOptionalInfo@2345@AEBU?$IReference@Uguid@winrt@@@Foundation@45@0@Z`
- size: `619`
- prototype: `__int64 *__fastcall(__int64 *, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180010918`
- `0x180010acc`

## callees

- `0x1800028f0`
- `0x180016fe4`
- `0x180017800`
- `0x180018440`
- `0x18001bf00`
- `0x18001c7d4`
- `0x18001c81c`
- `0x18001d50c`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18001c08a`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18001c08a`

## string_xrefs

- `0x18001c144`: `onecore\enduser\windowsupdate\muse\orchestrator\api\winrt\dll\windows.management.update.windowssoftwareupdate.cpp`
- `0x18001c159`: `onecore\enduser\windowsupdate\muse\orchestrator\api\winrt\dll\windows.management.update.windowssoftwareupdate.cpp`

## pseudocode

```c
__int64 *__fastcall winrt::Windows::Management::Update::implementation::GetSoftwareUpdate(
        __int64 *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        __int64 a12,
        __int64 a13,
        __int64 a14,
        __int64 a15,
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
  __int64 v27; // [rsp+98h] [rbp-68h] BYREF
  int v28[2]; // [rsp+A0h] [rbp-60h]
  __int64 v29; // [rsp+B0h] [rbp-50h]
  __int64 v30; // [rsp+B8h] [rbp-48h]
  __int64 v31; // [rsp+C0h] [rbp-40h]
  __int64 v32; // [rsp+C8h] [rbp-38h]
  __int64 v33; // [rsp+D0h] [rbp-30h]
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
    (unsigned int)v37,
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
  v17 = (*(__int64 (__fastcall **)(__int64, _QWORD *, __int64 *, IUnknown **))(*(_QWORD *)v27 + 80LL))(
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
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
  return v19;
}

```

## disassembly

```asm
0x18001bf00  push    rbp
0x18001bf02  push    rbx
0x18001bf03  push    rsi
0x18001bf04  push    rdi
0x18001bf05  push    r12
0x18001bf07  push    r13
0x18001bf09  push    r14
0x18001bf0b  push    r15
0x18001bf0d  lea     rbp, [rsp-28h]
0x18001bf12  sub     rsp, 128h
0x18001bf19  mov     rax, cs:__security_cookie
0x18001bf20  xor     rax, rsp
0x18001bf23  mov     [rbp+60h+var_48], rax
0x18001bf27  mov     [rbp+60h+var_98], r9
0x18001bf2b  mov     [rbp+60h+var_90], r8
0x18001bf2f  mov     [rbp+60h+var_88], rdx
0x18001bf33  mov     [rbp+60h+var_D0], rcx
0x18001bf37  mov     qword ptr [rbp+60h+var_C0], rcx
0x18001bf3b  mov     rax, [rbp+60h+arg_20]
0x18001bf42  mov     qword ptr [rbp+60h+var_C0], rax
0x18001bf46  mov     rax, [rbp+60h+arg_28]
0x18001bf4d  mov     [rbp+60h+var_A0], rax
0x18001bf51  mov     rax, [rbp+60h+arg_30]
0x18001bf58  mov     [rbp+60h+var_A8], rax
0x18001bf5c  mov     rax, [rbp+60h+arg_38]
0x18001bf63  mov     [rbp+60h+var_B0], rax
0x18001bf67  mov     rax, [rbp+60h+arg_40]
0x18001bf6e  mov     [rbp+60h+var_D8], rax
0x18001bf72  mov     r13, [rbp+60h+arg_48]
0x18001bf79  mov     r12, [rbp+60h+arg_50]
0x18001bf80  mov     r15, [rbp+60h+arg_58]
0x18001bf87  mov     r14, [rbp+60h+arg_60]
0x18001bf8e  mov     rsi, [rbp+60h+arg_68]
0x18001bf95  mov     rdi, [rbp+60h+arg_70]
0x18001bf9c  mov     rbx, [rbp+60h+arg_78]
0x18001bfa3  lea     rcx, [rbp+60h+var_C8]
0x18001bfa7  call    ??$CoCreateInstance@VUpdateSessionOrchestrator@@UIMoUsoOrchestrator4@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UIMoUsoOrchestrator4@@Uerr_exception_policy@wil@@@0@K@Z; wil::CoCreateInstance<UpdateSessionOrchestrator,IMoUsoOrchestrator4,wil::err_exception_policy>(ulong)
0x18001bfac  nop
0x18001bfad  mov     [rbp+60h+pProxy], 0
0x18001bfb5  mov     [rsp+160h+var_E8], rbx
0x18001bfba  mov     [rsp+160h+var_F0], rdi
0x18001bfbf  mov     [rsp+160h+var_F8], rsi
0x18001bfc4  mov     [rsp+160h+var_100], r14
0x18001bfc9  mov     [rsp+160h+var_108], r15
0x18001bfce  mov     [rsp+160h+var_110], r12
0x18001bfd3  mov     [rsp+160h+var_118], r13
0x18001bfd8  mov     rax, [rbp+60h+var_D8]
0x18001bfdc  mov     [rsp+160h+var_120], rax
0x18001bfe1  mov     rax, [rbp+60h+var_B0]
0x18001bfe5  mov     qword ptr [rsp+160h+dwCapabilities], rax
0x18001bfea  mov     rax, [rbp+60h+var_A8]
0x18001bfee  mov     [rsp+160h+pAuthInfo], rax
0x18001bff3  mov     rax, [rbp+60h+var_A0]
0x18001bff7  mov     qword ptr [rsp+160h+dwImpLevel], rax
0x18001bffc  mov     rax, qword ptr [rbp+60h+var_C0]
0x18001c000  mov     qword ptr [rsp+160h+dwAuthnLevel], rax; int
0x18001c005  mov     r9, [rbp+60h+var_98]
0x18001c009  mov     r8, [rbp+60h+var_90]
0x18001c00d  mov     rdx, [rbp+60h+var_88]
0x18001c011  lea     rcx, [rbp+60h+var_68]
0x18001c015  call    ?BuildUpdatePropertiesJsonString@implementation@Update@Management@Windows@winrt@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBUhstring@5@AEBW4WindowsSoftwareUpdateInstallationType@2345@000AEBUUri@Foundation@45@_K3AEBUWindowsSoftwareUpdateVersion@2345@4AEBUWindowsSoftwareUpdateAppPackageInfo@2345@AEBUWindowsSoftwareUpdateExecutionInfo@2345@AEBUWindowsSoftwareUpdateOptionalInfo@2345@AEBU?$IReference@Uguid@winrt@@@Foundation@45@0@Z; winrt::Windows::Management::Update::implementation::BuildUpdatePropertiesJsonString(winrt::hstring const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateInstallationType const &,winrt::hstring const &,winrt::hstring const &,winrt::hstring const &,winrt::Windows::Foundation::Uri const &,unsigned __int64,unsigned __int64,winrt::Windows::Management::Update::WindowsSoftwareUpdateVersion const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateVersion const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateAppPackageInfo const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateExecutionInfo const &,winrt::Windows::Management::Update::WindowsSoftwareUpdateOptionalInfo const &,winrt::Windows::Foundation::IReference<winrt::guid> const &,winrt::hstring const &)
0x18001c01a  nop
0x18001c01b  mov     rbx, [rbp+60h+var_C8]
0x18001c01f  mov     rax, [rbx]
0x18001c022  mov     rdi, [rax+50h]
0x18001c026  xor     esi, esi
0x18001c028  cmp     [rbp+60h+pProxy], rsi
0x18001c02c  jz      short loc_18001C037
0x18001c02e  lea     rcx, [rbp+60h+pProxy]
0x18001c032  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001c037  lea     rdx, [rbp+60h+var_68]
0x18001c03b  cmp     [rbp+60h+var_50], 7
0x18001c040  cmova   rdx, [rbp+60h+var_68]
0x18001c045  lea     r9, [rbp+60h+pProxy]
0x18001c049  lea     r8, ??$guid_v@UIWindowsSoftwareUpdate@Update@Management@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Management::Update::IWindowsSoftwareUpdate>
0x18001c050  mov     rcx, rbx
0x18001c053  mov     rax, rdi
0x18001c056  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c05b  mov     rcx, [rbp+68h]; this
0x18001c05f  test    eax, eax
0x18001c061  js      loc_18001C141
0x18001c067  mov     [rsp+160h+dwCapabilities], esi; dwCapabilities
0x18001c06b  mov     [rsp+160h+pAuthInfo], rsi; pAuthInfo
0x18001c070  mov     [rsp+160h+dwImpLevel], 3; dwImpLevel
0x18001c078  mov     [rsp+160h+dwAuthnLevel], esi; int
0x18001c07c  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x18001c080  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x18001c083  mov     r8d, edx; dwAuthzSvc
0x18001c086  mov     rcx, [rbp+60h+pProxy]; pProxy
0x18001c08a  call    cs:__imp_CoSetProxyBlanket
0x18001c090  mov     rcx, [rbp+68h]; this
0x18001c094  test    eax, eax
0x18001c096  js      loc_18001C156
0x18001c09c  mov     rcx, [rbp+60h+pProxy]
0x18001c0a0  test    rcx, rcx
0x18001c0a3  jnz     short loc_18001C0AE
0x18001c0a5  mov     rbx, [rbp+60h+var_D0]
0x18001c0a9  mov     [rbx], rsi
0x18001c0ac  jmp     short loc_18001C0E2
0x18001c0ae  mov     [rbp+60h+var_D8], rsi
0x18001c0b2  mov     [rbp+60h+var_80], esi
0x18001c0b5  xorps   xmm0, xmm0
0x18001c0b8  movdqu  [rbp+60h+var_78], xmm0
0x18001c0bd  mov     rax, [rcx]
0x18001c0c0  lea     r8, [rbp+60h+var_D8]
0x18001c0c4  lea     rdx, ??$guid_v@UIWindowsSoftwareUpdate@Update@Management@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Management::Update::IWindowsSoftwareUpdate>
0x18001c0cb  mov     rax, [rax]
0x18001c0ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c0d3  test    eax, eax
0x18001c0d5  js      short loc_18001C135
0x18001c0d7  mov     rax, [rbp+60h+var_D8]
0x18001c0db  mov     rbx, [rbp+60h+var_D0]
0x18001c0df  mov     [rbx], rax
0x18001c0e2  lea     rcx, [rbp+60h+var_68]
0x18001c0e6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001c0eb  nop
0x18001c0ec  cmp     [rbp+60h+pProxy], rsi
0x18001c0f0  jz      short loc_18001C0FC
0x18001c0f2  lea     rcx, [rbp+60h+pProxy]
0x18001c0f6  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001c0fb  nop
0x18001c0fc  mov     rcx, [rbp+60h+var_C8]
0x18001c100  test    rcx, rcx
0x18001c103  jz      short loc_18001C112
0x18001c105  mov     rdx, [rcx]
0x18001c108  mov     rax, [rdx+10h]
0x18001c10c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c111  nop
0x18001c112  mov     rax, rbx
0x18001c115  mov     rcx, [rbp+60h+var_48]
0x18001c119  xor     rcx, rsp; StackCookie
0x18001c11c  call    __security_check_cookie
0x18001c121  add     rsp, 128h
0x18001c128  pop     r15
0x18001c12a  pop     r14
0x18001c12c  pop     r13
0x18001c12e  pop     r12
0x18001c130  pop     rdi
0x18001c131  pop     rsi
0x18001c132  pop     rbx
0x18001c133  pop     rbp
0x18001c134  retn
0x18001c135  lea     rdx, [rbp+60h+var_80]
0x18001c139  mov     ecx, eax
0x18001c13b  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001c141  mov     r9d, eax; char *
0x18001c144  lea     r8, aOnecoreEnduser_0; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18001c14b  mov     edx, 11Ch; void *
0x18001c150  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001c156  mov     r9d, eax; char *
0x18001c159  lea     r8, aOnecoreEnduser_0; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18001c160  mov     edx, 127h; void *
0x18001c165  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
