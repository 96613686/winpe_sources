# winrt::impl::module_lock_updater<1>::~module_lock_updater<1>(void)

- ea: `0x180014618`
- end: `0x180014680`
- name: `??1?$module_lock_updater@$00@impl@winrt@@QEAA@XZ`
- size: `104`
- prototype: ``
- caller_count: `21`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180014688`
- `0x180017f20`
- `0x180017fc0`
- `0x180018060`
- `0x180018130`
- `0x180019e9c`
- `0x18001d4a0`
- `0x18001d500`
- `0x18001d598`
- `0x18001de54`
- `0x180021cc0`
- `0x1800289c0`
- `0x180028a20`
- `0x180033340`
- `0x180048720`
- `0x1800487c0`
- `0x1800489a0`
- `0x18004dadc`
- `0x1800659d0`
- `0x18007c3ac`
- `0x18007c8f0`

## callees

- `0x180014618`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x180014674`
- `msvcp_win!_Mtx_unlock` at `0x180014674`
- `msvcp_win!_Mtx_lock` at `0x180014623`
- `msvcp_win!_Mtx_lock` at `0x180014623`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180014632`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180014654`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180014632`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180014654`
- `combase!__imp_CoReleaseSharedService` at `0x180014661`
- `combase!__imp_CoReleaseSharedService` at `0x180014661`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int winrt::impl::module_lock_updater<1>::~module_lock_updater<1>()
{
  if ( _Mtx_lock((_Mtx_t)&wil::details::g_refCountLock) )
  {
    std::_Throw_Cpp_error(5);
    __debugbreak();
  }
  if ( dword_1800AEC1C == 0x7FFFFFFF )
  {
    dword_1800AEC1C = 2147483646;
    std::_Throw_Cpp_error(6);
    __debugbreak();
  }
  wil::details::g_refCount = CoReleaseSharedService(wil::details::g_service_id);
  return _Mtx_unlock((_Mtx_t)&wil::details::g_refCountLock);
}

```

## disassembly

```asm
0x180014618  sub     rsp, 28h
0x18001461c  lea     rcx, ?g_refCountLock@details@wil@@3Vmutex@std@@A; _Mtx_t
0x180014623  call    cs:__imp__Mtx_lock
0x180014629  test    eax, eax
0x18001462b  jz      short loc_180014639
0x18001462d  mov     ecx, 5
0x180014632  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180014638  int     3; Trap to Debugger
0x180014639  cmp     cs:dword_1800AEC1C, 7FFFFFFFh
0x180014643  jnz     short loc_18001465B
0x180014645  mov     cs:dword_1800AEC1C, 7FFFFFFEh
0x18001464f  mov     ecx, 6
0x180014654  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18001465a  int     3; Trap to Debugger
0x18001465b  mov     ecx, cs:?g_service_id@details@wil@@3KA; ulong wil::details::g_service_id
0x180014661  call    cs:__imp_CoReleaseSharedService
0x180014667  mov     cs:?g_refCount@details@wil@@3IA, eax; uint wil::details::g_refCount
0x18001466d  lea     rcx, ?g_refCountLock@details@wil@@3Vmutex@std@@A; _Mtx_t
0x180014674  call    cs:__imp__Mtx_unlock
0x18001467a  nop
0x18001467b  add     rsp, 28h
0x18001467f  retn
```
