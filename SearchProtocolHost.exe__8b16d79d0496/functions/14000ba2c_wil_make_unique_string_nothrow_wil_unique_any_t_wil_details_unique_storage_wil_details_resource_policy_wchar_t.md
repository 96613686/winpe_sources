# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(wchar_t const *,unsigned __int64)

- ea: `0x14000ba2c`
- end: `0x14000bafe`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W_K@Z`
- size: `210`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140036db4`

## callees

- `0x14000ba2c`
- `0x140015abc`
- `0x14003a0a8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14000ba9b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14000ba9b`

## string_xrefs

- `0x14000baec`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
_QWORD *__fastcall wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(
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
0x14000ba2c  push    rbx
0x14000ba2e  push    rbp
0x14000ba2f  push    rsi
0x14000ba30  push    rdi
0x14000ba31  push    r12
0x14000ba33  push    r14
0x14000ba35  push    r15
0x14000ba37  sub     rsp, 20h
0x14000ba3b  xor     r12d, r12d
0x14000ba3e  mov     rdi, r8
0x14000ba41  mov     rbp, rdx
0x14000ba44  mov     r14, rcx
0x14000ba47  test    rdx, rdx
0x14000ba4a  jnz     short loc_14000BA5B
0x14000ba4c  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x14000ba50  jz      loc_14000BAE7
0x14000ba56  mov     rbx, r8
0x14000ba59  jmp     short loc_14000BA90
0x14000ba5b  mov     ecx, 7FFFFFFFh
0x14000ba60  mov     rax, rdi
0x14000ba63  cmp     rdi, rcx
0x14000ba66  mov     rbx, rbp
0x14000ba69  cmovnb  rax, rcx
0x14000ba6d  test    rax, rax
0x14000ba70  jz      short loc_14000BA82
0x14000ba72  cmp     [rbx], r12w
0x14000ba76  jz      short loc_14000BA82
0x14000ba78  add     rbx, 2
0x14000ba7c  sub     rax, 1
0x14000ba80  jnz     short loc_14000BA72
0x14000ba82  sub     rbx, rbp
0x14000ba85  sar     rbx, 1
0x14000ba88  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x14000ba8c  cmovz   rdi, rbx
0x14000ba90  lea     r15, ds:2[rdi*2]
0x14000ba98  mov     rcx, r15; cb
0x14000ba9b  call    cs:__imp_CoTaskMemAlloc
0x14000baa1  mov     rsi, rax
0x14000baa4  test    rax, rax
0x14000baa7  jz      short loc_14000BAD2
0x14000baa9  test    rbp, rbp
0x14000baac  jz      short loc_14000BAC9
0x14000baae  add     rbx, rbx
0x14000bab1  mov     r8, rbp; Source
0x14000bab4  mov     r9, rbx; SourceSize
0x14000bab7  mov     rdx, r15; DestinationSize
0x14000baba  mov     rcx, rax; Destination
0x14000babd  call    memcpy_s
0x14000bac2  mov     [rbx+rsi], r12w
0x14000bac7  jmp     short loc_14000BACD
0x14000bac9  mov     [rax], r12w
0x14000bacd  mov     [rsi+rdi*2], r12w
0x14000bad2  mov     [r14], rsi
0x14000bad5  mov     rax, r14
0x14000bad8  add     rsp, 20h
0x14000badc  pop     r15
0x14000bade  pop     r14
0x14000bae0  pop     r12
0x14000bae2  pop     rdi
0x14000bae3  pop     rsi
0x14000bae4  pop     rbp
0x14000bae5  pop     rbx
0x14000bae6  retn
0x14000bae7  mov     rcx, [rsp+58h]; this
0x14000baec  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14000baf3  mov     edx, 0F89h; void *
0x14000baf8  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
