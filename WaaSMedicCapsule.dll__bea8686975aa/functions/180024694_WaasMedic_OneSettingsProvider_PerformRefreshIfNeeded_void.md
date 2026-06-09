# WaasMedic::OneSettingsProvider::PerformRefreshIfNeeded(void)

- ea: `0x180024694`
- end: `0x180024979`
- name: `?PerformRefreshIfNeeded@OneSettingsProvider@WaasMedic@@AEAAJXZ`
- size: `741`
- prototype: `__int64 __fastcall(WaasMedic::OneSettingsProvider *__hidden this)`
- caller_count: `4`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180023b50`
- `0x180023cd0`
- `0x180023e50`
- `0x180024080`

## callees

- `0x180003bb0`
- `0x180004708`
- `0x180009a54`
- `0x180023798`
- `0x180023888`
- `0x180023a3c`
- `0x180024694`
- `0x180024980`
- `0x180024998`
- `0x180024b40`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800247ce`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800247ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800247af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800247af`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
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
  void **v19; // [rsp+70h] [rbp-90h] BYREF
  int v20; // [rsp+78h] [rbp-88h] BYREF
  char v21; // [rsp+7Ch] [rbp-84h]
  int v22; // [rsp+A0h] [rbp-60h] BYREF
  const char *v23; // [rsp+A8h] [rbp-58h]
  __int64 v24; // [rsp+B0h] [rbp-50h]
  char v25; // [rsp+B8h] [rbp-48h]
  int v26; // [rsp+C0h] [rbp-40h]
  _BYTE v27[152]; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v28; // [rsp+160h] [rbp+60h]
  int v29; // [rsp+170h] [rbp+70h]
  __int64 v30; // [rsp+178h] [rbp+78h]
  int *v31; // [rsp+180h] [rbp+80h]
  __int64 v32; // [rsp+188h] [rbp+88h]
  __int64 v33; // [rsp+190h] [rbp+90h]
  void ***v34; // [rsp+198h] [rbp+98h]
  __int64 v35; // [rsp+1A0h] [rbp+A0h]
  int v36; // [rsp+1A8h] [rbp+A8h]
  int *v37; // [rsp+1B0h] [rbp+B0h]
  char v38; // [rsp+1B8h] [rbp+B8h]
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+108h]

  if ( !WaasMedic::OneSettingsProvider::m_settingsRefreshed && WaasMedic::OneSettingsProvider::m_maxRetries > 0 )
  {
    v20 = 0;
    v21 = 0;
    v25 = 0;
    v22 = 0;
    v23 = "OneSettingsActivity";
    v24 = 0;
    v26 = 0;
    v28 = 0;
    memset_0(v27, 0, sizeof(v27));
    v29 = 1;
    v30 = 0;
    v31 = &v20;
    v32 = 0;
    v33 = 0;
    v34 = &v19;
    v35 = 0;
    v36 = 0;
    v37 = &v22;
    v38 = 0;
    v19 = &WaasMedic::TelemetryProvider::OneSettingsActivity::`vftable';
    WaasMedic::TelemetryProvider::OneSettingsActivity::StartActivity((WaasMedic::TelemetryProvider::OneSettingsActivity *)&v19);
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
      JUMPOUT(0x180024978LL);
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
      v19 = &WaasMedic::TelemetryProvider::OneSettingsActivity::`vftable';
      wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v19);
      wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(&v19);
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
    wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(&v19);
    if ( v15 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    v19 = &WaasMedic::TelemetryProvider::OneSettingsActivity::`vftable';
    wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v19);
    wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(&v19);
  }
  return 0;
}

```

## disassembly

```asm
0x180024694  push    rbp
0x180024696  push    rbx
0x180024697  push    rsi
0x180024698  push    rdi
0x180024699  push    r14
0x18002469b  push    r15
0x18002469d  lea     rbp, [rsp-0D8h]
0x1800246a5  sub     rsp, 1D8h
0x1800246ac  mov     rax, cs:__security_cookie
0x1800246b3  xor     rax, rsp
0x1800246b6  mov     [rbp+100h+var_40], rax
0x1800246bd  mov     rdi, rcx
0x1800246c0  xor     r14d, r14d
0x1800246c3  cmp     cs:?m_settingsRefreshed@OneSettingsProvider@WaasMedic@@0_NA, r14b; bool WaasMedic::OneSettingsProvider::m_settingsRefreshed
0x1800246ca  jnz     loc_180024950
0x1800246d0  cmp     cs:?m_maxRetries@OneSettingsProvider@WaasMedic@@0HA, r14d; int WaasMedic::OneSettingsProvider::m_maxRetries
0x1800246d7  jle     loc_180024950
0x1800246dd  mov     [rsp+200h+var_188], r14d
0x1800246e2  mov     [rsp+200h+var_184], r14b
0x1800246e7  mov     [rbp+100h+var_148], r14b
0x1800246eb  mov     [rbp+100h+var_160], r14d
0x1800246ef  lea     rax, aOnesettingsact; "OneSettingsActivity"
0x1800246f6  mov     [rbp+100h+var_158], rax
0x1800246fa  mov     [rbp+100h+var_150], r14
0x1800246fe  mov     [rbp+100h+var_140], r14d
0x180024702  xorps   xmm0, xmm0
0x180024705  movdqa  [rbp+100h+var_A0], xmm0
0x18002470a  xor     edx, edx; Val
0x18002470c  mov     r8d, 98h; Size
0x180024712  lea     rcx, [rbp+100h+var_138]; void *
0x180024716  call    memset_0
0x18002471b  mov     [rbp+100h+var_90], 1
0x180024722  xor     eax, eax
0x180024724  mov     [rbp+100h+var_88], rax
0x180024728  lea     rax, [rsp+200h+var_188]
0x18002472d  mov     [rbp+100h+var_80], rax
0x180024734  mov     [rbp+100h+var_78], r14
0x18002473b  mov     [rbp+100h+var_70], r14
0x180024742  lea     rax, [rsp+200h+var_190]
0x180024747  mov     [rbp+100h+var_68], rax
0x18002474e  mov     [rbp+100h+var_60], r14
0x180024755  mov     [rbp+100h+var_58], r14d
0x18002475c  lea     rax, [rbp+100h+var_160]
0x180024760  mov     [rbp+100h+var_50], rax
0x180024767  mov     [rbp+100h+var_48], r14b
0x18002476e  lea     r15, ??_7OneSettingsActivity@TelemetryProvider@WaasMedic@@6B@; const WaasMedic::TelemetryProvider::OneSettingsActivity::`vftable'
0x180024775  mov     [rsp+200h+var_190], r15
0x18002477a  lea     rcx, [rsp+200h+var_190]; this
0x18002477f  call    ?StartActivity@OneSettingsActivity@TelemetryProvider@WaasMedic@@QEAAXXZ; WaasMedic::TelemetryProvider::OneSettingsActivity::StartActivity(void)
0x180024784  nop
0x180024785  dec     cs:?m_maxRetries@OneSettingsProvider@WaasMedic@@0HA; int WaasMedic::OneSettingsProvider::m_maxRetries
0x18002478b  mov     [rsp+200h+var_1D0], r14
0x180024790  mov     [rsp+200h+var_1C8], r14
0x180024795  mov     [rsp+200h+string], r14
0x18002479a  lea     r9, [rsp+200h+string]; string
0x18002479f  lea     r8, [rsp+200h+hstringHeader]; hstringHeader
0x1800247a4  lea     edx, [r14+39h]; length
0x1800247a8  lea     rcx, ?RuntimeClass_Windows_Internal_Flighting_OneSettings_OneSettingsManager@@3QBGB; "Windows.Internal.Flighting.OneSettings."...
0x1800247af  call    cs:__imp_WindowsCreateStringReference
0x1800247b5  test    eax, eax
0x1800247b7  js      loc_180024971
0x1800247bd  lea     r8, [rsp+200h+var_1C8]
0x1800247c2  lea     rdx, _GUID_6ebfc469_e65b_45eb_9863_b3f57e2a5017
0x1800247c9  mov     rcx, [rsp+200h+string]
0x1800247ce  call    cs:__imp_RoGetActivationFactory
0x1800247d4  mov     ebx, eax
0x1800247d6  test    eax, eax
0x1800247d8  jns     short loc_180024828
0x1800247da  mov     rcx, [rbp+108h]; this
0x1800247e1  mov     r9d, eax; char *
0x1800247e4  lea     r8, aOnecoreEnduser_22; "onecore\\enduser\\waasmedic\\lib\\provi"...
0x1800247eb  lea     edx, [r14+6Fh]; void *
0x1800247ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800247f4  nop
0x1800247f5  mov     rcx, [rsp+200h+var_1C8]
0x1800247fa  test    rcx, rcx
0x1800247fd  jz      short loc_18002480C
0x1800247ff  mov     rax, [rcx]
0x180024802  mov     rax, [rax+10h]
0x180024806  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002480b  nop
0x18002480c  mov     rcx, [rsp+200h+var_1D0]
0x180024811  test    rcx, rcx
0x180024814  jz      short loc_180024823
0x180024816  mov     rax, [rcx]
0x180024819  mov     rax, [rax+10h]
0x18002481d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024822  nop
0x180024823  jmp     loc_1800248DA
0x180024828  mov     rbx, [rsp+200h+var_1C8]
0x18002482d  mov     rax, [rbx]
0x180024830  mov     rsi, [rax+38h]
0x180024834  mov     rcx, [rsp+200h+var_1D0]
0x180024839  mov     [rsp+200h+var_1D0], r14
0x18002483e  test    rcx, rcx
0x180024841  jz      short loc_180024850
0x180024843  mov     rax, [rcx]
0x180024846  mov     rax, [rax+10h]
0x18002484a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002484f  nop
0x180024850  lea     rax, [rdi+8]
0x180024854  cmp     qword ptr [rax+18h], 7
0x180024859  jbe     short loc_18002485E
0x18002485b  mov     rax, [rax]
0x18002485e  mov     [rsp+200h+var_1C0], rax
0x180024863  lea     rdx, [rsp+200h+var_1C0]
0x180024868  lea     rcx, [rsp+200h+hstringHeader]
0x18002486d  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180024872  nop
0x180024873  lea     r9, [rsp+200h+var_1D0]
0x180024878  xor     r8d, r8d
0x18002487b  mov     rdx, [rax+18h]
0x18002487f  mov     rcx, rbx
0x180024882  mov     rax, rsi
0x180024885  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002488a  mov     ebx, eax
0x18002488c  test    eax, eax
0x18002488e  jns     short loc_1800248F7
0x180024890  mov     rcx, [rbp+108h]; this
0x180024897  mov     r9d, eax; char *
0x18002489a  lea     r8, aOnecoreEnduser_22; "onecore\\enduser\\waasmedic\\lib\\provi"...
0x1800248a1  mov     edx, 70h ; 'p'; void *
0x1800248a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800248ab  nop
0x1800248ac  mov     rcx, [rsp+200h+var_1C8]
0x1800248b1  test    rcx, rcx
0x1800248b4  jz      short loc_1800248C3
0x1800248b6  mov     rax, [rcx]
0x1800248b9  mov     rax, [rax+10h]
0x1800248bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800248c2  nop
0x1800248c3  mov     rcx, [rsp+200h+var_1D0]
0x1800248c8  test    rcx, rcx
0x1800248cb  jz      short loc_1800248DA
0x1800248cd  mov     rax, [rcx]
0x1800248d0  mov     rax, [rax+10h]
0x1800248d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800248d9  nop
0x1800248da  mov     [rsp+200h+var_190], r15
0x1800248df  lea     rcx, [rsp+200h+var_190]
0x1800248e4  call    ?Destroy@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800248e9  lea     rcx, [rsp+200h+var_190]
0x1800248ee  call    ??1?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800248f3  mov     eax, ebx
0x1800248f5  jmp     short loc_180024952
0x1800248f7  mov     cs:?m_settingsRefreshed@OneSettingsProvider@WaasMedic@@0_NA, 1; bool WaasMedic::OneSettingsProvider::m_settingsRefreshed
0x1800248fe  lea     rcx, [rsp+200h+var_190]
0x180024903  call    ?Stop@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180024908  nop
0x180024909  mov     rcx, [rsp+200h+var_1C8]
0x18002490e  test    rcx, rcx
0x180024911  jz      short loc_180024920
0x180024913  mov     rax, [rcx]
0x180024916  mov     rax, [rax+10h]
0x18002491a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002491f  nop
0x180024920  mov     rcx, [rsp+200h+var_1D0]
0x180024925  test    rcx, rcx
0x180024928  jz      short loc_180024937
0x18002492a  mov     rax, [rcx]
0x18002492d  mov     rax, [rax+10h]
0x180024931  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024936  nop
0x180024937  mov     [rsp+200h+var_190], r15
0x18002493c  lea     rcx, [rsp+200h+var_190]
0x180024941  call    ?Destroy@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180024946  lea     rcx, [rsp+200h+var_190]
0x18002494b  call    ??1?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x180024950  xor     eax, eax
0x180024952  mov     rcx, [rbp+100h+var_40]
0x180024959  xor     rcx, rsp; StackCookie
0x18002495c  call    __security_check_cookie
0x180024961  add     rsp, 1D8h
0x180024968  pop     r15
0x18002496a  pop     r14
0x18002496c  pop     rdi
0x18002496d  pop     rsi
0x18002496e  pop     rbx
0x18002496f  pop     rbp
0x180024970  retn
0x180024971  mov     ecx, eax; this
0x180024973  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
