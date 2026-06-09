# winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)

- ea: `0x18000dfc0`
- end: `0x18000dfd4`
- name: `??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ`
- size: `20`
- prototype: ``
- caller_count: `91`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007fc0`
- `0x18000e050`
- `0x180013750`
- `0x180014180`
- `0x180019ab0`
- `0x18001a71c`
- `0x18001d7f8`
- `0x18001d910`
- `0x18001da2c`
- `0x18001db44`
- `0x18001dc5c`
- `0x18001dd78`
- `0x18001de94`
- `0x18001f420`
- `0x18001f844`
- `0x18001f90c`
- `0x18002051c`
- `0x1800206c8`
- `0x180020e08`
- `0x1800210c4`
- `0x1800211c4`
- `0x180021ac0`
- `0x180021cc8`
- `0x180021d80`
- `0x180021dc4`
- `0x180021f24`
- `0x180021fdc`
- `0x180022098`
- `0x180022150`
- `0x18002220c`
- `0x1800222c4`
- `0x180022380`
- `0x180022438`
- `0x180022538`
- `0x180022b40`
- `0x180022da0`
- `0x180022f5c`
- `0x180023638`
- `0x1800237dc`
- `0x180023898`
- `0x180024574`
- `0x180025278`
- `0x180025b9c`
- `0x180025c7c`
- `0x180025e70`
- `0x1800263e4`
- `0x180026480`
- `0x180026c1c`
- `0x180026f00`
- `0x1800276f8`

## callees

- `0x1800072d8`
- `0x18000dfc0`

## pseudocode

```c
__int64 __fastcall winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(
        _QWORD *a1)
{
  __int64 result; // rax

  if ( *a1 )
    return winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1);
  return result;
}

```

## disassembly

```asm
0x18000dfc0  sub     rsp, 28h
0x18000dfc4  cmp     qword ptr [rcx], 0
0x18000dfc8  jz      short loc_18000DFCF
0x18000dfca  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000dfcf  add     rsp, 28h
0x18000dfd3  retn
```
