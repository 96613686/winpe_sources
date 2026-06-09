# wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)

- ea: `0x18000e3bc`
- end: `0x18000e3d3`
- name: `??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `23`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `56`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000e3b0`
- `0x18000e8f0`
- `0x18000eab0`
- `0x18000f180`
- `0x180010770`
- `0x180012c48`
- `0x180013c1c`
- `0x180015cf0`
- `0x1800170d0`
- `0x180017d90`
- `0x180018990`
- `0x180018f74`
- `0x1800192bc`
- `0x180019850`
- `0x18001a228`
- `0x18001ae60`
- `0x18001e5ac`
- `0x180020240`
- `0x1800215fc`
- `0x180021830`
- `0x180022afc`
- `0x180027250`
- `0x180027a68`
- `0x180027b20`
- `0x180028e14`
- `0x180029614`
- `0x1800297d0`
- `0x180029b20`
- `0x18002a980`
- `0x18002aa54`
- `0x18002aba0`
- `0x18002af1c`
- `0x18002b150`
- `0x18002b9b0`
- `0x18002bb40`
- `0x18002c080`
- `0x18002c2f0`
- `0x18002c7d0`
- `0x18002c9d0`
- `0x18002ce20`
- `0x18002fa88`
- `0x180030714`
- `0x1800308f8`
- `0x18003106c`
- `0x180031284`
- `0x180031d7c`
- `0x180032050`
- `0x180033334`
- `0x180036f74`
- `0x180037bb8`

## callees

- `0x18000e3bc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e3c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e3c8`

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
0x18000e3bc  sub     rsp, 28h
0x18000e3c0  mov     rcx, [rcx]; pv
0x18000e3c3  test    rcx, rcx
0x18000e3c6  jz      short loc_18000E3CE
0x18000e3c8  call    cs:__imp_CoTaskMemFree
0x18000e3ce  add     rsp, 28h
0x18000e3d2  retn
```
