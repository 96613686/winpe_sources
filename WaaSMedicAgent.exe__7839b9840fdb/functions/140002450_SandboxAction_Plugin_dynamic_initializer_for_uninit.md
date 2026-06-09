# SandboxAction::Plugin::_dynamic_initializer_for__uninit__

- ea: `0x140002450`
- end: `0x14000247d`
- name: `SandboxAction::Plugin::_dynamic_initializer_for__uninit__`
- size: `45`
- prototype: `int()`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140002db8`
- `0x140004290`

## string_xrefs

- `0x14000245a`: `Plugin_Uninit`

## pseudocode

```c
int SandboxAction::Plugin::_dynamic_initializer_for__uninit__()
{
  std::wstring::_Construct<1,unsigned short const *>((char **)&SandboxAction::Plugin::uninit, L"Plugin_Uninit", 0xDu);
  return atexit(SandboxAction::Plugin::_dynamic_atexit_destructor_for__uninit__);
}

```

## disassembly

```asm
0x140002450  sub     rsp, 28h
0x140002454  mov     r8d, 0Dh
0x14000245a  lea     rdx, aPluginUninit; "Plugin_Uninit"
0x140002461  lea     rcx, ?uninit@Plugin@SandboxAction@@3V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const SandboxAction::Plugin::uninit
0x140002468  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14000246d  lea     rcx, SandboxAction__Plugin___dynamic_atexit_destructor_for__uninit__
0x140002474  add     rsp, 28h
0x140002478  jmp     atexit
```
