# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)

- ea: `0x180017820`
- end: `0x18001783e`
- name: `??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `18`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180022b70`
- `0x180022f7c`
- `0x1800234ac`
- `0x180023600`
- `0x180026114`
- `0x18003c324`
- `0x18003c9f4`
- `0x18004ec20`
- `0x180050e90`
- `0x1800595dc`
- `0x18007b0b0`
- `0x18007bf3d`
- `0x18007bf97`
- `0x18007bfa9`
- `0x18007c0d4`
- `0x18007eca8`
- `0x18007edfe`
- `0x18007ee10`

## callees

- `0x180017820`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001782c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001782c`

## pseudocode

```c
void __fastcall wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(
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
0x180017820  sub     rsp, 28h
0x180017824  mov     rcx, [rcx]; pv
0x180017827  test    rcx, rcx
0x18001782a  jz      short loc_180017838
0x18001782c  call    cs:__imp_CoTaskMemFree
0x180017833  nop     dword ptr [rax+rax+00h]
0x180017838  add     rsp, 28h
0x18001783c  retn
```
