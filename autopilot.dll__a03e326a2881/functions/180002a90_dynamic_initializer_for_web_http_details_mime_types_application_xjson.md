# _dynamic_initializer_for__web::http::details::mime_types::application_xjson__

- ea: `0x180002a90`
- end: `0x180002abd`
- name: `_dynamic_initializer_for__web::http::details::mime_types::application_xjson__`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800049c8`
- `0x180013a40`

## string_xrefs

- `0x180002a9a`: `application/x-json`

## pseudocode

```c
int dynamic_initializer_for__web::http::details::mime_types::application_xjson__()
{
  std::wstring::_Construct<1,unsigned short const *>(
    &web::http::details::mime_types::application_xjson,
    L"application/x-json",
    18);
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__web::http::details::mime_types::application_xjson__);
}

```

## disassembly

```asm
0x180002a90  sub     rsp, 28h
0x180002a94  mov     r8d, 12h
0x180002a9a  lea     rdx, aApplicationXJs; "application/x-json"
0x180002aa1  lea     rcx, ?application_xjson@mime_types@details@http@web@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const web::http::details::mime_types::application_xjson
0x180002aa8  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180002aad  lea     rcx, _dynamic_atexit_destructor_for__web__http__details__mime_types__application_xjson__
0x180002ab4  add     rsp, 28h
0x180002ab8  jmp     atexit
```
