# SandboxAction::Plugin::_dynamic_initializer_for__init__

- ea: `0x140002350`
- end: `0x14000237d`
- name: `SandboxAction::Plugin::_dynamic_initializer_for__init__`
- size: `45`
- prototype: `int()`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140002db8`
- `0x140004290`

## string_xrefs

- `0x14000235a`: `Plugin_Init`

## pseudocode

```c
int SandboxAction::Plugin::_dynamic_initializer_for__init__()
{
  std::wstring::_Construct<1,unsigned short const *>(&SandboxAction::Plugin::init, L"Plugin_Init", 0xBu);
  return atexit(SandboxAction::Plugin::_dynamic_atexit_destructor_for__init__);
}

```

## disassembly

```asm
0x140002350  sub     rsp, 28h
0x140002354  mov     r8d, 0Bh
0x14000235a  lea     rdx, aPluginInit; "Plugin_Init"
0x140002361  lea     rcx, ?init@Plugin@SandboxAction@@3V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const SandboxAction::Plugin::init
0x140002368  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14000236d  lea     rcx, SandboxAction__Plugin___dynamic_atexit_destructor_for__init__
0x140002374  add     rsp, 28h
0x140002378  jmp     atexit
```
