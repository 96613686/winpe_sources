# wil::details::unique_storage<wil::details::resource_policy<_DismFeatureInfo *,long (*)(void *),&DismDelete(void *),wistd::integral_constant<unsigned __int64,0>,_DismFeatureInfo *,_DismFeatureInfo *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_DismFeatureInfo *,long (*)(void *),&DismDelete(void *),wistd::integral_constant<unsigned __int64,0>,_DismFeatureInfo *,_DismFeatureInfo *,0,std::nullptr_t>>(void)

- ea: `0x180011c0c`
- end: `0x180011c23`
- name: `??1?$unique_storage@U?$resource_policy@PEAU_DismFeatureInfo@@P6AJPEAX@Z$1?DismDelete@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `23`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180011bdc`
- `0x180013454`

## callees

- `0x180011c0c`

## import_xrefs

- `DismApi!DismDelete` at `0x180011c18`
- `DismApi!DismDelete` at `0x180011c18`

## pseudocode

```c
__int64 __fastcall wil::details::unique_storage<wil::details::resource_policy<_DismFeatureInfo *,long (*)(void *),&long DismDelete(void *),wistd::integral_constant<unsigned __int64,0>,_DismFeatureInfo *,_DismFeatureInfo *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_DismFeatureInfo *,long (*)(void *),&long DismDelete(void *),wistd::integral_constant<unsigned __int64,0>,_DismFeatureInfo *,_DismFeatureInfo *,0,std::nullptr_t>>(
        _QWORD *a1)
{
  __int64 result; // rax

  if ( *a1 )
    return DismDelete();
  return result;
}

```

## disassembly

```asm
0x180011c0c  sub     rsp, 28h
0x180011c10  mov     rcx, [rcx]
0x180011c13  test    rcx, rcx
0x180011c16  jz      short loc_180011C1E
0x180011c18  call    cs:__imp_DismDelete
0x180011c1e  add     rsp, 28h
0x180011c22  retn
```
