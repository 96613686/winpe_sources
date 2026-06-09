# wil::make_unique_cotaskmem_nothrow<CDPComActivityType [0]>(unsigned __int64)

- ea: `0x180026758`
- end: `0x1800267c5`
- name: `??$make_unique_cotaskmem_nothrow@$$BY0A@W4CDPComActivityType@@@wil@@YA?AV?$unique_ptr@$$BY0A@W4CDPComActivityType@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z`
- size: `109`
- prototype: `_QWORD *__fastcall(_QWORD *, unsigned __int64, __int64, const char *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180008fa0`

## callees

- `0x180026758`
- `0x180027418`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180026796`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180026796`

## string_xrefs

- `0x180026779`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
_QWORD *__fastcall wil::make_unique_cotaskmem_nothrow<enum CDPComActivityType [0]>(
        _QWORD *a1,
        unsigned __int64 a2,
        __int64 a3,
        const char *a4)
{
  __int64 v5; // rdi
  _DWORD *v6; // rax
  _DWORD *v7; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( a2 > 0x3FFFFFFFFFFFFFFFLL )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x1802,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
      a4);
  v5 = a2;
  v6 = CoTaskMemAlloc(4 * a2);
  *a1 = v6;
  if ( v6 )
  {
    v7 = &v6[v5];
    while ( v6 != v7 )
      *v6++ = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x180026758  mov     [rsp+arg_0], rbx
0x18002675d  push    rdi
0x18002675e  sub     rsp, 20h
0x180026762  mov     rax, 3FFFFFFFFFFFFFFFh
0x18002676c  mov     rbx, rcx
0x18002676f  cmp     rdx, rax
0x180026772  jbe     short loc_18002678B
0x180026774  mov     rcx, [rsp+28h]; this
0x180026779  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180026780  mov     edx, 1802h; void *
0x180026785  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18002678b  lea     rdi, ds:0[rdx*4]
0x180026793  mov     rcx, rdi; cb
0x180026796  call    cs:__imp_CoTaskMemAlloc
0x18002679c  mov     [rbx], rax
0x18002679f  test    rax, rax
0x1800267a2  jz      short loc_1800267B7
0x1800267a4  lea     rcx, [rdi+rax]
0x1800267a8  jmp     short loc_1800267B2
0x1800267aa  xor     edx, edx
0x1800267ac  mov     [rax], edx
0x1800267ae  add     rax, 4
0x1800267b2  cmp     rax, rcx
0x1800267b5  jnz     short loc_1800267AA
0x1800267b7  mov     rax, rbx
0x1800267ba  mov     rbx, [rsp+28h+arg_0]
0x1800267bf  add     rsp, 20h
0x1800267c3  pop     rdi
0x1800267c4  retn
```
