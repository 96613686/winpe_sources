# wil::make_unique_hlocal_nothrow<_GUID [0]>(unsigned __int64)

- ea: `0x180004db0`
- end: `0x180004e20`
- name: `??$make_unique_hlocal_nothrow@$$BY0A@U_GUID@@@wil@@YA?AV?$unique_ptr@$$BY0A@U_GUID@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z`
- size: `112`
- prototype: `_QWORD *__fastcall(_QWORD *, unsigned __int64, __int64, const char *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004c2c`

## callees

- `0x180004db0`
- `0x180008258`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004def`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004def`

## string_xrefs

- `0x180004dd4`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
_QWORD *__fastcall wil::make_unique_hlocal_nothrow<_GUID [0]>(
        _QWORD *a1,
        unsigned __int64 a2,
        __int64 a3,
        const char *a4)
{
  __int64 v5; // rbx
  _OWORD *v6; // rax
  _OWORD *v7; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( a2 > 0xFFFFFFFFFFFFFFFLL )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x12CE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      a4);
  v5 = a2;
  v6 = LocalAlloc(0, 16 * a2);
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
0x180004db0  mov     [rsp+arg_0], rbx
0x180004db5  push    rdi
0x180004db6  sub     rsp, 20h
0x180004dba  mov     rax, 0FFFFFFFFFFFFFFFh
0x180004dc4  mov     rbx, rdx
0x180004dc7  mov     rdi, rcx
0x180004dca  cmp     rdx, rax
0x180004dcd  jbe     short loc_180004DE6
0x180004dcf  mov     rcx, [rsp+28h]; this
0x180004dd4  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180004ddb  mov     edx, 12CEh; void *
0x180004de0  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180004de6  shl     rbx, 4
0x180004dea  xor     ecx, ecx; uFlags
0x180004dec  mov     rdx, rbx; uBytes
0x180004def  call    cs:__imp_LocalAlloc
0x180004df5  mov     [rdi], rax
0x180004df8  test    rax, rax
0x180004dfb  jz      short loc_180004E12
0x180004dfd  lea     rcx, [rbx+rax]
0x180004e01  jmp     short loc_180004E0D
0x180004e03  xorps   xmm0, xmm0
0x180004e06  movups  xmmword ptr [rax], xmm0
0x180004e09  add     rax, 10h
0x180004e0d  cmp     rax, rcx
0x180004e10  jnz     short loc_180004E03
0x180004e12  mov     rbx, [rsp+28h+arg_0]
0x180004e17  mov     rax, rdi
0x180004e1a  add     rsp, 20h
0x180004e1e  pop     rdi
0x180004e1f  retn
```
