# MidiSrvUpdateConfiguration

- ea: `0x14003ed10`
- end: `0x14003f246`
- name: `MidiSrvUpdateConfiguration`
- size: `1334`
- prototype: `__int64 __fastcall(__int64, const wchar_t *, _QWORD *)`
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x1400018e4`
- `0x140001ce8`
- `0x1400072d4`
- `0x14000984c`
- `0x14000a6b4`
- `0x14000c598`
- `0x14000ca00`
- `0x14000cc2c`
- `0x1400144ac`
- `0x140022ef4`
- `0x14002455c`
- `0x1400261b4`
- `0x14003cb98`
- `0x14003cfe0`
- `0x14003ed10`
- `0x14005a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x14003f047`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x14003f047`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14003eea6`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14003ef9a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14003f182`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14003eea6`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14003ef9a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14003f182`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14003edcb`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14003edcb`

## string_xrefs

- `0x14003f231`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x14003f084`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt\Windows.Data.Json.h`
- `0x14003ed66`: `MidiSrvUpdateConfiguration`
- `0x14003ee63`: `Only one config entry allowed per call`
- `0x14003ed41`: `avcore\midi2\service\exe\midisrvrpc.cpp`
- `0x14003ef7d`: `avcore\midi2\service\exe\midisrvrpc.cpp`
- `0x14003f10d`: `avcore\midi2\service\exe\midisrvrpc.cpp`

## pseudocode

```c
__int64 __fastcall MidiSrvUpdateConfiguration(__int64 a1, const wchar_t *a2, _QWORD *a3)
{
  _DWORD *v6; // rcx
  int v7; // r8d
  int v8; // r9d
  HRESULT v9; // eax
  CMidiSrv *v10; // rdx
  __int64 *v11; // rdi
  __int64 v12; // rax
  __int64 v13; // rsi
  volatile signed __int32 *v14; // rdi
  __int64 v15; // r8
  _DWORD *v16; // rcx
  int v17; // r8d
  int v18; // r9d
  volatile signed __int32 *v19; // rbx
  _QWORD *v20; // r8
  __int64 (__fastcall *v21)(_QWORD, int *, _QWORD *, __int64 *); // rax
  int v22; // eax
  unsigned int v23; // esi
  volatile signed __int32 *v24; // rbx
  __int64 v25; // rcx
  __int64 v26; // rax
  int v27; // eax
  const wchar_t *v28; // rbx
  int v29; // eax
  _DWORD *v30; // rcx
  int v31; // r8d
  int v32; // r9d
  volatile signed __int32 *v33; // rbx
  int v34; // [rsp+20h] [rbp-69h]
  _QWORD v35[2]; // [rsp+40h] [rbp-49h] BYREF
  int v36[4]; // [rsp+50h] [rbp-39h] BYREF
  __int64 v37; // [rsp+60h] [rbp-29h]
  _QWORD v38[2]; // [rsp+70h] [rbp-19h] BYREF
  __int128 v39; // [rsp+80h] [rbp-9h] BYREF
  __int128 v40; // [rsp+90h] [rbp+7h] BYREF
  __int128 v41; // [rsp+A0h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]
  const wchar_t *v43; // [rsp+F8h] [rbp+6Fh] BYREF
  __int64 v44; // [rsp+100h] [rbp+77h] BYREF
  const wchar_t *v45; // [rsp+108h] [rbp+7Fh] BYREF

  *a3 = 0;
  if ( a2 )
  {
    v6 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v6 > 4u )
    {
      v43 = a2;
      v45 = L"Enter";
      v35[0] = 0;
      *(_QWORD *)v36 = "MidiSrvUpdateConfiguration";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v6,
        (unsigned int)byte_14008B40D,
        v7,
        v8,
        (__int64)v36,
        (__int64)v35,
        (__int64)&v45,
        (__int64)&v43);
    }
    v39 = 0;
    v9 = CoInitializeEx(0, 0);
    if ( v9 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x14D3,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        (const char *)(unsigned int)v9,
        v34);
    v10 = g_MidiService;
    v11 = (__int64 *)((char *)g_MidiService + 64);
    v12 = *((_QWORD *)g_MidiService + 9);
    if ( v12 )
    {
      _InterlockedIncrement((volatile signed __int32 *)(v12 + 8));
      v10 = g_MidiService;
    }
    v13 = *v11;
    v14 = (volatile signed __int32 *)v11[1];
    std::shared_ptr<CMidiSessionTracker>::operator=(&v39, (char *)v10 + 32);
    v40 = 0;
    v15 = -1;
    v41 = 0;
    do
      ++v15;
    while ( a2[v15] );
    std::wstring::_Construct<1,unsigned short const *>(&v40, a2, v15);
    CMidiConfigurationManager::GetTransportSettingsFromJsonString(v13, v38, &v40);
    if ( v38[1] == 1 )
    {
      v44 = 0;
      v20 = (_QWORD *)(*(_QWORD *)v38[0] + 48LL);
      if ( *(_QWORD *)(*(_QWORD *)v38[0] + 72LL) > 7u )
        v20 = (_QWORD *)*v20;
      v21 = *(__int64 (__fastcall **)(_QWORD, int *, _QWORD *, __int64 *))(*(_QWORD *)v39 + 88LL);
      *(_OWORD *)v36 = *(_OWORD *)(*(_QWORD *)v38[0] + 32LL);
      v22 = v21(v39, v36, v20, &v44);
      v23 = v22;
      if ( v22 >= 0 )
      {
        v25 = -1;
        do
          ++v25;
        while ( *(_WORD *)(v44 + 2 * v25) );
        if ( (_DWORD)v25 )
        {
          if ( *(_WORD *)(v44 + 2LL * (unsigned int)v25) )
            abort();
          DWORD2(v40) = 1;
          *(_QWORD *)&v40 = (char *)&v40 + 8;
          HIDWORD(v40) = v25;
          *((_QWORD *)&v41 + 1) = v44;
        }
        else
        {
          *(_QWORD *)&v40 = 0;
        }
        v45 = (const wchar_t *)&v40;
        _InterlockedIncrement64(&qword_140096A98);
        if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics> )
        {
          *(_QWORD *)&v36[2] = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Data.Json.h";
          v43 = 0;
          v26 = *(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>;
          v36[0] = 296;
          v37 = 0;
          v27 = (*(__int64 (__fastcall **)(__int64, _QWORD, const wchar_t **))(v26 + 48))(
                  winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>,
                  v40,
                  &v43);
          if ( v27 < 0 )
            winrt::throw_hresult((unsigned int)v27, v36);
          v28 = v43;
          _InterlockedAdd64(&qword_140096A98, 0xFFFFFFFFFFFFFFFFuLL);
        }
        else
        {
          _InterlockedAdd64(&qword_140096A98, 0xFFFFFFFFFFFFFFFFuLL);
          ___call_AEAV_lambda_1___1__Parse_JsonObject_Json_Data_Windows_winrt__SA_AEBUhstring_param_7__Z____factory_cache_entry_UJsonObject_Json_Data_Windows_winrt__UIJsonObjectStatics_2345__impl_winrt__QEAA_A_PAEAV_lambda_1___1__Parse_JsonObject_Json_Data_Windows_2_SA_AEBUhstring_param_2__Z__Z(
            0,
            &v43,
            &v45);
          v28 = v43;
        }
        v45 = v28;
        if ( v28 )
          (*(void (__fastcall **)(const wchar_t *))(*(_QWORD *)v28 + 8LL))(v28);
        v29 = StringifyJsonToOutputParameter(&v45, a3);
        if ( v29 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x12D,
            (unsigned int)"avcore\\midi2\\service\\exe\\midisrvrpc.cpp",
            (const char *)(unsigned int)v29,
            v34);
        v30 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
        if ( *v30 > 4u )
        {
          *(_QWORD *)v36 = 0;
          v45 = L"Exit success";
          v35[0] = "MidiSrvUpdateConfiguration";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
            (_DWORD)v30,
            (unsigned int)word_14008B312,
            v31,
            v32,
            (__int64)v35,
            (__int64)v36,
            (__int64)&v45);
        }
        if ( v28 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v43);
        std::_Tree<std::_Tmap_traits<_GUID,std::wstring,GUIDCompare,std::allocator<std::pair<_GUID const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<_GUID,std::wstring,GUIDCompare,std::allocator<std::pair<_GUID const,std::wstring>>,0>>(v38);
        CoUninitialize();
        v33 = (volatile signed __int32 *)*((_QWORD *)&v39 + 1);
        if ( *((_QWORD *)&v39 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v39 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v33)(v33);
            if ( _InterlockedExchangeAdd(v33 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v33 + 8LL))(v33);
          }
        }
        if ( v14 )
        {
          if ( _InterlockedExchangeAdd(v14 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
            if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
          }
        }
        return 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x127,
          (unsigned int)"avcore\\midi2\\service\\exe\\midisrvrpc.cpp",
          (const char *)(unsigned int)v22,
          v34);
        std::_Tree<std::_Tmap_traits<_GUID,std::wstring,GUIDCompare,std::allocator<std::pair<_GUID const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<_GUID,std::wstring,GUIDCompare,std::allocator<std::pair<_GUID const,std::wstring>>,0>>(v38);
        CoUninitialize();
        v24 = (volatile signed __int32 *)*((_QWORD *)&v39 + 1);
        if ( *((_QWORD *)&v39 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v39 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v24)(v24);
            if ( _InterlockedExchangeAdd(v24 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v24 + 8LL))(v24);
          }
        }
        if ( v14 )
        {
          if ( _InterlockedExchangeAdd(v14 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
            if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
          }
        }
        return v23;
      }
    }
    else
    {
      v16 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
      if ( *v16 > 2u )
      {
        v45 = 0;
        v43 = L"Only one config entry allowed per call";
        *(_QWORD *)v36 = "MidiSrvUpdateConfiguration";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
          (_DWORD)v16,
          (unsigned int)&word_14008B376,
          v17,
          v18,
          (__int64)v36,
          (__int64)&v45,
          (__int64)&v43);
      }
      std::_Tree<std::_Tmap_traits<_GUID,std::wstring,GUIDCompare,std::allocator<std::pair<_GUID const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<_GUID,std::wstring,GUIDCompare,std::allocator<std::pair<_GUID const,std::wstring>>,0>>(v38);
      CoUninitialize();
      v19 = (volatile signed __int32 *)*((_QWORD *)&v39 + 1);
      if ( *((_QWORD *)&v39 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v39 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v19)(v19);
          if ( _InterlockedExchangeAdd(v19 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 8LL))(v19);
        }
      }
      if ( v14 && _InterlockedExchangeAdd(v14 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
        if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
      }
      return 2147500037LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xFB,
      (unsigned int)"avcore\\midi2\\service\\exe\\midisrvrpc.cpp",
      (const char *)0x80070057LL,
      v34);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x14003ed10  mov     [rsp-8+arg_0], rbx
0x14003ed15  push    rbp
0x14003ed16  push    rsi
0x14003ed17  push    rdi
0x14003ed18  push    r12
0x14003ed1a  push    r13
0x14003ed1c  push    r14
0x14003ed1e  push    r15
0x14003ed20  lea     rbp, [rsp-27h]
0x14003ed25  sub     rsp, 0B0h
0x14003ed2c  xor     r12d, r12d
0x14003ed2f  mov     r14, r8
0x14003ed32  mov     [r8], r12
0x14003ed35  mov     rbx, rdx
0x14003ed38  test    rdx, rdx
0x14003ed3b  jnz     short loc_14003ED61
0x14003ed3d  mov     rcx, [rbp+5Fh]; this
0x14003ed41  lea     r8, aAvcoreMidi2Ser_10; "avcore\\midi2\\service\\exe\\midisrvrpc"...
0x14003ed48  mov     ebx, 80070057h
0x14003ed4d  mov     edx, 0FBh; void *
0x14003ed52  mov     r9d, ebx; char *
0x14003ed55  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003ed5a  mov     eax, ebx
0x14003ed5c  jmp     loc_14003F206
0x14003ed61  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14003ed66  lea     r13, aMidisrvupdatec; "MidiSrvUpdateConfiguration"
0x14003ed6d  mov     rcx, [rax+8]
0x14003ed71  mov     eax, [rcx]
0x14003ed73  cmp     eax, 4
0x14003ed76  jbe     short loc_14003EDBF
0x14003ed78  lea     rax, aEnter; "Enter"
0x14003ed7f  mov     [rbp+57h+arg_8], rbx
0x14003ed83  mov     [rbp+57h+arg_18], rax
0x14003ed87  lea     rdx, byte_14008B40D
0x14003ed8e  lea     rax, [rbp+57h+arg_8]
0x14003ed92  mov     [rbp+57h+var_A0], r12
0x14003ed96  mov     [rsp+0E0h+var_A8], rax
0x14003ed9b  lea     rax, [rbp+57h+arg_18]
0x14003ed9f  mov     [rsp+0E0h+var_B0], rax
0x14003eda4  lea     rax, [rbp+57h+var_A0]
0x14003eda8  mov     [rsp+0E0h+var_B8], rax
0x14003edad  lea     rax, [rbp+57h+var_90]
0x14003edb1  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x14003edb6  mov     qword ptr [rbp+57h+var_90], r13
0x14003edba  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x14003edbf  xorps   xmm0, xmm0
0x14003edc2  xor     edx, edx; dwCoInit
0x14003edc4  xor     ecx, ecx; pvReserved
0x14003edc6  movdqu  [rbp+57h+var_60], xmm0
0x14003edcb  call    cs:__imp_CoInitializeEx
0x14003edd1  test    eax, eax
0x14003edd3  js      loc_14003F22D
0x14003edd9  mov     rdx, cs:?g_MidiService@@3V?$unique_ptr@VCMidiSrv@@U?$default_delete@VCMidiSrv@@@std@@@std@@A; std::unique_ptr<CMidiSrv> g_MidiService
0x14003ede0  lea     rdi, [rdx+40h]
0x14003ede4  mov     rax, [rdi+8]
0x14003ede8  test    rax, rax
0x14003edeb  jz      short loc_14003EDF8
0x14003eded  lock inc dword ptr [rax+8]
0x14003edf1  mov     rdx, cs:?g_MidiService@@3V?$unique_ptr@VCMidiSrv@@U?$default_delete@VCMidiSrv@@@std@@@std@@A; std::unique_ptr<CMidiSrv> g_MidiService
0x14003edf8  mov     rsi, [rdi]
0x14003edfb  lea     rcx, [rbp+57h+var_60]
0x14003edff  mov     rdi, [rdi+8]
0x14003ee03  add     rdx, 20h ; ' '
0x14003ee07  call    ??4?$shared_ptr@VCMidiSessionTracker@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<CMidiSessionTracker>::operator=(std::shared_ptr<CMidiSessionTracker> const &)
0x14003ee0c  xorps   xmm0, xmm0
0x14003ee0f  xorps   xmm1, xmm1
0x14003ee12  or      r15, 0FFFFFFFFFFFFFFFFh
0x14003ee16  movups  [rbp+57h+var_50], xmm0
0x14003ee1a  mov     r8, r15
0x14003ee1d  movdqu  [rbp+57h+var_40], xmm1
0x14003ee22  inc     r8
0x14003ee25  cmp     [rbx+r8*2], r12w
0x14003ee2a  jnz     short loc_14003EE22
0x14003ee2c  mov     rdx, rbx
0x14003ee2f  lea     rcx, [rbp+57h+var_50]
0x14003ee33  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14003ee38  lea     r8, [rbp+57h+var_50]
0x14003ee3c  mov     rcx, rsi
0x14003ee3f  lea     rdx, [rbp+57h+var_70]
0x14003ee43  call    ?GetTransportSettingsFromJsonString@CMidiConfigurationManager@@QEBA?AV?$map@U_GUID@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UGUIDCompare@@V?$allocator@U?$pair@$$CBU_GUID@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@3@@std@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@@Z; CMidiConfigurationManager::GetTransportSettingsFromJsonString(std::wstring)
0x14003ee48  cmp     [rbp+57h+var_68], 1
0x14003ee4d  jz      loc_14003EF32
0x14003ee53  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14003ee58  mov     rcx, [rax+8]
0x14003ee5c  mov     eax, [rcx]
0x14003ee5e  cmp     eax, 2
0x14003ee61  jbe     short loc_14003EE9D
0x14003ee63  lea     rax, aOnlyOneConfigE; "Only one config entry allowed per call"
0x14003ee6a  mov     [rbp+57h+arg_18], r12
0x14003ee6e  mov     [rbp+57h+arg_8], rax
0x14003ee72  lea     rdx, word_14008B376
0x14003ee79  lea     rax, [rbp+57h+arg_8]
0x14003ee7d  mov     qword ptr [rbp+57h+var_90], r13
0x14003ee81  mov     [rsp+0E0h+var_B0], rax
0x14003ee86  lea     rax, [rbp+57h+arg_18]
0x14003ee8a  mov     [rsp+0E0h+var_B8], rax
0x14003ee8f  lea     rax, [rbp+57h+var_90]
0x14003ee93  mov     qword ptr [rsp+0E0h+var_C0], rax
0x14003ee98  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x14003ee9d  lea     rcx, [rbp+57h+var_70]
0x14003eea1  call    ??1?$_Tree@V?$_Tmap_traits@U_GUID@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UGUIDCompare@@V?$allocator@U?$pair@$$CBU_GUID@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<_GUID,std::wstring,GUIDCompare,std::allocator<std::pair<_GUID const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<_GUID,std::wstring,GUIDCompare,std::allocator<std::pair<_GUID const,std::wstring>>,0>>(void)
0x14003eea6  call    cs:__imp_CoUninitialize
0x14003eeac  mov     rbx, qword ptr [rbp+57h+var_60+8]
0x14003eeb0  test    rbx, rbx
0x14003eeb3  jz      short loc_14003EEEC
0x14003eeb5  mov     eax, r15d
0x14003eeb8  lock xadd [rbx+8], eax
0x14003eebd  add     eax, r15d
0x14003eec0  jnz     short loc_14003EEEC
0x14003eec2  mov     rax, [rbx]
0x14003eec5  mov     rcx, rbx
0x14003eec8  mov     rax, [rax]
0x14003eecb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003eed0  mov     eax, r15d
0x14003eed3  lock xadd [rbx+0Ch], eax
0x14003eed8  add     eax, r15d
0x14003eedb  jnz     short loc_14003EEEC
0x14003eedd  mov     rax, [rbx]
0x14003eee0  mov     rcx, rbx
0x14003eee3  mov     rax, [rax+8]
0x14003eee7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003eeec  test    rdi, rdi
0x14003eeef  jz      short loc_14003EF28
0x14003eef1  mov     eax, r15d
0x14003eef4  lock xadd [rdi+8], eax
0x14003eef9  add     eax, r15d
0x14003eefc  jnz     short loc_14003EF28
0x14003eefe  mov     rax, [rdi]
0x14003ef01  mov     rcx, rdi
0x14003ef04  mov     rax, [rax]
0x14003ef07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003ef0c  mov     eax, r15d
0x14003ef0f  lock xadd [rdi+0Ch], eax
0x14003ef14  add     eax, r15d
0x14003ef17  jnz     short loc_14003EF28
0x14003ef19  mov     rax, [rdi]
0x14003ef1c  mov     rcx, rdi
0x14003ef1f  mov     rax, [rax+8]
0x14003ef23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003ef28  mov     eax, 80004005h
0x14003ef2d  jmp     loc_14003F206
0x14003ef32  mov     rcx, qword ptr [rbp+57h+var_60]
0x14003ef36  mov     [rbp+57h+arg_10], r12
0x14003ef3a  mov     rax, [rcx]
0x14003ef3d  mov     r10, [rax+58h]
0x14003ef41  mov     rax, [rbp+57h+var_70]
0x14003ef45  mov     rdx, [rax]
0x14003ef48  lea     r8, [rdx+30h]
0x14003ef4c  cmp     qword ptr [r8+18h], 7
0x14003ef51  jbe     short loc_14003EF56
0x14003ef53  mov     r8, [r8]
0x14003ef56  movups  xmm0, xmmword ptr [rdx+20h]
0x14003ef5a  lea     r9, [rbp+57h+arg_10]
0x14003ef5e  mov     rax, r10
0x14003ef61  lea     rdx, [rbp+57h+var_90]
0x14003ef65  movdqu  xmmword ptr [rbp+57h+var_90], xmm0
0x14003ef6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003ef6f  mov     esi, eax
0x14003ef71  test    eax, eax
0x14003ef73  jns     loc_14003F023
0x14003ef79  mov     rcx, [rbp+5Fh]; this
0x14003ef7d  lea     r8, aAvcoreMidi2Ser_10; "avcore\\midi2\\service\\exe\\midisrvrpc"...
0x14003ef84  mov     r9d, eax; char *
0x14003ef87  mov     edx, 127h; void *
0x14003ef8c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003ef91  lea     rcx, [rbp+57h+var_70]
0x14003ef95  call    ??1?$_Tree@V?$_Tmap_traits@U_GUID@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UGUIDCompare@@V?$allocator@U?$pair@$$CBU_GUID@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<_GUID,std::wstring,GUIDCompare,std::allocator<std::pair<_GUID const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<_GUID,std::wstring,GUIDCompare,std::allocator<std::pair<_GUID const,std::wstring>>,0>>(void)
0x14003ef9a  call    cs:__imp_CoUninitialize
0x14003efa0  mov     rbx, qword ptr [rbp+57h+var_60+8]
0x14003efa4  test    rbx, rbx
0x14003efa7  jz      short loc_14003EFE0
0x14003efa9  mov     eax, r15d
0x14003efac  lock xadd [rbx+8], eax
0x14003efb1  add     eax, r15d
0x14003efb4  jnz     short loc_14003EFE0
0x14003efb6  mov     rax, [rbx]
0x14003efb9  mov     rcx, rbx
0x14003efbc  mov     rax, [rax]
0x14003efbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003efc4  mov     eax, r15d
0x14003efc7  lock xadd [rbx+0Ch], eax
0x14003efcc  add     eax, r15d
0x14003efcf  jnz     short loc_14003EFE0
0x14003efd1  mov     rax, [rbx]
0x14003efd4  mov     rcx, rbx
0x14003efd7  mov     rax, [rax+8]
0x14003efdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003efe0  test    rdi, rdi
0x14003efe3  jz      short loc_14003F01C
0x14003efe5  mov     eax, r15d
0x14003efe8  lock xadd [rdi+8], eax
0x14003efed  add     eax, r15d
0x14003eff0  jnz     short loc_14003F01C
0x14003eff2  mov     rax, [rdi]
0x14003eff5  mov     rcx, rdi
0x14003eff8  mov     rax, [rax]
0x14003effb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003f000  mov     eax, r15d
0x14003f003  lock xadd [rdi+0Ch], eax
0x14003f008  add     eax, r15d
0x14003f00b  jnz     short loc_14003F01C
0x14003f00d  mov     rax, [rdi]
0x14003f010  mov     rcx, rdi
0x14003f013  mov     rax, [rax+8]
0x14003f017  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003f01c  mov     eax, esi
0x14003f01e  jmp     loc_14003F206
0x14003f023  mov     rdx, [rbp+57h+arg_10]
0x14003f027  mov     rcx, r15
0x14003f02a  inc     rcx
0x14003f02d  cmp     [rdx+rcx*2], r12w
0x14003f032  jnz     short loc_14003F02A
0x14003f034  test    ecx, ecx
0x14003f036  jnz     short loc_14003F03E
0x14003f038  mov     qword ptr [rbp+57h+var_50], r12
0x14003f03c  jmp     short loc_14003F064
0x14003f03e  mov     eax, ecx
0x14003f040  cmp     [rdx+rax*2], r12w
0x14003f045  jz      short loc_14003F04E
0x14003f047  call    cs:__imp_abort
0x14003f04e  lea     rax, [rbp+57h+var_50+8]
0x14003f052  mov     dword ptr [rbp+57h+var_50+8], 1
0x14003f059  mov     qword ptr [rbp+57h+var_50], rax
0x14003f05d  mov     dword ptr [rbp+57h+var_50+0Ch], ecx
0x14003f060  mov     qword ptr [rbp+57h+var_40+8], rdx
0x14003f064  lea     rax, [rbp+57h+var_50]
0x14003f068  mov     [rbp+57h+arg_18], rax
0x14003f06c  lock inc cs:qword_140096A98
0x14003f074  mov     rcx, cs:??$factory_cache_entry_v@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@12@A; factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>
0x14003f07b  test    rcx, rcx
0x14003f07e  jz      short loc_14003F0C8
0x14003f080  mov     rdx, qword ptr [rbp+57h+var_50]
0x14003f084  lea     rax, aOnecoreuapInte_2; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x14003f08b  mov     qword ptr [rbp+57h+var_90+8], rax
0x14003f08f  lea     r8, [rbp+57h+arg_8]
0x14003f093  mov     [rbp+57h+arg_8], r12
0x14003f097  mov     rax, [rcx]
0x14003f09a  mov     [rbp+57h+var_90], 128h
0x14003f0a1  mov     [rbp+57h+var_80], r12
0x14003f0a5  mov     rax, [rax+30h]
0x14003f0a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003f0ae  test    eax, eax
0x14003f0b0  js      loc_14003F221
0x14003f0b6  mov     rbx, [rbp+57h+arg_8]
0x14003f0ba  mov     [rbp+57h+arg_8], rbx
0x14003f0be  lock add cs:qword_140096A98, r15
0x14003f0c6  jmp     short loc_14003F0E1
0x14003f0c8  lock add cs:qword_140096A98, r15
0x14003f0d0  lea     r8, [rbp+57h+arg_18]
0x14003f0d4  lea     rdx, [rbp+57h+arg_8]
0x14003f0d8  call    ??$call@AEAV_lambda_1_@?1??Parse@JsonObject@Json@Data@Windows@winrt@@SA@AEBUhstring@param@7@@Z@@?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??Parse@JsonObject@Json@Data@Windows@2@SA@AEBUhstring@param@2@@Z@@Z
0x14003f0dd  mov     rbx, [rbp+57h+arg_8]
0x14003f0e1  mov     [rbp+57h+arg_18], rbx
0x14003f0e5  test    rbx, rbx
0x14003f0e8  jz      short loc_14003F0F9
0x14003f0ea  mov     rax, [rbx]
0x14003f0ed  mov     rcx, rbx
0x14003f0f0  mov     rax, [rax+8]
0x14003f0f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003f0f9  mov     rdx, r14
0x14003f0fc  lea     rcx, [rbp+57h+arg_18]
0x14003f100  call    ?StringifyJsonToOutputParameter@@YAJUJsonObject@Json@Data@Windows@winrt@@PEAPEAG@Z; StringifyJsonToOutputParameter(winrt::Windows::Data::Json::JsonObject,ushort * *)
0x14003f105  test    eax, eax
0x14003f107  jns     short loc_14003F121
0x14003f109  mov     rcx, [rbp+5Fh]; this
0x14003f10d  lea     r8, aAvcoreMidi2Ser_10; "avcore\\midi2\\service\\exe\\midisrvrpc"...
0x14003f114  mov     r9d, eax; char *
0x14003f117  mov     edx, 12Dh; void *
0x14003f11c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14003f121  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14003f126  mov     rcx, [rax+8]
0x14003f12a  mov     eax, [rcx]
0x14003f12c  cmp     eax, 4
0x14003f12f  jbe     short loc_14003F16B
0x14003f131  lea     rax, aExitSuccess_0; "Exit success"
0x14003f138  mov     qword ptr [rbp+57h+var_90], r12
0x14003f13c  mov     [rbp+57h+arg_18], rax
0x14003f140  lea     rdx, word_14008B312
0x14003f147  lea     rax, [rbp+57h+arg_18]
0x14003f14b  mov     [rbp+57h+var_A0], r13
0x14003f14f  mov     [rsp+0E0h+var_B0], rax
0x14003f154  lea     rax, [rbp+57h+var_90]
0x14003f158  mov     [rsp+0E0h+var_B8], rax
0x14003f15d  lea     rax, [rbp+57h+var_A0]
0x14003f161  mov     qword ptr [rsp+0E0h+var_C0], rax
0x14003f166  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x14003f16b  test    rbx, rbx
0x14003f16e  jz      short loc_14003F179
0x14003f170  lea     rcx, [rbp+57h+arg_8]
0x14003f174  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x14003f179  lea     rcx, [rbp+57h+var_70]
0x14003f17d  call    ??1?$_Tree@V?$_Tmap_traits@U_GUID@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UGUIDCompare@@V?$allocator@U?$pair@$$CBU_GUID@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<_GUID,std::wstring,GUIDCompare,std::allocator<std::pair<_GUID const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<_GUID,std::wstring,GUIDCompare,std::allocator<std::pair<_GUID const,std::wstring>>,0>>(void)
0x14003f182  call    cs:__imp_CoUninitialize
0x14003f188  mov     rbx, qword ptr [rbp+57h+var_60+8]
0x14003f18c  test    rbx, rbx
0x14003f18f  jz      short loc_14003F1C8
0x14003f191  mov     eax, r15d
0x14003f194  lock xadd [rbx+8], eax
0x14003f199  add     eax, r15d
0x14003f19c  jnz     short loc_14003F1C8
  ... truncated ...
```
