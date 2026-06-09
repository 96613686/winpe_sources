# std::vector<web::json::value,std::allocator<web::json::value>>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)

- ea: `0x180004260`
- end: `0x180004424`
- name: `??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@Vvalue@json@web@@V?$allocator@Vvalue@json@web@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z`
- size: `452`
- prototype: `char *__fastcall(char **, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x180006570`

## callees

- `0x180002cc0`
- `0x180002cfc`
- `0x180004260`
- `0x1800044a0`
- `0x180005860`
- `0x18001c7f4`
- `0x18002a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char *__fastcall std::vector<web::json::value>::_Resize_reallocate<std::_Value_init_tag>(
        char **a1,
        unsigned __int64 a2)
{
  char *v4; // r12
  unsigned __int64 v5; // rcx
  unsigned __int64 v6; // rdx
  unsigned __int64 v7; // rbx
  char *v8; // rbp
  unsigned __int64 v9; // r14
  _QWORD *v10; // rsi
  void *v11; // rax
  char *v12; // r8
  _QWORD *v13; // rdx
  char *i; // rcx
  __int64 v15; // rax
  char *v16; // rbx
  char *j; // rbp
  char *v18; // rcx
  unsigned __int64 v19; // rdx
  char *v20; // rax
  char *result; // rax

  if ( a2 > 0x1FFFFFFFFFFFFFFFLL )
    std::vector<std::pair<std::wstring,web::json::value>>::_Xlength();
  v4 = *a1;
  v5 = (a1[2] - *a1) >> 3;
  v6 = v5 >> 1;
  if ( v5 > 0x1FFFFFFFFFFFFFFFLL - (v5 >> 1) )
    goto LABEL_29;
  v7 = v5 + v6;
  if ( v5 + v6 >= a2 )
  {
    if ( v7 > 0x1FFFFFFFFFFFFFFFLL )
      goto LABEL_29;
  }
  else
  {
    v7 = a2;
  }
  v8 = a1[1];
  v9 = 8 * v7;
  if ( !(8 * v7) )
  {
    v10 = 0;
    goto LABEL_14;
  }
  if ( v9 < 0x1000 )
  {
    v10 = operator new(8 * v7);
    goto LABEL_14;
  }
  if ( v9 + 39 < v9 )
LABEL_29:
    __scrt_throw_std_bad_array_new_length();
  v11 = operator new(v9 + 39);
  if ( !v11 )
    __fastfail(5u);
  v10 = (_QWORD *)(((unsigned __int64)v11 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
  *(v10 - 1) = v11;
LABEL_14:
  std::_Uninitialized_value_construct_n<std::allocator<web::json::value>>(
    &v10[(v8 - v4) >> 3],
    a2 - ((v8 - v4) >> 3),
    a1);
  v12 = a1[1];
  v13 = v10;
  for ( i = *a1; i != v12; i += 8 )
  {
    v15 = *(_QWORD *)i;
    *(_QWORD *)i = 0;
    *v13++ = v15;
  }
  v16 = *a1;
  if ( *a1 )
  {
    for ( j = a1[1]; v16 != j; v16 += 8 )
    {
      if ( *(_QWORD *)v16 )
        (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)v16 + 192LL))(*(_QWORD *)v16, 1);
    }
    v18 = *a1;
    v19 = 8 * ((a1[2] - *a1) >> 3);
    if ( v19 < 0x1000 )
    {
      v20 = *a1;
    }
    else
    {
      v20 = (char *)*((_QWORD *)v18 - 1);
      if ( (unsigned __int64)(v18 - v20 - 8) > 0x1F )
        __fastfail(5u);
      v19 += 39LL;
    }
    operator delete(v20, v19);
  }
  *a1 = (char *)v10;
  a1[1] = (char *)&v10[a2];
  result = (char *)&v10[v9 / 8];
  a1[2] = (char *)&v10[v9 / 8];
  return result;
}

```

## disassembly

```asm
0x180004260  push    rbx
0x180004262  push    rbp
0x180004263  push    rsi
0x180004264  push    rdi
0x180004265  push    r12
0x180004267  push    r13
0x180004269  push    r14
0x18000426b  push    r15
0x18000426d  sub     rsp, 58h
0x180004271  mov     r15, rdx
0x180004274  mov     rdi, rcx
0x180004277  mov     r8, 1FFFFFFFFFFFFFFFh
0x180004281  cmp     rdx, r8
0x180004284  ja      loc_180004418
0x18000428a  mov     r12, [rcx]
0x18000428d  mov     rcx, [rcx+10h]
0x180004291  sub     rcx, r12
0x180004294  sar     rcx, 3
0x180004298  mov     rdx, rcx
0x18000429b  shr     rdx, 1
0x18000429e  mov     rax, r8
0x1800042a1  sub     rax, rdx
0x1800042a4  cmp     rcx, rax
0x1800042a7  ja      loc_18000441E
0x1800042ad  lea     rbx, [rcx+rdx]
0x1800042b1  cmp     rbx, r15
0x1800042b4  jnb     short loc_1800042BB
0x1800042b6  mov     rbx, r15
0x1800042b9  jmp     short loc_1800042C4
0x1800042bb  cmp     rbx, r8
0x1800042be  ja      loc_18000441E
0x1800042c4  mov     rbp, [rdi+8]
0x1800042c8  lea     r14, ds:0[rbx*8]
0x1800042d0  xor     r13d, r13d
0x1800042d3  test    r14, r14
0x1800042d6  jnz     short loc_1800042DD
0x1800042d8  mov     esi, r13d
0x1800042db  jmp     short loc_18000431D
0x1800042dd  cmp     r14, 1000h
0x1800042e4  jb      short loc_180004312
0x1800042e6  lea     rcx, [r14+27h]; Size
0x1800042ea  cmp     rcx, r14
0x1800042ed  jbe     loc_18000441E
0x1800042f3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800042f8  test    rax, rax
0x1800042fb  jnz     short loc_180004304
0x1800042fd  mov     ecx, 5
0x180004302  int     29h; Win8: RtlFailFast(ecx)
0x180004304  lea     rsi, [rax+27h]
0x180004308  and     rsi, 0FFFFFFFFFFFFFFE0h
0x18000430c  mov     [rsi-8], rax
0x180004310  jmp     short loc_18000431D
0x180004312  mov     rcx, r14; Size
0x180004315  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000431a  mov     rsi, rax
0x18000431d  sub     rbp, r12
0x180004320  sar     rbp, 3
0x180004324  lea     rcx, [rsi+rbp*8]
0x180004328  mov     [rsp+98h+var_78], rdi
0x18000432d  mov     [rsp+98h+var_70], rsi
0x180004332  mov     [rsp+98h+var_68], rbx
0x180004337  mov     [rsp+98h+var_60], rcx
0x18000433c  mov     [rsp+98h+var_58], rcx
0x180004341  mov     rdx, r15
0x180004344  sub     rdx, rbp
0x180004347  mov     r8, rdi
0x18000434a  call    ??$_Uninitialized_value_construct_n@V?$allocator@Vvalue@json@web@@@std@@@std@@YAPEAVvalue@json@web@@PEAV123@_KAEAV?$allocator@Vvalue@json@web@@@0@@Z; std::_Uninitialized_value_construct_n<std::allocator<web::json::value>>(web::json::value *,unsigned __int64,std::allocator<web::json::value> &)
0x18000434f  mov     r8, [rdi+8]
0x180004353  mov     rdx, rsi
0x180004356  mov     rcx, [rdi]
0x180004359  cmp     rcx, r8
0x18000435c  jz      short loc_180004376
0x18000435e  xchg    ax, ax
0x180004360  mov     rax, [rcx]
0x180004363  mov     [rcx], r13
0x180004366  mov     [rdx], rax
0x180004369  lea     rdx, [rdx+8]
0x18000436d  add     rcx, 8
0x180004371  cmp     rcx, r8
0x180004374  jnz     short loc_180004360
0x180004376  mov     rbx, [rdi]
0x180004379  test    rbx, rbx
0x18000437c  jz      short loc_1800043F4
0x18000437e  mov     rbp, [rdi+8]
0x180004382  cmp     rbx, rbp
0x180004385  jz      short loc_1800043AC
0x180004387  mov     rcx, [rbx]
0x18000438a  test    rcx, rcx
0x18000438d  jz      short loc_1800043A3
0x18000438f  mov     rax, [rcx]
0x180004392  mov     edx, 1
0x180004397  mov     rax, [rax+0C0h]
0x18000439e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043a3  add     rbx, 8
0x1800043a7  cmp     rbx, rbp
0x1800043aa  jnz     short loc_180004387
0x1800043ac  mov     rcx, [rdi]
0x1800043af  mov     rax, [rdi+10h]
0x1800043b3  sub     rax, rcx
0x1800043b6  sar     rax, 3
0x1800043ba  lea     rdx, ds:0[rax*8]; unsigned __int64
0x1800043c2  cmp     rdx, 1000h
0x1800043c9  jb      short loc_1800043E9
0x1800043cb  mov     rax, [rcx-8]
0x1800043cf  sub     rcx, rax
0x1800043d2  sub     rcx, 8
0x1800043d6  cmp     rcx, 1Fh
0x1800043da  ja      short loc_1800043E2
0x1800043dc  add     rdx, 27h ; '''
0x1800043e0  jmp     short loc_1800043EC
0x1800043e2  mov     ecx, 5
0x1800043e7  int     29h; Win8: RtlFailFast(ecx)
0x1800043e9  mov     rax, rcx
0x1800043ec  mov     rcx, rax; void *
0x1800043ef  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800043f4  mov     [rdi], rsi
0x1800043f7  lea     rax, [rsi+r15*8]
0x1800043fb  mov     [rdi+8], rax
0x1800043ff  lea     rax, [r14+rsi]
0x180004403  mov     [rdi+10h], rax
0x180004407  add     rsp, 58h
0x18000440b  pop     r15
0x18000440d  pop     r14
0x18000440f  pop     r13
0x180004411  pop     r12
0x180004413  pop     rdi
0x180004414  pop     rsi
0x180004415  pop     rbp
0x180004416  pop     rbx
0x180004417  retn
0x180004418  call    ?_Xlength@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@@2@@std@@CAXXZ; std::vector<std::pair<std::wstring,web::json::value>>::_Xlength(void)
0x18000441e  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
