# winrt::hresult_access_denied::hresult_access_denied(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)

- ea: `0x180006040`
- end: `0x180006060`
- name: `??0hresult_access_denied@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z`
- size: `32`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180009c90`

## callees

- `0x18000614c`

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
0x180006040  push    rbx
0x180006042  sub     rsp, 20h
0x180006046  mov     edx, cs:?error_access_denied@impl@winrt@@3Uhresult@2@B; winrt::hresult const winrt::impl::error_access_denied
0x18000604c  mov     r9, r8
0x18000604f  mov     rbx, rcx
0x180006052  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x180006057  mov     rax, rbx
0x18000605a  add     rsp, 20h
0x18000605e  pop     rbx
0x18000605f  retn
```
