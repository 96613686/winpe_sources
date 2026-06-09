# _dynamic_initializer_for__Windows::Service::Task::s_staticScanTask__

- ea: `0x180003ae0`
- end: `0x180003b0d`
- name: `_dynamic_initializer_for__Windows::Service::Task::s_staticScanTask__`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800338a4`
- `0x1800569e8`

## string_xrefs

- `0x180003aea`: `Schedule Scan Static Task`

## pseudocode

```c
int dynamic_initializer_for__Windows::Service::Task::s_staticScanTask__()
{
  std::wstring::_Construct<1,wchar_t const *>(Windows::Service::Task::s_staticScanTask);
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__Windows::Service::Task::s_staticScanTask__);
}

```

## disassembly

```asm
0x180003ae0  sub     rsp, 28h
0x180003ae4  mov     r8d, 19h
0x180003aea  lea     rdx, aScheduleScanSt; "Schedule Scan Static Task"
0x180003af1  lea     rcx, ?s_staticScanTask@Task@Service@Windows@@2V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@A; std::wstring Windows::Service::Task::s_staticScanTask
0x180003af8  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180003afd  lea     rcx, _dynamic_atexit_destructor_for__Windows__Service__Task__s_staticScanTask__
0x180003b04  add     rsp, 28h
0x180003b08  jmp     atexit
```
