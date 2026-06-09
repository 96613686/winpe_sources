# SandboxAction::PluginCollection::_dynamic_initializer_for__setCorrelationVector_compat__

- ea: `0x140002410`
- end: `0x14000243d`
- name: `SandboxAction::PluginCollection::_dynamic_initializer_for__setCorrelationVector_compat__`
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
int SandboxAction::PluginCollection::_dynamic_initializer_for__setCorrelationVector_compat__()
{
  std::wstring::_Construct<1,unsigned short const *>(
    (char **)SandboxAction::PluginCollection::setCorrelationVector_compat,
    L"SetCorrelationVector",
    0x14u);
  return atexit(SandboxAction::PluginCollection::_dynamic_atexit_destructor_for__setCorrelationVector_compat__);
}

```

## disassembly

```asm
0x140002410  sub     rsp, 28h
0x140002414  mov     r8d, 14h
0x14000241a  lea     rdx, aSetcorrelation; "SetCorrelationVector"
0x140002421  lea     rcx, ?setCorrelationVector_compat@PluginCollection@SandboxAction@@3V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const SandboxAction::PluginCollection::setCorrelationVector_compat
0x140002428  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14000242d  lea     rcx, SandboxAction__PluginCollection___dynamic_atexit_destructor_for__setCorrelationVector_compat__
0x140002434  add     rsp, 28h
0x140002438  jmp     atexit
```
