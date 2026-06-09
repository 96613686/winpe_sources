# CMidiEndpointProtocolWorker::Shutdown(void)

- ea: `0x1400435a0`
- end: `0x140043717`
- name: `?Shutdown@CMidiEndpointProtocolWorker@@UEAAJXZ`
- size: `375`
- prototype: `__int64 __fastcall(CMidiEndpointProtocolWorker *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x140001ce8`
- `0x14000984c`
- `0x14000c598`
- `0x14001e990`
- `0x140037070`
- `0x1400435a0`
- `0x14005a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400436a8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400436a8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140043640`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140043640`

## string_xrefs

- `0x14004366a`: `avcore\midi2\service\exe\midiendpointprotocolworker.cpp`
- `0x1400436d4`: `avcore\midi2\service\exe\midiendpointprotocolworker.cpp`
- `0x1400435e1`: `CMidiEndpointProtocolWorker::Shutdown`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMidiEndpointProtocolWorker::Shutdown(CMidiEndpointProtocolWorker *this)
{
  _DWORD *v2; // rcx
  __int64 v3; // r8
  __int64 v4; // r9
  _QWORD *v5; // rax
  __int64 v6; // rdx
  __int64 v7; // rcx
  int v8; // eax
  __int64 v9; // rcx
  __int64 v10; // rcx
  int v11; // eax
  __int64 v12; // rcx
  int v14[2]; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  _QWORD *v16; // [rsp+68h] [rbp+10h] BYREF
  const wchar_t *v17; // [rsp+70h] [rbp+18h] BYREF
  CMidiEndpointProtocolWorker *v18; // [rsp+78h] [rbp+20h] BYREF

  v2 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v2 > 4u )
  {
    v5 = (_QWORD *)((char *)this + 56);
    if ( *((_QWORD *)this + 10) > 7u )
      v5 = (_QWORD *)*v5;
    v16 = v5;
    v17 = L"Enter";
    v18 = this;
    *(_QWORD *)v14 = "CMidiEndpointProtocolWorker::Shutdown";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (__int64)v2,
      (__int64)qword_14008C4B0,
      v3,
      v4,
      v14,
      (__int64)&v18,
      &v17,
      &v16);
  }
  CMidiEndpointProtocolWorker::EndProcessing(this);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::__private_IsEnabled(
                          `wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::GetImpl'::`2'::impl,
                          v6) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
    v7 = *((_QWORD *)this + 26);
    if ( v7 )
    {
      v8 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 32LL))(v7);
      if ( v8 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x4B4,
          (int)"avcore\\midi2\\service\\exe\\midiendpointprotocolworker.cpp",
          (const char *)(unsigned int)v8);
      v9 = *((_QWORD *)this + 26);
      *((_QWORD *)this + 26) = 0;
      if ( v9 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    }
    if ( this != (CMidiEndpointProtocolWorker *)-16LL )
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  }
  else
  {
    v10 = *((_QWORD *)this + 26);
    if ( v10 )
    {
      v11 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 32LL))(v10);
      if ( v11 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x4BC,
          (int)"avcore\\midi2\\service\\exe\\midiendpointprotocolworker.cpp",
          (const char *)(unsigned int)v11);
      v12 = *((_QWORD *)this + 26);
      *((_QWORD *)this + 26) = 0;
      if ( v12 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1400435a0  mov     [rsp+arg_0], rbx
0x1400435a5  push    rdi
0x1400435a6  sub     rsp, 50h
0x1400435aa  mov     rbx, rcx
0x1400435ad  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x1400435b2  mov     rcx, [rax+8]
0x1400435b6  mov     eax, [rcx]
0x1400435b8  cmp     eax, 4
0x1400435bb  jbe     short loc_140043621
0x1400435bd  lea     rax, [rbx+38h]
0x1400435c1  cmp     qword ptr [rax+18h], 7
0x1400435c6  jbe     short loc_1400435CB
0x1400435c8  mov     rax, [rax]
0x1400435cb  mov     [rsp+58h+arg_8], rax
0x1400435d0  lea     rax, aEnter; "Enter"
0x1400435d7  mov     [rsp+58h+arg_10], rax
0x1400435dc  mov     [rsp+58h+arg_18], rbx
0x1400435e1  lea     rax, aCmidiendpointp_18; "CMidiEndpointProtocolWorker::Shutdown"
0x1400435e8  mov     qword ptr [rsp+58h+var_18], rax
0x1400435ed  lea     rax, [rsp+58h+arg_8]
0x1400435f2  mov     [rsp+58h+var_20], rax
0x1400435f7  lea     rax, [rsp+58h+arg_10]
0x1400435fc  mov     [rsp+58h+var_28], rax
0x140043601  lea     rax, [rsp+58h+arg_18]
0x140043606  mov     [rsp+58h+var_30], rax
0x14004360b  lea     rax, [rsp+58h+var_18]
0x140043610  mov     qword ptr [rsp+58h+var_38], rax; int
0x140043615  lea     rdx, qword_14008C4B0
0x14004361c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x140043621  mov     rcx, rbx; this
0x140043624  call    ?EndProcessing@CMidiEndpointProtocolWorker@@QEAAXXZ; CMidiEndpointProtocolWorker::EndProcessing(void)
0x140043629  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval> `wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::GetImpl(void)'::`2'::impl
0x140043630  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::__private_IsEnabled(void)
0x140043635  test    al, al
0x140043637  jz      short loc_1400436B0
0x140043639  lea     rdi, [rbx+10h]
0x14004363d  mov     rcx, rdi; lpCriticalSection
0x140043640  call    cs:__imp_EnterCriticalSection
0x140043646  mov     rcx, [rbx+0D0h]
0x14004364d  test    rcx, rcx
0x140043650  jz      short loc_1400436A0
0x140043652  mov     rax, [rcx]
0x140043655  mov     rax, [rax+20h]
0x140043659  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004365e  mov     rcx, [rsp+58h]; this
0x140043663  test    eax, eax
0x140043665  jns     short loc_14004367C
0x140043667  mov     r9d, eax; char *
0x14004366a  lea     r8, aAvcoreMidi2Ser; "avcore\\midi2\\service\\exe\\midiendpoi"...
0x140043671  mov     edx, 4B4h; void *
0x140043676  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14004367b  nop
0x14004367c  mov     rcx, [rbx+0D0h]
0x140043683  mov     qword ptr [rbx+0D0h], 0
0x14004368e  test    rcx, rcx
0x140043691  jz      short loc_1400436A0
0x140043693  mov     rax, [rcx]
0x140043696  mov     rax, [rax+10h]
0x14004369a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004369f  nop
0x1400436a0  test    rdi, rdi
0x1400436a3  jz      short loc_14004370A
0x1400436a5  mov     rcx, rdi; lpCriticalSection
0x1400436a8  call    cs:__imp_LeaveCriticalSection
0x1400436ae  jmp     short loc_14004370A
0x1400436b0  mov     rcx, [rbx+0D0h]
0x1400436b7  test    rcx, rcx
0x1400436ba  jz      short loc_14004370A
0x1400436bc  mov     rax, [rcx]
0x1400436bf  mov     rax, [rax+20h]
0x1400436c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400436c8  mov     rcx, [rsp+58h]; this
0x1400436cd  test    eax, eax
0x1400436cf  jns     short loc_1400436E6
0x1400436d1  mov     r9d, eax; char *
0x1400436d4  lea     r8, aAvcoreMidi2Ser; "avcore\\midi2\\service\\exe\\midiendpoi"...
0x1400436db  mov     edx, 4BCh; void *
0x1400436e0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1400436e5  nop
0x1400436e6  mov     rcx, [rbx+0D0h]
0x1400436ed  mov     qword ptr [rbx+0D0h], 0
0x1400436f8  test    rcx, rcx
0x1400436fb  jz      short loc_14004370A
0x1400436fd  mov     rax, [rcx]
0x140043700  mov     rax, [rax+10h]
0x140043704  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140043709  nop
0x14004370a  xor     eax, eax
0x14004370c  mov     rbx, [rsp+58h+arg_0]
0x140043711  add     rsp, 50h
0x140043715  pop     rdi
0x140043716  retn
```
