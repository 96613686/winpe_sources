# _dynamic_initializer_for__OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper::s_msiExecPath__

- ea: `0x1400027a0`
- end: `0x1400027ac`
- name: `_dynamic_initializer_for__OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper::s_msiExecPath__`
- size: `12`
- prototype: `int()`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140003624`

## pseudocode

```c
int dynamic_initializer_for__OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper::s_msiExecPath__()
{
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper::s_msiExecPath__);
}

```

## disassembly

```asm
0x1400027a0  lea     rcx, _dynamic_atexit_destructor_for__OSIntegration__DEH__Internal__CustomInstallActionWinRTHelper__s_msiExecPath__
0x1400027a7  jmp     atexit
```
