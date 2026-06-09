# web::json::details::_Object::format_impl<ushort>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1800046e0`
- end: `0x1800048b1`
- name: `??$format_impl@G@_Object@details@json@web@@AEBAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `465`
- prototype: `void **__fastcall(__int64, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180006370`

## callees

- `0x180003f60`
- `0x1800046e0`
- `0x180007ec0`
- `0x180007ee0`

## pseudocode

```c
void **__fastcall web::json::details::_Object::format_impl<unsigned short>(__int64 a1, unsigned __int64 *a2)
{
  unsigned __int64 *v2; // rsi
  unsigned __int64 v3; // rdx
  unsigned __int64 *v5; // rcx
  unsigned __int64 v6; // r8
  __int64 v7; // rdi
  __int64 v8; // rbx
  __int64 i; // rdi
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // r8
  char *v12; // rdx
  unsigned __int64 v13; // rcx
  unsigned __int64 v14; // r8
  char *v15; // rdx
  unsigned __int64 v16; // rcx
  unsigned __int64 v17; // r8
  char *v18; // rdx
  unsigned __int64 v19; // rcx
  unsigned __int64 v20; // rdx
  void **result; // rax

  v2 = a2;
  v3 = a2[2];
  v5 = v2;
  v6 = v2[3];
  if ( v3 >= v6 )
  {
    ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAXG_Z_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXG_Z_G_Z(
      (void **)v2,
      1u,
      0,
      123);
  }
  else
  {
    v2[2] = v3 + 1;
    if ( v6 > 7 )
      v5 = (unsigned __int64 *)*v2;
    *(_DWORD *)((char *)v5 + 2 * v3) = 123;
  }
  v7 = *(_QWORD *)(a1 + 16);
  v8 = *(_QWORD *)(a1 + 8);
  if ( v8 != v7 )
  {
    for ( i = v7 - 40; v8 != i; v8 += 40 )
    {
      web::json::details::format_string(v8, v2);
      v10 = v2[2];
      v11 = v2[3];
      if ( v10 >= v11 )
      {
        ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAXG_Z_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXG_Z_G_Z(
          (void **)v2,
          1u,
          0,
          58);
      }
      else
      {
        v12 = (char *)v2;
        v2[2] = v10 + 1;
        if ( v11 > 7 )
          v12 = (char *)*v2;
        *(_DWORD *)&v12[2 * v10] = 58;
      }
      web::json::value::format(v8 + 32, v2);
      v13 = v2[2];
      v14 = v2[3];
      if ( v13 >= v14 )
      {
        ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAXG_Z_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXG_Z_G_Z(
          (void **)v2,
          1u,
          0,
          44);
      }
      else
      {
        v15 = (char *)v2;
        v2[2] = v13 + 1;
        if ( v14 > 7 )
          v15 = (char *)*v2;
        *(_DWORD *)&v15[2 * v13] = 44;
      }
    }
    web::json::details::format_string(i, v2);
    v16 = v2[2];
    v17 = v2[3];
    if ( v16 >= v17 )
    {
      ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAXG_Z_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXG_Z_G_Z(
        (void **)v2,
        1u,
        0,
        58);
    }
    else
    {
      v18 = (char *)v2;
      v2[2] = v16 + 1;
      if ( v17 > 7 )
        v18 = (char *)*v2;
      *(_DWORD *)&v18[2 * v16] = 58;
    }
    web::json::value::format(i + 32, v2);
  }
  v19 = v2[2];
  v20 = v2[3];
  if ( v19 >= v20 )
    return ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAXG_Z_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXG_Z_G_Z(
             (void **)v2,
             1u,
             0,
             125);
  result = (void **)(v19 + 1);
  v2[2] = v19 + 1;
  if ( v20 > 7 )
    v2 = (unsigned __int64 *)*v2;
  *(_DWORD *)((char *)v2 + 2 * v19) = 125;
  return result;
}

```

## disassembly

```asm
0x1800046e0  push    rsi
0x1800046e2  sub     rsp, 20h
0x1800046e6  mov     rsi, rdx
0x1800046e9  mov     [rsp+28h+arg_0], rbx
0x1800046ee  mov     rdx, [rdx+10h]
0x1800046f2  mov     rbx, rcx
0x1800046f5  mov     [rsp+28h+arg_10], rdi
0x1800046fa  mov     rcx, rsi; Src
0x1800046fd  mov     r8, [rsi+18h]
0x180004701  cmp     rdx, r8
0x180004704  jnb     short loc_180004720
0x180004706  lea     rax, [rdx+1]
0x18000470a  mov     [rsi+10h], rax
0x18000470e  cmp     r8, 7
0x180004712  jbe     short loc_180004717
0x180004714  mov     rcx, [rsi]
0x180004717  mov     dword ptr [rcx+rdx*2], 7Bh ; '{'
0x18000471e  jmp     short loc_180004733
0x180004720  mov     r9d, 7Bh ; '{'
0x180004726  xor     r8d, r8d
0x180004729  mov     edx, 1
0x18000472e  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXG@Z@G@Z; std::wstring::_Reallocate_grow_by<`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort>(unsigned __int64,`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort)
0x180004733  mov     rdi, [rbx+10h]
0x180004737  mov     rbx, [rbx+8]
0x18000473b  cmp     rbx, rdi
0x18000473e  jz      loc_180004861
0x180004744  add     rdi, 0FFFFFFFFFFFFFFD8h
0x180004748  mov     [rsp+28h+arg_8], rbp
0x18000474d  mov     ebp, 3Ah ; ':'
0x180004752  cmp     rbx, rdi
0x180004755  jz      loc_18000480C
0x18000475b  mov     [rsp+28h+arg_18], r14
0x180004760  mov     r14d, 2Ch ; ','
0x180004766  nop     word ptr [rax+rax+00000000h]
0x180004770  mov     rdx, rsi
0x180004773  mov     rcx, rbx
0x180004776  call    ?format_string@details@json@web@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV45@@Z; web::json::details::format_string(std::wstring const &,std::wstring &)
0x18000477b  mov     rcx, [rsi+10h]
0x18000477f  mov     r8, [rsi+18h]
0x180004783  cmp     rcx, r8
0x180004786  jnb     short loc_1800047A1
0x180004788  lea     rax, [rcx+1]
0x18000478c  mov     rdx, rsi
0x18000478f  mov     [rsi+10h], rax
0x180004793  cmp     r8, 7
0x180004797  jbe     short loc_18000479C
0x180004799  mov     rdx, [rsi]
0x18000479c  mov     [rdx+rcx*2], ebp
0x18000479f  jmp     short loc_1800047B4
0x1800047a1  mov     r9d, ebp
0x1800047a4  xor     r8d, r8d
0x1800047a7  mov     edx, 1
0x1800047ac  mov     rcx, rsi; Src
0x1800047af  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXG@Z@G@Z; std::wstring::_Reallocate_grow_by<`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort>(unsigned __int64,`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort)
0x1800047b4  lea     rcx, [rbx+20h]
0x1800047b8  mov     rdx, rsi
0x1800047bb  call    ?format@value@json@web@@AEBAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::format(std::wstring &)
0x1800047c0  mov     rcx, [rsi+10h]
0x1800047c4  mov     r8, [rsi+18h]
0x1800047c8  cmp     rcx, r8
0x1800047cb  jnb     short loc_1800047E7
0x1800047cd  lea     rax, [rcx+1]
0x1800047d1  mov     rdx, rsi
0x1800047d4  mov     [rsi+10h], rax
0x1800047d8  cmp     r8, 7
0x1800047dc  jbe     short loc_1800047E1
0x1800047de  mov     rdx, [rsi]
0x1800047e1  mov     [rdx+rcx*2], r14d
0x1800047e5  jmp     short loc_1800047FA
0x1800047e7  mov     r9d, r14d
0x1800047ea  xor     r8d, r8d
0x1800047ed  mov     edx, 1
0x1800047f2  mov     rcx, rsi; Src
0x1800047f5  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXG@Z@G@Z; std::wstring::_Reallocate_grow_by<`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort>(unsigned __int64,`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort)
0x1800047fa  add     rbx, 28h ; '('
0x1800047fe  cmp     rbx, rdi
0x180004801  jnz     loc_180004770
0x180004807  mov     r14, [rsp+28h+arg_18]
0x18000480c  mov     rdx, rsi
0x18000480f  mov     rcx, rdi
0x180004812  call    ?format_string@details@json@web@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV45@@Z; web::json::details::format_string(std::wstring const &,std::wstring &)
0x180004817  mov     rcx, [rsi+10h]
0x18000481b  mov     r8, [rsi+18h]
0x18000481f  cmp     rcx, r8
0x180004822  jnb     short loc_18000483D
0x180004824  lea     rax, [rcx+1]
0x180004828  mov     rdx, rsi
0x18000482b  mov     [rsi+10h], rax
0x18000482f  cmp     r8, 7
0x180004833  jbe     short loc_180004838
0x180004835  mov     rdx, [rsi]
0x180004838  mov     [rdx+rcx*2], ebp
0x18000483b  jmp     short loc_180004850
0x18000483d  mov     r9d, ebp
0x180004840  xor     r8d, r8d
0x180004843  mov     edx, 1
0x180004848  mov     rcx, rsi; Src
0x18000484b  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXG@Z@G@Z; std::wstring::_Reallocate_grow_by<`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort>(unsigned __int64,`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort)
0x180004850  lea     rcx, [rdi+20h]
0x180004854  mov     rdx, rsi
0x180004857  call    ?format@value@json@web@@AEBAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::format(std::wstring &)
0x18000485c  mov     rbp, [rsp+28h+arg_8]
0x180004861  mov     rcx, [rsi+10h]
0x180004865  mov     rdx, [rsi+18h]
0x180004869  mov     rdi, [rsp+28h+arg_10]
0x18000486e  mov     rbx, [rsp+28h+arg_0]
0x180004873  cmp     rcx, rdx
0x180004876  jnb     short loc_180004896
0x180004878  lea     rax, [rcx+1]
0x18000487c  mov     [rsi+10h], rax
0x180004880  cmp     rdx, 7
0x180004884  jbe     short loc_180004889
0x180004886  mov     rsi, [rsi]
0x180004889  mov     dword ptr [rsi+rcx*2], 7Dh ; '}'
0x180004890  add     rsp, 20h
0x180004894  pop     rsi
0x180004895  retn
0x180004896  mov     r9d, 7Dh ; '}'
0x18000489c  xor     r8d, r8d
0x18000489f  mov     edx, 1
0x1800048a4  mov     rcx, rsi; Src
0x1800048a7  add     rsp, 20h
0x1800048ab  pop     rsi
0x1800048ac  jmp     ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXG@Z@G@Z; std::wstring::_Reallocate_grow_by<`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort>(unsigned __int64,`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort)
```
