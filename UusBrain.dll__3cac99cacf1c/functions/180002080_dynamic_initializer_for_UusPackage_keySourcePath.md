# _dynamic_initializer_for__UusPackage::_keySourcePath__

- ea: `0x180002080`
- end: `0x1800020ad`
- name: `_dynamic_initializer_for__UusPackage::_keySourcePath__`
- size: `45`
- prototype: `int()`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180029518`
- `0x180042ba4`

## string_xrefs

- `0x18000208a`: `sourcePath`

## pseudocode

```c
int dynamic_initializer_for__UusPackage::_keySourcePath__()
{
  std::wstring::_Construct<1,wchar_t const *>(UusPackage::_keySourcePath);
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__UusPackage::_keySourcePath__);
}

```

## disassembly

```asm
0x180002080  sub     rsp, 28h
0x180002084  mov     r8d, 0Ah
0x18000208a  lea     rdx, aSourcepath; "sourcePath"
0x180002091  lea     rcx, ?_keySourcePath@UusPackage@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const UusPackage::_keySourcePath
0x180002098  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18000209d  lea     rcx, _dynamic_atexit_destructor_for__UusPackage___keySourcePath__
0x1800020a4  add     rsp, 28h
0x1800020a8  jmp     atexit
```
