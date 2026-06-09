# CApplication::~CApplication(void)

- ea: `0x18002e374`
- end: `0x18002e489`
- name: `??1CApplication@@MEAA@XZ`
- size: `277`
- prototype: `void __fastcall(CApplication *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800384e0`

## callees

- `0x18000cd24`
- `0x18001c774`
- `0x18001e600`
- `0x180024a04`
- `0x18002e374`
- `0x18002e490`
- `0x18002e550`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002e3fd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002e40a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002e417`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002e424`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002e431`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002e43e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002e44b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002e467`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002e3fd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002e40a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002e417`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002e424`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002e431`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002e43e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002e44b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002e467`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e476`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e476`

## pseudocode

```c
void __fastcall CApplication::~CApplication(CApplication *this)
{
  __int64 v2; // rdx
  void *v3; // rcx

  *(_QWORD *)this = &CApplication::`vftable';
  v2 = *((_QWORD *)this + 33);
  if ( v2 )
  {
    (*(void (__fastcall **)(struct CAudioThreadPool *, __int64, __int64))(*(_QWORD *)ThreadPool + 32LL))(
      ThreadPool,
      v2,
      1);
    (*(void (__fastcall **)(struct CAudioThreadPool *, _QWORD))(*(_QWORD *)ThreadPool + 16LL))(
      ThreadPool,
      *((_QWORD *)this + 33));
  }
  CApplication::CleanupBCMStartupLatencyGracePeriod(this);
  CApplication::CleanupDelayedInteractivityNotification(this);
  CApplication::CleanupGoodFaithExemptionTimer(this);
  std::_Tree<std::_Tmap_traits<std::wstring,wil::com_ptr_t<IApplicationSpecificEndpointInfo,wil::err_returncode_policy>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<IApplicationSpecificEndpointInfo,wil::err_returncode_policy>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,wil::com_ptr_t<IApplicationSpecificEndpointInfo,wil::err_returncode_policy>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<IApplicationSpecificEndpointInfo,wil::err_returncode_policy>>>,0>>((char *)this + 704);
  std::_Func_class<void,>::~_Func_class<void,>((char *)this + 544);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 496));
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 11);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 384));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 336));
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 7);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 224));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 168));
  ATL::CAtlList<CPickerHostContext *,ATL::CElementTraits<CPickerHostContext *>>::RemoveAll((char *)this + 120);
  ATL::CAtlList<CPickerHostContext *,ATL::CElementTraits<CPickerHostContext *>>::RemoveAll((char *)this + 72);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  v3 = (void *)*((_QWORD *)this + 3);
  if ( v3 )
    CoTaskMemFree(v3);
  *((_DWORD *)this + 3) = -1073741823;
}

```

## disassembly

```asm
0x18002e374  push    rbx
0x18002e376  sub     rsp, 20h
0x18002e37a  mov     rbx, rcx
0x18002e37d  lea     rax, ??_7CApplication@@6B@; const CApplication::`vftable'
0x18002e384  mov     [rcx], rax
0x18002e387  mov     rdx, [rcx+108h]
0x18002e38e  test    rdx, rdx
0x18002e391  jz      short loc_18002E3C6
0x18002e393  mov     rcx, cs:?ThreadPool@@3PEAVCAudioThreadPool@@EA; CAudioThreadPool * ThreadPool
0x18002e39a  mov     rax, [rcx]
0x18002e39d  mov     r8d, 1
0x18002e3a3  mov     rax, [rax+20h]
0x18002e3a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e3ac  mov     rcx, cs:?ThreadPool@@3PEAVCAudioThreadPool@@EA; CAudioThreadPool * ThreadPool
0x18002e3b3  mov     rax, [rcx]
0x18002e3b6  mov     rdx, [rbx+108h]
0x18002e3bd  mov     rax, [rax+10h]
0x18002e3c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e3c6  mov     rcx, rbx; this
0x18002e3c9  call    ?CleanupBCMStartupLatencyGracePeriod@CApplication@@QEAAXXZ; CApplication::CleanupBCMStartupLatencyGracePeriod(void)
0x18002e3ce  mov     rcx, rbx; this
0x18002e3d1  call    ?CleanupDelayedInteractivityNotification@CApplication@@IEAAJXZ; CApplication::CleanupDelayedInteractivityNotification(void)
0x18002e3d6  mov     rcx, rbx; this
0x18002e3d9  call    ?CleanupGoodFaithExemptionTimer@CApplication@@QEAAJXZ; CApplication::CleanupGoodFaithExemptionTimer(void)
0x18002e3de  lea     rcx, [rbx+2C0h]
0x18002e3e5  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$com_ptr_t@UIApplicationSpecificEndpointInfo@@Uerr_returncode_policy@wil@@@wil@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$com_ptr_t@UIApplicationSpecificEndpointInfo@@Uerr_returncode_policy@wil@@@wil@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,wil::com_ptr_t<IApplicationSpecificEndpointInfo,wil::err_returncode_policy>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<IApplicationSpecificEndpointInfo,wil::err_returncode_policy>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,wil::com_ptr_t<IApplicationSpecificEndpointInfo,wil::err_returncode_policy>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,wil::com_ptr_t<IApplicationSpecificEndpointInfo,wil::err_returncode_policy>>>,0>>(void)
0x18002e3ea  lea     rcx, [rbx+220h]
0x18002e3f1  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x18002e3f6  lea     rcx, [rbx+1F0h]; lpCriticalSection
0x18002e3fd  call    cs:__imp_DeleteCriticalSection
0x18002e403  lea     rcx, [rbx+1B8h]; lpCriticalSection
0x18002e40a  call    cs:__imp_DeleteCriticalSection
0x18002e410  lea     rcx, [rbx+180h]; lpCriticalSection
0x18002e417  call    cs:__imp_DeleteCriticalSection
0x18002e41d  lea     rcx, [rbx+150h]; lpCriticalSection
0x18002e424  call    cs:__imp_DeleteCriticalSection
0x18002e42a  lea     rcx, [rbx+118h]; lpCriticalSection
0x18002e431  call    cs:__imp_DeleteCriticalSection
0x18002e437  lea     rcx, [rbx+0E0h]; lpCriticalSection
0x18002e43e  call    cs:__imp_DeleteCriticalSection
0x18002e444  lea     rcx, [rbx+0A8h]; lpCriticalSection
0x18002e44b  call    cs:__imp_DeleteCriticalSection
0x18002e451  lea     rcx, [rbx+78h]
0x18002e455  call    ?RemoveAll@?$CAtlList@PEAVCPickerHostContext@@V?$CElementTraits@PEAVCPickerHostContext@@@ATL@@@ATL@@QEAAXXZ; ATL::CAtlList<CPickerHostContext *,ATL::CElementTraits<CPickerHostContext *>>::RemoveAll(void)
0x18002e45a  lea     rcx, [rbx+48h]
0x18002e45e  call    ?RemoveAll@?$CAtlList@PEAVCPickerHostContext@@V?$CElementTraits@PEAVCPickerHostContext@@@ATL@@@ATL@@QEAAXXZ; ATL::CAtlList<CPickerHostContext *,ATL::CElementTraits<CPickerHostContext *>>::RemoveAll(void)
0x18002e463  lea     rcx, [rbx+20h]; lpCriticalSection
0x18002e467  call    cs:__imp_DeleteCriticalSection
0x18002e46d  mov     rcx, [rbx+18h]; pv
0x18002e471  test    rcx, rcx
0x18002e474  jz      short loc_18002E47C
0x18002e476  call    cs:__imp_CoTaskMemFree
0x18002e47c  mov     dword ptr [rbx+0Ch], 0C0000001h
0x18002e483  add     rsp, 20h
0x18002e487  pop     rbx
0x18002e488  retn
```
