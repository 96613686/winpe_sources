# _dynamic_initializer_for__web::http::header_names::cache_control__

- ea: `0x180002be0`
- end: `0x180002c0d`
- name: `_dynamic_initializer_for__web::http::header_names::cache_control__`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800049e8`
- `0x180013de4`

## string_xrefs

- `0x180002bea`: `Cache-Control`

## pseudocode

```c
int dynamic_initializer_for__web::http::header_names::cache_control__()
{
  std::wstring::_Construct<1,unsigned short const *>(&web::http::header_names::cache_control, L"Cache-Control", 0xDu);
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__web::http::header_names::cache_control__);
}

```

## disassembly

```asm
0x180002be0  sub     rsp, 28h
0x180002be4  mov     r8d, 0Dh
0x180002bea  lea     rdx, aCacheControl; "Cache-Control"
0x180002bf1  lea     rcx, ?cache_control@header_names@http@web@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const web::http::header_names::cache_control
0x180002bf8  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180002bfd  lea     rcx, _dynamic_atexit_destructor_for__web__http__header_names__cache_control__
0x180002c04  add     rsp, 28h
0x180002c08  jmp     atexit
```
