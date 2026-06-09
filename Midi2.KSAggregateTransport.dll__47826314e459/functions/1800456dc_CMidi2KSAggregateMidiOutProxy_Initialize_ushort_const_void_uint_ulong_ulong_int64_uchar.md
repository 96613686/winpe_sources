# CMidi2KSAggregateMidiOutProxy::Initialize(ushort const *,void *,uint,ulong,ulong *,__int64,uchar)

- ea: `0x1800456dc`
- end: `0x180045ccb`
- name: `?Initialize@CMidi2KSAggregateMidiOutProxy@@QEAAJPEBGPEAXIKPEAK_JE@Z`
- size: `1519`
- prototype: `__int64 __usercall@<rax>(CMidi2KSAggregateMidiOutProxy *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, void *@<r8>, unsigned int@<r9d>, unsigned int, unsigned int *, __int64, unsigned __int8)`
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
- `0x180044458`
- `0x1800456dc`
- `0x1800494d4`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180045ab7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180045ab7`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CMidi2KSAggregateMidiOutProxy::Initialize(
        CMidi2KSAggregateMidiOutProxy *this,
        const char *a2,
        void *a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int *a6,
        __int64 a7,
        unsigned __int8 a8)
{
  _DWORD *v12; // rcx
  int v13; // r8d
  int v14; // r9d
  _DWORD *v15; // rcx
  int v16; // r8d
  int v17; // r9d
  __int64 v18; // r8
  __int64 v19; // rax
  _QWORD *v20; // rbx
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
  __int64 (__fastcall *v34)(LPVOID, GUID *, char *); // r13
  __int64 v35; // rcx
  int v36; // eax
  unsigned int v37; // r14d
  int v38; // eax
  _DWORD *v39; // rcx
  int v40; // r8d
  int v41; // r9d
  int ppv; // [rsp+20h] [rbp-E0h]
  int ppva; // [rsp+20h] [rbp-E0h]
  _BYTE v44[4]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v45; // [rsp+54h] [rbp-ACh] BYREF
  LPVOID v46; // [rsp+58h] [rbp-A8h] BYREF
  int v47[2]; // [rsp+60h] [rbp-A0h] BYREF
  const wchar_t *v48; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v49[2]; // [rsp+70h] [rbp-90h] BYREF
  GUID rguid; // [rsp+80h] [rbp-80h] BYREF
  const char *v51; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v52[32]; // [rsp+98h] [rbp-68h] BYREF
  int v53; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v54; // [rsp+BCh] [rbp-44h]
  __int128 v55; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v56; // [rsp+D8h] [rbp-28h]
  __int64 v57; // [rsp+E0h] [rbp-20h]
  IID rclsid; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v59[32]; // [rsp+100h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]

  v51 = (const char *)a6;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix>::GetImpl'::`2'::impl) )
  {
    v12 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
    if ( *v12 > 4u )
    {
      v44[0] = a8;
      v45 = a4;
      v49[0] = a2;
      *(_QWORD *)v47 = L"Enter";
      v48 = (const wchar_t *)this;
      *(_QWORD *)&rguid.Data1 = "CMidi2KSAggregateMidiOutProxy::Initialize";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(
        (_DWORD)v12,
        (unsigned int)&word_18008B446,
        v13,
        v14,
        (__int64)&rguid,
        (__int64)&v48,
        (__int64)v47,
        (__int64)v49,
        (__int64)&v45,
        (__int64)v44);
    }
  }
  else
  {
    v15 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
    if ( *v15 > 4u )
    {
      v44[0] = a8;
      v45 = a4;
      *(_QWORD *)&rguid.Data1 = a2;
      v48 = (const wchar_t *)this;
      *(_QWORD *)v47 = "CMidi2KSAggregateMidiOutProxy::Initialize";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(
        (_DWORD)v15,
        (unsigned int)&dword_18008B3E4,
        v16,
        v17,
        (__int64)v47,
        (__int64)&v48,
        (__int64)&rguid,
        (__int64)&v45,
        (__int64)v44);
    }
  }
  *((_QWORD *)this + 9) = a7;
  *((_BYTE *)this + 80) = a8;
  v55 = 0;
  v56 = 0;
  v57 = 0;
  v18 = -1;
  do
    ++v18;
  while ( *(_WORD *)&a2[2 * v18] );
  std::wstring::_Construct<1,unsigned short const *>(&v55);
  v19 = std::wstring::wstring(v52, &v55);
  WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(v59, v19);
  std::wstring::operator=((char *)this + 16, v59);
  std::wstring::~wstring(v59);
  std::wstring::~wstring(&v55);
  _InterlockedExchange64((volatile __int64 *)this + 6, 0);
  v20 = operator new(0x70u);
  *(_QWORD *)&rguid.Data1 = v20;
  memset_0(v20, 0, 0x70u);
  v20[1] = 0;
  *((_DWORD *)v20 + 4) = 1;
  *((_BYTE *)v20 + 20) = 0;
  v20[3] = 0;
  v20[4] = 0;
  v20[5] = 0;
  v20[6] = 0;
  v20[7] = 0;
  v20[8] = 0;
  v20[9] = 0;
  v20[10] = 0;
  v20[11] = 0;
  v20[12] = 0;
  *((_DWORD *)v20 + 26) = 0;
  *v20 = &KSMidiOutDevice::`vftable';
  v21 = *((_QWORD *)this + 8);
  *((_QWORD *)this + 8) = v20;
  if ( v21 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v21 + 8LL))(v21, 1);
  v22 = *((_QWORD *)this + 8);
  if ( !v22 )
  {
    v23 = -2147024882;
    v24 = 64;
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v24,
      (unsigned int)"avcore\\midi2\\transport\\ksaggregatetransport\\midi2.ksaggregatemidioutproxy.cpp",
      (const char *)v23,
      ppv);
    return v23;
  }
  v23 = KSMidiOutDevice::Initialize(v22, a2, a3, a4);
  if ( (v23 & 0x80000000) != 0 )
  {
    v27 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
    if ( *v27 > 2u )
    {
      v45 = a4;
      *(_QWORD *)&rguid.Data1 = a2;
      LODWORD(v49[0]) = v23;
      v48 = L"Unable to initialize sub-device for input";
      *(_QWORD *)v47 = this;
      v51 = "CMidi2KSAggregateMidiOutProxy::Initialize";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        (_DWORD)v27,
        (unsigned int)byte_18008B37B,
        (_DWORD)v27,
        v28,
        (__int64)&v51,
        (__int64)v47,
        (__int64)&v48,
        (__int64)v49,
        (__int64)&rguid,
        (__int64)&v45);
    }
    v29 = *((_QWORD *)this + 8);
    *((_QWORD *)this + 8) = 0;
    if ( v29 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v29 + 8LL))(v29, 1);
    v24 = 92;
    goto LABEL_12;
  }
  v46 = 0;
  rclsid = GUID_96121591_8d68_479f_9b48_2bf0b90113f7;
  rguid = GUID_96121591_8d68_479f_9b48_2bf0b90113f7;
  IsComponentPermitted = WindowsMidiServicesInternal::IsComponentPermitted(&rguid, v26);
  v23 = IsComponentPermitted;
  if ( IsComponentPermitted < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"avcore\\midi2\\transport\\ksaggregatetransport\\midi2.ksaggregatemidioutproxy.cpp",
      (const char *)(unsigned int)IsComponentPermitted,
      ppv);
    if ( v46 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v46 + 16LL))(v46);
    return v23;
  }
  v31 = v46;
  v46 = 0;
  if ( v31 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v31 + 16LL))(v31);
  v32 = CoCreateInstance(&rclsid, 0, 0x17u, &GUID_65fa86a4_0433_4dcd_88e4_e565051cab2d, &v46);
  v23 = v32;
  if ( v32 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x68,
      (unsigned int)"avcore\\midi2\\transport\\ksaggregatetransport\\midi2.ksaggregatemidioutproxy.cpp",
      (const char *)(unsigned int)v32,
      ppva);
    if ( v46 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v46 + 16LL))(v46);
    return v23;
  }
  v33 = v46;
  v34 = *(__int64 (__fastcall **)(LPVOID, GUID *, char *))(*(_QWORD *)v46 + 24LL);
  v35 = *((_QWORD *)this + 7);
  *((_QWORD *)this + 7) = 0;
  if ( v35 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
  v36 = v34(v33, &GUID_5d2400f0_f2ee_4a51_a3be_0ac9a19c09c4, (char *)this + 56);
  v37 = v36;
  if ( v36 >= 0 )
  {
    v54 = 1;
    v53 = 2;
    BYTE4(v54) = a8;
    v38 = (*(__int64 (__fastcall **)(_QWORD, const char *, int *, const char *))(**((_QWORD **)this + 7) + 24LL))(
            *((_QWORD *)this + 7),
            a2,
            &v53,
            v51);
    v23 = v38;
    if ( v38 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x73,
        (unsigned int)"avcore\\midi2\\transport\\ksaggregatetransport\\midi2.ksaggregatemidioutproxy.cpp",
        (const char *)(unsigned int)v38,
        (int)this);
      if ( v46 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v46 + 16LL))(v46);
      return v23;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix>::GetImpl'::`2'::impl) )
    {
      v39 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
      if ( *v39 > 4u )
      {
        v44[0] = a8;
        LODWORD(v49[0]) = a4;
        v51 = a2;
        *(_QWORD *)&rguid.Data1 = L"Exit";
        v48 = (const wchar_t *)this;
        *(_QWORD *)v47 = "CMidi2KSAggregateMidiOutProxy::Initialize";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(
          (_DWORD)v39,
          (unsigned int)&unk_18008B310,
          v40,
          v41,
          (__int64)v47,
          (__int64)&v48,
          (__int64)&rguid,
          (__int64)&v51,
          (__int64)v49,
          (__int64)v44);
      }
    }
    if ( v46 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v46 + 16LL))(v46);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6A,
      (unsigned int)"avcore\\midi2\\transport\\ksaggregatetransport\\midi2.ksaggregatemidioutproxy.cpp",
      (const char *)(unsigned int)v36,
      ppva);
    if ( v46 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v46 + 16LL))(v46);
    return v37;
  }
}

```

## disassembly

```asm
0x1800456dc  push    rbp
0x1800456de  push    rbx
0x1800456df  push    rsi
0x1800456e0  push    rdi
0x1800456e1  push    r12
0x1800456e3  push    r13
0x1800456e5  push    r14
0x1800456e7  push    r15
0x1800456e9  lea     rbp, [rsp-38h]
0x1800456ee  sub     rsp, 138h
0x1800456f5  mov     rax, cs:__security_cookie
0x1800456fc  xor     rax, rsp
0x1800456ff  mov     [rbp+70h+var_50], rax
0x180045703  mov     r12d, r9d
0x180045706  mov     r13, r8
0x180045709  mov     rsi, rdx
0x18004570c  mov     rdi, rcx
0x18004570f  mov     r14, [rbp+70h+arg_28]
0x180045716  mov     [rbp+70h+var_E0], r14
0x18004571a  xor     ebx, ebx
0x18004571c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix> `wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix>::GetImpl(void)'::`2'::impl
0x180045723  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2VirtualPortDriversFix>::__private_IsEnabled(void)
0x180045728  mov     r15b, [rbp+70h+arg_38]
0x18004572f  test    al, al
0x180045731  jz      loc_1800457BF
0x180045737  call    ?Instance@MidiKSAggregateTransportTelemetryProvider@@KAPEAV1@XZ; MidiKSAggregateTransportTelemetryProvider::Instance(void)
0x18004573c  mov     rcx, [rax+8]
0x180045740  mov     eax, [rcx]
0x180045742  cmp     eax, 4
0x180045745  jbe     loc_18004582B
0x18004574b  mov     [rsp+170h+var_120], r15b
0x180045750  mov     [rsp+170h+var_11C], r12d
0x180045755  mov     [rsp+170h+var_100], rsi
0x18004575a  lea     rax, aEnter_0; "Enter"
0x180045761  mov     qword ptr [rsp+170h+var_110], rax
0x180045766  mov     [rsp+170h+var_108], rdi
0x18004576b  lea     rax, aCmidi2ksaggreg_18; "CMidi2KSAggregateMidiOutProxy::Initiali"...
0x180045772  mov     qword ptr [rbp+70h+rguid.Data1], rax
0x180045776  lea     rax, [rsp+170h+var_120]
0x18004577b  mov     [rsp+170h+var_128], rax
0x180045780  lea     rax, [rsp+170h+var_11C]
0x180045785  mov     [rsp+170h+var_130], rax
0x18004578a  lea     rax, [rsp+170h+var_100]
0x18004578f  mov     [rsp+170h+var_138], rax
0x180045794  lea     rax, [rsp+170h+var_110]
0x180045799  mov     [rsp+170h+var_140], rax
0x18004579e  lea     rax, [rsp+170h+var_108]
0x1800457a3  mov     [rsp+170h+var_148], rax
0x1800457a8  lea     rax, [rbp+70h+rguid]
0x1800457ac  mov     [rsp+170h+ppv], rax
0x1800457b1  lea     rdx, word_18008B446
0x1800457b8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &)
0x1800457bd  jmp     short loc_18004582B
0x1800457bf  call    ?Instance@MidiKSAggregateTransportTelemetryProvider@@KAPEAV1@XZ; MidiKSAggregateTransportTelemetryProvider::Instance(void)
0x1800457c4  mov     rcx, [rax+8]
0x1800457c8  mov     eax, [rcx]
0x1800457ca  cmp     eax, 4
0x1800457cd  jbe     short loc_18004582B
0x1800457cf  mov     [rsp+170h+var_120], r15b
0x1800457d4  mov     [rsp+170h+var_11C], r12d
0x1800457d9  mov     qword ptr [rbp+70h+rguid.Data1], rsi
0x1800457dd  mov     [rsp+170h+var_108], rdi
0x1800457e2  lea     rax, aCmidi2ksaggreg_18; "CMidi2KSAggregateMidiOutProxy::Initiali"...
0x1800457e9  mov     qword ptr [rsp+170h+var_110], rax
0x1800457ee  lea     rax, [rsp+170h+var_120]
0x1800457f3  mov     [rsp+170h+var_130], rax
0x1800457f8  lea     rax, [rsp+170h+var_11C]
0x1800457fd  mov     [rsp+170h+var_138], rax
0x180045802  lea     rax, [rbp+70h+rguid]
0x180045806  mov     [rsp+170h+var_140], rax
0x18004580b  lea     rax, [rsp+170h+var_108]
0x180045810  mov     [rsp+170h+var_148], rax
0x180045815  lea     rax, [rsp+170h+var_110]
0x18004581a  mov     [rsp+170h+ppv], rax; int
0x18004581f  lea     rdx, dword_18008B3E4
0x180045826  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &)
0x18004582b  mov     rax, [rbp+70h+arg_30]
0x180045832  mov     [rdi+48h], rax
0x180045836  mov     [rdi+50h], r15b
0x18004583a  xorps   xmm0, xmm0
0x18004583d  movups  [rbp+70h+var_A8], xmm0
0x180045841  mov     [rbp+70h+var_98], rbx
0x180045845  mov     [rbp+70h+var_90], rbx
0x180045849  or      r8, 0FFFFFFFFFFFFFFFFh
0x18004584d  inc     r8
0x180045850  cmp     [rsi+r8*2], bx
0x180045855  jnz     short loc_18004584D
0x180045857  mov     rdx, rsi
0x18004585a  lea     rcx, [rbp+70h+var_A8]
0x18004585e  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180045863  nop
0x180045864  lea     rdx, [rbp+70h+var_A8]
0x180045868  lea     rcx, [rbp+70h+var_D8]
0x18004586c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180045871  mov     rdx, rax
0x180045874  lea     rcx, [rbp+70h+var_70]
0x180045878  call    ?ToLowerTrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::ToLowerTrimmedWStringCopy(std::wstring)
0x18004587d  lea     rcx, [rdi+10h]
0x180045881  lea     rdx, [rbp+70h+var_70]
0x180045885  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18004588a  lea     rcx, [rbp+70h+var_70]; void *
0x18004588e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180045893  nop
0x180045894  lea     rcx, [rbp+70h+var_A8]; void *
0x180045898  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004589d  mov     rax, rbx
0x1800458a0  xchg    rax, [rdi+30h]
0x1800458a4  mov     ecx, 70h ; 'p'; Size
0x1800458a9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800458ae  mov     rbx, rax
0x1800458b1  mov     qword ptr [rbp+70h+rguid.Data1], rax
0x1800458b5  xor     edx, edx; Val
0x1800458b7  lea     r8d, [rdx+70h]; Size
0x1800458bb  mov     rcx, rax; void *
0x1800458be  call    memset_0
0x1800458c3  xor     eax, eax
0x1800458c5  mov     [rbx+8], rax
0x1800458c9  lea     r8d, [rax+1]
0x1800458cd  mov     [rbx+10h], r8d
0x1800458d1  xor     edx, edx
0x1800458d3  mov     [rbx+14h], dl
0x1800458d6  mov     [rbx+18h], rdx
0x1800458da  mov     [rbx+20h], rdx
0x1800458de  mov     [rbx+28h], rdx
0x1800458e2  mov     [rbx+30h], rdx
0x1800458e6  mov     [rbx+38h], rdx
0x1800458ea  mov     [rbx+40h], rdx
0x1800458ee  mov     [rbx+48h], rdx
0x1800458f2  mov     [rbx+50h], rdx
0x1800458f6  mov     [rbx+58h], rdx
0x1800458fa  mov     [rbx+60h], rdx
0x1800458fe  mov     [rbx+68h], edx
0x180045901  lea     rax, ??_7KSMidiOutDevice@@6B@; const KSMidiOutDevice::`vftable'
0x180045908  mov     [rbx], rax
0x18004590b  mov     rcx, [rdi+40h]
0x18004590f  mov     [rdi+40h], rbx
0x180045913  test    rcx, rcx
0x180045916  jz      short loc_180045927
0x180045918  mov     rax, [rcx]
0x18004591b  mov     edx, r8d
0x18004591e  mov     rax, [rax+8]
0x180045922  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045927  mov     rcx, [rdi+40h]
0x18004592b  test    rcx, rcx
0x18004592e  jnz     short loc_180045952
0x180045930  mov     ebx, 8007000Eh
0x180045935  lea     edx, [rcx+40h]; void *
0x180045938  lea     r8, aAvcoreMidi2Tra_5; "avcore\\midi2\\transport\\ksaggregatetr"...
0x18004593f  mov     r9d, ebx; char *
0x180045942  mov     rcx, [rbp+78h]; this
0x180045946  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004594b  mov     eax, ebx
0x18004594d  jmp     loc_180045CAB
0x180045952  mov     [rsp+170h+var_140], r14
0x180045957  mov     eax, [rbp+70h+arg_20]
0x18004595d  mov     dword ptr [rsp+170h+var_148], eax
0x180045961  mov     r9d, r12d
0x180045964  mov     r8, r13
0x180045967  mov     rdx, rsi
0x18004596a  call    ?Initialize@KSMidiOutDevice@@QEAAJPEBGPEAXIW4_MidiTransport@@KPEAKW4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004@@@Z; KSMidiOutDevice::Initialize(ushort const *,void *,uint,_MidiTransport,ulong,ulong *,__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004)
0x18004596f  mov     ebx, eax
0x180045971  xor     r14d, r14d
0x180045974  test    eax, eax
0x180045976  jns     loc_180045A27
0x18004597c  call    ?Instance@MidiKSAggregateTransportTelemetryProvider@@KAPEAV1@XZ; MidiKSAggregateTransportTelemetryProvider::Instance(void)
0x180045981  mov     r8, [rax+8]
0x180045985  mov     ecx, [r8]
0x180045988  cmp     ecx, 2
0x18004598b  jbe     short loc_1800459FF
0x18004598d  mov     [rsp+170h+var_11C], r12d
0x180045992  mov     qword ptr [rbp+70h+rguid.Data1], rsi
0x180045996  mov     dword ptr [rsp+170h+var_100], ebx
0x18004599a  lea     rax, aUnableToInitia_1; "Unable to initialize sub-device for inp"...
0x1800459a1  mov     [rsp+170h+var_108], rax
0x1800459a6  mov     qword ptr [rsp+170h+var_110], rdi
0x1800459ab  lea     rax, aCmidi2ksaggreg_18; "CMidi2KSAggregateMidiOutProxy::Initiali"...
0x1800459b2  mov     [rbp+70h+var_E0], rax
0x1800459b6  lea     rax, [rsp+170h+var_11C]
0x1800459bb  mov     [rsp+170h+var_128], rax
0x1800459c0  lea     rax, [rbp+70h+rguid]
0x1800459c4  mov     [rsp+170h+var_130], rax
0x1800459c9  lea     rax, [rsp+170h+var_100]
0x1800459ce  mov     [rsp+170h+var_138], rax
0x1800459d3  lea     rax, [rsp+170h+var_108]
0x1800459d8  mov     [rsp+170h+var_140], rax
0x1800459dd  lea     rax, [rsp+170h+var_110]
0x1800459e2  mov     [rsp+170h+var_148], rax
0x1800459e7  lea     rax, [rbp+70h+var_E0]
0x1800459eb  mov     [rsp+170h+ppv], rax
0x1800459f0  lea     rdx, byte_18008B37B
0x1800459f7  mov     rcx, r8
0x1800459fa  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@56@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1800459ff  mov     rcx, [rdi+40h]
0x180045a03  mov     [rdi+40h], r14
0x180045a07  test    rcx, rcx
0x180045a0a  jz      short loc_180045A1D
0x180045a0c  mov     rax, [rcx]
0x180045a0f  mov     edx, 1
0x180045a14  mov     rax, [rax+8]
0x180045a18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045a1d  mov     edx, 5Ch ; '\'
0x180045a22  jmp     loc_180045938
0x180045a27  mov     [rsp+170h+var_118], r14
0x180045a2c  movups  xmm0, xmmword ptr cs:_GUID_96121591_8d68_479f_9b48_2bf0b90113f7.Data1
0x180045a33  movaps  xmmword ptr [rbp+70h+rclsid.Data1], xmm0
0x180045a37  movdqa  xmmword ptr [rbp+70h+rguid.Data1], xmm0
0x180045a3c  lea     rcx, [rbp+70h+rguid]; rguid
0x180045a40  call    ?IsComponentPermitted@WindowsMidiServicesInternal@@YAJU_GUID@@@Z; WindowsMidiServicesInternal::IsComponentPermitted(_GUID)
0x180045a45  mov     ebx, eax
0x180045a47  test    eax, eax
0x180045a49  jns     short loc_180045A80
0x180045a4b  mov     rcx, [rbp+78h]; this
0x180045a4f  mov     r9d, eax; char *
0x180045a52  lea     r8, aAvcoreMidi2Tra_5; "avcore\\midi2\\transport\\ksaggregatetr"...
0x180045a59  mov     edx, 66h ; 'f'; void *
0x180045a5e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045a63  nop
0x180045a64  mov     rcx, [rsp+170h+var_118]
0x180045a69  test    rcx, rcx
0x180045a6c  jz      short loc_180045A7B
0x180045a6e  mov     rax, [rcx]
0x180045a71  mov     rax, [rax+10h]
0x180045a75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045a7a  nop
0x180045a7b  jmp     loc_18004594B
0x180045a80  mov     rcx, [rsp+170h+var_118]
0x180045a85  mov     [rsp+170h+var_118], r14
0x180045a8a  test    rcx, rcx
0x180045a8d  jz      short loc_180045A9C
0x180045a8f  mov     rax, [rcx]
0x180045a92  mov     rax, [rax+10h]
0x180045a96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045a9b  nop
0x180045a9c  lea     rax, [rsp+170h+var_118]
0x180045aa1  mov     [rsp+170h+ppv], rax; int
0x180045aa6  lea     r9, _GUID_65fa86a4_0433_4dcd_88e4_e565051cab2d; riid
0x180045aad  xor     edx, edx; pUnkOuter
0x180045aaf  lea     r8d, [rdx+17h]; dwClsContext
0x180045ab3  lea     rcx, [rbp+70h+rclsid]; rclsid
0x180045ab7  call    cs:__imp_CoCreateInstance
0x180045abd  mov     ebx, eax
0x180045abf  test    eax, eax
0x180045ac1  jns     short loc_180045AF8
0x180045ac3  mov     rcx, [rbp+78h]; this
0x180045ac7  mov     r9d, eax; char *
0x180045aca  lea     r8, aAvcoreMidi2Tra_5; "avcore\\midi2\\transport\\ksaggregatetr"...
0x180045ad1  mov     edx, 68h ; 'h'; void *
0x180045ad6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045adb  nop
0x180045adc  mov     rcx, [rsp+170h+var_118]
0x180045ae1  test    rcx, rcx
0x180045ae4  jz      short loc_180045AF3
0x180045ae6  mov     rax, [rcx]
0x180045ae9  mov     rax, [rax+10h]
0x180045aed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045af2  nop
0x180045af3  jmp     loc_18004594B
0x180045af8  mov     r14, [rsp+170h+var_118]
0x180045afd  mov     rax, [r14]
0x180045b00  mov     r13, [rax+18h]
0x180045b04  lea     rbx, [rdi+38h]
0x180045b08  mov     rcx, [rbx]
0x180045b0b  mov     qword ptr [rbx], 0
0x180045b12  test    rcx, rcx
0x180045b15  jz      short loc_180045B24
0x180045b17  mov     rdx, [rcx]
0x180045b1a  mov     rax, [rdx+10h]
0x180045b1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045b23  nop
0x180045b24  mov     r8, rbx
0x180045b27  lea     rdx, _GUID_5d2400f0_f2ee_4a51_a3be_0ac9a19c09c4
0x180045b2e  mov     rcx, r14
0x180045b31  mov     rax, r13
0x180045b34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045b39  mov     r14d, eax
0x180045b3c  test    eax, eax
0x180045b3e  jns     short loc_180045B78
0x180045b40  mov     rcx, [rbp+78h]; this
0x180045b44  mov     r9d, eax; char *
0x180045b47  lea     r8, aAvcoreMidi2Tra_5; "avcore\\midi2\\transport\\ksaggregatetr"...
0x180045b4e  mov     edx, 6Ah ; 'j'; void *
0x180045b53  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045b58  nop
0x180045b59  mov     rcx, [rsp+170h+var_118]
0x180045b5e  test    rcx, rcx
0x180045b61  jz      short loc_180045B70
0x180045b63  mov     rax, [rcx]
0x180045b66  mov     rax, [rax+10h]
0x180045b6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045b6f  nop
0x180045b70  mov     eax, r14d
0x180045b73  jmp     loc_180045CAB
0x180045b78  xor     eax, eax
0x180045b7a  mov     [rbp+70h+var_B8], rax
0x180045b7e  mov     [rbp+70h+var_B8+4], 1
0x180045b86  mov     dword ptr [rbp+70h+var_B8], 2
0x180045b8d  mov     [rbp+70h+var_B0], r15b
0x180045b91  mov     rcx, [rbx]
0x180045b94  mov     rax, [rcx]
0x180045b97  mov     [rsp+170h+var_140], 0
  ... truncated ...
```
