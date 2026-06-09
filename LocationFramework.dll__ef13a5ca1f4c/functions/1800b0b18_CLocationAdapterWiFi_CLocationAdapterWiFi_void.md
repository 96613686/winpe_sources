# CLocationAdapterWiFi::~CLocationAdapterWiFi(void)

- ea: `0x1800b0b18`
- end: `0x1800b0b91`
- name: `??1CLocationAdapterWiFi@@QEAA@XZ`
- size: `121`
- prototype: `void __fastcall(CLocationAdapterWiFi *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800af190`
- `0x1800afd54`

## callees

- `0x180015cfc`
- `0x180021450`
- `0x180023e34`
- `0x180039390`
- `0x18003f3c8`
- `0x180049994`
- `0x1800b0b18`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800b0b45`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800b0b6a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800b0b74`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800b0b45`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800b0b6a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800b0b74`

## pseudocode

```c
void __fastcall CLocationAdapterWiFi::~CLocationAdapterWiFi(CLocationAdapterWiFi *this)
{
  std::_Ref_count_base *v2; // rcx

  v2 = (std::_Ref_count_base *)*((_QWORD *)this + 53);
  if ( v2 )
    std::_Ref_count_base::_Decref(v2);
  std::vector<WifiBssidData>::_Tidy((char *)this + 392);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 344));
  std::_Tree<std::_Tmap_traits<enum PowerState,unsigned long,std::less<enum PowerState>,std::allocator<std::pair<enum PowerState const,unsigned long>>,0>>::~_Tree<std::_Tmap_traits<enum PowerState,unsigned long,std::less<enum PowerState>,std::allocator<std::pair<enum PowerState const,unsigned long>>,0>>((char *)this + 288);
  std::_Tree<std::_Tset_traits<ATL::CAdapt<ATL::CComPtr<IWiFiConnectionStateNotificationSink>>,std::less<ATL::CAdapt<ATL::CComPtr<IWiFiConnectionStateNotificationSink>>>,std::allocator<ATL::CAdapt<ATL::CComPtr<IWiFiConnectionStateNotificationSink>>>,0>>::~_Tree<std::_Tset_traits<ATL::CAdapt<ATL::CComPtr<IWiFiConnectionStateNotificationSink>>,std::less<ATL::CAdapt<ATL::CComPtr<IWiFiConnectionStateNotificationSink>>>,std::allocator<ATL::CAdapt<ATL::CComPtr<IWiFiConnectionStateNotificationSink>>>,0>>((char *)this + 232);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 128));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  std::_Tree<std::_Tset_traits<ATL::CAdapt<ATL::CComPtr<ILocationAdapterWiFiSink>>,std::less<ATL::CAdapt<ATL::CComPtr<ILocationAdapterWiFiSink>>>,std::allocator<ATL::CAdapt<ATL::CComPtr<ILocationAdapterWiFiSink>>>,0>>::~_Tree<std::_Tset_traits<ATL::CAdapt<ATL::CComPtr<ILocationAdapterWiFiSink>>,std::less<ATL::CAdapt<ATL::CComPtr<ILocationAdapterWiFiSink>>>,std::allocator<ATL::CAdapt<ATL::CComPtr<ILocationAdapterWiFiSink>>>,0>>((char *)this + 72);
  ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>((char *)this + 16);
}

```

## disassembly

```asm
0x1800b0b18  push    rbx
0x1800b0b1a  sub     rsp, 20h
0x1800b0b1e  mov     rbx, rcx
0x1800b0b21  mov     rcx, [rcx+1A8h]; this
0x1800b0b28  test    rcx, rcx
0x1800b0b2b  jz      short loc_1800B0B32
0x1800b0b2d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800b0b32  lea     rcx, [rbx+188h]
0x1800b0b39  call    ?_Tidy@?$vector@UWifiBssidData@@V?$allocator@UWifiBssidData@@@std@@@std@@AEAAXXZ; std::vector<WifiBssidData>::_Tidy(void)
0x1800b0b3e  lea     rcx, [rbx+158h]; lpCriticalSection
0x1800b0b45  call    cs:__imp_DeleteCriticalSection
0x1800b0b4b  lea     rcx, [rbx+120h]
0x1800b0b52  call    ??1?$_Tree@V?$_Tmap_traits@W4PowerState@@KU?$less@W4PowerState@@@std@@V?$allocator@U?$pair@$$CBW4PowerState@@K@std@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<PowerState,ulong,std::less<PowerState>,std::allocator<std::pair<PowerState const,ulong>>,0>>::~_Tree<std::_Tmap_traits<PowerState,ulong,std::less<PowerState>,std::allocator<std::pair<PowerState const,ulong>>,0>>(void)
0x1800b0b57  lea     rcx, [rbx+0E8h]
0x1800b0b5e  call    ??1?$_Tree@V?$_Tset_traits@V?$CAdapt@V?$CComPtr@UIWiFiConnectionStateNotificationSink@@@ATL@@@ATL@@U?$less@V?$CAdapt@V?$CComPtr@UIWiFiConnectionStateNotificationSink@@@ATL@@@ATL@@@std@@V?$allocator@V?$CAdapt@V?$CComPtr@UIWiFiConnectionStateNotificationSink@@@ATL@@@ATL@@@4@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<ATL::CAdapt<ATL::CComPtr<IWiFiConnectionStateNotificationSink>>,std::less<ATL::CAdapt<ATL::CComPtr<IWiFiConnectionStateNotificationSink>>>,std::allocator<ATL::CAdapt<ATL::CComPtr<IWiFiConnectionStateNotificationSink>>>,0>>::~_Tree<std::_Tset_traits<ATL::CAdapt<ATL::CComPtr<IWiFiConnectionStateNotificationSink>>,std::less<ATL::CAdapt<ATL::CComPtr<IWiFiConnectionStateNotificationSink>>>,std::allocator<ATL::CAdapt<ATL::CComPtr<IWiFiConnectionStateNotificationSink>>>,0>>(void)
0x1800b0b63  lea     rcx, [rbx+80h]; lpCriticalSection
0x1800b0b6a  call    cs:__imp_DeleteCriticalSection
0x1800b0b70  lea     rcx, [rbx+58h]; lpCriticalSection
0x1800b0b74  call    cs:__imp_DeleteCriticalSection
0x1800b0b7a  lea     rcx, [rbx+48h]
0x1800b0b7e  call    ??1?$_Tree@V?$_Tset_traits@V?$CAdapt@V?$CComPtr@UILocationAdapterWiFiSink@@@ATL@@@ATL@@U?$less@V?$CAdapt@V?$CComPtr@UILocationAdapterWiFiSink@@@ATL@@@ATL@@@std@@V?$allocator@V?$CAdapt@V?$CComPtr@UILocationAdapterWiFiSink@@@ATL@@@ATL@@@4@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<ATL::CAdapt<ATL::CComPtr<ILocationAdapterWiFiSink>>,std::less<ATL::CAdapt<ATL::CComPtr<ILocationAdapterWiFiSink>>>,std::allocator<ATL::CAdapt<ATL::CComPtr<ILocationAdapterWiFiSink>>>,0>>::~_Tree<std::_Tset_traits<ATL::CAdapt<ATL::CComPtr<ILocationAdapterWiFiSink>>,std::less<ATL::CAdapt<ATL::CComPtr<ILocationAdapterWiFiSink>>>,std::allocator<ATL::CAdapt<ATL::CComPtr<ILocationAdapterWiFiSink>>>,0>>(void)
0x1800b0b83  lea     rcx, [rbx+10h]
0x1800b0b87  add     rsp, 20h
0x1800b0b8b  pop     rbx
0x1800b0b8c  jmp     ??1?$CComObjectRootEx@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>(void)
```
