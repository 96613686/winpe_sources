# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x180018854`
- end: `0x180018956`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `258`
- prototype: `_QWORD *__fastcall(_QWORD *, char *, unsigned __int64, const char *)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180018ed0`
- `0x18001b940`
- `0x1800280d0`

## callees

- `0x180005356`
- `0x1800053c4`
- `0x1800098db`
- `0x18001223c`
- `0x180018854`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180018902`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180018902`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800188c5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800188c5`

## string_xrefs

- `0x180018944`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
_QWORD *__fastcall wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
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
  size_t v12; // rbx
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
  v10 = LocalAlloc(0, 2 * v4 + 2);
  v11 = v10;
  if ( v10 )
  {
    if ( a2 )
    {
      v12 = 2 * v7;
      if ( v12 )
      {
        if ( 2 * v4 + 2 < v12 )
        {
          memset_0(v10, 0, 2 * v4 + 2);
          *(_DWORD *)_o__errno() = 34;
          invalid_parameter_noinfo();
        }
        else
        {
          memcpy_0(v10, a2, v12);
        }
      }
      v11[v12 / 2] = 0;
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
0x180018854  push    rbx
0x180018856  push    rbp
0x180018857  push    rsi
0x180018858  push    rdi
0x180018859  push    r12
0x18001885b  push    r14
0x18001885d  push    r15
0x18001885f  sub     rsp, 20h
0x180018863  xor     r12d, r12d
0x180018866  mov     rdi, r8
0x180018869  mov     rbp, rdx
0x18001886c  mov     r15, rcx
0x18001886f  test    rdx, rdx
0x180018872  jnz     short loc_180018883
0x180018874  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x180018878  jz      loc_18001893F
0x18001887e  mov     rbx, r8
0x180018881  jmp     short loc_1800188B8
0x180018883  mov     ecx, 7FFFFFFFh
0x180018888  mov     rax, rdi
0x18001888b  cmp     rdi, rcx
0x18001888e  mov     rbx, rbp
0x180018891  cmovnb  rax, rcx
0x180018895  test    rax, rax
0x180018898  jz      short loc_1800188AA
0x18001889a  cmp     [rbx], r12w
0x18001889e  jz      short loc_1800188AA
0x1800188a0  add     rbx, 2
0x1800188a4  sub     rax, 1
0x1800188a8  jnz     short loc_18001889A
0x1800188aa  sub     rbx, rbp
0x1800188ad  sar     rbx, 1
0x1800188b0  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800188b4  cmovz   rdi, rbx
0x1800188b8  lea     r14, ds:2[rdi*2]
0x1800188c0  xor     ecx, ecx; uFlags
0x1800188c2  mov     rdx, r14; uBytes
0x1800188c5  call    cs:__imp_LocalAlloc
0x1800188cc  nop     dword ptr [rax+rax+00h]
0x1800188d1  mov     rsi, rax
0x1800188d4  test    rax, rax
0x1800188d7  jz      short loc_180018929
0x1800188d9  test    rbp, rbp
0x1800188dc  jz      short loc_180018920
0x1800188de  add     rbx, rbx
0x1800188e1  jz      short loc_180018919
0x1800188e3  mov     rcx, rax; void *
0x1800188e6  cmp     r14, rbx
0x1800188e9  jb      short loc_1800188F8
0x1800188eb  mov     r8, rbx; Size
0x1800188ee  mov     rdx, rbp; Src
0x1800188f1  call    memcpy_0
0x1800188f6  jmp     short loc_180018919
0x1800188f8  mov     r8, r14; Size
0x1800188fb  xor     edx, edx; Val
0x1800188fd  call    memset_0
0x180018902  call    cs:__imp__o__errno
0x180018909  nop     dword ptr [rax+rax+00h]
0x18001890e  mov     dword ptr [rax], 22h ; '"'
0x180018914  call    _invalid_parameter_noinfo
0x180018919  mov     [rbx+rsi], r12w
0x18001891e  jmp     short loc_180018924
0x180018920  mov     [rax], r12w
0x180018924  mov     [rsi+rdi*2], r12w
0x180018929  mov     [r15], rsi
0x18001892c  mov     rax, r15
0x18001892f  add     rsp, 20h
0x180018933  pop     r15
0x180018935  pop     r14
0x180018937  pop     r12
0x180018939  pop     rdi
0x18001893a  pop     rsi
0x18001893b  pop     rbp
0x18001893c  pop     rbx
0x18001893d  retn
0x18001893f  mov     rcx, [rsp+58h]; this
0x180018944  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001894b  mov     edx, 0F89h; void *
0x180018950  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
