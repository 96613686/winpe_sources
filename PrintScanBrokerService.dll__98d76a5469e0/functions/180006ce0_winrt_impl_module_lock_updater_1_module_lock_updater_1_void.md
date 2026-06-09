# winrt::impl::module_lock_updater<1>::module_lock_updater<1>(void)

- ea: `0x180006ce0`
- end: `0x180006d51`
- name: `??0?$module_lock_updater@$00@impl@winrt@@QEAA@XZ`
- size: `113`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `7`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180006674`
- `0x1800066e0`
- `0x180006744`
- `0x180006c4c`
- `0x180007020`
- `0x180009270`
- `0x1800122d8`

## callees

- `0x180006ce0`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x180006d41`
- `msvcp_win!_Mtx_unlock` at `0x180006d41`
- `msvcp_win!_Mtx_lock` at `0x180006cf0`
- `msvcp_win!_Mtx_lock` at `0x180006cf0`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180006cff`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180006d21`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180006cff`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180006d21`
- `combase!__imp_CoAddRefSharedService` at `0x180006d2e`
- `combase!__imp_CoAddRefSharedService` at `0x180006d2e`

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
  if ( dword_1800606AC == 0x7FFFFFFF )
  {
    dword_1800606AC = 2147483646;
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
0x180006ce0  push    rbx
0x180006ce2  sub     rsp, 20h
0x180006ce6  mov     rbx, rcx
0x180006ce9  lea     rcx, ?g_refCountLock@details@wil@@3Vmutex@std@@A; _Mtx_t
0x180006cf0  call    cs:__imp__Mtx_lock
0x180006cf6  test    eax, eax
0x180006cf8  jz      short loc_180006D06
0x180006cfa  mov     ecx, 5
0x180006cff  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180006d05  int     3; Trap to Debugger
0x180006d06  cmp     cs:dword_1800606AC, 7FFFFFFFh
0x180006d10  jnz     short loc_180006D28
0x180006d12  mov     cs:dword_1800606AC, 7FFFFFFEh
0x180006d1c  mov     ecx, 6
0x180006d21  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180006d27  int     3; Trap to Debugger
0x180006d28  mov     ecx, cs:?g_service_id@details@wil@@3KA; ulong wil::details::g_service_id
0x180006d2e  call    cs:__imp_CoAddRefSharedService
0x180006d34  mov     cs:?g_refCount@details@wil@@3IA, eax; uint wil::details::g_refCount
0x180006d3a  lea     rcx, ?g_refCountLock@details@wil@@3Vmutex@std@@A; _Mtx_t
0x180006d41  call    cs:__imp__Mtx_unlock
0x180006d47  nop
0x180006d48  mov     rax, rbx
0x180006d4b  add     rsp, 20h
0x180006d4f  pop     rbx
0x180006d50  retn
```
