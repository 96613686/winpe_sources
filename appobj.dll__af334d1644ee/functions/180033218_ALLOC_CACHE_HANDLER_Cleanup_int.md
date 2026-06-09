# ALLOC_CACHE_HANDLER::Cleanup(int)

- ea: `0x180033218`
- end: `0x18003324b`
- name: `?Cleanup@ALLOC_CACHE_HANDLER@@SAHH@Z`
- size: `51`
- prototype: `__int64 __fastcall()`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18003466c`

## callees

- `0x180033218`
- `0x180033850`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180033231`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180033231`

## pseudocode

```c
__int64 __fastcall ALLOC_CACHE_HANDLER::Cleanup()
{
  ALLOC_CACHE_HANDLER::ResetLookasideCleanupInterval();
  if ( ALLOC_CACHE_HANDLER::sm_fInitCsItems )
  {
    DeleteCriticalSection(&ALLOC_CACHE_HANDLER::sm_csItems);
    ALLOC_CACHE_HANDLER::sm_fInitCsItems = 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180033218  sub     rsp, 28h
0x18003321c  call    ?ResetLookasideCleanupInterval@ALLOC_CACHE_HANDLER@@SAHXZ; ALLOC_CACHE_HANDLER::ResetLookasideCleanupInterval(void)
0x180033221  cmp     cs:?sm_fInitCsItems@ALLOC_CACHE_HANDLER@@0HA, 0; int ALLOC_CACHE_HANDLER::sm_fInitCsItems
0x180033228  jz      short loc_180033241
0x18003322a  lea     rcx, ?sm_csItems@ALLOC_CACHE_HANDLER@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180033231  call    cs:__imp_DeleteCriticalSection
0x180033237  mov     cs:?sm_fInitCsItems@ALLOC_CACHE_HANDLER@@0HA, 0; int ALLOC_CACHE_HANDLER::sm_fInitCsItems
0x180033241  mov     eax, 1
0x180033246  add     rsp, 28h
0x18003324a  retn
```
