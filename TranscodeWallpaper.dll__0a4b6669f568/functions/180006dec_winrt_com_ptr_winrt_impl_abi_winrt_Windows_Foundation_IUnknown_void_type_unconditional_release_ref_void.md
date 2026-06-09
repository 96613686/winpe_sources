# winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)

- ea: `0x180006dec`
- end: `0x180006e05`
- name: `?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ`
- size: `25`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `8`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180006d6c`
- `0x18000c14c`
- `0x18000cdc0`
- `0x18000d230`
- `0x18000d5f0`
- `0x18000e927`
- `0x18000ea20`
- `0x18000eb19`

## callees

- `0x18000f010`

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
0x180006dec  mov     rdx, [rcx]
0x180006def  mov     qword ptr [rcx], 0
0x180006df6  mov     rcx, rdx
0x180006df9  mov     rax, [rdx]
0x180006dfc  mov     rax, [rax+10h]
0x180006e00  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
