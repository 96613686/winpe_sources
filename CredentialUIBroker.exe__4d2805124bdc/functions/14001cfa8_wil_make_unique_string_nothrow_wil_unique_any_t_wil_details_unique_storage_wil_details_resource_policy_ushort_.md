# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x14001cfa8`
- end: `0x14001d076`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `206`
- prototype: `_QWORD *__fastcall(_QWORD *, char *, unsigned __int64, const char *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14001dc30`

## callees

- `0x14000427c`
- `0x140017d8c`
- `0x14001cfa8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14001d02a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14001d02a`

## string_xrefs

- `0x14001cfd3`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x14001cfa8  push    rbx
0x14001cfaa  push    rbp
0x14001cfab  push    rsi
0x14001cfac  push    rdi
0x14001cfad  push    r12
0x14001cfaf  push    r14
0x14001cfb1  push    r15
0x14001cfb3  sub     rsp, 20h
0x14001cfb7  xor     r12d, r12d
0x14001cfba  mov     rdi, r8
0x14001cfbd  mov     rbp, rdx
0x14001cfc0  mov     r14, rcx
0x14001cfc3  test    rdx, rdx
0x14001cfc6  jnz     short loc_14001CFEA
0x14001cfc8  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x14001cfcc  jnz     short loc_14001CFE5
0x14001cfce  mov     rcx, [rsp+58h]; this
0x14001cfd3  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14001cfda  mov     edx, 0F89h; void *
0x14001cfdf  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x14001cfe5  mov     rbx, rdi
0x14001cfe8  jmp     short loc_14001D01F
0x14001cfea  mov     ecx, 7FFFFFFFh
0x14001cfef  mov     rax, rdi
0x14001cff2  cmp     rdi, rcx
0x14001cff5  mov     rbx, rbp
0x14001cff8  cmovnb  rax, rcx
0x14001cffc  test    rax, rax
0x14001cfff  jz      short loc_14001D011
0x14001d001  cmp     [rbx], r12w
0x14001d005  jz      short loc_14001D011
0x14001d007  add     rbx, 2
0x14001d00b  sub     rax, 1
0x14001d00f  jnz     short loc_14001D001
0x14001d011  sub     rbx, rbp
0x14001d014  sar     rbx, 1
0x14001d017  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x14001d01b  cmovz   rdi, rbx
0x14001d01f  lea     r15, ds:2[rdi*2]
0x14001d027  mov     rcx, r15; cb
0x14001d02a  call    cs:__imp_CoTaskMemAlloc
0x14001d030  mov     rsi, rax
0x14001d033  test    rax, rax
0x14001d036  jz      short loc_14001D061
0x14001d038  test    rbp, rbp
0x14001d03b  jz      short loc_14001D058
0x14001d03d  add     rbx, rbx
0x14001d040  mov     r8, rbp; Source
0x14001d043  mov     r9, rbx; SourceSize
0x14001d046  mov     rdx, r15; DestinationSize
0x14001d049  mov     rcx, rax; Destination
0x14001d04c  call    memcpy_s
0x14001d051  mov     [rbx+rsi], r12w
0x14001d056  jmp     short loc_14001D05C
0x14001d058  mov     [rax], r12w
0x14001d05c  mov     [rsi+rdi*2], r12w
0x14001d061  mov     [r14], rsi
0x14001d064  mov     rax, r14
0x14001d067  add     rsp, 20h
0x14001d06b  pop     r15
0x14001d06d  pop     r14
0x14001d06f  pop     r12
0x14001d071  pop     rdi
0x14001d072  pop     rsi
0x14001d073  pop     rbp
0x14001d074  pop     rbx
0x14001d075  retn
```
