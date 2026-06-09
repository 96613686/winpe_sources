# winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)

- ea: `0x180014974`
- end: `0x18001498d`
- name: `?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ`
- size: `25`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `41`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000de70`
- `0x18000e920`
- `0x18000ea80`
- `0x18000ee84`
- `0x18000efa8`
- `0x18000f3e8`
- `0x18000f954`
- `0x18000fa8c`
- `0x18000fb40`
- `0x18000fdf4`
- `0x180011018`
- `0x180012870`
- `0x180013b14`
- `0x180014170`
- `0x180014838`
- `0x180014e40`
- `0x180014fec`
- `0x180015198`
- `0x1800152f8`
- `0x180015efc`
- `0x18001656c`
- `0x180016638`
- `0x1800166ec`
- `0x1800167c4`
- `0x180016bd0`
- `0x180016ca0`
- `0x180016da4`
- `0x180016e7c`
- `0x180016f4c`
- `0x180017024`
- `0x1800176ec`
- `0x180017c54`
- `0x180018090`
- `0x180018264`
- `0x1800184c4`
- `0x180018580`
- `0x18001863c`
- `0x180018710`
- `0x180030a75`
- `0x180030b79`
- `0x180030c7d`

## callees

- `0x180032010`

## pseudocode

```c
__int64 __fastcall winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(
        __int64 *a1)
{
  __int64 v1; // rdx

  v1 = *a1;
  *a1 = 0;
  return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
}

```

## disassembly

```asm
0x180014974  mov     rdx, [rcx]
0x180014977  mov     qword ptr [rcx], 0
0x18001497e  mov     rcx, rdx
0x180014981  mov     rax, [rdx]
0x180014984  mov     rax, [rax+10h]
0x180014988  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
