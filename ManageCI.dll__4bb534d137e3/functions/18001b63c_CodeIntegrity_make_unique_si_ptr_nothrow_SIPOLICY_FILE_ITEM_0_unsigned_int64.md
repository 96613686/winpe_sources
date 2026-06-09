# CodeIntegrity::make_unique_si_ptr_nothrow<_SIPOLICY_FILE_ITEM [0]>(unsigned __int64)

- ea: `0x18001b63c`
- end: `0x18001b6b8`
- name: `??$make_unique_si_ptr_nothrow@$$BY0A@U_SIPOLICY_FILE_ITEM@@@CodeIntegrity@@YA?AV?$unique_ptr@$$BY0A@U_SIPOLICY_FILE_ITEM@@U?$function_deleter@P6AXPEAX@Z$1?SIPolicyFree@@YAX0@Z@wil@@@wistd@@_K@Z`
- size: `124`
- prototype: `char **__fastcall(char **, unsigned __int64, __int64, const char *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001b574`

## callees

- `0x180008258`
- `0x18001b63c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001b67d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001b67d`

## string_xrefs

- `0x18001b660`: `onecore\base\ci\management\dll\smartsi.h`

## pseudocode

```c
char **__fastcall CodeIntegrity::make_unique_si_ptr_nothrow<_SIPOLICY_FILE_ITEM [0]>(
        char **a1,
        unsigned __int64 a2,
        __int64 a3,
        const char *a4)
{
  char *v6; // rax
  char *v7; // rdx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( a2 > 0xAAAAAAAAAAAAAAALL )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x36,
      (unsigned int)"onecore\\base\\ci\\management\\dll\\smartsi.h",
      a4);
  v6 = (char *)LocalAlloc(0x40u, (unsigned int)(24 * a2));
  *a1 = v6;
  if ( v6 )
  {
    v7 = &v6[24 * a2];
    while ( v6 != v7 )
    {
      *(_OWORD *)v6 = 0;
      *((_QWORD *)v6 + 2) = 0;
      v6 += 24;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x18001b63c  mov     [rsp+arg_0], rbx
0x18001b641  push    rdi
0x18001b642  sub     rsp, 20h
0x18001b646  mov     rax, 0AAAAAAAAAAAAAAAh
0x18001b650  mov     rbx, rdx
0x18001b653  mov     rdi, rcx
0x18001b656  cmp     rdx, rax
0x18001b659  jbe     short loc_18001B672
0x18001b65b  mov     rcx, [rsp+28h]; this
0x18001b660  lea     r8, aOnecoreBaseCiM_6; "onecore\\base\\ci\\management\\dll\\sma"...
0x18001b667  mov     edx, 36h ; '6'; void *
0x18001b66c  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18001b672  lea     edx, [rdx+rdx*2]
0x18001b675  mov     ecx, 40h ; '@'; uFlags
0x18001b67a  shl     edx, 3; uBytes
0x18001b67d  call    cs:__imp_LocalAlloc
0x18001b683  mov     [rdi], rax
0x18001b686  test    rax, rax
0x18001b689  jz      short loc_18001B6AA
0x18001b68b  lea     rcx, [rbx+rbx*2]
0x18001b68f  lea     rdx, [rax+rcx*8]
0x18001b693  jmp     short loc_18001B6A5
0x18001b695  xor     ecx, ecx
0x18001b697  xorps   xmm0, xmm0
0x18001b69a  movups  xmmword ptr [rax], xmm0
0x18001b69d  mov     [rax+10h], rcx
0x18001b6a1  add     rax, 18h
0x18001b6a5  cmp     rax, rdx
0x18001b6a8  jnz     short loc_18001B695
0x18001b6aa  mov     rbx, [rsp+28h+arg_0]
0x18001b6af  mov     rax, rdi
0x18001b6b2  add     rsp, 20h
0x18001b6b6  pop     rdi
0x18001b6b7  retn
```
