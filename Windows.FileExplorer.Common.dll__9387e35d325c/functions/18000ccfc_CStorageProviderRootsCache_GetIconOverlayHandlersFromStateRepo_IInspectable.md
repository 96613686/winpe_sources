# CStorageProviderRootsCache::GetIconOverlayHandlersFromStateRepo(IInspectable *)

- ea: `0x18000ccfc`
- end: `0x18000ce73`
- name: `?GetIconOverlayHandlersFromStateRepo@CStorageProviderRootsCache@@AEAAJPEAUIInspectable@@@Z`
- size: `375`
- prototype: `int(CStorageProviderRootsCache *__hidden this, struct IInspectable *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000d188`

## callees

- `0x180004a54`
- `0x1800077c8`
- `0x18000ccfc`
- `0x18000ce80`
- `0x18000d0e0`
- `0x18000d128`
- `0x180024198`
- `0x18005e9c0`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ce1f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ce6b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ce1f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ce6b`

## string_xrefs

- `0x18000ce2e`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CStorageProviderRootsCache::GetIconOverlayHandlersFromStateRepo(
        CStorageProviderRootsCache *this,
        struct IInspectable *a2)
{
  __int64 v4; // rdx
  int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v10; // rcx
  LPVOID pv; // [rsp+20h] [rbp-20h] BYREF
  __int64 v12; // [rsp+28h] [rbp-18h]
  __int64 v13; // [rsp+30h] [rbp-10h]
  __int64 v14; // [rsp+38h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+8h]
  struct _GUID v16; // [rsp+60h] [rbp+20h] BYREF

  pv = 0;
  v12 = 0;
  v13 = 0;
  v14 = 0;
  winrt::impl::root_implements<winrt::iterable_base<winrt::impl::vector_impl<winrt::WindowsUdk::Storage::Provider::MicrosoftGraphRecentItemInfo,std::vector<winrt::WindowsUdk::Storage::Provider::MicrosoftGraphRecentItemInfo>,winrt::impl::single_threaded_collection_base>,winrt::WindowsUdk::Storage::Provider::MicrosoftGraphRecentItemInfo,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::WindowsUdk::Storage::Provider::MicrosoftGraphRecentItemInfo>>::abi_guard::abi_guard(
    v16.Data4,
    &pv);
  *(_QWORD *)&v16.Data1 = 0;
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v16);
  if ( StateRepoHelpers::LookupInPropertySet(
         (StateRepoHelpers *)a2,
         (struct IInspectable *)&stru_180091588,
         (const unsigned __int16 *)&GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c,
         &v16,
         (void **)pv) < 0 )
    goto LABEL_4;
  v5 = StateRepoHelpers::IterateThroughOneOrMultiplePropertySets__lambda_ebee2ac653baff94973a32d9d9d116a5___(
         *(_QWORD *)&v16.Data1,
         v4,
         v16.Data4);
  v6 = v5;
  if ( v5 >= 0 )
  {
    CCoSimpleArray<unsigned short *,4294967294,CSimpleArrayStandardCompareHelper<unsigned short *>>::~CCoSimpleArray<unsigned short *,4294967294,CSimpleArrayStandardCompareHelper<unsigned short *>>((char *)this + 624);
    *((_QWORD *)this + 78) = pv;
    *((_QWORD *)this + 80) = v13;
    v7 = v12;
    *((_QWORD *)this + 79) = v12;
    *((_QWORD *)this + 81) = v14;
    pv = 0;
    v13 = 0;
    v12 = 0;
    v14 = 0;
    *(_QWORD *)v16.Data4 = v7;
    CloudFilesTelemetry::IconOverlayHandlers_StateRepoQueried<unsigned __int64,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>> &>(
      v16.Data4,
      this);
LABEL_4:
    v8 = *(_QWORD *)&v16.Data1;
    if ( *(_QWORD *)&v16.Data1 )
    {
      *(_QWORD *)&v16.Data1 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    }
    if ( pv )
      CoTaskMemFree(pv);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xAB1,
    (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
    (const char *)(unsigned int)v5,
    (int)pv);
  v10 = *(_QWORD *)&v16.Data1;
  if ( *(_QWORD *)&v16.Data1 )
  {
    *(_QWORD *)&v16.Data1 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  }
  if ( pv )
    CoTaskMemFree(pv);
  return v6;
}

```

## disassembly

```asm
0x18000ccfc  mov     [rsp-8+arg_0], rbx
0x18000cd01  mov     [rsp-8+arg_8], rdi
0x18000cd06  push    rbp
0x18000cd07  mov     rbp, rsp
0x18000cd0a  sub     rsp, 40h
0x18000cd0e  mov     rbx, rdx
0x18000cd11  mov     rdi, rcx
0x18000cd14  mov     [rbp+pv], 0
0x18000cd1c  mov     [rbp+var_18], 0
0x18000cd24  mov     [rbp+var_10], 0
0x18000cd2c  mov     [rbp+var_8], 0
0x18000cd34  lea     rdx, [rbp+pv]
0x18000cd38  lea     rcx, [rbp+arg_10.Data4]
0x18000cd3c  call    ??0abi_guard@?$root_implements@Uiterator@?$iterable_base@U?$vector_impl@UMicrosoftGraphRecentItemInfo@Provider@Storage@WindowsUdk@winrt@@V?$vector@UMicrosoftGraphRecentItemInfo@Provider@Storage@WindowsUdk@winrt@@V?$allocator@UMicrosoftGraphRecentItemInfo@Provider@Storage@WindowsUdk@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@UMicrosoftGraphRecentItemInfo@Provider@Storage@WindowsUdk@3@Ucollection_version@23@@winrt@@U?$IIterator@UMicrosoftGraphRecentItemInfo@Provider@Storage@WindowsUdk@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@QEAA@AEAUiterator@?$iterable_base@U?$vector_impl@UMicrosoftGraphRecentItemInfo@Provider@Storage@WindowsUdk@winrt@@V?$vector@UMicrosoftGraphRecentItemInfo@Provider@Storage@WindowsUdk@winrt@@V?$allocator@UMicrosoftGraphRecentItemInfo@Provider@Storage@WindowsUdk@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@UMicrosoftGraphRecentItemInfo@Provider@Storage@WindowsUdk@3@Ucollection_version@23@@3@@Z; winrt::impl::root_implements<winrt::iterable_base<winrt::impl::vector_impl<winrt::WindowsUdk::Storage::Provider::MicrosoftGraphRecentItemInfo,std::vector<winrt::WindowsUdk::Storage::Provider::MicrosoftGraphRecentItemInfo>,winrt::impl::single_threaded_collection_base>,winrt::WindowsUdk::Storage::Provider::MicrosoftGraphRecentItemInfo,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::WindowsUdk::Storage::Provider::MicrosoftGraphRecentItemInfo>>::abi_guard::abi_guard(winrt::iterable_base<winrt::impl::vector_impl<winrt::WindowsUdk::Storage::Provider::MicrosoftGraphRecentItemInfo,std::vector<winrt::WindowsUdk::Storage::Provider::MicrosoftGraphRecentItemInfo>,winrt::impl::single_threaded_collection_base>,winrt::WindowsUdk::Storage::Provider::MicrosoftGraphRecentItemInfo,winrt::impl::collection_version>::iterator &)
0x18000cd41  mov     qword ptr [rbp+arg_10.Data1], 0
0x18000cd49  lea     rcx, [rbp+arg_10]
0x18000cd4d  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18000cd52  lea     r9, [rbp+arg_10]; struct _GUID *
0x18000cd56  lea     r8, _GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c; unsigned __int16 *
0x18000cd5d  lea     rdx, stru_180091588; struct IInspectable *
0x18000cd64  mov     rcx, rbx; this
0x18000cd67  call    ?LookupInPropertySet@StateRepoHelpers@@YAJPEAUIInspectable@@PEBGAEBU_GUID@@PEAPEAX@Z; StateRepoHelpers::LookupInPropertySet(IInspectable *,ushort const *,_GUID const &,void * *)
0x18000cd6c  test    eax, eax
0x18000cd6e  js      short loc_18000CDE6
0x18000cd70  lea     r8, [rbp+arg_10.Data4]
0x18000cd74  mov     rcx, qword ptr [rbp+arg_10.Data1]
0x18000cd78  call    StateRepoHelpers__IterateThroughOneOrMultiplePropertySets__lambda_ebee2ac653baff94973a32d9d9d116a5___
0x18000cd7d  mov     ebx, eax
0x18000cd7f  test    eax, eax
0x18000cd81  js      loc_18000CE27
0x18000cd87  lea     rbx, [rdi+270h]
0x18000cd8e  mov     rcx, rbx
0x18000cd91  call    ??1?$CCoSimpleArray@PEAG$0PPPPPPPO@V?$CSimpleArrayStandardCompareHelper@PEAG@@@@QEAA@XZ; CCoSimpleArray<ushort *,4294967294,CSimpleArrayStandardCompareHelper<ushort *>>::~CCoSimpleArray<ushort *,4294967294,CSimpleArrayStandardCompareHelper<ushort *>>(void)
0x18000cd96  mov     rax, [rbp+pv]
0x18000cd9a  mov     [rbx], rax
0x18000cd9d  mov     rax, [rbp+var_10]
0x18000cda1  mov     [rbx+10h], rax
0x18000cda5  mov     rcx, [rbp+var_18]
0x18000cda9  mov     [rbx+8], rcx
0x18000cdad  mov     rax, [rbp+var_8]
0x18000cdb1  mov     [rbx+18h], rax
0x18000cdb5  mov     [rbp+pv], 0
0x18000cdbd  mov     [rbp+var_10], 0
0x18000cdc5  mov     [rbp+var_18], 0
0x18000cdcd  mov     [rbp+var_8], 0
0x18000cdd5  mov     qword ptr [rbp+arg_10.Data4], rcx
0x18000cdd9  mov     rdx, rdi
0x18000cddc  lea     rcx, [rbp+arg_10.Data4]
0x18000cde0  call    ??$IconOverlayHandlers_StateRepoQueried@_KAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@CloudFilesTelemetry@@SAX$$QEA_KAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@Z; CloudFilesTelemetry::IconOverlayHandlers_StateRepoQueried<unsigned __int64,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &>(unsigned __int64 &&,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)
0x18000cde5  nop
0x18000cde6  mov     rcx, qword ptr [rbp+arg_10.Data1]
0x18000cdea  test    rcx, rcx
0x18000cded  jz      short loc_18000CE04
0x18000cdef  mov     qword ptr [rbp+arg_10.Data1], 0
0x18000cdf7  mov     rax, [rcx]
0x18000cdfa  mov     rax, [rax+10h]
0x18000cdfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce03  nop
0x18000ce04  mov     rcx, [rbp+pv]; pv
0x18000ce08  test    rcx, rcx
0x18000ce0b  jnz     short loc_18000CE1F
0x18000ce0d  xor     eax, eax
0x18000ce0f  mov     rbx, [rsp+40h+arg_0]
0x18000ce14  mov     rdi, [rsp+40h+arg_8]
0x18000ce19  add     rsp, 40h
0x18000ce1d  pop     rbp
0x18000ce1e  retn
0x18000ce1f  call    cs:__imp_CoTaskMemFree
0x18000ce25  jmp     short loc_18000CE0D
0x18000ce27  mov     rcx, [rbp+8]; this
0x18000ce2b  mov     r9d, ebx; char *
0x18000ce2e  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x18000ce35  mov     edx, 0AB1h; void *
0x18000ce3a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ce3f  nop
0x18000ce40  mov     rcx, qword ptr [rbp+arg_10.Data1]
0x18000ce44  test    rcx, rcx
0x18000ce47  jz      short loc_18000CE5E
0x18000ce49  mov     qword ptr [rbp+arg_10.Data1], 0
0x18000ce51  mov     rax, [rcx]
0x18000ce54  mov     rax, [rax+10h]
0x18000ce58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce5d  nop
0x18000ce5e  mov     rcx, [rbp+pv]; pv
0x18000ce62  test    rcx, rcx
0x18000ce65  jnz     short loc_18000CE6B
0x18000ce67  mov     eax, ebx
0x18000ce69  jmp     short loc_18000CE0F
0x18000ce6b  call    cs:__imp_CoTaskMemFree
0x18000ce71  jmp     short loc_18000CE67
```
