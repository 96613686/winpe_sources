# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::replace(unsigned __int64,unsigned __int64,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,unsigned __int64,unsigned __int64)

- ea: `0x14000b7a0`
- end: `0x14000ba58`
- name: `?replace@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_K0AEBV12@00@Z`
- size: `696`
- prototype: `_QWORD *__fastcall(_QWORD *, unsigned __int64, unsigned __int64, _QWORD *, unsigned __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x14000fbd8`

## callees

- `0x14000829c`
- `0x140008568`
- `0x14000865c`
- `0x14000b7a0`

## import_xrefs

- `msvcp110_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x14000ba51`
- `msvcp110_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x14000ba51`
- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x14000b816`
- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x14000b816`

## pseudocode

```c
_QWORD *__fastcall std::wstring::replace(
        _QWORD *a1,
        unsigned __int64 a2,
        unsigned __int64 a3,
        _QWORD *a4,
        unsigned __int64 a5,
        unsigned __int64 a6)
{
  _QWORD *v7; // r15
  unsigned __int64 v8; // rdx
  unsigned __int64 v9; // r14
  unsigned __int64 v11; // rax
  unsigned __int64 v12; // rsi
  unsigned __int64 v13; // rbp
  unsigned __int64 v14; // rax
  __int64 v15; // r12
  __int64 v16; // r13
  unsigned __int64 v17; // rax
  _QWORD *v18; // rcx
  _QWORD *v19; // rdx
  _QWORD *v20; // rax
  _QWORD *v21; // rax
  _QWORD *v22; // rcx
  _QWORD *v23; // rcx
  _QWORD *v24; // rdx
  __int64 v25; // r8
  char *v26; // rdx
  char *v27; // rcx
  _QWORD *v28; // rcx
  _QWORD *v29; // rdx
  _QWORD *v30; // rax
  _QWORD *v31; // rcx
  unsigned __int64 v32; // r15
  _QWORD *v33; // rcx
  _QWORD *v34; // rax
  _QWORD *v35; // rax
  _QWORD *v36; // rcx
  __int64 v37; // r14
  _QWORD *v38; // rax
  _QWORD *v39; // rcx
  _QWORD *v40; // rcx
  _QWORD *v41; // rdx
  _QWORD *v42; // rax
  unsigned __int64 v44; // [rsp+70h] [rbp+8h]

  v7 = a4;
  v8 = a1[2];
  v9 = a3;
  if ( v8 < a2 || (v11 = a4[2], v12 = a5, v11 < a5) )
  {
    std::_Xout_of_range("invalid string position");
    JUMPOUT(0x14000BA57LL);
  }
  v13 = a6;
  if ( v8 - a2 < a3 )
    v9 = v8 - a2;
  v14 = v11 - a5;
  if ( v14 < a6 )
    v13 = v14;
  if ( ~v13 <= v8 - v9 )
    std::_Xlength_error("string too long");
  v15 = v8 - a2 - v9;
  v16 = v13 - v9;
  v44 = v8 + v13 - v9;
  if ( v8 < v44 )
    std::wstring::_Grow(a1, v8 + v13 - v9, 0);
  v17 = a1[3];
  if ( a1 == v7 )
  {
    if ( v13 > v9 )
    {
      if ( a5 > a2 )
      {
        v32 = a2 + v9;
        if ( a2 + v9 > a5 )
        {
          if ( v17 < 8 )
          {
            v35 = a1;
            v36 = a1;
          }
          else
          {
            v35 = (_QWORD *)*a1;
            v36 = (_QWORD *)*a1;
          }
          std::char_traits<unsigned short>::move((char *)v35 + 2 * a2, (char *)v36 + 2 * a5, v9);
          v37 = 2 * v32;
          if ( a1[3] < 8u )
          {
            v39 = a1;
            v38 = a1;
          }
          else
          {
            v38 = (_QWORD *)*a1;
            v39 = (_QWORD *)*a1;
          }
          std::char_traits<unsigned short>::move((char *)v39 + 2 * a2 + 2 * v13, (char *)v38 + v37, v15);
          if ( a1[3] < 8u )
          {
            v40 = a1;
            v41 = a1;
          }
          else
          {
            v40 = (_QWORD *)*a1;
            v41 = (_QWORD *)*a1;
          }
          v27 = (char *)v40 + v37;
          v26 = (char *)v41 + 2 * a5 + 2 * v13;
          v25 = v16;
          goto LABEL_55;
        }
        if ( v17 < 8 )
        {
          v33 = a1;
          v34 = a1;
        }
        else
        {
          v33 = (_QWORD *)*a1;
          v34 = (_QWORD *)*a1;
        }
        std::char_traits<unsigned short>::move((char *)v33 + 2 * a2 + 2 * v13, (char *)v34 + 2 * v32, v15);
        if ( a1[3] < 8u )
        {
          v30 = a1;
          v31 = a1;
        }
        else
        {
          v30 = (_QWORD *)*a1;
          v31 = (_QWORD *)*a1;
        }
        v12 = v13 + a5 - v9;
      }
      else
      {
        if ( v17 < 8 )
        {
          v28 = a1;
          v29 = a1;
        }
        else
        {
          v28 = (_QWORD *)*a1;
          v29 = (_QWORD *)*a1;
        }
        std::char_traits<unsigned short>::move((char *)v28 + 2 * a2 + 2 * v13, (char *)v29 + 2 * a2 + 2 * v9, v15);
        if ( a1[3] < 8u )
        {
          v30 = a1;
          v31 = a1;
        }
        else
        {
          v30 = (_QWORD *)*a1;
          v31 = (_QWORD *)*a1;
        }
      }
      v26 = (char *)v31 + 2 * v12;
      v25 = v13;
      v27 = (char *)v30 + 2 * a2;
    }
    else
    {
      if ( v17 < 8 )
      {
        v21 = a1;
        v22 = a1;
      }
      else
      {
        v21 = (_QWORD *)*a1;
        v22 = (_QWORD *)*a1;
      }
      std::char_traits<unsigned short>::move((char *)v21 + 2 * a2, (char *)v22 + 2 * a5, v13);
      if ( a1[3] < 8u )
      {
        v23 = a1;
        v24 = a1;
      }
      else
      {
        v23 = (_QWORD *)*a1;
        v24 = (_QWORD *)*a1;
      }
      v25 = v15;
      v26 = (char *)v24 + 2 * a2 + 2 * v9;
      v27 = (char *)v23 + 2 * a2 + 2 * v13;
    }
LABEL_55:
    std::char_traits<unsigned short>::move(v27, v26, v25);
    goto LABEL_56;
  }
  if ( v17 < 8 )
  {
    v18 = a1;
    v19 = a1;
  }
  else
  {
    v18 = (_QWORD *)*a1;
    v19 = (_QWORD *)*a1;
  }
  std::char_traits<unsigned short>::move((char *)v18 + 2 * a2 + 2 * v13, (char *)v19 + 2 * a2 + 2 * v9, v15);
  if ( v7[3] >= 8u )
    v7 = (_QWORD *)*v7;
  if ( a1[3] < 8u )
    v20 = a1;
  else
    v20 = (_QWORD *)*a1;
  std::char_traits<unsigned short>::copy((char *)v20 + 2 * a2, (char *)v7 + 2 * a5, v13);
LABEL_56:
  if ( a1[3] < 8u )
    v42 = a1;
  else
    v42 = (_QWORD *)*a1;
  a1[2] = v44;
  *((_WORD *)v42 + v44) = 0;
  return a1;
}

```

## disassembly

```asm
0x14000b7a0  push    rbx
0x14000b7a2  push    rbp
0x14000b7a3  push    rsi
0x14000b7a4  push    rdi
0x14000b7a5  push    r12
0x14000b7a7  push    r13
0x14000b7a9  push    r14
0x14000b7ab  push    r15
0x14000b7ad  sub     rsp, 28h
0x14000b7b1  mov     rdi, rdx
0x14000b7b4  mov     r15, r9
0x14000b7b7  mov     rdx, [rcx+10h]
0x14000b7bb  mov     r14, r8
0x14000b7be  mov     rbx, rcx
0x14000b7c1  cmp     rdx, rdi
0x14000b7c4  jb      loc_14000BA4A
0x14000b7ca  mov     rax, [r9+10h]
0x14000b7ce  mov     rsi, [rsp+68h+arg_20]
0x14000b7d6  cmp     rax, rsi
0x14000b7d9  jb      loc_14000BA4A
0x14000b7df  mov     rbp, [rsp+68h+arg_28]
0x14000b7e7  mov     r12, rdx
0x14000b7ea  sub     r12, rdi
0x14000b7ed  mov     rcx, rdx
0x14000b7f0  cmp     r12, r8
0x14000b7f3  cmovb   r14, r12
0x14000b7f7  sub     rax, rsi
0x14000b7fa  cmp     rax, rbp
0x14000b7fd  cmovb   rbp, rax
0x14000b801  sub     rcx, r14
0x14000b804  mov     rax, rbp
0x14000b807  not     rax
0x14000b80a  cmp     rax, rcx
0x14000b80d  ja      short loc_14000B81D
0x14000b80f  lea     rcx, aStringTooLong; "string too long"
0x14000b816  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x14000b81d  mov     r13, rbp
0x14000b820  sub     r12, r14
0x14000b823  sub     r13, r14
0x14000b826  lea     rax, [rdx+r13]
0x14000b82a  mov     [rsp+68h+arg_0], rax
0x14000b82f  cmp     rdx, rax
0x14000b832  jnb     short loc_14000B842
0x14000b834  xor     r8d, r8d
0x14000b837  mov     rdx, rax
0x14000b83a  mov     rcx, rbx
0x14000b83d  call    ?_Grow@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA_N_K_N@Z; std::wstring::_Grow(unsigned __int64,bool)
0x14000b842  mov     rax, [rbx+18h]
0x14000b846  cmp     rbx, r15
0x14000b849  jz      short loc_14000B8A5
0x14000b84b  cmp     rax, 8
0x14000b84f  jb      short loc_14000B859
0x14000b851  mov     rcx, [rbx]
0x14000b854  mov     rdx, rcx
0x14000b857  jmp     short loc_14000B85F
0x14000b859  mov     rcx, rbx
0x14000b85c  mov     rdx, rbx
0x14000b85f  lea     rax, [rdi+r14]
0x14000b863  mov     r8, r12
0x14000b866  lea     rdx, [rdx+rax*2]
0x14000b86a  lea     rax, [rdi+rbp]
0x14000b86e  lea     rcx, [rcx+rax*2]
0x14000b872  call    ?move@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z; std::char_traits<ushort>::move(ushort *,ushort const *,unsigned __int64)
0x14000b877  cmp     qword ptr [r15+18h], 8
0x14000b87c  jb      short loc_14000B881
0x14000b87e  mov     r15, [r15]
0x14000b881  cmp     qword ptr [rbx+18h], 8
0x14000b886  jb      short loc_14000B88D
0x14000b888  mov     rax, [rbx]
0x14000b88b  jmp     short loc_14000B890
0x14000b88d  mov     rax, rbx
0x14000b890  lea     rdx, [r15+rsi*2]
0x14000b894  mov     r8, rbp
0x14000b897  lea     rcx, [rax+rdi*2]
0x14000b89b  call    ?copy@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z; std::char_traits<ushort>::copy(ushort *,ushort const *,unsigned __int64)
0x14000b8a0  jmp     loc_14000BA18
0x14000b8a5  cmp     rbp, r14
0x14000b8a8  ja      short loc_14000B8FB
0x14000b8aa  cmp     rax, 8
0x14000b8ae  jb      short loc_14000B8B8
0x14000b8b0  mov     rax, [rbx]
0x14000b8b3  mov     rcx, rax
0x14000b8b6  jmp     short loc_14000B8BE
0x14000b8b8  mov     rax, rbx
0x14000b8bb  mov     rcx, rbx
0x14000b8be  lea     rdx, [rcx+rsi*2]
0x14000b8c2  mov     r8, rbp
0x14000b8c5  lea     rcx, [rax+rdi*2]
0x14000b8c9  call    ?move@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z; std::char_traits<ushort>::move(ushort *,ushort const *,unsigned __int64)
0x14000b8ce  cmp     qword ptr [rbx+18h], 8
0x14000b8d3  jb      short loc_14000B8DD
0x14000b8d5  mov     rcx, [rbx]
0x14000b8d8  mov     rdx, rcx
0x14000b8db  jmp     short loc_14000B8E3
0x14000b8dd  mov     rcx, rbx
0x14000b8e0  mov     rdx, rbx
0x14000b8e3  lea     rax, [rdi+r14]
0x14000b8e7  mov     r8, r12
0x14000b8ea  lea     rdx, [rdx+rax*2]
0x14000b8ee  lea     rax, [rdi+rbp]
0x14000b8f2  lea     rcx, [rcx+rax*2]
0x14000b8f6  jmp     loc_14000BA13
0x14000b8fb  cmp     rsi, rdi
0x14000b8fe  ja      short loc_14000B951
0x14000b900  cmp     rax, 8
0x14000b904  jb      short loc_14000B90E
0x14000b906  mov     rcx, [rbx]
0x14000b909  mov     rdx, rcx
0x14000b90c  jmp     short loc_14000B914
0x14000b90e  mov     rcx, rbx
0x14000b911  mov     rdx, rbx
0x14000b914  lea     rax, [rdi+r14]
0x14000b918  mov     r8, r12
0x14000b91b  lea     rdx, [rdx+rax*2]
0x14000b91f  lea     rax, [rdi+rbp]
0x14000b923  lea     rcx, [rcx+rax*2]
0x14000b927  call    ?move@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z; std::char_traits<ushort>::move(ushort *,ushort const *,unsigned __int64)
0x14000b92c  cmp     qword ptr [rbx+18h], 8
0x14000b931  jb      short loc_14000B93B
0x14000b933  mov     rax, [rbx]
0x14000b936  mov     rcx, rax
0x14000b939  jmp     short loc_14000B941
0x14000b93b  mov     rax, rbx
0x14000b93e  mov     rcx, rbx
0x14000b941  lea     rdx, [rcx+rsi*2]
0x14000b945  mov     r8, rbp
0x14000b948  lea     rcx, [rax+rdi*2]
0x14000b94c  jmp     loc_14000BA13
0x14000b951  lea     r15, [rdi+r14]
0x14000b955  cmp     r15, rsi
0x14000b958  ja      short loc_14000B99F
0x14000b95a  cmp     rax, 8
0x14000b95e  jb      short loc_14000B968
0x14000b960  mov     rcx, [rbx]
0x14000b963  mov     rax, rcx
0x14000b966  jmp     short loc_14000B96E
0x14000b968  mov     rcx, rbx
0x14000b96b  mov     rax, rbx
0x14000b96e  lea     rdx, [rax+r15*2]
0x14000b972  mov     r8, r12
0x14000b975  lea     rax, [rdi+rbp]
0x14000b979  lea     rcx, [rcx+rax*2]
0x14000b97d  call    ?move@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z; std::char_traits<ushort>::move(ushort *,ushort const *,unsigned __int64)
0x14000b982  cmp     qword ptr [rbx+18h], 8
0x14000b987  jb      short loc_14000B991
0x14000b989  mov     rax, [rbx]
0x14000b98c  mov     rcx, rax
0x14000b98f  jmp     short loc_14000B997
0x14000b991  mov     rax, rbx
0x14000b994  mov     rcx, rbx
0x14000b997  sub     rsi, r14
0x14000b99a  add     rsi, rbp
0x14000b99d  jmp     short loc_14000B941
0x14000b99f  cmp     rax, 8
0x14000b9a3  jb      short loc_14000B9AD
0x14000b9a5  mov     rax, [rbx]
0x14000b9a8  mov     rcx, rax
0x14000b9ab  jmp     short loc_14000B9B3
0x14000b9ad  mov     rax, rbx
0x14000b9b0  mov     rcx, rbx
0x14000b9b3  lea     rdx, [rcx+rsi*2]
0x14000b9b7  mov     r8, r14
0x14000b9ba  lea     rcx, [rax+rdi*2]
0x14000b9be  call    ?move@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z; std::char_traits<ushort>::move(ushort *,ushort const *,unsigned __int64)
0x14000b9c3  cmp     qword ptr [rbx+18h], 8
0x14000b9c8  lea     r14, [r15+r15]
0x14000b9cc  jb      short loc_14000B9D6
0x14000b9ce  mov     rax, [rbx]
0x14000b9d1  mov     rcx, rax
0x14000b9d4  jmp     short loc_14000B9DC
0x14000b9d6  mov     rcx, rbx
0x14000b9d9  mov     rax, rbx
0x14000b9dc  lea     rdx, [r14+rax]
0x14000b9e0  mov     r8, r12
0x14000b9e3  lea     rax, [rdi+rbp]
0x14000b9e7  lea     rcx, [rcx+rax*2]
0x14000b9eb  call    ?move@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z; std::char_traits<ushort>::move(ushort *,ushort const *,unsigned __int64)
0x14000b9f0  cmp     qword ptr [rbx+18h], 8
0x14000b9f5  jb      short loc_14000B9FF
0x14000b9f7  mov     rcx, [rbx]
0x14000b9fa  mov     rdx, rcx
0x14000b9fd  jmp     short loc_14000BA05
0x14000b9ff  mov     rcx, rbx
0x14000ba02  mov     rdx, rbx
0x14000ba05  lea     rax, [rsi+rbp]
0x14000ba09  add     rcx, r14
0x14000ba0c  lea     rdx, [rdx+rax*2]
0x14000ba10  mov     r8, r13
0x14000ba13  call    ?move@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z; std::char_traits<ushort>::move(ushort *,ushort const *,unsigned __int64)
0x14000ba18  cmp     qword ptr [rbx+18h], 8
0x14000ba1d  jb      short loc_14000BA24
0x14000ba1f  mov     rax, [rbx]
0x14000ba22  jmp     short loc_14000BA27
0x14000ba24  mov     rax, rbx
0x14000ba27  mov     rcx, [rsp+68h+arg_0]
0x14000ba2c  xor     edx, edx
0x14000ba2e  mov     [rbx+10h], rcx
0x14000ba32  mov     [rax+rcx*2], dx
0x14000ba36  mov     rax, rbx
0x14000ba39  add     rsp, 28h
0x14000ba3d  pop     r15
0x14000ba3f  pop     r14
0x14000ba41  pop     r13
0x14000ba43  pop     r12
0x14000ba45  pop     rdi
0x14000ba46  pop     rsi
0x14000ba47  pop     rbp
0x14000ba48  pop     rbx
0x14000ba49  retn
0x14000ba4a  lea     rcx, aInvalidStringP; "invalid string position"
0x14000ba51  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
```
