# winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)

- ea: `0x180022a18`
- end: `0x180022a31`
- name: `?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ`
- size: `25`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `25`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001c99c`
- `0x18001ca58`
- `0x18001d048`
- `0x18001d160`
- `0x18001d278`
- `0x18001d390`
- `0x18001d4a8`
- `0x18001d5c0`
- `0x18001d6d8`
- `0x18001d7f0`
- `0x18001d90c`
- `0x18001de08`
- `0x18001e080`
- `0x18001e438`
- `0x18001f4c8`
- `0x18001f90c`
- `0x18001fa8c`
- `0x18001faf0`
- `0x18001fb50`
- `0x18001ff2c`
- `0x180021c9c`
- `0x180021ddc`
- `0x1800220bc`
- `0x180022258`
- `0x180022888`

## callees

- `0x180031010`

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
0x180022a18  mov     rdx, [rcx]
0x180022a1b  mov     qword ptr [rcx], 0
0x180022a22  mov     rcx, rdx
0x180022a25  mov     rax, [rdx]
0x180022a28  mov     rax, [rax+10h]
0x180022a2c  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
