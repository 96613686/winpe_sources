# UiaManagerImpl::~UiaManagerImpl(void)

- ea: `0x18001a5e0`
- end: `0x18001a66d`
- name: `??1UiaManagerImpl@@UEAA@XZ`
- size: `141`
- prototype: `void __fastcall(UiaManagerImpl *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180073a60`

## callees

- `0x1800054f8`
- `0x180007344`
- `0x18001a5e0`
- `0x18001a674`
- `0x18001a6d0`
- `0x18001a72c`
- `0x18001a788`
- `0x18001a7e4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001a60d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001a60d`

## pseudocode

```c
void __fastcall UiaManagerImpl::~UiaManagerImpl(UiaManagerImpl *this)
{
  std::_Ref_count_base *v2; // rcx

  v2 = (std::_Ref_count_base *)*((_QWORD *)this + 118);
  if ( v2 )
    std::_Ref_count_base::_Decref(v2);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 848);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 808));
  std::_Hash<std::_Umap_traits<_GUID,wil::com_ptr_t<IUiaCrossMachineServices,wil::err_exception_policy>,std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,wil::com_ptr_t<IUiaCrossMachineServices,wil::err_exception_policy>>>,0>>::~_Hash<std::_Umap_traits<_GUID,wil::com_ptr_t<IUiaCrossMachineServices,wil::err_exception_policy>,std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,wil::com_ptr_t<IUiaCrossMachineServices,wil::err_exception_policy>>>,0>>((char *)this + 744);
  std::_Hash<std::_Umap_traits<std::pair<_GUID,HWND__ *>,std::optional<ProviderEntrypointId>,std::_Uhash_compare<std::pair<_GUID,HWND__ *>,std::hash<std::pair<_GUID,HWND__ *>>,std::equal_to<std::pair<_GUID,HWND__ *>>>,std::allocator<std::pair<std::pair<_GUID,HWND__ *> const,std::optional<ProviderEntrypointId>>>,0>>::~_Hash<std::_Umap_traits<std::pair<_GUID,HWND__ *>,std::optional<ProviderEntrypointId>,std::_Uhash_compare<std::pair<_GUID,HWND__ *>,std::hash<std::pair<_GUID,HWND__ *>>,std::equal_to<std::pair<_GUID,HWND__ *>>>,std::allocator<std::pair<std::pair<_GUID,HWND__ *> const,std::optional<ProviderEntrypointId>>>,0>>((char *)this + 600);
  std::_Hash<std::_Umap_traits<_GUID,std::optional<ProviderEntrypointId>,std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,std::optional<ProviderEntrypointId>>>,0>>::~_Hash<std::_Umap_traits<_GUID,std::optional<ProviderEntrypointId>,std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,std::optional<ProviderEntrypointId>>>,0>>((char *)this + 456);
  std::_Hash<std::_Umap_traits<_GUID,wil::com_ptr_t<IUiaManagerCrossMachineConnection,wil::err_exception_policy>,std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,wil::com_ptr_t<IUiaManagerCrossMachineConnection,wil::err_exception_policy>>>,0>>::~_Hash<std::_Umap_traits<_GUID,wil::com_ptr_t<IUiaManagerCrossMachineConnection,wil::err_exception_policy>,std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,wil::com_ptr_t<IUiaManagerCrossMachineConnection,wil::err_exception_policy>>>,0>>((char *)this + 312);
  std::_Hash<std::_Umap_traits<unsigned int,wil::com_ptr_t<IWeakReference,wil::err_exception_policy>,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,wil::com_ptr_t<IWeakReference,wil::err_exception_policy>>>,0>>::~_Hash<std::_Umap_traits<unsigned int,wil::com_ptr_t<IWeakReference,wil::err_exception_policy>,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,wil::com_ptr_t<IWeakReference,wil::err_exception_policy>>>,0>>((char *)this + 168);
  std::_Hash<std::_Umap_traits<unsigned int,wil::com_ptr_t<IWeakReference,wil::err_exception_policy>,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,wil::com_ptr_t<IWeakReference,wil::err_exception_policy>>>,0>>::~_Hash<std::_Umap_traits<unsigned int,wil::com_ptr_t<IWeakReference,wil::err_exception_policy>,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,wil::com_ptr_t<IWeakReference,wil::err_exception_policy>>>,0>>((char *)this + 104);
  *((_DWORD *)this + 25) = -1073741823;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 24);
}

```

## disassembly

```asm
0x18001a5e0  push    rbx
0x18001a5e2  sub     rsp, 20h
0x18001a5e6  mov     rbx, rcx
0x18001a5e9  mov     rcx, [rcx+3B0h]; this
0x18001a5f0  test    rcx, rcx
0x18001a5f3  jz      short loc_18001A5FA
0x18001a5f5  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001a5fa  lea     rcx, [rbx+350h]
0x18001a601  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001a606  lea     rcx, [rbx+328h]; lpCriticalSection
0x18001a60d  call    cs:__imp_DeleteCriticalSection
0x18001a613  lea     rcx, [rbx+2E8h]
0x18001a61a  call    ??1?$_Hash@V?$_Umap_traits@U_GUID@@V?$com_ptr_t@UIUiaCrossMachineServices@@Uerr_exception_policy@wil@@@wil@@V?$_Uhash_compare@U_GUID@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@3@@std@@V?$allocator@U?$pair@$$CBU_GUID@@V?$com_ptr_t@UIUiaCrossMachineServices@@Uerr_exception_policy@wil@@@wil@@@std@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<_GUID,wil::com_ptr_t<IUiaCrossMachineServices,wil::err_exception_policy>,std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,wil::com_ptr_t<IUiaCrossMachineServices,wil::err_exception_policy>>>,0>>::~_Hash<std::_Umap_traits<_GUID,wil::com_ptr_t<IUiaCrossMachineServices,wil::err_exception_policy>,std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,wil::com_ptr_t<IUiaCrossMachineServices,wil::err_exception_policy>>>,0>>(void)
0x18001a61f  lea     rcx, [rbx+258h]
0x18001a626  call    ??1?$_Hash@V?$_Umap_traits@U?$pair@U_GUID@@PEAUHWND__@@@std@@V?$optional@VProviderEntrypointId@@@2@V?$_Uhash_compare@U?$pair@U_GUID@@PEAUHWND__@@@std@@U?$hash@U?$pair@U_GUID@@PEAUHWND__@@@std@@@2@U?$equal_to@U?$pair@U_GUID@@PEAUHWND__@@@std@@@2@@2@V?$allocator@U?$pair@$$CBU?$pair@U_GUID@@PEAUHWND__@@@std@@V?$optional@VProviderEntrypointId@@@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::pair<_GUID,HWND__ *>,std::optional<ProviderEntrypointId>,std::_Uhash_compare<std::pair<_GUID,HWND__ *>,std::hash<std::pair<_GUID,HWND__ *>>,std::equal_to<std::pair<_GUID,HWND__ *>>>,std::allocator<std::pair<std::pair<_GUID,HWND__ *> const,std::optional<ProviderEntrypointId>>>,0>>::~_Hash<std::_Umap_traits<std::pair<_GUID,HWND__ *>,std::optional<ProviderEntrypointId>,std::_Uhash_compare<std::pair<_GUID,HWND__ *>,std::hash<std::pair<_GUID,HWND__ *>>,std::equal_to<std::pair<_GUID,HWND__ *>>>,std::allocator<std::pair<std::pair<_GUID,HWND__ *> const,std::optional<ProviderEntrypointId>>>,0>>(void)
0x18001a62b  lea     rcx, [rbx+1C8h]
0x18001a632  call    ??1?$_Hash@V?$_Umap_traits@U_GUID@@V?$optional@VProviderEntrypointId@@@std@@V?$_Uhash_compare@U_GUID@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@3@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$optional@VProviderEntrypointId@@@std@@@std@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<_GUID,std::optional<ProviderEntrypointId>,std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,std::optional<ProviderEntrypointId>>>,0>>::~_Hash<std::_Umap_traits<_GUID,std::optional<ProviderEntrypointId>,std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,std::optional<ProviderEntrypointId>>>,0>>(void)
0x18001a637  lea     rcx, [rbx+138h]
0x18001a63e  call    ??1?$_Hash@V?$_Umap_traits@U_GUID@@V?$com_ptr_t@UIUiaManagerCrossMachineConnection@@Uerr_exception_policy@wil@@@wil@@V?$_Uhash_compare@U_GUID@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@3@@std@@V?$allocator@U?$pair@$$CBU_GUID@@V?$com_ptr_t@UIUiaManagerCrossMachineConnection@@Uerr_exception_policy@wil@@@wil@@@std@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<_GUID,wil::com_ptr_t<IUiaManagerCrossMachineConnection,wil::err_exception_policy>,std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,wil::com_ptr_t<IUiaManagerCrossMachineConnection,wil::err_exception_policy>>>,0>>::~_Hash<std::_Umap_traits<_GUID,wil::com_ptr_t<IUiaManagerCrossMachineConnection,wil::err_exception_policy>,std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,wil::com_ptr_t<IUiaManagerCrossMachineConnection,wil::err_exception_policy>>>,0>>(void)
0x18001a643  lea     rcx, [rbx+0A8h]
0x18001a64a  call    ??1?$_Hash@V?$_Umap_traits@IV?$com_ptr_t@UIWeakReference@@Uerr_exception_policy@wil@@@wil@@V?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@std@@V?$allocator@U?$pair@$$CBIV?$com_ptr_t@UIWeakReference@@Uerr_exception_policy@wil@@@wil@@@std@@@4@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<uint,wil::com_ptr_t<IWeakReference,wil::err_exception_policy>,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<std::pair<uint const,wil::com_ptr_t<IWeakReference,wil::err_exception_policy>>>,0>>::~_Hash<std::_Umap_traits<uint,wil::com_ptr_t<IWeakReference,wil::err_exception_policy>,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<std::pair<uint const,wil::com_ptr_t<IWeakReference,wil::err_exception_policy>>>,0>>(void)
0x18001a64f  lea     rcx, [rbx+68h]
0x18001a653  call    ??1?$_Hash@V?$_Umap_traits@IV?$com_ptr_t@UIWeakReference@@Uerr_exception_policy@wil@@@wil@@V?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@std@@V?$allocator@U?$pair@$$CBIV?$com_ptr_t@UIWeakReference@@Uerr_exception_policy@wil@@@wil@@@std@@@4@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<uint,wil::com_ptr_t<IWeakReference,wil::err_exception_policy>,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<std::pair<uint const,wil::com_ptr_t<IWeakReference,wil::err_exception_policy>>>,0>>::~_Hash<std::_Umap_traits<uint,wil::com_ptr_t<IWeakReference,wil::err_exception_policy>,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<std::pair<uint const,wil::com_ptr_t<IWeakReference,wil::err_exception_policy>>>,0>>(void)
0x18001a658  lea     rcx, [rbx+18h]
0x18001a65c  mov     dword ptr [rbx+64h], 0C0000001h
0x18001a663  add     rsp, 20h
0x18001a667  pop     rbx
0x18001a668  jmp     ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
```
