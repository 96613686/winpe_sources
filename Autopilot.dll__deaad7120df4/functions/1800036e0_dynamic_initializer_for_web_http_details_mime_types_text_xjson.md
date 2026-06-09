# _dynamic_initializer_for__web::http::details::mime_types::text_xjson__

- ea: `0x1800036e0`
- end: `0x18000370d`
- name: `_dynamic_initializer_for__web::http::details::mime_types::text_xjson__`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800049e8`
- `0x180013de4`

## string_xrefs

- `0x1800036ea`: `text/x-json`

## pseudocode

```c
int dynamic_initializer_for__web::http::details::mime_types::text_xjson__()
{
  std::wstring::_Construct<1,unsigned short const *>(&web::http::details::mime_types::text_xjson, L"text/x-json", 0xBu);
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__web::http::details::mime_types::text_xjson__);
}

```

## disassembly

```asm
0x1800036e0  sub     rsp, 28h
0x1800036e4  mov     r8d, 0Bh
0x1800036ea  lea     rdx, aTextXJson; "text/x-json"
0x1800036f1  lea     rcx, ?text_xjson@mime_types@details@http@web@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const web::http::details::mime_types::text_xjson
0x1800036f8  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800036fd  lea     rcx, _dynamic_atexit_destructor_for__web__http__details__mime_types__text_xjson__
0x180003704  add     rsp, 28h
0x180003708  jmp     atexit
```
