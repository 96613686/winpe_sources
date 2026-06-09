# winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)

- ea: `0x18000750c`
- end: `0x180007525`
- name: `?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ`
- size: `25`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `27`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180007434`
- `0x180007708`
- `0x1800086e0`
- `0x1800087f8`
- `0x180008910`
- `0x180008ce0`
- `0x180008f84`
- `0x1800092f8`
- `0x180009390`
- `0x180009f40`
- `0x18000a360`
- `0x18000a904`
- `0x18000a97c`
- `0x18000a9dc`
- `0x18000aa20`
- `0x18000c534`
- `0x18000d424`
- `0x18000f77c`
- `0x18000f8bc`
- `0x18000fa50`
- `0x18000fb18`
- `0x180010e20`
- `0x180011a10`
- `0x180011ea8`
- `0x180012f8c`
- `0x180015920`
- `0x180015a9c`

## callees

- `0x180018010`

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
0x18000750c  mov     rdx, [rcx]
0x18000750f  mov     qword ptr [rcx], 0
0x180007516  mov     rcx, rdx
0x180007519  mov     rax, [rdx]
0x18000751c  mov     rax, [rax+10h]
0x180007520  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
