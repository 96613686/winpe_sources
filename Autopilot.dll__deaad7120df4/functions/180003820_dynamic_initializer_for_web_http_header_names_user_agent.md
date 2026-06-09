# _dynamic_initializer_for__web::http::header_names::user_agent__

- ea: `0x180003820`
- end: `0x18000384d`
- name: `_dynamic_initializer_for__web::http::header_names::user_agent__`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800049e8`
- `0x180013de4`

## string_xrefs

- `0x18000382a`: `User-Agent`

## pseudocode

```c
int dynamic_initializer_for__web::http::header_names::user_agent__()
{
  std::wstring::_Construct<1,unsigned short const *>(&web::http::header_names::user_agent, L"User-Agent", 0xAu);
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__web::http::header_names::user_agent__);
}

```

## disassembly

```asm
0x180003820  sub     rsp, 28h
0x180003824  mov     r8d, 0Ah
0x18000382a  lea     rdx, aUserAgent; "User-Agent"
0x180003831  lea     rcx, ?user_agent@header_names@http@web@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const web::http::header_names::user_agent
0x180003838  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000383d  lea     rcx, _dynamic_atexit_destructor_for__web__http__header_names__user_agent__
0x180003844  add     rsp, 28h
0x180003848  jmp     atexit
```
