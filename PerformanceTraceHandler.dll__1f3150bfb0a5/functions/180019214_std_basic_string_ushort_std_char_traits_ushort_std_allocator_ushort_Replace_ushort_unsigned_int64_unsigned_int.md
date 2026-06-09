# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Replace<ushort>(unsigned __int64,unsigned __int64,ushort const * const,unsigned __int64)

- ea: `0x180019214`
- end: `0x1800193dc`
- name: `??$_Replace@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_K_KQEBG0@Z`
- size: `456`
- prototype: `__int64 __fastcall(_QWORD *, unsigned __int64, __int64, __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180019d50`

## callees

- `0x1800036f8`
- `0x180003704`
- `0x180019110`
- `0x180019214`

## import_xrefs

- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180019245`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180019245`

## pseudocode

```c
__int64 __fastcall std::wstring::_Replace<unsigned short>(
        _QWORD *a1,
        unsigned __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned __int64 a5)
{
  unsigned __int64 v5; // r12
  unsigned __int64 v7; // rbp
  unsigned __int64 v8; // r8
  _QWORD *v9; // rax
  unsigned __int64 v11; // r13
  _QWORD *v12; // rax
  char *v13; // rdi
  unsigned __int64 v14; // rcx
  wchar_t *v15; // r8
  const wchar_t *v16; // rdx
  __int64 v17; // rdi
  wchar_t *v18; // [rsp+98h] [rbp+20h]

  v5 = a1[2];
  if ( v5 < a2 )
  {
    std::_Xout_of_range("invalid string position");
    __debugbreak();
  }
  v7 = 5;
  v8 = a1[3];
  if ( v5 - a2 < 5 )
    v7 = v5 - a2;
  if ( v7 == a5 )
  {
    if ( v8 <= 7 )
      v9 = a1;
    else
      v9 = (_QWORD *)*a1;
    memmove_0((char *)v9 + 2 * a2, L"&", 2 * a5);
    return (__int64)a1;
  }
  v11 = v5 - a2 - v7;
  if ( a5 < v7 )
  {
    if ( v8 <= 7 )
      v12 = a1;
    else
      v12 = (_QWORD *)*a1;
    v13 = (char *)v12 + 2 * a2;
    memmove_0(v13, L"&", 2 * a5);
    memmove_0(&v13[2 * a5], &v13[2 * v7], 2 * v11 + 2);
    a1[2] = a5 + v5 - v7;
    return (__int64)a1;
  }
  v14 = a5 - v7;
  if ( a5 - v7 <= v8 - v5 )
  {
    a1[2] = v14 + v5;
    if ( v8 <= 7 )
      v15 = (wchar_t *)a1;
    else
      v15 = (wchar_t *)*a1;
    v18 = &v15[a2];
    v16 = &v18[v7];
    if ( &asc_180021004[a5] <= v18 || L"&" > &v15[v5] )
    {
      v17 = a5;
    }
    else if ( v16 > L"&" )
    {
      v17 = v16 - L"&";
    }
    else
    {
      v17 = 0;
    }
    memmove_0((void *)&v16[v14], v16, 2 * v11 + 2);
    memmove_0(v18, L"&", 2 * v17);
    memcpy_0(&v18[v17], &asc_180021004[v17 + a5 - v7], 2 * (a5 - v17));
    return (__int64)a1;
  }
  return std::wstring::_Reallocate_grow_by<_lambda_622fe101509e1fd0c758e599152cbb8b_,unsigned __int64,unsigned __int64,unsigned short const *,unsigned __int64>(
           (_DWORD)a1,
           (int)a5 - (int)v7,
           v8,
           a2,
           v7);
}

```

## disassembly

```asm
0x180019214  mov     [rsp+arg_0], rbx
0x180019219  mov     [rsp+arg_18], r9
0x18001921e  mov     [rsp+arg_10], r8
0x180019223  push    rbp
0x180019224  push    rsi
0x180019225  push    rdi
0x180019226  push    r12
0x180019228  push    r13
0x18001922a  push    r14
0x18001922c  push    r15
0x18001922e  sub     rsp, 40h
0x180019232  mov     r12, [rcx+10h]
0x180019236  mov     rsi, rcx
0x180019239  cmp     r12, rdx
0x18001923c  jnb     short loc_18001924C
0x18001923e  lea     rcx, aInvalidStringP; "invalid string position"
0x180019245  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x18001924b  int     3; Trap to Debugger
0x18001924c  mov     r14, [rsp+78h+arg_20]
0x180019254  mov     ebp, 5
0x180019259  mov     r8, [rcx+18h]
0x18001925d  mov     r13, r12
0x180019260  sub     r13, rdx
0x180019263  cmp     r13, rbp
0x180019266  cmovb   rbp, r13
0x18001926a  cmp     rbp, r14
0x18001926d  jnz     short loc_180019299
0x18001926f  cmp     r8, 7
0x180019273  jbe     short loc_18001927A
0x180019275  mov     rax, [rcx]
0x180019278  jmp     short loc_18001927D
0x18001927a  mov     rax, rsi
0x18001927d  lea     rcx, [rax+rdx*2]; void *
0x180019281  lea     rdx, asc_180021004; "&"
0x180019288  lea     r8, [r14+r14]; Size
0x18001928c  call    memmove_0
0x180019291  mov     rax, rsi
0x180019294  jmp     loc_1800193C4
0x180019299  sub     r13, rbp
0x18001929c  cmp     r14, rbp
0x18001929f  jnb     short loc_1800192EA
0x1800192a1  cmp     r8, 7
0x1800192a5  jbe     short loc_1800192AC
0x1800192a7  mov     rax, [rcx]
0x1800192aa  jmp     short loc_1800192AF
0x1800192ac  mov     rax, rsi
0x1800192af  lea     rdi, [rax+rdx*2]
0x1800192b3  lea     rbx, [r14+r14]
0x1800192b7  mov     rcx, rdi; void *
0x1800192ba  mov     r8, rbx; Size
0x1800192bd  lea     rdx, asc_180021004; "&"
0x1800192c4  call    memmove_0
0x1800192c9  lea     r8, ds:2[r13*2]; Size
0x1800192d1  lea     rdx, [rdi+rbp*2]; Src
0x1800192d5  lea     rcx, [rdi+rbx]; void *
0x1800192d9  call    memmove_0
0x1800192de  sub     r12, rbp
0x1800192e1  add     r12, r14
0x1800192e4  mov     [rsi+10h], r12
0x1800192e8  jmp     short loc_180019291
0x1800192ea  mov     rcx, r14
0x1800192ed  mov     rax, r8
0x1800192f0  sub     rcx, rbp
0x1800192f3  sub     rax, r12
0x1800192f6  mov     [rsp+78h+arg_10], rcx
0x1800192fe  cmp     rcx, rax
0x180019301  ja      loc_1800193AC
0x180019307  lea     rax, [rcx+r12]
0x18001930b  mov     [rsi+10h], rax
0x18001930f  cmp     r8, 7
0x180019313  jbe     short loc_18001931A
0x180019315  mov     r8, [rsi]
0x180019318  jmp     short loc_18001931D
0x18001931a  mov     r8, rsi
0x18001931d  lea     r9, [r8+rdx*2]
0x180019321  lea     r15, asc_180021004; "&"
0x180019328  mov     [rsp+78h+arg_18], r9
0x180019330  lea     rax, [r15+r14*2]
0x180019334  lea     rdx, [r9+rbp*2]; Src
0x180019338  cmp     rax, r9
0x18001933b  jbe     short loc_18001935A
0x18001933d  lea     rax, [r8+r12*2]
0x180019341  cmp     r15, rax
0x180019344  ja      short loc_18001935A
0x180019346  cmp     rdx, r15
0x180019349  ja      short loc_18001934F
0x18001934b  xor     edi, edi
0x18001934d  jmp     short loc_18001935D
0x18001934f  mov     rdi, rdx
0x180019352  sub     rdi, r15
0x180019355  sar     rdi, 1
0x180019358  jmp     short loc_18001935D
0x18001935a  mov     rdi, r14
0x18001935d  lea     r8, ds:2[r13*2]; Size
0x180019365  lea     rcx, [rdx+rcx*2]; void *
0x180019369  call    memmove_0
0x18001936e  mov     r12, [rsp+78h+arg_18]
0x180019376  lea     rbx, [rdi+rdi]
0x18001937a  mov     r8, rbx; Size
0x18001937d  mov     rcx, r12; void *
0x180019380  mov     rdx, r15; Src
0x180019383  call    memmove_0
0x180019388  mov     rax, [rsp+78h+arg_10]
0x180019390  lea     rcx, [rbx+r12]; void *
0x180019394  add     rax, rdi
0x180019397  sub     r14, rdi
0x18001939a  lea     rdx, [r15+rax*2]; Src
0x18001939e  lea     r8, [r14+r14]; Size
0x1800193a2  call    memcpy_0
0x1800193a7  jmp     loc_180019291
0x1800193ac  mov     r9, rdx
0x1800193af  mov     [rsp+78h+var_48], r14
0x1800193b4  mov     rdx, rcx
0x1800193b7  mov     [rsp+78h+var_58], rbp
0x1800193bc  mov     rcx, rsi
0x1800193bf  call    ??$_Reallocate_grow_by@V_lambda_622fe101509e1fd0c758e599152cbb8b_@@_K_KPEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_622fe101509e1fd0c758e599152cbb8b_@@_K2PEBG2@Z; std::wstring::_Reallocate_grow_by<_lambda_622fe101509e1fd0c758e599152cbb8b_,unsigned __int64,unsigned __int64,ushort const *,unsigned __int64>(unsigned __int64,_lambda_622fe101509e1fd0c758e599152cbb8b_,unsigned __int64,unsigned __int64,ushort const *,unsigned __int64)
0x1800193c4  mov     rbx, [rsp+78h+arg_0]
0x1800193cc  add     rsp, 40h
0x1800193d0  pop     r15
0x1800193d2  pop     r14
0x1800193d4  pop     r13
0x1800193d6  pop     r12
0x1800193d8  pop     rdi
0x1800193d9  pop     rsi
0x1800193da  pop     rbp
0x1800193db  retn
```
