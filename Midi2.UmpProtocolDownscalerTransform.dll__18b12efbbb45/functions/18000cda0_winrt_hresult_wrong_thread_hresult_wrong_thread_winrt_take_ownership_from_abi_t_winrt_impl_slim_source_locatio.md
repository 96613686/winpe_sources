# winrt::hresult_wrong_thread::hresult_wrong_thread(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)

- ea: `0x18000cda0`
- end: `0x18000cdc0`
- name: `??0hresult_wrong_thread@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z`
- size: `32`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180011a4c`

## callees

- `0x18000c974`

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
0x18000cda0  push    rbx
0x18000cda2  sub     rsp, 20h
0x18000cda6  mov     edx, cs:?error_wrong_thread@impl@winrt@@3Uhresult@2@B; winrt::hresult const winrt::impl::error_wrong_thread
0x18000cdac  mov     r9, r8
0x18000cdaf  mov     rbx, rcx
0x18000cdb2  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18000cdb7  mov     rax, rbx
0x18000cdba  add     rsp, 20h
0x18000cdbe  pop     rbx
0x18000cdbf  retn
```
