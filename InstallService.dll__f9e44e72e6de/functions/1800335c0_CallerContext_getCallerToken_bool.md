# CallerContext::_getCallerToken(bool)

- ea: `0x1800335c0`
- end: `0x180033808`
- name: `?_getCallerToken@CallerContext@@CA?AV?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@_N@Z`
- size: `584`
- prototype: `_QWORD *__fastcall(_QWORD *, char)`
- caller_count: `2`
- callee_count: `15`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180032318`
- `0x180033314`

## callees

- `0x18000ee20`
- `0x1800127c8`
- `0x180014f18`
- `0x18001c414`
- `0x180022e14`
- `0x18002ec2c`
- `0x180032844`
- `0x180032b18`
- `0x180032bbc`
- `0x180032c50`
- `0x180032d10`
- `0x18003320c`
- `0x180033584`
- `0x1800335c0`
- `0x1801dae5c`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800335fb`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800336dc`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800335fb`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800336dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180033660`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180033744`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180033660`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180033744`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180033618`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800336f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180033618`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800336f9`

## string_xrefs

- `0x18003362d`: `InstallService COM Caller SID: %s`
- `0x180033641`: `CallerContext::_getCallerToken`
- `0x180033722`: `CallerContext::_getCallerToken`
- `0x18003379c`: `CallerContext::_getCallerToken`
- `0x18003364c`: `onecoreuap\enduser\winstore\installservice\lib\callercontext.cpp`
- `0x18003372f`: `onecoreuap\enduser\winstore\installservice\lib\callercontext.cpp`
- `0x1800337a3`: `onecoreuap\enduser\winstore\installservice\lib\callercontext.cpp`
- `0x1800337f6`: `onecoreuap\enduser\winstore\installservice\lib\callercontext.cpp`
- `0x18003370e`: `InstallService InProc Caller. Using current thread impersonation token SID: %s`
- `0x180033788`: `InstallService InProc Caller. Current Thread not impersonating. Using current process (LocalSystem)`
- `0x18003367a`: `storeAppInstallation`
- `0x180033666`: `storeAppInstall`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
_QWORD *__fastcall CallerContext::_getCallerToken(_QWORD *a1, char a2)
{
  HSTRING *v4; // rax
  void *v5; // rdx
  void *v6; // rdx
  __int64 CurrentThreadTokenOrEmpty; // rax
  HSTRING *TokenSid; // rax
  PCWSTR StringRawBuffer; // rax
  unsigned int v10; // r8d
  unsigned int v12; // eax
  int v13; // [rsp+20h] [rbp-60h]
  void **v14; // [rsp+58h] [rbp-28h] BYREF
  HANDLE TokenHandle; // [rsp+60h] [rbp-20h]
  _QWORD v16[3]; // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]
  HSTRING string; // [rsp+B0h] [rbp+30h] BYREF

  TokenHelpers::GetCOMClientToken(&v14);
  if ( !TokenHandle )
  {
    CurrentThreadTokenOrEmpty = TokenHelpers::GetCurrentThreadTokenOrEmpty(v16);
    Microsoft::WRL::Wrappers::HandleT<HINTERNETTraits>::operator=(&v14, CurrentThreadTokenOrEmpty);
    v16[0] = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
    Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(v16);
    if ( TokenHandle )
    {
      if ( IsDebuggerPresent() )
      {
        TokenSid = (HSTRING *)TokenHelpers::GetTokenSid(&string, &v14);
        StringRawBuffer = WindowsGetStringRawBuffer(*TokenSid, 0);
        LogMessage(
          4u,
          "onecoreuap\\enduser\\winstore\\installservice\\lib\\callercontext.cpp",
          0x51u,
          "CallerContext::_getCallerToken",
          -1,
          L"InstallService InProc Caller. Using current thread impersonation token SID: %s",
          0,
          0,
          StringRawBuffer);
        WindowsDeleteString(string);
      }
      goto LABEL_11;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SendProgressAsync>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SendProgressAsync>::GetImpl'::`2'::impl) )
    {
      if ( !a2 )
      {
LABEL_17:
        TokenHelpers::GetSelfToken(a1);
        goto LABEL_18;
      }
      v10 = 92;
    }
    else
    {
      v10 = 97;
    }
    LogSimpleMessage(
      2u,
      "onecoreuap\\enduser\\winstore\\installservice\\lib\\callercontext.cpp",
      v10,
      "CallerContext::_getCallerToken",
      -1,
      L"InstallService InProc Caller. Current Thread not impersonating. Using current process (LocalSystem)",
      0,
      0);
    goto LABEL_17;
  }
  if ( IsDebuggerPresent() )
  {
    v4 = (HSTRING *)TokenHelpers::GetTokenSid(&string, &v14);
    WindowsGetStringRawBuffer(*v4, 0);
    LogMessage(
      4u,
      "onecoreuap\\enduser\\winstore\\installservice\\lib\\callercontext.cpp",
      0x37u,
      "CallerContext::_getCallerToken",
      -1,
      L"InstallService COM Caller SID: %s",
      0,
      0);
    WindowsDeleteString(string);
  }
  if ( !(unsigned __int8)TokenHelpers::TokenHasCapability(&v14, L"storeAppInstall")
    && !(unsigned __int8)TokenHelpers::TokenHasCapability(&v14, L"storeAppInstallation") )
  {
    v12 = wil::verify_hresult<long>(2151657480LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3D,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\callercontext.cpp",
      (const char *)v12,
      v13);
  }
  if ( TokenHelpers::GetIntegrityLevel((TokenHelpers *)TokenHandle, v5) < 0x2000 )
    TokenHelpers::ElevateToMediumIntegrityLevel(TokenHandle, v6);
LABEL_11:
  *a1 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
  a1[1] = TokenHandle;
  TokenHandle = 0;
LABEL_18:
  v14 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(&v14);
  return a1;
}

```

## disassembly

```asm
0x1800335c0  mov     [rsp-18h+arg_0], rbx
0x1800335c5  mov     [rsp-18h+arg_8], rsi
0x1800335ca  push    rbp
0x1800335cb  push    rdi
0x1800335cc  push    r14
0x1800335ce  mov     rbp, rsp
0x1800335d1  sub     rsp, 80h
0x1800335d8  mov     dil, dl
0x1800335db  mov     rbx, rcx
0x1800335de  xor     esi, esi
0x1800335e0  lea     rcx, [rbp+var_28]
0x1800335e4  call    ?GetCOMClientToken@TokenHelpers@@YA?AV?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@XZ; TokenHelpers::GetCOMClientToken(void)
0x1800335e9  nop
0x1800335ea  lea     r14, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x1800335f1  cmp     [rbp+TokenHandle], rsi
0x1800335f5  jz      loc_1800336B4
0x1800335fb  call    cs:__imp_IsDebuggerPresent
0x180033601  test    eax, eax
0x180033603  jz      short loc_180033666
0x180033605  lea     rdx, [rbp+var_28]
0x180033609  lea     rcx, [rbp+string]
0x18003360d  call    ?GetTokenSid@TokenHelpers@@YA?AVHString@Wrappers@WRL@Microsoft@@AEBV?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@345@@Z; TokenHelpers::GetTokenSid(Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits> const &)
0x180033612  nop
0x180033613  xor     edx, edx; length
0x180033615  mov     rcx, [rax]; string
0x180033618  call    cs:__imp_WindowsGetStringRawBuffer
0x18003361e  mov     [rsp+80h+var_40], rax
0x180033623  mov     [rsp+80h+var_48], rsi; unsigned __int16 *
0x180033628  mov     [rsp+80h+var_50], rsi; char *
0x18003362d  lea     rax, aInstallservice_4; "InstallService COM Caller SID: %s"
0x180033634  mov     [rsp+80h+var_58], rax; unsigned __int16 *
0x180033639  mov     [rsp+80h+var_60], 0FFFFFFFFh; int
0x180033641  lea     r9, aCallercontextG; "CallerContext::_getCallerToken"
0x180033648  lea     r8d, [rsi+37h]; unsigned int
0x18003364c  lea     rdx, aOnecoreuapEndu_68; "onecoreuap\\enduser\\winstore\\installs"...
0x180033653  lea     ecx, [rsi+4]; unsigned int
0x180033656  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x18003365b  nop
0x18003365c  mov     rcx, [rbp+string]; string
0x180033660  call    cs:__imp_WindowsDeleteString
0x180033666  lea     rdx, aStoreappinstal; "storeAppInstall"
0x18003366d  lea     rcx, [rbp+var_28]
0x180033671  call    ?TokenHasCapability@TokenHelpers@@YA_NAEBV?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@PEBG@Z; TokenHelpers::TokenHasCapability(Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits> const &,ushort const *)
0x180033676  test    al, al
0x180033678  jnz     short loc_180033692
0x18003367a  lea     rdx, aStoreappinstal_0; "storeAppInstallation"
0x180033681  lea     rcx, [rbp+var_28]
0x180033685  call    ?TokenHasCapability@TokenHelpers@@YA_NAEBV?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@PEBG@Z; TokenHelpers::TokenHasCapability(Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits> const &,ushort const *)
0x18003368a  test    al, al
0x18003368c  jz      loc_1800337E5
0x180033692  mov     rcx, [rbp+TokenHandle]; this
0x180033696  call    ?GetIntegrityLevel@TokenHelpers@@YAKPEAX@Z; TokenHelpers::GetIntegrityLevel(void *)
0x18003369b  cmp     eax, 2000h
0x1800336a0  jnb     loc_18003374A
0x1800336a6  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800336aa  call    ?ElevateToMediumIntegrityLevel@TokenHelpers@@YAXPEAX@Z; TokenHelpers::ElevateToMediumIntegrityLevel(void *)
0x1800336af  jmp     loc_18003374A
0x1800336b4  lea     rcx, [rbp+var_18]
0x1800336b8  call    ?GetCurrentThreadTokenOrEmpty@TokenHelpers@@YA?AV?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@XZ; TokenHelpers::GetCurrentThreadTokenOrEmpty(void)
0x1800336bd  mov     rdx, rax
0x1800336c0  lea     rcx, [rbp+var_28]
0x1800336c4  call    ??4?$HandleT@UHINTERNETTraits@@@Wrappers@WRL@Microsoft@@QEAAAEAV0123@$$QEAV0123@@Z; Microsoft::WRL::Wrappers::HandleT<HINTERNETTraits>::operator=(Microsoft::WRL::Wrappers::HandleT<HINTERNETTraits> &&)
0x1800336c9  mov     [rbp+var_18], r14
0x1800336cd  lea     rcx, [rbp+var_18]
0x1800336d1  call    ?Close@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(void)
0x1800336d6  cmp     [rbp+TokenHandle], rsi
0x1800336da  jz      short loc_18003375B
0x1800336dc  call    cs:__imp_IsDebuggerPresent
0x1800336e2  test    eax, eax
0x1800336e4  jz      short loc_18003374A
0x1800336e6  lea     rdx, [rbp+var_28]
0x1800336ea  lea     rcx, [rbp+string]
0x1800336ee  call    ?GetTokenSid@TokenHelpers@@YA?AVHString@Wrappers@WRL@Microsoft@@AEBV?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@345@@Z; TokenHelpers::GetTokenSid(Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits> const &)
0x1800336f3  nop
0x1800336f4  xor     edx, edx; length
0x1800336f6  mov     rcx, [rax]; string
0x1800336f9  call    cs:__imp_WindowsGetStringRawBuffer
0x1800336ff  mov     [rsp+80h+var_40], rax
0x180033704  mov     [rsp+80h+var_48], rsi; unsigned __int16 *
0x180033709  mov     [rsp+80h+var_50], rsi; char *
0x18003370e  lea     rax, aInstallservice_25; "InstallService InProc Caller. Using cur"...
0x180033715  mov     [rsp+80h+var_58], rax; unsigned __int16 *
0x18003371a  mov     [rsp+80h+var_60], 0FFFFFFFFh; int
0x180033722  lea     r9, aCallercontextG; "CallerContext::_getCallerToken"
0x180033729  mov     r8d, 51h ; 'Q'; unsigned int
0x18003372f  lea     rdx, aOnecoreuapEndu_68; "onecoreuap\\enduser\\winstore\\installs"...
0x180033736  lea     ecx, [r8-4Dh]; unsigned int
0x18003373a  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x18003373f  nop
0x180033740  mov     rcx, [rbp+string]; string
0x180033744  call    cs:__imp_WindowsDeleteString
0x18003374a  mov     [rbx], r14
0x18003374d  mov     rax, [rbp+TokenHandle]
0x180033751  mov     [rbx+8], rax
0x180033755  mov     [rbp+TokenHandle], rsi
0x180033759  jmp     short loc_1800337BD
0x18003375b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SendProgressAsync@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SendProgressAsync@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SendProgressAsync> `wil::Feature<__WilFeatureTraits_Feature_SendProgressAsync>::GetImpl(void)'::`2'::impl
0x180033762  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SendProgressAsync@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SendProgressAsync>::__private_IsEnabled(void)
0x180033767  test    al, al
0x180033769  jz      short loc_180033778
0x18003376b  test    dil, dil
0x18003376e  jz      short loc_1800337B4
0x180033770  mov     r8d, 5Ch ; '\'
0x180033776  jmp     short loc_18003377E
0x180033778  mov     r8d, 61h ; 'a'; unsigned int
0x18003377e  mov     [rsp+80h+var_48], rsi; unsigned __int16 *
0x180033783  mov     [rsp+80h+var_50], rsi; char *
0x180033788  lea     rax, aInstallservice_24; "InstallService InProc Caller. Current T"...
0x18003378f  mov     [rsp+80h+var_58], rax; unsigned __int16 *
0x180033794  mov     [rsp+80h+var_60], 0FFFFFFFFh; int
0x18003379c  lea     r9, aCallercontextG; "CallerContext::_getCallerToken"
0x1800337a3  lea     rdx, aOnecoreuapEndu_68; "onecoreuap\\enduser\\winstore\\installs"...
0x1800337aa  mov     ecx, 2; unsigned int
0x1800337af  call    ?LogSimpleMessage@@YAXIPEBDI0JPEBG01@Z; LogSimpleMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *)
0x1800337b4  mov     rcx, rbx
0x1800337b7  call    ?GetSelfToken@TokenHelpers@@YA?AV?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@XZ; TokenHelpers::GetSelfToken(void)
0x1800337bc  nop
0x1800337bd  mov     [rbp+var_28], r14
0x1800337c1  lea     rcx, [rbp+var_28]
0x1800337c5  call    ?Close@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(void)
0x1800337ca  mov     rax, rbx
0x1800337cd  lea     r11, [rsp+80h+var_s0]
0x1800337d5  mov     rbx, [r11+20h]
0x1800337d9  mov     rsi, [r11+28h]
0x1800337dd  mov     rsp, r11
0x1800337e0  pop     r14
0x1800337e2  pop     rdi
0x1800337e3  pop     rbp
0x1800337e4  retn
0x1800337e5  mov     ecx, 803FB008h
0x1800337ea  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800337ef  mov     r9d, eax; char *
0x1800337f2  mov     rcx, [rbp+18h]; this
0x1800337f6  lea     r8, aOnecoreuapEndu_68; "onecoreuap\\enduser\\winstore\\installs"...
0x1800337fd  mov     edx, 3Dh ; '='; void *
0x180033802  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
