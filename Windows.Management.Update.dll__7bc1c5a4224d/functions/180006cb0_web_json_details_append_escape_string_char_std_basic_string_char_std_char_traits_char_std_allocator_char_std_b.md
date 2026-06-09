# web::json::details::append_escape_string<char>(std::basic_string<char,std::char_traits<char>,std::allocator<char>> &,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x180006cb0`
- end: `0x1800072cd`
- name: `??$append_escape_string@D@details@json@web@@YAXAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV34@@Z`
- size: `1565`
- prototype: `void __fastcall(char *Src, _QWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180007c70`
- `0x180007fa0`

## callees

- `0x180003df0`
- `0x180006cb0`

## pseudocode

```c
void __fastcall web::json::details::append_escape_string<char>(char *Src, _QWORD *a2)
{
  unsigned __int8 *v3; // rcx
  _QWORD *v4; // r8
  char *v5; // r14
  unsigned __int8 *v6; // rbp
  unsigned __int64 *v7; // rsi
  unsigned __int64 *v8; // rdi
  char v9; // r9
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rdx
  char *v12; // rax
  unsigned __int64 v13; // rcx
  unsigned __int64 v14; // rdx
  unsigned __int64 v15; // rcx
  unsigned __int64 v16; // rdx
  char *v17; // rax
  unsigned __int64 v18; // rcx
  unsigned __int64 v19; // rdx
  unsigned __int64 v20; // rcx
  unsigned __int64 v21; // rdx
  char *v22; // rax
  unsigned __int64 v23; // rcx
  unsigned __int64 v24; // rdx
  unsigned __int64 v25; // rcx
  unsigned __int64 v26; // rdx
  char *v27; // rax
  unsigned __int64 v28; // rcx
  unsigned __int64 v29; // rdx
  unsigned __int64 v30; // rcx
  unsigned __int64 v31; // rdx
  char *v32; // rax
  unsigned __int64 v33; // rcx
  unsigned __int64 v34; // rdx
  unsigned __int64 v35; // rcx
  unsigned __int64 v36; // rdx
  char *v37; // rax
  unsigned __int64 v38; // rcx
  unsigned __int64 v39; // rdx
  unsigned __int64 v40; // rcx
  unsigned __int64 v41; // rdx
  char *v42; // rax
  unsigned __int64 v43; // rcx
  unsigned __int64 v44; // rdx
  unsigned __int64 v45; // rcx
  unsigned __int64 v46; // rdx
  char *v47; // rax
  unsigned __int64 v48; // rcx
  unsigned __int64 v49; // rdx
  char *v50; // rax
  unsigned __int64 v51; // rcx
  unsigned __int64 v52; // rdx
  char *v53; // rax
  unsigned __int64 v54; // rcx
  unsigned __int64 v55; // rdx
  char *v56; // rax
  unsigned __int64 v57; // rcx
  unsigned __int64 v58; // rdx
  char v59; // r9
  char *v60; // rax
  char *v61; // rax

  if ( a2[3] <= 0xFu )
  {
    v4 = a2;
    v3 = (unsigned __int8 *)a2;
    v5 = (char *)a2;
  }
  else
  {
    v3 = (unsigned __int8 *)*a2;
    v4 = (_QWORD *)*a2;
    v5 = (char *)*a2;
  }
  v6 = (unsigned __int8 *)v4 + a2[2];
  if ( v3 != v6 )
  {
    v7 = (unsigned __int64 *)(Src + 24);
    v8 = (unsigned __int64 *)(Src + 16);
    while ( 1 )
    {
      v9 = *v5;
      switch ( *v5 )
      {
        case 8:
          v20 = *v8;
          v21 = *v7;
          if ( *v8 >= *v7 )
          {
            ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAXD_Z_D___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXD_Z_D_Z(Src);
          }
          else
          {
            *v8 = v20 + 1;
            v22 = Src;
            if ( v21 > 0xF )
              v22 = *(char **)Src;
            *(_WORD *)&v22[v20] = 92;
          }
          v23 = *v8;
          v24 = *v7;
          if ( *v8 >= *v7 )
            goto LABEL_26;
          *v8 = v23 + 1;
          if ( v24 <= 0xF )
            *(_WORD *)&Src[v23] = 98;
          else
            *(_WORD *)(*(_QWORD *)Src + v23) = 98;
          goto LABEL_27;
        case 9:
          v40 = *v8;
          v41 = *v7;
          if ( *v8 >= *v7 )
          {
            ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAXD_Z_D___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXD_Z_D_Z(Src);
          }
          else
          {
            *v8 = v40 + 1;
            v42 = Src;
            if ( v41 > 0xF )
              v42 = *(char **)Src;
            *(_WORD *)&v42[v40] = 92;
          }
          v43 = *v8;
          v44 = *v7;
          if ( *v8 >= *v7 )
            goto LABEL_26;
          *((_QWORD *)Src + 2) = v43 + 1;
          if ( v44 <= 0xF )
            *(_WORD *)&Src[v43] = 116;
          else
            *(_WORD *)(*(_QWORD *)Src + v43) = 116;
          goto LABEL_27;
        case 10:
          v35 = *v8;
          v36 = *v7;
          if ( *v8 >= *v7 )
          {
            ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAXD_Z_D___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXD_Z_D_Z(Src);
          }
          else
          {
            *v8 = v35 + 1;
            v37 = Src;
            if ( v36 > 0xF )
              v37 = *(char **)Src;
            *(_WORD *)&v37[v35] = 92;
          }
          v38 = *v8;
          v39 = *v7;
          if ( *v8 >= *v7 )
            goto LABEL_26;
          *((_QWORD *)Src + 2) = v38 + 1;
          if ( v39 <= 0xF )
            *(_WORD *)&Src[v38] = 110;
          else
            *(_WORD *)(*(_QWORD *)Src + v38) = 110;
          goto LABEL_27;
        case 12:
          v25 = *v8;
          v26 = *v7;
          if ( *v8 >= *v7 )
          {
            ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAXD_Z_D___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXD_Z_D_Z(Src);
          }
          else
          {
            *v8 = v25 + 1;
            v27 = Src;
            if ( v26 > 0xF )
              v27 = *(char **)Src;
            *(_WORD *)&v27[v25] = 92;
          }
          v28 = *v8;
          v29 = *v7;
          if ( *v8 >= *v7 )
            goto LABEL_26;
          *((_QWORD *)Src + 2) = v28 + 1;
          if ( v29 <= 0xF )
            *(_WORD *)&Src[v28] = 102;
          else
            *(_WORD *)(*(_QWORD *)Src + v28) = 102;
          goto LABEL_27;
        case 13:
          v30 = *v8;
          v31 = *v7;
          if ( *v8 >= *v7 )
          {
            ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAXD_Z_D___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXD_Z_D_Z(Src);
          }
          else
          {
            *v8 = v30 + 1;
            v32 = Src;
            if ( v31 > 0xF )
              v32 = *(char **)Src;
            *(_WORD *)&v32[v30] = 92;
          }
          v33 = *v8;
          v34 = *v7;
          if ( *v8 >= *v7 )
            goto LABEL_26;
          *((_QWORD *)Src + 2) = v33 + 1;
          if ( v34 <= 0xF )
            *(_WORD *)&Src[v33] = 114;
          else
            *(_WORD *)(*(_QWORD *)Src + v33) = 114;
          goto LABEL_27;
        case 34:
          v10 = *v8;
          v11 = *v7;
          if ( *v8 >= *v7 )
          {
            ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAXD_Z_D___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXD_Z_D_Z(Src);
          }
          else
          {
            *v8 = v10 + 1;
            v12 = Src;
            if ( v11 > 0xF )
              v12 = *(char **)Src;
            *(_WORD *)&v12[v10] = 92;
          }
          v13 = *v8;
          v14 = *v7;
          if ( *v8 >= *v7 )
          {
            ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAXD_Z_D___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXD_Z_D_Z(Src);
            v8 = (unsigned __int64 *)(Src + 16);
            v7 = (unsigned __int64 *)(Src + 24);
          }
          else
          {
            *v8 = v13 + 1;
            if ( v14 <= 0xF )
            {
              *(_WORD *)&Src[v13] = 34;
              v8 = (unsigned __int64 *)(Src + 16);
              v7 = (unsigned __int64 *)(Src + 24);
            }
            else
            {
              v8 = (unsigned __int64 *)(Src + 16);
              v7 = (unsigned __int64 *)(Src + 24);
              *(_WORD *)(v13 + *(_QWORD *)Src) = 34;
            }
          }
          goto LABEL_27;
        case 92:
          v15 = *v8;
          v16 = *v7;
          if ( *v8 >= *v7 )
          {
            ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAXD_Z_D___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXD_Z_D_Z(Src);
          }
          else
          {
            *v8 = v15 + 1;
            v17 = Src;
            if ( v16 > 0xF )
              v17 = *(char **)Src;
            *(_WORD *)&v17[v15] = 92;
          }
          v18 = *v8;
          v19 = *v7;
          if ( *v8 >= *v7 )
            goto LABEL_26;
          *v8 = v18 + 1;
          if ( v19 <= 0xF )
            *(_WORD *)&Src[v18] = 92;
          else
            *(_WORD *)(v18 + *(_QWORD *)Src) = 92;
          goto LABEL_27;
        default:
          v45 = *v8;
          v46 = *v7;
          if ( (unsigned __int8)v9 > 0x1Fu )
          {
            if ( v45 < v46 )
            {
              *v8 = v45 + 1;
              goto LABEL_109;
            }
          }
          else
          {
            if ( v45 >= v46 )
            {
              ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAXD_Z_D___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXD_Z_D_Z(Src);
            }
            else
            {
              *v8 = v45 + 1;
              v47 = Src;
              if ( v46 > 0xF )
                v47 = *(char **)Src;
              *(_WORD *)&v47[v45] = 92;
            }
            v48 = *((_QWORD *)Src + 2);
            v49 = *((_QWORD *)Src + 3);
            if ( v48 >= v49 )
            {
              ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAXD_Z_D___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXD_Z_D_Z(Src);
            }
            else
            {
              *((_QWORD *)Src + 2) = v48 + 1;
              v50 = Src;
              if ( v49 > 0xF )
                v50 = *(char **)Src;
              *(_WORD *)&v50[v48] = 117;
            }
            v51 = *((_QWORD *)Src + 2);
            v52 = *((_QWORD *)Src + 3);
            if ( v51 >= v52 )
            {
              ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAXD_Z_D___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXD_Z_D_Z(Src);
            }
            else
            {
              *((_QWORD *)Src + 2) = v51 + 1;
              v53 = Src;
              if ( v52 > 0xF )
                v53 = *(char **)Src;
              *(_WORD *)&v53[v51] = 48;
            }
            v54 = *((_QWORD *)Src + 2);
            v55 = *((_QWORD *)Src + 3);
            if ( v54 >= v55 )
            {
              ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAXD_Z_D___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXD_Z_D_Z(Src);
            }
            else
            {
              *((_QWORD *)Src + 2) = v54 + 1;
              v56 = Src;
              if ( v55 > 0xF )
                v56 = *(char **)Src;
              *(_WORD *)&v56[v54] = 48;
            }
            v57 = *((_QWORD *)Src + 2);
            v58 = *((_QWORD *)Src + 3);
            v59 = `web::json::details::append_escape_string<char>'::`11'::intToHex[(unsigned __int64)(unsigned __int8)*v5 >> 4];
            if ( v57 >= v58 )
            {
              ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAXD_Z_D___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXD_Z_D_Z(Src);
            }
            else
            {
              *((_QWORD *)Src + 2) = v57 + 1;
              v60 = Src;
              if ( v58 > 0xF )
                v60 = *(char **)Src;
              v60[v57] = v59;
              v60[v57 + 1] = 0;
            }
            v45 = *((_QWORD *)Src + 2);
            v46 = *((_QWORD *)Src + 3);
            v9 = `web::json::details::append_escape_string<char>'::`11'::intToHex[*v5 & 0xF];
            if ( v45 < v46 )
            {
              *((_QWORD *)Src + 2) = v45 + 1;
LABEL_109:
              v61 = Src;
              if ( v46 > 0xF )
                v61 = *(char **)Src;
              v61[v45 + 1] = 0;
              v61[v45] = v9;
              goto LABEL_27;
            }
          }
LABEL_26:
          ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAXD_Z_D___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXD_Z_D_Z(Src);
LABEL_27:
          if ( ++v5 == (char *)v6 )
            return;
          break;
      }
    }
  }
}

```

## disassembly

```asm
0x180006cb0  push    rbx
0x180006cb2  push    rbp
0x180006cb3  push    r14
0x180006cb5  sub     rsp, 20h
0x180006cb9  cmp     qword ptr [rdx+18h], 0Fh
0x180006cbe  mov     rbx, rcx
0x180006cc1  jbe     short loc_180006CCE
0x180006cc3  mov     rcx, [rdx]
0x180006cc6  mov     r8, rcx
0x180006cc9  mov     r14, rcx
0x180006ccc  jmp     short loc_180006CD7
0x180006cce  mov     r8, rdx
0x180006cd1  mov     rcx, rdx
0x180006cd4  mov     r14, rdx
0x180006cd7  mov     rbp, [rdx+10h]
0x180006cdb  add     rbp, r8
0x180006cde  cmp     rcx, rbp
0x180006ce1  jz      loc_180006E6A
0x180006ce7  mov     [rsp+38h+arg_0], rsi
0x180006cec  lea     rsi, [rbx+18h]
0x180006cf0  mov     [rsp+38h+arg_8], rdi
0x180006cf5  lea     rdi, [rbx+10h]
0x180006cf9  mov     [rsp+38h+arg_10], r15
0x180006cfe  lea     r15, cs:180000000h
0x180006d05  nop     word ptr [rax+rax+00000000h]
0x180006d10  movsx   r9d, byte ptr [r14]
0x180006d14  mov     eax, r9d
0x180006d17  add     eax, 0FFFFFFF8h; switch 85 cases
0x180006d1a  cmp     eax, 54h
0x180006d1d  ja      def_180006D39; jumptable 0000000180006D39 default case, cases 11,14-33,35-91
0x180006d23  cdqe
0x180006d25  movzx   eax, ds:(byte_180007278 - 180000000h)[r15+rax]
0x180006d2e  mov     ecx, ds:(jpt_180006D39 - 180000000h)[r15+rax*4]
0x180006d36  add     rcx, r15
0x180006d39  jmp     rcx; switch jump
0x180006d3b  mov     rcx, [rdi]; jumptable 0000000180006D39 case 34
0x180006d3e  mov     rdx, [rsi]
0x180006d41  cmp     rcx, rdx
0x180006d44  jnb     short loc_180006D61
0x180006d46  lea     rax, [rcx+1]
0x180006d4a  mov     [rdi], rax
0x180006d4d  mov     rax, rbx
0x180006d50  cmp     rdx, 0Fh
0x180006d54  jbe     short loc_180006D59
0x180006d56  mov     rax, [rbx]
0x180006d59  mov     word ptr [rcx+rax], 5Ch ; '\'
0x180006d5f  jmp     short loc_180006D74
0x180006d61  mov     r9b, 5Ch ; '\'
0x180006d64  xor     r8d, r8d
0x180006d67  mov     edx, 1
0x180006d6c  mov     rcx, rbx; Src
0x180006d6f  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXD@Z@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXD@Z@D@Z; std::string::_Reallocate_grow_by<`std::string::push_back(char)'::`2'::_lambda_1_,char>(unsigned __int64,`std::string::push_back(char)'::`2'::_lambda_1_,char)
0x180006d74  mov     rcx, [rdi]
0x180006d77  mov     rdx, [rsi]
0x180006d7a  cmp     rcx, rdx
0x180006d7d  jnb     short loc_180006DB8
0x180006d7f  lea     rax, [rcx+1]
0x180006d83  mov     [rdi], rax
0x180006d86  cmp     rdx, 0Fh
0x180006d8a  jbe     short loc_180006DA2
0x180006d8c  mov     rax, [rbx]
0x180006d8f  lea     rdi, [rbx+10h]
0x180006d93  lea     rsi, [rbx+18h]
0x180006d97  mov     word ptr [rcx+rax], 22h ; '"'
0x180006d9d  jmp     loc_180006E4F
0x180006da2  mov     rax, rbx
0x180006da5  mov     word ptr [rcx+rbx], 22h ; '"'
0x180006dab  lea     rdi, [rbx+10h]
0x180006daf  lea     rsi, [rbx+18h]
0x180006db3  jmp     loc_180006E4F
0x180006db8  mov     r9b, 22h ; '"'
0x180006dbb  xor     r8d, r8d
0x180006dbe  mov     edx, 1
0x180006dc3  mov     rcx, rbx; Src
0x180006dc6  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXD@Z@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXD@Z@D@Z; std::string::_Reallocate_grow_by<`std::string::push_back(char)'::`2'::_lambda_1_,char>(unsigned __int64,`std::string::push_back(char)'::`2'::_lambda_1_,char)
0x180006dcb  lea     rdi, [rbx+10h]
0x180006dcf  lea     rsi, [rbx+18h]
0x180006dd3  jmp     short loc_180006E4F
0x180006dd5  mov     rcx, [rdi]; jumptable 0000000180006D39 case 92
0x180006dd8  mov     rdx, [rsi]
0x180006ddb  cmp     rcx, rdx
0x180006dde  jnb     short loc_180006DFB
0x180006de0  lea     rax, [rcx+1]
0x180006de4  mov     [rdi], rax
0x180006de7  mov     rax, rbx
0x180006dea  cmp     rdx, 0Fh
0x180006dee  jbe     short loc_180006DF3
0x180006df0  mov     rax, [rbx]
0x180006df3  mov     word ptr [rcx+rax], 5Ch ; '\'
0x180006df9  jmp     short loc_180006E0E
0x180006dfb  mov     r9b, 5Ch ; '\'
0x180006dfe  xor     r8d, r8d
0x180006e01  mov     edx, 1
0x180006e06  mov     rcx, rbx; Src
0x180006e09  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXD@Z@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXD@Z@D@Z; std::string::_Reallocate_grow_by<`std::string::push_back(char)'::`2'::_lambda_1_,char>(unsigned __int64,`std::string::push_back(char)'::`2'::_lambda_1_,char)
0x180006e0e  mov     rcx, [rdi]
0x180006e11  mov     rdx, [rsi]
0x180006e14  cmp     rcx, rdx
0x180006e17  jnb     short loc_180006E3C
0x180006e19  lea     rax, [rcx+1]
0x180006e1d  mov     [rdi], rax
0x180006e20  cmp     rdx, 0Fh
0x180006e24  jbe     short loc_180006E31
0x180006e26  mov     rax, [rbx]
0x180006e29  mov     word ptr [rcx+rax], 5Ch ; '\'
0x180006e2f  jmp     short loc_180006E4F
0x180006e31  mov     rax, rbx
0x180006e34  mov     word ptr [rcx+rbx], 5Ch ; '\'
0x180006e3a  jmp     short loc_180006E4F
0x180006e3c  mov     r9b, 5Ch ; '\'
0x180006e3f  xor     r8d, r8d
0x180006e42  mov     edx, 1
0x180006e47  mov     rcx, rbx; Src
0x180006e4a  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXD@Z@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXD@Z@D@Z; std::string::_Reallocate_grow_by<`std::string::push_back(char)'::`2'::_lambda_1_,char>(unsigned __int64,`std::string::push_back(char)'::`2'::_lambda_1_,char)
0x180006e4f  inc     r14
0x180006e52  cmp     r14, rbp
0x180006e55  jnz     loc_180006D10
0x180006e5b  mov     r15, [rsp+38h+arg_10]
0x180006e60  mov     rdi, [rsp+38h+arg_8]
0x180006e65  mov     rsi, [rsp+38h+arg_0]
0x180006e6a  add     rsp, 20h
0x180006e6e  pop     r14
0x180006e70  pop     rbp
0x180006e71  pop     rbx
0x180006e72  retn
0x180006e73  mov     rcx, [rdi]; jumptable 0000000180006D39 case 8
0x180006e76  mov     rdx, [rsi]
0x180006e79  cmp     rcx, rdx
0x180006e7c  jnb     short loc_180006E99
0x180006e7e  lea     rax, [rcx+1]
0x180006e82  mov     [rdi], rax
0x180006e85  mov     rax, rbx
0x180006e88  cmp     rdx, 0Fh
0x180006e8c  jbe     short loc_180006E91
0x180006e8e  mov     rax, [rbx]
0x180006e91  mov     word ptr [rax+rcx], 5Ch ; '\'
0x180006e97  jmp     short loc_180006EAC
0x180006e99  mov     r9b, 5Ch ; '\'
0x180006e9c  xor     r8d, r8d
0x180006e9f  mov     edx, 1
0x180006ea4  mov     rcx, rbx; Src
0x180006ea7  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXD@Z@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXD@Z@D@Z; std::string::_Reallocate_grow_by<`std::string::push_back(char)'::`2'::_lambda_1_,char>(unsigned __int64,`std::string::push_back(char)'::`2'::_lambda_1_,char)
0x180006eac  mov     rcx, [rdi]
0x180006eaf  mov     rdx, [rsi]
0x180006eb2  cmp     rcx, rdx
0x180006eb5  jnb     short loc_180006EDD
0x180006eb7  lea     rax, [rcx+1]
0x180006ebb  mov     [rdi], rax
0x180006ebe  cmp     rdx, 0Fh
0x180006ec2  jbe     short loc_180006ECF
0x180006ec4  mov     rax, [rbx]
0x180006ec7  mov     word ptr [rax+rcx], 62h ; 'b'
0x180006ecd  jmp     short loc_180006E4F
0x180006ecf  mov     rax, rbx
0x180006ed2  mov     word ptr [rbx+rcx], 62h ; 'b'
0x180006ed8  jmp     loc_180006E4F
0x180006edd  mov     r9b, 62h ; 'b'
0x180006ee0  jmp     loc_180006E3F
0x180006ee5  mov     rcx, [rdi]; jumptable 0000000180006D39 case 12
0x180006ee8  mov     rdx, [rsi]
0x180006eeb  cmp     rcx, rdx
0x180006eee  jnb     short loc_180006F0B
0x180006ef0  lea     rax, [rcx+1]
0x180006ef4  mov     [rdi], rax
0x180006ef7  mov     rax, rbx
0x180006efa  cmp     rdx, 0Fh
0x180006efe  jbe     short loc_180006F03
0x180006f00  mov     rax, [rbx]
0x180006f03  mov     word ptr [rax+rcx], 5Ch ; '\'
0x180006f09  jmp     short loc_180006F1E
0x180006f0b  mov     r9b, 5Ch ; '\'
0x180006f0e  xor     r8d, r8d
0x180006f11  mov     edx, 1
0x180006f16  mov     rcx, rbx; Src
0x180006f19  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXD@Z@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXD@Z@D@Z; std::string::_Reallocate_grow_by<`std::string::push_back(char)'::`2'::_lambda_1_,char>(unsigned __int64,`std::string::push_back(char)'::`2'::_lambda_1_,char)
0x180006f1e  mov     rcx, [rdi]
0x180006f21  mov     rdx, [rsi]
0x180006f24  cmp     rcx, rdx
0x180006f27  jnb     short loc_180006F53
0x180006f29  lea     rax, [rcx+1]
0x180006f2d  mov     [rbx+10h], rax
0x180006f31  cmp     rdx, 0Fh
0x180006f35  jbe     short loc_180006F45
0x180006f37  mov     rax, [rbx]
0x180006f3a  mov     word ptr [rax+rcx], 66h ; 'f'
0x180006f40  jmp     loc_180006E4F
0x180006f45  mov     rax, rbx
0x180006f48  mov     word ptr [rbx+rcx], 66h ; 'f'
0x180006f4e  jmp     loc_180006E4F
0x180006f53  mov     r9b, 66h ; 'f'
0x180006f56  jmp     loc_180006E3F
0x180006f5b  mov     rcx, [rdi]; jumptable 0000000180006D39 case 13
0x180006f5e  mov     rdx, [rsi]
0x180006f61  cmp     rcx, rdx
0x180006f64  jnb     short loc_180006F81
0x180006f66  lea     rax, [rcx+1]
0x180006f6a  mov     [rdi], rax
0x180006f6d  mov     rax, rbx
0x180006f70  cmp     rdx, 0Fh
0x180006f74  jbe     short loc_180006F79
0x180006f76  mov     rax, [rbx]
0x180006f79  mov     word ptr [rax+rcx], 5Ch ; '\'
0x180006f7f  jmp     short loc_180006F94
0x180006f81  mov     r9b, 5Ch ; '\'
0x180006f84  xor     r8d, r8d
0x180006f87  mov     edx, 1
0x180006f8c  mov     rcx, rbx; Src
0x180006f8f  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXD@Z@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXD@Z@D@Z; std::string::_Reallocate_grow_by<`std::string::push_back(char)'::`2'::_lambda_1_,char>(unsigned __int64,`std::string::push_back(char)'::`2'::_lambda_1_,char)
0x180006f94  mov     rcx, [rdi]
0x180006f97  mov     rdx, [rsi]
0x180006f9a  cmp     rcx, rdx
0x180006f9d  jnb     short loc_180006FC9
0x180006f9f  lea     rax, [rcx+1]
0x180006fa3  mov     [rbx+10h], rax
0x180006fa7  cmp     rdx, 0Fh
0x180006fab  jbe     short loc_180006FBB
0x180006fad  mov     rax, [rbx]
0x180006fb0  mov     word ptr [rax+rcx], 72h ; 'r'
0x180006fb6  jmp     loc_180006E4F
0x180006fbb  mov     rax, rbx
0x180006fbe  mov     word ptr [rbx+rcx], 72h ; 'r'
0x180006fc4  jmp     loc_180006E4F
0x180006fc9  mov     r9b, 72h ; 'r'
0x180006fcc  jmp     loc_180006E3F
0x180006fd1  mov     rcx, [rdi]; jumptable 0000000180006D39 case 10
0x180006fd4  mov     rdx, [rsi]
0x180006fd7  cmp     rcx, rdx
0x180006fda  jnb     short loc_180006FF7
0x180006fdc  lea     rax, [rcx+1]
0x180006fe0  mov     [rdi], rax
0x180006fe3  mov     rax, rbx
0x180006fe6  cmp     rdx, 0Fh
0x180006fea  jbe     short loc_180006FEF
0x180006fec  mov     rax, [rbx]
0x180006fef  mov     word ptr [rax+rcx], 5Ch ; '\'
0x180006ff5  jmp     short loc_18000700A
0x180006ff7  mov     r9b, 5Ch ; '\'
0x180006ffa  xor     r8d, r8d
0x180006ffd  mov     edx, 1
0x180007002  mov     rcx, rbx; Src
0x180007005  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXD@Z@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXD@Z@D@Z; std::string::_Reallocate_grow_by<`std::string::push_back(char)'::`2'::_lambda_1_,char>(unsigned __int64,`std::string::push_back(char)'::`2'::_lambda_1_,char)
0x18000700a  mov     rcx, [rdi]
0x18000700d  mov     rdx, [rsi]
0x180007010  cmp     rcx, rdx
0x180007013  jnb     short loc_18000703F
0x180007015  lea     rax, [rcx+1]
0x180007019  mov     [rbx+10h], rax
0x18000701d  cmp     rdx, 0Fh
0x180007021  jbe     short loc_180007031
0x180007023  mov     rax, [rbx]
0x180007026  mov     word ptr [rax+rcx], 6Eh ; 'n'
0x18000702c  jmp     loc_180006E4F
0x180007031  mov     rax, rbx
0x180007034  mov     word ptr [rbx+rcx], 6Eh ; 'n'
0x18000703a  jmp     loc_180006E4F
0x18000703f  mov     r9b, 6Eh ; 'n'
0x180007042  jmp     loc_180006E3F
0x180007047  mov     rcx, [rdi]; jumptable 0000000180006D39 case 9
0x18000704a  mov     rdx, [rsi]
0x18000704d  cmp     rcx, rdx
0x180007050  jnb     short loc_18000706D
0x180007052  lea     rax, [rcx+1]
0x180007056  mov     [rdi], rax
0x180007059  mov     rax, rbx
0x18000705c  cmp     rdx, 0Fh
0x180007060  jbe     short loc_180007065
0x180007062  mov     rax, [rbx]
0x180007065  mov     word ptr [rax+rcx], 5Ch ; '\'
0x18000706b  jmp     short loc_180007080
0x18000706d  mov     r9b, 5Ch ; '\'
0x180007070  xor     r8d, r8d
0x180007073  mov     edx, 1
0x180007078  mov     rcx, rbx; Src
0x18000707b  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXD@Z@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXD@Z@D@Z; std::string::_Reallocate_grow_by<`std::string::push_back(char)'::`2'::_lambda_1_,char>(unsigned __int64,`std::string::push_back(char)'::`2'::_lambda_1_,char)
0x180007080  mov     rcx, [rdi]
0x180007083  mov     rdx, [rsi]
0x180007086  cmp     rcx, rdx
0x180007089  jnb     short loc_1800070B5
0x18000708b  lea     rax, [rcx+1]
0x18000708f  mov     [rbx+10h], rax
0x180007093  cmp     rdx, 0Fh
0x180007097  jbe     short loc_1800070A7
0x180007099  mov     rax, [rbx]
0x18000709c  mov     word ptr [rax+rcx], 74h ; 't'
0x1800070a2  jmp     loc_180006E4F
0x1800070a7  mov     rax, rbx
0x1800070aa  mov     word ptr [rbx+rcx], 74h ; 't'
0x1800070b0  jmp     loc_180006E4F
0x1800070b5  mov     r9b, 74h ; 't'
0x1800070b8  jmp     loc_180006E3F
0x1800070bd  mov     rcx, [rdi]; jumptable 0000000180006D39 default case, cases 11,14-33,35-91
0x1800070c0  mov     rdx, [rsi]
0x1800070c3  cmp     r9b, 1Fh
0x1800070c7  ja      loc_18000722C
0x1800070cd  cmp     rcx, rdx
0x1800070d0  jnb     short loc_1800070ED
0x1800070d2  lea     rax, [rcx+1]
0x1800070d6  mov     [rdi], rax
0x1800070d9  mov     rax, rbx
0x1800070dc  cmp     rdx, 0Fh
  ... truncated ...
```
