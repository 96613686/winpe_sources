# WaasMedic::OneSettingsProvider::PerformRefreshIfNeeded(void)

- ea: `0x180024bbc`
- end: `0x180024e3f`
- name: `?PerformRefreshIfNeeded@OneSettingsProvider@WaasMedic@@AEAAJXZ`
- size: `643`
- prototype: `__int64 __fastcall(WaasMedic::OneSettingsProvider *__hidden this)`
- caller_count: `4`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180024460`
- `0x180024610`
- `0x1800247c0`
- `0x180024a10`

## callees

- `0x1800050a0`
- `0x18000bbd4`
- `0x18000f658`
- `0x1800101c8`
- `0x180012540`
- `0x18001afd4`
- `0x180024360`
- `0x180024bbc`
- `0x180024e48`
- `0x180024e60`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180024c66`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180024c66`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180024c85`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180024c85`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall WaasMedic::OneSettingsProvider::PerformRefreshIfNeeded(WaasMedic::OneSettingsProvider *this)
{
  HRESULT v2; // eax
  int v3; // edx
  unsigned int v4; // r8d
  int ActivationFactory; // eax
  unsigned int v6; // ebx
  __int64 v7; // rbx
  __int64 (__fastcall *v8)(__int64, _QWORD, _QWORD, __int64 *); // rsi
  _QWORD *v9; // rax
  __int64 v10; // rax
  int v11; // eax
  int v13; // [rsp+20h] [rbp-E0h]
  __int64 v14; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v15; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD *v16; // [rsp+40h] [rbp-C0h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-B8h] BYREF
  HSTRING string; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v19[42]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+E8h]

  if ( !WaasMedic::OneSettingsProvider::m_settingsRefreshed && WaasMedic::OneSettingsProvider::m_maxRetries > 0 )
  {
    wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
      v19,
      "OneSettingsActivity");
    v19[0] = &WaasMedic::TelemetryProvider::OneSettingsActivity::`vftable';
    WaasMedic::TelemetryProvider::OneSettingsActivity::StartActivity((WaasMedic::TelemetryProvider::OneSettingsActivity *)v19);
    --WaasMedic::OneSettingsProvider::m_maxRetries;
    v14 = 0;
    v15 = 0;
    string = 0;
    v2 = WindowsCreateStringReference(
           L"Windows.Internal.Flighting.OneSettings.OneSettingsManager",
           0x39u,
           &hstringHeader,
           &string);
    if ( v2 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v2, v3, v4);
      JUMPOUT(0x180024E3ELL);
    }
    ActivationFactory = RoGetActivationFactory(string, &GUID_6ebfc469_e65b_45eb_9863_b3f57e2a5017, &v15);
    v6 = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6F,
        (unsigned int)"onecore\\enduser\\waasmedic\\lib\\providers\\onesettingsprovider.cpp",
        (const char *)(unsigned int)ActivationFactory,
        v13);
      if ( v15 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
LABEL_15:
      v19[0] = &WaasMedic::TelemetryProvider::OneSettingsActivity::`vftable';
      wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v19);
      wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v19);
      return v6;
    }
    v7 = v15;
    v8 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v15 + 56LL);
    v14 = 0;
    v9 = (_QWORD *)((char *)this + 8);
    if ( *((_QWORD *)this + 4) > 7u )
      v9 = (_QWORD *)*v9;
    v16 = v9;
    v10 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v16);
    v11 = v8(v7, *(_QWORD *)(v10 + 24), 0, &v14);
    v6 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x70,
        (unsigned int)"onecore\\enduser\\waasmedic\\lib\\providers\\onesettingsprovider.cpp",
        (const char *)(unsigned int)v11,
        v13);
      if ( v15 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      if ( v14 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      goto LABEL_15;
    }
    WaasMedic::OneSettingsProvider::m_settingsRefreshed = 1;
    wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
      v19,
      0);
    if ( v15 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    v19[0] = &WaasMedic::TelemetryProvider::OneSettingsActivity::`vftable';
    wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v19);
    wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v19);
  }
  return 0;
}

```

## disassembly

```asm
0x180024bbc  mov     [rsp-8+arg_8], rbx
0x180024bc1  mov     [rsp-8+arg_10], rsi
0x180024bc6  push    rbp
0x180024bc7  push    rdi
0x180024bc8  push    r15
0x180024bca  lea     rbp, [rsp-0D0h]
0x180024bd2  sub     rsp, 1D0h
0x180024bd9  mov     rax, cs:__security_cookie
0x180024be0  xor     rax, rsp
0x180024be3  mov     [rbp+0E0h+var_20], rax
0x180024bea  mov     rdi, rcx
0x180024bed  cmp     cs:?m_settingsRefreshed@OneSettingsProvider@WaasMedic@@0_NA, 0; bool WaasMedic::OneSettingsProvider::m_settingsRefreshed
0x180024bf4  jnz     loc_180024E0E
0x180024bfa  cmp     cs:?m_maxRetries@OneSettingsProvider@WaasMedic@@0HA, 0; int WaasMedic::OneSettingsProvider::m_maxRetries
0x180024c01  jle     loc_180024E0E
0x180024c07  lea     rdx, aOnesettingsact; "OneSettingsActivity"
0x180024c0e  lea     rcx, [rsp+1E0h+var_170]
0x180024c13  call    ??0?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180024c18  lea     r15, ??_7OneSettingsActivity@TelemetryProvider@WaasMedic@@6B@; const WaasMedic::TelemetryProvider::OneSettingsActivity::`vftable'
0x180024c1f  mov     [rsp+1E0h+var_170], r15
0x180024c24  lea     rcx, [rsp+1E0h+var_170]; this
0x180024c29  call    ?StartActivity@OneSettingsActivity@TelemetryProvider@WaasMedic@@QEAAXXZ; WaasMedic::TelemetryProvider::OneSettingsActivity::StartActivity(void)
0x180024c2e  nop
0x180024c2f  dec     cs:?m_maxRetries@OneSettingsProvider@WaasMedic@@0HA; int WaasMedic::OneSettingsProvider::m_maxRetries
0x180024c35  mov     [rsp+1E0h+var_1B0], 0
0x180024c3e  mov     [rsp+1E0h+var_1A8], 0
0x180024c47  mov     [rsp+1E0h+string], 0
0x180024c50  lea     r9, [rsp+1E0h+string]; string
0x180024c55  lea     r8, [rsp+1E0h+hstringHeader]; hstringHeader
0x180024c5a  mov     edx, 39h ; '9'; length
0x180024c5f  lea     rcx, ?RuntimeClass_Windows_Internal_Flighting_OneSettings_OneSettingsManager@@3QBGB; "Windows.Internal.Flighting.OneSettings."...
0x180024c66  call    cs:__imp_WindowsCreateStringReference
0x180024c6c  test    eax, eax
0x180024c6e  js      loc_180024E37
0x180024c74  lea     r8, [rsp+1E0h+var_1A8]
0x180024c79  lea     rdx, _GUID_6ebfc469_e65b_45eb_9863_b3f57e2a5017
0x180024c80  mov     rcx, [rsp+1E0h+string]
0x180024c85  call    cs:__imp_RoGetActivationFactory
0x180024c8b  mov     ebx, eax
0x180024c8d  test    eax, eax
0x180024c8f  jns     short loc_180024CE0
0x180024c91  mov     rcx, [rbp+0E8h]; this
0x180024c98  mov     r9d, eax; char *
0x180024c9b  lea     r8, aOnecoreEnduser_12; "onecore\\enduser\\waasmedic\\lib\\provi"...
0x180024ca2  mov     edx, 6Fh ; 'o'; void *
0x180024ca7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024cac  nop
0x180024cad  mov     rcx, [rsp+1E0h+var_1A8]
0x180024cb2  test    rcx, rcx
0x180024cb5  jz      short loc_180024CC4
0x180024cb7  mov     rax, [rcx]
0x180024cba  mov     rax, [rax+10h]
0x180024cbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024cc3  nop
0x180024cc4  mov     rcx, [rsp+1E0h+var_1B0]
0x180024cc9  test    rcx, rcx
0x180024ccc  jz      short loc_180024CDB
0x180024cce  mov     rax, [rcx]
0x180024cd1  mov     rax, [rax+10h]
0x180024cd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024cda  nop
0x180024cdb  jmp     loc_180024D96
0x180024ce0  mov     rbx, [rsp+1E0h+var_1A8]
0x180024ce5  mov     rax, [rbx]
0x180024ce8  mov     rsi, [rax+38h]
0x180024cec  mov     rcx, [rsp+1E0h+var_1B0]
0x180024cf1  mov     [rsp+1E0h+var_1B0], 0
0x180024cfa  test    rcx, rcx
0x180024cfd  jz      short loc_180024D0C
0x180024cff  mov     rax, [rcx]
0x180024d02  mov     rax, [rax+10h]
0x180024d06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024d0b  nop
0x180024d0c  lea     rax, [rdi+8]
0x180024d10  cmp     qword ptr [rax+18h], 7
0x180024d15  jbe     short loc_180024D1A
0x180024d17  mov     rax, [rax]
0x180024d1a  mov     [rsp+1E0h+var_1A0], rax
0x180024d1f  lea     rdx, [rsp+1E0h+var_1A0]
0x180024d24  lea     rcx, [rsp+1E0h+hstringHeader]
0x180024d29  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180024d2e  nop
0x180024d2f  lea     r9, [rsp+1E0h+var_1B0]
0x180024d34  xor     r8d, r8d
0x180024d37  mov     rdx, [rax+18h]
0x180024d3b  mov     rcx, rbx
0x180024d3e  mov     rax, rsi
0x180024d41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024d46  mov     ebx, eax
0x180024d48  test    eax, eax
0x180024d4a  jns     short loc_180024DB3
0x180024d4c  mov     rcx, [rbp+0E8h]; this
0x180024d53  mov     r9d, eax; char *
0x180024d56  lea     r8, aOnecoreEnduser_12; "onecore\\enduser\\waasmedic\\lib\\provi"...
0x180024d5d  mov     edx, 70h ; 'p'; void *
0x180024d62  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024d67  nop
0x180024d68  mov     rcx, [rsp+1E0h+var_1A8]
0x180024d6d  test    rcx, rcx
0x180024d70  jz      short loc_180024D7F
0x180024d72  mov     rax, [rcx]
0x180024d75  mov     rax, [rax+10h]
0x180024d79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024d7e  nop
0x180024d7f  mov     rcx, [rsp+1E0h+var_1B0]
0x180024d84  test    rcx, rcx
0x180024d87  jz      short loc_180024D96
0x180024d89  mov     rax, [rcx]
0x180024d8c  mov     rax, [rax+10h]
0x180024d90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024d95  nop
0x180024d96  mov     [rsp+1E0h+var_170], r15
0x180024d9b  lea     rcx, [rsp+1E0h+var_170]
0x180024da0  call    ?Destroy@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180024da5  lea     rcx, [rsp+1E0h+var_170]
0x180024daa  call    ??1?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x180024daf  mov     eax, ebx
0x180024db1  jmp     short loc_180024E10
0x180024db3  mov     cs:?m_settingsRefreshed@OneSettingsProvider@WaasMedic@@0_NA, 1; bool WaasMedic::OneSettingsProvider::m_settingsRefreshed
0x180024dba  xor     edx, edx
0x180024dbc  lea     rcx, [rsp+1E0h+var_170]
0x180024dc1  call    ?Stop@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180024dc6  nop
0x180024dc7  mov     rcx, [rsp+1E0h+var_1A8]
0x180024dcc  test    rcx, rcx
0x180024dcf  jz      short loc_180024DDE
0x180024dd1  mov     rax, [rcx]
0x180024dd4  mov     rax, [rax+10h]
0x180024dd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024ddd  nop
0x180024dde  mov     rcx, [rsp+1E0h+var_1B0]
0x180024de3  test    rcx, rcx
0x180024de6  jz      short loc_180024DF5
0x180024de8  mov     rax, [rcx]
0x180024deb  mov     rax, [rax+10h]
0x180024def  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024df4  nop
0x180024df5  mov     [rsp+1E0h+var_170], r15
0x180024dfa  lea     rcx, [rsp+1E0h+var_170]
0x180024dff  call    ?Destroy@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180024e04  lea     rcx, [rsp+1E0h+var_170]
0x180024e09  call    ??1?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x180024e0e  xor     eax, eax
0x180024e10  mov     rcx, [rbp+0E0h+var_20]
0x180024e17  xor     rcx, rsp; StackCookie
0x180024e1a  call    __security_check_cookie
0x180024e1f  lea     r11, [rsp+1E0h+var_10]
0x180024e27  mov     rbx, [r11+28h]
0x180024e2b  mov     rsi, [r11+30h]
0x180024e2f  mov     rsp, r11
0x180024e32  pop     r15
0x180024e34  pop     rdi
0x180024e35  pop     rbp
0x180024e36  retn
0x180024e37  mov     ecx, eax; this
0x180024e39  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
