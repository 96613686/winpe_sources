# CEndpointCharacteristics::DiscoverProcessingModeCharacteristics(void)

- ea: `0x180141f28`
- end: `0x1801422d3`
- name: `?DiscoverProcessingModeCharacteristics@CEndpointCharacteristics@@AEAAJXZ`
- size: `939`
- prototype: `__int64 __fastcall(CEndpointCharacteristics *__hidden this)`
- caller_count: `2`
- callee_count: `16`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180066864`
- `0x1800cb5ac`

## callees

- `0x18000bb58`
- `0x180046260`
- `0x180051cac`
- `0x180069100`
- `0x180069744`
- `0x18006fe80`
- `0x180071750`
- `0x180073310`
- `0x180089b6c`
- `0x1800b52d8`
- `0x1800bd2cc`
- `0x1800bd768`
- `0x1800cf8c0`
- `0x180141f28`
- `0x180142cdc`
- `0x18015f980`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180142027`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180142071`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180142027`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180142071`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x180141f8c`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x180141f8c`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1801421d6`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1801421d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180142281`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18014229d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801422a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180142281`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18014229d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801422a7`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CEndpointCharacteristics::DiscoverProcessingModeCharacteristics(CEndpointCharacteristics *this)
{
  int v2; // r15d
  struct KSMULTIPLE_ITEM *v3; // rbx
  struct KSMULTIPLE_ITEM *v4; // rdi
  int PacketSizeConstraints; // eax
  __int64 OemEnginePeriodicity; // rdx
  __int64 v7; // rsi
  int v8; // r8d
  int v9; // r9d
  DWORD pcbData; // [rsp+50h] [rbp-B0h] BYREF
  int pvData; // [rsp+54h] [rbp-ACh] BYREF
  struct KSMULTIPLE_ITEM *v13; // [rsp+58h] [rbp-A8h] BYREF
  LPVOID pv; // [rsp+60h] [rbp-A0h] BYREF
  struct KSMULTIPLE_ITEM *v15; // [rsp+68h] [rbp-98h] BYREF
  __int64 TimeSec; // [rsp+70h] [rbp-90h] BYREF
  int v17; // [rsp+78h] [rbp-88h] BYREF
  __int64 v18; // [rsp+80h] [rbp-80h] BYREF
  __int64 v19; // [rsp+88h] [rbp-78h] BYREF
  __int64 v20; // [rsp+90h] [rbp-70h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+98h] [rbp-68h] BYREF
  LARGE_INTEGER Frequency; // [rsp+A0h] [rbp-60h] BYREF
  char v23[4]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v24; // [rsp+194h] [rbp+94h]
  int v25; // [rsp+119Ch] [rbp+109Ch]
  GUID v26; // [rsp+11A0h] [rbp+10A0h]
  char v27[4]; // [rsp+11B0h] [rbp+10B0h] BYREF
  __int64 v28; // [rsp+1294h] [rbp+1194h]
  int v29; // [rsp+229Ch] [rbp+219Ch]
  GUID v30; // [rsp+22A0h] [rbp+21A0h]

  v2 = 0;
  if ( (int)CEndpointCharacteristics::GetProcessingModeCharacteristicsFromPropertyStore(this) < 0 )
  {
    v13 = 0;
    v3 = 0;
    v15 = 0;
    v18 = 0;
    PerformanceCount.QuadPart = 0;
    v20 = 0;
    QueryPerformanceFrequency(&Frequency);
    CQPCStopWatch::Start((CQPCStopWatch *)&v20);
    GetSupportedDataRangeForEndpoint(eHostProcessConnector, *((struct IMMDevice **)this + 5), &v13);
    v4 = v13;
    PacketSizeConstraints = GetPacketSizeConstraints((__int64)g_DeviceEnumerator, *((_QWORD *)this + 9), &v18);
    v2 = 0;
    if ( PacketSizeConstraints != -2147023728 )
      v2 = PacketSizeConstraints;
    pvData = 0;
    pcbData = 4;
    RegGetValueW(
      HKEY_LOCAL_MACHINE,
      L"Software\\Microsoft\\Windows\\CurrentVersion\\Audio",
      L"ProbeForMinimumPeriod",
      0x18u,
      0,
      &pvData,
      &pcbData);
    v17 = 0;
    pcbData = 4;
    RegGetValueW(
      HKEY_LOCAL_MACHINE,
      L"Software\\Microsoft\\Windows\\CurrentVersion\\Audio",
      L"MaxCapturePeriodicityInMs",
      0x18u,
      0,
      &v17,
      &pcbData);
    OemEnginePeriodicity = CEndpointCharacteristics::GetOemEnginePeriodicity(this);
    TimeSec = OemEnginePeriodicity;
    v7 = v18;
    if ( v2 >= 0 && *((_DWORD *)this + 64) )
    {
      *(_DWORD *)v23 = 3;
      v24 = 0;
      v25 = 0;
      v26 = GUID_00000000_0000_0000_0000_000000000000;
      GetSupportedDataRangeForEndpoint(eKeywordDetectorConnector, *((struct IMMDevice **)this + 5), &v15);
      v3 = v15;
      v2 = CEndpointCharacteristics::DiscoverConnectorProcessingModeCharacteristics(
             this,
             v7,
             pvData != 0,
             TimeSec,
             (__int64)this + 296,
             (char)v23);
      CEndpointCharacteristics::CacheUnsupportedConnectorFormats(this, (struct CUnsupportedConnectorFormats *)v23);
      OemEnginePeriodicity = TimeSec;
    }
    *(_DWORD *)v27 = 0;
    v28 = 0;
    v29 = 0;
    v30 = GUID_00000000_0000_0000_0000_000000000000;
    if ( v2 >= 0 )
    {
      v2 = CEndpointCharacteristics::DiscoverConnectorProcessingModeCharacteristics(
             this,
             v7,
             pvData != 0,
             OemEnginePeriodicity,
             (__int64)this + 272,
             (char)v27);
      if ( v2 >= 0 && !*((_DWORD *)this + 65) )
        CEndpointCharacteristics::CacheProcessingModeCharacteristics(this);
    }
    CEndpointCharacteristics::CacheUnsupportedConnectorFormats(this, (struct CUnsupportedConnectorFormats *)v27);
    QueryPerformanceCounter(&PerformanceCount);
    pv = 0;
    if ( (int)CEndpointCharacteristics::GetEndpointId(this, (unsigned __int16 **)&pv) >= 0
      && **((_DWORD **)this + 1036) > 4u
      && (unsigned __int8)tlgKeywordOn(*((_QWORD *)this + 1036), 0x200000000010LL) )
    {
      TimeSec = CQPCStopWatch::GetTimeSec((CQPCStopWatch *)&v20);
      LODWORD(v13) = v2;
      v15 = (struct KSMULTIPLE_ITEM *)pv;
      v19 = 2048;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        v8,
        (unsigned int)&unk_1801A9E49,
        v8,
        v9,
        (__int64)&v19,
        (__int64)&v15,
        (__int64)&v13,
        (__int64)&TimeSec);
    }
    CoTaskMemFree(pv);
    pv = 0;
    std::unique_ptr<PacketSizeConstraints>::~unique_ptr<PacketSizeConstraints>(&v18);
    CoTaskMemFree(v3);
    CoTaskMemFree(v4);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180141f28  push    rbp
0x180141f2a  push    rbx
0x180141f2b  push    rsi
0x180141f2c  push    rdi
0x180141f2d  push    r12
0x180141f2f  push    r13
0x180141f31  push    r14
0x180141f33  push    r15
0x180141f35  lea     rbp, [rsp-21C8h]
0x180141f3d  mov     eax, 22C8h
0x180141f42  call    _alloca_probe
0x180141f47  sub     rsp, rax
0x180141f4a  mov     rax, cs:__security_cookie
0x180141f51  xor     rax, rsp
0x180141f54  mov     [rbp+2200h+var_50], rax
0x180141f5b  mov     r14, rcx
0x180141f5e  xor     esi, esi
0x180141f60  mov     r15d, esi
0x180141f63  call    ?GetProcessingModeCharacteristicsFromPropertyStore@CEndpointCharacteristics@@AEAAJXZ; CEndpointCharacteristics::GetProcessingModeCharacteristicsFromPropertyStore(void)
0x180141f68  test    eax, eax
0x180141f6a  jns     loc_1801422AD
0x180141f70  mov     [rsp+2300h+var_22A8], rsi
0x180141f75  mov     ebx, esi
0x180141f77  mov     [rsp+2300h+var_2298], rbx
0x180141f7c  mov     [rbp+2200h+var_2280], rsi
0x180141f80  mov     qword ptr [rbp+2200h+PerformanceCount], rsi
0x180141f84  mov     [rbp+2200h+var_2270], rsi
0x180141f88  lea     rcx, [rbp+2200h+Frequency]; lpFrequency
0x180141f8c  call    cs:__imp_QueryPerformanceFrequency
0x180141f92  lea     rcx, [rbp+2200h+var_2270]; this
0x180141f96  call    ?Start@CQPCStopWatch@@QEAAHXZ; CQPCStopWatch::Start(void)
0x180141f9b  lea     r8, [rsp+2300h+var_22A8]; struct KSMULTIPLE_ITEM **
0x180141fa0  mov     rdx, [r14+28h]; struct IMMDevice *
0x180141fa4  xor     ecx, ecx; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x180141fa6  call    ?GetSupportedDataRangeForEndpoint@@YAJW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEAUIMMDevice@@PEAPEAUKSMULTIPLE_ITEM@@@Z; GetSupportedDataRangeForEndpoint(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,IMMDevice *,KSMULTIPLE_ITEM * *)
0x180141fab  mov     rdi, [rsp+2300h+var_22A8]
0x180141fb0  test    eax, eax
0x180141fb2  js      short loc_180141FBE
0x180141fb4  mov     r12d, [rdi+4]
0x180141fb8  lea     r13, [rdi+8]
0x180141fbc  jmp     short loc_180141FC4
0x180141fbe  mov     r12d, esi
0x180141fc1  mov     r13, rsi
0x180141fc4  lea     r8, [rbp+2200h+var_2280]
0x180141fc8  mov     rdx, [r14+48h]
0x180141fcc  mov     rcx, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x180141fd3  call    ?GetPacketSizeConstraints@@YAJPEAUIMMDeviceEnumerator@@PEAUIPropertyStore@@AEAV?$unique_ptr@UPacketSizeConstraints@@U?$default_delete@UPacketSizeConstraints@@@std@@@std@@@Z; GetPacketSizeConstraints(IMMDeviceEnumerator *,IPropertyStore *,std::unique_ptr<PacketSizeConstraints> &)
0x180141fd8  mov     r15d, esi
0x180141fdb  cmp     eax, 80070490h
0x180141fe0  cmovnz  r15d, eax
0x180141fe4  mov     [rsp+2300h+var_22AC], esi
0x180141fe8  mov     [rsp+2300h+var_22B0], 4
0x180141ff0  lea     rax, [rsp+2300h+var_22B0]
0x180141ff5  mov     [rsp+2300h+pcbData], rax; pcbData
0x180141ffa  lea     rax, [rsp+2300h+var_22AC]
0x180141fff  mov     [rsp+2300h+pvData], rax; pvData
0x180142004  mov     [rsp+2300h+pdwType], rsi; pdwType
0x180142009  mov     r9d, 18h; dwFlags
0x18014200f  lea     r8, aProbeforminimu; "ProbeForMinimumPeriod"
0x180142016  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18014201d  mov     rsi, 0FFFFFFFF80000002h
0x180142024  mov     rcx, rsi; hkey
0x180142027  call    cs:__imp_RegGetValueW
0x18014202d  mov     [rsp+2300h+var_2288], 0
0x180142035  mov     [rsp+2300h+var_22B0], 4
0x18014203d  lea     rax, [rsp+2300h+var_22B0]
0x180142042  mov     [rsp+2300h+pcbData], rax; pcbData
0x180142047  lea     rax, [rsp+2300h+var_2288]
0x18014204c  mov     [rsp+2300h+pvData], rax; pvData
0x180142051  mov     [rsp+2300h+pdwType], 0; pdwType
0x18014205a  mov     r9d, 18h; dwFlags
0x180142060  lea     r8, aMaxcaptureperi; "MaxCapturePeriodicityInMs"
0x180142067  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18014206e  mov     rcx, rsi; hkey
0x180142071  call    cs:__imp_RegGetValueW
0x180142077  mov     rcx, r14; this
0x18014207a  call    ?GetOemEnginePeriodicity@CEndpointCharacteristics@@AEAA_JXZ; CEndpointCharacteristics::GetOemEnginePeriodicity(void)
0x18014207f  mov     rdx, rax
0x180142082  mov     [rsp+2300h+var_2290], rax
0x180142087  mov     rsi, [rbp+2200h+var_2280]
0x18014208b  xor     ecx, ecx
0x18014208d  test    r15d, r15d
0x180142090  js      loc_180142142
0x180142096  cmp     [r14+100h], ecx
0x18014209d  jz      loc_180142142
0x1801420a3  lea     r15d, [rcx+3]
0x1801420a7  mov     dword ptr [rbp+2200h+var_2250], r15d
0x1801420ab  mov     [rbp+2200h+var_216C], rcx
0x1801420b2  mov     [rbp+2200h+var_1164], ecx
0x1801420b8  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1801420bf  movdqu  [rbp+2200h+var_1160], xmm0
0x1801420c7  lea     r8, [rsp+2300h+var_2298]; struct KSMULTIPLE_ITEM **
0x1801420cc  mov     rdx, [r14+28h]; struct IMMDevice *
0x1801420d0  mov     ecx, r15d; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x1801420d3  call    ?GetSupportedDataRangeForEndpoint@@YAJW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEAUIMMDevice@@PEAPEAUKSMULTIPLE_ITEM@@@Z; GetSupportedDataRangeForEndpoint(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,IMMDevice *,KSMULTIPLE_ITEM * *)
0x1801420d8  mov     rbx, [rsp+2300h+var_2298]
0x1801420dd  test    eax, eax
0x1801420df  js      short loc_1801420EB
0x1801420e1  mov     r8d, [rbx+4]
0x1801420e5  lea     r9, [rbx+8]
0x1801420e9  jmp     short loc_1801420F1
0x1801420eb  xor     r8d, r8d
0x1801420ee  xor     r9d, r9d
0x1801420f1  cmp     [rsp+2300h+var_22AC], 0
0x1801420f6  setnz   cl
0x1801420f9  lea     rax, [r14+128h]
0x180142100  lea     r10, [rbp+2200h+var_2250]
0x180142104  mov     qword ptr [rsp+2300h+var_22C0], r10; char
0x180142109  mov     [rsp+2300h+var_22C8], rax; __int64
0x18014210e  mov     rax, [rsp+2300h+var_2290]
0x180142113  mov     [rsp+2300h+pcbData], rax; __int64
0x180142118  mov     byte ptr [rsp+2300h+pvData], cl; char
0x18014211c  mov     [rsp+2300h+pdwType], rsi; __int64
0x180142121  mov     edx, r15d
0x180142124  mov     rcx, r14; this
0x180142127  call    ?DiscoverConnectorProcessingModeCharacteristics@CEndpointCharacteristics@@AEAAJW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@IPEATKSDATAFORMAT@@PEAUPacketSizeConstraints@@_N_JAEAV?$vector@V?$unique_ptr@VCConnectorProcessingModeCharacteristics@@U?$default_delete@VCConnectorProcessingModeCharacteristics@@@std@@@std@@V?$allocator@V?$unique_ptr@VCConnectorProcessingModeCharacteristics@@U?$default_delete@VCConnectorProcessingModeCharacteristics@@@std@@@std@@@2@@std@@PEAVCUnsupportedConnectorFormats@@@Z; CEndpointCharacteristics::DiscoverConnectorProcessingModeCharacteristics(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,uint,KSDATAFORMAT *,PacketSizeConstraints *,bool,__int64,std::vector<std::unique_ptr<CConnectorProcessingModeCharacteristics>> &,CUnsupportedConnectorFormats *)
0x18014212c  mov     r15d, eax
0x18014212f  lea     rdx, [rbp+2200h+var_2250]; struct CUnsupportedConnectorFormats *
0x180142133  mov     rcx, r14; this
0x180142136  call    ?CacheUnsupportedConnectorFormats@CEndpointCharacteristics@@AEAAXPEAVCUnsupportedConnectorFormats@@@Z; CEndpointCharacteristics::CacheUnsupportedConnectorFormats(CUnsupportedConnectorFormats *)
0x18014213b  mov     rdx, [rsp+2300h+var_2290]
0x180142140  xor     ecx, ecx
0x180142142  mov     dword ptr [rbp+2200h+var_1150], ecx
0x180142148  mov     [rbp+2200h+var_106C], 0
0x180142153  mov     [rbp+2200h+var_64], ecx
0x180142159  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180142160  movdqu  [rbp+2200h+var_60], xmm0
0x180142168  test    r15d, r15d
0x18014216b  js      short loc_1801421C3
0x18014216d  cmp     [rsp+2300h+var_22AC], ecx
0x180142171  setnz   cl
0x180142174  lea     rax, [r14+110h]
0x18014217b  lea     r8, [rbp+2200h+var_1150]
0x180142182  mov     qword ptr [rsp+2300h+var_22C0], r8; char
0x180142187  mov     [rsp+2300h+var_22C8], rax; __int64
0x18014218c  mov     [rsp+2300h+pcbData], rdx; __int64
0x180142191  mov     byte ptr [rsp+2300h+pvData], cl; char
0x180142195  mov     [rsp+2300h+pdwType], rsi; __int64
0x18014219a  mov     r9, r13
0x18014219d  mov     r8d, r12d
0x1801421a0  xor     edx, edx
0x1801421a2  mov     rcx, r14; this
0x1801421a5  call    ?DiscoverConnectorProcessingModeCharacteristics@CEndpointCharacteristics@@AEAAJW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@IPEATKSDATAFORMAT@@PEAUPacketSizeConstraints@@_N_JAEAV?$vector@V?$unique_ptr@VCConnectorProcessingModeCharacteristics@@U?$default_delete@VCConnectorProcessingModeCharacteristics@@@std@@@std@@V?$allocator@V?$unique_ptr@VCConnectorProcessingModeCharacteristics@@U?$default_delete@VCConnectorProcessingModeCharacteristics@@@std@@@std@@@2@@std@@PEAVCUnsupportedConnectorFormats@@@Z; CEndpointCharacteristics::DiscoverConnectorProcessingModeCharacteristics(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,uint,KSDATAFORMAT *,PacketSizeConstraints *,bool,__int64,std::vector<std::unique_ptr<CConnectorProcessingModeCharacteristics>> &,CUnsupportedConnectorFormats *)
0x1801421aa  mov     r15d, eax
0x1801421ad  test    eax, eax
0x1801421af  js      short loc_1801421C3
0x1801421b1  cmp     dword ptr [r14+104h], 0
0x1801421b9  jnz     short loc_1801421C3
0x1801421bb  mov     rcx, r14; this
0x1801421be  call    ?CacheProcessingModeCharacteristics@CEndpointCharacteristics@@AEAAJXZ; CEndpointCharacteristics::CacheProcessingModeCharacteristics(void)
0x1801421c3  lea     rdx, [rbp+2200h+var_1150]; struct CUnsupportedConnectorFormats *
0x1801421ca  mov     rcx, r14; this
0x1801421cd  call    ?CacheUnsupportedConnectorFormats@CEndpointCharacteristics@@AEAAXPEAVCUnsupportedConnectorFormats@@@Z; CEndpointCharacteristics::CacheUnsupportedConnectorFormats(CUnsupportedConnectorFormats *)
0x1801421d2  lea     rcx, [rbp+2200h+PerformanceCount]; lpPerformanceCount
0x1801421d6  call    cs:__imp_QueryPerformanceCounter
0x1801421dc  mov     [rsp+2300h+pv], 0
0x1801421e5  lea     rdx, [rsp+2300h+pv]; unsigned __int16 **
0x1801421ea  mov     rcx, r14; this
0x1801421ed  call    ?GetEndpointId@CEndpointCharacteristics@@QEAAJPEAPEAG@Z; CEndpointCharacteristics::GetEndpointId(ushort * *)
0x1801421f2  test    eax, eax
0x1801421f4  js      loc_18014227C
0x1801421fa  mov     r8, [r14+2060h]
0x180142201  mov     eax, [r8]
0x180142204  cmp     eax, 4
0x180142207  jbe     short loc_18014227C
0x180142209  mov     rdx, 200000000010h
0x180142213  mov     rcx, r8
0x180142216  call    _tlgKeywordOn
0x18014221b  test    al, al
0x18014221d  jz      short loc_18014227C
0x18014221f  lea     rcx, [rbp+2200h+var_2270]; this
0x180142223  call    ?GetTimeSec@CQPCStopWatch@@QEAANXZ; CQPCStopWatch::GetTimeSec(void)
0x180142228  movsd   [rsp+2300h+var_2290], xmm0
0x18014222e  mov     dword ptr [rsp+2300h+var_22A8], r15d
0x180142233  mov     rax, [rsp+2300h+pv]
0x180142238  mov     [rsp+2300h+var_2298], rax
0x18014223d  mov     [rbp+2200h+var_2278], 800h
0x180142245  lea     rax, [rsp+2300h+var_2290]
0x18014224a  mov     [rsp+2300h+var_22C8], rax
0x18014224f  lea     rax, [rsp+2300h+var_22A8]
0x180142254  mov     [rsp+2300h+pcbData], rax
0x180142259  lea     rax, [rsp+2300h+var_2298]
0x18014225e  mov     [rsp+2300h+pvData], rax
0x180142263  lea     rax, [rbp+2200h+var_2278]
0x180142267  mov     [rsp+2300h+pdwType], rax
0x18014226c  lea     rdx, unk_1801A9E49
0x180142273  mov     rcx, r8
0x180142276  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18014227b  nop
0x18014227c  mov     rcx, [rsp+2300h+pv]; pv
0x180142281  call    cs:__imp_CoTaskMemFree
0x180142287  mov     [rsp+2300h+pv], 0
0x180142290  lea     rcx, [rbp+2200h+var_2280]
0x180142294  call    ??1?$unique_ptr@UPacketSizeConstraints@@U?$default_delete@UPacketSizeConstraints@@@std@@@std@@QEAA@XZ; std::unique_ptr<PacketSizeConstraints>::~unique_ptr<PacketSizeConstraints>(void)
0x180142299  nop
0x18014229a  mov     rcx, rbx; pv
0x18014229d  call    cs:__imp_CoTaskMemFree
0x1801422a3  nop
0x1801422a4  mov     rcx, rdi; pv
0x1801422a7  call    cs:__imp_CoTaskMemFree
0x1801422ad  mov     eax, r15d
0x1801422b0  mov     rcx, [rbp+2200h+var_50]
0x1801422b7  xor     rcx, rsp; StackCookie
0x1801422ba  call    __security_check_cookie
0x1801422bf  add     rsp, 22C8h
0x1801422c6  pop     r15
0x1801422c8  pop     r14
0x1801422ca  pop     r13
0x1801422cc  pop     r12
0x1801422ce  pop     rdi
0x1801422cf  pop     rsi
0x1801422d0  pop     rbx
0x1801422d1  pop     rbp
0x1801422d2  retn
```
