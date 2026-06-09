# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x180009538`
- end: `0x1800095c8`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `144`
- prototype: `_QWORD *__fastcall(_QWORD *, char *, __int64, const char *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800094f0`

## callees

- `0x180005920`
- `0x180009538`
- `0x18000f094`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009590`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009590`

## string_xrefs

- `0x180009558`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

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
0x180009538  push    rbx
0x18000953a  push    rbp
0x18000953b  push    rsi
0x18000953c  push    rdi
0x18000953d  push    r14
0x18000953f  push    r15
0x180009541  sub     rsp, 28h
0x180009545  xor     r15d, r15d
0x180009548  mov     rbx, rdx
0x18000954b  mov     rsi, rcx
0x18000954e  test    rdx, rdx
0x180009551  jnz     short loc_18000956A
0x180009553  mov     rcx, [rsp+58h]; this
0x180009558  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000955f  mov     edx, 0F89h; void *
0x180009564  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000956a  mov     ecx, 7FFFFFFFh
0x18000956f  mov     rax, rbx
0x180009572  cmp     [rax], r15w
0x180009576  jz      short loc_180009582
0x180009578  add     rax, 2
0x18000957c  sub     rcx, 1
0x180009580  jnz     short loc_180009572
0x180009582  sub     rax, rbx
0x180009585  sar     rax, 1
0x180009588  lea     r14, [rax+rax]
0x18000958c  lea     rcx, [r14+2]; cb
0x180009590  call    cs:__imp_CoTaskMemAlloc
0x180009596  mov     rdi, rax
0x180009599  test    rax, rax
0x18000959c  jz      short loc_1800095B5
0x18000959e  mov     r9, r14; SourceSize
0x1800095a1  lea     rdx, [r14+2]; DestinationSize
0x1800095a5  mov     r8, rbx; Source
0x1800095a8  mov     rcx, rax; Destination
0x1800095ab  call    memcpy_s
0x1800095b0  mov     [r14+rdi], r15w
0x1800095b5  mov     [rsi], rdi
0x1800095b8  mov     rax, rsi
0x1800095bb  add     rsp, 28h
0x1800095bf  pop     r15
0x1800095c1  pop     r14
0x1800095c3  pop     rdi
0x1800095c4  pop     rsi
0x1800095c5  pop     rbp
0x1800095c6  pop     rbx
0x1800095c7  retn
```
