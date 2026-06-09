# CLocationProviderComposite::~CLocationProviderComposite(void)

- ea: `0x1800b0d78`
- end: `0x1800b0e17`
- name: `??1CLocationProviderComposite@@UEAA@XZ`
- size: `159`
- prototype: `void __fastcall(CLocationProviderComposite *__hidden this)`
- caller_count: `3`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800af4c0`
- `0x1800b0070`
- `0x1800b2030`

## callees

- `0x1800143c4`
- `0x18001598c`
- `0x180015cfc`
- `0x1800831e0`
- `0x180084374`
- `0x180084464`
- `0x180085934`
- `0x1800b0398`
- `0x1800b104c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800b0d94`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800b0dd6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800b0de3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800b0d94`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800b0dd6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800b0de3`

## pseudocode

```c
void __fastcall CLocationProviderComposite::~CLocationProviderComposite(CLocationProviderComposite *this)
{
  __int64 v2; // rcx

  Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageSession>::InternalRelease((char *)this + 672);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 632));
  std::_List_node<ATL::CAdapt<ATL::CComPtr<IWindowsActionDialog>>,void *>::_Free_non_head<std::allocator<std::_List_node<ATL::CAdapt<ATL::CComPtr<IWindowsActionDialog>>,void *>>>(
    v2,
    *((_QWORD ***)this + 77));
  std::_Deallocate<16>(*((void **)this + 77), 0x18u);
  CLocationWorkQueue_Impl<0>::~CLocationWorkQueue_Impl<0>((char *)this + 360);
  CSpeedEstimator::~CSpeedEstimator((CLocationProviderComposite *)((char *)this + 248));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 208));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 168));
  std::_Tree<std::_Tmap_traits<enum LOCATION_POSITIONINGENGINE,__MIDL___MIDL_itf_compositepe_0000_0000_0003,std::less<enum LOCATION_POSITIONINGENGINE>,std::allocator<std::pair<enum LOCATION_POSITIONINGENGINE const,__MIDL___MIDL_itf_compositepe_0000_0000_0003>>,0>>::~_Tree<std::_Tmap_traits<enum LOCATION_POSITIONINGENGINE,__MIDL___MIDL_itf_compositepe_0000_0000_0003,std::less<enum LOCATION_POSITIONINGENGINE>,std::allocator<std::pair<enum LOCATION_POSITIONINGENGINE const,__MIDL___MIDL_itf_compositepe_0000_0000_0003>>,0>>((char *)this + 144);
  std::_Tree<std::_Tmap_traits<enum LOCATION_POSITIONINGENGINE,__MIDL___MIDL_itf_compositepe_0000_0000_0002,std::less<enum LOCATION_POSITIONINGENGINE>,std::allocator<std::pair<enum LOCATION_POSITIONINGENGINE const,__MIDL___MIDL_itf_compositepe_0000_0000_0002>>,0>>::~_Tree<std::_Tmap_traits<enum LOCATION_POSITIONINGENGINE,__MIDL___MIDL_itf_compositepe_0000_0000_0002,std::less<enum LOCATION_POSITIONINGENGINE>,std::allocator<std::pair<enum LOCATION_POSITIONINGENGINE const,__MIDL___MIDL_itf_compositepe_0000_0000_0002>>,0>>((char *)this + 128);
  CLocationProviderTemplate<ILocationProviderWiFi,3>::~CLocationProviderTemplate<ILocationProviderWiFi,3>(this);
  ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>((char *)this + 72);
}

```

## disassembly

```asm
0x1800b0d78  push    rbx
0x1800b0d7a  sub     rsp, 20h
0x1800b0d7e  mov     rbx, rcx
0x1800b0d81  add     rcx, 2A0h
0x1800b0d88  call    ?InternalRelease@?$ComPtr@UICapabilityUsageSession@Management@CapabilityAccess@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageSession>::InternalRelease(void)
0x1800b0d8d  lea     rcx, [rbx+278h]; lpCriticalSection
0x1800b0d94  call    cs:__imp_DeleteCriticalSection
0x1800b0d9a  mov     rdx, [rbx+268h]
0x1800b0da1  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$CAdapt@V?$CComPtr@UIWindowsActionDialog@@@ATL@@@ATL@@PEAX@std@@@std@@@?$_List_node@V?$CAdapt@V?$CComPtr@UIWindowsActionDialog@@@ATL@@@ATL@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$CAdapt@V?$CComPtr@UIWindowsActionDialog@@@ATL@@@ATL@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<ATL::CAdapt<ATL::CComPtr<IWindowsActionDialog>>,void *>::_Free_non_head<std::allocator<std::_List_node<ATL::CAdapt<ATL::CComPtr<IWindowsActionDialog>>,void *>>>(std::allocator<std::_List_node<ATL::CAdapt<ATL::CComPtr<IWindowsActionDialog>>,void *>> &,std::_List_node<ATL::CAdapt<ATL::CComPtr<IWindowsActionDialog>>,void *> *)
0x1800b0da6  mov     rcx, [rbx+268h]
0x1800b0dad  mov     edx, 18h
0x1800b0db2  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800b0db7  lea     rcx, [rbx+168h]
0x1800b0dbe  call    ??1?$CLocationWorkQueue_Impl@$0A@@@UEAA@XZ; CLocationWorkQueue_Impl<0>::~CLocationWorkQueue_Impl<0>(void)
0x1800b0dc3  lea     rcx, [rbx+0F8h]; this
0x1800b0dca  call    ??1CSpeedEstimator@@UEAA@XZ; CSpeedEstimator::~CSpeedEstimator(void)
0x1800b0dcf  lea     rcx, [rbx+0D0h]; lpCriticalSection
0x1800b0dd6  call    cs:__imp_DeleteCriticalSection
0x1800b0ddc  lea     rcx, [rbx+0A8h]; lpCriticalSection
0x1800b0de3  call    cs:__imp_DeleteCriticalSection
0x1800b0de9  lea     rcx, [rbx+90h]
0x1800b0df0  call    ??1?$_Tree@V?$_Tmap_traits@W4LOCATION_POSITIONINGENGINE@@U__MIDL___MIDL_itf_compositepe_0000_0000_0003@@U?$less@W4LOCATION_POSITIONINGENGINE@@@std@@V?$allocator@U?$pair@$$CBW4LOCATION_POSITIONINGENGINE@@U__MIDL___MIDL_itf_compositepe_0000_0000_0003@@@std@@@4@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<LOCATION_POSITIONINGENGINE,__MIDL___MIDL_itf_compositepe_0000_0000_0003,std::less<LOCATION_POSITIONINGENGINE>,std::allocator<std::pair<LOCATION_POSITIONINGENGINE const,__MIDL___MIDL_itf_compositepe_0000_0000_0003>>,0>>::~_Tree<std::_Tmap_traits<LOCATION_POSITIONINGENGINE,__MIDL___MIDL_itf_compositepe_0000_0000_0003,std::less<LOCATION_POSITIONINGENGINE>,std::allocator<std::pair<LOCATION_POSITIONINGENGINE const,__MIDL___MIDL_itf_compositepe_0000_0000_0003>>,0>>(void)
0x1800b0df5  lea     rcx, [rbx+80h]
0x1800b0dfc  call    ??1?$_Tree@V?$_Tmap_traits@W4LOCATION_POSITIONINGENGINE@@U__MIDL___MIDL_itf_compositepe_0000_0000_0002@@U?$less@W4LOCATION_POSITIONINGENGINE@@@std@@V?$allocator@U?$pair@$$CBW4LOCATION_POSITIONINGENGINE@@U__MIDL___MIDL_itf_compositepe_0000_0000_0002@@@std@@@4@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<LOCATION_POSITIONINGENGINE,__MIDL___MIDL_itf_compositepe_0000_0000_0002,std::less<LOCATION_POSITIONINGENGINE>,std::allocator<std::pair<LOCATION_POSITIONINGENGINE const,__MIDL___MIDL_itf_compositepe_0000_0000_0002>>,0>>::~_Tree<std::_Tmap_traits<LOCATION_POSITIONINGENGINE,__MIDL___MIDL_itf_compositepe_0000_0000_0002,std::less<LOCATION_POSITIONINGENGINE>,std::allocator<std::pair<LOCATION_POSITIONINGENGINE const,__MIDL___MIDL_itf_compositepe_0000_0000_0002>>,0>>(void)
0x1800b0e01  mov     rcx, rbx
0x1800b0e04  call    ??1?$CLocationProviderTemplate@UILocationProviderWiFi@@$02@@UEAA@XZ; CLocationProviderTemplate<ILocationProviderWiFi,3>::~CLocationProviderTemplate<ILocationProviderWiFi,3>(void)
0x1800b0e09  lea     rcx, [rbx+48h]
0x1800b0e0d  add     rsp, 20h
0x1800b0e11  pop     rbx
0x1800b0e12  jmp     ??1?$CComObjectRootEx@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>(void)
```
