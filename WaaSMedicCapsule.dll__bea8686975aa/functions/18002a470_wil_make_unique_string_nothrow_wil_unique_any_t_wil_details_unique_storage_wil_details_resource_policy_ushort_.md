# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x18002a470`
- end: `0x18002a563`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `243`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002dd7c`

## callees

- `0x180004682`
- `0x180004708`
- `0x180005ee5`
- `0x18001b0d4`
- `0x18002a470`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002a516`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002a516`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002a4df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002a4df`

## string_xrefs

- `0x18002a551`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
_QWORD *__fastcall wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        _QWORD *a1,
        char *a2,
        unsigned __int64 a3,
        const char *a4)
{
  unsigned __int64 v4; // rbx
  __int64 v7; // rdi
  __int64 v8; // rax
  char *v9; // rdi
  _WORD *v10; // rax
  _WORD *v11; // rsi
  size_t v12; // rdi
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
0x18002a470  push    rbx
0x18002a472  push    rbp
0x18002a473  push    rsi
0x18002a474  push    rdi
0x18002a475  push    r12
0x18002a477  push    r14
0x18002a479  push    r15
0x18002a47b  sub     rsp, 20h
0x18002a47f  xor     r12d, r12d
0x18002a482  mov     rbx, r8
0x18002a485  mov     rbp, rdx
0x18002a488  mov     r15, rcx
0x18002a48b  test    rdx, rdx
0x18002a48e  jnz     short loc_18002A49F
0x18002a490  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18002a494  jz      loc_18002A54C
0x18002a49a  mov     rdi, rbx
0x18002a49d  jmp     short loc_18002A4D4
0x18002a49f  mov     ecx, 7FFFFFFFh
0x18002a4a4  mov     rax, rbx
0x18002a4a7  cmp     rbx, rcx
0x18002a4aa  mov     rdi, rbp
0x18002a4ad  cmovnb  rax, rcx
0x18002a4b1  test    rax, rax
0x18002a4b4  jz      short loc_18002A4C6
0x18002a4b6  cmp     [rdi], r12w
0x18002a4ba  jz      short loc_18002A4C6
0x18002a4bc  add     rdi, 2
0x18002a4c0  sub     rax, 1
0x18002a4c4  jnz     short loc_18002A4B6
0x18002a4c6  sub     rdi, rbp
0x18002a4c9  sar     rdi, 1
0x18002a4cc  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18002a4d0  cmovz   rbx, rdi
0x18002a4d4  lea     r14, ds:2[rbx*2]
0x18002a4dc  mov     rcx, r14; cb
0x18002a4df  call    cs:__imp_CoTaskMemAlloc
0x18002a4e5  mov     rsi, rax
0x18002a4e8  test    rax, rax
0x18002a4eb  jz      short loc_18002A537
0x18002a4ed  test    rbp, rbp
0x18002a4f0  jz      short loc_18002A52E
0x18002a4f2  add     rdi, rdi
0x18002a4f5  jz      short loc_18002A527
0x18002a4f7  mov     rcx, rax; void *
0x18002a4fa  cmp     r14, rdi
0x18002a4fd  jb      short loc_18002A50C
0x18002a4ff  mov     r8, rdi; Size
0x18002a502  mov     rdx, rbp; Src
0x18002a505  call    memcpy_0
0x18002a50a  jmp     short loc_18002A527
0x18002a50c  mov     r8, r14; Size
0x18002a50f  xor     edx, edx; Val
0x18002a511  call    memset_0
0x18002a516  call    cs:__imp__o__errno
0x18002a51c  mov     dword ptr [rax], 22h ; '"'
0x18002a522  call    _invalid_parameter_noinfo
0x18002a527  mov     [rdi+rsi], r12w
0x18002a52c  jmp     short loc_18002A532
0x18002a52e  mov     [rax], r12w
0x18002a532  mov     [rsi+rbx*2], r12w
0x18002a537  mov     [r15], rsi
0x18002a53a  mov     rax, r15
0x18002a53d  add     rsp, 20h
0x18002a541  pop     r15
0x18002a543  pop     r14
0x18002a545  pop     r12
0x18002a547  pop     rdi
0x18002a548  pop     rsi
0x18002a549  pop     rbp
0x18002a54a  pop     rbx
0x18002a54b  retn
0x18002a54c  mov     rcx, [rsp+58h]; this
0x18002a551  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002a558  mov     edx, 0F89h; void *
0x18002a55d  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
