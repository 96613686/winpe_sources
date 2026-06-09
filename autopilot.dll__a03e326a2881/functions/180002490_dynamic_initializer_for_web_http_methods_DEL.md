# _dynamic_initializer_for__web::http::methods::DEL__

- ea: `0x180002490`
- end: `0x1800024bd`
- name: `_dynamic_initializer_for__web::http::methods::DEL__`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800049c8`
- `0x180013a40`

## string_xrefs

- `0x18000249a`: `DELETE`

## pseudocode

```c
int dynamic_initializer_for__web::http::methods::DEL__()
{
  std::wstring::_Construct<1,unsigned short const *>(&web::http::methods::DEL, L"DELETE", 6);
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__web::http::methods::DEL__);
}

```

## disassembly

```asm
0x180002490  sub     rsp, 28h
0x180002494  mov     r8d, 6
0x18000249a  lea     rdx, aDelete; "DELETE"
0x1800024a1  lea     rcx, ?DEL@methods@http@web@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const web::http::methods::DEL
0x1800024a8  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800024ad  lea     rcx, _dynamic_atexit_destructor_for__web__http__methods__DEL__
0x1800024b4  add     rsp, 28h
0x1800024b8  jmp     atexit
```
