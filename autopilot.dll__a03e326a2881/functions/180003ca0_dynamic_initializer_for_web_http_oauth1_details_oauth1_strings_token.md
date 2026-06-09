# _dynamic_initializer_for__web::http::oauth1::details::oauth1_strings::token__

- ea: `0x180003ca0`
- end: `0x180003cc7`
- name: `_dynamic_initializer_for__web::http::oauth1::details::oauth1_strings::token__`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800049c8`
- `0x1800146c8`

## string_xrefs

- `0x180003ca4`: `oauth_token`

## pseudocode

```c
int dynamic_initializer_for__web::http::oauth1::details::oauth1_strings::token__()
{
  std::wstring::wstring(&web::http::oauth1::details::oauth1_strings::token, L"oauth_token");
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__web::http::oauth1::details::oauth1_strings::token__);
}

```

## disassembly

```asm
0x180003ca0  sub     rsp, 28h
0x180003ca4  lea     rdx, aOauthToken; "oauth_token"
0x180003cab  lea     rcx, ?token@oauth1_strings@details@oauth1@http@web@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const web::http::oauth1::details::oauth1_strings::token
0x180003cb2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180003cb7  lea     rcx, _dynamic_atexit_destructor_for__web__http__oauth1__details__oauth1_strings__token__
0x180003cbe  add     rsp, 28h
0x180003cc2  jmp     atexit
```
