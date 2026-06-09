# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x180015140`
- end: `0x18001520e`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `206`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18001d65c`
- `0x180021600`
- `0x180069324`

## callees

- `0x180010728`
- `0x18001360c`
- `0x180015140`

## import_xrefs

- `OLE32!CoTaskMemAlloc` at `0x1800151c2`
- `OLE32!CoTaskMemAlloc` at `0x1800151c2`

## string_xrefs

- `0x18001516b`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x180015140  push    rbx
0x180015142  push    rbp
0x180015143  push    rsi
0x180015144  push    rdi
0x180015145  push    r12
0x180015147  push    r14
0x180015149  push    r15
0x18001514b  sub     rsp, 20h
0x18001514f  xor     r12d, r12d
0x180015152  mov     rdi, r8
0x180015155  mov     rbp, rdx
0x180015158  mov     r14, rcx
0x18001515b  test    rdx, rdx
0x18001515e  jnz     short loc_180015182
0x180015160  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x180015164  jnz     short loc_18001517D
0x180015166  mov     rcx, [rsp+58h]; this
0x18001516b  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180015172  mov     edx, 0F89h; void *
0x180015177  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18001517d  mov     rbx, rdi
0x180015180  jmp     short loc_1800151B7
0x180015182  mov     ecx, 7FFFFFFFh
0x180015187  mov     rax, rdi
0x18001518a  cmp     rdi, rcx
0x18001518d  mov     rbx, rbp
0x180015190  cmovnb  rax, rcx
0x180015194  test    rax, rax
0x180015197  jz      short loc_1800151A9
0x180015199  cmp     [rbx], r12w
0x18001519d  jz      short loc_1800151A9
0x18001519f  add     rbx, 2
0x1800151a3  sub     rax, 1
0x1800151a7  jnz     short loc_180015199
0x1800151a9  sub     rbx, rbp
0x1800151ac  sar     rbx, 1
0x1800151af  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800151b3  cmovz   rdi, rbx
0x1800151b7  lea     r15, ds:2[rdi*2]
0x1800151bf  mov     rcx, r15; cb
0x1800151c2  call    cs:__imp_CoTaskMemAlloc
0x1800151c8  mov     rsi, rax
0x1800151cb  test    rax, rax
0x1800151ce  jz      short loc_1800151F9
0x1800151d0  test    rbp, rbp
0x1800151d3  jz      short loc_1800151F0
0x1800151d5  add     rbx, rbx
0x1800151d8  mov     r8, rbp; Source
0x1800151db  mov     r9, rbx; SourceSize
0x1800151de  mov     rdx, r15; DestinationSize
0x1800151e1  mov     rcx, rax; Destination
0x1800151e4  call    memcpy_s
0x1800151e9  mov     [rbx+rsi], r12w
0x1800151ee  jmp     short loc_1800151F4
0x1800151f0  mov     [rax], r12w
0x1800151f4  mov     [rsi+rdi*2], r12w
0x1800151f9  mov     [r14], rsi
0x1800151fc  mov     rax, r14
0x1800151ff  add     rsp, 20h
0x180015203  pop     r15
0x180015205  pop     r14
0x180015207  pop     r12
0x180015209  pop     rdi
0x18001520a  pop     rsi
0x18001520b  pop     rbp
0x18001520c  pop     rbx
0x18001520d  retn
```
