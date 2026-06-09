# _dynamic_initializer_for__HrtfConfigurationKey___0

- ea: `0x180001eb0`
- end: `0x180001ed7`
- name: `_dynamic_initializer_for__HrtfConfigurationKey___0`
- size: `39`
- prototype: `int()`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000274c`
- `0x18000424c`

## pseudocode

```c
int dynamic_initializer_for__HrtfConfigurationKey___0()
{
  std::wstring::wstring(&qword_18001FB80, L"Hrtf");
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__HrtfConfigurationKey___0);
}

```

## disassembly

```asm
0x180001eb0  sub     rsp, 28h
0x180001eb4  lea     rdx, aHrtf; "Hrtf"
0x180001ebb  lea     rcx, qword_18001FB80; void *
0x180001ec2  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x180001ec7  lea     rcx, _dynamic_atexit_destructor_for__HrtfConfigurationKey___0
0x180001ece  add     rsp, 28h
0x180001ed2  jmp     atexit
```
