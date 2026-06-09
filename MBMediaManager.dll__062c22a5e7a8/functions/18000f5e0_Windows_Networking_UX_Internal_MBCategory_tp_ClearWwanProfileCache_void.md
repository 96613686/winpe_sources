# Windows::Networking::UX::Internal::MBCategory::tp_ClearWwanProfileCache(void)

- ea: `0x18000f5e0`
- end: `0x18000f90a`
- name: `?tp_ClearWwanProfileCache@MBCategory@Internal@UX@Networking@Windows@@AEAAXXZ`
- size: `810`
- prototype: `void __fastcall(Windows::Networking::UX::Internal::MBCategory *__hidden this)`
- caller_count: `1`
- callee_count: `20`
- tags: `broker_com_uri`

## callers

- `0x18000ea3c`

## callees

- `0x180002150`
- `0x18000735c`
- `0x18000ccb0`
- `0x18000f26c`
- `0x18000f3b0`
- `0x18000f5e0`
- `0x18000f910`
- `0x18000f950`
- `0x18000fe78`
- `0x18001f584`
- `0x18001f5b8`
- `0x180023018`
- `0x180023d28`
- `0x180023da8`
- `0x1800260c8`
- `0x18002cd20`
- `0x18002d6a0`
- `0x180042428`
- `0x180044ae8`
- `0x180059010`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000f82f`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000f82f`

## string_xrefs

- `0x18000f60e`: `Clearing Profile Cache`
- `0x18000f61a`: `Windows::Networking::UX::Internal::MBCategory::tp_ClearWwanProfileCache`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Windows::Networking::UX::Internal::MBCategory::tp_ClearWwanProfileCache(
        Windows::Networking::UX::Internal::MBCategory *this)
{
  __int64 v2; // rdx
  __int64 v3; // rdx
  char *v4; // r12
  __int64 i; // rbx
  _QWORD *v6; // rdx
  unsigned __int64 v7; // rsi
  __int64 v8; // rdx
  char **v9; // r13
  char *v10; // rax
  int v11; // r14d
  char **v12; // rcx
  __int64 v13; // r15
  char ***v14; // rdi
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // rcx
  __int64 j; // rax
  char *v19; // rdi
  __int64 v20; // rsi
  __int64 v21; // rbx
  char **v22; // rcx
  __int64 k; // rax
  char *m; // rcx
  char **v25; // [rsp+20h] [rbp-79h] BYREF
  __int64 v26; // [rsp+28h] [rbp-71h]
  __int64 v27; // [rsp+30h] [rbp-69h] BYREF
  int v28; // [rsp+38h] [rbp-61h]
  int v29; // [rsp+3Ch] [rbp-5Dh]
  __int64 v30; // [rsp+40h] [rbp-59h] BYREF
  Windows::Networking::UX::Internal::MBCategory *v31; // [rsp+48h] [rbp-51h]
  void **v32; // [rsp+50h] [rbp-49h] BYREF
  __int64 v33; // [rsp+58h] [rbp-41h]
  char *v34; // [rsp+60h] [rbp-39h]
  _OWORD v35[2]; // [rsp+78h] [rbp-21h] BYREF
  unsigned __int64 v36; // [rsp+98h] [rbp-1h] BYREF

  v31 = this;
  MBSettingUXLogging::Verbose(
    "Windows::Networking::UX::Internal::MBCategory::tp_ClearWwanProfileCache",
    4665,
    "Clearing Profile Cache");
  v25 = 0;
  v26 = 0;
  std::_Tree<std::_Tset_traits<Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>,std::less<Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>>,std::allocator<Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>>,0>>::_Alloc_sentinel_and_proxy(&v25);
  v2 = **((_QWORD **)this + 116);
  v27 = v2;
  while ( !*(_BYTE *)(v2 + 25) )
  {
    std::pair<std::wstring const,Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>>::pair<std::wstring const,Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>>(
      (__int64)v35,
      v2 + 32);
    if ( v36 )
    {
      LOBYTE(v3) = 1;
      (*(void (__fastcall **)(unsigned __int64, __int64))(*(_QWORD *)v36 + 272LL))(v36, v3);
      std::_Tree<std::_Tset_traits<Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>,std::less<Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>>,std::allocator<Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>>,0>>::insert<0,0>(
        (__int64 *)&v25,
        (__int64)&v32,
        (__int64 *)&v36);
    }
    std::pair<std::wstring const,Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>>::~pair<std::wstring const,Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>>((__int64)v35);
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>>>>,std::_Iterator_base0>::operator++(&v27);
    v2 = v27;
  }
  std::_Tree<std::_Tmap_traits<std::wstring,Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>>>,0>>::clear((char *)this + 928);
  v4 = (char *)this + 944;
  for ( i = **((_QWORD **)this + 118); !*(_BYTE *)(i + 25); i = j )
  {
    memset(v35, 0, sizeof(v35));
    v6 = (_QWORD *)(i + 32);
    if ( *(_QWORD *)(i + 56) > 7u )
      v6 = (_QWORD *)*v6;
    std::wstring::_Construct<2,unsigned short const *>(v35, v6, *(_QWORD *)(i + 48));
    v36 = *(_QWORD *)(i + 64);
    v7 = v36;
    Microsoft::WRL::ComPtr<Windows::Networking::UX::IUserInputType>::InternalAddRef(&v36);
    if ( v7 )
    {
      LOBYTE(v8) = 1;
      (*(void (__fastcall **)(unsigned __int64, __int64))(*(_QWORD *)v7 + 272LL))(v7, v8);
      v9 = v25;
      v10 = v25[1];
      v11 = 0;
      v30 = 0;
      v12 = v25;
      if ( v10[25] )
      {
        v13 = (__int64)v10;
      }
      else
      {
        do
        {
          v13 = (__int64)v10;
          v34 = v10;
          if ( *((_QWORD *)v10 + 4) >= v7 )
          {
            v11 = 1;
            v12 = (char **)v10;
          }
          else
          {
            v11 = 0;
            v10 += 16;
          }
          v10 = *(char **)v10;
        }
        while ( !v10[25] );
      }
      if ( *((_BYTE *)v12 + 25) || v7 < (unsigned __int64)v12[4] )
      {
        if ( v26 == 0x666666666666666LL )
          std::_Xlength_error("map/set too long");
        v32 = (void **)&v25;
        v33 = 0;
        v14 = (char ***)operator new(0x28u);
        v14[4] = (char **)v7;
        Microsoft::WRL::ComPtr<Windows::Networking::UX::IUserInputType>::InternalAddRef(v14 + 4);
        *v14 = v9;
        v14[1] = v9;
        v14[2] = v9;
        *((_WORD *)v14 + 12) = 0;
        v33 = 0;
        v27 = v13;
        v28 = v11;
        v29 = v30;
        std::_Tree_val<std::_Tree_simple_types<Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>>>::_Insert_node(
          &v25,
          (__int64)&v27,
          (__int64)v14);
      }
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v36);
    std::wstring::_Tidy_deallocate(v35);
    v17 = *(_QWORD *)(i + 16);
    if ( *(_BYTE *)(v17 + 25) )
    {
      for ( j = *(_QWORD *)(i + 8); !*(_BYTE *)(j + 25) && i == *(_QWORD *)(j + 16); j = *(_QWORD *)(j + 8) )
        i = j;
    }
    else
    {
      j = std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>>>>::_Min(
            v17,
            v15,
            v16);
    }
  }
  std::_Tree<std::_Tmap_traits<std::wstring,Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>>>,0>>::clear(v4);
  v19 = *v25;
  v20 = (__int64)v31;
  while ( !v19[25] )
  {
    v30 = *((_QWORD *)v19 + 4);
    v21 = v30;
    Microsoft::WRL::ComPtr<Windows::Networking::UX::IUserInputType>::InternalAddRef(&v30);
    v27 = v21;
    Microsoft::WRL::ComPtr<Windows::Networking::UX::IUserInputType>::InternalAddRef(&v27);
    Windows::Networking::UX::Internal::MBCategory::_SubmitThreadpoolInvoke(v20, &v27);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
    v22 = (char **)*((_QWORD *)v19 + 2);
    if ( *((_BYTE *)v22 + 25) )
    {
      for ( k = *((_QWORD *)v19 + 1); !*(_BYTE *)(k + 25) && v19 == *(char **)(k + 16); k = *(_QWORD *)(k + 8) )
        v19 = (char *)k;
      v19 = (char *)k;
    }
    else
    {
      v19 = (char *)*((_QWORD *)v19 + 2);
      for ( m = *v22; !m[25]; m = *(char **)m )
        v19 = m;
    }
  }
  std::_Tree_val<std::_Tree_simple_types<Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>>>::_Erase_tree<std::allocator<std::_Tree_node<Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>,void *>>>(
    (__int64)&v25,
    (__int64)&v25,
    v25[1]);
  std::_Deallocate<16>(v25, (struct std::nothrow_t *)0x28);
}

```

## disassembly

```asm
0x18000f5e0  push    rbp
0x18000f5e2  push    rbx
0x18000f5e3  push    rsi
0x18000f5e4  push    rdi
0x18000f5e5  push    r12
0x18000f5e7  push    r13
0x18000f5e9  push    r14
0x18000f5eb  push    r15
0x18000f5ed  lea     rbp, [rsp-1Fh]
0x18000f5f2  sub     rsp, 0B8h
0x18000f5f9  mov     rax, cs:__security_cookie
0x18000f600  xor     rax, rsp
0x18000f603  mov     [rbp+57h+var_50], rax
0x18000f607  mov     rsi, rcx
0x18000f60a  mov     [rbp+57h+var_A8], rcx
0x18000f60e  lea     r8, aClearingProfil; "Clearing Profile Cache"
0x18000f615  mov     edx, 1239h; unsigned int
0x18000f61a  lea     rcx, aWindowsNetwork_129; "Windows::Networking::UX::Internal::MBCa"...
0x18000f621  call    ?Verbose@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Verbose(char const *,ulong,char const *,...)
0x18000f626  xor     r15d, r15d
0x18000f629  mov     [rbp+57h+var_D0], r15
0x18000f62d  mov     [rbp+57h+var_C8], r15
0x18000f631  lea     rcx, [rbp+57h+var_D0]
0x18000f635  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tset_traits@V?$ComPtr@UIMbConnectionProfile@UX@Networking@Windows@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIMbConnectionProfile@UX@Networking@Windows@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIMbConnectionProfile@UX@Networking@Windows@@@WRL@Microsoft@@@5@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tset_traits<Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>,std::less<Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>>,std::allocator<Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>>,0>>::_Alloc_sentinel_and_proxy(void)
0x18000f63a  nop
0x18000f63b  lea     rbx, [rsi+3A0h]
0x18000f642  mov     rdx, [rbx]
0x18000f645  mov     rdx, [rdx]
0x18000f648  mov     [rbp+57h+var_C0], rdx
0x18000f64c  cmp     [rdx+19h], r15b
0x18000f650  jnz     short loc_18000F6A4
0x18000f652  add     rdx, 20h ; ' '
0x18000f656  lea     rcx, [rbp+57h+var_78]
0x18000f65a  call    ??0?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIMbConnectionProfile@UX@Networking@Windows@@@WRL@Microsoft@@@std@@QEAA@AEBU01@@Z; std::pair<std::wstring const,Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>>::pair<std::wstring const,Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>>(std::pair<std::wstring const,Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>> const &)
0x18000f65f  nop
0x18000f660  mov     rcx, [rbp+57h+var_58]
0x18000f664  test    rcx, rcx
0x18000f667  jz      short loc_18000F68C
0x18000f669  mov     rax, [rcx]
0x18000f66c  mov     dl, 1
0x18000f66e  mov     rax, [rax+110h]
0x18000f675  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f67a  lea     r8, [rbp+57h+var_58]
0x18000f67e  lea     rdx, [rbp+57h+var_A0]
0x18000f682  lea     rcx, [rbp+57h+var_D0]
0x18000f686  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@V?$ComPtr@UIMbConnectionProfile@UX@Networking@Windows@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIMbConnectionProfile@UX@Networking@Windows@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIMbConnectionProfile@UX@Networking@Windows@@@WRL@Microsoft@@@5@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$ComPtr@UIMbConnectionProfile@UX@Networking@Windows@@@WRL@Microsoft@@@std@@@std@@@std@@_N@1@AEBV?$ComPtr@UIMbConnectionProfile@UX@Networking@Windows@@@WRL@Microsoft@@@Z; std::_Tree<std::_Tset_traits<Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>,std::less<Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>>,std::allocator<Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>>,0>>::insert<0,0>(Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile> const &)
0x18000f68b  nop
0x18000f68c  lea     rcx, [rbp+57h+var_78]
0x18000f690  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIMbConnectionProfile@UX@Networking@Windows@@@WRL@Microsoft@@@std@@QEAA@XZ; std::pair<std::wstring const,Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>>::~pair<std::wstring const,Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>>(void)
0x18000f695  lea     rcx, [rbp+57h+var_C0]
0x18000f699  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIMbConnectionProfile@UX@Networking@Windows@@@WRL@Microsoft@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>>>>,std::_Iterator_base0>::operator++(void)
0x18000f69e  mov     rdx, [rbp+57h+var_C0]
0x18000f6a2  jmp     short loc_18000F64C
0x18000f6a4  mov     rcx, rbx
0x18000f6a7  call    ?clear@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIMbConnectionProfile@UX@Networking@Windows@@@WRL@Microsoft@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIMbConnectionProfile@UX@Networking@Windows@@@WRL@Microsoft@@@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tmap_traits<std::wstring,Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>>>,0>>::clear(void)
0x18000f6ac  lea     r12, [rsi+3B0h]
0x18000f6b3  mov     rbx, [r12]
0x18000f6b7  mov     rbx, [rbx]
0x18000f6ba  cmp     [rbx+19h], r15b
0x18000f6be  jnz     loc_18000F836
0x18000f6c4  xorps   xmm0, xmm0
0x18000f6c7  movups  [rbp+57h+var_78], xmm0
0x18000f6cb  xorps   xmm1, xmm1
0x18000f6ce  movdqu  [rbp+57h+var_68], xmm1
0x18000f6d3  lea     rdx, [rbx+20h]
0x18000f6d7  cmp     qword ptr [rbx+38h], 7
0x18000f6dc  jbe     short loc_18000F6E1
0x18000f6de  mov     rdx, [rdx]
0x18000f6e1  mov     r8, [rbx+30h]
0x18000f6e5  lea     rcx, [rbp+57h+var_78]
0x18000f6e9  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x18000f6ee  mov     rsi, [rbx+40h]
0x18000f6f2  mov     [rbp+57h+var_58], rsi
0x18000f6f6  lea     rcx, [rbp+57h+var_58]
0x18000f6fa  call    ?InternalAddRef@?$ComPtr@UIUserInputType@UX@Networking@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Networking::UX::IUserInputType>::InternalAddRef(void)
0x18000f6ff  nop
0x18000f700  test    rsi, rsi
0x18000f703  jz      loc_18000F7E4
0x18000f709  mov     rax, [rsi]
0x18000f70c  mov     dl, 1
0x18000f70e  mov     rcx, rsi
0x18000f711  mov     rax, [rax+110h]
0x18000f718  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f71d  mov     r13, [rbp+57h+var_D0]
0x18000f721  mov     rax, [r13+8]
0x18000f725  mov     r14d, r15d
0x18000f728  xor     ecx, ecx
0x18000f72a  mov     [rbp+57h+var_B0], rcx
0x18000f72e  mov     rcx, r13
0x18000f731  cmp     [rax+19h], r15b
0x18000f735  jnz     short loc_18000F761
0x18000f737  mov     r15, rax
0x18000f73a  mov     [rbp+57h+var_90], rax
0x18000f73e  cmp     [rax+20h], rsi
0x18000f742  jnb     short loc_18000F74D
0x18000f744  xor     r14d, r14d
0x18000f747  add     rax, 10h
0x18000f74b  jmp     short loc_18000F756
0x18000f74d  mov     r14d, 1
0x18000f753  mov     rcx, rax
0x18000f756  mov     rax, [rax]
0x18000f759  cmp     byte ptr [rax+19h], 0
0x18000f75d  jz      short loc_18000F737
0x18000f75f  jmp     short loc_18000F764
0x18000f761  mov     r15, rax
0x18000f764  cmp     byte ptr [rcx+19h], 0
0x18000f768  jnz     short loc_18000F770
0x18000f76a  cmp     rsi, [rcx+20h]
0x18000f76e  jnb     short loc_18000F7E1
0x18000f770  mov     rax, 666666666666666h
0x18000f77a  cmp     [rbp+57h+var_C8], rax
0x18000f77e  jz      loc_18000F828
0x18000f784  lea     rax, [rbp+57h+var_D0]
0x18000f788  mov     [rbp+57h+var_A0], rax
0x18000f78c  mov     [rbp+57h+var_98], 0
0x18000f794  mov     ecx, 28h ; '('; Size
0x18000f799  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000f79e  mov     rdi, rax
0x18000f7a1  lea     rcx, [rax+20h]
0x18000f7a5  mov     [rcx], rsi
0x18000f7a8  call    ?InternalAddRef@?$ComPtr@UIUserInputType@UX@Networking@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Networking::UX::IUserInputType>::InternalAddRef(void)
0x18000f7ad  mov     [rdi], r13
0x18000f7b0  mov     [rdi+8], r13
0x18000f7b4  mov     [rdi+10h], r13
0x18000f7b8  xor     eax, eax
0x18000f7ba  mov     [rdi+18h], ax
0x18000f7be  mov     [rbp+57h+var_98], rax
0x18000f7c2  mov     [rbp+57h+var_C0], r15
0x18000f7c6  mov     [rbp+57h+var_B8], r14d
0x18000f7ca  mov     rax, [rbp+57h+var_B0]
0x18000f7ce  mov     [rbp+57h+var_B4], eax
0x18000f7d1  mov     r8, rdi
0x18000f7d4  lea     rdx, [rbp+57h+var_C0]
0x18000f7d8  lea     rcx, [rbp+57h+var_D0]
0x18000f7dc  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@V?$ComPtr@UIMbConnectionProfile@UX@Networking@Windows@@@WRL@Microsoft@@@std@@@std@@QEAAPEAU?$_Tree_node@V?$ComPtr@UIMbConnectionProfile@UX@Networking@Windows@@@WRL@Microsoft@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@V?$ComPtr@UIMbConnectionProfile@UX@Networking@Windows@@@WRL@Microsoft@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>>>::_Insert_node(std::_Tree_id<std::_Tree_node<Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>,void *> *>,std::_Tree_node<Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>,void *> * const)
0x18000f7e1  xor     r15d, r15d
0x18000f7e4  lea     rcx, [rbp+57h+var_58]
0x18000f7e8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000f7ed  lea     rcx, [rbp+57h+var_78]
0x18000f7f1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000f7f6  mov     rcx, [rbx+10h]
0x18000f7fa  cmp     [rcx+19h], r15b
0x18000f7fe  jz      short loc_18000F81B
0x18000f800  mov     rax, [rbx+8]
0x18000f804  jmp     short loc_18000F813
0x18000f806  cmp     rbx, [rax+10h]
0x18000f80a  jnz     short loc_18000F820
0x18000f80c  mov     rbx, rax
0x18000f80f  mov     rax, [rax+8]
0x18000f813  cmp     [rax+19h], r15b
0x18000f817  jz      short loc_18000F806
0x18000f819  jmp     short loc_18000F820
0x18000f81b  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIMbConnectionProfile@UX@Networking@Windows@@@WRL@Microsoft@@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIMbConnectionProfile@UX@Networking@Windows@@@WRL@Microsoft@@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>>>>::_Min(std::_Tree_node<std::pair<std::wstring const,Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>>,void *> *)
0x18000f820  mov     rbx, rax
0x18000f823  jmp     loc_18000F6BA
0x18000f828  lea     rcx, aMapSetTooLong; "map/set too long"
0x18000f82f  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000f836  mov     rcx, r12
0x18000f839  call    ?clear@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIMbConnectionProfile@UX@Networking@Windows@@@WRL@Microsoft@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIMbConnectionProfile@UX@Networking@Windows@@@WRL@Microsoft@@@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tmap_traits<std::wstring,Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>>>,0>>::clear(void)
0x18000f83e  mov     rdi, [rbp+57h+var_D0]
0x18000f842  mov     rdi, [rdi]
0x18000f845  mov     rsi, [rbp+57h+var_A8]
0x18000f849  cmp     [rdi+19h], r15b
0x18000f84d  jnz     short loc_18000F8C7
0x18000f84f  mov     rbx, [rdi+20h]
0x18000f853  mov     [rbp+57h+var_B0], rbx
0x18000f857  lea     rcx, [rbp+57h+var_B0]
0x18000f85b  call    ?InternalAddRef@?$ComPtr@UIUserInputType@UX@Networking@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Networking::UX::IUserInputType>::InternalAddRef(void)
0x18000f860  mov     [rbp+57h+var_C0], rbx
0x18000f864  lea     rcx, [rbp+57h+var_C0]
0x18000f868  call    ?InternalAddRef@?$ComPtr@UIUserInputType@UX@Networking@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Networking::UX::IUserInputType>::InternalAddRef(void)
0x18000f86d  lea     rdx, [rbp+57h+var_C0]
0x18000f871  mov     rcx, rsi
0x18000f874  call    ?_SubmitThreadpoolInvoke@MBCategory@Internal@UX@Networking@Windows@@AEAAJV?$ComPtr@UIMbConnectionProfile@UX@Networking@Windows@@@WRL@Microsoft@@@Z; Windows::Networking::UX::Internal::MBCategory::_SubmitThreadpoolInvoke(Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>)
0x18000f879  lea     rcx, [rbp+57h+var_B0]
0x18000f87d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000f882  mov     rcx, [rdi+10h]
0x18000f886  cmp     [rcx+19h], r15b
0x18000f88a  jz      short loc_18000F8AA
0x18000f88c  mov     rax, [rdi+8]
0x18000f890  jmp     short loc_18000F89F
0x18000f892  cmp     rdi, [rax+10h]
0x18000f896  jnz     short loc_18000F8A5
0x18000f898  mov     rdi, rax
0x18000f89b  mov     rax, [rax+8]
0x18000f89f  cmp     [rax+19h], r15b
0x18000f8a3  jz      short loc_18000F892
0x18000f8a5  mov     rdi, rax
0x18000f8a8  jmp     short loc_18000F849
0x18000f8aa  mov     rdi, rcx
0x18000f8ad  mov     rcx, [rcx]
0x18000f8b0  cmp     [rcx+19h], r15b
0x18000f8b4  jnz     short loc_18000F849
0x18000f8b6  mov     rdi, rcx
0x18000f8b9  mov     rax, [rcx]
0x18000f8bc  mov     rcx, rax
0x18000f8bf  cmp     [rax+19h], r15b
0x18000f8c3  jz      short loc_18000F8B6
0x18000f8c5  jmp     short loc_18000F849
0x18000f8c7  mov     r8, [rbp+57h+var_D0]
0x18000f8cb  mov     r8, [r8+8]
0x18000f8cf  lea     rdx, [rbp+57h+var_D0]
0x18000f8d3  lea     rcx, [rbp+57h+var_D0]
0x18000f8d7  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@V?$ComPtr@UIMbConnectionProfile@UX@Networking@Windows@@@WRL@Microsoft@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@V?$ComPtr@UIMbConnectionProfile@UX@Networking@Windows@@@WRL@Microsoft@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@V?$ComPtr@UIMbConnectionProfile@UX@Networking@Windows@@@WRL@Microsoft@@PEAX@std@@@1@PEAU?$_Tree_node@V?$ComPtr@UIMbConnectionProfile@UX@Networking@Windows@@@WRL@Microsoft@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>>>::_Erase_tree<std::allocator<std::_Tree_node<Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>,void *>>>(std::allocator<std::_Tree_node<Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>,void *>> &,std::_Tree_node<Microsoft::WRL::ComPtr<Windows::Networking::UX::IMbConnectionProfile>,void *> *)
0x18000f8dc  mov     edx, 28h ; '('
0x18000f8e1  mov     rcx, [rbp+57h+var_D0]
0x18000f8e5  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000f8ea  mov     rcx, [rbp+57h+var_50]
0x18000f8ee  xor     rcx, rsp; StackCookie
0x18000f8f1  call    __security_check_cookie
0x18000f8f6  add     rsp, 0B8h
0x18000f8fd  pop     r15
0x18000f8ff  pop     r14
0x18000f901  pop     r13
0x18000f903  pop     r12
0x18000f905  pop     rdi
0x18000f906  pop     rsi
0x18000f907  pop     rbx
0x18000f908  pop     rbp
0x18000f909  retn
```
