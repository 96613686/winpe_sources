# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_CLEANUP_GROUP *,void (*)(_TP_CLEANUP_GROUP *),&DestroyThreadpoolCleanupGroup(_TP_CLEANUP_GROUP *),wistd::integral_constant<unsigned __int64,0>,_TP_CLEANUP_GROUP *,_TP_CLEANUP_GROUP *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_CLEANUP_GROUP *,void (*)(_TP_CLEANUP_GROUP *),&DestroyThreadpoolCleanupGroup(_TP_CLEANUP_GROUP *),wistd::integral_constant<unsigned __int64,0>,_TP_CLEANUP_GROUP *,_TP_CLEANUP_GROUP *,0,std::nullptr_t>>>(void)

- ea: `0x18004f9ac`
- end: `0x18004f9d9`
- name: `??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_CLEANUP_GROUP@@P6AXPEAU1@@Z$1?DestroyThreadpoolCleanupGroup@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ`
- size: `45`
- prototype: `void __fastcall(PTP_CLEANUP_GROUP *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180068390`
- `0x1800683ce`

## callees

- `0x18004f9ac`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18004f9cd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18004f9cd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18004f9c4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18004f9c4`

## pseudocode

```c
void __fastcall wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_CLEANUP_GROUP *,void (*)(_TP_CLEANUP_GROUP *),&void DestroyThreadpoolCleanupGroup(_TP_CLEANUP_GROUP *),wistd::integral_constant<unsigned __int64,0>,_TP_CLEANUP_GROUP *,_TP_CLEANUP_GROUP *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_CLEANUP_GROUP *,void (*)(_TP_CLEANUP_GROUP *),&void DestroyThreadpoolCleanupGroup(_TP_CLEANUP_GROUP *),wistd::integral_constant<unsigned __int64,0>,_TP_CLEANUP_GROUP *,_TP_CLEANUP_GROUP *,0,std::nullptr_t>>>(
        PTP_CLEANUP_GROUP *a1)
{
  struct _TP_CLEANUP_GROUP *v1; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    CloseThreadpoolCleanupGroupMembers(*a1, 1, 0);
    CloseThreadpoolCleanupGroup(v1);
  }
}

```

## disassembly

```asm
0x18004f9ac  push    rbx
0x18004f9ae  sub     rsp, 20h
0x18004f9b2  mov     rbx, [rcx]
0x18004f9b5  test    rbx, rbx
0x18004f9b8  jz      short loc_18004F9D3
0x18004f9ba  xor     r8d, r8d; pvCleanupContext
0x18004f9bd  mov     rcx, rbx; ptpcg
0x18004f9c0  lea     edx, [r8+1]; fCancelPendingCallbacks
0x18004f9c4  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x18004f9ca  mov     rcx, rbx; ptpcg
0x18004f9cd  call    cs:__imp_CloseThreadpoolCleanupGroup
0x18004f9d3  add     rsp, 20h
0x18004f9d7  pop     rbx
0x18004f9d8  retn
```
