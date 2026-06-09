# CMidi2LoopbackMidiEndpointManager::Initialize(IMidiDeviceManager *,IMidiEndpointProtocolManager *)

- ea: `0x180020170`
- end: `0x180020323`
- name: `?Initialize@CMidi2LoopbackMidiEndpointManager@@UEAAJPEAUIMidiDeviceManager@@PEAUIMidiEndpointProtocolManager@@@Z`
- size: `435`
- prototype: `__int64 __fastcall(CMidi2LoopbackMidiEndpointManager *__hidden this, struct IMidiDeviceManager *, struct IMidiEndpointProtocolManager *)`
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180001a38`
- `0x18000a024`
- `0x18000ccd8`
- `0x18001b624`
- `0x18001d188`
- `0x180020170`
- `0x1800203c8`
- `0x180021328`
- `0x180032010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMidi2LoopbackMidiEndpointManager::Initialize(
        CMidi2LoopbackMidiEndpointManager *this,
        __int64 (__fastcall ***a2)(struct IMidiDeviceManager *, GUID *, char *),
        __int64 (__fastcall ***a3)(struct IMidiEndpointProtocolManager *, GUID *, char *))
{
  _DWORD *v6; // rcx
  int v7; // r8d
  int v8; // r9d
  __int64 v9; // rdx
  __int64 (__fastcall *v11)(struct IMidiDeviceManager *, GUID *, char *); // rbp
  __int64 v12; // rcx
  int ParentDevice; // edi
  __int64 v14; // rdx
  __int64 (__fastcall *v15)(struct IMidiEndpointProtocolManager *, GUID *, char *); // rsi
  __int64 v16; // rcx
  int v17; // eax
  int v18; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  CMidi2LoopbackMidiEndpointManager *v20; // [rsp+58h] [rbp+10h] BYREF
  const char *v21; // [rsp+68h] [rbp+20h] BYREF

  v6 = (_DWORD *)*((_QWORD *)MidiLoopbackMidiTransportTelemetryProvider::Instance() + 1);
  if ( *v6 > 4u )
  {
    v20 = this;
    v21 = "CMidi2LoopbackMidiEndpointManager::Initialize";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      (_DWORD)v6,
      (unsigned int)byte_18005884D,
      v7,
      v8,
      (__int64)&v21,
      (__int64)&v20);
  }
  if ( !a2 )
  {
    v9 = 40;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"avcore\\midi2\\transport\\loopbackmiditransport\\midi2.loopbackmidiendpointmanager.cpp",
      (const char *)0x80070057LL,
      v18);
    return 2147942487LL;
  }
  if ( !a3 )
  {
    v9 = 41;
    goto LABEL_5;
  }
  v11 = **a2;
  v12 = *((_QWORD *)this + 11);
  *((_QWORD *)this + 11) = 0;
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  ParentDevice = v11((struct IMidiDeviceManager *)a2, &GUID_a04374d3_4514_44e1_a2f9_7d8b907aef1f, (char *)this + 88);
  if ( ParentDevice < 0 )
  {
    v14 = 43;
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"avcore\\midi2\\transport\\loopbackmiditransport\\midi2.loopbackmidiendpointmanager.cpp",
      (const char *)(unsigned int)ParentDevice,
      v18);
    return (unsigned int)ParentDevice;
  }
  v15 = **a3;
  v16 = *((_QWORD *)this + 12);
  *((_QWORD *)this + 12) = 0;
  if ( v16 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  ParentDevice = v15(
                   (struct IMidiEndpointProtocolManager *)a3,
                   &GUID_7a3def20_fb76_49b6_a3a0_3dcbcda8f482,
                   (char *)this + 96);
  if ( ParentDevice < 0 )
  {
    v14 = 44;
    goto LABEL_12;
  }
  *(GUID *)((char *)this + 36) = TransportLayerGUID;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2ContainerIds>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2ContainerIds>::GetImpl'::`2'::impl) )
    *(_OWORD *)((char *)this + 20) = *(_OWORD *)((char *)this + 36);
  ParentDevice = CMidi2LoopbackMidiEndpointManager::CreateParentDevice(this);
  if ( ParentDevice < 0 )
  {
    v14 = 56;
    goto LABEL_12;
  }
  *((_BYTE *)this + 16) = 1;
  v17 = CMidi2LoopbackMidiEndpointManager::ProcessWorkQueue(this);
  if ( v17 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x3D,
      (unsigned int)"avcore\\midi2\\transport\\loopbackmiditransport\\midi2.loopbackmidiendpointmanager.cpp",
      (const char *)(unsigned int)v17,
      v18);
  return 0;
}

```

## disassembly

```asm
0x180020170  mov     [rsp+arg_0], rbx
0x180020175  mov     [rsp+arg_10], rbp
0x18002017a  push    rsi
0x18002017b  push    rdi
0x18002017c  push    r14
0x18002017e  sub     rsp, 30h
0x180020182  mov     r14, r8
0x180020185  mov     rdi, rdx
0x180020188  mov     rbx, rcx
0x18002018b  call    ?Instance@MidiLoopbackMidiTransportTelemetryProvider@@KAPEAV1@XZ; MidiLoopbackMidiTransportTelemetryProvider::Instance(void)
0x180020190  mov     rcx, [rax+8]
0x180020194  mov     eax, [rcx]
0x180020196  cmp     eax, 4
0x180020199  jbe     short loc_1800201CC
0x18002019b  mov     [rsp+48h+arg_8], rbx
0x1800201a0  lea     rax, aCmidi2loopback_4; "CMidi2LoopbackMidiEndpointManager::Init"...
0x1800201a7  mov     [rsp+48h+arg_18], rax
0x1800201ac  lea     rax, [rsp+48h+arg_8]
0x1800201b1  mov     [rsp+48h+var_20], rax
0x1800201b6  lea     rax, [rsp+48h+arg_18]
0x1800201bb  mov     qword ptr [rsp+48h+var_28], rax; int
0x1800201c0  lea     rdx, byte_18005884D
0x1800201c7  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x1800201cc  test    rdi, rdi
0x1800201cf  jnz     short loc_1800201F4
0x1800201d1  lea     edx, [rdi+28h]; void *
0x1800201d4  mov     ebx, 80070057h
0x1800201d9  lea     r8, aAvcoreMidi2Tra; "avcore\\midi2\\transport\\loopbackmidit"...
0x1800201e0  mov     r9d, ebx; char *
0x1800201e3  mov     rcx, [rsp+48h]; this
0x1800201e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800201ed  mov     eax, ebx
0x1800201ef  jmp     loc_180020310
0x1800201f4  test    r14, r14
0x1800201f7  jnz     short loc_1800201FF
0x1800201f9  lea     edx, [r14+29h]
0x1800201fd  jmp     short loc_1800201D4
0x1800201ff  mov     rax, [rdi]
0x180020202  mov     rbp, [rax]
0x180020205  lea     rsi, [rbx+58h]
0x180020209  mov     rcx, [rsi]
0x18002020c  mov     qword ptr [rsi], 0
0x180020213  test    rcx, rcx
0x180020216  jz      short loc_180020225
0x180020218  mov     rdx, [rcx]
0x18002021b  mov     rax, [rdx+10h]
0x18002021f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020224  nop
0x180020225  mov     r8, rsi
0x180020228  lea     rdx, _GUID_a04374d3_4514_44e1_a2f9_7d8b907aef1f
0x18002022f  mov     rcx, rdi
0x180020232  mov     rax, rbp
0x180020235  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002023a  mov     edi, eax
0x18002023c  test    eax, eax
0x18002023e  jns     short loc_180020260
0x180020240  mov     edx, 2Bh ; '+'; void *
0x180020245  mov     rcx, [rsp+48h]; this
0x18002024a  mov     r9d, edi; char *
0x18002024d  lea     r8, aAvcoreMidi2Tra; "avcore\\midi2\\transport\\loopbackmidit"...
0x180020254  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020259  mov     eax, edi
0x18002025b  jmp     loc_180020310
0x180020260  mov     rax, [r14]
0x180020263  mov     rsi, [rax]
0x180020266  lea     rdi, [rbx+60h]
0x18002026a  mov     rcx, [rdi]
0x18002026d  mov     qword ptr [rdi], 0
0x180020274  test    rcx, rcx
0x180020277  jz      short loc_180020286
0x180020279  mov     rdx, [rcx]
0x18002027c  mov     rax, [rdx+10h]
0x180020280  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020285  nop
0x180020286  mov     r8, rdi
0x180020289  lea     rdx, _GUID_7a3def20_fb76_49b6_a3a0_3dcbcda8f482
0x180020290  mov     rcx, r14
0x180020293  mov     rax, rsi
0x180020296  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002029b  mov     edi, eax
0x18002029d  test    eax, eax
0x18002029f  jns     short loc_1800202A8
0x1800202a1  mov     edx, 2Ch ; ','
0x1800202a6  jmp     short loc_180020245
0x1800202a8  movups  xmm0, xmmword ptr cs:?TransportLayerGUID@@3U_GUID@@A.Data1; _GUID TransportLayerGUID ...
0x1800202af  movdqu  xmmword ptr [rbx+24h], xmm0
0x1800202b4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_MIDI2ContainerIds@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2ContainerIds@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2ContainerIds> `wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2ContainerIds>::GetImpl(void)'::`2'::impl
0x1800202bb  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2ContainerIds@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2ContainerIds>::__private_IsEnabled(void)
0x1800202c0  test    al, al
0x1800202c2  jnz     short loc_1800202CD
0x1800202c4  movups  xmm0, xmmword ptr [rbx+24h]
0x1800202c8  movdqu  xmmword ptr [rbx+14h], xmm0
0x1800202cd  mov     rcx, rbx; this
0x1800202d0  call    ?CreateParentDevice@CMidi2LoopbackMidiEndpointManager@@AEAAJXZ; CMidi2LoopbackMidiEndpointManager::CreateParentDevice(void)
0x1800202d5  mov     edi, eax
0x1800202d7  test    eax, eax
0x1800202d9  jns     short loc_1800202E5
0x1800202db  mov     edx, 38h ; '8'
0x1800202e0  jmp     loc_180020245
0x1800202e5  mov     byte ptr [rbx+10h], 1
0x1800202e9  mov     rcx, rbx; this
0x1800202ec  call    ?ProcessWorkQueue@CMidi2LoopbackMidiEndpointManager@@AEAAJXZ; CMidi2LoopbackMidiEndpointManager::ProcessWorkQueue(void)
0x1800202f1  test    eax, eax
0x1800202f3  jns     short loc_18002030E
0x1800202f5  mov     rcx, [rsp+48h]; this
0x1800202fa  mov     r9d, eax; char *
0x1800202fd  lea     r8, aAvcoreMidi2Tra; "avcore\\midi2\\transport\\loopbackmidit"...
0x180020304  mov     edx, 3Dh ; '='; void *
0x180020309  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002030e  xor     eax, eax
0x180020310  mov     rbx, [rsp+48h+arg_0]
0x180020315  mov     rbp, [rsp+48h+arg_10]
0x18002031a  add     rsp, 30h
0x18002031e  pop     r14
0x180020320  pop     rdi
0x180020321  pop     rsi
0x180020322  retn
```
