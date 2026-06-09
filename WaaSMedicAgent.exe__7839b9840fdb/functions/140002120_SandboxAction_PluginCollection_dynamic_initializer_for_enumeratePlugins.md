# SandboxAction::PluginCollection::_dynamic_initializer_for__enumeratePlugins__

- ea: `0x140002120`
- end: `0x14000214d`
- name: `SandboxAction::PluginCollection::_dynamic_initializer_for__enumeratePlugins__`
- size: `45`
- prototype: `int()`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140002db8`
- `0x140004290`

## string_xrefs

- `0x14000212a`: `Capsule_EnumeratePlugins`

## pseudocode

```c
int SandboxAction::PluginCollection::_dynamic_initializer_for__enumeratePlugins__()
{
  std::wstring::_Construct<1,unsigned short const *>(
    (char **)SandboxAction::PluginCollection::enumeratePlugins,
    L"Capsule_EnumeratePlugins",
    0x18u);
  return atexit(SandboxAction::PluginCollection::_dynamic_atexit_destructor_for__enumeratePlugins__);
}

```

## disassembly

```asm
0x140002120  sub     rsp, 28h
0x140002124  mov     r8d, 18h
0x14000212a  lea     rdx, aCapsuleEnumera; "Capsule_EnumeratePlugins"
0x140002131  lea     rcx, ?enumeratePlugins@PluginCollection@SandboxAction@@3V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const SandboxAction::PluginCollection::enumeratePlugins
0x140002138  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14000213d  lea     rcx, SandboxAction__PluginCollection___dynamic_atexit_destructor_for__enumeratePlugins__
0x140002144  add     rsp, 28h
0x140002148  jmp     atexit
```
