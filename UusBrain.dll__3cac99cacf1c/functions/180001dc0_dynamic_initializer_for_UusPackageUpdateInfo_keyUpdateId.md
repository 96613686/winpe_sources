# _dynamic_initializer_for__UusPackageUpdateInfo::_keyUpdateId__

- ea: `0x180001dc0`
- end: `0x180001ded`
- name: `_dynamic_initializer_for__UusPackageUpdateInfo::_keyUpdateId__`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180029518`
- `0x180042ba4`

## string_xrefs

- `0x180001dca`: `UpdateId`

## pseudocode

```c
int dynamic_initializer_for__UusPackageUpdateInfo::_keyUpdateId__()
{
  std::wstring::_Construct<1,wchar_t const *>(UusPackageUpdateInfo::_keyUpdateId);
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__UusPackageUpdateInfo::_keyUpdateId__);
}

```

## disassembly

```asm
0x180001dc0  sub     rsp, 28h
0x180001dc4  mov     r8d, 8
0x180001dca  lea     rdx, aUpdateid; "UpdateId"
0x180001dd1  lea     rcx, ?_keyUpdateId@UusPackageUpdateInfo@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const UusPackageUpdateInfo::_keyUpdateId
0x180001dd8  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180001ddd  lea     rcx, _dynamic_atexit_destructor_for__UusPackageUpdateInfo___keyUpdateId__
0x180001de4  add     rsp, 28h
0x180001de8  jmp     atexit
```
