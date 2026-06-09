# std::basic_string<char,std::char_traits<char>,std::allocator_static<char>,_STL70>::basic_string<char,std::char_traits<char>,std::allocator_static<char>,_STL70>(char const *)

- ea: `0x180002d0c`
- end: `0x180002dbc`
- name: `??0?$basic_string@DU?$char_traits@D@std@@V?$allocator_static@D@2@V_STL70@@@std@@QEAA@PEBD@Z`
- size: `176`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180006834`
- `0x180007988`
- `0x18000a840`

## callees

- `0x180001434`
- `0x180002d0c`
- `0x18000b11c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180002d98`
- `msvcrt!memcpy_s` at `0x180002d98`

## pseudocode

```c
__int64 __fastcall std::basic_string<char,std::char_traits<char>,std::allocator_static<char>,_STL70>::basic_string<char,std::char_traits<char>,std::allocator_static<char>,_STL70>(
        __int64 a1,
        _BYTE *a2)
{
  void **v2; // rsi
  unsigned __int64 v5; // rbx
  rsize_t v6; // rdx
  void *v7; // rcx

  v2 = (void **)(a1 + 8);
  *(_QWORD *)(a1 + 32) = 15;
  *(_QWORD *)(a1 + 24) = 0;
  *(_BYTE *)(a1 + 8) = 0;
  v5 = -1;
  do
    ++v5;
  while ( a2[v5] );
  if ( v5 == -1 )
    std::_String_base::_Xlen();
  if ( *(_QWORD *)(a1 + 32) < v5 )
  {
    std::string::_Copy(a1, v5, *(_QWORD *)(a1 + 24));
    if ( !v5 )
      return a1;
    goto LABEL_7;
  }
  if ( v5 )
  {
LABEL_7:
    v6 = *(_QWORD *)(a1 + 32);
    if ( v6 < 0x10 )
      v7 = v2;
    else
      v7 = *v2;
    memcpy_s(v7, v6, a2, v5);
    if ( *(_QWORD *)(a1 + 32) >= 0x10u )
      v2 = (void **)*v2;
    *(_QWORD *)(a1 + 24) = v5;
    *((_BYTE *)v2 + v5) = 0;
    return a1;
  }
  if ( *(_QWORD *)(a1 + 32) >= 0x10u )
    v2 = (void **)*v2;
  *(_QWORD *)(a1 + 24) = 0;
  *(_BYTE *)v2 = 0;
  return a1;
}

```

## disassembly

```asm
0x180002d0c  push    rbx
0x180002d0e  push    rbp
0x180002d0f  push    rsi
0x180002d10  push    rdi
0x180002d11  sub     rsp, 28h
0x180002d15  lea     rsi, [rcx+8]
0x180002d19  mov     qword ptr [rcx+20h], 0Fh
0x180002d21  mov     qword ptr [rcx+18h], 0
0x180002d29  mov     rbp, rdx
0x180002d2c  mov     byte ptr [rsi], 0
0x180002d2f  mov     rdi, rcx
0x180002d32  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180002d36  inc     rbx
0x180002d39  cmp     byte ptr [rbx+rdx], 0
0x180002d3d  jnz     short loc_180002D36
0x180002d3f  cmp     rbx, 0FFFFFFFFFFFFFFFEh
0x180002d43  jbe     short loc_180002D4A
0x180002d45  call    ?_Xlen@_String_base@std@@SAXXZ; std::_String_base::_Xlen(void)
0x180002d4a  cmp     [rdi+20h], rbx
0x180002d4e  jnb     short loc_180002D73
0x180002d50  mov     r8, [rdi+18h]
0x180002d54  mov     rdx, rbx
0x180002d57  mov     rcx, rdi
0x180002d5a  call    ?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@IEAAX_K0@Z; std::string::_Copy(unsigned __int64,unsigned __int64)
0x180002d5f  test    rbx, rbx
0x180002d62  jz      short loc_180002DB0
0x180002d64  mov     rdx, [rdi+20h]; DestinationSize
0x180002d68  cmp     rdx, 10h
0x180002d6c  jb      short loc_180002D8F
0x180002d6e  mov     rcx, [rsi]
0x180002d71  jmp     short loc_180002D92
0x180002d73  test    rbx, rbx
0x180002d76  jnz     short loc_180002D64
0x180002d78  cmp     qword ptr [rdi+20h], 10h
0x180002d7d  jb      short loc_180002D82
0x180002d7f  mov     rsi, [rsi]
0x180002d82  mov     qword ptr [rdi+18h], 0
0x180002d8a  mov     byte ptr [rsi], 0
0x180002d8d  jmp     short loc_180002DB0
0x180002d8f  mov     rcx, rsi; Destination
0x180002d92  mov     r9, rbx; SourceSize
0x180002d95  mov     r8, rbp; Source
0x180002d98  call    cs:__imp_memcpy_s
0x180002d9e  cmp     qword ptr [rdi+20h], 10h
0x180002da3  jb      short loc_180002DA8
0x180002da5  mov     rsi, [rsi]
0x180002da8  mov     [rdi+18h], rbx
0x180002dac  mov     byte ptr [rsi+rbx], 0
0x180002db0  mov     rax, rdi
0x180002db3  add     rsp, 28h
0x180002db7  pop     rdi
0x180002db8  pop     rsi
0x180002db9  pop     rbp
0x180002dba  pop     rbx
0x180002dbb  retn
```
