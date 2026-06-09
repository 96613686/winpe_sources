# winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)

- ea: `0x1800072d8`
- end: `0x1800072f1`
- name: `?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ`
- size: `25`
- prototype: ``
- caller_count: `51`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180007200`
- `0x1800078ec`
- `0x180007924`
- `0x180007ea0`
- `0x18000dfc0`
- `0x18000dfdc`
- `0x18000eb3c`
- `0x18000ec2c`
- `0x18001a860`
- `0x18001a91c`
- `0x18001d7f8`
- `0x18001d910`
- `0x18001da2c`
- `0x18001db44`
- `0x18001dc5c`
- `0x18001dd78`
- `0x18001de94`
- `0x18001e738`
- `0x18001e998`
- `0x18001eca0`
- `0x18001ee78`
- `0x18001ef10`
- `0x18001fb34`
- `0x18001fd80`
- `0x180020038`
- `0x180020410`
- `0x18002086c`
- `0x180022b40`
- `0x180023898`
- `0x18002474c`
- `0x180024db8`
- `0x180025134`
- `0x180025380`
- `0x180025484`
- `0x1800259f0`
- `0x180025b6c`
- `0x180025c38`
- `0x180025fd0`
- `0x18002624c`
- `0x1800267b8`
- `0x180026c1c`
- `0x180026f00`
- `0x180026ff4`
- `0x180027428`
- `0x18002873c`
- `0x180028ad4`
- `0x180028f50`
- `0x1800293b0`
- `0x1800296e0`
- `0x18002a150`

## callees

- `0x180035010`

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
0x1800072d8  mov     rdx, [rcx]
0x1800072db  mov     qword ptr [rcx], 0
0x1800072e2  mov     rcx, rdx
0x1800072e5  mov     rax, [rdx]
0x1800072e8  mov     rax, [rax+10h]
0x1800072ec  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
