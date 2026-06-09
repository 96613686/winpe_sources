# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x18003c8b0`
- end: `0x18003c9b1`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `257`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003d9e4`

## callees

- `0x18001ef78`
- `0x18003c8b0`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18003c958`
- `msvcrt!memcpy_s` at `0x18003c958`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003c930`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003c930`

## string_xrefs

- `0x18003c99f`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  _QWORD *result; // rax
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v4 = a3;
  if ( !a2 && a3 == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xDBF,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      a4);
  v7 = a3;
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
  }
  if ( a3 == -1 )
    v4 = v7;
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
  result = a1;
  *a1 = v11;
  return result;
}

```

## disassembly

```asm
0x18003c8b0  mov     rax, rsp
0x18003c8b3  mov     [rax+8], rbx
0x18003c8b7  mov     [rax+10h], rbp
0x18003c8bb  mov     [rax+18h], rsi
0x18003c8bf  mov     [rax+20h], rdi
0x18003c8c3  push    r12
0x18003c8c5  push    r14
0x18003c8c7  push    r15
0x18003c8c9  sub     rsp, 20h
0x18003c8cd  xor     r12d, r12d
0x18003c8d0  mov     rdi, r8
0x18003c8d3  mov     rbp, rdx
0x18003c8d6  mov     r14, rcx
0x18003c8d9  test    rdx, rdx
0x18003c8dc  jnz     short loc_18003C8E8
0x18003c8de  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18003c8e2  jz      loc_18003C99A
0x18003c8e8  mov     rbx, rdi
0x18003c8eb  test    rbp, rbp
0x18003c8ee  jz      short loc_18003C91D
0x18003c8f0  mov     ecx, 7FFFFFFFh
0x18003c8f5  mov     rax, rdi
0x18003c8f8  cmp     rdi, rcx
0x18003c8fb  mov     rbx, rbp
0x18003c8fe  cmovnb  rax, rcx
0x18003c902  test    rax, rax
0x18003c905  jz      short loc_18003C917
0x18003c907  cmp     [rbx], r12w
0x18003c90b  jz      short loc_18003C917
0x18003c90d  add     rbx, 2
0x18003c911  sub     rax, 1
0x18003c915  jnz     short loc_18003C907
0x18003c917  sub     rbx, rbp
0x18003c91a  sar     rbx, 1
0x18003c91d  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18003c921  cmovz   rdi, rbx
0x18003c925  lea     r15, ds:2[rdi*2]
0x18003c92d  mov     rcx, r15; cb
0x18003c930  call    cs:__imp_CoTaskMemAlloc
0x18003c937  nop     dword ptr [rax+rax+00h]
0x18003c93c  mov     rsi, rax
0x18003c93f  test    rax, rax
0x18003c942  jz      short loc_18003C974
0x18003c944  test    rbp, rbp
0x18003c947  jz      short loc_18003C96B
0x18003c949  add     rbx, rbx
0x18003c94c  mov     r8, rbp; Source
0x18003c94f  mov     r9, rbx; SourceSize
0x18003c952  mov     rdx, r15; DestinationSize
0x18003c955  mov     rcx, rax; Destination
0x18003c958  call    cs:__imp_memcpy_s
0x18003c95f  nop     dword ptr [rax+rax+00h]
0x18003c964  mov     [rbx+rsi], r12w
0x18003c969  jmp     short loc_18003C96F
0x18003c96b  mov     [rax], r12w
0x18003c96f  mov     [rsi+rdi*2], r12w
0x18003c974  mov     rbx, [rsp+38h+arg_0]
0x18003c979  mov     rax, r14
0x18003c97c  mov     rbp, [rsp+38h+arg_8]
0x18003c981  mov     rdi, [rsp+38h+arg_18]
0x18003c986  mov     [r14], rsi
0x18003c989  mov     rsi, [rsp+38h+arg_10]
0x18003c98e  add     rsp, 20h
0x18003c992  pop     r15
0x18003c994  pop     r14
0x18003c996  pop     r12
0x18003c998  retn
0x18003c99a  mov     rcx, [rsp+38h]; this
0x18003c99f  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003c9a6  mov     edx, 0DBFh; void *
0x18003c9ab  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
