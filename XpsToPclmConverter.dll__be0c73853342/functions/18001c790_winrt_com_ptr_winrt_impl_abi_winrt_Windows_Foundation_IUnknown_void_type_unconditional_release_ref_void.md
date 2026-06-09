# winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)

- ea: `0x18001c790`
- end: `0x18001c7a9`
- name: `?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ`
- size: `25`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001b4b8`
- `0x18001c248`
- `0x18001c354`
- `0x18001ca9c`

## callees

- `0x18001f010`

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
0x18001c790  mov     rdx, [rcx]
0x18001c793  mov     qword ptr [rcx], 0
0x18001c79a  mov     rcx, rdx
0x18001c79d  mov     rax, [rdx]
0x18001c7a0  mov     rax, [rax+10h]
0x18001c7a4  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
