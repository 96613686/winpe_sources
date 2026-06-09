# Microsoft::Bluetooth::Protocols::Avctp::AvctpRadioEnumerator::OnDeviceArrival(ushort const *,_DEVPROPERTY const *,ulong)

- ea: `0x18002e1e0`
- end: `0x18002e549`
- name: `?OnDeviceArrival@AvctpRadioEnumerator@Avctp@Protocols@Bluetooth@Microsoft@@EEAAXPEBGPEBU_DEVPROPERTY@@K@Z`
- size: `873`
- prototype: `void __fastcall(Microsoft::Bluetooth::Protocols::Avctp::AvctpRadioEnumerator *__hidden this, const unsigned __int16 *, const struct _DEVPROPERTY *, unsigned int)`
- caller_count: `0`
- callee_count: `23`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001dd0`
- `0x180004060`
- `0x18000de78`
- `0x18000fccc`
- `0x18000fcf8`
- `0x180012f50`
- `0x1800151ac`
- `0x1800151f4`
- `0x1800163ac`
- `0x180019d20`
- `0x18001fd88`
- `0x18002c794`
- `0x18002c9cc`
- `0x18002d234`
- `0x18002d400`
- `0x18002d798`
- `0x18002db0c`
- `0x18002de00`
- `0x18002e1e0`
- `0x18002eac8`
- `0x18002eb08`
- `0x180041708`
- `0x18005f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002e223`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002e223`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall Microsoft::Bluetooth::Protocols::Avctp::AvctpRadioEnumerator::OnDeviceArrival(
        Microsoft::Bluetooth::Protocols::Avctp::AvctpRadioEnumerator *this,
        const unsigned __int16 *a2,
        const struct _DEVPROPERTY *a3,
        unsigned int a4)
{
  char *v8; // rbx
  unsigned int v9; // r13d
  char v10; // dl
  __int64 v11; // r8
  unsigned __int64 v12; // rbx
  __int64 v13; // rax
  __int64 v14; // r8
  __int64 *v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rdx
  std::_Ref_count_base *v18; // rcx
  __int64 v19; // rdi
  void (__fastcall *v20)(__int64, __int64 *, _BYTE *); // rbx
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rbx
  char v24[4]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v25[4]; // [rsp+54h] [rbp-ACh] BYREF
  unsigned __int64 RadioAddressFromProperties; // [rsp+58h] [rbp-A8h] BYREF
  char *v27; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v28; // [rsp+68h] [rbp-98h] BYREF
  std::_Ref_count_base *v29; // [rsp+70h] [rbp-90h]
  _BYTE v30[8]; // [rsp+78h] [rbp-88h] BYREF
  std::_Ref_count_base *v31; // [rsp+80h] [rbp-80h]
  _BYTE v32[40]; // [rsp+98h] [rbp-68h] BYREF
  _QWORD v33[9]; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v34[9]; // [rsp+108h] [rbp+8h] BYREF
  _BYTE v35[80]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v36[80]; // [rsp+1A0h] [rbp+A0h] BYREF

  v8 = (char *)this + 328;
  AcquireSRWLockExclusive((PSRWLOCK)this + 41);
  v27 = v8;
  v9 = 0;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
    || (v10 = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u) )
  {
    v10 = 0;
  }
  if ( v10 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_Sq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      4,
      1,
      10,
      &WPP_530b9183aa8e352d9d3e79246b5dacd2_Traceguids,
      (__int64)a2,
      (char)this);
  v24[0] = 0;
  Microsoft::Bluetooth::Foundation::DeviceHelpers::FindBooleanProperty(
    v25,
    &DEVPKEY_Bluetooth_RadioIsCentralRoleSupported,
    a3,
    a4);
  if ( !*((_QWORD *)this + 62) && v25[0] )
  {
    v11 = -1;
    do
      ++v11;
    while ( a2[v11] );
    std::wstring::_Assign<unsigned short>((char *)this + 480);
    *((_BYTE *)this + 512) = 1;
    v9 = 2;
    if ( !*((_BYTE *)this + 514) )
    {
      *((_BYTE *)this + 514) = 1;
      Microsoft::Bluetooth::Protocols::Avctp::AvctpRadioEnumerator::InitGmcsHandler(this);
    }
    Microsoft::Bluetooth::Foundation::DeviceHelpers::FindBooleanProperty(
      v25,
      &DEVPKEY_Bluetooth_RadioIsConnectedIsochronousStreamsSupported,
      a3,
      a4);
    if ( v25[0] )
    {
      *((_BYTE *)this + 513) = 1;
      v12 = **((_QWORD **)this + 44);
      RadioAddressFromProperties = v12;
      while ( !*(_BYTE *)(v12 + 25) )
      {
        v13 = std::wstring::wstring(v32);
        LOBYTE(v14) = 1;
        std::_Func_class<void,std::wstring,bool>::operator()(v12 + 48, v13, v14);
        std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,Microsoft::Bluetooth::Audio::ChosenTransportContext>>>,std::_Iterator_base0>::operator++(&RadioAddressFromProperties);
        v12 = RadioAddressFromProperties;
      }
      v24[0] = 1;
    }
  }
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56664216>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56664216>::GetImpl'::`2'::impl)
    && !*((_QWORD *)this + 67) )
  {
    RadioAddressFromProperties = Microsoft::Bluetooth::Foundation::DeviceHelpers::GetRadioAddressFromProperties(a3, a4);
    v15 = (__int64 *)std::make_shared<Microsoft::Bluetooth::Audio::BluetoothAudioTransportSelector,unsigned __int64 &,bool &>(
                       v30,
                       &RadioAddressFromProperties,
                       v24);
    v16 = *v15;
    v17 = v15[1];
    *v15 = 0;
    v15[1] = 0;
    *((_QWORD *)this + 67) = v16;
    v18 = (std::_Ref_count_base *)*((_QWORD *)this + 68);
    *((_QWORD *)this + 68) = v17;
    if ( v18 )
      std::_Ref_count_base::_Decref(v18);
    if ( v31 )
      std::_Ref_count_base::_Decref(v31);
    Microsoft::Bluetooth::Audio::BluetoothAudioTransportSelector::Initialize(*((Microsoft::Bluetooth::Audio::BluetoothAudioTransportSelector **)this
                                                                             + 67));
  }
  v19 = *((_QWORD *)this + 7);
  v20 = *(void (__fastcall **)(__int64, __int64 *, _BYTE *))(*(_QWORD *)v19 + 8LL);
  std::wstring::wstring((__int64)v30, (__int64)a2);
  v20(v19, &v28, v30);
  std::wstring::_Tidy_deallocate(v30);
  v21 = (*(__int64 (__fastcall **)(__int64, _BYTE *, _QWORD, char *))(*(_QWORD *)v28 + 8LL))(
          v28,
          v36,
          v9,
          (char *)this + 72);
  Microsoft::Bluetooth::Foundation::Token::Token(v33, v21);
  v22 = (*(__int64 (__fastcall **)(__int64, _BYTE *, _QWORD, char *))(*(_QWORD *)v28 + 8LL))(
          v28,
          v35,
          0,
          (char *)this + 200);
  Microsoft::Bluetooth::Foundation::Token::Token(v34, v22);
  std::wstring::wstring((__int64)v32, (__int64)a2);
  v23 = *(_QWORD *)std::map<std::wstring,Microsoft::Bluetooth::Protocols::Avctp::AvctpRadioEnumerator::RadioSdpRegistrations>::_Try_emplace<std::wstring,>(
                     (__int64 *)this + 42,
                     (__int64)v30,
                     (__int64)v32);
  Microsoft::Bluetooth::Foundation::Token::operator=(v23 + 64, v33);
  Microsoft::Bluetooth::Foundation::Token::operator=(v23 + 136, v34);
  std::wstring::_Tidy_deallocate(v32);
  Microsoft::Bluetooth::Protocols::Avctp::AvctpRadioEnumerator::RadioSdpRegistrations::~RadioSdpRegistrations((Microsoft::Bluetooth::Protocols::Avctp::AvctpRadioEnumerator::RadioSdpRegistrations *)v33);
  Microsoft::Bluetooth::Foundation::Token::~Token((Microsoft::Bluetooth::Foundation::Token *)v35);
  Microsoft::Bluetooth::Foundation::Token::~Token((Microsoft::Bluetooth::Foundation::Token *)v36);
  if ( v29 )
    std::_Ref_count_base::_Decref(v29);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v27);
}

```

## disassembly

```asm
0x18002e1e0  push    rbp
0x18002e1e2  push    rbx
0x18002e1e3  push    rsi
0x18002e1e4  push    rdi
0x18002e1e5  push    r12
0x18002e1e7  push    r13
0x18002e1e9  push    r14
0x18002e1eb  push    r15
0x18002e1ed  lea     rbp, [rsp-108h]
0x18002e1f5  sub     rsp, 208h
0x18002e1fc  mov     rax, cs:__security_cookie
0x18002e203  xor     rax, rsp
0x18002e206  mov     [rbp+140h+var_50], rax
0x18002e20d  mov     r12d, r9d
0x18002e210  mov     r15, r8
0x18002e213  mov     r14, rdx
0x18002e216  mov     rsi, rcx
0x18002e219  lea     rbx, [rcx+148h]
0x18002e220  mov     rcx, rbx; SRWLock
0x18002e223  call    cs:__imp_AcquireSRWLockExclusive
0x18002e229  mov     [rsp+240h+var_1E0], rbx
0x18002e22e  xor     ebx, ebx
0x18002e230  mov     r13d, ebx
0x18002e233  lea     rax, WPP_GLOBAL_Control
0x18002e23a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e241  cmp     rcx, rax
0x18002e244  jz      short loc_18002E254
0x18002e246  test    byte ptr [rcx+1Ch], 1
0x18002e24a  jz      short loc_18002E254
0x18002e24c  cmp     byte ptr [rcx+19h], 4
0x18002e250  mov     dl, 1
0x18002e252  jnb     short loc_18002E256
0x18002e254  mov     dl, bl
0x18002e256  lea     rax, WPP_RECORDER_INITIALIZED
0x18002e25d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18002e264  setnz   r8b
0x18002e268  test    dl, dl
0x18002e26a  jnz     short loc_18002E271
0x18002e26c  test    r8b, r8b
0x18002e26f  jz      short loc_18002E2A8
0x18002e271  mov     qword ptr [rsp+240h+var_1F8], rsi; char
0x18002e276  mov     [rsp+240h+var_200], r14; __int64
0x18002e27b  lea     rax, WPP_530b9183aa8e352d9d3e79246b5dacd2_Traceguids
0x18002e282  mov     [rsp+240h+MessageGuid], rax; MessageGuid
0x18002e287  mov     [rsp+240h+var_210], 0Ah; __int16
0x18002e28e  mov     [rsp+240h+var_218], 1; int
0x18002e296  mov     [rsp+240h+var_220], 4; char
0x18002e29b  mov     r9, [rcx+28h]
0x18002e29f  mov     rcx, [rcx+10h]; LoggerHandle
0x18002e2a3  call    WPP_RECORDER_AND_TRACE_SF_Sq
0x18002e2a8  mov     [rsp+240h+var_1F0], bl
0x18002e2ac  mov     r9d, r12d
0x18002e2af  mov     r8, r15
0x18002e2b2  lea     rdx, DEVPKEY_Bluetooth_RadioIsCentralRoleSupported
0x18002e2b9  lea     rcx, [rsp+240h+var_1EC]
0x18002e2be  call    ?FindBooleanProperty@DeviceHelpers@Foundation@Bluetooth@Microsoft@@SA?AU?$pair@_N_N@std@@AEBU_DEVPROPKEY@@PEBU_DEVPROPERTY@@K@Z; Microsoft::Bluetooth::Foundation::DeviceHelpers::FindBooleanProperty(_DEVPROPKEY const &,_DEVPROPERTY const *,ulong)
0x18002e2c3  lea     rdi, [rsi+1E0h]
0x18002e2ca  cmp     [rdi+10h], rbx
0x18002e2ce  jnz     loc_18002E387
0x18002e2d4  cmp     [rsp+240h+var_1EC], bl
0x18002e2d8  jz      loc_18002E387
0x18002e2de  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002e2e2  inc     r8
0x18002e2e5  cmp     [r14+r8*2], bx
0x18002e2ea  jnz     short loc_18002E2E2
0x18002e2ec  mov     rdx, r14
0x18002e2ef  mov     rcx, rdi
0x18002e2f2  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18002e2f7  mov     byte ptr [rsi+200h], 1
0x18002e2fe  mov     r13d, 2
0x18002e304  cmp     [rsi+202h], bl
0x18002e30a  jnz     short loc_18002E31B
0x18002e30c  mov     byte ptr [rsi+202h], 1
0x18002e313  mov     rcx, rsi; this
0x18002e316  call    ?InitGmcsHandler@AvctpRadioEnumerator@Avctp@Protocols@Bluetooth@Microsoft@@AEAAXXZ; Microsoft::Bluetooth::Protocols::Avctp::AvctpRadioEnumerator::InitGmcsHandler(void)
0x18002e31b  mov     r9d, r12d
0x18002e31e  mov     r8, r15
0x18002e321  lea     rdx, DEVPKEY_Bluetooth_RadioIsConnectedIsochronousStreamsSupported
0x18002e328  lea     rcx, [rsp+240h+var_1EC]
0x18002e32d  call    ?FindBooleanProperty@DeviceHelpers@Foundation@Bluetooth@Microsoft@@SA?AU?$pair@_N_N@std@@AEBU_DEVPROPKEY@@PEBU_DEVPROPERTY@@K@Z; Microsoft::Bluetooth::Foundation::DeviceHelpers::FindBooleanProperty(_DEVPROPKEY const &,_DEVPROPERTY const *,ulong)
0x18002e332  cmp     [rsp+240h+var_1EC], bl
0x18002e336  jz      short loc_18002E387
0x18002e338  mov     byte ptr [rsi+201h], 1
0x18002e33f  mov     rbx, [rsi+160h]
0x18002e346  mov     rbx, [rbx]
0x18002e349  mov     [rsp+240h+var_1E8], rbx
0x18002e34e  cmp     byte ptr [rbx+19h], 0
0x18002e352  jnz     short loc_18002E380
0x18002e354  mov     rdx, rdi
0x18002e357  lea     rcx, [rbp+140h+var_1A8]
0x18002e35b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002e360  lea     rcx, [rbx+30h]
0x18002e364  mov     r8b, 1
0x18002e367  mov     rdx, rax
0x18002e36a  call    ??R?$_Func_class@XV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@std@@QEBAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_N@Z; std::_Func_class<void,std::wstring,bool>::operator()(std::wstring,bool)
0x18002e36f  lea     rcx, [rsp+240h+var_1E8]
0x18002e374  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@UChosenTransportContext@Audio@Bluetooth@Microsoft@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,Microsoft::Bluetooth::Audio::ChosenTransportContext>>>,std::_Iterator_base0>::operator++(void)
0x18002e379  mov     rbx, [rsp+240h+var_1E8]
0x18002e37e  jmp     short loc_18002E34E
0x18002e380  mov     [rsp+240h+var_1F0], 1
0x18002e385  xor     ebx, ebx
0x18002e387  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56664216@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56664216@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56664216> `wil::Feature<__WilFeatureTraits_Feature_56664216>::GetImpl(void)'::`2'::impl
0x18002e38e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56664216@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56664216>::__private_IsEnabled(void)
0x18002e393  test    al, al
0x18002e395  jnz     short loc_18002E40B
0x18002e397  cmp     [rsi+218h], rbx
0x18002e39e  jnz     short loc_18002E40B
0x18002e3a0  mov     edx, r12d; unsigned int
0x18002e3a3  mov     rcx, r15; struct _DEVPROPERTY *
0x18002e3a6  call    ?GetRadioAddressFromProperties@DeviceHelpers@Foundation@Bluetooth@Microsoft@@SA_KPEBU_DEVPROPERTY@@K@Z; Microsoft::Bluetooth::Foundation::DeviceHelpers::GetRadioAddressFromProperties(_DEVPROPERTY const *,ulong)
0x18002e3ab  mov     [rsp+240h+var_1E8], rax
0x18002e3b0  lea     r8, [rsp+240h+var_1F0]
0x18002e3b5  lea     rdx, [rsp+240h+var_1E8]
0x18002e3ba  lea     rcx, [rsp+240h+var_1C8]
0x18002e3bf  call    ??$make_shared@VBluetoothAudioTransportSelector@Audio@Bluetooth@Microsoft@@AEA_KAEA_N@std@@YA?AV?$shared_ptr@VBluetoothAudioTransportSelector@Audio@Bluetooth@Microsoft@@@0@AEA_KAEA_N@Z; std::make_shared<Microsoft::Bluetooth::Audio::BluetoothAudioTransportSelector,unsigned __int64 &,bool &>(unsigned __int64 &,bool &)
0x18002e3c4  mov     rcx, [rax]
0x18002e3c7  mov     rdx, [rax+8]
0x18002e3cb  mov     [rax], rbx
0x18002e3ce  mov     [rax+8], rbx
0x18002e3d2  mov     [rsi+218h], rcx
0x18002e3d9  mov     rcx, [rsi+220h]; this
0x18002e3e0  mov     [rsi+220h], rdx
0x18002e3e7  test    rcx, rcx
0x18002e3ea  jz      short loc_18002E3F1
0x18002e3ec  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002e3f1  mov     rcx, [rbp+140h+var_1C0]; this
0x18002e3f5  test    rcx, rcx
0x18002e3f8  jz      short loc_18002E3FF
0x18002e3fa  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002e3ff  mov     rcx, [rsi+218h]; this
0x18002e406  call    ?Initialize@BluetoothAudioTransportSelector@Audio@Bluetooth@Microsoft@@QEAAXXZ; Microsoft::Bluetooth::Audio::BluetoothAudioTransportSelector::Initialize(void)
0x18002e40b  mov     rdi, [rsi+38h]
0x18002e40f  mov     rax, [rdi]
0x18002e412  mov     rbx, [rax+8]
0x18002e416  mov     rdx, r14
0x18002e419  lea     rcx, [rsp+240h+var_1C8]
0x18002e41e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002e423  nop
0x18002e424  lea     r8, [rsp+240h+var_1C8]
0x18002e429  lea     rdx, [rsp+240h+var_1D8]
0x18002e42e  mov     rcx, rdi
0x18002e431  mov     rax, rbx
0x18002e434  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e439  nop
0x18002e43a  lea     rcx, [rsp+240h+var_1C8]
0x18002e43f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002e444  mov     rcx, [rsp+240h+var_1D8]
0x18002e449  mov     rax, [rcx]
0x18002e44c  lea     r9, [rsi+48h]
0x18002e450  mov     r8d, r13d
0x18002e453  lea     rdx, [rbp+140h+var_A0]
0x18002e45a  mov     rax, [rax+8]
0x18002e45e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e463  nop
0x18002e464  mov     rdx, rax
0x18002e467  lea     rcx, [rbp+140h+var_180]
0x18002e46b  call    ??0Token@Foundation@Bluetooth@Microsoft@@QEAA@$$QEAV0123@@Z; Microsoft::Bluetooth::Foundation::Token::Token(Microsoft::Bluetooth::Foundation::Token &&)
0x18002e470  nop
0x18002e471  mov     rcx, [rsp+240h+var_1D8]
0x18002e476  mov     rax, [rcx]
0x18002e479  lea     r9, [rsi+0C8h]
0x18002e480  xor     r8d, r8d
0x18002e483  lea     rdx, [rbp+140h+var_F0]
0x18002e487  mov     rax, [rax+8]
0x18002e48b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e490  nop
0x18002e491  mov     rdx, rax
0x18002e494  lea     rcx, [rbp+140h+var_138]
0x18002e498  call    ??0Token@Foundation@Bluetooth@Microsoft@@QEAA@$$QEAV0123@@Z; Microsoft::Bluetooth::Foundation::Token::Token(Microsoft::Bluetooth::Foundation::Token &&)
0x18002e49d  nop
0x18002e49e  mov     rdx, r14
0x18002e4a1  lea     rcx, [rbp+140h+var_1A8]
0x18002e4a5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002e4aa  nop
0x18002e4ab  lea     rcx, [rsi+150h]
0x18002e4b2  lea     r8, [rbp+140h+var_1A8]
0x18002e4b6  lea     rdx, [rsp+240h+var_1C8]
0x18002e4bb  call    ??$_Try_emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@URadioSdpRegistrations@AvctpRadioEnumerator@Avctp@Protocols@Bluetooth@Microsoft@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@URadioSdpRegistrations@AvctpRadioEnumerator@Avctp@Protocols@Bluetooth@Microsoft@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@URadioSdpRegistrations@AvctpRadioEnumerator@Avctp@Protocols@Bluetooth@Microsoft@@@std@@PEAX@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,Microsoft::Bluetooth::Protocols::Avctp::AvctpRadioEnumerator::RadioSdpRegistrations>::_Try_emplace<std::wstring,>(std::wstring &&)
0x18002e4c0  mov     rbx, [rax]
0x18002e4c3  lea     rdx, [rbp+140h+var_180]
0x18002e4c7  lea     rcx, [rbx+40h]
0x18002e4cb  call    ??4Token@Foundation@Bluetooth@Microsoft@@QEAAAEAV0123@$$QEAV0123@@Z; Microsoft::Bluetooth::Foundation::Token::operator=(Microsoft::Bluetooth::Foundation::Token &&)
0x18002e4d0  lea     rcx, [rbx+88h]
0x18002e4d7  lea     rdx, [rbp+140h+var_138]
0x18002e4db  call    ??4Token@Foundation@Bluetooth@Microsoft@@QEAAAEAV0123@$$QEAV0123@@Z; Microsoft::Bluetooth::Foundation::Token::operator=(Microsoft::Bluetooth::Foundation::Token &&)
0x18002e4e0  nop
0x18002e4e1  lea     rcx, [rbp+140h+var_1A8]
0x18002e4e5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002e4ea  nop
0x18002e4eb  lea     rcx, [rbp+140h+var_180]; this
0x18002e4ef  call    ??1RadioSdpRegistrations@AvctpRadioEnumerator@Avctp@Protocols@Bluetooth@Microsoft@@QEAA@XZ; Microsoft::Bluetooth::Protocols::Avctp::AvctpRadioEnumerator::RadioSdpRegistrations::~RadioSdpRegistrations(void)
0x18002e4f4  nop
0x18002e4f5  lea     rcx, [rbp+140h+var_F0]; this
0x18002e4f9  call    ??1Token@Foundation@Bluetooth@Microsoft@@UEAA@XZ; Microsoft::Bluetooth::Foundation::Token::~Token(void)
0x18002e4fe  nop
0x18002e4ff  lea     rcx, [rbp+140h+var_A0]; this
0x18002e506  call    ??1Token@Foundation@Bluetooth@Microsoft@@UEAA@XZ; Microsoft::Bluetooth::Foundation::Token::~Token(void)
0x18002e50b  nop
0x18002e50c  mov     rcx, [rsp+240h+var_1D0]; this
0x18002e511  test    rcx, rcx
0x18002e514  jz      short loc_18002E51C
0x18002e516  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002e51b  nop
0x18002e51c  lea     rcx, [rsp+240h+var_1E0]
0x18002e521  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002e526  mov     rcx, [rbp+140h+var_50]
0x18002e52d  xor     rcx, rsp; StackCookie
0x18002e530  call    __security_check_cookie
0x18002e535  add     rsp, 208h
0x18002e53c  pop     r15
0x18002e53e  pop     r14
0x18002e540  pop     r13
0x18002e542  pop     r12
0x18002e544  pop     rdi
0x18002e545  pop     rsi
0x18002e546  pop     rbx
0x18002e547  pop     rbp
0x18002e548  retn
```
