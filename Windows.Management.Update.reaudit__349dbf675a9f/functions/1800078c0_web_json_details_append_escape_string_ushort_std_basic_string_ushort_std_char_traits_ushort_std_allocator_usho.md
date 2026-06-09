# web::json::details::append_escape_string<ushort>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1800078c0`
- end: `0x180007ead`
- name: `??$append_escape_string@G@details@json@web@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV34@@Z`
- size: `1517`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800082e0`
- `0x180008410`

## callees

- `0x180004230`
- `0x1800078c0`

## pseudocode

```c
_QWORD *__fastcall web::json::details::append_escape_string<unsigned short>(_QWORD *Src, _QWORD *a2)
{
  _WORD *v3; // rcx
  _QWORD *v4; // r8
  _QWORD *result; // rax
  _WORD *v6; // rdi
  _WORD *v7; // rsi
  unsigned int v8; // r9d
  unsigned __int64 v9; // rcx
  unsigned __int64 v10; // rdx
  _QWORD *v11; // rax
  unsigned __int64 v12; // rcx
  unsigned __int64 v13; // rdx
  unsigned __int64 v14; // rcx
  unsigned __int64 v15; // rdx
  _QWORD *v16; // rax
  unsigned __int64 v17; // rcx
  unsigned __int64 v18; // rdx
  unsigned __int64 v19; // rcx
  unsigned __int64 v20; // rdx
  _QWORD *v21; // rax
  unsigned __int64 v22; // rcx
  unsigned __int64 v23; // rdx
  unsigned __int64 v24; // rcx
  unsigned __int64 v25; // rdx
  _QWORD *v26; // rax
  unsigned __int64 v27; // rcx
  unsigned __int64 v28; // rdx
  unsigned __int64 v29; // rcx
  unsigned __int64 v30; // rdx
  _QWORD *v31; // rax
  unsigned __int64 v32; // rcx
  unsigned __int64 v33; // rdx
  unsigned __int64 v34; // rcx
  unsigned __int64 v35; // rdx
  _QWORD *v36; // rax
  unsigned __int64 v37; // rcx
  unsigned __int64 v38; // rdx
  unsigned __int64 v39; // rcx
  unsigned __int64 v40; // rdx
  _QWORD *v41; // rax
  unsigned __int64 v42; // rcx
  unsigned __int64 v43; // rdx
  unsigned __int64 v44; // rcx
  unsigned __int64 v45; // rdx
  _QWORD *v46; // rax
  unsigned __int64 v47; // rcx
  unsigned __int64 v48; // rdx
  _QWORD *v49; // rax
  unsigned __int64 v50; // rcx
  unsigned __int64 v51; // rdx
  _QWORD *v52; // rax
  unsigned __int64 v53; // rcx
  unsigned __int64 v54; // rdx
  _QWORD *v55; // rax
  unsigned __int64 v56; // rcx
  unsigned __int64 v57; // rdx
  __int16 v58; // r9
  _QWORD *v59; // rax

  v3 = a2;
  if ( a2[3] <= 7u )
  {
    v4 = a2;
  }
  else
  {
    v3 = (_WORD *)*a2;
    v4 = (_QWORD *)*a2;
  }
  result = (_QWORD *)a2[2];
  v6 = v3;
  v7 = (_WORD *)v4 + (_QWORD)result;
  if ( v3 != v7 )
  {
    do
    {
      v8 = (unsigned __int16)*v6;
      switch ( *v6 )
      {
        case 8:
          v19 = Src[2];
          v20 = Src[3];
          if ( v19 >= v20 )
          {
            ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAXG_Z_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXG_Z_G_Z(Src);
          }
          else
          {
            Src[2] = v19 + 1;
            v21 = Src;
            if ( v20 > 7 )
              v21 = (_QWORD *)*Src;
            *(_DWORD *)((char *)v21 + 2 * v19) = 92;
          }
          v22 = Src[2];
          v23 = Src[3];
          if ( v22 >= v23 )
            goto LABEL_15;
          Src[2] = v22 + 1;
          result = Src;
          if ( v23 > 7 )
            result = (_QWORD *)*Src;
          *(_DWORD *)((char *)result + 2 * v22) = 98;
          break;
        case 9:
          v39 = Src[2];
          v40 = Src[3];
          if ( v39 >= v40 )
          {
            ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAXG_Z_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXG_Z_G_Z(Src);
          }
          else
          {
            Src[2] = v39 + 1;
            v41 = Src;
            if ( v40 > 7 )
              v41 = (_QWORD *)*Src;
            *(_DWORD *)((char *)v41 + 2 * v39) = 92;
          }
          v42 = Src[2];
          v43 = Src[3];
          if ( v42 >= v43 )
            goto LABEL_15;
          Src[2] = v42 + 1;
          result = Src;
          if ( v43 > 7 )
            result = (_QWORD *)*Src;
          *(_DWORD *)((char *)result + 2 * v42) = 116;
          break;
        case 0xA:
          v34 = Src[2];
          v35 = Src[3];
          if ( v34 >= v35 )
          {
            ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAXG_Z_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXG_Z_G_Z(Src);
          }
          else
          {
            Src[2] = v34 + 1;
            v36 = Src;
            if ( v35 > 7 )
              v36 = (_QWORD *)*Src;
            *(_DWORD *)((char *)v36 + 2 * v34) = 92;
          }
          v37 = Src[2];
          v38 = Src[3];
          if ( v37 >= v38 )
            goto LABEL_15;
          Src[2] = v37 + 1;
          result = Src;
          if ( v38 > 7 )
            result = (_QWORD *)*Src;
          *(_DWORD *)((char *)result + 2 * v37) = 110;
          break;
        case 0xC:
          v24 = Src[2];
          v25 = Src[3];
          if ( v24 >= v25 )
          {
            ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAXG_Z_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXG_Z_G_Z(Src);
          }
          else
          {
            Src[2] = v24 + 1;
            v26 = Src;
            if ( v25 > 7 )
              v26 = (_QWORD *)*Src;
            *(_DWORD *)((char *)v26 + 2 * v24) = 92;
          }
          v27 = Src[2];
          v28 = Src[3];
          if ( v27 >= v28 )
            goto LABEL_15;
          Src[2] = v27 + 1;
          result = Src;
          if ( v28 > 7 )
            result = (_QWORD *)*Src;
          *(_DWORD *)((char *)result + 2 * v27) = 102;
          break;
        case 0xD:
          v29 = Src[2];
          v30 = Src[3];
          if ( v29 >= v30 )
          {
            ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAXG_Z_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXG_Z_G_Z(Src);
          }
          else
          {
            Src[2] = v29 + 1;
            v31 = Src;
            if ( v30 > 7 )
              v31 = (_QWORD *)*Src;
            *(_DWORD *)((char *)v31 + 2 * v29) = 92;
          }
          v32 = Src[2];
          v33 = Src[3];
          if ( v32 >= v33 )
            goto LABEL_15;
          Src[2] = v32 + 1;
          result = Src;
          if ( v33 > 7 )
            result = (_QWORD *)*Src;
          *(_DWORD *)((char *)result + 2 * v32) = 114;
          break;
        case 0x22:
          v9 = Src[2];
          v10 = Src[3];
          if ( v9 >= v10 )
          {
            ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAXG_Z_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXG_Z_G_Z(Src);
          }
          else
          {
            Src[2] = v9 + 1;
            v11 = Src;
            if ( v10 > 7 )
              v11 = (_QWORD *)*Src;
            *(_DWORD *)((char *)v11 + 2 * v9) = 92;
          }
          v12 = Src[2];
          v13 = Src[3];
          if ( v12 >= v13 )
            goto LABEL_15;
          Src[2] = v12 + 1;
          result = Src;
          if ( v13 > 7 )
            result = (_QWORD *)*Src;
          *(_DWORD *)((char *)result + 2 * v12) = 34;
          break;
        case 0x5C:
          v14 = Src[2];
          v15 = Src[3];
          if ( v14 >= v15 )
          {
            ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAXG_Z_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXG_Z_G_Z(Src);
          }
          else
          {
            Src[2] = v14 + 1;
            v16 = Src;
            if ( v15 > 7 )
              v16 = (_QWORD *)*Src;
            *(_DWORD *)((char *)v16 + 2 * v14) = 92;
          }
          v17 = Src[2];
          v18 = Src[3];
          if ( v17 >= v18 )
            goto LABEL_15;
          Src[2] = v17 + 1;
          result = Src;
          if ( v18 > 7 )
            result = (_QWORD *)*Src;
          *(_DWORD *)((char *)result + 2 * v17) = 92;
          break;
        default:
          v44 = Src[2];
          v45 = Src[3];
          if ( v8 <= 0x1F )
          {
            if ( v44 >= v45 )
            {
              ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAXG_Z_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXG_Z_G_Z(Src);
            }
            else
            {
              Src[2] = v44 + 1;
              v46 = Src;
              if ( v45 > 7 )
                v46 = (_QWORD *)*Src;
              *(_DWORD *)((char *)v46 + 2 * v44) = 92;
            }
            v47 = Src[2];
            v48 = Src[3];
            if ( v47 >= v48 )
            {
              ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAXG_Z_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXG_Z_G_Z(Src);
            }
            else
            {
              Src[2] = v47 + 1;
              v49 = Src;
              if ( v48 > 7 )
                v49 = (_QWORD *)*Src;
              *(_DWORD *)((char *)v49 + 2 * v47) = 117;
            }
            v50 = Src[2];
            v51 = Src[3];
            if ( v50 >= v51 )
            {
              ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAXG_Z_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXG_Z_G_Z(Src);
            }
            else
            {
              Src[2] = v50 + 1;
              v52 = Src;
              if ( v51 > 7 )
                v52 = (_QWORD *)*Src;
              *(_DWORD *)((char *)v52 + 2 * v50) = 48;
            }
            v53 = Src[2];
            v54 = Src[3];
            if ( v53 >= v54 )
            {
              ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAXG_Z_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXG_Z_G_Z(Src);
            }
            else
            {
              Src[2] = v53 + 1;
              v55 = Src;
              if ( v54 > 7 )
                v55 = (_QWORD *)*Src;
              *(_DWORD *)((char *)v55 + 2 * v53) = 48;
            }
            v56 = Src[2];
            v57 = Src[3];
            v58 = `web::json::details::append_escape_string<unsigned short>'::`11'::intToHex[((unsigned __int64)(unsigned __int16)*v6 >> 4)
                                                                                           & 0xF];
            if ( v56 >= v57 )
            {
              ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAXG_Z_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXG_Z_G_Z(Src);
            }
            else
            {
              Src[2] = v56 + 1;
              v59 = Src;
              if ( v57 > 7 )
                v59 = (_QWORD *)*Src;
              *((_WORD *)v59 + v56) = v58;
              *((_WORD *)v59 + v56 + 1) = 0;
            }
            v44 = Src[2];
            v45 = Src[3];
            LOWORD(v8) = `web::json::details::append_escape_string<unsigned short>'::`11'::intToHex[*v6 & 0xF];
          }
          if ( v44 >= v45 )
          {
LABEL_15:
            result = (_QWORD *)____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAXG_Z_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXG_Z_G_Z(Src);
          }
          else
          {
            Src[2] = v44 + 1;
            result = Src;
            if ( v45 > 7 )
              result = (_QWORD *)*Src;
            *((_WORD *)result + v44 + 1) = 0;
            *((_WORD *)result + v44) = v8;
          }
          break;
      }
      ++v6;
    }
    while ( v6 != v7 );
  }
  return result;
}

```

## disassembly

```asm
0x1800078c0  push    rbx
0x1800078c2  push    rsi
0x1800078c3  push    rdi
0x1800078c4  sub     rsp, 30h
0x1800078c8  cmp     qword ptr [rdx+18h], 7
0x1800078cd  mov     rbx, rcx
0x1800078d0  mov     rcx, rdx
0x1800078d3  jbe     short loc_1800078DD
0x1800078d5  mov     rcx, [rdx]
0x1800078d8  mov     r8, rcx
0x1800078db  jmp     short loc_1800078E0
0x1800078dd  mov     r8, rdx
0x1800078e0  mov     rax, [rdx+10h]
0x1800078e4  mov     rdi, rcx
0x1800078e7  lea     rsi, [r8+rax*2]
0x1800078eb  cmp     rcx, rsi
0x1800078ee  jz      loc_180007A08
0x1800078f4  mov     [rsp+48h+arg_0], rbp
0x1800078f9  xor     ebp, ebp
0x1800078fb  mov     [rsp+48h+arg_8], r12
0x180007900  lea     r12, cs:180000000h
0x180007907  mov     [rsp+48h+arg_10], r13
0x18000790c  mov     [rsp+48h+var_20], r14
0x180007911  mov     [rsp+48h+var_28], r15
0x180007916  lea     r14d, [rbp+5Ch]
0x18000791a  lea     r8d, [rbp+22h]
0x18000791e  lea     r10d, [rbp+62h]
0x180007922  lea     r11d, [rbp+66h]
0x180007926  lea     r13d, [rbp+75h]
0x18000792a  lea     r15d, [rbp+30h]
0x18000792e  xchg    ax, ax
0x180007930  movzx   r9d, word ptr [rdi]
0x180007934  lea     eax, [r9-8]; switch 85 cases
0x180007938  cmp     eax, 54h
0x18000793b  ja      def_180007957; jumptable 0000000180007957 default case, cases 11,14-33,35-91
0x180007941  cdqe
0x180007943  movzx   eax, ds:(byte_180007E58 - 180000000h)[r12+rax]
0x18000794c  mov     ecx, ds:(jpt_180007957 - 180000000h)[r12+rax*4]
0x180007954  add     rcx, r12
0x180007957  jmp     rcx; switch jump
0x180007959  mov     rcx, [rbx+10h]; jumptable 0000000180007957 case 34
0x18000795d  mov     rdx, [rbx+18h]
0x180007961  cmp     rcx, rdx
0x180007964  jnb     short loc_180007980
0x180007966  lea     rax, [rcx+1]
0x18000796a  mov     [rbx+10h], rax
0x18000796e  mov     rax, rbx
0x180007971  cmp     rdx, 7
0x180007975  jbe     short loc_18000797A
0x180007977  mov     rax, [rbx]
0x18000797a  mov     [rax+rcx*2], r14d
0x18000797e  jmp     short loc_180007998
0x180007980  xor     r8d, r8d
0x180007983  mov     r9d, r14d
0x180007986  mov     rcx, rbx; Src
0x180007989  lea     edx, [r8+1]
0x18000798d  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXG@Z@G@Z; std::wstring::_Reallocate_grow_by<`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort>(unsigned __int64,`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort)
0x180007992  mov     r8d, 22h ; '"'
0x180007998  mov     rcx, [rbx+10h]
0x18000799c  mov     rdx, [rbx+18h]
0x1800079a0  cmp     rcx, rdx
0x1800079a3  jnb     short loc_1800079C2
0x1800079a5  lea     rax, [rcx+1]
0x1800079a9  mov     [rbx+10h], rax
0x1800079ad  mov     rax, rbx
0x1800079b0  cmp     rdx, 7
0x1800079b4  jbe     short loc_1800079B9
0x1800079b6  mov     rax, [rbx]
0x1800079b9  mov     dword ptr [rax+rcx*2], 22h ; '"'
0x1800079c0  jmp     short loc_1800079D4
0x1800079c2  mov     r9d, r8d
0x1800079c5  xor     r8d, r8d
0x1800079c8  mov     rcx, rbx; Src
0x1800079cb  lea     edx, [r8+1]
0x1800079cf  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXG@Z@G@Z; std::wstring::_Reallocate_grow_by<`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort>(unsigned __int64,`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort)
0x1800079d4  mov     r8d, 22h ; '"'
0x1800079da  add     rdi, 2
0x1800079de  lea     r10d, [r8+40h]
0x1800079e2  lea     r11d, [r8+44h]
0x1800079e6  cmp     rdi, rsi
0x1800079e9  jnz     loc_180007930
0x1800079ef  mov     r15, [rsp+48h+var_28]
0x1800079f4  mov     r14, [rsp+48h+var_20]
0x1800079f9  mov     r13, [rsp+48h+arg_10]
0x1800079fe  mov     r12, [rsp+48h+arg_8]
0x180007a03  mov     rbp, [rsp+48h+arg_0]
0x180007a08  add     rsp, 30h
0x180007a0c  pop     rdi
0x180007a0d  pop     rsi
0x180007a0e  pop     rbx
0x180007a0f  retn
0x180007a10  mov     rcx, [rbx+10h]; jumptable 0000000180007957 case 92
0x180007a14  mov     rdx, [rbx+18h]
0x180007a18  cmp     rcx, rdx
0x180007a1b  jnb     short loc_180007A37
0x180007a1d  lea     rax, [rcx+1]
0x180007a21  mov     [rbx+10h], rax
0x180007a25  mov     rax, rbx
0x180007a28  cmp     rdx, 7
0x180007a2c  jbe     short loc_180007A31
0x180007a2e  mov     rax, [rbx]
0x180007a31  mov     [rax+rcx*2], r14d
0x180007a35  jmp     short loc_180007A49
0x180007a37  xor     r8d, r8d
0x180007a3a  mov     r9d, r14d
0x180007a3d  mov     rcx, rbx; Src
0x180007a40  lea     edx, [r8+1]
0x180007a44  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXG@Z@G@Z; std::wstring::_Reallocate_grow_by<`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort>(unsigned __int64,`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort)
0x180007a49  mov     rcx, [rbx+10h]
0x180007a4d  mov     rdx, [rbx+18h]
0x180007a51  cmp     rcx, rdx
0x180007a54  jnb     short loc_180007A73
0x180007a56  lea     rax, [rcx+1]
0x180007a5a  mov     [rbx+10h], rax
0x180007a5e  mov     rax, rbx
0x180007a61  cmp     rdx, 7
0x180007a65  jbe     short loc_180007A6A
0x180007a67  mov     rax, [rbx]
0x180007a6a  mov     [rax+rcx*2], r14d
0x180007a6e  jmp     loc_1800079D4
0x180007a73  mov     r9d, r14d
0x180007a76  jmp     loc_1800079C5
0x180007a7b  mov     rcx, [rbx+10h]; jumptable 0000000180007957 case 8
0x180007a7f  mov     rdx, [rbx+18h]
0x180007a83  cmp     rcx, rdx
0x180007a86  jnb     short loc_180007AA2
0x180007a88  lea     rax, [rcx+1]
0x180007a8c  mov     [rbx+10h], rax
0x180007a90  mov     rax, rbx
0x180007a93  cmp     rdx, 7
0x180007a97  jbe     short loc_180007A9C
0x180007a99  mov     rax, [rbx]
0x180007a9c  mov     [rax+rcx*2], r14d
0x180007aa0  jmp     short loc_180007ABA
0x180007aa2  xor     r8d, r8d
0x180007aa5  mov     r9d, r14d
0x180007aa8  mov     rcx, rbx; Src
0x180007aab  lea     edx, [r8+1]
0x180007aaf  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXG@Z@G@Z; std::wstring::_Reallocate_grow_by<`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort>(unsigned __int64,`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort)
0x180007ab4  mov     r10d, 62h ; 'b'
0x180007aba  mov     rcx, [rbx+10h]
0x180007abe  mov     rdx, [rbx+18h]
0x180007ac2  cmp     rcx, rdx
0x180007ac5  jnb     short loc_180007AE7
0x180007ac7  lea     rax, [rcx+1]
0x180007acb  mov     [rbx+10h], rax
0x180007acf  mov     rax, rbx
0x180007ad2  cmp     rdx, 7
0x180007ad6  jbe     short loc_180007ADB
0x180007ad8  mov     rax, [rbx]
0x180007adb  mov     dword ptr [rax+rcx*2], 62h ; 'b'
0x180007ae2  jmp     loc_1800079D4
0x180007ae7  mov     r9d, r10d
0x180007aea  jmp     loc_1800079C5
0x180007aef  mov     rcx, [rbx+10h]; jumptable 0000000180007957 case 12
0x180007af3  mov     rdx, [rbx+18h]
0x180007af7  cmp     rcx, rdx
0x180007afa  jnb     short loc_180007B16
0x180007afc  lea     rax, [rcx+1]
0x180007b00  mov     [rbx+10h], rax
0x180007b04  mov     rax, rbx
0x180007b07  cmp     rdx, 7
0x180007b0b  jbe     short loc_180007B10
0x180007b0d  mov     rax, [rbx]
0x180007b10  mov     [rax+rcx*2], r14d
0x180007b14  jmp     short loc_180007B2E
0x180007b16  xor     r8d, r8d
0x180007b19  mov     r9d, r14d
0x180007b1c  mov     rcx, rbx; Src
0x180007b1f  lea     edx, [r8+1]
0x180007b23  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXG@Z@G@Z; std::wstring::_Reallocate_grow_by<`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort>(unsigned __int64,`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort)
0x180007b28  mov     r11d, 66h ; 'f'
0x180007b2e  mov     rcx, [rbx+10h]
0x180007b32  mov     rdx, [rbx+18h]
0x180007b36  cmp     rcx, rdx
0x180007b39  jnb     short loc_180007B5B
0x180007b3b  lea     rax, [rcx+1]
0x180007b3f  mov     [rbx+10h], rax
0x180007b43  mov     rax, rbx
0x180007b46  cmp     rdx, 7
0x180007b4a  jbe     short loc_180007B4F
0x180007b4c  mov     rax, [rbx]
0x180007b4f  mov     dword ptr [rax+rcx*2], 66h ; 'f'
0x180007b56  jmp     loc_1800079D4
0x180007b5b  mov     r9d, r11d
0x180007b5e  jmp     loc_1800079C5
0x180007b63  mov     rcx, [rbx+10h]; jumptable 0000000180007957 case 13
0x180007b67  mov     rdx, [rbx+18h]
0x180007b6b  cmp     rcx, rdx
0x180007b6e  jnb     short loc_180007B8A
0x180007b70  lea     rax, [rcx+1]
0x180007b74  mov     [rbx+10h], rax
0x180007b78  mov     rax, rbx
0x180007b7b  cmp     rdx, 7
0x180007b7f  jbe     short loc_180007B84
0x180007b81  mov     rax, [rbx]
0x180007b84  mov     [rax+rcx*2], r14d
0x180007b88  jmp     short loc_180007B9C
0x180007b8a  xor     r8d, r8d
0x180007b8d  mov     r9d, r14d
0x180007b90  mov     rcx, rbx; Src
0x180007b93  lea     edx, [r8+1]
0x180007b97  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXG@Z@G@Z; std::wstring::_Reallocate_grow_by<`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort>(unsigned __int64,`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort)
0x180007b9c  mov     rcx, [rbx+10h]
0x180007ba0  mov     rdx, [rbx+18h]
0x180007ba4  cmp     rcx, rdx
0x180007ba7  jnb     short loc_180007BC9
0x180007ba9  lea     rax, [rcx+1]
0x180007bad  mov     [rbx+10h], rax
0x180007bb1  mov     rax, rbx
0x180007bb4  cmp     rdx, 7
0x180007bb8  jbe     short loc_180007BBD
0x180007bba  mov     rax, [rbx]
0x180007bbd  mov     dword ptr [rax+rcx*2], 72h ; 'r'
0x180007bc4  jmp     loc_1800079D4
0x180007bc9  mov     r9d, 72h ; 'r'
0x180007bcf  jmp     loc_1800079C5
0x180007bd4  mov     rcx, [rbx+10h]; jumptable 0000000180007957 case 10
0x180007bd8  mov     rdx, [rbx+18h]
0x180007bdc  cmp     rcx, rdx
0x180007bdf  jnb     short loc_180007BFB
0x180007be1  lea     rax, [rcx+1]
0x180007be5  mov     [rbx+10h], rax
0x180007be9  mov     rax, rbx
0x180007bec  cmp     rdx, 7
0x180007bf0  jbe     short loc_180007BF5
0x180007bf2  mov     rax, [rbx]
0x180007bf5  mov     [rax+rcx*2], r14d
0x180007bf9  jmp     short loc_180007C0D
0x180007bfb  xor     r8d, r8d
0x180007bfe  mov     r9d, r14d
0x180007c01  mov     rcx, rbx; Src
0x180007c04  lea     edx, [r8+1]
0x180007c08  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXG@Z@G@Z; std::wstring::_Reallocate_grow_by<`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort>(unsigned __int64,`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort)
0x180007c0d  mov     rcx, [rbx+10h]
0x180007c11  mov     rdx, [rbx+18h]
0x180007c15  cmp     rcx, rdx
0x180007c18  jnb     short loc_180007C3A
0x180007c1a  lea     rax, [rcx+1]
0x180007c1e  mov     [rbx+10h], rax
0x180007c22  mov     rax, rbx
0x180007c25  cmp     rdx, 7
0x180007c29  jbe     short loc_180007C2E
0x180007c2b  mov     rax, [rbx]
0x180007c2e  mov     dword ptr [rax+rcx*2], 6Eh ; 'n'
0x180007c35  jmp     loc_1800079D4
0x180007c3a  mov     r9d, 6Eh ; 'n'
0x180007c40  jmp     loc_1800079C5
0x180007c45  mov     rcx, [rbx+10h]; jumptable 0000000180007957 case 9
0x180007c49  mov     rdx, [rbx+18h]
0x180007c4d  cmp     rcx, rdx
0x180007c50  jnb     short loc_180007C6C
0x180007c52  lea     rax, [rcx+1]
0x180007c56  mov     [rbx+10h], rax
0x180007c5a  mov     rax, rbx
0x180007c5d  cmp     rdx, 7
0x180007c61  jbe     short loc_180007C66
0x180007c63  mov     rax, [rbx]
0x180007c66  mov     [rax+rcx*2], r14d
0x180007c6a  jmp     short loc_180007C7E
0x180007c6c  xor     r8d, r8d
0x180007c6f  mov     r9d, r14d
0x180007c72  mov     rcx, rbx; Src
0x180007c75  lea     edx, [r8+1]
0x180007c79  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXG@Z@G@Z; std::wstring::_Reallocate_grow_by<`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort>(unsigned __int64,`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort)
0x180007c7e  mov     rcx, [rbx+10h]
0x180007c82  mov     rdx, [rbx+18h]
0x180007c86  cmp     rcx, rdx
0x180007c89  jnb     short loc_180007CAB
0x180007c8b  lea     rax, [rcx+1]
0x180007c8f  mov     [rbx+10h], rax
0x180007c93  mov     rax, rbx
0x180007c96  cmp     rdx, 7
0x180007c9a  jbe     short loc_180007C9F
0x180007c9c  mov     rax, [rbx]
0x180007c9f  mov     dword ptr [rax+rcx*2], 74h ; 't'
0x180007ca6  jmp     loc_1800079D4
0x180007cab  mov     r9d, 74h ; 't'
0x180007cb1  jmp     loc_1800079C5
0x180007cb6  mov     rcx, [rbx+10h]; jumptable 0000000180007957 default case, cases 11,14-33,35-91
0x180007cba  mov     rdx, [rbx+18h]
0x180007cbe  cmp     r9d, 1Fh
0x180007cc2  ja      loc_180007E0A
0x180007cc8  cmp     rcx, rdx
0x180007ccb  jnb     short loc_180007CE7
0x180007ccd  lea     rax, [rcx+1]
0x180007cd1  mov     [rbx+10h], rax
0x180007cd5  mov     rax, rbx
0x180007cd8  cmp     rdx, 7
0x180007cdc  jbe     short loc_180007CE1
0x180007cde  mov     rax, [rbx]
0x180007ce1  mov     [rax+rcx*2], r14d
0x180007ce5  jmp     short loc_180007CF9
0x180007ce7  xor     r8d, r8d
0x180007cea  mov     r9d, r14d
0x180007ced  mov     rcx, rbx; Src
0x180007cf0  lea     edx, [r8+1]
0x180007cf4  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXG@Z@G@Z; std::wstring::_Reallocate_grow_by<`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort>(unsigned __int64,`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort)
0x180007cf9  mov     rcx, [rbx+10h]
0x180007cfd  mov     rdx, [rbx+18h]
  ... truncated ...
```
