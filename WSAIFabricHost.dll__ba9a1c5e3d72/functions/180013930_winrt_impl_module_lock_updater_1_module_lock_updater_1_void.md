# winrt::impl::module_lock_updater<1>::module_lock_updater<1>(void)

- ea: `0x180013930`
- end: `0x1800139a1`
- name: `??0?$module_lock_updater@$00@impl@winrt@@QEAA@XZ`
- size: `113`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `54`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180012de4`
- `0x1800137a0`
- `0x180019440`
- `0x18001a1a0`
- `0x18001a6b4`
- `0x18001dc68`
- `0x18001e4a0`
- `0x18001e8ec`
- `0x180021d2c`
- `0x1800240c8`
- `0x1800241b8`
- `0x180027f48`
- `0x18002bbb4`
- `0x18002bd1c`
- `0x18002e9ac`
- `0x18002eb08`
- `0x18002ec64`
- `0x18002f824`
- `0x180030310`
- `0x180030410`
- `0x180030510`
- `0x180030600`
- `0x180030700`
- `0x180030800`
- `0x180030900`
- `0x180030a00`
- `0x180030af0`
- `0x180030bf0`
- `0x180030f6c`
- `0x1800353b8`
- `0x180035cb0`
- `0x180037a10`
- `0x180037b10`
- `0x180037d00`
- `0x180043400`
- `0x18004a3a0`
- `0x18004b240`
- `0x18004b7b0`
- `0x18004bf60`
- `0x18004c4b0`
- `0x180052410`
- `0x180053984`
- `0x180059e98`
- `0x180059f60`
- `0x18005a050`
- `0x18005a200`
- `0x18005d800`
- `0x180062660`
- `0x18006e4d4`
- `0x18006e878`

## callees

- `0x180013930`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x180013991`
- `msvcp_win!_Mtx_unlock` at `0x180013991`
- `msvcp_win!_Mtx_lock` at `0x180013940`
- `msvcp_win!_Mtx_lock` at `0x180013940`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001394f`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180013971`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001394f`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180013971`
- `combase!__imp_CoAddRefSharedService` at `0x18001397e`
- `combase!__imp_CoAddRefSharedService` at `0x18001397e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall winrt::impl::module_lock_updater<1>::module_lock_updater<1>(__int64 a1)
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
  wil::details::g_refCount = CoAddRefSharedService(wil::details::g_service_id);
  _Mtx_unlock((_Mtx_t)&wil::details::g_refCountLock);
  return a1;
}

```

## disassembly

```asm
0x180013930  push    rbx
0x180013932  sub     rsp, 20h
0x180013936  mov     rbx, rcx
0x180013939  lea     rcx, ?g_refCountLock@details@wil@@3Vmutex@std@@A; _Mtx_t
0x180013940  call    cs:__imp__Mtx_lock
0x180013946  test    eax, eax
0x180013948  jz      short loc_180013956
0x18001394a  mov     ecx, 5
0x18001394f  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180013955  int     3; Trap to Debugger
0x180013956  cmp     cs:dword_1800AEC1C, 7FFFFFFFh
0x180013960  jnz     short loc_180013978
0x180013962  mov     cs:dword_1800AEC1C, 7FFFFFFEh
0x18001396c  mov     ecx, 6
0x180013971  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180013977  int     3; Trap to Debugger
0x180013978  mov     ecx, cs:?g_service_id@details@wil@@3KA; ulong wil::details::g_service_id
0x18001397e  call    cs:__imp_CoAddRefSharedService
0x180013984  mov     cs:?g_refCount@details@wil@@3IA, eax; uint wil::details::g_refCount
0x18001398a  lea     rcx, ?g_refCountLock@details@wil@@3Vmutex@std@@A; _Mtx_t
0x180013991  call    cs:__imp__Mtx_unlock
0x180013997  nop
0x180013998  mov     rax, rbx
0x18001399b  add     rsp, 20h
0x18001399f  pop     rbx
0x1800139a0  retn
```
