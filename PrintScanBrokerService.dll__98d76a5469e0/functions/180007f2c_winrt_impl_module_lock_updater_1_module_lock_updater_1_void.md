# winrt::impl::module_lock_updater<1>::~module_lock_updater<1>(void)

- ea: `0x180007f2c`
- end: `0x180007f94`
- name: `??1?$module_lock_updater@$00@impl@winrt@@QEAA@XZ`
- size: `104`
- prototype: `int()`
- caller_count: `4`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180007f9c`
- `0x180007fc0`
- `0x18000d610`
- `0x18001251c`

## callees

- `0x180007f2c`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x180007f88`
- `msvcp_win!_Mtx_unlock` at `0x180007f88`
- `msvcp_win!_Mtx_lock` at `0x180007f37`
- `msvcp_win!_Mtx_lock` at `0x180007f37`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180007f46`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180007f68`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180007f46`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180007f68`
- `combase!__imp_CoReleaseSharedService` at `0x180007f75`
- `combase!__imp_CoReleaseSharedService` at `0x180007f75`

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
  if ( dword_1800606AC == 0x7FFFFFFF )
  {
    dword_1800606AC = 2147483646;
    std::_Throw_Cpp_error(6);
    __debugbreak();
  }
  wil::details::g_refCount = CoReleaseSharedService(wil::details::g_service_id);
  return _Mtx_unlock((_Mtx_t)&wil::details::g_refCountLock);
}

```

## disassembly

```asm
0x180007f2c  sub     rsp, 28h
0x180007f30  lea     rcx, ?g_refCountLock@details@wil@@3Vmutex@std@@A; _Mtx_t
0x180007f37  call    cs:__imp__Mtx_lock
0x180007f3d  test    eax, eax
0x180007f3f  jz      short loc_180007F4D
0x180007f41  mov     ecx, 5
0x180007f46  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180007f4c  int     3; Trap to Debugger
0x180007f4d  cmp     cs:dword_1800606AC, 7FFFFFFFh
0x180007f57  jnz     short loc_180007F6F
0x180007f59  mov     cs:dword_1800606AC, 7FFFFFFEh
0x180007f63  mov     ecx, 6
0x180007f68  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180007f6e  int     3; Trap to Debugger
0x180007f6f  mov     ecx, cs:?g_service_id@details@wil@@3KA; ulong wil::details::g_service_id
0x180007f75  call    cs:__imp_CoReleaseSharedService
0x180007f7b  mov     cs:?g_refCount@details@wil@@3IA, eax; uint wil::details::g_refCount
0x180007f81  lea     rcx, ?g_refCountLock@details@wil@@3Vmutex@std@@A; _Mtx_t
0x180007f88  call    cs:__imp__Mtx_unlock
0x180007f8e  nop
0x180007f8f  add     rsp, 28h
0x180007f93  retn
```
