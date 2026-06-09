# std::basic_string<char,std::char_traits<char>,std::allocator<char>,_STL70>::replace(unsigned __int64,unsigned __int64,std::basic_string<char,std::char_traits<char>,std::allocator<char>,_STL70> const &,unsigned __int64,unsigned __int64)

- ea: `0x1800222b4`
- end: `0x180022642`
- name: `?replace@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@QEAAAEAV12@_K0AEBV12@00@Z`
- size: `910`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180020cc8`
- `0x180081fac`
- `0x1800bc80c`

## callees

- `0x1800208b0`
- `0x1800222b4`
- `0x1800cdb60`
- `0x1800cdbbc`

## import_xrefs

- `msvcrt!memmove_s` at `0x1800223a7`
- `msvcrt!memmove_s` at `0x180022466`
- `msvcrt!memmove_s` at `0x18002248b`
- `msvcrt!memmove_s` at `0x1800224ed`
- `msvcrt!memmove_s` at `0x18002253f`
- `msvcrt!memmove_s` at `0x180022580`
- `msvcrt!memmove_s` at `0x1800225ad`
- `msvcrt!memmove_s` at `0x1800223a7`
- `msvcrt!memmove_s` at `0x180022466`
- `msvcrt!memmove_s` at `0x18002248b`
- `msvcrt!memmove_s` at `0x1800224ed`
- `msvcrt!memmove_s` at `0x18002253f`
- `msvcrt!memmove_s` at `0x180022580`
- `msvcrt!memmove_s` at `0x1800225ad`
- `msvcrt!memcpy_s` at `0x1800223de`
- `msvcrt!memcpy_s` at `0x1800223de`

## pseudocode

```c
_QWORD *__fastcall std::string::replace(
        _QWORD *a1,
        unsigned __int64 a2,
        rsize_t a3,
        _QWORD *a4,
        unsigned __int64 a5,
        unsigned __int64 a6)
{
  rsize_t v6; // r14
  unsigned __int64 v9; // rdx
  rsize_t v10; // rbp
  unsigned __int64 v11; // rdx
  rsize_t v12; // rax
  rsize_t v13; // r13
  rsize_t v14; // r12
  _QWORD *v15; // rbx
  unsigned __int64 v16; // rdx
  _QWORD *v17; // rax
  _QWORD *v18; // rcx
  _QWORD *v19; // rcx
  unsigned __int64 v20; // rdx
  _QWORD *v21; // rax
  _QWORD *result; // rax
  _QWORD *v23; // rax
  _QWORD *v24; // rax
  _QWORD *v25; // r8
  char *v26; // r8
  rsize_t v27; // rdx
  char *v28; // rcx
  rsize_t v29; // r9
  _QWORD *v30; // rax
  _QWORD *v31; // rcx
  unsigned __int64 v32; // rdx
  _QWORD *v33; // rax
  _QWORD *v34; // rcx
  _QWORD *v35; // rax
  _QWORD *v36; // rcx
  unsigned __int64 v37; // rdx
  _QWORD *v38; // rcx
  _QWORD *v39; // rax
  _QWORD *v40; // rcx
  _QWORD *v41; // rax
  _QWORD *v42; // rcx
  unsigned __int64 v43; // rdx
  _QWORD *v44; // rax
  _QWORD *v45; // rcx
  unsigned __int64 v46; // rdx
  _QWORD *v47; // rax
  _QWORD *v48; // rcx

  v6 = a3;
  if ( a1[3] < a2 || (v9 = a4[3], v9 < a5) )
    std::_String_base::_Xran();
  v10 = a6;
  if ( a1[3] - a2 < a3 )
    v6 = a1[3] - a2;
  v11 = v9 - a5;
  if ( v11 < a6 )
    v10 = v11;
  if ( ~v10 <= a1[3] - v6 )
    std::_String_base::_Xlen();
  v12 = a1[3];
  v13 = v12 - a2 - v6;
  v14 = v10 - v6 + v12;
  if ( v12 < v14 )
  {
    if ( v14 == -1 )
      std::_String_base::_Xlen();
    if ( a1[4] < v14 )
    {
      std::string::_Copy(a1, v10 - v6 + v12, a1[3]);
    }
    else if ( !v14 )
    {
      v23 = a1 + 1;
      if ( a1[4] >= 0x10u )
        v23 = (_QWORD *)*v23;
      a1[3] = 0;
      *(_BYTE *)v23 = 0;
    }
  }
  v15 = a1 + 1;
  v16 = a1[4];
  if ( a1 == a4 )
  {
    if ( v10 <= v6 )
    {
      if ( v16 < 0x10 )
      {
        v30 = a1 + 1;
        v31 = a1 + 1;
      }
      else
      {
        v30 = (_QWORD *)*v15;
        v31 = (_QWORD *)*v15;
      }
      memmove_s((char *)v30 + a2, v16 - a2, (char *)v31 + a5, v10);
      v32 = a1[4];
      if ( v32 < 0x10 )
      {
        v33 = a1 + 1;
        v34 = a1 + 1;
      }
      else
      {
        v33 = (_QWORD *)*v15;
        v34 = (_QWORD *)*v15;
      }
      v26 = (char *)v34 + a2 + v6;
      v27 = v32 - a2 - v10;
      v29 = v13;
      v28 = (char *)v33 + a2 + v10;
      goto LABEL_32;
    }
    if ( a5 <= a2 )
    {
      if ( v16 < 0x10 )
      {
        v35 = a1 + 1;
        v36 = a1 + 1;
      }
      else
      {
        v35 = (_QWORD *)*v15;
        v36 = (_QWORD *)*v15;
      }
      memmove_s((char *)v35 + a2 + v10, v16 - a2 - v10, (char *)v36 + a2 + v6, v13);
      v37 = a1[4];
      if ( v37 < 0x10 )
      {
        v24 = a1 + 1;
        v38 = a1 + 1;
      }
      else
      {
        v24 = (_QWORD *)*v15;
        v38 = (_QWORD *)*v15;
      }
      v26 = (char *)v38 + a5;
    }
    else
    {
      if ( a2 + v6 > a5 )
      {
        if ( v16 < 0x10 )
        {
          v41 = a1 + 1;
          v42 = a1 + 1;
        }
        else
        {
          v41 = (_QWORD *)*v15;
          v42 = (_QWORD *)*v15;
        }
        memmove_s((char *)v41 + a2, v16 - a2, (char *)v42 + a5, v6);
        v43 = a1[4];
        if ( v43 < 0x10 )
        {
          v44 = a1 + 1;
          v45 = a1 + 1;
        }
        else
        {
          v44 = (_QWORD *)*v15;
          v45 = (_QWORD *)*v15;
        }
        memmove_s((char *)v44 + a2 + v10, v43 - a2 - v10, (char *)v45 + a2 + v6, v13);
        v46 = a1[4];
        if ( v46 < 0x10 )
        {
          v47 = a1 + 1;
          v48 = a1 + 1;
        }
        else
        {
          v47 = (_QWORD *)*v15;
          v48 = (_QWORD *)*v15;
        }
        v29 = v10 - v6;
        v26 = (char *)v48 + a5 + v10;
        v27 = v46 - a2 - v6;
        v28 = (char *)v47 + a2 + v6;
        goto LABEL_32;
      }
      if ( v16 < 0x10 )
      {
        v39 = a1 + 1;
        v40 = a1 + 1;
      }
      else
      {
        v39 = (_QWORD *)*v15;
        v40 = (_QWORD *)*v15;
      }
      memmove_s((char *)v39 + a2 + v10, v16 - a2 - v10, (char *)v40 + a2 + v6, v13);
      v37 = a1[4];
      if ( v37 >= 0x10 )
      {
        v24 = (_QWORD *)*v15;
        v25 = (_QWORD *)*v15;
      }
      else
      {
        v24 = a1 + 1;
        v25 = a1 + 1;
      }
      v26 = (char *)v25 + a5 - v6 + v10;
    }
    v27 = v37 - a2;
    v28 = (char *)v24 + a2;
    v29 = v10;
LABEL_32:
    memmove_s(v28, v27, v26, v29);
    goto LABEL_20;
  }
  if ( v16 < 0x10 )
  {
    v17 = a1 + 1;
    v18 = a1 + 1;
  }
  else
  {
    v17 = (_QWORD *)*v15;
    v18 = (_QWORD *)*v15;
  }
  memmove_s((char *)v17 + a2 + v10, v16 - a2 - v10, (char *)v18 + a2 + v6, v13);
  v19 = a4 + 1;
  if ( a4[4] >= 0x10u )
    v19 = (_QWORD *)*v19;
  v20 = a1[4];
  if ( v20 < 0x10 )
    v21 = a1 + 1;
  else
    v21 = (_QWORD *)*v15;
  memcpy_s((char *)v21 + a2, v20 - a2, (char *)v19 + a5, v10);
LABEL_20:
  if ( a1[4] >= 0x10u )
    v15 = (_QWORD *)*v15;
  a1[3] = v14;
  result = a1;
  *((_BYTE *)v15 + v14) = 0;
  return result;
}

```

## disassembly

```asm
0x1800222b4  mov     [rsp+arg_18], r9
0x1800222b9  push    rbx
0x1800222ba  push    rbp
0x1800222bb  push    rsi
0x1800222bc  push    rdi
0x1800222bd  push    r12
0x1800222bf  push    r13
0x1800222c1  push    r14
0x1800222c3  push    r15
0x1800222c5  sub     rsp, 28h
0x1800222c9  mov     rbx, r9
0x1800222cc  mov     r15, [rsp+68h+arg_20]
0x1800222d4  mov     r14, r8
0x1800222d7  mov     rsi, rdx
0x1800222da  mov     rdi, rcx
0x1800222dd  cmp     [rcx+18h], rdx
0x1800222e1  jb      loc_1800225FC
0x1800222e7  mov     rdx, [r9+18h]
0x1800222eb  cmp     rdx, r15
0x1800222ee  jb      loc_1800225FC
0x1800222f4  mov     rcx, [rdi+18h]
0x1800222f8  mov     rbp, [rsp+68h+arg_28]
0x180022300  mov     rax, rcx
0x180022303  sub     rax, rsi
0x180022306  cmp     rax, r14
0x180022309  cmovb   r14, rax
0x18002230d  sub     rdx, r15
0x180022310  cmp     rdx, rbp
0x180022313  cmovb   rbp, rdx
0x180022317  sub     rcx, r14
0x18002231a  mov     rax, rbp
0x18002231d  not     rax
0x180022320  cmp     rax, rcx
0x180022323  jbe     loc_18002260A
0x180022329  mov     rax, [rdi+18h]
0x18002232d  mov     rcx, rbp
0x180022330  sub     rcx, r14
0x180022333  mov     r13, rax
0x180022336  sub     r13, rsi
0x180022339  mov     [rsp+68h+arg_20], rcx
0x180022341  sub     r13, r14
0x180022344  lea     r12, [rcx+rax]
0x180022348  cmp     rax, r12
0x18002234b  jnb     short loc_18002236A
0x18002234d  cmp     r12, 0FFFFFFFFFFFFFFFEh
0x180022351  ja      loc_180022614
0x180022357  cmp     [rdi+20h], r12
0x18002235b  jb      loc_18002241B
0x180022361  test    r12, r12
0x180022364  jz      loc_18002242F
0x18002236a  lea     rbx, [rdi+8]
0x18002236e  mov     rdx, [rdi+20h]
0x180022372  cmp     rdi, [rsp+68h+arg_18]
0x18002237a  jz      loc_18002261E
0x180022380  cmp     rdx, 10h
0x180022384  jb      loc_18002240B
0x18002238a  mov     rax, [rbx]
0x18002238d  mov     rcx, rax
0x180022390  lea     r8, [rcx+rsi]
0x180022394  sub     rdx, rsi
0x180022397  lea     rcx, [rax+rsi]
0x18002239b  add     r8, r14; Source
0x18002239e  add     rcx, rbp; Destination
0x1800223a1  sub     rdx, rbp; DestinationSize
0x1800223a4  mov     r9, r13; SourceSize
0x1800223a7  call    cs:__imp_memmove_s
0x1800223ad  mov     rax, [rsp+68h+arg_18]
0x1800223b5  cmp     qword ptr [rax+20h], 10h
0x1800223ba  lea     rcx, [rax+8]
0x1800223be  jb      short loc_1800223C3
0x1800223c0  mov     rcx, [rcx]
0x1800223c3  mov     rdx, [rdi+20h]
0x1800223c7  cmp     rdx, 10h
0x1800223cb  jb      short loc_180022416
0x1800223cd  mov     rax, [rbx]
0x1800223d0  lea     r8, [rcx+r15]; Source
0x1800223d4  sub     rdx, rsi; DestinationSize
0x1800223d7  lea     rcx, [rax+rsi]; Destination
0x1800223db  mov     r9, rbp; SourceSize
0x1800223de  call    cs:__imp_memcpy_s
0x1800223e4  cmp     qword ptr [rdi+20h], 10h
0x1800223e9  jb      short loc_1800223EE
0x1800223eb  mov     rbx, [rbx]
0x1800223ee  mov     [rdi+18h], r12
0x1800223f2  mov     rax, rdi
0x1800223f5  mov     byte ptr [rbx+r12], 0
0x1800223fa  add     rsp, 28h
0x1800223fe  pop     r15
0x180022400  pop     r14
0x180022402  pop     r13
0x180022404  pop     r12
0x180022406  pop     rdi
0x180022407  pop     rsi
0x180022408  pop     rbp
0x180022409  pop     rbx
0x18002240a  retn
0x18002240b  mov     rax, rbx
0x18002240e  mov     rcx, rbx
0x180022411  jmp     loc_180022390
0x180022416  mov     rax, rbx
0x180022419  jmp     short loc_1800223D0
0x18002241b  mov     r8, [rdi+18h]
0x18002241f  mov     rdx, r12
0x180022422  mov     rcx, rdi
0x180022425  call    ?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@IEAAX_K0@Z; std::string::_Copy(unsigned __int64,unsigned __int64)
0x18002242a  jmp     loc_18002236A
0x18002242f  cmp     qword ptr [rdi+20h], 10h
0x180022434  lea     rax, [rdi+8]
0x180022438  jb      short loc_18002243D
0x18002243a  mov     rax, [rax]
0x18002243d  mov     qword ptr [rdi+18h], 0
0x180022445  mov     byte ptr [rax], 0
0x180022448  jmp     loc_18002236A
0x18002244d  mov     rax, [rbx]
0x180022450  mov     r8, rax
0x180022453  sub     r8, r14
0x180022456  add     r8, r15
0x180022459  add     r8, rbp; Source
0x18002245c  sub     rdx, rsi; DestinationSize
0x18002245f  lea     rcx, [rax+rsi]; Destination
0x180022463  mov     r9, rbp; SourceSize
0x180022466  call    cs:__imp_memmove_s
0x18002246c  jmp     loc_1800223E4
0x180022471  cmp     rdx, 10h
0x180022475  jb      short loc_1800224BA
0x180022477  mov     rax, [rbx]
0x18002247a  mov     rcx, rax
0x18002247d  lea     r8, [rcx+r15]; Source
0x180022481  sub     rdx, rsi; DestinationSize
0x180022484  lea     rcx, [rax+rsi]; Destination
0x180022488  mov     r9, rbp; SourceSize
0x18002248b  call    cs:__imp_memmove_s
0x180022491  mov     rdx, [rdi+20h]
0x180022495  cmp     rdx, 10h
0x180022499  jb      short loc_1800224C2
0x18002249b  mov     rax, [rbx]
0x18002249e  mov     rcx, rax
0x1800224a1  lea     r8, [rcx+rsi]
0x1800224a5  sub     rdx, rsi
0x1800224a8  add     r8, r14
0x1800224ab  lea     rcx, [rax+rsi]
0x1800224af  sub     rdx, rbp
0x1800224b2  mov     r9, r13
0x1800224b5  add     rcx, rbp
0x1800224b8  jmp     short loc_180022466
0x1800224ba  mov     rax, rbx
0x1800224bd  mov     rcx, rbx
0x1800224c0  jmp     short loc_18002247D
0x1800224c2  mov     rax, rbx
0x1800224c5  mov     rcx, rbx
0x1800224c8  jmp     short loc_1800224A1
0x1800224ca  cmp     rdx, 10h
0x1800224ce  jb      short loc_18002250C
0x1800224d0  mov     rax, [rbx]
0x1800224d3  mov     rcx, rax
0x1800224d6  lea     r8, [rcx+rsi]
0x1800224da  sub     rdx, rsi
0x1800224dd  lea     rcx, [rax+rsi]
0x1800224e1  add     r8, r14; Source
0x1800224e4  add     rcx, rbp; Destination
0x1800224e7  sub     rdx, rbp; DestinationSize
0x1800224ea  mov     r9, r13; SourceSize
0x1800224ed  call    cs:__imp_memmove_s
0x1800224f3  mov     rdx, [rdi+20h]
0x1800224f7  cmp     rdx, 10h
0x1800224fb  jb      short loc_180022514
0x1800224fd  mov     rax, [rbx]
0x180022500  mov     rcx, rax
0x180022503  lea     r8, [rcx+r15]
0x180022507  jmp     loc_18002245C
0x18002250c  mov     rax, rbx
0x18002250f  mov     rcx, rbx
0x180022512  jmp     short loc_1800224D6
0x180022514  mov     rax, rbx
0x180022517  mov     rcx, rbx
0x18002251a  jmp     short loc_180022503
0x18002251c  cmp     rdx, 10h
0x180022520  jb      short loc_18002255E
0x180022522  mov     rax, [rbx]
0x180022525  mov     rcx, rax
0x180022528  lea     r8, [rcx+rsi]
0x18002252c  sub     rdx, rsi
0x18002252f  lea     rcx, [rax+rsi]
0x180022533  add     r8, r14; Source
0x180022536  add     rcx, rbp; Destination
0x180022539  sub     rdx, rbp; DestinationSize
0x18002253c  mov     r9, r13; SourceSize
0x18002253f  call    cs:__imp_memmove_s
0x180022545  mov     rdx, [rdi+20h]
0x180022549  cmp     rdx, 10h
0x18002254d  jnb     loc_18002244D
0x180022553  mov     rax, rbx
0x180022556  mov     r8, rbx
0x180022559  jmp     loc_180022453
0x18002255e  mov     rax, rbx
0x180022561  mov     rcx, rbx
0x180022564  jmp     short loc_180022528
0x180022566  cmp     rdx, 10h
0x18002256a  jb      short loc_1800225E4
0x18002256c  mov     rax, [rbx]
0x18002256f  mov     rcx, rax
0x180022572  lea     r8, [rcx+r15]; Source
0x180022576  sub     rdx, rsi; DestinationSize
0x180022579  lea     rcx, [rax+rsi]; Destination
0x18002257d  mov     r9, r14; SourceSize
0x180022580  call    cs:__imp_memmove_s
0x180022586  mov     rdx, [rdi+20h]
0x18002258a  cmp     rdx, 10h
0x18002258e  jb      short loc_1800225EC
0x180022590  mov     rax, [rbx]
0x180022593  mov     rcx, rax
0x180022596  lea     r8, [rcx+rsi]
0x18002259a  sub     rdx, rsi
0x18002259d  lea     rcx, [rax+rsi]
0x1800225a1  add     r8, r14; Source
0x1800225a4  add     rcx, rbp; Destination
0x1800225a7  sub     rdx, rbp; DestinationSize
0x1800225aa  mov     r9, r13; SourceSize
0x1800225ad  call    cs:__imp_memmove_s
0x1800225b3  mov     rdx, [rdi+20h]
0x1800225b7  cmp     rdx, 10h
0x1800225bb  jb      short loc_1800225F4
0x1800225bd  mov     rax, [rbx]
0x1800225c0  mov     rcx, rax
0x1800225c3  mov     r9, [rsp+68h+arg_20]
0x1800225cb  lea     r8, [rcx+r15]
0x1800225cf  sub     rdx, rsi
0x1800225d2  lea     rcx, [rax+rsi]
0x1800225d6  add     r8, rbp
0x1800225d9  sub     rdx, r14
0x1800225dc  add     rcx, r14
0x1800225df  jmp     loc_180022466
0x1800225e4  mov     rax, rbx
0x1800225e7  mov     rcx, rbx
0x1800225ea  jmp     short loc_180022572
0x1800225ec  mov     rax, rbx
0x1800225ef  mov     rcx, rbx
0x1800225f2  jmp     short loc_180022596
0x1800225f4  mov     rax, rbx
0x1800225f7  mov     rcx, rbx
0x1800225fa  jmp     short loc_1800225C3
0x1800225fc  call    ?_Xran@_String_base@std@@SAXXZ; std::_String_base::_Xran(void)
0x180022601  mov     rdx, [rbx+18h]
0x180022605  jmp     loc_1800222F4
0x18002260a  call    ?_Xlen@_String_base@std@@SAXXZ; std::_String_base::_Xlen(void)
0x18002260f  jmp     loc_180022329
0x180022614  call    ?_Xlen@_String_base@std@@SAXXZ; std::_String_base::_Xlen(void)
0x180022619  jmp     loc_180022357
0x18002261e  cmp     rbp, r14
0x180022621  jbe     loc_180022471
0x180022627  cmp     r15, rsi
0x18002262a  jbe     loc_1800224CA
0x180022630  lea     rax, [rsi+r14]
0x180022634  cmp     rax, r15
0x180022637  ja      loc_180022566
0x18002263d  jmp     loc_18002251C
```
