# std::_Tree_temp_node<std::allocator<std::_Tree_node<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,void *>>>::_Tree_temp_node<std::allocator<std::_Tree_node<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,void *>>>(std::allocator<std::_Tree_node<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,void *>> &,std::_Tree_node<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,void *> *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &&)

- ea: `0x18001af50`
- end: `0x18001b002`
- name: `??$?0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Tree_temp_node@V?$allocator@U?$_Tree_node@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAX@std@@@std@@@std@@QEAA@AEAV?$allocator@U?$_Tree_node@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAX@std@@@1@PEAU?$_Tree_node@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAX@1@$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z`
- size: `178`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18001a86c`
- `0x18001ab10`

## callees

- `0x18000ab0c`
- `0x18001af50`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18001af7d`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18001af7d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall std::_Tree_temp_node<std::allocator<std::_Tree_node<std::wstring,void *>>>::_Tree_temp_node<std::allocator<std::_Tree_node<std::wstring,void *>>>(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  _OWORD *v7; // rax
  __int64 i; // rcx

  *a1 = a2;
  a1[1] = 0;
  v7 = malloc(0x40u);
  if ( !v7 )
    std::_Xbad_alloc();
  a1[1] = v7;
  v7[2] = 0;
  *((_QWORD *)v7 + 6) = 0;
  *((_QWORD *)v7 + 7) = 0;
  v7[2] = *(_OWORD *)a4;
  v7[3] = *(_OWORD *)(a4 + 16);
  *(_WORD *)a4 = 0;
  *(_QWORD *)(a4 + 16) = 0;
  *(_QWORD *)(a4 + 24) = 7;
  *(_QWORD *)a1[1] = a3;
  *(_QWORD *)(a1[1] + 8LL) = a3;
  *(_QWORD *)(a1[1] + 16LL) = a3;
  for ( i = 0; i < 2; ++i )
    *(_BYTE *)(a1[1] + i + 24) = 0;
  return a1;
}

```

## disassembly

```asm
0x18001af50  mov     rax, rsp
0x18001af53  mov     [rax+10h], rbx
0x18001af57  mov     [rax+18h], rbp
0x18001af5b  mov     [rax+20h], rsi
0x18001af5f  mov     [rax+8], rcx
0x18001af63  push    rdi
0x18001af64  sub     rsp, 20h
0x18001af68  mov     rdi, r9
0x18001af6b  mov     rsi, r8
0x18001af6e  mov     rbx, rcx
0x18001af71  mov     [rcx], rdx
0x18001af74  xor     ebp, ebp
0x18001af76  mov     [rcx+8], rbp
0x18001af7a  lea     ecx, [rbp+40h]; Size
0x18001af7d  call    cs:__imp_malloc
0x18001af83  test    rax, rax
0x18001af86  jz      short loc_18001AFFC
0x18001af88  mov     [rbx+8], rax
0x18001af8c  xorps   xmm0, xmm0
0x18001af8f  movups  xmmword ptr [rax+20h], xmm0
0x18001af93  mov     [rax+30h], rbp
0x18001af97  mov     [rax+38h], rbp
0x18001af9b  movups  xmm0, xmmword ptr [rdi]
0x18001af9e  movups  xmmword ptr [rax+20h], xmm0
0x18001afa2  movups  xmm1, xmmword ptr [rdi+10h]
0x18001afa6  movups  xmmword ptr [rax+30h], xmm1
0x18001afaa  mov     [rdi], bp
0x18001afad  mov     [rdi+10h], rbp
0x18001afb1  mov     qword ptr [rdi+18h], 7
0x18001afb9  mov     rax, [rbx+8]
0x18001afbd  mov     [rax], rsi
0x18001afc0  mov     rax, [rbx+8]
0x18001afc4  mov     [rax+8], rsi
0x18001afc8  mov     rax, [rbx+8]
0x18001afcc  mov     [rax+10h], rsi
0x18001afd0  mov     ecx, ebp
0x18001afd2  mov     rax, [rbx+8]
0x18001afd6  mov     [rax+rcx+18h], bpl
0x18001afdb  inc     rcx
0x18001afde  cmp     rcx, 2
0x18001afe2  jl      short loc_18001AFD2
0x18001afe4  mov     rax, rbx
0x18001afe7  mov     rbx, [rsp+28h+arg_8]
0x18001afec  mov     rbp, [rsp+28h+arg_10]
0x18001aff1  mov     rsi, [rsp+28h+arg_18]
0x18001aff6  add     rsp, 20h
0x18001affa  pop     rdi
0x18001affb  retn
0x18001affc  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
