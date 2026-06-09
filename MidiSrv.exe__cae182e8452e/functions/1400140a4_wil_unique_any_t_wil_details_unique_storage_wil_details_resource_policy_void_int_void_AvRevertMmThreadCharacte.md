# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&AvRevertMmThreadCharacteristics(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&AvRevertMmThreadCharacteristics(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(void)

- ea: `0x1400140a4`
- end: `0x1400140bb`
- name: `??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?AvRevertMmThreadCharacteristics@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ`
- size: `23`
- prototype: `BOOL __fastcall(void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140056b90`

## callees

- `0x1400140a4`

## import_xrefs

- `AVRT!AvRevertMmThreadCharacteristics` at `0x1400140b0`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x1400140b0`

## pseudocode

```c
BOOL __fastcall wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int AvRevertMmThreadCharacteristics(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int AvRevertMmThreadCharacteristics(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(
        void **a1)
{
  void *v1; // rcx
  BOOL result; // eax

  v1 = *a1;
  if ( v1 )
    return AvRevertMmThreadCharacteristics(v1);
  return result;
}

```

## disassembly

```asm
0x1400140a4  sub     rsp, 28h
0x1400140a8  mov     rcx, [rcx]; AvrtHandle
0x1400140ab  test    rcx, rcx
0x1400140ae  jz      short loc_1400140B6
0x1400140b0  call    cs:__imp_AvRevertMmThreadCharacteristics
0x1400140b6  add     rsp, 28h
0x1400140ba  retn
```
