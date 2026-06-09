# _dynamic_initializer_for__web::http::details::mime_types::text_json__

- ea: `0x180003550`
- end: `0x18000357d`
- name: `_dynamic_initializer_for__web::http::details::mime_types::text_json__`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800049c8`
- `0x180013a40`

## string_xrefs

- `0x18000355a`: `text/json`

## pseudocode

```c
int dynamic_initializer_for__web::http::details::mime_types::text_json__()
{
  std::wstring::_Construct<1,unsigned short const *>(&web::http::details::mime_types::text_json, L"text/json", 9);
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__web::http::details::mime_types::text_json__);
}

```

## disassembly

```asm
0x180003550  sub     rsp, 28h
0x180003554  mov     r8d, 9
0x18000355a  lea     rdx, aTextJson; "text/json"
0x180003561  lea     rcx, ?text_json@mime_types@details@http@web@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const web::http::details::mime_types::text_json
0x180003568  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000356d  lea     rcx, _dynamic_atexit_destructor_for__web__http__details__mime_types__text_json__
0x180003574  add     rsp, 28h
0x180003578  jmp     atexit
```
