# winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)

- ea: `0x1800058b0`
- end: `0x1800058c4`
- name: `??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ`
- size: `20`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `52`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800104e8`
- `0x18002a691`
- `0x18002a6b5`
- `0x18002a6d9`
- `0x18002a6fd`
- `0x18002a70f`
- `0x18002a756`
- `0x18002a768`
- `0x18002a7a2`
- `0x18002a7ca`
- `0x18002a7dc`
- `0x18002a7ee`
- `0x18002a85a`
- `0x18002a889`
- `0x18002a89b`
- `0x18002a8ad`
- `0x18002a8bf`
- `0x18002a8d1`
- `0x18002a8e3`
- `0x18002a8f5`
- `0x18002a93d`
- `0x18002a94f`
- `0x18002a961`
- `0x18002a985`
- `0x18002a997`
- `0x18002a9a9`
- `0x18002a9bb`
- `0x18002a9f1`
- `0x18002aa2f`
- `0x18002aa65`
- `0x18002aa94`
- `0x18002aaa6`
- `0x18002aba6`
- `0x18002abdc`
- `0x18002abee`
- `0x18002ac2f`
- `0x18002ac65`
- `0x18002ac9b`
- `0x18002af30`
- `0x18002af5c`
- `0x18002b465`
- `0x18002b683`
- `0x18002b6b4`
- `0x18002b7b3`
- `0x18002b996`
- `0x18002b9c5`
- `0x18002ba43`
- `0x18002ba55`
- `0x18002ba79`
- `0x18002bade`

## callees

- `0x1800058b0`
- `0x18000b5d0`

## pseudocode

```c
__int64 __fastcall winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(
        _QWORD *a1)
{
  __int64 result; // rax

  if ( *a1 )
    return winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(a1);
  return result;
}

```

## disassembly

```asm
0x1800058b0  sub     rsp, 28h
0x1800058b4  cmp     qword ptr [rcx], 0
0x1800058b8  jz      short loc_1800058BF
0x1800058ba  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x1800058bf  add     rsp, 28h
0x1800058c3  retn
```
