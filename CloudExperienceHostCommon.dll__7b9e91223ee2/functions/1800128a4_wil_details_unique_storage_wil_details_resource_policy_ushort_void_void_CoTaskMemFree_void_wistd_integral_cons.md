# wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)

- ea: `0x1800128a4`
- end: `0x1800128bb`
- name: `??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `23`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `40`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180003af4`
- `0x180004b80`
- `0x180004db0`
- `0x180004edc`
- `0x180010b40`
- `0x180011188`
- `0x180012774`
- `0x180013ef4`
- `0x1800181f0`
- `0x180019250`
- `0x180021e08`
- `0x180022c50`
- `0x180023c4c`
- `0x1800240f8`
- `0x180024cbc`
- `0x180024d70`
- `0x18002583c`
- `0x180026668`
- `0x180026848`
- `0x18003d0c0`
- `0x18003d190`
- `0x180048cb8`
- `0x18005880c`
- `0x1800588dc`
- `0x1800589e0`
- `0x180058ab8`
- `0x180058b90`
- `0x180058cb8`
- `0x180059108`
- `0x18005d5ec`
- `0x18005ffe4`
- `0x18007ab44`
- `0x18007b7e0`
- `0x18007ccb4`
- `0x18007ce38`
- `0x18007e250`
- `0x180083528`
- `0x18009f404`
- `0x1800a1540`
- `0x1800b7630`

## callees

- `0x1800128a4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800128b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800128b0`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(
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
0x1800128a4  sub     rsp, 28h
0x1800128a8  mov     rcx, [rcx]; pv
0x1800128ab  test    rcx, rcx
0x1800128ae  jz      short loc_1800128B6
0x1800128b0  call    cs:__imp_CoTaskMemFree
0x1800128b6  add     rsp, 28h
0x1800128ba  retn
```
