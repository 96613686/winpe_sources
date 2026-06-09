# ALLOC_CACHE_HANDLER::Cleanup(int)

- ea: `0x1800076b4`
- end: `0x1800076e7`
- name: `?Cleanup@ALLOC_CACHE_HANDLER@@SAHH@Z`
- size: `51`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180006e00`

## callees

- `0x1800076b4`
- `0x180007c2c`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800076cd`
- `KERNEL32!DeleteCriticalSection` at `0x1800076cd`

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
0x1800076b4  sub     rsp, 28h
0x1800076b8  call    ?ResetLookasideCleanupInterval@ALLOC_CACHE_HANDLER@@SAHXZ; ALLOC_CACHE_HANDLER::ResetLookasideCleanupInterval(void)
0x1800076bd  cmp     cs:?sm_fInitCsItems@ALLOC_CACHE_HANDLER@@0HA, 0; int ALLOC_CACHE_HANDLER::sm_fInitCsItems
0x1800076c4  jz      short loc_1800076DD
0x1800076c6  lea     rcx, ?sm_csItems@ALLOC_CACHE_HANDLER@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800076cd  call    cs:__imp_DeleteCriticalSection
0x1800076d3  mov     cs:?sm_fInitCsItems@ALLOC_CACHE_HANDLER@@0HA, 0; int ALLOC_CACHE_HANDLER::sm_fInitCsItems
0x1800076dd  mov     eax, 1
0x1800076e2  add     rsp, 28h
0x1800076e6  retn
```
