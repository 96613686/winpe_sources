# wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)

- ea: `0x18000d504`
- end: `0x18000d51b`
- name: `??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(void **)`
- caller_count: `26`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000c0c4`
- `0x18000ca78`
- `0x18000cf04`
- `0x18000d474`
- `0x18000e2fc`
- `0x18000fa4c`
- `0x18000fcb0`
- `0x180010000`
- `0x1800100fc`
- `0x180011604`
- `0x180011c44`
- `0x180011f68`
- `0x180013284`
- `0x180016180`
- `0x18001738c`
- `0x18001c8cc`
- `0x18001cb1c`
- `0x18001cd30`
- `0x18001cffc`
- `0x18001d224`
- `0x18001d438`
- `0x18001d790`
- `0x18001daa0`
- `0x18001dd30`
- `0x18001dfc0`
- `0x18001e210`

## callees

- `0x18000d504`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d510`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d510`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x18000d504  sub     rsp, 28h
0x18000d508  mov     rcx, [rcx]; pv
0x18000d50b  test    rcx, rcx
0x18000d50e  jz      short loc_18000D516
0x18000d510  call    cs:__imp_CoTaskMemFree
0x18000d516  add     rsp, 28h
0x18000d51a  retn
```
