# CLocationSession::~CLocationSession(void)

- ea: `0x180050990`
- end: `0x180050aac`
- name: `??1CLocationSession@@QEAA@XZ`
- size: `284`
- prototype: `void __fastcall(CLocationSession *__hidden this)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005091c`
- `0x1800af688`

## callees

- `0x180012398`
- `0x1800143c4`
- `0x18001598c`
- `0x180015cfc`
- `0x18001cd38`
- `0x18001efe0`
- `0x180020164`
- `0x180021450`
- `0x180050990`
- `0x180068960`
- `0x1800831b0`
- `0x1800831e0`
- `0x1800e9204`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800509b1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180050a32`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180050a3f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180050a4c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180050a59`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800509b1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180050a32`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180050a3f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180050a4c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180050a59`
- `OLEAUT32!__imp_SysFreeString` at `0x180050a98`
- `OLEAUT32!__imp_SysFreeString` at `0x180050a98`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CLocationSession::~CLocationSession(CLocationSession *this)
{
  std::_Ref_count_base *v2; // rcx
  __int64 v3; // rcx

  CLocationSession::Dispose(this);
  std::_Tree<std::_Tmap_traits<enum LOCATION_POSITIONINGENGINE,std::pair<POSITIONINFO_COORDINATE,POSITIONINFO_STATUS>,std::less<enum LOCATION_POSITIONINGENGINE>,std::allocator<std::pair<enum LOCATION_POSITIONINGENGINE const,std::pair<POSITIONINFO_COORDINATE,POSITIONINFO_STATUS>>>,0>>::~_Tree<std::_Tmap_traits<enum LOCATION_POSITIONINGENGINE,std::pair<POSITIONINFO_COORDINATE,POSITIONINFO_STATUS>,std::less<enum LOCATION_POSITIONINGENGINE>,std::allocator<std::pair<enum LOCATION_POSITIONINGENGINE const,std::pair<POSITIONINFO_COORDINATE,POSITIONINFO_STATUS>>>,0>>((char *)this + 1120);
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 27);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((char *)this + 1064);
  LocationWnfSubscribe_Impl::~LocationWnfSubscribe_Impl((CLocationSession *)((char *)this + 1008));
  Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageSession>::InternalRelease((char *)this + 1000);
  v2 = (std::_Ref_count_base *)*((_QWORD *)this + 124);
  if ( v2 )
    std::_Ref_count_base::_Decref(v2);
  DynamicPrivilegeCookie::Uninitialize((CLocationSession *)((char *)this + 968));
  DynamicPrivilegeCookie::Uninitialize((CLocationSession *)((char *)this + 960));
  LOCATION_APISESSIONINFO::~LOCATION_APISESSIONINFO((CLocationSession *)((char *)this + 648));
  ATL::CSid::~CSid((CLocationSession *)((char *)this + 504));
  ATL::CSid::~CSid((CLocationSession *)((char *)this + 384));
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 8);
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 7);
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 6);
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 5);
  std::_List_node<ATL::CAdapt<ATL::CComPtr<IWindowsActionDialog>>,void *>::_Free_non_head<std::allocator<std::_List_node<ATL::CAdapt<ATL::CComPtr<IWindowsActionDialog>>,void *>>>(
    v3,
    *((_QWORD ***)this + 23));
  std::_Deallocate<16>(*((void **)this + 23), 0x18u);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((char *)this + 176);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((char *)this + 152);
  SysFreeString(*((BSTR *)this + 13));
  ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>((char *)this + 24);
}

```

## disassembly

```asm
0x180050990  push    rbx
0x180050992  sub     rsp, 20h
0x180050996  mov     rbx, rcx
0x180050999  call    ?Dispose@CLocationSession@@UEAAJXZ; CLocationSession::Dispose(void)
0x18005099e  lea     rcx, [rbx+460h]
0x1800509a5  call    ??1?$_Tree@V?$_Tmap_traits@W4LOCATION_POSITIONINGENGINE@@U?$pair@UPOSITIONINFO_COORDINATE@@UPOSITIONINFO_STATUS@@@std@@U?$less@W4LOCATION_POSITIONINGENGINE@@@3@V?$allocator@U?$pair@$$CBW4LOCATION_POSITIONINGENGINE@@U?$pair@UPOSITIONINFO_COORDINATE@@UPOSITIONINFO_STATUS@@@std@@@std@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<LOCATION_POSITIONINGENGINE,std::pair<POSITIONINFO_COORDINATE,POSITIONINFO_STATUS>,std::less<LOCATION_POSITIONINGENGINE>,std::allocator<std::pair<LOCATION_POSITIONINGENGINE const,std::pair<POSITIONINFO_COORDINATE,POSITIONINFO_STATUS>>>,0>>::~_Tree<std::_Tmap_traits<LOCATION_POSITIONINGENGINE,std::pair<POSITIONINFO_COORDINATE,POSITIONINFO_STATUS>,std::less<LOCATION_POSITIONINGENGINE>,std::allocator<std::pair<LOCATION_POSITIONINGENGINE const,std::pair<POSITIONINFO_COORDINATE,POSITIONINFO_STATUS>>>,0>>(void)
0x1800509aa  lea     rcx, [rbx+438h]; lpCriticalSection
0x1800509b1  call    cs:__imp_DeleteCriticalSection
0x1800509b7  lea     rcx, [rbx+428h]
0x1800509be  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800509c3  lea     rcx, [rbx+3F0h]; this
0x1800509ca  call    ??1LocationWnfSubscribe_Impl@@UEAA@XZ; LocationWnfSubscribe_Impl::~LocationWnfSubscribe_Impl(void)
0x1800509cf  lea     rcx, [rbx+3E8h]
0x1800509d6  call    ?InternalRelease@?$ComPtr@UICapabilityUsageSession@Management@CapabilityAccess@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageSession>::InternalRelease(void)
0x1800509db  mov     rcx, [rbx+3E0h]; this
0x1800509e2  test    rcx, rcx
0x1800509e5  jz      short loc_1800509ED
0x1800509e7  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800509ec  nop
0x1800509ed  lea     rcx, [rbx+3C8h]; this
0x1800509f4  call    ?Uninitialize@DynamicPrivilegeCookie@@QEAAJXZ; DynamicPrivilegeCookie::Uninitialize(void)
0x1800509f9  nop
0x1800509fa  lea     rcx, [rbx+3C0h]; this
0x180050a01  call    ?Uninitialize@DynamicPrivilegeCookie@@QEAAJXZ; DynamicPrivilegeCookie::Uninitialize(void)
0x180050a06  nop
0x180050a07  lea     rcx, [rbx+288h]; this
0x180050a0e  call    ??1LOCATION_APISESSIONINFO@@QEAA@XZ; LOCATION_APISESSIONINFO::~LOCATION_APISESSIONINFO(void)
0x180050a13  lea     rcx, [rbx+1F8h]; this
0x180050a1a  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x180050a1f  lea     rcx, [rbx+180h]; this
0x180050a26  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x180050a2b  lea     rcx, [rbx+140h]; lpCriticalSection
0x180050a32  call    cs:__imp_DeleteCriticalSection
0x180050a38  lea     rcx, [rbx+118h]; lpCriticalSection
0x180050a3f  call    cs:__imp_DeleteCriticalSection
0x180050a45  lea     rcx, [rbx+0F0h]; lpCriticalSection
0x180050a4c  call    cs:__imp_DeleteCriticalSection
0x180050a52  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180050a59  call    cs:__imp_DeleteCriticalSection
0x180050a5f  mov     rdx, [rbx+0B8h]
0x180050a66  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$CAdapt@V?$CComPtr@UIWindowsActionDialog@@@ATL@@@ATL@@PEAX@std@@@std@@@?$_List_node@V?$CAdapt@V?$CComPtr@UIWindowsActionDialog@@@ATL@@@ATL@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$CAdapt@V?$CComPtr@UIWindowsActionDialog@@@ATL@@@ATL@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<ATL::CAdapt<ATL::CComPtr<IWindowsActionDialog>>,void *>::_Free_non_head<std::allocator<std::_List_node<ATL::CAdapt<ATL::CComPtr<IWindowsActionDialog>>,void *>>>(std::allocator<std::_List_node<ATL::CAdapt<ATL::CComPtr<IWindowsActionDialog>>,void *>> &,std::_List_node<ATL::CAdapt<ATL::CComPtr<IWindowsActionDialog>>,void *> *)
0x180050a6b  mov     edx, 18h
0x180050a70  mov     rcx, [rbx+0B8h]
0x180050a77  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180050a7c  lea     rcx, [rbx+0B0h]
0x180050a83  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180050a88  lea     rcx, [rbx+98h]
0x180050a8f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180050a94  mov     rcx, [rbx+68h]; bstrString
0x180050a98  call    cs:__imp_SysFreeString
0x180050a9e  lea     rcx, [rbx+18h]
0x180050aa2  add     rsp, 20h
0x180050aa6  pop     rbx
0x180050aa7  jmp     ??1?$CComObjectRootEx@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>(void)
```
