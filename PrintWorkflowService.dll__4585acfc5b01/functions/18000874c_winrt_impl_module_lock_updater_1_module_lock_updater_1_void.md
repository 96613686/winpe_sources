# winrt::impl::module_lock_updater<1>::module_lock_updater<1>(void)

- ea: `0x18000874c`
- end: `0x18000878a`
- name: `??0?$module_lock_updater@$00@impl@winrt@@QEAA@XZ`
- size: `62`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `58`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180007d68`
- `0x180007dd4`
- `0x180007e40`
- `0x180007ea4`
- `0x180007f08`
- `0x180008010`
- `0x1800086dc`
- `0x180008bbc`
- `0x180008d00`
- `0x180024490`
- `0x180024538`
- `0x180024e84`
- `0x180024f60`
- `0x1800251c0`
- `0x180025254`
- `0x180028294`
- `0x1800295cc`
- `0x1800297b4`
- `0x180029a4c`
- `0x18002b498`
- `0x18002ecbc`
- `0x1800300c0`
- `0x180030870`
- `0x180030a00`
- `0x180030aa4`
- `0x180031030`
- `0x180031194`
- `0x180036270`
- `0x180036318`
- `0x1800363c0`
- `0x180036468`
- `0x180036510`
- `0x1800365b8`
- `0x180037f7c`
- `0x18003826c`
- `0x180038538`
- `0x1800388a4`
- `0x180038c64`
- `0x180038cf8`
- `0x180038d8c`
- `0x180039ad4`
- `0x18003c504`
- `0x18003dc10`
- `0x18003efb4`
- `0x180041d24`
- `0x180042974`
- `0x180044974`
- `0x180045f7c`
- `0x1800474c8`
- `0x180047e60`

## callees

- `0x180013348`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x18000877a`
- `msvcp_win!_Mtx_unlock` at `0x18000877a`
- `combase!__imp_CoAddRefSharedService` at `0x180008767`
- `combase!__imp_CoAddRefSharedService` at `0x180008767`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall winrt::impl::module_lock_updater<1>::module_lock_updater<1>(__int64 a1)
{
  std::_Mutex_base::lock((std::_Mutex_base *)&wil::details::g_refCountLock);
  wil::details::g_refCount = CoAddRefSharedService(wil::details::g_service_id);
  _Mtx_unlock((_Mtx_t)&wil::details::g_refCountLock);
  return a1;
}

```

## disassembly

```asm
0x18000874c  push    rbx
0x18000874e  sub     rsp, 20h
0x180008752  mov     rbx, rcx
0x180008755  lea     rcx, ?g_refCountLock@details@wil@@3Vmutex@std@@A; this
0x18000875c  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180008761  mov     ecx, cs:?g_service_id@details@wil@@3KA; ulong wil::details::g_service_id
0x180008767  call    cs:__imp_CoAddRefSharedService
0x18000876d  mov     cs:?g_refCount@details@wil@@3IA, eax; uint wil::details::g_refCount
0x180008773  lea     rcx, ?g_refCountLock@details@wil@@3Vmutex@std@@A; _Mtx_t
0x18000877a  call    cs:__imp__Mtx_unlock
0x180008780  nop
0x180008781  mov     rax, rbx
0x180008784  add     rsp, 20h
0x180008788  pop     rbx
0x180008789  retn
```
