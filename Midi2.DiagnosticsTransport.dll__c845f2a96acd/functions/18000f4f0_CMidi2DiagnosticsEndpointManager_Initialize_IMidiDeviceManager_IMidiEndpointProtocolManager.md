# CMidi2DiagnosticsEndpointManager::Initialize(IMidiDeviceManager *,IMidiEndpointProtocolManager *)

- ea: `0x18000f4f0`
- end: `0x18000f7ce`
- name: `?Initialize@CMidi2DiagnosticsEndpointManager@@UEAAJPEAUIMidiDeviceManager@@PEAUIMidiEndpointProtocolManager@@@Z`
- size: `734`
- prototype: `__int64 __fastcall(CMidi2DiagnosticsEndpointManager *__hidden this, struct IMidiDeviceManager *, struct IMidiEndpointProtocolManager *)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1800016dc`
- `0x180008f64`
- `0x18000add8`
- `0x18000c4c0`
- `0x18000ccf8`
- `0x18000d0b4`
- `0x18000d31c`
- `0x18000f4f0`
- `0x180010078`
- `0x180013010`

## string_xrefs

- `0x18000f619`: `Service Test Loopback A`
- `0x18000f6a6`: `Service Test Loopback B`
- `0x18000f736`: `Service Test Ping (Internal)`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMidi2DiagnosticsEndpointManager::Initialize(
        CMidi2DiagnosticsEndpointManager *this,
        __int64 (__fastcall ***a2)(struct IMidiDeviceManager *, GUID *, char *),
        struct IMidiEndpointProtocolManager *a3)
{
  _DWORD *v5; // rcx
  int v6; // r8d
  int v7; // r9d
  int v8; // ebx
  __int64 v9; // rdx
  __int64 (__fastcall *v11)(struct IMidiDeviceManager *, GUID *, char *); // r14
  __int64 v12; // rcx
  int ParentDevice; // edi
  __int64 v14; // rdx
  int v15; // [rsp+20h] [rbp-29h]
  __int128 v16; // [rsp+30h] [rbp-19h] BYREF
  __int128 v17; // [rsp+40h] [rbp-9h]
  __int128 v18; // [rsp+50h] [rbp+7h] BYREF
  __int128 v19; // [rsp+60h] [rbp+17h]
  __int128 v20; // [rsp+70h] [rbp+27h] BYREF
  __int128 v21; // [rsp+80h] [rbp+37h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]
  CMidi2DiagnosticsEndpointManager *v23; // [rsp+B8h] [rbp+6Fh] BYREF
  const char *v24; // [rsp+C8h] [rbp+7Fh] BYREF

  v5 = (_DWORD *)*((_QWORD *)MidiDiagnosticsTransportTelemetryProvider::Instance() + 1);
  if ( *v5 > 4u )
  {
    v23 = this;
    v24 = "CMidi2DiagnosticsEndpointManager::Initialize";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      (_DWORD)v5,
      (unsigned int)qword_180016DE0,
      v6,
      v7,
      (__int64)&v24,
      (__int64)&v23);
  }
  if ( !a2 )
  {
    v8 = -2147024809;
    v9 = 39;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"avcore\\midi2\\transport\\diagnosticstransport\\midi2.diagnosticsendpointmanager.cpp",
      (const char *)(unsigned int)v8,
      v15);
    return (unsigned int)v8;
  }
  v11 = **a2;
  v12 = *((_QWORD *)this + 6);
  *((_QWORD *)this + 6) = 0;
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  ParentDevice = v11((struct IMidiDeviceManager *)a2, &GUID_a04374d3_4514_44e1_a2f9_7d8b907aef1f, (char *)this + 48);
  if ( ParentDevice < 0 )
  {
    v14 = 41;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"avcore\\midi2\\transport\\diagnosticstransport\\midi2.diagnosticsendpointmanager.cpp",
      (const char *)(unsigned int)ParentDevice,
      v15);
    return (unsigned int)ParentDevice;
  }
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2ContainerIds>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2ContainerIds>::GetImpl'::`2'::impl) )
    *((_OWORD *)this + 1) = *((_OWORD *)this + 2);
  ParentDevice = CMidi2DiagnosticsEndpointManager::CreateParentDevice(this);
  if ( ParentDevice < 0 )
  {
    v14 = 50;
    goto LABEL_10;
  }
  v16 = 0;
  v17 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v16, L"Service Test Loopback A", 23);
  v18 = 0;
  v19 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v18, L"LOOPBACK_A", 10);
  v20 = 0;
  v21 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v20, L"MIDIU_DIAG_LOOPBACK_A", 21);
  ParentDevice = CMidi2DiagnosticsEndpointManager::CreateLoopbackEndpoint((__int64)this, &v20, &v18, &v16);
  if ( ParentDevice < 0 )
  {
    v14 = 52;
    goto LABEL_10;
  }
  v20 = 0;
  v21 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v20, L"Service Test Loopback B", 23);
  v18 = 0;
  v19 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v18, L"LOOPBACK_B", 10);
  v16 = 0;
  v17 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v16, L"MIDIU_DIAG_LOOPBACK_B", 21);
  ParentDevice = CMidi2DiagnosticsEndpointManager::CreateLoopbackEndpoint((__int64)this, &v16, &v18, &v20);
  if ( ParentDevice < 0 )
  {
    v14 = 53;
    goto LABEL_10;
  }
  v20 = 0;
  v21 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v20, L"Service Test Ping (Internal)", 28);
  v18 = 0;
  v19 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v18, L"PING", 4);
  v16 = 0;
  v17 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v16, L"MIDIU_DIAG_PING", 15);
  v8 = CMidi2DiagnosticsEndpointManager::CreatePingEndpoint((__int64)this, &v16, &v18, &v20);
  if ( v8 < 0 )
  {
    v9 = 55;
    goto LABEL_5;
  }
  return 0;
}

```

## disassembly

```asm
0x18000f4f0  mov     [rsp-8+arg_0], rbx
0x18000f4f5  mov     [rsp-8+arg_10], rsi
0x18000f4fa  push    rbp
0x18000f4fb  push    rdi
0x18000f4fc  push    r14
0x18000f4fe  lea     rbp, [rsp-47h]
0x18000f503  sub     rsp, 90h
0x18000f50a  mov     rdi, rdx
0x18000f50d  mov     rbx, rcx
0x18000f510  call    ?Instance@MidiDiagnosticsTransportTelemetryProvider@@KAPEAV1@XZ; MidiDiagnosticsTransportTelemetryProvider::Instance(void)
0x18000f515  mov     rcx, [rax+8]
0x18000f519  mov     eax, [rcx]
0x18000f51b  cmp     eax, 4
0x18000f51e  jbe     short loc_18000F54D
0x18000f520  mov     [rbp+57h+arg_8], rbx
0x18000f524  lea     rax, aCmidi2diagnost_6; "CMidi2DiagnosticsEndpointManager::Initi"...
0x18000f52b  mov     [rbp+57h+arg_18], rax
0x18000f52f  lea     rax, [rbp+57h+arg_8]
0x18000f533  mov     [rsp+0A0h+var_78], rax
0x18000f538  lea     rax, [rbp+57h+arg_18]
0x18000f53c  mov     qword ptr [rsp+0A0h+var_80], rax; int
0x18000f541  lea     rdx, qword_180016DE0
0x18000f548  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18000f54d  test    rdi, rdi
0x18000f550  jnz     short loc_18000F574
0x18000f552  mov     ebx, 80070057h
0x18000f557  lea     edx, [rdi+27h]; void *
0x18000f55a  lea     r8, aAvcoreMidi2Tra_3; "avcore\\midi2\\transport\\diagnosticstr"...
0x18000f561  mov     r9d, ebx; char *
0x18000f564  mov     rcx, [rbp+5Fh]; this
0x18000f568  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f56d  mov     eax, ebx
0x18000f56f  jmp     loc_18000F7B6
0x18000f574  mov     rax, [rdi]
0x18000f577  mov     r14, [rax]
0x18000f57a  lea     rsi, [rbx+30h]
0x18000f57e  mov     rcx, [rsi]
0x18000f581  mov     qword ptr [rsi], 0
0x18000f588  test    rcx, rcx
0x18000f58b  jz      short loc_18000F59A
0x18000f58d  mov     rdx, [rcx]
0x18000f590  mov     rax, [rdx+10h]
0x18000f594  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f599  nop
0x18000f59a  mov     r8, rsi
0x18000f59d  lea     rdx, _GUID_a04374d3_4514_44e1_a2f9_7d8b907aef1f
0x18000f5a4  mov     rcx, rdi
0x18000f5a7  mov     rax, r14
0x18000f5aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f5af  mov     edi, eax
0x18000f5b1  test    eax, eax
0x18000f5b3  jns     short loc_18000F5D4
0x18000f5b5  mov     edx, 29h ; ')'; void *
0x18000f5ba  lea     r8, aAvcoreMidi2Tra_3; "avcore\\midi2\\transport\\diagnosticstr"...
0x18000f5c1  mov     r9d, edi; char *
0x18000f5c4  mov     rcx, [rbp+5Fh]; this
0x18000f5c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f5cd  mov     eax, edi
0x18000f5cf  jmp     loc_18000F7B6
0x18000f5d4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_MIDI2ContainerIds@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2ContainerIds@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2ContainerIds> `wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2ContainerIds>::GetImpl(void)'::`2'::impl
0x18000f5db  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2ContainerIds@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2ContainerIds>::__private_IsEnabled(void)
0x18000f5e0  test    al, al
0x18000f5e2  jnz     short loc_18000F5ED
0x18000f5e4  movups  xmm0, xmmword ptr [rbx+20h]
0x18000f5e8  movdqu  xmmword ptr [rbx+10h], xmm0
0x18000f5ed  mov     rcx, rbx; this
0x18000f5f0  call    ?CreateParentDevice@CMidi2DiagnosticsEndpointManager@@AEAAJXZ; CMidi2DiagnosticsEndpointManager::CreateParentDevice(void)
0x18000f5f5  mov     edi, eax
0x18000f5f7  test    eax, eax
0x18000f5f9  jns     short loc_18000F602
0x18000f5fb  mov     edx, 32h ; '2'
0x18000f600  jmp     short loc_18000F5BA
0x18000f602  xorps   xmm0, xmm0
0x18000f605  movups  [rbp+57h+var_70], xmm0
0x18000f609  xorps   xmm1, xmm1
0x18000f60c  movdqu  [rbp+57h+var_60], xmm1
0x18000f611  mov     esi, 17h
0x18000f616  mov     r8d, esi
0x18000f619  lea     rdx, aServiceTestLoo; "Service Test Loopback A"
0x18000f620  lea     rcx, [rbp+57h+var_70]
0x18000f624  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000f629  xorps   xmm0, xmm0
0x18000f62c  movups  [rbp+57h+var_50], xmm0
0x18000f630  xorps   xmm1, xmm1
0x18000f633  movdqu  [rbp+57h+var_40], xmm1
0x18000f638  lea     r14d, [rsi-0Dh]
0x18000f63c  mov     r8d, r14d
0x18000f63f  lea     rdx, aLoopbackA; "LOOPBACK_A"
0x18000f646  lea     rcx, [rbp+57h+var_50]
0x18000f64a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000f64f  xorps   xmm0, xmm0
0x18000f652  movups  [rbp+57h+var_30], xmm0
0x18000f656  xorps   xmm1, xmm1
0x18000f659  movdqu  [rbp+57h+var_20], xmm1
0x18000f65e  lea     r8d, [rsi-2]
0x18000f662  lea     rdx, aMidiuDiagLoopb_0; "MIDIU_DIAG_LOOPBACK_A"
0x18000f669  lea     rcx, [rbp+57h+var_30]
0x18000f66d  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000f672  lea     r9, [rbp+57h+var_70]
0x18000f676  lea     r8, [rbp+57h+var_50]
0x18000f67a  lea     rdx, [rbp+57h+var_30]
0x18000f67e  mov     rcx, rbx
0x18000f681  call    ?CreateLoopbackEndpoint@CMidi2DiagnosticsEndpointManager@@AEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00W4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0002@@@Z; CMidi2DiagnosticsEndpointManager::CreateLoopbackEndpoint(std::wstring,std::wstring,std::wstring,__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0002)
0x18000f686  mov     edi, eax
0x18000f688  test    eax, eax
0x18000f68a  jns     short loc_18000F694
0x18000f68c  lea     edx, [rsi+1Dh]
0x18000f68f  jmp     loc_18000F5BA
0x18000f694  xorps   xmm0, xmm0
0x18000f697  movups  [rbp+57h+var_30], xmm0
0x18000f69b  xorps   xmm1, xmm1
0x18000f69e  movdqu  [rbp+57h+var_20], xmm1
0x18000f6a3  mov     r8, rsi
0x18000f6a6  lea     rdx, aServiceTestLoo_0; "Service Test Loopback B"
0x18000f6ad  lea     rcx, [rbp+57h+var_30]
0x18000f6b1  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000f6b6  xorps   xmm0, xmm0
0x18000f6b9  movups  [rbp+57h+var_50], xmm0
0x18000f6bd  xorps   xmm1, xmm1
0x18000f6c0  movdqu  [rbp+57h+var_40], xmm1
0x18000f6c5  mov     r8, r14
0x18000f6c8  lea     rdx, aLoopbackB; "LOOPBACK_B"
0x18000f6cf  lea     rcx, [rbp+57h+var_50]
0x18000f6d3  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000f6d8  xorps   xmm0, xmm0
0x18000f6db  movups  [rbp+57h+var_70], xmm0
0x18000f6df  xorps   xmm1, xmm1
0x18000f6e2  movdqu  [rbp+57h+var_60], xmm1
0x18000f6e7  mov     r8d, 15h
0x18000f6ed  lea     rdx, aMidiuDiagLoopb; "MIDIU_DIAG_LOOPBACK_B"
0x18000f6f4  lea     rcx, [rbp+57h+var_70]
0x18000f6f8  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000f6fd  lea     r9, [rbp+57h+var_30]
0x18000f701  lea     r8, [rbp+57h+var_50]
0x18000f705  lea     rdx, [rbp+57h+var_70]
0x18000f709  mov     rcx, rbx
0x18000f70c  call    ?CreateLoopbackEndpoint@CMidi2DiagnosticsEndpointManager@@AEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00W4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0002@@@Z; CMidi2DiagnosticsEndpointManager::CreateLoopbackEndpoint(std::wstring,std::wstring,std::wstring,__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0002)
0x18000f711  mov     edi, eax
0x18000f713  test    eax, eax
0x18000f715  jns     short loc_18000F721
0x18000f717  mov     edx, 35h ; '5'
0x18000f71c  jmp     loc_18000F5BA
0x18000f721  xorps   xmm0, xmm0
0x18000f724  movups  [rbp+57h+var_30], xmm0
0x18000f728  xorps   xmm1, xmm1
0x18000f72b  movdqu  [rbp+57h+var_20], xmm1
0x18000f730  mov     r8d, 1Ch
0x18000f736  lea     rdx, aServiceTestPin; "Service Test Ping (Internal)"
0x18000f73d  lea     rcx, [rbp+57h+var_30]
0x18000f741  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000f746  xorps   xmm0, xmm0
0x18000f749  movups  [rbp+57h+var_50], xmm0
0x18000f74d  xorps   xmm1, xmm1
0x18000f750  movdqu  [rbp+57h+var_40], xmm1
0x18000f755  mov     r8d, 4
0x18000f75b  lea     rdx, aPing; "PING"
0x18000f762  lea     rcx, [rbp+57h+var_50]
0x18000f766  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000f76b  xorps   xmm0, xmm0
0x18000f76e  movups  [rbp+57h+var_70], xmm0
0x18000f772  xorps   xmm1, xmm1
0x18000f775  movdqu  [rbp+57h+var_60], xmm1
0x18000f77a  mov     r8d, 0Fh
0x18000f780  lea     rdx, aMidiuDiagPing; "MIDIU_DIAG_PING"
0x18000f787  lea     rcx, [rbp+57h+var_70]
0x18000f78b  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000f790  lea     r9, [rbp+57h+var_30]
0x18000f794  lea     r8, [rbp+57h+var_50]
0x18000f798  lea     rdx, [rbp+57h+var_70]
0x18000f79c  mov     rcx, rbx
0x18000f79f  call    ?CreatePingEndpoint@CMidi2DiagnosticsEndpointManager@@AEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00W4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0002@@@Z; CMidi2DiagnosticsEndpointManager::CreatePingEndpoint(std::wstring,std::wstring,std::wstring,__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0002)
0x18000f7a4  mov     ebx, eax
0x18000f7a6  test    eax, eax
0x18000f7a8  jns     short loc_18000F7B4
0x18000f7aa  mov     edx, 37h ; '7'
0x18000f7af  jmp     loc_18000F55A
0x18000f7b4  xor     eax, eax
0x18000f7b6  lea     r11, [rsp+0A0h+var_10]
0x18000f7be  mov     rbx, [r11+20h]
0x18000f7c2  mov     rsi, [r11+30h]
0x18000f7c6  mov     rsp, r11
0x18000f7c9  pop     r14
0x18000f7cb  pop     rdi
0x18000f7cc  pop     rbp
0x18000f7cd  retn
```
