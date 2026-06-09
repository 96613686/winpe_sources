# CMidi2KSAggregateTransport::Activate(_GUID const &,void * *)

- ea: `0x1800124e0`
- end: `0x180012b0c`
- name: `?Activate@CMidi2KSAggregateTransport@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `1580`
- prototype: `__int64 __fastcall(CMidi2KSAggregateTransport *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1800016dc`
- `0x180005800`
- `0x18000b394`
- `0x18000e0b0`
- `0x18000e200`
- `0x18000e37c`
- `0x1800106c8`
- `0x1800117d8`
- `0x1800124e0`
- `0x18005e010`

## string_xrefs

- `0x1800128da`: `IMidiTransportConfigurationManager`
- `0x1800129e7`: `IMidiServiceTransportPluginMetadataProvider`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CMidi2KSAggregateTransport::Activate(const wchar_t *this, const struct _GUID *a2, void **a3)
{
  unsigned int v6; // ebx
  _DWORD *v8; // rcx
  int v9; // r8d
  int v10; // r9d
  _DWORD *v11; // rax
  _DWORD *v12; // rdi
  _DWORD *v13; // rcx
  int v14; // r8d
  int v15; // r9d
  struct TransportState *v16; // rbx
  __int64 v17; // rbx
  TransportState *v18; // rax
  struct TransportState *v19; // rbx
  __int64 v20; // rbx
  int v21; // edi
  __int64 v22; // rdx
  struct TransportState *v23; // rbx
  __int64 v24; // rbx
  TransportState *v25; // rax
  struct TransportState *v26; // rbx
  __int64 v27; // rbx
  _DWORD *v28; // rcx
  int v29; // r8d
  int v30; // r9d
  struct TransportState *v31; // rax
  __int64 v32; // rbx
  TransportState *v33; // rax
  struct TransportState *v34; // rax
  __int64 v35; // rbx
  _DWORD *v36; // rcx
  int v37; // r8d
  int v38; // r9d
  _DWORD *v39; // rax
  _DWORD *v40; // rdi
  int v41; // [rsp+20h] [rbp-30h]
  int v42[2]; // [rsp+40h] [rbp-10h] BYREF
  int v43[2]; // [rsp+48h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  const wchar_t *v45; // [rsp+80h] [rbp+30h] BYREF
  const wchar_t *v46; // [rsp+88h] [rbp+38h] BYREF

  if ( !a3 )
  {
    v6 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x13,
      (unsigned int)"avcore\\midi2\\transport\\ksaggregatetransport\\midi2.ksaggregatetransport.cpp",
      (const char *)0x80070057LL,
      v41);
    return v6;
  }
  if ( *(_QWORD *)&GUID_b89bbb45_7001_4bea_bbd8_c7cc26e7836c.Data1 == *(_QWORD *)&a2->Data1
    && *(_QWORD *)GUID_b89bbb45_7001_4bea_bbd8_c7cc26e7836c.Data4 == *(_QWORD *)a2->Data4 )
  {
    v8 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
    if ( *v8 > 4u )
    {
      v46 = L"IMidiBidirectional";
      *(_QWORD *)v42 = this;
      *(_QWORD *)v43 = "CMidi2KSAggregateTransport::Activate";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v8,
        (unsigned int)&word_18008863E,
        v9,
        v10,
        (__int64)v43,
        (__int64)v42,
        (__int64)&v46);
    }
    v45 = 0;
    v11 = operator new(0x40u, (const struct std::nothrow_t *)std::nothrow);
    v12 = v11;
    if ( !v11 )
    {
      v6 = -2147024882;
LABEL_13:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x21,
        (unsigned int)"avcore\\midi2\\transport\\ksaggregatetransport\\midi2.ksaggregatetransport.cpp",
        (const char *)v6,
        v41);
      if ( v45 )
        (*(void (__fastcall **)(const wchar_t *))(*(_QWORD *)v45 + 16LL))(v45);
      return v6;
    }
    v11[3] = 1;
    *(_QWORD *)v11 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMidiBidirectional>::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v12 = &CMidi2KSAggregateMidiBidi::`vftable';
    *((_OWORD *)v12 + 1) = 0;
    *((_QWORD *)v12 + 4) = 0;
    *((_QWORD *)v12 + 5) = 7;
    *((_WORD *)v12 + 8) = 0;
    *((_QWORD *)v12 + 6) = 0;
    *((_QWORD *)v12 + 7) = 0;
    v6 = (**(__int64 (__fastcall ***)(_DWORD *, GUID *, const wchar_t **))v12)(
           v12,
           &GUID_b89bbb45_7001_4bea_bbd8_c7cc26e7836c,
           &v45);
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v12 + 16LL))(v12);
    if ( (v6 & 0x80000000) != 0 )
      goto LABEL_13;
    *a3 = (void *)v45;
    return 0;
  }
  if ( *(_QWORD *)&GUID_badff6d2_0e3c_4009_a473_6ba82c008662.Data1 == *(_QWORD *)&a2->Data1
    && *(_QWORD *)GUID_badff6d2_0e3c_4009_a473_6ba82c008662.Data4 == *(_QWORD *)a2->Data4 )
  {
    v13 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
    if ( *v13 > 4u )
    {
      v45 = L"IMidiEndpointManager";
      v46 = this;
      *(_QWORD *)v43 = "CMidi2KSAggregateTransport::Activate";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v13,
        (unsigned int)word_18008860A,
        v14,
        v15,
        (__int64)v43,
        (__int64)&v46,
        (__int64)&v45);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix>::GetImpl'::`2'::impl) )
    {
      v16 = TransportState::Current();
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix>::GetImpl'::`2'::impl) )
      {
        v17 = *((_QWORD *)v16 + 1);
        if ( v17 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 8LL))(v17);
      }
      else
      {
        v17 = 0;
      }
      if ( v17 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      }
      else
      {
        v18 = TransportState::Current();
        TransportState::ConstructEndpointManager(v18);
      }
      v19 = TransportState::Current();
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix>::GetImpl'::`2'::impl) )
      {
        v20 = *((_QWORD *)v19 + 1);
        if ( v20 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 8LL))(v20);
      }
      else
      {
        v20 = 0;
      }
      v21 = (**(__int64 (__fastcall ***)(__int64, const struct _GUID *, void **))v20)(v20, a2, a3);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
      if ( v21 < 0 )
      {
        v22 = 55;
LABEL_37:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v22,
          (unsigned int)"avcore\\midi2\\transport\\ksaggregatetransport\\midi2.ksaggregatetransport.cpp",
          (const char *)(unsigned int)v21,
          v41);
        return (unsigned int)v21;
      }
    }
    else
    {
      v23 = TransportState::Current();
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix>::GetImpl'::`2'::impl) )
      {
        v24 = 0;
      }
      else
      {
        v24 = *(_QWORD *)v23;
        if ( v24 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 8LL))(v24);
      }
      if ( v24 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
      }
      else
      {
        v25 = TransportState::Current();
        TransportState::ConstructEndpointManager(v25);
      }
      v26 = TransportState::Current();
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix>::GetImpl'::`2'::impl) )
      {
        v27 = 0;
      }
      else
      {
        v27 = *(_QWORD *)v26;
        if ( v27 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 8LL))(v27);
      }
      v21 = (**(__int64 (__fastcall ***)(__int64, const struct _GUID *, void **))v27)(v27, a2, a3);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
      if ( v21 < 0 )
      {
        v22 = 65;
        goto LABEL_37;
      }
    }
    return 0;
  }
  if ( *(_QWORD *)&GUID_f19dd642_1809_4497_9eee_f230b11bd6fb.Data1 == *(_QWORD *)&a2->Data1
    && *(_QWORD *)GUID_f19dd642_1809_4497_9eee_f230b11bd6fb.Data4 == *(_QWORD *)a2->Data4 )
  {
    v28 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
    if ( *v28 > 4u )
    {
      v45 = L"IMidiTransportConfigurationManager";
      v46 = this;
      *(_QWORD *)v43 = "CMidi2KSAggregateTransport::Activate";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v28,
        (unsigned int)&word_1800885D6,
        v29,
        v30,
        (__int64)v43,
        (__int64)&v46,
        (__int64)&v45);
    }
    v31 = TransportState::Current();
    v32 = *((_QWORD *)v31 + 2);
    if ( v32 )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v32 + 8LL))(*((_QWORD *)v31 + 2));
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    }
    else
    {
      v33 = TransportState::Current();
      TransportState::ConstructConfigurationManager(v33);
    }
    v34 = TransportState::Current();
    v35 = *((_QWORD *)v34 + 2);
    if ( v35 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v35 + 8LL))(*((_QWORD *)v34 + 2));
    v21 = (**(__int64 (__fastcall ***)(__int64, const struct _GUID *, void **))v35)(v35, a2, a3);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    if ( v21 < 0 )
    {
      v22 = 88;
      goto LABEL_37;
    }
    return 0;
  }
  if ( *(_QWORD *)&GUID_8d542740_83f8_4a9a_8627_cd6324b6c1f4.Data1 == *(_QWORD *)&a2->Data1
    && *(_QWORD *)GUID_8d542740_83f8_4a9a_8627_cd6324b6c1f4.Data4 == *(_QWORD *)a2->Data4 )
  {
    v36 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
    if ( *v36 > 4u )
    {
      v46 = L"IMidiServiceTransportPluginMetadataProvider";
      *(_QWORD *)v43 = this;
      *(_QWORD *)v42 = "CMidi2KSAggregateTransport::Activate";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v36,
        (unsigned int)word_1800885A2,
        v37,
        v38,
        (__int64)v42,
        (__int64)v43,
        (__int64)&v46);
    }
    v45 = 0;
    v39 = operator new(0x10u, (const struct std::nothrow_t *)std::nothrow);
    v40 = v39;
    if ( v39 )
    {
      v39[3] = 1;
      *(_QWORD *)v39 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMidiServiceTransportPluginMetadataProvider>::`vftable';
      if ( Microsoft::WRL::Details::ModuleBase::module_ )
        (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                             + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
      *(_QWORD *)v40 = &CMidi2KSAggregateMidiPluginMetadataProvider::`vftable';
      v6 = ((__int64 (__fastcall *)(_DWORD *, GUID *, const wchar_t **))CMidi2KSAggregateMidiPluginMetadataProvider::`vftable')(
             v40,
             &GUID_8d542740_83f8_4a9a_8627_cd6324b6c1f4,
             &v45);
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v40 + 16LL))(v40);
      if ( (v6 & 0x80000000) == 0 )
      {
        *a3 = (void *)v45;
        return 0;
      }
    }
    else
    {
      v6 = -2147024882;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x67,
      (unsigned int)"avcore\\midi2\\transport\\ksaggregatetransport\\midi2.ksaggregatetransport.cpp",
      (const char *)v6,
      v41);
    if ( v45 )
      (*(void (__fastcall **)(const wchar_t *))(*(_QWORD *)v45 + 16LL))(v45);
    return v6;
  }
  return 2147500034LL;
}

```

## disassembly

```asm
0x1800124e0  mov     [rsp-18h+arg_0], rbx
0x1800124e5  mov     [rsp-18h+arg_8], rsi
0x1800124ea  push    rbp
0x1800124eb  push    rdi
0x1800124ec  push    r15
0x1800124ee  mov     rbp, rsp
0x1800124f1  sub     rsp, 50h
0x1800124f5  mov     rsi, r8
0x1800124f8  mov     rdi, rdx
0x1800124fb  mov     rbx, rcx
0x1800124fe  test    r8, r8
0x180012501  jnz     short loc_180012525
0x180012503  mov     rcx, [rbp+18h]; this
0x180012507  mov     ebx, 80070057h
0x18001250c  mov     r9d, ebx; char *
0x18001250f  lea     r8, aAvcoreMidi2Tra_8; "avcore\\midi2\\transport\\ksaggregatetr"...
0x180012516  lea     edx, [rsi+13h]; void *
0x180012519  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001251e  mov     eax, ebx
0x180012520  jmp     loc_180012AF9
0x180012525  mov     rax, qword ptr cs:_GUID_b89bbb45_7001_4bea_bbd8_c7cc26e7836c.Data1
0x18001252c  cmp     rax, [rdx]
0x18001252f  jnz     loc_18001268B
0x180012535  mov     rax, qword ptr cs:_GUID_b89bbb45_7001_4bea_bbd8_c7cc26e7836c.Data4
0x18001253c  cmp     rax, [rdx+8]
0x180012540  jnz     loc_18001268B
0x180012546  call    ?Instance@MidiKSAggregateTransportTelemetryProvider@@KAPEAV1@XZ; MidiKSAggregateTransportTelemetryProvider::Instance(void)
0x18001254b  mov     rcx, [rax+8]
0x18001254f  mov     eax, [rcx]
0x180012551  cmp     eax, 4
0x180012554  jbe     short loc_180012598
0x180012556  lea     rax, aImidibidirecti; "IMidiBidirectional"
0x18001255d  mov     [rbp+arg_18], rax
0x180012561  mov     qword ptr [rbp+var_10], rbx
0x180012565  lea     rax, aCmidi2ksaggreg_13; "CMidi2KSAggregateTransport::Activate"
0x18001256c  mov     qword ptr [rbp+var_8], rax
0x180012570  lea     rax, [rbp+arg_18]
0x180012574  mov     [rsp+50h+var_20], rax
0x180012579  lea     rax, [rbp+var_10]
0x18001257d  mov     [rsp+50h+var_28], rax
0x180012582  lea     rax, [rbp+var_8]
0x180012586  mov     qword ptr [rsp+50h+var_30], rax; int
0x18001258b  lea     rdx, word_18008863E
0x180012592  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x180012597  nop
0x180012598  mov     [rbp+arg_10], 0
0x1800125a0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800125a7  mov     ecx, 40h ; '@'; unsigned __int64
0x1800125ac  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800125b1  mov     rdi, rax
0x1800125b4  test    rax, rax
0x1800125b7  jnz     short loc_1800125C3
0x1800125b9  mov     ebx, 8007000Eh
0x1800125be  jmp     loc_18001264B
0x1800125c3  mov     dword ptr [rax+0Ch], 1
0x1800125ca  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIMidiBidirectional@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMidiBidirectional>::`vftable'
0x1800125d1  mov     [rdi], rax
0x1800125d4  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800125db  test    rcx, rcx
0x1800125de  jz      short loc_1800125ED
0x1800125e0  mov     rax, [rcx]
0x1800125e3  mov     rax, [rax+8]
0x1800125e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800125ec  nop
0x1800125ed  lea     rax, ??_7CMidi2KSAggregateMidiBidi@@6B@; const CMidi2KSAggregateMidiBidi::`vftable'
0x1800125f4  mov     [rdi], rax
0x1800125f7  xorps   xmm0, xmm0
0x1800125fa  movups  xmmword ptr [rdi+10h], xmm0
0x1800125fe  mov     qword ptr [rdi+20h], 0
0x180012606  mov     qword ptr [rdi+28h], 7
0x18001260e  xor     eax, eax
0x180012610  mov     [rdi+10h], ax
0x180012614  mov     [rdi+30h], rax
0x180012618  mov     [rdi+38h], rax
0x18001261c  mov     rax, [rdi]
0x18001261f  lea     r8, [rbp+arg_10]
0x180012623  lea     rdx, _GUID_b89bbb45_7001_4bea_bbd8_c7cc26e7836c
0x18001262a  mov     rcx, rdi
0x18001262d  mov     rax, [rax]
0x180012630  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012635  mov     ebx, eax
0x180012637  mov     rax, [rdi]
0x18001263a  mov     rcx, rdi
0x18001263d  mov     rax, [rax+10h]
0x180012641  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012646  nop
0x180012647  test    ebx, ebx
0x180012649  jns     short loc_18001267F
0x18001264b  mov     rcx, [rbp+18h]; this
0x18001264f  mov     r9d, ebx; char *
0x180012652  lea     r8, aAvcoreMidi2Tra_8; "avcore\\midi2\\transport\\ksaggregatetr"...
0x180012659  mov     edx, 21h ; '!'; void *
0x18001265e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012663  nop
0x180012664  mov     rcx, [rbp+arg_10]
0x180012668  test    rcx, rcx
0x18001266b  jz      short loc_18001267A
0x18001266d  mov     rax, [rcx]
0x180012670  mov     rax, [rax+10h]
0x180012674  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012679  nop
0x18001267a  jmp     loc_18001251E
0x18001267f  mov     rax, [rbp+arg_10]
0x180012683  mov     [rsi], rax
0x180012686  jmp     loc_180012AF0
0x18001268b  mov     rax, qword ptr cs:_GUID_badff6d2_0e3c_4009_a473_6ba82c008662.Data1
0x180012692  cmp     rax, [rdx]
0x180012695  jnz     loc_1800128A9
0x18001269b  mov     rax, qword ptr cs:_GUID_badff6d2_0e3c_4009_a473_6ba82c008662.Data4
0x1800126a2  cmp     rax, [rdx+8]
0x1800126a6  jnz     loc_1800128A9
0x1800126ac  call    ?Instance@MidiKSAggregateTransportTelemetryProvider@@KAPEAV1@XZ; MidiKSAggregateTransportTelemetryProvider::Instance(void)
0x1800126b1  mov     rcx, [rax+8]
0x1800126b5  mov     eax, [rcx]
0x1800126b7  cmp     eax, 4
0x1800126ba  jbe     short loc_1800126FD
0x1800126bc  lea     rax, aImidiendpointm; "IMidiEndpointManager"
0x1800126c3  mov     [rbp+arg_10], rax
0x1800126c7  mov     [rbp+arg_18], rbx
0x1800126cb  lea     rax, aCmidi2ksaggreg_13; "CMidi2KSAggregateTransport::Activate"
0x1800126d2  mov     qword ptr [rbp+var_8], rax
0x1800126d6  lea     rax, [rbp+arg_10]
0x1800126da  mov     [rsp+50h+var_20], rax
0x1800126df  lea     rax, [rbp+arg_18]
0x1800126e3  mov     [rsp+50h+var_28], rax
0x1800126e8  lea     rax, [rbp+var_8]
0x1800126ec  mov     qword ptr [rsp+50h+var_30], rax; int
0x1800126f1  lea     rdx, word_18008860A
0x1800126f8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x1800126fd  lea     r15, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix> `wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix>::GetImpl(void)'::`2'::impl
0x180012704  mov     rcx, r15
0x180012707  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix>::__private_IsEnabled(void)
0x18001270c  test    al, al
0x18001270e  jz      loc_1800127EA
0x180012714  call    ?Current@TransportState@@SAAEAV1@XZ; TransportState::Current(void)
0x180012719  mov     rbx, rax
0x18001271c  mov     rcx, r15
0x18001271f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix>::__private_IsEnabled(void)
0x180012724  test    al, al
0x180012726  jz      short loc_180012743
0x180012728  mov     rbx, [rbx+8]
0x18001272c  test    rbx, rbx
0x18001272f  jz      short loc_180012741
0x180012731  mov     rax, [rbx]
0x180012734  mov     rcx, rbx
0x180012737  mov     rax, [rax+8]
0x18001273b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012740  nop
0x180012741  jmp     short loc_180012745
0x180012743  xor     ebx, ebx
0x180012745  test    rbx, rbx
0x180012748  jz      short loc_18001275A
0x18001274a  mov     rax, [rbx]
0x18001274d  mov     rcx, rbx
0x180012750  mov     rax, [rax+10h]
0x180012754  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012759  nop
0x18001275a  test    rbx, rbx
0x18001275d  jnz     short loc_18001276C
0x18001275f  call    ?Current@TransportState@@SAAEAV1@XZ; TransportState::Current(void)
0x180012764  mov     rcx, rax; this
0x180012767  call    ?ConstructEndpointManager@TransportState@@QEAAJXZ; TransportState::ConstructEndpointManager(void)
0x18001276c  call    ?Current@TransportState@@SAAEAV1@XZ; TransportState::Current(void)
0x180012771  mov     rbx, rax
0x180012774  mov     rcx, r15
0x180012777  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix>::__private_IsEnabled(void)
0x18001277c  test    al, al
0x18001277e  jz      short loc_18001279B
0x180012780  mov     rbx, [rbx+8]
0x180012784  test    rbx, rbx
0x180012787  jz      short loc_180012799
0x180012789  mov     rax, [rbx]
0x18001278c  mov     rcx, rbx
0x18001278f  mov     rax, [rax+8]
0x180012793  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012798  nop
0x180012799  jmp     short loc_18001279D
0x18001279b  xor     ebx, ebx
0x18001279d  mov     rax, [rbx]
0x1800127a0  mov     r8, rsi
0x1800127a3  mov     rdx, rdi
0x1800127a6  mov     rcx, rbx
0x1800127a9  mov     rax, [rax]
0x1800127ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800127b1  mov     edi, eax
0x1800127b3  mov     rcx, [rbx]
0x1800127b6  mov     rax, [rcx+10h]
0x1800127ba  mov     rcx, rbx
0x1800127bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800127c2  nop
0x1800127c3  test    edi, edi
0x1800127c5  jns     loc_180012AF0
0x1800127cb  mov     edx, 37h ; '7'; void *
0x1800127d0  mov     rcx, [rbp+18h]; this
0x1800127d4  mov     r9d, edi; char *
0x1800127d7  lea     r8, aAvcoreMidi2Tra_8; "avcore\\midi2\\transport\\ksaggregatetr"...
0x1800127de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800127e3  mov     eax, edi
0x1800127e5  jmp     loc_180012AF9
0x1800127ea  call    ?Current@TransportState@@SAAEAV1@XZ; TransportState::Current(void)
0x1800127ef  mov     rbx, rax
0x1800127f2  mov     rcx, r15
0x1800127f5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix>::__private_IsEnabled(void)
0x1800127fa  test    al, al
0x1800127fc  jz      short loc_180012802
0x1800127fe  xor     ebx, ebx
0x180012800  jmp     short loc_18001281A
0x180012802  mov     rbx, [rbx]
0x180012805  test    rbx, rbx
0x180012808  jz      short loc_18001281A
0x18001280a  mov     rax, [rbx]
0x18001280d  mov     rcx, rbx
0x180012810  mov     rax, [rax+8]
0x180012814  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012819  nop
0x18001281a  test    rbx, rbx
0x18001281d  jz      short loc_18001282F
0x18001281f  mov     rax, [rbx]
0x180012822  mov     rcx, rbx
0x180012825  mov     rax, [rax+10h]
0x180012829  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001282e  nop
0x18001282f  test    rbx, rbx
0x180012832  jnz     short loc_180012841
0x180012834  call    ?Current@TransportState@@SAAEAV1@XZ; TransportState::Current(void)
0x180012839  mov     rcx, rax; this
0x18001283c  call    ?ConstructEndpointManager@TransportState@@QEAAJXZ; TransportState::ConstructEndpointManager(void)
0x180012841  call    ?Current@TransportState@@SAAEAV1@XZ; TransportState::Current(void)
0x180012846  mov     rbx, rax
0x180012849  mov     rcx, r15
0x18001284c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix>::__private_IsEnabled(void)
0x180012851  test    al, al
0x180012853  jz      short loc_180012859
0x180012855  xor     ebx, ebx
0x180012857  jmp     short loc_180012871
0x180012859  mov     rbx, [rbx]
0x18001285c  test    rbx, rbx
0x18001285f  jz      short loc_180012871
0x180012861  mov     rax, [rbx]
0x180012864  mov     rcx, rbx
0x180012867  mov     rax, [rax+8]
0x18001286b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012870  nop
0x180012871  mov     rax, [rbx]
0x180012874  mov     r8, rsi
0x180012877  mov     rdx, rdi
0x18001287a  mov     rcx, rbx
0x18001287d  mov     rax, [rax]
0x180012880  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012885  mov     edi, eax
0x180012887  mov     rcx, [rbx]
0x18001288a  mov     rax, [rcx+10h]
0x18001288e  mov     rcx, rbx
0x180012891  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012896  nop
0x180012897  test    edi, edi
0x180012899  jns     loc_180012AF0
0x18001289f  mov     edx, 41h ; 'A'
0x1800128a4  jmp     loc_1800127D0
0x1800128a9  mov     rax, qword ptr cs:_GUID_f19dd642_1809_4497_9eee_f230b11bd6fb.Data1
0x1800128b0  cmp     rax, [rdx]
0x1800128b3  jnz     loc_1800129B6
0x1800128b9  mov     rax, qword ptr cs:_GUID_f19dd642_1809_4497_9eee_f230b11bd6fb.Data4
0x1800128c0  cmp     rax, [rdx+8]
0x1800128c4  jnz     loc_1800129B6
0x1800128ca  call    ?Instance@MidiKSAggregateTransportTelemetryProvider@@KAPEAV1@XZ; MidiKSAggregateTransportTelemetryProvider::Instance(void)
0x1800128cf  mov     rcx, [rax+8]
0x1800128d3  mov     eax, [rcx]
0x1800128d5  cmp     eax, 4
0x1800128d8  jbe     short loc_18001291B
0x1800128da  lea     rax, aImiditransport; "IMidiTransportConfigurationManager"
0x1800128e1  mov     [rbp+arg_10], rax
0x1800128e5  mov     [rbp+arg_18], rbx
0x1800128e9  lea     rax, aCmidi2ksaggreg_13; "CMidi2KSAggregateTransport::Activate"
0x1800128f0  mov     qword ptr [rbp+var_8], rax
0x1800128f4  lea     rax, [rbp+arg_10]
0x1800128f8  mov     [rsp+50h+var_20], rax
0x1800128fd  lea     rax, [rbp+arg_18]
0x180012901  mov     [rsp+50h+var_28], rax
0x180012906  lea     rax, [rbp+var_8]
0x18001290a  mov     qword ptr [rsp+50h+var_30], rax
0x18001290f  lea     rdx, word_1800885D6
0x180012916  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x18001291b  call    ?Current@TransportState@@SAAEAV1@XZ; TransportState::Current(void)
0x180012920  mov     rbx, [rax+10h]
0x180012924  test    rbx, rbx
0x180012927  jz      short loc_180012939
0x180012929  mov     rax, [rbx]
0x18001292c  mov     rcx, rbx
0x18001292f  mov     rax, [rax+8]
0x180012933  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012938  nop
0x180012939  test    rbx, rbx
0x18001293c  jz      short loc_18001294E
0x18001293e  mov     rax, [rbx]
0x180012941  mov     rcx, rbx
0x180012944  mov     rax, [rax+10h]
0x180012948  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001294d  nop
0x18001294e  test    rbx, rbx
  ... truncated ...
```
