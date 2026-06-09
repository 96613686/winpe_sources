# std::unique_ptr_unsigned_short__BPT::CoCreateUsingDiagnosticsMode_::_2_::CoTaskMemFreeFunctor_::_unique_ptr_unsigned_short__BPT::CoCreateUsingDiagnosticsMode_::_2_::CoTaskMemFreeFunctor_

- ea: `0x180030ab4`
- end: `0x180030acb`
- name: `std::unique_ptr_unsigned_short__BPT::CoCreateUsingDiagnosticsMode_::_2_::CoTaskMemFreeFunctor_::_unique_ptr_unsigned_short__BPT::CoCreateUsingDiagnosticsMode_::_2_::CoTaskMemFreeFunctor_`
- size: `23`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1800341fd`

## callees

- `0x180030ab4`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180030ac0`
- `ole32!CoTaskMemFree` at `0x180030ac0`

## pseudocode

```c
void __fastcall std::unique_ptr_unsigned_short__BPT::CoCreateUsingDiagnosticsMode_::_2_::CoTaskMemFreeFunctor_::_unique_ptr_unsigned_short__BPT::CoCreateUsingDiagnosticsMode_::_2_::CoTaskMemFreeFunctor_(
        void **a1)
{
  void *v1; // rcx

  v1 = *a1;
  if ( v1 )
    CoTaskMemFree(v1);
}

```

## disassembly

```asm
0x180030ab4  sub     rsp, 28h
0x180030ab8  mov     rcx, [rcx]; pv
0x180030abb  test    rcx, rcx
0x180030abe  jz      short loc_180030AC6
0x180030ac0  call    cs:__imp_CoTaskMemFree
0x180030ac6  add     rsp, 28h
0x180030aca  retn
```
