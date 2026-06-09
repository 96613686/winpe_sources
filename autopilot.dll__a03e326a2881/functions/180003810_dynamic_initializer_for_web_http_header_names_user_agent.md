# _dynamic_initializer_for__web::http::header_names::user_agent__

- ea: `0x180003810`
- end: `0x18000383d`
- name: `_dynamic_initializer_for__web::http::header_names::user_agent__`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800049c8`
- `0x180013a40`

## string_xrefs

- `0x18000381a`: `User-Agent`

## pseudocode

```c
int dynamic_initializer_for__web::http::header_names::user_agent__()
{
  std::wstring::_Construct<1,unsigned short const *>(&web::http::header_names::user_agent, L"User-Agent", 10);
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__web::http::header_names::user_agent__);
}

```

## disassembly

```asm
0x180003810  sub     rsp, 28h
0x180003814  mov     r8d, 0Ah
0x18000381a  lea     rdx, aUserAgent; "User-Agent"
0x180003821  lea     rcx, ?user_agent@header_names@http@web@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const web::http::header_names::user_agent
0x180003828  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000382d  lea     rcx, _dynamic_atexit_destructor_for__web__http__header_names__user_agent__
0x180003834  add     rsp, 28h
0x180003838  jmp     atexit
```
