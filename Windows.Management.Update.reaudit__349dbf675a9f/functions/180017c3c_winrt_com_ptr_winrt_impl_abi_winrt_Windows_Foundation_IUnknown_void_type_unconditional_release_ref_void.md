# winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)

- ea: `0x180017c3c`
- end: `0x180017c52`
- name: `?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ`
- size: `22`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `67`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180011460`
- `0x180011610`
- `0x180011954`
- `0x180011ad0`
- `0x180011c34`
- `0x180011ddc`
- `0x1800121f8`
- `0x180012324`
- `0x180012490`
- `0x180012504`
- `0x1800125c0`
- `0x180012628`
- `0x18001272c`
- `0x1800128a0`
- `0x180012970`
- `0x180012a30`
- `0x180012b20`
- `0x180012bf0`
- `0x180013ba0`
- `0x180015660`
- `0x1800171c4`
- `0x180017400`
- `0x180017470`
- `0x180017510`
- `0x1800176c0`
- `0x180017870`
- `0x180017b18`
- `0x180018b84`
- `0x180019118`
- `0x18001d150`
- `0x18001ede0`
- `0x18001efbc`
- `0x18001f3b4`
- `0x18001f3f4`
- `0x18001f628`
- `0x18001fa0c`
- `0x18001fa3c`
- `0x18001fd70`
- `0x18001fdd0`
- `0x180020010`
- `0x180020144`
- `0x180020464`
- `0x180020730`
- `0x180020890`
- `0x1800209b0`
- `0x180020bc0`
- `0x180020cdc`
- `0x1800213ac`
- `0x180023118`
- `0x180024600`

## callees

- `0x18002c010`

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
0x180017c3c  mov     rdx, [rcx]
0x180017c3f  and     qword ptr [rcx], 0
0x180017c43  mov     rcx, rdx
0x180017c46  mov     rax, [rdx]
0x180017c49  mov     rax, [rax+10h]
0x180017c4d  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
