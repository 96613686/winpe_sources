# web::json::details::append_escape_string<char>(std::basic_string<char,std::char_traits<char>,std::allocator<char>> &,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x180007310`
- end: `0x1800078b1`
- name: `??$append_escape_string@D@details@json@web@@YAXAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV34@@Z`
- size: `1441`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180008170`
- `0x1800084e0`

## callees

- `0x1800040c0`
- `0x180007310`

## pseudocode

```c
void __fastcall web::json::details::append_escape_string<char>(_QWORD *Src, unsigned __int8 *a2)
{
  unsigned __int8 *v3; // rcx
  unsigned __int8 *v4; // r8
  char *v5; // rdi
  unsigned __int8 *v6; // rsi
  char v7; // r9
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rdx
  _QWORD *v10; // rax
  unsigned __int64 v11; // rcx
  unsigned __int64 v12; // rdx
  _QWORD *v13; // rax
  unsigned __int64 v14; // rcx
  unsigned __int64 v15; // rdx
  _QWORD *v16; // rax
  unsigned __int64 v17; // rcx
  unsigned __int64 v18; // rdx
  _QWORD *v19; // rax
  unsigned __int64 v20; // rcx
  unsigned __int64 v21; // rdx
  _QWORD *v22; // rax
  unsigned __int64 v23; // rcx
  unsigned __int64 v24; // rdx
  _QWORD *v25; // rax
  unsigned __int64 v26; // rcx
  unsigned __int64 v27; // rdx
  _QWORD *v28; // rax
  unsigned __int64 v29; // rcx
  unsigned __int64 v30; // rdx
  _QWORD *v31; // rax
  unsigned __int64 v32; // rcx
  unsigned __int64 v33; // rdx
  _QWORD *v34; // rax
  unsigned __int64 v35; // rcx
  unsigned __int64 v36; // rdx
  _QWORD *v37; // rax
  unsigned __int64 v38; // rcx
  unsigned __int64 v39; // rdx
  _QWORD *v40; // rax
  unsigned __int64 v41; // rcx
  unsigned __int64 v42; // rdx
  _QWORD *v43; // rax
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
  _QWORD *v58; // rax
  unsigned __int64 v59; // rcx
  unsigned __int64 v60; // rdx
  _QWORD *v61; // rax
  unsigned __int64 v62; // rcx
  unsigned __int64 v63; // rdx
  char v64; // r9
  _QWORD *v65; // rax
  _QWORD *v66; // rax

  v3 = a2;
  if ( *((_QWORD *)a2 + 3) <= 0xFu )
  {
    v4 = a2;
  }
  else
  {
    v3 = *(unsigned __int8 **)a2;
    v4 = *(unsigned __int8 **)a2;
  }
  v5 = (char *)v3;
  v6 = &v4[*((_QWORD *)a2 + 2)];
  if ( v3 != v6 )
  {
    do
    {
      v7 = *v5;
      switch ( *v5 )
      {
        case 8:
          v20 = Src[2];
          v21 = Src[3];
          if ( v20 >= v21 )
          {
            ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAXD_Z_D___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXD_Z_D_Z(Src);
          }
          else
          {
            Src[2] = v20 + 1;
            v22 = Src;
            if ( v21 > 0xF )
              v22 = (_QWORD *)*Src;
            *(_WORD *)((char *)v22 + v20) = 92;
          }
          v23 = Src[2];
          v24 = Src[3];
          if ( v23 >= v24 )
            goto LABEL_15;
          Src[2] = v23 + 1;
          v25 = Src;
          if ( v24 > 0xF )
            v25 = (_QWORD *)*Src;
          *(_WORD *)((char *)v25 + v23) = 98;
          break;
        case 9:
          v44 = Src[2];
          v45 = Src[3];
          if ( v44 >= v45 )
          {
            ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAXD_Z_D___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXD_Z_D_Z(Src);
          }
          else
          {
            Src[2] = v44 + 1;
            v46 = Src;
            if ( v45 > 0xF )
              v46 = (_QWORD *)*Src;
            *(_WORD *)((char *)v46 + v44) = 92;
          }
          v47 = Src[2];
          v48 = Src[3];
          if ( v47 >= v48 )
            goto LABEL_15;
          Src[2] = v47 + 1;
          v49 = Src;
          if ( v48 > 0xF )
            v49 = (_QWORD *)*Src;
          *(_WORD *)((char *)v49 + v47) = 116;
          break;
        case 10:
          v38 = Src[2];
          v39 = Src[3];
          if ( v38 >= v39 )
          {
            ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAXD_Z_D___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXD_Z_D_Z(Src);
          }
          else
          {
            Src[2] = v38 + 1;
            v40 = Src;
            if ( v39 > 0xF )
              v40 = (_QWORD *)*Src;
            *(_WORD *)((char *)v40 + v38) = 92;
          }
          v41 = Src[2];
          v42 = Src[3];
          if ( v41 >= v42 )
            goto LABEL_15;
          Src[2] = v41 + 1;
          v43 = Src;
          if ( v42 > 0xF )
            v43 = (_QWORD *)*Src;
          *(_WORD *)((char *)v43 + v41) = 110;
          break;
        case 12:
          v26 = Src[2];
          v27 = Src[3];
          if ( v26 >= v27 )
          {
            ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAXD_Z_D___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXD_Z_D_Z(Src);
          }
          else
          {
            Src[2] = v26 + 1;
            v28 = Src;
            if ( v27 > 0xF )
              v28 = (_QWORD *)*Src;
            *(_WORD *)((char *)v28 + v26) = 92;
          }
          v29 = Src[2];
          v30 = Src[3];
          if ( v29 >= v30 )
            goto LABEL_15;
          Src[2] = v29 + 1;
          v31 = Src;
          if ( v30 > 0xF )
            v31 = (_QWORD *)*Src;
          *(_WORD *)((char *)v31 + v29) = 102;
          break;
        case 13:
          v32 = Src[2];
          v33 = Src[3];
          if ( v32 >= v33 )
          {
            ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAXD_Z_D___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXD_Z_D_Z(Src);
          }
          else
          {
            Src[2] = v32 + 1;
            v34 = Src;
            if ( v33 > 0xF )
              v34 = (_QWORD *)*Src;
            *(_WORD *)((char *)v34 + v32) = 92;
          }
          v35 = Src[2];
          v36 = Src[3];
          if ( v35 >= v36 )
            goto LABEL_15;
          Src[2] = v35 + 1;
          v37 = Src;
          if ( v36 > 0xF )
            v37 = (_QWORD *)*Src;
          *(_WORD *)((char *)v37 + v35) = 114;
          break;
        case 34:
          v8 = Src[2];
          v9 = Src[3];
          if ( v8 >= v9 )
          {
            ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAXD_Z_D___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXD_Z_D_Z(Src);
          }
          else
          {
            Src[2] = v8 + 1;
            v10 = Src;
            if ( v9 > 0xF )
              v10 = (_QWORD *)*Src;
            *(_WORD *)((char *)v10 + v8) = 92;
          }
          v11 = Src[2];
          v12 = Src[3];
          if ( v11 >= v12 )
            goto LABEL_15;
          Src[2] = v11 + 1;
          v13 = Src;
          if ( v12 > 0xF )
            v13 = (_QWORD *)*Src;
          *(_WORD *)((char *)v13 + v11) = 34;
          break;
        case 92:
          v14 = Src[2];
          v15 = Src[3];
          if ( v14 >= v15 )
          {
            ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAXD_Z_D___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXD_Z_D_Z(Src);
          }
          else
          {
            Src[2] = v14 + 1;
            v16 = Src;
            if ( v15 > 0xF )
              v16 = (_QWORD *)*Src;
            *(_WORD *)((char *)v16 + v14) = 92;
          }
          v17 = Src[2];
          v18 = Src[3];
          if ( v17 >= v18 )
            goto LABEL_15;
          Src[2] = v17 + 1;
          v19 = Src;
          if ( v18 > 0xF )
            v19 = (_QWORD *)*Src;
          *(_WORD *)((char *)v19 + v17) = 92;
          break;
        default:
          v50 = Src[2];
          v51 = Src[3];
          if ( (unsigned __int8)v7 <= 0x1Fu )
          {
            if ( v50 >= v51 )
            {
              ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAXD_Z_D___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXD_Z_D_Z(Src);
            }
            else
            {
              Src[2] = v50 + 1;
              v52 = Src;
              if ( v51 > 0xF )
                v52 = (_QWORD *)*Src;
              *(_WORD *)((char *)v52 + v50) = 92;
            }
            v53 = Src[2];
            v54 = Src[3];
            if ( v53 >= v54 )
            {
              ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAXD_Z_D___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXD_Z_D_Z(Src);
            }
            else
            {
              Src[2] = v53 + 1;
              v55 = Src;
              if ( v54 > 0xF )
                v55 = (_QWORD *)*Src;
              *(_WORD *)((char *)v55 + v53) = 117;
            }
            v56 = Src[2];
            v57 = Src[3];
            if ( v56 >= v57 )
            {
              ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAXD_Z_D___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXD_Z_D_Z(Src);
            }
            else
            {
              Src[2] = v56 + 1;
              v58 = Src;
              if ( v57 > 0xF )
                v58 = (_QWORD *)*Src;
              *(_WORD *)((char *)v58 + v56) = 48;
            }
            v59 = Src[2];
            v60 = Src[3];
            if ( v59 >= v60 )
            {
              ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAXD_Z_D___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXD_Z_D_Z(Src);
            }
            else
            {
              Src[2] = v59 + 1;
              v61 = Src;
              if ( v60 > 0xF )
                v61 = (_QWORD *)*Src;
              *(_WORD *)((char *)v61 + v59) = 48;
            }
            v62 = Src[2];
            v63 = Src[3];
            v64 = `web::json::details::append_escape_string<char>'::`11'::intToHex[(unsigned __int64)(unsigned __int8)*v5 >> 4];
            if ( v62 >= v63 )
            {
              ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAXD_Z_D___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXD_Z_D_Z(Src);
            }
            else
            {
              Src[2] = v62 + 1;
              v65 = Src;
              if ( v63 > 0xF )
                v65 = (_QWORD *)*Src;
              *((_BYTE *)v65 + v62) = v64;
              *((_BYTE *)v65 + v62 + 1) = 0;
            }
            v50 = Src[2];
            v51 = Src[3];
            v7 = `web::json::details::append_escape_string<char>'::`11'::intToHex[*v5 & 0xF];
          }
          if ( v50 >= v51 )
          {
LABEL_15:
            ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAXD_Z_D___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXD_Z_D_Z(Src);
          }
          else
          {
            Src[2] = v50 + 1;
            v66 = Src;
            if ( v51 > 0xF )
              v66 = (_QWORD *)*Src;
            *((_BYTE *)v66 + v50 + 1) = 0;
            *((_BYTE *)v66 + v50) = v7;
          }
          break;
      }
      ++v5;
    }
    while ( v5 != (char *)v6 );
  }
}

```

## disassembly

```asm
0x180007310  mov     [rsp+arg_8], rbx
0x180007315  mov     [rsp+arg_10], rsi
0x18000731a  push    rdi
0x18000731b  sub     rsp, 20h
0x18000731f  cmp     qword ptr [rdx+18h], 0Fh
0x180007324  mov     rbx, rcx
0x180007327  mov     rcx, rdx
0x18000732a  jbe     short loc_180007334
0x18000732c  mov     rcx, [rdx]
0x18000732f  mov     r8, rcx
0x180007332  jmp     short loc_180007337
0x180007334  mov     r8, rdx
0x180007337  mov     rsi, [rdx+10h]
0x18000733b  mov     rdi, rcx
0x18000733e  add     rsi, r8
0x180007341  cmp     rcx, rsi
0x180007344  jz      loc_18000740E
0x18000734a  mov     [rsp+28h+arg_0], rbp
0x18000734f  lea     rbp, cs:180000000h
0x180007356  nop     word ptr [rax+rax+00000000h]
0x180007360  movsx   r9d, byte ptr [rdi]
0x180007364  lea     eax, [r9-8]; switch 85 cases
0x180007368  cmp     eax, 54h
0x18000736b  ja      def_180007385; jumptable 0000000180007385 default case, cases 11,14-33,35-91
0x180007371  cdqe
0x180007373  movzx   eax, ds:(byte_18000785C - 180000000h)[rax+rbp]
0x18000737b  mov     ecx, ss:(jpt_180007385 - 180000000h)[rbp+rax*4]
0x180007382  add     rcx, rbp
0x180007385  jmp     rcx; switch jump
0x180007387  mov     rcx, [rbx+10h]; jumptable 0000000180007385 case 34
0x18000738b  mov     rdx, [rbx+18h]
0x18000738f  cmp     rcx, rdx
0x180007392  jnb     short loc_1800073B0
0x180007394  lea     rax, [rcx+1]
0x180007398  mov     [rbx+10h], rax
0x18000739c  mov     rax, rbx
0x18000739f  cmp     rdx, 0Fh
0x1800073a3  jbe     short loc_1800073A8
0x1800073a5  mov     rax, [rbx]
0x1800073a8  mov     word ptr [rax+rcx], 5Ch ; '\'
0x1800073ae  jmp     short loc_1800073C2
0x1800073b0  xor     r8d, r8d
0x1800073b3  mov     r9b, 5Ch ; '\'
0x1800073b6  mov     rcx, rbx; Src
0x1800073b9  lea     edx, [r8+1]
0x1800073bd  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXD@Z@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXD@Z@D@Z; std::string::_Reallocate_grow_by<`std::string::push_back(char)'::`2'::_lambda_1_,char>(unsigned __int64,`std::string::push_back(char)'::`2'::_lambda_1_,char)
0x1800073c2  mov     rcx, [rbx+10h]
0x1800073c6  mov     rdx, [rbx+18h]
0x1800073ca  cmp     rcx, rdx
0x1800073cd  jnb     short loc_1800073EB
0x1800073cf  lea     rax, [rcx+1]
0x1800073d3  mov     [rbx+10h], rax
0x1800073d7  mov     rax, rbx
0x1800073da  cmp     rdx, 0Fh
0x1800073de  jbe     short loc_1800073E3
0x1800073e0  mov     rax, [rbx]
0x1800073e3  mov     word ptr [rax+rcx], 22h ; '"'
0x1800073e9  jmp     short loc_1800073FD
0x1800073eb  mov     r9b, 22h ; '"'
0x1800073ee  xor     r8d, r8d
0x1800073f1  mov     rcx, rbx; Src
0x1800073f4  lea     edx, [r8+1]
0x1800073f8  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXD@Z@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXD@Z@D@Z; std::string::_Reallocate_grow_by<`std::string::push_back(char)'::`2'::_lambda_1_,char>(unsigned __int64,`std::string::push_back(char)'::`2'::_lambda_1_,char)
0x1800073fd  inc     rdi
0x180007400  cmp     rdi, rsi
0x180007403  jnz     loc_180007360
0x180007409  mov     rbp, [rsp+28h+arg_0]
0x18000740e  mov     rbx, [rsp+28h+arg_8]
0x180007413  mov     rsi, [rsp+28h+arg_10]
0x180007418  add     rsp, 20h
0x18000741c  pop     rdi
0x18000741d  retn
0x18000741e  mov     rcx, [rbx+10h]; jumptable 0000000180007385 case 92
0x180007422  mov     rdx, [rbx+18h]
0x180007426  cmp     rcx, rdx
0x180007429  jnb     short loc_180007447
0x18000742b  lea     rax, [rcx+1]
0x18000742f  mov     [rbx+10h], rax
0x180007433  mov     rax, rbx
0x180007436  cmp     rdx, 0Fh
0x18000743a  jbe     short loc_18000743F
0x18000743c  mov     rax, [rbx]
0x18000743f  mov     word ptr [rax+rcx], 5Ch ; '\'
0x180007445  jmp     short loc_180007459
0x180007447  xor     r8d, r8d
0x18000744a  mov     r9b, 5Ch ; '\'
0x18000744d  mov     rcx, rbx; Src
0x180007450  lea     edx, [r8+1]
0x180007454  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXD@Z@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXD@Z@D@Z; std::string::_Reallocate_grow_by<`std::string::push_back(char)'::`2'::_lambda_1_,char>(unsigned __int64,`std::string::push_back(char)'::`2'::_lambda_1_,char)
0x180007459  mov     rcx, [rbx+10h]
0x18000745d  mov     rdx, [rbx+18h]
0x180007461  cmp     rcx, rdx
0x180007464  jnb     short loc_180007485
0x180007466  lea     rax, [rcx+1]
0x18000746a  mov     [rbx+10h], rax
0x18000746e  mov     rax, rbx
0x180007471  cmp     rdx, 0Fh
0x180007475  jbe     short loc_18000747A
0x180007477  mov     rax, [rbx]
0x18000747a  mov     word ptr [rax+rcx], 5Ch ; '\'
0x180007480  jmp     loc_1800073FD
0x180007485  mov     r9b, 5Ch ; '\'
0x180007488  jmp     loc_1800073EE
0x18000748d  mov     rcx, [rbx+10h]; jumptable 0000000180007385 case 8
0x180007491  mov     rdx, [rbx+18h]
0x180007495  cmp     rcx, rdx
0x180007498  jnb     short loc_1800074B6
0x18000749a  lea     rax, [rcx+1]
0x18000749e  mov     [rbx+10h], rax
0x1800074a2  mov     rax, rbx
0x1800074a5  cmp     rdx, 0Fh
0x1800074a9  jbe     short loc_1800074AE
0x1800074ab  mov     rax, [rbx]
0x1800074ae  mov     word ptr [rax+rcx], 5Ch ; '\'
0x1800074b4  jmp     short loc_1800074C8
0x1800074b6  xor     r8d, r8d
0x1800074b9  mov     r9b, 5Ch ; '\'
0x1800074bc  mov     rcx, rbx; Src
0x1800074bf  lea     edx, [r8+1]
0x1800074c3  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXD@Z@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXD@Z@D@Z; std::string::_Reallocate_grow_by<`std::string::push_back(char)'::`2'::_lambda_1_,char>(unsigned __int64,`std::string::push_back(char)'::`2'::_lambda_1_,char)
0x1800074c8  mov     rcx, [rbx+10h]
0x1800074cc  mov     rdx, [rbx+18h]
0x1800074d0  cmp     rcx, rdx
0x1800074d3  jnb     short loc_1800074F4
0x1800074d5  lea     rax, [rcx+1]
0x1800074d9  mov     [rbx+10h], rax
0x1800074dd  mov     rax, rbx
0x1800074e0  cmp     rdx, 0Fh
0x1800074e4  jbe     short loc_1800074E9
0x1800074e6  mov     rax, [rbx]
0x1800074e9  mov     word ptr [rax+rcx], 62h ; 'b'
0x1800074ef  jmp     loc_1800073FD
0x1800074f4  mov     r9b, 62h ; 'b'
0x1800074f7  jmp     loc_1800073EE
0x1800074fc  mov     rcx, [rbx+10h]; jumptable 0000000180007385 case 12
0x180007500  mov     rdx, [rbx+18h]
0x180007504  cmp     rcx, rdx
0x180007507  jnb     short loc_180007525
0x180007509  lea     rax, [rcx+1]
0x18000750d  mov     [rbx+10h], rax
0x180007511  mov     rax, rbx
0x180007514  cmp     rdx, 0Fh
0x180007518  jbe     short loc_18000751D
0x18000751a  mov     rax, [rbx]
0x18000751d  mov     word ptr [rax+rcx], 5Ch ; '\'
0x180007523  jmp     short loc_180007537
0x180007525  xor     r8d, r8d
0x180007528  mov     r9b, 5Ch ; '\'
0x18000752b  mov     rcx, rbx; Src
0x18000752e  lea     edx, [r8+1]
0x180007532  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXD@Z@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXD@Z@D@Z; std::string::_Reallocate_grow_by<`std::string::push_back(char)'::`2'::_lambda_1_,char>(unsigned __int64,`std::string::push_back(char)'::`2'::_lambda_1_,char)
0x180007537  mov     rcx, [rbx+10h]
0x18000753b  mov     rdx, [rbx+18h]
0x18000753f  cmp     rcx, rdx
0x180007542  jnb     short loc_180007563
0x180007544  lea     rax, [rcx+1]
0x180007548  mov     [rbx+10h], rax
0x18000754c  mov     rax, rbx
0x18000754f  cmp     rdx, 0Fh
0x180007553  jbe     short loc_180007558
0x180007555  mov     rax, [rbx]
0x180007558  mov     word ptr [rax+rcx], 66h ; 'f'
0x18000755e  jmp     loc_1800073FD
0x180007563  mov     r9b, 66h ; 'f'
0x180007566  jmp     loc_1800073EE
0x18000756b  mov     rcx, [rbx+10h]; jumptable 0000000180007385 case 13
0x18000756f  mov     rdx, [rbx+18h]
0x180007573  cmp     rcx, rdx
0x180007576  jnb     short loc_180007594
0x180007578  lea     rax, [rcx+1]
0x18000757c  mov     [rbx+10h], rax
0x180007580  mov     rax, rbx
0x180007583  cmp     rdx, 0Fh
0x180007587  jbe     short loc_18000758C
0x180007589  mov     rax, [rbx]
0x18000758c  mov     word ptr [rax+rcx], 5Ch ; '\'
0x180007592  jmp     short loc_1800075A6
0x180007594  xor     r8d, r8d
0x180007597  mov     r9b, 5Ch ; '\'
0x18000759a  mov     rcx, rbx; Src
0x18000759d  lea     edx, [r8+1]
0x1800075a1  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXD@Z@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXD@Z@D@Z; std::string::_Reallocate_grow_by<`std::string::push_back(char)'::`2'::_lambda_1_,char>(unsigned __int64,`std::string::push_back(char)'::`2'::_lambda_1_,char)
0x1800075a6  mov     rcx, [rbx+10h]
0x1800075aa  mov     rdx, [rbx+18h]
0x1800075ae  cmp     rcx, rdx
0x1800075b1  jnb     short loc_1800075D2
0x1800075b3  lea     rax, [rcx+1]
0x1800075b7  mov     [rbx+10h], rax
0x1800075bb  mov     rax, rbx
0x1800075be  cmp     rdx, 0Fh
0x1800075c2  jbe     short loc_1800075C7
0x1800075c4  mov     rax, [rbx]
0x1800075c7  mov     word ptr [rax+rcx], 72h ; 'r'
0x1800075cd  jmp     loc_1800073FD
0x1800075d2  mov     r9b, 72h ; 'r'
0x1800075d5  jmp     loc_1800073EE
0x1800075da  mov     rcx, [rbx+10h]; jumptable 0000000180007385 case 10
0x1800075de  mov     rdx, [rbx+18h]
0x1800075e2  cmp     rcx, rdx
0x1800075e5  jnb     short loc_180007603
0x1800075e7  lea     rax, [rcx+1]
0x1800075eb  mov     [rbx+10h], rax
0x1800075ef  mov     rax, rbx
0x1800075f2  cmp     rdx, 0Fh
0x1800075f6  jbe     short loc_1800075FB
0x1800075f8  mov     rax, [rbx]
0x1800075fb  mov     word ptr [rax+rcx], 5Ch ; '\'
0x180007601  jmp     short loc_180007615
0x180007603  xor     r8d, r8d
0x180007606  mov     r9b, 5Ch ; '\'
0x180007609  mov     rcx, rbx; Src
0x18000760c  lea     edx, [r8+1]
0x180007610  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXD@Z@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXD@Z@D@Z; std::string::_Reallocate_grow_by<`std::string::push_back(char)'::`2'::_lambda_1_,char>(unsigned __int64,`std::string::push_back(char)'::`2'::_lambda_1_,char)
0x180007615  mov     rcx, [rbx+10h]
0x180007619  mov     rdx, [rbx+18h]
0x18000761d  cmp     rcx, rdx
0x180007620  jnb     short loc_180007641
0x180007622  lea     rax, [rcx+1]
0x180007626  mov     [rbx+10h], rax
0x18000762a  mov     rax, rbx
0x18000762d  cmp     rdx, 0Fh
0x180007631  jbe     short loc_180007636
0x180007633  mov     rax, [rbx]
0x180007636  mov     word ptr [rax+rcx], 6Eh ; 'n'
0x18000763c  jmp     loc_1800073FD
0x180007641  mov     r9b, 6Eh ; 'n'
0x180007644  jmp     loc_1800073EE
0x180007649  mov     rcx, [rbx+10h]; jumptable 0000000180007385 case 9
0x18000764d  mov     rdx, [rbx+18h]
0x180007651  cmp     rcx, rdx
0x180007654  jnb     short loc_180007672
0x180007656  lea     rax, [rcx+1]
0x18000765a  mov     [rbx+10h], rax
0x18000765e  mov     rax, rbx
0x180007661  cmp     rdx, 0Fh
0x180007665  jbe     short loc_18000766A
0x180007667  mov     rax, [rbx]
0x18000766a  mov     word ptr [rax+rcx], 5Ch ; '\'
0x180007670  jmp     short loc_180007684
0x180007672  xor     r8d, r8d
0x180007675  mov     r9b, 5Ch ; '\'
0x180007678  mov     rcx, rbx; Src
0x18000767b  lea     edx, [r8+1]
0x18000767f  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXD@Z@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXD@Z@D@Z; std::string::_Reallocate_grow_by<`std::string::push_back(char)'::`2'::_lambda_1_,char>(unsigned __int64,`std::string::push_back(char)'::`2'::_lambda_1_,char)
0x180007684  mov     rcx, [rbx+10h]
0x180007688  mov     rdx, [rbx+18h]
0x18000768c  cmp     rcx, rdx
0x18000768f  jnb     short loc_1800076B0
0x180007691  lea     rax, [rcx+1]
0x180007695  mov     [rbx+10h], rax
0x180007699  mov     rax, rbx
0x18000769c  cmp     rdx, 0Fh
0x1800076a0  jbe     short loc_1800076A5
0x1800076a2  mov     rax, [rbx]
0x1800076a5  mov     word ptr [rax+rcx], 74h ; 't'
0x1800076ab  jmp     loc_1800073FD
0x1800076b0  mov     r9b, 74h ; 't'
0x1800076b3  jmp     loc_1800073EE
0x1800076b8  mov     rcx, [rbx+10h]; jumptable 0000000180007385 default case, cases 11,14-33,35-91
0x1800076bc  mov     rdx, [rbx+18h]
0x1800076c0  cmp     r9b, 1Fh
0x1800076c4  ja      loc_180007811
0x1800076ca  cmp     rcx, rdx
0x1800076cd  jnb     short loc_1800076EB
0x1800076cf  lea     rax, [rcx+1]
0x1800076d3  mov     [rbx+10h], rax
0x1800076d7  mov     rax, rbx
0x1800076da  cmp     rdx, 0Fh
0x1800076de  jbe     short loc_1800076E3
0x1800076e0  mov     rax, [rbx]
0x1800076e3  mov     word ptr [rax+rcx], 5Ch ; '\'
0x1800076e9  jmp     short loc_1800076FD
0x1800076eb  xor     r8d, r8d
0x1800076ee  mov     r9b, 5Ch ; '\'
0x1800076f1  mov     rcx, rbx; Src
0x1800076f4  lea     edx, [r8+1]
0x1800076f8  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXD@Z@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXD@Z@D@Z; std::string::_Reallocate_grow_by<`std::string::push_back(char)'::`2'::_lambda_1_,char>(unsigned __int64,`std::string::push_back(char)'::`2'::_lambda_1_,char)
0x1800076fd  mov     rcx, [rbx+10h]
0x180007701  mov     rdx, [rbx+18h]
0x180007705  cmp     rcx, rdx
0x180007708  jnb     short loc_180007726
0x18000770a  lea     rax, [rcx+1]
0x18000770e  mov     [rbx+10h], rax
0x180007712  mov     rax, rbx
0x180007715  cmp     rdx, 0Fh
0x180007719  jbe     short loc_18000771E
0x18000771b  mov     rax, [rbx]
0x18000771e  mov     word ptr [rax+rcx], 75h ; 'u'
0x180007724  jmp     short loc_180007738
0x180007726  xor     r8d, r8d
0x180007729  mov     r9b, 75h ; 'u'
0x18000772c  mov     rcx, rbx; Src
0x18000772f  lea     edx, [r8+1]
0x180007733  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXD@Z@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXD@Z@D@Z; std::string::_Reallocate_grow_by<`std::string::push_back(char)'::`2'::_lambda_1_,char>(unsigned __int64,`std::string::push_back(char)'::`2'::_lambda_1_,char)
0x180007738  mov     rcx, [rbx+10h]
0x18000773c  mov     rdx, [rbx+18h]
0x180007740  cmp     rcx, rdx
0x180007743  jnb     short loc_180007761
0x180007745  lea     rax, [rcx+1]
0x180007749  mov     [rbx+10h], rax
  ... truncated ...
```
