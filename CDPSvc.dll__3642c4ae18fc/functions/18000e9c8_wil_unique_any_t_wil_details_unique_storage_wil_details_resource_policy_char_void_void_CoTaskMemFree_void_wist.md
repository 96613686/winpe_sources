# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)

- ea: `0x18000e9c8`
- end: `0x18000e9df`
- name: `??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ`
- size: `23`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `32`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000cd08`
- `0x18000db68`
- `0x18000e9e8`
- `0x18000f848`
- `0x1800106c4`
- `0x180012c2c`
- `0x180012da0`
- `0x180016808`
- `0x18001dc90`
- `0x180063d30`
- `0x180063d50`
- `0x180063d70`
- `0x180063e20`
- `0x180063e40`
- `0x180063f20`
- `0x180063f80`
- `0x180063fa0`
- `0x1800643c1`
- `0x1800643d3`
- `0x1800643e5`
- `0x1800643f7`
- `0x180064409`
- `0x18006441b`
- `0x18006442d`
- `0x18006443f`
- `0x180064451`
- `0x180064463`
- `0x180064475`
- `0x1800644ab`
- `0x1800644bd`
- `0x1800645e6`
- `0x1800645f8`

## callees

- `0x18000e9c8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e9d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e9d4`

## pseudocode

```c
void __fastcall wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(
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
0x18000e9c8  sub     rsp, 28h
0x18000e9cc  mov     rcx, [rcx]; pv
0x18000e9cf  test    rcx, rcx
0x18000e9d2  jz      short loc_18000E9DA
0x18000e9d4  call    cs:__imp_CoTaskMemFree
0x18000e9da  add     rsp, 28h
0x18000e9de  retn
```
