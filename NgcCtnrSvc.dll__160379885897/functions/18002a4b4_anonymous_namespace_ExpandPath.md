# _anonymous_namespace_::ExpandPath

- ea: `0x18002a4b4`
- end: `0x18002a55f`
- name: `_anonymous_namespace_::ExpandPath`
- size: `171`
- prototype: `LPWSTR *__fastcall(LPWSTR *, const WCHAR *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002a0a0`

## callees

- `0x18002364c`
- `0x18002a4b4`
- `0x18004733c`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002a4dd`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002a524`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002a4dd`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002a524`

## string_xrefs

- `0x18002a4f4`: `onecore\ds\security\trustlet\utils\vtl0\lib\trustletcontrol.cpp`
- `0x18002a539`: `onecore\ds\security\trustlet\utils\vtl0\lib\trustletcontrol.cpp`

## pseudocode

```c
LPWSTR *__fastcall anonymous_namespace_::ExpandPath(LPWSTR *a1, const WCHAR *a2)
{
  DWORD v4; // eax
  const char *v5; // r9
  DWORD v6; // edi
  const char *v7; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v4 = ExpandEnvironmentStringsW(a2, 0, 0);
  v6 = v4;
  if ( !v4 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x114,
      (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl0\\lib\\trustletcontrol.cpp",
      v5);
  wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    a1,
    0,
    v4);
  if ( !ExpandEnvironmentStringsW(a2, *a1, v6) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x11C,
      (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl0\\lib\\trustletcontrol.cpp",
      v7);
  return a1;
}

```

## disassembly

```asm
0x18002a4b4  mov     rax, rsp
0x18002a4b7  mov     [rax+10h], rbx
0x18002a4bb  mov     [rax+18h], rsi
0x18002a4bf  mov     [rax+8], rcx
0x18002a4c3  push    rdi
0x18002a4c4  sub     rsp, 30h
0x18002a4c8  mov     rsi, rdx
0x18002a4cb  mov     rbx, rcx
0x18002a4ce  mov     dword ptr [rax-18h], 0
0x18002a4d5  xor     r8d, r8d; nSize
0x18002a4d8  xor     edx, edx; lpDst
0x18002a4da  mov     rcx, rsi; lpSrc
0x18002a4dd  call    cs:__imp_ExpandEnvironmentStringsW
0x18002a4e4  nop     dword ptr [rax+rax+00h]
0x18002a4e9  mov     edi, eax
0x18002a4eb  mov     rcx, [rsp+38h]; this
0x18002a4f0  test    eax, eax
0x18002a4f2  jnz     short loc_18002A506
0x18002a4f4  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\trustlet\\utils"...
0x18002a4fb  mov     edx, 114h; void *
0x18002a500  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18002a506  mov     r8, rdi
0x18002a509  xor     edx, edx
0x18002a50b  mov     rcx, rbx
0x18002a50e  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18002a513  mov     [rsp+38h+var_18], 3
0x18002a51b  mov     r8d, edi; nSize
0x18002a51e  mov     rdx, [rbx]; lpDst
0x18002a521  mov     rcx, rsi; lpSrc
0x18002a524  call    cs:__imp_ExpandEnvironmentStringsW
0x18002a52b  nop     dword ptr [rax+rax+00h]
0x18002a530  test    eax, eax
0x18002a532  jnz     short loc_18002A54B
0x18002a534  mov     rcx, [rsp+38h]; this
0x18002a539  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\trustlet\\utils"...
0x18002a540  mov     edx, 11Ch; void *
0x18002a545  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18002a54b  mov     rax, rbx
0x18002a54e  mov     rbx, [rsp+38h+arg_8]
0x18002a553  mov     rsi, [rsp+38h+arg_10]
0x18002a558  add     rsp, 30h
0x18002a55c  pop     rdi
0x18002a55d  retn
```
