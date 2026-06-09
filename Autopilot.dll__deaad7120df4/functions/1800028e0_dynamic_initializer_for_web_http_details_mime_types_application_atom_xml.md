# _dynamic_initializer_for__web::http::details::mime_types::application_atom_xml__

- ea: `0x1800028e0`
- end: `0x18000290d`
- name: `_dynamic_initializer_for__web::http::details::mime_types::application_atom_xml__`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800049e8`
- `0x180013de4`

## string_xrefs

- `0x1800028ea`: `application/atom+xml`

## pseudocode

```c
int dynamic_initializer_for__web::http::details::mime_types::application_atom_xml__()
{
  std::wstring::_Construct<1,unsigned short const *>(
    &web::http::details::mime_types::application_atom_xml,
    L"application/atom+xml",
    0x14u);
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__web::http::details::mime_types::application_atom_xml__);
}

```

## disassembly

```asm
0x1800028e0  sub     rsp, 28h
0x1800028e4  mov     r8d, 14h
0x1800028ea  lea     rdx, aApplicationAto; "application/atom+xml"
0x1800028f1  lea     rcx, ?application_atom_xml@mime_types@details@http@web@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const web::http::details::mime_types::application_atom_xml
0x1800028f8  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800028fd  lea     rcx, _dynamic_atexit_destructor_for__web__http__details__mime_types__application_atom_xml__
0x180002904  add     rsp, 28h
0x180002908  jmp     atexit
```
