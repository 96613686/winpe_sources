# LanguageFeaturesUninstaller::GetFeaturesToUninstall(PayloadTypesMask)

- ea: `0x180017a80`
- end: `0x180017e7e`
- name: `?GetFeaturesToUninstall@LanguageFeaturesUninstaller@@QEBA?AV?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@VPayloadTypesMask@@@Z`
- size: `1022`
- prototype: `struct CbsLanguageFeature *__fastcall(__int64, struct CbsLanguageFeature *, int)`
- caller_count: `2`
- callee_count: `18`
- tags: `reparse_path, registry_config, installer_update`

## callers

- `0x180013e1c`
- `0x180014788`

## callees

- `0x180003520`
- `0x180003544`
- `0x18000ba74`
- `0x18000c000`
- `0x18000cef4`
- `0x18000fb40`
- `0x18000ff28`
- `0x180010094`
- `0x18001142c`
- `0x1800118f4`
- `0x180012394`
- `0x180012984`
- `0x180017a80`
- `0x18001dea4`
- `0x1800214f4`
- `0x180021590`
- `0x180022024`
- `0x180023df0`

## import_xrefs

- `ext-ms-win-devmgmt-policy-l1-1-1!PolicyManager_GetPolicy` at `0x180017b03`
- `ext-ms-win-devmgmt-policy-l1-1-1!PolicyManager_GetPolicy` at `0x180017b03`
- `ext-ms-win-devmgmt-policy-l1-1-1!PolicyManager_FreeGetPolicyData` at `0x180017b14`
- `ext-ms-win-devmgmt-policy-l1-1-1!PolicyManager_FreeGetPolicyData` at `0x180017b29`
- `ext-ms-win-devmgmt-policy-l1-1-1!PolicyManager_FreeGetPolicyData` at `0x180017b14`
- `ext-ms-win-devmgmt-policy-l1-1-1!PolicyManager_FreeGetPolicyData` at `0x180017b29`

## string_xrefs

- `0x180017af5`: `AllowLanguageFeaturesUninstall`

## pseudocode

```c
struct CbsLanguageFeature *__fastcall LanguageFeaturesUninstaller::GetFeaturesToUninstall(
        __int64 a1,
        struct CbsLanguageFeature *a2,
        int a3)
{
  struct CbsLanguageFeature *v3; // r13
  unsigned int v5; // r15d
  int v6; // ebx
  _QWORD *v7; // rax
  __int64 *v8; // rdi
  __int64 *i; // rbx
  int v10; // esi
  int v11; // r15d
  CbsLanguageFeature *v12; // rsi
  CbsLanguageFeature *v13; // r12
  const struct CbsLanguageFeature *v14; // r12
  const struct CbsLanguageFeature *j; // rsi
  CbsLanguageFeature *v16; // rax
  CbsLanguageFeature *v17; // rdx
  __int64 v18; // rbx
  __int64 v19; // r14
  CbsLanguageFeature *v20; // rsi
  CbsLanguageFeature *k; // rdi
  const wchar_t *v22; // rcx
  const wchar_t *v23; // rdx
  size_t v24; // r8
  CbsLanguageFeature *v25; // rcx
  struct CbsLanguageFeature *v27; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v28[16]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v29[8]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v30[24]; // [rsp+90h] [rbp-70h] BYREF
  CbsLanguageFeature *v31[2]; // [rsp+A8h] [rbp-58h] BYREF
  CbsLanguageFeature *v32; // [rsp+B8h] [rbp-48h]
  CbsLanguageFeature *v33[2]; // [rsp+C0h] [rbp-40h] BYREF
  CbsLanguageFeature *v34; // [rsp+D0h] [rbp-30h]
  __int64 v35; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v36; // [rsp+E8h] [rbp-18h] BYREF
  int v37; // [rsp+F0h] [rbp-10h] BYREF
  _QWORD v38[2]; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v39; // [rsp+108h] [rbp+8h] BYREF
  __int128 v40; // [rsp+110h] [rbp+10h]
  __int64 v41; // [rsp+120h] [rbp+20h]
  __int64 v42; // [rsp+128h] [rbp+28h]
  int v43; // [rsp+190h] [rbp+90h] BYREF

  v43 = a3;
  v3 = a2;
  v27 = a2;
  v35 = (__int64)a2;
  v5 = 0;
  *(_OWORD *)v31 = 0;
  v32 = 0;
  if ( !*(_BYTE *)(a1 + 72) )
  {
    v35 = 0x200000001LL;
    v36 = 0;
    if ( (int)PolicyManager_GetPolicy(L"TextInput", L"AllowLanguageFeaturesUninstall", &v35, &v36) < 0 )
    {
      if ( v36 )
        PolicyManager_FreeGetPolicyData(v36);
    }
    else
    {
      v6 = *(_DWORD *)(v36 + 16);
      PolicyManager_FreeGetPolicyData(v36);
      if ( v6 != 1 )
        goto LABEL_25;
    }
  }
  if ( *(_QWORD *)a1 != *(_QWORD *)(a1 + 8) )
  {
    v37 = 0;
    v38[0] = 0;
    v38[1] = 0;
    v7 = operator new(0x30u);
    *v7 = v7;
    v7[1] = v7;
    v38[0] = v7;
    v39 = 0;
    v40 = 0;
    v41 = 7;
    v42 = 8;
    v37 = 1065353216;
    std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<enum PayloadType const,std::vector<CbsLanguageFeature>>>>>>>::_Assign_grow(
      &v39,
      16,
      v7);
    v33[0] = (CbsLanguageFeature *)&v43;
    v33[1] = (CbsLanguageFeature *)a1;
    v34 = (CbsLanguageFeature *)&v37;
    std::for_each<std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<CbsLanguageFeature>>>,_lambda_dbf3cdd2fb635a27b8a2727f64a1eb0d_>(
      v30,
      *(_QWORD *)(a1 + 48),
      *(_QWORD *)(a1 + 56),
      v33);
    v8 = (__int64 *)v38[0];
    for ( i = *(__int64 **)v38[0]; i != v8; i = (__int64 *)*i )
    {
      v10 = *((_DWORD *)i + 4);
      std::vector<std::wstring>::vector<std::wstring>(v33, a1);
      v11 = v5 | 2;
      if ( v10 == 1 )
        std::copy_if<std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>,std::back_insert_iterator<std::vector<std::wstring>>,_lambda_89e20cf5b205b052b5f2ed9adeb67dd7_>(
          &v36,
          *(_QWORD *)(a1 + 24),
          *(_QWORD *)(a1 + 32),
          (__int64)v33,
          (__int64 *)a1);
      v12 = v33[0];
      v13 = v33[1];
      while ( v12 != v13 )
      {
        v29[0] = (__int64)&std::_Func_impl_no_alloc<_lambda_e8565040e165d3daccfd4cbfb75449a5_,long,unsigned short const *,unsigned short const *,int *>::`vftable';
        v29[7] = (__int64)v29;
        FindClosestLanguageFeature<CbsLanguageFeature,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<CbsLanguageFeature>>>>(
          &v35,
          i[3],
          i[4],
          (int)v12,
          v29);
        if ( v35 != i[4] )
          std::vector<CbsLanguageFeature>::erase(i + 3, v28);
        v12 = (CbsLanguageFeature *)((char *)v12 + 32);
      }
      v14 = (const struct CbsLanguageFeature *)i[4];
      for ( j = (const struct CbsLanguageFeature *)i[3]; j != v14; j = (const struct CbsLanguageFeature *)((char *)j + 192) )
      {
        if ( v31[1] == v32 )
        {
          std::vector<CbsLanguageFeature>::_Emplace_reallocate<CbsLanguageFeature const &>(v31, v31[1]);
        }
        else
        {
          CbsLanguageFeature::CbsLanguageFeature(v31[1], j);
          v31[1] = (CbsLanguageFeature *)((char *)v31[1] + 192);
        }
      }
      v5 = v11 & 0xFFFFFFFD;
      std::vector<std::wstring>::_Tidy((__int64)v33);
    }
    std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<enum PayloadType const,std::vector<CbsLanguageFeature>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<enum PayloadType const,std::vector<CbsLanguageFeature>>>>>>>(&v39);
    std::list<std::pair<enum PayloadType const,std::vector<CbsLanguageFeature>>>::~list<std::pair<enum PayloadType const,std::vector<CbsLanguageFeature>>>(v38);
    v3 = v27;
  }
LABEL_25:
  v16 = v31[0];
  v17 = v31[1];
  if ( v31[0] != v31[1] )
  {
    NormalizeContainer<std::vector<CbsLanguageFeature>>(v31);
    *(_OWORD *)v33 = 0;
    v34 = 0;
    v18 = *(_QWORD *)(a1 + 48);
    v19 = *(_QWORD *)(a1 + 56);
    while ( v18 != v19 )
    {
      v20 = v31[1];
      for ( k = v31[0]; k != v20; k = (CbsLanguageFeature *)((char *)k + 192) )
      {
        if ( *((_DWORD *)k + 46) == *(_DWORD *)(v18 + 184) )
        {
          v22 = (const wchar_t *)((char *)k + 152);
          v23 = (const wchar_t *)(v18 + 152);
          if ( *(_QWORD *)(v18 + 176) > 7u )
            v23 = *(const wchar_t **)v23;
          v24 = *((_QWORD *)k + 21);
          if ( *((_QWORD *)k + 22) > 7u )
            v22 = *(const wchar_t **)v22;
          if ( v24 == *(_QWORD *)(v18 + 168) && (!v24 || !wmemcmp(v22, v23, v24)) )
            break;
        }
      }
      if ( k == v31[1] )
      {
        if ( v33[1] == v34 )
        {
          std::vector<CbsLanguageFeature>::_Emplace_reallocate<CbsLanguageFeature const &>(v33, v33[1]);
        }
        else
        {
          CbsLanguageFeature::CbsLanguageFeature(v33[1], (const struct CbsLanguageFeature *)v18);
          v33[1] = (CbsLanguageFeature *)((char *)v33[1] + 192);
        }
      }
      v18 += 192;
    }
    while ( 1 )
    {
      std::find_if<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<CbsLanguageFeature>>>,_lambda_19a36c88fbff04654dab99dd6c19dadf_>(
        &v27,
        v31[0],
        v31[1],
        v33);
      if ( v27 == v31[1] )
        break;
      if ( v33[1] == v34 )
      {
        std::vector<CbsLanguageFeature>::_Emplace_reallocate<CbsLanguageFeature const &>(v33, v33[1]);
      }
      else
      {
        CbsLanguageFeature::CbsLanguageFeature(v33[1], v27);
        v33[1] = (CbsLanguageFeature *)((char *)v33[1] + 192);
      }
      std::vector<CbsLanguageFeature>::erase(v31, v28);
    }
    std::vector<CbsLanguageFeature>::_Tidy((__int64)v33);
    v17 = v31[1];
    v16 = v31[0];
  }
  v25 = v32;
  v32 = 0;
  v31[1] = 0;
  v31[0] = 0;
  *(_QWORD *)v3 = v16;
  *((_QWORD *)v3 + 1) = v17;
  *((_QWORD *)v3 + 2) = v25;
  std::vector<CbsLanguageFeature>::_Tidy((__int64)v31);
  return v3;
}

```

## disassembly

```asm
0x180017a80  mov     [rsp-8+arg_18], rbx
0x180017a85  mov     [rsp-8+arg_10], r8d
0x180017a8a  push    rbp
0x180017a8b  push    rsi
0x180017a8c  push    rdi
0x180017a8d  push    r12
0x180017a8f  push    r13
0x180017a91  push    r14
0x180017a93  push    r15
0x180017a95  lea     rbp, [rsp-40h]
0x180017a9a  sub     rsp, 140h
0x180017aa1  mov     rax, cs:__security_cookie
0x180017aa8  xor     rax, rsp
0x180017aab  mov     [rbp+70h+var_40], rax
0x180017aaf  mov     r13, rdx
0x180017ab2  mov     [rsp+170h+var_138], rdx
0x180017ab7  mov     r14, rcx
0x180017aba  mov     [rbp+70h+var_90], rdx
0x180017abe  xor     r12d, r12d
0x180017ac1  mov     r15d, r12d
0x180017ac4  mov     [rsp+170h+var_140], r12d
0x180017ac9  xorps   xmm0, xmm0
0x180017acc  movdqu  xmmword ptr [rbp+70h+var_C8], xmm0
0x180017ad1  mov     [rbp+70h+var_B8], r12
0x180017ad5  cmp     [rcx+48h], r12b
0x180017ad9  jnz     short loc_180017B2F
0x180017adb  mov     dword ptr [rbp+70h+var_90], 1
0x180017ae2  mov     dword ptr [rbp+70h+var_90+4], 2
0x180017ae9  mov     [rbp+70h+var_88], r12
0x180017aed  lea     r9, [rbp+70h+var_88]
0x180017af1  lea     r8, [rbp+70h+var_90]
0x180017af5  lea     rdx, aAllowlanguagef; "AllowLanguageFeaturesUninstall"
0x180017afc  lea     rcx, aTextinput; "TextInput"
0x180017b03  call    cs:__imp_PolicyManager_GetPolicy
0x180017b09  mov     rcx, [rbp+70h+var_88]
0x180017b0d  test    eax, eax
0x180017b0f  js      short loc_180017B24
0x180017b11  mov     ebx, [rcx+10h]
0x180017b14  call    cs:__imp_PolicyManager_FreeGetPolicyData
0x180017b1a  cmp     ebx, 1
0x180017b1d  jz      short loc_180017B2F
0x180017b1f  jmp     loc_180017CDE
0x180017b24  test    rcx, rcx
0x180017b27  jz      short loc_180017B2F
0x180017b29  call    cs:__imp_PolicyManager_FreeGetPolicyData
0x180017b2f  mov     rax, [r14+8]
0x180017b33  cmp     [r14], rax
0x180017b36  jz      loc_180017CDE
0x180017b3c  mov     [rbp+70h+var_80], 0
0x180017b43  mov     [rbp+70h+var_78], r12
0x180017b47  mov     [rbp+70h+var_70], r12
0x180017b4b  mov     ecx, 30h ; '0'; Size
0x180017b50  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180017b55  mov     [rax], rax
0x180017b58  mov     [rax+8], rax
0x180017b5c  mov     [rbp+70h+var_78], rax
0x180017b60  mov     [rbp+70h+var_68], r12
0x180017b64  xorps   xmm0, xmm0
0x180017b67  movdqa  [rbp+70h+var_60], xmm0
0x180017b6c  mov     [rbp+70h+var_50], 7
0x180017b74  mov     [rbp+70h+var_48], 8
0x180017b7c  mov     [rbp+70h+var_80], 3F800000h
0x180017b83  mov     r8, rax
0x180017b86  mov     edx, 10h
0x180017b8b  lea     rcx, [rbp+70h+var_68]
0x180017b8f  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBW4PayloadType@@V?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBW4PayloadType@@V?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<PayloadType const,std::vector<CbsLanguageFeature>>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<PayloadType const,std::vector<CbsLanguageFeature>>>>>)
0x180017b94  nop
0x180017b95  lea     rax, [rbp+70h+arg_10]
0x180017b9c  mov     [rbp+70h+var_B0], rax
0x180017ba0  mov     [rbp+70h+var_B0+8], r14
0x180017ba4  lea     rax, [rbp+70h+var_80]
0x180017ba8  mov     [rbp+70h+var_A0], rax
0x180017bac  lea     r9, [rbp+70h+var_B0]
0x180017bb0  mov     r8, [r14+38h]
0x180017bb4  mov     rdx, [r14+30h]
0x180017bb8  lea     rcx, [rbp+70h+var_E0]
0x180017bbc  call    ??$for_each@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@VCbsLanguageFeature@@@std@@@std@@@std@@V_lambda_dbf3cdd2fb635a27b8a2727f64a1eb0d_@@@std@@YA?AV_lambda_dbf3cdd2fb635a27b8a2727f64a1eb0d_@@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@VCbsLanguageFeature@@@std@@@std@@@0@0V1@@Z; std::for_each<std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<CbsLanguageFeature>>>,_lambda_dbf3cdd2fb635a27b8a2727f64a1eb0d_>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<CbsLanguageFeature>>>,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<CbsLanguageFeature>>>,_lambda_dbf3cdd2fb635a27b8a2727f64a1eb0d_)
0x180017bc1  mov     rdi, [rbp+70h+var_78]
0x180017bc5  mov     rbx, [rdi]
0x180017bc8  cmp     rbx, rdi
0x180017bcb  jz      loc_180017CC4
0x180017bd1  mov     esi, [rbx+10h]
0x180017bd4  mov     rdx, r14
0x180017bd7  lea     rcx, [rbp+70h+var_B0]
0x180017bdb  call    ??0?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@AEBV01@@Z; std::vector<std::wstring>::vector<std::wstring>(std::vector<std::wstring> const &)
0x180017be0  or      r15d, 2
0x180017be4  mov     [rsp+170h+var_140], r15d
0x180017be9  cmp     esi, 1
0x180017bec  jnz     short loc_180017C08
0x180017bee  mov     [rsp+170h+var_150], r14
0x180017bf3  lea     r9, [rbp+70h+var_B0]
0x180017bf7  mov     r8, [r14+20h]
0x180017bfb  mov     rdx, [r14+18h]
0x180017bff  lea     rcx, [rbp+70h+var_88]
0x180017c03  call    ??$copy_if@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@V?$back_insert_iterator@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@2@V_lambda_89e20cf5b205b052b5f2ed9adeb67dd7_@@@std@@YA?AV?$back_insert_iterator@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@0@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@0@0V10@V_lambda_89e20cf5b205b052b5f2ed9adeb67dd7_@@@Z; std::copy_if<std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>,std::back_insert_iterator<std::vector<std::wstring>>,_lambda_89e20cf5b205b052b5f2ed9adeb67dd7_>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>,std::back_insert_iterator<std::vector<std::wstring>>,_lambda_89e20cf5b205b052b5f2ed9adeb67dd7_)
0x180017c08  mov     rsi, [rbp+70h+var_B0]
0x180017c0c  mov     r12, [rbp+70h+var_B0+8]
0x180017c10  jmp     short loc_180017C61
0x180017c12  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_e8565040e165d3daccfd4cbfb75449a5_@@JPEBGPEBGPEAH@std@@6B@; const std::_Func_impl_no_alloc<_lambda_e8565040e165d3daccfd4cbfb75449a5_,long,ushort const *,ushort const *,int *>::`vftable'
0x180017c19  mov     [rsp+170h+var_120], rax
0x180017c1e  lea     rax, [rsp+170h+var_120]
0x180017c23  mov     [rbp+70h+var_E8], rax
0x180017c27  lea     rax, [rsp+170h+var_120]
0x180017c2c  mov     [rsp+170h+var_150], rax
0x180017c31  mov     r9, rsi
0x180017c34  mov     r8, [rbx+20h]
0x180017c38  mov     rdx, [rbx+18h]
0x180017c3c  lea     rcx, [rbp+70h+var_90]
0x180017c40  call    ??$FindClosestLanguageFeature@VCbsLanguageFeature@@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@VCbsLanguageFeature@@@std@@@std@@@std@@@@YA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@VCbsLanguageFeature@@@std@@@std@@@std@@V01@0AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@V?$function@$$A6AJPEBG0PEAH@Z@1@@Z; FindClosestLanguageFeature<CbsLanguageFeature,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<CbsLanguageFeature>>>>(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<CbsLanguageFeature>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<CbsLanguageFeature>>>,std::wstring const &,std::function<long (ushort const *,ushort const *,int *)>)
0x180017c45  mov     r8, [rbp+70h+var_90]
0x180017c49  cmp     r8, [rbx+20h]
0x180017c4d  jz      short loc_180017C5D
0x180017c4f  lea     rdx, [rsp+170h+var_130]
0x180017c54  lea     rcx, [rbx+18h]
0x180017c58  call    ?erase@?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@VCbsLanguageFeature@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@VCbsLanguageFeature@@@std@@@std@@@2@@Z; std::vector<CbsLanguageFeature>::erase(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<CbsLanguageFeature>>>)
0x180017c5d  add     rsi, 20h ; ' '
0x180017c61  cmp     rsi, r12
0x180017c64  jnz     short loc_180017C12
0x180017c66  mov     r12, [rbx+20h]
0x180017c6a  mov     rsi, [rbx+18h]
0x180017c6e  jmp     short loc_180017CA5
0x180017c70  mov     rax, [rbp+70h+var_C8+8]
0x180017c74  cmp     rax, [rbp+70h+var_B8]
0x180017c78  jz      short loc_180017C8F
0x180017c7a  mov     rdx, rsi; struct CbsLanguageFeature *
0x180017c7d  mov     rcx, rax; this
0x180017c80  call    ??0CbsLanguageFeature@@QEAA@AEBV0@@Z; CbsLanguageFeature::CbsLanguageFeature(CbsLanguageFeature const &)
0x180017c85  add     [rbp+70h+var_C8+8], 0C0h
0x180017c8d  jmp     short loc_180017C9E
0x180017c8f  mov     r8, rsi
0x180017c92  mov     rdx, rax
0x180017c95  lea     rcx, [rbp+70h+var_C8]
0x180017c99  call    ??$_Emplace_reallocate@AEBVCbsLanguageFeature@@@?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@AEAAPEAVCbsLanguageFeature@@QEAV2@AEBV2@@Z; std::vector<CbsLanguageFeature>::_Emplace_reallocate<CbsLanguageFeature const &>(CbsLanguageFeature * const,CbsLanguageFeature const &)
0x180017c9e  add     rsi, 0C0h
0x180017ca5  cmp     rsi, r12
0x180017ca8  jnz     short loc_180017C70
0x180017caa  and     r15d, 0FFFFFFFDh
0x180017cae  mov     [rsp+170h+var_140], r15d
0x180017cb3  lea     rcx, [rbp+70h+var_B0]
0x180017cb7  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180017cbc  mov     rbx, [rbx]
0x180017cbf  jmp     loc_180017BC8
0x180017cc4  lea     rcx, [rbp+70h+var_68]
0x180017cc8  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBW4PayloadType@@V?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<PayloadType const,std::vector<CbsLanguageFeature>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<PayloadType const,std::vector<CbsLanguageFeature>>>>>>>(void)
0x180017ccd  lea     rcx, [rbp+70h+var_78]
0x180017cd1  call    ??1?$list@U?$pair@$$CBW4PayloadType@@V?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@@std@@V?$allocator@U?$pair@$$CBW4PayloadType@@V?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@@std@@@2@@std@@QEAA@XZ; std::list<std::pair<PayloadType const,std::vector<CbsLanguageFeature>>>::~list<std::pair<PayloadType const,std::vector<CbsLanguageFeature>>>(void)
0x180017cd6  mov     r13, [rsp+170h+var_138]
0x180017cdb  xor     r12d, r12d
0x180017cde  mov     rax, [rbp+70h+var_C8]
0x180017ce2  mov     rdx, [rbp+70h+var_C8+8]
0x180017ce6  cmp     rax, rdx
0x180017ce9  jz      loc_180017E2F
0x180017cef  lea     rcx, [rbp+70h+var_C8]
0x180017cf3  call    ??$NormalizeContainer@V?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@@@YAXAEAV?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@@Z; NormalizeContainer<std::vector<CbsLanguageFeature>>(std::vector<CbsLanguageFeature> &)
0x180017cf8  xorps   xmm0, xmm0
0x180017cfb  movdqu  xmmword ptr [rbp+70h+var_B0], xmm0
0x180017d00  mov     [rbp+70h+var_A0], r12
0x180017d04  mov     rbx, [r14+30h]
0x180017d08  mov     r14, [r14+38h]
0x180017d0c  jmp     loc_180017DB3
0x180017d11  mov     rsi, [rbp+70h+var_C8+8]
0x180017d15  mov     rdi, [rbp+70h+var_C8]
0x180017d19  jmp     short loc_180017D73
0x180017d1b  mov     eax, [rbx+0B8h]
0x180017d21  cmp     [rdi+0B8h], eax
0x180017d27  jnz     short loc_180017D6C
0x180017d29  lea     rcx, [rdi+98h]
0x180017d30  lea     rdx, [rbx+98h]
0x180017d37  cmp     qword ptr [rbx+0B0h], 7
0x180017d3f  jbe     short loc_180017D44
0x180017d41  mov     rdx, [rdx]; S2
0x180017d44  mov     r8, [rdi+0A8h]; N
0x180017d4b  cmp     qword ptr [rcx+18h], 7
0x180017d50  jbe     short loc_180017D55
0x180017d52  mov     rcx, [rcx]; S1
0x180017d55  cmp     r8, [rbx+0A8h]
0x180017d5c  jnz     short loc_180017D6C
0x180017d5e  test    r8, r8
0x180017d61  jz      short loc_180017D78
0x180017d63  call    wmemcmp
0x180017d68  test    eax, eax
0x180017d6a  jz      short loc_180017D78
0x180017d6c  add     rdi, 0C0h
0x180017d73  cmp     rdi, rsi
0x180017d76  jnz     short loc_180017D1B
0x180017d78  cmp     rdi, [rbp+70h+var_C8+8]
0x180017d7c  jnz     short loc_180017DAC
0x180017d7e  mov     rax, [rbp+70h+var_B0+8]
0x180017d82  cmp     rax, [rbp+70h+var_A0]
0x180017d86  jz      short loc_180017D9D
0x180017d88  mov     rdx, rbx; struct CbsLanguageFeature *
0x180017d8b  mov     rcx, rax; this
0x180017d8e  call    ??0CbsLanguageFeature@@QEAA@AEBV0@@Z; CbsLanguageFeature::CbsLanguageFeature(CbsLanguageFeature const &)
0x180017d93  add     [rbp+70h+var_B0+8], 0C0h
0x180017d9b  jmp     short loc_180017DAC
0x180017d9d  mov     r8, rbx
0x180017da0  mov     rdx, rax
0x180017da3  lea     rcx, [rbp+70h+var_B0]
0x180017da7  call    ??$_Emplace_reallocate@AEBVCbsLanguageFeature@@@?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@AEAAPEAVCbsLanguageFeature@@QEAV2@AEBV2@@Z; std::vector<CbsLanguageFeature>::_Emplace_reallocate<CbsLanguageFeature const &>(CbsLanguageFeature * const,CbsLanguageFeature const &)
0x180017dac  add     rbx, 0C0h
0x180017db3  cmp     rbx, r14
0x180017db6  jnz     loc_180017D11
0x180017dbc  lea     r9, [rbp+70h+var_B0]
0x180017dc0  mov     r8, [rbp+70h+var_C8+8]
0x180017dc4  mov     rdx, [rbp+70h+var_C8]
0x180017dc8  lea     rcx, [rsp+170h+var_138]
0x180017dcd  call    ??$find_if@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@VCbsLanguageFeature@@@std@@@std@@@std@@V_lambda_19a36c88fbff04654dab99dd6c19dadf_@@@std@@YA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@VCbsLanguageFeature@@@std@@@std@@@0@V10@V10@V_lambda_19a36c88fbff04654dab99dd6c19dadf_@@@Z; std::find_if<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<CbsLanguageFeature>>>,_lambda_19a36c88fbff04654dab99dd6c19dadf_>(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<CbsLanguageFeature>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<CbsLanguageFeature>>>,_lambda_19a36c88fbff04654dab99dd6c19dadf_)
0x180017dd2  mov     rbx, [rsp+170h+var_138]
0x180017dd7  cmp     rbx, [rbp+70h+var_C8+8]
0x180017ddb  jz      short loc_180017E1E
0x180017ddd  mov     rax, [rbp+70h+var_B0+8]
0x180017de1  cmp     rax, [rbp+70h+var_A0]
0x180017de5  jz      short loc_180017DFC
0x180017de7  mov     rdx, rbx; struct CbsLanguageFeature *
0x180017dea  mov     rcx, rax; this
0x180017ded  call    ??0CbsLanguageFeature@@QEAA@AEBV0@@Z; CbsLanguageFeature::CbsLanguageFeature(CbsLanguageFeature const &)
0x180017df2  add     [rbp+70h+var_B0+8], 0C0h
0x180017dfa  jmp     short loc_180017E0B
0x180017dfc  mov     r8, rbx
0x180017dff  mov     rdx, rax
0x180017e02  lea     rcx, [rbp+70h+var_B0]
0x180017e06  call    ??$_Emplace_reallocate@AEBVCbsLanguageFeature@@@?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@AEAAPEAVCbsLanguageFeature@@QEAV2@AEBV2@@Z; std::vector<CbsLanguageFeature>::_Emplace_reallocate<CbsLanguageFeature const &>(CbsLanguageFeature * const,CbsLanguageFeature const &)
0x180017e0b  mov     r8, rbx
0x180017e0e  lea     rdx, [rsp+170h+var_130]
0x180017e13  lea     rcx, [rbp+70h+var_C8]
0x180017e17  call    ?erase@?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@VCbsLanguageFeature@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@VCbsLanguageFeature@@@std@@@std@@@2@@Z; std::vector<CbsLanguageFeature>::erase(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<CbsLanguageFeature>>>)
0x180017e1c  jmp     short loc_180017DBC
0x180017e1e  lea     rcx, [rbp+70h+var_B0]
0x180017e22  call    ?_Tidy@?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@AEAAXXZ; std::vector<CbsLanguageFeature>::_Tidy(void)
0x180017e27  mov     rdx, [rbp+70h+var_C8+8]
0x180017e2b  mov     rax, [rbp+70h+var_C8]
0x180017e2f  mov     rcx, [rbp+70h+var_B8]
0x180017e33  mov     [rbp+70h+var_B8], r12
0x180017e37  mov     [rbp+70h+var_C8+8], r12
0x180017e3b  mov     [rbp+70h+var_C8], r12
0x180017e3f  mov     [r13+0], rax
0x180017e43  mov     [r13+8], rdx
0x180017e47  mov     [r13+10h], rcx
0x180017e4b  lea     rcx, [rbp+70h+var_C8]
0x180017e4f  call    ?_Tidy@?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@AEAAXXZ; std::vector<CbsLanguageFeature>::_Tidy(void)
0x180017e54  mov     rax, r13
0x180017e57  mov     rcx, [rbp+70h+var_40]
0x180017e5b  xor     rcx, rsp; StackCookie
0x180017e5e  call    __security_check_cookie
0x180017e63  mov     rbx, [rsp+170h+arg_18]
0x180017e6b  add     rsp, 140h
0x180017e72  pop     r15
0x180017e74  pop     r14
0x180017e76  pop     r13
0x180017e78  pop     r12
0x180017e7a  pop     rdi
0x180017e7b  pop     rsi
0x180017e7c  pop     rbp
0x180017e7d  retn
```
