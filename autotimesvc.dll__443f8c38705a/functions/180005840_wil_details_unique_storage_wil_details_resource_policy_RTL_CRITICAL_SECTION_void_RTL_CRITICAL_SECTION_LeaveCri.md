# wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)

- ea: `0x180005840`
- end: `0x180005857`
- name: `??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION **)`
- caller_count: `15`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800057a8`
- `0x180005eb0`
- `0x180005f40`
- `0x180006ec4`
- `0x18000743c`
- `0x180007534`
- `0x18000891c`
- `0x1800096b0`
- `0x18000b668`
- `0x18000b7d8`
- `0x18000b86c`
- `0x18000b910`
- `0x18000b98c`
- `0x18000b9f0`
- `0x18000ba48`

## callees

- `0x180005840`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000584c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000584c`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(
        struct _RTL_CRITICAL_SECTION **a1)
{
  struct _RTL_CRITICAL_SECTION *v1; // rcx

  v1 = *a1;
  if ( v1 )
    LeaveCriticalSection(v1);
}

```

## disassembly

```asm
0x180005840  sub     rsp, 28h
0x180005844  mov     rcx, [rcx]; lpCriticalSection
0x180005847  test    rcx, rcx
0x18000584a  jz      short loc_180005852
0x18000584c  call    cs:__imp_LeaveCriticalSection
0x180005852  add     rsp, 28h
0x180005856  retn
```
