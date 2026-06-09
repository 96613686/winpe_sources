# wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)

- ea: `0x180012408`
- end: `0x18001241f`
- name: `??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `23`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `28`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180007278`
- `0x180007f14`
- `0x180008038`
- `0x180010bec`
- `0x1800123b0`
- `0x180012534`
- `0x180012dc0`
- `0x180018e14`
- `0x1800192ec`
- `0x180019638`
- `0x180019cd8`
- `0x18001a5d4`
- `0x18001b2b8`
- `0x18001d318`
- `0x1800201bc`
- `0x180022660`
- `0x180022924`
- `0x180022ec4`
- `0x180023984`
- `0x180024614`
- `0x180024dd4`
- `0x18002695c`
- `0x18002722c`
- `0x1800273bc`
- `0x180028ab4`
- `0x18002f320`
- `0x18002f4f8`
- `0x180030224`

## callees

- `0x180012408`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012414`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012414`

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
0x180012408  sub     rsp, 28h
0x18001240c  mov     rcx, [rcx]; pv
0x18001240f  test    rcx, rcx
0x180012412  jz      short loc_18001241A
0x180012414  call    cs:__imp_CoTaskMemFree
0x18001241a  add     rsp, 28h
0x18001241e  retn
```
