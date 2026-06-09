# wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)

- ea: `0x14000e19c`
- end: `0x14000e1b3`
- name: `??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(void **)`
- caller_count: `17`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14000e340`
- `0x140015980`
- `0x140015cd8`
- `0x140015fa0`
- `0x140017c9c`
- `0x14001a2e8`
- `0x14001bd28`
- `0x140025a34`
- `0x140025cd4`
- `0x14002632c`
- `0x140026cd0`
- `0x1400270ac`
- `0x14002f580`
- `0x14002f70c`
- `0x14002fc40`
- `0x14003780c`
- `0x140039ab0`

## callees

- `0x14000e19c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000e1a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000e1a8`

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
0x14000e19c  sub     rsp, 28h
0x14000e1a0  mov     rcx, [rcx]; pv
0x14000e1a3  test    rcx, rcx
0x14000e1a6  jz      short loc_14000E1AE
0x14000e1a8  call    cs:__imp_CoTaskMemFree
0x14000e1ae  add     rsp, 28h
0x14000e1b2  retn
```
