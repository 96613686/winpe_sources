# AppHostNavigatorTemplate<AppHostConfigPathNavigator,IAppHostConfigPathNavigator,ConfigPathNavigationTree>::~AppHostNavigatorTemplate<AppHostConfigPathNavigator,IAppHostConfigPathNavigator,ConfigPathNavigationTree>(void)

- ea: `0x180004320`
- end: `0x180004367`
- name: `??1?$AppHostNavigatorTemplate@VAppHostConfigPathNavigator@@UIAppHostConfigPathNavigator@@VConfigPathNavigationTree@@@@UEAA@XZ`
- size: `71`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180004580`

## callees

- `0x1800039b0`
- `0x180003a1c`

## pseudocode

```c
void __fastcall AppHostNavigatorTemplate<AppHostConfigPathNavigator,IAppHostConfigPathNavigator,ConfigPathNavigationTree>::~AppHostNavigatorTemplate<AppHostConfigPathNavigator,IAppHostConfigPathNavigator,ConfigPathNavigationTree>(
        __int64 a1)
{
  *(_QWORD *)a1 = &AppHostNavigatorTemplate<AppHostConfigPathNavigator,IAppHostConfigPathNavigator,ConfigPathNavigationTree>::`vftable'{for `IXPathNavigator'};
  *(_QWORD *)(a1 + 8) = &AppHostNavigatorTemplate<AppHostConfigPathNavigator,IAppHostConfigPathNavigator,ConfigPathNavigationTree>::`vftable'{for `ATL::IDispatchImpl<IAppHostConfigPathNavigator,&__s_GUID const _GUID_a0601362_def3_4571_809b_5b856e5e5521,&_GUID const LIBID_AppHostNavigatorsLibrary,1,0,ATL::CComTypeInfoHolder>'};
  *(_QWORD *)(a1 + 16) = &AppHostConfigPathNavigator::`vftable'{for `InvasivePtrObject'};
  InvasivePtr<ConfigLocationsTree>::Reset((InvasivePtrObject **)(a1 + 40));
  *(_QWORD *)(a1 + 16) = &InvasivePtrObject::`vftable';
  ModuleRefCounter::Release();
}

```

## disassembly

```asm
0x180004320  push    rbx
0x180004322  sub     rsp, 20h
0x180004326  lea     rax, ??_7?$AppHostNavigatorTemplate@VAppHostConfigPathNavigator@@UIAppHostConfigPathNavigator@@VConfigPathNavigationTree@@@@6BIXPathNavigator@@@; const AppHostNavigatorTemplate<AppHostConfigPathNavigator,IAppHostConfigPathNavigator,ConfigPathNavigationTree>::`vftable'{for `IXPathNavigator'}
0x18000432d  mov     rbx, rcx
0x180004330  mov     [rcx], rax
0x180004333  lea     rax, ??_7?$AppHostNavigatorTemplate@VAppHostConfigPathNavigator@@UIAppHostConfigPathNavigator@@VConfigPathNavigationTree@@@@6B?$IDispatchImpl@UIAppHostConfigPathNavigator@@$1?_GUID_a0601362_def3_4571_809b_5b856e5e5521@@3U__s_GUID@@B$1?LIBID_AppHostNavigatorsLibrary@@3U_GUID@@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@@; const AppHostNavigatorTemplate<AppHostConfigPathNavigator,IAppHostConfigPathNavigator,ConfigPathNavigationTree>::`vftable'{for `ATL::IDispatchImpl<IAppHostConfigPathNavigator,&__s_GUID const _GUID_a0601362_def3_4571_809b_5b856e5e5521,&_GUID const LIBID_AppHostNavigatorsLibrary,1,0,ATL::CComTypeInfoHolder>'}
0x18000433a  mov     [rcx+8], rax
0x18000433e  lea     rax, ??_7AppHostConfigPathNavigator@@6BInvasivePtrObject@@@; const AppHostConfigPathNavigator::`vftable'{for `InvasivePtrObject'}
0x180004345  mov     [rcx+10h], rax
0x180004349  add     rcx, 28h ; '('
0x18000434d  call    ?Reset@?$InvasivePtr@VConfigLocationsTree@@@@QEAAXXZ; InvasivePtr<ConfigLocationsTree>::Reset(void)
0x180004352  lea     rax, ??_7InvasivePtrObject@@6B@; const InvasivePtrObject::`vftable'
0x180004359  mov     [rbx+10h], rax
0x18000435d  add     rsp, 20h
0x180004361  pop     rbx
0x180004362  jmp     ?Release@ModuleRefCounter@@SAXXZ; ModuleRefCounter::Release(void)
```
