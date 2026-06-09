# winrt::com_ptr<IXamlPopupFactoryConfigurationOptions>::~com_ptr<IXamlPopupFactoryConfigurationOptions>(void)

- ea: `0x18000f104`
- end: `0x18000f118`
- name: `??1?$com_ptr@UIXamlPopupFactoryConfigurationOptions@@@winrt@@QEAA@XZ`
- size: `20`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `17`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002a907`
- `0x18002a919`
- `0x18002a92b`
- `0x18002ab5e`
- `0x18002ab70`
- `0x18002ab82`
- `0x18002bc92`
- `0x18002bca4`
- `0x18002bcb6`
- `0x18002bcc8`
- `0x18002bcec`
- `0x18002bcfe`
- `0x18002bd10`
- `0x18002be88`
- `0x18002bef4`
- `0x18002bf06`
- `0x18002bf5a`

## callees

- `0x18000b5f0`
- `0x18000f104`

## pseudocode

```c
__int64 __fastcall winrt::com_ptr<IXamlPopupFactoryConfigurationOptions>::~com_ptr<IXamlPopupFactoryConfigurationOptions>(
        _QWORD *a1)
{
  __int64 result; // rax

  if ( *a1 )
    return winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(a1);
  return result;
}

```

## disassembly

```asm
0x18000f104  sub     rsp, 28h
0x18000f108  cmp     qword ptr [rcx], 0
0x18000f10c  jz      short loc_18000F113
0x18000f10e  call    ?unconditional_release_ref@?$com_ptr@UINetFwPolicy2@@@winrt@@AEAAXXZ; winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(void)
0x18000f113  add     rsp, 28h
0x18000f117  retn
```
