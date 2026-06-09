# _dynamic_initializer_for__web::http::details::mime_types::application_xml__

- ea: `0x180002ad0`
- end: `0x180002afd`
- name: `_dynamic_initializer_for__web::http::details::mime_types::application_xml__`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800049c8`
- `0x180013a40`

## string_xrefs

- `0x180002ada`: `application/xml`

## pseudocode

```c
int dynamic_initializer_for__web::http::details::mime_types::application_xml__()
{
  std::wstring::_Construct<1,unsigned short const *>(
    &web::http::details::mime_types::application_xml,
    L"application/xml",
    15);
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__web::http::details::mime_types::application_xml__);
}

```

## disassembly

```asm
0x180002ad0  sub     rsp, 28h
0x180002ad4  mov     r8d, 0Fh
0x180002ada  lea     rdx, aApplicationXml; "application/xml"
0x180002ae1  lea     rcx, ?application_xml@mime_types@details@http@web@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const web::http::details::mime_types::application_xml
0x180002ae8  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180002aed  lea     rcx, _dynamic_atexit_destructor_for__web__http__details__mime_types__application_xml__
0x180002af4  add     rsp, 28h
0x180002af8  jmp     atexit
```
