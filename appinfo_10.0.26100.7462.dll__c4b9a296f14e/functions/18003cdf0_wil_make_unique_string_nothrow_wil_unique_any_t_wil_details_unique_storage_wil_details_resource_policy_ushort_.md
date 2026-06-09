# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x18003cdf0`
- end: `0x18003cef1`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `257`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003df24`

## callees

- `0x18001ef78`
- `0x18003cdf0`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18003ce98`
- `msvcrt!memcpy_s` at `0x18003ce98`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003ce70`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003ce70`

## string_xrefs

- `0x18003cedf`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x18003cdf0  mov     rax, rsp
0x18003cdf3  mov     [rax+8], rbx
0x18003cdf7  mov     [rax+10h], rbp
0x18003cdfb  mov     [rax+18h], rsi
0x18003cdff  mov     [rax+20h], rdi
0x18003ce03  push    r12
0x18003ce05  push    r14
0x18003ce07  push    r15
0x18003ce09  sub     rsp, 20h
0x18003ce0d  xor     r12d, r12d
0x18003ce10  mov     rdi, r8
0x18003ce13  mov     rbp, rdx
0x18003ce16  mov     r14, rcx
0x18003ce19  test    rdx, rdx
0x18003ce1c  jnz     short loc_18003CE28
0x18003ce1e  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18003ce22  jz      loc_18003CEDA
0x18003ce28  mov     rbx, rdi
0x18003ce2b  test    rbp, rbp
0x18003ce2e  jz      short loc_18003CE5D
0x18003ce30  mov     ecx, 7FFFFFFFh
0x18003ce35  mov     rax, rdi
0x18003ce38  cmp     rdi, rcx
0x18003ce3b  mov     rbx, rbp
0x18003ce3e  cmovnb  rax, rcx
0x18003ce42  test    rax, rax
0x18003ce45  jz      short loc_18003CE57
0x18003ce47  cmp     [rbx], r12w
0x18003ce4b  jz      short loc_18003CE57
0x18003ce4d  add     rbx, 2
0x18003ce51  sub     rax, 1
0x18003ce55  jnz     short loc_18003CE47
0x18003ce57  sub     rbx, rbp
0x18003ce5a  sar     rbx, 1
0x18003ce5d  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18003ce61  cmovz   rdi, rbx
0x18003ce65  lea     r15, ds:2[rdi*2]
0x18003ce6d  mov     rcx, r15; cb
0x18003ce70  call    cs:__imp_CoTaskMemAlloc
0x18003ce77  nop     dword ptr [rax+rax+00h]
0x18003ce7c  mov     rsi, rax
0x18003ce7f  test    rax, rax
0x18003ce82  jz      short loc_18003CEB4
0x18003ce84  test    rbp, rbp
0x18003ce87  jz      short loc_18003CEAB
0x18003ce89  add     rbx, rbx
0x18003ce8c  mov     r8, rbp; Source
0x18003ce8f  mov     r9, rbx; SourceSize
0x18003ce92  mov     rdx, r15; DestinationSize
0x18003ce95  mov     rcx, rax; Destination
0x18003ce98  call    cs:__imp_memcpy_s
0x18003ce9f  nop     dword ptr [rax+rax+00h]
0x18003cea4  mov     [rbx+rsi], r12w
0x18003cea9  jmp     short loc_18003CEAF
0x18003ceab  mov     [rax], r12w
0x18003ceaf  mov     [rsi+rdi*2], r12w
0x18003ceb4  mov     rbx, [rsp+38h+arg_0]
0x18003ceb9  mov     rax, r14
0x18003cebc  mov     rbp, [rsp+38h+arg_8]
0x18003cec1  mov     rdi, [rsp+38h+arg_18]
0x18003cec6  mov     [r14], rsi
0x18003cec9  mov     rsi, [rsp+38h+arg_10]
0x18003cece  add     rsp, 20h
0x18003ced2  pop     r15
0x18003ced4  pop     r14
0x18003ced6  pop     r12
0x18003ced8  retn
0x18003ceda  mov     rcx, [rsp+38h]; this
0x18003cedf  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003cee6  mov     edx, 0DBFh; void *
0x18003ceeb  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
