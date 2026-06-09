# std::_Hash<std::_Uset_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,0>>::erase(std::_List_const_iterator<std::_List_val<std::_List_simple_types<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>>)

- ea: `0x18000d0f0`
- end: `0x18000d206`
- name: `?erase@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@2@V32@@Z`
- size: `278`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *, void **)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180022057`
- `0x180022aa9`

## callees

- `0x18000d0f0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000d1cd`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000d1eb`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000d1cd`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000d1eb`

## pseudocode

```c
_QWORD *__fastcall std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::erase(
        _QWORD *a1,
        _QWORD *a2,
        void **a3)
{
  void **v3; // rdi
  unsigned __int64 v6; // rcx
  unsigned __int8 *v8; // r9
  unsigned __int64 v9; // rdx
  unsigned __int64 i; // r8
  __int64 v11; // rax
  unsigned __int64 v12; // rax
  unsigned __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rdx
  void *v16; // rax
  void *v17; // rbp

  v3 = a3 + 2;
  v6 = 2LL * (_QWORD)a3[4];
  if ( (unsigned __int64)a3[5] < 8 )
    v8 = (unsigned __int8 *)(a3 + 2);
  else
    v8 = (unsigned __int8 *)*v3;
  v9 = 0;
  for ( i = 0xCBF29CE484222325uLL; v9 < v6; i = 0x100000001B3LL * (v11 ^ i) )
    v11 = v8[v9++];
  v12 = a1[5];
  v13 = v12 & (i ^ HIDWORD(i));
  if ( a1[6] <= v13 )
    v13 = v13 - (v12 >> 1) - 1;
  v14 = a1[2];
  v15 = 2 * v13;
  if ( *(void ***)(v14 + 8 * v15 + 8) == a3 )
  {
    if ( *(void ***)(v14 + 8 * v15) == a3 )
    {
      *(_QWORD *)(v14 + 8 * v15) = *a1;
      v14 = a1[2];
      v16 = (void *)*a1;
    }
    else
    {
      v16 = a3[1];
    }
    *(_QWORD *)(v14 + 8 * v15 + 8) = v16;
  }
  else if ( *(void ***)(v14 + 8 * v15) == a3 )
  {
    *(_QWORD *)(v14 + 8 * v15) = *a3;
  }
  v17 = *a3;
  if ( a3 != (void **)*a1 )
  {
    *(_QWORD *)a3[1] = v17;
    *((_QWORD *)*a3 + 1) = a3[1];
    if ( (unsigned __int64)v3[3] >= 8 )
      operator delete(*v3);
    v3[3] = (void *)7;
    v3[2] = 0;
    *(_WORD *)v3 = 0;
    operator delete(a3);
    --a1[1];
  }
  *a2 = v17;
  return a2;
}

```

## disassembly

```asm
0x18000d0f0  push    rbx
0x18000d0f2  push    rbp
0x18000d0f3  push    rsi
0x18000d0f4  push    rdi
0x18000d0f5  push    r14
0x18000d0f7  sub     rsp, 20h
0x18000d0fb  lea     rdi, [r8+10h]
0x18000d0ff  mov     rsi, rcx
0x18000d102  mov     rcx, [rdi+10h]
0x18000d106  mov     rbx, r8
0x18000d109  add     rcx, rcx
0x18000d10c  mov     r14, rdx
0x18000d10f  cmp     qword ptr [rdi+18h], 8
0x18000d114  jb      short loc_18000D11B
0x18000d116  mov     r9, [rdi]
0x18000d119  jmp     short loc_18000D11E
0x18000d11b  mov     r9, rdi
0x18000d11e  xor     edx, edx
0x18000d120  mov     r8, 0CBF29CE484222325h
0x18000d12a  test    rcx, rcx
0x18000d12d  jz      short loc_18000D14D
0x18000d12f  movzx   eax, byte ptr [r9+rdx]
0x18000d134  mov     r10, 100000001B3h
0x18000d13e  xor     r8, rax
0x18000d141  inc     rdx
0x18000d144  imul    r8, r10
0x18000d148  cmp     rdx, rcx
0x18000d14b  jb      short loc_18000D12F
0x18000d14d  mov     rax, [rsi+28h]
0x18000d151  mov     rdx, r8
0x18000d154  shr     rdx, 20h
0x18000d158  xor     rdx, r8
0x18000d15b  and     rdx, rax
0x18000d15e  cmp     [rsi+30h], rdx
0x18000d162  ja      short loc_18000D16D
0x18000d164  shr     rax, 1
0x18000d167  sub     rdx, rax
0x18000d16a  dec     rdx
0x18000d16d  mov     rcx, [rsi+10h]
0x18000d171  add     rdx, rdx
0x18000d174  cmp     [rcx+rdx*8+8], rbx
0x18000d179  jnz     short loc_18000D19C
0x18000d17b  cmp     [rcx+rdx*8], rbx
0x18000d17f  jnz     short loc_18000D191
0x18000d181  mov     rax, [rsi]
0x18000d184  mov     [rcx+rdx*8], rax
0x18000d188  mov     rcx, [rsi+10h]
0x18000d18c  mov     rax, [rsi]
0x18000d18f  jmp     short loc_18000D195
0x18000d191  mov     rax, [rbx+8]
0x18000d195  mov     [rcx+rdx*8+8], rax
0x18000d19a  jmp     short loc_18000D1A9
0x18000d19c  cmp     [rcx+rdx*8], rbx
0x18000d1a0  jnz     short loc_18000D1A9
0x18000d1a2  mov     rax, [rbx]
0x18000d1a5  mov     [rcx+rdx*8], rax
0x18000d1a9  mov     rbp, [rbx]
0x18000d1ac  cmp     rbx, [rsi]
0x18000d1af  jz      short loc_18000D1F5
0x18000d1b1  mov     rax, [rbx+8]
0x18000d1b5  mov     [rax], rbp
0x18000d1b8  mov     rcx, [rbx]
0x18000d1bb  mov     rax, [rbx+8]
0x18000d1bf  mov     [rcx+8], rax
0x18000d1c3  cmp     qword ptr [rdi+18h], 8
0x18000d1c8  jb      short loc_18000D1D3
0x18000d1ca  mov     rcx, [rdi]
0x18000d1cd  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000d1d3  xor     eax, eax
0x18000d1d5  mov     qword ptr [rdi+18h], 7
0x18000d1dd  mov     qword ptr [rdi+10h], 0
0x18000d1e5  mov     rcx, rbx
0x18000d1e8  mov     [rdi], ax
0x18000d1eb  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000d1f1  dec     qword ptr [rsi+8]
0x18000d1f5  mov     [r14], rbp
0x18000d1f8  mov     rax, r14
0x18000d1fb  add     rsp, 20h
0x18000d1ff  pop     r14
0x18000d201  pop     rdi
0x18000d202  pop     rsi
0x18000d203  pop     rbp
0x18000d204  pop     rbx
0x18000d205  retn
```
