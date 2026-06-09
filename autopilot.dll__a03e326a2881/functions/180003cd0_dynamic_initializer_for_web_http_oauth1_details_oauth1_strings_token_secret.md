# _dynamic_initializer_for__web::http::oauth1::details::oauth1_strings::token_secret__

- ea: `0x180003cd0`
- end: `0x180003cf7`
- name: `_dynamic_initializer_for__web::http::oauth1::details::oauth1_strings::token_secret__`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800049c8`
- `0x1800146c8`

## string_xrefs

- `0x180003cd4`: `oauth_token_secret`

## pseudocode

```c
int dynamic_initializer_for__web::http::oauth1::details::oauth1_strings::token_secret__()
{
  std::wstring::wstring(&web::http::oauth1::details::oauth1_strings::token_secret, L"oauth_token_secret");
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__web::http::oauth1::details::oauth1_strings::token_secret__);
}

```

## disassembly

```asm
0x180003cd0  sub     rsp, 28h
0x180003cd4  lea     rdx, aOauthTokenSecr; "oauth_token_secret"
0x180003cdb  lea     rcx, ?token_secret@oauth1_strings@details@oauth1@http@web@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const web::http::oauth1::details::oauth1_strings::token_secret
0x180003ce2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180003ce7  lea     rcx, _dynamic_atexit_destructor_for__web__http__oauth1__details__oauth1_strings__token_secret__
0x180003cee  add     rsp, 28h
0x180003cf2  jmp     atexit
```
