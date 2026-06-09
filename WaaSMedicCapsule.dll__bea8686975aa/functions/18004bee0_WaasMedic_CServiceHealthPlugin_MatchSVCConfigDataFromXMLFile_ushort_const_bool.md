# WaasMedic::CServiceHealthPlugin::MatchSVCConfigDataFromXMLFile(ushort const *,bool &)

- ea: `0x18004bee0`
- end: `0x18004c244`
- name: `?MatchSVCConfigDataFromXMLFile@CServiceHealthPlugin@WaasMedic@@AEAAJPEBGAEA_N@Z`
- size: `868`
- prototype: `int(WaasMedic::CServiceHealthPlugin *__hidden this, const unsigned __int16 *, bool *)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180002058`
- `0x180003bd4`
- `0x1800040b8`
- `0x180009a54`
- `0x180016c9c`
- `0x18002543c`
- `0x1800333e4`
- `0x180033464`
- `0x1800344c4`
- `0x18003460c`
- `0x180034f00`
- `0x18004bee0`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18004c1d2`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18004c1d2`

## string_xrefs

- `0x18004bf1b`: `onecore\enduser\waasmedic\lib\plugins\servicehealthplugin.cpp`
- `0x18004bfb8`: `Looking for service config information in file %ws`
- `0x18004bff2`: `Successfully gathered service config information from file %ws. Service name is %ws`
- `0x18004c1eb`: `Failed to gather service info from file [%ws] ErrorCode = 0x%08x`
- `0x18004c02d`: `Failed to gather service config info from device for service %ws ErrorCode = 0x%08x`
- `0x18004c019`: `Successfully gathered service config information from device. Service name is %ws`
- `0x18004c06d`: `MatchServiceConfiguration succeeded for service [%ws]`
- `0x18004c041`: `Comparing service configuration information for service %ws`
- `0x18004c09c`: `Service configuration on the device does NOT match with service configuration in component XML for service [%ws]. ErrorCode = 0x%08x`
- `0x18004c085`: `Service configuration on the device matches with service configuration in component XML for service [%ws]`
- `0x18004c1dc`: `MatchServiceConfiguration failed for service [%ws] ErrorCode = 0x%08x`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WaasMedic::CServiceHealthPlugin::MatchSVCConfigDataFromXMLFile(
        WaasMedic::CServiceHealthPlugin *this,
        const unsigned __int16 *a2,
        bool *a3)
{
  void *v7; // rbx
  unsigned __int16 *v8; // rsi
  int v9; // eax
  unsigned int matched; // r14d
  WaasMedic *v11; // rdi
  int v12; // eax
  bool *v13; // r9
  char *v14; // r15
  __int64 v15; // r13
  _QWORD *v16; // rax
  _QWORD *v17; // rdx
  __int64 v18; // rbx
  _QWORD *v19; // rax
  _QWORD *v20; // rcx
  const struct _tlgProvider_t *v21; // rax
  int v22; // r9d
  int v23; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+40h]
  WaasMedic *v26; // [rsp+A8h] [rbp+50h] BYREF
  unsigned __int16 *v27; // [rsp+B0h] [rbp+58h] BYREF
  __int64 v28; // [rsp+B8h] [rbp+60h] BYREF

  LOBYTE(v26) = 0;
  *a3 = 0;
  if ( a2 )
  {
    v7 = operator new(0x50u);
    v27 = (unsigned __int16 *)v7;
    *(_BYTE *)v7 = 0;
    *((_QWORD *)v7 + 1) = 0;
    *((_QWORD *)v7 + 2) = 0;
    *((_QWORD *)v7 + 3) = 0;
    *((_QWORD *)v7 + 4) = 0;
    *((_QWORD *)v7 + 5) = 0;
    *((_DWORD *)v7 + 12) = -1;
    *((_DWORD *)v7 + 13) = -1;
    *((_DWORD *)v7 + 14) = -1;
    *((_QWORD *)v7 + 8) = 0;
    *((_DWORD *)v7 + 18) = -1;
    *((_DWORD *)v7 + 19) = 0;
    v8 = (unsigned __int16 *)operator new(0x68u);
    v27 = v8;
    *(_BYTE *)v8 = 0;
    *((_QWORD *)v8 + 1) = 0;
    *((_QWORD *)v8 + 2) = 0;
    *((_QWORD *)v8 + 3) = 0;
    *((_QWORD *)v8 + 4) = 0;
    *((_QWORD *)v8 + 5) = 0;
    *((_QWORD *)v8 + 6) = 0;
    *((_QWORD *)v8 + 7) = 0;
    *((_QWORD *)v8 + 8) = 0;
    *((_QWORD *)v8 + 9) = 0;
    *((_QWORD *)v8 + 10) = 0;
    *((_QWORD *)v8 + 11) = 0;
    *((_QWORD *)v8 + 12) = 0;
    LogLevelW(4u, L"Looking for service config information in file %ws", a2);
    v9 = WaasMedic::CServiceInformationFromXML::GatherServiceInfoFromComponentXML(
           (WaasMedic::CServiceInformationFromXML *)v7,
           a2);
    matched = v9;
    if ( v9 >= 0 && (v11 = (WaasMedic *)*((_QWORD *)v7 + 1)) != 0 )
    {
      LogLevelW(
        4u,
        L"Successfully gathered service config information from file %ws. Service name is %ws",
        a2,
        *((_QWORD *)v7 + 1));
      v12 = WaasMedic::CServiceInformationFromDevice::GatherServiceInfoFromDevice(
              (WaasMedic::CServiceInformationFromDevice *)v8,
              v11);
      if ( v12 < 0 )
        LogLevelW(
          3u,
          L"Failed to gather service config info from device for service %ws ErrorCode = 0x%08x",
          v11,
          (unsigned int)v12);
      else
        LogLevelW(4u, L"Successfully gathered service config information from device. Service name is %ws", v11);
      LogLevelW(4u, L"Comparing service configuration information for service %ws", v11);
      matched = WaasMedic::MatchServiceConfiguration(
                  (WaasMedic *)v7,
                  (struct WaasMedic::CServiceInformationFromXML *)v8,
                  (struct WaasMedic::CServiceInformationFromDevice *)&v26,
                  v13);
      if ( (matched & 0x80000000) != 0 )
      {
        LogLevelW(2u, L"MatchServiceConfiguration failed for service [%ws] ErrorCode = 0x%08x", v11, matched);
      }
      else
      {
        LogLevelW(4u, L"MatchServiceConfiguration succeeded for service [%ws]", v11);
        if ( (_BYTE)v26 )
        {
          LogLevelW(
            4u,
            L"Service configuration on the device matches with service configuration in component XML for service [%ws]",
            v11);
        }
        else
        {
          LogLevelW(
            3u,
            L"Service configuration on the device does NOT match with service configuration in component XML for service ["
             "%ws]. ErrorCode = 0x%08x",
            v11,
            matched);
          v14 = (char *)this + 232;
          v15 = *((_QWORD *)this + 29);
          if ( *((_QWORD *)v14 + 1) == 0xAAAAAAAAAAAAAAALL )
            goto LABEL_17;
          v16 = operator new(0x18u);
          v16[2] = v7;
          ++*((_QWORD *)v14 + 1);
          v17 = *(_QWORD **)(v15 + 8);
          *v16 = v15;
          v16[1] = v17;
          *(_QWORD *)(v15 + 8) = v16;
          *v17 = v16;
          if ( *((_QWORD *)this + 32) == 0xAAAAAAAAAAAAAAALL )
LABEL_17:
            std::_Xlength_error("list too long");
          v18 = *((_QWORD *)this + 31);
          v19 = operator new(0x18u);
          v19[2] = v8;
          ++*((_QWORD *)this + 32);
          v20 = *(_QWORD **)(v18 + 8);
          *v19 = v18;
          v19[1] = v20;
          *(_QWORD *)(v18 + 8) = v19;
          *v20 = v19;
          *a3 = 1;
          v7 = 0;
          v8 = 0;
          v21 = WaasMedic::TelemetryProvider::Provider();
          if ( *(_DWORD *)v21 > 5u
            && (*((_QWORD *)v21 + 2) & 0x400000000000LL) != 0
            && (*((_QWORD *)v21 + 3) & 0x400000000000LL) == *((_QWORD *)v21 + 3) )
          {
            v26 = v11;
            v27 = &gc_pszVersionString;
            v28 = 0x1000000;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
              (_DWORD)v21,
              (unsigned int)&unk_18008A128,
              0,
              v22,
              (__int64)&v28,
              (__int64)&v27,
              (__int64)&v26);
          }
        }
      }
    }
    else
    {
      LogLevelW(2u, L"Failed to gather service info from file [%ws] ErrorCode = 0x%08x", a2, (unsigned int)v9);
    }
    if ( v7 )
    {
      WaasMedic::CServiceInformationFromXML::~CServiceInformationFromXML((WaasMedic::CServiceInformationFromXML *)v7);
      operator delete(v7, (const struct std::nothrow_t *)0x50);
    }
    if ( v8 )
    {
      WaasMedic::CServiceInformationFromDevice::~CServiceInformationFromDevice((WaasMedic::CServiceInformationFromDevice *)v8);
      operator delete(v8, (const struct std::nothrow_t *)0x68);
    }
    return matched;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2AD,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\servicehealthplugin.cpp",
      (const char *)0x80004003LL,
      v23);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x18004bee0  mov     [rsp-40h+arg_0], rcx
0x18004bee5  push    rbp
0x18004bee6  push    rbx
0x18004bee7  push    rsi
0x18004bee8  push    rdi
0x18004bee9  push    r12
0x18004beeb  push    r13
0x18004beed  push    r14
0x18004beef  push    r15
0x18004bef1  mov     rbp, rsp
0x18004bef4  sub     rsp, 58h
0x18004bef8  mov     r12, r8
0x18004befb  mov     r15, rdx
0x18004befe  mov     r13, rcx
0x18004bf01  xor     edi, edi
0x18004bf03  mov     byte ptr [rbp+arg_8], dil
0x18004bf07  mov     [r8], dil
0x18004bf0a  test    rdx, rdx
0x18004bf0d  jnz     short loc_18004BF33
0x18004bf0f  mov     rcx, [rbp+40h]; this
0x18004bf13  mov     ebx, 80004003h
0x18004bf18  mov     r9d, ebx; char *
0x18004bf1b  lea     r8, aOnecoreEnduser_40; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x18004bf22  mov     edx, 2ADh; void *
0x18004bf27  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004bf2c  mov     eax, ebx
0x18004bf2e  jmp     loc_18004C233
0x18004bf33  mov     ecx, 50h ; 'P'; Size
0x18004bf38  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004bf3d  mov     rbx, rax
0x18004bf40  mov     [rbp+arg_10], rax
0x18004bf44  mov     [rax], dil
0x18004bf47  mov     [rax+8], rdi
0x18004bf4b  mov     [rax+10h], rdi
0x18004bf4f  mov     [rax+18h], rdi
0x18004bf53  mov     [rax+20h], rdi
0x18004bf57  mov     [rax+28h], rdi
0x18004bf5b  or      eax, 0FFFFFFFFh
0x18004bf5e  mov     [rbx+30h], eax
0x18004bf61  mov     [rbx+34h], eax
0x18004bf64  mov     [rbx+38h], eax
0x18004bf67  mov     [rbx+40h], rdi
0x18004bf6b  mov     [rbx+48h], eax
0x18004bf6e  mov     [rbx+4Ch], edi
0x18004bf71  mov     ecx, 68h ; 'h'; Size
0x18004bf76  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004bf7b  mov     rsi, rax
0x18004bf7e  mov     [rbp+arg_10], rax
0x18004bf82  mov     [rax], dil
0x18004bf85  mov     [rax+8], rdi
0x18004bf89  mov     [rax+10h], rdi
0x18004bf8d  mov     [rax+18h], rdi
0x18004bf91  mov     [rax+20h], rdi
0x18004bf95  mov     [rax+28h], rdi
0x18004bf99  mov     [rax+30h], rdi
0x18004bf9d  mov     [rax+38h], rdi
0x18004bfa1  mov     [rax+40h], rdi
0x18004bfa5  mov     [rax+48h], rdi
0x18004bfa9  mov     [rax+50h], rdi
0x18004bfad  mov     [rax+58h], rdi
0x18004bfb1  mov     [rax+60h], rdi
0x18004bfb5  mov     r8, r15
0x18004bfb8  lea     rdx, aLookingForServ; "Looking for service config information "...
0x18004bfbf  mov     ecx, 4; unsigned __int8
0x18004bfc4  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18004bfc9  mov     rdx, r15; unsigned __int16 *
0x18004bfcc  mov     rcx, rbx; this
0x18004bfcf  call    ?GatherServiceInfoFromComponentXML@CServiceInformationFromXML@WaasMedic@@QEAAJPEBG@Z; WaasMedic::CServiceInformationFromXML::GatherServiceInfoFromComponentXML(ushort const *)
0x18004bfd4  mov     r14d, eax
0x18004bfd7  test    eax, eax
0x18004bfd9  js      loc_18004C1E5
0x18004bfdf  mov     rdi, [rbx+8]
0x18004bfe3  test    rdi, rdi
0x18004bfe6  jz      loc_18004C1E5
0x18004bfec  mov     r9, rdi
0x18004bfef  mov     r8, r15
0x18004bff2  lea     rdx, aSuccessfullyGa; "Successfully gathered service config in"...
0x18004bff9  mov     r15d, 4
0x18004bfff  mov     ecx, r15d; unsigned __int8
0x18004c002  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18004c007  mov     rdx, rdi; unsigned __int16 *
0x18004c00a  mov     rcx, rsi; this
0x18004c00d  call    ?GatherServiceInfoFromDevice@CServiceInformationFromDevice@WaasMedic@@QEAAJPEBG@Z; WaasMedic::CServiceInformationFromDevice::GatherServiceInfoFromDevice(ushort const *)
0x18004c012  mov     r8, rdi
0x18004c015  test    eax, eax
0x18004c017  js      short loc_18004C02A
0x18004c019  lea     rdx, aSuccessfullyGa_0; "Successfully gathered service config in"...
0x18004c020  mov     ecx, r15d; unsigned __int8
0x18004c023  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18004c028  jmp     short loc_18004C03E
0x18004c02a  mov     r9d, eax
0x18004c02d  lea     rdx, aFailedToGather_0; "Failed to gather service config info fr"...
0x18004c034  mov     ecx, 3; unsigned __int8
0x18004c039  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18004c03e  mov     r8, rdi
0x18004c041  lea     rdx, aComparingServi; "Comparing service configuration informa"...
0x18004c048  mov     ecx, r15d; unsigned __int8
0x18004c04b  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18004c050  lea     r8, [rbp+arg_8]; struct WaasMedic::CServiceInformationFromDevice *
0x18004c054  mov     rdx, rsi; struct WaasMedic::CServiceInformationFromXML *
0x18004c057  mov     rcx, rbx; this
0x18004c05a  call    ?MatchServiceConfiguration@WaasMedic@@YAJPEAVCServiceInformationFromXML@1@PEAVCServiceInformationFromDevice@1@PEA_N@Z; WaasMedic::MatchServiceConfiguration(WaasMedic::CServiceInformationFromXML *,WaasMedic::CServiceInformationFromDevice *,bool *)
0x18004c05f  mov     r14d, eax
0x18004c062  mov     r8, rdi
0x18004c065  test    eax, eax
0x18004c067  js      loc_18004C1D9
0x18004c06d  lea     rdx, aMatchserviceco_0; "MatchServiceConfiguration succeeded for"...
0x18004c074  mov     ecx, r15d; unsigned __int8
0x18004c077  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18004c07c  mov     r8, rdi
0x18004c07f  cmp     byte ptr [rbp+arg_8], 0
0x18004c083  jz      short loc_18004C099
0x18004c085  lea     rdx, aServiceConfigu_0; "Service configuration on the device mat"...
0x18004c08c  mov     ecx, r15d; unsigned __int8
0x18004c08f  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18004c094  jmp     loc_18004C1FC
0x18004c099  mov     r9d, r14d
0x18004c09c  lea     rdx, aServiceConfigu; "Service configuration on the device doe"...
0x18004c0a3  mov     ecx, 3; unsigned __int8
0x18004c0a8  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18004c0ad  lea     r15, [r13+0E8h]
0x18004c0b4  mov     r13, [r15]
0x18004c0b7  mov     rax, 0AAAAAAAAAAAAAAAh
0x18004c0c1  cmp     [r15+8], rax
0x18004c0c5  jz      loc_18004C1CB
0x18004c0cb  mov     [rbp+var_18], r15
0x18004c0cf  mov     [rbp+var_10], 0
0x18004c0d7  mov     ecx, 18h; Size
0x18004c0dc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004c0e1  mov     [rax+10h], rbx
0x18004c0e5  inc     qword ptr [r15+8]
0x18004c0e9  mov     rdx, [r13+8]
0x18004c0ed  mov     [rax], r13
0x18004c0f0  mov     [rax+8], rdx
0x18004c0f4  mov     [r13+8], rax
0x18004c0f8  mov     [rdx], rax
0x18004c0fb  mov     r15, [rbp+arg_0]
0x18004c0ff  add     r15, 0F8h
0x18004c106  mov     rax, 0AAAAAAAAAAAAAAAh
0x18004c110  cmp     [r15+8], rax
0x18004c114  jz      loc_18004C1CB
0x18004c11a  mov     rbx, [r15]
0x18004c11d  mov     [rbp+var_18], r15
0x18004c121  mov     [rbp+var_10], 0
0x18004c129  mov     ecx, 18h; Size
0x18004c12e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004c133  mov     [rax+10h], rsi
0x18004c137  inc     qword ptr [r15+8]
0x18004c13b  mov     rcx, [rbx+8]
0x18004c13f  mov     [rax], rbx
0x18004c142  mov     [rax+8], rcx
0x18004c146  mov     [rbx+8], rax
0x18004c14a  mov     [rcx], rax
0x18004c14d  mov     byte ptr [r12], 1
0x18004c152  xor     ebx, ebx
0x18004c154  xor     esi, esi
0x18004c156  call    ?Provider@TelemetryProvider@WaasMedic@@SAPEBU_tlgProvider_t@@XZ; WaasMedic::TelemetryProvider::Provider(void)
0x18004c15b  mov     ecx, [rax]
0x18004c15d  cmp     ecx, 5
0x18004c160  jbe     loc_18004C1FC
0x18004c166  mov     rdx, [rax+18h]
0x18004c16a  mov     rcx, [rax+10h]
0x18004c16e  mov     r8, 400000000000h
0x18004c178  test    r8, rcx
0x18004c17b  jz      short loc_18004C1FC
0x18004c17d  mov     rcx, rdx
0x18004c180  and     rcx, r8
0x18004c183  cmp     rcx, rdx
0x18004c186  jnz     short loc_18004C1FC
0x18004c188  mov     [rbp+arg_8], rdi
0x18004c18c  lea     rcx, ?gc_pszVersionString@@3PAGA; ushort near * gc_pszVersionString
0x18004c193  mov     [rbp+arg_10], rcx
0x18004c197  mov     [rbp+arg_18], 1000000h
0x18004c19f  lea     rcx, [rbp+arg_8]
0x18004c1a3  mov     [rsp+58h+var_28], rcx
0x18004c1a8  lea     rcx, [rbp+arg_10]
0x18004c1ac  mov     [rsp+58h+var_30], rcx
0x18004c1b1  lea     rcx, [rbp+arg_18]
0x18004c1b5  mov     [rsp+58h+var_38], rcx
0x18004c1ba  lea     rdx, unk_18008A128
0x18004c1c1  mov     rcx, rax
0x18004c1c4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18004c1c9  jmp     short loc_18004C1FC
0x18004c1cb  lea     rcx, aListTooLong; "list too long"
0x18004c1d2  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18004c1d9  mov     r9d, r14d
0x18004c1dc  lea     rdx, aMatchserviceco; "MatchServiceConfiguration failed for se"...
0x18004c1e3  jmp     short loc_18004C1F2
0x18004c1e5  mov     r9d, eax
0x18004c1e8  mov     r8, r15
0x18004c1eb  lea     rdx, aFailedToGather_1; "Failed to gather service info from file"...
0x18004c1f2  mov     ecx, 2; unsigned __int8
0x18004c1f7  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18004c1fc  test    rbx, rbx
0x18004c1ff  jz      short loc_18004C216
0x18004c201  mov     rcx, rbx; this
0x18004c204  call    ??1CServiceInformationFromXML@WaasMedic@@QEAA@XZ; WaasMedic::CServiceInformationFromXML::~CServiceInformationFromXML(void)
0x18004c209  mov     edx, 50h ; 'P'; struct std::nothrow_t *
0x18004c20e  mov     rcx, rbx; void *
0x18004c211  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004c216  test    rsi, rsi
0x18004c219  jz      short loc_18004C230
0x18004c21b  mov     rcx, rsi; this
0x18004c21e  call    ??1CServiceInformationFromDevice@WaasMedic@@QEAA@XZ; WaasMedic::CServiceInformationFromDevice::~CServiceInformationFromDevice(void)
0x18004c223  mov     edx, 68h ; 'h'; struct std::nothrow_t *
0x18004c228  mov     rcx, rsi; void *
0x18004c22b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004c230  mov     eax, r14d
0x18004c233  add     rsp, 58h
0x18004c237  pop     r15
0x18004c239  pop     r14
0x18004c23b  pop     r13
0x18004c23d  pop     r12
0x18004c23f  pop     rdi
0x18004c240  pop     rsi
0x18004c241  pop     rbx
0x18004c242  pop     rbp
0x18004c243  retn
```
