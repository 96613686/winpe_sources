# CMidi2KSAggregateMidiInProxy::Initialize(ushort const *,void *,uint,ulong,ulong *,IMidiCallback *,__int64,uchar)

- ea: `0x180043eb4`
- end: `0x180044451`
- name: `?Initialize@CMidi2KSAggregateMidiInProxy@@QEAAJPEBGPEAXIKPEAKPEAUIMidiCallback@@_JE@Z`
- size: `1437`
- prototype: `__int64 __fastcall(CMidi2KSAggregateMidiInProxy *__hidden this, const unsigned __int16 *, void *, unsigned int, unsigned int, unsigned int *, struct IMidiCallback *, __int64, char)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1800163a8`

## callees

- `0x180002a84`
- `0x180002bc0`
- `0x180002cf4`
- `0x180005020`
- `0x180005070`
- `0x180005e9c`
- `0x18000b394`
- `0x18000d430`
- `0x1800106c8`
- `0x1800117d8`
- `0x180013118`
- `0x180014194`
- `0x18001aa6c`
- `0x18001b160`
- `0x180043eb4`
- `0x180044458`
- `0x180049100`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800442cf`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800442cf`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CMidi2KSAggregateMidiInProxy::Initialize(
        CMidi2KSAggregateMidiInProxy *this,
        const unsigned __int16 *a2,
        void *a3,
        int a4,
        unsigned int a5,
        unsigned int *a6,
        struct IMidiCallback *a7,
        __int64 a8,
        char a9)
{
  _DWORD *v12; // rcx
  int v13; // r8d
  int v14; // r9d
  _DWORD *v15; // rcx
  int v16; // r8d
  int v17; // r9d
  __int64 v18; // r8
  __int64 v19; // rax
  wchar_t *v20; // rbx
  __int64 v21; // rcx
  __int64 v22; // rcx
  unsigned int v23; // ebx
  __int64 v24; // rdx
  struct _GUID *v26; // rdx
  _DWORD *v27; // r8
  int v28; // r9d
  __int64 v29; // rcx
  int IsComponentPermitted; // eax
  LPVOID v31; // rcx
  HRESULT v32; // eax
  LPVOID v33; // r14
  __int64 (__fastcall *v34)(LPVOID, GUID *, char *); // r12
  __int64 v35; // rcx
  int v36; // eax
  unsigned int v37; // r14d
  int v38; // eax
  LPVOID *ppv; // [rsp+20h] [rbp-E0h]
  int ppva; // [rsp+20h] [rbp-E0h]
  LPVOID *ppvb; // [rsp+20h] [rbp-E0h]
  _BYTE v42[4]; // [rsp+50h] [rbp-B0h] BYREF
  int v43; // [rsp+54h] [rbp-ACh] BYREF
  LPVOID v44; // [rsp+58h] [rbp-A8h] BYREF
  const wchar_t *v45; // [rsp+60h] [rbp-A0h] BYREF
  int v46[2]; // [rsp+68h] [rbp-98h] BYREF
  CMidi2KSAggregateMidiInProxy *v47; // [rsp+70h] [rbp-90h] BYREF
  const unsigned __int16 *v48; // [rsp+78h] [rbp-88h] BYREF
  GUID rguid; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v50[32]; // [rsp+90h] [rbp-70h] BYREF
  int v51; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v52; // [rsp+B4h] [rbp-4Ch]
  __int128 v53; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v54; // [rsp+D0h] [rbp-30h]
  __int64 v55; // [rsp+D8h] [rbp-28h]
  IID rclsid; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v57[32]; // [rsp+F0h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  *(_QWORD *)&rguid.Data1 = a3;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix>::GetImpl'::`2'::impl) )
  {
    v12 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
    if ( *v12 > 4u )
    {
      v42[0] = a9;
      v43 = a4;
      v48 = a2;
      *(_QWORD *)v46 = L"Enter";
      v47 = this;
      v45 = (const wchar_t *)"CMidi2KSAggregateMidiInProxy::Initialize";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(
        (_DWORD)v12,
        (unsigned int)byte_18008B04B,
        v13,
        v14,
        (__int64)&v45,
        (__int64)&v47,
        (__int64)v46,
        (__int64)&v48,
        (__int64)&v43,
        (__int64)v42);
    }
  }
  else
  {
    v15 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
    if ( *v15 > 4u )
    {
      v42[0] = a9;
      v43 = a4;
      v45 = a2;
      v47 = this;
      *(_QWORD *)v46 = "CMidi2KSAggregateMidiInProxy::Initialize";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(
        (_DWORD)v15,
        (unsigned int)byte_18008AFE9,
        v16,
        v17,
        (__int64)v46,
        (__int64)&v47,
        (__int64)&v45,
        (__int64)&v43,
        (__int64)v42);
    }
  }
  *((_QWORD *)this + 8) = a7;
  *((_QWORD *)this + 10) = a8;
  *((_BYTE *)this + 88) = a9;
  v53 = 0;
  v54 = 0;
  v55 = 0;
  v18 = -1;
  do
    ++v18;
  while ( a2[v18] );
  std::wstring::_Construct<1,unsigned short const *>(&v53);
  v19 = std::wstring::wstring(v50, &v53);
  WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(v57, v19);
  std::wstring::operator=((char *)this + 16, v57);
  std::wstring::~wstring(v57);
  std::wstring::~wstring(&v53);
  _InterlockedExchange64((volatile __int64 *)this + 6, 0);
  v20 = (wchar_t *)operator new(0xA8u);
  v45 = v20;
  memset_0(v20, 0, 0xA8u);
  *((_QWORD *)v20 + 1) = 0;
  *((_DWORD *)v20 + 4) = 1;
  *((_BYTE *)v20 + 20) = 0;
  *((_QWORD *)v20 + 3) = 0;
  *((_QWORD *)v20 + 4) = 0;
  *((_QWORD *)v20 + 5) = 0;
  *((_QWORD *)v20 + 6) = 0;
  *((_QWORD *)v20 + 7) = 0;
  *((_QWORD *)v20 + 8) = 0;
  *((_QWORD *)v20 + 9) = 0;
  *((_QWORD *)v20 + 10) = 0;
  *((_QWORD *)v20 + 11) = 0;
  *((_QWORD *)v20 + 12) = 0;
  *((_DWORD *)v20 + 26) = 0;
  *(_QWORD *)v20 = &KSMidiInDevice::`vftable';
  *((_QWORD *)v20 + 14) = 0;
  *((_QWORD *)v20 + 15) = 0;
  *((_QWORD *)v20 + 16) = 0;
  *((_QWORD *)v20 + 17) = 0;
  *((_QWORD *)v20 + 18) = 0;
  *((_DWORD *)v20 + 38) = 1;
  *((_QWORD *)v20 + 20) = 0;
  v21 = *((_QWORD *)this + 9);
  *((_QWORD *)this + 9) = v20;
  if ( v21 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v21 + 8LL))(v21, 1);
  v22 = *((_QWORD *)this + 9);
  if ( !v22 )
  {
    v23 = -2147024882;
    v24 = 67;
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v24,
      (unsigned int)"avcore\\midi2\\transport\\ksaggregatetransport\\midi2.ksaggregatemidiinproxy.cpp",
      (const char *)v23,
      (int)ppv);
    return v23;
  }
  v23 = KSMidiInDevice::Initialize(v22, a2, *(void **)&rguid.Data1, a4, (__int64)ppv, a5, a6, this, a8);
  if ( (v23 & 0x80000000) != 0 )
  {
    v27 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
    if ( *v27 > 2u )
    {
      v43 = a4;
      *(_QWORD *)&rguid.Data1 = a2;
      LODWORD(v48) = v23;
      v45 = L"Unable to initialize sub-device for input";
      v47 = this;
      *(_QWORD *)v46 = "CMidi2KSAggregateMidiInProxy::Initialize";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        (_DWORD)v27,
        (unsigned int)&unk_18008AF80,
        (_DWORD)v27,
        v28,
        (__int64)v46,
        (__int64)&v47,
        (__int64)&v45,
        (__int64)&v48,
        (__int64)&rguid,
        (__int64)&v43);
    }
    v29 = *((_QWORD *)this + 9);
    *((_QWORD *)this + 9) = 0;
    if ( v29 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v29 + 8LL))(v29, 1);
    v24 = 97;
    goto LABEL_12;
  }
  v44 = 0;
  rclsid = GUID_a8798c54_6066_45f0_9adb_648bc0641abf;
  rguid = GUID_a8798c54_6066_45f0_9adb_648bc0641abf;
  IsComponentPermitted = WindowsMidiServicesInternal::IsComponentPermitted(&rguid, v26);
  v23 = IsComponentPermitted;
  if ( IsComponentPermitted < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6B,
      (unsigned int)"avcore\\midi2\\transport\\ksaggregatetransport\\midi2.ksaggregatemidiinproxy.cpp",
      (const char *)(unsigned int)IsComponentPermitted,
      (int)ppv);
    if ( v44 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v44 + 16LL))(v44);
    return v23;
  }
  v31 = v44;
  v44 = 0;
  if ( v31 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v31 + 16LL))(v31);
  v32 = CoCreateInstance(&rclsid, 0, 0x17u, &GUID_65fa86a4_0433_4dcd_88e4_e565051cab2d, &v44);
  v23 = v32;
  if ( v32 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6D,
      (unsigned int)"avcore\\midi2\\transport\\ksaggregatetransport\\midi2.ksaggregatemidiinproxy.cpp",
      (const char *)(unsigned int)v32,
      ppva);
    if ( v44 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v44 + 16LL))(v44);
    return v23;
  }
  v33 = v44;
  v34 = *(__int64 (__fastcall **)(LPVOID, GUID *, char *))(*(_QWORD *)v44 + 24LL);
  v35 = *((_QWORD *)this + 7);
  *((_QWORD *)this + 7) = 0;
  if ( v35 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
  v36 = v34(v33, &GUID_5d2400f0_f2ee_4a51_a3be_0ac9a19c09c4, (char *)this + 56);
  v37 = v36;
  if ( v36 >= 0 )
  {
    v52 = 2;
    v51 = 1;
    BYTE4(v52) = a9;
    ppvb = (LPVOID *)*((_QWORD *)this + 8);
    v38 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, int *, unsigned int *))(**((_QWORD **)this + 7)
                                                                                             + 24LL))(
            *((_QWORD *)this + 7),
            a2,
            &v51,
            a6);
    v23 = v38;
    if ( v38 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x77,
        (unsigned int)"avcore\\midi2\\transport\\ksaggregatetransport\\midi2.ksaggregatemidiinproxy.cpp",
        (const char *)(unsigned int)v38,
        (int)ppvb);
      if ( v44 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v44 + 16LL))(v44);
      return v23;
    }
    if ( v44 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v44 + 16LL))(v44);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6F,
      (unsigned int)"avcore\\midi2\\transport\\ksaggregatetransport\\midi2.ksaggregatemidiinproxy.cpp",
      (const char *)(unsigned int)v36,
      ppva);
    if ( v44 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v44 + 16LL))(v44);
    return v37;
  }
}

```

## disassembly

```asm
0x180043eb4  push    rbp
0x180043eb6  push    rbx
0x180043eb7  push    rsi
0x180043eb8  push    rdi
0x180043eb9  push    r12
0x180043ebb  push    r13
0x180043ebd  push    r14
0x180043ebf  push    r15
0x180043ec1  lea     rbp, [rsp-28h]
0x180043ec6  sub     rsp, 128h
0x180043ecd  mov     rax, cs:__security_cookie
0x180043ed4  xor     rax, rsp
0x180043ed7  mov     [rbp+60h+var_50], rax
0x180043edb  mov     r14d, r9d
0x180043ede  mov     qword ptr [rbp+60h+rguid.Data1], r8
0x180043ee2  mov     rsi, rdx
0x180043ee5  mov     rdi, rcx
0x180043ee8  mov     r13, [rbp+60h+arg_28]
0x180043eef  xor     ebx, ebx
0x180043ef1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix> `wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix>::GetImpl(void)'::`2'::impl
0x180043ef8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix>::__private_IsEnabled(void)
0x180043efd  lea     r12, aCmidi2ksaggreg_4; "CMidi2KSAggregateMidiInProxy::Initializ"...
0x180043f04  mov     r15b, [rbp+60h+arg_40]
0x180043f0b  test    al, al
0x180043f0d  jz      loc_180043F96
0x180043f13  call    ?Instance@MidiKSAggregateTransportTelemetryProvider@@KAPEAV1@XZ; MidiKSAggregateTransportTelemetryProvider::Instance(void)
0x180043f18  mov     rcx, [rax+8]
0x180043f1c  mov     eax, [rcx]
0x180043f1e  cmp     eax, 4
0x180043f21  jbe     loc_180043FFD
0x180043f27  mov     [rsp+160h+var_110], r15b
0x180043f2c  mov     [rsp+160h+var_10C], r14d
0x180043f31  mov     [rsp+160h+var_E8], rsi
0x180043f36  lea     rax, aEnter_0; "Enter"
0x180043f3d  mov     qword ptr [rsp+160h+var_F8], rax
0x180043f42  mov     [rsp+160h+var_F0], rdi
0x180043f47  mov     [rsp+160h+var_100], r12
0x180043f4c  lea     rax, [rsp+160h+var_110]
0x180043f51  mov     [rsp+160h+var_118], rax
0x180043f56  lea     rax, [rsp+160h+var_10C]
0x180043f5b  mov     [rsp+160h+var_120], rax
0x180043f60  lea     rax, [rsp+160h+var_E8]
0x180043f65  mov     [rsp+160h+var_128], rax
0x180043f6a  lea     rax, [rsp+160h+var_F8]
0x180043f6f  mov     [rsp+160h+var_130], rax
0x180043f74  lea     rax, [rsp+160h+var_F0]
0x180043f79  mov     [rsp+160h+var_138], rax
0x180043f7e  lea     rax, [rsp+160h+var_100]
0x180043f83  mov     [rsp+160h+ppv], rax
0x180043f88  lea     rdx, byte_18008B04B
0x180043f8f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &)
0x180043f94  jmp     short loc_180043FFD
0x180043f96  call    ?Instance@MidiKSAggregateTransportTelemetryProvider@@KAPEAV1@XZ; MidiKSAggregateTransportTelemetryProvider::Instance(void)
0x180043f9b  mov     rcx, [rax+8]
0x180043f9f  mov     eax, [rcx]
0x180043fa1  cmp     eax, 4
0x180043fa4  jbe     short loc_180043FFD
0x180043fa6  mov     [rsp+160h+var_110], r15b
0x180043fab  mov     [rsp+160h+var_10C], r14d
0x180043fb0  mov     [rsp+160h+var_100], rsi
0x180043fb5  mov     [rsp+160h+var_F0], rdi
0x180043fba  mov     qword ptr [rsp+160h+var_F8], r12
0x180043fbf  lea     rax, [rsp+160h+var_110]
0x180043fc4  mov     [rsp+160h+var_120], rax
0x180043fc9  lea     rax, [rsp+160h+var_10C]
0x180043fce  mov     [rsp+160h+var_128], rax
0x180043fd3  lea     rax, [rsp+160h+var_100]
0x180043fd8  mov     [rsp+160h+var_130], rax
0x180043fdd  lea     rax, [rsp+160h+var_F0]
0x180043fe2  mov     [rsp+160h+var_138], rax
0x180043fe7  lea     rax, [rsp+160h+var_F8]
0x180043fec  mov     [rsp+160h+ppv], rax; int
0x180043ff1  lea     rdx, byte_18008AFE9
0x180043ff8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &)
0x180043ffd  mov     rax, [rbp+60h+arg_30]
0x180044004  mov     [rdi+40h], rax
0x180044008  mov     r12, [rbp+60h+arg_38]
0x18004400f  mov     [rdi+50h], r12
0x180044013  mov     [rdi+58h], r15b
0x180044017  xorps   xmm0, xmm0
0x18004401a  movups  [rbp+60h+var_A0], xmm0
0x18004401e  mov     [rbp+60h+var_90], rbx
0x180044022  mov     [rbp+60h+var_88], rbx
0x180044026  or      r8, 0FFFFFFFFFFFFFFFFh
0x18004402a  inc     r8
0x18004402d  cmp     [rsi+r8*2], bx
0x180044032  jnz     short loc_18004402A
0x180044034  mov     rdx, rsi
0x180044037  lea     rcx, [rbp+60h+var_A0]
0x18004403b  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180044040  nop
0x180044041  lea     rdx, [rbp+60h+var_A0]
0x180044045  lea     rcx, [rbp+60h+var_D0]
0x180044049  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004404e  mov     rdx, rax
0x180044051  lea     rcx, [rbp+60h+var_70]
0x180044055  call    ?ToLowerTrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(std::wstring)
0x18004405a  lea     rcx, [rdi+10h]
0x18004405e  lea     rdx, [rbp+60h+var_70]
0x180044062  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180044067  lea     rcx, [rbp+60h+var_70]; void *
0x18004406b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180044070  nop
0x180044071  lea     rcx, [rbp+60h+var_A0]; void *
0x180044075  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004407a  mov     rax, rbx
0x18004407d  xchg    rax, [rdi+30h]
0x180044081  mov     ecx, 0A8h; Size
0x180044086  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004408b  mov     rbx, rax
0x18004408e  mov     [rsp+160h+var_100], rax
0x180044093  xor     edx, edx; Val
0x180044095  mov     r8d, 0A8h; Size
0x18004409b  mov     rcx, rax; void *
0x18004409e  call    memset_0
0x1800440a3  xor     eax, eax
0x1800440a5  mov     [rbx+8], rax
0x1800440a9  lea     r8d, [rax+1]
0x1800440ad  mov     [rbx+10h], r8d
0x1800440b1  xor     edx, edx
0x1800440b3  mov     [rbx+14h], dl
0x1800440b6  mov     [rbx+18h], rdx
0x1800440ba  mov     [rbx+20h], rdx
0x1800440be  mov     [rbx+28h], rdx
0x1800440c2  mov     [rbx+30h], rdx
0x1800440c6  mov     [rbx+38h], rdx
0x1800440ca  mov     [rbx+40h], rdx
0x1800440ce  mov     [rbx+48h], rdx
0x1800440d2  mov     [rbx+50h], rdx
0x1800440d6  mov     [rbx+58h], rdx
0x1800440da  mov     [rbx+60h], rdx
0x1800440de  mov     [rbx+68h], edx
0x1800440e1  lea     rax, ??_7KSMidiInDevice@@6B@; const KSMidiInDevice::`vftable'
0x1800440e8  mov     [rbx], rax
0x1800440eb  mov     [rbx+70h], rdx
0x1800440ef  mov     [rbx+78h], rdx
0x1800440f3  mov     [rbx+80h], rdx
0x1800440fa  mov     [rbx+88h], rdx
0x180044101  mov     [rbx+90h], rdx
0x180044108  mov     [rbx+98h], r8d
0x18004410f  mov     [rbx+0A0h], rdx
0x180044116  mov     rcx, [rdi+48h]
0x18004411a  mov     [rdi+48h], rbx
0x18004411e  test    rcx, rcx
0x180044121  jz      short loc_180044132
0x180044123  mov     rax, [rcx]
0x180044126  mov     edx, r8d
0x180044129  mov     rax, [rax+8]
0x18004412d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044132  mov     rcx, [rdi+48h]
0x180044136  test    rcx, rcx
0x180044139  jnz     short loc_18004415D
0x18004413b  mov     ebx, 8007000Eh
0x180044140  lea     edx, [rcx+43h]; void *
0x180044143  lea     r8, aAvcoreMidi2Tra; "avcore\\midi2\\transport\\ksaggregatetr"...
0x18004414a  mov     r9d, ebx; char *
0x18004414d  mov     rcx, [rbp+68h]; this
0x180044151  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180044156  mov     eax, ebx
0x180044158  jmp     loc_180044431
0x18004415d  mov     [rsp+160h+var_120], r12
0x180044162  mov     [rsp+160h+var_128], rdi
0x180044167  mov     [rsp+160h+var_130], r13
0x18004416c  mov     eax, [rbp+60h+arg_20]
0x180044172  mov     dword ptr [rsp+160h+var_138], eax
0x180044176  mov     r9d, r14d
0x180044179  mov     r8, qword ptr [rbp+60h+rguid.Data1]
0x18004417d  mov     rdx, rsi
0x180044180  call    ?Initialize@KSMidiInDevice@@QEAAJPEBGPEAXIW4_MidiTransport@@KPEAKPEAUIMidiCallback@@_JW4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004@@@Z; KSMidiInDevice::Initialize(ushort const *,void *,uint,_MidiTransport,ulong,ulong *,IMidiCallback *,__int64,__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004)
0x180044185  mov     ebx, eax
0x180044187  xor     r12d, r12d
0x18004418a  test    eax, eax
0x18004418c  jns     loc_18004423F
0x180044192  call    ?Instance@MidiKSAggregateTransportTelemetryProvider@@KAPEAV1@XZ; MidiKSAggregateTransportTelemetryProvider::Instance(void)
0x180044197  mov     r8, [rax+8]
0x18004419b  mov     ecx, [r8]
0x18004419e  cmp     ecx, 2
0x1800441a1  jbe     short loc_180044217
0x1800441a3  mov     [rsp+160h+var_10C], r14d
0x1800441a8  mov     qword ptr [rbp+60h+rguid.Data1], rsi
0x1800441ac  mov     dword ptr [rsp+160h+var_E8], ebx
0x1800441b0  lea     rax, aUnableToInitia_1; "Unable to initialize sub-device for inp"...
0x1800441b7  mov     [rsp+160h+var_100], rax
0x1800441bc  mov     [rsp+160h+var_F0], rdi
0x1800441c1  lea     rax, aCmidi2ksaggreg_4; "CMidi2KSAggregateMidiInProxy::Initializ"...
0x1800441c8  mov     qword ptr [rsp+160h+var_F8], rax
0x1800441cd  lea     rax, [rsp+160h+var_10C]
0x1800441d2  mov     [rsp+160h+var_118], rax
0x1800441d7  lea     rax, [rbp+60h+rguid]
0x1800441db  mov     [rsp+160h+var_120], rax
0x1800441e0  lea     rax, [rsp+160h+var_E8]
0x1800441e5  mov     [rsp+160h+var_128], rax
0x1800441ea  lea     rax, [rsp+160h+var_100]
0x1800441ef  mov     [rsp+160h+var_130], rax
0x1800441f4  lea     rax, [rsp+160h+var_F0]
0x1800441f9  mov     [rsp+160h+var_138], rax
0x1800441fe  lea     rax, [rsp+160h+var_F8]
0x180044203  mov     [rsp+160h+ppv], rax
0x180044208  lea     rdx, unk_18008AF80
0x18004420f  mov     rcx, r8
0x180044212  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@56@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180044217  mov     rcx, [rdi+48h]
0x18004421b  mov     [rdi+48h], r12
0x18004421f  test    rcx, rcx
0x180044222  jz      short loc_180044235
0x180044224  mov     rax, [rcx]
0x180044227  mov     edx, 1
0x18004422c  mov     rax, [rax+8]
0x180044230  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044235  mov     edx, 61h ; 'a'
0x18004423a  jmp     loc_180044143
0x18004423f  mov     [rsp+160h+var_108], r12
0x180044244  movups  xmm0, xmmword ptr cs:_GUID_a8798c54_6066_45f0_9adb_648bc0641abf.Data1
0x18004424b  movaps  xmmword ptr [rbp+60h+rclsid.Data1], xmm0
0x18004424f  movdqa  xmmword ptr [rbp+60h+rguid.Data1], xmm0
0x180044254  lea     rcx, [rbp+60h+rguid]; rguid
0x180044258  call    ?IsComponentPermitted@WindowsMidiServicesInternal@@YAJU_GUID@@@Z; WindowsMidiServicesInternal::IsComponentPermitted(_GUID)
0x18004425d  mov     ebx, eax
0x18004425f  test    eax, eax
0x180044261  jns     short loc_180044298
0x180044263  mov     rcx, [rbp+68h]; this
0x180044267  mov     r9d, eax; char *
0x18004426a  lea     r8, aAvcoreMidi2Tra; "avcore\\midi2\\transport\\ksaggregatetr"...
0x180044271  mov     edx, 6Bh ; 'k'; void *
0x180044276  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004427b  nop
0x18004427c  mov     rcx, [rsp+160h+var_108]
0x180044281  test    rcx, rcx
0x180044284  jz      short loc_180044293
0x180044286  mov     rax, [rcx]
0x180044289  mov     rax, [rax+10h]
0x18004428d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044292  nop
0x180044293  jmp     loc_180044156
0x180044298  mov     rcx, [rsp+160h+var_108]
0x18004429d  mov     [rsp+160h+var_108], r12
0x1800442a2  test    rcx, rcx
0x1800442a5  jz      short loc_1800442B4
0x1800442a7  mov     rax, [rcx]
0x1800442aa  mov     rax, [rax+10h]
0x1800442ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800442b3  nop
0x1800442b4  lea     rax, [rsp+160h+var_108]
0x1800442b9  mov     [rsp+160h+ppv], rax; int
0x1800442be  lea     r9, _GUID_65fa86a4_0433_4dcd_88e4_e565051cab2d; riid
0x1800442c5  xor     edx, edx; pUnkOuter
0x1800442c7  lea     r8d, [rdx+17h]; dwClsContext
0x1800442cb  lea     rcx, [rbp+60h+rclsid]; rclsid
0x1800442cf  call    cs:__imp_CoCreateInstance
0x1800442d5  mov     ebx, eax
0x1800442d7  test    eax, eax
0x1800442d9  jns     short loc_180044310
0x1800442db  mov     rcx, [rbp+68h]; this
0x1800442df  mov     r9d, eax; char *
0x1800442e2  lea     r8, aAvcoreMidi2Tra; "avcore\\midi2\\transport\\ksaggregatetr"...
0x1800442e9  mov     edx, 6Dh ; 'm'; void *
0x1800442ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800442f3  nop
0x1800442f4  mov     rcx, [rsp+160h+var_108]
0x1800442f9  test    rcx, rcx
0x1800442fc  jz      short loc_18004430B
0x1800442fe  mov     rax, [rcx]
0x180044301  mov     rax, [rax+10h]
0x180044305  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004430a  nop
0x18004430b  jmp     loc_180044156
0x180044310  mov     r14, [rsp+160h+var_108]
0x180044315  mov     rax, [r14]
0x180044318  mov     r12, [rax+18h]
0x18004431c  lea     rbx, [rdi+38h]
0x180044320  mov     rcx, [rbx]
0x180044323  mov     qword ptr [rbx], 0
0x18004432a  test    rcx, rcx
0x18004432d  jz      short loc_18004433C
0x18004432f  mov     rdx, [rcx]
0x180044332  mov     rax, [rdx+10h]
0x180044336  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004433b  nop
0x18004433c  mov     r8, rbx
0x18004433f  lea     rdx, _GUID_5d2400f0_f2ee_4a51_a3be_0ac9a19c09c4
0x180044346  mov     rcx, r14
0x180044349  mov     rax, r12
0x18004434c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044351  mov     r14d, eax
0x180044354  test    eax, eax
0x180044356  jns     short loc_180044390
0x180044358  mov     rcx, [rbp+68h]; this
0x18004435c  mov     r9d, eax; char *
0x18004435f  lea     r8, aAvcoreMidi2Tra; "avcore\\midi2\\transport\\ksaggregatetr"...
0x180044366  mov     edx, 6Fh ; 'o'; void *
0x18004436b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180044370  nop
0x180044371  mov     rcx, [rsp+160h+var_108]
0x180044376  test    rcx, rcx
0x180044379  jz      short loc_180044388
0x18004437b  mov     rax, [rcx]
0x18004437e  mov     rax, [rax+10h]
0x180044382  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044387  nop
0x180044388  mov     eax, r14d
  ... truncated ...
```
