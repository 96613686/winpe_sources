# AppHostNavigatorTemplate<AppHostRawConfigNavigator,IAppHostRawConfigNavigator,RawConfigTree>::~AppHostNavigatorTemplate<AppHostRawConfigNavigator,IAppHostRawConfigNavigator,RawConfigTree>(void)

- ea: `0x180008f80`
- end: `0x180008fc7`
- name: `??1?$AppHostNavigatorTemplate@VAppHostRawConfigNavigator@@UIAppHostRawConfigNavigator@@VRawConfigTree@@@@UEAA@XZ`
- size: `71`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180008fe0`

## callees

- `0x1800039b0`
- `0x180003a1c`

## pseudocode

```c
void __fastcall AppHostNavigatorTemplate<AppHostRawConfigNavigator,IAppHostRawConfigNavigator,RawConfigTree>::~AppHostNavigatorTemplate<AppHostRawConfigNavigator,IAppHostRawConfigNavigator,RawConfigTree>(
        __int64 a1)
{
  *(_QWORD *)a1 = &AppHostNavigatorTemplate<AppHostRawConfigNavigator,IAppHostRawConfigNavigator,RawConfigTree>::`vftable'{for `IXPathNavigator'};
  *(_QWORD *)(a1 + 8) = &AppHostNavigatorTemplate<AppHostRawConfigNavigator,IAppHostRawConfigNavigator,RawConfigTree>::`vftable'{for `ATL::IDispatchImpl<IAppHostRawConfigNavigator,&__s_GUID const _GUID_4f29aa5f_4a59_4e88_bc5a_a902f6ff1d86,&_GUID const LIBID_AppHostNavigatorsLibrary,1,0,ATL::CComTypeInfoHolder>'};
  *(_QWORD *)(a1 + 16) = &AppHostNavigatorTemplate<AppHostRawConfigNavigator,IAppHostRawConfigNavigator,RawConfigTree>::`vftable'{for `InvasivePtrObject'};
  InvasivePtr<ConfigLocationsTree>::Reset((InvasivePtrObject **)(a1 + 40));
  *(_QWORD *)(a1 + 16) = &InvasivePtrObject::`vftable';
  ModuleRefCounter::Release();
}

```

## disassembly

```asm
0x180008f80  push    rbx
0x180008f82  sub     rsp, 20h
0x180008f86  lea     rax, ??_7?$AppHostNavigatorTemplate@VAppHostRawConfigNavigator@@UIAppHostRawConfigNavigator@@VRawConfigTree@@@@6BIXPathNavigator@@@; const AppHostNavigatorTemplate<AppHostRawConfigNavigator,IAppHostRawConfigNavigator,RawConfigTree>::`vftable'{for `IXPathNavigator'}
0x180008f8d  mov     rbx, rcx
0x180008f90  mov     [rcx], rax
0x180008f93  lea     rax, ??_7?$AppHostNavigatorTemplate@VAppHostRawConfigNavigator@@UIAppHostRawConfigNavigator@@VRawConfigTree@@@@6B?$IDispatchImpl@UIAppHostRawConfigNavigator@@$1?_GUID_4f29aa5f_4a59_4e88_bc5a_a902f6ff1d86@@3U__s_GUID@@B$1?LIBID_AppHostNavigatorsLibrary@@3U_GUID@@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@@; const AppHostNavigatorTemplate<AppHostRawConfigNavigator,IAppHostRawConfigNavigator,RawConfigTree>::`vftable'{for `ATL::IDispatchImpl<IAppHostRawConfigNavigator,&__s_GUID const _GUID_4f29aa5f_4a59_4e88_bc5a_a902f6ff1d86,&_GUID const LIBID_AppHostNavigatorsLibrary,1,0,ATL::CComTypeInfoHolder>'}
0x180008f9a  mov     [rcx+8], rax
0x180008f9e  lea     rax, ??_7?$AppHostNavigatorTemplate@VAppHostRawConfigNavigator@@UIAppHostRawConfigNavigator@@VRawConfigTree@@@@6BInvasivePtrObject@@@; const AppHostNavigatorTemplate<AppHostRawConfigNavigator,IAppHostRawConfigNavigator,RawConfigTree>::`vftable'{for `InvasivePtrObject'}
0x180008fa5  mov     [rcx+10h], rax
0x180008fa9  add     rcx, 28h ; '('
0x180008fad  call    ?Reset@?$InvasivePtr@VConfigLocationsTree@@@@QEAAXXZ; InvasivePtr<ConfigLocationsTree>::Reset(void)
0x180008fb2  lea     rax, ??_7InvasivePtrObject@@6B@; const InvasivePtrObject::`vftable'
0x180008fb9  mov     [rbx+10h], rax
0x180008fbd  add     rsp, 20h
0x180008fc1  pop     rbx
0x180008fc2  jmp     ?Release@ModuleRefCounter@@SAXXZ; ModuleRefCounter::Release(void)
```
