# winrt::impl::module_lock_updater<1>::module_lock_updater<1>(void)

- ea: `0x1800156f4`
- end: `0x180015732`
- name: `??0?$module_lock_updater@$00@impl@winrt@@QEAA@XZ`
- size: `62`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `80`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180015068`
- `0x18001c900`
- `0x18002e6bc`
- `0x18002eb40`
- `0x18003307c`
- `0x180033dec`
- `0x180033f70`
- `0x180034014`
- `0x180035748`
- `0x1800357b4`
- `0x180056fc8`
- `0x180068614`
- `0x180068b18`
- `0x180068bc4`
- `0x180069324`
- `0x18006b004`
- `0x18006c0ac`
- `0x18006c604`
- `0x18006ceec`
- `0x180072ccc`
- `0x180072fcc`
- `0x18007331c`
- `0x1800739a8`
- `0x180079ebc`
- `0x18007a0e4`
- `0x18007d46c`
- `0x18007d4f8`
- `0x18007d584`
- `0x18007d610`
- `0x180082824`
- `0x180083d8c`
- `0x1800a4504`
- `0x1800a45ac`
- `0x1800a4654`
- `0x1800a7920`
- `0x1800a7a10`
- `0x1800a7de4`
- `0x1800a7e48`
- `0x1800a7eac`
- `0x1800a7f10`
- `0x1800a7f74`
- `0x1800a7fd8`
- `0x1800a838c`
- `0x1800a8420`
- `0x1800a84b4`
- `0x1800aaa70`
- `0x1800ade3c`
- `0x1800bb694`
- `0x1800bb784`
- `0x1800c4128`

## callees

- `0x18001d614`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x180015722`
- `msvcp_win!_Mtx_unlock` at `0x180015722`
- `combase!__imp_CoAddRefSharedService` at `0x18001570f`
- `combase!__imp_CoAddRefSharedService` at `0x18001570f`

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
0x1800156f4  push    rbx
0x1800156f6  sub     rsp, 20h
0x1800156fa  mov     rbx, rcx
0x1800156fd  lea     rcx, ?g_refCountLock@details@wil@@3Vmutex@std@@A; this
0x180015704  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180015709  mov     ecx, cs:?g_service_id@details@wil@@3KA; ulong wil::details::g_service_id
0x18001570f  call    cs:__imp_CoAddRefSharedService
0x180015715  mov     cs:?g_refCount@details@wil@@3IA, eax; uint wil::details::g_refCount
0x18001571b  lea     rcx, ?g_refCountLock@details@wil@@3Vmutex@std@@A; _Mtx_t
0x180015722  call    cs:__imp__Mtx_unlock
0x180015728  nop
0x180015729  mov     rax, rbx
0x18001572c  add     rsp, 20h
0x180015730  pop     rbx
0x180015731  retn
```
