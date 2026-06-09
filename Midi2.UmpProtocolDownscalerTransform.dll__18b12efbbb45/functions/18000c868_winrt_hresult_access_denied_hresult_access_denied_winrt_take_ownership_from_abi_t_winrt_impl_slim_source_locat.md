# winrt::hresult_access_denied::hresult_access_denied(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)

- ea: `0x18000c868`
- end: `0x18000c888`
- name: `??0hresult_access_denied@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z`
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
__int64 __fastcall winrt::hresult_access_denied::hresult_access_denied(__int64 a1, __int64 a2, __int64 a3)
{
  winrt::hresult_error::hresult_error(a1, winrt::impl::error_access_denied, a3, a3);
  return a1;
}

```

## disassembly

```asm
0x18000c868  push    rbx
0x18000c86a  sub     rsp, 20h
0x18000c86e  mov     edx, cs:?error_access_denied@impl@winrt@@3Uhresult@2@B; winrt::hresult const winrt::impl::error_access_denied
0x18000c874  mov     r9, r8
0x18000c877  mov     rbx, rcx
0x18000c87a  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x18000c87f  mov     rax, rbx
0x18000c882  add     rsp, 20h
0x18000c886  pop     rbx
0x18000c887  retn
```
