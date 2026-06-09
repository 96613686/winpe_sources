# CMidi2KSMidiConfigurationManager::ProcessCustomProperties(winrt::hstring,std::shared_ptr<WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria>,winrt::Windows::Data::Json::JsonObject,std::shared_ptr<WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomProperties> &,std::vector<_DEVPROPERTY,std::allocator<_DEVPROPERTY>> &,std::shared_ptr<WindowsMidiServicesNamingLib::MidiEndpointNameTable> &,winrt::Windows::Data::Json::JsonObject &)

- ea: `0x1800230a0`
- end: `0x18002352e`
- name: `?ProcessCustomProperties@CMidi2KSMidiConfigurationManager@@AEAAJUhstring@winrt@@V?$shared_ptr@VMidiEndpointMatchCriteria@WindowsMidiServicesPluginConfigurationLib@@@std@@UJsonObject@Json@Data@Windows@3@AEAV?$shared_ptr@VMidiEndpointCustomProperties@WindowsMidiServicesPluginConfigurationLib@@@5@AEAV?$vector@U_DEVPROPERTY@@V?$allocator@U_DEVPROPERTY@@@std@@@5@AEAV?$shared_ptr@VMidiEndpointNameTable@WindowsMidiServicesNamingLib@@@5@AEAU67893@@Z`
- size: `1166`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180023ac0`

## callees

- `0x1800016dc`
- `0x1800052fc`
- `0x180005374`
- `0x18000d1c0`
- `0x18000db18`
- `0x18001fdb0`
- `0x1800222c0`
- `0x1800225bc`
- `0x1800230a0`
- `0x18002a964`
- `0x18002af94`
- `0x18002c0a8`
- `0x1800378b8`
- `0x18003984c`
- `0x180039958`
- `0x180039a64`
- `0x180041010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180023527`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180023527`

## string_xrefs

- `0x180023271`: `avcore\midi2\transport\kstransport\midi2.ksmidiconfigurationmanager.cpp`
- `0x1800231dd`: `CMidi2KSMidiConfigurationManager::ProcessCustomProperties`
- `0x18002344c`: `CMidi2KSMidiConfigurationManager::ProcessCustomProperties`
- `0x1800231ce`: `Failed reading custom user properties`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 CMidi2KSMidiConfigurationManager::ProcessCustomProperties(__int64 a1, ...)
{
  _QWORD *v1; // r15
  __int64 v2; // r12
  volatile signed __int32 **v3; // r14
  WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomProperties **v5; // rax
  WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomProperties *v6; // rcx
  WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomProperties *v7; // rdx
  WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomProperties **v8; // rdi
  volatile signed __int32 *v9; // rbx
  volatile signed __int32 *v10; // rbx
  _DWORD *v11; // rcx
  int v12; // r8d
  int v13; // r9d
  __int64 v14; // rcx
  WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomProperties *v15; // rax
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
  WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomProperties **v48; // [rsp+D0h] [rbp+60h]
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
  v48 = va_arg(va1, WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomProperties **);
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
    v5 = WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomProperties::FromJson(
           (WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomProperties **)v42,
           (__int64)va1);
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
        _InterlockedIncrement((volatile signed __int32 *)v15 + 2);
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
          (void *)0x6A,
          (unsigned int)"avcore\\midi2\\transport\\kstransport\\midi2.ksmidiconfigurationmanager.cpp",
          (const char *)0x80004005LL,
          v40);
      if ( *v3 )
      {
        if ( (unsigned __int8)WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomProperties::WriteAllProperties(
                                *v8,
                                v49) )
        {
          if ( *((_QWORD *)*v8 + 7) || *((_QWORD *)*v8 + 5) )
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
            v23 = (__int64 *)**((_QWORD **)*v8 + 4);
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
            v27 = (__int64 *)**((_QWORD **)*v8 + 6);
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
          v32 = (_DWORD *)*((_QWORD *)MidiKSTransportTelemetryProvider::Instance() + 1);
          if ( *v32 > 4u )
          {
            v44 = L"Failed writing custom user properties";
            *(_QWORD *)&v42[0] = a1;
            *(_QWORD *)&v41 = "CMidi2KSMidiConfigurationManager::ProcessCustomProperties";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
              (_DWORD)v32,
              (unsigned int)&dword_180068E5C,
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
      v11 = (_DWORD *)*((_QWORD *)MidiKSTransportTelemetryProvider::Instance() + 1);
      if ( *v11 > 4u )
      {
        v44 = L"Failed reading custom user properties";
        *(_QWORD *)&v41 = a1;
        *(_QWORD *)&v42[0] = "CMidi2KSMidiConfigurationManager::ProcessCustomProperties";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
          (_DWORD)v11,
          (unsigned int)word_180068E2A,
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
0x1800230a0  mov     rax, rsp
0x1800230a3  mov     [rax+8], rbx
0x1800230a7  mov     [rax+20h], r9
0x1800230ab  mov     [rax+18h], r8
0x1800230af  mov     [rax+10h], rdx
0x1800230b3  push    rbp
0x1800230b4  push    rsi
0x1800230b5  push    rdi
0x1800230b6  push    r12
0x1800230b8  push    r13
0x1800230ba  push    r14
0x1800230bc  push    r15
0x1800230be  mov     rbp, rsp
0x1800230c1  sub     rsp, 70h
0x1800230c5  mov     r15, r9
0x1800230c8  mov     r12, r8
0x1800230cb  mov     r14, rdx
0x1800230ce  mov     rsi, rcx
0x1800230d1  mov     rax, cs:?PropertyKey@MidiEndpointCustomProperties@WindowsMidiServicesPluginConfigurationLib@@2Uhstring@winrt@@A; winrt::hstring WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomProperties::PropertyKey
0x1800230d8  mov     qword ptr [rbp+var_20], rax
0x1800230dc  lea     rdx, [rbp+var_20]
0x1800230e0  mov     rcx, r9
0x1800230e3  call    ?HasKey@?$consume_Windows_Foundation_Collections_IMap@UJsonObject@Json@Data@Windows@winrt@@Uhstring@5@UIJsonValue@2345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(winrt::param::hstring const &)
0x1800230e8  xor     r13d, r13d
0x1800230eb  test    al, al
0x1800230ed  jz      loc_18002348F
0x1800230f3  mov     rax, cs:?PropertyKey@MidiEndpointCustomProperties@WindowsMidiServicesPluginConfigurationLib@@2Uhstring@winrt@@A; winrt::hstring WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomProperties::PropertyKey
0x1800230fa  mov     qword ptr [rbp+var_20], rax
0x1800230fe  lea     r8, [rbp+var_20]
0x180023102  lea     rdx, [rbp+arg_38]
0x180023106  mov     rcx, r15
0x180023109  call    ?GetNamedObject@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedObject(winrt::param::hstring const &)
0x18002310e  nop
0x18002310f  lea     rdx, [rbp+arg_38]
0x180023113  lea     rcx, [rbp+var_20]
0x180023117  call    ?FromJson@MidiEndpointCustomProperties@WindowsMidiServicesPluginConfigurationLib@@SA?AV?$shared_ptr@VMidiEndpointCustomProperties@WindowsMidiServicesPluginConfigurationLib@@@std@@AEBUJsonObject@Json@Data@Windows@winrt@@@Z; WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomProperties::FromJson(winrt::Windows::Data::Json::JsonObject const &)
0x18002311c  mov     rcx, [rax]
0x18002311f  mov     rdx, [rax+8]
0x180023123  mov     [rax], r13
0x180023126  mov     [rax+8], r13
0x18002312a  mov     rdi, [rbp+arg_20]
0x18002312e  mov     [rdi], rcx
0x180023131  mov     rbx, [rdi+8]
0x180023135  mov     [rdi+8], rdx
0x180023139  test    rbx, rbx
0x18002313c  jz      short loc_180023175
0x18002313e  or      eax, 0FFFFFFFFh
0x180023141  lock xadd [rbx+8], eax
0x180023146  cmp     eax, 1
0x180023149  jnz     short loc_180023175
0x18002314b  mov     rax, [rbx]
0x18002314e  mov     rcx, rbx
0x180023151  mov     rax, [rax]
0x180023154  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023159  or      eax, 0FFFFFFFFh
0x18002315c  lock xadd [rbx+0Ch], eax
0x180023161  cmp     eax, 1
0x180023164  jnz     short loc_180023175
0x180023166  mov     rax, [rbx]
0x180023169  mov     rcx, rbx
0x18002316c  mov     rax, [rax+8]
0x180023170  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023175  mov     rbx, qword ptr [rbp+var_20+8]
0x180023179  test    rbx, rbx
0x18002317c  jz      short loc_1800231B5
0x18002317e  or      eax, 0FFFFFFFFh
0x180023181  lock xadd [rbx+8], eax
0x180023186  cmp     eax, 1
0x180023189  jnz     short loc_1800231B5
0x18002318b  mov     rax, [rbx]
0x18002318e  mov     rcx, rbx
0x180023191  mov     rax, [rax]
0x180023194  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023199  or      eax, 0FFFFFFFFh
0x18002319c  lock xadd [rbx+0Ch], eax
0x1800231a1  cmp     eax, 1
0x1800231a4  jnz     short loc_1800231B5
0x1800231a6  mov     rax, [rbx]
0x1800231a9  mov     rcx, rbx
0x1800231ac  mov     rax, [rax+8]
0x1800231b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800231b5  cmp     [rdi], r13
0x1800231b8  jnz     short loc_18002320A
0x1800231ba  call    ?Instance@MidiKSTransportTelemetryProvider@@KAPEAV1@XZ; MidiKSTransportTelemetryProvider::Instance(void)
0x1800231bf  mov     rcx, [rax+8]
0x1800231c3  mov     eax, [rcx]
0x1800231c5  cmp     eax, 4
0x1800231c8  jbe     loc_18002347F
0x1800231ce  lea     rax, aFailedReadingC; "Failed reading custom user properties"
0x1800231d5  mov     [rbp+arg_8], rax
0x1800231d9  mov     qword ptr [rbp+var_30], rsi
0x1800231dd  lea     rax, aCmidi2ksmidico_1; "CMidi2KSMidiConfigurationManager::Proce"...
0x1800231e4  mov     qword ptr [rbp+var_20], rax
0x1800231e8  lea     rax, [rbp+arg_8]
0x1800231ec  mov     [rsp+70h+var_40], rax
0x1800231f1  lea     rax, [rbp+var_30]
0x1800231f5  mov     [rsp+70h+var_48], rax
0x1800231fa  lea     rax, [rbp+var_20]
0x1800231fe  lea     rdx, word_180068E2A
0x180023205  jmp     loc_180023474
0x18002320a  mov     rcx, [rsi+10h]
0x18002320e  xorps   xmm0, xmm0
0x180023211  movdqu  [rbp+var_30], xmm0
0x180023216  mov     rax, [rdi+8]
0x18002321a  test    rax, rax
0x18002321d  jz      short loc_180023223
0x18002321f  lock inc dword ptr [rax+8]
0x180023223  mov     rax, [rdi]
0x180023226  mov     qword ptr [rbp+var_30], rax
0x18002322a  mov     rax, [rdi+8]
0x18002322e  mov     qword ptr [rbp+var_30+8], rax
0x180023232  movdqu  [rbp+var_20], xmm0
0x180023237  mov     rax, [r12+8]
0x18002323c  test    rax, rax
0x18002323f  jz      short loc_180023245
0x180023241  lock inc dword ptr [rax+8]
0x180023245  mov     rax, [r12]
0x180023249  mov     qword ptr [rbp+var_20], rax
0x18002324d  mov     rax, [r12+8]
0x180023252  mov     qword ptr [rbp+var_20+8], rax
0x180023256  mov     rbx, [rbp+38h]
0x18002325a  lea     r8, [rbp+var_30]
0x18002325e  lea     rdx, [rbp+var_20]
0x180023262  call    ?Add@MidiEndpointCustomPropertiesCache@WindowsMidiServicesPluginConfigurationLib@@QEAA_NV?$shared_ptr@VMidiEndpointMatchCriteria@WindowsMidiServicesPluginConfigurationLib@@@std@@V?$shared_ptr@VMidiEndpointCustomProperties@WindowsMidiServicesPluginConfigurationLib@@@4@@Z; WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomPropertiesCache::Add(std::shared_ptr<WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria>,std::shared_ptr<WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomProperties>)
0x180023267  test    al, al
0x180023269  jnz     short loc_180023285
0x18002326b  mov     r9d, 80004005h; char *
0x180023271  lea     r8, aAvcoreMidi2Tra_7; "avcore\\midi2\\transport\\kstransport\\"...
0x180023278  mov     edx, 6Ah ; 'j'; void *
0x18002327d  mov     rcx, rbx; this
0x180023280  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180023285  cmp     [r14], r13
0x180023288  jz      loc_18002347F
0x18002328e  mov     rdx, [rbp+arg_28]
0x180023292  mov     rcx, [rdi]
0x180023295  call    ?WriteAllProperties@MidiEndpointCustomProperties@WindowsMidiServicesPluginConfigurationLib@@QEAA_NAEAV?$vector@U_DEVPROPERTY@@V?$allocator@U_DEVPROPERTY@@@std@@@std@@@Z; WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomProperties::WriteAllProperties(std::vector<_DEVPROPERTY> &)
0x18002329a  test    al, al
0x18002329c  jz      loc_18002342D
0x1800232a2  mov     rax, [rdi]
0x1800232a5  cmp     [rax+38h], r13
0x1800232a9  ja      short loc_1800232B5
0x1800232ab  cmp     [rax+28h], r13
0x1800232af  jbe     loc_18002347F
0x1800232b5  mov     rdx, r14
0x1800232b8  lea     rcx, [rbp+var_20]
0x1800232bc  call    ?FromEndpointDeviceId@MidiEndpointNameTable@WindowsMidiServicesNamingLib@@SA?AV?$shared_ptr@VMidiEndpointNameTable@WindowsMidiServicesNamingLib@@@std@@AEBUhstring@winrt@@@Z; WindowsMidiServicesNamingLib::MidiEndpointNameTable::FromEndpointDeviceId(winrt::hstring const &)
0x1800232c1  mov     rcx, [rax]
0x1800232c4  mov     rdx, [rax+8]
0x1800232c8  mov     [rax], r13
0x1800232cb  mov     [rax+8], r13
0x1800232cf  mov     rsi, [rbp+arg_30]
0x1800232d3  mov     [rsi], rcx
0x1800232d6  mov     rbx, [rsi+8]
0x1800232da  mov     [rsi+8], rdx
0x1800232de  test    rbx, rbx
0x1800232e1  jz      short loc_18002331A
0x1800232e3  or      eax, 0FFFFFFFFh
0x1800232e6  lock xadd [rbx+8], eax
0x1800232eb  cmp     eax, 1
0x1800232ee  jnz     short loc_18002331A
0x1800232f0  mov     rax, [rbx]
0x1800232f3  mov     rcx, rbx
0x1800232f6  mov     rax, [rax]
0x1800232f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800232fe  or      eax, 0FFFFFFFFh
0x180023301  lock xadd [rbx+0Ch], eax
0x180023306  cmp     eax, 1
0x180023309  jnz     short loc_18002331A
0x18002330b  mov     rax, [rbx]
0x18002330e  mov     rcx, rbx
0x180023311  mov     rax, [rax+8]
0x180023315  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002331a  mov     rbx, qword ptr [rbp+var_20+8]
0x18002331e  test    rbx, rbx
0x180023321  jz      short loc_18002335A
0x180023323  or      eax, 0FFFFFFFFh
0x180023326  lock xadd [rbx+8], eax
0x18002332b  cmp     eax, 1
0x18002332e  jnz     short loc_18002335A
0x180023330  mov     rax, [rbx]
0x180023333  mov     rcx, rbx
0x180023336  mov     rax, [rax]
0x180023339  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002333e  or      eax, 0FFFFFFFFh
0x180023341  lock xadd [rbx+0Ch], eax
0x180023346  cmp     eax, 1
0x180023349  jnz     short loc_18002335A
0x18002334b  mov     rax, [rbx]
0x18002334e  mov     rcx, rbx
0x180023351  mov     rax, [rax+8]
0x180023355  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002335a  mov     rax, [rdi]
0x18002335d  mov     rbx, [rax+20h]
0x180023361  mov     rbx, [rbx]
0x180023364  cmp     [rbx+19h], r13b
0x180023368  jnz     short loc_1800233BE
0x18002336a  lea     r8, [rbx+30h]; struct winrt::hstring *
0x18002336e  mov     dl, [rbx+28h]; unsigned __int8
0x180023371  mov     rcx, [rsi]; this
0x180023374  call    ?UpdateSourceEntryCustomName@MidiEndpointNameTable@WindowsMidiServicesNamingLib@@QEAA_NEAEBUhstring@winrt@@@Z; WindowsMidiServicesNamingLib::MidiEndpointNameTable::UpdateSourceEntryCustomName(uchar,winrt::hstring const &)
0x180023379  mov     rcx, [rbx+10h]
0x18002337d  cmp     [rcx+19h], r13b
0x180023381  jz      short loc_1800233A1
0x180023383  mov     rax, [rbx+8]
0x180023387  jmp     short loc_180023396
0x180023389  cmp     rbx, [rax+10h]
0x18002338d  jnz     short loc_18002339C
0x18002338f  mov     rbx, rax
0x180023392  mov     rax, [rax+8]
0x180023396  cmp     [rax+19h], r13b
0x18002339a  jz      short loc_180023389
0x18002339c  mov     rbx, rax
0x18002339f  jmp     short loc_180023364
0x1800233a1  mov     rbx, rcx
0x1800233a4  mov     rcx, [rcx]
0x1800233a7  cmp     [rcx+19h], r13b
0x1800233ab  jnz     short loc_180023364
0x1800233ad  mov     rbx, rcx
0x1800233b0  mov     rax, [rcx]
0x1800233b3  mov     rcx, rax
0x1800233b6  cmp     [rax+19h], r13b
0x1800233ba  jz      short loc_1800233AD
0x1800233bc  jmp     short loc_180023364
0x1800233be  mov     rax, [rdi]
0x1800233c1  mov     rbx, [rax+30h]
0x1800233c5  mov     rbx, [rbx]
0x1800233c8  mov     rcx, [rsi]; this
0x1800233cb  cmp     [rbx+19h], r13b
0x1800233cf  jnz     short loc_180023422
0x1800233d1  lea     r8, [rbx+30h]; struct winrt::hstring *
0x1800233d5  mov     dl, [rbx+28h]; unsigned __int8
0x1800233d8  call    ?UpdateDestinationEntryCustomName@MidiEndpointNameTable@WindowsMidiServicesNamingLib@@QEAA_NEAEBUhstring@winrt@@@Z; WindowsMidiServicesNamingLib::MidiEndpointNameTable::UpdateDestinationEntryCustomName(uchar,winrt::hstring const &)
0x1800233dd  mov     rcx, [rbx+10h]
0x1800233e1  cmp     [rcx+19h], r13b
0x1800233e5  jz      short loc_180023405
0x1800233e7  mov     rax, [rbx+8]
0x1800233eb  jmp     short loc_1800233FA
0x1800233ed  cmp     rbx, [rax+10h]
0x1800233f1  jnz     short loc_180023400
0x1800233f3  mov     rbx, rax
0x1800233f6  mov     rax, [rax+8]
0x1800233fa  cmp     [rax+19h], r13b
0x1800233fe  jz      short loc_1800233ED
0x180023400  mov     rbx, rax
0x180023403  jmp     short loc_1800233C8
0x180023405  mov     rbx, rcx
0x180023408  mov     rcx, [rcx]
0x18002340b  cmp     [rcx+19h], r13b
0x18002340f  jnz     short loc_1800233C8
0x180023411  mov     rbx, rcx
0x180023414  mov     rax, [rcx]
0x180023417  mov     rcx, rax
0x18002341a  cmp     [rax+19h], r13b
0x18002341e  jz      short loc_180023411
0x180023420  jmp     short loc_1800233C8
0x180023422  mov     rdx, [rbp+arg_28]
0x180023426  call    ?WriteProperties@MidiEndpointNameTable@WindowsMidiServicesNamingLib@@QEAAJAEAV?$vector@U_DEVPROPERTY@@V?$allocator@U_DEVPROPERTY@@@std@@@std@@@Z; WindowsMidiServicesNamingLib::MidiEndpointNameTable::WriteProperties(std::vector<_DEVPROPERTY> &)
0x18002342b  jmp     short loc_18002347F
0x18002342d  call    ?Instance@MidiKSTransportTelemetryProvider@@KAPEAV1@XZ; MidiKSTransportTelemetryProvider::Instance(void)
0x180023432  mov     rcx, [rax+8]
0x180023436  mov     eax, [rcx]
0x180023438  cmp     eax, 4
0x18002343b  jbe     short loc_18002347F
0x18002343d  lea     rax, aFailedWritingC; "Failed writing custom user properties"
0x180023444  mov     [rbp+arg_8], rax
0x180023448  mov     qword ptr [rbp+var_20], rsi
0x18002344c  lea     rax, aCmidi2ksmidico_1; "CMidi2KSMidiConfigurationManager::Proce"...
0x180023453  mov     qword ptr [rbp+var_30], rax
0x180023457  lea     rax, [rbp+arg_8]
0x18002345b  mov     [rsp+70h+var_40], rax
0x180023460  lea     rax, [rbp+var_20]
0x180023464  mov     [rsp+70h+var_48], rax
0x180023469  lea     rax, [rbp+var_30]
0x18002346d  lea     rdx, dword_180068E5C
0x180023474  mov     [rsp+70h+var_50], rax
0x180023479  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x18002347e  nop
0x18002347f  cmp     [rbp+arg_38], r13
0x180023483  jz      short loc_18002348F
0x180023485  lea     rcx, [rbp+arg_38]
0x180023489  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18002348e  nop
0x18002348f  mov     rbx, [r14]
0x180023492  test    rbx, rbx
0x180023495  jz      short loc_1800234BA
0x180023497  or      eax, 0FFFFFFFFh
0x18002349a  lock xadd [rbx+18h], eax
0x18002349f  sub     eax, 1
0x1800234a2  jnz     short loc_180023523
0x1800234a4  nop
0x1800234a5  call    WINRT_IMPL_GetProcessHeap
0x1800234aa  mov     rcx, rax; hHeap
0x1800234ad  mov     r8, rbx; lpMem
0x1800234b0  xor     edx, edx; dwFlags
0x1800234b2  call    WINRT_IMPL_HeapFree
0x1800234b7  mov     [r14], r13
0x1800234ba  mov     rbx, [r12+8]
0x1800234bf  test    rbx, rbx
0x1800234c2  jz      short loc_1800234FC
0x1800234c4  or      eax, 0FFFFFFFFh
  ... truncated ...
```
