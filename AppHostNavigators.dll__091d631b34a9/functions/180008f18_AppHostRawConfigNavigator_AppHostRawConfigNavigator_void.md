# AppHostRawConfigNavigator::AppHostRawConfigNavigator(void)

- ea: `0x180008f18`
- end: `0x180008f78`
- name: `??0AppHostRawConfigNavigator@@QEAA@XZ`
- size: `96`
- prototype: `AppHostRawConfigNavigator *__fastcall(AppHostRawConfigNavigator *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180009018`
- `0x1800092a0`

## callees

- `0x180002310`

## pseudocode

```c
AppHostRawConfigNavigator *__fastcall AppHostRawConfigNavigator::AppHostRawConfigNavigator(
        AppHostRawConfigNavigator *this)
{
  AppHostRawConfigNavigator *result; // rax

  ModuleRefCounter::AddRef();
  *((_QWORD *)this + 2) = &InvasivePtrObject::`vftable';
  *((_DWORD *)this + 6) = 1;
  *((_DWORD *)this + 8) = -1;
  *((_QWORD *)this + 5) = 0;
  *(_QWORD *)this = &AppHostRawConfigNavigator::`vftable'{for `IXPathNavigator'};
  *((_QWORD *)this + 1) = &AppHostRawConfigNavigator::`vftable'{for `ATL::IDispatchImpl<IAppHostRawConfigNavigator,&__s_GUID const _GUID_4f29aa5f_4a59_4e88_bc5a_a902f6ff1d86,&_GUID const LIBID_AppHostNavigatorsLibrary,1,0,ATL::CComTypeInfoHolder>'};
  *((_QWORD *)this + 2) = &AppHostNavigatorTemplate<AppHostRawConfigNavigator,IAppHostRawConfigNavigator,RawConfigTree>::`vftable'{for `InvasivePtrObject'};
  result = this;
  *((_QWORD *)this + 6) = 0;
  return result;
}

```

## disassembly

```asm
0x180008f18  push    rbx
0x180008f1a  sub     rsp, 20h
0x180008f1e  mov     rbx, rcx
0x180008f21  call    ?AddRef@ModuleRefCounter@@SAXXZ; ModuleRefCounter::AddRef(void)
0x180008f26  lea     rax, ??_7InvasivePtrObject@@6B@; const InvasivePtrObject::`vftable'
0x180008f2d  mov     [rbx+10h], rax
0x180008f31  lea     rax, ??_7AppHostRawConfigNavigator@@6BIXPathNavigator@@@; const AppHostRawConfigNavigator::`vftable'{for `IXPathNavigator'}
0x180008f38  mov     dword ptr [rbx+18h], 1
0x180008f3f  mov     dword ptr [rbx+20h], 0FFFFFFFFh
0x180008f46  mov     qword ptr [rbx+28h], 0
0x180008f4e  mov     [rbx], rax
0x180008f51  lea     rax, ??_7AppHostRawConfigNavigator@@6B?$IDispatchImpl@UIAppHostRawConfigNavigator@@$1?_GUID_4f29aa5f_4a59_4e88_bc5a_a902f6ff1d86@@3U__s_GUID@@B$1?LIBID_AppHostNavigatorsLibrary@@3U_GUID@@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@@; const AppHostRawConfigNavigator::`vftable'{for `ATL::IDispatchImpl<IAppHostRawConfigNavigator,&__s_GUID const _GUID_4f29aa5f_4a59_4e88_bc5a_a902f6ff1d86,&_GUID const LIBID_AppHostNavigatorsLibrary,1,0,ATL::CComTypeInfoHolder>'}
0x180008f58  mov     [rbx+8], rax
0x180008f5c  lea     rax, ??_7?$AppHostNavigatorTemplate@VAppHostRawConfigNavigator@@UIAppHostRawConfigNavigator@@VRawConfigTree@@@@6BInvasivePtrObject@@@; const AppHostNavigatorTemplate<AppHostRawConfigNavigator,IAppHostRawConfigNavigator,RawConfigTree>::`vftable'{for `InvasivePtrObject'}
0x180008f63  mov     [rbx+10h], rax
0x180008f67  mov     rax, rbx
0x180008f6a  mov     qword ptr [rbx+30h], 0
0x180008f72  add     rsp, 20h
0x180008f76  pop     rbx
0x180008f77  retn
```
