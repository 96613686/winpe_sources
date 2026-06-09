# winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)

- ea: `0x180003840`
- end: `0x18000385b`
- name: `?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ`
- size: `27`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `38`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180003640`
- `0x180003b50`
- `0x180003c60`
- `0x180004c30`
- `0x180004e00`
- `0x180005200`
- `0x180005d90`
- `0x180005df0`
- `0x1800060e0`
- `0x180006750`
- `0x180007190`
- `0x180007330`
- `0x180007410`
- `0x180007c40`
- `0x1800085a0`
- `0x180008850`
- `0x180008c70`
- `0x180009310`
- `0x1800093a0`
- `0x1800099a0`
- `0x18000a470`
- `0x18000bdd0`
- `0x18000be70`
- `0x18000e3e0`
- `0x18000e5e0`
- `0x18000ec30`
- `0x18000f140`
- `0x18000f430`
- `0x180011aa0`
- `0x180011c00`
- `0x1800132d0`
- `0x1800160a0`
- `0x18001c7a0`
- `0x18001ca20`
- `0x18001e4d4`
- `0x18001e5fa`
- `0x18001e720`
- `0x18001fd60`

## callees

- `0x18001cdf0`

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
0x180003840  mov     rdx, [rcx]
0x180003843  mov     qword ptr [rcx], 0
0x18000384a  mov     rcx, rdx
0x18000384d  mov     rax, [rdx]
0x180003850  mov     rax, [rax+10h]
0x180003854  jmp     cs:__guard_dispatch_icall_fptr
```
