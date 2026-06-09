# winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)

- ea: `0x1800215e8`
- end: `0x180021601`
- name: `?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ`
- size: `25`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `22`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000eb28`
- `0x18000ec34`
- `0x18000edf0`
- `0x18000ef74`
- `0x18000f0c0`
- `0x18000f1dc`
- `0x18000f2f8`
- `0x18000f400`
- `0x18000f53c`
- `0x18000f644`
- `0x18000fbc4`
- `0x180011e60`
- `0x180012514`
- `0x180012c1c`
- `0x180012c48`
- `0x180012d20`
- `0x18001c150`
- `0x18001ee7c`
- `0x18001f560`
- `0x18001f82c`
- `0x18001fbc4`
- `0x1800214b4`

## callees

- `0x180024010`

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
0x1800215e8  mov     rdx, [rcx]
0x1800215eb  mov     qword ptr [rcx], 0
0x1800215f2  mov     rcx, rdx
0x1800215f5  mov     rax, [rdx]
0x1800215f8  mov     rax, [rax+10h]
0x1800215fc  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
