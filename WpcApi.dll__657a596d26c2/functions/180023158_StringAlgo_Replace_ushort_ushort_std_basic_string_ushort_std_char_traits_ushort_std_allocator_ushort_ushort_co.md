# StringAlgo::Replace<ushort,ushort>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ushort const *,ushort const *)

- ea: `0x180023158`
- end: `0x180023459`
- name: `??$Replace@GG@StringAlgo@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@PEBG1@Z`
- size: `769`
- prototype: `__int64 __fastcall(__int64, _QWORD *, __int64, _WORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800236e0`

## callees

- `0x1800032a0`
- `0x1800045d0`
- `0x18000490d`
- `0x180004925`
- `0x180005f9c`
- `0x18001f530`
- `0x180023158`
- `0x1800234d0`

## pseudocode

```c
__int64 __fastcall StringAlgo::Replace<unsigned short,unsigned short>(__int64 a1, _QWORD *a2, __int64 a3, _WORD *a4)
{
  __int64 v5; // r11
  __int64 v8; // r10
  __int64 v9; // r8
  unsigned __int64 v10; // r15
  unsigned __int64 v11; // r9
  unsigned __int64 v12; // rcx
  _QWORD *v13; // rdi
  char *v14; // rbx
  __int64 v15; // rax
  _QWORD *v16; // rdx
  unsigned __int64 v17; // rcx
  _QWORD *v18; // rax
  unsigned __int64 v19; // r9
  unsigned __int64 v20; // rdx
  unsigned __int64 v21; // r14
  unsigned __int64 v22; // rbp
  _QWORD *v23; // rax
  unsigned __int64 v24; // r11
  _QWORD *v25; // rax
  char *v26; // rdi
  unsigned __int64 v27; // r10
  _QWORD *v28; // rcx
  char *v29; // r9
  __int64 v30; // rdi
  char *v32; // [rsp+40h] [rbp-88h]
  char *v33; // [rsp+40h] [rbp-88h]
  unsigned __int64 v34; // [rsp+48h] [rbp-80h]
  __int64 v35; // [rsp+50h] [rbp-78h]
  __int64 v36; // [rsp+58h] [rbp-70h]

  v5 = a3;
  v8 = -1;
  do
    ++v8;
  while ( *(_WORD *)(a3 + 2 * v8) );
  v36 = v8;
  v9 = -1;
  do
    ++v9;
  while ( a4[v9] );
  v35 = v9;
  v10 = 0;
  while ( 1 )
  {
    v11 = -1;
    do
      ++v11;
    while ( *(_WORD *)(v5 + 2 * v11) );
    v12 = a2[2];
    v13 = a2;
    if ( a2[3] > 7u )
      v13 = (_QWORD *)*a2;
    if ( v11 > v12 || v10 > v12 - v11 )
      break;
    if ( v11 )
    {
      v14 = (char *)v13 + 2 * v12;
      v15 = _std_search_2((char *)v13 + 2 * v10, v14, v5);
      if ( (char *)v15 == v14 )
        break;
      v10 = (v15 - (__int64)v13) >> 1;
      v9 = v35;
      v8 = v36;
    }
    if ( v10 == -1 )
      break;
    v16 = a2;
    v17 = a2[3];
    if ( v17 <= 7 )
    {
      v18 = a2;
    }
    else
    {
      v18 = (_QWORD *)*a2;
      v16 = (_QWORD *)*a2;
    }
    v19 = (__int64)((__int64)v16 + 2 * v10 - (_QWORD)v18) >> 1;
    v20 = a2[2];
    if ( v20 < v19 )
      std::_String_val<std::_Simple_types<unsigned short>>::_Xran();
    v21 = (2 * v9) >> 1;
    v22 = (2 * v8) >> 1;
    if ( v20 - v19 < v22 )
      v22 = v20 - v19;
    if ( v22 == v21 )
    {
      v23 = a2;
      if ( v17 > 7 )
        v23 = (_QWORD *)*a2;
      memmove_0((char *)v23 + 2 * v19, a4, 2 * v21);
    }
    else
    {
      v32 = (char *)(v20 - v22);
      v24 = v20 - v22 - v19;
      v34 = v24;
      if ( v21 >= v22 )
      {
        v27 = v21 - v22;
        if ( v21 - v22 > v17 - v20 )
        {
          std::wstring::_Reallocate_grow_by<_lambda_622fe101509e1fd0c758e599152cbb8b_,unsigned __int64,unsigned __int64,unsigned short const *,unsigned __int64>(
            a2,
            v22,
            a4,
            (2 * v9) >> 1);
        }
        else
        {
          a2[2] = v20 + v27;
          if ( v17 <= 7 )
            v28 = a2;
          else
            v28 = (_QWORD *)*a2;
          v33 = (char *)v28 + 2 * v19;
          v29 = &v33[2 * v22];
          if ( &a4[v21] <= (_WORD *)v33 || a4 > (_WORD *)v28 + v20 )
          {
            v30 = (2 * v9) >> 1;
          }
          else if ( v29 > (char *)a4 )
          {
            v30 = (v29 - (char *)a4) >> 1;
          }
          else
          {
            v30 = 0;
          }
          memmove_0(&v29[2 * v27], v29, 2 * v24 + 2);
          memmove_0(v33, a4, 2 * v30);
          memcpy_0(&v33[2 * v30], &a4[v30 + v21 - v22], 2 * (v21 - v30));
        }
      }
      else
      {
        v25 = a2;
        if ( v17 > 7 )
          v25 = (_QWORD *)*a2;
        v26 = (char *)v25 + 2 * v19;
        memmove_0(v26, a4, 2 * v21);
        memmove_0(&v26[2 * v21], &v26[2 * v22], 2 * v34 + 2);
        a2[2] = &v32[v21];
      }
    }
    v9 = v35;
    v10 += v35;
    v8 = v36;
    v5 = a3;
  }
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  *(_OWORD *)a1 = *(_OWORD *)a2;
  *(_OWORD *)(a1 + 16) = *((_OWORD *)a2 + 1);
  a2[2] = 0;
  a2[3] = 7;
  *(_WORD *)a2 = 0;
  std::wstring::~wstring(a2);
  return a1;
}

```

## disassembly

```asm
0x180023158  push    rbx
0x18002315a  push    rbp
0x18002315b  push    rsi
0x18002315c  push    rdi
0x18002315d  push    r12
0x18002315f  push    r13
0x180023161  push    r14
0x180023163  push    r15
0x180023165  sub     rsp, 88h
0x18002316c  mov     rax, cs:__security_cookie
0x180023173  xor     rax, rsp
0x180023176  mov     [rsp+0C8h+var_50], rax
0x18002317b  mov     r12, r9
0x18002317e  mov     r11, r8
0x180023181  mov     [rsp+0C8h+var_60], r8
0x180023186  mov     rsi, rdx
0x180023189  mov     r13, rcx
0x18002318c  mov     [rsp+0C8h+var_88], rcx
0x180023191  mov     [rsp+0C8h+var_58], rdx
0x180023196  xor     ebp, ebp
0x180023198  or      r14, 0FFFFFFFFFFFFFFFFh
0x18002319c  mov     r10, r14
0x18002319f  inc     r10
0x1800231a2  cmp     [r8+r10*2], bp
0x1800231a7  jnz     short loc_18002319F
0x1800231a9  mov     [rsp+0C8h+var_70], r10
0x1800231ae  mov     r8, r14
0x1800231b1  inc     r8
0x1800231b4  cmp     [r9+r8*2], bp
0x1800231b9  jnz     short loc_1800231B1
0x1800231bb  mov     [rsp+0C8h+var_78], r8
0x1800231c0  mov     r15, rbp
0x1800231c3  mov     r9, r14
0x1800231c6  inc     r9
0x1800231c9  cmp     [r11+r9*2], bp
0x1800231ce  jnz     short loc_1800231C6
0x1800231d0  mov     rcx, [rsi+10h]
0x1800231d4  mov     rdi, rsi
0x1800231d7  cmp     qword ptr [rsi+18h], 7
0x1800231dc  jbe     short loc_1800231E1
0x1800231de  mov     rdi, [rsi]
0x1800231e1  cmp     r9, rcx
0x1800231e4  ja      loc_1800233F7
0x1800231ea  mov     rax, rcx
0x1800231ed  sub     rax, r9
0x1800231f0  cmp     r15, rax
0x1800231f3  ja      loc_1800233F7
0x1800231f9  test    r9, r9
0x1800231fc  jz      short loc_18002322D
0x1800231fe  lea     rbx, [rdi+rcx*2]
0x180023202  lea     rcx, [rdi+r15*2]
0x180023206  mov     r8, r11
0x180023209  mov     rdx, rbx
0x18002320c  call    __std_search_2
0x180023211  mov     r15, rax
0x180023214  cmp     rax, rbx
0x180023217  jz      loc_1800233F7
0x18002321d  sub     r15, rdi
0x180023220  sar     r15, 1
0x180023223  mov     r8, [rsp+0C8h+var_78]
0x180023228  mov     r10, [rsp+0C8h+var_70]
0x18002322d  cmp     r15, r14
0x180023230  jz      loc_1800233F7
0x180023236  mov     rdx, rsi
0x180023239  mov     rcx, [rsi+18h]
0x18002323d  cmp     rcx, 7
0x180023241  jbe     short loc_18002324B
0x180023243  mov     rax, [rsi]
0x180023246  mov     rdx, rax
0x180023249  jmp     short loc_18002324E
0x18002324b  mov     rax, rsi
0x18002324e  lea     r9, [r15+r15]
0x180023252  sub     r9, rax
0x180023255  add     r9, rdx
0x180023258  sar     r9, 1
0x18002325b  mov     rdx, [rsi+10h]
0x18002325f  cmp     rdx, r9
0x180023262  jb      loc_180023453
0x180023268  lea     r14, [r8+r8]
0x18002326c  sar     r14, 1
0x18002326f  lea     rbp, [r10+r10]
0x180023273  sar     rbp, 1
0x180023276  mov     rax, rdx
0x180023279  sub     rax, r9
0x18002327c  cmp     rax, rbp
0x18002327f  cmovb   rbp, rax
0x180023283  cmp     rbp, r14
0x180023286  jnz     short loc_1800232A9
0x180023288  mov     rax, rsi
0x18002328b  cmp     rcx, 7
0x18002328f  jbe     short loc_180023294
0x180023291  mov     rax, [rsi]
0x180023294  lea     r8, [r14+r14]; Size
0x180023298  lea     rcx, [rax+r9*2]; void *
0x18002329c  mov     rdx, r12; Src
0x18002329f  call    memmove_0
0x1800232a4  jmp     loc_1800233DA
0x1800232a9  mov     rax, rdx
0x1800232ac  sub     rax, rbp
0x1800232af  mov     [rsp+0C8h+var_88], rax
0x1800232b4  mov     r11, rax
0x1800232b7  sub     r11, r9
0x1800232ba  mov     [rsp+0C8h+var_80], r11
0x1800232bf  cmp     r14, rbp
0x1800232c2  jnb     short loc_180023311
0x1800232c4  mov     rax, rsi
0x1800232c7  cmp     rcx, 7
0x1800232cb  jbe     short loc_1800232D0
0x1800232cd  mov     rax, [rsi]
0x1800232d0  lea     rdi, [rax+r9*2]
0x1800232d4  lea     rbx, [r14+r14]
0x1800232d8  mov     r8, rbx; Size
0x1800232db  mov     rdx, r12; Src
0x1800232de  mov     rcx, rdi; void *
0x1800232e1  call    memmove_0
0x1800232e6  mov     r8, [rsp+0C8h+var_80]
0x1800232eb  lea     r8, ds:2[r8*2]; Size
0x1800232f3  lea     rdx, [rdi+rbp*2]; Src
0x1800232f7  lea     rcx, [rdi+rbx]; void *
0x1800232fb  call    memmove_0
0x180023300  mov     rax, [rsp+0C8h+var_88]
0x180023305  add     rax, r14
0x180023308  mov     [rsi+10h], rax
0x18002330c  jmp     loc_1800233DA
0x180023311  mov     r10, r14
0x180023314  sub     r10, rbp
0x180023317  mov     [rsp+0C8h+var_80], r10
0x18002331c  mov     rax, rcx
0x18002331f  sub     rax, rdx
0x180023322  cmp     r10, rax
0x180023325  ja      loc_1800233C0
0x18002332b  lea     rax, [rdx+r10]
0x18002332f  mov     [rsi+10h], rax
0x180023333  cmp     rcx, 7
0x180023337  jbe     short loc_18002333E
0x180023339  mov     rcx, [rsi]
0x18002333c  jmp     short loc_180023341
0x18002333e  mov     rcx, rsi
0x180023341  lea     r8, [rcx+r9*2]
0x180023345  mov     [rsp+0C8h+var_88], r8
0x18002334a  lea     r9, [r8+rbp*2]
0x18002334e  lea     rax, [r12+r14*2]
0x180023352  cmp     rax, r8
0x180023355  jbe     short loc_180023374
0x180023357  lea     rax, [rcx+rdx*2]
0x18002335b  cmp     r12, rax
0x18002335e  ja      short loc_180023374
0x180023360  cmp     r9, r12
0x180023363  ja      short loc_180023369
0x180023365  xor     edi, edi
0x180023367  jmp     short loc_180023377
0x180023369  mov     rdi, r9
0x18002336c  sub     rdi, r12
0x18002336f  sar     rdi, 1
0x180023372  jmp     short loc_180023377
0x180023374  mov     rdi, r14
0x180023377  lea     r8, ds:2[r11*2]; Size
0x18002337f  lea     rcx, [r9+r10*2]; void *
0x180023383  mov     rdx, r9; Src
0x180023386  call    memmove_0
0x18002338b  lea     rbx, [rdi+rdi]
0x18002338f  mov     r8, rbx; Size
0x180023392  mov     rdx, r12; Src
0x180023395  mov     rbp, [rsp+0C8h+var_88]
0x18002339a  mov     rcx, rbp; void *
0x18002339d  call    memmove_0
0x1800233a2  sub     r14, rdi
0x1800233a5  lea     r8, [r14+r14]; Size
0x1800233a9  mov     rax, [rsp+0C8h+var_80]
0x1800233ae  add     rax, rdi
0x1800233b1  lea     rdx, [r12+rax*2]; Src
0x1800233b5  lea     rcx, [rbx+rbp]; void *
0x1800233b9  call    memcpy_0
0x1800233be  jmp     short loc_1800233DA
0x1800233c0  mov     [rsp+0C8h+var_98], r14; __int64
0x1800233c5  mov     [rsp+0C8h+var_A0], r12; void *
0x1800233ca  mov     [rsp+0C8h+var_A8], rbp; __int64
0x1800233cf  mov     rdx, r10
0x1800233d2  mov     rcx, rsi; Src
0x1800233d5  call    ??$_Reallocate_grow_by@V_lambda_622fe101509e1fd0c758e599152cbb8b_@@_K_KPEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_622fe101509e1fd0c758e599152cbb8b_@@_K2PEBG2@Z; std::wstring::_Reallocate_grow_by<_lambda_622fe101509e1fd0c758e599152cbb8b_,unsigned __int64,unsigned __int64,ushort const *,unsigned __int64>(unsigned __int64,_lambda_622fe101509e1fd0c758e599152cbb8b_,unsigned __int64,unsigned __int64,ushort const *,unsigned __int64)
0x1800233da  mov     r8, [rsp+0C8h+var_78]
0x1800233df  add     r15, r8
0x1800233e2  mov     r10, [rsp+0C8h+var_70]
0x1800233e7  mov     r11, [rsp+0C8h+var_60]
0x1800233ec  xor     ebp, ebp
0x1800233ee  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800233f2  jmp     loc_1800231C3
0x1800233f7  xorps   xmm0, xmm0
0x1800233fa  movups  xmmword ptr [r13+0], xmm0
0x1800233ff  mov     [r13+10h], rbp
0x180023403  mov     [r13+18h], rbp
0x180023407  movups  xmm0, xmmword ptr [rsi]
0x18002340a  movups  xmmword ptr [r13+0], xmm0
0x18002340f  movups  xmm1, xmmword ptr [rsi+10h]
0x180023413  movups  xmmword ptr [r13+10h], xmm1
0x180023418  mov     [rsi+10h], rbp
0x18002341c  mov     qword ptr [rsi+18h], 7
0x180023424  mov     [rsi], bp
0x180023427  mov     rcx, rsi
0x18002342a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002342f  mov     rax, r13
0x180023432  mov     rcx, [rsp+0C8h+var_50]
0x180023437  xor     rcx, rsp; StackCookie
0x18002343a  call    __security_check_cookie
0x18002343f  add     rsp, 88h
0x180023446  pop     r15
0x180023448  pop     r14
0x18002344a  pop     r13
0x18002344c  pop     r12
0x18002344e  pop     rdi
0x18002344f  pop     rsi
0x180023450  pop     rbp
0x180023451  pop     rbx
0x180023452  retn
0x180023453  call    ?_Xran@?$_String_val@U?$_Simple_types@G@std@@@std@@SAXXZ; std::_String_val<std::_Simple_types<ushort>>::_Xran(void)
```
