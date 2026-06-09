# wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)

- ea: `0x14000f22c`
- end: `0x14000f243`
- name: `??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `23`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `21`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140007bc0`
- `0x14000b7ac`
- `0x14000f1b8`
- `0x140010268`
- `0x1400205cc`
- `0x1400346d4`
- `0x140035020`
- `0x140035158`
- `0x140035494`
- `0x1400356d0`
- `0x1400365a0`
- `0x140036db4`
- `0x1400378f8`
- `0x1400389f8`
- `0x140038b18`
- `0x140043184`
- `0x1400580a8`
- `0x14005a5a0`
- `0x14005b1f0`
- `0x14005b42c`
- `0x14005ba44`

## callees

- `0x14000f22c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000f238`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000f238`

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
0x14000f22c  sub     rsp, 28h
0x14000f230  mov     rcx, [rcx]; pv
0x14000f233  test    rcx, rcx
0x14000f236  jz      short loc_14000F23E
0x14000f238  call    cs:__imp_CoTaskMemFree
0x14000f23e  add     rsp, 28h
0x14000f242  retn
```
