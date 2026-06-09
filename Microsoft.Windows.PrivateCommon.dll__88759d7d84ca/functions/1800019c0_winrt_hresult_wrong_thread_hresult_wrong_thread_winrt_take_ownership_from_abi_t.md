# winrt::hresult_wrong_thread::hresult_wrong_thread(winrt::take_ownership_from_abi_t)

- ea: `0x1800019c0`
- end: `0x1800019dd`
- name: `??0hresult_wrong_thread@winrt@@QEAA@Utake_ownership_from_abi_t@1@@Z`
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
__int64 __fastcall winrt::hresult_wrong_thread::hresult_wrong_thread(__int64 a1)
{
  winrt::hresult_error::hresult_error(a1, winrt::impl::error_wrong_thread);
  return a1;
}

```

## disassembly

```asm
0x1800019c0  push    rbx
0x1800019c2  sub     rsp, 20h
0x1800019c6  mov     edx, cs:?error_wrong_thread@impl@winrt@@3Uhresult@2@B
0x1800019cc  mov     rbx, rcx
0x1800019cf  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@Utake_ownership_from_abi_t@1@@Z
0x1800019d4  mov     rax, rbx
0x1800019d7  add     rsp, 20h
0x1800019db  pop     rbx
0x1800019dc  retn
```
