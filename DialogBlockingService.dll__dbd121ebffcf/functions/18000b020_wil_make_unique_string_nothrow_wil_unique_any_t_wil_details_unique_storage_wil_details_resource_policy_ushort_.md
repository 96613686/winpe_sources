# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x18000b020`
- end: `0x18000b0e6`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `198`
- prototype: `_QWORD *__fastcall(_QWORD *, char *, unsigned __int64, const char *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000ad54`
- `0x18000b680`

## callees

- `0x1800020ac`
- `0x18000952c`
- `0x18000b020`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b08f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b08f`

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
      wil::details::in1diag3::_FailFast_Unexpected(retaddr, 0, 0xFFFFFFFF, a4);
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
0x18000b020  push    rbx
0x18000b022  push    rbp
0x18000b023  push    rsi
0x18000b024  push    rdi
0x18000b025  push    r12
0x18000b027  push    r14
0x18000b029  push    r15
0x18000b02b  sub     rsp, 20h
0x18000b02f  xor     r12d, r12d
0x18000b032  mov     rdi, r8
0x18000b035  mov     rbp, rdx
0x18000b038  mov     r14, rcx
0x18000b03b  test    rdx, rdx
0x18000b03e  jnz     short loc_18000B04F
0x18000b040  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18000b044  jz      loc_18000B0DB
0x18000b04a  mov     rbx, r8
0x18000b04d  jmp     short loc_18000B084
0x18000b04f  mov     ecx, 7FFFFFFFh
0x18000b054  mov     rax, rdi
0x18000b057  cmp     rdi, rcx
0x18000b05a  mov     rbx, rbp
0x18000b05d  cmovnb  rax, rcx
0x18000b061  test    rax, rax
0x18000b064  jz      short loc_18000B076
0x18000b066  cmp     [rbx], r12w
0x18000b06a  jz      short loc_18000B076
0x18000b06c  add     rbx, 2
0x18000b070  sub     rax, 1
0x18000b074  jnz     short loc_18000B066
0x18000b076  sub     rbx, rbp
0x18000b079  sar     rbx, 1
0x18000b07c  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18000b080  cmovz   rdi, rbx
0x18000b084  lea     r15, ds:2[rdi*2]
0x18000b08c  mov     rcx, r15; cb
0x18000b08f  call    cs:__imp_CoTaskMemAlloc
0x18000b095  mov     rsi, rax
0x18000b098  test    rax, rax
0x18000b09b  jz      short loc_18000B0C6
0x18000b09d  test    rbp, rbp
0x18000b0a0  jz      short loc_18000B0BD
0x18000b0a2  add     rbx, rbx
0x18000b0a5  mov     r8, rbp; Source
0x18000b0a8  mov     r9, rbx; SourceSize
0x18000b0ab  mov     rdx, r15; DestinationSize
0x18000b0ae  mov     rcx, rax; Destination
0x18000b0b1  call    memcpy_s
0x18000b0b6  mov     [rbx+rsi], r12w
0x18000b0bb  jmp     short loc_18000B0C1
0x18000b0bd  mov     [rax], r12w
0x18000b0c1  mov     [rsi+rdi*2], r12w
0x18000b0c6  mov     [r14], rsi
0x18000b0c9  mov     rax, r14
0x18000b0cc  add     rsp, 20h
0x18000b0d0  pop     r15
0x18000b0d2  pop     r14
0x18000b0d4  pop     r12
0x18000b0d6  pop     rdi
0x18000b0d7  pop     rsi
0x18000b0d8  pop     rbp
0x18000b0d9  pop     rbx
0x18000b0da  retn
0x18000b0db  mov     rcx, [rsp+58h]; this
0x18000b0e0  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
