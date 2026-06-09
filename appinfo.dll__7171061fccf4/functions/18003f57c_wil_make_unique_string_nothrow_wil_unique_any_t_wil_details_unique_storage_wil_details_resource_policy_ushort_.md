# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x18003f57c`
- end: `0x18003f64f`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `211`
- prototype: `_QWORD *__fastcall(_QWORD *, char *, unsigned __int64, const char *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180040804`

## callees

- `0x180021fa4`
- `0x18003f57c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18003f60d`
- `msvcrt!memcpy_s` at `0x18003f60d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003f5eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003f5eb`

## string_xrefs

- `0x18003f63d`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x18003f57c  push    rbx
0x18003f57e  push    rbp
0x18003f57f  push    rsi
0x18003f580  push    rdi
0x18003f581  push    r12
0x18003f583  push    r14
0x18003f585  push    r15
0x18003f587  sub     rsp, 20h
0x18003f58b  xor     r12d, r12d
0x18003f58e  mov     rdi, r8
0x18003f591  mov     rbp, rdx
0x18003f594  mov     r14, rcx
0x18003f597  test    rdx, rdx
0x18003f59a  jnz     short loc_18003F5AB
0x18003f59c  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18003f5a0  jz      loc_18003F638
0x18003f5a6  mov     rbx, r8
0x18003f5a9  jmp     short loc_18003F5E0
0x18003f5ab  mov     ecx, 7FFFFFFFh
0x18003f5b0  mov     rax, rdi
0x18003f5b3  cmp     rdi, rcx
0x18003f5b6  mov     rbx, rbp
0x18003f5b9  cmovnb  rax, rcx
0x18003f5bd  test    rax, rax
0x18003f5c0  jz      short loc_18003F5D2
0x18003f5c2  cmp     [rbx], r12w
0x18003f5c6  jz      short loc_18003F5D2
0x18003f5c8  add     rbx, 2
0x18003f5cc  sub     rax, 1
0x18003f5d0  jnz     short loc_18003F5C2
0x18003f5d2  sub     rbx, rbp
0x18003f5d5  sar     rbx, 1
0x18003f5d8  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18003f5dc  cmovz   rdi, rbx
0x18003f5e0  lea     r15, ds:2[rdi*2]
0x18003f5e8  mov     rcx, r15; cb
0x18003f5eb  call    cs:__imp_CoTaskMemAlloc
0x18003f5f1  mov     rsi, rax
0x18003f5f4  test    rax, rax
0x18003f5f7  jz      short loc_18003F623
0x18003f5f9  test    rbp, rbp
0x18003f5fc  jz      short loc_18003F61A
0x18003f5fe  add     rbx, rbx
0x18003f601  mov     r8, rbp; Source
0x18003f604  mov     r9, rbx; SourceSize
0x18003f607  mov     rdx, r15; DestinationSize
0x18003f60a  mov     rcx, rax; Destination
0x18003f60d  call    cs:__imp_memcpy_s
0x18003f613  mov     [rbx+rsi], r12w
0x18003f618  jmp     short loc_18003F61E
0x18003f61a  mov     [rax], r12w
0x18003f61e  mov     [rsi+rdi*2], r12w
0x18003f623  mov     [r14], rsi
0x18003f626  mov     rax, r14
0x18003f629  add     rsp, 20h
0x18003f62d  pop     r15
0x18003f62f  pop     r14
0x18003f631  pop     r12
0x18003f633  pop     rdi
0x18003f634  pop     rsi
0x18003f635  pop     rbp
0x18003f636  pop     rbx
0x18003f637  retn
0x18003f638  mov     rcx, [rsp+58h]; this
0x18003f63d  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003f644  mov     edx, 0F89h; void *
0x18003f649  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
