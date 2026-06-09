# _dynamic_initializer_for__UpdateApiPath__

- ea: `0x180002250`
- end: `0x180002277`
- name: `_dynamic_initializer_for__UpdateApiPath__`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180003284`
- `0x1800191a8`

## string_xrefs

- `0x180002254`: `Software\Microsoft\Windows\UpdateApi`

## pseudocode

```c
int dynamic_initializer_for__UpdateApiPath__()
{
  std::wstring::wstring(qword_180042AD0, L"Software\\Microsoft\\Windows\\UpdateApi");
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__UpdateApiPath__);
}

```

## disassembly

```asm
0x180002250  sub     rsp, 28h
0x180002254  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows\\UpdateApi"
0x18000225b  lea     rcx, qword_180042AD0
0x180002262  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180002267  lea     rcx, _dynamic_atexit_destructor_for__UpdateApiPath__
0x18000226e  add     rsp, 28h
0x180002272  jmp     atexit
```
