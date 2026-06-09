# UWAInstallWork::~UWAInstallWork(void)

- ea: `0x1800e48a8`
- end: `0x1800e4b03`
- name: `??1UWAInstallWork@@UEAA@XZ`
- size: `603`
- prototype: `void __fastcall(UWAInstallWork *__hidden this)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800e57a0`

## callees

- `0x1800101f4`
- `0x18001bf24`
- `0x18001c964`
- `0x180021e10`
- `0x180021f74`
- `0x180022268`
- `0x1800222d8`
- `0x180022374`
- `0x1800225e4`
- `0x18002d98c`
- `0x180044af8`
- `0x180051818`
- `0x1800df870`
- `0x1800e3f74`
- `0x1800e3fd0`
- `0x1800e40a8`
- `0x1800e48a8`
- `0x1800fea18`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800e4a01`
- `OLEAUT32!__imp_SysFreeString` at `0x1800e4a01`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e4a0e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e4a22`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e4a36`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e4a4a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e4a5e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e4a98`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e4aa6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e4abd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e4acb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e4ad9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e4ae7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e4a0e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e4a22`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e4a36`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e4a4a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e4a5e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e4a98`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e4aa6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e4abd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e4acb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e4ad9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e4ae7`

## pseudocode

```c
void __fastcall UWAInstallWork::~UWAInstallWork(UWAInstallWork *this)
{
  __int64 v2; // rcx
  std::_Ref_count_base *v3; // rcx
  __int64 v4; // rdx

  wistd::unique_ptr<InstallAgentPdcActivation,wistd::default_delete<InstallAgentPdcActivation>>::reset(
    (char *)this + 1280,
    0);
  std::_Tree<std::_Tmap_traits<__int64,__int64,std::less<__int64>,std::allocator<std::pair<__int64 const,__int64>>,0>>::~_Tree<std::_Tmap_traits<__int64,__int64,std::less<__int64>,std::allocator<std::pair<__int64 const,__int64>>,0>>((char *)this + 1256);
  Microsoft::WRL::EventSource<InstallQueue::IProgressEventHandler,Microsoft::WRL::InvokeModeOptions<-2>>::~EventSource<InstallQueue::IProgressEventHandler,Microsoft::WRL::InvokeModeOptions<-2>>((char *)this + 1216);
  v2 = *((_QWORD *)this + 149);
  if ( v2 )
  {
    std::_Destroy_range<std::allocator<UWAInstallWork::TaskProgressInfo>>(v2, *((_QWORD *)this + 150));
    std::_Deallocate<16>(
      *((void **)this + 149),
      (struct std::nothrow_t *)(8 * ((__int64)(*((_QWORD *)this + 151) - *((_QWORD *)this + 149)) >> 3)));
    *((_QWORD *)this + 149) = 0;
    *((_QWORD *)this + 150) = 0;
    *((_QWORD *)this + 151) = 0;
  }
  std::vector<Microsoft::WRL::ComPtr<WindowsUpdate::Internal::FulfillmentDataInfo>>::_Tidy((char *)this + 1168);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease((char *)this + 1160);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease((char *)this + 1152);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease((char *)this + 1144);
  std::wstring::_Tidy_deallocate((char *)this + 1008);
  std::wstring::_Tidy_deallocate((char *)this + 952);
  std::_Hash<std::_Umap_traits<std::wstring,unsigned __int64,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::~_Hash<std::_Umap_traits<std::wstring,unsigned __int64,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>((char *)this + 856);
  std::wstring::_Tidy_deallocate((char *)this + 824);
  std::_Hash<std::_Umap_traits<std::wstring,unsigned __int64,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::~_Hash<std::_Umap_traits<std::wstring,unsigned __int64,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>((char *)this + 760);
  std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>((char *)this + 696);
  std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>((char *)this + 632);
  std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>((char *)this + 616);
  std::vector<std::wstring>::_Tidy((char *)this + 592);
  std::vector<std::wstring>::_Tidy((char *)this + 568);
  std::vector<std::wstring>::_Tidy((char *)this + 536);
  std::vector<std::wstring>::_Tidy((char *)this + 512);
  SysFreeString(*((BSTR *)this + 62));
  WindowsDeleteString(*((HSTRING *)this + 61));
  *((_QWORD *)this + 61) = 0;
  WindowsDeleteString(*((HSTRING *)this + 60));
  *((_QWORD *)this + 60) = 0;
  WindowsDeleteString(*((HSTRING *)this + 59));
  *((_QWORD *)this + 59) = 0;
  WindowsDeleteString(*((HSTRING *)this + 58));
  *((_QWORD *)this + 58) = 0;
  WindowsDeleteString(*((HSTRING *)this + 57));
  *((_QWORD *)this + 57) = 0;
  v3 = (std::_Ref_count_base *)*((_QWORD *)this + 56);
  if ( v3 )
    std::_Ref_count_base::_Decref(v3);
  std::_Temporary_owner<TraceLoggingCorrelationVector>::~_Temporary_owner<TraceLoggingCorrelationVector>((char *)this + 296);
  CallerContext::~CallerContext((UWAInstallWork *)((char *)this + 152));
  WindowsDeleteString(*((HSTRING *)this + 15));
  *((_QWORD *)this + 15) = 0;
  WindowsDeleteString(*((HSTRING *)this + 14));
  *((_QWORD *)this + 14) = 0;
  wil::com_ptr_t<InstallQueue,wil::err_exception_policy>::~com_ptr_t<InstallQueue,wil::err_exception_policy>(
    (char *)this + 104,
    v4);
  WindowsDeleteString(*((HSTRING *)this + 12));
  *((_QWORD *)this + 12) = 0;
  WindowsDeleteString(*((HSTRING *)this + 11));
  *((_QWORD *)this + 11) = 0;
  WindowsDeleteString(*((HSTRING *)this + 10));
  *((_QWORD *)this + 10) = 0;
  WindowsDeleteString(*((HSTRING *)this + 9));
  *((_QWORD *)this + 9) = 0;
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IMapView<HSTRING__ *,Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *>,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IMapView<HSTRING__ *,Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *>,Microsoft::WRL::FtmBase>(this);
}

```

## disassembly

```asm
0x1800e48a8  mov     [rsp+arg_0], rbx
0x1800e48ad  push    rdi
0x1800e48ae  sub     rsp, 20h
0x1800e48b2  mov     rbx, rcx
0x1800e48b5  xor     edx, edx
0x1800e48b7  add     rcx, 500h
0x1800e48be  call    ?reset@?$unique_ptr@VInstallAgentPdcActivation@@U?$default_delete@VInstallAgentPdcActivation@@@wistd@@@wistd@@QEAAXPEAVInstallAgentPdcActivation@@@Z; wistd::unique_ptr<InstallAgentPdcActivation,wistd::default_delete<InstallAgentPdcActivation>>::reset(InstallAgentPdcActivation *)
0x1800e48c3  lea     rcx, [rbx+4E8h]
0x1800e48ca  call    ??1?$_Tree@V?$_Tmap_traits@_J_JU?$less@_J@std@@V?$allocator@U?$pair@$$CB_J_J@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<__int64,__int64,std::less<__int64>,std::allocator<std::pair<__int64 const,__int64>>,0>>::~_Tree<std::_Tmap_traits<__int64,__int64,std::less<__int64>,std::allocator<std::pair<__int64 const,__int64>>,0>>(void)
0x1800e48cf  lea     rcx, [rbx+4C0h]
0x1800e48d6  call    ??1?$EventSource@UIProgressEventHandler@InstallQueue@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::EventSource<InstallQueue::IProgressEventHandler,Microsoft::WRL::InvokeModeOptions<-2>>::~EventSource<InstallQueue::IProgressEventHandler,Microsoft::WRL::InvokeModeOptions<-2>>(void)
0x1800e48db  mov     rcx, [rbx+4A8h]
0x1800e48e2  xor     edi, edi
0x1800e48e4  test    rcx, rcx
0x1800e48e7  jz      short loc_1800E493A
0x1800e48e9  mov     rdx, [rbx+4B0h]
0x1800e48f0  call    ??$_Destroy_range@V?$allocator@UTaskProgressInfo@UWAInstallWork@@@std@@@std@@YAXPEAUTaskProgressInfo@UWAInstallWork@@QEAU12@AEAV?$allocator@UTaskProgressInfo@UWAInstallWork@@@0@@Z; std::_Destroy_range<std::allocator<UWAInstallWork::TaskProgressInfo>>(UWAInstallWork::TaskProgressInfo *,UWAInstallWork::TaskProgressInfo * const,std::allocator<UWAInstallWork::TaskProgressInfo> &)
0x1800e48f5  mov     rcx, [rbx+4A8h]
0x1800e48fc  mov     rdx, 0CCCCCCCCCCCCCCCDh
0x1800e4906  mov     rax, [rbx+4B8h]
0x1800e490d  sub     rax, rcx
0x1800e4910  sar     rax, 3
0x1800e4914  imul    rax, rdx
0x1800e4918  lea     rdx, [rax+rax*4]
0x1800e491c  shl     rdx, 3
0x1800e4920  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800e4925  mov     [rbx+4A8h], rdi
0x1800e492c  mov     [rbx+4B0h], rdi
0x1800e4933  mov     [rbx+4B8h], rdi
0x1800e493a  lea     rcx, [rbx+490h]
0x1800e4941  call    ?_Tidy@?$vector@V?$ComPtr@VFulfillmentDataInfo@Internal@WindowsUpdate@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VFulfillmentDataInfo@Internal@WindowsUpdate@@@WRL@Microsoft@@@std@@@std@@AEAAXXZ; std::vector<Microsoft::WRL::ComPtr<WindowsUpdate::Internal::FulfillmentDataInfo>>::_Tidy(void)
0x1800e4946  lea     rcx, [rbx+488h]
0x1800e494d  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800e4952  lea     rcx, [rbx+480h]
0x1800e4959  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800e495e  lea     rcx, [rbx+478h]
0x1800e4965  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800e496a  lea     rcx, [rbx+3F0h]
0x1800e4971  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e4976  lea     rcx, [rbx+3B8h]
0x1800e497d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e4982  lea     rcx, [rbx+358h]
0x1800e4989  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KV?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,unsigned __int64,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::~_Hash<std::_Umap_traits<std::wstring,unsigned __int64,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>(void)
0x1800e498e  lea     rcx, [rbx+338h]
0x1800e4995  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e499a  lea     rcx, [rbx+2F8h]
0x1800e49a1  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KV?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,unsigned __int64,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::~_Hash<std::_Umap_traits<std::wstring,unsigned __int64,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>(void)
0x1800e49a6  lea     rcx, [rbx+2B8h]
0x1800e49ad  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x1800e49b2  lea     rcx, [rbx+278h]
0x1800e49b9  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x1800e49be  lea     rcx, [rbx+268h]
0x1800e49c5  call    ??1?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(void)
0x1800e49ca  lea     rcx, [rbx+250h]
0x1800e49d1  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800e49d6  lea     rcx, [rbx+238h]
0x1800e49dd  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800e49e2  lea     rcx, [rbx+218h]
0x1800e49e9  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800e49ee  lea     rcx, [rbx+200h]
0x1800e49f5  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800e49fa  mov     rcx, [rbx+1F0h]; bstrString
0x1800e4a01  call    cs:__imp_SysFreeString
0x1800e4a07  mov     rcx, [rbx+1E8h]; string
0x1800e4a0e  call    cs:__imp_WindowsDeleteString
0x1800e4a14  mov     [rbx+1E8h], rdi
0x1800e4a1b  mov     rcx, [rbx+1E0h]; string
0x1800e4a22  call    cs:__imp_WindowsDeleteString
0x1800e4a28  mov     [rbx+1E0h], rdi
0x1800e4a2f  mov     rcx, [rbx+1D8h]; string
0x1800e4a36  call    cs:__imp_WindowsDeleteString
0x1800e4a3c  mov     [rbx+1D8h], rdi
0x1800e4a43  mov     rcx, [rbx+1D0h]; string
0x1800e4a4a  call    cs:__imp_WindowsDeleteString
0x1800e4a50  mov     [rbx+1D0h], rdi
0x1800e4a57  mov     rcx, [rbx+1C8h]; string
0x1800e4a5e  call    cs:__imp_WindowsDeleteString
0x1800e4a64  mov     [rbx+1C8h], rdi
0x1800e4a6b  mov     rcx, [rbx+1C0h]; this
0x1800e4a72  test    rcx, rcx
0x1800e4a75  jz      short loc_1800E4A7C
0x1800e4a77  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800e4a7c  lea     rcx, [rbx+128h]
0x1800e4a83  call    ??1?$_Temporary_owner@VTraceLoggingCorrelationVector@@@std@@QEAA@XZ; std::_Temporary_owner<TraceLoggingCorrelationVector>::~_Temporary_owner<TraceLoggingCorrelationVector>(void)
0x1800e4a88  lea     rcx, [rbx+98h]; this
0x1800e4a8f  call    ??1CallerContext@@QEAA@XZ; CallerContext::~CallerContext(void)
0x1800e4a94  mov     rcx, [rbx+78h]; string
0x1800e4a98  call    cs:__imp_WindowsDeleteString
0x1800e4a9e  mov     [rbx+78h], rdi
0x1800e4aa2  mov     rcx, [rbx+70h]; string
0x1800e4aa6  call    cs:__imp_WindowsDeleteString
0x1800e4aac  lea     rcx, [rbx+68h]
0x1800e4ab0  mov     [rbx+70h], rdi
0x1800e4ab4  call    ??1?$com_ptr_t@VInstallQueue@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<InstallQueue,wil::err_exception_policy>::~com_ptr_t<InstallQueue,wil::err_exception_policy>(void)
0x1800e4ab9  mov     rcx, [rbx+60h]; string
0x1800e4abd  call    cs:__imp_WindowsDeleteString
0x1800e4ac3  mov     [rbx+60h], rdi
0x1800e4ac7  mov     rcx, [rbx+58h]; string
0x1800e4acb  call    cs:__imp_WindowsDeleteString
0x1800e4ad1  mov     [rbx+58h], rdi
0x1800e4ad5  mov     rcx, [rbx+50h]; string
0x1800e4ad9  call    cs:__imp_WindowsDeleteString
0x1800e4adf  mov     [rbx+50h], rdi
0x1800e4ae3  mov     rcx, [rbx+48h]; string
0x1800e4ae7  call    cs:__imp_WindowsDeleteString
0x1800e4aed  mov     rcx, rbx
0x1800e4af0  mov     [rbx+48h], rdi
0x1800e4af4  mov     rbx, [rsp+28h+arg_0]
0x1800e4af9  add     rsp, 20h
0x1800e4afd  pop     rdi
0x1800e4afe  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@U?$IMapView@PEAUHSTRING__@@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@567@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IMapView<HSTRING__ *,Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *>,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IMapView<HSTRING__ *,Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *>,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *>,Microsoft::WRL::FtmBase>(void)
```
