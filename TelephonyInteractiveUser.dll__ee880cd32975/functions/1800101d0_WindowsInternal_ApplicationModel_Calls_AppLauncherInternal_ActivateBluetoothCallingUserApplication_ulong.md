# WindowsInternal::ApplicationModel::Calls::AppLauncherInternal::_ActivateBluetoothCallingUserApplication(ulong *)

- ea: `0x1800101d0`
- end: `0x18001046f`
- name: `?_ActivateBluetoothCallingUserApplication@AppLauncherInternal@Calls@ApplicationModel@WindowsInternal@@MEAAJPEAK@Z`
- size: `671`
- prototype: `__int64 __fastcall(WindowsInternal::ApplicationModel::Calls::AppLauncherInternal *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800012b8`
- `0x180001dc0`
- `0x180001de4`
- `0x180007044`
- `0x18000cf2c`
- `0x18000e060`
- `0x18000e284`
- `0x18000ea30`
- `0x1800101d0`
- `0x1800105ec`
- `0x1800165c4`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180010342`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180010342`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001030b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001030b`

## pseudocode

```c
__int64 __fastcall WindowsInternal::ApplicationModel::Calls::AppLauncherInternal::_ActivateBluetoothCallingUserApplication(
        WindowsInternal::ApplicationModel::Calls::AppLauncherInternal *this,
        unsigned int *a2)
{
  int v4; // ebx
  Windows::ApplicationModel::Activation::PhoneCallActivatedEventArgsImpl *v6; // rax
  signed __int64 v7; // rdx
  __int64 v8; // rdi
  signed __int64 v9; // rcx
  bool v10; // zf
  signed __int64 v11; // rax
  signed __int32 v12; // eax
  const char *v13; // rbx
  HRESULT v14; // eax
  unsigned int v15; // esi
  LPVOID v16; // rsi
  __int64 v17; // r13
  HRESULT v18; // eax
  int v19; // edx
  unsigned int v20; // r8d
  __int64 v21; // rdx
  int v22; // ecx
  __int64 v23; // r8
  int v24; // r9d
  __int64 v25; // rdx
  __int64 v26; // r8
  LPVOID v27; // rcx
  LPVOID v28; // rcx
  const char *v29; // [rsp+40h] [rbp-40h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-38h] BYREF
  HSTRING string; // [rsp+60h] [rbp-20h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp-18h] BYREF

  *a2 = 0;
  v4 = WindowsInternal::ApplicationModel::Calls::AppLauncherInternal::_EnsureCallControlPublicApiFeatureAvailable(this);
  if ( v4 < 0 )
    goto LABEL_2;
  v6 = (Windows::ApplicationModel::Activation::PhoneCallActivatedEventArgsImpl *)operator new(
                                                                                   0xF0u,
                                                                                   (const struct std::nothrow_t *)std::nothrow);
  if ( !v6 )
  {
    v4 = -2147024882;
LABEL_2:
    Log_HREvent_0((unsigned int)v4, 1, "onecoreuap\\net\\phone\\telephonyinteractiveuser\\lib\\applauncher.cpp");
    return (unsigned int)v4;
  }
  v8 = Windows::ApplicationModel::Activation::PhoneCallActivatedEventArgsImpl::PhoneCallActivatedEventArgsImpl(v6);
  *(_OWORD *)(v8 + 224) = *((_OWORD *)this + 4);
  *(_DWORD *)(v8 + 72) = 1025;
  v9 = *(_QWORD *)(v8 + 216);
  while ( v9 >= 0 )
  {
    if ( (_DWORD)v9 != 0x7FFFFFFF )
    {
      v7 = v9 + 1;
      v11 = _InterlockedCompareExchange64((volatile signed __int64 *)(v8 + 216), v9 + 1, v9);
      v10 = v9 == v11;
      v9 = v11;
      if ( !v10 )
        continue;
    }
    goto LABEL_12;
  }
  do
  {
    v12 = *(_DWORD *)(2 * v9 + 0x10);
    if ( v12 == 0x7FFFFFFF )
      break;
    v7 = (unsigned int)(v12 + 1);
  }
  while ( v12 != _InterlockedCompareExchange((volatile signed __int32 *)(2 * v9 + 16), v7, v12) );
LABEL_12:
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,CActivatedEventArgsBase,Windows::ApplicationModel::Activation::IPhoneCallActivatedEventArgs,Microsoft::WRL::CloakedIid<Windows::Foundation::Marshaling::Internal::IValueMarshalByPropertySet>,Microsoft::WRL::FtmBase>::Release(
    v8,
    v7,
    0x7FFFFFFF);
  v29 = 0;
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,CActivatedEventArgsBase,Windows::ApplicationModel::Activation::IPhoneCallActivatedEventArgs,Microsoft::WRL::CloakedIid<Windows::Foundation::Marshaling::Internal::IValueMarshalByPropertySet>,Microsoft::WRL::FtmBase>::QueryInterface(
    v8,
    &GUID_cf651713_cd08_4fd8_b697_a281b6544e2e,
    &v29);
  v13 = v29;
  if ( !v29 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  ppv = 0;
  v14 = CoCreateInstance(&CLSID_ApplicationActivationManager, 0, 1u, &GUID_54e4c428_d1d4_47d4_ade6_46c829114a7d, &ppv);
  v15 = v14;
  if ( v14 < 0 )
    goto LABEL_17;
  v16 = ppv;
  v17 = *(_QWORD *)ppv;
  string = 0;
  v18 = WindowsCreateStringReference(L"Windows.PhoneCallActivation", 0x1Bu, &hstringHeader, &string);
  if ( v18 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v18, v19, v20);
    JUMPOUT(0x18001046ELL);
  }
  v14 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD, HSTRING, const char *, _DWORD, unsigned int *))(v17 + 24))(
          v16,
          *(_QWORD *)(*((_QWORD *)this + 4) + 16LL),
          0,
          string,
          v13,
          0,
          a2);
  v15 = v14;
  if ( v14 >= 0 )
  {
    if ( (unsigned int)dword_180025038 > 4 )
    {
      v29 = "ActivateApplicationForContractByAppId Succeeded";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v22,
        (unsigned int)byte_180020681,
        v23,
        v24,
        (__int64)&v29);
    }
    v28 = ppv;
    if ( ppv )
    {
      ppv = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v28 + 16LL))(v28);
    }
    if ( v13 )
      (*(void (__fastcall **)(const char *))(*(_QWORD *)v13 + 16LL))(v13);
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,CActivatedEventArgsBase,Windows::ApplicationModel::Activation::IPhoneCallActivatedEventArgs,Microsoft::WRL::CloakedIid<Windows::Foundation::Marshaling::Internal::IValueMarshalByPropertySet>,Microsoft::WRL::FtmBase>::Release(
      v8,
      v21,
      v23);
    return 0;
  }
  else
  {
LABEL_17:
    Log_HREvent_0((unsigned int)v14, 1, "onecoreuap\\net\\phone\\telephonyinteractiveuser\\lib\\applauncher.cpp");
    v27 = ppv;
    if ( ppv )
    {
      ppv = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v27 + 16LL))(v27);
    }
    if ( v13 )
      (*(void (__fastcall **)(const char *))(*(_QWORD *)v13 + 16LL))(v13);
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,CActivatedEventArgsBase,Windows::ApplicationModel::Activation::IPhoneCallActivatedEventArgs,Microsoft::WRL::CloakedIid<Windows::Foundation::Marshaling::Internal::IValueMarshalByPropertySet>,Microsoft::WRL::FtmBase>::Release(
      v8,
      v25,
      v26);
    return v15;
  }
}

```

## disassembly

```asm
0x1800101d0  mov     [rsp-28h+arg_10], rbx
0x1800101d5  mov     [rsp-28h+arg_18], rsi
0x1800101da  push    rbp
0x1800101db  push    rdi
0x1800101dc  push    r13
0x1800101de  push    r14
0x1800101e0  push    r15
0x1800101e2  mov     rbp, rsp
0x1800101e5  sub     rsp, 80h
0x1800101ec  mov     rax, cs:__security_cookie
0x1800101f3  xor     rax, rsp
0x1800101f6  mov     [rbp+var_10], rax
0x1800101fa  mov     r14, rdx
0x1800101fd  mov     dword ptr [rdx], 0
0x180010203  mov     r15, rcx
0x180010206  call    ?_EnsureCallControlPublicApiFeatureAvailable@AppLauncherInternal@Calls@ApplicationModel@WindowsInternal@@IEAAJXZ; WindowsInternal::ApplicationModel::Calls::AppLauncherInternal::_EnsureCallControlPublicApiFeatureAvailable(void)
0x18001020b  mov     ebx, eax
0x18001020d  test    eax, eax
0x18001020f  jns     short loc_180010231
0x180010211  mov     r9d, 166h
0x180010217  mov     edx, 1
0x18001021c  lea     r8, aOnecoreuapNetP_3; "onecoreuap\\net\\phone\\telephonyintera"...
0x180010223  mov     ecx, ebx
0x180010225  call    Log_HREvent_0
0x18001022a  mov     eax, ebx
0x18001022c  jmp     loc_18001043F
0x180010231  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180010238  mov     ecx, 0F0h; unsigned __int64
0x18001023d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180010242  test    rax, rax
0x180010245  jnz     short loc_180010254
0x180010247  mov     r9d, 169h
0x18001024d  mov     ebx, 8007000Eh
0x180010252  jmp     short loc_180010217
0x180010254  mov     rcx, rax; this
0x180010257  call    ??0PhoneCallActivatedEventArgsImpl@Activation@ApplicationModel@Windows@@QEAA@XZ; Windows::ApplicationModel::Activation::PhoneCallActivatedEventArgsImpl::PhoneCallActivatedEventArgsImpl(void)
0x18001025c  movups  xmm0, xmmword ptr [r15+40h]
0x180010261  mov     rdi, rax
0x180010264  mov     r8d, 7FFFFFFFh
0x18001026a  movdqu  xmmword ptr [rax+0E0h], xmm0
0x180010272  mov     dword ptr [rax+48h], 401h
0x180010279  mov     rcx, [rax+0D8h]
0x180010280  test    rcx, rcx
0x180010283  js      short loc_1800102AC
0x180010285  cmp     ecx, r8d
0x180010288  jz      short loc_1800102B5
0x18001028a  lea     rdx, [rcx+1]
0x18001028e  mov     rax, rcx
0x180010291  lock cmpxchg [rdi+0D8h], rdx
0x18001029a  mov     rcx, rax
0x18001029d  jnz     short loc_180010280
0x18001029f  jmp     short loc_1800102B5
0x1800102a1  lea     edx, [rax+1]
0x1800102a4  lock cmpxchg [rcx+rcx+10h], edx
0x1800102aa  jz      short loc_1800102B5
0x1800102ac  mov     eax, [rcx+rcx+10h]
0x1800102b0  cmp     eax, r8d
0x1800102b3  jnz     short loc_1800102A1
0x1800102b5  mov     rcx, rdi
0x1800102b8  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@VCActivatedEventArgsBase@@UIPhoneCallActivatedEventArgs@Activation@ApplicationModel@Windows@@U?$CloakedIid@UIValueMarshalByPropertySet@Internal@Marshaling@Foundation@Windows@@@23@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,CActivatedEventArgsBase,Windows::ApplicationModel::Activation::IPhoneCallActivatedEventArgs,Microsoft::WRL::CloakedIid<Windows::Foundation::Marshaling::Internal::IValueMarshalByPropertySet>,Microsoft::WRL::FtmBase>::Release(void)
0x1800102bd  lea     r8, [rbp+var_40]
0x1800102c1  mov     [rbp+var_40], 0
0x1800102c9  lea     rdx, _GUID_cf651713_cd08_4fd8_b697_a281b6544e2e
0x1800102d0  mov     rcx, rdi
0x1800102d3  call    ?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@VCActivatedEventArgsBase@@UIPhoneCallActivatedEventArgs@Activation@ApplicationModel@Windows@@U?$CloakedIid@UIValueMarshalByPropertySet@Internal@Marshaling@Foundation@Windows@@@23@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,CActivatedEventArgsBase,Windows::ApplicationModel::Activation::IPhoneCallActivatedEventArgs,Microsoft::WRL::CloakedIid<Windows::Foundation::Marshaling::Internal::IValueMarshalByPropertySet>,Microsoft::WRL::FtmBase>::QueryInterface(_GUID const &,void * *)
0x1800102d8  mov     rbx, [rbp+var_40]
0x1800102dc  test    rbx, rbx
0x1800102df  jnz     short loc_1800102E6
0x1800102e1  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800102e6  xor     edx, edx; pUnkOuter
0x1800102e8  mov     [rbp+var_18], 0
0x1800102f0  lea     rax, [rbp+var_18]
0x1800102f4  lea     r9, _GUID_54e4c428_d1d4_47d4_ade6_46c829114a7d; riid
0x1800102fb  mov     [rsp+80h+ppv], rax; ppv
0x180010300  lea     rcx, CLSID_ApplicationActivationManager; rclsid
0x180010307  lea     r8d, [rdx+1]; dwClsContext
0x18001030b  call    cs:__imp_CoCreateInstance
0x180010311  mov     esi, eax
0x180010313  test    eax, eax
0x180010315  jns     short loc_18001031F
0x180010317  mov     r9d, 171h
0x18001031d  jmp     short loc_180010389
0x18001031f  mov     rsi, [rbp+var_18]
0x180010323  lea     r9, [rbp+string]; string
0x180010327  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18001032b  mov     edx, 1Bh; length
0x180010330  lea     rcx, aWindowsPhoneca; "Windows.PhoneCallActivation"
0x180010337  mov     r13, [rsi]
0x18001033a  mov     [rbp+string], 0
0x180010342  call    cs:__imp_WindowsCreateStringReference
0x180010348  test    eax, eax
0x18001034a  js      loc_180010467
0x180010350  mov     rdx, [r15+20h]
0x180010354  xor     r8d, r8d
0x180010357  mov     r9, [rbp+string]
0x18001035b  mov     rcx, rsi
0x18001035e  mov     rax, [r13+18h]
0x180010362  mov     [rsp+80h+var_50], r14
0x180010367  mov     rdx, [rdx+10h]
0x18001036b  mov     [rsp+80h+var_58], 0
0x180010373  mov     [rsp+80h+ppv], rbx
0x180010378  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001037d  mov     esi, eax
0x18001037f  test    eax, eax
0x180010381  jns     short loc_1800103D9
0x180010383  mov     r9d, 174h
0x180010389  lea     r8, aOnecoreuapNetP_3; "onecoreuap\\net\\phone\\telephonyintera"...
0x180010390  mov     edx, 1
0x180010395  mov     ecx, eax
0x180010397  call    Log_HREvent_0
0x18001039c  mov     rcx, [rbp+var_18]
0x1800103a0  test    rcx, rcx
0x1800103a3  jz      short loc_1800103B9
0x1800103a5  mov     [rbp+var_18], 0
0x1800103ad  mov     rax, [rcx]
0x1800103b0  mov     rax, [rax+10h]
0x1800103b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800103b9  test    rbx, rbx
0x1800103bc  jz      short loc_1800103CD
0x1800103be  mov     rax, [rbx]
0x1800103c1  mov     rcx, rbx
0x1800103c4  mov     rax, [rax+10h]
0x1800103c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800103cd  mov     rcx, rdi
0x1800103d0  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@VCActivatedEventArgsBase@@UIPhoneCallActivatedEventArgs@Activation@ApplicationModel@Windows@@U?$CloakedIid@UIValueMarshalByPropertySet@Internal@Marshaling@Foundation@Windows@@@23@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,CActivatedEventArgsBase,Windows::ApplicationModel::Activation::IPhoneCallActivatedEventArgs,Microsoft::WRL::CloakedIid<Windows::Foundation::Marshaling::Internal::IValueMarshalByPropertySet>,Microsoft::WRL::FtmBase>::Release(void)
0x1800103d5  mov     eax, esi
0x1800103d7  jmp     short loc_18001043F
0x1800103d9  mov     eax, cs:dword_180025038
0x1800103df  cmp     eax, 4
0x1800103e2  jbe     short loc_180010404
0x1800103e4  lea     rax, aActivateapplic; "ActivateApplicationForContractByAppId S"...
0x1800103eb  mov     [rbp+var_40], rax
0x1800103ef  lea     rdx, byte_180020681
0x1800103f6  lea     rax, [rbp+var_40]
0x1800103fa  mov     [rsp+80h+ppv], rax
0x1800103ff  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180010404  mov     rcx, [rbp+var_18]
0x180010408  test    rcx, rcx
0x18001040b  jz      short loc_180010421
0x18001040d  mov     [rbp+var_18], 0
0x180010415  mov     rax, [rcx]
0x180010418  mov     rax, [rax+10h]
0x18001041c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010421  test    rbx, rbx
0x180010424  jz      short loc_180010435
0x180010426  mov     rax, [rbx]
0x180010429  mov     rcx, rbx
0x18001042c  mov     rax, [rax+10h]
0x180010430  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010435  mov     rcx, rdi
0x180010438  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@VCActivatedEventArgsBase@@UIPhoneCallActivatedEventArgs@Activation@ApplicationModel@Windows@@U?$CloakedIid@UIValueMarshalByPropertySet@Internal@Marshaling@Foundation@Windows@@@23@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,CActivatedEventArgsBase,Windows::ApplicationModel::Activation::IPhoneCallActivatedEventArgs,Microsoft::WRL::CloakedIid<Windows::Foundation::Marshaling::Internal::IValueMarshalByPropertySet>,Microsoft::WRL::FtmBase>::Release(void)
0x18001043d  xor     eax, eax
0x18001043f  mov     rcx, [rbp+var_10]
0x180010443  xor     rcx, rsp; StackCookie
0x180010446  call    __security_check_cookie
0x18001044b  lea     r11, [rsp+80h+var_s0]
0x180010453  mov     rbx, [r11+40h]
0x180010457  mov     rsi, [r11+48h]
0x18001045b  mov     rsp, r11
0x18001045e  pop     r15
0x180010460  pop     r14
0x180010462  pop     r13
0x180010464  pop     rdi
0x180010465  pop     rbp
0x180010466  retn
0x180010467  mov     ecx, eax; this
0x180010469  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
