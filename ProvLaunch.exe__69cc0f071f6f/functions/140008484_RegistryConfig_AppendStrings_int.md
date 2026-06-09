# RegistryConfig::AppendStrings(int,...)

- ea: `0x140008484`
- end: `0x140008621`
- name: `?AppendStrings@RegistryConfig@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@HZZ`
- size: `413`
- prototype: `char *(__int64, char *, int, ...)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140008628`
- `0x1400088ac`

## callees

- `0x140006550`
- `0x140008484`
- `0x14000937c`
- `0x14000951c`
- `0x14000a326`

## pseudocode

```c
char *RegistryConfig::AppendStrings(__int64 a1, char *a2, int a3, ...)
{
  va_list v4; // r15
  int i; // r14d
  _WORD *v6; // rbp
  unsigned __int64 v7; // rsi
  unsigned __int64 v8; // rdx
  unsigned __int64 v9; // rax
  char *v10; // rcx
  _BYTE *v11; // rax
  __int64 v12; // r8
  unsigned __int64 v13; // rdi
  unsigned __int64 v14; // rcx
  _WORD *v15; // rcx
  unsigned __int64 v16; // rcx
  int v18; // [rsp+20h] [rbp-48h]
  va_list va; // [rsp+88h] [rbp+20h] BYREF

  va_start(va, a3);
  *((_QWORD *)a2 + 3) = 7;
  *((_QWORD *)a2 + 2) = 0;
  *(_WORD *)a2 = 0;
  v18 = 1;
  va_copy(v4, va);
  for ( i = 0; i < a3; ++i )
  {
    v4 += 8;
    v6 = (_WORD *)*((_QWORD *)v4 - 1);
    if ( *v6 )
    {
      v7 = -1;
      do
        ++v7;
      while ( v6[v7] );
    }
    else
    {
      v7 = 0;
    }
    v8 = *((_QWORD *)a2 + 3);
    if ( v8 < 8 )
      v9 = (unsigned __int64)a2;
    else
      v9 = *(_QWORD *)a2;
    if ( (unsigned __int64)v6 < v9
      || (v8 < 8 ? (v10 = a2) : (v10 = *(char **)a2), &v10[2 * *((_QWORD *)a2 + 2)] <= (char *)v6) )
    {
      v12 = *((_QWORD *)a2 + 2);
      if ( ~v12 <= v7 )
        std::wstring::_Xlen();
      if ( !v7 )
        continue;
      v13 = v12 + v7;
      if ( v12 + v7 > 0x7FFFFFFFFFFFFFFELL )
        std::wstring::_Xlen();
      if ( v8 >= v13 )
      {
        if ( !v13 )
        {
          if ( v8 < 8 )
            v15 = a2;
          else
            v15 = *(_WORD **)a2;
          *((_QWORD *)a2 + 2) = 0;
          *v15 = 0;
          continue;
        }
LABEL_23:
        if ( *((_QWORD *)a2 + 3) < 8u )
          v14 = (unsigned __int64)a2;
        else
          v14 = *(_QWORD *)a2;
        memcpy_0((void *)(v14 + 2LL * *((_QWORD *)a2 + 2)), v6, 2 * v7);
        if ( *((_QWORD *)a2 + 3) < 8u )
          v16 = (unsigned __int64)a2;
        else
          v16 = *(_QWORD *)a2;
        *((_QWORD *)a2 + 2) = v13;
        *(_WORD *)(v16 + 2 * v13) = 0;
        continue;
      }
      std::wstring::_Copy((const void **)a2, v12 + v7, v12);
      if ( v13 )
        goto LABEL_23;
    }
    else
    {
      if ( v8 < 8 )
        v11 = a2;
      else
        v11 = *(_BYTE **)a2;
      std::wstring::append(a2, a2, ((char *)v6 - v11) >> 1, v7, v18);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x140008484  mov     rax, rsp
0x140008487  mov     [rax+18h], r8d
0x14000848b  mov     [rax+10h], rdx
0x14000848f  mov     [rax+20h], r9
0x140008493  push    rbx
0x140008494  push    rbp
0x140008495  push    rsi
0x140008496  push    rdi
0x140008497  push    r12
0x140008499  push    r14
0x14000849b  push    r15
0x14000849d  sub     rsp, 30h
0x1400084a1  mov     rbx, rdx
0x1400084a4  xor     r12d, r12d
0x1400084a7  mov     [rax-48h], r12d
0x1400084ab  mov     qword ptr [rdx+18h], 7
0x1400084b3  mov     [rdx+10h], r12
0x1400084b7  mov     [rdx], r12w
0x1400084bb  mov     dword ptr [rax-48h], 1
0x1400084c2  lea     r15, [rax+20h]
0x1400084c6  mov     r14d, r12d
0x1400084c9  cmp     [rax+18h], r12d
0x1400084cd  jle     loc_140008603
0x1400084d3  lea     r15, [r15+8]
0x1400084d7  mov     rbp, [r15-8]
0x1400084db  cmp     [rbp+0], r12w
0x1400084e0  jnz     short loc_1400084E7
0x1400084e2  mov     rsi, r12
0x1400084e5  jmp     short loc_1400084F6
0x1400084e7  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1400084eb  inc     rsi
0x1400084ee  cmp     [rbp+rsi*2+0], r12w
0x1400084f4  jnz     short loc_1400084EB
0x1400084f6  mov     rdx, [rbx+18h]
0x1400084fa  cmp     rdx, 8
0x1400084fe  jb      short loc_140008505
0x140008500  mov     rax, [rbx]
0x140008503  jmp     short loc_140008508
0x140008505  mov     rax, rbx
0x140008508  cmp     rbp, rax
0x14000850b  jb      short loc_140008552
0x14000850d  cmp     rdx, 8
0x140008511  jb      short loc_140008518
0x140008513  mov     rcx, [rbx]
0x140008516  jmp     short loc_14000851B
0x140008518  mov     rcx, rbx
0x14000851b  mov     rax, [rbx+10h]
0x14000851f  lea     rcx, [rcx+rax*2]
0x140008523  cmp     rcx, rbp
0x140008526  jbe     short loc_140008552
0x140008528  cmp     rdx, 8
0x14000852c  jb      short loc_140008533
0x14000852e  mov     rax, [rbx]
0x140008531  jmp     short loc_140008536
0x140008533  mov     rax, rbx
0x140008536  sub     rbp, rax
0x140008539  sar     rbp, 1
0x14000853c  mov     r9, rsi
0x14000853f  mov     r8, rbp
0x140008542  mov     rdx, rbx
0x140008545  mov     rcx, rbx
0x140008548  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x14000854d  jmp     loc_1400085F2
0x140008552  mov     r8, [rbx+10h]
0x140008556  mov     rax, r8
0x140008559  not     rax
0x14000855c  cmp     rax, rsi
0x14000855f  jbe     loc_14000861B
0x140008565  test    rsi, rsi
0x140008568  jz      loc_1400085F2
0x14000856e  lea     rdi, [r8+rsi]
0x140008572  mov     rax, 7FFFFFFFFFFFFFFEh
0x14000857c  cmp     rdi, rax
0x14000857f  ja      loc_140008615
0x140008585  cmp     rdx, rdi
0x140008588  jnb     short loc_1400085A6
0x14000858a  mov     rdx, rdi
0x14000858d  mov     rcx, rbx; Src
0x140008590  call    ?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z; std::wstring::_Copy(unsigned __int64,unsigned __int64)
0x140008595  test    rdi, rdi
0x140008598  jz      short loc_1400085F2
0x14000859a  cmp     qword ptr [rbx+18h], 8
0x14000859f  jb      short loc_1400085C3
0x1400085a1  mov     rcx, [rbx]
0x1400085a4  jmp     short loc_1400085C6
0x1400085a6  test    rdi, rdi
0x1400085a9  jnz     short loc_14000859A
0x1400085ab  cmp     rdx, 8
0x1400085af  jb      short loc_1400085B6
0x1400085b1  mov     rcx, [rbx]
0x1400085b4  jmp     short loc_1400085B9
0x1400085b6  mov     rcx, rbx
0x1400085b9  mov     [rbx+10h], r12
0x1400085bd  mov     [rcx], r12w
0x1400085c1  jmp     short loc_1400085F2
0x1400085c3  mov     rcx, rbx
0x1400085c6  lea     r8, [rsi+rsi]; Size
0x1400085ca  mov     rax, [rbx+10h]
0x1400085ce  lea     rcx, [rcx+rax*2]; void *
0x1400085d2  mov     rdx, rbp; Src
0x1400085d5  call    memcpy_0
0x1400085da  cmp     qword ptr [rbx+18h], 8
0x1400085df  jb      short loc_1400085E6
0x1400085e1  mov     rcx, [rbx]
0x1400085e4  jmp     short loc_1400085E9
0x1400085e6  mov     rcx, rbx
0x1400085e9  mov     [rbx+10h], rdi
0x1400085ed  mov     [rcx+rdi*2], r12w
0x1400085f2  inc     r14d
0x1400085f5  cmp     r14d, [rsp+68h+arg_10]
0x1400085fd  jl      loc_1400084D3
0x140008603  mov     rax, rbx
0x140008606  add     rsp, 30h
0x14000860a  pop     r15
0x14000860c  pop     r14
0x14000860e  pop     r12
0x140008610  pop     rdi
0x140008611  pop     rsi
0x140008612  pop     rbp
0x140008613  pop     rbx
0x140008614  retn
0x140008615  call    ?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xlen(void)
0x14000861b  call    ?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xlen(void)
```
