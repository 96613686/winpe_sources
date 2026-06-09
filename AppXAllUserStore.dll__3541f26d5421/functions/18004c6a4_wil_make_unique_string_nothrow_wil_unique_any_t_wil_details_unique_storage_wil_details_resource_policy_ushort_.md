# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x18004c6a4`
- end: `0x18004c735`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `145`
- prototype: `_QWORD *__fastcall(_QWORD *, char *, __int64, const char *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004c73c`

## callees

- `0x180023ed8`
- `0x18004c6a4`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18004c700`
- `msvcrt!memcpy_s` at `0x18004c700`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004c6e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004c6e5`

## string_xrefs

- `0x18004c723`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
_QWORD *__fastcall wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        _QWORD *a1,
        char *a2,
        __int64 a3,
        const char *a4)
{
  __int64 v6; // rcx
  char *v7; // rax
  rsize_t v8; // r14
  char *v9; // rax
  char *v10; // rdi
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  if ( !a2 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xF89,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      a4);
  v6 = 0x7FFFFFFF;
  v7 = a2;
  do
  {
    if ( !*(_WORD *)v7 )
      break;
    v7 += 2;
    --v6;
  }
  while ( v6 );
  v8 = 2 * ((v7 - a2) >> 1);
  v9 = (char *)CoTaskMemAlloc(v8 + 2);
  v10 = v9;
  if ( v9 )
  {
    memcpy_s(v9, v8 + 2, a2, v8);
    *(_WORD *)&v10[v8] = 0;
  }
  *a1 = v10;
  return a1;
}

```

## disassembly

```asm
0x18004c6a4  push    rbx
0x18004c6a6  push    rbp
0x18004c6a7  push    rsi
0x18004c6a8  push    rdi
0x18004c6a9  push    r14
0x18004c6ab  push    r15
0x18004c6ad  sub     rsp, 28h
0x18004c6b1  xor     r15d, r15d
0x18004c6b4  mov     rbx, rdx
0x18004c6b7  mov     rsi, rcx
0x18004c6ba  test    rdx, rdx
0x18004c6bd  jz      short loc_18004C71E
0x18004c6bf  mov     ecx, 7FFFFFFFh
0x18004c6c4  mov     rax, rdx
0x18004c6c7  cmp     [rax], r15w
0x18004c6cb  jz      short loc_18004C6D7
0x18004c6cd  add     rax, 2
0x18004c6d1  sub     rcx, 1
0x18004c6d5  jnz     short loc_18004C6C7
0x18004c6d7  sub     rax, rbx
0x18004c6da  sar     rax, 1
0x18004c6dd  lea     r14, [rax+rax]
0x18004c6e1  lea     rcx, [r14+2]; cb
0x18004c6e5  call    cs:__imp_CoTaskMemAlloc
0x18004c6eb  mov     rdi, rax
0x18004c6ee  test    rax, rax
0x18004c6f1  jz      short loc_18004C70B
0x18004c6f3  mov     r9, r14; SourceSize
0x18004c6f6  lea     rdx, [r14+2]; DestinationSize
0x18004c6fa  mov     r8, rbx; Source
0x18004c6fd  mov     rcx, rax; Destination
0x18004c700  call    cs:__imp_memcpy_s
0x18004c706  mov     [r14+rdi], r15w
0x18004c70b  mov     [rsi], rdi
0x18004c70e  mov     rax, rsi
0x18004c711  add     rsp, 28h
0x18004c715  pop     r15
0x18004c717  pop     r14
0x18004c719  pop     rdi
0x18004c71a  pop     rsi
0x18004c71b  pop     rbp
0x18004c71c  pop     rbx
0x18004c71d  retn
0x18004c71e  mov     rcx, [rsp+58h]; this
0x18004c723  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18004c72a  mov     edx, 0F89h; void *
0x18004c72f  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
