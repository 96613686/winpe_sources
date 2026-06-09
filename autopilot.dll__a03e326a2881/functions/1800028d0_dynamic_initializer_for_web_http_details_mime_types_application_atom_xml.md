# _dynamic_initializer_for__web::http::details::mime_types::application_atom_xml__

- ea: `0x1800028d0`
- end: `0x1800028fd`
- name: `_dynamic_initializer_for__web::http::details::mime_types::application_atom_xml__`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800049c8`
- `0x180013a40`

## string_xrefs

- `0x1800028da`: `application/atom+xml`

## pseudocode

```c
int dynamic_initializer_for__web::http::details::mime_types::application_atom_xml__()
{
  std::wstring::_Construct<1,unsigned short const *>(
    &web::http::details::mime_types::application_atom_xml,
    L"application/atom+xml",
    20);
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__web::http::details::mime_types::application_atom_xml__);
}

```

## disassembly

```asm
0x1800028d0  sub     rsp, 28h
0x1800028d4  mov     r8d, 14h
0x1800028da  lea     rdx, aApplicationAto; "application/atom+xml"
0x1800028e1  lea     rcx, ?application_atom_xml@mime_types@details@http@web@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const web::http::details::mime_types::application_atom_xml
0x1800028e8  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800028ed  lea     rcx, _dynamic_atexit_destructor_for__web__http__details__mime_types__application_atom_xml__
0x1800028f4  add     rsp, 28h
0x1800028f8  jmp     atexit
```
