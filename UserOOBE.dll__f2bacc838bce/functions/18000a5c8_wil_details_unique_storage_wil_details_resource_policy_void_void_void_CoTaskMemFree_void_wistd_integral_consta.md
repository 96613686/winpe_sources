# wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)

- ea: `0x18000a5c8`
- end: `0x18000a5df`
- name: `??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `23`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `53`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180009604`
- `0x18000a580`
- `0x18000a71c`
- `0x18000ad04`
- `0x180010ae8`
- `0x180010e3c`
- `0x180011538`
- `0x180012014`
- `0x180012ab8`
- `0x180015a90`
- `0x180016e6c`
- `0x18001bc90`
- `0x18001bd7c`
- `0x18001bf10`
- `0x18001fad4`
- `0x180020028`
- `0x180020c58`
- `0x1800218b8`
- `0x18002197c`
- `0x180021a84`
- `0x180021b8c`
- `0x180021c8c`
- `0x180022690`
- `0x1800227c8`
- `0x180022900`
- `0x1800233ec`
- `0x180023b4c`
- `0x180023c30`
- `0x180023e38`
- `0x180024144`
- `0x18002586c`
- `0x180025b8c`
- `0x180025ca0`
- `0x1800261ac`
- `0x180026ab0`
- `0x180026c00`
- `0x180028684`
- `0x180028adc`
- `0x180029260`
- `0x18002a480`
- `0x18002ba90`
- `0x18002bd20`
- `0x1800331a8`
- `0x1800332ac`
- `0x180033374`
- `0x180034cf4`
- `0x1800374e8`
- `0x18003c358`
- `0x18003c8cc`
- `0x18003cbf4`

## callees

- `0x18000a5c8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a5d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a5d4`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(
        void **a1)
{
  void *v1; // rcx

  v1 = *a1;
  if ( v1 )
    CoTaskMemFree(v1);
}

```

## disassembly

```asm
0x18000a5c8  sub     rsp, 28h
0x18000a5cc  mov     rcx, [rcx]; pv
0x18000a5cf  test    rcx, rcx
0x18000a5d2  jz      short loc_18000A5DA
0x18000a5d4  call    cs:__imp_CoTaskMemFree
0x18000a5da  add     rsp, 28h
0x18000a5de  retn
```
