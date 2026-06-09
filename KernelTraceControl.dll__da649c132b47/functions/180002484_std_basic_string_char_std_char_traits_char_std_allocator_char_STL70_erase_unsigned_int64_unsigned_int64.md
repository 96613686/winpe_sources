# std::basic_string<char,std::char_traits<char>,std::allocator<char>,_STL70>::erase(unsigned __int64,unsigned __int64)

- ea: `0x180002484`
- end: `0x18000252b`
- name: `?erase@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@QEAAAEAV12@_K0@Z`
- size: `167`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002720`

## callees

- `0x180002484`
- `0x1800276c0`

## import_xrefs

- `msvcrt!memmove_s` at `0x1800024f4`
- `msvcrt!memmove_s` at `0x1800024f4`

## pseudocode

```c
_QWORD *__fastcall std::string::erase(_QWORD *a1, unsigned __int64 a2, unsigned __int64 a3)
{
  unsigned __int64 v3; // rsi
  unsigned __int64 v6; // r9
  unsigned __int64 v7; // rdx
  _QWORD *v8; // rbx
  _QWORD *v9; // rcx
  _QWORD *v10; // rax
  unsigned __int64 v11; // rax
  bool v12; // cf

  v3 = a3;
  if ( a1[3] < a2 )
    std::_String_base::_Xran();
  v6 = a1[3] - a2;
  if ( v6 < a3 )
    v3 = a1[3] - a2;
  if ( v3 )
  {
    v7 = a1[4];
    v8 = a1 + 1;
    if ( v7 < 0x10 )
      v9 = a1 + 1;
    else
      v9 = (_QWORD *)*v8;
    if ( v7 < 0x10 )
      v10 = a1 + 1;
    else
      v10 = (_QWORD *)*v8;
    memmove_s((char *)v10 + a2, v7 - a2, (char *)v9 + a2 + v3, v6 - v3);
    v11 = a1[3] - v3;
    v12 = a1[4] < 0x10u;
    a1[3] = v11;
    if ( !v12 )
      v8 = (_QWORD *)*v8;
    *((_BYTE *)v8 + v11) = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x180002484  mov     [rsp+arg_0], rbx
0x180002489  mov     [rsp+arg_8], rbp
0x18000248e  mov     [rsp+arg_10], rsi
0x180002493  push    rdi
0x180002494  sub     rsp, 20h
0x180002498  mov     rsi, r8
0x18000249b  mov     rbp, rdx
0x18000249e  mov     rdi, rcx
0x1800024a1  cmp     [rcx+18h], rdx
0x1800024a5  jnb     short loc_1800024AC
0x1800024a7  call    ?_Xran@_String_base@std@@SAXXZ
0x1800024ac  mov     r9, [rdi+18h]
0x1800024b0  sub     r9, rbp
0x1800024b3  cmp     r9, rsi
0x1800024b6  cmovb   rsi, r9
0x1800024ba  test    rsi, rsi
0x1800024bd  jz      short loc_180002513
0x1800024bf  mov     rdx, [rdi+20h]
0x1800024c3  lea     rbx, [rdi+8]
0x1800024c7  cmp     rdx, 10h
0x1800024cb  jb      short loc_1800024D2
0x1800024cd  mov     rcx, [rbx]
0x1800024d0  jmp     short loc_1800024D5
0x1800024d2  mov     rcx, rbx
0x1800024d5  cmp     rdx, 10h
0x1800024d9  jb      short loc_1800024E0
0x1800024db  mov     rax, [rbx]
0x1800024de  jmp     short loc_1800024E3
0x1800024e0  mov     rax, rbx
0x1800024e3  lea     r8, [rcx+rbp]
0x1800024e7  sub     r9, rsi; SourceSize
0x1800024ea  add     r8, rsi; Source
0x1800024ed  lea     rcx, [rax+rbp]; Destination
0x1800024f1  sub     rdx, rbp; DestinationSize
0x1800024f4  call    cs:__imp_memmove_s
0x1800024fa  mov     rax, [rdi+18h]
0x1800024fe  sub     rax, rsi
0x180002501  cmp     qword ptr [rdi+20h], 10h
0x180002506  mov     [rdi+18h], rax
0x18000250a  jb      short loc_18000250F
0x18000250c  mov     rbx, [rbx]
0x18000250f  mov     byte ptr [rbx+rax], 0
0x180002513  mov     rbx, [rsp+28h+arg_0]
0x180002518  mov     rax, rdi
0x18000251b  mov     rbp, [rsp+28h+arg_8]
0x180002520  mov     rsi, [rsp+28h+arg_10]
0x180002525  add     rsp, 20h
0x180002529  pop     rdi
0x18000252a  retn
```
