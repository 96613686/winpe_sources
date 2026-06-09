# winrt::hresult_wrong_thread::hresult_wrong_thread(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)

- ea: `0x180009ab8`
- end: `0x180009ad8`
- name: `??0hresult_wrong_thread@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z`
- size: `32`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b3ac`

## callees

- `0x1800096f0`

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
0x180009ab8  push    rbx
0x180009aba  sub     rsp, 20h
0x180009abe  mov     edx, cs:?error_wrong_thread@impl@winrt@@3Uhresult@2@B; winrt::hresult const winrt::impl::error_wrong_thread
0x180009ac4  mov     r9, r8
0x180009ac7  mov     rbx, rcx
0x180009aca  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x180009acf  mov     rax, rbx
0x180009ad2  add     rsp, 20h
0x180009ad6  pop     rbx
0x180009ad7  retn
```
