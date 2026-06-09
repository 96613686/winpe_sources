# CMidi2VirtualMidiEndpointManager::Initialize(IMidiDeviceManager *,IMidiEndpointProtocolManager *)

- ea: `0x180010b50`
- end: `0x180010cce`
- name: `?Initialize@CMidi2VirtualMidiEndpointManager@@UEAAJPEAUIMidiDeviceManager@@PEAUIMidiEndpointProtocolManager@@@Z`
- size: `382`
- prototype: `__int64 __fastcall(CMidi2VirtualMidiEndpointManager *__hidden this, struct IMidiDeviceManager *, struct IMidiEndpointProtocolManager *)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800017d0`
- `0x180009784`
- `0x18000b5f8`
- `0x18000e840`
- `0x180010b50`
- `0x180011a7c`
- `0x180021010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMidi2VirtualMidiEndpointManager::Initialize(
        CMidi2VirtualMidiEndpointManager *this,
        __int64 (__fastcall ***a2)(struct IMidiDeviceManager *, GUID *, char *),
        __int64 (__fastcall ***a3)(struct IMidiEndpointProtocolManager *, GUID *, char *))
{
  _DWORD *v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 v9; // rdx
  int ParentDevice; // ebx
  __int64 (__fastcall *v12)(struct IMidiDeviceManager *, GUID *, char *); // rbp
  __int64 v13; // rcx
  int v14; // edi
  __int64 v15; // rdx
  __int64 (__fastcall *v16)(struct IMidiEndpointProtocolManager *, GUID *, char *); // rsi
  __int64 v17; // rcx
  int v18; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  CMidi2VirtualMidiEndpointManager *v20; // [rsp+58h] [rbp+10h] BYREF
  const char *v21; // [rsp+68h] [rbp+20h] BYREF

  v6 = (_DWORD *)*((_QWORD *)MidiVirtualMidiTransportTelemetryProvider::Instance() + 1);
  if ( *v6 > 4u )
  {
    v20 = this;
    v21 = "CMidi2VirtualMidiEndpointManager::Initialize";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      (__int64)v6,
      (unsigned __int8 *)&dword_1800268E4,
      v7,
      v8,
      (const unsigned __int16 **)&v21,
      (__int64)&v20);
  }
  if ( !a2 )
  {
    v9 = 40;
LABEL_5:
    ParentDevice = -2147024809;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"avcore\\midi2\\transport\\virtualmiditransport\\midi2.virtualmidiendpointmanager.cpp",
      (const char *)(unsigned int)ParentDevice,
      v18);
    return (unsigned int)ParentDevice;
  }
  if ( !a3 )
  {
    v9 = 41;
    goto LABEL_5;
  }
  v12 = **a2;
  v13 = *((_QWORD *)this + 8);
  *((_QWORD *)this + 8) = 0;
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  v14 = v12((struct IMidiDeviceManager *)a2, &GUID_a04374d3_4514_44e1_a2f9_7d8b907aef1f, (char *)this + 64);
  if ( v14 < 0 )
  {
    v15 = 43;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"avcore\\midi2\\transport\\virtualmiditransport\\midi2.virtualmidiendpointmanager.cpp",
      (const char *)(unsigned int)v14,
      v18);
    return (unsigned int)v14;
  }
  v16 = **a3;
  v17 = *((_QWORD *)this + 9);
  *((_QWORD *)this + 9) = 0;
  if ( v17 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  v14 = v16((struct IMidiEndpointProtocolManager *)a3, &GUID_7a3def20_fb76_49b6_a3a0_3dcbcda8f482, (char *)this + 72);
  if ( v14 < 0 )
  {
    v15 = 44;
    goto LABEL_13;
  }
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2ContainerIds>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2ContainerIds>::GetImpl'::`2'::impl) )
    *((GUID *)this + 1) = GUID_8feaad91_70e1_4a19_997a_377720a719c1;
  ParentDevice = CMidi2VirtualMidiEndpointManager::CreateParentDevice(this);
  if ( ParentDevice < 0 )
  {
    v9 = 54;
    goto LABEL_6;
  }
  return 0;
}

```

## disassembly

```asm
0x180010b50  mov     [rsp+arg_0], rbx
0x180010b55  mov     [rsp+arg_10], rbp
0x180010b5a  push    rsi
0x180010b5b  push    rdi
0x180010b5c  push    r14
0x180010b5e  sub     rsp, 30h
0x180010b62  mov     r14, r8
0x180010b65  mov     rdi, rdx
0x180010b68  mov     rbx, rcx
0x180010b6b  call    ?Instance@MidiVirtualMidiTransportTelemetryProvider@@KAPEAV1@XZ; MidiVirtualMidiTransportTelemetryProvider::Instance(void)
0x180010b70  mov     rcx, [rax+8]
0x180010b74  mov     eax, [rcx]
0x180010b76  cmp     eax, 4
0x180010b79  jbe     short loc_180010BAC
0x180010b7b  mov     [rsp+48h+arg_8], rbx
0x180010b80  lea     rax, aCmidi2virtualm_12; "CMidi2VirtualMidiEndpointManager::Initi"...
0x180010b87  mov     [rsp+48h+arg_18], rax
0x180010b8c  lea     rax, [rsp+48h+arg_8]
0x180010b91  mov     [rsp+48h+var_20], rax
0x180010b96  lea     rax, [rsp+48h+arg_18]
0x180010b9b  mov     qword ptr [rsp+48h+var_28], rax; int
0x180010ba0  lea     rdx, dword_1800268E4
0x180010ba7  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x180010bac  test    rdi, rdi
0x180010baf  jnz     short loc_180010BD4
0x180010bb1  lea     edx, [rdi+28h]; void *
0x180010bb4  mov     ebx, 80070057h
0x180010bb9  mov     rcx, [rsp+48h]; this
0x180010bbe  mov     r9d, ebx; char *
0x180010bc1  lea     r8, aAvcoreMidi2Tra_4; "avcore\\midi2\\transport\\virtualmiditr"...
0x180010bc8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010bcd  mov     eax, ebx
0x180010bcf  jmp     loc_180010CBB
0x180010bd4  test    r14, r14
0x180010bd7  jnz     short loc_180010BDF
0x180010bd9  lea     edx, [r14+29h]
0x180010bdd  jmp     short loc_180010BB4
0x180010bdf  mov     rax, [rdi]
0x180010be2  mov     rbp, [rax]
0x180010be5  lea     rsi, [rbx+40h]
0x180010be9  mov     rcx, [rsi]
0x180010bec  mov     qword ptr [rsi], 0
0x180010bf3  test    rcx, rcx
0x180010bf6  jz      short loc_180010C05
0x180010bf8  mov     rdx, [rcx]
0x180010bfb  mov     rax, [rdx+10h]
0x180010bff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c04  nop
0x180010c05  mov     r8, rsi
0x180010c08  lea     rdx, _GUID_a04374d3_4514_44e1_a2f9_7d8b907aef1f
0x180010c0f  mov     rcx, rdi
0x180010c12  mov     rax, rbp
0x180010c15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c1a  mov     edi, eax
0x180010c1c  test    eax, eax
0x180010c1e  jns     short loc_180010C3D
0x180010c20  mov     edx, 2Bh ; '+'; void *
0x180010c25  lea     r8, aAvcoreMidi2Tra_4; "avcore\\midi2\\transport\\virtualmiditr"...
0x180010c2c  mov     r9d, edi; char *
0x180010c2f  mov     rcx, [rsp+48h]; this
0x180010c34  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010c39  mov     eax, edi
0x180010c3b  jmp     short loc_180010CBB
0x180010c3d  mov     rax, [r14]
0x180010c40  mov     rsi, [rax]
0x180010c43  lea     rdi, [rbx+48h]
0x180010c47  mov     rcx, [rdi]
0x180010c4a  mov     qword ptr [rdi], 0
0x180010c51  test    rcx, rcx
0x180010c54  jz      short loc_180010C63
0x180010c56  mov     rdx, [rcx]
0x180010c59  mov     rax, [rdx+10h]
0x180010c5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c62  nop
0x180010c63  mov     r8, rdi
0x180010c66  lea     rdx, _GUID_7a3def20_fb76_49b6_a3a0_3dcbcda8f482
0x180010c6d  mov     rcx, r14
0x180010c70  mov     rax, rsi
0x180010c73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c78  mov     edi, eax
0x180010c7a  test    eax, eax
0x180010c7c  jns     short loc_180010C85
0x180010c7e  mov     edx, 2Ch ; ','
0x180010c83  jmp     short loc_180010C25
0x180010c85  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_MIDI2ContainerIds@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2ContainerIds@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2ContainerIds> `wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2ContainerIds>::GetImpl(void)'::`2'::impl
0x180010c8c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2ContainerIds@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2ContainerIds>::__private_IsEnabled(void)
0x180010c91  test    al, al
0x180010c93  jnz     short loc_180010CA1
0x180010c95  movups  xmm0, xmmword ptr cs:_GUID_8feaad91_70e1_4a19_997a_377720a719c1.Data1
0x180010c9c  movdqu  xmmword ptr [rbx+10h], xmm0
0x180010ca1  mov     rcx, rbx; this
0x180010ca4  call    ?CreateParentDevice@CMidi2VirtualMidiEndpointManager@@AEAAJXZ; CMidi2VirtualMidiEndpointManager::CreateParentDevice(void)
0x180010ca9  mov     ebx, eax
0x180010cab  test    eax, eax
0x180010cad  jns     short loc_180010CB9
0x180010caf  mov     edx, 36h ; '6'
0x180010cb4  jmp     loc_180010BB9
0x180010cb9  xor     eax, eax
0x180010cbb  mov     rbx, [rsp+48h+arg_0]
0x180010cc0  mov     rbp, [rsp+48h+arg_10]
0x180010cc5  add     rsp, 30h
0x180010cc9  pop     r14
0x180010ccb  pop     rdi
0x180010ccc  pop     rsi
0x180010ccd  retn
```
