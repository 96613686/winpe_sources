# wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)

- ea: `0x18001666c`
- end: `0x180016683`
- name: `??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `23`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `35`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x180015258`
- `0x180016614`
- `0x18001d65c`
- `0x1800200d4`
- `0x180020f48`
- `0x180021600`
- `0x18002241c`
- `0x180022758`
- `0x1800229a0`
- `0x180022f50`
- `0x180023414`
- `0x180024084`
- `0x180033b6c`
- `0x18003dbe8`
- `0x180044708`
- `0x1800450ac`
- `0x180045e38`
- `0x180059f08`
- `0x180069324`
- `0x180097a9c`
- `0x18009ac3c`
- `0x1800a35e8`
- `0x1800a5f44`
- `0x1800a96f0`
- `0x1800aa010`
- `0x1800ab0ec`
- `0x1800ad43c`
- `0x1800adf58`
- `0x1800ae108`
- `0x1800bb290`
- `0x1800bc5ac`
- `0x1800bca00`
- `0x1800bd330`
- `0x1800e5e6c`
- `0x180129920`

## callees

- `0x18001666c`

## import_xrefs

- `OLE32!CoTaskMemFree` at `0x180016678`
- `OLE32!CoTaskMemFree` at `0x180016678`

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
0x18001666c  sub     rsp, 28h
0x180016670  mov     rcx, [rcx]; pv
0x180016673  test    rcx, rcx
0x180016676  jz      short loc_18001667E
0x180016678  call    cs:__imp_CoTaskMemFree
0x18001667e  add     rsp, 28h
0x180016682  retn
```
