# AppHostNavigatorTemplate<AppHostConfigLocationsNavigator,IAppHostConfigLocationsNavigator,ConfigLocationsTree>::~AppHostNavigatorTemplate<AppHostConfigLocationsNavigator,IAppHostConfigLocationsNavigator,ConfigLocationsTree>(void)

- ea: `0x1800020f0`
- end: `0x180002137`
- name: `??1?$AppHostNavigatorTemplate@VAppHostConfigLocationsNavigator@@UIAppHostConfigLocationsNavigator@@VConfigLocationsTree@@@@UEAA@XZ`
- size: `71`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180002270`

## callees

- `0x1800039b0`
- `0x180003a1c`

## pseudocode

```c
void __fastcall AppHostNavigatorTemplate<AppHostConfigLocationsNavigator,IAppHostConfigLocationsNavigator,ConfigLocationsTree>::~AppHostNavigatorTemplate<AppHostConfigLocationsNavigator,IAppHostConfigLocationsNavigator,ConfigLocationsTree>(
        __int64 a1)
{
  *(_QWORD *)a1 = &AppHostNavigatorTemplate<AppHostConfigLocationsNavigator,IAppHostConfigLocationsNavigator,ConfigLocationsTree>::`vftable'{for `IXPathNavigator'};
  *(_QWORD *)(a1 + 8) = &AppHostNavigatorTemplate<AppHostConfigLocationsNavigator,IAppHostConfigLocationsNavigator,ConfigLocationsTree>::`vftable'{for `ATL::IDispatchImpl<IAppHostConfigLocationsNavigator,&__s_GUID const _GUID_9dfa9beb_c15f_450e_bf3a_1d56c67b5c0b,&_GUID const LIBID_AppHostNavigatorsLibrary,1,0,ATL::CComTypeInfoHolder>'};
  *(_QWORD *)(a1 + 16) = &AppHostConfigLocationsNavigator::`vftable'{for `InvasivePtrObject'};
  InvasivePtr<ConfigLocationsTree>::Reset((InvasivePtrObject **)(a1 + 40));
  *(_QWORD *)(a1 + 16) = &InvasivePtrObject::`vftable';
  ModuleRefCounter::Release();
}

```

## disassembly

```asm
0x1800020f0  push    rbx
0x1800020f2  sub     rsp, 20h
0x1800020f6  lea     rax, ??_7?$AppHostNavigatorTemplate@VAppHostConfigLocationsNavigator@@UIAppHostConfigLocationsNavigator@@VConfigLocationsTree@@@@6BIXPathNavigator@@@; const AppHostNavigatorTemplate<AppHostConfigLocationsNavigator,IAppHostConfigLocationsNavigator,ConfigLocationsTree>::`vftable'{for `IXPathNavigator'}
0x1800020fd  mov     rbx, rcx
0x180002100  mov     [rcx], rax
0x180002103  lea     rax, ??_7?$AppHostNavigatorTemplate@VAppHostConfigLocationsNavigator@@UIAppHostConfigLocationsNavigator@@VConfigLocationsTree@@@@6B?$IDispatchImpl@UIAppHostConfigLocationsNavigator@@$1?_GUID_9dfa9beb_c15f_450e_bf3a_1d56c67b5c0b@@3U__s_GUID@@B$1?LIBID_AppHostNavigatorsLibrary@@3U_GUID@@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@@; const AppHostNavigatorTemplate<AppHostConfigLocationsNavigator,IAppHostConfigLocationsNavigator,ConfigLocationsTree>::`vftable'{for `ATL::IDispatchImpl<IAppHostConfigLocationsNavigator,&__s_GUID const _GUID_9dfa9beb_c15f_450e_bf3a_1d56c67b5c0b,&_GUID const LIBID_AppHostNavigatorsLibrary,1,0,ATL::CComTypeInfoHolder>'}
0x18000210a  mov     [rcx+8], rax
0x18000210e  lea     rax, ??_7AppHostConfigLocationsNavigator@@6BInvasivePtrObject@@@; const AppHostConfigLocationsNavigator::`vftable'{for `InvasivePtrObject'}
0x180002115  mov     [rcx+10h], rax
0x180002119  add     rcx, 28h ; '('
0x18000211d  call    ?Reset@?$InvasivePtr@VConfigLocationsTree@@@@QEAAXXZ; InvasivePtr<ConfigLocationsTree>::Reset(void)
0x180002122  lea     rax, ??_7InvasivePtrObject@@6B@; const InvasivePtrObject::`vftable'
0x180002129  mov     [rbx+10h], rax
0x18000212d  add     rsp, 20h
0x180002131  pop     rbx
0x180002132  jmp     ?Release@ModuleRefCounter@@SAXXZ; ModuleRefCounter::Release(void)
```
