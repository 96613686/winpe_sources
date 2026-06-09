# web::json::details::append_escape_string<ushort>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1800072e0`
- end: `0x18000790d`
- name: `??$append_escape_string@G@details@json@web@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV34@@Z`
- size: `1581`
- prototype: `void **__fastcall(void **Src, _QWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180007db0`
- `0x180007ee0`

## callees

- `0x180003f60`
- `0x1800072e0`
- `0x180007920`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void **__fastcall web::json::details::append_escape_string<unsigned short>(void **Src, _QWORD *a2)
{
  _QWORD *v3; // rcx
  _QWORD *v4; // r8
  _WORD *v5; // rbp
  void **result; // rax
  _WORD *v7; // r14
  unsigned __int64 *v8; // rsi
  unsigned __int64 *v9; // rdi
  unsigned int v10; // r9d
  unsigned __int64 v11; // rcx
  unsigned __int64 v12; // rdx
  void **v13; // r8
  unsigned __int64 v14; // rcx
  unsigned __int64 v15; // rdx
  unsigned __int64 v16; // rcx
  unsigned __int64 v17; // rdx
  void **v18; // r8
  unsigned __int64 v19; // rcx
  unsigned __int64 v20; // rdx
  unsigned __int64 v21; // rcx
  unsigned __int64 v22; // rdx
  void **v23; // r8
  unsigned __int64 v24; // rcx
  unsigned __int64 v25; // rdx
  unsigned __int64 v26; // rcx
  unsigned __int64 v27; // rdx
  void **v28; // r8
  unsigned __int64 v29; // rcx
  unsigned __int64 v30; // rdx
  unsigned __int64 v31; // rcx
  unsigned __int64 v32; // rdx
  void **v33; // r8
  unsigned __int64 v34; // rcx
  unsigned __int64 v35; // rdx
  unsigned __int64 v36; // rcx
  unsigned __int64 v37; // rdx
  void **v38; // r8
  unsigned __int64 v39; // rcx
  unsigned __int64 v40; // rdx
  unsigned __int64 v41; // rcx
  unsigned __int64 v42; // rdx
  void **v43; // r8
  unsigned __int64 v44; // rcx
  unsigned __int64 v45; // rdx
  unsigned __int64 v46; // rcx
  unsigned __int64 v47; // rdx
  void **v48; // r8
  unsigned __int64 v49; // rcx
  unsigned __int64 v50; // rdx
  void **v51; // r8
  unsigned __int64 v52; // rcx
  unsigned __int64 v53; // rdx
  void **v54; // r8
  unsigned __int64 v55; // rcx
  unsigned __int64 v56; // rdx
  void **v57; // r8
  void **v58; // r8

  if ( a2[3] <= 7u )
  {
    v4 = a2;
    v3 = a2;
    v5 = a2;
  }
  else
  {
    v3 = (_QWORD *)*a2;
    v4 = (_QWORD *)*a2;
    v5 = (_WORD *)*a2;
  }
  result = (void **)a2[2];
  v7 = (_WORD *)v4 + (_QWORD)result;
  if ( v3 != (_QWORD *)v7 )
  {
    v8 = (unsigned __int64 *)(Src + 3);
    v9 = (unsigned __int64 *)(Src + 2);
    do
    {
      v10 = (unsigned __int16)*v5;
      switch ( *v5 )
      {
        case 8:
          v21 = *v9;
          v22 = *v8;
          if ( *v9 >= *v8 )
          {
            ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAXG_Z_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXG_Z_G_Z(
              Src,
              1u,
              0,
              92);
          }
          else
          {
            v23 = Src;
            *v9 = v21 + 1;
            if ( v22 > 7 )
              v23 = (void **)*Src;
            *(_DWORD *)((char *)v23 + 2 * v21) = 92;
          }
          v24 = *v9;
          v25 = *v8;
          if ( *v9 >= *v8 )
          {
            LOWORD(v10) = 98;
            goto LABEL_27;
          }
          result = (void **)(v24 + 1);
          *v9 = v24 + 1;
          if ( v25 <= 7 )
            *(_DWORD *)((char *)Src + 2 * v24) = 98;
          else
            *(_DWORD *)((char *)*Src + 2 * v24) = 98;
          break;
        case 9:
          v41 = *v9;
          v42 = *v8;
          if ( *v9 >= *v8 )
          {
            ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAXG_Z_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXG_Z_G_Z(
              Src,
              1u,
              0,
              92);
          }
          else
          {
            v43 = Src;
            *v9 = v41 + 1;
            if ( v42 > 7 )
              v43 = (void **)*Src;
            *(_DWORD *)((char *)v43 + 2 * v41) = 92;
          }
          v44 = *v9;
          v45 = *v8;
          if ( *v9 >= *v8 )
          {
            LOWORD(v10) = 116;
            goto LABEL_27;
          }
          result = (void **)(v44 + 1);
          Src[2] = (void *)(v44 + 1);
          if ( v45 <= 7 )
            *(_DWORD *)((char *)Src + 2 * v44) = 116;
          else
            *(_DWORD *)((char *)*Src + 2 * v44) = 116;
          break;
        case 0xA:
          v36 = *v9;
          v37 = *v8;
          if ( *v9 >= *v8 )
          {
            ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAXG_Z_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXG_Z_G_Z(
              Src,
              1u,
              0,
              92);
          }
          else
          {
            v38 = Src;
            *v9 = v36 + 1;
            if ( v37 > 7 )
              v38 = (void **)*Src;
            *(_DWORD *)((char *)v38 + 2 * v36) = 92;
          }
          v39 = *v9;
          v40 = *v8;
          if ( *v9 >= *v8 )
          {
            LOWORD(v10) = 110;
            goto LABEL_27;
          }
          result = (void **)(v39 + 1);
          Src[2] = (void *)(v39 + 1);
          if ( v40 <= 7 )
            *(_DWORD *)((char *)Src + 2 * v39) = 110;
          else
            *(_DWORD *)((char *)*Src + 2 * v39) = 110;
          break;
        case 0xC:
          v26 = *v9;
          v27 = *v8;
          if ( *v9 >= *v8 )
          {
            ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAXG_Z_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXG_Z_G_Z(
              Src,
              1u,
              0,
              92);
          }
          else
          {
            v28 = Src;
            *v9 = v26 + 1;
            if ( v27 > 7 )
              v28 = (void **)*Src;
            *(_DWORD *)((char *)v28 + 2 * v26) = 92;
          }
          v29 = *v9;
          v30 = *v8;
          if ( *v9 >= *v8 )
          {
            LOWORD(v10) = 102;
            goto LABEL_27;
          }
          result = (void **)(v29 + 1);
          Src[2] = (void *)(v29 + 1);
          if ( v30 <= 7 )
            *(_DWORD *)((char *)Src + 2 * v29) = 102;
          else
            *(_DWORD *)((char *)*Src + 2 * v29) = 102;
          break;
        case 0xD:
          v31 = *v9;
          v32 = *v8;
          if ( *v9 >= *v8 )
          {
            ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAXG_Z_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXG_Z_G_Z(
              Src,
              1u,
              0,
              92);
          }
          else
          {
            v33 = Src;
            *v9 = v31 + 1;
            if ( v32 > 7 )
              v33 = (void **)*Src;
            *(_DWORD *)((char *)v33 + 2 * v31) = 92;
          }
          v34 = *v9;
          v35 = *v8;
          if ( *v9 >= *v8 )
          {
            LOWORD(v10) = 114;
            goto LABEL_27;
          }
          result = (void **)(v34 + 1);
          Src[2] = (void *)(v34 + 1);
          if ( v35 <= 7 )
            *(_DWORD *)((char *)Src + 2 * v34) = 114;
          else
            *(_DWORD *)((char *)*Src + 2 * v34) = 114;
          break;
        case 0x22:
          v11 = *v9;
          v12 = *v8;
          if ( *v9 >= *v8 )
          {
            ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAXG_Z_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXG_Z_G_Z(
              Src,
              1u,
              0,
              92);
          }
          else
          {
            v13 = Src;
            *v9 = v11 + 1;
            if ( v12 > 7 )
              v13 = (void **)*Src;
            *(_DWORD *)((char *)v13 + 2 * v11) = 92;
          }
          v14 = *v9;
          v15 = *v8;
          if ( *v9 >= *v8 )
          {
            result = ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAXG_Z_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXG_Z_G_Z(
                       Src,
                       1u,
                       0,
                       34);
            v9 = (unsigned __int64 *)(Src + 2);
            v8 = (unsigned __int64 *)(Src + 3);
          }
          else
          {
            result = (void **)(v14 + 1);
            *v9 = v14 + 1;
            if ( v15 <= 7 )
            {
              *(_DWORD *)((char *)Src + 2 * v14) = 34;
              v9 = (unsigned __int64 *)(Src + 2);
              v8 = (unsigned __int64 *)(Src + 3);
            }
            else
            {
              v9 = (unsigned __int64 *)(Src + 2);
              v8 = (unsigned __int64 *)(Src + 3);
              *(_DWORD *)((char *)*Src + 2 * v14) = 34;
            }
          }
          break;
        case 0x5C:
          v16 = *v9;
          v17 = *v8;
          if ( *v9 >= *v8 )
          {
            ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAXG_Z_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXG_Z_G_Z(
              Src,
              1u,
              0,
              92);
          }
          else
          {
            v18 = Src;
            *v9 = v16 + 1;
            if ( v17 > 7 )
              v18 = (void **)*Src;
            *(_DWORD *)((char *)v18 + 2 * v16) = 92;
          }
          v19 = *v9;
          v20 = *v8;
          if ( *v9 >= *v8 )
          {
            LOWORD(v10) = 92;
            goto LABEL_27;
          }
          result = (void **)(v19 + 1);
          *v9 = v19 + 1;
          if ( v20 <= 7 )
            *(_DWORD *)((char *)Src + 2 * v19) = 92;
          else
            *(_DWORD *)((char *)*Src + 2 * v19) = 92;
          break;
        default:
          v46 = *v9;
          v47 = *v8;
          if ( v10 > 0x1F )
          {
            if ( v46 >= v47 )
            {
LABEL_27:
              result = ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAXG_Z_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXG_Z_G_Z(
                         Src,
                         1u,
                         0,
                         v10);
            }
            else
            {
              v58 = Src;
              *v9 = v46 + 1;
              if ( v47 > 7 )
                v58 = (void **)*Src;
              result = 0;
              *((_WORD *)v58 + v46) = v10;
              *((_WORD *)v58 + v46 + 1) = 0;
            }
          }
          else
          {
            if ( v46 >= v47 )
            {
              ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAXG_Z_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXG_Z_G_Z(
                Src,
                1u,
                0,
                92);
            }
            else
            {
              v48 = Src;
              *v9 = v46 + 1;
              if ( v47 > 7 )
                v48 = (void **)*Src;
              *(_DWORD *)((char *)v48 + 2 * v46) = 92;
            }
            v49 = (unsigned __int64)Src[2];
            v50 = (unsigned __int64)Src[3];
            if ( v49 >= v50 )
            {
              ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAXG_Z_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXG_Z_G_Z(
                Src,
                1u,
                0,
                117);
            }
            else
            {
              v51 = Src;
              Src[2] = (void *)(v49 + 1);
              if ( v50 > 7 )
                v51 = (void **)*Src;
              *(_DWORD *)((char *)v51 + 2 * v49) = 117;
            }
            v52 = (unsigned __int64)Src[2];
            v53 = (unsigned __int64)Src[3];
            if ( v52 >= v53 )
            {
              ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAXG_Z_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXG_Z_G_Z(
                Src,
                1u,
                0,
                48);
            }
            else
            {
              v54 = Src;
              Src[2] = (void *)(v52 + 1);
              if ( v53 > 7 )
                v54 = (void **)*Src;
              *(_DWORD *)((char *)v54 + 2 * v52) = 48;
            }
            v55 = (unsigned __int64)Src[2];
            v56 = (unsigned __int64)Src[3];
            if ( v55 >= v56 )
            {
              ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAXG_Z_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXG_Z_G_Z(
                Src,
                1u,
                0,
                48);
            }
            else
            {
              v57 = Src;
              Src[2] = (void *)(v55 + 1);
              if ( v56 > 7 )
                v57 = (void **)*Src;
              *(_DWORD *)((char *)v57 + 2 * v55) = 48;
            }
            std::wstring::operator+=(Src);
            result = (void **)std::wstring::operator+=(Src);
          }
          break;
      }
      ++v5;
    }
    while ( v5 != v7 );
  }
  return result;
}

```

## disassembly

```asm
0x1800072e0  push    rbx
0x1800072e2  push    rbp
0x1800072e3  push    r14
0x1800072e5  sub     rsp, 30h
0x1800072e9  cmp     qword ptr [rdx+18h], 7
0x1800072ee  mov     rbx, rcx
0x1800072f1  jbe     short loc_1800072FE
0x1800072f3  mov     rcx, [rdx]
0x1800072f6  mov     r8, rcx
0x1800072f9  mov     rbp, rcx
0x1800072fc  jmp     short loc_180007307
0x1800072fe  mov     r8, rdx
0x180007301  mov     rcx, rdx
0x180007304  mov     rbp, rdx
0x180007307  mov     rax, [rdx+10h]
0x18000730b  lea     r14, [r8+rax*2]
0x18000730f  cmp     rcx, r14
0x180007312  jz      loc_1800074D0
0x180007318  mov     [rsp+48h+arg_0], rsi
0x18000731d  mov     r11d, 22h ; '"'
0x180007323  mov     [rsp+48h+arg_8], rdi
0x180007328  lea     rsi, [rbx+18h]
0x18000732c  mov     [rsp+48h+arg_10], r12
0x180007331  lea     rdi, [rbx+10h]
0x180007335  mov     [rsp+48h+var_20], r13
0x18000733a  mov     r10d, 75h ; 'u'
0x180007340  mov     [rsp+48h+var_28], r15
0x180007345  lea     r13, cs:180000000h
0x18000734c  mov     r15d, 5Ch ; '\'
0x180007352  mov     r12d, 30h ; '0'
0x180007358  nop     dword ptr [rax+rax+00000000h]
0x180007360  movzx   r9d, word ptr [rbp+0]
0x180007365  lea     eax, [r9-8]; switch 85 cases
0x180007369  cmp     eax, 54h
0x18000736c  ja      def_180007388; jumptable 0000000180007388 default case, cases 11,14-33,35-91
0x180007372  cdqe
0x180007374  movzx   eax, ds:(byte_1800078B8 - 180000000h)[rax+r13]
0x18000737d  mov     ecx, ds:(jpt_180007388 - 180000000h)[r13+rax*4]
0x180007385  add     rcx, r13
0x180007388  jmp     rcx; switch jump
0x18000738a  mov     rcx, [rdi]; jumptable 0000000180007388 case 34
0x18000738d  mov     rdx, [rsi]
0x180007390  cmp     rcx, rdx
0x180007393  jnb     short loc_1800073AE
0x180007395  lea     rax, [rcx+1]
0x180007399  mov     r8, rbx
0x18000739c  mov     [rdi], rax
0x18000739f  cmp     rdx, 7
0x1800073a3  jbe     short loc_1800073A8
0x1800073a5  mov     r8, [rbx]
0x1800073a8  mov     [r8+rcx*2], r15d
0x1800073ac  jmp     short loc_1800073C7
0x1800073ae  mov     r9d, r15d
0x1800073b1  xor     r8d, r8d
0x1800073b4  mov     edx, 1
0x1800073b9  mov     rcx, rbx; Src
0x1800073bc  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXG@Z@G@Z; std::wstring::_Reallocate_grow_by<`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort>(unsigned __int64,`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort)
0x1800073c1  mov     r11d, 22h ; '"'
0x1800073c7  mov     rcx, [rdi]
0x1800073ca  mov     rdx, [rsi]
0x1800073cd  cmp     rcx, rdx
0x1800073d0  jnb     short loc_18000740D
0x1800073d2  lea     rax, [rcx+1]
0x1800073d6  mov     [rdi], rax
0x1800073d9  cmp     rdx, 7
0x1800073dd  jbe     short loc_1800073F6
0x1800073df  mov     rdx, [rbx]
0x1800073e2  lea     rdi, [rbx+10h]
0x1800073e6  lea     rsi, [rbx+18h]
0x1800073ea  mov     dword ptr [rdx+rcx*2], 22h ; '"'
0x1800073f1  jmp     loc_18000749E
0x1800073f6  mov     rdx, rbx
0x1800073f9  mov     dword ptr [rbx+rcx*2], 22h ; '"'
0x180007400  lea     rdi, [rbx+10h]
0x180007404  lea     rsi, [rbx+18h]
0x180007408  jmp     loc_18000749E
0x18000740d  mov     r9d, r11d
0x180007410  xor     r8d, r8d
0x180007413  mov     edx, 1
0x180007418  mov     rcx, rbx; Src
0x18000741b  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXG@Z@G@Z; std::wstring::_Reallocate_grow_by<`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort>(unsigned __int64,`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort)
0x180007420  lea     rdi, [rbx+10h]
0x180007424  lea     rsi, [rbx+18h]
0x180007428  jmp     short loc_18000749E
0x18000742a  mov     rcx, [rdi]; jumptable 0000000180007388 case 92
0x18000742d  mov     rdx, [rsi]
0x180007430  cmp     rcx, rdx
0x180007433  jnb     short loc_18000744E
0x180007435  lea     rax, [rcx+1]
0x180007439  mov     r8, rbx
0x18000743c  mov     [rdi], rax
0x18000743f  cmp     rdx, 7
0x180007443  jbe     short loc_180007448
0x180007445  mov     r8, [rbx]
0x180007448  mov     [r8+rcx*2], r15d
0x18000744c  jmp     short loc_180007461
0x18000744e  mov     r9d, r15d
0x180007451  xor     r8d, r8d
0x180007454  mov     edx, 1
0x180007459  mov     rcx, rbx; Src
0x18000745c  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXG@Z@G@Z; std::wstring::_Reallocate_grow_by<`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort>(unsigned __int64,`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort)
0x180007461  mov     rcx, [rdi]
0x180007464  mov     rdx, [rsi]
0x180007467  cmp     rcx, rdx
0x18000746a  jnb     short loc_18000748B
0x18000746c  lea     rax, [rcx+1]
0x180007470  mov     [rdi], rax
0x180007473  cmp     rdx, 7
0x180007477  jbe     short loc_180007482
0x180007479  mov     rdx, [rbx]
0x18000747c  mov     [rdx+rcx*2], r15d
0x180007480  jmp     short loc_18000749E
0x180007482  mov     rdx, rbx
0x180007485  mov     [rbx+rcx*2], r15d
0x180007489  jmp     short loc_18000749E
0x18000748b  mov     r9d, r15d
0x18000748e  xor     r8d, r8d
0x180007491  mov     edx, 1
0x180007496  mov     rcx, rbx; Src
0x180007499  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXG@Z@G@Z; std::wstring::_Reallocate_grow_by<`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort>(unsigned __int64,`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort)
0x18000749e  mov     r10d, 75h ; 'u'
0x1800074a4  add     rbp, 2
0x1800074a8  mov     r11d, 22h ; '"'
0x1800074ae  cmp     rbp, r14
0x1800074b1  jnz     loc_180007360
0x1800074b7  mov     r15, [rsp+48h+var_28]
0x1800074bc  mov     r13, [rsp+48h+var_20]
0x1800074c1  mov     r12, [rsp+48h+arg_10]
0x1800074c6  mov     rdi, [rsp+48h+arg_8]
0x1800074cb  mov     rsi, [rsp+48h+arg_0]
0x1800074d0  add     rsp, 30h
0x1800074d4  pop     r14
0x1800074d6  pop     rbp
0x1800074d7  pop     rbx
0x1800074d8  retn
0x1800074d9  mov     rcx, [rdi]; jumptable 0000000180007388 case 8
0x1800074dc  mov     rdx, [rsi]
0x1800074df  cmp     rcx, rdx
0x1800074e2  jnb     short loc_1800074FD
0x1800074e4  lea     rax, [rcx+1]
0x1800074e8  mov     r8, rbx
0x1800074eb  mov     [rdi], rax
0x1800074ee  cmp     rdx, 7
0x1800074f2  jbe     short loc_1800074F7
0x1800074f4  mov     r8, [rbx]
0x1800074f7  mov     [r8+rcx*2], r15d
0x1800074fb  jmp     short loc_180007510
0x1800074fd  mov     r9d, r15d
0x180007500  xor     r8d, r8d
0x180007503  mov     edx, 1
0x180007508  mov     rcx, rbx; Src
0x18000750b  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXG@Z@G@Z; std::wstring::_Reallocate_grow_by<`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort>(unsigned __int64,`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort)
0x180007510  mov     rcx, [rdi]
0x180007513  mov     rdx, [rsi]
0x180007516  cmp     rcx, rdx
0x180007519  jnb     short loc_180007546
0x18000751b  lea     rax, [rcx+1]
0x18000751f  mov     [rdi], rax
0x180007522  cmp     rdx, 7
0x180007526  jbe     short loc_180007537
0x180007528  mov     rdx, [rbx]
0x18000752b  mov     dword ptr [rdx+rcx*2], 62h ; 'b'
0x180007532  jmp     loc_18000749E
0x180007537  mov     rdx, rbx
0x18000753a  mov     dword ptr [rbx+rcx*2], 62h ; 'b'
0x180007541  jmp     loc_18000749E
0x180007546  mov     r9d, 62h ; 'b'
0x18000754c  jmp     loc_18000748E
0x180007551  mov     rcx, [rdi]; jumptable 0000000180007388 case 12
0x180007554  mov     rdx, [rsi]
0x180007557  cmp     rcx, rdx
0x18000755a  jnb     short loc_180007575
0x18000755c  lea     rax, [rcx+1]
0x180007560  mov     r8, rbx
0x180007563  mov     [rdi], rax
0x180007566  cmp     rdx, 7
0x18000756a  jbe     short loc_18000756F
0x18000756c  mov     r8, [rbx]
0x18000756f  mov     [r8+rcx*2], r15d
0x180007573  jmp     short loc_180007588
0x180007575  mov     r9d, r15d
0x180007578  xor     r8d, r8d
0x18000757b  mov     edx, 1
0x180007580  mov     rcx, rbx; Src
0x180007583  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXG@Z@G@Z; std::wstring::_Reallocate_grow_by<`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort>(unsigned __int64,`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort)
0x180007588  mov     rcx, [rdi]
0x18000758b  mov     rdx, [rsi]
0x18000758e  cmp     rcx, rdx
0x180007591  jnb     short loc_1800075BF
0x180007593  lea     rax, [rcx+1]
0x180007597  mov     [rbx+10h], rax
0x18000759b  cmp     rdx, 7
0x18000759f  jbe     short loc_1800075B0
0x1800075a1  mov     rdx, [rbx]
0x1800075a4  mov     dword ptr [rdx+rcx*2], 66h ; 'f'
0x1800075ab  jmp     loc_18000749E
0x1800075b0  mov     rdx, rbx
0x1800075b3  mov     dword ptr [rbx+rcx*2], 66h ; 'f'
0x1800075ba  jmp     loc_18000749E
0x1800075bf  mov     r9d, 66h ; 'f'
0x1800075c5  jmp     loc_18000748E
0x1800075ca  mov     rcx, [rdi]; jumptable 0000000180007388 case 13
0x1800075cd  mov     rdx, [rsi]
0x1800075d0  cmp     rcx, rdx
0x1800075d3  jnb     short loc_1800075EE
0x1800075d5  lea     rax, [rcx+1]
0x1800075d9  mov     r8, rbx
0x1800075dc  mov     [rdi], rax
0x1800075df  cmp     rdx, 7
0x1800075e3  jbe     short loc_1800075E8
0x1800075e5  mov     r8, [rbx]
0x1800075e8  mov     [r8+rcx*2], r15d
0x1800075ec  jmp     short loc_180007601
0x1800075ee  mov     r9d, r15d
0x1800075f1  xor     r8d, r8d
0x1800075f4  mov     edx, 1
0x1800075f9  mov     rcx, rbx; Src
0x1800075fc  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXG@Z@G@Z; std::wstring::_Reallocate_grow_by<`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort>(unsigned __int64,`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort)
0x180007601  mov     rcx, [rdi]
0x180007604  mov     rdx, [rsi]
0x180007607  cmp     rcx, rdx
0x18000760a  jnb     short loc_180007638
0x18000760c  lea     rax, [rcx+1]
0x180007610  mov     [rbx+10h], rax
0x180007614  cmp     rdx, 7
0x180007618  jbe     short loc_180007629
0x18000761a  mov     rdx, [rbx]
0x18000761d  mov     dword ptr [rdx+rcx*2], 72h ; 'r'
0x180007624  jmp     loc_18000749E
0x180007629  mov     rdx, rbx
0x18000762c  mov     dword ptr [rbx+rcx*2], 72h ; 'r'
0x180007633  jmp     loc_18000749E
0x180007638  mov     r9d, 72h ; 'r'
0x18000763e  jmp     loc_18000748E
0x180007643  mov     rcx, [rdi]; jumptable 0000000180007388 case 10
0x180007646  mov     rdx, [rsi]
0x180007649  cmp     rcx, rdx
0x18000764c  jnb     short loc_180007667
0x18000764e  lea     rax, [rcx+1]
0x180007652  mov     r8, rbx
0x180007655  mov     [rdi], rax
0x180007658  cmp     rdx, 7
0x18000765c  jbe     short loc_180007661
0x18000765e  mov     r8, [rbx]
0x180007661  mov     [r8+rcx*2], r15d
0x180007665  jmp     short loc_18000767A
0x180007667  mov     r9d, r15d
0x18000766a  xor     r8d, r8d
0x18000766d  mov     edx, 1
0x180007672  mov     rcx, rbx; Src
0x180007675  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXG@Z@G@Z; std::wstring::_Reallocate_grow_by<`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort>(unsigned __int64,`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort)
0x18000767a  mov     rcx, [rdi]
0x18000767d  mov     rdx, [rsi]
0x180007680  cmp     rcx, rdx
0x180007683  jnb     short loc_1800076B1
0x180007685  lea     rax, [rcx+1]
0x180007689  mov     [rbx+10h], rax
0x18000768d  cmp     rdx, 7
0x180007691  jbe     short loc_1800076A2
0x180007693  mov     rdx, [rbx]
0x180007696  mov     dword ptr [rdx+rcx*2], 6Eh ; 'n'
0x18000769d  jmp     loc_18000749E
0x1800076a2  mov     rdx, rbx
0x1800076a5  mov     dword ptr [rbx+rcx*2], 6Eh ; 'n'
0x1800076ac  jmp     loc_18000749E
0x1800076b1  mov     r9d, 6Eh ; 'n'
0x1800076b7  jmp     loc_18000748E
0x1800076bc  mov     rcx, [rdi]; jumptable 0000000180007388 case 9
0x1800076bf  mov     rdx, [rsi]
0x1800076c2  cmp     rcx, rdx
0x1800076c5  jnb     short loc_1800076E0
0x1800076c7  lea     rax, [rcx+1]
0x1800076cb  mov     r8, rbx
0x1800076ce  mov     [rdi], rax
0x1800076d1  cmp     rdx, 7
0x1800076d5  jbe     short loc_1800076DA
0x1800076d7  mov     r8, [rbx]
0x1800076da  mov     [r8+rcx*2], r15d
0x1800076de  jmp     short loc_1800076F3
0x1800076e0  mov     r9d, r15d
0x1800076e3  xor     r8d, r8d
0x1800076e6  mov     edx, 1
0x1800076eb  mov     rcx, rbx; Src
0x1800076ee  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXG@Z@G@Z; std::wstring::_Reallocate_grow_by<`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort>(unsigned __int64,`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort)
0x1800076f3  mov     rcx, [rdi]
0x1800076f6  mov     rdx, [rsi]
0x1800076f9  cmp     rcx, rdx
0x1800076fc  jnb     short loc_18000772A
0x1800076fe  lea     rax, [rcx+1]
0x180007702  mov     [rbx+10h], rax
0x180007706  cmp     rdx, 7
0x18000770a  jbe     short loc_18000771B
0x18000770c  mov     rdx, [rbx]
0x18000770f  mov     dword ptr [rdx+rcx*2], 74h ; 't'
0x180007716  jmp     loc_18000749E
0x18000771b  mov     rdx, rbx
0x18000771e  mov     dword ptr [rbx+rcx*2], 74h ; 't'
0x180007725  jmp     loc_18000749E
0x18000772a  mov     r9d, 74h ; 't'
0x180007730  jmp     loc_18000748E
  ... truncated ...
```
