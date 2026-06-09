# tlx::_LazyImpl<SharingTokenManager,tlx::lazy_construct<SharingTokenManager>,tlx::static_lazy<SharingTokenManager,0,tlx::lazy_construct<SharingTokenManager>>>::_Initializer::~_Initializer(void)

- ea: `0x1800044cc`
- end: `0x1800044ea`
- name: `??1_Initializer@?$_LazyImpl@VSharingTokenManager@@V?$lazy_construct@VSharingTokenManager@@@tlx@@V?$static_lazy@VSharingTokenManager@@$0A@V?$lazy_construct@VSharingTokenManager@@@tlx@@@3@@tlx@@QEAA@XZ`
- size: `30`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180006f78`
- `0x18000f300`
- `0x18000f384`
- `0x18000f468`

## callees

- `0x1800044cc`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800044df`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800044df`

## pseudocode

```c
BOOL __fastcall tlx::_LazyImpl<SharingTokenManager,tlx::lazy_construct<SharingTokenManager>,tlx::static_lazy<SharingTokenManager,0,tlx::lazy_construct<SharingTokenManager>>>::_Initializer::~_Initializer(
        union _RTL_RUN_ONCE **a1)
{
  union _RTL_RUN_ONCE *v1; // rcx
  BOOL result; // eax

  v1 = *a1;
  if ( v1 )
    return InitOnceComplete(v1, 4u, 0);
  return result;
}

```

## disassembly

```asm
0x1800044cc  sub     rsp, 28h
0x1800044d0  mov     rcx, [rcx]; lpInitOnce
0x1800044d3  test    rcx, rcx
0x1800044d6  jz      short loc_1800044E5
0x1800044d8  xor     r8d, r8d; lpContext
0x1800044db  lea     edx, [r8+4]; dwFlags
0x1800044df  call    cs:__imp_InitOnceComplete
0x1800044e5  add     rsp, 28h
0x1800044e9  retn
```
