# CMidi2KSAggregateMidiConfigurationManager::ProcessCustomProperties(winrt::hstring,std::shared_ptr<WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria>,winrt::Windows::Data::Json::JsonObject,std::shared_ptr<WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomProperties> &,std::vector<_DEVPROPERTY,std::allocator<_DEVPROPERTY>> &,std::shared_ptr<WindowsMidiServicesNamingLib::MidiEndpointNameTable> &,winrt::Windows::Data::Json::JsonObject &)

- ea: `0x18001dd50`
- end: `0x18001e1de`
- name: `?ProcessCustomProperties@CMidi2KSAggregateMidiConfigurationManager@@AEAAJUhstring@winrt@@V?$shared_ptr@VMidiEndpointMatchCriteria@WindowsMidiServicesPluginConfigurationLib@@@std@@UJsonObject@Json@Data@Windows@3@AEAV?$shared_ptr@VMidiEndpointCustomProperties@WindowsMidiServicesPluginConfigurationLib@@@5@AEAV?$vector@U_DEVPROPERTY@@V?$allocator@U_DEVPROPERTY@@@std@@@5@AEAV?$shared_ptr@VMidiEndpointNameTable@WindowsMidiServicesNamingLib@@@5@AEAU67893@@Z`
- size: `1166`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18001e790`

## callees

- `0x1800016dc`
- `0x180005f2c`
- `0x180005fa4`
- `0x180010b94`
- `0x1800117d8`
- `0x180019924`
- `0x18001cf74`
- `0x18001d270`
- `0x18001dd50`
- `0x18004b224`
- `0x18004c338`
- `0x18004cc34`
- `0x1800553b4`
- `0x180056eb8`
- `0x180056fc4`
- `0x1800570d0`
- `0x18005e010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001e1d7`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001e1d7`

## string_xrefs

- `0x18001df21`: `avcore\midi2\transport\ksaggregatetransport\midi2.ksaggregatemidiconfigurationmanager.cpp`
- `0x18001e0ed`: `Unable to write custom user properties.`
- `0x18001de8d`: `CMidi2KSAggregateMidiConfigurationManager::ProcessCustomProperties`
- `0x18001e0fc`: `CMidi2KSAggregateMidiConfigurationManager::ProcessCustomProperties`
- `0x18001de7e`: `Failed reading custom user properties`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 CMidi2KSAggregateMidiConfigurationManager::ProcessCustomProperties(__int64 a1, ...)
{
  _QWORD *v1; // r15
  __int64 v2; // r12
  volatile signed __int32 **v3; // r14
  __int64 *v5; // rax
  __int64 v6; // rcx
  __int64 v7; // rdx
  _QWORD *v8; // rdi
  volatile signed __int32 *v9; // rbx
  volatile signed __int32 *v10; // rbx
  _DWORD *v11; // rcx
  int v12; // r8d
  int v13; // r9d
  __int64 v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 *v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // rsi
  volatile signed __int32 *v21; // rbx
  volatile signed __int32 *v22; // rbx
  __int64 *v23; // rbx
  __int64 **v24; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  __int64 *v27; // rbx
  WindowsMidiServicesNamingLib::MidiEndpointNameTable *v28; // rcx
  __int64 **v29; // rcx
  __int64 *k; // rax
  __int64 *m; // rcx
  _DWORD *v32; // rcx
  int v33; // r8d
  int v34; // r9d
  volatile signed __int32 *v35; // rbx
  int v36; // eax
  HANDLE ProcessHeap; // rax
  volatile signed __int32 *v38; // rbx
  int v40; // [rsp+20h] [rbp-50h]
  __int128 v41; // [rsp+40h] [rbp-30h] BYREF
  _OWORD v42[2]; // [rsp+50h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]
  const wchar_t *v44; // [rsp+B8h] [rbp+48h] BYREF
  va_list va; // [rsp+B8h] [rbp+48h]
  __int64 v46; // [rsp+C0h] [rbp+50h]
  _QWORD *v47; // [rsp+C8h] [rbp+58h]
  _QWORD *v48; // [rsp+D0h] [rbp+60h]
  __int64 v49; // [rsp+D8h] [rbp+68h]
  _QWORD *v50; // [rsp+E0h] [rbp+70h]
  __int64 v51; // [rsp+E8h] [rbp+78h] BYREF
  va_list va1; // [rsp+E8h] [rbp+78h]
  va_list va2; // [rsp+F0h] [rbp+80h] BYREF

  va_start(va2, a1);
  va_start(va1, a1);
  va_start(va, a1);
  v44 = va_arg(va1, const wchar_t *);
  v46 = va_arg(va1, _QWORD);
  v47 = va_arg(va1, _QWORD *);
  v48 = va_arg(va1, _QWORD *);
  v49 = va_arg(va1, _QWORD);
  v50 = va_arg(va1, _QWORD *);
  va_copy(va2, va1);
  v51 = va_arg(va2, _QWORD);
  v1 = v47;
  v2 = v46;
  v3 = (volatile signed __int32 **)v44;
  *(_QWORD *)&v42[0] = WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomProperties::PropertyKey;
  if ( (unsigned __int8)winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(
                          v47,
                          v42) )
  {
    *(_QWORD *)&v42[0] = WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomProperties::PropertyKey;
    winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedObject(
      v1,
      (__int64 *)va1,
      v42);
    v5 = (__int64 *)WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomProperties::FromJson(
                      v42,
                      (__int64 *)va1);
    v6 = *v5;
    v7 = v5[1];
    *v5 = 0;
    v5[1] = 0;
    v8 = v48;
    *v48 = v6;
    v9 = (volatile signed __int32 *)v8[1];
    v8[1] = v7;
    if ( v9 )
    {
      if ( _InterlockedExchangeAdd(v9 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v9)(v9);
        if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
      }
    }
    v10 = (volatile signed __int32 *)*((_QWORD *)&v42[0] + 1);
    if ( *((_QWORD *)&v42[0] + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v42[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
        if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
      }
    }
    if ( *v8 )
    {
      v14 = *(_QWORD *)(a1 + 16);
      v41 = 0;
      v15 = v8[1];
      if ( v15 )
        _InterlockedIncrement((volatile signed __int32 *)(v15 + 8));
      v41 = *(_OWORD *)v8;
      v42[0] = 0;
      v16 = *(_QWORD *)(v2 + 8);
      if ( v16 )
        _InterlockedIncrement((volatile signed __int32 *)(v16 + 8));
      v42[0] = *(_OWORD *)v2;
      if ( !(unsigned __int8)WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomPropertiesCache::Add(
                               v14,
                               v42,
                               &v41) )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x6D,
          (unsigned int)"avcore\\midi2\\transport\\ksaggregatetransport\\midi2.ksaggregatemidiconfigurationmanager.cpp",
          (const char *)0x80004005LL,
          v40);
      if ( *v3 )
      {
        if ( (unsigned __int8)WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomProperties::WriteAllProperties(
                                *v8,
                                v49) )
        {
          if ( *(_QWORD *)(*v8 + 56LL) || *(_QWORD *)(*v8 + 40LL) )
          {
            v17 = (__int64 *)WindowsMidiServicesNamingLib::MidiEndpointNameTable::FromEndpointDeviceId(v42, v3);
            v18 = *v17;
            v19 = v17[1];
            *v17 = 0;
            v17[1] = 0;
            v20 = (__int64)v50;
            *v50 = v18;
            v21 = *(volatile signed __int32 **)(v20 + 8);
            *(_QWORD *)(v20 + 8) = v19;
            if ( v21 )
            {
              if ( _InterlockedExchangeAdd(v21 + 2, 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v21)(v21);
                if ( _InterlockedExchangeAdd(v21 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v21 + 8LL))(v21);
              }
            }
            v22 = (volatile signed __int32 *)*((_QWORD *)&v42[0] + 1);
            if ( *((_QWORD *)&v42[0] + 1) )
            {
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v42[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v22)(v22);
                if ( _InterlockedExchangeAdd(v22 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v22 + 8LL))(v22);
              }
            }
            v23 = **(__int64 ***)(*v8 + 32LL);
            while ( !*((_BYTE *)v23 + 25) )
            {
              WindowsMidiServicesNamingLib::MidiEndpointNameTable::UpdateSourceEntryCustomName(
                *(WindowsMidiServicesNamingLib::MidiEndpointNameTable **)v20,
                *((_BYTE *)v23 + 40),
                (const struct winrt::hstring *)(v23 + 6));
              v24 = (__int64 **)v23[2];
              if ( *((_BYTE *)v24 + 25) )
              {
                for ( i = (__int64 *)v23[1]; !*((_BYTE *)i + 25) && v23 == (__int64 *)i[2]; i = (__int64 *)i[1] )
                  v23 = i;
                v23 = i;
              }
              else
              {
                v23 = (__int64 *)v23[2];
                for ( j = *v24; !*((_BYTE *)j + 25); j = (__int64 *)*j )
                  v23 = j;
              }
            }
            v27 = **(__int64 ***)(*v8 + 48LL);
            while ( 1 )
            {
              v28 = *(WindowsMidiServicesNamingLib::MidiEndpointNameTable **)v20;
              if ( *((_BYTE *)v27 + 25) )
                break;
              WindowsMidiServicesNamingLib::MidiEndpointNameTable::UpdateDestinationEntryCustomName(
                v28,
                *((_BYTE *)v27 + 40),
                (const struct winrt::hstring *)(v27 + 6));
              v29 = (__int64 **)v27[2];
              if ( *((_BYTE *)v29 + 25) )
              {
                for ( k = (__int64 *)v27[1]; !*((_BYTE *)k + 25) && v27 == (__int64 *)k[2]; k = (__int64 *)k[1] )
                  v27 = k;
                v27 = k;
              }
              else
              {
                v27 = (__int64 *)v27[2];
                for ( m = *v29; !*((_BYTE *)m + 25); m = (__int64 *)*m )
                  v27 = m;
              }
            }
            WindowsMidiServicesNamingLib::MidiEndpointNameTable::WriteProperties(v28, v49);
          }
        }
        else
        {
          v32 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
          if ( *v32 > 4u )
          {
            v44 = L"Unable to write custom user properties.";
            *(_QWORD *)&v42[0] = a1;
            *(_QWORD *)&v41 = "CMidi2KSAggregateMidiConfigurationManager::ProcessCustomProperties";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
              (_DWORD)v32,
              (unsigned int)byte_1800890A5,
              v33,
              v34,
              (__int64)&v41,
              (__int64)v42,
              (__int64)va);
          }
        }
      }
    }
    else
    {
      v11 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
      if ( *v11 > 4u )
      {
        v44 = L"Failed reading custom user properties";
        *(_QWORD *)&v41 = a1;
        *(_QWORD *)&v42[0] = "CMidi2KSAggregateMidiConfigurationManager::ProcessCustomProperties";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
          (_DWORD)v11,
          (unsigned int)byte_180089073,
          v12,
          v13,
          (__int64)v42,
          (__int64)&v41,
          (__int64)va);
      }
    }
    if ( v51 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((__int64 *)va1);
  }
  v35 = *v3;
  if ( *v3 )
  {
    v36 = _InterlockedDecrement(v35 + 6);
    if ( v36 )
    {
      if ( v36 < 0 )
        abort();
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v35);
    }
    *v3 = 0;
  }
  v38 = *(volatile signed __int32 **)(v2 + 8);
  if ( v38 )
  {
    if ( _InterlockedExchangeAdd(v38 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v38)(v38);
      if ( _InterlockedExchangeAdd(v38 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v38 + 8LL))(v38);
    }
  }
  if ( *v1 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v1);
  return 0;
}

```

## disassembly

```asm
0x18001dd50  mov     rax, rsp
0x18001dd53  mov     [rax+8], rbx
0x18001dd57  mov     [rax+20h], r9
0x18001dd5b  mov     [rax+18h], r8
0x18001dd5f  mov     [rax+10h], rdx
0x18001dd63  push    rbp
0x18001dd64  push    rsi
0x18001dd65  push    rdi
0x18001dd66  push    r12
0x18001dd68  push    r13
0x18001dd6a  push    r14
0x18001dd6c  push    r15
0x18001dd6e  mov     rbp, rsp
0x18001dd71  sub     rsp, 70h
0x18001dd75  mov     r15, r9
0x18001dd78  mov     r12, r8
0x18001dd7b  mov     r14, rdx
0x18001dd7e  mov     rsi, rcx
0x18001dd81  mov     rax, cs:?PropertyKey@MidiEndpointCustomProperties@WindowsMidiServicesPluginConfigurationLib@@2Uhstring@winrt@@A; winrt::hstring WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomProperties::PropertyKey
0x18001dd88  mov     qword ptr [rbp+var_20], rax
0x18001dd8c  lea     rdx, [rbp+var_20]
0x18001dd90  mov     rcx, r9
0x18001dd93  call    ?HasKey@?$consume_Windows_Foundation_Collections_IMap@UJsonObject@Json@Data@Windows@winrt@@Uhstring@5@UIJsonValue@2345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(winrt::param::hstring const &)
0x18001dd98  xor     r13d, r13d
0x18001dd9b  test    al, al
0x18001dd9d  jz      loc_18001E13F
0x18001dda3  mov     rax, cs:?PropertyKey@MidiEndpointCustomProperties@WindowsMidiServicesPluginConfigurationLib@@2Uhstring@winrt@@A; winrt::hstring WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomProperties::PropertyKey
0x18001ddaa  mov     qword ptr [rbp+var_20], rax
0x18001ddae  lea     r8, [rbp+var_20]
0x18001ddb2  lea     rdx, [rbp+arg_38]
0x18001ddb6  mov     rcx, r15
0x18001ddb9  call    ?GetNamedObject@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedObject(winrt::param::hstring const &)
0x18001ddbe  nop
0x18001ddbf  lea     rdx, [rbp+arg_38]
0x18001ddc3  lea     rcx, [rbp+var_20]
0x18001ddc7  call    ?FromJson@MidiEndpointCustomProperties@WindowsMidiServicesPluginConfigurationLib@@SA?AV?$shared_ptr@VMidiEndpointCustomProperties@WindowsMidiServicesPluginConfigurationLib@@@std@@AEBUJsonObject@Json@Data@Windows@winrt@@@Z; WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomProperties::FromJson(winrt::Windows::Data::Json::JsonObject const &)
0x18001ddcc  mov     rcx, [rax]
0x18001ddcf  mov     rdx, [rax+8]
0x18001ddd3  mov     [rax], r13
0x18001ddd6  mov     [rax+8], r13
0x18001ddda  mov     rdi, [rbp+arg_20]
0x18001ddde  mov     [rdi], rcx
0x18001dde1  mov     rbx, [rdi+8]
0x18001dde5  mov     [rdi+8], rdx
0x18001dde9  test    rbx, rbx
0x18001ddec  jz      short loc_18001DE25
0x18001ddee  or      eax, 0FFFFFFFFh
0x18001ddf1  lock xadd [rbx+8], eax
0x18001ddf6  cmp     eax, 1
0x18001ddf9  jnz     short loc_18001DE25
0x18001ddfb  mov     rax, [rbx]
0x18001ddfe  mov     rcx, rbx
0x18001de01  mov     rax, [rax]
0x18001de04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001de09  or      eax, 0FFFFFFFFh
0x18001de0c  lock xadd [rbx+0Ch], eax
0x18001de11  cmp     eax, 1
0x18001de14  jnz     short loc_18001DE25
0x18001de16  mov     rax, [rbx]
0x18001de19  mov     rcx, rbx
0x18001de1c  mov     rax, [rax+8]
0x18001de20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001de25  mov     rbx, qword ptr [rbp+var_20+8]
0x18001de29  test    rbx, rbx
0x18001de2c  jz      short loc_18001DE65
0x18001de2e  or      eax, 0FFFFFFFFh
0x18001de31  lock xadd [rbx+8], eax
0x18001de36  cmp     eax, 1
0x18001de39  jnz     short loc_18001DE65
0x18001de3b  mov     rax, [rbx]
0x18001de3e  mov     rcx, rbx
0x18001de41  mov     rax, [rax]
0x18001de44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001de49  or      eax, 0FFFFFFFFh
0x18001de4c  lock xadd [rbx+0Ch], eax
0x18001de51  cmp     eax, 1
0x18001de54  jnz     short loc_18001DE65
0x18001de56  mov     rax, [rbx]
0x18001de59  mov     rcx, rbx
0x18001de5c  mov     rax, [rax+8]
0x18001de60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001de65  cmp     [rdi], r13
0x18001de68  jnz     short loc_18001DEBA
0x18001de6a  call    ?Instance@MidiKSAggregateTransportTelemetryProvider@@KAPEAV1@XZ; MidiKSAggregateTransportTelemetryProvider::Instance(void)
0x18001de6f  mov     rcx, [rax+8]
0x18001de73  mov     eax, [rcx]
0x18001de75  cmp     eax, 4
0x18001de78  jbe     loc_18001E12F
0x18001de7e  lea     rax, aFailedReadingC; "Failed reading custom user properties"
0x18001de85  mov     [rbp+arg_8], rax
0x18001de89  mov     qword ptr [rbp+var_30], rsi
0x18001de8d  lea     rax, aCmidi2ksaggreg_32; "CMidi2KSAggregateMidiConfigurationManag"...
0x18001de94  mov     qword ptr [rbp+var_20], rax
0x18001de98  lea     rax, [rbp+arg_8]
0x18001de9c  mov     [rsp+70h+var_40], rax
0x18001dea1  lea     rax, [rbp+var_30]
0x18001dea5  mov     [rsp+70h+var_48], rax
0x18001deaa  lea     rax, [rbp+var_20]
0x18001deae  lea     rdx, byte_180089073
0x18001deb5  jmp     loc_18001E124
0x18001deba  mov     rcx, [rsi+10h]
0x18001debe  xorps   xmm0, xmm0
0x18001dec1  movdqu  [rbp+var_30], xmm0
0x18001dec6  mov     rax, [rdi+8]
0x18001deca  test    rax, rax
0x18001decd  jz      short loc_18001DED3
0x18001decf  lock inc dword ptr [rax+8]
0x18001ded3  mov     rax, [rdi]
0x18001ded6  mov     qword ptr [rbp+var_30], rax
0x18001deda  mov     rax, [rdi+8]
0x18001dede  mov     qword ptr [rbp+var_30+8], rax
0x18001dee2  movdqu  [rbp+var_20], xmm0
0x18001dee7  mov     rax, [r12+8]
0x18001deec  test    rax, rax
0x18001deef  jz      short loc_18001DEF5
0x18001def1  lock inc dword ptr [rax+8]
0x18001def5  mov     rax, [r12]
0x18001def9  mov     qword ptr [rbp+var_20], rax
0x18001defd  mov     rax, [r12+8]
0x18001df02  mov     qword ptr [rbp+var_20+8], rax
0x18001df06  mov     rbx, [rbp+38h]
0x18001df0a  lea     r8, [rbp+var_30]
0x18001df0e  lea     rdx, [rbp+var_20]
0x18001df12  call    ?Add@MidiEndpointCustomPropertiesCache@WindowsMidiServicesPluginConfigurationLib@@QEAA_NV?$shared_ptr@VMidiEndpointMatchCriteria@WindowsMidiServicesPluginConfigurationLib@@@std@@V?$shared_ptr@VMidiEndpointCustomProperties@WindowsMidiServicesPluginConfigurationLib@@@4@@Z; WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomPropertiesCache::Add(std::shared_ptr<WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria>,std::shared_ptr<WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomProperties>)
0x18001df17  test    al, al
0x18001df19  jnz     short loc_18001DF35
0x18001df1b  mov     r9d, 80004005h; char *
0x18001df21  lea     r8, aAvcoreMidi2Tra_2; "avcore\\midi2\\transport\\ksaggregatetr"...
0x18001df28  mov     edx, 6Dh ; 'm'; void *
0x18001df2d  mov     rcx, rbx; this
0x18001df30  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001df35  cmp     [r14], r13
0x18001df38  jz      loc_18001E12F
0x18001df3e  mov     rdx, [rbp+arg_28]
0x18001df42  mov     rcx, [rdi]
0x18001df45  call    ?WriteAllProperties@MidiEndpointCustomProperties@WindowsMidiServicesPluginConfigurationLib@@QEAA_NAEAV?$vector@U_DEVPROPERTY@@V?$allocator@U_DEVPROPERTY@@@std@@@std@@@Z; WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomProperties::WriteAllProperties(std::vector<_DEVPROPERTY> &)
0x18001df4a  test    al, al
0x18001df4c  jz      loc_18001E0DD
0x18001df52  mov     rax, [rdi]
0x18001df55  cmp     [rax+38h], r13
0x18001df59  ja      short loc_18001DF65
0x18001df5b  cmp     [rax+28h], r13
0x18001df5f  jbe     loc_18001E12F
0x18001df65  mov     rdx, r14
0x18001df68  lea     rcx, [rbp+var_20]
0x18001df6c  call    ?FromEndpointDeviceId@MidiEndpointNameTable@WindowsMidiServicesNamingLib@@SA?AV?$shared_ptr@VMidiEndpointNameTable@WindowsMidiServicesNamingLib@@@std@@AEBUhstring@winrt@@@Z; WindowsMidiServicesNamingLib::MidiEndpointNameTable::FromEndpointDeviceId(winrt::hstring const &)
0x18001df71  mov     rcx, [rax]
0x18001df74  mov     rdx, [rax+8]
0x18001df78  mov     [rax], r13
0x18001df7b  mov     [rax+8], r13
0x18001df7f  mov     rsi, [rbp+arg_30]
0x18001df83  mov     [rsi], rcx
0x18001df86  mov     rbx, [rsi+8]
0x18001df8a  mov     [rsi+8], rdx
0x18001df8e  test    rbx, rbx
0x18001df91  jz      short loc_18001DFCA
0x18001df93  or      eax, 0FFFFFFFFh
0x18001df96  lock xadd [rbx+8], eax
0x18001df9b  cmp     eax, 1
0x18001df9e  jnz     short loc_18001DFCA
0x18001dfa0  mov     rax, [rbx]
0x18001dfa3  mov     rcx, rbx
0x18001dfa6  mov     rax, [rax]
0x18001dfa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dfae  or      eax, 0FFFFFFFFh
0x18001dfb1  lock xadd [rbx+0Ch], eax
0x18001dfb6  cmp     eax, 1
0x18001dfb9  jnz     short loc_18001DFCA
0x18001dfbb  mov     rax, [rbx]
0x18001dfbe  mov     rcx, rbx
0x18001dfc1  mov     rax, [rax+8]
0x18001dfc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dfca  mov     rbx, qword ptr [rbp+var_20+8]
0x18001dfce  test    rbx, rbx
0x18001dfd1  jz      short loc_18001E00A
0x18001dfd3  or      eax, 0FFFFFFFFh
0x18001dfd6  lock xadd [rbx+8], eax
0x18001dfdb  cmp     eax, 1
0x18001dfde  jnz     short loc_18001E00A
0x18001dfe0  mov     rax, [rbx]
0x18001dfe3  mov     rcx, rbx
0x18001dfe6  mov     rax, [rax]
0x18001dfe9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dfee  or      eax, 0FFFFFFFFh
0x18001dff1  lock xadd [rbx+0Ch], eax
0x18001dff6  cmp     eax, 1
0x18001dff9  jnz     short loc_18001E00A
0x18001dffb  mov     rax, [rbx]
0x18001dffe  mov     rcx, rbx
0x18001e001  mov     rax, [rax+8]
0x18001e005  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e00a  mov     rax, [rdi]
0x18001e00d  mov     rbx, [rax+20h]
0x18001e011  mov     rbx, [rbx]
0x18001e014  cmp     [rbx+19h], r13b
0x18001e018  jnz     short loc_18001E06E
0x18001e01a  lea     r8, [rbx+30h]; struct winrt::hstring *
0x18001e01e  mov     dl, [rbx+28h]; unsigned __int8
0x18001e021  mov     rcx, [rsi]; this
0x18001e024  call    ?UpdateSourceEntryCustomName@MidiEndpointNameTable@WindowsMidiServicesNamingLib@@QEAA_NEAEBUhstring@winrt@@@Z; WindowsMidiServicesNamingLib::MidiEndpointNameTable::UpdateSourceEntryCustomName(uchar,winrt::hstring const &)
0x18001e029  mov     rcx, [rbx+10h]
0x18001e02d  cmp     [rcx+19h], r13b
0x18001e031  jz      short loc_18001E051
0x18001e033  mov     rax, [rbx+8]
0x18001e037  jmp     short loc_18001E046
0x18001e039  cmp     rbx, [rax+10h]
0x18001e03d  jnz     short loc_18001E04C
0x18001e03f  mov     rbx, rax
0x18001e042  mov     rax, [rax+8]
0x18001e046  cmp     [rax+19h], r13b
0x18001e04a  jz      short loc_18001E039
0x18001e04c  mov     rbx, rax
0x18001e04f  jmp     short loc_18001E014
0x18001e051  mov     rbx, rcx
0x18001e054  mov     rcx, [rcx]
0x18001e057  cmp     [rcx+19h], r13b
0x18001e05b  jnz     short loc_18001E014
0x18001e05d  mov     rbx, rcx
0x18001e060  mov     rax, [rcx]
0x18001e063  mov     rcx, rax
0x18001e066  cmp     [rax+19h], r13b
0x18001e06a  jz      short loc_18001E05D
0x18001e06c  jmp     short loc_18001E014
0x18001e06e  mov     rax, [rdi]
0x18001e071  mov     rbx, [rax+30h]
0x18001e075  mov     rbx, [rbx]
0x18001e078  mov     rcx, [rsi]; this
0x18001e07b  cmp     [rbx+19h], r13b
0x18001e07f  jnz     short loc_18001E0D2
0x18001e081  lea     r8, [rbx+30h]; struct winrt::hstring *
0x18001e085  mov     dl, [rbx+28h]; unsigned __int8
0x18001e088  call    ?UpdateDestinationEntryCustomName@MidiEndpointNameTable@WindowsMidiServicesNamingLib@@QEAA_NEAEBUhstring@winrt@@@Z; WindowsMidiServicesNamingLib::MidiEndpointNameTable::UpdateDestinationEntryCustomName(uchar,winrt::hstring const &)
0x18001e08d  mov     rcx, [rbx+10h]
0x18001e091  cmp     [rcx+19h], r13b
0x18001e095  jz      short loc_18001E0B5
0x18001e097  mov     rax, [rbx+8]
0x18001e09b  jmp     short loc_18001E0AA
0x18001e09d  cmp     rbx, [rax+10h]
0x18001e0a1  jnz     short loc_18001E0B0
0x18001e0a3  mov     rbx, rax
0x18001e0a6  mov     rax, [rax+8]
0x18001e0aa  cmp     [rax+19h], r13b
0x18001e0ae  jz      short loc_18001E09D
0x18001e0b0  mov     rbx, rax
0x18001e0b3  jmp     short loc_18001E078
0x18001e0b5  mov     rbx, rcx
0x18001e0b8  mov     rcx, [rcx]
0x18001e0bb  cmp     [rcx+19h], r13b
0x18001e0bf  jnz     short loc_18001E078
0x18001e0c1  mov     rbx, rcx
0x18001e0c4  mov     rax, [rcx]
0x18001e0c7  mov     rcx, rax
0x18001e0ca  cmp     [rax+19h], r13b
0x18001e0ce  jz      short loc_18001E0C1
0x18001e0d0  jmp     short loc_18001E078
0x18001e0d2  mov     rdx, [rbp+arg_28]
0x18001e0d6  call    ?WriteProperties@MidiEndpointNameTable@WindowsMidiServicesNamingLib@@QEAAJAEAV?$vector@U_DEVPROPERTY@@V?$allocator@U_DEVPROPERTY@@@std@@@std@@@Z; WindowsMidiServicesNamingLib::MidiEndpointNameTable::WriteProperties(std::vector<_DEVPROPERTY> &)
0x18001e0db  jmp     short loc_18001E12F
0x18001e0dd  call    ?Instance@MidiKSAggregateTransportTelemetryProvider@@KAPEAV1@XZ; MidiKSAggregateTransportTelemetryProvider::Instance(void)
0x18001e0e2  mov     rcx, [rax+8]
0x18001e0e6  mov     eax, [rcx]
0x18001e0e8  cmp     eax, 4
0x18001e0eb  jbe     short loc_18001E12F
0x18001e0ed  lea     rax, aUnableToWriteC; "Unable to write custom user properties."
0x18001e0f4  mov     [rbp+arg_8], rax
0x18001e0f8  mov     qword ptr [rbp+var_20], rsi
0x18001e0fc  lea     rax, aCmidi2ksaggreg_32; "CMidi2KSAggregateMidiConfigurationManag"...
0x18001e103  mov     qword ptr [rbp+var_30], rax
0x18001e107  lea     rax, [rbp+arg_8]
0x18001e10b  mov     [rsp+70h+var_40], rax
0x18001e110  lea     rax, [rbp+var_20]
0x18001e114  mov     [rsp+70h+var_48], rax
0x18001e119  lea     rax, [rbp+var_30]
0x18001e11d  lea     rdx, byte_1800890A5
0x18001e124  mov     [rsp+70h+var_50], rax
0x18001e129  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x18001e12e  nop
0x18001e12f  cmp     [rbp+arg_38], r13
0x18001e133  jz      short loc_18001E13F
0x18001e135  lea     rcx, [rbp+arg_38]
0x18001e139  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001e13e  nop
0x18001e13f  mov     rbx, [r14]
0x18001e142  test    rbx, rbx
0x18001e145  jz      short loc_18001E16A
0x18001e147  or      eax, 0FFFFFFFFh
0x18001e14a  lock xadd [rbx+18h], eax
0x18001e14f  sub     eax, 1
0x18001e152  jnz     short loc_18001E1D3
0x18001e154  nop
0x18001e155  call    WINRT_IMPL_GetProcessHeap
0x18001e15a  mov     rcx, rax; hHeap
0x18001e15d  mov     r8, rbx; lpMem
0x18001e160  xor     edx, edx; dwFlags
0x18001e162  call    WINRT_IMPL_HeapFree
0x18001e167  mov     [r14], r13
0x18001e16a  mov     rbx, [r12+8]
0x18001e16f  test    rbx, rbx
0x18001e172  jz      short loc_18001E1AC
0x18001e174  or      eax, 0FFFFFFFFh
  ... truncated ...
```
