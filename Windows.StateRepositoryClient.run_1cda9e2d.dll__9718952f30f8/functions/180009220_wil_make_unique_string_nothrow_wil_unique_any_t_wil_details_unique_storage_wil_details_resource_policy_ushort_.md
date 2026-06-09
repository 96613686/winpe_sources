# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x180009220`
- end: `0x1800092b2`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `146`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000bf90`

## callees

- `0x1800035e8`
- `0x180009220`
- `0x18000c568`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000927a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000927a`

## string_xrefs

- `0x180009240`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
_QWORD *__fastcall wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
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
  v9 = (char *)LocalAlloc(0, v8 + 2);
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
0x180009220  push    rbx
0x180009222  push    rbp
0x180009223  push    rsi
0x180009224  push    rdi
0x180009225  push    r14
0x180009227  push    r15
0x180009229  sub     rsp, 28h
0x18000922d  xor     r15d, r15d
0x180009230  mov     rbx, rdx
0x180009233  mov     rsi, rcx
0x180009236  test    rdx, rdx
0x180009239  jnz     short loc_180009252
0x18000923b  mov     rcx, [rsp+58h]; this
0x180009240  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180009247  mov     edx, 0F89h; void *
0x18000924c  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180009252  mov     ecx, 7FFFFFFFh
0x180009257  mov     rax, rbx
0x18000925a  cmp     [rax], r15w
0x18000925e  jz      short loc_18000926A
0x180009260  add     rax, 2
0x180009264  sub     rcx, 1
0x180009268  jnz     short loc_18000925A
0x18000926a  sub     rax, rbx
0x18000926d  xor     ecx, ecx; uFlags
0x18000926f  sar     rax, 1
0x180009272  lea     r14, [rax+rax]
0x180009276  lea     rdx, [r14+2]; uBytes
0x18000927a  call    cs:__imp_LocalAlloc
0x180009280  mov     rdi, rax
0x180009283  test    rax, rax
0x180009286  jz      short loc_18000929F
0x180009288  mov     r9, r14; SourceSize
0x18000928b  lea     rdx, [r14+2]; DestinationSize
0x18000928f  mov     r8, rbx; Source
0x180009292  mov     rcx, rax; Destination
0x180009295  call    memcpy_s
0x18000929a  mov     [r14+rdi], r15w
0x18000929f  mov     [rsi], rdi
0x1800092a2  mov     rax, rsi
0x1800092a5  add     rsp, 28h
0x1800092a9  pop     r15
0x1800092ab  pop     r14
0x1800092ad  pop     rdi
0x1800092ae  pop     rsi
0x1800092af  pop     rbp
0x1800092b0  pop     rbx
0x1800092b1  retn
```
