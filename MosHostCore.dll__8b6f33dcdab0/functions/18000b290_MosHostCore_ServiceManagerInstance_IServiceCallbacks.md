# MosHostCore_ServiceManagerInstance(IServiceCallbacks *)

- ea: `0x18000b290`
- end: `0x18000b2dd`
- name: `?MosHostCore_ServiceManagerInstance@@YAPEAUIServiceManager@@PEAUIServiceCallbacks@@@Z`
- size: `77`
- prototype: `struct IServiceManager *__fastcall(struct IServiceCallbacks *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task`

## callees

- `0x180025010`

## import_xrefs

- `MapsStore!MapsStore_SetServiceCallbacks` at `0x18000b2b8`
- `MapsStore!MapsStore_SetServiceCallbacks` at `0x18000b2b8`
- `mapsbtsvc!MapsBackgroundTransferService_SetServiceCallbacks` at `0x18000b2c1`
- `mapsbtsvc!MapsBackgroundTransferService_SetServiceCallbacks` at `0x18000b2c1`
- `MosStorage!MosStorage_SetServiceCallbacks` at `0x18000b2af`
- `MosStorage!MosStorage_SetServiceCallbacks` at `0x18000b2af`
- `MapConfiguration!ConfigurationManager_SetServiceCallbacks` at `0x18000b2ca`
- `MapConfiguration!ConfigurationManager_SetServiceCallbacks` at `0x18000b2ca`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
struct IServiceManager *__fastcall MosHostCore_ServiceManagerInstance(struct IServiceCallbacks *a1)
{
  __int64 v1; // rax
  __int64 v2; // rbx

  v1 = *(_QWORD *)a1;
  qword_180035648 = (__int64)a1;
  v2 = (*(__int64 (**)(void))(v1 + 32))();
  MosStorage_SetServiceCallbacks(v2);
  MapsStore_SetServiceCallbacks(v2);
  MapsBackgroundTransferService_SetServiceCallbacks(v2);
  ConfigurationManager_SetServiceCallbacks(v2);
  return (struct IServiceManager *)&ServiceManager::sm_svcmgr;
}

```

## disassembly

```asm
0x18000b290  push    rbx
0x18000b292  sub     rsp, 20h
0x18000b296  mov     rax, [rcx]
0x18000b299  mov     cs:qword_180035648, rcx
0x18000b2a0  mov     rax, [rax+20h]
0x18000b2a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b2a9  mov     rcx, rax
0x18000b2ac  mov     rbx, rax
0x18000b2af  call    cs:__imp_MosStorage_SetServiceCallbacks
0x18000b2b5  mov     rcx, rbx
0x18000b2b8  call    cs:__imp_MapsStore_SetServiceCallbacks
0x18000b2be  mov     rcx, rbx
0x18000b2c1  call    cs:__imp_MapsBackgroundTransferService_SetServiceCallbacks
0x18000b2c7  mov     rcx, rbx
0x18000b2ca  call    cs:__imp_ConfigurationManager_SetServiceCallbacks
0x18000b2d0  lea     rax, ?sm_svcmgr@ServiceManager@@0V1@A; ServiceManager ServiceManager::sm_svcmgr
0x18000b2d7  add     rsp, 20h
0x18000b2db  pop     rbx
0x18000b2dc  retn
```
