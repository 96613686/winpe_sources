# _dynamic_initializer_for__sc_strProvToolPath__

- ea: `0x1800020a0`
- end: `0x1800020c7`
- name: `_dynamic_initializer_for__sc_strProvToolPath__`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000299c`
- `0x18000f534`

## string_xrefs

- `0x1800020a4`: `%WINDIR%\system32\provtool.exe`

## pseudocode

```c
int dynamic_initializer_for__sc_strProvToolPath__()
{
  std::wstring::wstring(&lpSrc, L"%WINDIR%\\system32\\provtool.exe");
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__sc_strProvToolPath__);
}

```

## disassembly

```asm
0x1800020a0  sub     rsp, 28h
0x1800020a4  lea     rdx, aWindirSystem32; "%WINDIR%\\system32\\provtool.exe"
0x1800020ab  lea     rcx, lpSrc
0x1800020b2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1800020b7  lea     rcx, _dynamic_atexit_destructor_for__sc_strProvToolPath__
0x1800020be  add     rsp, 28h
0x1800020c2  jmp     atexit
```
