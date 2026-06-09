# AppHostNavigatorTemplate<AppHostMergedConfigNavigator,IAppHostMergedConfigNavigator,MergedConfigTree>::~AppHostNavigatorTemplate<AppHostMergedConfigNavigator,IAppHostMergedConfigNavigator,MergedConfigTree>(void)

- ea: `0x1800069e4`
- end: `0x180006a2b`
- name: `??1?$AppHostNavigatorTemplate@VAppHostMergedConfigNavigator@@UIAppHostMergedConfigNavigator@@VMergedConfigTree@@@@UEAA@XZ`
- size: `71`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180006a50`

## callees

- `0x1800039b0`
- `0x180003a1c`

## pseudocode

```c
void __fastcall AppHostNavigatorTemplate<AppHostMergedConfigNavigator,IAppHostMergedConfigNavigator,MergedConfigTree>::~AppHostNavigatorTemplate<AppHostMergedConfigNavigator,IAppHostMergedConfigNavigator,MergedConfigTree>(
        __int64 a1)
{
  *(_QWORD *)a1 = &AppHostMergedConfigNavigator::`vftable'{for `IXPathNavigator'};
  *(_QWORD *)(a1 + 8) = &AppHostNavigatorTemplate<AppHostMergedConfigNavigator,IAppHostMergedConfigNavigator,MergedConfigTree>::`vftable'{for `ATL::IDispatchImpl<IAppHostMergedConfigNavigator,&__s_GUID const _GUID_6bf27412_bb61_40c6_9ad6_1a790cbd0cb8,&_GUID const LIBID_AppHostNavigatorsLibrary,1,0,ATL::CComTypeInfoHolder>'};
  *(_QWORD *)(a1 + 16) = &AppHostMergedConfigNavigator::`vftable'{for `InvasivePtrObject'};
  InvasivePtr<ConfigLocationsTree>::Reset((InvasivePtrObject **)(a1 + 40));
  *(_QWORD *)(a1 + 16) = &InvasivePtrObject::`vftable';
  ModuleRefCounter::Release();
}

```

## disassembly

```asm
0x1800069e4  push    rbx
0x1800069e6  sub     rsp, 20h
0x1800069ea  lea     rax, ??_7AppHostMergedConfigNavigator@@6BIXPathNavigator@@@; const AppHostMergedConfigNavigator::`vftable'{for `IXPathNavigator'}
0x1800069f1  mov     rbx, rcx
0x1800069f4  mov     [rcx], rax
0x1800069f7  lea     rax, ??_7?$AppHostNavigatorTemplate@VAppHostMergedConfigNavigator@@UIAppHostMergedConfigNavigator@@VMergedConfigTree@@@@6B?$IDispatchImpl@UIAppHostMergedConfigNavigator@@$1?_GUID_6bf27412_bb61_40c6_9ad6_1a790cbd0cb8@@3U__s_GUID@@B$1?LIBID_AppHostNavigatorsLibrary@@3U_GUID@@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@@; const AppHostNavigatorTemplate<AppHostMergedConfigNavigator,IAppHostMergedConfigNavigator,MergedConfigTree>::`vftable'{for `ATL::IDispatchImpl<IAppHostMergedConfigNavigator,&__s_GUID const _GUID_6bf27412_bb61_40c6_9ad6_1a790cbd0cb8,&_GUID const LIBID_AppHostNavigatorsLibrary,1,0,ATL::CComTypeInfoHolder>'}
0x1800069fe  mov     [rcx+8], rax
0x180006a02  lea     rax, ??_7AppHostMergedConfigNavigator@@6BInvasivePtrObject@@@; const AppHostMergedConfigNavigator::`vftable'{for `InvasivePtrObject'}
0x180006a09  mov     [rcx+10h], rax
0x180006a0d  add     rcx, 28h ; '('
0x180006a11  call    ?Reset@?$InvasivePtr@VConfigLocationsTree@@@@QEAAXXZ; InvasivePtr<ConfigLocationsTree>::Reset(void)
0x180006a16  lea     rax, ??_7InvasivePtrObject@@6B@; const InvasivePtrObject::`vftable'
0x180006a1d  mov     [rbx+10h], rax
0x180006a21  add     rsp, 20h
0x180006a25  pop     rbx
0x180006a26  jmp     ?Release@ModuleRefCounter@@SAXXZ; ModuleRefCounter::Release(void)
```
