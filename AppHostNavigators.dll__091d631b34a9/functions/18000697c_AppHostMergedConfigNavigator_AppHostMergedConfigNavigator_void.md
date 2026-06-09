# AppHostMergedConfigNavigator::AppHostMergedConfigNavigator(void)

- ea: `0x18000697c`
- end: `0x1800069dc`
- name: `??0AppHostMergedConfigNavigator@@QEAA@XZ`
- size: `96`
- prototype: `AppHostMergedConfigNavigator *__fastcall(AppHostMergedConfigNavigator *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180006a88`
- `0x180006cf4`

## callees

- `0x180002310`

## pseudocode

```c
AppHostMergedConfigNavigator *__fastcall AppHostMergedConfigNavigator::AppHostMergedConfigNavigator(
        AppHostMergedConfigNavigator *this)
{
  AppHostMergedConfigNavigator *result; // rax

  ModuleRefCounter::AddRef();
  *((_QWORD *)this + 2) = &InvasivePtrObject::`vftable';
  *((_DWORD *)this + 6) = 1;
  *((_DWORD *)this + 8) = -1;
  *((_QWORD *)this + 5) = 0;
  *(_QWORD *)this = &AppHostMergedConfigNavigator::`vftable'{for `IXPathNavigator'};
  *((_QWORD *)this + 1) = &AppHostMergedConfigNavigator::`vftable'{for `ATL::IDispatchImpl<IAppHostMergedConfigNavigator,&__s_GUID const _GUID_6bf27412_bb61_40c6_9ad6_1a790cbd0cb8,&_GUID const LIBID_AppHostNavigatorsLibrary,1,0,ATL::CComTypeInfoHolder>'};
  *((_QWORD *)this + 2) = &AppHostMergedConfigNavigator::`vftable'{for `InvasivePtrObject'};
  result = this;
  *((_QWORD *)this + 6) = 0;
  return result;
}

```

## disassembly

```asm
0x18000697c  push    rbx
0x18000697e  sub     rsp, 20h
0x180006982  mov     rbx, rcx
0x180006985  call    ?AddRef@ModuleRefCounter@@SAXXZ; ModuleRefCounter::AddRef(void)
0x18000698a  lea     rax, ??_7InvasivePtrObject@@6B@; const InvasivePtrObject::`vftable'
0x180006991  mov     [rbx+10h], rax
0x180006995  lea     rax, ??_7AppHostMergedConfigNavigator@@6BIXPathNavigator@@@; const AppHostMergedConfigNavigator::`vftable'{for `IXPathNavigator'}
0x18000699c  mov     dword ptr [rbx+18h], 1
0x1800069a3  mov     dword ptr [rbx+20h], 0FFFFFFFFh
0x1800069aa  mov     qword ptr [rbx+28h], 0
0x1800069b2  mov     [rbx], rax
0x1800069b5  lea     rax, ??_7AppHostMergedConfigNavigator@@6B?$IDispatchImpl@UIAppHostMergedConfigNavigator@@$1?_GUID_6bf27412_bb61_40c6_9ad6_1a790cbd0cb8@@3U__s_GUID@@B$1?LIBID_AppHostNavigatorsLibrary@@3U_GUID@@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@@; const AppHostMergedConfigNavigator::`vftable'{for `ATL::IDispatchImpl<IAppHostMergedConfigNavigator,&__s_GUID const _GUID_6bf27412_bb61_40c6_9ad6_1a790cbd0cb8,&_GUID const LIBID_AppHostNavigatorsLibrary,1,0,ATL::CComTypeInfoHolder>'}
0x1800069bc  mov     [rbx+8], rax
0x1800069c0  lea     rax, ??_7AppHostMergedConfigNavigator@@6BInvasivePtrObject@@@; const AppHostMergedConfigNavigator::`vftable'{for `InvasivePtrObject'}
0x1800069c7  mov     [rbx+10h], rax
0x1800069cb  mov     rax, rbx
0x1800069ce  mov     qword ptr [rbx+30h], 0
0x1800069d6  add     rsp, 20h
0x1800069da  pop     rbx
0x1800069db  retn
```
