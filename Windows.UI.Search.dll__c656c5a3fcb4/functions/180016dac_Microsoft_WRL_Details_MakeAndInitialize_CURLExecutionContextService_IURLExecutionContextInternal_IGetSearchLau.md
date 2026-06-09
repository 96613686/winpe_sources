# Microsoft::WRL::Details::MakeAndInitialize<CURLExecutionContextService,IURLExecutionContextInternal,IGetSearchLaunchModeForWindow * &>(IURLExecutionContextInternal * *,IGetSearchLaunchModeForWindow * &)

- ea: `0x180016dac`
- end: `0x180016ea1`
- name: `??$MakeAndInitialize@VCURLExecutionContextService@@UIURLExecutionContextInternal@@AEAPEAUIGetSearchLaunchModeForWindow@@@Details@WRL@Microsoft@@YAJPEAPEAUIURLExecutionContextInternal@@AEAPEAUIGetSearchLaunchModeForWindow@@@Z`
- size: `245`
- prototype: `__int64 __fastcall(_QWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800115e0`

## callees

- `0x180003d70`
- `0x180007b3c`
- `0x18000e084`
- `0x180016dac`
- `0x180016ea8`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x180016e3b`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x180016e3b`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180016e16`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180016e16`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<CURLExecutionContextService,IURLExecutionContextInternal,IGetSearchLaunchModeForWindow * &>(
        _QWORD *a1,
        __int64 *a2)
{
  CURLExecutionContextService *v4; // rax
  HRESULT AgileReference; // ebx
  void **v6; // rdi
  __int64 v7; // rbp
  CURLExecutionContextService *v9; // [rsp+40h] [rbp+8h] BYREF
  CURLExecutionContextService *v10; // [rsp+50h] [rbp+18h]
  CURLExecutionContextService *v11; // [rsp+58h] [rbp+20h]

  *a1 = 0;
  v4 = (CURLExecutionContextService *)operator new(0x78u, (const struct std::nothrow_t *)std::nothrow);
  v9 = v4;
  v10 = v4;
  if ( v4 )
  {
    v11 = v4;
    v6 = (void **)CURLExecutionContextService::CURLExecutionContextService(v4);
    v9 = 0;
    v7 = *a2;
    AgileReference = PSCreateMemoryPropertyStore(&GUID_71604b0f_97b0_4764_8577_2f13e98a1422, v6 + 13);
    if ( AgileReference < 0
      || (Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(v6 + 14),
          AgileReference = RoGetAgileReference(0, &GUID_f88ddd9c_e19f_4ffb_9bf7_6199f8e45940, v7, v6 + 14),
          AgileReference < 0) )
    {
      if ( v6 )
        (*((void (__fastcall **)(void **))*v6 + 2))(v6);
    }
    else
    {
      AgileReference = (*(__int64 (__fastcall **)(void **, GUID *, _QWORD *))*v6)(
                         v6,
                         &GUID_f01d35df_ec24_4e75_8085_cf9ebe01274c,
                         a1);
      (*((void (__fastcall **)(void **))*v6 + 2))(v6);
    }
  }
  else
  {
    AgileReference = -2147024882;
  }
  Microsoft::WRL::Details::MakeAllocator<CSearchActivatedEventArgs>::~MakeAllocator<CSearchActivatedEventArgs>(&v9);
  return (unsigned int)AgileReference;
}

```

## disassembly

```asm
0x180016dac  mov     [rsp+arg_8], rbx
0x180016db1  push    rbp
0x180016db2  push    rsi
0x180016db3  push    rdi
0x180016db4  sub     rsp, 20h
0x180016db8  mov     rbx, rdx
0x180016dbb  mov     rsi, rcx
0x180016dbe  mov     qword ptr [rcx], 0
0x180016dc5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180016dcc  mov     ecx, 78h ; 'x'; unsigned __int64
0x180016dd1  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180016dd6  mov     [rsp+38h+arg_0], rax
0x180016ddb  mov     [rsp+38h+arg_10], rax
0x180016de0  test    rax, rax
0x180016de3  jnz     short loc_180016DEF
0x180016de5  mov     ebx, 8007000Eh
0x180016dea  jmp     loc_180016E88
0x180016def  mov     [rsp+38h+arg_18], rax
0x180016df4  mov     rcx, rax; this
0x180016df7  call    ??0CURLExecutionContextService@@QEAA@XZ; CURLExecutionContextService::CURLExecutionContextService(void)
0x180016dfc  mov     rdi, rax
0x180016dff  mov     [rsp+38h+arg_0], 0
0x180016e08  mov     rbp, [rbx]
0x180016e0b  lea     rdx, [rax+68h]; ppv
0x180016e0f  lea     rcx, _GUID_71604b0f_97b0_4764_8577_2f13e98a1422; riid
0x180016e16  call    cs:__imp_PSCreateMemoryPropertyStore
0x180016e1c  mov     ebx, eax
0x180016e1e  test    eax, eax
0x180016e20  js      short loc_180016E73
0x180016e22  lea     rcx, [rdi+70h]
0x180016e26  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180016e2b  lea     r9, [rdi+70h]
0x180016e2f  mov     r8, rbp
0x180016e32  lea     rdx, _GUID_f88ddd9c_e19f_4ffb_9bf7_6199f8e45940
0x180016e39  xor     ecx, ecx
0x180016e3b  call    cs:__imp_RoGetAgileReference
0x180016e41  mov     ebx, eax
0x180016e43  test    eax, eax
0x180016e45  js      short loc_180016E73
0x180016e47  mov     rax, [rdi]
0x180016e4a  mov     r8, rsi
0x180016e4d  lea     rdx, _GUID_f01d35df_ec24_4e75_8085_cf9ebe01274c
0x180016e54  mov     rcx, rdi
0x180016e57  mov     rax, [rax]
0x180016e5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e5f  mov     ebx, eax
0x180016e61  mov     rcx, [rdi]
0x180016e64  mov     rax, [rcx+10h]
0x180016e68  mov     rcx, rdi
0x180016e6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e70  nop
0x180016e71  jmp     short loc_180016E88
0x180016e73  test    rdi, rdi
0x180016e76  jz      short loc_180016E88
0x180016e78  mov     rax, [rdi]
0x180016e7b  mov     rcx, rdi
0x180016e7e  mov     rax, [rax+10h]
0x180016e82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e87  nop
0x180016e88  lea     rcx, [rsp+38h+arg_0]
0x180016e8d  call    ??1?$MakeAllocator@VCSearchActivatedEventArgs@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<CSearchActivatedEventArgs>::~MakeAllocator<CSearchActivatedEventArgs>(void)
0x180016e92  mov     eax, ebx
0x180016e94  mov     rbx, [rsp+38h+arg_8]
0x180016e99  add     rsp, 20h
0x180016e9d  pop     rdi
0x180016e9e  pop     rsi
0x180016e9f  pop     rbp
0x180016ea0  retn
```
