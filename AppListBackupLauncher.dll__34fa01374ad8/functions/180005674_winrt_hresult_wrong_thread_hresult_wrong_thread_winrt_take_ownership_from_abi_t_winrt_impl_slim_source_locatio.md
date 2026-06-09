# winrt::hresult_wrong_thread::hresult_wrong_thread(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)

- ea: `0x180005674`
- end: `0x180005694`
- name: `??0hresult_wrong_thread@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z`
- size: `32`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000f214`

## callees

- `0x180005314`

## pseudocode

```c
__int64 __fastcall winrt::hresult_wrong_thread::hresult_wrong_thread(__int64 a1, __int64 a2, __int64 a3)
{
  winrt::hresult_error::hresult_error(a1, winrt::impl::error_wrong_thread, a3, a3);
  return a1;
}

```

## disassembly

```asm
0x180005674  push    rbx
0x180005676  sub     rsp, 20h
0x18000567a  mov     edx, cs:?error_wrong_thread@impl@winrt@@3Uhresult@2@B; winrt::hresult const winrt::impl::error_wrong_thread
0x180005680  mov     r9, r8
0x180005683  mov     rbx, rcx
0x180005686  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18000568b  mov     rax, rbx
0x18000568e  add     rsp, 20h
0x180005692  pop     rbx
0x180005693  retn
```
