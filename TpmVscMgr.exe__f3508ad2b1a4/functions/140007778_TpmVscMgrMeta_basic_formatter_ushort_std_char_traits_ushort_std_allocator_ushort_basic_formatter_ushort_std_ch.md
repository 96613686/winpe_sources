# TpmVscMgrMeta::basic_formatter<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_formatter<ushort,std::char_traits<ushort>,std::allocator<ushort>>(rangelib::range<ushort const *> const &)

- ea: `0x140007778`
- end: `0x140007b82`
- name: `??0?$basic_formatter@GU?$char_traits@G@std@@V?$allocator@G@2@@TpmVscMgrMeta@@QEAA@AEBV?$range@PEBG@rangelib@@@Z`
- size: `1034`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `12`
- tags: ``

## callers

- `0x14000641c`
- `0x140008784`
- `0x14000e510`
- `0x14000e62c`
- `0x14000f54c`

## callees

- `0x1400016a0`
- `0x140001990`
- `0x1400067e8`
- `0x1400068f4`
- `0x140006af4`
- `0x140006f18`
- `0x140007394`
- `0x1400074fc`
- `0x140007778`
- `0x140008278`
- `0x14000859c`
- `0x140011530`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall TpmVscMgrMeta::basic_formatter<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::basic_formatter<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(
        __int64 a1,
        char **a2)
{
  __int64 v3; // r15
  _QWORD *v4; // r13
  _QWORD *v5; // rax
  _QWORD *v6; // rax
  char v7; // cl
  char v8; // di
  char *v9; // r14
  char *v10; // rsi
  char *v11; // rax
  __m128i si128; // xmm6
  char *v13; // r15
  __int16 v14; // r12
  unsigned __int64 v15; // rdx
  void **v16; // rdi
  __int64 v17; // rbx
  __int64 v18; // rbx
  __int64 v19; // rax
  __int64 v20; // rdi
  __int64 *v21; // rdx
  void **v22; // rcx
  char v24; // [rsp+28h] [rbp-B9h]
  char *v25; // [rsp+30h] [rbp-B1h]
  _QWORD *v26; // [rsp+38h] [rbp-A9h]
  __int64 v27; // [rsp+40h] [rbp-A1h] BYREF
  __int64 v28; // [rsp+48h] [rbp-99h]
  __int64 v29; // [rsp+58h] [rbp-89h]
  char v30[16]; // [rsp+68h] [rbp-79h] BYREF
  __int128 v31; // [rsp+78h] [rbp-69h] BYREF
  __m128i v32; // [rsp+88h] [rbp-59h]
  void *v33[2]; // [rsp+98h] [rbp-49h] BYREF
  __int64 v34; // [rsp+A8h] [rbp-39h]
  unsigned __int64 v35; // [rsp+B0h] [rbp-31h]
  _BYTE v36[32]; // [rsp+B8h] [rbp-29h] BYREF
  char v37[24]; // [rsp+D8h] [rbp-9h] BYREF

  v3 = a1;
  v28 = a1;
  v29 = a1;
  *(_BYTE *)a1 = 1;
  v4 = (_QWORD *)(a1 + 8);
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 16) = 0;
  v5 = operator new(0x30u);
  *v5 = v5;
  v5[1] = v5;
  *v4 = v5;
  v26 = (_QWORD *)(v3 + 24);
  *(_QWORD *)(v3 + 24) = 0;
  *(_QWORD *)(v3 + 32) = 0;
  v6 = operator new(0x58u);
  *v6 = v6;
  v6[1] = v6;
  v6[2] = v6;
  *((_WORD *)v6 + 12) = 257;
  *(_QWORD *)(v3 + 24) = v6;
  *(_OWORD *)(v3 + 40) = 0;
  *(_QWORD *)(v3 + 56) = 0;
  *(_QWORD *)(v3 + 64) = 7;
  *(_WORD *)(v3 + 40) = 0;
  v7 = 0;
  v24 = 0;
  v8 = 0;
  *(_OWORD *)v33 = 0;
  v34 = 0;
  v35 = 7;
  LOWORD(v33[0]) = 0;
  v9 = *a2;
  v10 = *a2;
  v11 = a2[1];
  v25 = v11;
  if ( *a2 != v11 )
  {
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    while ( 1 )
    {
      v13 = v10 + 2;
      if ( v10 + 2 == v11 )
        v14 = 0;
      else
        v14 = *(_WORD *)v13;
      if ( v7 )
      {
        if ( v8 )
        {
          if ( *(_WORD *)v10 != 125 )
            goto LABEL_41;
        }
        else
        {
          if ( *(_WORD *)v10 != 125 )
            goto LABEL_41;
          if ( (__int64)((v10 - v9) & 0xFFFFFFFFFFFFFFFEuLL) > 6 )
          {
            v15 = (v10 - (v9 + 4)) >> 1;
            if ( v15 > v35 )
            {
              std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v33);
            }
            else
            {
              v16 = v33;
              if ( v35 > 7 )
                v16 = (void **)v33[0];
              v34 = (v10 - (v9 + 4)) >> 1;
              v17 = 2 * v15;
              memmove_0(v16, v9 + 4, 2 * v15);
              *(_WORD *)((char *)v16 + v17) = 0;
            }
            v7 = v24;
          }
          v8 = 1;
          v11 = v25;
        }
        if ( v14 != 123 )
        {
          if ( v34 )
          {
            v31 = 0;
            v32 = 0;
            if ( v9 == v13 )
            {
              v32 = si128;
              LOWORD(v31) = 0;
            }
            else
            {
              std::wstring::_Construct<1,unsigned short const *>(&v31, v9, (v13 - v9) >> 1);
            }
            v18 = std::list<std::wstring>::_Emplace<std::wstring>(v4, *v4, &v31);
            v27 = v18;
            std::wstring::~wstring(&v31);
            v31 = 0;
            v32.m128i_i64[0] = 0;
            v19 = std::make_pair<std::wstring &,std::vector<std::_List_iterator<std::_List_val<std::_List_simple_types<std::wstring>>>>>(
                    v36,
                    v33,
                    &v31);
            v20 = *(_QWORD *)std::map<std::wstring,std::vector<std::_List_iterator<std::_List_val<std::_List_simple_types<std::wstring>>>>>::insert<std::pair<std::wstring,std::vector<std::_List_iterator<std::_List_val<std::_List_simple_types<std::wstring>>>>>,0>(
                               v26,
                               v30,
                               v19);
            std::vector<std::_List_iterator<std::_List_val<std::_List_simple_types<std::wstring>>>>::~vector<std::_List_iterator<std::_List_val<std::_List_simple_types<std::wstring>>>>(v37);
            std::wstring::~wstring(v36);
            std::vector<std::_List_iterator<std::_List_val<std::_List_simple_types<std::wstring>>>>::~vector<std::_List_iterator<std::_List_val<std::_List_simple_types<std::wstring>>>>(&v31);
            if ( v20 != *v26 )
            {
              v21 = *(__int64 **)(v20 + 72);
              if ( v21 == *(__int64 **)(v20 + 80) )
              {
                std::vector<std::_List_iterator<std::_List_val<std::_List_simple_types<std::wstring>>>>::_Emplace_reallocate<std::_List_iterator<std::_List_val<std::_List_simple_types<std::wstring>>> const &>(
                  v20 + 64,
                  v21,
                  &v27);
              }
              else
              {
                *v21 = v18;
                *(_QWORD *)(v20 + 72) += 8LL;
              }
            }
          }
          v9 = v10 + 2;
          v34 = 0;
          v22 = v33;
          if ( v35 > 7 )
            v22 = (void **)v33[0];
          *(_WORD *)v22 = 0;
          v7 = 0;
          v11 = v25;
LABEL_40:
          v8 = 0;
          v24 = v7;
        }
      }
      else if ( *(_WORD *)v10 == 37 )
      {
        if ( v14 == 37 )
        {
          v31 = 0;
          v32 = 0;
          if ( v9 == v13 )
          {
            v32 = si128;
            LOWORD(v31) = 0;
          }
          else
          {
            std::wstring::_Construct<1,unsigned short const *>(&v31, v9, (v13 - v9) >> 1);
          }
          std::list<std::wstring>::_Emplace<std::wstring>(v4, *v4, &v31);
          std::wstring::~wstring(&v31);
          v10 += 2;
          v9 = v13 + 2;
          v7 = v24;
          v11 = v25;
          goto LABEL_41;
        }
        if ( v14 == 123 )
        {
          if ( v9 != v10 )
          {
            v31 = 0;
            v32 = 0;
            std::wstring::_Construct<1,unsigned short const *>(&v31, v9, (v10 - v9) >> 1);
            std::list<std::wstring>::_Emplace<std::wstring>(v4, *v4, &v31);
            std::wstring::~wstring(&v31);
            v11 = v25;
          }
          v9 = v10;
          v7 = 1;
          goto LABEL_40;
        }
      }
LABEL_41:
      v10 += 2;
      if ( v10 == v11 )
      {
        v3 = v28;
        break;
      }
    }
  }
  if ( v9 != v10 )
  {
    v31 = 0;
    v32 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v31, v9, (v10 - v9) >> 1);
    std::list<std::wstring>::_Emplace<std::wstring>(v4, *v4, &v31);
    std::wstring::~wstring(&v31);
  }
  std::wstring::~wstring(v33);
  return v3;
}

```

## disassembly

```asm
0x140007778  mov     rax, rsp
0x14000777b  mov     [rax+18h], rbx
0x14000777f  push    rbp
0x140007780  push    rsi
0x140007781  push    rdi
0x140007782  push    r12
0x140007784  push    r13
0x140007786  push    r14
0x140007788  push    r15
0x14000778a  lea     rbp, [rax-5Fh]
0x14000778e  sub     rsp, 100h
0x140007795  movaps  xmmword ptr [rax-48h], xmm6
0x140007799  mov     rax, cs:__security_cookie
0x1400077a0  xor     rax, rsp
0x1400077a3  mov     [rbp+57h+var_48], rax
0x1400077a7  mov     rbx, rdx
0x1400077aa  mov     r15, rcx
0x1400077ad  mov     [rsp+130h+var_F0], rcx
0x1400077b2  mov     [rsp+130h+var_E0], rcx
0x1400077b7  mov     byte ptr [rcx], 1
0x1400077ba  lea     r13, [rcx+8]
0x1400077be  mov     qword ptr [r13+0], 0
0x1400077c6  mov     qword ptr [r13+8], 0
0x1400077ce  mov     ecx, 30h ; '0'; Size
0x1400077d3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400077d8  mov     [rax], rax
0x1400077db  mov     [rax+8], rax
0x1400077df  mov     [r13+0], rax
0x1400077e3  lea     rdi, [r15+18h]
0x1400077e7  mov     [rsp+130h+var_100], rdi
0x1400077ec  mov     qword ptr [rdi], 0
0x1400077f3  mov     qword ptr [rdi+8], 0
0x1400077fb  mov     ecx, 58h ; 'X'; Size
0x140007800  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140007805  mov     [rax], rax
0x140007808  mov     [rax+8], rax
0x14000780c  mov     [rax+10h], rax
0x140007810  mov     word ptr [rax+18h], 101h
0x140007816  mov     [rdi], rax
0x140007819  xorps   xmm0, xmm0
0x14000781c  movups  xmmword ptr [r15+28h], xmm0
0x140007821  mov     qword ptr [r15+38h], 0
0x140007829  mov     qword ptr [r15+40h], 7
0x140007831  xor     eax, eax
0x140007833  mov     [r15+28h], ax
0x140007838  xor     cl, cl
0x14000783a  mov     byte ptr [rsp+130h+var_110], cl
0x14000783e  xor     dil, dil
0x140007841  movups  xmmword ptr [rbp+57h+var_A0], xmm0
0x140007845  mov     [rbp+57h+var_90], rax
0x140007849  mov     [rbp+57h+var_88], 7
0x140007851  mov     word ptr [rbp+57h+var_A0], ax
0x140007855  mov     r14, [rbx]
0x140007858  mov     rsi, r14
0x14000785b  mov     rax, [rbx+8]
0x14000785f  mov     [rsp+130h+var_108], rax
0x140007864  cmp     r14, rax
0x140007867  jz      loc_140007B04
0x14000786d  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x140007875  lea     r15, [rsi+2]
0x140007879  cmp     r15, rax
0x14000787c  jnz     short loc_140007883
0x14000787e  xor     r12d, r12d
0x140007881  jmp     short loc_140007887
0x140007883  movzx   r12d, word ptr [r15]
0x140007887  test    cl, cl
0x140007889  jz      loc_140007A22
0x14000788f  test    dil, dil
0x140007892  jnz     short loc_140007904
0x140007894  cmp     word ptr [rsi], 7Dh ; '}'
0x140007898  jnz     loc_140007AF2
0x14000789e  mov     rax, rsi
0x1400078a1  sub     rax, r14
0x1400078a4  and     rax, 0FFFFFFFFFFFFFFFEh
0x1400078a8  cmp     rax, 6
0x1400078ac  jle     short loc_1400078FA
0x1400078ae  lea     r9, [r14+4]
0x1400078b2  mov     rdx, rsi
0x1400078b5  sub     rdx, r9
0x1400078b8  sar     rdx, 1
0x1400078bb  cmp     rdx, [rbp+57h+var_88]
0x1400078bf  ja      short loc_1400078ED
0x1400078c1  lea     rdi, [rbp+57h+var_A0]
0x1400078c5  cmp     [rbp+57h+var_88], 7
0x1400078ca  cmova   rdi, [rbp+57h+var_A0]
0x1400078cf  mov     [rbp+57h+var_90], rdx
0x1400078d3  lea     rbx, [rdx+rdx]
0x1400078d7  mov     r8, rbx; Size
0x1400078da  mov     rdx, r9; Src
0x1400078dd  mov     rcx, rdi; void *
0x1400078e0  call    memmove_0
0x1400078e5  xor     eax, eax
0x1400078e7  mov     [rbx+rdi], ax
0x1400078eb  jmp     short loc_1400078F6
0x1400078ed  lea     rcx, [rbp+57h+var_A0]
0x1400078f1  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x1400078f6  mov     cl, byte ptr [rsp+130h+var_110]
0x1400078fa  mov     dil, 1
0x1400078fd  mov     rax, [rsp+130h+var_108]
0x140007902  jmp     short loc_14000790E
0x140007904  cmp     word ptr [rsi], 7Dh ; '}'
0x140007908  jnz     loc_140007AF2
0x14000790e  cmp     r12w, 7Bh ; '{'
0x140007913  jz      loc_140007AF2
0x140007919  cmp     [rbp+57h+var_90], 0
0x14000791e  jz      loc_1400079F8
0x140007924  xorps   xmm0, xmm0
0x140007927  movups  [rbp+57h+var_C0], xmm0
0x14000792b  xorps   xmm1, xmm1
0x14000792e  movdqu  [rbp+57h+var_B0], xmm1
0x140007933  cmp     r14, r15
0x140007936  jnz     short loc_140007945
0x140007938  movdqu  [rbp+57h+var_B0], xmm6
0x14000793d  xor     eax, eax
0x14000793f  mov     word ptr [rbp+57h+var_C0], ax
0x140007943  jmp     short loc_14000795B
0x140007945  mov     r8, r15
0x140007948  sub     r8, r14
0x14000794b  sar     r8, 1
0x14000794e  mov     rdx, r14
0x140007951  lea     rcx, [rbp+57h+var_C0]
0x140007955  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14000795a  nop
0x14000795b  lea     r8, [rbp+57h+var_C0]
0x14000795f  mov     rdx, [r13+0]
0x140007963  mov     rcx, r13
0x140007966  call    ??$_Emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAPEAU?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@1@QEAU21@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::list<std::wstring>::_Emplace<std::wstring>(std::_List_node<std::wstring,void *> * const,std::wstring &&)
0x14000796b  mov     rbx, rax
0x14000796e  mov     [rsp+130h+var_F8], rax
0x140007973  lea     rcx, [rbp+57h+var_C0]
0x140007977  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000797c  xorps   xmm0, xmm0
0x14000797f  movdqu  [rbp+57h+var_C0], xmm0
0x140007984  mov     qword ptr [rbp+57h+var_B0], 0
0x14000798c  lea     r8, [rbp+57h+var_C0]
0x140007990  lea     rdx, [rbp+57h+var_A0]
0x140007994  lea     rcx, [rbp+57h+var_80]
0x140007998  call    ??$make_pair@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@V?$allocator@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@@2@@2@@std@@YA?AU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@V?$allocator@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@@2@@2@@0@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV?$vector@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@V?$allocator@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@@2@@0@@Z; std::make_pair<std::wstring &,std::vector<std::_List_iterator<std::_List_val<std::_List_simple_types<std::wstring>>>>>(std::wstring &,std::vector<std::_List_iterator<std::_List_val<std::_List_simple_types<std::wstring>>>> &&)
0x14000799d  nop
0x14000799e  mov     r8, rax
0x1400079a1  lea     rdx, [rbp+57h+var_D0]
0x1400079a5  mov     r14, [rsp+130h+var_100]
0x1400079aa  mov     rcx, r14
0x1400079ad  call    ??$insert@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@V?$allocator@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@@2@@2@@std@@$0A@@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@V?$allocator@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@@2@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@V?$allocator@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@@2@@2@@std@@@2@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@V?$allocator@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@@2@@2@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@V?$allocator@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@@2@@2@@1@@Z
0x1400079b2  mov     rdi, [rax]
0x1400079b5  lea     rcx, [rbp+57h+var_60]
0x1400079b9  call    ??1?$vector@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@V?$allocator@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::_List_iterator<std::_List_val<std::_List_simple_types<std::wstring>>>>::~vector<std::_List_iterator<std::_List_val<std::_List_simple_types<std::wstring>>>>(void)
0x1400079be  lea     rcx, [rbp+57h+var_80]
0x1400079c2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400079c7  nop
0x1400079c8  lea     rcx, [rbp+57h+var_C0]
0x1400079cc  call    ??1?$vector@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@V?$allocator@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::_List_iterator<std::_List_val<std::_List_simple_types<std::wstring>>>>::~vector<std::_List_iterator<std::_List_val<std::_List_simple_types<std::wstring>>>>(void)
0x1400079d1  cmp     rdi, [r14]
0x1400079d4  jz      short loc_1400079F8
0x1400079d6  lea     rcx, [rdi+40h]
0x1400079da  mov     rdx, [rdi+48h]
0x1400079de  cmp     rdx, [rdi+50h]
0x1400079e2  jz      short loc_1400079EE
0x1400079e4  mov     [rdx], rbx
0x1400079e7  add     qword ptr [rcx+8], 8
0x1400079ec  jmp     short loc_1400079F8
0x1400079ee  lea     r8, [rsp+130h+var_F8]
0x1400079f3  call    ??$_Emplace_reallocate@AEBV?$_List_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@@?$vector@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@V?$allocator@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@@2@@std@@AEAAPEAV?$_List_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@1@QEAV21@AEBV21@@Z; std::vector<std::_List_iterator<std::_List_val<std::_List_simple_types<std::wstring>>>>::_Emplace_reallocate<std::_List_iterator<std::_List_val<std::_List_simple_types<std::wstring>>> const &>(std::_List_iterator<std::_List_val<std::_List_simple_types<std::wstring>>> * const,std::_List_iterator<std::_List_val<std::_List_simple_types<std::wstring>>> const &)
0x1400079f8  mov     r14, r15
0x1400079fb  mov     [rbp+57h+var_90], 0
0x140007a03  lea     rcx, [rbp+57h+var_A0]
0x140007a07  cmp     [rbp+57h+var_88], 7
0x140007a0c  cmova   rcx, [rbp+57h+var_A0]
0x140007a11  xor     eax, eax
0x140007a13  mov     [rcx], ax
0x140007a16  xor     cl, cl
0x140007a18  mov     rax, [rsp+130h+var_108]
0x140007a1d  jmp     loc_140007AEB
0x140007a22  cmp     word ptr [rsi], 25h ; '%'
0x140007a26  jnz     loc_140007AF2
0x140007a2c  cmp     r12w, 25h ; '%'
0x140007a31  jnz     short loc_140007A96
0x140007a33  xorps   xmm0, xmm0
0x140007a36  movups  [rbp+57h+var_C0], xmm0
0x140007a3a  xorps   xmm1, xmm1
0x140007a3d  movdqu  [rbp+57h+var_B0], xmm1
0x140007a42  cmp     r14, r15
0x140007a45  jnz     short loc_140007A54
0x140007a47  movdqu  [rbp+57h+var_B0], xmm6
0x140007a4c  xor     eax, eax
0x140007a4e  mov     word ptr [rbp+57h+var_C0], ax
0x140007a52  jmp     short loc_140007A6A
0x140007a54  mov     r8, r15
0x140007a57  sub     r8, r14
0x140007a5a  sar     r8, 1
0x140007a5d  mov     rdx, r14
0x140007a60  lea     rcx, [rbp+57h+var_C0]
0x140007a64  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140007a69  nop
0x140007a6a  lea     r8, [rbp+57h+var_C0]
0x140007a6e  mov     rdx, [r13+0]
0x140007a72  mov     rcx, r13
0x140007a75  call    ??$_Emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAPEAU?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@1@QEAU21@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::list<std::wstring>::_Emplace<std::wstring>(std::_List_node<std::wstring,void *> * const,std::wstring &&)
0x140007a7a  nop
0x140007a7b  lea     rcx, [rbp+57h+var_C0]
0x140007a7f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140007a84  mov     rsi, r15
0x140007a87  lea     r14, [r15+2]
0x140007a8b  mov     cl, byte ptr [rsp+130h+var_110]
0x140007a8f  mov     rax, [rsp+130h+var_108]
0x140007a94  jmp     short loc_140007AF2
0x140007a96  cmp     r12w, 7Bh ; '{'
0x140007a9b  jnz     short loc_140007AF2
0x140007a9d  cmp     r14, rsi
0x140007aa0  jz      short loc_140007AE6
0x140007aa2  xorps   xmm0, xmm0
0x140007aa5  movups  [rbp+57h+var_C0], xmm0
0x140007aa9  xorps   xmm1, xmm1
0x140007aac  movdqu  [rbp+57h+var_B0], xmm1
0x140007ab1  mov     r8, rsi
0x140007ab4  sub     r8, r14
0x140007ab7  sar     r8, 1
0x140007aba  mov     rdx, r14
0x140007abd  lea     rcx, [rbp+57h+var_C0]
0x140007ac1  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140007ac6  nop
0x140007ac7  lea     r8, [rbp+57h+var_C0]
0x140007acb  mov     rdx, [r13+0]
0x140007acf  mov     rcx, r13
0x140007ad2  call    ??$_Emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAPEAU?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@1@QEAU21@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::list<std::wstring>::_Emplace<std::wstring>(std::_List_node<std::wstring,void *> * const,std::wstring &&)
0x140007ad7  nop
0x140007ad8  lea     rcx, [rbp+57h+var_C0]
0x140007adc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140007ae1  mov     rax, [rsp+130h+var_108]
0x140007ae6  mov     r14, rsi
0x140007ae9  mov     cl, 1
0x140007aeb  xor     dil, dil
0x140007aee  mov     byte ptr [rsp+130h+var_110], cl
0x140007af2  add     rsi, 2
0x140007af6  cmp     rsi, rax
0x140007af9  jnz     loc_140007875
0x140007aff  mov     r15, [rsp+130h+var_F0]
0x140007b04  cmp     r14, rsi
0x140007b07  jz      short loc_140007B49
0x140007b09  xorps   xmm0, xmm0
0x140007b0c  movups  [rbp+57h+var_C0], xmm0
0x140007b10  xorps   xmm1, xmm1
0x140007b13  movdqu  [rbp+57h+var_B0], xmm1
0x140007b18  sub     rsi, r14
0x140007b1b  sar     rsi, 1
0x140007b1e  mov     r8, rsi
0x140007b21  mov     rdx, r14
0x140007b24  lea     rcx, [rbp+57h+var_C0]
0x140007b28  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140007b2d  nop
0x140007b2e  lea     r8, [rbp+57h+var_C0]
0x140007b32  mov     rdx, [r13+0]
0x140007b36  mov     rcx, r13
0x140007b39  call    ??$_Emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAPEAU?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@1@QEAU21@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::list<std::wstring>::_Emplace<std::wstring>(std::_List_node<std::wstring,void *> * const,std::wstring &&)
0x140007b3e  nop
0x140007b3f  lea     rcx, [rbp+57h+var_C0]
0x140007b43  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140007b48  nop
0x140007b49  lea     rcx, [rbp+57h+var_A0]
0x140007b4d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140007b52  nop
0x140007b53  mov     rax, r15
0x140007b56  mov     rcx, [rbp+57h+var_48]
0x140007b5a  xor     rcx, rsp; StackCookie
0x140007b5d  call    __security_check_cookie
0x140007b62  lea     r11, [rsp+130h+var_30]
0x140007b6a  mov     rbx, [r11+50h]
0x140007b6e  movaps  xmm6, xmmword ptr [r11-10h]
0x140007b73  mov     rsp, r11
0x140007b76  pop     r15
0x140007b78  pop     r14
0x140007b7a  pop     r13
0x140007b7c  pop     r12
0x140007b7e  pop     rdi
0x140007b7f  pop     rsi
0x140007b80  pop     rbp
0x140007b81  retn
```
