# winrt::impl::module_lock_updater<1>::module_lock_updater<1>(void)

- ea: `0x18000c1f0`
- end: `0x18000c261`
- name: `??0?$module_lock_updater@$00@impl@winrt@@QEAA@XZ`
- size: `113`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `7`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18000f86c`
- `0x18000faa4`
- `0x180013180`
- `0x180014a70`
- `0x180014dac`
- `0x1800175bc`
- `0x180017c78`

## callees

- `0x18000c1f0`

## import_xrefs

- `msvcp_win!_Mtx_lock` at `0x18000c200`
- `msvcp_win!_Mtx_lock` at `0x18000c200`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000c20f`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000c231`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000c20f`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000c231`
- `msvcp_win!_Mtx_unlock` at `0x18000c251`
- `msvcp_win!_Mtx_unlock` at `0x18000c251`
- `combase!__imp_CoAddRefSharedService` at `0x18000c23e`
- `combase!__imp_CoAddRefSharedService` at `0x18000c23e`

## pseudocode

```c
__int64 __fastcall winrt::impl::module_lock_updater<1>::module_lock_updater<1>(__int64 a1)
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
  wil::details::g_refCount = CoAddRefSharedService(wil::details::g_service_id);
  _Mtx_unlock((_Mtx_t)&wil::details::g_refCountLock);
  return a1;
}

```

## disassembly

```asm
0x18000c1f0  push    rbx
0x18000c1f2  sub     rsp, 20h
0x18000c1f6  mov     rbx, rcx
0x18000c1f9  lea     rcx, ?g_refCountLock@details@wil@@3Vmutex@std@@A; _Mtx_t
0x18000c200  call    cs:__imp__Mtx_lock
0x18000c206  test    eax, eax
0x18000c208  jz      short loc_18000C216
0x18000c20a  mov     ecx, 5
0x18000c20f  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18000c215  int     3; Trap to Debugger
0x18000c216  cmp     cs:dword_18010EE0C, 7FFFFFFFh
0x18000c220  jnz     short loc_18000C238
0x18000c222  mov     cs:dword_18010EE0C, 7FFFFFFEh
0x18000c22c  mov     ecx, 6
0x18000c231  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18000c237  int     3; Trap to Debugger
0x18000c238  mov     ecx, cs:?g_service_id@details@wil@@3KA; ulong wil::details::g_service_id
0x18000c23e  call    cs:__imp_CoAddRefSharedService
0x18000c244  mov     cs:?g_refCount@details@wil@@3IA, eax; uint wil::details::g_refCount
0x18000c24a  lea     rcx, ?g_refCountLock@details@wil@@3Vmutex@std@@A; _Mtx_t
0x18000c251  call    cs:__imp__Mtx_unlock
0x18000c257  nop
0x18000c258  mov     rax, rbx
0x18000c25b  add     rsp, 20h
0x18000c25f  pop     rbx
0x18000c260  retn
```
