# CMidi2VirtualMidiTransport::Activate(_GUID const &,void * *)

- ea: `0x18000c140`
- end: `0x18000c6d0`
- name: `?Activate@CMidi2VirtualMidiTransport@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `1424`
- prototype: `__int64 __fastcall(CMidi2VirtualMidiTransport *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800016dc`
- `0x180003d6c`
- `0x180009784`
- `0x18000b5f8`
- `0x18000c140`
- `0x18001abd4`
- `0x18001acb8`
- `0x18001adc4`
- `0x180021010`

## string_xrefs

- `0x18000c43c`: `IMidiTransportConfigurationManager`
- `0x18000c549`: `IMidiServiceTransportPluginMetadataProvider`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CMidi2VirtualMidiTransport::Activate(const wchar_t *this, const struct _GUID *a2, void **a3)
{
  int v6; // ebx
  __int64 v7; // rdx
  _DWORD *v8; // rcx
  int v9; // r8d
  int v10; // r9d
  _DWORD *v11; // rax
  _DWORD *v12; // rdi
  _DWORD *v13; // rcx
  int v14; // r8d
  int v15; // r9d
  struct TransportState *v16; // rax
  __int64 v17; // rdi
  TransportState *v18; // rax
  struct TransportState *v19; // rax
  __int64 v20; // rdi
  _DWORD *v21; // rcx
  int v22; // r8d
  int v23; // r9d
  struct TransportState *v24; // rax
  __int64 v25; // rdi
  TransportState *v26; // rax
  struct TransportState *v27; // rax
  __int64 v28; // rdi
  _DWORD *v29; // rcx
  int v30; // r8d
  int v31; // r9d
  _DWORD *v32; // rax
  _DWORD *v33; // rdi
  _DWORD *v35; // rcx
  int v36; // r8d
  int v37; // r9d
  int v38; // [rsp+20h] [rbp-30h]
  int v39[2]; // [rsp+40h] [rbp-10h] BYREF
  int v40[2]; // [rsp+48h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  const wchar_t *v42; // [rsp+80h] [rbp+30h] BYREF
  const wchar_t *v43; // [rsp+88h] [rbp+38h] BYREF

  if ( a3 )
  {
    if ( *(_QWORD *)&GUID_b89bbb45_7001_4bea_bbd8_c7cc26e7836c.Data1 == *(_QWORD *)&a2->Data1
      && *(_QWORD *)GUID_b89bbb45_7001_4bea_bbd8_c7cc26e7836c.Data4 == *(_QWORD *)a2->Data4 )
    {
      v8 = (_DWORD *)*((_QWORD *)MidiVirtualMidiTransportTelemetryProvider::Instance() + 1);
      if ( *v8 > 4u )
      {
        v43 = L"IMidiBidirectional";
        *(_QWORD *)v39 = this;
        *(_QWORD *)v40 = "CMidi2VirtualMidiTransport::Activate";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
          (_DWORD)v8,
          (unsigned int)byte_18002663B,
          v9,
          v10,
          (__int64)v40,
          (__int64)v39,
          (__int64)&v43);
      }
      v42 = 0;
      v11 = operator new(0x70u, (const struct std::nothrow_t *)std::nothrow);
      v12 = v11;
      if ( !v11 )
      {
        v6 = -2147024882;
LABEL_12:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x22,
          (unsigned int)"avcore\\midi2\\transport\\virtualmiditransport\\midi2.virtualmiditransport.cpp",
          (const char *)(unsigned int)v6,
          v38);
        if ( v42 )
          (*(void (__fastcall **)(const wchar_t *))(*(_QWORD *)v42 + 16LL))(v42);
        return (unsigned int)v6;
      }
      v11[5] = 1;
      *(_QWORD *)v11 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMidiBidirectional,IMidiCallback>::`vftable'{for `IMidiBidirectional'};
      *((_QWORD *)v11 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMidiBidirectional,IMidiCallback>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IMidiCallback>'};
      if ( Microsoft::WRL::Details::ModuleBase::module_ )
        (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                             + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
      *(_QWORD *)v12 = &CMidi2VirtualMidiBidi::`vftable'{for `IMidiBidirectional'};
      *((_QWORD *)v12 + 1) = &CMidi2VirtualMidiBidi::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IMidiCallback>'};
      *((_QWORD *)v12 + 3) = 0;
      *((_QWORD *)v12 + 4) = 0;
      *((_QWORD *)v12 + 5) = 0;
      *(_OWORD *)(v12 + 14) = 0;
      *((_QWORD *)v12 + 9) = 0;
      *((_QWORD *)v12 + 10) = 7;
      *((_WORD *)v12 + 28) = 0;
      *(_OWORD *)(v12 + 22) = 0;
      *((_BYTE *)v12 + 104) = 0;
      v6 = (**(__int64 (__fastcall ***)(_DWORD *, GUID *, const wchar_t **))v12)(
             v12,
             &GUID_b89bbb45_7001_4bea_bbd8_c7cc26e7836c,
             &v42);
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v12 + 16LL))(v12);
      if ( v6 < 0 )
        goto LABEL_12;
      *a3 = (void *)v42;
    }
    else if ( *(_QWORD *)&GUID_badff6d2_0e3c_4009_a473_6ba82c008662.Data1 == *(_QWORD *)&a2->Data1
           && *(_QWORD *)GUID_badff6d2_0e3c_4009_a473_6ba82c008662.Data4 == *(_QWORD *)a2->Data4 )
    {
      v13 = (_DWORD *)*((_QWORD *)MidiVirtualMidiTransportTelemetryProvider::Instance() + 1);
      if ( *v13 > 4u )
      {
        v42 = L"IMidiEndpointManager";
        v43 = this;
        *(_QWORD *)v40 = "CMidi2VirtualMidiTransport::Activate";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
          (_DWORD)v13,
          (unsigned int)&byte_180026607,
          v14,
          v15,
          (__int64)v40,
          (__int64)&v43,
          (__int64)&v42);
      }
      v16 = TransportState::Current();
      v17 = *((_QWORD *)v16 + 2);
      if ( v17 )
      {
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v17 + 8LL))(*((_QWORD *)v16 + 2));
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      }
      else
      {
        v18 = TransportState::Current();
        TransportState::ConstructEndpointManager(v18);
      }
      v19 = TransportState::Current();
      v20 = *((_QWORD *)v19 + 2);
      if ( v20 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v20 + 8LL))(*((_QWORD *)v19 + 2));
      v6 = (**(__int64 (__fastcall ***)(__int64, const struct _GUID *, void **))v20)(v20, a2, a3);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
      if ( v6 < 0 )
      {
        v7 = 56;
        goto LABEL_55;
      }
    }
    else
    {
      if ( *(_QWORD *)&GUID_f19dd642_1809_4497_9eee_f230b11bd6fb.Data1 != *(_QWORD *)&a2->Data1
        || *(_QWORD *)GUID_f19dd642_1809_4497_9eee_f230b11bd6fb.Data4 != *(_QWORD *)a2->Data4 )
      {
        if ( *(_QWORD *)&GUID_8d542740_83f8_4a9a_8627_cd6324b6c1f4.Data1 != *(_QWORD *)&a2->Data1
          || *(_QWORD *)GUID_8d542740_83f8_4a9a_8627_cd6324b6c1f4.Data4 != *(_QWORD *)a2->Data4 )
        {
          v35 = (_DWORD *)*((_QWORD *)MidiVirtualMidiTransportTelemetryProvider::Instance() + 1);
          if ( *v35 > 2u )
          {
            v42 = L"(Unknown)";
            v43 = this;
            *(_QWORD *)v40 = "CMidi2VirtualMidiTransport::Activate";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
              (_DWORD)v35,
              (unsigned int)word_18002656A,
              v36,
              v37,
              (__int64)v40,
              (__int64)&v43,
              (__int64)&v42);
          }
          v6 = -2147467262;
          v7 = 109;
          goto LABEL_55;
        }
        v29 = (_DWORD *)*((_QWORD *)MidiVirtualMidiTransportTelemetryProvider::Instance() + 1);
        if ( *v29 > 4u )
        {
          v43 = L"IMidiServiceTransportPluginMetadataProvider";
          *(_QWORD *)v40 = this;
          *(_QWORD *)v39 = "CMidi2VirtualMidiTransport::Activate";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
            (_DWORD)v29,
            (unsigned int)&byte_18002659F,
            v30,
            v31,
            (__int64)v39,
            (__int64)v40,
            (__int64)&v43);
        }
        v42 = 0;
        v32 = operator new(0x20u, (const struct std::nothrow_t *)std::nothrow);
        v33 = v32;
        if ( v32 )
        {
          v32[3] = 1;
          *(_QWORD *)v32 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMidiServiceTransportPluginMetadataProvider>::`vftable';
          if ( Microsoft::WRL::Details::ModuleBase::module_ )
            (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                                 + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
          *(_QWORD *)v33 = &CMidi2VirtualMidiPluginMetadataProvider::`vftable';
          v6 = ((__int64 (__fastcall *)(_DWORD *, GUID *, const wchar_t **))CMidi2VirtualMidiPluginMetadataProvider::`vftable')(
                 v33,
                 &GUID_8d542740_83f8_4a9a_8627_cd6324b6c1f4,
                 &v42);
          (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v33 + 16LL))(v33);
          if ( v6 >= 0 )
          {
            *a3 = (void *)v42;
            return 0;
          }
        }
        else
        {
          v6 = -2147024882;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5D,
          (unsigned int)"avcore\\midi2\\transport\\virtualmiditransport\\midi2.virtualmiditransport.cpp",
          (const char *)(unsigned int)v6,
          v38);
        if ( v42 )
          (*(void (__fastcall **)(const wchar_t *))(*(_QWORD *)v42 + 16LL))(v42);
        return (unsigned int)v6;
      }
      v21 = (_DWORD *)*((_QWORD *)MidiVirtualMidiTransportTelemetryProvider::Instance() + 1);
      if ( *v21 > 4u )
      {
        v42 = L"IMidiTransportConfigurationManager";
        v43 = this;
        *(_QWORD *)v40 = "CMidi2VirtualMidiTransport::Activate";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
          (_DWORD)v21,
          (unsigned int)byte_1800265D3,
          v22,
          v23,
          (__int64)v40,
          (__int64)&v43,
          (__int64)&v42);
      }
      v24 = TransportState::Current();
      v25 = *((_QWORD *)v24 + 3);
      if ( v25 )
      {
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v25 + 8LL))(*((_QWORD *)v24 + 3));
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
      }
      else
      {
        v26 = TransportState::Current();
        TransportState::ConstructConfigurationManager(v26);
      }
      v27 = TransportState::Current();
      v28 = *((_QWORD *)v27 + 3);
      if ( v28 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v28 + 8LL))(*((_QWORD *)v27 + 3));
      v6 = (**(__int64 (__fastcall ***)(__int64, const struct _GUID *, void **))v28)(v28, a2, a3);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
      if ( v6 < 0 )
      {
        v7 = 77;
        goto LABEL_55;
      }
    }
    return 0;
  }
  v6 = -2147024809;
  v7 = 19;
LABEL_55:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v7,
    (unsigned int)"avcore\\midi2\\transport\\virtualmiditransport\\midi2.virtualmiditransport.cpp",
    (const char *)(unsigned int)v6,
    v38);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000c140  mov     [rsp-18h+arg_0], rbx
0x18000c145  push    rbp
0x18000c146  push    rsi
0x18000c147  push    rdi
0x18000c148  mov     rbp, rsp
0x18000c14b  sub     rsp, 50h
0x18000c14f  mov     rsi, r8
0x18000c152  mov     rbx, rdx
0x18000c155  mov     rdi, rcx
0x18000c158  test    r8, r8
0x18000c15b  jnz     short loc_18000C16B
0x18000c15d  mov     ebx, 80070057h
0x18000c162  lea     edx, [r8+13h]
0x18000c166  jmp     loc_18000C6AE
0x18000c16b  mov     rax, qword ptr cs:_GUID_b89bbb45_7001_4bea_bbd8_c7cc26e7836c.Data1
0x18000c172  cmp     rax, [rdx]
0x18000c175  jnz     loc_18000C2FE
0x18000c17b  mov     rax, qword ptr cs:_GUID_b89bbb45_7001_4bea_bbd8_c7cc26e7836c.Data4
0x18000c182  cmp     rax, [rdx+8]
0x18000c186  jnz     loc_18000C2FE
0x18000c18c  call    ?Instance@MidiVirtualMidiTransportTelemetryProvider@@KAPEAV1@XZ; MidiVirtualMidiTransportTelemetryProvider::Instance(void)
0x18000c191  mov     rcx, [rax+8]
0x18000c195  mov     eax, [rcx]
0x18000c197  cmp     eax, 4
0x18000c19a  jbe     short loc_18000C1DE
0x18000c19c  lea     rax, aImidibidirecti; "IMidiBidirectional"
0x18000c1a3  mov     [rbp+arg_18], rax
0x18000c1a7  mov     qword ptr [rbp+var_10], rdi
0x18000c1ab  lea     rax, aCmidi2virtualm_2; "CMidi2VirtualMidiTransport::Activate"
0x18000c1b2  mov     qword ptr [rbp+var_8], rax
0x18000c1b6  lea     rax, [rbp+arg_18]
0x18000c1ba  mov     [rsp+50h+var_20], rax
0x18000c1bf  lea     rax, [rbp+var_10]
0x18000c1c3  mov     [rsp+50h+var_28], rax
0x18000c1c8  lea     rax, [rbp+var_8]
0x18000c1cc  mov     qword ptr [rsp+50h+var_30], rax; int
0x18000c1d1  lea     rdx, byte_18002663B
0x18000c1d8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x18000c1dd  nop
0x18000c1de  mov     [rbp+arg_10], 0
0x18000c1e6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000c1ed  mov     ecx, 70h ; 'p'; unsigned __int64
0x18000c1f2  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000c1f7  mov     rdi, rax
0x18000c1fa  test    rax, rax
0x18000c1fd  jnz     short loc_18000C209
0x18000c1ff  mov     ebx, 8007000Eh
0x18000c204  jmp     loc_18000C2BE
0x18000c209  mov     dword ptr [rax+14h], 1
0x18000c210  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIMidiBidirectional@@UIMidiCallback@@@WRL@Microsoft@@6BIMidiBidirectional@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMidiBidirectional,IMidiCallback>::`vftable'{for `IMidiBidirectional'}
0x18000c217  mov     [rdi], rax
0x18000c21a  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIMidiBidirectional@@UIMidiCallback@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIMidiCallback@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMidiBidirectional,IMidiCallback>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IMidiCallback>'}
0x18000c221  mov     [rdi+8], rax
0x18000c225  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000c22c  test    rcx, rcx
0x18000c22f  jz      short loc_18000C23E
0x18000c231  mov     rax, [rcx]
0x18000c234  mov     rax, [rax+8]
0x18000c238  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c23d  nop
0x18000c23e  lea     rax, ??_7CMidi2VirtualMidiBidi@@6BIMidiBidirectional@@@; const CMidi2VirtualMidiBidi::`vftable'{for `IMidiBidirectional'}
0x18000c245  mov     [rdi], rax
0x18000c248  lea     rax, ??_7CMidi2VirtualMidiBidi@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIMidiCallback@@@Details@WRL@Microsoft@@@; const CMidi2VirtualMidiBidi::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IMidiCallback>'}
0x18000c24f  mov     [rdi+8], rax
0x18000c253  mov     qword ptr [rdi+18h], 0
0x18000c25b  mov     qword ptr [rdi+20h], 0
0x18000c263  mov     qword ptr [rdi+28h], 0
0x18000c26b  xorps   xmm0, xmm0
0x18000c26e  movups  xmmword ptr [rdi+38h], xmm0
0x18000c272  mov     qword ptr [rdi+48h], 0
0x18000c27a  mov     qword ptr [rdi+50h], 7
0x18000c282  xor     eax, eax
0x18000c284  mov     [rdi+38h], ax
0x18000c288  movups  xmmword ptr [rdi+58h], xmm0
0x18000c28c  mov     [rdi+68h], al
0x18000c28f  mov     rax, [rdi]
0x18000c292  lea     r8, [rbp+arg_10]
0x18000c296  lea     rdx, _GUID_b89bbb45_7001_4bea_bbd8_c7cc26e7836c
0x18000c29d  mov     rcx, rdi
0x18000c2a0  mov     rax, [rax]
0x18000c2a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c2a8  mov     ebx, eax
0x18000c2aa  mov     rax, [rdi]
0x18000c2ad  mov     rcx, rdi
0x18000c2b0  mov     rax, [rax+10h]
0x18000c2b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c2b9  nop
0x18000c2ba  test    ebx, ebx
0x18000c2bc  jns     short loc_18000C2F2
0x18000c2be  mov     rcx, [rbp+18h]; this
0x18000c2c2  mov     r9d, ebx; char *
0x18000c2c5  lea     r8, aAvcoreMidi2Tra_2; "avcore\\midi2\\transport\\virtualmiditr"...
0x18000c2cc  mov     edx, 22h ; '"'; void *
0x18000c2d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c2d6  nop
0x18000c2d7  mov     rcx, [rbp+arg_10]
0x18000c2db  test    rcx, rcx
0x18000c2de  jz      short loc_18000C2ED
0x18000c2e0  mov     rax, [rcx]
0x18000c2e3  mov     rax, [rax+10h]
0x18000c2e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c2ec  nop
0x18000c2ed  jmp     loc_18000C6C1
0x18000c2f2  mov     rax, [rbp+arg_10]
0x18000c2f6  mov     [rsi], rax
0x18000c2f9  jmp     loc_18000C64F
0x18000c2fe  mov     rax, qword ptr cs:_GUID_badff6d2_0e3c_4009_a473_6ba82c008662.Data1
0x18000c305  cmp     rax, [rdx]
0x18000c308  jnz     loc_18000C40B
0x18000c30e  mov     rax, qword ptr cs:_GUID_badff6d2_0e3c_4009_a473_6ba82c008662.Data4
0x18000c315  cmp     rax, [rdx+8]
0x18000c319  jnz     loc_18000C40B
0x18000c31f  call    ?Instance@MidiVirtualMidiTransportTelemetryProvider@@KAPEAV1@XZ; MidiVirtualMidiTransportTelemetryProvider::Instance(void)
0x18000c324  mov     rcx, [rax+8]
0x18000c328  mov     eax, [rcx]
0x18000c32a  cmp     eax, 4
0x18000c32d  jbe     short loc_18000C370
0x18000c32f  lea     rax, aImidiendpointm; "IMidiEndpointManager"
0x18000c336  mov     [rbp+arg_10], rax
0x18000c33a  mov     [rbp+arg_18], rdi
0x18000c33e  lea     rax, aCmidi2virtualm_2; "CMidi2VirtualMidiTransport::Activate"
0x18000c345  mov     qword ptr [rbp+var_8], rax
0x18000c349  lea     rax, [rbp+arg_10]
0x18000c34d  mov     [rsp+50h+var_20], rax
0x18000c352  lea     rax, [rbp+arg_18]
0x18000c356  mov     [rsp+50h+var_28], rax
0x18000c35b  lea     rax, [rbp+var_8]
0x18000c35f  mov     qword ptr [rsp+50h+var_30], rax
0x18000c364  lea     rdx, byte_180026607
0x18000c36b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x18000c370  call    ?Current@TransportState@@SAAEAV1@XZ; TransportState::Current(void)
0x18000c375  mov     rdi, [rax+10h]
0x18000c379  test    rdi, rdi
0x18000c37c  jz      short loc_18000C38E
0x18000c37e  mov     rax, [rdi]
0x18000c381  mov     rcx, rdi
0x18000c384  mov     rax, [rax+8]
0x18000c388  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c38d  nop
0x18000c38e  test    rdi, rdi
0x18000c391  jz      short loc_18000C3A3
0x18000c393  mov     rax, [rdi]
0x18000c396  mov     rcx, rdi
0x18000c399  mov     rax, [rax+10h]
0x18000c39d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3a2  nop
0x18000c3a3  test    rdi, rdi
0x18000c3a6  jnz     short loc_18000C3B5
0x18000c3a8  call    ?Current@TransportState@@SAAEAV1@XZ; TransportState::Current(void)
0x18000c3ad  mov     rcx, rax; this
0x18000c3b0  call    ?ConstructEndpointManager@TransportState@@QEAAJXZ; TransportState::ConstructEndpointManager(void)
0x18000c3b5  call    ?Current@TransportState@@SAAEAV1@XZ; TransportState::Current(void)
0x18000c3ba  mov     rdi, [rax+10h]
0x18000c3be  test    rdi, rdi
0x18000c3c1  jz      short loc_18000C3D3
0x18000c3c3  mov     rax, [rdi]
0x18000c3c6  mov     rcx, rdi
0x18000c3c9  mov     rax, [rax+8]
0x18000c3cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3d2  nop
0x18000c3d3  mov     rax, [rdi]
0x18000c3d6  mov     r8, rsi
0x18000c3d9  mov     rdx, rbx
0x18000c3dc  mov     rcx, rdi
0x18000c3df  mov     rax, [rax]
0x18000c3e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3e7  mov     ebx, eax
0x18000c3e9  mov     rdx, [rdi]
0x18000c3ec  mov     rcx, rdi
0x18000c3ef  mov     rax, [rdx+10h]
0x18000c3f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3f8  nop
0x18000c3f9  test    ebx, ebx
0x18000c3fb  jns     loc_18000C64F
0x18000c401  mov     edx, 38h ; '8'
0x18000c406  jmp     loc_18000C6AE
0x18000c40b  mov     rax, qword ptr cs:_GUID_f19dd642_1809_4497_9eee_f230b11bd6fb.Data1
0x18000c412  cmp     rax, [rdx]
0x18000c415  jnz     loc_18000C518
0x18000c41b  mov     rax, qword ptr cs:_GUID_f19dd642_1809_4497_9eee_f230b11bd6fb.Data4
0x18000c422  cmp     rax, [rdx+8]
0x18000c426  jnz     loc_18000C518
0x18000c42c  call    ?Instance@MidiVirtualMidiTransportTelemetryProvider@@KAPEAV1@XZ; MidiVirtualMidiTransportTelemetryProvider::Instance(void)
0x18000c431  mov     rcx, [rax+8]
0x18000c435  mov     eax, [rcx]
0x18000c437  cmp     eax, 4
0x18000c43a  jbe     short loc_18000C47D
0x18000c43c  lea     rax, aImiditransport; "IMidiTransportConfigurationManager"
0x18000c443  mov     [rbp+arg_10], rax
0x18000c447  mov     [rbp+arg_18], rdi
0x18000c44b  lea     rax, aCmidi2virtualm_2; "CMidi2VirtualMidiTransport::Activate"
0x18000c452  mov     qword ptr [rbp+var_8], rax
0x18000c456  lea     rax, [rbp+arg_10]
0x18000c45a  mov     [rsp+50h+var_20], rax
0x18000c45f  lea     rax, [rbp+arg_18]
0x18000c463  mov     [rsp+50h+var_28], rax
0x18000c468  lea     rax, [rbp+var_8]
0x18000c46c  mov     qword ptr [rsp+50h+var_30], rax
0x18000c471  lea     rdx, byte_1800265D3
0x18000c478  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x18000c47d  call    ?Current@TransportState@@SAAEAV1@XZ; TransportState::Current(void)
0x18000c482  mov     rdi, [rax+18h]
0x18000c486  test    rdi, rdi
0x18000c489  jz      short loc_18000C49B
0x18000c48b  mov     rax, [rdi]
0x18000c48e  mov     rcx, rdi
0x18000c491  mov     rax, [rax+8]
0x18000c495  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c49a  nop
0x18000c49b  test    rdi, rdi
0x18000c49e  jz      short loc_18000C4B0
0x18000c4a0  mov     rax, [rdi]
0x18000c4a3  mov     rcx, rdi
0x18000c4a6  mov     rax, [rax+10h]
0x18000c4aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c4af  nop
0x18000c4b0  test    rdi, rdi
0x18000c4b3  jnz     short loc_18000C4C2
0x18000c4b5  call    ?Current@TransportState@@SAAEAV1@XZ; TransportState::Current(void)
0x18000c4ba  mov     rcx, rax; this
0x18000c4bd  call    ?ConstructConfigurationManager@TransportState@@QEAAJXZ; TransportState::ConstructConfigurationManager(void)
0x18000c4c2  call    ?Current@TransportState@@SAAEAV1@XZ; TransportState::Current(void)
0x18000c4c7  mov     rdi, [rax+18h]
0x18000c4cb  test    rdi, rdi
0x18000c4ce  jz      short loc_18000C4E0
0x18000c4d0  mov     rax, [rdi]
0x18000c4d3  mov     rcx, rdi
0x18000c4d6  mov     rax, [rax+8]
0x18000c4da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c4df  nop
0x18000c4e0  mov     rax, [rdi]
0x18000c4e3  mov     r8, rsi
0x18000c4e6  mov     rdx, rbx
0x18000c4e9  mov     rcx, rdi
0x18000c4ec  mov     rax, [rax]
0x18000c4ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c4f4  mov     ebx, eax
0x18000c4f6  mov     rdx, [rdi]
0x18000c4f9  mov     rcx, rdi
0x18000c4fc  mov     rax, [rdx+10h]
0x18000c500  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c505  nop
0x18000c506  test    ebx, ebx
0x18000c508  jns     loc_18000C64F
0x18000c50e  mov     edx, 4Dh ; 'M'
0x18000c513  jmp     loc_18000C6AE
0x18000c518  mov     rax, qword ptr cs:_GUID_8d542740_83f8_4a9a_8627_cd6324b6c1f4.Data1
0x18000c51f  cmp     rax, [rdx]
0x18000c522  jnz     loc_18000C653
0x18000c528  mov     rax, qword ptr cs:_GUID_8d542740_83f8_4a9a_8627_cd6324b6c1f4.Data4
0x18000c52f  cmp     rax, [rdx+8]
0x18000c533  jnz     loc_18000C653
0x18000c539  call    ?Instance@MidiVirtualMidiTransportTelemetryProvider@@KAPEAV1@XZ; MidiVirtualMidiTransportTelemetryProvider::Instance(void)
0x18000c53e  mov     rcx, [rax+8]
0x18000c542  mov     eax, [rcx]
0x18000c544  cmp     eax, 4
0x18000c547  jbe     short loc_18000C58B
0x18000c549  lea     rax, aImidiservicetr; "IMidiServiceTransportPluginMetadataProv"...
0x18000c550  mov     [rbp+arg_18], rax
0x18000c554  mov     qword ptr [rbp+var_8], rdi
0x18000c558  lea     rax, aCmidi2virtualm_2; "CMidi2VirtualMidiTransport::Activate"
0x18000c55f  mov     qword ptr [rbp+var_10], rax
0x18000c563  lea     rax, [rbp+arg_18]
0x18000c567  mov     [rsp+50h+var_20], rax
0x18000c56c  lea     rax, [rbp+var_8]
0x18000c570  mov     [rsp+50h+var_28], rax
0x18000c575  lea     rax, [rbp+var_10]
0x18000c579  mov     qword ptr [rsp+50h+var_30], rax; int
0x18000c57e  lea     rdx, byte_18002659F
0x18000c585  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x18000c58a  nop
0x18000c58b  mov     [rbp+arg_10], 0
0x18000c593  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000c59a  mov     ecx, 20h ; ' '; unsigned __int64
0x18000c59f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000c5a4  mov     rdi, rax
0x18000c5a7  test    rax, rax
0x18000c5aa  jnz     short loc_18000C5B3
0x18000c5ac  mov     ebx, 8007000Eh
0x18000c5b1  jmp     short loc_18000C617
0x18000c5b3  mov     dword ptr [rax+0Ch], 1
0x18000c5ba  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIMidiServiceTransportPluginMetadataProvider@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMidiServiceTransportPluginMetadataProvider>::`vftable'
0x18000c5c1  mov     [rdi], rax
0x18000c5c4  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000c5cb  test    rcx, rcx
0x18000c5ce  jz      short loc_18000C5DD
0x18000c5d0  mov     rax, [rcx]
0x18000c5d3  mov     rax, [rax+8]
0x18000c5d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c5dc  nop
0x18000c5dd  lea     rax, ??_7CMidi2VirtualMidiPluginMetadataProvider@@6B@; const CMidi2VirtualMidiPluginMetadataProvider::`vftable'
0x18000c5e4  mov     [rdi], rax
0x18000c5e7  lea     r8, [rbp+arg_10]
0x18000c5eb  lea     rdx, _GUID_8d542740_83f8_4a9a_8627_cd6324b6c1f4
0x18000c5f2  mov     rcx, rdi
0x18000c5f5  mov     rax, cs:??_7CMidi2VirtualMidiPluginMetadataProvider@@6B@; const CMidi2VirtualMidiPluginMetadataProvider::`vftable'
0x18000c5fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c601  mov     ebx, eax
0x18000c603  mov     rax, [rdi]
0x18000c606  mov     rcx, rdi
  ... truncated ...
```
