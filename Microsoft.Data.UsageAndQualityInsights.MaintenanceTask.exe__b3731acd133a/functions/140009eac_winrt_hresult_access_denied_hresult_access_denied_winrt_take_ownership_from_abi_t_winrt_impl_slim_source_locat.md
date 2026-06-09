# winrt::hresult_access_denied::hresult_access_denied(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)

- ea: `0x140009eac`
- end: `0x140009ecc`
- name: `??0hresult_access_denied@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z`
- size: `32`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000b0a8`

## callees

- `0x140009f74`

## pseudocode

```c
__int64 __fastcall winrt::hresult_access_denied::hresult_access_denied(__int64 a1, __int64 a2, __int64 a3)
{
  winrt::hresult_error::hresult_error(a1, winrt::impl::error_access_denied, a3, a3);
  return a1;
}

```

## disassembly

```asm
0x140009eac  push    rbx
0x140009eae  sub     rsp, 20h
0x140009eb2  mov     edx, cs:?error_access_denied@impl@winrt@@3Uhresult@2@B; winrt::hresult const winrt::impl::error_access_denied
0x140009eb8  mov     r9, r8
0x140009ebb  mov     rbx, rcx
0x140009ebe  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x140009ec3  mov     rax, rbx
0x140009ec6  add     rsp, 20h
0x140009eca  pop     rbx
0x140009ecb  retn
```
