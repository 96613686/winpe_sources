# winrt::impl::module_lock_updater<1>::module_lock_updater<1>(void)

- ea: `0x18001d11c`
- end: `0x18001d18d`
- name: `??0?$module_lock_updater@$00@impl@winrt@@QEAA@XZ`
- size: `113`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `6`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18000f47c`
- `0x18001d010`
- `0x18001deb0`
- `0x18001ecc8`
- `0x180020f0c`
- `0x1800e3914`

## callees

- `0x18001d11c`

## import_xrefs

- `msvcp_win!_Mtx_lock` at `0x18001d12c`
- `msvcp_win!_Mtx_lock` at `0x18001d12c`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001d13b`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001d15d`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001d13b`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001d15d`
- `msvcp_win!_Mtx_unlock` at `0x18001d17d`
- `msvcp_win!_Mtx_unlock` at `0x18001d17d`
- `combase!__imp_CoAddRefSharedService` at `0x18001d16a`
- `combase!__imp_CoAddRefSharedService` at `0x18001d16a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall winrt::impl::module_lock_updater<1>::module_lock_updater<1>(__int64 a1)
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
  wil::details::g_refCount = CoAddRefSharedService(wil::details::g_service_id);
  _Mtx_unlock((_Mtx_t)&wil::details::g_refCountLock);
  return a1;
}

```

## disassembly

```asm
0x18001d11c  push    rbx
0x18001d11e  sub     rsp, 20h
0x18001d122  mov     rbx, rcx
0x18001d125  lea     rcx, ?g_refCountLock@details@wil@@3Vmutex@std@@A; _Mtx_t
0x18001d12c  call    cs:__imp__Mtx_lock
0x18001d132  test    eax, eax
0x18001d134  jz      short loc_18001D142
0x18001d136  mov     ecx, 5
0x18001d13b  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18001d141  int     3; Trap to Debugger
0x18001d142  cmp     cs:dword_18015926C, 7FFFFFFFh
0x18001d14c  jnz     short loc_18001D164
0x18001d14e  mov     cs:dword_18015926C, 7FFFFFFEh
0x18001d158  mov     ecx, 6
0x18001d15d  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18001d163  int     3; Trap to Debugger
0x18001d164  mov     ecx, cs:?g_service_id@details@wil@@3KA; ulong wil::details::g_service_id
0x18001d16a  call    cs:__imp_CoAddRefSharedService
0x18001d170  mov     cs:?g_refCount@details@wil@@3IA, eax; uint wil::details::g_refCount
0x18001d176  lea     rcx, ?g_refCountLock@details@wil@@3Vmutex@std@@A; _Mtx_t
0x18001d17d  call    cs:__imp__Mtx_unlock
0x18001d183  nop
0x18001d184  mov     rax, rbx
0x18001d187  add     rsp, 20h
0x18001d18b  pop     rbx
0x18001d18c  retn
```
