# _dynamic_initializer_for__UusState::_subdirStateFolder__

- ea: `0x180001cc0`
- end: `0x180001ced`
- name: `_dynamic_initializer_for__UusState::_subdirStateFolder__`
- size: `45`
- prototype: `int()`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180029518`
- `0x180042ba4`

## string_xrefs

- `0x180001cca`: `%ProgramData%\Microsoft\Windows\UUS\State`

## pseudocode

```c
int dynamic_initializer_for__UusState::_subdirStateFolder__()
{
  std::wstring::_Construct<1,wchar_t const *>(&UusState::_subdirStateFolder);
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__UusState::_subdirStateFolder__);
}

```

## disassembly

```asm
0x180001cc0  sub     rsp, 28h
0x180001cc4  mov     r8d, 29h ; ')'
0x180001cca  lea     rdx, aProgramdataMic_1; "%ProgramData%\\Microsoft\\Windows\\UUS"...
0x180001cd1  lea     rcx, ?_subdirStateFolder@UusState@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const UusState::_subdirStateFolder
0x180001cd8  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180001cdd  lea     rcx, _dynamic_atexit_destructor_for__UusState___subdirStateFolder__
0x180001ce4  add     rsp, 28h
0x180001ce8  jmp     atexit
```
