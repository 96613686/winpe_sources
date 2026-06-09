# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x180028a04`
- end: `0x180028a5e`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `90`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64, __int64, const char *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180030224`

## callees

- `0x180018bac`
- `0x180028a04`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180028a39`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180028a39`

## string_xrefs

- `0x180028a1f`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  _WORD *v6; // rax
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( a3 == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xF89,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      a4);
  v6 = CoTaskMemAlloc(2 * a3 + 2);
  if ( v6 )
  {
    *v6 = 0;
    v6[a3] = 0;
  }
  *a1 = v6;
  return a1;
}

```

## disassembly

```asm
0x180028a04  mov     [rsp+arg_0], rbx
0x180028a09  push    rdi
0x180028a0a  sub     rsp, 20h
0x180028a0e  mov     rdi, r8
0x180028a11  mov     rbx, rcx
0x180028a14  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x180028a18  jnz     short loc_180028A31
0x180028a1a  mov     rcx, [rsp+28h]; this
0x180028a1f  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180028a26  mov     edx, 0F89h; void *
0x180028a2b  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180028a31  lea     rcx, ds:2[r8*2]; cb
0x180028a39  call    cs:__imp_CoTaskMemAlloc
0x180028a3f  test    rax, rax
0x180028a42  jz      short loc_180028A4D
0x180028a44  xor     ecx, ecx
0x180028a46  mov     [rax], cx
0x180028a49  mov     [rax+rdi*2], cx
0x180028a4d  mov     [rbx], rax
0x180028a50  mov     rax, rbx
0x180028a53  mov     rbx, [rsp+28h+arg_0]
0x180028a58  add     rsp, 20h
0x180028a5c  pop     rdi
0x180028a5d  retn
```
