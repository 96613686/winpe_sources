# InstantiatePasskeyManagerOld(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,PluginAuthenticatorInstance &)

- ea: `0x18011f0b0`
- end: `0x18011f3f9`
- name: `?InstantiatePasskeyManagerOld@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAUPluginAuthenticatorInstance@@@Z`
- size: `841`
- prototype: `__int64 __fastcall(const OLECHAR *lpsz, LPVOID *ppv, __int64)`
- caller_count: `4`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18009f1c0`
- `0x18009f958`
- `0x1800a33e4`
- `0x1801139f8`

## callees

- `0x1800021d8`
- `0x18002bbc8`
- `0x180036da4`
- `0x180046820`
- `0x18006f174`
- `0x18011f0b0`
- `0x18013c090`
- `0x180149010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x18011f191`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x18011f191`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18011f148`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18011f148`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18011f1d2`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18011f2d0`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18011f374`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18011f3b1`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18011f1d2`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18011f2d0`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18011f374`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18011f3b1`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x18011f227`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x18011f227`

## string_xrefs

- `0x18011f160`: `onecore\ds\security\fido\ctap\transports_modern\ctaputils.cpp`
- `0x18011f294`: `onecore\ds\security\fido\ctap\transports_modern\ctaputils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall InstantiatePasskeyManagerOld(const OLECHAR *lpsz, LPVOID *ppv, __int64 a3)
{
  _DWORD *v5; // rcx
  HRESULT ClassObject; // ebx
  __int64 v7; // rdx
  LPVOID v8; // rbx
  HRESULT AgileReference; // eax
  __int64 v10; // rdx
  LPVOID v11; // rdi
  __int64 (__fastcall *v12)(LPVOID, _QWORD, GUID *, LPVOID *); // rbx
  IUnknown **v13; // r14
  IUnknown *v14; // rdi
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbx
  IUnknown *v16; // rdi
  HRESULT (__stdcall *v17)(IUnknown *, const IID *const, void **); // rbx
  int ppva; // [rsp+20h] [rbp-50h]
  __int64 v20; // [rsp+40h] [rbp-30h] BYREF
  __int64 v21; // [rsp+48h] [rbp-28h] BYREF
  __int64 v22; // [rsp+50h] [rbp-20h] BYREF
  GUID pclsid; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(
                          `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl'::`2'::impl,
                          ppv,
                          a3) )
  {
    v5 = *(_DWORD **)(wil::details::static_lazy<FidoPluginProvider>::get() + 16);
    if ( *v5 > 4u )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        v5,
        &word_18018D7FE,
        0);
  }
  else if ( (unsigned int)dword_1801AB110 > 4 )
  {
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_1801AB110,
      &word_18018D82E,
      0);
  }
  pclsid = 0;
  if ( *((_QWORD *)lpsz + 3) > 7u )
    lpsz = *(const OLECHAR **)lpsz;
  ClassObject = CLSIDFromString(lpsz, &pclsid);
  if ( ClassObject >= 0 )
  {
    _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(ppv);
    ClassObject = CoGetClassObject(&pclsid, 0x110004u, 0, &GUID_00000001_0000_0000_c000_000000000046, ppv);
    if ( ClassObject < 0 )
    {
      v7 = 679;
      goto LABEL_10;
    }
    ClassObject = CoSetProxyBlanket(
                    (IUnknown *)*ppv,
                    0xFFFFFFFF,
                    0xFFFFFFFF,
                    (OLECHAR *)0xFFFFFFFFFFFFFFFFLL,
                    0,
                    2u,
                    0,
                    0x20u);
    if ( ClassObject < 0 )
    {
      v7 = 683;
      goto LABEL_10;
    }
    v22 = 0;
    v21 = 0;
    v20 = 0;
    _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v21);
    _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v22);
    v8 = *ppv;
    if ( *ppv )
    {
      _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v20);
      AgileReference = RoGetAgileReference(0, &GUID_00000001_0000_0000_c000_000000000046, v8, &v20);
      ClassObject = AgileReference;
      if ( AgileReference < 0 )
      {
        v10 = 686;
        goto LABEL_21;
      }
    }
    else
    {
      v21 = 0;
      v22 = v20;
      v20 = 0;
      _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v22);
      _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v21);
    }
    v11 = *ppv;
    v12 = *(__int64 (__fastcall **)(LPVOID, _QWORD, GUID *, LPVOID *))(*(_QWORD *)*ppv + 24LL);
    v13 = (IUnknown **)(ppv + 1);
    _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(ppv + 1);
    AgileReference = v12(v11, 0, &GUID_00000000_0000_0000_c000_000000000046, ppv + 1);
    ClassObject = AgileReference;
    if ( AgileReference >= 0 )
    {
      AgileReference = CoSetProxyBlanket(*v13, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 2u, 0, 0x20u);
      ClassObject = AgileReference;
      if ( AgileReference >= 0 )
      {
        v14 = *v13;
        QueryInterface = (*v13)->lpVtbl->QueryInterface;
        _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(ppv + 3);
        if ( ((unsigned int (__fastcall *)(IUnknown *, GUID *, LPVOID *))QueryInterface)(
               v14,
               &GUID_d26bcf6f_b54c_43ff_9f06_d5bf148625f7,
               ppv + 3) == -2147467262 )
        {
          v16 = *v13;
          v17 = (*v13)->lpVtbl->QueryInterface;
          _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(ppv + 2);
          AgileReference = ((__int64 (__fastcall *)(IUnknown *, GUID *, LPVOID *))v17)(
                             v16,
                             &GUID_e6466e9a_b2f3_47c5_b88d_89bc14a8d998,
                             ppv + 2);
          ClassObject = AgileReference;
          if ( AgileReference < 0 )
          {
            v10 = 696;
            goto LABEL_21;
          }
          AgileReference = CoSetProxyBlanket(
                             (IUnknown *)ppv[2],
                             0xFFFFFFFF,
                             0xFFFFFFFF,
                             (OLECHAR *)0xFFFFFFFFFFFFFFFFLL,
                             0,
                             2u,
                             0,
                             0x20u);
          ClassObject = AgileReference;
          if ( AgileReference < 0 )
          {
            v10 = 699;
            goto LABEL_21;
          }
        }
        else
        {
          AgileReference = CoSetProxyBlanket(
                             (IUnknown *)ppv[3],
                             0xFFFFFFFF,
                             0xFFFFFFFF,
                             (OLECHAR *)0xFFFFFFFFFFFFFFFFLL,
                             0,
                             2u,
                             0,
                             0x20u);
          ClassObject = AgileReference;
          if ( AgileReference < 0 )
          {
            v10 = 705;
            goto LABEL_21;
          }
        }
        ClassObject = 0;
        goto LABEL_32;
      }
      v10 = 691;
    }
    else
    {
      v10 = 688;
    }
LABEL_21:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaputils.cpp",
      (const char *)(unsigned int)AgileReference,
      ppva);
LABEL_32:
    _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v20);
    return (unsigned int)ClassObject;
  }
  v7 = 672;
LABEL_10:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v7,
    (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaputils.cpp",
    (const char *)(unsigned int)ClassObject,
    ppva);
  return (unsigned int)ClassObject;
}

```

## disassembly

```asm
0x18011f0b0  mov     [rsp-38h+arg_10], rbx
0x18011f0b5  push    rbp
0x18011f0b6  push    rsi
0x18011f0b7  push    rdi
0x18011f0b8  push    r12
0x18011f0ba  push    r13
0x18011f0bc  push    r14
0x18011f0be  push    r15
0x18011f0c0  mov     rbp, rsp
0x18011f0c3  sub     rsp, 70h
0x18011f0c7  mov     rax, cs:__security_cookie
0x18011f0ce  xor     rax, rsp
0x18011f0d1  mov     [rbp+var_8], rax
0x18011f0d5  mov     rsi, rdx
0x18011f0d8  mov     rbx, rcx
0x18011f0db  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2> `wil::Feature<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::GetImpl(void)'::`2'::impl
0x18011f0e2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WebAuthNTraceLoggingImprovementsV2>::__private_IsEnabled(void)
0x18011f0e7  xor     r12d, r12d
0x18011f0ea  test    al, al
0x18011f0ec  jz      short loc_18011F10F
0x18011f0ee  call    ?get@?$static_lazy@VFidoPluginProvider@@@details@wil@@QEAAPEAVFidoPluginProvider@@P6AXXZ@Z; wil::details::static_lazy<FidoPluginProvider>::get(void (*)(void))
0x18011f0f3  mov     rcx, [rax+10h]
0x18011f0f7  mov     eax, [rcx]
0x18011f0f9  cmp     eax, 4
0x18011f0fc  jbe     short loc_18011F130
0x18011f0fe  xor     r8d, r8d
0x18011f101  lea     rdx, word_18018D7FE
0x18011f108  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18011f10d  jmp     short loc_18011F130
0x18011f10f  mov     eax, cs:dword_1801AB110
0x18011f115  cmp     eax, 4
0x18011f118  jbe     short loc_18011F130
0x18011f11a  xor     r8d, r8d
0x18011f11d  lea     rdx, word_18018D82E
0x18011f124  lea     rcx, dword_1801AB110
0x18011f12b  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18011f130  xorps   xmm0, xmm0
0x18011f133  movups  xmmword ptr [rbp+pclsid.Data1], xmm0
0x18011f137  cmp     qword ptr [rbx+18h], 7
0x18011f13c  jbe     short loc_18011F141
0x18011f13e  mov     rbx, [rbx]
0x18011f141  lea     rdx, [rbp+pclsid]; pclsid
0x18011f145  mov     rcx, rbx; lpsz
0x18011f148  call    cs:__imp_CLSIDFromString
0x18011f14e  mov     ebx, eax
0x18011f150  test    eax, eax
0x18011f152  jns     short loc_18011F171
0x18011f154  mov     edx, 2A0h; void *
0x18011f159  mov     rcx, [rbp+38h]; this
0x18011f15d  mov     r9d, ebx; char *
0x18011f160  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18011f167  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011f16c  jmp     loc_18011F3D3
0x18011f171  mov     rcx, rsi
0x18011f174  call    ?InternalRelease@?$ComPtr@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::InternalRelease(void)
0x18011f179  mov     [rsp+70h+ppv], rsi; ppv
0x18011f17e  lea     r9, _GUID_00000001_0000_0000_c000_000000000046; riid
0x18011f185  xor     r8d, r8d; pvReserved
0x18011f188  mov     edx, 110004h; dwClsContext
0x18011f18d  lea     rcx, [rbp+pclsid]; rclsid
0x18011f191  call    cs:__imp_CoGetClassObject
0x18011f197  mov     ebx, eax
0x18011f199  test    eax, eax
0x18011f19b  jns     short loc_18011F1A4
0x18011f19d  mov     edx, 2A7h
0x18011f1a2  jmp     short loc_18011F159
0x18011f1a4  mov     r15d, 20h ; ' '
0x18011f1aa  mov     [rsp+70h+dwCapabilities], r15d; dwCapabilities
0x18011f1af  mov     [rsp+70h+pAuthInfo], r12; pAuthInfo
0x18011f1b4  mov     [rsp+70h+dwImpLevel], 2; dwImpLevel
0x18011f1bc  mov     dword ptr [rsp+70h+ppv], r12d; int
0x18011f1c1  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x18011f1c5  or      r13d, 0FFFFFFFFh
0x18011f1c9  mov     r8d, r13d; dwAuthzSvc
0x18011f1cc  mov     edx, r13d; dwAuthnSvc
0x18011f1cf  mov     rcx, [rsi]; pProxy
0x18011f1d2  call    cs:__imp_CoSetProxyBlanket
0x18011f1d8  mov     ebx, eax
0x18011f1da  test    eax, eax
0x18011f1dc  jns     short loc_18011F1E8
0x18011f1de  mov     edx, 2ABh
0x18011f1e3  jmp     loc_18011F159
0x18011f1e8  mov     [rbp+var_20], r12
0x18011f1ec  mov     [rbp+var_28], r12
0x18011f1f0  mov     [rbp+var_30], r12
0x18011f1f4  lea     rcx, [rbp+var_28]
0x18011f1f8  call    ?InternalRelease@?$ComPtr@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::InternalRelease(void)
0x18011f1fd  lea     rcx, [rbp+var_20]
0x18011f201  call    ?InternalRelease@?$ComPtr@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::InternalRelease(void)
0x18011f206  mov     rbx, [rsi]
0x18011f209  test    rbx, rbx
0x18011f20c  jz      short loc_18011F23A
0x18011f20e  lea     rcx, [rbp+var_30]
0x18011f212  call    ?InternalRelease@?$ComPtr@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::InternalRelease(void)
0x18011f217  lea     r9, [rbp+var_30]
0x18011f21b  mov     r8, rbx
0x18011f21e  lea     rdx, _GUID_00000001_0000_0000_c000_000000000046
0x18011f225  xor     ecx, ecx
0x18011f227  call    cs:__imp_RoGetAgileReference
0x18011f22d  mov     ebx, eax
0x18011f22f  test    eax, eax
0x18011f231  jns     short loc_18011F25C
0x18011f233  mov     edx, 2AEh
0x18011f238  jmp     short loc_18011F294
0x18011f23a  mov     [rbp+var_28], r12
0x18011f23e  mov     rax, [rbp+var_30]
0x18011f242  mov     [rbp+var_20], rax
0x18011f246  mov     [rbp+var_30], r12
0x18011f24a  lea     rcx, [rbp+var_20]
0x18011f24e  call    ?InternalRelease@?$ComPtr@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::InternalRelease(void)
0x18011f253  lea     rcx, [rbp+var_28]
0x18011f257  call    ?InternalRelease@?$ComPtr@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::InternalRelease(void)
0x18011f25c  mov     rdi, [rsi]
0x18011f25f  mov     rax, [rdi]
0x18011f262  mov     rbx, [rax+18h]
0x18011f266  lea     r14, [rsi+8]
0x18011f26a  mov     rcx, r14
0x18011f26d  call    ?InternalRelease@?$ComPtr@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::InternalRelease(void)
0x18011f272  mov     r9, r14
0x18011f275  lea     r8, _GUID_00000000_0000_0000_c000_000000000046
0x18011f27c  xor     edx, edx
0x18011f27e  mov     rcx, rdi
0x18011f281  mov     rax, rbx
0x18011f284  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011f289  mov     ebx, eax
0x18011f28b  test    eax, eax
0x18011f28d  jns     short loc_18011F2AC
0x18011f28f  mov     edx, 2B0h; void *
0x18011f294  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18011f29b  mov     r9d, eax; char *
0x18011f29e  mov     rcx, [rbp+38h]; this
0x18011f2a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011f2a7  jmp     loc_18011F3CA
0x18011f2ac  mov     [rsp+70h+dwCapabilities], r15d; dwCapabilities
0x18011f2b1  mov     [rsp+70h+pAuthInfo], r12; pAuthInfo
0x18011f2b6  mov     [rsp+70h+dwImpLevel], 2; dwImpLevel
0x18011f2be  mov     dword ptr [rsp+70h+ppv], r12d; dwAuthnLevel
0x18011f2c3  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x18011f2c7  mov     r8d, r13d; dwAuthzSvc
0x18011f2ca  mov     edx, r13d; dwAuthnSvc
0x18011f2cd  mov     rcx, [r14]; pProxy
0x18011f2d0  call    cs:__imp_CoSetProxyBlanket
0x18011f2d6  mov     ebx, eax
0x18011f2d8  test    eax, eax
0x18011f2da  jns     short loc_18011F2E3
0x18011f2dc  mov     edx, 2B3h
0x18011f2e1  jmp     short loc_18011F294
0x18011f2e3  mov     rdi, [r14]
0x18011f2e6  mov     rax, [rdi]
0x18011f2e9  mov     rbx, [rax]
0x18011f2ec  lea     r15, [rsi+18h]
0x18011f2f0  mov     rcx, r15
0x18011f2f3  call    ?InternalRelease@?$ComPtr@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::InternalRelease(void)
0x18011f2f8  mov     r8, r15
0x18011f2fb  lea     rdx, _GUID_d26bcf6f_b54c_43ff_9f06_d5bf148625f7
0x18011f302  mov     rcx, rdi
0x18011f305  mov     rax, rbx
0x18011f308  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011f30d  cmp     eax, 80004002h
0x18011f312  jnz     short loc_18011F38A
0x18011f314  mov     rdi, [r14]
0x18011f317  mov     rax, [rdi]
0x18011f31a  mov     rbx, [rax]
0x18011f31d  lea     rcx, [rsi+10h]
0x18011f321  call    ?InternalRelease@?$ComPtr@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::InternalRelease(void)
0x18011f326  lea     r8, [rsi+10h]
0x18011f32a  lea     rdx, _GUID_e6466e9a_b2f3_47c5_b88d_89bc14a8d998
0x18011f331  mov     rcx, rdi
0x18011f334  mov     rax, rbx
0x18011f337  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011f33c  mov     ebx, eax
0x18011f33e  test    eax, eax
0x18011f340  jns     short loc_18011F34C
0x18011f342  mov     edx, 2B8h
0x18011f347  jmp     loc_18011F294
0x18011f34c  mov     [rsp+70h+dwCapabilities], 20h ; ' '; dwCapabilities
0x18011f354  mov     [rsp+70h+pAuthInfo], r12; pAuthInfo
0x18011f359  mov     [rsp+70h+dwImpLevel], 2; dwImpLevel
0x18011f361  mov     dword ptr [rsp+70h+ppv], r12d; dwAuthnLevel
0x18011f366  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x18011f36a  mov     r8d, r13d; dwAuthzSvc
0x18011f36d  mov     edx, r13d; dwAuthnSvc
0x18011f370  mov     rcx, [rsi+10h]; pProxy
0x18011f374  call    cs:__imp_CoSetProxyBlanket
0x18011f37a  mov     ebx, eax
0x18011f37c  test    eax, eax
0x18011f37e  jns     short loc_18011F3C7
0x18011f380  mov     edx, 2BBh
0x18011f385  jmp     loc_18011F294
0x18011f38a  mov     [rsp+70h+dwCapabilities], 20h ; ' '; dwCapabilities
0x18011f392  mov     [rsp+70h+pAuthInfo], r12; pAuthInfo
0x18011f397  mov     [rsp+70h+dwImpLevel], 2; dwImpLevel
0x18011f39f  mov     dword ptr [rsp+70h+ppv], r12d; dwAuthnLevel
0x18011f3a4  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x18011f3a8  mov     r8d, r13d; dwAuthzSvc
0x18011f3ab  mov     edx, r13d; dwAuthnSvc
0x18011f3ae  mov     rcx, [r15]; pProxy
0x18011f3b1  call    cs:__imp_CoSetProxyBlanket
0x18011f3b7  mov     ebx, eax
0x18011f3b9  test    eax, eax
0x18011f3bb  jns     short loc_18011F3C7
0x18011f3bd  mov     edx, 2C1h
0x18011f3c2  jmp     loc_18011F294
0x18011f3c7  mov     ebx, r12d
0x18011f3ca  lea     rcx, [rbp+var_30]
0x18011f3ce  call    ?InternalRelease@?$ComPtr@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::InternalRelease(void)
0x18011f3d3  mov     eax, ebx
0x18011f3d5  mov     rcx, [rbp+var_8]
0x18011f3d9  xor     rcx, rsp; StackCookie
0x18011f3dc  call    __security_check_cookie
0x18011f3e1  mov     rbx, [rsp+70h+arg_10]
0x18011f3e9  add     rsp, 70h
0x18011f3ed  pop     r15
0x18011f3ef  pop     r14
0x18011f3f1  pop     r13
0x18011f3f3  pop     r12
0x18011f3f5  pop     rdi
0x18011f3f6  pop     rsi
0x18011f3f7  pop     rbp
0x18011f3f8  retn
```
