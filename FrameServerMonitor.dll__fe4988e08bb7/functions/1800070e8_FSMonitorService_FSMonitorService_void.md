# FSMonitorService::~FSMonitorService(void)

- ea: `0x1800070e8`
- end: `0x1800071a5`
- name: `??1FSMonitorService@@MEAA@XZ`
- size: `189`
- prototype: `void __fastcall(FSMonitorService *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x1800072c0`

## callees

- `0x180003194`
- `0x1800032d0`
- `0x1800060e8`
- `0x180006f3c`
- `0x180006f9c`
- `0x180007068`
- `0x1800070e8`
- `0x18000cffc`
- `0x18000d4f8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007139`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007146`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007139`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007146`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000719e`

## pseudocode

```c
void __fastcall FSMonitorService::~FSMonitorService(FSMonitorService *this)
{
  __int64 v2; // rcx
  void *v3; // rdx

  *(_QWORD *)this = &FSMonitorService::`vftable';
  if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 0x10u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 14, &WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids, v2);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit((char *)this + 312);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 272));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
  CTUnkArray<IMFSensorDeviceIdInternal>::~CTUnkArray<IMFSensorDeviceIdInternal>((char *)this + 200);
  `vector destructor iterator'((char *)this + 168, 0x10u, 2u, (void (*)(void *))FSMWatcherEntry::~FSMWatcherEntry);
  CTUnkArray<IFSMemory>::~CTUnkArray<IFSMemory>((char *)this + 144);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    (wil::details **)this + 16,
    v3);
  wil::details::unique_storage<wil::details::resource_policy<_RPC_BINDING_VECTOR *,void (*)(_RPC_BINDING_VECTOR *),&void wil::details::WpRpcBindingVectorFree(_RPC_BINDING_VECTOR *),wistd::integral_constant<unsigned __int64,0>,_RPC_BINDING_VECTOR *,_RPC_BINDING_VECTOR *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RPC_BINDING_VECTOR *,void (*)(_RPC_BINDING_VECTOR *),&void wil::details::WpRpcBindingVectorFree(_RPC_BINDING_VECTOR *),wistd::integral_constant<unsigned __int64,0>,_RPC_BINDING_VECTOR *,_RPC_BINDING_VECTOR *,0,std::nullptr_t>>((char *)this + 96);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
}

```

## disassembly

```asm
0x1800070e8  push    rbx
0x1800070ea  sub     rsp, 20h
0x1800070ee  lea     rax, ??_7FSMonitorService@@6B@; const FSMonitorService::`vftable'
0x1800070f5  mov     rbx, rcx
0x1800070f8  mov     [rcx], rax
0x1800070fb  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180007100  cmp     al, 10h
0x180007102  jb      short loc_180007126
0x180007104  mov     r9, rcx
0x180007107  lea     r8, WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids
0x18000710e  mov     rcx, cs:WPP_GLOBAL_Control
0x180007115  mov     edx, 0Eh
0x18000711a  mov     rcx, [rcx+0D8h]
0x180007121  call    WPP_SF_q
0x180007126  lea     rcx, [rbx+138h]
0x18000712d  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180007132  lea     rcx, [rbx+110h]; lpCriticalSection
0x180007139  call    cs:__imp_DeleteCriticalSection
0x18000713f  lea     rcx, [rbx+0E8h]; lpCriticalSection
0x180007146  call    cs:__imp_DeleteCriticalSection
0x18000714c  lea     rcx, [rbx+0C8h]
0x180007153  call    ??1?$CTUnkArray@UIMFSensorDeviceIdInternal@@@@QEAA@XZ; CTUnkArray<IMFSensorDeviceIdInternal>::~CTUnkArray<IMFSensorDeviceIdInternal>(void)
0x180007158  mov     edx, 10h; unsigned __int64
0x18000715d  lea     rcx, [rbx+0A8h]; void *
0x180007164  lea     r9, ??1FSMWatcherEntry@@QEAA@XZ; void (*)(void *)
0x18000716b  lea     r8d, [rdx-0Eh]; unsigned __int64
0x18000716f  call    ??_I@YAXPEAX_K1P6AX0@Z@Z; `vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180007174  lea     rcx, [rbx+90h]
0x18000717b  call    ??1?$CTUnkArray@UIFSMemory@@@@QEAA@XZ; CTUnkArray<IFSMemory>::~CTUnkArray<IFSMemory>(void)
0x180007180  lea     rcx, [rbx+80h]
0x180007187  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000718c  lea     rcx, [rbx+60h]
0x180007190  call    ??1?$unique_storage@U?$resource_policy@PEAU_RPC_BINDING_VECTOR@@P6AXPEAU1@@Z$1?WpRpcBindingVectorFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RPC_BINDING_VECTOR *,void (*)(_RPC_BINDING_VECTOR *),&wil::details::WpRpcBindingVectorFree(_RPC_BINDING_VECTOR *),wistd::integral_constant<unsigned __int64,0>,_RPC_BINDING_VECTOR *,_RPC_BINDING_VECTOR *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RPC_BINDING_VECTOR *,void (*)(_RPC_BINDING_VECTOR *),&wil::details::WpRpcBindingVectorFree(_RPC_BINDING_VECTOR *),wistd::integral_constant<unsigned __int64,0>,_RPC_BINDING_VECTOR *,_RPC_BINDING_VECTOR *,0,std::nullptr_t>>(void)
0x180007195  lea     rcx, [rbx+30h]
0x180007199  add     rsp, 20h
0x18000719d  pop     rbx
0x18000719e  jmp     cs:__imp_DeleteCriticalSection
```
