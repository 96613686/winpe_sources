# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&DeleteBoundaryDescriptor(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&DeleteBoundaryDescriptor(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(void)

- ea: `0x140024744`
- end: `0x14002475b`
- name: `??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?DeleteBoundaryDescriptor@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x14004f21c`

## callees

- `0x140024744`

## import_xrefs

- `api-ms-win-core-namespace-l1-1-0!DeleteBoundaryDescriptor` at `0x140024750`
- `api-ms-win-core-namespace-l1-1-0!DeleteBoundaryDescriptor` at `0x140024750`

## pseudocode

```c
void __fastcall wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void DeleteBoundaryDescriptor(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void DeleteBoundaryDescriptor(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(
        void **a1)
{
  void *v1; // rcx

  v1 = *a1;
  if ( v1 )
    DeleteBoundaryDescriptor(v1);
}

```

## disassembly

```asm
0x140024744  sub     rsp, 28h
0x140024748  mov     rcx, [rcx]; BoundaryDescriptor
0x14002474b  test    rcx, rcx
0x14002474e  jz      short loc_140024756
0x140024750  call    cs:__imp_DeleteBoundaryDescriptor
0x140024756  add     rsp, 28h
0x14002475a  retn
```
