# WOSCSettings::WOSCSettings(bool)

- ea: `0x18003d178`
- end: `0x18003d47d`
- name: `??0WOSCSettings@@AEAA@_N@Z`
- size: `773`
- prototype: `WOSCSettings *__fastcall(WOSCSettings *__hidden this, bool)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18003e98c`

## callees

- `0x180007660`
- `0x1800209fc`
- `0x1800233b8`
- `0x18003d178`
- `0x18003eccc`
- `0x180071010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003d258`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003d258`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d29e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d29e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18003d26d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18003d27e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18003d28f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18003d26d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18003d27e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18003d28f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003d1f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003d2db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003d340`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003d3a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003d1f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003d2db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003d340`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003d3a6`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18003d212`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18003d35d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18003d212`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18003d35d`

## string_xrefs

- `0x18003d40c`: `onecore\enduser\windowsupdate\muse\common\lib\woscsettings.cpp`
- `0x18003d429`: `onecore\enduser\windowsupdate\muse\common\lib\woscsettings.cpp`
- `0x18003d446`: `onecore\enduser\windowsupdate\muse\common\lib\woscsettings.cpp`
- `0x18003d463`: `onecore\enduser\windowsupdate\muse\common\lib\woscsettings.cpp`
- `0x18003d262`: `LastRefreshAttempted`
- `0x18003d284`: `LastUpdated`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
WOSCSettings *__fastcall WOSCSettings::WOSCSettings(WOSCSettings *this, char a2)
{
  HRESULT v3; // eax
  int v4; // edx
  unsigned int v5; // r8d
  int ActivationFactory; // eax
  wil::details::in1diag3 *v7; // rcx
  __int64 *v8; // rdi
  __int64 v9; // rsi
  __int64 v10; // rcx
  HRESULT v11; // eax
  int v12; // edx
  unsigned int v13; // r8d
  int v14; // eax
  wil::details::in1diag3 *v15; // rcx
  void (*v16)(void); // rax
  HRESULT v17; // eax
  int v18; // edx
  unsigned int v19; // r8d
  int v20; // eax
  wil::details::in1diag3 *v21; // rcx
  __int64 *v22; // rdi
  __int64 v23; // rsi
  __int64 v24; // rcx
  HRESULT v25; // eax
  int v26; // edx
  unsigned int v27; // r8d
  int v28; // eax
  int phkResult; // [rsp+20h] [rbp-50h]
  __int64 *v31; // [rsp+30h] [rbp-40h] BYREF
  HKEY hKey[2]; // [rsp+38h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-28h] BYREF
  HSTRING string; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  hKey[1] = (HKEY)this;
  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 2;
  *((_OWORD *)this + 2) = 0;
  *((_OWORD *)this + 3) = 0;
  *((_OWORD *)this + 4) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_DWORD *)this + 20) = -1;
  *((_DWORD *)this + 21) = 0;
  if ( a2 )
  {
    v31 = 0;
    string = 0;
    v3 = WindowsCreateStringReference(
           L"Windows.Internal.Flighting.OneSettings.OneSettingsManager",
           0x39u,
           &hstringHeader,
           &string);
    if ( v3 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v3, v4, v5);
    }
    else
    {
      ActivationFactory = RoGetActivationFactory(string, &GUID_6ebfc469_e65b_45eb_9863_b3f57e2a5017, &v31);
      v7 = retaddr;
      if ( ActivationFactory >= 0 )
      {
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_OneSettingsForceRefresh>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_OneSettingsForceRefresh>::GetImpl'::`2'::impl) )
        {
          hKey[0] = 0;
          if ( RegOpenKeyExW(
                 HKEY_LOCAL_MACHINE,
                 L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Wosc\\Client\\Persistent\\ClientState\\MUSE",
                 0,
                 0xF003Fu,
                 hKey) >= 0 )
          {
            RegDeleteValueW(hKey[0], L"LastRefreshAttempted");
            RegDeleteValueW(hKey[0], L"LastRefreshByApp");
            RegDeleteValueW(hKey[0], L"LastUpdated");
          }
          if ( hKey[0] )
            RegCloseKey(hKey[0]);
        }
        v8 = v31;
        v9 = *v31;
        v10 = *(_QWORD *)this;
        *(_QWORD *)this = 0;
        if ( v10 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
        string = 0;
        v11 = WindowsCreateStringReference(L"MUSE", 4u, &hstringHeader, &string);
        if ( v11 < 0 )
        {
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v11, v12, v13);
        }
        else
        {
          v14 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, _QWORD, WOSCSettings *))(v9 + 56))(v8, string, 0, this);
          v15 = retaddr;
          if ( v14 >= 0 )
          {
            if ( v31 )
            {
              v16 = *(void (**)(void))(*v31 + 16);
LABEL_23:
              v16();
              return this;
            }
            return this;
          }
        }
        wil::details::in1diag3::Throw_Hr(
          v15,
          (void *)0x2C,
          (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\common\\lib\\woscsettings.cpp",
          (const char *)(unsigned int)v14,
          phkResult);
      }
    }
    wil::details::in1diag3::Throw_Hr(
      v7,
      (void *)0x19,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\common\\lib\\woscsettings.cpp",
      (const char *)(unsigned int)ActivationFactory,
      phkResult);
  }
  v31 = 0;
  string = 0;
  v17 = WindowsCreateStringReference(
          L"Windows.Internal.Flighting.OneSettings.OneSettingsPayload",
          0x39u,
          &hstringHeader,
          &string);
  if ( v17 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v17, v18, v19);
LABEL_31:
    wil::details::in1diag3::Throw_Hr(
      v21,
      (void *)0x33,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\common\\lib\\woscsettings.cpp",
      (const char *)(unsigned int)v20,
      phkResult);
  }
  v20 = RoGetActivationFactory(string, &GUID_d70cd0ed_0f1b_4bec_9bec_c230dc7996b0, &v31);
  v21 = retaddr;
  if ( v20 < 0 )
    goto LABEL_31;
  v22 = v31;
  v23 = *v31;
  v24 = *(_QWORD *)this;
  *(_QWORD *)this = 0;
  if ( v24 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  string = 0;
  v25 = WindowsCreateStringReference(L"MUSE", 4u, &hstringHeader, &string);
  if ( v25 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v25, v26, v27);
    JUMPOUT(0x18003D47CLL);
  }
  v28 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, WOSCSettings *))(v23 + 48))(v22, string, this);
  if ( v28 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x37,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\common\\lib\\woscsettings.cpp",
      (const char *)(unsigned int)v28,
      phkResult);
  if ( v31 )
  {
    v16 = *(void (**)(void))(*v31 + 16);
    goto LABEL_23;
  }
  return this;
}

```

## disassembly

```asm
0x18003d178  mov     [rsp-18h+arg_8], rbx
0x18003d17d  mov     [rsp-18h+arg_10], rsi
0x18003d182  push    rbp
0x18003d183  push    rdi
0x18003d184  push    r14
0x18003d186  mov     rbp, rsp
0x18003d189  sub     rsp, 70h
0x18003d18d  mov     rax, cs:__security_cookie
0x18003d194  xor     rax, rsp
0x18003d197  mov     [rbp+var_8], rax
0x18003d19b  mov     rbx, rcx
0x18003d19e  mov     [rbp+var_30], rcx
0x18003d1a2  xor     r14d, r14d
0x18003d1a5  mov     [rcx], r14
0x18003d1a8  mov     qword ptr [rcx+8], 2
0x18003d1b0  xorps   xmm0, xmm0
0x18003d1b3  movups  xmmword ptr [rcx+20h], xmm0
0x18003d1b7  movups  xmmword ptr [rcx+30h], xmm0
0x18003d1bb  movups  xmmword ptr [rcx+40h], xmm0
0x18003d1bf  mov     [rcx+10h], r14
0x18003d1c3  mov     [rcx+18h], r14
0x18003d1c7  mov     dword ptr [rcx+50h], 0FFFFFFFFh
0x18003d1ce  mov     [rcx+54h], r14d
0x18003d1d2  test    dl, dl
0x18003d1d4  jz      loc_18003D324
0x18003d1da  mov     [rbp+var_40], r14
0x18003d1de  mov     [rbp+string], r14
0x18003d1e2  lea     r9, [rbp+string]; string
0x18003d1e6  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18003d1ea  lea     edx, [r14+39h]; length
0x18003d1ee  lea     rcx, ?RuntimeClass_Windows_Internal_Flighting_OneSettings_OneSettingsManager@@3QBGB; "Windows.Internal.Flighting.OneSettings."...
0x18003d1f5  call    cs:__imp_WindowsCreateStringReference
0x18003d1fb  test    eax, eax
0x18003d1fd  js      loc_18003D41E
0x18003d203  lea     r8, [rbp+var_40]
0x18003d207  lea     rdx, _GUID_6ebfc469_e65b_45eb_9863_b3f57e2a5017
0x18003d20e  mov     rcx, [rbp+string]
0x18003d212  call    cs:__imp_RoGetActivationFactory
0x18003d218  mov     rcx, [rbp+18h]
0x18003d21c  test    eax, eax
0x18003d21e  js      loc_18003D426
0x18003d224  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_OneSettingsForceRefresh@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_OneSettingsForceRefresh@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_OneSettingsForceRefresh> `wil::Feature<__WilFeatureTraits_Feature_Containment_OneSettingsForceRefresh>::GetImpl(void)'::`2'::impl
0x18003d22b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_OneSettingsForceRefresh@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_OneSettingsForceRefresh>::__private_IsEnabled(void)
0x18003d230  test    al, al
0x18003d232  jz      short loc_18003D2A4
0x18003d234  mov     [rbp+hKey], r14
0x18003d238  lea     rax, [rbp+hKey]
0x18003d23c  mov     qword ptr [rsp+70h+phkResult], rax; int
0x18003d241  mov     r9d, 0F003Fh; samDesired
0x18003d247  xor     r8d, r8d; ulOptions
0x18003d24a  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18003d251  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003d258  call    cs:__imp_RegOpenKeyExW
0x18003d25e  test    eax, eax
0x18003d260  js      short loc_18003D295
0x18003d262  lea     rdx, aLastrefreshatt; "LastRefreshAttempted"
0x18003d269  mov     rcx, [rbp+hKey]; hKey
0x18003d26d  call    cs:__imp_RegDeleteValueW
0x18003d273  lea     rdx, aLastrefreshbya; "LastRefreshByApp"
0x18003d27a  mov     rcx, [rbp+hKey]; hKey
0x18003d27e  call    cs:__imp_RegDeleteValueW
0x18003d284  lea     rdx, aLastupdated; "LastUpdated"
0x18003d28b  mov     rcx, [rbp+hKey]; hKey
0x18003d28f  call    cs:__imp_RegDeleteValueW
0x18003d295  mov     rcx, [rbp+hKey]; hKey
0x18003d299  test    rcx, rcx
0x18003d29c  jz      short loc_18003D2A4
0x18003d29e  call    cs:__imp_RegCloseKey
0x18003d2a4  mov     rdi, [rbp+var_40]
0x18003d2a8  mov     rsi, [rdi]
0x18003d2ab  mov     rcx, [rbx]
0x18003d2ae  mov     [rbx], r14
0x18003d2b1  test    rcx, rcx
0x18003d2b4  jz      short loc_18003D2C3
0x18003d2b6  mov     rax, [rcx]
0x18003d2b9  mov     rax, [rax+10h]
0x18003d2bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d2c2  nop
0x18003d2c3  mov     [rbp+string], r14
0x18003d2c7  lea     r9, [rbp+string]; string
0x18003d2cb  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18003d2cf  mov     edx, 4; length
0x18003d2d4  lea     rcx, aMuse; "MUSE"
0x18003d2db  call    cs:__imp_WindowsCreateStringReference
0x18003d2e1  test    eax, eax
0x18003d2e3  js      loc_18003D43B
0x18003d2e9  mov     r9, rbx
0x18003d2ec  xor     r8d, r8d
0x18003d2ef  mov     rdx, [rbp+string]
0x18003d2f3  mov     rcx, rdi
0x18003d2f6  mov     rax, [rsi+38h]
0x18003d2fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d2ff  mov     rcx, [rbp+18h]
0x18003d303  test    eax, eax
0x18003d305  js      loc_18003D443
0x18003d30b  mov     rcx, [rbp+var_40]
0x18003d30f  test    rcx, rcx
0x18003d312  jz      loc_18003D3E5
0x18003d318  mov     rax, [rcx]
0x18003d31b  mov     rax, [rax+10h]
0x18003d31f  jmp     loc_18003D3DF
0x18003d324  mov     [rbp+var_40], r14
0x18003d328  mov     [rbp+string], r14
0x18003d32c  lea     r9, [rbp+string]; string
0x18003d330  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18003d334  mov     edx, 39h ; '9'; length
0x18003d339  lea     rcx, ?RuntimeClass_Windows_Internal_Flighting_OneSettings_OneSettingsPayload@@3QBGB; "Windows.Internal.Flighting.OneSettings."...
0x18003d340  call    cs:__imp_WindowsCreateStringReference
0x18003d346  test    eax, eax
0x18003d348  js      loc_18003D458
0x18003d34e  lea     r8, [rbp+var_40]
0x18003d352  lea     rdx, _GUID_d70cd0ed_0f1b_4bec_9bec_c230dc7996b0
0x18003d359  mov     rcx, [rbp+string]
0x18003d35d  call    cs:__imp_RoGetActivationFactory
0x18003d363  mov     rcx, [rbp+18h]
0x18003d367  test    eax, eax
0x18003d369  js      loc_18003D460
0x18003d36f  mov     rdi, [rbp+var_40]
0x18003d373  mov     rsi, [rdi]
0x18003d376  mov     rcx, [rbx]
0x18003d379  mov     [rbx], r14
0x18003d37c  test    rcx, rcx
0x18003d37f  jz      short loc_18003D38E
0x18003d381  mov     rax, [rcx]
0x18003d384  mov     rax, [rax+10h]
0x18003d388  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d38d  nop
0x18003d38e  mov     [rbp+string], r14
0x18003d392  lea     r9, [rbp+string]; string
0x18003d396  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18003d39a  mov     edx, 4; length
0x18003d39f  lea     rcx, aMuse; "MUSE"
0x18003d3a6  call    cs:__imp_WindowsCreateStringReference
0x18003d3ac  test    eax, eax
0x18003d3ae  js      loc_18003D475
0x18003d3b4  mov     r8, rbx
0x18003d3b7  mov     rdx, [rbp+string]
0x18003d3bb  mov     rcx, rdi
0x18003d3be  mov     rax, [rsi+30h]
0x18003d3c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d3c7  mov     rcx, [rbp+18h]; this
0x18003d3cb  test    eax, eax
0x18003d3cd  js      short loc_18003D409
0x18003d3cf  mov     rcx, [rbp+var_40]
0x18003d3d3  test    rcx, rcx
0x18003d3d6  jz      short loc_18003D3E5
0x18003d3d8  mov     rdx, [rcx]
0x18003d3db  mov     rax, [rdx+10h]
0x18003d3df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d3e4  nop
0x18003d3e5  mov     rax, rbx
0x18003d3e8  mov     rcx, [rbp+var_8]
0x18003d3ec  xor     rcx, rsp; StackCookie
0x18003d3ef  call    __security_check_cookie
0x18003d3f4  lea     r11, [rsp+70h+var_s0]
0x18003d3f9  mov     rbx, [r11+28h]
0x18003d3fd  mov     rsi, [r11+30h]
0x18003d401  mov     rsp, r11
0x18003d404  pop     r14
0x18003d406  pop     rdi
0x18003d407  pop     rbp
0x18003d408  retn
0x18003d409  mov     r9d, eax; char *
0x18003d40c  lea     r8, aOnecoreEnduser_3; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18003d413  mov     edx, 37h ; '7'; void *
0x18003d418  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003d41e  mov     ecx, eax; this
0x18003d420  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18003d425  nop
0x18003d426  mov     r9d, eax; char *
0x18003d429  lea     r8, aOnecoreEnduser_3; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18003d430  mov     edx, 19h; void *
0x18003d435  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003d43b  mov     ecx, eax; this
0x18003d43d  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18003d442  nop
0x18003d443  mov     r9d, eax; char *
0x18003d446  lea     r8, aOnecoreEnduser_3; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18003d44d  mov     edx, 2Ch ; ','; void *
0x18003d452  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003d458  mov     ecx, eax; this
0x18003d45a  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18003d45f  nop
0x18003d460  mov     r9d, eax; char *
0x18003d463  lea     r8, aOnecoreEnduser_3; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18003d46a  mov     edx, 33h ; '3'; void *
0x18003d46f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003d475  mov     ecx, eax; this
0x18003d477  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
