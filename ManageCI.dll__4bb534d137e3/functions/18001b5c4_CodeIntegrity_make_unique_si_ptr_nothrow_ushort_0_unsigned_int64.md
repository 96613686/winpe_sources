# CodeIntegrity::make_unique_si_ptr_nothrow<ushort * [0]>(unsigned __int64)

- ea: `0x18001b5c4`
- end: `0x18001b636`
- name: `??$make_unique_si_ptr_nothrow@$$BY0A@PEAG@CodeIntegrity@@YA?AV?$unique_ptr@$$BY0A@PEAGU?$function_deleter@P6AXPEAX@Z$1?SIPolicyFree@@YAX0@Z@wil@@@wistd@@_K@Z`
- size: `114`
- prototype: `_QWORD *__fastcall(_QWORD *, unsigned __int64, __int64, const char *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001b524`

## callees

- `0x180008258`
- `0x18001b5c4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001b606`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001b606`

## string_xrefs

- `0x18001b5e8`: `onecore\base\ci\management\dll\smartsi.h`

## pseudocode

```c
_QWORD *__fastcall CodeIntegrity::make_unique_si_ptr_nothrow<unsigned short * [0]>(
        _QWORD *a1,
        unsigned __int64 a2,
        __int64 a3,
        const char *a4)
{
  _QWORD *v6; // rax
  _QWORD *v7; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( a2 > 0x1FFFFFFFFFFFFFFFLL )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x36,
      (unsigned int)"onecore\\base\\ci\\management\\dll\\smartsi.h",
      a4);
  v6 = LocalAlloc(0x40u, (unsigned int)(8 * a2));
  *a1 = v6;
  if ( v6 )
  {
    v7 = &v6[a2];
    while ( v6 != v7 )
      *v6++ = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x18001b5c4  mov     [rsp+arg_0], rbx
0x18001b5c9  push    rdi
0x18001b5ca  sub     rsp, 20h
0x18001b5ce  mov     rax, 1FFFFFFFFFFFFFFFh
0x18001b5d8  mov     rbx, rdx
0x18001b5db  mov     rdi, rcx
0x18001b5de  cmp     rdx, rax
0x18001b5e1  jbe     short loc_18001B5FA
0x18001b5e3  mov     rcx, [rsp+28h]; this
0x18001b5e8  lea     r8, aOnecoreBaseCiM_6; "onecore\\base\\ci\\management\\dll\\sma"...
0x18001b5ef  mov     edx, 36h ; '6'; void *
0x18001b5f4  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18001b5fa  lea     edx, ds:0[rdx*8]; uBytes
0x18001b601  mov     ecx, 40h ; '@'; uFlags
0x18001b606  call    cs:__imp_LocalAlloc
0x18001b60c  mov     [rdi], rax
0x18001b60f  test    rax, rax
0x18001b612  jz      short loc_18001B628
0x18001b614  lea     rcx, [rax+rbx*8]
0x18001b618  jmp     short loc_18001B623
0x18001b61a  xor     edx, edx
0x18001b61c  mov     [rax], rdx
0x18001b61f  add     rax, 8
0x18001b623  cmp     rax, rcx
0x18001b626  jnz     short loc_18001B61A
0x18001b628  mov     rbx, [rsp+28h+arg_0]
0x18001b62d  mov     rax, rdi
0x18001b630  add     rsp, 20h
0x18001b634  pop     rdi
0x18001b635  retn
```
