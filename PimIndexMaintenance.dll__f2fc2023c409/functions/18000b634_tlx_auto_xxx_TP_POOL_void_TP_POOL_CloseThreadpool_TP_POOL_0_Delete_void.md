# tlx::auto_xxx<_TP_POOL *,void (*)(_TP_POOL *),&CloseThreadpool(_TP_POOL *),0>::_Delete(void)

- ea: `0x18000b634`
- end: `0x18000b64b`
- name: `?_Delete@?$auto_xxx@PEAU_TP_POOL@@P6AXPEAU1@@Z$1?CloseThreadpool@@YAX0@Z$0A@@tlx@@AEAAXXZ`
- size: `23`
- prototype: `void __fastcall(struct _TP_POOL **)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180004880`
- `0x180009814`
- `0x180009c7c`

## callees

- `0x18000b634`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x18000b640`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x18000b640`

## pseudocode

```c
void __fastcall tlx::auto_xxx<_TP_POOL *,void (*)(_TP_POOL *),&void CloseThreadpool(_TP_POOL *),0>::_Delete(
        struct _TP_POOL **a1)
{
  struct _TP_POOL *v1; // rcx

  v1 = *a1;
  if ( v1 )
    CloseThreadpool(v1);
}

```

## disassembly

```asm
0x18000b634  sub     rsp, 28h
0x18000b638  mov     rcx, [rcx]; ptpp
0x18000b63b  test    rcx, rcx
0x18000b63e  jz      short loc_18000B646
0x18000b640  call    cs:__imp_CloseThreadpool
0x18000b646  add     rsp, 28h
0x18000b64a  retn
```
