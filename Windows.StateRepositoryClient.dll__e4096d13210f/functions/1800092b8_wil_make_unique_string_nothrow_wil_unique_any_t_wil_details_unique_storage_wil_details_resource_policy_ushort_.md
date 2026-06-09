# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x1800092b8`
- end: `0x180009348`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `144`
- prototype: `_QWORD *__fastcall(_QWORD *, char *, __int64, const char *)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000d100`
- `0x18000d490`
- `0x18000d7d0`

## callees

- `0x1800035e8`
- `0x1800092b8`
- `0x18000c568`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800092f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800092f9`

## string_xrefs

- `0x180009336`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

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
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
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
0x1800092b8  push    rbx
0x1800092ba  push    rbp
0x1800092bb  push    rsi
0x1800092bc  push    rdi
0x1800092bd  push    r14
0x1800092bf  push    r15
0x1800092c1  sub     rsp, 28h
0x1800092c5  xor     r15d, r15d
0x1800092c8  mov     rbx, rdx
0x1800092cb  mov     rsi, rcx
0x1800092ce  test    rdx, rdx
0x1800092d1  jz      short loc_180009331
0x1800092d3  mov     ecx, 7FFFFFFFh
0x1800092d8  mov     rax, rdx
0x1800092db  cmp     [rax], r15w
0x1800092df  jz      short loc_1800092EB
0x1800092e1  add     rax, 2
0x1800092e5  sub     rcx, 1
0x1800092e9  jnz     short loc_1800092DB
0x1800092eb  sub     rax, rbx
0x1800092ee  sar     rax, 1
0x1800092f1  lea     r14, [rax+rax]
0x1800092f5  lea     rcx, [r14+2]; cb
0x1800092f9  call    cs:__imp_CoTaskMemAlloc
0x1800092ff  mov     rdi, rax
0x180009302  test    rax, rax
0x180009305  jz      short loc_18000931E
0x180009307  mov     r9, r14; SourceSize
0x18000930a  lea     rdx, [r14+2]; DestinationSize
0x18000930e  mov     r8, rbx; Source
0x180009311  mov     rcx, rax; Destination
0x180009314  call    memcpy_s
0x180009319  mov     [r14+rdi], r15w
0x18000931e  mov     [rsi], rdi
0x180009321  mov     rax, rsi
0x180009324  add     rsp, 28h
0x180009328  pop     r15
0x18000932a  pop     r14
0x18000932c  pop     rdi
0x18000932d  pop     rsi
0x18000932e  pop     rbp
0x18000932f  pop     rbx
0x180009330  retn
0x180009331  mov     rcx, [rsp+58h]; this
0x180009336  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000933d  mov     edx, 0F89h; void *
0x180009342  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
