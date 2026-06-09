# CMidi2KSAggregateMidiOutProxy::Callback(__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004,void *,uint,__int64,__int64)

- ea: `0x180045460`
- end: `0x1800456d3`
- name: `?Callback@CMidi2KSAggregateMidiOutProxy@@UEAAJW4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004@@PEAXI_J2@Z`
- size: `627`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, installer_update`

## callees

- `0x180001e28`
- `0x18000b394`
- `0x1800117d8`
- `0x180019924`
- `0x180045460`
- `0x180047b58`
- `0x18004aa70`
- `0x180058858`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800455a0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180045603`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800455a0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180045603`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18004556d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18004556d`

## pseudocode

```c
__int64 __fastcall CMidi2KSAggregateMidiOutProxy::Callback(
        __int64 a1,
        unsigned int a2,
        void *a3,
        unsigned int a4,
        __int64 a5)
{
  unsigned int v9; // ebx
  __int64 v10; // rdx
  struct MidiKSAggregateTransportTelemetryProvider *v12; // rax
  int v13; // r8d
  int v14; // r9d
  __int64 v15; // r15
  _DWORD *v16; // rcx
  __int64 v17; // rbx
  RTL_SRWLOCK *v18; // rdi
  __int64 v19; // rdx
  __int64 v20; // rcx
  int v21; // eax
  __int64 v22; // rdx
  __int64 v23; // rcx
  int v24; // eax
  __int64 v25; // rdx
  int v26; // [rsp+20h] [rbp-49h]
  unsigned int v27; // [rsp+60h] [rbp-9h] BYREF
  __int64 v28; // [rsp+68h] [rbp-1h] BYREF
  void *v29; // [rsp+70h] [rbp+7h] BYREF
  const wchar_t *v30; // [rsp+78h] [rbp+Fh] BYREF
  __int64 v31; // [rsp+80h] [rbp+17h] BYREF
  int v32[2]; // [rsp+88h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+4Fh]
  unsigned int v34; // [rsp+D0h] [rbp+67h] BYREF

  if ( !a3 )
  {
    v9 = -2147024809;
    v10 = 191;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"avcore\\midi2\\transport\\ksaggregatetransport\\midi2.ksaggregatemidioutproxy.cpp",
      (const char *)v9,
      v26);
    return v9;
  }
  if ( !*(_QWORD *)(a1 + 64) )
  {
    v9 = -2147467261;
    v10 = 192;
    goto LABEL_3;
  }
  v12 = MidiKSAggregateTransportTelemetryProvider::Instance();
  v15 = a5;
  v16 = (_DWORD *)*((_QWORD *)v12 + 1);
  if ( *v16 > 5u )
  {
    v28 = a5;
    v30 = L"MidiOut callback received from translation. Sending data to device.";
    v34 = a4;
    *(_QWORD *)v32 = "CMidi2KSAggregateMidiOutProxy::Callback";
    v29 = a3;
    v27 = a2;
    v31 = a1;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      (_DWORD)v16,
      (unsigned int)&dword_18008B234,
      v13,
      v14,
      (__int64)v32,
      (__int64)&v31,
      (__int64)&v30,
      (__int64)&v27,
      (__int64)&v29,
      (__int64)&v34,
      (__int64)&v28);
  }
  v17 = *(_QWORD *)(a1 + 64);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::GetImpl'::`2'::impl) )
  {
    v18 = (RTL_SRWLOCK *)(v17 + 8);
    AcquireSRWLockShared((PSRWLOCK)(v17 + 8));
    if ( !a4 )
    {
      v9 = -2147024809;
      v19 = 629;
      goto LABEL_11;
    }
    if ( *(_BYTE *)(v17 + 20) )
    {
      v9 = -2147024890;
      v19 = 630;
LABEL_11:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v19,
        (unsigned int)"avcore\\midi2\\libs\\midiks\\midiks.cpp",
        (const char *)v9,
        v26);
      if ( v18 )
        ReleaseSRWLockShared(v18);
      goto LABEL_32;
    }
    v20 = *(_QWORD *)(v17 + 88);
    if ( v20 )
    {
      v26 = v15;
      v21 = CMidiXProc::SendMidiMessage(v20, a2, a3, a4);
      v9 = v21;
      if ( v21 >= 0 )
        goto LABEL_19;
      v22 = 635;
    }
    else
    {
      v21 = KSMidiOutDevice::WritePacketMidiData((KSMidiOutDevice *)v17, a3, a4, v15);
      v9 = v21;
      if ( v21 >= 0 )
      {
LABEL_19:
        if ( v18 )
          ReleaseSRWLockShared(v18);
        goto LABEL_31;
      }
      v22 = 642;
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v22,
      (unsigned int)"avcore\\midi2\\libs\\midiks\\midiks.cpp",
      (const char *)(unsigned int)v21,
      v26);
    goto LABEL_19;
  }
  if ( !a4 )
  {
    v9 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x289,
      (unsigned int)"avcore\\midi2\\libs\\midiks\\midiks.cpp",
      (const char *)0x80070057LL,
      v26);
LABEL_32:
    v10 = 223;
    goto LABEL_3;
  }
  v23 = *(_QWORD *)(v17 + 88);
  if ( v23 )
  {
    v26 = v15;
    v24 = CMidiXProc::SendMidiMessage(v23, a2, a3, a4);
    v9 = v24;
    if ( v24 >= 0 )
      goto LABEL_31;
    v25 = 654;
  }
  else
  {
    v24 = KSMidiOutDevice::WritePacketMidiData((KSMidiOutDevice *)v17, a3, a4, v15);
    v9 = v24;
    if ( v24 >= 0 )
      goto LABEL_31;
    v25 = 661;
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)v25,
    (unsigned int)"avcore\\midi2\\libs\\midiks\\midiks.cpp",
    (const char *)(unsigned int)v24,
    v26);
LABEL_31:
  if ( (v9 & 0x80000000) != 0 )
    goto LABEL_32;
  return 0;
}

```

## disassembly

```asm
0x180045460  mov     [rsp-8+arg_0], rbx
0x180045465  mov     [rsp-8+arg_8], rsi
0x18004546a  push    rbp
0x18004546b  push    rdi
0x18004546c  push    r12
0x18004546e  push    r14
0x180045470  push    r15
0x180045472  lea     rbp, [rsp-27h]
0x180045477  sub     rsp, 90h
0x18004547e  mov     esi, r9d
0x180045481  mov     r14, r8
0x180045484  mov     r12d, edx
0x180045487  mov     rbx, rcx
0x18004548a  test    r8, r8
0x18004548d  jnz     short loc_1800454B3
0x18004548f  mov     ebx, 80070057h
0x180045494  mov     edx, 0BFh; void *
0x180045499  mov     rcx, [rbp+4Fh]; this
0x18004549d  lea     r8, aAvcoreMidi2Tra_5; "avcore\\midi2\\transport\\ksaggregatetr"...
0x1800454a4  mov     r9d, ebx; char *
0x1800454a7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800454ac  mov     eax, ebx
0x1800454ae  jmp     loc_1800456B7
0x1800454b3  cmp     qword ptr [rcx+40h], 0
0x1800454b8  jnz     short loc_1800454C6
0x1800454ba  mov     ebx, 80004003h
0x1800454bf  mov     edx, 0C0h
0x1800454c4  jmp     short loc_180045499
0x1800454c6  call    ?Instance@MidiKSAggregateTransportTelemetryProvider@@KAPEAV1@XZ; MidiKSAggregateTransportTelemetryProvider::Instance(void)
0x1800454cb  mov     r15, [rbp+47h+arg_20]
0x1800454cf  mov     rcx, [rax+8]
0x1800454d3  mov     eax, [rcx]
0x1800454d5  cmp     eax, 5
0x1800454d8  jbe     short loc_18004554E
0x1800454da  lea     rax, aMidioutCallbac; "MidiOut callback received from translat"...
0x1800454e1  mov     [rbp+47h+var_48], r15
0x1800454e5  mov     [rbp+47h+var_38], rax
0x1800454e9  lea     rdx, dword_18008B234
0x1800454f0  lea     rax, aCmidi2ksaggreg_39; "CMidi2KSAggregateMidiOutProxy::Callback"
0x1800454f7  mov     [rbp+47h+arg_10], esi
0x1800454fa  mov     qword ptr [rbp+47h+var_28], rax
0x1800454fe  lea     rax, [rbp+47h+var_48]
0x180045502  mov     [rsp+0B0h+var_60], rax
0x180045507  lea     rax, [rbp+47h+arg_10]
0x18004550b  mov     [rsp+0B0h+var_68], rax
0x180045510  lea     rax, [rbp+47h+var_40]
0x180045514  mov     [rsp+0B0h+var_70], rax
0x180045519  lea     rax, [rbp+47h+var_50]
0x18004551d  mov     [rsp+0B0h+var_78], rax
0x180045522  lea     rax, [rbp+47h+var_38]
0x180045526  mov     [rsp+0B0h+var_80], rax
0x18004552b  lea     rax, [rbp+47h+var_30]
0x18004552f  mov     [rsp+0B0h+var_88], rax
0x180045534  lea     rax, [rbp+47h+var_28]
0x180045538  mov     qword ptr [rsp+0B0h+var_90], rax; int
0x18004553d  mov     [rbp+47h+var_40], r14
0x180045541  mov     [rbp+47h+var_50], r12d
0x180045545  mov     [rbp+47h+var_30], rbx
0x180045549  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U2@U4@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@464@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18004554e  mov     rbx, [rbx+40h]
0x180045552  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval> `wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::GetImpl(void)'::`2'::impl
0x180045559  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::__private_IsEnabled(void)
0x18004555e  test    al, al
0x180045560  jz      loc_18004562C
0x180045566  lea     rdi, [rbx+8]
0x18004556a  mov     rcx, rdi; SRWLock
0x18004556d  call    cs:__imp_AcquireSRWLockShared
0x180045573  test    esi, esi
0x180045575  jnz     short loc_1800455AB
0x180045577  mov     ebx, 80070057h
0x18004557c  mov     edx, 275h; void *
0x180045581  mov     rcx, [rbp+4Fh]; this
0x180045585  lea     r8, aAvcoreMidi2Lib; "avcore\\midi2\\libs\\midiks\\midiks.cpp"
0x18004558c  mov     r9d, ebx; char *
0x18004558f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045594  test    rdi, rdi
0x180045597  jz      loc_1800456AB
0x18004559d  mov     rcx, rdi; SRWLock
0x1800455a0  call    cs:__imp_ReleaseSRWLockShared
0x1800455a6  jmp     loc_1800456AB
0x1800455ab  cmp     byte ptr [rbx+14h], 0
0x1800455af  jz      short loc_1800455BD
0x1800455b1  mov     ebx, 80070006h
0x1800455b6  mov     edx, 276h
0x1800455bb  jmp     short loc_180045581
0x1800455bd  mov     rcx, [rbx+58h]
0x1800455c1  test    rcx, rcx
0x1800455c4  jz      short loc_18004560E
0x1800455c6  mov     r9d, esi
0x1800455c9  mov     qword ptr [rsp+0B0h+var_90], r15; int
0x1800455ce  mov     r8, r14
0x1800455d1  mov     edx, r12d
0x1800455d4  call    ?SendMidiMessage@CMidiXProc@@QEAAJW4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004@@PEAXI_J@Z; CMidiXProc::SendMidiMessage(__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004,void *,uint,__int64)
0x1800455d9  mov     ebx, eax
0x1800455db  test    eax, eax
0x1800455dd  jns     short loc_1800455F7
0x1800455df  mov     edx, 27Bh; void *
0x1800455e4  mov     rcx, [rbp+4Fh]; this
0x1800455e8  lea     r8, aAvcoreMidi2Lib; "avcore\\midi2\\libs\\midiks\\midiks.cpp"
0x1800455ef  mov     r9d, eax; char *
0x1800455f2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800455f7  test    rdi, rdi
0x1800455fa  jz      loc_1800456A7
0x180045600  mov     rcx, rdi; SRWLock
0x180045603  call    cs:__imp_ReleaseSRWLockShared
0x180045609  jmp     loc_1800456A7
0x18004560e  mov     r9, r15; __int64
0x180045611  mov     r8d, esi; unsigned int
0x180045614  mov     rdx, r14; void *
0x180045617  mov     rcx, rbx; this
0x18004561a  call    ?WritePacketMidiData@KSMidiOutDevice@@AEAAJPEAXI_J@Z; KSMidiOutDevice::WritePacketMidiData(void *,uint,__int64)
0x18004561f  mov     ebx, eax
0x180045621  test    eax, eax
0x180045623  jns     short loc_1800455F7
0x180045625  mov     edx, 282h
0x18004562a  jmp     short loc_1800455E4
0x18004562c  test    esi, esi
0x18004562e  jnz     short loc_18004564F
0x180045630  mov     rcx, [rbp+4Fh]; this
0x180045634  lea     r8, aAvcoreMidi2Lib; "avcore\\midi2\\libs\\midiks\\midiks.cpp"
0x18004563b  mov     ebx, 80070057h
0x180045640  mov     edx, 289h; void *
0x180045645  mov     r9d, ebx; char *
0x180045648  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004564d  jmp     short loc_1800456AB
0x18004564f  mov     rcx, [rbx+58h]
0x180045653  test    rcx, rcx
0x180045656  jz      short loc_180045678
0x180045658  mov     r9d, esi
0x18004565b  mov     qword ptr [rsp+0B0h+var_90], r15
0x180045660  mov     r8, r14
0x180045663  mov     edx, r12d
0x180045666  call    ?SendMidiMessage@CMidiXProc@@QEAAJW4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004@@PEAXI_J@Z; CMidiXProc::SendMidiMessage(__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004,void *,uint,__int64)
0x18004566b  mov     ebx, eax
0x18004566d  test    eax, eax
0x18004566f  jns     short loc_1800456A7
0x180045671  mov     edx, 28Eh
0x180045676  jmp     short loc_180045694
0x180045678  mov     r9, r15; __int64
0x18004567b  mov     r8d, esi; unsigned int
0x18004567e  mov     rdx, r14; void *
0x180045681  mov     rcx, rbx; this
0x180045684  call    ?WritePacketMidiData@KSMidiOutDevice@@AEAAJPEAXI_J@Z; KSMidiOutDevice::WritePacketMidiData(void *,uint,__int64)
0x180045689  mov     ebx, eax
0x18004568b  test    eax, eax
0x18004568d  jns     short loc_1800456A7
0x18004568f  mov     edx, 295h; void *
0x180045694  mov     rcx, [rbp+4Fh]; this
0x180045698  lea     r8, aAvcoreMidi2Lib; "avcore\\midi2\\libs\\midiks\\midiks.cpp"
0x18004569f  mov     r9d, eax; char *
0x1800456a2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800456a7  test    ebx, ebx
0x1800456a9  jns     short loc_1800456B5
0x1800456ab  mov     edx, 0DFh
0x1800456b0  jmp     loc_180045499
0x1800456b5  xor     eax, eax
0x1800456b7  lea     r11, [rsp+0B0h+var_20]
0x1800456bf  mov     rbx, [r11+30h]
0x1800456c3  mov     rsi, [r11+38h]
0x1800456c7  mov     rsp, r11
0x1800456ca  pop     r15
0x1800456cc  pop     r14
0x1800456ce  pop     r12
0x1800456d0  pop     rdi
0x1800456d1  pop     rbp
0x1800456d2  retn
```
