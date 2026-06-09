# winrt::impl::module_lock_updater<1>::~module_lock_updater<1>(void)

- ea: `0x18000c3e8`
- end: `0x18000c450`
- name: `??1?$module_lock_updater@$00@impl@winrt@@QEAA@XZ`
- size: `104`
- prototype: `int()`
- caller_count: `4`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18000c458`
- `0x18000e968`
- `0x18000ea40`
- `0x18000fa60`

## callees

- `0x18000c3e8`

## import_xrefs

- `msvcp_win!_Mtx_lock` at `0x18000c3f3`
- `msvcp_win!_Mtx_lock` at `0x18000c3f3`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000c402`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000c424`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000c402`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000c424`
- `msvcp_win!_Mtx_unlock` at `0x18000c444`
- `msvcp_win!_Mtx_unlock` at `0x18000c444`
- `combase!__imp_CoReleaseSharedService` at `0x18000c431`
- `combase!__imp_CoReleaseSharedService` at `0x18000c431`

## pseudocode

```c
int winrt::impl::module_lock_updater<1>::~module_lock_updater<1>()
{
  if ( _Mtx_lock((_Mtx_t)&wil::details::g_refCountLock) )
  {
    std::_Throw_Cpp_error(5);
    __debugbreak();
  }
  if ( dword_18010EE0C == 0x7FFFFFFF )
  {
    dword_18010EE0C = 2147483646;
    std::_Throw_Cpp_error(6);
    __debugbreak();
  }
  wil::details::g_refCount = CoReleaseSharedService(wil::details::g_service_id);
  return _Mtx_unlock((_Mtx_t)&wil::details::g_refCountLock);
}

```

## disassembly

```asm
0x18000c3e8  sub     rsp, 28h
0x18000c3ec  lea     rcx, ?g_refCountLock@details@wil@@3Vmutex@std@@A; _Mtx_t
0x18000c3f3  call    cs:__imp__Mtx_lock
0x18000c3f9  test    eax, eax
0x18000c3fb  jz      short loc_18000C409
0x18000c3fd  mov     ecx, 5
0x18000c402  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18000c408  int     3; Trap to Debugger
0x18000c409  cmp     cs:dword_18010EE0C, 7FFFFFFFh
0x18000c413  jnz     short loc_18000C42B
0x18000c415  mov     cs:dword_18010EE0C, 7FFFFFFEh
0x18000c41f  mov     ecx, 6
0x18000c424  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18000c42a  int     3; Trap to Debugger
0x18000c42b  mov     ecx, cs:?g_service_id@details@wil@@3KA; ulong wil::details::g_service_id
0x18000c431  call    cs:__imp_CoReleaseSharedService
0x18000c437  mov     cs:?g_refCount@details@wil@@3IA, eax; uint wil::details::g_refCount
0x18000c43d  lea     rcx, ?g_refCountLock@details@wil@@3Vmutex@std@@A; _Mtx_t
0x18000c444  call    cs:__imp__Mtx_unlock
0x18000c44a  nop
0x18000c44b  add     rsp, 28h
0x18000c44f  retn
```
