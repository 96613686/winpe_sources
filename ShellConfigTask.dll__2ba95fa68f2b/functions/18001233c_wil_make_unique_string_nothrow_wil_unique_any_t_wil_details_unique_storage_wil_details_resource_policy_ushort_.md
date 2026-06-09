# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x18001233c`
- end: `0x18001240e`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `210`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180023834`
- `0x180025648`

## callees

- `0x180006cb8`
- `0x18000cdf0`
- `0x18001233c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800123ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800123ab`

## string_xrefs

- `0x1800123fc`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

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
0x18001233c  push    rbx
0x18001233e  push    rbp
0x18001233f  push    rsi
0x180012340  push    rdi
0x180012341  push    r12
0x180012343  push    r14
0x180012345  push    r15
0x180012347  sub     rsp, 20h
0x18001234b  xor     r12d, r12d
0x18001234e  mov     rdi, r8
0x180012351  mov     rbp, rdx
0x180012354  mov     r14, rcx
0x180012357  test    rdx, rdx
0x18001235a  jnz     short loc_18001236B
0x18001235c  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x180012360  jz      loc_1800123F7
0x180012366  mov     rbx, r8
0x180012369  jmp     short loc_1800123A0
0x18001236b  mov     ecx, 7FFFFFFFh
0x180012370  mov     rax, rdi
0x180012373  cmp     rdi, rcx
0x180012376  mov     rbx, rbp
0x180012379  cmovnb  rax, rcx
0x18001237d  test    rax, rax
0x180012380  jz      short loc_180012392
0x180012382  cmp     [rbx], r12w
0x180012386  jz      short loc_180012392
0x180012388  add     rbx, 2
0x18001238c  sub     rax, 1
0x180012390  jnz     short loc_180012382
0x180012392  sub     rbx, rbp
0x180012395  sar     rbx, 1
0x180012398  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18001239c  cmovz   rdi, rbx
0x1800123a0  lea     r15, ds:2[rdi*2]
0x1800123a8  mov     rcx, r15; cb
0x1800123ab  call    cs:__imp_CoTaskMemAlloc
0x1800123b1  mov     rsi, rax
0x1800123b4  test    rax, rax
0x1800123b7  jz      short loc_1800123E2
0x1800123b9  test    rbp, rbp
0x1800123bc  jz      short loc_1800123D9
0x1800123be  add     rbx, rbx
0x1800123c1  mov     r8, rbp; Source
0x1800123c4  mov     r9, rbx; SourceSize
0x1800123c7  mov     rdx, r15; DestinationSize
0x1800123ca  mov     rcx, rax; Destination
0x1800123cd  call    memcpy_s
0x1800123d2  mov     [rbx+rsi], r12w
0x1800123d7  jmp     short loc_1800123DD
0x1800123d9  mov     [rax], r12w
0x1800123dd  mov     [rsi+rdi*2], r12w
0x1800123e2  mov     [r14], rsi
0x1800123e5  mov     rax, r14
0x1800123e8  add     rsp, 20h
0x1800123ec  pop     r15
0x1800123ee  pop     r14
0x1800123f0  pop     r12
0x1800123f2  pop     rdi
0x1800123f3  pop     rsi
0x1800123f4  pop     rbp
0x1800123f5  pop     rbx
0x1800123f6  retn
0x1800123f7  mov     rcx, [rsp+58h]; this
0x1800123fc  lea     r8, aOnecoreInterna_7; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180012403  mov     edx, 0F89h; void *
0x180012408  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
