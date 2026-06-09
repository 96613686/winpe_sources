# SandboxAction::PluginCollection::_dynamic_initializer_for__setCorrelationVector__

- ea: `0x1400023d0`
- end: `0x1400023fd`
- name: `SandboxAction::PluginCollection::_dynamic_initializer_for__setCorrelationVector__`
- size: `45`
- prototype: `int()`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140002db8`
- `0x140004290`

## pseudocode

```c
int SandboxAction::PluginCollection::_dynamic_initializer_for__setCorrelationVector__()
{
  std::wstring::_Construct<1,unsigned short const *>(
    (char **)&SandboxAction::PluginCollection::setCorrelationVector,
    L"Capsule_SetCorrelationVector",
    0x1Cu);
  return atexit(SandboxAction::PluginCollection::_dynamic_atexit_destructor_for__setCorrelationVector__);
}

```

## disassembly

```asm
0x1400023d0  sub     rsp, 28h
0x1400023d4  mov     r8d, 1Ch
0x1400023da  lea     rdx, aCapsuleSetcorr; "Capsule_SetCorrelationVector"
0x1400023e1  lea     rcx, ?setCorrelationVector@PluginCollection@SandboxAction@@3V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const SandboxAction::PluginCollection::setCorrelationVector
0x1400023e8  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1400023ed  lea     rcx, SandboxAction__PluginCollection___dynamic_atexit_destructor_for__setCorrelationVector__
0x1400023f4  add     rsp, 28h
0x1400023f8  jmp     atexit
```
