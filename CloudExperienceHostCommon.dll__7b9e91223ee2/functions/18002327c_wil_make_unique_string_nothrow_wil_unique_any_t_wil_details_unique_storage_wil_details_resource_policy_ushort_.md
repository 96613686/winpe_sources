# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x18002327c`
- end: `0x18002334a`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `206`
- prototype: `_QWORD *__fastcall(_QWORD *, char *, unsigned __int64, const char *)`
- caller_count: `7`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180026848`
- `0x18005ffe4`
- `0x18007ba38`
- `0x18007ce38`
- `0x180083528`
- `0x18009f404`
- `0x1800a1540`

## callees

- `0x1800203fc`
- `0x18002327c`
- `0x180027a7c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800232fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800232fe`

## string_xrefs

- `0x1800232a7`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
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
0x18002327c  push    rbx
0x18002327e  push    rbp
0x18002327f  push    rsi
0x180023280  push    rdi
0x180023281  push    r12
0x180023283  push    r14
0x180023285  push    r15
0x180023287  sub     rsp, 20h
0x18002328b  xor     r12d, r12d
0x18002328e  mov     rdi, r8
0x180023291  mov     rbp, rdx
0x180023294  mov     r14, rcx
0x180023297  test    rdx, rdx
0x18002329a  jnz     short loc_1800232BE
0x18002329c  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x1800232a0  jnz     short loc_1800232B9
0x1800232a2  mov     rcx, [rsp+58h]; this
0x1800232a7  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800232ae  mov     edx, 0F89h; void *
0x1800232b3  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800232b9  mov     rbx, rdi
0x1800232bc  jmp     short loc_1800232F3
0x1800232be  mov     ecx, 7FFFFFFFh
0x1800232c3  mov     rax, rdi
0x1800232c6  cmp     rdi, rcx
0x1800232c9  mov     rbx, rbp
0x1800232cc  cmovnb  rax, rcx
0x1800232d0  test    rax, rax
0x1800232d3  jz      short loc_1800232E5
0x1800232d5  cmp     [rbx], r12w
0x1800232d9  jz      short loc_1800232E5
0x1800232db  add     rbx, 2
0x1800232df  sub     rax, 1
0x1800232e3  jnz     short loc_1800232D5
0x1800232e5  sub     rbx, rbp
0x1800232e8  sar     rbx, 1
0x1800232eb  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800232ef  cmovz   rdi, rbx
0x1800232f3  lea     r15, ds:2[rdi*2]
0x1800232fb  mov     rcx, r15; cb
0x1800232fe  call    cs:__imp_CoTaskMemAlloc
0x180023304  mov     rsi, rax
0x180023307  test    rax, rax
0x18002330a  jz      short loc_180023335
0x18002330c  test    rbp, rbp
0x18002330f  jz      short loc_18002332C
0x180023311  add     rbx, rbx
0x180023314  mov     r8, rbp; Source
0x180023317  mov     r9, rbx; SourceSize
0x18002331a  mov     rdx, r15; DestinationSize
0x18002331d  mov     rcx, rax; Destination
0x180023320  call    memcpy_s
0x180023325  mov     [rbx+rsi], r12w
0x18002332a  jmp     short loc_180023330
0x18002332c  mov     [rax], r12w
0x180023330  mov     [rsi+rdi*2], r12w
0x180023335  mov     [r14], rsi
0x180023338  mov     rax, r14
0x18002333b  add     rsp, 20h
0x18002333f  pop     r15
0x180023341  pop     r14
0x180023343  pop     r12
0x180023345  pop     rdi
0x180023346  pop     rsi
0x180023347  pop     rbp
0x180023348  pop     rbx
0x180023349  retn
```
