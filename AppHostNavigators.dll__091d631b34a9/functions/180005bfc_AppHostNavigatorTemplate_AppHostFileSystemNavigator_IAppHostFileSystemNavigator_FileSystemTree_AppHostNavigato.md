# AppHostNavigatorTemplate<AppHostFileSystemNavigator,IAppHostFileSystemNavigator,FileSystemTree>::~AppHostNavigatorTemplate<AppHostFileSystemNavigator,IAppHostFileSystemNavigator,FileSystemTree>(void)

- ea: `0x180005bfc`
- end: `0x180005c43`
- name: `??1?$AppHostNavigatorTemplate@VAppHostFileSystemNavigator@@UIAppHostFileSystemNavigator@@VFileSystemTree@@@@UEAA@XZ`
- size: `71`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180005d10`

## callees

- `0x1800039b0`
- `0x180003a1c`

## pseudocode

```c
void __fastcall AppHostNavigatorTemplate<AppHostFileSystemNavigator,IAppHostFileSystemNavigator,FileSystemTree>::~AppHostNavigatorTemplate<AppHostFileSystemNavigator,IAppHostFileSystemNavigator,FileSystemTree>(
        __int64 a1)
{
  *(_QWORD *)a1 = &AppHostFileSystemNavigator::`vftable'{for `IXPathNavigator'};
  *(_QWORD *)(a1 + 8) = &AppHostNavigatorTemplate<AppHostFileSystemNavigator,IAppHostFileSystemNavigator,FileSystemTree>::`vftable'{for `ATL::IDispatchImpl<IAppHostFileSystemNavigator,&__s_GUID const _GUID_355bd6c9_0a2e_42fa_ba7e_b4495b9dbeae,&_GUID const LIBID_AppHostNavigatorsLibrary,1,0,ATL::CComTypeInfoHolder>'};
  *(_QWORD *)(a1 + 16) = &AppHostFileSystemNavigator::`vftable'{for `InvasivePtrObject'};
  InvasivePtr<ConfigLocationsTree>::Reset((InvasivePtrObject **)(a1 + 40));
  *(_QWORD *)(a1 + 16) = &InvasivePtrObject::`vftable';
  ModuleRefCounter::Release();
}

```

## disassembly

```asm
0x180005bfc  push    rbx
0x180005bfe  sub     rsp, 20h
0x180005c02  lea     rax, ??_7AppHostFileSystemNavigator@@6BIXPathNavigator@@@; const AppHostFileSystemNavigator::`vftable'{for `IXPathNavigator'}
0x180005c09  mov     rbx, rcx
0x180005c0c  mov     [rcx], rax
0x180005c0f  lea     rax, ??_7?$AppHostNavigatorTemplate@VAppHostFileSystemNavigator@@UIAppHostFileSystemNavigator@@VFileSystemTree@@@@6B?$IDispatchImpl@UIAppHostFileSystemNavigator@@$1?_GUID_355bd6c9_0a2e_42fa_ba7e_b4495b9dbeae@@3U__s_GUID@@B$1?LIBID_AppHostNavigatorsLibrary@@3U_GUID@@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@@; const AppHostNavigatorTemplate<AppHostFileSystemNavigator,IAppHostFileSystemNavigator,FileSystemTree>::`vftable'{for `ATL::IDispatchImpl<IAppHostFileSystemNavigator,&__s_GUID const _GUID_355bd6c9_0a2e_42fa_ba7e_b4495b9dbeae,&_GUID const LIBID_AppHostNavigatorsLibrary,1,0,ATL::CComTypeInfoHolder>'}
0x180005c16  mov     [rcx+8], rax
0x180005c1a  lea     rax, ??_7AppHostFileSystemNavigator@@6BInvasivePtrObject@@@; const AppHostFileSystemNavigator::`vftable'{for `InvasivePtrObject'}
0x180005c21  mov     [rcx+10h], rax
0x180005c25  add     rcx, 28h ; '('
0x180005c29  call    ?Reset@?$InvasivePtr@VConfigLocationsTree@@@@QEAAXXZ; InvasivePtr<ConfigLocationsTree>::Reset(void)
0x180005c2e  lea     rax, ??_7InvasivePtrObject@@6B@; const InvasivePtrObject::`vftable'
0x180005c35  mov     [rbx+10h], rax
0x180005c39  add     rsp, 20h
0x180005c3d  pop     rbx
0x180005c3e  jmp     ?Release@ModuleRefCounter@@SAXXZ; ModuleRefCounter::Release(void)
```
