# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x18003b65c`
- end: `0x18003b6b6`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `90`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64, __int64, const char *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004fcac`

## callees

- `0x180013828`
- `0x18003b65c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003b67a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003b67a`

## string_xrefs

- `0x18003b6a4`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
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
0x18003b65c  mov     [rsp+arg_0], rbx
0x18003b661  push    rdi
0x18003b662  sub     rsp, 20h
0x18003b666  mov     rdi, r8
0x18003b669  mov     rbx, rcx
0x18003b66c  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18003b670  jz      short loc_18003B69F
0x18003b672  lea     rcx, ds:2[r8*2]; cb
0x18003b67a  call    cs:__imp_CoTaskMemAlloc
0x18003b680  test    rax, rax
0x18003b683  jz      short loc_18003B68E
0x18003b685  xor     ecx, ecx
0x18003b687  mov     [rax], cx
0x18003b68a  mov     [rax+rdi*2], cx
0x18003b68e  mov     [rbx], rax
0x18003b691  mov     rax, rbx
0x18003b694  mov     rbx, [rsp+28h+arg_0]
0x18003b699  add     rsp, 20h
0x18003b69d  pop     rdi
0x18003b69e  retn
0x18003b69f  mov     rcx, [rsp+28h]; this
0x18003b6a4  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003b6ab  mov     edx, 0F89h; void *
0x18003b6b0  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
