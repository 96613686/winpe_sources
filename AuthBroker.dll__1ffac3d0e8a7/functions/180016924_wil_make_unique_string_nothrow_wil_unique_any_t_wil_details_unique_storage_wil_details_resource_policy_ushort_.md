# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x180016924`
- end: `0x1800169f5`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `209`
- prototype: `wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (__cdecl*)(void *),&LocalFree,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > > *__fastcall(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (__cdecl*)(void *),&LocalFree,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > > *result, const wchar_t *source, unsigned __int64 length)`
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180018148`
- `0x18001a4c4`
- `0x18001a920`
- `0x18001f8ec`
- `0x18001fab0`

## callees

- `0x18000e1c0`
- `0x180016924`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800169ca`
- `msvcrt!memcpy_s` at `0x1800169ca`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800169a8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800169a8`

## string_xrefs

- `0x18001694f`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (__cdecl*)(void *),&LocalFree,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > > *__fastcall wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (__cdecl*)(void *),&LocalFree,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > > *result,
        const wchar_t *source,
        unsigned __int64 length)
{
  unsigned __int64 v3; // rdi
  __int64 v6; // rbx
  unsigned __int64 v7; // rax
  const wchar_t *v8; // rbx
  wchar_t *v9; // rax
  wchar_t *v10; // rsi
  rsize_t v11; // rbx
  void *retaddr; // [rsp+58h] [rbp+0h]

  v3 = length;
  if ( source )
  {
    v7 = length;
    v8 = source;
    if ( length >= 0x7FFFFFFF )
      v7 = 0x7FFFFFFF;
    for ( ; v7; --v7 )
    {
      if ( !*v8 )
        break;
      ++v8;
    }
    v6 = v8 - source;
    if ( length == -1 )
      v3 = v6;
  }
  else
  {
    if ( length == -1 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        0xF89u,
        "onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h");
    v6 = length;
  }
  v9 = (wchar_t *)LocalAlloc(0, 2 * v3 + 2);
  v10 = v9;
  if ( v9 )
  {
    if ( source )
    {
      v11 = v6;
      memcpy_s(v9, 2 * v3 + 2, source, v11 * 2);
      v10[v11] = 0;
    }
    else
    {
      *v9 = 0;
    }
    v10[v3] = 0;
  }
  result->m_ptr = v10;
  return result;
}

```

## disassembly

```asm
0x180016924  push    rbx
0x180016926  push    rbp
0x180016927  push    rsi
0x180016928  push    rdi
0x180016929  push    r12
0x18001692b  push    r14
0x18001692d  push    r15
0x18001692f  sub     rsp, 20h
0x180016933  xor     r12d, r12d
0x180016936  mov     rdi, length
0x180016939  mov     rbp, source
0x18001693c  mov     r14, rcx
0x18001693f  test    source, source
0x180016942  jnz     short loc_180016966
0x180016944  cmp     length, 0FFFFFFFFFFFFFFFFh
0x180016948  jnz     short loc_180016961
0x18001694a  mov     rcx, [rsp+58h]; callerReturnAddress
0x18001694f  lea     length, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180016956  mov     edx, 0F89h; lineNumber
0x18001695b  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180016961  mov     rbx, rdi
0x180016964  jmp     short loc_18001699B
0x180016966  mov     ecx, 7FFFFFFFh
0x18001696b  mov     rax, rdi
0x18001696e  cmp     rdi, rcx
0x180016971  mov     rbx, rbp
0x180016974  cmovnb  rax, rcx
0x180016978  test    rax, rax
0x18001697b  jz      short loc_18001698D
0x18001697d  cmp     [rbx], r12w
0x180016981  jz      short loc_18001698D
0x180016983  add     rbx, 2
0x180016987  sub     rax, 1
0x18001698b  jnz     short loc_18001697D
0x18001698d  sub     rbx, rbp
0x180016990  sar     rbx, 1
0x180016993  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180016997  cmovz   rdi, rbx
0x18001699b  lea     r15, ds:2[rdi*2]
0x1800169a3  xor     ecx, ecx; uFlags
0x1800169a5  mov     source, r15; uBytes
0x1800169a8  call    cs:__imp_LocalAlloc
0x1800169ae  mov     rsi, rax
0x1800169b1  test    rax, rax
0x1800169b4  jz      short loc_1800169E0
0x1800169b6  test    rbp, rbp
0x1800169b9  jz      short loc_1800169D7
0x1800169bb  add     rbx, rbx
0x1800169be  mov     length, rbp; Source
0x1800169c1  mov     r9, rbx; SourceSize
0x1800169c4  mov     source, r15; DestinationSize
0x1800169c7  mov     rcx, rax; Destination
0x1800169ca  call    cs:__imp_memcpy_s
0x1800169d0  mov     [rbx+rsi], r12w
0x1800169d5  jmp     short loc_1800169DB
0x1800169d7  mov     [rax], r12w
0x1800169db  mov     [rsi+rdi*2], r12w
0x1800169e0  mov     [r14], rsi
0x1800169e3  mov     rax, r14
0x1800169e6  add     rsp, 20h
0x1800169ea  pop     r15
0x1800169ec  pop     r14
0x1800169ee  pop     r12
0x1800169f0  pop     rdi
0x1800169f1  pop     rsi
0x1800169f2  pop     rbp
0x1800169f3  pop     rbx
0x1800169f4  retn
```
