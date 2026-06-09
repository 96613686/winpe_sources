# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x180055c30`
- end: `0x180055cfe`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `206`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180055d04`

## callees

- `0x180002adc`
- `0x18001049c`
- `0x180055c30`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180055cb2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180055cb2`

## string_xrefs

- `0x180055c5b`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x180055c30  push    rbx
0x180055c32  push    rbp
0x180055c33  push    rsi
0x180055c34  push    rdi
0x180055c35  push    r12
0x180055c37  push    r14
0x180055c39  push    r15
0x180055c3b  sub     rsp, 20h
0x180055c3f  xor     r12d, r12d
0x180055c42  mov     rdi, r8
0x180055c45  mov     rbp, rdx
0x180055c48  mov     r14, rcx
0x180055c4b  test    rdx, rdx
0x180055c4e  jnz     short loc_180055C72
0x180055c50  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x180055c54  jnz     short loc_180055C6D
0x180055c56  mov     rcx, [rsp+58h]; this
0x180055c5b  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180055c62  mov     edx, 0F89h; void *
0x180055c67  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180055c6d  mov     rbx, rdi
0x180055c70  jmp     short loc_180055CA7
0x180055c72  mov     ecx, 7FFFFFFFh
0x180055c77  mov     rax, rdi
0x180055c7a  cmp     rdi, rcx
0x180055c7d  mov     rbx, rbp
0x180055c80  cmovnb  rax, rcx
0x180055c84  test    rax, rax
0x180055c87  jz      short loc_180055C99
0x180055c89  cmp     [rbx], r12w
0x180055c8d  jz      short loc_180055C99
0x180055c8f  add     rbx, 2
0x180055c93  sub     rax, 1
0x180055c97  jnz     short loc_180055C89
0x180055c99  sub     rbx, rbp
0x180055c9c  sar     rbx, 1
0x180055c9f  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180055ca3  cmovz   rdi, rbx
0x180055ca7  lea     r15, ds:2[rdi*2]
0x180055caf  mov     rcx, r15; cb
0x180055cb2  call    cs:__imp_CoTaskMemAlloc
0x180055cb8  mov     rsi, rax
0x180055cbb  test    rax, rax
0x180055cbe  jz      short loc_180055CE9
0x180055cc0  test    rbp, rbp
0x180055cc3  jz      short loc_180055CE0
0x180055cc5  add     rbx, rbx
0x180055cc8  mov     r8, rbp; Source
0x180055ccb  mov     r9, rbx; SourceSize
0x180055cce  mov     rdx, r15; DestinationSize
0x180055cd1  mov     rcx, rax; Destination
0x180055cd4  call    memcpy_s
0x180055cd9  mov     [rbx+rsi], r12w
0x180055cde  jmp     short loc_180055CE4
0x180055ce0  mov     [rax], r12w
0x180055ce4  mov     [rsi+rdi*2], r12w
0x180055ce9  mov     [r14], rsi
0x180055cec  mov     rax, r14
0x180055cef  add     rsp, 20h
0x180055cf3  pop     r15
0x180055cf5  pop     r14
0x180055cf7  pop     r12
0x180055cf9  pop     rdi
0x180055cfa  pop     rsi
0x180055cfb  pop     rbp
0x180055cfc  pop     rbx
0x180055cfd  retn
```
