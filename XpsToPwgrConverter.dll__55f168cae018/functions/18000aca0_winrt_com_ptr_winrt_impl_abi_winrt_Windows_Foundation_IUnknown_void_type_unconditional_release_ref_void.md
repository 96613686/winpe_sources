# winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)

- ea: `0x18000aca0`
- end: `0x18000acb9`
- name: `?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ`
- size: `25`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000df98`
- `0x18000ef40`
- `0x1800100ed`
- `0x1800103bd`

## callees

- `0x180011010`

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
0x18000aca0  mov     rdx, [rcx]
0x18000aca3  mov     qword ptr [rcx], 0
0x18000acaa  mov     rcx, rdx
0x18000acad  mov     rax, [rdx]
0x18000acb0  mov     rax, [rax+10h]
0x18000acb4  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
