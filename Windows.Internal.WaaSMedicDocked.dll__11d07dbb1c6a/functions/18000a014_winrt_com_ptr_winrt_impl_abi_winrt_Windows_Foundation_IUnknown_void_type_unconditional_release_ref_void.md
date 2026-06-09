# winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)

- ea: `0x18000a014`
- end: `0x18000a02d`
- name: `?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ`
- size: `25`
- prototype: `__int64(void)`
- caller_count: `20`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180005be0`
- `0x18000614c`
- `0x1800066b8`
- `0x180006814`
- `0x1800069d4`
- `0x180006a0c`
- `0x180006b30`
- `0x180006ba0`
- `0x180006e30`
- `0x180008030`
- `0x180008230`
- `0x180008df0`
- `0x180008fa0`
- `0x18000917c`
- `0x18000964c`
- `0x1800097e0`
- `0x180009ef0`
- `0x18000bb6e`
- `0x18000bc67`
- `0x18000bd60`

## callees

- `0x18000d010`

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
0x18000a014  mov     rdx, [rcx]
0x18000a017  mov     qword ptr [rcx], 0
0x18000a01e  mov     rcx, rdx
0x18000a021  mov     rax, [rdx]
0x18000a024  mov     rax, [rax+10h]
0x18000a028  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
