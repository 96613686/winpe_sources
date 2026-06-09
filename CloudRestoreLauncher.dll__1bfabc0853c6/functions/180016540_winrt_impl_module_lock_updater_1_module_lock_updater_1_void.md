# winrt::impl::module_lock_updater<1>::~module_lock_updater<1>(void)

- ea: `0x180016540`
- end: `0x180016575`
- name: `??1?$module_lock_updater@$00@impl@winrt@@QEAA@XZ`
- size: `53`
- prototype: ``
- caller_count: `12`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800164e4`
- `0x18001650c`
- `0x180036454`
- `0x18003ec20`
- `0x18003ee10`
- `0x18006d40c`
- `0x18006d574`
- `0x18007db64`
- `0x1800a8600`
- `0x1800c5e40`
- `0x180103ae0`
- `0x180103c38`

## callees

- `0x18001d614`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x180016569`
- `msvcp_win!_Mtx_unlock` at `0x180016569`
- `combase!__imp_CoReleaseSharedService` at `0x180016556`
- `combase!__imp_CoReleaseSharedService` at `0x180016556`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int winrt::impl::module_lock_updater<1>::~module_lock_updater<1>()
{
  std::_Mutex_base::lock((std::_Mutex_base *)&wil::details::g_refCountLock);
  wil::details::g_refCount = CoReleaseSharedService(wil::details::g_service_id);
  return _Mtx_unlock((_Mtx_t)&wil::details::g_refCountLock);
}

```

## disassembly

```asm
0x180016540  sub     rsp, 28h
0x180016544  lea     rcx, ?g_refCountLock@details@wil@@3Vmutex@std@@A; this
0x18001654b  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180016550  mov     ecx, cs:?g_service_id@details@wil@@3KA; ulong wil::details::g_service_id
0x180016556  call    cs:__imp_CoReleaseSharedService
0x18001655c  mov     cs:?g_refCount@details@wil@@3IA, eax; uint wil::details::g_refCount
0x180016562  lea     rcx, ?g_refCountLock@details@wil@@3Vmutex@std@@A; _Mtx_t
0x180016569  call    cs:__imp__Mtx_unlock
0x18001656f  nop
0x180016570  add     rsp, 28h
0x180016574  retn
```
