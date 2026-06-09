# winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)

- ea: `0x18000f544`
- end: `0x18000f55d`
- name: `?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ`
- size: `25`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `16`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800047c0`
- `0x1800049a8`
- `0x180004d78`
- `0x180005314`
- `0x180005740`
- `0x180005b54`
- `0x180006578`
- `0x18000b770`
- `0x18000dfe0`
- `0x18000ec24`
- `0x18000efbc`
- `0x18000f474`
- `0x180010d62`
- `0x180010e6d`
- `0x180010f66`
- `0x18001105f`

## callees

- `0x180012010`

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
0x18000f544  mov     rdx, [rcx]
0x18000f547  mov     qword ptr [rcx], 0
0x18000f54e  mov     rcx, rdx
0x18000f551  mov     rax, [rdx]
0x18000f554  mov     rax, [rax+10h]
0x18000f558  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
