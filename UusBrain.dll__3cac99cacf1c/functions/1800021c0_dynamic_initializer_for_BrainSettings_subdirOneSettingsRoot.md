# _dynamic_initializer_for__BrainSettings::_subdirOneSettingsRoot__

- ea: `0x1800021c0`
- end: `0x1800021ed`
- name: `_dynamic_initializer_for__BrainSettings::_subdirOneSettingsRoot__`
- size: `45`
- prototype: `int()`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180029518`
- `0x180042ba4`

## string_xrefs

- `0x1800021ca`: `%ProgramData%\Microsoft\Windows\OneSettings`

## pseudocode

```c
int dynamic_initializer_for__BrainSettings::_subdirOneSettingsRoot__()
{
  std::wstring::_Construct<1,wchar_t const *>(&BrainSettings::_subdirOneSettingsRoot);
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__BrainSettings::_subdirOneSettingsRoot__);
}

```

## disassembly

```asm
0x1800021c0  sub     rsp, 28h
0x1800021c4  mov     r8d, 2Bh ; '+'
0x1800021ca  lea     rdx, aProgramdataMic_0; "%ProgramData%\\Microsoft\\Windows\\OneS"...
0x1800021d1  lea     rcx, ?_subdirOneSettingsRoot@BrainSettings@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const BrainSettings::_subdirOneSettingsRoot
0x1800021d8  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800021dd  lea     rcx, _dynamic_atexit_destructor_for__BrainSettings___subdirOneSettingsRoot__
0x1800021e4  add     rsp, 28h
0x1800021e8  jmp     atexit
```
