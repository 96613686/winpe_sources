# wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x18003834c`
- end: `0x1800383bb`
- name: `??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `111`
- prototype: `HSTRING *__fastcall(HSTRING *string, PCNZWCH sourceString)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180074b20`

## callees

- `0x18003834c`
- `0x1800383c4`
- `0x18005517c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180038384`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180038384`

## string_xrefs

- `0x18003839c`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
HSTRING *__fastcall wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(
        HSTRING *string,
        PCNZWCH sourceString)
{
  __int64 v4; // rdi
  const char *v5; // r9
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v4 = -1;
  do
    ++v4;
  while ( sourceString[v4] );
  *string = 0;
  wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
    string,
    0);
  WindowsCreateString(sourceString, v4, string);
  if ( !*string )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0xFF8,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v5);
  return string;
}

```

## disassembly

```asm
0x18003834c  mov     [rsp+arg_0], rcx
0x180038351  push    rbx
0x180038352  push    rbp
0x180038353  push    rsi
0x180038354  push    rdi
0x180038355  sub     rsp, 38h
0x180038359  mov     rsi, rdx
0x18003835c  mov     rbx, rcx
0x18003835f  xor     ebp, ebp
0x180038361  mov     [rsp+58h+var_38], ebp
0x180038365  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180038369  inc     rdi
0x18003836c  cmp     [rdx+rdi*2], bp
0x180038370  jnz     short loc_180038369
0x180038372  mov     [rcx], rbp
0x180038375  xor     edx, edx
0x180038377  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x18003837c  mov     edx, edi; length
0x18003837e  mov     r8, rbx; string
0x180038381  mov     rcx, rsi; sourceString
0x180038384  call    cs:__imp_WindowsCreateString
0x18003838a  mov     [rsp+58h+var_38], 1
0x180038392  mov     rcx, [rsp+58h]; this
0x180038397  cmp     [rbx], rbp
0x18003839a  jnz     short loc_1800383AE
0x18003839c  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800383a3  mov     edx, 0FF8h; void *
0x1800383a8  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x1800383ae  mov     rax, rbx
0x1800383b1  add     rsp, 38h
0x1800383b5  pop     rdi
0x1800383b6  pop     rsi
0x1800383b7  pop     rbp
0x1800383b8  pop     rbx
0x1800383b9  retn
```
