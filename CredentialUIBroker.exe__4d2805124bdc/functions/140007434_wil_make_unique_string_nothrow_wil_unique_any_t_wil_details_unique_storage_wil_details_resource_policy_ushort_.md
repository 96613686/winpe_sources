# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x140007434`
- end: `0x140007501`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `205`
- prototype: `_QWORD *__fastcall(_QWORD *, char *, unsigned __int64, const char *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14001a788`

## callees

- `0x140007434`
- `0x140017d8c`
- `0x140019058`
- `0x14001c2b8`

## string_xrefs

- `0x14000745f`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
_QWORD *__fastcall wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
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
  v10 = wil::details::heap_allocator::allocate(2 * v4 + 2);
  v11 = v10;
  if ( v10 )
  {
    if ( a2 )
    {
      v12 = v7;
      memcpy_s_0(v10, 2 * v4 + 2, a2, v12 * 2);
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
0x140007434  push    rbx
0x140007436  push    rbp
0x140007437  push    rsi
0x140007438  push    rdi
0x140007439  push    r12
0x14000743b  push    r14
0x14000743d  push    r15
0x14000743f  sub     rsp, 20h
0x140007443  xor     r12d, r12d
0x140007446  mov     rdi, r8
0x140007449  mov     rbp, rdx
0x14000744c  mov     r14, rcx
0x14000744f  test    rdx, rdx
0x140007452  jnz     short loc_140007476
0x140007454  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x140007458  jnz     short loc_140007471
0x14000745a  mov     rcx, [rsp+58h]; this
0x14000745f  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140007466  mov     edx, 0F89h; void *
0x14000746b  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x140007471  mov     rbx, rdi
0x140007474  jmp     short loc_1400074AB
0x140007476  mov     ecx, 7FFFFFFFh
0x14000747b  mov     rax, rdi
0x14000747e  cmp     rdi, rcx
0x140007481  mov     rbx, rbp
0x140007484  cmovnb  rax, rcx
0x140007488  test    rax, rax
0x14000748b  jz      short loc_14000749D
0x14000748d  cmp     [rbx], r12w
0x140007491  jz      short loc_14000749D
0x140007493  add     rbx, 2
0x140007497  sub     rax, 1
0x14000749b  jnz     short loc_14000748D
0x14000749d  sub     rbx, rbp
0x1400074a0  sar     rbx, 1
0x1400074a3  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1400074a7  cmovz   rdi, rbx
0x1400074ab  lea     r15, ds:2[rdi*2]
0x1400074b3  mov     rcx, r15; unsigned __int64
0x1400074b6  call    ?allocate@heap_allocator@details@wil@@SAPEAX_K@Z; wil::details::heap_allocator::allocate(unsigned __int64)
0x1400074bb  mov     rsi, rax
0x1400074be  test    rax, rax
0x1400074c1  jz      short loc_1400074EC
0x1400074c3  test    rbp, rbp
0x1400074c6  jz      short loc_1400074E3
0x1400074c8  add     rbx, rbx
0x1400074cb  mov     r8, rbp; Source
0x1400074ce  mov     r9, rbx; SourceSize
0x1400074d1  mov     rdx, r15; DestinationSize
0x1400074d4  mov     rcx, rax; Destination
0x1400074d7  call    memcpy_s_0
0x1400074dc  mov     [rbx+rsi], r12w
0x1400074e1  jmp     short loc_1400074E7
0x1400074e3  mov     [rax], r12w
0x1400074e7  mov     [rsi+rdi*2], r12w
0x1400074ec  mov     [r14], rsi
0x1400074ef  mov     rax, r14
0x1400074f2  add     rsp, 20h
0x1400074f6  pop     r15
0x1400074f8  pop     r14
0x1400074fa  pop     r12
0x1400074fc  pop     rdi
0x1400074fd  pop     rsi
0x1400074fe  pop     rbp
0x1400074ff  pop     rbx
0x140007500  retn
```
