# winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)

- ea: `0x18000b5d0`
- end: `0x18000b5e9`
- name: `?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ`
- size: `25`
- prototype: `double __fastcall(_QWORD)`
- caller_count: `120`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180005188`
- `0x1800055b4`
- `0x1800058b0`
- `0x1800058cc`
- `0x180005974`
- `0x180005a4c`
- `0x180005b74`
- `0x180005df8`
- `0x180006810`
- `0x1800069e0`
- `0x180008f90`
- `0x18000af78`
- `0x18000b4ac`
- `0x18000b860`
- `0x18000c4f0`
- `0x18000ca50`
- `0x18000cba4`
- `0x18000ccf8`
- `0x18000ce4c`
- `0x18000cfe4`
- `0x18000d1b0`
- `0x18000d360`
- `0x18000d4d8`
- `0x18000d688`
- `0x18000d800`
- `0x18000d9cc`
- `0x18000db2c`
- `0x18000dc50`
- `0x18000dd74`
- `0x18000de98`
- `0x18000dfbc`
- `0x18000e0e0`
- `0x18000e324`
- `0x18000e70c`
- `0x18000eaa8`
- `0x18000ec84`
- `0x18000ed88`
- `0x18000f298`
- `0x18000f30c`
- `0x18000f3bc`
- `0x18000f46c`
- `0x18000f660`
- `0x18000f708`
- `0x18000f7b0`
- `0x18000f858`
- `0x18000f900`
- `0x18000f9a8`
- `0x18000ffac`
- `0x1800104e8`
- `0x180011b80`

## callees

- `0x18002d010`

## pseudocode

```c
__int64 __fastcall winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(
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
0x18000b5d0  mov     rdx, [rcx]
0x18000b5d3  mov     qword ptr [rcx], 0
0x18000b5da  mov     rcx, rdx
0x18000b5dd  mov     rax, [rdx]
0x18000b5e0  mov     rax, [rax+10h]
0x18000b5e4  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
