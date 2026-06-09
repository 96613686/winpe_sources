# _dynamic_initializer_for__web::http::header_names::access_control_allow_origin__

- ea: `0x180002820`
- end: `0x18000284d`
- name: `_dynamic_initializer_for__web::http::header_names::access_control_allow_origin__`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800049e8`
- `0x180013de4`

## string_xrefs

- `0x18000282a`: `Access-Control-Allow-Origin`

## pseudocode

```c
int dynamic_initializer_for__web::http::header_names::access_control_allow_origin__()
{
  std::wstring::_Construct<1,unsigned short const *>(
    &web::http::header_names::access_control_allow_origin,
    L"Access-Control-Allow-Origin",
    0x1Bu);
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__web::http::header_names::access_control_allow_origin__);
}

```

## disassembly

```asm
0x180002820  sub     rsp, 28h
0x180002824  mov     r8d, 1Bh
0x18000282a  lea     rdx, aAccessControlA; "Access-Control-Allow-Origin"
0x180002831  lea     rcx, ?access_control_allow_origin@header_names@http@web@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const web::http::header_names::access_control_allow_origin
0x180002838  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000283d  lea     rcx, _dynamic_atexit_destructor_for__web__http__header_names__access_control_allow_origin__
0x180002844  add     rsp, 28h
0x180002848  jmp     atexit
```
