# winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)

- ea: `0x180005cb0`
- end: `0x180005ccb`
- name: `?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ`
- size: `27`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `10`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001530`
- `0x1800017b0`
- `0x180001850`
- `0x180001980`
- `0x180001dc0`
- `0x180001f80`
- `0x180007070`
- `0x18000c514`
- `0x18000c63a`
- `0x18000c760`

## callees

- `0x18000b930`

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
0x180005cb0  mov     rdx, [rcx]
0x180005cb3  mov     qword ptr [rcx], 0
0x180005cba  mov     rcx, rdx
0x180005cbd  mov     rax, [rdx]
0x180005cc0  mov     rax, [rax+10h]
0x180005cc4  jmp     cs:__guard_dispatch_icall_fptr
```
