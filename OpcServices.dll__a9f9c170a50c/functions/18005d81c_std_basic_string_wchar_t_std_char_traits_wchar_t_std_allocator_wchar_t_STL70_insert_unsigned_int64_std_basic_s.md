# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>,_STL70>::insert(unsigned __int64,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>,_STL70> const &,unsigned __int64,unsigned __int64)

- ea: `0x18005d81c`
- end: `0x18005d97e`
- name: `?insert@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAAAEAV12@_KAEBV12@00@Z`
- size: `354`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18005c4a4`

## callees

- `0x18001c4b0`
- `0x18005d81c`
- `0x1800cdb60`
- `0x1800cdbbc`

## import_xrefs

- `msvcrt!memmove_s` at `0x18005d8d9`
- `msvcrt!memmove_s` at `0x18005d916`
- `msvcrt!memmove_s` at `0x18005d8d9`
- `msvcrt!memmove_s` at `0x18005d916`
- `msvcrt!memcpy_s` at `0x18005d94f`
- `msvcrt!memcpy_s` at `0x18005d94f`

## pseudocode

```c
_QWORD *__fastcall std::wstring::insert(
        _QWORD *a1,
        unsigned __int64 a2,
        _QWORD *a3,
        unsigned __int64 a4,
        unsigned __int64 a5)
{
  unsigned __int64 v6; // r14
  unsigned __int64 v7; // rcx
  unsigned __int64 v10; // rsi
  unsigned __int64 v11; // rcx
  unsigned __int64 v12; // r13
  _QWORD *v13; // rdi
  unsigned __int64 v14; // rdx
  __int64 v15; // r12
  _QWORD *v16; // rcx
  _QWORD *v17; // rax
  unsigned __int64 v18; // rdx
  _QWORD *v19; // rax
  _QWORD *v20; // rcx
  _QWORD *v21; // rax
  unsigned __int64 v22; // rdx
  _QWORD *v23; // rcx

  v6 = a4;
  v7 = a1[3];
  if ( v7 < a2 || a3[3] < a4 )
    std::_String_base::_Xran();
  v10 = a5;
  v11 = ~v7;
  if ( a3[3] - a4 < a5 )
    v10 = a3[3] - a4;
  if ( v11 <= v10 )
    std::_String_base::_Xlen();
  if ( v10 )
  {
    v12 = v10 + a1[3];
    if ( (unsigned __int8)std::wstring::_Grow(a1, v12, 0) )
    {
      v13 = a1 + 1;
      v14 = a1[4];
      v15 = 2 * a2;
      if ( v14 < 8 )
      {
        v16 = a1 + 1;
        v17 = a1 + 1;
      }
      else
      {
        v16 = (_QWORD *)*v13;
        v17 = (_QWORD *)*v13;
      }
      memmove_s((char *)v16 + 2 * a2 + 2 * v10, 2 * (v14 - a2 - v10), (char *)v17 + v15, 2 * (a1[3] - a2));
      if ( a1 == a3 )
      {
        if ( a2 < v6 )
          v6 += v10;
        v18 = a1[4];
        if ( v18 < 8 )
        {
          v19 = a1 + 1;
          v20 = a1 + 1;
        }
        else
        {
          v19 = (_QWORD *)*v13;
          v20 = (_QWORD *)*v13;
        }
        memmove_s((char *)v19 + v15, 2 * (v18 - a2), (char *)v20 + 2 * v6, 2 * v10);
      }
      else
      {
        v21 = a3 + 1;
        if ( a3[4] >= 8u )
          v21 = (_QWORD *)*v21;
        v22 = a1[4];
        if ( v22 < 8 )
          v23 = a1 + 1;
        else
          v23 = (_QWORD *)*v13;
        memcpy_s((char *)v23 + v15, 2 * (v22 - a2), (char *)v21 + 2 * v6, 2 * v10);
      }
      if ( a1[4] >= 8u )
        v13 = (_QWORD *)*v13;
      a1[3] = v12;
      *((_WORD *)v13 + v12) = 0;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x18005d81c  push    rbx
0x18005d81e  push    rbp
0x18005d81f  push    rsi
0x18005d820  push    rdi
0x18005d821  push    r12
0x18005d823  push    r13
0x18005d825  push    r14
0x18005d827  push    r15
0x18005d829  sub     rsp, 28h
0x18005d82d  mov     rbx, rcx
0x18005d830  mov     r14, r9
0x18005d833  mov     rcx, [rcx+18h]
0x18005d837  mov     rbp, r8
0x18005d83a  mov     r15, rdx
0x18005d83d  cmp     rcx, rdx
0x18005d840  jb      short loc_18005D848
0x18005d842  cmp     [r8+18h], r9
0x18005d846  jnb     short loc_18005D851
0x18005d848  call    ?_Xran@_String_base@std@@SAXXZ; std::_String_base::_Xran(void)
0x18005d84d  mov     rcx, [rbx+18h]
0x18005d851  mov     rsi, [rsp+68h+arg_20]
0x18005d859  not     rcx
0x18005d85c  mov     rax, [rbp+18h]
0x18005d860  sub     rax, r14
0x18005d863  cmp     rax, rsi
0x18005d866  cmovb   rsi, rax
0x18005d86a  cmp     rcx, rsi
0x18005d86d  ja      short loc_18005D874
0x18005d86f  call    ?_Xlen@_String_base@std@@SAXXZ; std::_String_base::_Xlen(void)
0x18005d874  test    rsi, rsi
0x18005d877  jz      loc_18005D96A
0x18005d87d  mov     r13, [rbx+18h]
0x18005d881  xor     r8d, r8d
0x18005d884  add     r13, rsi
0x18005d887  mov     rcx, rbx
0x18005d88a  mov     rdx, r13
0x18005d88d  call    ?_Grow@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAA_N_K_N@Z; std::wstring::_Grow(unsigned __int64,bool)
0x18005d892  test    al, al
0x18005d894  jz      loc_18005D96A
0x18005d89a  mov     r9, [rbx+18h]
0x18005d89e  lea     rdi, [rbx+8]
0x18005d8a2  mov     rdx, [rbx+20h]
0x18005d8a6  lea     r12, [r15+r15]
0x18005d8aa  sub     r9, r15
0x18005d8ad  cmp     rdx, 8
0x18005d8b1  jb      short loc_18005D8BB
0x18005d8b3  mov     rcx, [rdi]
0x18005d8b6  mov     rax, rcx
0x18005d8b9  jmp     short loc_18005D8C1
0x18005d8bb  mov     rcx, rdi
0x18005d8be  mov     rax, rdi
0x18005d8c1  sub     rdx, r15
0x18005d8c4  lea     r8, [r12+rax]; Source
0x18005d8c8  sub     rdx, rsi
0x18005d8cb  lea     rax, [r15+rsi]
0x18005d8cf  add     rdx, rdx; DestinationSize
0x18005d8d2  lea     rcx, [rcx+rax*2]; Destination
0x18005d8d6  add     r9, r9; SourceSize
0x18005d8d9  call    cs:__imp_memmove_s
0x18005d8df  cmp     rbx, rbp
0x18005d8e2  jnz     short loc_18005D91E
0x18005d8e4  cmp     r15, r14
0x18005d8e7  jnb     short loc_18005D8EC
0x18005d8e9  add     r14, rsi
0x18005d8ec  mov     rdx, [rbx+20h]
0x18005d8f0  cmp     rdx, 8
0x18005d8f4  jb      short loc_18005D8FE
0x18005d8f6  mov     rax, [rdi]
0x18005d8f9  mov     rcx, rax
0x18005d8fc  jmp     short loc_18005D904
0x18005d8fe  mov     rax, rdi
0x18005d901  mov     rcx, rdi
0x18005d904  sub     rdx, r15
0x18005d907  lea     r8, [rcx+r14*2]; Source
0x18005d90b  add     rdx, rdx; DestinationSize
0x18005d90e  lea     r9, [rsi+rsi]; SourceSize
0x18005d912  lea     rcx, [r12+rax]; Destination
0x18005d916  call    cs:__imp_memmove_s
0x18005d91c  jmp     short loc_18005D955
0x18005d91e  cmp     qword ptr [rbp+20h], 8
0x18005d923  lea     rax, [rbp+8]
0x18005d927  jb      short loc_18005D92C
0x18005d929  mov     rax, [rax]
0x18005d92c  mov     rdx, [rbx+20h]
0x18005d930  cmp     rdx, 8
0x18005d934  jb      short loc_18005D93B
0x18005d936  mov     rcx, [rdi]
0x18005d939  jmp     short loc_18005D93E
0x18005d93b  mov     rcx, rdi
0x18005d93e  sub     rdx, r15
0x18005d941  lea     r9, [rsi+rsi]; SourceSize
0x18005d945  add     rdx, rdx; DestinationSize
0x18005d948  lea     r8, [rax+r14*2]; Source
0x18005d94c  add     rcx, r12; Destination
0x18005d94f  call    cs:__imp_memcpy_s
0x18005d955  cmp     qword ptr [rbx+20h], 8
0x18005d95a  jb      short loc_18005D95F
0x18005d95c  mov     rdi, [rdi]
0x18005d95f  xor     eax, eax
0x18005d961  mov     [rbx+18h], r13
0x18005d965  mov     [rdi+r13*2], ax
0x18005d96a  mov     rax, rbx
0x18005d96d  add     rsp, 28h
0x18005d971  pop     r15
0x18005d973  pop     r14
0x18005d975  pop     r13
0x18005d977  pop     r12
0x18005d979  pop     rdi
0x18005d97a  pop     rsi
0x18005d97b  pop     rbp
0x18005d97c  pop     rbx
0x18005d97d  retn
```
