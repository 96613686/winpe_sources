# winrt::hresult_wrong_thread::hresult_wrong_thread(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)

- ea: `0x14000a35c`
- end: `0x14000a37c`
- name: `??0hresult_wrong_thread@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z`
- size: `32`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000b0a8`

## callees

- `0x140009f74`

## pseudocode

```c
__int64 __fastcall winrt::hresult_wrong_thread::hresult_wrong_thread(__int64 a1, __int64 a2, unsigned int *a3)
{
  winrt::hresult_error::hresult_error(a1, winrt::impl::error_wrong_thread, (__int64)a3, a3);
  return a1;
}

```

## disassembly

```asm
0x14000a35c  push    rbx
0x14000a35e  sub     rsp, 20h
0x14000a362  mov     edx, cs:?error_wrong_thread@impl@winrt@@3Uhresult@2@B; winrt::hresult const winrt::impl::error_wrong_thread
0x14000a368  mov     r9, r8
0x14000a36b  mov     rbx, rcx
0x14000a36e  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x14000a373  mov     rax, rbx
0x14000a376  add     rsp, 20h
0x14000a37a  pop     rbx
0x14000a37b  retn
```
