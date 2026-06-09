# CMidi2DiagnosticsTransport::Activate(_GUID const &,void * *)

- ea: `0x18000b9f0`
- end: `0x18000bf52`
- name: `?Activate@CMidi2DiagnosticsTransport@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `1378`
- prototype: `__int64 __fastcall(CMidi2DiagnosticsTransport *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800016dc`
- `0x180001784`
- `0x18000384c`
- `0x180008f64`
- `0x18000add8`
- `0x18000b74c`
- `0x18000b9f0`
- `0x180013010`

## string_xrefs

- `0x18000bd2c`: `IMidiTransportConfigurationManager`
- `0x18000bdf6`: `IMidiServiceTransportPluginMetadataProvider`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CMidi2DiagnosticsTransport::Activate(
        CMidi2DiagnosticsTransport *this,
        const struct _GUID *a2,
        CMidi2DiagnosticsTransport **a3)
{
  unsigned int v5; // ebx
  _DWORD *v7; // rcx
  int v8; // r8d
  int v9; // r9d
  _DWORD *v10; // rax
  _DWORD *v11; // rdi
  _DWORD *v12; // rcx
  int v13; // r8d
  int v14; // r9d
  _DWORD *v15; // rax
  _DWORD *v16; // rdi
  _DWORD *v17; // rcx
  int v18; // r8d
  int v19; // r9d
  int v20; // eax
  _DWORD *v21; // rcx
  int v22; // r8d
  int v23; // r9d
  _DWORD *v24; // rax
  _DWORD *v25; // rdi
  _DWORD *v26; // rcx
  int v27; // r8d
  int v28; // r9d
  int v29; // [rsp+20h] [rbp-30h]
  int v30[2]; // [rsp+40h] [rbp-10h] BYREF
  int v31[2]; // [rsp+48h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  CMidi2DiagnosticsTransport *v33; // [rsp+80h] [rbp+30h] BYREF
  const wchar_t *v34; // [rsp+88h] [rbp+38h] BYREF

  if ( !a3 )
  {
    v5 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x13,
      (unsigned int)"avcore\\midi2\\transport\\diagnosticstransport\\midi2.diagnosticstransport.cpp",
      (const char *)0x80070057LL,
      v29);
    return v5;
  }
  if ( *(_QWORD *)&GUID_b89bbb45_7001_4bea_bbd8_c7cc26e7836c.Data1 == *(_QWORD *)&a2->Data1
    && *(_QWORD *)GUID_b89bbb45_7001_4bea_bbd8_c7cc26e7836c.Data4 == *(_QWORD *)a2->Data4 )
  {
    v7 = (_DWORD *)*((_QWORD *)MidiDiagnosticsTransportTelemetryProvider::Instance() + 1);
    if ( *v7 > 4u )
    {
      v34 = L"IMidiBidirectional";
      *(_QWORD *)v30 = this;
      *(_QWORD *)v31 = "CMidi2DiagnosticsTransport::Activate";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v7,
        (unsigned int)qword_180016D08,
        v8,
        v9,
        (__int64)v31,
        (__int64)v30,
        (__int64)&v34);
    }
    v33 = 0;
    v10 = operator new(0x40u, (const struct std::nothrow_t *)std::nothrow);
    v11 = v10;
    if ( !v10 )
    {
      v5 = -2147024882;
LABEL_13:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x21,
        (unsigned int)"avcore\\midi2\\transport\\diagnosticstransport\\midi2.diagnosticstransport.cpp",
        (const char *)v5,
        v29);
      if ( v33 )
        (*(void (__fastcall **)(CMidi2DiagnosticsTransport *))(*(_QWORD *)v33 + 16LL))(v33);
      return v5;
    }
    v10[5] = 1;
    *(_QWORD *)v10 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMidiBidirectional,IMidiCallback>::`vftable'{for `IMidiBidirectional'};
    *((_QWORD *)v10 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMidiBidirectional,IMidiCallback>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IMidiCallback>'};
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v11 = &CMidi2LoopbackMidiBidi::`vftable'{for `IMidiBidirectional'};
    *((_QWORD *)v11 + 1) = &CMidi2LoopbackMidiBidi::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IMidiCallback>'};
    *((_BYTE *)v11 + 57) = 0;
    v5 = ((__int64 (__fastcall *)(_DWORD *, GUID *, CMidi2DiagnosticsTransport **))CMidi2LoopbackMidiBidi::`vftable'{for `IMidiBidirectional'})(
           v11,
           &GUID_b89bbb45_7001_4bea_bbd8_c7cc26e7836c,
           &v33);
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v11 + 16LL))(v11);
    if ( (v5 & 0x80000000) != 0 )
      goto LABEL_13;
    *a3 = v33;
    return 0;
  }
  if ( *(_QWORD *)&GUID_badff6d2_0e3c_4009_a473_6ba82c008662.Data1 == *(_QWORD *)&a2->Data1
    && *(_QWORD *)GUID_badff6d2_0e3c_4009_a473_6ba82c008662.Data4 == *(_QWORD *)a2->Data4 )
  {
    v12 = (_DWORD *)*((_QWORD *)MidiDiagnosticsTransportTelemetryProvider::Instance() + 1);
    if ( *v12 > 4u )
    {
      v34 = L"IMidiEndpointManager";
      *(_QWORD *)v31 = this;
      *(_QWORD *)v30 = "CMidi2DiagnosticsTransport::Activate";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v12,
        (unsigned int)&dword_180016CD4,
        v13,
        v14,
        (__int64)v30,
        (__int64)v31,
        (__int64)&v34);
    }
    v33 = 0;
    v15 = operator new(0x58u, (const struct std::nothrow_t *)std::nothrow);
    v16 = v15;
    if ( !v15 )
    {
      v5 = -2147024882;
LABEL_26:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x31,
        (unsigned int)"avcore\\midi2\\transport\\diagnosticstransport\\midi2.diagnosticstransport.cpp",
        (const char *)v5,
        v29);
      if ( v33 )
        (*(void (__fastcall **)(CMidi2DiagnosticsTransport *))(*(_QWORD *)v33 + 16LL))(v33);
      return v5;
    }
    v15[3] = 1;
    *(_QWORD *)v15 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMidiEndpointManager>::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v16 = &CMidi2DiagnosticsEndpointManager::`vftable';
    *((_OWORD *)v16 + 1) = 0;
    *((GUID *)v16 + 2) = GUID_ac9b5417_3fe0_4e62_960f_034ee4235a1a;
    *((_QWORD *)v16 + 6) = 0;
    *(_OWORD *)(v16 + 14) = 0;
    *((_QWORD *)v16 + 9) = 0;
    *((_QWORD *)v16 + 10) = 7;
    *((_WORD *)v16 + 28) = 0;
    v5 = (**(__int64 (__fastcall ***)(_DWORD *, GUID *, CMidi2DiagnosticsTransport **))v16)(
           v16,
           &GUID_badff6d2_0e3c_4009_a473_6ba82c008662,
           &v33);
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v16 + 16LL))(v16);
    if ( (v5 & 0x80000000) != 0 )
      goto LABEL_26;
    *a3 = v33;
    return 0;
  }
  if ( *(_QWORD *)&GUID_f19dd642_1809_4497_9eee_f230b11bd6fb.Data1 == *(_QWORD *)&a2->Data1
    && *(_QWORD *)GUID_f19dd642_1809_4497_9eee_f230b11bd6fb.Data4 == *(_QWORD *)a2->Data4 )
  {
    v17 = (_DWORD *)*((_QWORD *)MidiDiagnosticsTransportTelemetryProvider::Instance() + 1);
    if ( *v17 > 4u )
    {
      v34 = L"IMidiTransportConfigurationManager";
      *(_QWORD *)v31 = this;
      *(_QWORD *)v30 = "CMidi2DiagnosticsTransport::Activate";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v17,
        (unsigned int)qword_180016CA0,
        v18,
        v19,
        (__int64)v30,
        (__int64)v31,
        (__int64)&v34);
    }
    v33 = 0;
    v20 = Microsoft::WRL::Details::MakeAndInitialize<CMidi2DiagnosticsMidiConfigurationManager,IMidiTransportConfigurationManager,>(&v33);
    v5 = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x41,
        (unsigned int)"avcore\\midi2\\transport\\diagnosticstransport\\midi2.diagnosticstransport.cpp",
        (const char *)(unsigned int)v20,
        v29);
      if ( v33 )
        (*(void (__fastcall **)(CMidi2DiagnosticsTransport *))(*(_QWORD *)v33 + 16LL))(v33);
      return v5;
    }
    *a3 = v33;
    return 0;
  }
  if ( *(_QWORD *)&GUID_8d542740_83f8_4a9a_8627_cd6324b6c1f4.Data1 == *(_QWORD *)&a2->Data1
    && *(_QWORD *)GUID_8d542740_83f8_4a9a_8627_cd6324b6c1f4.Data4 == *(_QWORD *)a2->Data4 )
  {
    v21 = (_DWORD *)*((_QWORD *)MidiDiagnosticsTransportTelemetryProvider::Instance() + 1);
    if ( *v21 > 4u )
    {
      v34 = L"IMidiServiceTransportPluginMetadataProvider";
      *(_QWORD *)v31 = this;
      *(_QWORD *)v30 = "CMidi2DiagnosticsTransport::Activate";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v21,
        (unsigned int)&dword_180016C6C,
        v22,
        v23,
        (__int64)v30,
        (__int64)v31,
        (__int64)&v34);
    }
    v33 = 0;
    v24 = operator new(0x20u, (const struct std::nothrow_t *)std::nothrow);
    v25 = v24;
    if ( v24 )
    {
      v24[3] = 1;
      *(_QWORD *)v24 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMidiServiceTransportPluginMetadataProvider>::`vftable';
      if ( Microsoft::WRL::Details::ModuleBase::module_ )
        (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                             + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
      *(_QWORD *)v25 = &CMidi2DiagnosticsPluginMetadataProvider::`vftable';
      v5 = ((__int64 (__fastcall *)(_DWORD *, GUID *, CMidi2DiagnosticsTransport **))CMidi2DiagnosticsPluginMetadataProvider::`vftable')(
             v25,
             &GUID_8d542740_83f8_4a9a_8627_cd6324b6c1f4,
             &v33);
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v25 + 16LL))(v25);
      if ( (v5 & 0x80000000) == 0 )
      {
        *a3 = v33;
        return 0;
      }
    }
    else
    {
      v5 = -2147024882;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x52,
      (unsigned int)"avcore\\midi2\\transport\\diagnosticstransport\\midi2.diagnosticstransport.cpp",
      (const char *)v5,
      v29);
    if ( v33 )
      (*(void (__fastcall **)(CMidi2DiagnosticsTransport *))(*(_QWORD *)v33 + 16LL))(v33);
    return v5;
  }
  v26 = (_DWORD *)*((_QWORD *)MidiDiagnosticsTransportTelemetryProvider::Instance() + 1);
  if ( *v26 > 4u )
  {
    v33 = this;
    v34 = (const wchar_t *)"CMidi2DiagnosticsTransport::Activate";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      (_DWORD)v26,
      (unsigned int)word_180016C42,
      v27,
      v28,
      (__int64)&v34,
      (__int64)&v33);
  }
  return 2147500034LL;
}

```

## disassembly

```asm
0x18000b9f0  mov     [rsp-18h+arg_0], rbx
0x18000b9f5  push    rbp
0x18000b9f6  push    rsi
0x18000b9f7  push    rdi
0x18000b9f8  mov     rbp, rsp
0x18000b9fb  sub     rsp, 50h
0x18000b9ff  mov     rsi, r8
0x18000ba02  mov     rbx, rcx
0x18000ba05  test    r8, r8
0x18000ba08  jnz     short loc_18000BA2C
0x18000ba0a  mov     rcx, [rbp+18h]; this
0x18000ba0e  mov     ebx, 80070057h
0x18000ba13  mov     r9d, ebx; char *
0x18000ba16  lea     r8, aAvcoreMidi2Tra; "avcore\\midi2\\transport\\diagnosticstr"...
0x18000ba1d  lea     edx, [rsi+13h]; void *
0x18000ba20  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ba25  mov     eax, ebx
0x18000ba27  jmp     loc_18000BF45
0x18000ba2c  mov     rax, qword ptr cs:_GUID_b89bbb45_7001_4bea_bbd8_c7cc26e7836c.Data1
0x18000ba33  cmp     rax, [rdx]
0x18000ba36  jnz     loc_18000BB85
0x18000ba3c  mov     rax, qword ptr cs:_GUID_b89bbb45_7001_4bea_bbd8_c7cc26e7836c.Data4
0x18000ba43  cmp     rax, [rdx+8]
0x18000ba47  jnz     loc_18000BB85
0x18000ba4d  call    ?Instance@MidiDiagnosticsTransportTelemetryProvider@@KAPEAV1@XZ; MidiDiagnosticsTransportTelemetryProvider::Instance(void)
0x18000ba52  mov     rcx, [rax+8]
0x18000ba56  mov     eax, [rcx]
0x18000ba58  cmp     eax, 4
0x18000ba5b  jbe     short loc_18000BA9F
0x18000ba5d  lea     rax, aImidibidirecti; "IMidiBidirectional"
0x18000ba64  mov     [rbp+arg_18], rax
0x18000ba68  mov     qword ptr [rbp+var_10], rbx
0x18000ba6c  lea     rax, aCmidi2diagnost_1; "CMidi2DiagnosticsTransport::Activate"
0x18000ba73  mov     qword ptr [rbp+var_8], rax
0x18000ba77  lea     rax, [rbp+arg_18]
0x18000ba7b  mov     [rsp+50h+var_20], rax
0x18000ba80  lea     rax, [rbp+var_10]
0x18000ba84  mov     [rsp+50h+var_28], rax
0x18000ba89  lea     rax, [rbp+var_8]
0x18000ba8d  mov     qword ptr [rsp+50h+var_30], rax; int
0x18000ba92  lea     rdx, qword_180016D08
0x18000ba99  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x18000ba9e  nop
0x18000ba9f  mov     [rbp+arg_10], 0
0x18000baa7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000baae  mov     ecx, 40h ; '@'; unsigned __int64
0x18000bab3  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000bab8  mov     rdi, rax
0x18000babb  test    rax, rax
0x18000babe  jnz     short loc_18000BAC7
0x18000bac0  mov     ebx, 8007000Eh
0x18000bac5  jmp     short loc_18000BB45
0x18000bac7  mov     dword ptr [rax+14h], 1
0x18000bace  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIMidiBidirectional@@UIMidiCallback@@@WRL@Microsoft@@6BIMidiBidirectional@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMidiBidirectional,IMidiCallback>::`vftable'{for `IMidiBidirectional'}
0x18000bad5  mov     [rdi], rax
0x18000bad8  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIMidiBidirectional@@UIMidiCallback@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIMidiCallback@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMidiBidirectional,IMidiCallback>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IMidiCallback>'}
0x18000badf  mov     [rdi+8], rax
0x18000bae3  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000baea  test    rcx, rcx
0x18000baed  jz      short loc_18000BAFC
0x18000baef  mov     rax, [rcx]
0x18000baf2  mov     rax, [rax+8]
0x18000baf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bafb  nop
0x18000bafc  lea     rax, ??_7CMidi2LoopbackMidiBidi@@6BIMidiBidirectional@@@; const CMidi2LoopbackMidiBidi::`vftable'{for `IMidiBidirectional'}
0x18000bb03  mov     [rdi], rax
0x18000bb06  lea     rax, ??_7CMidi2LoopbackMidiBidi@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIMidiCallback@@@Details@WRL@Microsoft@@@; const CMidi2LoopbackMidiBidi::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IMidiCallback>'}
0x18000bb0d  mov     [rdi+8], rax
0x18000bb11  mov     byte ptr [rdi+39h], 0
0x18000bb15  lea     r8, [rbp+arg_10]
0x18000bb19  lea     rdx, _GUID_b89bbb45_7001_4bea_bbd8_c7cc26e7836c
0x18000bb20  mov     rcx, rdi
0x18000bb23  mov     rax, cs:??_7CMidi2LoopbackMidiBidi@@6BIMidiBidirectional@@@; const CMidi2LoopbackMidiBidi::`vftable'{for `IMidiBidirectional'}
0x18000bb2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb2f  mov     ebx, eax
0x18000bb31  mov     rax, [rdi]
0x18000bb34  mov     rcx, rdi
0x18000bb37  mov     rax, [rax+10h]
0x18000bb3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb40  nop
0x18000bb41  test    ebx, ebx
0x18000bb43  jns     short loc_18000BB79
0x18000bb45  mov     rcx, [rbp+18h]; this
0x18000bb49  mov     r9d, ebx; char *
0x18000bb4c  lea     r8, aAvcoreMidi2Tra; "avcore\\midi2\\transport\\diagnosticstr"...
0x18000bb53  mov     edx, 21h ; '!'; void *
0x18000bb58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bb5d  nop
0x18000bb5e  mov     rcx, [rbp+arg_10]
0x18000bb62  test    rcx, rcx
0x18000bb65  jz      short loc_18000BB74
0x18000bb67  mov     rax, [rcx]
0x18000bb6a  mov     rax, [rax+10h]
0x18000bb6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb73  nop
0x18000bb74  jmp     loc_18000BA25
0x18000bb79  mov     rax, [rbp+arg_10]
0x18000bb7d  mov     [rsi], rax
0x18000bb80  jmp     loc_18000BEFF
0x18000bb85  mov     rax, qword ptr cs:_GUID_badff6d2_0e3c_4009_a473_6ba82c008662.Data1
0x18000bb8c  cmp     rax, [rdx]
0x18000bb8f  jnz     loc_18000BCFB
0x18000bb95  mov     rax, qword ptr cs:_GUID_badff6d2_0e3c_4009_a473_6ba82c008662.Data4
0x18000bb9c  cmp     rax, [rdx+8]
0x18000bba0  jnz     loc_18000BCFB
0x18000bba6  call    ?Instance@MidiDiagnosticsTransportTelemetryProvider@@KAPEAV1@XZ; MidiDiagnosticsTransportTelemetryProvider::Instance(void)
0x18000bbab  mov     rcx, [rax+8]
0x18000bbaf  mov     eax, [rcx]
0x18000bbb1  cmp     eax, 4
0x18000bbb4  jbe     short loc_18000BBF8
0x18000bbb6  lea     rax, aImidiendpointm; "IMidiEndpointManager"
0x18000bbbd  mov     [rbp+arg_18], rax
0x18000bbc1  mov     qword ptr [rbp+var_8], rbx
0x18000bbc5  lea     rax, aCmidi2diagnost_1; "CMidi2DiagnosticsTransport::Activate"
0x18000bbcc  mov     qword ptr [rbp+var_10], rax
0x18000bbd0  lea     rax, [rbp+arg_18]
0x18000bbd4  mov     [rsp+50h+var_20], rax
0x18000bbd9  lea     rax, [rbp+var_8]
0x18000bbdd  mov     [rsp+50h+var_28], rax
0x18000bbe2  lea     rax, [rbp+var_10]
0x18000bbe6  mov     qword ptr [rsp+50h+var_30], rax; int
0x18000bbeb  lea     rdx, dword_180016CD4
0x18000bbf2  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x18000bbf7  nop
0x18000bbf8  mov     [rbp+arg_10], 0
0x18000bc00  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000bc07  mov     ecx, 58h ; 'X'; unsigned __int64
0x18000bc0c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000bc11  mov     rdi, rax
0x18000bc14  test    rax, rax
0x18000bc17  jnz     short loc_18000BC23
0x18000bc19  mov     ebx, 8007000Eh
0x18000bc1e  jmp     loc_18000BCBB
0x18000bc23  mov     dword ptr [rax+0Ch], 1
0x18000bc2a  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIMidiEndpointManager@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMidiEndpointManager>::`vftable'
0x18000bc31  mov     [rdi], rax
0x18000bc34  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000bc3b  test    rcx, rcx
0x18000bc3e  jz      short loc_18000BC4D
0x18000bc40  mov     rax, [rcx]
0x18000bc43  mov     rax, [rax+8]
0x18000bc47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc4c  nop
0x18000bc4d  lea     rax, ??_7CMidi2DiagnosticsEndpointManager@@6B@; const CMidi2DiagnosticsEndpointManager::`vftable'
0x18000bc54  mov     [rdi], rax
0x18000bc57  xorps   xmm0, xmm0
0x18000bc5a  movups  xmmword ptr [rdi+10h], xmm0
0x18000bc5e  movups  xmm1, xmmword ptr cs:_GUID_ac9b5417_3fe0_4e62_960f_034ee4235a1a.Data1
0x18000bc65  movdqu  xmmword ptr [rdi+20h], xmm1
0x18000bc6a  mov     qword ptr [rdi+30h], 0
0x18000bc72  movups  xmmword ptr [rdi+38h], xmm0
0x18000bc76  mov     qword ptr [rdi+48h], 0
0x18000bc7e  mov     qword ptr [rdi+50h], 7
0x18000bc86  xor     eax, eax
0x18000bc88  mov     [rdi+38h], ax
0x18000bc8c  mov     rax, [rdi]
0x18000bc8f  lea     r8, [rbp+arg_10]
0x18000bc93  lea     rdx, _GUID_badff6d2_0e3c_4009_a473_6ba82c008662
0x18000bc9a  mov     rcx, rdi
0x18000bc9d  mov     rax, [rax]
0x18000bca0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bca5  mov     ebx, eax
0x18000bca7  mov     rax, [rdi]
0x18000bcaa  mov     rcx, rdi
0x18000bcad  mov     rax, [rax+10h]
0x18000bcb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bcb6  nop
0x18000bcb7  test    ebx, ebx
0x18000bcb9  jns     short loc_18000BCEF
0x18000bcbb  mov     rcx, [rbp+18h]; this
0x18000bcbf  mov     r9d, ebx; char *
0x18000bcc2  lea     r8, aAvcoreMidi2Tra; "avcore\\midi2\\transport\\diagnosticstr"...
0x18000bcc9  mov     edx, 31h ; '1'; void *
0x18000bcce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bcd3  nop
0x18000bcd4  mov     rcx, [rbp+arg_10]
0x18000bcd8  test    rcx, rcx
0x18000bcdb  jz      short loc_18000BCEA
0x18000bcdd  mov     rax, [rcx]
0x18000bce0  mov     rax, [rax+10h]
0x18000bce4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bce9  nop
0x18000bcea  jmp     loc_18000BA25
0x18000bcef  mov     rax, [rbp+arg_10]
0x18000bcf3  mov     [rsi], rax
0x18000bcf6  jmp     loc_18000BEFF
0x18000bcfb  mov     rax, qword ptr cs:_GUID_f19dd642_1809_4497_9eee_f230b11bd6fb.Data1
0x18000bd02  cmp     rax, [rdx]
0x18000bd05  jnz     loc_18000BDC5
0x18000bd0b  mov     rax, qword ptr cs:_GUID_f19dd642_1809_4497_9eee_f230b11bd6fb.Data4
0x18000bd12  cmp     rax, [rdx+8]
0x18000bd16  jnz     loc_18000BDC5
0x18000bd1c  call    ?Instance@MidiDiagnosticsTransportTelemetryProvider@@KAPEAV1@XZ; MidiDiagnosticsTransportTelemetryProvider::Instance(void)
0x18000bd21  mov     rcx, [rax+8]
0x18000bd25  mov     eax, [rcx]
0x18000bd27  cmp     eax, 4
0x18000bd2a  jbe     short loc_18000BD6E
0x18000bd2c  lea     rax, aImiditransport; "IMidiTransportConfigurationManager"
0x18000bd33  mov     [rbp+arg_18], rax
0x18000bd37  mov     qword ptr [rbp+var_8], rbx
0x18000bd3b  lea     rax, aCmidi2diagnost_1; "CMidi2DiagnosticsTransport::Activate"
0x18000bd42  mov     qword ptr [rbp+var_10], rax
0x18000bd46  lea     rax, [rbp+arg_18]
0x18000bd4a  mov     [rsp+50h+var_20], rax
0x18000bd4f  lea     rax, [rbp+var_8]
0x18000bd53  mov     [rsp+50h+var_28], rax
0x18000bd58  lea     rax, [rbp+var_10]
0x18000bd5c  mov     qword ptr [rsp+50h+var_30], rax; int
0x18000bd61  lea     rdx, qword_180016CA0
0x18000bd68  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x18000bd6d  nop
0x18000bd6e  mov     [rbp+arg_10], 0
0x18000bd76  lea     rcx, [rbp+arg_10]
0x18000bd7a  call    ??$MakeAndInitialize@VCMidi2DiagnosticsMidiConfigurationManager@@UIMidiTransportConfigurationManager@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIMidiTransportConfigurationManager@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CMidi2DiagnosticsMidiConfigurationManager,IMidiTransportConfigurationManager,>(IMidiTransportConfigurationManager * *)
0x18000bd7f  mov     ebx, eax
0x18000bd81  test    eax, eax
0x18000bd83  jns     short loc_18000BDB9
0x18000bd85  mov     rcx, [rbp+18h]; this
0x18000bd89  mov     r9d, eax; char *
0x18000bd8c  lea     r8, aAvcoreMidi2Tra; "avcore\\midi2\\transport\\diagnosticstr"...
0x18000bd93  mov     edx, 41h ; 'A'; void *
0x18000bd98  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bd9d  nop
0x18000bd9e  mov     rcx, [rbp+arg_10]
0x18000bda2  test    rcx, rcx
0x18000bda5  jz      short loc_18000BDB4
0x18000bda7  mov     rax, [rcx]
0x18000bdaa  mov     rax, [rax+10h]
0x18000bdae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bdb3  nop
0x18000bdb4  jmp     loc_18000BA25
0x18000bdb9  mov     rax, [rbp+arg_10]
0x18000bdbd  mov     [rsi], rax
0x18000bdc0  jmp     loc_18000BEFF
0x18000bdc5  mov     rax, qword ptr cs:_GUID_8d542740_83f8_4a9a_8627_cd6324b6c1f4.Data1
0x18000bdcc  cmp     rax, [rdx]
0x18000bdcf  jnz     loc_18000BF03
0x18000bdd5  mov     rax, qword ptr cs:_GUID_8d542740_83f8_4a9a_8627_cd6324b6c1f4.Data4
0x18000bddc  cmp     rax, [rdx+8]
0x18000bde0  jnz     loc_18000BF03
0x18000bde6  call    ?Instance@MidiDiagnosticsTransportTelemetryProvider@@KAPEAV1@XZ; MidiDiagnosticsTransportTelemetryProvider::Instance(void)
0x18000bdeb  mov     rcx, [rax+8]
0x18000bdef  mov     eax, [rcx]
0x18000bdf1  cmp     eax, 4
0x18000bdf4  jbe     short loc_18000BE38
0x18000bdf6  lea     rax, aImidiservicetr; "IMidiServiceTransportPluginMetadataProv"...
0x18000bdfd  mov     [rbp+arg_18], rax
0x18000be01  mov     qword ptr [rbp+var_8], rbx
0x18000be05  lea     rax, aCmidi2diagnost_1; "CMidi2DiagnosticsTransport::Activate"
0x18000be0c  mov     qword ptr [rbp+var_10], rax
0x18000be10  lea     rax, [rbp+arg_18]
0x18000be14  mov     [rsp+50h+var_20], rax
0x18000be19  lea     rax, [rbp+var_8]
0x18000be1d  mov     [rsp+50h+var_28], rax
0x18000be22  lea     rax, [rbp+var_10]
0x18000be26  mov     qword ptr [rsp+50h+var_30], rax; int
0x18000be2b  lea     rdx, dword_180016C6C
0x18000be32  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x18000be37  nop
0x18000be38  mov     [rbp+arg_10], 0
0x18000be40  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000be47  mov     ecx, 20h ; ' '; unsigned __int64
0x18000be4c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000be51  mov     rdi, rax
0x18000be54  test    rax, rax
0x18000be57  jnz     short loc_18000BE60
0x18000be59  mov     ebx, 8007000Eh
0x18000be5e  jmp     short loc_18000BEC4
0x18000be60  mov     dword ptr [rax+0Ch], 1
0x18000be67  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIMidiServiceTransportPluginMetadataProvider@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMidiServiceTransportPluginMetadataProvider>::`vftable'
0x18000be6e  mov     [rdi], rax
0x18000be71  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000be78  test    rcx, rcx
0x18000be7b  jz      short loc_18000BE8A
0x18000be7d  mov     rax, [rcx]
0x18000be80  mov     rax, [rax+8]
0x18000be84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be89  nop
0x18000be8a  lea     rax, ??_7CMidi2DiagnosticsPluginMetadataProvider@@6B@; const CMidi2DiagnosticsPluginMetadataProvider::`vftable'
0x18000be91  mov     [rdi], rax
0x18000be94  lea     r8, [rbp+arg_10]
0x18000be98  lea     rdx, _GUID_8d542740_83f8_4a9a_8627_cd6324b6c1f4
0x18000be9f  mov     rcx, rdi
0x18000bea2  mov     rax, cs:??_7CMidi2DiagnosticsPluginMetadataProvider@@6B@; const CMidi2DiagnosticsPluginMetadataProvider::`vftable'
0x18000bea9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000beae  mov     ebx, eax
0x18000beb0  mov     rax, [rdi]
0x18000beb3  mov     rcx, rdi
0x18000beb6  mov     rax, [rax+10h]
0x18000beba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bebf  nop
0x18000bec0  test    ebx, ebx
0x18000bec2  jns     short loc_18000BEF8
0x18000bec4  mov     rcx, [rbp+18h]; this
0x18000bec8  mov     r9d, ebx; char *
0x18000becb  lea     r8, aAvcoreMidi2Tra; "avcore\\midi2\\transport\\diagnosticstr"...
0x18000bed2  mov     edx, 52h ; 'R'; void *
0x18000bed7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bedc  nop
0x18000bedd  mov     rcx, [rbp+arg_10]
  ... truncated ...
```
