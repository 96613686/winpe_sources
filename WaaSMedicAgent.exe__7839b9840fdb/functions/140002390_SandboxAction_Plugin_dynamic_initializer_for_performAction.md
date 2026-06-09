# SandboxAction::Plugin::_dynamic_initializer_for__performAction__

- ea: `0x140002390`
- end: `0x1400023bd`
- name: `SandboxAction::Plugin::_dynamic_initializer_for__performAction__`
- size: `45`
- prototype: `int()`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140002db8`
- `0x140004290`

## string_xrefs

- `0x14000239a`: `Plugin_PerformAction`

## pseudocode

```c
int SandboxAction::Plugin::_dynamic_initializer_for__performAction__()
{
  std::wstring::_Construct<1,unsigned short const *>(
    (char **)&SandboxAction::Plugin::performAction,
    L"Plugin_PerformAction",
    0x14u);
  return atexit(SandboxAction::Plugin::_dynamic_atexit_destructor_for__performAction__);
}

```

## disassembly

```asm
0x140002390  sub     rsp, 28h
0x140002394  mov     r8d, 14h
0x14000239a  lea     rdx, aPluginPerforma; "Plugin_PerformAction"
0x1400023a1  lea     rcx, ?performAction@Plugin@SandboxAction@@3V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const SandboxAction::Plugin::performAction
0x1400023a8  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1400023ad  lea     rcx, SandboxAction__Plugin___dynamic_atexit_destructor_for__performAction__
0x1400023b4  add     rsp, 28h
0x1400023b8  jmp     atexit
```
