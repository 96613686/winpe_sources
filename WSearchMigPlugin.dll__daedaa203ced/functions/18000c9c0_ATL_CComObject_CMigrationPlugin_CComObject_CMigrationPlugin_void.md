# ATL::CComObject<CMigrationPlugin>::~CComObject<CMigrationPlugin>(void)

- ea: `0x18000c9c0`
- end: `0x18000ca3e`
- name: `??1?$CComObject@VCMigrationPlugin@@@ATL@@UEAA@XZ`
- size: `126`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000ce40`

## callees

- `0x18000c9c0`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ca32`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ca32`

## pseudocode

```c
void __fastcall ATL::CComObject<CMigrationPlugin>::~CComObject<CMigrationPlugin>(__int64 a1)
{
  *(_DWORD *)(a1 + 48) = -1073741823;
  *(_QWORD *)a1 = &ATL::CComObject<CMigrationPlugin>::`vftable'{for `ATL::IDispatchImpl<IDiscovery,&__s_GUID const _GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822c,&__s_GUID const _GUID_f31091e5_b0a8_11d6_b6fc_005056c00008,2,0,ATL::CComTypeInfoHolder>'};
  *(_QWORD *)(a1 + 8) = &ATL::CComObject<CMigrationPlugin>::`vftable'{for `ATL::IDispatchImpl<IPreGather,&__s_GUID const _GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822f,&__s_GUID const _GUID_f31091e5_b0a8_11d6_b6fc_005056c00008,2,0,ATL::CComTypeInfoHolder>'};
  *(_QWORD *)(a1 + 16) = &ATL::CComObject<CMigrationPlugin>::`vftable'{for `ATL::IDispatchImpl<IPostGather,&__s_GUID const _GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a18230,&__s_GUID const _GUID_f31091e5_b0a8_11d6_b6fc_005056c00008,2,0,ATL::CComTypeInfoHolder>'};
  *(_QWORD *)(a1 + 24) = &ATL::CComObject<CMigrationPlugin>::`vftable'{for `ATL::IDispatchImpl<IPreApply,&__s_GUID const _GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822d,&__s_GUID const _GUID_f31091e5_b0a8_11d6_b6fc_005056c00008,2,0,ATL::CComTypeInfoHolder>'};
  *(_QWORD *)(a1 + 32) = &ATL::CComObject<CMigrationPlugin>::`vftable'{for `ATL::IDispatchImpl<IPostApply,&__s_GUID const _GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822e,&__s_GUID const _GUID_f31091e5_b0a8_11d6_b6fc_005056c00008,2,0,ATL::CComTypeInfoHolder>'};
  *(_QWORD *)(a1 + 40) = &ATL::CComObject<CMigrationPlugin>::`vftable'{for `ATL::IProvideClassInfoImpl<&__s_GUID const _GUID_617c0a54_d12e_4340_87e7_01cc31bde762,&public: static _GUID ATL::CAtlModule::m_libid,1,0,ATL::CComTypeInfoHolder>'};
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  if ( *(_BYTE *)(a1 + 96) )
  {
    *(_BYTE *)(a1 + 96) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 56));
  }
}

```

## disassembly

```asm
0x18000c9c0  push    rbx
0x18000c9c2  sub     rsp, 20h
0x18000c9c6  mov     dword ptr [rcx+30h], 0C0000001h
0x18000c9cd  lea     rax, ??_7?$CComObject@VCMigrationPlugin@@@ATL@@6B?$IDispatchImpl@UIDiscovery@@$1?_GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822c@@3U__s_GUID@@B$1?_GUID_f31091e5_b0a8_11d6_b6fc_005056c00008@@3U3@B$01$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CMigrationPlugin>::`vftable'{for `ATL::IDispatchImpl<IDiscovery,&__s_GUID const _GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822c,&__s_GUID const _GUID_f31091e5_b0a8_11d6_b6fc_005056c00008,2,0,ATL::CComTypeInfoHolder>'}
0x18000c9d4  mov     [rcx], rax
0x18000c9d7  mov     rbx, rcx
0x18000c9da  lea     rax, ??_7?$CComObject@VCMigrationPlugin@@@ATL@@6B?$IDispatchImpl@UIPreGather@@$1?_GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822f@@3U__s_GUID@@B$1?_GUID_f31091e5_b0a8_11d6_b6fc_005056c00008@@3U3@B$01$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CMigrationPlugin>::`vftable'{for `ATL::IDispatchImpl<IPreGather,&__s_GUID const _GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822f,&__s_GUID const _GUID_f31091e5_b0a8_11d6_b6fc_005056c00008,2,0,ATL::CComTypeInfoHolder>'}
0x18000c9e1  mov     [rcx+8], rax
0x18000c9e5  lea     rax, ??_7?$CComObject@VCMigrationPlugin@@@ATL@@6B?$IDispatchImpl@UIPostGather@@$1?_GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a18230@@3U__s_GUID@@B$1?_GUID_f31091e5_b0a8_11d6_b6fc_005056c00008@@3U3@B$01$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CMigrationPlugin>::`vftable'{for `ATL::IDispatchImpl<IPostGather,&__s_GUID const _GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a18230,&__s_GUID const _GUID_f31091e5_b0a8_11d6_b6fc_005056c00008,2,0,ATL::CComTypeInfoHolder>'}
0x18000c9ec  mov     [rcx+10h], rax
0x18000c9f0  lea     rax, ??_7?$CComObject@VCMigrationPlugin@@@ATL@@6B?$IDispatchImpl@UIPreApply@@$1?_GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822d@@3U__s_GUID@@B$1?_GUID_f31091e5_b0a8_11d6_b6fc_005056c00008@@3U3@B$01$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CMigrationPlugin>::`vftable'{for `ATL::IDispatchImpl<IPreApply,&__s_GUID const _GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822d,&__s_GUID const _GUID_f31091e5_b0a8_11d6_b6fc_005056c00008,2,0,ATL::CComTypeInfoHolder>'}
0x18000c9f7  mov     [rcx+18h], rax
0x18000c9fb  lea     rax, ??_7?$CComObject@VCMigrationPlugin@@@ATL@@6B?$IDispatchImpl@UIPostApply@@$1?_GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822e@@3U__s_GUID@@B$1?_GUID_f31091e5_b0a8_11d6_b6fc_005056c00008@@3U3@B$01$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CMigrationPlugin>::`vftable'{for `ATL::IDispatchImpl<IPostApply,&__s_GUID const _GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822e,&__s_GUID const _GUID_f31091e5_b0a8_11d6_b6fc_005056c00008,2,0,ATL::CComTypeInfoHolder>'}
0x18000ca02  mov     [rcx+20h], rax
0x18000ca06  lea     rax, ??_7?$CComObject@VCMigrationPlugin@@@ATL@@6B?$IProvideClassInfoImpl@$1?_GUID_617c0a54_d12e_4340_87e7_01cc31bde762@@3U__s_GUID@@B$1?m_libid@CAtlModule@ATL@@2U_GUID@@A$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CMigrationPlugin>::`vftable'{for `ATL::IProvideClassInfoImpl<&__s_GUID const _GUID_617c0a54_d12e_4340_87e7_01cc31bde762,&_GUID ATL::CAtlModule::m_libid,1,0,ATL::CComTypeInfoHolder>'}
0x18000ca0d  mov     [rcx+28h], rax
0x18000ca11  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000ca18  mov     rax, [rcx]
0x18000ca1b  mov     rax, [rax+10h]
0x18000ca1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca24  lea     rcx, [rbx+38h]; lpCriticalSection
0x18000ca28  cmp     byte ptr [rcx+28h], 0
0x18000ca2c  jz      short loc_18000CA38
0x18000ca2e  mov     byte ptr [rcx+28h], 0
0x18000ca32  call    cs:__imp_DeleteCriticalSection
0x18000ca38  add     rsp, 20h
0x18000ca3c  pop     rbx
0x18000ca3d  retn
```
