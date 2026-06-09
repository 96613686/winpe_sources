# _Performance::Interner::CStringInternerT_Performance::Interner::impl::hash_compare_LPCWSTR_ci_ATL::CComFakeCriticalSection_::Intern_::_1_::catch$1

- ea: `0x180028821`
- end: `0x180028841`
- name: `_Performance::Interner::CStringInternerT_Performance::Interner::impl::hash_compare_LPCWSTR_ci_ATL::CComFakeCriticalSection_::Intern_::_1_::catch$1`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001894`
- `0x18000242c`

## pseudocode

```c
void __fastcall __noreturn Performance::Interner::CStringInternerT_Performance::Interner::impl::hash_compare_LPCWSTR_ci_ATL::CComFakeCriticalSection_::Intern_::_1_::catch_1(
        __int64 a1,
        __int64 a2)
{
  operator delete(*(void **)(a2 + 120));
  throw;
}

```

## disassembly

```asm
0x180028821  mov     [rsp+arg_8], rdx
0x180028826  push    rbp
0x180028827  sub     rsp, 20h
0x18002882b  mov     rbp, rdx
0x18002882e  mov     rcx, [rbp+78h]; Block
0x180028832  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180028837  xor     edx, edx; pThrowInfo
0x180028839  xor     ecx, ecx; pExceptionObject
0x18002883b  call    _CxxThrowException_0
```
