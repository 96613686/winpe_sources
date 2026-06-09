# CMidi2UmpProtocolDownscalerMidiTransform::OnDeviceUpdated(winrt::Windows::Devices::Enumeration::DeviceWatcher,winrt::Windows::Devices::Enumeration::DeviceInformationUpdate)

- ea: `0x18000fac0`
- end: `0x18000fe38`
- name: `?OnDeviceUpdated@CMidi2UmpProtocolDownscalerMidiTransform@@AEAAJUDeviceWatcher@Enumeration@Devices@Windows@winrt@@UDeviceInformationUpdate@3456@@Z`
- size: `888`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x1800016dc`
- `0x180008924`
- `0x18000a798`
- `0x18000c050`
- `0x18000d5a0`
- `0x18000f7f4`
- `0x18000fac0`
- `0x18000feac`
- `0x180011a4c`
- `0x180011e0c`
- `0x180013010`

## string_xrefs

- `0x18000fc52`: `avcore\midi2\transform\umpprotocoldownscaler\midi2.umpprotocoldownscalermiditransform.cpp`
- `0x18000fb9a`: `Configured Protocol has changed`
- `0x18000fb77`: `CMidi2UmpProtocolDownscalerMidiTransform::OnDeviceUpdated`
- `0x18000fcc1`: `New protocol is MIDI 1.0. Downscaling enabled`
- `0x18000fd3f`: `New protocol is MIDI 2.0. Downscaling disabled. Upscaling is not required because endpoint supports MIDI 1 protocol as well`
- `0x18000fda6`: `New protocol is MIDI 2.0. Endpoint doesn't declare MIDI 1 support, so we will upscale MIDI 1 protocol messages.`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CMidi2UmpProtocolDownscalerMidiTransform::OnDeviceUpdated(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  __int64 *v6; // rax
  __int64 v7; // rcx
  int v8; // eax
  _DWORD *v9; // rcx
  int v10; // r8d
  int v11; // r9d
  const char *v12; // rbx
  const char *v13; // rax
  __int64 v14; // rax
  char v16; // al
  _DWORD *v17; // rcx
  int v18; // r8d
  int v19; // r9d
  _DWORD *v20; // rcx
  int v21; // r8d
  int v22; // r9d
  _DWORD *v23; // rcx
  int v24; // r8d
  int v25; // r9d
  int v26; // [rsp+20h] [rbp-59h]
  const char *v27; // [rsp+40h] [rbp-39h] BYREF
  const wchar_t *v28; // [rsp+48h] [rbp-31h] BYREF
  const wchar_t *v29; // [rsp+50h] [rbp-29h] BYREF
  const char *v30; // [rsp+58h] [rbp-21h] BYREF
  int v31; // [rsp+60h] [rbp-19h] BYREF
  const char *v32; // [rsp+68h] [rbp-11h]
  __int64 v33; // [rsp+70h] [rbp-9h]
  int *v34; // [rsp+78h] [rbp-1h] BYREF
  int v35; // [rsp+80h] [rbp+7h] BYREF
  int v36; // [rsp+84h] [rbp+Bh]
  const wchar_t *v37; // [rsp+90h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]
  __int64 v39; // [rsp+F8h] [rbp+7Fh] BYREF

  v6 = (__int64 *)winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformationUpdate<winrt::Windows::Devices::Enumeration::IDeviceInformationUpdate>::Properties(
                    a3,
                    &v27);
  v35 = 1;
  v36 = 42;
  v37 = L"{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} 400";
  v34 = &v35;
  LOBYTE(v39) = 0;
  v7 = *v6;
  v31 = 226;
  v32 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt/Windows.Foundation.Collections.h";
  v33 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64, int *, __int64 *))(*(_QWORD *)v7 + 64LL))(v7, &v35, &v39);
  if ( v8 < 0 )
    winrt::throw_hresult((unsigned int)v8, &v31);
  if ( v27 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v27);
  if ( (_BYTE)v39 )
  {
    v9 = (_DWORD *)*((_QWORD *)MidiUmpProtocolDownscalerTransformTelemetryProvider::Instance() + 1);
    if ( *v9 <= 4u )
    {
      v12 = (const char *)(a1 + 104);
    }
    else
    {
      v12 = (const char *)(a1 + 104);
      if ( *(_QWORD *)(a1 + 128) <= 7u )
        v13 = (const char *)(a1 + 104);
      else
        v13 = *(const char **)v12;
      v27 = v13;
      v28 = L"Configured Protocol has changed";
      v29 = (const wchar_t *)a1;
      v30 = "CMidi2UmpProtocolDownscalerMidiTransform::OnDeviceUpdated";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v9,
        (unsigned int)&word_180017346,
        v10,
        v11,
        (__int64)&v30,
        (__int64)&v29,
        (__int64)&v28,
        (__int64)&v27);
    }
    v14 = winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformationUpdate<winrt::Windows::Devices::Enumeration::IDeviceInformationUpdate>::Properties(
            a3,
            &v27);
    v35 = 1;
    v36 = 42;
    v37 = L"{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} 400";
    v34 = &v35;
    winrt::impl::consume_Windows_Foundation_Collections_IMapView<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(
      v14,
      &v39,
      &v34);
    if ( v27 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v27);
    v30 = 0;
    if ( (unsigned __int8)winrt::Windows::Foundation::operator==(&v39, &v30) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x84,
        (unsigned int)"avcore\\midi2\\transform\\umpprotocoldownscaler\\midi2.umpprotocoldownscalermiditransform.cpp",
        (const char *)0x80070057LL,
        v26);
      if ( v39 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v39);
      if ( *a2 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a2);
      if ( *a3 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a3);
      return 2147942487LL;
    }
    v16 = winrt::unbox_value<unsigned char>(&v39);
    if ( v16 == 1 )
    {
      v17 = (_DWORD *)*((_QWORD *)MidiUmpProtocolDownscalerTransformTelemetryProvider::Instance() + 1);
      if ( *v17 > 4u )
      {
        if ( *((_QWORD *)v12 + 3) > 7u )
          v12 = *(const char **)v12;
        v30 = v12;
        v29 = L"New protocol is MIDI 1.0. Downscaling enabled";
        v28 = (const wchar_t *)a1;
        v27 = "CMidi2UmpProtocolDownscalerMidiTransform::OnDeviceUpdated";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          (_DWORD)v17,
          (unsigned int)qword_1800172F0,
          v18,
          v19,
          (__int64)&v27,
          (__int64)&v28,
          (__int64)&v29,
          (__int64)&v30);
      }
      *(_WORD *)(a1 + 96) = 1;
    }
    else if ( v16 == 2 )
    {
      *(_BYTE *)(a1 + 96) = 0;
      if ( *(_BYTE *)(a1 + 98) )
      {
        v20 = (_DWORD *)*((_QWORD *)MidiUmpProtocolDownscalerTransformTelemetryProvider::Instance() + 1);
        if ( *v20 > 4u )
        {
          if ( *((_QWORD *)v12 + 3) > 7u )
            v12 = *(const char **)v12;
          v30 = v12;
          v29 = L"New protocol is MIDI 2.0. Downscaling disabled. Upscaling is not required because endpoint supports MIDI"
                 " 1 protocol as well";
          v28 = (const wchar_t *)a1;
          v27 = "CMidi2UmpProtocolDownscalerMidiTransform::OnDeviceUpdated";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
            (_DWORD)v20,
            (unsigned int)word_18001729A,
            v21,
            v22,
            (__int64)&v27,
            (__int64)&v28,
            (__int64)&v29,
            (__int64)&v30);
        }
        *(_BYTE *)(a1 + 97) = 0;
      }
      else
      {
        v23 = (_DWORD *)*((_QWORD *)MidiUmpProtocolDownscalerTransformTelemetryProvider::Instance() + 1);
        if ( *v23 > 4u )
        {
          if ( *((_QWORD *)v12 + 3) > 7u )
            v12 = *(const char **)v12;
          v30 = v12;
          v29 = L"New protocol is MIDI 2.0. Endpoint doesn't declare MIDI 1 support, so we will upscale MIDI 1 protocol messages.";
          v28 = (const wchar_t *)a1;
          v27 = "CMidi2UmpProtocolDownscalerMidiTransform::OnDeviceUpdated";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
            (_DWORD)v23,
            (unsigned int)&dword_180017244,
            v24,
            v25,
            (__int64)&v27,
            (__int64)&v28,
            (__int64)&v29,
            (__int64)&v30);
        }
        *(_BYTE *)(a1 + 97) = 1;
      }
    }
    if ( v39 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v39);
  }
  if ( *a2 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a2);
  if ( *a3 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a3);
  return 0;
}

```

## disassembly

```asm
0x18000fac0  mov     [rsp-8+arg_10], r8
0x18000fac5  mov     [rsp-8+arg_8], rdx
0x18000faca  push    rbp
0x18000facb  push    rbx
0x18000facc  push    rsi
0x18000facd  push    rdi
0x18000face  push    r13
0x18000fad0  push    r14
0x18000fad2  push    r15
0x18000fad4  lea     rbp, [rsp-27h]
0x18000fad9  sub     rsp, 0A0h
0x18000fae0  mov     rsi, r8
0x18000fae3  mov     r14, rdx
0x18000fae6  mov     rdi, rcx
0x18000fae9  lea     rdx, [rbp+57h+var_90]
0x18000faed  mov     rcx, r8
0x18000faf0  call    ?Properties@?$consume_Windows_Devices_Enumeration_IDeviceInformationUpdate@UIDeviceInformationUpdate@Enumeration@Devices@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformationUpdate<winrt::Windows::Devices::Enumeration::IDeviceInformationUpdate>::Properties(void)
0x18000faf5  nop
0x18000faf6  mov     [rbp+57h+var_50], 1
0x18000fafd  mov     [rbp+57h+var_4C], 2Ah ; '*'
0x18000fb04  lea     rcx, a3f114a6a11fa4b_0; "{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} "...
0x18000fb0b  mov     [rbp+57h+var_40], rcx
0x18000fb0f  lea     rcx, [rbp+57h+var_50]
0x18000fb13  mov     [rbp+57h+var_58], rcx
0x18000fb17  xor     r15d, r15d
0x18000fb1a  mov     byte ptr [rbp+57h+arg_18], r15b
0x18000fb1e  mov     rcx, [rax]
0x18000fb21  mov     [rbp+57h+var_70], 0E2h
0x18000fb28  lea     rax, aOnecoreuapInte_2; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x18000fb2f  mov     [rbp+57h+var_68], rax
0x18000fb33  mov     [rbp+57h+var_60], r15
0x18000fb37  mov     rax, [rcx]
0x18000fb3a  lea     r8, [rbp+57h+arg_18]
0x18000fb3e  lea     rdx, [rbp+57h+var_50]
0x18000fb42  mov     rax, [rax+40h]
0x18000fb46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb4b  test    eax, eax
0x18000fb4d  js      loc_18000FE2C
0x18000fb53  cmp     [rbp+57h+var_90], r15
0x18000fb57  jz      short loc_18000FB62
0x18000fb59  lea     rcx, [rbp+57h+var_90]
0x18000fb5d  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000fb62  cmp     byte ptr [rbp+57h+arg_18], r15b
0x18000fb66  jz      loc_18000FDFD
0x18000fb6c  call    ?Instance@MidiUmpProtocolDownscalerTransformTelemetryProvider@@KAPEAV1@XZ; MidiUmpProtocolDownscalerTransformTelemetryProvider::Instance(void)
0x18000fb71  mov     rcx, [rax+8]
0x18000fb75  mov     eax, [rcx]
0x18000fb77  lea     r13, aCmidi2umpproto_0; "CMidi2UmpProtocolDownscalerMidiTransfor"...
0x18000fb7e  cmp     eax, 4
0x18000fb81  jbe     short loc_18000FBDF
0x18000fb83  lea     rbx, [rdi+68h]
0x18000fb87  cmp     qword ptr [rbx+18h], 7
0x18000fb8c  jbe     short loc_18000FB93
0x18000fb8e  mov     rax, [rbx]
0x18000fb91  jmp     short loc_18000FB96
0x18000fb93  mov     rax, rbx
0x18000fb96  mov     [rbp+57h+var_90], rax
0x18000fb9a  lea     rax, aConfiguredProt; "Configured Protocol has changed"
0x18000fba1  mov     [rbp+57h+var_88], rax
0x18000fba5  mov     [rbp+57h+var_80], rdi
0x18000fba9  mov     [rbp+57h+var_78], r13
0x18000fbad  lea     rax, [rbp+57h+var_90]
0x18000fbb1  mov     [rsp+0D0h+var_98], rax
0x18000fbb6  lea     rax, [rbp+57h+var_88]
0x18000fbba  mov     [rsp+0D0h+var_A0], rax
0x18000fbbf  lea     rax, [rbp+57h+var_80]
0x18000fbc3  mov     [rsp+0D0h+var_A8], rax
0x18000fbc8  lea     rax, [rbp+57h+var_78]
0x18000fbcc  mov     [rsp+0D0h+var_B0], rax
0x18000fbd1  lea     rdx, word_180017346
0x18000fbd8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18000fbdd  jmp     short loc_18000FBE3
0x18000fbdf  lea     rbx, [rdi+68h]
0x18000fbe3  lea     rdx, [rbp+57h+var_90]
0x18000fbe7  mov     rcx, rsi
0x18000fbea  call    ?Properties@?$consume_Windows_Devices_Enumeration_IDeviceInformationUpdate@UIDeviceInformationUpdate@Enumeration@Devices@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformationUpdate<winrt::Windows::Devices::Enumeration::IDeviceInformationUpdate>::Properties(void)
0x18000fbef  nop
0x18000fbf0  mov     [rbp+57h+var_50], 1
0x18000fbf7  mov     [rbp+57h+var_4C], 2Ah ; '*'
0x18000fbfe  lea     rcx, a3f114a6a11fa4b_0; "{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} "...
0x18000fc05  mov     [rbp+57h+var_40], rcx
0x18000fc09  lea     rcx, [rbp+57h+var_50]
0x18000fc0d  mov     [rbp+57h+var_58], rcx
0x18000fc11  lea     r8, [rbp+57h+var_58]
0x18000fc15  lea     rdx, [rbp+57h+arg_18]
0x18000fc19  mov     rcx, rax
0x18000fc1c  call    ?Lookup@?$consume_Windows_Foundation_Collections_IMapView@U?$IMapView@Uhstring@winrt@@UIInspectable@Foundation@Windows@2@@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMapView<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Windows::Foundation::IInspectable>,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(winrt::param::hstring const &)
0x18000fc21  nop
0x18000fc22  cmp     [rbp+57h+var_90], r15
0x18000fc26  jz      short loc_18000FC31
0x18000fc28  lea     rcx, [rbp+57h+var_90]
0x18000fc2c  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000fc31  mov     [rbp+57h+var_78], r15
0x18000fc35  lea     rdx, [rbp+57h+var_78]
0x18000fc39  lea     rcx, [rbp+57h+arg_18]
0x18000fc3d  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x18000fc42  test    al, al
0x18000fc44  jz      short loc_18000FC96
0x18000fc46  mov     rcx, [rbp+5Fh]; this
0x18000fc4a  mov     ebx, 80070057h
0x18000fc4f  mov     r9d, ebx; char *
0x18000fc52  lea     r8, aAvcoreMidi2Tra; "avcore\\midi2\\transform\\umpprotocoldo"...
0x18000fc59  mov     edx, 84h; void *
0x18000fc5e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fc63  nop
0x18000fc64  cmp     [rbp+57h+arg_18], r15
0x18000fc68  jz      short loc_18000FC74
0x18000fc6a  lea     rcx, [rbp+57h+arg_18]
0x18000fc6e  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000fc73  nop
0x18000fc74  cmp     [r14], r15
0x18000fc77  jz      short loc_18000FC82
0x18000fc79  mov     rcx, r14
0x18000fc7c  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000fc81  nop
0x18000fc82  cmp     [rsi], r15
0x18000fc85  jz      short loc_18000FC8F
0x18000fc87  mov     rcx, rsi
0x18000fc8a  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000fc8f  mov     eax, ebx
0x18000fc91  jmp     loc_18000FE1A
0x18000fc96  lea     rcx, [rbp+57h+arg_18]
0x18000fc9a  call    ??$unbox_value@E@winrt@@YAEAEBUIInspectable@Foundation@Windows@0@@Z; winrt::unbox_value<uchar>(winrt::Windows::Foundation::IInspectable const &)
0x18000fc9f  cmp     al, 1
0x18000fca1  jnz     short loc_18000FD0F
0x18000fca3  call    ?Instance@MidiUmpProtocolDownscalerTransformTelemetryProvider@@KAPEAV1@XZ; MidiUmpProtocolDownscalerTransformTelemetryProvider::Instance(void)
0x18000fca8  mov     rcx, [rax+8]
0x18000fcac  mov     eax, [rcx]
0x18000fcae  cmp     eax, 4
0x18000fcb1  jbe     short loc_18000FD04
0x18000fcb3  cmp     qword ptr [rbx+18h], 7
0x18000fcb8  jbe     short loc_18000FCBD
0x18000fcba  mov     rbx, [rbx]
0x18000fcbd  mov     [rbp+57h+var_78], rbx
0x18000fcc1  lea     rax, aNewProtocolIsM_1; "New protocol is MIDI 1.0. Downscaling e"...
0x18000fcc8  mov     [rbp+57h+var_80], rax
0x18000fccc  mov     [rbp+57h+var_88], rdi
0x18000fcd0  mov     [rbp+57h+var_90], r13
0x18000fcd4  lea     rax, [rbp+57h+var_78]
0x18000fcd8  mov     [rsp+0D0h+var_98], rax
0x18000fcdd  lea     rax, [rbp+57h+var_80]
0x18000fce1  mov     [rsp+0D0h+var_A0], rax
0x18000fce6  lea     rax, [rbp+57h+var_88]
0x18000fcea  mov     [rsp+0D0h+var_A8], rax
0x18000fcef  lea     rax, [rbp+57h+var_90]
0x18000fcf3  mov     [rsp+0D0h+var_B0], rax
0x18000fcf8  lea     rdx, qword_1800172F0
0x18000fcff  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18000fd04  mov     word ptr [rdi+60h], 1
0x18000fd0a  jmp     loc_18000FDED
0x18000fd0f  cmp     al, 2
0x18000fd11  jnz     loc_18000FDED
0x18000fd17  mov     [rdi+60h], r15b
0x18000fd1b  cmp     [rdi+62h], r15b
0x18000fd1f  jz      short loc_18000FD88
0x18000fd21  call    ?Instance@MidiUmpProtocolDownscalerTransformTelemetryProvider@@KAPEAV1@XZ; MidiUmpProtocolDownscalerTransformTelemetryProvider::Instance(void)
0x18000fd26  mov     rcx, [rax+8]
0x18000fd2a  mov     eax, [rcx]
0x18000fd2c  cmp     eax, 4
0x18000fd2f  jbe     short loc_18000FD82
0x18000fd31  cmp     qword ptr [rbx+18h], 7
0x18000fd36  jbe     short loc_18000FD3B
0x18000fd38  mov     rbx, [rbx]
0x18000fd3b  mov     [rbp+57h+var_78], rbx
0x18000fd3f  lea     rax, aNewProtocolIsM_0; "New protocol is MIDI 2.0. Downscaling d"...
0x18000fd46  mov     [rbp+57h+var_80], rax
0x18000fd4a  mov     [rbp+57h+var_88], rdi
0x18000fd4e  mov     [rbp+57h+var_90], r13
0x18000fd52  lea     rax, [rbp+57h+var_78]
0x18000fd56  mov     [rsp+0D0h+var_98], rax
0x18000fd5b  lea     rax, [rbp+57h+var_80]
0x18000fd5f  mov     [rsp+0D0h+var_A0], rax
0x18000fd64  lea     rax, [rbp+57h+var_88]
0x18000fd68  mov     [rsp+0D0h+var_A8], rax
0x18000fd6d  lea     rax, [rbp+57h+var_90]
0x18000fd71  mov     [rsp+0D0h+var_B0], rax
0x18000fd76  lea     rdx, word_18001729A
0x18000fd7d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18000fd82  mov     [rdi+61h], r15b
0x18000fd86  jmp     short loc_18000FDED
0x18000fd88  call    ?Instance@MidiUmpProtocolDownscalerTransformTelemetryProvider@@KAPEAV1@XZ; MidiUmpProtocolDownscalerTransformTelemetryProvider::Instance(void)
0x18000fd8d  mov     rcx, [rax+8]
0x18000fd91  mov     eax, [rcx]
0x18000fd93  cmp     eax, 4
0x18000fd96  jbe     short loc_18000FDE9
0x18000fd98  cmp     qword ptr [rbx+18h], 7
0x18000fd9d  jbe     short loc_18000FDA2
0x18000fd9f  mov     rbx, [rbx]
0x18000fda2  mov     [rbp+57h+var_78], rbx
0x18000fda6  lea     rax, aNewProtocolIsM; "New protocol is MIDI 2.0. Endpoint does"...
0x18000fdad  mov     [rbp+57h+var_80], rax
0x18000fdb1  mov     [rbp+57h+var_88], rdi
0x18000fdb5  mov     [rbp+57h+var_90], r13
0x18000fdb9  lea     rax, [rbp+57h+var_78]
0x18000fdbd  mov     [rsp+0D0h+var_98], rax
0x18000fdc2  lea     rax, [rbp+57h+var_80]
0x18000fdc6  mov     [rsp+0D0h+var_A0], rax
0x18000fdcb  lea     rax, [rbp+57h+var_88]
0x18000fdcf  mov     [rsp+0D0h+var_A8], rax
0x18000fdd4  lea     rax, [rbp+57h+var_90]
0x18000fdd8  mov     [rsp+0D0h+var_B0], rax
0x18000fddd  lea     rdx, dword_180017244
0x18000fde4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18000fde9  mov     byte ptr [rdi+61h], 1
0x18000fded  cmp     [rbp+57h+arg_18], r15
0x18000fdf1  jz      short loc_18000FDFD
0x18000fdf3  lea     rcx, [rbp+57h+arg_18]
0x18000fdf7  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000fdfc  nop
0x18000fdfd  cmp     [r14], r15
0x18000fe00  jz      short loc_18000FE0B
0x18000fe02  mov     rcx, r14
0x18000fe05  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000fe0a  nop
0x18000fe0b  cmp     [rsi], r15
0x18000fe0e  jz      short loc_18000FE18
0x18000fe10  mov     rcx, rsi
0x18000fe13  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000fe18  xor     eax, eax
0x18000fe1a  add     rsp, 0A0h
0x18000fe21  pop     r15
0x18000fe23  pop     r14
0x18000fe25  pop     r13
0x18000fe27  pop     rdi
0x18000fe28  pop     rsi
0x18000fe29  pop     rbx
0x18000fe2a  pop     rbp
0x18000fe2b  retn
0x18000fe2c  lea     rdx, [rbp+57h+var_70]
0x18000fe30  mov     ecx, eax
0x18000fe32  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
