# _dynamic_initializer_for__EnvironmentConfigurationKeyMap___0

- ea: `0x180001df0`
- end: `0x180001ea4`
- name: `_dynamic_initializer_for__EnvironmentConfigurationKeyMap___0`
- size: `180`
- prototype: `int()`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000274c`
- `0x18000424c`

## pseudocode

```c
int dynamic_initializer_for__EnvironmentConfigurationKeyMap___0()
{
  std::wstring::wstring(qword_18001FBA0, L"ReverbSmall");
  std::wstring::wstring(qword_18001FBC0, L"ReverbMedium");
  std::wstring::wstring(qword_18001FBE0, L"ReverbLarge");
  std::wstring::wstring(qword_18001FC00, L"ReverbOutdoor");
  std::wstring::wstring(qword_18001FC20, L"ReverbAverage");
  std::wstring::wstring(qword_18001FC40, L"ReverbDynamicShort");
  std::wstring::wstring(qword_18001FC60, L"ReverbDynamicMedium");
  std::wstring::wstring(qword_18001FC80, L"ReverbDynamicLong");
  return atexit(dynamic_atexit_destructor_for__EnvironmentConfigurationKeyMap___0);
}

```

## disassembly

```asm
0x180001df0  sub     rsp, 28h
0x180001df4  lea     rdx, aReverbsmall; "ReverbSmall"
0x180001dfb  lea     rcx, qword_18001FBA0; void *
0x180001e02  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x180001e07  nop
0x180001e08  lea     rdx, aReverbmedium; "ReverbMedium"
0x180001e0f  lea     rcx, qword_18001FBC0; void *
0x180001e16  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x180001e1b  nop
0x180001e1c  lea     rdx, aReverblarge; "ReverbLarge"
0x180001e23  lea     rcx, qword_18001FBE0; void *
0x180001e2a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x180001e2f  nop
0x180001e30  lea     rdx, aReverboutdoor; "ReverbOutdoor"
0x180001e37  lea     rcx, qword_18001FC00; void *
0x180001e3e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x180001e43  nop
0x180001e44  lea     rdx, aReverbaverage; "ReverbAverage"
0x180001e4b  lea     rcx, qword_18001FC20; void *
0x180001e52  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x180001e57  nop
0x180001e58  lea     rdx, aReverbdynamics; "ReverbDynamicShort"
0x180001e5f  lea     rcx, qword_18001FC40; void *
0x180001e66  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x180001e6b  nop
0x180001e6c  lea     rdx, aReverbdynamicm; "ReverbDynamicMedium"
0x180001e73  lea     rcx, qword_18001FC60; void *
0x180001e7a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x180001e7f  nop
0x180001e80  lea     rdx, aReverbdynamicl; "ReverbDynamicLong"
0x180001e87  lea     rcx, qword_18001FC80; void *
0x180001e8e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x180001e93  nop
0x180001e94  lea     rcx, _dynamic_atexit_destructor_for__EnvironmentConfigurationKeyMap___0
0x180001e9b  add     rsp, 28h
0x180001e9f  jmp     atexit
```
