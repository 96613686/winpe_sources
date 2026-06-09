# CMidi2KSTransport::Activate(_GUID const &,void * *)

- ea: `0x18000e6f0`
- end: `0x18000edf0`
- name: `?Activate@CMidi2KSTransport@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `1792`
- prototype: `__int64 __fastcall(CMidi2KSTransport *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800016dc`
- `0x180004bf0`
- `0x18000a814`
- `0x18000cb40`
- `0x18000cc90`
- `0x18000cdcc`
- `0x18000db18`
- `0x18000e55c`
- `0x18000e6f0`
- `0x180041010`

## string_xrefs

- `0x18000ebc4`: `IMidiTransportConfigurationManager`
- `0x18000ecd1`: `IMidiServiceTransportPluginMetadataProvider`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CMidi2KSTransport::Activate(const wchar_t *this, const struct _GUID *a2, void **a3)
{
  int v6; // ebx
  __int64 v7; // rdx
  _DWORD *v9; // rcx
  int v10; // r8d
  int v11; // r9d
  _QWORD *v12; // rax
  _QWORD *v13; // rdi
  _DWORD *v14; // rcx
  int v15; // r8d
  int v16; // r9d
  _QWORD *v17; // rax
  _QWORD *v18; // rdi
  _DWORD *v19; // rcx
  int v20; // r8d
  int v21; // r9d
  int v22; // eax
  _DWORD *v23; // rcx
  int v24; // r8d
  int v25; // r9d
  struct TransportState *v26; // rax
  __int64 v27; // rdi
  TransportState *v28; // rax
  struct TransportState *v29; // rax
  __int64 v30; // rdi
  _DWORD *v31; // rcx
  int v32; // r8d
  int v33; // r9d
  struct TransportState *v34; // rax
  __int64 v35; // rdi
  TransportState *v36; // rax
  struct TransportState *v37; // rax
  __int64 v38; // rdi
  _DWORD *v39; // rcx
  int v40; // r8d
  int v41; // r9d
  _DWORD *v42; // rax
  _DWORD *v43; // rdi
  int v44; // [rsp+20h] [rbp-30h]
  int v45[2]; // [rsp+40h] [rbp-10h] BYREF
  int v46[2]; // [rsp+48h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  const wchar_t *v48; // [rsp+80h] [rbp+30h] BYREF
  const wchar_t *v49; // [rsp+88h] [rbp+38h] BYREF

  if ( !a3 )
  {
    v6 = -2147024809;
    v7 = 19;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"avcore\\midi2\\transport\\kstransport\\midi2.kstransport.cpp",
      (const char *)(unsigned int)v6,
      v44);
    return (unsigned int)v6;
  }
  if ( *(_QWORD *)&GUID_6c4b8bf9_8133_4b41_8303_1fde78e20aca.Data1 == *(_QWORD *)&a2->Data1
    && *(_QWORD *)GUID_6c4b8bf9_8133_4b41_8303_1fde78e20aca.Data4 == *(_QWORD *)a2->Data4 )
  {
    v9 = (_DWORD *)*((_QWORD *)MidiKSTransportTelemetryProvider::Instance() + 1);
    if ( *v9 > 4u )
    {
      v49 = L"IMidiIn";
      *(_QWORD *)v45 = this;
      *(_QWORD *)v46 = "CMidi2KSTransport::Activate";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v9,
        (unsigned int)&word_1800685AE,
        v10,
        v11,
        (__int64)v46,
        (__int64)v45,
        (__int64)&v49);
    }
    v48 = 0;
    v12 = operator new(0x18u, (const struct std::nothrow_t *)std::nothrow);
    v13 = v12;
    if ( !v12 )
    {
      v6 = -2147024882;
LABEL_14:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x21,
        (unsigned int)"avcore\\midi2\\transport\\kstransport\\midi2.kstransport.cpp",
        (const char *)(unsigned int)v6,
        v44);
      if ( v48 )
        (*(void (__fastcall **)(const wchar_t *))(*(_QWORD *)v48 + 16LL))(v48);
      return (unsigned int)v6;
    }
    *((_DWORD *)v12 + 3) = 1;
    *v12 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMidiIn>::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *v13 = &CMidi2KSMidiIn::`vftable';
    v13[2] = 0;
    v6 = ((__int64 (__fastcall *)(_QWORD *, GUID *, const wchar_t **))CMidi2KSMidiIn::`vftable')(
           v13,
           &GUID_6c4b8bf9_8133_4b41_8303_1fde78e20aca,
           &v48);
    (*(void (__fastcall **)(_QWORD *))(*v13 + 16LL))(v13);
    if ( v6 < 0 )
      goto LABEL_14;
    *a3 = (void *)v48;
    return 0;
  }
  if ( *(_QWORD *)&GUID_f328d645_7d6d_4924_a7e3_9dee245189f9.Data1 == *(_QWORD *)&a2->Data1
    && *(_QWORD *)GUID_f328d645_7d6d_4924_a7e3_9dee245189f9.Data4 == *(_QWORD *)a2->Data4 )
  {
    v14 = (_DWORD *)*((_QWORD *)MidiKSTransportTelemetryProvider::Instance() + 1);
    if ( *v14 > 4u )
    {
      v49 = L"IMidiOut";
      *(_QWORD *)v46 = this;
      *(_QWORD *)v45 = "CMidi2KSTransport::Activate";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v14,
        (unsigned int)word_18006857A,
        v15,
        v16,
        (__int64)v45,
        (__int64)v46,
        (__int64)&v49);
    }
    v48 = 0;
    v17 = operator new(0x18u, (const struct std::nothrow_t *)std::nothrow);
    v18 = v17;
    if ( !v17 )
    {
      v6 = -2147024882;
LABEL_27:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x30,
        (unsigned int)"avcore\\midi2\\transport\\kstransport\\midi2.kstransport.cpp",
        (const char *)(unsigned int)v6,
        v44);
      if ( v48 )
        (*(void (__fastcall **)(const wchar_t *))(*(_QWORD *)v48 + 16LL))(v48);
      return (unsigned int)v6;
    }
    *((_DWORD *)v17 + 3) = 1;
    *v17 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMidiOut>::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *v18 = &CMidi2KSMidiOut::`vftable';
    v18[2] = 0;
    v6 = ((__int64 (__fastcall *)(_QWORD *, GUID *, const wchar_t **))CMidi2KSMidiOut::`vftable')(
           v18,
           &GUID_f328d645_7d6d_4924_a7e3_9dee245189f9,
           &v48);
    (*(void (__fastcall **)(_QWORD *))(*v18 + 16LL))(v18);
    if ( v6 < 0 )
      goto LABEL_27;
    *a3 = (void *)v48;
    return 0;
  }
  if ( *(_QWORD *)&GUID_b89bbb45_7001_4bea_bbd8_c7cc26e7836c.Data1 == *(_QWORD *)&a2->Data1
    && *(_QWORD *)GUID_b89bbb45_7001_4bea_bbd8_c7cc26e7836c.Data4 == *(_QWORD *)a2->Data4 )
  {
    v19 = (_DWORD *)*((_QWORD *)MidiKSTransportTelemetryProvider::Instance() + 1);
    if ( *v19 > 4u )
    {
      v49 = L"IMidiBidirectional";
      *(_QWORD *)v46 = this;
      *(_QWORD *)v45 = "CMidi2KSTransport::Activate";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v19,
        (unsigned int)&word_180068546,
        v20,
        v21,
        (__int64)v45,
        (__int64)v46,
        (__int64)&v49);
    }
    v48 = 0;
    v22 = Microsoft::WRL::Details::MakeAndInitialize<CMidi2KSMidiBidi,IMidiBidirectional,>(&v48);
    v6 = v22;
    if ( v22 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3F,
        (unsigned int)"avcore\\midi2\\transport\\kstransport\\midi2.kstransport.cpp",
        (const char *)(unsigned int)v22,
        v44);
      if ( v48 )
        (*(void (__fastcall **)(const wchar_t *))(*(_QWORD *)v48 + 16LL))(v48);
      return (unsigned int)v6;
    }
    *a3 = (void *)v48;
    return 0;
  }
  if ( *(_QWORD *)&GUID_badff6d2_0e3c_4009_a473_6ba82c008662.Data1 == *(_QWORD *)&a2->Data1
    && *(_QWORD *)GUID_badff6d2_0e3c_4009_a473_6ba82c008662.Data4 == *(_QWORD *)a2->Data4 )
  {
    v23 = (_DWORD *)*((_QWORD *)MidiKSTransportTelemetryProvider::Instance() + 1);
    if ( *v23 > 4u )
    {
      v48 = L"IMidiEndpointManager";
      v49 = this;
      *(_QWORD *)v46 = "CMidi2KSTransport::Activate";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v23,
        (unsigned int)word_180068512,
        v24,
        v25,
        (__int64)v46,
        (__int64)&v49,
        (__int64)&v48);
    }
    v26 = TransportState::Current();
    v27 = *(_QWORD *)v26;
    if ( *(_QWORD *)v26 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v27 + 8LL))(*(_QWORD *)v26);
    if ( v27 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    }
    else
    {
      v28 = TransportState::Current();
      TransportState::ConstructEndpointManager(v28);
    }
    v29 = TransportState::Current();
    v30 = *(_QWORD *)v29;
    if ( *(_QWORD *)v29 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v30 + 8LL))(*(_QWORD *)v29);
    v6 = (**(__int64 (__fastcall ***)(__int64, const struct _GUID *, void **))v30)(v30, a2, a3);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    if ( v6 < 0 )
    {
      v7 = 84;
      goto LABEL_3;
    }
    return 0;
  }
  if ( *(_QWORD *)&GUID_f19dd642_1809_4497_9eee_f230b11bd6fb.Data1 == *(_QWORD *)&a2->Data1
    && *(_QWORD *)GUID_f19dd642_1809_4497_9eee_f230b11bd6fb.Data4 == *(_QWORD *)a2->Data4 )
  {
    v31 = (_DWORD *)*((_QWORD *)MidiKSTransportTelemetryProvider::Instance() + 1);
    if ( *v31 > 4u )
    {
      v48 = L"IMidiTransportConfigurationManager";
      v49 = this;
      *(_QWORD *)v46 = "CMidi2KSTransport::Activate";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v31,
        (unsigned int)&word_1800684DE,
        v32,
        v33,
        (__int64)v46,
        (__int64)&v49,
        (__int64)&v48);
    }
    v34 = TransportState::Current();
    v35 = *((_QWORD *)v34 + 1);
    if ( v35 )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v35 + 8LL))(*((_QWORD *)v34 + 1));
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    }
    else
    {
      v36 = TransportState::Current();
      TransportState::ConstructConfigurationManager(v36);
    }
    v37 = TransportState::Current();
    v38 = *((_QWORD *)v37 + 1);
    if ( v38 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v38 + 8LL))(*((_QWORD *)v37 + 1));
    v6 = (**(__int64 (__fastcall ***)(__int64, const struct _GUID *, void **))v38)(v38, a2, a3);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
    if ( v6 < 0 )
    {
      v7 = 103;
      goto LABEL_3;
    }
    return 0;
  }
  if ( *(_QWORD *)&GUID_8d542740_83f8_4a9a_8627_cd6324b6c1f4.Data1 == *(_QWORD *)&a2->Data1
    && *(_QWORD *)GUID_8d542740_83f8_4a9a_8627_cd6324b6c1f4.Data4 == *(_QWORD *)a2->Data4 )
  {
    v39 = (_DWORD *)*((_QWORD *)MidiKSTransportTelemetryProvider::Instance() + 1);
    if ( *v39 > 4u )
    {
      v49 = L"IMidiServiceTransportPluginMetadataProvider";
      *(_QWORD *)v46 = this;
      *(_QWORD *)v45 = "CMidi2KSTransport::Activate";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v39,
        (unsigned int)word_1800684AA,
        v40,
        v41,
        (__int64)v45,
        (__int64)v46,
        (__int64)&v49);
    }
    v48 = 0;
    v42 = operator new(0x10u, (const struct std::nothrow_t *)std::nothrow);
    v43 = v42;
    if ( v42 )
    {
      v42[3] = 1;
      *(_QWORD *)v42 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMidiServiceTransportPluginMetadataProvider>::`vftable';
      if ( Microsoft::WRL::Details::ModuleBase::module_ )
        (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                             + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
      *(_QWORD *)v43 = &CMidi2KSMidiPluginMetadataProvider::`vftable';
      v6 = ((__int64 (__fastcall *)(_DWORD *, GUID *, const wchar_t **))CMidi2KSMidiPluginMetadataProvider::`vftable')(
             v43,
             &GUID_8d542740_83f8_4a9a_8627_cd6324b6c1f4,
             &v48);
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v43 + 16LL))(v43);
      if ( v6 >= 0 )
      {
        *a3 = (void *)v48;
        return 0;
      }
    }
    else
    {
      v6 = -2147024882;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x76,
      (unsigned int)"avcore\\midi2\\transport\\kstransport\\midi2.kstransport.cpp",
      (const char *)(unsigned int)v6,
      v44);
    if ( v48 )
      (*(void (__fastcall **)(const wchar_t *))(*(_QWORD *)v48 + 16LL))(v48);
    return (unsigned int)v6;
  }
  return 2147500034LL;
}

```

## disassembly

```asm
0x18000e6f0  mov     [rsp-18h+arg_0], rbx
0x18000e6f5  push    rbp
0x18000e6f6  push    rsi
0x18000e6f7  push    rdi
0x18000e6f8  mov     rbp, rsp
0x18000e6fb  sub     rsp, 50h
0x18000e6ff  mov     rsi, r8
0x18000e702  mov     rbx, rdx
0x18000e705  mov     rdi, rcx
0x18000e708  test    r8, r8
0x18000e70b  jnz     short loc_18000E730
0x18000e70d  mov     ebx, 80070057h
0x18000e712  lea     edx, [r8+13h]; void *
0x18000e716  mov     rcx, [rbp+18h]; this
0x18000e71a  mov     r9d, ebx; char *
0x18000e71d  lea     r8, aAvcoreMidi2Tra; "avcore\\midi2\\transport\\kstransport\\"...
0x18000e724  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e729  mov     eax, ebx
0x18000e72b  jmp     loc_18000EDE3
0x18000e730  mov     rax, qword ptr cs:_GUID_6c4b8bf9_8133_4b41_8303_1fde78e20aca.Data1
0x18000e737  cmp     rax, [rdx]
0x18000e73a  jnz     loc_18000E877
0x18000e740  mov     rax, qword ptr cs:_GUID_6c4b8bf9_8133_4b41_8303_1fde78e20aca.Data4
0x18000e747  cmp     rax, [rdx+8]
0x18000e74b  jnz     loc_18000E877
0x18000e751  call    ?Instance@MidiKSTransportTelemetryProvider@@KAPEAV1@XZ; MidiKSTransportTelemetryProvider::Instance(void)
0x18000e756  mov     rcx, [rax+8]
0x18000e75a  mov     eax, [rcx]
0x18000e75c  cmp     eax, 4
0x18000e75f  jbe     short loc_18000E7A3
0x18000e761  lea     rax, aImidiin; "IMidiIn"
0x18000e768  mov     [rbp+arg_18], rax
0x18000e76c  mov     qword ptr [rbp+var_10], rdi
0x18000e770  lea     rax, aCmidi2kstransp; "CMidi2KSTransport::Activate"
0x18000e777  mov     qword ptr [rbp+var_8], rax
0x18000e77b  lea     rax, [rbp+arg_18]
0x18000e77f  mov     [rsp+50h+var_20], rax
0x18000e784  lea     rax, [rbp+var_10]
0x18000e788  mov     [rsp+50h+var_28], rax
0x18000e78d  lea     rax, [rbp+var_8]
0x18000e791  mov     qword ptr [rsp+50h+var_30], rax; int
0x18000e796  lea     rdx, word_1800685AE
0x18000e79d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x18000e7a2  nop
0x18000e7a3  mov     [rbp+arg_10], 0
0x18000e7ab  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000e7b2  mov     ecx, 18h; unsigned __int64
0x18000e7b7  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000e7bc  mov     rdi, rax
0x18000e7bf  test    rax, rax
0x18000e7c2  jnz     short loc_18000E7CB
0x18000e7c4  mov     ebx, 8007000Eh
0x18000e7c9  jmp     short loc_18000E837
0x18000e7cb  mov     dword ptr [rax+0Ch], 1
0x18000e7d2  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIMidiIn@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMidiIn>::`vftable'
0x18000e7d9  mov     [rdi], rax
0x18000e7dc  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000e7e3  test    rcx, rcx
0x18000e7e6  jz      short loc_18000E7F5
0x18000e7e8  mov     rax, [rcx]
0x18000e7eb  mov     rax, [rax+8]
0x18000e7ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e7f4  nop
0x18000e7f5  lea     rax, ??_7CMidi2KSMidiIn@@6B@; const CMidi2KSMidiIn::`vftable'
0x18000e7fc  mov     [rdi], rax
0x18000e7ff  mov     qword ptr [rdi+10h], 0
0x18000e807  lea     r8, [rbp+arg_10]
0x18000e80b  lea     rdx, _GUID_6c4b8bf9_8133_4b41_8303_1fde78e20aca
0x18000e812  mov     rcx, rdi
0x18000e815  mov     rax, cs:??_7CMidi2KSMidiIn@@6B@; const CMidi2KSMidiIn::`vftable'
0x18000e81c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e821  mov     ebx, eax
0x18000e823  mov     rax, [rdi]
0x18000e826  mov     rcx, rdi
0x18000e829  mov     rax, [rax+10h]
0x18000e82d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e832  nop
0x18000e833  test    ebx, ebx
0x18000e835  jns     short loc_18000E86B
0x18000e837  mov     rcx, [rbp+18h]; this
0x18000e83b  mov     r9d, ebx; char *
0x18000e83e  lea     r8, aAvcoreMidi2Tra; "avcore\\midi2\\transport\\kstransport\\"...
0x18000e845  mov     edx, 21h ; '!'; void *
0x18000e84a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e84f  nop
0x18000e850  mov     rcx, [rbp+arg_10]
0x18000e854  test    rcx, rcx
0x18000e857  jz      short loc_18000E866
0x18000e859  mov     rax, [rcx]
0x18000e85c  mov     rax, [rax+10h]
0x18000e860  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e865  nop
0x18000e866  jmp     loc_18000E729
0x18000e86b  mov     rax, [rbp+arg_10]
0x18000e86f  mov     [rsi], rax
0x18000e872  jmp     loc_18000EDDA
0x18000e877  mov     rax, qword ptr cs:_GUID_f328d645_7d6d_4924_a7e3_9dee245189f9.Data1
0x18000e87e  cmp     rax, [rdx]
0x18000e881  jnz     loc_18000E9BE
0x18000e887  mov     rax, qword ptr cs:_GUID_f328d645_7d6d_4924_a7e3_9dee245189f9.Data4
0x18000e88e  cmp     rax, [rdx+8]
0x18000e892  jnz     loc_18000E9BE
0x18000e898  call    ?Instance@MidiKSTransportTelemetryProvider@@KAPEAV1@XZ; MidiKSTransportTelemetryProvider::Instance(void)
0x18000e89d  mov     rcx, [rax+8]
0x18000e8a1  mov     eax, [rcx]
0x18000e8a3  cmp     eax, 4
0x18000e8a6  jbe     short loc_18000E8EA
0x18000e8a8  lea     rax, aImidiout; "IMidiOut"
0x18000e8af  mov     [rbp+arg_18], rax
0x18000e8b3  mov     qword ptr [rbp+var_8], rdi
0x18000e8b7  lea     rax, aCmidi2kstransp; "CMidi2KSTransport::Activate"
0x18000e8be  mov     qword ptr [rbp+var_10], rax
0x18000e8c2  lea     rax, [rbp+arg_18]
0x18000e8c6  mov     [rsp+50h+var_20], rax
0x18000e8cb  lea     rax, [rbp+var_8]
0x18000e8cf  mov     [rsp+50h+var_28], rax
0x18000e8d4  lea     rax, [rbp+var_10]
0x18000e8d8  mov     qword ptr [rsp+50h+var_30], rax; int
0x18000e8dd  lea     rdx, word_18006857A
0x18000e8e4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x18000e8e9  nop
0x18000e8ea  mov     [rbp+arg_10], 0
0x18000e8f2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000e8f9  mov     ecx, 18h; unsigned __int64
0x18000e8fe  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000e903  mov     rdi, rax
0x18000e906  test    rax, rax
0x18000e909  jnz     short loc_18000E912
0x18000e90b  mov     ebx, 8007000Eh
0x18000e910  jmp     short loc_18000E97E
0x18000e912  mov     dword ptr [rax+0Ch], 1
0x18000e919  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIMidiOut@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMidiOut>::`vftable'
0x18000e920  mov     [rdi], rax
0x18000e923  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000e92a  test    rcx, rcx
0x18000e92d  jz      short loc_18000E93C
0x18000e92f  mov     rax, [rcx]
0x18000e932  mov     rax, [rax+8]
0x18000e936  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e93b  nop
0x18000e93c  lea     rax, ??_7CMidi2KSMidiOut@@6B@; const CMidi2KSMidiOut::`vftable'
0x18000e943  mov     [rdi], rax
0x18000e946  mov     qword ptr [rdi+10h], 0
0x18000e94e  lea     r8, [rbp+arg_10]
0x18000e952  lea     rdx, _GUID_f328d645_7d6d_4924_a7e3_9dee245189f9
0x18000e959  mov     rcx, rdi
0x18000e95c  mov     rax, cs:??_7CMidi2KSMidiOut@@6B@; const CMidi2KSMidiOut::`vftable'
0x18000e963  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e968  mov     ebx, eax
0x18000e96a  mov     rax, [rdi]
0x18000e96d  mov     rcx, rdi
0x18000e970  mov     rax, [rax+10h]
0x18000e974  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e979  nop
0x18000e97a  test    ebx, ebx
0x18000e97c  jns     short loc_18000E9B2
0x18000e97e  mov     rcx, [rbp+18h]; this
0x18000e982  mov     r9d, ebx; char *
0x18000e985  lea     r8, aAvcoreMidi2Tra; "avcore\\midi2\\transport\\kstransport\\"...
0x18000e98c  mov     edx, 30h ; '0'; void *
0x18000e991  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e996  nop
0x18000e997  mov     rcx, [rbp+arg_10]
0x18000e99b  test    rcx, rcx
0x18000e99e  jz      short loc_18000E9AD
0x18000e9a0  mov     rax, [rcx]
0x18000e9a3  mov     rax, [rax+10h]
0x18000e9a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e9ac  nop
0x18000e9ad  jmp     loc_18000E729
0x18000e9b2  mov     rax, [rbp+arg_10]
0x18000e9b6  mov     [rsi], rax
0x18000e9b9  jmp     loc_18000EDDA
0x18000e9be  mov     rax, qword ptr cs:_GUID_b89bbb45_7001_4bea_bbd8_c7cc26e7836c.Data1
0x18000e9c5  cmp     rax, [rdx]
0x18000e9c8  jnz     loc_18000EA88
0x18000e9ce  mov     rax, qword ptr cs:_GUID_b89bbb45_7001_4bea_bbd8_c7cc26e7836c.Data4
0x18000e9d5  cmp     rax, [rdx+8]
0x18000e9d9  jnz     loc_18000EA88
0x18000e9df  call    ?Instance@MidiKSTransportTelemetryProvider@@KAPEAV1@XZ; MidiKSTransportTelemetryProvider::Instance(void)
0x18000e9e4  mov     rcx, [rax+8]
0x18000e9e8  mov     eax, [rcx]
0x18000e9ea  cmp     eax, 4
0x18000e9ed  jbe     short loc_18000EA31
0x18000e9ef  lea     rax, aImidibidirecti; "IMidiBidirectional"
0x18000e9f6  mov     [rbp+arg_18], rax
0x18000e9fa  mov     qword ptr [rbp+var_8], rdi
0x18000e9fe  lea     rax, aCmidi2kstransp; "CMidi2KSTransport::Activate"
0x18000ea05  mov     qword ptr [rbp+var_10], rax
0x18000ea09  lea     rax, [rbp+arg_18]
0x18000ea0d  mov     [rsp+50h+var_20], rax
0x18000ea12  lea     rax, [rbp+var_8]
0x18000ea16  mov     [rsp+50h+var_28], rax
0x18000ea1b  lea     rax, [rbp+var_10]
0x18000ea1f  mov     qword ptr [rsp+50h+var_30], rax; int
0x18000ea24  lea     rdx, word_180068546
0x18000ea2b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x18000ea30  nop
0x18000ea31  mov     [rbp+arg_10], 0
0x18000ea39  lea     rcx, [rbp+arg_10]
0x18000ea3d  call    ??$MakeAndInitialize@VCMidi2KSMidiBidi@@UIMidiBidirectional@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIMidiBidirectional@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CMidi2KSMidiBidi,IMidiBidirectional,>(IMidiBidirectional * *)
0x18000ea42  mov     ebx, eax
0x18000ea44  test    eax, eax
0x18000ea46  jns     short loc_18000EA7C
0x18000ea48  mov     rcx, [rbp+18h]; this
0x18000ea4c  mov     r9d, eax; char *
0x18000ea4f  lea     r8, aAvcoreMidi2Tra; "avcore\\midi2\\transport\\kstransport\\"...
0x18000ea56  mov     edx, 3Fh ; '?'; void *
0x18000ea5b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ea60  nop
0x18000ea61  mov     rcx, [rbp+arg_10]
0x18000ea65  test    rcx, rcx
0x18000ea68  jz      short loc_18000EA77
0x18000ea6a  mov     rax, [rcx]
0x18000ea6d  mov     rax, [rax+10h]
0x18000ea71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea76  nop
0x18000ea77  jmp     loc_18000E729
0x18000ea7c  mov     rax, [rbp+arg_10]
0x18000ea80  mov     [rsi], rax
0x18000ea83  jmp     loc_18000EDDA
0x18000ea88  mov     rax, qword ptr cs:_GUID_badff6d2_0e3c_4009_a473_6ba82c008662.Data1
0x18000ea8f  cmp     rax, [rdx]
0x18000ea92  jnz     loc_18000EB93
0x18000ea98  mov     rax, qword ptr cs:_GUID_badff6d2_0e3c_4009_a473_6ba82c008662.Data4
0x18000ea9f  cmp     rax, [rdx+8]
0x18000eaa3  jnz     loc_18000EB93
0x18000eaa9  call    ?Instance@MidiKSTransportTelemetryProvider@@KAPEAV1@XZ; MidiKSTransportTelemetryProvider::Instance(void)
0x18000eaae  mov     rcx, [rax+8]
0x18000eab2  mov     eax, [rcx]
0x18000eab4  cmp     eax, 4
0x18000eab7  jbe     short loc_18000EAFA
0x18000eab9  lea     rax, aImidiendpointm; "IMidiEndpointManager"
0x18000eac0  mov     [rbp+arg_10], rax
0x18000eac4  mov     [rbp+arg_18], rdi
0x18000eac8  lea     rax, aCmidi2kstransp; "CMidi2KSTransport::Activate"
0x18000eacf  mov     qword ptr [rbp+var_8], rax
0x18000ead3  lea     rax, [rbp+arg_10]
0x18000ead7  mov     [rsp+50h+var_20], rax
0x18000eadc  lea     rax, [rbp+arg_18]
0x18000eae0  mov     [rsp+50h+var_28], rax
0x18000eae5  lea     rax, [rbp+var_8]
0x18000eae9  mov     qword ptr [rsp+50h+var_30], rax
0x18000eaee  lea     rdx, word_180068512
0x18000eaf5  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x18000eafa  call    ?Current@TransportState@@SAAEAV1@XZ; TransportState::Current(void)
0x18000eaff  mov     rdi, [rax]
0x18000eb02  test    rdi, rdi
0x18000eb05  jz      short loc_18000EB17
0x18000eb07  mov     rax, [rdi]
0x18000eb0a  mov     rcx, rdi
0x18000eb0d  mov     rax, [rax+8]
0x18000eb11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb16  nop
0x18000eb17  test    rdi, rdi
0x18000eb1a  jz      short loc_18000EB2C
0x18000eb1c  mov     rax, [rdi]
0x18000eb1f  mov     rcx, rdi
0x18000eb22  mov     rax, [rax+10h]
0x18000eb26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb2b  nop
0x18000eb2c  test    rdi, rdi
0x18000eb2f  jnz     short loc_18000EB3E
0x18000eb31  call    ?Current@TransportState@@SAAEAV1@XZ; TransportState::Current(void)
0x18000eb36  mov     rcx, rax; this
0x18000eb39  call    ?ConstructEndpointManager@TransportState@@QEAAJXZ; TransportState::ConstructEndpointManager(void)
0x18000eb3e  call    ?Current@TransportState@@SAAEAV1@XZ; TransportState::Current(void)
0x18000eb43  mov     rdi, [rax]
0x18000eb46  test    rdi, rdi
0x18000eb49  jz      short loc_18000EB5B
0x18000eb4b  mov     rax, [rdi]
0x18000eb4e  mov     rcx, rdi
0x18000eb51  mov     rax, [rax+8]
0x18000eb55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb5a  nop
0x18000eb5b  mov     rax, [rdi]
0x18000eb5e  mov     r8, rsi
0x18000eb61  mov     rdx, rbx
0x18000eb64  mov     rcx, rdi
0x18000eb67  mov     rax, [rax]
0x18000eb6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb6f  mov     ebx, eax
0x18000eb71  mov     rdx, [rdi]
0x18000eb74  mov     rcx, rdi
0x18000eb77  mov     rax, [rdx+10h]
0x18000eb7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb80  nop
0x18000eb81  test    ebx, ebx
0x18000eb83  jns     loc_18000EDDA
0x18000eb89  mov     edx, 54h ; 'T'
0x18000eb8e  jmp     loc_18000E716
0x18000eb93  mov     rax, qword ptr cs:_GUID_f19dd642_1809_4497_9eee_f230b11bd6fb.Data1
0x18000eb9a  cmp     rax, [rdx]
0x18000eb9d  jnz     loc_18000ECA0
0x18000eba3  mov     rax, qword ptr cs:_GUID_f19dd642_1809_4497_9eee_f230b11bd6fb.Data4
0x18000ebaa  cmp     rax, [rdx+8]
0x18000ebae  jnz     loc_18000ECA0
0x18000ebb4  call    ?Instance@MidiKSTransportTelemetryProvider@@KAPEAV1@XZ; MidiKSTransportTelemetryProvider::Instance(void)
0x18000ebb9  mov     rcx, [rax+8]
0x18000ebbd  mov     eax, [rcx]
  ... truncated ...
```
