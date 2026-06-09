# _dynamic_initializer_for__UusPackage::_subdirSxSRoot__

- ea: `0x180001f40`
- end: `0x180001f6d`
- name: `_dynamic_initializer_for__UusPackage::_subdirSxSRoot__`
- size: `45`
- prototype: `int()`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180029518`
- `0x180042ba4`

## string_xrefs

- `0x180001f4a`: `%ProgramData%\Microsoft\Windows\UUS\Packages`

## pseudocode

```c
int dynamic_initializer_for__UusPackage::_subdirSxSRoot__()
{
  std::wstring::_Construct<1,wchar_t const *>(&UusPackage::_subdirSxSRoot);
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__UusPackage::_subdirSxSRoot__);
}

```

## disassembly

```asm
0x180001f40  sub     rsp, 28h
0x180001f44  mov     r8d, 2Ch ; ','
0x180001f4a  lea     rdx, aProgramdataMic; "%ProgramData%\\Microsoft\\Windows\\UUS"...
0x180001f51  lea     rcx, ?_subdirSxSRoot@UusPackage@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const UusPackage::_subdirSxSRoot
0x180001f58  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180001f5d  lea     rcx, _dynamic_atexit_destructor_for__UusPackage___subdirSxSRoot__
0x180001f64  add     rsp, 28h
0x180001f68  jmp     atexit
```
