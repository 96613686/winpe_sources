# std::vector<uchar,std::allocator<uchar>>::resize(unsigned __int64)

- ea: `0x180025080`
- end: `0x180025174`
- name: `?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z`
- size: `244`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180023c8c`
- `0x180023d04`
- `0x180048ce0`

## callees

- `0x180009570`
- `0x180009e14`
- `0x180025080`
- `0x18002706c`

## import_xrefs

- `VCRUNTIME140!memset` at `0x180025112`
- `VCRUNTIME140!memset` at `0x18002514c`
- `VCRUNTIME140!memset` at `0x180025112`
- `VCRUNTIME140!memset` at `0x18002514c`
- `VCRUNTIME140!memmove` at `0x180025125`
- `VCRUNTIME140!memmove` at `0x180025125`

## pseudocode

```c
char *__fastcall std::vector<unsigned char>::resize(char **a1, unsigned __int64 a2)
{
  char *v2; // rbx
  char *result; // rax
  unsigned __int64 v5; // r15
  unsigned __int64 v7; // rcx
  __int64 v8; // rsi
  unsigned __int64 v9; // rdx
  char *v10; // rbx
  unsigned __int64 v11; // rdi

  v2 = a1[1];
  result = *a1;
  v5 = v2 - *a1;
  if ( a2 >= v5 )
  {
    if ( a2 > v5 )
    {
      v7 = a1[2] - result;
      if ( a2 <= v7 )
      {
        _mm_lfence();
        v11 = a2 - v5;
        memset(v2, 0, a2 - v5);
        result = &v2[v11];
        a1[1] = &v2[v11];
      }
      else
      {
        v8 = 0x7FFFFFFFFFFFFFFFLL;
        if ( a2 > 0x7FFFFFFFFFFFFFFFLL )
          std::vector<Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::ModuleDetails>::_Xlength(v7, a2);
        _mm_lfence();
        v9 = v7 >> 1;
        if ( v7 <= 0x7FFFFFFFFFFFFFFFLL - (v7 >> 1) )
        {
          v8 = v9 + v7;
          if ( v9 + v7 < a2 )
            v8 = a2;
        }
        v10 = (char *)std::_Allocate<16,std::_Default_allocate_traits>(v8);
        memset(&v10[v5], 0, a2 - v5);
        memmove(v10, *a1, a1[1] - *a1);
        return (char *)std::vector<unsigned char>::_Change_array(a1, v10, a2, v8);
      }
    }
  }
  else
  {
    result += a2;
    a1[1] = result;
  }
  return result;
}

```

## disassembly

```asm
0x180025080  mov     [rsp+arg_10], rbx
0x180025085  mov     [rsp+arg_18], rsi
0x18002508a  push    rdi
0x18002508b  push    r14
0x18002508d  push    r15
0x18002508f  sub     rsp, 20h
0x180025093  mov     rbx, [rcx+8]
0x180025097  mov     rdi, rdx
0x18002509a  mov     rax, [rcx]
0x18002509d  mov     r15, rbx
0x1800250a0  sub     r15, rax
0x1800250a3  mov     r14, rcx
0x1800250a6  cmp     rdx, r15
0x1800250a9  jnb     short loc_1800250B7
0x1800250ab  add     rax, rdx
0x1800250ae  mov     [rcx+8], rax
0x1800250b2  jmp     loc_18002515A
0x1800250b7  jbe     loc_18002515A
0x1800250bd  mov     rcx, [rcx+10h]
0x1800250c1  sub     rcx, rax
0x1800250c4  cmp     rdi, rcx
0x1800250c7  jbe     short loc_18002513E
0x1800250c9  mov     rsi, 7FFFFFFFFFFFFFFFh
0x1800250d3  cmp     rdi, rsi
0x1800250d6  ja      loc_18002516E
0x1800250dc  lfence
0x1800250df  mov     rdx, rcx
0x1800250e2  mov     rax, rsi
0x1800250e5  shr     rdx, 1
0x1800250e8  sub     rax, rdx
0x1800250eb  cmp     rcx, rax
0x1800250ee  ja      short loc_1800250FB
0x1800250f0  lea     rsi, [rdx+rcx]
0x1800250f4  cmp     rsi, rdi
0x1800250f7  cmovb   rsi, rdi
0x1800250fb  mov     rcx, rsi
0x1800250fe  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180025103  mov     r8, rdi
0x180025106  xor     edx, edx; Val
0x180025108  sub     r8, r15; Size
0x18002510b  mov     rbx, rax
0x18002510e  lea     rcx, [r15+rax]; void *
0x180025112  call    cs:__imp_memset
0x180025118  mov     r8, [r14+8]
0x18002511c  mov     rcx, rbx; void *
0x18002511f  sub     r8, [r14]; Size
0x180025122  mov     rdx, [r14]; Src
0x180025125  call    cs:__imp_memmove
0x18002512b  mov     r9, rsi
0x18002512e  mov     r8, rdi
0x180025131  mov     rdx, rbx
0x180025134  mov     rcx, r14
0x180025137  call    ?_Change_array@?$vector@EV?$allocator@E@std@@@std@@AEAAXQEAE_K1@Z; std::vector<uchar>::_Change_array(uchar * const,unsigned __int64,unsigned __int64)
0x18002513c  jmp     short loc_18002515A
0x18002513e  lfence
0x180025141  sub     rdi, r15
0x180025144  xor     edx, edx; Val
0x180025146  mov     r8, rdi; Size
0x180025149  mov     rcx, rbx; void *
0x18002514c  call    cs:__imp_memset
0x180025152  lea     rax, [rdi+rbx]
0x180025156  mov     [r14+8], rax
0x18002515a  mov     rbx, [rsp+38h+arg_10]
0x18002515f  mov     rsi, [rsp+38h+arg_18]
0x180025164  add     rsp, 20h
0x180025168  pop     r15
0x18002516a  pop     r14
0x18002516c  pop     rdi
0x18002516d  retn
0x18002516e  call    ?_Xlength@?$vector@UModuleDetails@NgenSymbolHelper@StandardCollector@DiagnosticsHub@Microsoft@@V?$allocator@UModuleDetails@NgenSymbolHelper@StandardCollector@DiagnosticsHub@Microsoft@@@std@@@std@@CAXXZ; std::vector<Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::ModuleDetails>::_Xlength(void)
```
