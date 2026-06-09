# winrt::impl::module_lock_updater<1>::~module_lock_updater<1>(void)

- ea: `0x180009d88`
- end: `0x180009dbd`
- name: `??1?$module_lock_updater@$00@impl@winrt@@QEAA@XZ`
- size: `53`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180009dc4`
- `0x180009de8`
- `0x180010390`
- `0x18002531c`
- `0x1800312dc`
- `0x180031304`
- `0x180046724`

## callees

- `0x180013348`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x180009db1`
- `msvcp_win!_Mtx_unlock` at `0x180009db1`
- `combase!__imp_CoReleaseSharedService` at `0x180009d9e`
- `combase!__imp_CoReleaseSharedService` at `0x180009d9e`

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
0x180009d88  sub     rsp, 28h
0x180009d8c  lea     rcx, ?g_refCountLock@details@wil@@3Vmutex@std@@A; this
0x180009d93  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180009d98  mov     ecx, cs:?g_service_id@details@wil@@3KA; ulong wil::details::g_service_id
0x180009d9e  call    cs:__imp_CoReleaseSharedService
0x180009da4  mov     cs:?g_refCount@details@wil@@3IA, eax; uint wil::details::g_refCount
0x180009daa  lea     rcx, ?g_refCountLock@details@wil@@3Vmutex@std@@A; _Mtx_t
0x180009db1  call    cs:__imp__Mtx_unlock
0x180009db7  nop
0x180009db8  add     rsp, 28h
0x180009dbc  retn
```
