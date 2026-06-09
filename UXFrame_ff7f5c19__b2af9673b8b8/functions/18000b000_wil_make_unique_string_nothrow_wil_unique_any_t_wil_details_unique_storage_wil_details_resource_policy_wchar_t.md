# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(wchar_t const *,unsigned __int64)

- ea: `0x18000b000`
- end: `0x18000b0ce`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W_K@Z`
- size: `206`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800195b0`

## callees

- `0x18000b000`
- `0x18001049c`
- `0x18001d2dc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b082`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b082`

## string_xrefs

- `0x18000b02b`: `OneCore\Internal\Sdk\Inc\wil\opensource\wil\resource.h`

## pseudocode

```c
_QWORD *__fastcall wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(
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
        (unsigned int)"OneCore\\Internal\\Sdk\\Inc\\wil\\opensource\\wil\\resource.h",
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
0x18000b000  push    rbx
0x18000b002  push    rbp
0x18000b003  push    rsi
0x18000b004  push    rdi
0x18000b005  push    r12
0x18000b007  push    r14
0x18000b009  push    r15
0x18000b00b  sub     rsp, 20h
0x18000b00f  xor     r12d, r12d
0x18000b012  mov     rdi, r8
0x18000b015  mov     rbp, rdx
0x18000b018  mov     r14, rcx
0x18000b01b  test    rdx, rdx
0x18000b01e  jnz     short loc_18000B042
0x18000b020  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18000b024  jnz     short loc_18000B03D
0x18000b026  mov     rcx, [rsp+58h]; this
0x18000b02b  lea     r8, aOnecoreInterna_2; "OneCore\\Internal\\Sdk\\Inc\\wil\\opens"...
0x18000b032  mov     edx, 0F89h; void *
0x18000b037  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000b03d  mov     rbx, rdi
0x18000b040  jmp     short loc_18000B077
0x18000b042  mov     ecx, 7FFFFFFFh
0x18000b047  mov     rax, rdi
0x18000b04a  cmp     rdi, rcx
0x18000b04d  mov     rbx, rbp
0x18000b050  cmovnb  rax, rcx
0x18000b054  test    rax, rax
0x18000b057  jz      short loc_18000B069
0x18000b059  cmp     [rbx], r12w
0x18000b05d  jz      short loc_18000B069
0x18000b05f  add     rbx, 2
0x18000b063  sub     rax, 1
0x18000b067  jnz     short loc_18000B059
0x18000b069  sub     rbx, rbp
0x18000b06c  sar     rbx, 1
0x18000b06f  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18000b073  cmovz   rdi, rbx
0x18000b077  lea     r15, ds:2[rdi*2]
0x18000b07f  mov     rcx, r15; cb
0x18000b082  call    cs:__imp_CoTaskMemAlloc
0x18000b088  mov     rsi, rax
0x18000b08b  test    rax, rax
0x18000b08e  jz      short loc_18000B0B9
0x18000b090  test    rbp, rbp
0x18000b093  jz      short loc_18000B0B0
0x18000b095  add     rbx, rbx
0x18000b098  mov     r8, rbp; Source
0x18000b09b  mov     r9, rbx; SourceSize
0x18000b09e  mov     rdx, r15; DestinationSize
0x18000b0a1  mov     rcx, rax; Destination
0x18000b0a4  call    memcpy_s_0
0x18000b0a9  mov     [rbx+rsi], r12w
0x18000b0ae  jmp     short loc_18000B0B4
0x18000b0b0  mov     [rax], r12w
0x18000b0b4  mov     [rsi+rdi*2], r12w
0x18000b0b9  mov     [r14], rsi
0x18000b0bc  mov     rax, r14
0x18000b0bf  add     rsp, 20h
0x18000b0c3  pop     r15
0x18000b0c5  pop     r14
0x18000b0c7  pop     r12
0x18000b0c9  pop     rdi
0x18000b0ca  pop     rsi
0x18000b0cb  pop     rbp
0x18000b0cc  pop     rbx
0x18000b0cd  retn
```
