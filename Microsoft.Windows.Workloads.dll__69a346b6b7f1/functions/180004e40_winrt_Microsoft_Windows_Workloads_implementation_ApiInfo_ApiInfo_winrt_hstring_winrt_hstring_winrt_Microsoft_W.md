# winrt::Microsoft::Windows::Workloads::implementation::ApiInfo::ApiInfo(winrt::hstring,winrt::hstring,winrt::Microsoft::Windows::Workloads::Workload,winrt::Microsoft::Windows::Management::Deployment::PackageSetItem,winrt::guid,winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>)

- ea: `0x180004e40`
- end: `0x1800052c8`
- name: `??0ApiInfo@implementation@Workloads@Windows@Microsoft@winrt@@QEAA@Uhstring@5@0UWorkload@2345@UPackageSetItem@Deployment@Management@345@Uguid@5@U?$IMap@Uhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@@Collections@Foundation@35@@Z`
- size: `1160`
- prototype: `__int64 __fastcall(__int64, winrt::impl **, winrt::impl **, _QWORD *, _QWORD *, _OWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0x180026960`

## callees

- `0x1800040a0`
- `0x180004e40`
- `0x18000a350`
- `0x18000c890`
- `0x18000db50`
- `0x18000e370`
- `0x18000e420`
- `0x1800101e0`
- `0x1800104d0`
- `0x1800157c0`
- `0x180030ae5`
- `0x180030aeb`
- `0x180034ef0`
- `0x180035060`
- `0x18003bed0`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x1800051c0`
- `KERNEL32!GetModuleHandleW` at `0x1800051c0`
- `KERNEL32!InitOnceExecuteOnce` at `0x180004fb2`
- `KERNEL32!InitOnceExecuteOnce` at `0x180004fb2`
- `KERNEL32!GetProcAddress` at `0x1800051d0`
- `KERNEL32!GetProcAddress` at `0x1800051d0`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x1800052a7`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x1800052b2`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x1800052a7`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x1800052b2`

## string_xrefs

- `0x1800051c9`: `g_WSAIFabricService`

## pseudocode

```c
__int64 __fastcall winrt::Microsoft::Windows::Workloads::implementation::ApiInfo::ApiInfo(
        __int64 a1,
        winrt::impl **a2,
        winrt::impl **a3,
        _QWORD *a4,
        _QWORD *a5,
        _OWORD *a6,
        _QWORD *a7)
{
  _QWORD *v10; // r14
  __int64 v11; // r12
  struct winrt::impl::hstring_header *v12; // rdx
  __int64 v13; // rcx
  _QWORD *v14; // rax
  __int64 v15; // rcx
  char **v16; // rsi
  __int64 v17; // rcx
  void *v18; // rdx
  unsigned int v19; // r8d
  const char *v20; // r9
  _QWORD *v21; // rax
  __int64 v22; // rax
  __int64 v23; // rcx
  __int64 v24; // r14
  _QWORD *v25; // rbx
  struct winrt::impl::hstring_header *v26; // rdx
  _OWORD *v27; // rbx
  _QWORD *v28; // rax
  __int64 v29; // rcx
  HMODULE ModuleHandleW; // rax
  volatile signed __int32 **v31; // r12
  volatile signed __int32 *v32; // rbx
  int v33; // eax
  HANDLE ProcessHeap; // rax
  winrt::impl *v35; // rbx
  int v36; // esi
  HANDLE v37; // rax
  char *v39; // [rsp+20h] [rbp-B1h] BYREF
  __int128 *v40; // [rsp+28h] [rbp-A9h]
  _QWORD *v41; // [rsp+30h] [rbp-A1h]
  __int64 v42; // [rsp+38h] [rbp-99h]
  _QWORD *v43; // [rsp+40h] [rbp-91h]
  volatile signed __int32 **v44; // [rsp+48h] [rbp-89h]
  _QWORD *v45; // [rsp+50h] [rbp-81h]
  __int128 v46; // [rsp+60h] [rbp-71h] BYREF
  __int64 v47; // [rsp+70h] [rbp-61h]
  winrt::impl **v48; // [rsp+78h] [rbp-59h]
  winrt::impl **v49; // [rsp+80h] [rbp-51h]
  _QWORD *v50; // [rsp+88h] [rbp-49h]
  _QWORD *v51; // [rsp+90h] [rbp-41h]
  _QWORD *v52; // [rsp+98h] [rbp-39h]
  _BYTE v53[24]; // [rsp+A0h] [rbp-31h] BYREF
  __int128 v54; // [rsp+B8h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+47h]

  v45 = a4;
  v44 = (volatile signed __int32 **)a2;
  v47 = a1;
  v48 = a2;
  v49 = a3;
  v50 = a4;
  v10 = a5;
  v43 = a5;
  v51 = a5;
  v52 = a7;
  v11 = a1 + 16;
  *(_QWORD *)(a1 + 16) = &winrt::impl::produce<winrt::Microsoft::Windows::Workloads::implementation::ApiInfo,winrt::Microsoft::Windows::Workloads::IApiInfo>::`vftable';
  *(_QWORD *)(a1 + 24) = &winrt::impl::produce<winrt::Microsoft::Windows::Workloads::implementation::ApiInfo,winrt::Microsoft::Windows::Workloads::IApiInfo2>::`vftable';
  *(_QWORD *)(a1 + 32) = &winrt::impl::produce<winrt::Microsoft::Windows::Workloads::implementation::ApiInfo,winrt::Microsoft::Windows::Workloads::IApiInfo3>::`vftable';
  *(_QWORD *)(a1 + 40) = &winrt::impl::produce<winrt::Microsoft::Windows::Workloads::implementation::ApiInfo,winrt::Microsoft::Windows::Workloads::IApiInfo4>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *(_QWORD *)(a1 + 8) = 1;
  *(_QWORD *)a1 = &winrt::impl::heap_implements<winrt::Microsoft::Windows::Workloads::implementation::ApiInfo>::`vftable';
  *(_QWORD *)(a1 + 48) = winrt::impl::duplicate_hstring(*a2, (struct winrt::impl::hstring_header *)a2);
  *(_QWORD *)(a1 + 56) = winrt::impl::duplicate_hstring(*a3, v12);
  *(_QWORD *)(a1 + 64) = 0;
  *(_WORD *)(a1 + 72) = 0;
  *(_OWORD *)(a1 + 76) = *a6;
  v13 = *a4;
  *(_QWORD *)(a1 + 96) = *a4;
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 8LL))(v13);
  *(_QWORD *)(a1 + 104) = 0;
  *(_QWORD *)(a1 + 112) = 0;
  v14 = operator new(0x40u);
  *v14 = v14;
  v14[1] = v14;
  v14[2] = v14;
  *((_WORD *)v14 + 12) = 257;
  *(_QWORD *)(a1 + 104) = v14;
  v15 = *a5;
  *(_QWORD *)(a1 + 120) = *a5;
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 8LL))(v15);
  v16 = (char **)(a1 + 128);
  v17 = *a7;
  *(_QWORD *)(a1 + 128) = *a7;
  if ( v17 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 8LL))(v17);
  *(_DWORD *)(a1 + 136) = 4;
  InitOnceExecuteOnce(
    &`wil::Wil_Staging_FailFastOnAssertEnabled'::`2'::s_initonce,
    _lambda_a4019648cf9f036c07417add878aba48_::_lambda_invoker_cdecl_,
    0,
    0);
  if ( `wil::Wil_Staging_FailFastOnAssertEnabled'::`2'::s_isFailFastOnAssertEnabled
    && !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_iCxz8Qnks>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_iCxz8Qnks>::GetImpl'::`2'::impl) )
  {
    wil::details::in1diag3::_FailFast_Unexpected(retaddr, v18, v19, v20);
  }
  if ( !*v16 )
  {
    v54 = 0u;
    v21 = operator new(0x30u);
    *v21 = v21;
    v21[1] = v21;
    v21[2] = v21;
    *((_WORD *)v21 + 12) = 257;
    *(_QWORD *)&v54 = v21;
    v22 = std::_Tree<std::_Tmap_traits<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::less<winrt::hstring>,std::allocator<std::pair<winrt::hstring const,winrt::Microsoft::Windows::Workloads::ApiInfo>>,0>>::_Find_lower_bound<winrt::hstring>(
            &v54,
            v53,
            a3);
    v46 = *(_OWORD *)v22;
    v42 = *(_QWORD *)(v22 + 16);
    if ( *(_BYTE *)(v42 + 25) || (unsigned __int8)std::less<winrt::hstring>::operator()(v23, a3, v42 + 32) )
    {
      if ( *((_QWORD *)&v54 + 1) == 0x555555555555555LL )
        std::_Throw_tree_length_error();
      v24 = v54;
      v40 = &v54;
      v25 = operator new(0x30u);
      v41 = v25;
      v25[4] = winrt::impl::duplicate_hstring(*a3, v26);
      v25[5] = v11;
      if ( v11 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
      *v25 = v24;
      v25[1] = v24;
      v25[2] = v24;
      *((_WORD *)v25 + 12) = 0;
      std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,winrt::Microsoft::Windows::Workloads::WorkloadManager>>>::_Insert_node(
        &v54,
        &v46,
        v25);
    }
    v27 = operator new(0x40u);
    v40 = v27;
    *((_QWORD *)v27 + 2) = &winrt::impl::produce<winrt::impl::map_impl<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::map<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>>::`vftable';
    *((_QWORD *)v27 + 3) = &winrt::impl::produce<winrt::impl::map_impl<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::map<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>>::`vftable';
    *((_QWORD *)v27 + 4) = &winrt::impl::produce<winrt::impl::map_impl<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::map<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>>>::`vftable';
    _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
    *((_QWORD *)v27 + 1) = 1;
    *((_DWORD *)v27 + 10) = 0;
    *(_QWORD *)v27 = &winrt::impl::map_impl<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::map<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>,winrt::impl::single_threaded_collection_base>::`vftable';
    *((_QWORD *)v27 + 6) = 0;
    *((_QWORD *)v27 + 7) = 0;
    v28 = operator new(0x30u);
    *v28 = v28;
    v28[1] = v28;
    v28[2] = v28;
    *((_WORD *)v28 + 12) = 257;
    *((_QWORD *)v27 + 6) = v28;
    *((_QWORD *)v27 + 6) = v54;
    *(_QWORD *)&v54 = v28;
    v29 = *((_QWORD *)v27 + 7);
    *((_QWORD *)v27 + 7) = *((_QWORD *)&v54 + 1);
    *((_QWORD *)&v54 + 1) = v29;
    *(_QWORD *)v27 = &winrt::impl::map_impl<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::map<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>,winrt::impl::single_threaded_collection_base>::`vftable';
    v39 = (char *)(v27 + 1);
    if ( v16 == &v39 )
    {
      if ( v27 != (_OWORD *)-16LL )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v39);
    }
    else
    {
      if ( *v16 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 128);
      *v16 = (char *)(v27 + 1);
    }
    std::_Tree<std::_Tmap_traits<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::less<winrt::hstring>,std::allocator<std::pair<winrt::hstring const,winrt::Microsoft::Windows::Workloads::ApiInfo>>,0>>::~_Tree<std::_Tmap_traits<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::less<winrt::hstring>,std::allocator<std::pair<winrt::hstring const,winrt::Microsoft::Windows::Workloads::ApiInfo>>,0>>(&v54);
    v10 = v43;
  }
  ModuleHandleW = GetModuleHandleW(0);
  if ( GetProcAddress(ModuleHandleW, "g_WSAIFabricService") )
    *(_DWORD *)(a1 + 136) = 1;
  v31 = v44;
  v32 = *v44;
  if ( *v44 )
  {
    v33 = _InterlockedDecrement(v32 + 6);
    if ( v33 )
    {
      if ( v33 < 0 )
        abort();
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v32);
    }
    *v31 = 0;
  }
  v35 = *a3;
  if ( *a3 )
  {
    v36 = _InterlockedDecrement((volatile signed __int32 *)v35 + 6);
    if ( v36 )
    {
      if ( v36 < 0 )
        abort();
    }
    else
    {
      v37 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v37, 0, v35);
    }
    *a3 = 0;
  }
  if ( *v45 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v45);
  if ( *v10 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v10);
  if ( *a7 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a7);
  return a1;
}

```

## disassembly

```asm
0x180004e40  push    rbp
0x180004e42  push    rbx
0x180004e43  push    rsi
0x180004e44  push    rdi
0x180004e45  push    r12
0x180004e47  push    r13
0x180004e49  push    r14
0x180004e4b  push    r15
0x180004e4d  lea     rbp, [rsp-7]
0x180004e52  sub     rsp, 0D8h
0x180004e59  mov     rax, cs:__security_cookie
0x180004e60  xor     rax, rsp
0x180004e63  mov     [rbp+3Fh+var_48], rax
0x180004e67  mov     rbx, r9
0x180004e6a  mov     [rsp+110h+var_C0], rbx
0x180004e6f  mov     r15, r8
0x180004e72  mov     [rsp+110h+var_C8], rdx
0x180004e77  mov     rdi, rcx
0x180004e7a  mov     [rbp+3Fh+var_A0], rcx
0x180004e7e  mov     [rbp+3Fh+var_98], rdx
0x180004e82  mov     [rbp+3Fh+var_90], r8
0x180004e86  mov     [rbp+3Fh+var_88], rbx
0x180004e8a  mov     r14, [rbp+3Fh+arg_20]
0x180004e8e  mov     [rsp+110h+var_D0], r14
0x180004e93  mov     [rbp+3Fh+var_80], r14
0x180004e97  mov     r13, [rbp+3Fh+arg_30]
0x180004e9b  mov     [rbp+3Fh+var_78], r13
0x180004e9f  xor     esi, esi
0x180004ea1  lea     r12, [rcx+10h]
0x180004ea5  lea     rcx, ??_7?$produce@UApiInfo@implementation@Workloads@Windows@Microsoft@winrt@@UIApiInfo@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Windows::Workloads::implementation::ApiInfo,winrt::Microsoft::Windows::Workloads::IApiInfo>::`vftable'
0x180004eac  mov     [r12], rcx
0x180004eb0  lea     rcx, ??_7?$produce@UApiInfo@implementation@Workloads@Windows@Microsoft@winrt@@UIApiInfo2@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Windows::Workloads::implementation::ApiInfo,winrt::Microsoft::Windows::Workloads::IApiInfo2>::`vftable'
0x180004eb7  mov     [r12+8], rcx
0x180004ebc  lea     rcx, ??_7?$produce@UApiInfo@implementation@Workloads@Windows@Microsoft@winrt@@UIApiInfo3@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Windows::Workloads::implementation::ApiInfo,winrt::Microsoft::Windows::Workloads::IApiInfo3>::`vftable'
0x180004ec3  mov     [r12+10h], rcx
0x180004ec8  lea     rcx, ??_7?$produce@UApiInfo@implementation@Workloads@Windows@Microsoft@winrt@@UIApiInfo4@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Windows::Workloads::implementation::ApiInfo,winrt::Microsoft::Windows::Workloads::IApiInfo4>::`vftable'
0x180004ecf  mov     [r12+18h], rcx
0x180004ed4  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180004edb  mov     qword ptr [rdi+8], 1
0x180004ee3  lea     rcx, ??_7?$heap_implements@UApiInfo@implementation@Workloads@Windows@Microsoft@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Microsoft::Windows::Workloads::implementation::ApiInfo>::`vftable'
0x180004eea  mov     [rdi], rcx
0x180004eed  mov     rcx, [rdx]; this
0x180004ef0  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x180004ef5  mov     [rdi+30h], rax
0x180004ef9  mov     rcx, [r15]; this
0x180004efc  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x180004f01  mov     [rdi+38h], rax
0x180004f05  mov     [rdi+40h], rsi
0x180004f09  mov     [rdi+48h], si
0x180004f0d  mov     rax, [rbp+3Fh+arg_28]
0x180004f11  movaps  xmm0, xmmword ptr [rax]
0x180004f14  movups  xmmword ptr [rdi+4Ch], xmm0
0x180004f18  mov     rcx, [rbx]
0x180004f1b  mov     [rdi+60h], rcx
0x180004f1f  test    rcx, rcx
0x180004f22  jz      short loc_180004F32
0x180004f24  mov     rax, [rcx]
0x180004f27  mov     rax, [rax+8]
0x180004f2b  call    cs:__guard_dispatch_icall_fptr
0x180004f31  nop
0x180004f32  mov     [rdi+68h], rsi
0x180004f36  mov     [rdi+70h], rsi
0x180004f3a  mov     ecx, 40h ; '@'; Size
0x180004f3f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004f44  mov     [rax], rax
0x180004f47  mov     [rax+8], rax
0x180004f4b  mov     [rax+10h], rax
0x180004f4f  mov     word ptr [rax+18h], 101h
0x180004f55  mov     [rdi+68h], rax
0x180004f59  mov     rcx, [r14]
0x180004f5c  mov     [rdi+78h], rcx
0x180004f60  test    rcx, rcx
0x180004f63  jz      short loc_180004F73
0x180004f65  mov     rax, [rcx]
0x180004f68  mov     rax, [rax+8]
0x180004f6c  call    cs:__guard_dispatch_icall_fptr
0x180004f72  nop
0x180004f73  lea     rsi, [rdi+80h]
0x180004f7a  mov     rcx, [r13+0]
0x180004f7e  mov     [rsi], rcx
0x180004f81  test    rcx, rcx
0x180004f84  jz      short loc_180004F94
0x180004f86  mov     rax, [rcx]
0x180004f89  mov     rax, [rax+8]
0x180004f8d  call    cs:__guard_dispatch_icall_fptr
0x180004f93  nop
0x180004f94  mov     dword ptr [rdi+88h], 4
0x180004f9e  xor     r9d, r9d; Context
0x180004fa1  xor     r8d, r8d; Parameter
0x180004fa4  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_a4019648cf9f036c07417add878aba48_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180004fab  lea     rcx, ?s_initonce@?1??Wil_Staging_FailFastOnAssertEnabled@wil@@YA_NXZ@4T_RTL_RUN_ONCE@@A; InitOnce
0x180004fb2  call    cs:__imp_InitOnceExecuteOnce
0x180004fb8  cmp     cs:?s_isFailFastOnAssertEnabled@?1??Wil_Staging_FailFastOnAssertEnabled@wil@@YA_NXZ@4_NA, 0; bool `wil::Wil_Staging_FailFastOnAssertEnabled(void)'::`2'::s_isFailFastOnAssertEnabled
0x180004fbf  jz      short loc_180004FD9
0x180004fc1  mov     rbx, [rbp+47h]
0x180004fc5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_iCxz8Qnks@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_iCxz8Qnks@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_iCxz8Qnks> `wil::Feature<__WilFeatureTraits_Feature_iCxz8Qnks>::GetImpl(void)'::`2'::impl
0x180004fcc  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_iCxz8Qnks@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_iCxz8Qnks>::__private_IsEnabled(wil::ReportingKind)
0x180004fd1  test    al, al
0x180004fd3  jz      loc_1800052BF
0x180004fd9  cmp     qword ptr [rsi], 0
0x180004fdd  jnz     loc_1800051BE
0x180004fe3  xorps   xmm0, xmm0
0x180004fe6  movups  [rbp+3Fh+var_58], xmm0
0x180004fea  xor     ebx, ebx
0x180004fec  mov     qword ptr [rbp+3Fh+var_58], rbx
0x180004ff0  mov     qword ptr [rbp+3Fh+var_58+8], rbx
0x180004ff4  mov     ecx, 30h ; '0'; Size
0x180004ff9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004ffe  mov     [rax], rax
0x180005001  mov     [rax+8], rax
0x180005005  mov     [rax+10h], rax
0x180005009  mov     word ptr [rax+18h], 101h
0x18000500f  mov     qword ptr [rbp+3Fh+var_58], rax
0x180005013  mov     r8, r15
0x180005016  lea     rdx, [rbp+3Fh+var_70]
0x18000501a  lea     rcx, [rbp+3Fh+var_58]
0x18000501e  call    ??$_Find_lower_bound@Uhstring@winrt@@@?$_Tree@V?$_Tmap_traits@Uhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@U?$less@Uhstring@winrt@@@std@@V?$allocator@U?$pair@$$CBUhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@@std@@@8@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBUhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@@std@@PEAX@std@@@1@AEBUhstring@winrt@@@Z; std::_Tree<std::_Tmap_traits<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::less<winrt::hstring>,std::allocator<std::pair<winrt::hstring const,winrt::Microsoft::Windows::Workloads::ApiInfo>>,0>>::_Find_lower_bound<winrt::hstring>(winrt::hstring const &)
0x180005023  movups  xmm0, xmmword ptr [rax]
0x180005026  movups  [rbp+3Fh+var_B0], xmm0
0x18000502a  movsd   xmm0, qword ptr [rax+10h]
0x18000502f  movsd   [rsp+110h+var_D8], xmm0
0x180005035  mov     r8, [rsp+110h+var_D8]
0x18000503a  cmp     [r8+19h], bl
0x18000503e  jnz     short loc_180005054
0x180005040  add     r8, 20h ; ' '
0x180005044  mov     rdx, r15
0x180005047  call    ??R?$less@Uhstring@winrt@@@std@@QEBA_NAEBUhstring@winrt@@0@Z; std::less<winrt::hstring>::operator()(winrt::hstring const &,winrt::hstring const &)
0x18000504c  test    al, al
0x18000504e  jz      loc_1800050DB
0x180005054  mov     rax, 555555555555555h
0x18000505e  cmp     qword ptr [rbp+3Fh+var_58+8], rax
0x180005062  jz      loc_1800052B9
0x180005068  mov     r14, qword ptr [rbp+3Fh+var_58]
0x18000506c  lea     rax, [rbp+3Fh+var_58]
0x180005070  mov     [rsp+110h+var_E8], rax
0x180005075  mov     [rsp+110h+var_E0], rbx
0x18000507a  mov     ecx, 30h ; '0'; Size
0x18000507f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005084  mov     rbx, rax
0x180005087  mov     [rsp+110h+var_E0], rax
0x18000508c  mov     rcx, [r15]; this
0x18000508f  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x180005094  mov     [rbx+20h], rax
0x180005098  mov     [rbx+28h], r12
0x18000509c  test    r12, r12
0x18000509f  jz      short loc_1800050B2
0x1800050a1  mov     rax, [r12]
0x1800050a5  mov     rcx, r12
0x1800050a8  mov     rax, [rax+8]
0x1800050ac  call    cs:__guard_dispatch_icall_fptr
0x1800050b2  mov     [rbx], r14
0x1800050b5  mov     [rbx+8], r14
0x1800050b9  mov     [rbx+10h], r14
0x1800050bd  mov     word ptr [rbx+18h], 0
0x1800050c3  movups  xmm0, [rbp+3Fh+var_B0]
0x1800050c7  movaps  [rbp+3Fh+var_B0], xmm0
0x1800050cb  mov     r8, rbx
0x1800050ce  lea     rdx, [rbp+3Fh+var_B0]
0x1800050d2  lea     rcx, [rbp+3Fh+var_58]
0x1800050d6  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KUWorkloadManager@Workloads@Windows@Microsoft@winrt@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CB_KUWorkloadManager@Workloads@Windows@Microsoft@winrt@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CB_KUWorkloadManager@Workloads@Windows@Microsoft@winrt@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,winrt::Microsoft::Windows::Workloads::WorkloadManager>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<unsigned __int64 const,winrt::Microsoft::Windows::Workloads::WorkloadManager>,void *> *>,std::_Tree_node<std::pair<unsigned __int64 const,winrt::Microsoft::Windows::Workloads::WorkloadManager>,void *> * const)
0x1800050db  mov     ecx, 40h ; '@'; Size
0x1800050e0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800050e5  mov     rbx, rax
0x1800050e8  mov     [rsp+110h+var_E8], rax
0x1800050ed  lea     r14, [rax+10h]
0x1800050f1  lea     rax, ??_7?$produce@U?$map_impl@Uhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@V?$map@Uhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@U?$less@Uhstring@winrt@@@std@@V?$allocator@U?$pair@$$CBUhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@@std@@@8@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@U?$IMap@Uhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@@Collections@Foundation@Windows@3@@impl@winrt@@6B@; const winrt::impl::produce<winrt::impl::map_impl<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::map<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>>::`vftable'
0x1800050f8  mov     [r14], rax
0x1800050fb  lea     rax, ??_7?$produce@U?$map_impl@Uhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@V?$map@Uhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@U?$less@Uhstring@winrt@@@std@@V?$allocator@U?$pair@$$CBUhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@@std@@@8@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@U?$IMapView@Uhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@@Collections@Foundation@Windows@3@@impl@winrt@@6B@; const winrt::impl::produce<winrt::impl::map_impl<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::map<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>>::`vftable'
0x180005102  mov     [r14+8], rax
0x180005106  lea     rax, ??_7?$produce@U?$map_impl@Uhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@V?$map@Uhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@U?$less@Uhstring@winrt@@@std@@V?$allocator@U?$pair@$$CBUhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@@std@@@8@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@U?$IIterable@U?$IKeyValuePair@Uhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@@Collections@Foundation@Windows@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@6B@; const winrt::impl::produce<winrt::impl::map_impl<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::map<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>>>::`vftable'
0x18000510d  mov     [r14+10h], rax
0x180005111  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180005118  mov     qword ptr [rbx+8], 1
0x180005120  xor     eax, eax
0x180005122  mov     [rbx+28h], eax
0x180005125  lea     rax, ??_7?$map_impl@Uhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@V?$map@Uhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@U?$less@Uhstring@winrt@@@std@@V?$allocator@U?$pair@$$CBUhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@@std@@@8@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@6B@; const winrt::impl::map_impl<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::map<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>,winrt::impl::single_threaded_collection_base>::`vftable'
0x18000512c  mov     [rbx], rax
0x18000512f  xor     eax, eax
0x180005131  mov     [rbx+30h], rax
0x180005135  mov     [rbx+38h], rax
0x180005139  mov     ecx, 30h ; '0'; Size
0x18000513e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005143  mov     [rax], rax
0x180005146  mov     [rax+8], rax
0x18000514a  mov     [rax+10h], rax
0x18000514e  mov     word ptr [rax+18h], 101h
0x180005154  mov     [rbx+30h], rax
0x180005158  mov     rcx, qword ptr [rbp+3Fh+var_58]
0x18000515c  mov     [rbx+30h], rcx
0x180005160  mov     qword ptr [rbp+3Fh+var_58], rax
0x180005164  mov     rcx, [rbx+38h]
0x180005168  mov     rax, qword ptr [rbp+3Fh+var_58+8]
0x18000516c  mov     [rbx+38h], rax
0x180005170  mov     qword ptr [rbp+3Fh+var_58+8], rcx
0x180005174  lea     rax, ??_7?$map_impl@Uhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@V?$map@Uhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@U?$less@Uhstring@winrt@@@std@@V?$allocator@U?$pair@$$CBUhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@@std@@@8@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@6B@; const winrt::impl::map_impl<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::map<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>,winrt::impl::single_threaded_collection_base>::`vftable'
0x18000517b  mov     [rbx], rax
0x18000517e  mov     [rsp+110h+var_F0], r14
0x180005183  lea     rax, [rsp+110h+var_F0]
0x180005188  cmp     rsi, rax
0x18000518b  jz      short loc_1800051A0
0x18000518d  cmp     qword ptr [rsi], 0
0x180005191  jz      short loc_18000519B
0x180005193  mov     rcx, rsi
0x180005196  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000519b  mov     [rsi], r14
0x18000519e  jmp     short loc_1800051B0
0x1800051a0  test    r14, r14
0x1800051a3  jz      short loc_1800051B0
0x1800051a5  lea     rcx, [rsp+110h+var_F0]
0x1800051aa  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800051af  nop
0x1800051b0  lea     rcx, [rbp+3Fh+var_58]
0x1800051b4  call    ??1?$_Tree@V?$_Tmap_traits@Uhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@U?$less@Uhstring@winrt@@@std@@V?$allocator@U?$pair@$$CBUhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@@std@@@8@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::less<winrt::hstring>,std::allocator<std::pair<winrt::hstring const,winrt::Microsoft::Windows::Workloads::ApiInfo>>,0>>::~_Tree<std::_Tmap_traits<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::less<winrt::hstring>,std::allocator<std::pair<winrt::hstring const,winrt::Microsoft::Windows::Workloads::ApiInfo>>,0>>(void)
0x1800051b9  mov     r14, [rsp+110h+var_D0]
0x1800051be  xor     ecx, ecx; lpModuleName
0x1800051c0  call    cs:__imp_GetModuleHandleW
0x1800051c6  mov     rcx, rax; hModule
0x1800051c9  lea     rdx, aGWsaifabricser; "g_WSAIFabricService"
0x1800051d0  call    cs:__imp_GetProcAddress
0x1800051d6  test    rax, rax
0x1800051d9  jz      short loc_1800051E5
0x1800051db  mov     dword ptr [rdi+88h], 1
0x1800051e5  mov     r12, [rsp+110h+var_C8]
0x1800051ea  mov     rbx, [r12]
0x1800051ee  mov     esi, 0FFFFFFFFh
0x1800051f3  test    rbx, rbx
0x1800051f6  jz      short loc_180005222
0x1800051f8  mov     eax, esi
0x1800051fa  lock xadd [rbx+18h], eax
0x1800051ff  sub     eax, 1
0x180005202  jnz     loc_18000529F
0x180005208  call    WINRT_IMPL_GetProcessHeap
0x18000520d  mov     rcx, rax; hHeap
0x180005210  mov     r8, rbx; lpMem
0x180005213  xor     edx, edx; dwFlags
0x180005215  call    WINRT_IMPL_HeapFree
0x18000521a  mov     qword ptr [r12], 0
0x180005222  mov     rbx, [r15]
0x180005225  test    rbx, rbx
0x180005228  jz      short loc_18000524D
0x18000522a  lock xadd [rbx+18h], esi
0x18000522f  sub     esi, 1
0x180005232  jnz     short loc_1800052AE
0x180005234  call    WINRT_IMPL_GetProcessHeap
0x180005239  mov     rcx, rax; hHeap
0x18000523c  mov     r8, rbx; lpMem
0x18000523f  xor     edx, edx; dwFlags
0x180005241  call    WINRT_IMPL_HeapFree
0x180005246  mov     qword ptr [r15], 0
0x18000524d  mov     rcx, [rsp+110h+var_C0]
0x180005252  cmp     qword ptr [rcx], 0
0x180005256  jz      short loc_18000525E
0x180005258  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000525d  nop
0x18000525e  cmp     qword ptr [r14], 0
0x180005262  jz      short loc_18000526D
0x180005264  mov     rcx, r14
0x180005267  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000526c  nop
0x18000526d  cmp     qword ptr [r13+0], 0
0x180005272  jz      short loc_18000527C
0x180005274  mov     rcx, r13
0x180005277  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000527c  mov     rax, rdi
0x18000527f  mov     rcx, [rbp+3Fh+var_48]
0x180005283  xor     rcx, rsp; StackCookie
0x180005286  call    __security_check_cookie
0x18000528b  add     rsp, 0D8h
0x180005292  pop     r15
0x180005294  pop     r14
0x180005296  pop     r13
0x180005298  pop     r12
0x18000529a  pop     rdi
0x18000529b  pop     rsi
0x18000529c  pop     rbx
0x18000529d  pop     rbp
0x18000529e  retn
0x18000529f  test    eax, eax
0x1800052a1  jns     loc_18000521A
0x1800052a7  call    cs:__imp_abort
0x1800052ae  test    esi, esi
0x1800052b0  jns     short loc_180005246
0x1800052b2  call    cs:__imp_abort
0x1800052b9  call    ?_Throw_tree_length_error@std@@YAXXZ; std::_Throw_tree_length_error(void)
0x1800052bf  mov     rcx, rbx; this
0x1800052c2  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
