# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x18000b2fc`
- end: `0x18000b3cf`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180018cf0`

## callees

- `0x18000b2fc`
- `0x18001804c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000b38d`
- `msvcrt!memcpy_s` at `0x18000b38d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b36b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b36b`

## string_xrefs

- `0x18000b3bd`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
_QWORD *__fastcall wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        _QWORD *a1,
        char *a2,
        unsigned __int64 a3,
        const char *a4)
{
  unsigned __int64 v4; // rdi
  __int64 v7; // rbx
  __int64 v8; // rax
  char *v9; // rbx
  _WORD *v10; // rax
  _WORD *v11; // rsi
  rsize_t v12; // rbx
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v4 = a3;
  if ( a2 )
  {
    v8 = a3;
    v9 = a2;
    if ( a3 >= 0x7FFFFFFF )
      v8 = 0x7FFFFFFF;
    for ( ; v8; --v8 )
    {
      if ( !*(_WORD *)v9 )
        break;
      v9 += 2;
    }
    v7 = (v9 - a2) >> 1;
    if ( a3 == -1 )
      v4 = v7;
  }
  else
  {
    if ( a3 == -1 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xF89,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        a4);
    v7 = a3;
  }
  v10 = CoTaskMemAlloc(2 * v4 + 2);
  v11 = v10;
  if ( v10 )
  {
    if ( a2 )
    {
      v12 = v7;
      memcpy_s(v10, 2 * v4 + 2, a2, v12 * 2);
      v11[v12] = 0;
    }
    else
    {
      *v10 = 0;
    }
    v11[v4] = 0;
  }
  *a1 = v11;
  return a1;
}

```

## disassembly

```asm
0x18000b2fc  push    rbx
0x18000b2fe  push    rbp
0x18000b2ff  push    rsi
0x18000b300  push    rdi
0x18000b301  push    r12
0x18000b303  push    r14
0x18000b305  push    r15
0x18000b307  sub     rsp, 20h
0x18000b30b  xor     r12d, r12d
0x18000b30e  mov     rdi, r8
0x18000b311  mov     rbp, rdx
0x18000b314  mov     r14, rcx
0x18000b317  test    rdx, rdx
0x18000b31a  jnz     short loc_18000B32B
0x18000b31c  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18000b320  jz      loc_18000B3B8
0x18000b326  mov     rbx, r8
0x18000b329  jmp     short loc_18000B360
0x18000b32b  mov     ecx, 7FFFFFFFh
0x18000b330  mov     rax, rdi
0x18000b333  cmp     rdi, rcx
0x18000b336  mov     rbx, rbp
0x18000b339  cmovnb  rax, rcx
0x18000b33d  test    rax, rax
0x18000b340  jz      short loc_18000B352
0x18000b342  cmp     [rbx], r12w
0x18000b346  jz      short loc_18000B352
0x18000b348  add     rbx, 2
0x18000b34c  sub     rax, 1
0x18000b350  jnz     short loc_18000B342
0x18000b352  sub     rbx, rbp
0x18000b355  sar     rbx, 1
0x18000b358  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18000b35c  cmovz   rdi, rbx
0x18000b360  lea     r15, ds:2[rdi*2]
0x18000b368  mov     rcx, r15; cb
0x18000b36b  call    cs:__imp_CoTaskMemAlloc
0x18000b371  mov     rsi, rax
0x18000b374  test    rax, rax
0x18000b377  jz      short loc_18000B3A3
0x18000b379  test    rbp, rbp
0x18000b37c  jz      short loc_18000B39A
0x18000b37e  add     rbx, rbx
0x18000b381  mov     r8, rbp; Source
0x18000b384  mov     r9, rbx; SourceSize
0x18000b387  mov     rdx, r15; DestinationSize
0x18000b38a  mov     rcx, rax; Destination
0x18000b38d  call    cs:__imp_memcpy_s
0x18000b393  mov     [rbx+rsi], r12w
0x18000b398  jmp     short loc_18000B39E
0x18000b39a  mov     [rax], r12w
0x18000b39e  mov     [rsi+rdi*2], r12w
0x18000b3a3  mov     [r14], rsi
0x18000b3a6  mov     rax, r14
0x18000b3a9  add     rsp, 20h
0x18000b3ad  pop     r15
0x18000b3af  pop     r14
0x18000b3b1  pop     r12
0x18000b3b3  pop     rdi
0x18000b3b4  pop     rsi
0x18000b3b5  pop     rbp
0x18000b3b6  pop     rbx
0x18000b3b7  retn
0x18000b3b8  mov     rcx, [rsp+58h]; this
0x18000b3bd  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000b3c4  mov     edx, 0F89h; void *
0x18000b3c9  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
