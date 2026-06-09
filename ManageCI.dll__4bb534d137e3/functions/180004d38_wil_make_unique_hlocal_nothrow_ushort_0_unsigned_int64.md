# wil::make_unique_hlocal_nothrow<ushort * [0]>(unsigned __int64)

- ea: `0x180004d38`
- end: `0x180004da8`
- name: `??$make_unique_hlocal_nothrow@$$BY0A@PEAG@wil@@YA?AV?$unique_ptr@$$BY0A@PEAGU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z`
- size: `112`
- prototype: `_QWORD *__fastcall(_QWORD *, unsigned __int64, __int64, const char *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004bdc`

## callees

- `0x180004d38`
- `0x180008258`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004d78`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004d78`

## string_xrefs

- `0x180004d59`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
_QWORD *__fastcall wil::make_unique_hlocal_nothrow<unsigned short * [0]>(
        _QWORD *a1,
        unsigned __int64 a2,
        __int64 a3,
        const char *a4)
{
  __int64 v5; // rdi
  _QWORD *v6; // rax
  _QWORD *v7; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( a2 > 0x1FFFFFFFFFFFFFFFLL )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x12CE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      a4);
  v5 = a2;
  v6 = LocalAlloc(0, 8 * a2);
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
0x180004d38  mov     [rsp+arg_0], rbx
0x180004d3d  push    rdi
0x180004d3e  sub     rsp, 20h
0x180004d42  mov     rax, 1FFFFFFFFFFFFFFFh
0x180004d4c  mov     rbx, rcx
0x180004d4f  cmp     rdx, rax
0x180004d52  jbe     short loc_180004D6B
0x180004d54  mov     rcx, [rsp+28h]; this
0x180004d59  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180004d60  mov     edx, 12CEh; void *
0x180004d65  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180004d6b  lea     rdi, ds:0[rdx*8]
0x180004d73  xor     ecx, ecx; uFlags
0x180004d75  mov     rdx, rdi; uBytes
0x180004d78  call    cs:__imp_LocalAlloc
0x180004d7e  mov     [rbx], rax
0x180004d81  test    rax, rax
0x180004d84  jz      short loc_180004D9A
0x180004d86  lea     rcx, [rdi+rax]
0x180004d8a  jmp     short loc_180004D95
0x180004d8c  xor     edx, edx
0x180004d8e  mov     [rax], rdx
0x180004d91  add     rax, 8
0x180004d95  cmp     rax, rcx
0x180004d98  jnz     short loc_180004D8C
0x180004d9a  mov     rax, rbx
0x180004d9d  mov     rbx, [rsp+28h+arg_0]
0x180004da2  add     rsp, 20h
0x180004da6  pop     rdi
0x180004da7  retn
```
