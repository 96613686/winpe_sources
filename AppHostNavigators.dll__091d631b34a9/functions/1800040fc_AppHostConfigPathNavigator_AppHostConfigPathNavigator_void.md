# AppHostConfigPathNavigator::AppHostConfigPathNavigator(void)

- ea: `0x1800040fc`
- end: `0x18000415c`
- name: `??0AppHostConfigPathNavigator@@QEAA@XZ`
- size: `96`
- prototype: `AppHostConfigPathNavigator *__fastcall(AppHostConfigPathNavigator *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180004840`
- `0x180004c04`

## callees

- `0x180002310`

## pseudocode

```c
AppHostConfigPathNavigator *__fastcall AppHostConfigPathNavigator::AppHostConfigPathNavigator(
        AppHostConfigPathNavigator *this)
{
  AppHostConfigPathNavigator *result; // rax

  ModuleRefCounter::AddRef();
  *((_QWORD *)this + 2) = &InvasivePtrObject::`vftable';
  *((_DWORD *)this + 6) = 1;
  *((_DWORD *)this + 8) = -1;
  *((_QWORD *)this + 5) = 0;
  *(_QWORD *)this = &AppHostConfigPathNavigator::`vftable'{for `IXPathNavigator'};
  *((_QWORD *)this + 1) = &AppHostConfigPathNavigator::`vftable'{for `ATL::IDispatchImpl<IAppHostConfigPathNavigator,&__s_GUID const _GUID_a0601362_def3_4571_809b_5b856e5e5521,&_GUID const LIBID_AppHostNavigatorsLibrary,1,0,ATL::CComTypeInfoHolder>'};
  *((_QWORD *)this + 2) = &AppHostConfigPathNavigator::`vftable'{for `InvasivePtrObject'};
  result = this;
  *((_QWORD *)this + 6) = 0;
  return result;
}

```

## disassembly

```asm
0x1800040fc  push    rbx
0x1800040fe  sub     rsp, 20h
0x180004102  mov     rbx, rcx
0x180004105  call    ?AddRef@ModuleRefCounter@@SAXXZ; ModuleRefCounter::AddRef(void)
0x18000410a  lea     rax, ??_7InvasivePtrObject@@6B@; const InvasivePtrObject::`vftable'
0x180004111  mov     [rbx+10h], rax
0x180004115  lea     rax, ??_7AppHostConfigPathNavigator@@6BIXPathNavigator@@@; const AppHostConfigPathNavigator::`vftable'{for `IXPathNavigator'}
0x18000411c  mov     dword ptr [rbx+18h], 1
0x180004123  mov     dword ptr [rbx+20h], 0FFFFFFFFh
0x18000412a  mov     qword ptr [rbx+28h], 0
0x180004132  mov     [rbx], rax
0x180004135  lea     rax, ??_7AppHostConfigPathNavigator@@6B?$IDispatchImpl@UIAppHostConfigPathNavigator@@$1?_GUID_a0601362_def3_4571_809b_5b856e5e5521@@3U__s_GUID@@B$1?LIBID_AppHostNavigatorsLibrary@@3U_GUID@@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@@; const AppHostConfigPathNavigator::`vftable'{for `ATL::IDispatchImpl<IAppHostConfigPathNavigator,&__s_GUID const _GUID_a0601362_def3_4571_809b_5b856e5e5521,&_GUID const LIBID_AppHostNavigatorsLibrary,1,0,ATL::CComTypeInfoHolder>'}
0x18000413c  mov     [rbx+8], rax
0x180004140  lea     rax, ??_7AppHostConfigPathNavigator@@6BInvasivePtrObject@@@; const AppHostConfigPathNavigator::`vftable'{for `InvasivePtrObject'}
0x180004147  mov     [rbx+10h], rax
0x18000414b  mov     rax, rbx
0x18000414e  mov     qword ptr [rbx+30h], 0
0x180004156  add     rsp, 20h
0x18000415a  pop     rbx
0x18000415b  retn
```
