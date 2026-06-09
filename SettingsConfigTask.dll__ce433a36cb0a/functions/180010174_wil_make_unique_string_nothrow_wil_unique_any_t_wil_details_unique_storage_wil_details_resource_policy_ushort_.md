# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x180010174`
- end: `0x180010242`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `206`
- prototype: `_QWORD *__fastcall(_QWORD *, char *, unsigned __int64, const char *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001f51c`

## callees

- `0x180005c3c`
- `0x18000b99c`
- `0x180010174`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800101f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800101f6`

## string_xrefs

- `0x18001019f`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

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
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
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
0x180010174  push    rbx
0x180010176  push    rbp
0x180010177  push    rsi
0x180010178  push    rdi
0x180010179  push    r12
0x18001017b  push    r14
0x18001017d  push    r15
0x18001017f  sub     rsp, 20h
0x180010183  xor     r12d, r12d
0x180010186  mov     rdi, r8
0x180010189  mov     rbp, rdx
0x18001018c  mov     r14, rcx
0x18001018f  test    rdx, rdx
0x180010192  jnz     short loc_1800101B6
0x180010194  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x180010198  jnz     short loc_1800101B1
0x18001019a  mov     rcx, [rsp+58h]; this
0x18001019f  lea     r8, aOnecoreInterna_7; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800101a6  mov     edx, 0F89h; void *
0x1800101ab  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800101b1  mov     rbx, rdi
0x1800101b4  jmp     short loc_1800101EB
0x1800101b6  mov     ecx, 7FFFFFFFh
0x1800101bb  mov     rax, rdi
0x1800101be  cmp     rdi, rcx
0x1800101c1  mov     rbx, rbp
0x1800101c4  cmovnb  rax, rcx
0x1800101c8  test    rax, rax
0x1800101cb  jz      short loc_1800101DD
0x1800101cd  cmp     [rbx], r12w
0x1800101d1  jz      short loc_1800101DD
0x1800101d3  add     rbx, 2
0x1800101d7  sub     rax, 1
0x1800101db  jnz     short loc_1800101CD
0x1800101dd  sub     rbx, rbp
0x1800101e0  sar     rbx, 1
0x1800101e3  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800101e7  cmovz   rdi, rbx
0x1800101eb  lea     r15, ds:2[rdi*2]
0x1800101f3  mov     rcx, r15; cb
0x1800101f6  call    cs:__imp_CoTaskMemAlloc
0x1800101fc  mov     rsi, rax
0x1800101ff  test    rax, rax
0x180010202  jz      short loc_18001022D
0x180010204  test    rbp, rbp
0x180010207  jz      short loc_180010224
0x180010209  add     rbx, rbx
0x18001020c  mov     r8, rbp; Source
0x18001020f  mov     r9, rbx; SourceSize
0x180010212  mov     rdx, r15; DestinationSize
0x180010215  mov     rcx, rax; Destination
0x180010218  call    memcpy_s
0x18001021d  mov     [rbx+rsi], r12w
0x180010222  jmp     short loc_180010228
0x180010224  mov     [rax], r12w
0x180010228  mov     [rsi+rdi*2], r12w
0x18001022d  mov     [r14], rsi
0x180010230  mov     rax, r14
0x180010233  add     rsp, 20h
0x180010237  pop     r15
0x180010239  pop     r14
0x18001023b  pop     r12
0x18001023d  pop     rdi
0x18001023e  pop     rsi
0x18001023f  pop     rbp
0x180010240  pop     rbx
0x180010241  retn
```
