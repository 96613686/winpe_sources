# _dynamic_initializer_for__UusPackage::_filenameBom__

- ea: `0x180001f80`
- end: `0x180001fad`
- name: `_dynamic_initializer_for__UusPackage::_filenameBom__`
- size: `45`
- prototype: `int()`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180029518`
- `0x180042ba4`

## string_xrefs

- `0x180001f8a`: `uusp.json`

## pseudocode

```c
int dynamic_initializer_for__UusPackage::_filenameBom__()
{
  std::wstring::_Construct<1,wchar_t const *>(&UusPackage::_filenameBom);
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__UusPackage::_filenameBom__);
}

```

## disassembly

```asm
0x180001f80  sub     rsp, 28h
0x180001f84  mov     r8d, 9
0x180001f8a  lea     rdx, aUuspJson; "uusp.json"
0x180001f91  lea     rcx, ?_filenameBom@UusPackage@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const UusPackage::_filenameBom
0x180001f98  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180001f9d  lea     rcx, _dynamic_atexit_destructor_for__UusPackage___filenameBom__
0x180001fa4  add     rsp, 28h
0x180001fa8  jmp     atexit
```
