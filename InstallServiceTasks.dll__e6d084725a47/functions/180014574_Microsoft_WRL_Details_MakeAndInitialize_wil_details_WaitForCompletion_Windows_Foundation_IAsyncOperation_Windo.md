# Microsoft::WRL::Details::MakeAndInitialize<`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *> *>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate,`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *> *>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate,>(`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *> *>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate * *)

- ea: `0x180014574`
- end: `0x1800146c3`
- name: `??$MakeAndInitialize@VCompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@V1?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@@23@YAJ01K2@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVCompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@@Z`
- size: `335`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180014b44`

## callees

- `0x18000398c`
- `0x180006f08`
- `0x18000760c`
- `0x18000912c`
- `0x18000a958`
- `0x18000d490`
- `0x180014574`
- `0x180015380`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18001463a`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18001463a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014648`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014648`

## string_xrefs

- `0x1800146a6`: `onecore\internal\sdk\inc\wil\opensource/wil/winrt.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ___MakeAndInitialize_VCompletionDelegate__1____WaitForCompletion_PEAU__IAsyncOperation_PEAU__IVectorView_PEAVAppInstallItem_InstallControl_Preview_Store_ApplicationModel_Windows___Collections_Foundation_Windows___Foundation_Windows___details_wil__YAJPEAU__IAsyncOperation_PEAU__IVectorView_PEAVAppInstallItem_InstallControl_Preview_Store_ApplicationModel_Windows___Collections_Foundation_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__KPEA_N_Z_V1_1____WaitForCompletion_PEAU__IAsyncOperation_PEAU__IVectorView_PEAVAppInstallItem_InstallControl_Preview_Store_ApplicationModel_Windows___Collections_Foundation_Windows___Foundation_Windows___23_YAJ01K2_Z___V_Details_WRL_Microsoft__YAJPEAPEAVCompletionDelegate__1____WaitForCompletion_PEAU__IAsyncOperation_PEAU__IVectorView_PEAVAppInstallItem_InstallControl_Preview_Store_ApplicationModel_Windows___Collections_Foundation_Windows___Foundation_Windows___details_wil__YAJPEAU__IAsyncOperation_PEAU__IVectorView_PEAVAppInstallItem_InstallControl_Preview_Store_ApplicationModel_Windows___Collections_Foundation_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__KPEA_N_Z__Z(
        _QWORD *a1)
{
  _DWORD *v2; // rbx
  unsigned int v3; // edi
  wil::details *v4; // rcx
  HANDLE Event; // rbp
  int LastErrorFailHr; // eax
  int v8; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  _DWORD *v10; // [rsp+40h] [rbp+8h] BYREF
  _DWORD *v11; // [rsp+48h] [rbp+10h] BYREF

  *a1 = 0;
  v2 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  v11 = v2;
  if ( v2 )
  {
    *(_QWORD *)v2 = &Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *>::`vftable';
    Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v2 + 2));
    v2[11] = 1;
    *(_QWORD *)v2 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *>'};
    *((_QWORD *)v2 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v2 = &`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *> *>'::`2'::CompletionDelegate::`vftable';
    *((_QWORD *)v2 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    v2[12] = 0;
    *((_QWORD *)v2 + 7) = 0;
    v10 = v2;
    v11 = 0;
    Event = CreateEventExW(0, 0, 0, 0x1F0003u);
    if ( Event )
    {
      GetLastError();
      _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
        v2 + 14,
        Event);
    }
    else
    {
      LastErrorFailHr = wil::details::GetLastErrorFailHr(v4);
      v3 = LastErrorFailHr;
      if ( LastErrorFailHr < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x62B,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/winrt.h",
          (const char *)(unsigned int)LastErrorFailHr,
          v8);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v10);
        goto LABEL_8;
      }
    }
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v2 + 8LL))(v2);
    *a1 = v2;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v10);
    v3 = 0;
  }
  else
  {
    v3 = -2147024882;
  }
LABEL_8:
  __1__MakeAllocator_VCompletionDelegate__1____WaitForCompletion_PEAU__IAsyncOperation_PEAU__IVectorView_PEAVAppInstallItem_InstallControl_Preview_Store_ApplicationModel_Windows___Collections_Foundation_Windows___Foundation_Windows___details_wil__YAJPEAU__IAsyncOperation_PEAU__IVectorView_PEAVAppInstallItem_InstallControl_Preview_Store_ApplicationModel_Windows___Collections_Foundation_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__KPEA_N_Z__Details_WRL_Microsoft__QEAA_XZ(&v11);
  return v3;
}

```

## disassembly

```asm
0x180014574  mov     [rsp+arg_10], rbx
0x180014579  push    rbp
0x18001457a  push    rsi
0x18001457b  push    rdi; int
0x18001457c  sub     rsp, 20h
0x180014580  mov     rsi, rcx
0x180014583  mov     qword ptr [rcx], 0
0x18001458a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180014591  mov     ecx, 40h ; '@'; unsigned __int64
0x180014596  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001459b  mov     rbx, rax
0x18001459e  mov     [rsp+38h+arg_8], rax
0x1800145a3  test    rax, rax
0x1800145a6  jnz     short loc_1800145B2
0x1800145a8  mov     edi, 8007000Eh
0x1800145ad  jmp     loc_18001467A
0x1800145b2  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *>::`vftable'
0x1800145b9  mov     [rbx], rax
0x1800145bc  lea     rdi, [rbx+8]
0x1800145c0  mov     rcx, rdi; this
0x1800145c3  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x1800145c8  mov     dword ptr [rbx+2Ch], 1
0x1800145cf  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *>'}
0x1800145d6  mov     [rbx], rax
0x1800145d9  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800145e0  mov     [rdi], rax
0x1800145e3  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800145ea  test    rcx, rcx
0x1800145ed  jz      short loc_1800145FC
0x1800145ef  mov     rax, [rcx]
0x1800145f2  mov     rax, [rax+8]
0x1800145f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800145fb  nop
0x1800145fc  lea     rax, ??_7CompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@6B?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@45@@; const `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *> *>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *>'}
0x180014603  mov     [rbx], rax
0x180014606  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18001460d  mov     [rdi], rax
0x180014610  mov     dword ptr [rbx+30h], 0
0x180014617  mov     qword ptr [rbx+38h], 0
0x18001461f  mov     [rsp+38h+arg_0], rbx
0x180014624  mov     [rsp+38h+arg_8], 0
0x18001462d  mov     r9d, 1F0003h; dwDesiredAccess
0x180014633  xor     r8d, r8d; dwFlags
0x180014636  xor     edx, edx; lpName
0x180014638  xor     ecx, ecx; lpEventAttributes
0x18001463a  call    cs:__imp_CreateEventExW
0x180014640  mov     rbp, rax
0x180014643  test    rax, rax
0x180014646  jz      short loc_180014693
0x180014648  call    cs:__imp_GetLastError
0x18001464e  mov     rdx, rbp
0x180014651  lea     rcx, [rbx+38h]
0x180014655  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18001465a  nop
0x18001465b  mov     rax, [rbx]
0x18001465e  mov     rcx, rbx
0x180014661  mov     rax, [rax+8]
0x180014665  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001466a  nop
0x18001466b  mov     [rsi], rbx
0x18001466e  lea     rcx, [rsp+38h+arg_0]
0x180014673  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180014678  xor     edi, edi
0x18001467a  lea     rcx, [rsp+38h+arg_8]
0x18001467f  call    ??1?$MakeAllocator@VCompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *> *>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate>::~MakeAllocator<`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *> *>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *> *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate>(void)
0x180014684  mov     eax, edi
0x180014686  mov     rbx, [rsp+38h+arg_10]
0x18001468b  add     rsp, 20h
0x18001468f  pop     rdi
0x180014690  pop     rsi
0x180014691  pop     rbp
0x180014692  retn
0x180014693  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180014698  mov     edi, eax
0x18001469a  test    eax, eax
0x18001469c  jns     short loc_18001465B
0x18001469e  mov     rcx, [rsp+38h]; this
0x1800146a3  mov     r9d, eax; char *
0x1800146a6  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800146ad  mov     edx, 62Bh; void *
0x1800146b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800146b7  lea     rcx, [rsp+38h+arg_0]
0x1800146bc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800146c1  jmp     short loc_18001467A
```
