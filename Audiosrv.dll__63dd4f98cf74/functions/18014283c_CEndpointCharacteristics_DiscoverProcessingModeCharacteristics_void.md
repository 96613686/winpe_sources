# CEndpointCharacteristics::DiscoverProcessingModeCharacteristics(void)

- ea: `0x18014283c`
- end: `0x180142be7`
- name: `?DiscoverProcessingModeCharacteristics@CEndpointCharacteristics@@AEAAJXZ`
- size: `939`
- prototype: `__int64 __fastcall(struct IMMDevice **this)`
- caller_count: `2`
- callee_count: `16`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800663d4`
- `0x1800c95bc`

## callees

- `0x18000bca8`
- `0x180045dd0`
- `0x18005181c`
- `0x180068c70`
- `0x1800692b4`
- `0x18006f980`
- `0x180071250`
- `0x180072e10`
- `0x18008966c`
- `0x1800b35e8`
- `0x1800bb77c`
- `0x1800bbc18`
- `0x1800cd8d0`
- `0x18014283c`
- `0x1801435ec`
- `0x180160690`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18014293b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180142985`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18014293b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180142985`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x1801428a0`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x1801428a0`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180142aea`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180142aea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180142b95`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180142bb1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180142bbb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180142b95`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180142bb1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180142bbb`

## pseudocode

```c
__int64 __fastcall CEndpointCharacteristics::DiscoverProcessingModeCharacteristics(struct IMMDevice **this)
{
  int v2; // r15d
  struct KSMULTIPLE_ITEM *v3; // rbx
  int SupportedDataRangeForEndpoint; // eax
  struct KSMULTIPLE_ITEM *v5; // rdi
  ULONG Count; // r12d
  struct KSMULTIPLE_ITEM *v7; // r13
  int PacketSizeConstraints; // eax
  __int64 OemEnginePeriodicity; // rdx
  __int64 v10; // rsi
  int v11; // eax
  ULONG v12; // r8d
  struct KSMULTIPLE_ITEM *v13; // r9
  int v14; // r8d
  int v15; // r9d
  DWORD pcbData; // [rsp+50h] [rbp-B0h] BYREF
  int pvData; // [rsp+54h] [rbp-ACh] BYREF
  struct KSMULTIPLE_ITEM *v19; // [rsp+58h] [rbp-A8h] BYREF
  LPVOID pv; // [rsp+60h] [rbp-A0h] BYREF
  struct KSMULTIPLE_ITEM *v21; // [rsp+68h] [rbp-98h] BYREF
  __int64 TimeSec; // [rsp+70h] [rbp-90h] BYREF
  int v23; // [rsp+78h] [rbp-88h] BYREF
  __int64 v24; // [rsp+80h] [rbp-80h] BYREF
  __int64 v25; // [rsp+88h] [rbp-78h] BYREF
  __int64 v26; // [rsp+90h] [rbp-70h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+98h] [rbp-68h] BYREF
  LARGE_INTEGER Frequency; // [rsp+A0h] [rbp-60h] BYREF
  char v29[4]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v30; // [rsp+194h] [rbp+94h]
  int v31; // [rsp+119Ch] [rbp+109Ch]
  GUID v32; // [rsp+11A0h] [rbp+10A0h]
  char v33[4]; // [rsp+11B0h] [rbp+10B0h] BYREF
  __int64 v34; // [rsp+1294h] [rbp+1194h]
  int v35; // [rsp+229Ch] [rbp+219Ch]
  GUID v36; // [rsp+22A0h] [rbp+21A0h]

  v2 = 0;
  if ( (int)CEndpointCharacteristics::GetProcessingModeCharacteristicsFromPropertyStore((CEndpointCharacteristics *)this) < 0 )
  {
    v19 = 0;
    v3 = 0;
    v21 = 0;
    v24 = 0;
    PerformanceCount.QuadPart = 0;
    v26 = 0;
    QueryPerformanceFrequency(&Frequency);
    CQPCStopWatch::Start((CQPCStopWatch *)&v26);
    SupportedDataRangeForEndpoint = GetSupportedDataRangeForEndpoint(eHostProcessConnector, this[5], &v19);
    v5 = v19;
    if ( SupportedDataRangeForEndpoint < 0 )
    {
      Count = 0;
      v7 = 0;
    }
    else
    {
      Count = v19->Count;
      v7 = v19 + 1;
    }
    PacketSizeConstraints = GetPacketSizeConstraints(g_DeviceEnumerator, this[9], &v24);
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
    v23 = 0;
    pcbData = 4;
    RegGetValueW(
      HKEY_LOCAL_MACHINE,
      L"Software\\Microsoft\\Windows\\CurrentVersion\\Audio",
      L"MaxCapturePeriodicityInMs",
      0x18u,
      0,
      &v23,
      &pcbData);
    OemEnginePeriodicity = CEndpointCharacteristics::GetOemEnginePeriodicity((CEndpointCharacteristics *)this);
    TimeSec = OemEnginePeriodicity;
    v10 = v24;
    if ( v2 >= 0 && *((_DWORD *)this + 64) )
    {
      *(_DWORD *)v29 = 3;
      v30 = 0;
      v31 = 0;
      v32 = GUID_00000000_0000_0000_0000_000000000000;
      v11 = GetSupportedDataRangeForEndpoint(eKeywordDetectorConnector, this[5], &v21);
      v3 = v21;
      if ( v11 < 0 )
      {
        v12 = 0;
        v13 = 0;
      }
      else
      {
        v12 = v21->Count;
        v13 = v21 + 1;
      }
      v2 = CEndpointCharacteristics::DiscoverConnectorProcessingModeCharacteristics(
             (CEndpointCharacteristics *)this,
             3u,
             v12,
             (__int64)v13,
             v10,
             pvData != 0,
             TimeSec,
             (__int64)(this + 37),
             (char)v29);
      CEndpointCharacteristics::CacheUnsupportedConnectorFormats(
        (CEndpointCharacteristics *)this,
        (struct CUnsupportedConnectorFormats *)v29);
      OemEnginePeriodicity = TimeSec;
    }
    *(_DWORD *)v33 = 0;
    v34 = 0;
    v35 = 0;
    v36 = GUID_00000000_0000_0000_0000_000000000000;
    if ( v2 >= 0 )
    {
      v2 = CEndpointCharacteristics::DiscoverConnectorProcessingModeCharacteristics(
             (CEndpointCharacteristics *)this,
             0,
             Count,
             (__int64)v7,
             v10,
             pvData != 0,
             OemEnginePeriodicity,
             (__int64)(this + 34),
             (char)v33);
      if ( v2 >= 0 && !*((_DWORD *)this + 65) )
        CEndpointCharacteristics::CacheProcessingModeCharacteristics((CEndpointCharacteristics *)this);
    }
    CEndpointCharacteristics::CacheUnsupportedConnectorFormats(
      (CEndpointCharacteristics *)this,
      (struct CUnsupportedConnectorFormats *)v33);
    QueryPerformanceCounter(&PerformanceCount);
    pv = 0;
    if ( (int)CEndpointCharacteristics::GetEndpointId((CEndpointCharacteristics *)this, (unsigned __int16 **)&pv) >= 0
      && LODWORD(this[1036]->lpVtbl) > 4
      && (unsigned __int8)tlgKeywordOn(this[1036], 0x200000000010LL) )
    {
      TimeSec = CQPCStopWatch::GetTimeSec((CQPCStopWatch *)&v26);
      LODWORD(v19) = v2;
      v21 = (struct KSMULTIPLE_ITEM *)pv;
      v25 = 2048;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        v14,
        (unsigned int)byte_1801A9D71,
        v14,
        v15,
        (__int64)&v25,
        (__int64)&v21,
        (__int64)&v19,
        (__int64)&TimeSec);
    }
    CoTaskMemFree(pv);
    pv = 0;
    std::unique_ptr<PacketSizeConstraints>::~unique_ptr<PacketSizeConstraints>(&v24);
    CoTaskMemFree(v3);
    CoTaskMemFree(v5);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18014283c  push    rbp
0x18014283e  push    rbx
0x18014283f  push    rsi
0x180142840  push    rdi
0x180142841  push    r12
0x180142843  push    r13
0x180142845  push    r14
0x180142847  push    r15
0x180142849  lea     rbp, [rsp-21C8h]
0x180142851  mov     eax, 22C8h
0x180142856  call    _alloca_probe
0x18014285b  sub     rsp, rax
0x18014285e  mov     rax, cs:__security_cookie
0x180142865  xor     rax, rsp
0x180142868  mov     [rbp+2200h+var_50], rax
0x18014286f  mov     r14, rcx
0x180142872  xor     esi, esi
0x180142874  mov     r15d, esi
0x180142877  call    ?GetProcessingModeCharacteristicsFromPropertyStore@CEndpointCharacteristics@@AEAAJXZ; CEndpointCharacteristics::GetProcessingModeCharacteristicsFromPropertyStore(void)
0x18014287c  test    eax, eax
0x18014287e  jns     loc_180142BC1
0x180142884  mov     [rsp+2300h+var_22A8], rsi
0x180142889  mov     ebx, esi
0x18014288b  mov     [rsp+2300h+var_2298], rbx
0x180142890  mov     [rbp+2200h+var_2280], rsi
0x180142894  mov     qword ptr [rbp+2200h+PerformanceCount], rsi
0x180142898  mov     [rbp+2200h+var_2270], rsi
0x18014289c  lea     rcx, [rbp+2200h+Frequency]; lpFrequency
0x1801428a0  call    cs:__imp_QueryPerformanceFrequency
0x1801428a6  lea     rcx, [rbp+2200h+var_2270]; this
0x1801428aa  call    ?Start@CQPCStopWatch@@QEAAHXZ; CQPCStopWatch::Start(void)
0x1801428af  lea     r8, [rsp+2300h+var_22A8]; struct KSMULTIPLE_ITEM **
0x1801428b4  mov     rdx, [r14+28h]; struct IMMDevice *
0x1801428b8  xor     ecx, ecx; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x1801428ba  call    ?GetSupportedDataRangeForEndpoint@@YAJW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEAUIMMDevice@@PEAPEAUKSMULTIPLE_ITEM@@@Z; GetSupportedDataRangeForEndpoint(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,IMMDevice *,KSMULTIPLE_ITEM * *)
0x1801428bf  mov     rdi, [rsp+2300h+var_22A8]
0x1801428c4  test    eax, eax
0x1801428c6  js      short loc_1801428D2
0x1801428c8  mov     r12d, [rdi+4]
0x1801428cc  lea     r13, [rdi+8]
0x1801428d0  jmp     short loc_1801428D8
0x1801428d2  mov     r12d, esi
0x1801428d5  mov     r13, rsi
0x1801428d8  lea     r8, [rbp+2200h+var_2280]
0x1801428dc  mov     rdx, [r14+48h]
0x1801428e0  mov     rcx, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x1801428e7  call    ?GetPacketSizeConstraints@@YAJPEAUIMMDeviceEnumerator@@PEAUIPropertyStore@@AEAV?$unique_ptr@UPacketSizeConstraints@@U?$default_delete@UPacketSizeConstraints@@@std@@@std@@@Z; GetPacketSizeConstraints(IMMDeviceEnumerator *,IPropertyStore *,std::unique_ptr<PacketSizeConstraints> &)
0x1801428ec  mov     r15d, esi
0x1801428ef  cmp     eax, 80070490h
0x1801428f4  cmovnz  r15d, eax
0x1801428f8  mov     [rsp+2300h+var_22AC], esi
0x1801428fc  mov     [rsp+2300h+var_22B0], 4
0x180142904  lea     rax, [rsp+2300h+var_22B0]
0x180142909  mov     [rsp+2300h+pcbData], rax; pcbData
0x18014290e  lea     rax, [rsp+2300h+var_22AC]
0x180142913  mov     [rsp+2300h+pvData], rax; pvData
0x180142918  mov     [rsp+2300h+pdwType], rsi; pdwType
0x18014291d  mov     r9d, 18h; dwFlags
0x180142923  lea     r8, aProbeforminimu; "ProbeForMinimumPeriod"
0x18014292a  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180142931  mov     rsi, 0FFFFFFFF80000002h
0x180142938  mov     rcx, rsi; hkey
0x18014293b  call    cs:__imp_RegGetValueW
0x180142941  mov     [rsp+2300h+var_2288], 0
0x180142949  mov     [rsp+2300h+var_22B0], 4
0x180142951  lea     rax, [rsp+2300h+var_22B0]
0x180142956  mov     [rsp+2300h+pcbData], rax; pcbData
0x18014295b  lea     rax, [rsp+2300h+var_2288]
0x180142960  mov     [rsp+2300h+pvData], rax; pvData
0x180142965  mov     [rsp+2300h+pdwType], 0; pdwType
0x18014296e  mov     r9d, 18h; dwFlags
0x180142974  lea     r8, aMaxcaptureperi; "MaxCapturePeriodicityInMs"
0x18014297b  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180142982  mov     rcx, rsi; hkey
0x180142985  call    cs:__imp_RegGetValueW
0x18014298b  mov     rcx, r14; this
0x18014298e  call    ?GetOemEnginePeriodicity@CEndpointCharacteristics@@AEAA_JXZ; CEndpointCharacteristics::GetOemEnginePeriodicity(void)
0x180142993  mov     rdx, rax
0x180142996  mov     [rsp+2300h+var_2290], rax
0x18014299b  mov     rsi, [rbp+2200h+var_2280]
0x18014299f  xor     ecx, ecx
0x1801429a1  test    r15d, r15d
0x1801429a4  js      loc_180142A56
0x1801429aa  cmp     [r14+100h], ecx
0x1801429b1  jz      loc_180142A56
0x1801429b7  lea     r15d, [rcx+3]
0x1801429bb  mov     dword ptr [rbp+2200h+var_2250], r15d
0x1801429bf  mov     [rbp+2200h+var_216C], rcx
0x1801429c6  mov     [rbp+2200h+var_1164], ecx
0x1801429cc  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1801429d3  movdqu  [rbp+2200h+var_1160], xmm0
0x1801429db  lea     r8, [rsp+2300h+var_2298]; struct KSMULTIPLE_ITEM **
0x1801429e0  mov     rdx, [r14+28h]; struct IMMDevice *
0x1801429e4  mov     ecx, r15d; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x1801429e7  call    ?GetSupportedDataRangeForEndpoint@@YAJW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEAUIMMDevice@@PEAPEAUKSMULTIPLE_ITEM@@@Z; GetSupportedDataRangeForEndpoint(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,IMMDevice *,KSMULTIPLE_ITEM * *)
0x1801429ec  mov     rbx, [rsp+2300h+var_2298]
0x1801429f1  test    eax, eax
0x1801429f3  js      short loc_1801429FF
0x1801429f5  mov     r8d, [rbx+4]
0x1801429f9  lea     r9, [rbx+8]
0x1801429fd  jmp     short loc_180142A05
0x1801429ff  xor     r8d, r8d
0x180142a02  xor     r9d, r9d
0x180142a05  cmp     [rsp+2300h+var_22AC], 0
0x180142a0a  setnz   cl
0x180142a0d  lea     rax, [r14+128h]
0x180142a14  lea     r10, [rbp+2200h+var_2250]
0x180142a18  mov     qword ptr [rsp+2300h+var_22C0], r10; char
0x180142a1d  mov     [rsp+2300h+var_22C8], rax; __int64
0x180142a22  mov     rax, [rsp+2300h+var_2290]
0x180142a27  mov     [rsp+2300h+pcbData], rax; __int64
0x180142a2c  mov     byte ptr [rsp+2300h+pvData], cl; char
0x180142a30  mov     [rsp+2300h+pdwType], rsi; __int64
0x180142a35  mov     edx, r15d
0x180142a38  mov     rcx, r14; this
0x180142a3b  call    ?DiscoverConnectorProcessingModeCharacteristics@CEndpointCharacteristics@@AEAAJW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@IPEATKSDATAFORMAT@@PEAUPacketSizeConstraints@@_N_JAEAV?$vector@V?$unique_ptr@VCConnectorProcessingModeCharacteristics@@U?$default_delete@VCConnectorProcessingModeCharacteristics@@@std@@@std@@V?$allocator@V?$unique_ptr@VCConnectorProcessingModeCharacteristics@@U?$default_delete@VCConnectorProcessingModeCharacteristics@@@std@@@std@@@2@@std@@PEAVCUnsupportedConnectorFormats@@@Z; CEndpointCharacteristics::DiscoverConnectorProcessingModeCharacteristics(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,uint,KSDATAFORMAT *,PacketSizeConstraints *,bool,__int64,std::vector<std::unique_ptr<CConnectorProcessingModeCharacteristics>> &,CUnsupportedConnectorFormats *)
0x180142a40  mov     r15d, eax
0x180142a43  lea     rdx, [rbp+2200h+var_2250]; struct CUnsupportedConnectorFormats *
0x180142a47  mov     rcx, r14; this
0x180142a4a  call    ?CacheUnsupportedConnectorFormats@CEndpointCharacteristics@@AEAAXPEAVCUnsupportedConnectorFormats@@@Z; CEndpointCharacteristics::CacheUnsupportedConnectorFormats(CUnsupportedConnectorFormats *)
0x180142a4f  mov     rdx, [rsp+2300h+var_2290]
0x180142a54  xor     ecx, ecx
0x180142a56  mov     dword ptr [rbp+2200h+var_1150], ecx
0x180142a5c  mov     [rbp+2200h+var_106C], 0
0x180142a67  mov     [rbp+2200h+var_64], ecx
0x180142a6d  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180142a74  movdqu  [rbp+2200h+var_60], xmm0
0x180142a7c  test    r15d, r15d
0x180142a7f  js      short loc_180142AD7
0x180142a81  cmp     [rsp+2300h+var_22AC], ecx
0x180142a85  setnz   cl
0x180142a88  lea     rax, [r14+110h]
0x180142a8f  lea     r8, [rbp+2200h+var_1150]
0x180142a96  mov     qword ptr [rsp+2300h+var_22C0], r8; char
0x180142a9b  mov     [rsp+2300h+var_22C8], rax; __int64
0x180142aa0  mov     [rsp+2300h+pcbData], rdx; __int64
0x180142aa5  mov     byte ptr [rsp+2300h+pvData], cl; char
0x180142aa9  mov     [rsp+2300h+pdwType], rsi; __int64
0x180142aae  mov     r9, r13
0x180142ab1  mov     r8d, r12d
0x180142ab4  xor     edx, edx
0x180142ab6  mov     rcx, r14; this
0x180142ab9  call    ?DiscoverConnectorProcessingModeCharacteristics@CEndpointCharacteristics@@AEAAJW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@IPEATKSDATAFORMAT@@PEAUPacketSizeConstraints@@_N_JAEAV?$vector@V?$unique_ptr@VCConnectorProcessingModeCharacteristics@@U?$default_delete@VCConnectorProcessingModeCharacteristics@@@std@@@std@@V?$allocator@V?$unique_ptr@VCConnectorProcessingModeCharacteristics@@U?$default_delete@VCConnectorProcessingModeCharacteristics@@@std@@@std@@@2@@std@@PEAVCUnsupportedConnectorFormats@@@Z; CEndpointCharacteristics::DiscoverConnectorProcessingModeCharacteristics(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,uint,KSDATAFORMAT *,PacketSizeConstraints *,bool,__int64,std::vector<std::unique_ptr<CConnectorProcessingModeCharacteristics>> &,CUnsupportedConnectorFormats *)
0x180142abe  mov     r15d, eax
0x180142ac1  test    eax, eax
0x180142ac3  js      short loc_180142AD7
0x180142ac5  cmp     dword ptr [r14+104h], 0
0x180142acd  jnz     short loc_180142AD7
0x180142acf  mov     rcx, r14; this
0x180142ad2  call    ?CacheProcessingModeCharacteristics@CEndpointCharacteristics@@AEAAJXZ; CEndpointCharacteristics::CacheProcessingModeCharacteristics(void)
0x180142ad7  lea     rdx, [rbp+2200h+var_1150]; struct CUnsupportedConnectorFormats *
0x180142ade  mov     rcx, r14; this
0x180142ae1  call    ?CacheUnsupportedConnectorFormats@CEndpointCharacteristics@@AEAAXPEAVCUnsupportedConnectorFormats@@@Z; CEndpointCharacteristics::CacheUnsupportedConnectorFormats(CUnsupportedConnectorFormats *)
0x180142ae6  lea     rcx, [rbp+2200h+PerformanceCount]; lpPerformanceCount
0x180142aea  call    cs:__imp_QueryPerformanceCounter
0x180142af0  mov     [rsp+2300h+pv], 0
0x180142af9  lea     rdx, [rsp+2300h+pv]; unsigned __int16 **
0x180142afe  mov     rcx, r14; this
0x180142b01  call    ?GetEndpointId@CEndpointCharacteristics@@QEAAJPEAPEAG@Z; CEndpointCharacteristics::GetEndpointId(ushort * *)
0x180142b06  test    eax, eax
0x180142b08  js      loc_180142B90
0x180142b0e  mov     r8, [r14+2060h]
0x180142b15  mov     eax, [r8]
0x180142b18  cmp     eax, 4
0x180142b1b  jbe     short loc_180142B90
0x180142b1d  mov     rdx, 200000000010h
0x180142b27  mov     rcx, r8
0x180142b2a  call    _tlgKeywordOn
0x180142b2f  test    al, al
0x180142b31  jz      short loc_180142B90
0x180142b33  lea     rcx, [rbp+2200h+var_2270]; this
0x180142b37  call    ?GetTimeSec@CQPCStopWatch@@QEAANXZ; CQPCStopWatch::GetTimeSec(void)
0x180142b3c  movsd   [rsp+2300h+var_2290], xmm0
0x180142b42  mov     dword ptr [rsp+2300h+var_22A8], r15d
0x180142b47  mov     rax, [rsp+2300h+pv]
0x180142b4c  mov     [rsp+2300h+var_2298], rax
0x180142b51  mov     [rbp+2200h+var_2278], 800h
0x180142b59  lea     rax, [rsp+2300h+var_2290]
0x180142b5e  mov     [rsp+2300h+var_22C8], rax
0x180142b63  lea     rax, [rsp+2300h+var_22A8]
0x180142b68  mov     [rsp+2300h+pcbData], rax
0x180142b6d  lea     rax, [rsp+2300h+var_2298]
0x180142b72  mov     [rsp+2300h+pvData], rax
0x180142b77  lea     rax, [rbp+2200h+var_2278]
0x180142b7b  mov     [rsp+2300h+pdwType], rax
0x180142b80  lea     rdx, byte_1801A9D71
0x180142b87  mov     rcx, r8
0x180142b8a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x180142b8f  nop
0x180142b90  mov     rcx, [rsp+2300h+pv]; pv
0x180142b95  call    cs:__imp_CoTaskMemFree
0x180142b9b  mov     [rsp+2300h+pv], 0
0x180142ba4  lea     rcx, [rbp+2200h+var_2280]
0x180142ba8  call    ??1?$unique_ptr@UPacketSizeConstraints@@U?$default_delete@UPacketSizeConstraints@@@std@@@std@@QEAA@XZ; std::unique_ptr<PacketSizeConstraints>::~unique_ptr<PacketSizeConstraints>(void)
0x180142bad  nop
0x180142bae  mov     rcx, rbx; pv
0x180142bb1  call    cs:__imp_CoTaskMemFree
0x180142bb7  nop
0x180142bb8  mov     rcx, rdi; pv
0x180142bbb  call    cs:__imp_CoTaskMemFree
0x180142bc1  mov     eax, r15d
0x180142bc4  mov     rcx, [rbp+2200h+var_50]
0x180142bcb  xor     rcx, rsp; StackCookie
0x180142bce  call    __security_check_cookie
0x180142bd3  add     rsp, 22C8h
0x180142bda  pop     r15
0x180142bdc  pop     r14
0x180142bde  pop     r13
0x180142be0  pop     r12
0x180142be2  pop     rdi
0x180142be3  pop     rsi
0x180142be4  pop     rbx
0x180142be5  pop     rbp
0x180142be6  retn
```
