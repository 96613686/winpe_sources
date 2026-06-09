# winrt::hresult_access_denied::hresult_access_denied(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)

- ea: `0x180005208`
- end: `0x180005228`
- name: `??0hresult_access_denied@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z`
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
__int64 __fastcall winrt::hresult_access_denied::hresult_access_denied(__int64 a1, __int64 a2, __int64 a3)
{
  winrt::hresult_error::hresult_error(a1, (unsigned int)winrt::impl::error_access_denied, a3, a3);
  return a1;
}

```

## disassembly

```asm
0x180005208  push    rbx
0x18000520a  sub     rsp, 20h
0x18000520e  mov     edx, cs:?error_access_denied@impl@winrt@@3Uhresult@2@B; winrt::hresult const winrt::impl::error_access_denied
0x180005214  mov     r9, r8
0x180005217  mov     rbx, rcx
0x18000521a  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18000521f  mov     rax, rbx
0x180005222  add     rsp, 20h
0x180005226  pop     rbx
0x180005227  retn
```
