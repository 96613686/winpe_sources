# winrt::impl::module_lock_updater<1>::~module_lock_updater<1>(void)

- ea: `0x18001d524`
- end: `0x18001d58c`
- name: `??1?$module_lock_updater@$00@impl@winrt@@QEAA@XZ`
- size: `104`
- prototype: `int()`
- caller_count: `5`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18001d600`
- `0x18001fcc8`
- `0x18001fd60`
- `0x18001fe20`
- `0x180021274`

## callees

- `0x18001d524`

## import_xrefs

- `msvcp_win!_Mtx_lock` at `0x18001d52f`
- `msvcp_win!_Mtx_lock` at `0x18001d52f`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001d53e`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001d560`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001d53e`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001d560`
- `msvcp_win!_Mtx_unlock` at `0x18001d580`
- `msvcp_win!_Mtx_unlock` at `0x18001d580`
- `combase!__imp_CoReleaseSharedService` at `0x18001d56d`
- `combase!__imp_CoReleaseSharedService` at `0x18001d56d`

## pseudocode

```c
int winrt::impl::module_lock_updater<1>::~module_lock_updater<1>()
{
  if ( _Mtx_lock((_Mtx_t)&wil::details::g_refCountLock) )
  {
    std::_Throw_Cpp_error(5);
    __debugbreak();
  }
  if ( dword_18015926C == 0x7FFFFFFF )
  {
    dword_18015926C = 2147483646;
    std::_Throw_Cpp_error(6);
    __debugbreak();
  }
  wil::details::g_refCount = CoReleaseSharedService(wil::details::g_service_id);
  return _Mtx_unlock((_Mtx_t)&wil::details::g_refCountLock);
}

```

## disassembly

```asm
0x18001d524  sub     rsp, 28h
0x18001d528  lea     rcx, ?g_refCountLock@details@wil@@3Vmutex@std@@A; _Mtx_t
0x18001d52f  call    cs:__imp__Mtx_lock
0x18001d535  test    eax, eax
0x18001d537  jz      short loc_18001D545
0x18001d539  mov     ecx, 5
0x18001d53e  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18001d544  int     3; Trap to Debugger
0x18001d545  cmp     cs:dword_18015926C, 7FFFFFFFh
0x18001d54f  jnz     short loc_18001D567
0x18001d551  mov     cs:dword_18015926C, 7FFFFFFEh
0x18001d55b  mov     ecx, 6
0x18001d560  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18001d566  int     3; Trap to Debugger
0x18001d567  mov     ecx, cs:?g_service_id@details@wil@@3KA; ulong wil::details::g_service_id
0x18001d56d  call    cs:__imp_CoReleaseSharedService
0x18001d573  mov     cs:?g_refCount@details@wil@@3IA, eax; uint wil::details::g_refCount
0x18001d579  lea     rcx, ?g_refCountLock@details@wil@@3Vmutex@std@@A; _Mtx_t
0x18001d580  call    cs:__imp__Mtx_unlock
0x18001d586  nop
0x18001d587  add     rsp, 28h
0x18001d58b  retn
```
