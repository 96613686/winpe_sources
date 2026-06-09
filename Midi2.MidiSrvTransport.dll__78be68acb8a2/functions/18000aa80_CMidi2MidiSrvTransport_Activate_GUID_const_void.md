# CMidi2MidiSrvTransport::Activate(_GUID const &,void * *)

- ea: `0x18000aa80`
- end: `0x18000b0d4`
- name: `?Activate@CMidi2MidiSrvTransport@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `1620`
- prototype: `__int64 __fastcall(CMidi2MidiSrvTransport *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800016dc`
- `0x1800028ec`
- `0x180007e24`
- `0x180009bf8`
- `0x18000a63c`
- `0x18000a6ec`
- `0x18000a7b8`
- `0x18000a884`
- `0x18000aa80`
- `0x180015010`

## string_xrefs

- `0x18000ae45`: `IMidiTransportConfigurationManager`
- `0x18000af0f`: `IMidiServicePluginMetadataReporter`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CMidi2MidiSrvTransport::Activate(const wchar_t *this, const struct _GUID *a2, const wchar_t **a3)
{
  unsigned int v5; // ebx
  _DWORD *v7; // rcx
  int v8; // r8d
  int v9; // r9d
  _QWORD *v10; // rax
  _QWORD *v11; // rsi
  _DWORD *v12; // rcx
  int v13; // r8d
  int v14; // r9d
  _QWORD *v15; // rax
  _QWORD *v16; // rsi
  _DWORD *v17; // rcx
  int v18; // r8d
  int v19; // r9d
  int v20; // eax
  _DWORD *v21; // rcx
  int v22; // r8d
  int v23; // r9d
  int v24; // eax
  _DWORD *v25; // rcx
  int v26; // r8d
  int v27; // r9d
  int v28; // eax
  _DWORD *v29; // rcx
  int v30; // r8d
  int v31; // r9d
  int v32; // eax
  _DWORD *v33; // rcx
  int v34; // r8d
  int v35; // r9d
  int v36; // [rsp+20h] [rbp-30h]
  int v37[2]; // [rsp+40h] [rbp-10h] BYREF
  int v38[2]; // [rsp+48h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  const wchar_t *v40; // [rsp+80h] [rbp+30h] BYREF
  const wchar_t *v41; // [rsp+88h] [rbp+38h] BYREF

  if ( !a3 )
  {
    v5 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x13,
      (unsigned int)"avcore\\midi2\\transport\\midisrvtransport\\midi2.midisrvtransport.cpp",
      (const char *)0x80070057LL,
      v36);
    return v5;
  }
  if ( *(_QWORD *)&GUID_6c4b8bf9_8133_4b41_8303_1fde78e20aca.Data1 == *(_QWORD *)&a2->Data1
    && *(_QWORD *)GUID_6c4b8bf9_8133_4b41_8303_1fde78e20aca.Data4 == *(_QWORD *)a2->Data4 )
  {
    v7 = (_DWORD *)*((_QWORD *)MidiSrvTransportTelemetryProvider::Instance() + 1);
    if ( *v7 > 4u )
    {
      v41 = L"IMidiIn";
      *(_QWORD *)v37 = this;
      *(_QWORD *)v38 = "CMidi2MidiSrvTransport::Activate";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v7,
        (unsigned int)byte_180019E39,
        v8,
        v9,
        (__int64)v38,
        (__int64)v37,
        (__int64)&v41);
    }
    v40 = 0;
    v10 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
    v11 = v10;
    if ( !v10 )
    {
      v5 = -2147024882;
LABEL_13:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x21,
        (unsigned int)"avcore\\midi2\\transport\\midisrvtransport\\midi2.midisrvtransport.cpp",
        (const char *)v5,
        v36);
      if ( v40 )
        (*(void (__fastcall **)(const wchar_t *))(*(_QWORD *)v40 + 16LL))(v40);
      return v5;
    }
    *((_DWORD *)v10 + 3) = 1;
    *v10 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMidiIn>::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *v11 = &CMidi2MidiSrvIn::`vftable';
    v11[2] = 0;
    v5 = ((__int64 (__fastcall *)(_QWORD *, GUID *, const wchar_t **))CMidi2MidiSrvIn::`vftable')(
           v11,
           &GUID_6c4b8bf9_8133_4b41_8303_1fde78e20aca,
           &v40);
    (*(void (__fastcall **)(_QWORD *))(*v11 + 16LL))(v11);
    if ( (v5 & 0x80000000) != 0 )
      goto LABEL_13;
    *a3 = v40;
    return 0;
  }
  if ( *(_QWORD *)&GUID_f328d645_7d6d_4924_a7e3_9dee245189f9.Data1 == *(_QWORD *)&a2->Data1
    && *(_QWORD *)GUID_f328d645_7d6d_4924_a7e3_9dee245189f9.Data4 == *(_QWORD *)a2->Data4 )
  {
    v12 = (_DWORD *)*((_QWORD *)MidiSrvTransportTelemetryProvider::Instance() + 1);
    if ( *v12 > 4u )
    {
      v41 = L"IMidiOut";
      *(_QWORD *)v38 = this;
      *(_QWORD *)v37 = "CMidi2MidiSrvTransport::Activate";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v12,
        (unsigned int)byte_180019E05,
        v13,
        v14,
        (__int64)v37,
        (__int64)v38,
        (__int64)&v41);
    }
    v40 = 0;
    v15 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
    v16 = v15;
    if ( !v15 )
    {
      v5 = -2147024882;
LABEL_26:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x30,
        (unsigned int)"avcore\\midi2\\transport\\midisrvtransport\\midi2.midisrvtransport.cpp",
        (const char *)v5,
        v36);
      if ( v40 )
        (*(void (__fastcall **)(const wchar_t *))(*(_QWORD *)v40 + 16LL))(v40);
      return v5;
    }
    *((_DWORD *)v15 + 3) = 1;
    *v15 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMidiOut>::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *v16 = &CMidi2MidiSrvOut::`vftable';
    v16[2] = 0;
    v5 = ((__int64 (__fastcall *)(_QWORD *, GUID *, const wchar_t **))CMidi2MidiSrvOut::`vftable')(
           v16,
           &GUID_f328d645_7d6d_4924_a7e3_9dee245189f9,
           &v40);
    (*(void (__fastcall **)(_QWORD *))(*v16 + 16LL))(v16);
    if ( (v5 & 0x80000000) != 0 )
      goto LABEL_26;
    *a3 = v40;
    return 0;
  }
  if ( *(_QWORD *)&GUID_b89bbb45_7001_4bea_bbd8_c7cc26e7836c.Data1 == *(_QWORD *)&a2->Data1
    && *(_QWORD *)GUID_b89bbb45_7001_4bea_bbd8_c7cc26e7836c.Data4 == *(_QWORD *)a2->Data4 )
  {
    v17 = (_DWORD *)*((_QWORD *)MidiSrvTransportTelemetryProvider::Instance() + 1);
    if ( *v17 > 4u )
    {
      v41 = L"IMidiBidirectional";
      *(_QWORD *)v38 = this;
      *(_QWORD *)v37 = "CMidi2MidiSrvTransport::Activate";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v17,
        (unsigned int)byte_180019DD1,
        v18,
        v19,
        (__int64)v37,
        (__int64)v38,
        (__int64)&v41);
    }
    v40 = 0;
    v20 = Microsoft::WRL::Details::MakeAndInitialize<CMidi2MidiSrvBidi,IMidiBidirectional,>(&v40);
    v5 = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3F,
        (unsigned int)"avcore\\midi2\\transport\\midisrvtransport\\midi2.midisrvtransport.cpp",
        (const char *)(unsigned int)v20,
        v36);
      if ( v40 )
        (*(void (__fastcall **)(const wchar_t *))(*(_QWORD *)v40 + 16LL))(v40);
      return v5;
    }
    *a3 = v40;
    return 0;
  }
  if ( *(_QWORD *)&GUID_f19dd642_1809_4497_9eee_f230b11bd6fb.Data1 == *(_QWORD *)&a2->Data1
    && *(_QWORD *)GUID_f19dd642_1809_4497_9eee_f230b11bd6fb.Data4 == *(_QWORD *)a2->Data4 )
  {
    v21 = (_DWORD *)*((_QWORD *)MidiSrvTransportTelemetryProvider::Instance() + 1);
    if ( *v21 > 4u )
    {
      v41 = L"IMidiTransportConfigurationManager";
      *(_QWORD *)v38 = this;
      *(_QWORD *)v37 = "CMidi2MidiSrvTransport::Activate";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v21,
        (unsigned int)byte_180019D9D,
        v22,
        v23,
        (__int64)v37,
        (__int64)v38,
        (__int64)&v41);
    }
    v40 = 0;
    v24 = Microsoft::WRL::Details::MakeAndInitialize<CMidi2MidiSrvConfigurationManager,IMidiTransportConfigurationManager,>(&v40);
    v5 = v24;
    if ( v24 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4E,
        (unsigned int)"avcore\\midi2\\transport\\midisrvtransport\\midi2.midisrvtransport.cpp",
        (const char *)(unsigned int)v24,
        v36);
      if ( v40 )
        (*(void (__fastcall **)(const wchar_t *))(*(_QWORD *)v40 + 16LL))(v40);
      return v5;
    }
    *a3 = v40;
    return 0;
  }
  if ( *(_QWORD *)&GUID_469c7722_f779_40c3_b648_52620f75dcee.Data1 == *(_QWORD *)&a2->Data1
    && *(_QWORD *)GUID_469c7722_f779_40c3_b648_52620f75dcee.Data4 == *(_QWORD *)a2->Data4 )
  {
    v25 = (_DWORD *)*((_QWORD *)MidiSrvTransportTelemetryProvider::Instance() + 1);
    if ( *v25 > 4u )
    {
      v41 = L"IMidiServicePluginMetadataReporter";
      *(_QWORD *)v38 = this;
      *(_QWORD *)v37 = "CMidi2MidiSrvTransport::Activate";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v25,
        (unsigned int)byte_180019D69,
        v26,
        v27,
        (__int64)v37,
        (__int64)v38,
        (__int64)&v41);
    }
    v40 = 0;
    v28 = Microsoft::WRL::Details::MakeAndInitialize<CMidi2MidiSrvConfigurationManager,IMidiServicePluginMetadataReporter,>(&v40);
    v5 = v28;
    if ( v28 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5E,
        (unsigned int)"avcore\\midi2\\transport\\midisrvtransport\\midi2.midisrvtransport.cpp",
        (const char *)(unsigned int)v28,
        v36);
      if ( v40 )
        (*(void (__fastcall **)(const wchar_t *))(*(_QWORD *)v40 + 16LL))(v40);
      return v5;
    }
    *a3 = v40;
    return 0;
  }
  if ( *(_QWORD *)&GUID_194c2746_3ae5_419a_94d9_20416c7dbefe.Data1 == *(_QWORD *)&a2->Data1
    && *(_QWORD *)GUID_194c2746_3ae5_419a_94d9_20416c7dbefe.Data4 == *(_QWORD *)a2->Data4 )
  {
    v29 = (_DWORD *)*((_QWORD *)MidiSrvTransportTelemetryProvider::Instance() + 1);
    if ( *v29 > 4u )
    {
      v41 = L"IMidiSessionTracker";
      *(_QWORD *)v38 = this;
      *(_QWORD *)v37 = "CMidi2MidiSrvTransport::Activate";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v29,
        (unsigned int)byte_180019D35,
        v30,
        v31,
        (__int64)v37,
        (__int64)v38,
        (__int64)&v41);
    }
    v40 = 0;
    v32 = Microsoft::WRL::Details::MakeAndInitialize<CMidi2MidiSrvSessionTracker,IMidiSessionTracker,>(&v40);
    v5 = v32;
    if ( v32 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6F,
        (unsigned int)"avcore\\midi2\\transport\\midisrvtransport\\midi2.midisrvtransport.cpp",
        (const char *)(unsigned int)v32,
        v36);
      if ( v40 )
        (*(void (__fastcall **)(const wchar_t *))(*(_QWORD *)v40 + 16LL))(v40);
      return v5;
    }
    *a3 = v40;
    return 0;
  }
  v33 = (_DWORD *)*((_QWORD *)MidiSrvTransportTelemetryProvider::Instance() + 1);
  if ( *v33 > 4u )
  {
    v40 = L"Unknown interface requested";
    v41 = this;
    *(_QWORD *)v38 = "CMidi2MidiSrvTransport::Activate";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
      (_DWORD)v33,
      (unsigned int)word_180019D02,
      v34,
      v35,
      (__int64)v38,
      (__int64)&v41,
      (__int64)&v40);
  }
  return 2147500034LL;
}

```

## disassembly

```asm
0x18000aa80  mov     [rsp-18h+arg_0], rbx
0x18000aa85  push    rbp
0x18000aa86  push    rsi
0x18000aa87  push    rdi
0x18000aa88  mov     rbp, rsp
0x18000aa8b  sub     rsp, 50h
0x18000aa8f  mov     rdi, r8
0x18000aa92  mov     rbx, rcx
0x18000aa95  test    r8, r8
0x18000aa98  jnz     short loc_18000AABC
0x18000aa9a  mov     rcx, [rbp+18h]; this
0x18000aa9e  mov     ebx, 80070057h
0x18000aaa3  mov     r9d, ebx; char *
0x18000aaa6  lea     r8, aAvcoreMidi2Tra; "avcore\\midi2\\transport\\midisrvtransp"...
0x18000aaad  lea     edx, [rdi+13h]; void *
0x18000aab0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000aab5  mov     eax, ebx
0x18000aab7  jmp     loc_18000B0C7
0x18000aabc  mov     rax, qword ptr cs:_GUID_6c4b8bf9_8133_4b41_8303_1fde78e20aca.Data1
0x18000aac3  cmp     rax, [rdx]
0x18000aac6  jnz     loc_18000AC03
0x18000aacc  mov     rax, qword ptr cs:_GUID_6c4b8bf9_8133_4b41_8303_1fde78e20aca.Data4
0x18000aad3  cmp     rax, [rdx+8]
0x18000aad7  jnz     loc_18000AC03
0x18000aadd  call    ?Instance@MidiSrvTransportTelemetryProvider@@KAPEAV1@XZ; MidiSrvTransportTelemetryProvider::Instance(void)
0x18000aae2  mov     rcx, [rax+8]
0x18000aae6  mov     eax, [rcx]
0x18000aae8  cmp     eax, 4
0x18000aaeb  jbe     short loc_18000AB2F
0x18000aaed  lea     rax, aImidiin; "IMidiIn"
0x18000aaf4  mov     [rbp+arg_18], rax
0x18000aaf8  mov     qword ptr [rbp+var_10], rbx
0x18000aafc  lea     rax, aCmidi2midisrvt; "CMidi2MidiSrvTransport::Activate"
0x18000ab03  mov     qword ptr [rbp+var_8], rax
0x18000ab07  lea     rax, [rbp+arg_18]
0x18000ab0b  mov     [rsp+50h+var_20], rax
0x18000ab10  lea     rax, [rbp+var_10]
0x18000ab14  mov     [rsp+50h+var_28], rax
0x18000ab19  lea     rax, [rbp+var_8]
0x18000ab1d  mov     qword ptr [rsp+50h+var_30], rax; int
0x18000ab22  lea     rdx, byte_180019E39
0x18000ab29  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x18000ab2e  nop
0x18000ab2f  mov     [rbp+arg_10], 0
0x18000ab37  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000ab3e  mov     ecx, 18h; unsigned __int64
0x18000ab43  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000ab48  mov     rsi, rax
0x18000ab4b  test    rax, rax
0x18000ab4e  jnz     short loc_18000AB57
0x18000ab50  mov     ebx, 8007000Eh
0x18000ab55  jmp     short loc_18000ABC3
0x18000ab57  mov     dword ptr [rax+0Ch], 1
0x18000ab5e  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIMidiIn@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMidiIn>::`vftable'
0x18000ab65  mov     [rsi], rax
0x18000ab68  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000ab6f  test    rcx, rcx
0x18000ab72  jz      short loc_18000AB81
0x18000ab74  mov     rax, [rcx]
0x18000ab77  mov     rax, [rax+8]
0x18000ab7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab80  nop
0x18000ab81  lea     rax, ??_7CMidi2MidiSrvIn@@6B@; const CMidi2MidiSrvIn::`vftable'
0x18000ab88  mov     [rsi], rax
0x18000ab8b  mov     qword ptr [rsi+10h], 0
0x18000ab93  lea     r8, [rbp+arg_10]
0x18000ab97  lea     rdx, _GUID_6c4b8bf9_8133_4b41_8303_1fde78e20aca
0x18000ab9e  mov     rcx, rsi
0x18000aba1  mov     rax, cs:??_7CMidi2MidiSrvIn@@6B@; const CMidi2MidiSrvIn::`vftable'
0x18000aba8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000abad  mov     ebx, eax
0x18000abaf  mov     rax, [rsi]
0x18000abb2  mov     rcx, rsi
0x18000abb5  mov     rax, [rax+10h]
0x18000abb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000abbe  nop
0x18000abbf  test    ebx, ebx
0x18000abc1  jns     short loc_18000ABF7
0x18000abc3  mov     rcx, [rbp+18h]; this
0x18000abc7  mov     r9d, ebx; char *
0x18000abca  lea     r8, aAvcoreMidi2Tra; "avcore\\midi2\\transport\\midisrvtransp"...
0x18000abd1  mov     edx, 21h ; '!'; void *
0x18000abd6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000abdb  nop
0x18000abdc  mov     rcx, [rbp+arg_10]
0x18000abe0  test    rcx, rcx
0x18000abe3  jz      short loc_18000ABF2
0x18000abe5  mov     rax, [rcx]
0x18000abe8  mov     rax, [rax+10h]
0x18000abec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000abf1  nop
0x18000abf2  jmp     loc_18000AAB5
0x18000abf7  mov     rax, [rbp+arg_10]
0x18000abfb  mov     [rdi], rax
0x18000abfe  jmp     loc_18000B06D
0x18000ac03  mov     rax, qword ptr cs:_GUID_f328d645_7d6d_4924_a7e3_9dee245189f9.Data1
0x18000ac0a  cmp     rax, [rdx]
0x18000ac0d  jnz     loc_18000AD4A
0x18000ac13  mov     rax, qword ptr cs:_GUID_f328d645_7d6d_4924_a7e3_9dee245189f9.Data4
0x18000ac1a  cmp     rax, [rdx+8]
0x18000ac1e  jnz     loc_18000AD4A
0x18000ac24  call    ?Instance@MidiSrvTransportTelemetryProvider@@KAPEAV1@XZ; MidiSrvTransportTelemetryProvider::Instance(void)
0x18000ac29  mov     rcx, [rax+8]
0x18000ac2d  mov     eax, [rcx]
0x18000ac2f  cmp     eax, 4
0x18000ac32  jbe     short loc_18000AC76
0x18000ac34  lea     rax, aImidiout; "IMidiOut"
0x18000ac3b  mov     [rbp+arg_18], rax
0x18000ac3f  mov     qword ptr [rbp+var_8], rbx
0x18000ac43  lea     rax, aCmidi2midisrvt; "CMidi2MidiSrvTransport::Activate"
0x18000ac4a  mov     qword ptr [rbp+var_10], rax
0x18000ac4e  lea     rax, [rbp+arg_18]
0x18000ac52  mov     [rsp+50h+var_20], rax
0x18000ac57  lea     rax, [rbp+var_8]
0x18000ac5b  mov     [rsp+50h+var_28], rax
0x18000ac60  lea     rax, [rbp+var_10]
0x18000ac64  mov     qword ptr [rsp+50h+var_30], rax; int
0x18000ac69  lea     rdx, byte_180019E05
0x18000ac70  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x18000ac75  nop
0x18000ac76  mov     [rbp+arg_10], 0
0x18000ac7e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000ac85  mov     ecx, 18h; unsigned __int64
0x18000ac8a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000ac8f  mov     rsi, rax
0x18000ac92  test    rax, rax
0x18000ac95  jnz     short loc_18000AC9E
0x18000ac97  mov     ebx, 8007000Eh
0x18000ac9c  jmp     short loc_18000AD0A
0x18000ac9e  mov     dword ptr [rax+0Ch], 1
0x18000aca5  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIMidiOut@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMidiOut>::`vftable'
0x18000acac  mov     [rsi], rax
0x18000acaf  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000acb6  test    rcx, rcx
0x18000acb9  jz      short loc_18000ACC8
0x18000acbb  mov     rax, [rcx]
0x18000acbe  mov     rax, [rax+8]
0x18000acc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000acc7  nop
0x18000acc8  lea     rax, ??_7CMidi2MidiSrvOut@@6B@; const CMidi2MidiSrvOut::`vftable'
0x18000accf  mov     [rsi], rax
0x18000acd2  mov     qword ptr [rsi+10h], 0
0x18000acda  lea     r8, [rbp+arg_10]
0x18000acde  lea     rdx, _GUID_f328d645_7d6d_4924_a7e3_9dee245189f9
0x18000ace5  mov     rcx, rsi
0x18000ace8  mov     rax, cs:??_7CMidi2MidiSrvOut@@6B@; const CMidi2MidiSrvOut::`vftable'
0x18000acef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000acf4  mov     ebx, eax
0x18000acf6  mov     rax, [rsi]
0x18000acf9  mov     rcx, rsi
0x18000acfc  mov     rax, [rax+10h]
0x18000ad00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad05  nop
0x18000ad06  test    ebx, ebx
0x18000ad08  jns     short loc_18000AD3E
0x18000ad0a  mov     rcx, [rbp+18h]; this
0x18000ad0e  mov     r9d, ebx; char *
0x18000ad11  lea     r8, aAvcoreMidi2Tra; "avcore\\midi2\\transport\\midisrvtransp"...
0x18000ad18  mov     edx, 30h ; '0'; void *
0x18000ad1d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ad22  nop
0x18000ad23  mov     rcx, [rbp+arg_10]
0x18000ad27  test    rcx, rcx
0x18000ad2a  jz      short loc_18000AD39
0x18000ad2c  mov     rdx, [rcx]
0x18000ad2f  mov     rax, [rdx+10h]
0x18000ad33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad38  nop
0x18000ad39  jmp     loc_18000AAB5
0x18000ad3e  mov     rax, [rbp+arg_10]
0x18000ad42  mov     [rdi], rax
0x18000ad45  jmp     loc_18000B06D
0x18000ad4a  mov     rax, qword ptr cs:_GUID_b89bbb45_7001_4bea_bbd8_c7cc26e7836c.Data1
0x18000ad51  cmp     rax, [rdx]
0x18000ad54  jnz     loc_18000AE14
0x18000ad5a  mov     rax, qword ptr cs:_GUID_b89bbb45_7001_4bea_bbd8_c7cc26e7836c.Data4
0x18000ad61  cmp     rax, [rdx+8]
0x18000ad65  jnz     loc_18000AE14
0x18000ad6b  call    ?Instance@MidiSrvTransportTelemetryProvider@@KAPEAV1@XZ; MidiSrvTransportTelemetryProvider::Instance(void)
0x18000ad70  mov     rcx, [rax+8]
0x18000ad74  mov     eax, [rcx]
0x18000ad76  cmp     eax, 4
0x18000ad79  jbe     short loc_18000ADBD
0x18000ad7b  lea     rax, aImidibidirecti; "IMidiBidirectional"
0x18000ad82  mov     [rbp+arg_18], rax
0x18000ad86  mov     qword ptr [rbp+var_8], rbx
0x18000ad8a  lea     rax, aCmidi2midisrvt; "CMidi2MidiSrvTransport::Activate"
0x18000ad91  mov     qword ptr [rbp+var_10], rax
0x18000ad95  lea     rax, [rbp+arg_18]
0x18000ad99  mov     [rsp+50h+var_20], rax
0x18000ad9e  lea     rax, [rbp+var_8]
0x18000ada2  mov     [rsp+50h+var_28], rax
0x18000ada7  lea     rax, [rbp+var_10]
0x18000adab  mov     qword ptr [rsp+50h+var_30], rax; int
0x18000adb0  lea     rdx, byte_180019DD1
0x18000adb7  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x18000adbc  nop
0x18000adbd  mov     [rbp+arg_10], 0
0x18000adc5  lea     rcx, [rbp+arg_10]
0x18000adc9  call    ??$MakeAndInitialize@VCMidi2MidiSrvBidi@@UIMidiBidirectional@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIMidiBidirectional@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CMidi2MidiSrvBidi,IMidiBidirectional,>(IMidiBidirectional * *)
0x18000adce  mov     ebx, eax
0x18000add0  test    eax, eax
0x18000add2  jns     short loc_18000AE08
0x18000add4  mov     rcx, [rbp+18h]; this
0x18000add8  mov     r9d, eax; char *
0x18000addb  lea     r8, aAvcoreMidi2Tra; "avcore\\midi2\\transport\\midisrvtransp"...
0x18000ade2  mov     edx, 3Fh ; '?'; void *
0x18000ade7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000adec  nop
0x18000aded  mov     rcx, [rbp+arg_10]
0x18000adf1  test    rcx, rcx
0x18000adf4  jz      short loc_18000AE03
0x18000adf6  mov     rax, [rcx]
0x18000adf9  mov     rax, [rax+10h]
0x18000adfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae02  nop
0x18000ae03  jmp     loc_18000AAB5
0x18000ae08  mov     rax, [rbp+arg_10]
0x18000ae0c  mov     [rdi], rax
0x18000ae0f  jmp     loc_18000B06D
0x18000ae14  mov     rax, qword ptr cs:_GUID_f19dd642_1809_4497_9eee_f230b11bd6fb.Data1
0x18000ae1b  cmp     rax, [rdx]
0x18000ae1e  jnz     loc_18000AEDE
0x18000ae24  mov     rax, qword ptr cs:_GUID_f19dd642_1809_4497_9eee_f230b11bd6fb.Data4
0x18000ae2b  cmp     rax, [rdx+8]
0x18000ae2f  jnz     loc_18000AEDE
0x18000ae35  call    ?Instance@MidiSrvTransportTelemetryProvider@@KAPEAV1@XZ; MidiSrvTransportTelemetryProvider::Instance(void)
0x18000ae3a  mov     rcx, [rax+8]
0x18000ae3e  mov     eax, [rcx]
0x18000ae40  cmp     eax, 4
0x18000ae43  jbe     short loc_18000AE87
0x18000ae45  lea     rax, aImiditransport; "IMidiTransportConfigurationManager"
0x18000ae4c  mov     [rbp+arg_18], rax
0x18000ae50  mov     qword ptr [rbp+var_8], rbx
0x18000ae54  lea     rax, aCmidi2midisrvt; "CMidi2MidiSrvTransport::Activate"
0x18000ae5b  mov     qword ptr [rbp+var_10], rax
0x18000ae5f  lea     rax, [rbp+arg_18]
0x18000ae63  mov     [rsp+50h+var_20], rax
0x18000ae68  lea     rax, [rbp+var_8]
0x18000ae6c  mov     [rsp+50h+var_28], rax
0x18000ae71  lea     rax, [rbp+var_10]
0x18000ae75  mov     qword ptr [rsp+50h+var_30], rax; int
0x18000ae7a  lea     rdx, byte_180019D9D
0x18000ae81  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x18000ae86  nop
0x18000ae87  mov     [rbp+arg_10], 0
0x18000ae8f  lea     rcx, [rbp+arg_10]
0x18000ae93  call    ??$MakeAndInitialize@VCMidi2MidiSrvConfigurationManager@@UIMidiTransportConfigurationManager@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIMidiTransportConfigurationManager@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CMidi2MidiSrvConfigurationManager,IMidiTransportConfigurationManager,>(IMidiTransportConfigurationManager * *)
0x18000ae98  mov     ebx, eax
0x18000ae9a  test    eax, eax
0x18000ae9c  jns     short loc_18000AED2
0x18000ae9e  mov     rcx, [rbp+18h]; this
0x18000aea2  mov     r9d, eax; char *
0x18000aea5  lea     r8, aAvcoreMidi2Tra; "avcore\\midi2\\transport\\midisrvtransp"...
0x18000aeac  mov     edx, 4Eh ; 'N'; void *
0x18000aeb1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000aeb6  nop
0x18000aeb7  mov     rcx, [rbp+arg_10]
0x18000aebb  test    rcx, rcx
0x18000aebe  jz      short loc_18000AECD
0x18000aec0  mov     rax, [rcx]
0x18000aec3  mov     rax, [rax+10h]
0x18000aec7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aecc  nop
0x18000aecd  jmp     loc_18000AAB5
0x18000aed2  mov     rax, [rbp+arg_10]
0x18000aed6  mov     [rdi], rax
0x18000aed9  jmp     loc_18000B06D
0x18000aede  mov     rax, qword ptr cs:_GUID_469c7722_f779_40c3_b648_52620f75dcee.Data1
0x18000aee5  cmp     rax, [rdx]
0x18000aee8  jnz     loc_18000AFA8
0x18000aeee  mov     rax, qword ptr cs:_GUID_469c7722_f779_40c3_b648_52620f75dcee.Data4
0x18000aef5  cmp     rax, [rdx+8]
0x18000aef9  jnz     loc_18000AFA8
0x18000aeff  call    ?Instance@MidiSrvTransportTelemetryProvider@@KAPEAV1@XZ; MidiSrvTransportTelemetryProvider::Instance(void)
0x18000af04  mov     rcx, [rax+8]
0x18000af08  mov     eax, [rcx]
0x18000af0a  cmp     eax, 4
0x18000af0d  jbe     short loc_18000AF51
0x18000af0f  lea     rax, aImidiservicepl; "IMidiServicePluginMetadataReporter"
0x18000af16  mov     [rbp+arg_18], rax
0x18000af1a  mov     qword ptr [rbp+var_8], rbx
0x18000af1e  lea     rax, aCmidi2midisrvt; "CMidi2MidiSrvTransport::Activate"
0x18000af25  mov     qword ptr [rbp+var_10], rax
0x18000af29  lea     rax, [rbp+arg_18]
0x18000af2d  mov     [rsp+50h+var_20], rax
0x18000af32  lea     rax, [rbp+var_8]
0x18000af36  mov     [rsp+50h+var_28], rax
0x18000af3b  lea     rax, [rbp+var_10]
0x18000af3f  mov     qword ptr [rsp+50h+var_30], rax; int
0x18000af44  lea     rdx, byte_180019D69
0x18000af4b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x18000af50  nop
0x18000af51  mov     [rbp+arg_10], 0
0x18000af59  lea     rcx, [rbp+arg_10]
0x18000af5d  call    ??$MakeAndInitialize@VCMidi2MidiSrvConfigurationManager@@UIMidiServicePluginMetadataReporter@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIMidiServicePluginMetadataReporter@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CMidi2MidiSrvConfigurationManager,IMidiServicePluginMetadataReporter,>(IMidiServicePluginMetadataReporter * *)
0x18000af62  mov     ebx, eax
0x18000af64  test    eax, eax
0x18000af66  jns     short loc_18000AF9C
0x18000af68  mov     rcx, [rbp+18h]; this
  ... truncated ...
```
