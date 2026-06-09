# CStartMenuPathCompleteQueryCache::~CStartMenuPathCompleteQueryCache(void)

- ea: `0x1800280dc`
- end: `0x18002812a`
- name: `??1CStartMenuPathCompleteQueryCache@@AEAA@XZ`
- size: `78`
- prototype: `void __fastcall(CStartMenuPathCompleteQueryCache *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002f7b0`

## callees

- `0x180010fcc`
- `0x180014220`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028111`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028111`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028100`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028100`

## pseudocode

```c
void __fastcall CStartMenuPathCompleteQueryCache::~CStartMenuPathCompleteQueryCache(
        CStartMenuPathCompleteQueryCache *this)
{
  *(_QWORD *)this = &CStartMenuPathCompleteQueryCache::`vftable';
  CDPA<ICondition,CTContainer_PolicyUnOwned<ICondition>>::DestroyCallback((char *)this + 24);
  CloseHandle(*((HANDLE *)this + 2));
  _InterlockedDecrement(&g_cDllRef);
  CoTaskMemFree(*((LPVOID *)this + 4));
  CDPA_Base<_ITEMID_CHILD,CTContainer_PolicyUnOwned<_ITEMID_CHILD>>::~CDPA_Base<_ITEMID_CHILD,CTContainer_PolicyUnOwned<_ITEMID_CHILD>>((struct _DPA **)this + 3);
}

```

## disassembly

```asm
0x1800280dc  mov     [rsp+arg_0], rbx
0x1800280e1  push    rdi
0x1800280e2  sub     rsp, 20h
0x1800280e6  lea     rax, ??_7CStartMenuPathCompleteQueryCache@@6B@
0x1800280ed  mov     rdi, rcx
0x1800280f0  mov     [rcx], rax
0x1800280f3  add     rcx, 18h
0x1800280f7  call    ?DestroyCallback@?$CDPA@UICondition@@V?$CTContainer_PolicyUnOwned@UICondition@@@@@@QEAAXP6AHPEAUICondition@@PEAX@Z1@Z
0x1800280fc  mov     rcx, [rdi+10h]; hObject
0x180028100  call    cs:__imp_CloseHandle
0x180028106  lock dec cs:?g_cDllRef@@3JA
0x18002810d  mov     rcx, [rdi+20h]; pv
0x180028111  call    cs:__imp_CoTaskMemFree
0x180028117  lea     rcx, [rdi+18h]
0x18002811b  mov     rbx, [rsp+28h+arg_0]
0x180028120  add     rsp, 20h
0x180028124  pop     rdi
0x180028125  jmp     ??1?$CDPA_Base@U_ITEMID_CHILD@@V?$CTContainer_PolicyUnOwned@U_ITEMID_CHILD@@@@@@QEAA@XZ
```
