# _dynamic_initializer_for__UusPackage::_keyTargetPath__

- ea: `0x1800020c0`
- end: `0x1800020ed`
- name: `_dynamic_initializer_for__UusPackage::_keyTargetPath__`
- size: `45`
- prototype: `int()`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180029518`
- `0x180042ba4`

## string_xrefs

- `0x1800020ca`: `targetPath`

## pseudocode

```c
int dynamic_initializer_for__UusPackage::_keyTargetPath__()
{
  std::wstring::_Construct<1,wchar_t const *>(UusPackage::_keyTargetPath);
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__UusPackage::_keyTargetPath__);
}

```

## disassembly

```asm
0x1800020c0  sub     rsp, 28h
0x1800020c4  mov     r8d, 0Ah
0x1800020ca  lea     rdx, aTargetpath; "targetPath"
0x1800020d1  lea     rcx, ?_keyTargetPath@UusPackage@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const UusPackage::_keyTargetPath
0x1800020d8  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800020dd  lea     rcx, _dynamic_atexit_destructor_for__UusPackage___keyTargetPath__
0x1800020e4  add     rsp, 28h
0x1800020e8  jmp     atexit
```
