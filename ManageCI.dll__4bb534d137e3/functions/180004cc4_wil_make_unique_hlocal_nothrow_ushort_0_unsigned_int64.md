# wil::make_unique_hlocal_nothrow<ushort [0]>(unsigned __int64)

- ea: `0x180004cc4`
- end: `0x180004d30`
- name: `??$make_unique_hlocal_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z`
- size: `108`
- prototype: `_QWORD *__fastcall(_QWORD *, unsigned __int64, __int64, const char *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004b8c`

## callees

- `0x180004cc4`
- `0x180008258`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004d00`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004d00`

## string_xrefs

- `0x180004ce5`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
_QWORD *__fastcall wil::make_unique_hlocal_nothrow<unsigned short [0]>(
        _QWORD *a1,
        unsigned __int64 a2,
        __int64 a3,
        const char *a4)
{
  __int64 v5; // rdi
  _WORD *v6; // rax
  _WORD *v7; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( a2 > 0x7FFFFFFFFFFFFFFFLL )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x12CE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      a4);
  v5 = a2;
  v6 = LocalAlloc(0, 2 * a2);
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
0x180004cc4  mov     [rsp+arg_0], rbx
0x180004cc9  push    rdi
0x180004cca  sub     rsp, 20h
0x180004cce  mov     rax, 7FFFFFFFFFFFFFFFh
0x180004cd8  mov     rbx, rcx
0x180004cdb  cmp     rdx, rax
0x180004cde  jbe     short loc_180004CF7
0x180004ce0  mov     rcx, [rsp+28h]; this
0x180004ce5  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180004cec  mov     edx, 12CEh; void *
0x180004cf1  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180004cf7  lea     rdi, [rdx+rdx]
0x180004cfb  xor     ecx, ecx; uFlags
0x180004cfd  mov     rdx, rdi; uBytes
0x180004d00  call    cs:__imp_LocalAlloc
0x180004d06  mov     [rbx], rax
0x180004d09  test    rax, rax
0x180004d0c  jz      short loc_180004D22
0x180004d0e  lea     rcx, [rdi+rax]
0x180004d12  jmp     short loc_180004D1D
0x180004d14  xor     edx, edx
0x180004d16  mov     [rax], dx
0x180004d19  add     rax, 2
0x180004d1d  cmp     rax, rcx
0x180004d20  jnz     short loc_180004D14
0x180004d22  mov     rax, rbx
0x180004d25  mov     rbx, [rsp+28h+arg_0]
0x180004d2a  add     rsp, 20h
0x180004d2e  pop     rdi
0x180004d2f  retn
```
