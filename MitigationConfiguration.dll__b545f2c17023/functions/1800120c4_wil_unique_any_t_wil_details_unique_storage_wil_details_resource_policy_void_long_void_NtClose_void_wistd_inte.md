# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(void)

- ea: `0x1800120c4`
- end: `0x1800120db`
- name: `??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?NtClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ`
- size: `23`
- prototype: `NTSTATUS __fastcall(void **)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x180013f5a`
- `0x180013f6c`
- `0x180013fa2`

## callees

- `0x1800120c4`

## import_xrefs

- `ntdll!NtClose` at `0x1800120d0`
- `ntdll!NtClose` at `0x1800120d0`

## pseudocode

```c
NTSTATUS __fastcall wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(
        void **a1)
{
  void *v1; // rcx
  NTSTATUS result; // eax

  v1 = *a1;
  if ( v1 )
    return NtClose(v1);
  return result;
}

```

## disassembly

```asm
0x1800120c4  sub     rsp, 28h
0x1800120c8  mov     rcx, [rcx]; Handle
0x1800120cb  test    rcx, rcx
0x1800120ce  jz      short loc_1800120D6
0x1800120d0  call    cs:__imp_NtClose
0x1800120d6  add     rsp, 28h
0x1800120da  retn
```
