# winrt::hresult_access_denied::hresult_access_denied(winrt::take_ownership_from_abi_t)

- ea: `0x180001960`
- end: `0x18000197d`
- name: `??0hresult_access_denied@winrt@@QEAA@Utake_ownership_from_abi_t@1@@Z`
- size: `29`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001b40`

## callees

- `0x180001530`

## pseudocode

```c
__int64 __fastcall winrt::hresult_access_denied::hresult_access_denied(__int64 a1)
{
  winrt::hresult_error::hresult_error(a1, (unsigned int)winrt::impl::error_access_denied);
  return a1;
}

```

## disassembly

```asm
0x180001960  push    rbx
0x180001962  sub     rsp, 20h
0x180001966  mov     edx, cs:?error_access_denied@impl@winrt@@3Uhresult@2@B
0x18000196c  mov     rbx, rcx
0x18000196f  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@Utake_ownership_from_abi_t@1@@Z
0x180001974  mov     rax, rbx
0x180001977  add     rsp, 20h
0x18000197b  pop     rbx
0x18000197c  retn
```
