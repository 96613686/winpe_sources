# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x18002aa2c`
- end: `0x18002aafe`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `210`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002c548`

## callees

- `0x180007554`
- `0x180009cc8`
- `0x18002aa2c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002aa9b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002aa9b`

## string_xrefs

- `0x18002aaec`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x18002aa2c  push    rbx
0x18002aa2e  push    rbp
0x18002aa2f  push    rsi
0x18002aa30  push    rdi
0x18002aa31  push    r12
0x18002aa33  push    r14
0x18002aa35  push    r15
0x18002aa37  sub     rsp, 20h
0x18002aa3b  xor     r12d, r12d
0x18002aa3e  mov     rdi, r8
0x18002aa41  mov     rbp, rdx
0x18002aa44  mov     r14, rcx
0x18002aa47  test    rdx, rdx
0x18002aa4a  jnz     short loc_18002AA5B
0x18002aa4c  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18002aa50  jz      loc_18002AAE7
0x18002aa56  mov     rbx, r8
0x18002aa59  jmp     short loc_18002AA90
0x18002aa5b  mov     ecx, 7FFFFFFFh
0x18002aa60  mov     rax, rdi
0x18002aa63  cmp     rdi, rcx
0x18002aa66  mov     rbx, rbp
0x18002aa69  cmovnb  rax, rcx
0x18002aa6d  test    rax, rax
0x18002aa70  jz      short loc_18002AA82
0x18002aa72  cmp     [rbx], r12w
0x18002aa76  jz      short loc_18002AA82
0x18002aa78  add     rbx, 2
0x18002aa7c  sub     rax, 1
0x18002aa80  jnz     short loc_18002AA72
0x18002aa82  sub     rbx, rbp
0x18002aa85  sar     rbx, 1
0x18002aa88  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18002aa8c  cmovz   rdi, rbx
0x18002aa90  lea     r15, ds:2[rdi*2]
0x18002aa98  mov     rcx, r15; cb
0x18002aa9b  call    cs:__imp_CoTaskMemAlloc
0x18002aaa1  mov     rsi, rax
0x18002aaa4  test    rax, rax
0x18002aaa7  jz      short loc_18002AAD2
0x18002aaa9  test    rbp, rbp
0x18002aaac  jz      short loc_18002AAC9
0x18002aaae  add     rbx, rbx
0x18002aab1  mov     r8, rbp; Source
0x18002aab4  mov     r9, rbx; SourceSize
0x18002aab7  mov     rdx, r15; DestinationSize
0x18002aaba  mov     rcx, rax; Destination
0x18002aabd  call    memcpy_s
0x18002aac2  mov     [rbx+rsi], r12w
0x18002aac7  jmp     short loc_18002AACD
0x18002aac9  mov     [rax], r12w
0x18002aacd  mov     [rsi+rdi*2], r12w
0x18002aad2  mov     [r14], rsi
0x18002aad5  mov     rax, r14
0x18002aad8  add     rsp, 20h
0x18002aadc  pop     r15
0x18002aade  pop     r14
0x18002aae0  pop     r12
0x18002aae2  pop     rdi
0x18002aae3  pop     rsi
0x18002aae4  pop     rbp
0x18002aae5  pop     rbx
0x18002aae6  retn
0x18002aae7  mov     rcx, [rsp+58h]; this
0x18002aaec  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002aaf3  mov     edx, 0F89h; void *
0x18002aaf8  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
