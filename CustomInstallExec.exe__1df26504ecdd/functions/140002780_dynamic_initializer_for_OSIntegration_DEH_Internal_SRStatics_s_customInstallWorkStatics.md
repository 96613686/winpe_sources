# _dynamic_initializer_for__OSIntegration::DEH::Internal::SRStatics::s_customInstallWorkStatics__

- ea: `0x140002780`
- end: `0x14000278c`
- name: `_dynamic_initializer_for__OSIntegration::DEH::Internal::SRStatics::s_customInstallWorkStatics__`
- size: `12`
- prototype: `int()`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140003624`

## pseudocode

```c
int dynamic_initializer_for__OSIntegration::DEH::Internal::SRStatics::s_customInstallWorkStatics__()
{
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__OSIntegration::DEH::Internal::SRStatics::s_customInstallWorkStatics__);
}

```

## disassembly

```asm
0x140002780  lea     rcx, _dynamic_atexit_destructor_for__OSIntegration__DEH__Internal__SRStatics__s_customInstallWorkStatics__
0x140002787  jmp     atexit
```
