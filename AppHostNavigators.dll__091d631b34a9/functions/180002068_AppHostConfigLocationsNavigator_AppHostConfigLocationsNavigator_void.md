# AppHostConfigLocationsNavigator::AppHostConfigLocationsNavigator(void)

- ea: `0x180002068`
- end: `0x1800020c8`
- name: `??0AppHostConfigLocationsNavigator@@QEAA@XZ`
- size: `96`
- prototype: `AppHostConfigLocationsNavigator *__fastcall(AppHostConfigLocationsNavigator *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180002544`
- `0x18000280c`

## callees

- `0x180002310`

## pseudocode

```c
AppHostConfigLocationsNavigator *__fastcall AppHostConfigLocationsNavigator::AppHostConfigLocationsNavigator(
        AppHostConfigLocationsNavigator *this)
{
  AppHostConfigLocationsNavigator *result; // rax

  ModuleRefCounter::AddRef();
  *((_QWORD *)this + 2) = &InvasivePtrObject::`vftable';
  *((_DWORD *)this + 6) = 1;
  *((_DWORD *)this + 8) = -1;
  *((_QWORD *)this + 5) = 0;
  *(_QWORD *)this = &AppHostConfigLocationsNavigator::`vftable'{for `IXPathNavigator'};
  *((_QWORD *)this + 1) = &AppHostConfigLocationsNavigator::`vftable'{for `ATL::IDispatchImpl<IAppHostConfigLocationsNavigator,&__s_GUID const _GUID_9dfa9beb_c15f_450e_bf3a_1d56c67b5c0b,&_GUID const LIBID_AppHostNavigatorsLibrary,1,0,ATL::CComTypeInfoHolder>'};
  *((_QWORD *)this + 2) = &AppHostConfigLocationsNavigator::`vftable'{for `InvasivePtrObject'};
  result = this;
  *((_QWORD *)this + 6) = 0;
  return result;
}

```

## disassembly

```asm
0x180002068  push    rbx
0x18000206a  sub     rsp, 20h
0x18000206e  mov     rbx, rcx
0x180002071  call    ?AddRef@ModuleRefCounter@@SAXXZ; ModuleRefCounter::AddRef(void)
0x180002076  lea     rax, ??_7InvasivePtrObject@@6B@; const InvasivePtrObject::`vftable'
0x18000207d  mov     [rbx+10h], rax
0x180002081  lea     rax, ??_7AppHostConfigLocationsNavigator@@6BIXPathNavigator@@@; const AppHostConfigLocationsNavigator::`vftable'{for `IXPathNavigator'}
0x180002088  mov     dword ptr [rbx+18h], 1
0x18000208f  mov     dword ptr [rbx+20h], 0FFFFFFFFh
0x180002096  mov     qword ptr [rbx+28h], 0
0x18000209e  mov     [rbx], rax
0x1800020a1  lea     rax, ??_7AppHostConfigLocationsNavigator@@6B?$IDispatchImpl@UIAppHostConfigLocationsNavigator@@$1?_GUID_9dfa9beb_c15f_450e_bf3a_1d56c67b5c0b@@3U__s_GUID@@B$1?LIBID_AppHostNavigatorsLibrary@@3U_GUID@@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@@; const AppHostConfigLocationsNavigator::`vftable'{for `ATL::IDispatchImpl<IAppHostConfigLocationsNavigator,&__s_GUID const _GUID_9dfa9beb_c15f_450e_bf3a_1d56c67b5c0b,&_GUID const LIBID_AppHostNavigatorsLibrary,1,0,ATL::CComTypeInfoHolder>'}
0x1800020a8  mov     [rbx+8], rax
0x1800020ac  lea     rax, ??_7AppHostConfigLocationsNavigator@@6BInvasivePtrObject@@@; const AppHostConfigLocationsNavigator::`vftable'{for `InvasivePtrObject'}
0x1800020b3  mov     [rbx+10h], rax
0x1800020b7  mov     rax, rbx
0x1800020ba  mov     qword ptr [rbx+30h], 0
0x1800020c2  add     rsp, 20h
0x1800020c6  pop     rbx
0x1800020c7  retn
```
