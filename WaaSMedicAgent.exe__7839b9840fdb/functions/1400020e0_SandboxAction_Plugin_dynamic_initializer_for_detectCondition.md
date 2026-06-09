# SandboxAction::Plugin::_dynamic_initializer_for__detectCondition__

- ea: `0x1400020e0`
- end: `0x14000210d`
- name: `SandboxAction::Plugin::_dynamic_initializer_for__detectCondition__`
- size: `45`
- prototype: `int()`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140002db8`
- `0x140004290`

## string_xrefs

- `0x1400020ea`: `Plugin_DetectCondition`

## pseudocode

```c
int SandboxAction::Plugin::_dynamic_initializer_for__detectCondition__()
{
  std::wstring::_Construct<1,unsigned short const *>(
    (char **)&SandboxAction::Plugin::detectCondition,
    L"Plugin_DetectCondition",
    0x16u);
  return atexit(SandboxAction::Plugin::_dynamic_atexit_destructor_for__detectCondition__);
}

```

## disassembly

```asm
0x1400020e0  sub     rsp, 28h
0x1400020e4  mov     r8d, 16h
0x1400020ea  lea     rdx, aPluginDetectco; "Plugin_DetectCondition"
0x1400020f1  lea     rcx, ?detectCondition@Plugin@SandboxAction@@3V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const SandboxAction::Plugin::detectCondition
0x1400020f8  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1400020fd  lea     rcx, SandboxAction__Plugin___dynamic_atexit_destructor_for__detectCondition__
0x140002104  add     rsp, 28h
0x140002108  jmp     atexit
```
