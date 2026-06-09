# tlx::auto_xxx<_TP_CLEANUP_GROUP *,void (*)(_TP_CLEANUP_GROUP *),&CloseThreadpoolCleanupGroup(_TP_CLEANUP_GROUP *),0>::_Delete(void)

- ea: `0x18000b614`
- end: `0x18000b62b`
- name: `?_Delete@?$auto_xxx@PEAU_TP_CLEANUP_GROUP@@P6AXPEAU1@@Z$1?CloseThreadpoolCleanupGroup@@YAX0@Z$0A@@tlx@@AEAAXXZ`
- size: `23`
- prototype: `void __fastcall(struct _TP_CLEANUP_GROUP **)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180004880`
- `0x180009814`
- `0x180009c7c`

## callees

- `0x18000b614`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18000b620`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18000b620`

## pseudocode

```c
void __fastcall tlx::auto_xxx<_TP_CLEANUP_GROUP *,void (*)(_TP_CLEANUP_GROUP *),&void CloseThreadpoolCleanupGroup(_TP_CLEANUP_GROUP *),0>::_Delete(
        struct _TP_CLEANUP_GROUP **a1)
{
  struct _TP_CLEANUP_GROUP *v1; // rcx

  v1 = *a1;
  if ( v1 )
    CloseThreadpoolCleanupGroup(v1);
}

```

## disassembly

```asm
0x18000b614  sub     rsp, 28h
0x18000b618  mov     rcx, [rcx]; ptpcg
0x18000b61b  test    rcx, rcx
0x18000b61e  jz      short loc_18000B626
0x18000b620  call    cs:__imp_CloseThreadpoolCleanupGroup
0x18000b626  add     rsp, 28h
0x18000b62a  retn
```
