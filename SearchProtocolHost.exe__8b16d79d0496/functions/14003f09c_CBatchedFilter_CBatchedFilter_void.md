# CBatchedFilter::~CBatchedFilter(void)

- ea: `0x14003f09c`
- end: `0x14003f1b5`
- name: `??1CBatchedFilter@@UEAA@XZ`
- size: `281`
- prototype: `void __fastcall(CBatchedFilter *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14003f4b0`

## callees

- `0x14000a108`
- `0x14003376c`
- `0x14003ea48`
- `0x14003f09c`
- `0x14003f7f0`
- `0x140041500`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003f17e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003f17e`

## pseudocode

```c
void __fastcall CBatchedFilter::~CBatchedFilter(CBatchedFilter *this)
{
  __int64 v2; // rcx
  void *v3; // rcx

  *(_QWORD *)this = &CBatchedFilter::`vftable';
  *((_QWORD *)this + 1) = &CBatchedFilter::`vftable'{for `IGenericFilter'};
  *((_QWORD *)this + 2) = &CBatchedFilter::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ITextFilter,IValueFilter,ISemanticFilter,IPersistStream,IInitializeWithStream>'};
  *((_QWORD *)this + 3) = &CBatchedFilter::`vftable'{for `IValueFilter'};
  *((_QWORD *)this + 4) = &CBatchedFilter::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ISemanticFilter,IPersistStream,IInitializeWithStream>'};
  *((_QWORD *)this + 5) = &CBatchedFilter::`vftable'{for `IPersistStream'};
  *((_QWORD *)this + 6) = &CBatchedFilter::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IInitializeWithStream>'};
  CBatchedFilter::Cleanup(this);
  v2 = *((_QWORD *)this + 28);
  if ( v2 )
  {
    std::_Destroy_range<std::allocator<std::unique_ptr<std::wstring>>>(v2, *((_QWORD *)this + 29));
    std::_Deallocate<16>(
      *((_QWORD *)this + 28),
      (*((_QWORD *)this + 30) - *((_QWORD *)this + 28)) & 0xFFFFFFFFFFFFFFF8uLL);
    *((_QWORD *)this + 28) = 0;
    *((_QWORD *)this + 29) = 0;
    *((_QWORD *)this + 30) = 0;
  }
  std::wstring::_Tidy_deallocate((char *)this + 192);
  std::wstring::_Tidy_deallocate((char *)this + 160);
  std::wstring::_Tidy_deallocate((char *)this + 128);
  v3 = (void *)*((_QWORD *)this + 15);
  *((_QWORD *)this + 15) = 0;
  if ( v3 )
    CoTaskMemFree(v3);
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>::InternalRelease((char *)this + 88);
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>::InternalRelease((char *)this + 80);
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>::InternalRelease((char *)this + 72);
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>::InternalRelease((char *)this + 64);
  *((_DWORD *)this + 15) = -1073741823;
}

```

## disassembly

```asm
0x14003f09c  push    rbx
0x14003f09e  sub     rsp, 20h
0x14003f0a2  lea     rax, ??_7CBatchedFilter@@6B@; const CBatchedFilter::`vftable'
0x14003f0a9  mov     rbx, rcx
0x14003f0ac  mov     [rcx], rax
0x14003f0af  lea     rax, ??_7CBatchedFilter@@6BIGenericFilter@@@; const CBatchedFilter::`vftable'{for `IGenericFilter'}
0x14003f0b6  mov     [rcx+8], rax
0x14003f0ba  lea     rax, ??_7CBatchedFilter@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UITextFilter@@UIValueFilter@@UISemanticFilter@@UIPersistStream@@UIInitializeWithStream@@@Details@WRL@Microsoft@@@; const CBatchedFilter::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ITextFilter,IValueFilter,ISemanticFilter,IPersistStream,IInitializeWithStream>'}
0x14003f0c1  mov     [rcx+10h], rax
0x14003f0c5  lea     rax, ??_7CBatchedFilter@@6BIValueFilter@@@; const CBatchedFilter::`vftable'{for `IValueFilter'}
0x14003f0cc  mov     [rcx+18h], rax
0x14003f0d0  lea     rax, ??_7CBatchedFilter@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UISemanticFilter@@UIPersistStream@@UIInitializeWithStream@@@Details@WRL@Microsoft@@@; const CBatchedFilter::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ISemanticFilter,IPersistStream,IInitializeWithStream>'}
0x14003f0d7  mov     [rcx+20h], rax
0x14003f0db  lea     rax, ??_7CBatchedFilter@@6BIPersistStream@@@; const CBatchedFilter::`vftable'{for `IPersistStream'}
0x14003f0e2  mov     [rcx+28h], rax
0x14003f0e6  lea     rax, ??_7CBatchedFilter@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIInitializeWithStream@@@Details@WRL@Microsoft@@@; const CBatchedFilter::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IInitializeWithStream>'}
0x14003f0ed  mov     [rcx+30h], rax
0x14003f0f1  call    ?Cleanup@CBatchedFilter@@AEAAXXZ; CBatchedFilter::Cleanup(void)
0x14003f0f6  mov     rcx, [rbx+0E0h]
0x14003f0fd  test    rcx, rcx
0x14003f100  jz      short loc_14003F149
0x14003f102  mov     rdx, [rbx+0E8h]
0x14003f109  call    ??$_Destroy_range@V?$allocator@V?$unique_ptr@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$default_delete@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@@std@@@std@@YAXPEAV?$unique_ptr@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$default_delete@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@0@QEAV10@AEAV?$allocator@V?$unique_ptr@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$default_delete@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::unique_ptr<std::wstring>>>(std::unique_ptr<std::wstring> *,std::unique_ptr<std::wstring> * const,std::allocator<std::unique_ptr<std::wstring>> &)
0x14003f10e  mov     rcx, [rbx+0E0h]
0x14003f115  mov     rdx, [rbx+0F0h]
0x14003f11c  sub     rdx, rcx
0x14003f11f  and     rdx, 0FFFFFFFFFFFFFFF8h
0x14003f123  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x14003f128  mov     qword ptr [rbx+0E0h], 0
0x14003f133  mov     qword ptr [rbx+0E8h], 0
0x14003f13e  mov     qword ptr [rbx+0F0h], 0
0x14003f149  lea     rcx, [rbx+0C0h]
0x14003f150  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14003f155  lea     rcx, [rbx+0A0h]
0x14003f15c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14003f161  lea     rcx, [rbx+80h]
0x14003f168  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14003f16d  mov     rcx, [rbx+78h]; pv
0x14003f171  mov     qword ptr [rbx+78h], 0
0x14003f179  test    rcx, rcx
0x14003f17c  jz      short loc_14003F184
0x14003f17e  call    cs:__imp_CoTaskMemFree
0x14003f184  lea     rcx, [rbx+58h]
0x14003f188  call    ?InternalRelease@?$ComPtr@UIApplicationExtensionStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>::InternalRelease(void)
0x14003f18d  lea     rcx, [rbx+50h]
0x14003f191  call    ?InternalRelease@?$ComPtr@UIApplicationExtensionStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>::InternalRelease(void)
0x14003f196  lea     rcx, [rbx+48h]
0x14003f19a  call    ?InternalRelease@?$ComPtr@UIApplicationExtensionStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>::InternalRelease(void)
0x14003f19f  lea     rcx, [rbx+40h]
0x14003f1a3  call    ?InternalRelease@?$ComPtr@UIApplicationExtensionStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationExtensionStatics>::InternalRelease(void)
0x14003f1a8  mov     dword ptr [rbx+3Ch], 0C0000001h
0x14003f1af  add     rsp, 20h
0x14003f1b3  pop     rbx
0x14003f1b4  retn
```
