# CMidi2LoopbackMidiTransport::Activate(_GUID const &,void * *)

- ea: `0x18000d720`
- end: `0x18000dc59`
- name: `?Activate@CMidi2LoopbackMidiTransport@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `1337`
- prototype: `__int64 __fastcall(CMidi2LoopbackMidiTransport *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800016dc`
- `0x18000499c`
- `0x18000a024`
- `0x18000bdf0`
- `0x18000bed4`
- `0x18000bfe4`
- `0x18000ccd8`
- `0x18000d720`
- `0x180032010`

## string_xrefs

- `0x18000da2d`: `IMidiTransportConfigurationManager`
- `0x18000db3a`: `IMidiServiceTransportPluginMetadataProvider`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CMidi2LoopbackMidiTransport::Activate(const wchar_t *this, const struct _GUID *a2, void **a3)
{
  int v6; // ebx
  __int64 v7; // rdx
  _DWORD *v9; // rcx
  int v10; // r8d
  int v11; // r9d
  _DWORD *v12; // rax
  _DWORD *v13; // rdi
  _DWORD *v14; // rcx
  int v15; // r8d
  int v16; // r9d
  struct TransportState *v17; // rax
  __int64 v18; // rdi
  TransportState *v19; // rax
  struct TransportState *v20; // rax
  __int64 v21; // rdi
  _DWORD *v22; // rcx
  int v23; // r8d
  int v24; // r9d
  struct TransportState *v25; // rax
  __int64 v26; // rdi
  TransportState *v27; // rax
  struct TransportState *v28; // rax
  __int64 v29; // rdi
  _DWORD *v30; // rcx
  int v31; // r8d
  int v32; // r9d
  _DWORD *v33; // rax
  _DWORD *v34; // rdi
  int v35; // [rsp+20h] [rbp-30h]
  int v36[2]; // [rsp+40h] [rbp-10h] BYREF
  int v37[2]; // [rsp+48h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  const wchar_t *v39; // [rsp+80h] [rbp+30h] BYREF
  const wchar_t *v40; // [rsp+88h] [rbp+38h] BYREF

  if ( !a3 )
  {
    v6 = -2147024809;
    v7 = 19;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"avcore\\midi2\\transport\\loopbackmiditransport\\midi2.loopbackmiditransport.cpp",
      (const char *)(unsigned int)v6,
      v35);
    return (unsigned int)v6;
  }
  if ( *(_QWORD *)&GUID_b89bbb45_7001_4bea_bbd8_c7cc26e7836c.Data1 == *(_QWORD *)&a2->Data1
    && *(_QWORD *)GUID_b89bbb45_7001_4bea_bbd8_c7cc26e7836c.Data4 == *(_QWORD *)a2->Data4 )
  {
    v9 = (_DWORD *)*((_QWORD *)MidiLoopbackMidiTransportTelemetryProvider::Instance() + 1);
    if ( *v9 > 4u )
    {
      v40 = L"IMidiBidirectional";
      *(_QWORD *)v36 = this;
      *(_QWORD *)v37 = "CMidi2LoopbackMidiTransport::Activate";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v9,
        (unsigned int)&word_180057E56,
        v10,
        v11,
        (__int64)v37,
        (__int64)v36,
        (__int64)&v40);
    }
    v39 = 0;
    v12 = operator new(0x70u, (const struct std::nothrow_t *)std::nothrow);
    v13 = v12;
    if ( !v12 )
    {
      v6 = -2147024882;
LABEL_14:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x23,
        (unsigned int)"avcore\\midi2\\transport\\loopbackmiditransport\\midi2.loopbackmiditransport.cpp",
        (const char *)(unsigned int)v6,
        v35);
      if ( v39 )
        (*(void (__fastcall **)(const wchar_t *))(*(_QWORD *)v39 + 16LL))(v39);
      return (unsigned int)v6;
    }
    v12[5] = 1;
    *(_QWORD *)v12 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMidiBidirectional,IMidiCallback>::`vftable'{for `IMidiBidirectional'};
    *((_QWORD *)v12 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMidiBidirectional,IMidiCallback>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IMidiCallback>'};
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v13 = &CMidi2LoopbackMidiBidi::`vftable'{for `IMidiBidirectional'};
    *((_QWORD *)v13 + 1) = &CMidi2LoopbackMidiBidi::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IMidiCallback>'};
    *((_BYTE *)v13 + 24) = 0;
    *((_OWORD *)v13 + 2) = 0;
    *((_QWORD *)v13 + 6) = 0;
    *((_QWORD *)v13 + 7) = 7;
    *((_WORD *)v13 + 16) = 0;
    *((_QWORD *)v13 + 8) = 0;
    *((_QWORD *)v13 + 9) = 0;
    *((_OWORD *)v13 + 5) = 0;
    *((_QWORD *)v13 + 12) = 0;
    *((_QWORD *)v13 + 13) = 7;
    *((_WORD *)v13 + 40) = 0;
    v6 = (**(__int64 (__fastcall ***)(_DWORD *, GUID *, const wchar_t **))v13)(
           v13,
           &GUID_b89bbb45_7001_4bea_bbd8_c7cc26e7836c,
           &v39);
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v13 + 16LL))(v13);
    if ( v6 < 0 )
      goto LABEL_14;
    *a3 = (void *)v39;
    return 0;
  }
  if ( *(_QWORD *)&GUID_badff6d2_0e3c_4009_a473_6ba82c008662.Data1 == *(_QWORD *)&a2->Data1
    && *(_QWORD *)GUID_badff6d2_0e3c_4009_a473_6ba82c008662.Data4 == *(_QWORD *)a2->Data4 )
  {
    v14 = (_DWORD *)*((_QWORD *)MidiLoopbackMidiTransportTelemetryProvider::Instance() + 1);
    if ( *v14 > 4u )
    {
      v39 = L"IMidiEndpointManager";
      v40 = this;
      *(_QWORD *)v37 = "CMidi2LoopbackMidiTransport::Activate";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v14,
        (unsigned int)word_180057E22,
        v15,
        v16,
        (__int64)v37,
        (__int64)&v40,
        (__int64)&v39);
    }
    v17 = TransportState::Current();
    v18 = *(_QWORD *)v17;
    if ( *(_QWORD *)v17 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v18 + 8LL))(*(_QWORD *)v17);
    if ( v18 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    }
    else
    {
      v19 = TransportState::Current();
      TransportState::ConstructEndpointManager(v19);
    }
    v20 = TransportState::Current();
    v21 = *(_QWORD *)v20;
    if ( *(_QWORD *)v20 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v21 + 8LL))(*(_QWORD *)v20);
    v6 = (**(__int64 (__fastcall ***)(__int64, const struct _GUID *, void **))v21)(v21, a2, a3);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    if ( v6 < 0 )
    {
      v7 = 56;
      goto LABEL_3;
    }
    return 0;
  }
  if ( *(_QWORD *)&GUID_f19dd642_1809_4497_9eee_f230b11bd6fb.Data1 == *(_QWORD *)&a2->Data1
    && *(_QWORD *)GUID_f19dd642_1809_4497_9eee_f230b11bd6fb.Data4 == *(_QWORD *)a2->Data4 )
  {
    v22 = (_DWORD *)*((_QWORD *)MidiLoopbackMidiTransportTelemetryProvider::Instance() + 1);
    if ( *v22 > 4u )
    {
      v39 = L"IMidiTransportConfigurationManager";
      v40 = this;
      *(_QWORD *)v37 = "CMidi2LoopbackMidiTransport::Activate";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v22,
        (unsigned int)&word_180057DEE,
        v23,
        v24,
        (__int64)v37,
        (__int64)&v40,
        (__int64)&v39);
    }
    v25 = TransportState::Current();
    v26 = *((_QWORD *)v25 + 1);
    if ( v26 )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v26 + 8LL))(*((_QWORD *)v25 + 1));
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    }
    else
    {
      v27 = TransportState::Current();
      TransportState::ConstructConfigurationManager(v27);
    }
    v28 = TransportState::Current();
    v29 = *((_QWORD *)v28 + 1);
    if ( v29 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v29 + 8LL))(*((_QWORD *)v28 + 1));
    v6 = (**(__int64 (__fastcall ***)(__int64, const struct _GUID *, void **))v29)(v29, a2, a3);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    if ( v6 < 0 )
    {
      v7 = 76;
      goto LABEL_3;
    }
    return 0;
  }
  if ( *(_QWORD *)&GUID_8d542740_83f8_4a9a_8627_cd6324b6c1f4.Data1 == *(_QWORD *)&a2->Data1
    && *(_QWORD *)GUID_8d542740_83f8_4a9a_8627_cd6324b6c1f4.Data4 == *(_QWORD *)a2->Data4 )
  {
    v30 = (_DWORD *)*((_QWORD *)MidiLoopbackMidiTransportTelemetryProvider::Instance() + 1);
    if ( *v30 > 4u )
    {
      v40 = L"IMidiServiceTransportPluginMetadataProvider";
      *(_QWORD *)v37 = this;
      *(_QWORD *)v36 = "CMidi2LoopbackMidiTransport::Activate";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v30,
        (unsigned int)word_180057DBA,
        v31,
        v32,
        (__int64)v36,
        (__int64)v37,
        (__int64)&v40);
    }
    v39 = 0;
    v33 = operator new(0x20u, (const struct std::nothrow_t *)std::nothrow);
    v34 = v33;
    if ( v33 )
    {
      v33[3] = 1;
      *(_QWORD *)v33 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMidiServiceTransportPluginMetadataProvider>::`vftable';
      if ( Microsoft::WRL::Details::ModuleBase::module_ )
        (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                             + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
      *(_QWORD *)v34 = &CMidi2LoopbackMidiPluginMetadataProvider::`vftable';
      v6 = ((__int64 (__fastcall *)(_DWORD *, GUID *, const wchar_t **))CMidi2LoopbackMidiPluginMetadataProvider::`vftable')(
             v34,
             &GUID_8d542740_83f8_4a9a_8627_cd6324b6c1f4,
             &v39);
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v34 + 16LL))(v34);
      if ( v6 >= 0 )
      {
        *a3 = (void *)v39;
        return 0;
      }
    }
    else
    {
      v6 = -2147024882;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5B,
      (unsigned int)"avcore\\midi2\\transport\\loopbackmiditransport\\midi2.loopbackmiditransport.cpp",
      (const char *)(unsigned int)v6,
      v35);
    if ( v39 )
      (*(void (__fastcall **)(const wchar_t *))(*(_QWORD *)v39 + 16LL))(v39);
    return (unsigned int)v6;
  }
  return 2147500034LL;
}

```

## disassembly

```asm
0x18000d720  mov     [rsp-18h+arg_0], rbx
0x18000d725  push    rbp
0x18000d726  push    rsi
0x18000d727  push    rdi
0x18000d728  mov     rbp, rsp
0x18000d72b  sub     rsp, 50h
0x18000d72f  mov     rsi, r8
0x18000d732  mov     rbx, rdx
0x18000d735  mov     rdi, rcx
0x18000d738  test    r8, r8
0x18000d73b  jnz     short loc_18000D760
0x18000d73d  mov     ebx, 80070057h
0x18000d742  lea     edx, [r8+13h]; void *
0x18000d746  mov     rcx, [rbp+18h]; this
0x18000d74a  mov     r9d, ebx; char *
0x18000d74d  lea     r8, aAvcoreMidi2Tra_4; "avcore\\midi2\\transport\\loopbackmidit"...
0x18000d754  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d759  mov     eax, ebx
0x18000d75b  jmp     loc_18000DC4C
0x18000d760  mov     rax, qword ptr cs:_GUID_b89bbb45_7001_4bea_bbd8_c7cc26e7836c.Data1
0x18000d767  cmp     rax, [rdx]
0x18000d76a  jnz     loc_18000D8F1
0x18000d770  mov     rax, qword ptr cs:_GUID_b89bbb45_7001_4bea_bbd8_c7cc26e7836c.Data4
0x18000d777  cmp     rax, [rdx+8]
0x18000d77b  jnz     loc_18000D8F1
0x18000d781  call    ?Instance@MidiLoopbackMidiTransportTelemetryProvider@@KAPEAV1@XZ; MidiLoopbackMidiTransportTelemetryProvider::Instance(void)
0x18000d786  mov     rcx, [rax+8]
0x18000d78a  mov     eax, [rcx]
0x18000d78c  cmp     eax, 4
0x18000d78f  jbe     short loc_18000D7D3
0x18000d791  lea     rax, aImidibidirecti; "IMidiBidirectional"
0x18000d798  mov     [rbp+arg_18], rax
0x18000d79c  mov     qword ptr [rbp+var_10], rdi
0x18000d7a0  lea     rax, aCmidi2loopback_1; "CMidi2LoopbackMidiTransport::Activate"
0x18000d7a7  mov     qword ptr [rbp+var_8], rax
0x18000d7ab  lea     rax, [rbp+arg_18]
0x18000d7af  mov     [rsp+50h+var_20], rax
0x18000d7b4  lea     rax, [rbp+var_10]
0x18000d7b8  mov     [rsp+50h+var_28], rax
0x18000d7bd  lea     rax, [rbp+var_8]
0x18000d7c1  mov     qword ptr [rsp+50h+var_30], rax; int
0x18000d7c6  lea     rdx, word_180057E56
0x18000d7cd  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x18000d7d2  nop
0x18000d7d3  mov     [rbp+arg_10], 0
0x18000d7db  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000d7e2  mov     ecx, 70h ; 'p'; unsigned __int64
0x18000d7e7  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000d7ec  mov     rdi, rax
0x18000d7ef  test    rax, rax
0x18000d7f2  jnz     short loc_18000D7FE
0x18000d7f4  mov     ebx, 8007000Eh
0x18000d7f9  jmp     loc_18000D8B1
0x18000d7fe  mov     dword ptr [rax+14h], 1
0x18000d805  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIMidiBidirectional@@UIMidiCallback@@@WRL@Microsoft@@6BIMidiBidirectional@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMidiBidirectional,IMidiCallback>::`vftable'{for `IMidiBidirectional'}
0x18000d80c  mov     [rdi], rax
0x18000d80f  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIMidiBidirectional@@UIMidiCallback@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIMidiCallback@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMidiBidirectional,IMidiCallback>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IMidiCallback>'}
0x18000d816  mov     [rdi+8], rax
0x18000d81a  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000d821  test    rcx, rcx
0x18000d824  jz      short loc_18000D833
0x18000d826  mov     rax, [rcx]
0x18000d829  mov     rax, [rax+8]
0x18000d82d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d832  nop
0x18000d833  lea     rax, ??_7CMidi2LoopbackMidiBidi@@6BIMidiBidirectional@@@; const CMidi2LoopbackMidiBidi::`vftable'{for `IMidiBidirectional'}
0x18000d83a  mov     [rdi], rax
0x18000d83d  lea     rax, ??_7CMidi2LoopbackMidiBidi@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIMidiCallback@@@Details@WRL@Microsoft@@@; const CMidi2LoopbackMidiBidi::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IMidiCallback>'}
0x18000d844  mov     [rdi+8], rax
0x18000d848  mov     byte ptr [rdi+18h], 0
0x18000d84c  xorps   xmm0, xmm0
0x18000d84f  movups  xmmword ptr [rdi+20h], xmm0
0x18000d853  mov     qword ptr [rdi+30h], 0
0x18000d85b  mov     ecx, 7
0x18000d860  mov     [rdi+38h], rcx
0x18000d864  xor     eax, eax
0x18000d866  mov     [rdi+20h], ax
0x18000d86a  mov     [rdi+40h], rax
0x18000d86e  mov     [rdi+48h], rax
0x18000d872  movups  xmmword ptr [rdi+50h], xmm0
0x18000d876  mov     [rdi+60h], rax
0x18000d87a  mov     [rdi+68h], rcx
0x18000d87e  mov     [rdi+50h], ax
0x18000d882  mov     rax, [rdi]
0x18000d885  lea     r8, [rbp+arg_10]
0x18000d889  lea     rdx, _GUID_b89bbb45_7001_4bea_bbd8_c7cc26e7836c
0x18000d890  mov     rcx, rdi
0x18000d893  mov     rax, [rax]
0x18000d896  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d89b  mov     ebx, eax
0x18000d89d  mov     rax, [rdi]
0x18000d8a0  mov     rcx, rdi
0x18000d8a3  mov     rax, [rax+10h]
0x18000d8a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d8ac  nop
0x18000d8ad  test    ebx, ebx
0x18000d8af  jns     short loc_18000D8E5
0x18000d8b1  mov     rcx, [rbp+18h]; this
0x18000d8b5  mov     r9d, ebx; char *
0x18000d8b8  lea     r8, aAvcoreMidi2Tra_4; "avcore\\midi2\\transport\\loopbackmidit"...
0x18000d8bf  mov     edx, 23h ; '#'; void *
0x18000d8c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d8c9  nop
0x18000d8ca  mov     rcx, [rbp+arg_10]
0x18000d8ce  test    rcx, rcx
0x18000d8d1  jz      short loc_18000D8E0
0x18000d8d3  mov     rax, [rcx]
0x18000d8d6  mov     rax, [rax+10h]
0x18000d8da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d8df  nop
0x18000d8e0  jmp     loc_18000D759
0x18000d8e5  mov     rax, [rbp+arg_10]
0x18000d8e9  mov     [rsi], rax
0x18000d8ec  jmp     loc_18000DC43
0x18000d8f1  mov     rax, qword ptr cs:_GUID_badff6d2_0e3c_4009_a473_6ba82c008662.Data1
0x18000d8f8  cmp     rax, [rdx]
0x18000d8fb  jnz     loc_18000D9FC
0x18000d901  mov     rax, qword ptr cs:_GUID_badff6d2_0e3c_4009_a473_6ba82c008662.Data4
0x18000d908  cmp     rax, [rdx+8]
0x18000d90c  jnz     loc_18000D9FC
0x18000d912  call    ?Instance@MidiLoopbackMidiTransportTelemetryProvider@@KAPEAV1@XZ; MidiLoopbackMidiTransportTelemetryProvider::Instance(void)
0x18000d917  mov     rcx, [rax+8]
0x18000d91b  mov     eax, [rcx]
0x18000d91d  cmp     eax, 4
0x18000d920  jbe     short loc_18000D963
0x18000d922  lea     rax, aImidiendpointm; "IMidiEndpointManager"
0x18000d929  mov     [rbp+arg_10], rax
0x18000d92d  mov     [rbp+arg_18], rdi
0x18000d931  lea     rax, aCmidi2loopback_1; "CMidi2LoopbackMidiTransport::Activate"
0x18000d938  mov     qword ptr [rbp+var_8], rax
0x18000d93c  lea     rax, [rbp+arg_10]
0x18000d940  mov     [rsp+50h+var_20], rax
0x18000d945  lea     rax, [rbp+arg_18]
0x18000d949  mov     [rsp+50h+var_28], rax
0x18000d94e  lea     rax, [rbp+var_8]
0x18000d952  mov     qword ptr [rsp+50h+var_30], rax
0x18000d957  lea     rdx, word_180057E22
0x18000d95e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x18000d963  call    ?Current@TransportState@@SAAEAV1@XZ; TransportState::Current(void)
0x18000d968  mov     rdi, [rax]
0x18000d96b  test    rdi, rdi
0x18000d96e  jz      short loc_18000D980
0x18000d970  mov     rax, [rdi]
0x18000d973  mov     rcx, rdi
0x18000d976  mov     rax, [rax+8]
0x18000d97a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d97f  nop
0x18000d980  test    rdi, rdi
0x18000d983  jz      short loc_18000D995
0x18000d985  mov     rax, [rdi]
0x18000d988  mov     rcx, rdi
0x18000d98b  mov     rax, [rax+10h]
0x18000d98f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d994  nop
0x18000d995  test    rdi, rdi
0x18000d998  jnz     short loc_18000D9A7
0x18000d99a  call    ?Current@TransportState@@SAAEAV1@XZ; TransportState::Current(void)
0x18000d99f  mov     rcx, rax; this
0x18000d9a2  call    ?ConstructEndpointManager@TransportState@@QEAAJXZ; TransportState::ConstructEndpointManager(void)
0x18000d9a7  call    ?Current@TransportState@@SAAEAV1@XZ; TransportState::Current(void)
0x18000d9ac  mov     rdi, [rax]
0x18000d9af  test    rdi, rdi
0x18000d9b2  jz      short loc_18000D9C4
0x18000d9b4  mov     rax, [rdi]
0x18000d9b7  mov     rcx, rdi
0x18000d9ba  mov     rax, [rax+8]
0x18000d9be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d9c3  nop
0x18000d9c4  mov     rax, [rdi]
0x18000d9c7  mov     r8, rsi
0x18000d9ca  mov     rdx, rbx
0x18000d9cd  mov     rcx, rdi
0x18000d9d0  mov     rax, [rax]
0x18000d9d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d9d8  mov     ebx, eax
0x18000d9da  mov     rdx, [rdi]
0x18000d9dd  mov     rcx, rdi
0x18000d9e0  mov     rax, [rdx+10h]
0x18000d9e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d9e9  nop
0x18000d9ea  test    ebx, ebx
0x18000d9ec  jns     loc_18000DC43
0x18000d9f2  mov     edx, 38h ; '8'
0x18000d9f7  jmp     loc_18000D746
0x18000d9fc  mov     rax, qword ptr cs:_GUID_f19dd642_1809_4497_9eee_f230b11bd6fb.Data1
0x18000da03  cmp     rax, [rdx]
0x18000da06  jnz     loc_18000DB09
0x18000da0c  mov     rax, qword ptr cs:_GUID_f19dd642_1809_4497_9eee_f230b11bd6fb.Data4
0x18000da13  cmp     rax, [rdx+8]
0x18000da17  jnz     loc_18000DB09
0x18000da1d  call    ?Instance@MidiLoopbackMidiTransportTelemetryProvider@@KAPEAV1@XZ; MidiLoopbackMidiTransportTelemetryProvider::Instance(void)
0x18000da22  mov     rcx, [rax+8]
0x18000da26  mov     eax, [rcx]
0x18000da28  cmp     eax, 4
0x18000da2b  jbe     short loc_18000DA6E
0x18000da2d  lea     rax, aImiditransport; "IMidiTransportConfigurationManager"
0x18000da34  mov     [rbp+arg_10], rax
0x18000da38  mov     [rbp+arg_18], rdi
0x18000da3c  lea     rax, aCmidi2loopback_1; "CMidi2LoopbackMidiTransport::Activate"
0x18000da43  mov     qword ptr [rbp+var_8], rax
0x18000da47  lea     rax, [rbp+arg_10]
0x18000da4b  mov     [rsp+50h+var_20], rax
0x18000da50  lea     rax, [rbp+arg_18]
0x18000da54  mov     [rsp+50h+var_28], rax
0x18000da59  lea     rax, [rbp+var_8]
0x18000da5d  mov     qword ptr [rsp+50h+var_30], rax
0x18000da62  lea     rdx, word_180057DEE
0x18000da69  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x18000da6e  call    ?Current@TransportState@@SAAEAV1@XZ; TransportState::Current(void)
0x18000da73  mov     rdi, [rax+8]
0x18000da77  test    rdi, rdi
0x18000da7a  jz      short loc_18000DA8C
0x18000da7c  mov     rax, [rdi]
0x18000da7f  mov     rcx, rdi
0x18000da82  mov     rax, [rax+8]
0x18000da86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da8b  nop
0x18000da8c  test    rdi, rdi
0x18000da8f  jz      short loc_18000DAA1
0x18000da91  mov     rax, [rdi]
0x18000da94  mov     rcx, rdi
0x18000da97  mov     rax, [rax+10h]
0x18000da9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000daa0  nop
0x18000daa1  test    rdi, rdi
0x18000daa4  jnz     short loc_18000DAB3
0x18000daa6  call    ?Current@TransportState@@SAAEAV1@XZ; TransportState::Current(void)
0x18000daab  mov     rcx, rax; this
0x18000daae  call    ?ConstructConfigurationManager@TransportState@@QEAAJXZ; TransportState::ConstructConfigurationManager(void)
0x18000dab3  call    ?Current@TransportState@@SAAEAV1@XZ; TransportState::Current(void)
0x18000dab8  mov     rdi, [rax+8]
0x18000dabc  test    rdi, rdi
0x18000dabf  jz      short loc_18000DAD1
0x18000dac1  mov     rax, [rdi]
0x18000dac4  mov     rcx, rdi
0x18000dac7  mov     rax, [rax+8]
0x18000dacb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dad0  nop
0x18000dad1  mov     rax, [rdi]
0x18000dad4  mov     r8, rsi
0x18000dad7  mov     rdx, rbx
0x18000dada  mov     rcx, rdi
0x18000dadd  mov     rax, [rax]
0x18000dae0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dae5  mov     ebx, eax
0x18000dae7  mov     rdx, [rdi]
0x18000daea  mov     rcx, rdi
0x18000daed  mov     rax, [rdx+10h]
0x18000daf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000daf6  nop
0x18000daf7  test    ebx, ebx
0x18000daf9  jns     loc_18000DC43
0x18000daff  mov     edx, 4Ch ; 'L'
0x18000db04  jmp     loc_18000D746
0x18000db09  mov     rax, qword ptr cs:_GUID_8d542740_83f8_4a9a_8627_cd6324b6c1f4.Data1
0x18000db10  cmp     rax, [rdx]
0x18000db13  jnz     loc_18000DC47
0x18000db19  mov     rax, qword ptr cs:_GUID_8d542740_83f8_4a9a_8627_cd6324b6c1f4.Data4
0x18000db20  cmp     rax, [rdx+8]
0x18000db24  jnz     loc_18000DC47
0x18000db2a  call    ?Instance@MidiLoopbackMidiTransportTelemetryProvider@@KAPEAV1@XZ; MidiLoopbackMidiTransportTelemetryProvider::Instance(void)
0x18000db2f  mov     rcx, [rax+8]
0x18000db33  mov     eax, [rcx]
0x18000db35  cmp     eax, 4
0x18000db38  jbe     short loc_18000DB7C
0x18000db3a  lea     rax, aImidiservicetr; "IMidiServiceTransportPluginMetadataProv"...
0x18000db41  mov     [rbp+arg_18], rax
0x18000db45  mov     qword ptr [rbp+var_8], rdi
0x18000db49  lea     rax, aCmidi2loopback_1; "CMidi2LoopbackMidiTransport::Activate"
0x18000db50  mov     qword ptr [rbp+var_10], rax
0x18000db54  lea     rax, [rbp+arg_18]
0x18000db58  mov     [rsp+50h+var_20], rax
0x18000db5d  lea     rax, [rbp+var_8]
0x18000db61  mov     [rsp+50h+var_28], rax
0x18000db66  lea     rax, [rbp+var_10]
0x18000db6a  mov     qword ptr [rsp+50h+var_30], rax; int
0x18000db6f  lea     rdx, word_180057DBA
0x18000db76  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x18000db7b  nop
0x18000db7c  mov     [rbp+arg_10], 0
0x18000db84  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000db8b  mov     ecx, 20h ; ' '; unsigned __int64
0x18000db90  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000db95  mov     rdi, rax
0x18000db98  test    rax, rax
0x18000db9b  jnz     short loc_18000DBA4
0x18000db9d  mov     ebx, 8007000Eh
0x18000dba2  jmp     short loc_18000DC08
0x18000dba4  mov     dword ptr [rax+0Ch], 1
0x18000dbab  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIMidiServiceTransportPluginMetadataProvider@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMidiServiceTransportPluginMetadataProvider>::`vftable'
0x18000dbb2  mov     [rdi], rax
0x18000dbb5  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000dbbc  test    rcx, rcx
0x18000dbbf  jz      short loc_18000DBCE
0x18000dbc1  mov     rax, [rcx]
0x18000dbc4  mov     rax, [rax+8]
0x18000dbc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dbcd  nop
0x18000dbce  lea     rax, ??_7CMidi2LoopbackMidiPluginMetadataProvider@@6B@; const CMidi2LoopbackMidiPluginMetadataProvider::`vftable'
0x18000dbd5  mov     [rdi], rax
  ... truncated ...
```
