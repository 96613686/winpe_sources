# _dynamic_initializer_for__web::http::details::mime_types::application_json__

- ea: `0x1800029a0`
- end: `0x1800029cd`
- name: `_dynamic_initializer_for__web::http::details::mime_types::application_json__`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800049e8`
- `0x180013de4`

## string_xrefs

- `0x1800029aa`: `application/json`

## pseudocode

```c
int dynamic_initializer_for__web::http::details::mime_types::application_json__()
{
  std::wstring::_Construct<1,unsigned short const *>(
    &web::http::details::mime_types::application_json,
    L"application/json",
    0x10u);
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__web::http::details::mime_types::application_json__);
}

```

## disassembly

```asm
0x1800029a0  sub     rsp, 28h
0x1800029a4  mov     r8d, 10h
0x1800029aa  lea     rdx, aApplicationJso; "application/json"
0x1800029b1  lea     rcx, ?application_json@mime_types@details@http@web@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const web::http::details::mime_types::application_json
0x1800029b8  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800029bd  lea     rcx, _dynamic_atexit_destructor_for__web__http__details__mime_types__application_json__
0x1800029c4  add     rsp, 28h
0x1800029c8  jmp     atexit
```
