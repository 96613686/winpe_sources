# UsageAndQualityInsights::Configuration::ConfigStore::AreNewConfigsAvailable(void)

- ea: `0x1800e65d4`
- end: `0x1800e6bb0`
- name: `?AreNewConfigsAvailable@ConfigStore@Configuration@UsageAndQualityInsights@@QEBA_NXZ`
- size: `1500`
- prototype: `bool __fastcall(UsageAndQualityInsights::Configuration::ConfigStore *__hidden this)`
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800e75bc`

## callees

- `0x1800033d0`
- `0x180003870`
- `0x1800038b8`
- `0x18000d9d4`
- `0x18000eee0`
- `0x180012dd4`
- `0x180013ff8`
- `0x180020650`
- `0x18002c4a0`
- `0x1800349f0`
- `0x180034f1c`
- `0x180036e34`
- `0x180039814`
- `0x1800e2d2c`
- `0x1800e2f0c`
- `0x1800e37c8`
- `0x1800e3c8c`
- `0x1800e3e50`
- `0x1800e4d1c`
- `0x1800e5f5c`
- `0x1800e65d4`
- `0x180108010`

## string_xrefs

- `0x1800e66ce`: `{}_V{}.json`
- `0x1800e6829`: `.json`
- `0x1800e6899`: `onecore\base\usageandqualityinsights\service\lib\configuration\configstore.cpp`
- `0x1800e6883`: `Config file is not a JSON file`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
bool __fastcall UsageAndQualityInsights::Configuration::ConfigStore::AreNewConfigsAvailable(
        UsageAndQualityInsights::Configuration::ConfigStore *this)
{
  int v2; // edi
  _QWORD *v3; // rax
  __int64 *v4; // rbx
  __int64 *v5; // r12
  bool v6; // si
  std::_Format_arg_index *v7; // r14
  __int64 v8; // r15
  __int64 *v9; // rax
  _QWORD *v10; // rdx
  __int64 v11; // r8
  int v12; // edi
  volatile signed __int32 *v13; // rbx
  std::filesystem::directory_entry *v14; // rbx
  int v15; // edi
  char *v16; // r14
  __int64 v17; // rax
  int v18; // edi
  bool v19; // zf
  char v20; // al
  unsigned int v21; // edi
  __int64 v22; // rax
  int v23; // edi
  __int128 *p_Src; // rdx
  __int64 v25; // r9
  unsigned __int64 i; // rcx
  bool v27; // bl
  __int64 v28; // rax
  _QWORD *v29; // rdx
  __int64 v30; // r14
  unsigned __int64 j; // rcx
  _QWORD *v32; // rbx
  __int64 v33; // rcx
  __int64 v34; // rdx
  _QWORD *v35; // rax
  __int64 v36; // rdx
  volatile signed __int32 *v37; // rbx
  volatile signed __int32 *v38; // rbx
  volatile signed __int32 *v39; // rbx
  volatile signed __int32 *v40; // rbx
  int v42; // [rsp+20h] [rbp-E0h]
  char *v43[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v44; // [rsp+40h] [rbp-C0h]
  std::filesystem::directory_entry *v45[2]; // [rsp+50h] [rbp-B0h] BYREF
  int v46; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD *v47; // [rsp+68h] [rbp-98h] BYREF
  __int64 v48; // [rsp+70h] [rbp-90h]
  __int64 v49; // [rsp+78h] [rbp-88h] BYREF
  __int128 v50; // [rsp+80h] [rbp-80h]
  __int64 v51; // [rsp+90h] [rbp-70h]
  __int64 v52; // [rsp+98h] [rbp-68h]
  __int128 v53; // [rsp+A0h] [rbp-60h] BYREF
  char v54[16]; // [rsp+B0h] [rbp-50h] BYREF
  __int128 Src; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v56; // [rsp+D0h] [rbp-30h]
  unsigned __int64 v57; // [rsp+D8h] [rbp-28h]
  _QWORD v58[4]; // [rsp+E0h] [rbp-20h] BYREF
  int v59; // [rsp+100h] [rbp+0h]
  __int128 v60; // [rsp+108h] [rbp+8h] BYREF
  __int64 v61; // [rsp+118h] [rbp+18h]
  __int64 v62; // [rsp+120h] [rbp+20h]
  _QWORD v63[2]; // [rsp+128h] [rbp+28h] BYREF
  __int64 v64; // [rsp+138h] [rbp+38h]
  unsigned __int64 v65; // [rsp+140h] [rbp+40h]
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]

  v2 = 0;
  LODWORD(v44) = 0;
  v48 = 0;
  v3 = operator new(0x30u);
  *v3 = v3;
  v3[1] = v3;
  v47 = v3;
  v49 = 0;
  v50 = 0;
  v51 = 7;
  v52 = 8;
  v46 = 1065353216;
  std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Assign_grow(
    &v49,
    16,
    v3);
  v4 = (__int64 *)*((_QWORD *)this + 21);
  v5 = (__int64 *)*((_QWORD *)this + 22);
  v6 = 1;
  while ( v4 != v5 )
  {
    v7 = (std::_Format_arg_index *)v58;
    v8 = 2;
    do
    {
      std::_Format_arg_index::_Format_arg_index(v7);
      v7 = (std::_Format_arg_index *)((char *)v7 + 8);
      --v8;
    }
    while ( v8 );
    if ( (unsigned __int64)v4[3] <= 7 )
      v9 = v4;
    else
      v9 = (__int64 *)*v4;
    v58[2] = v9;
    v58[3] = v4[2];
    v58[0] = 0xC000000000000000uLL;
    v59 = *((_DWORD *)v4 + 8);
    v58[1] = 0x2000000000000010LL;
    v45[0] = (std::filesystem::directory_entry *)L"{}_V{}.json";
    v45[1] = (std::filesystem::directory_entry *)11;
    v43[0] = (char *)2;
    v43[1] = (char *)v58;
    v44 = *(_OWORD *)v45;
    std::vformat<0>(&Src);
    v2 |= 4u;
    std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::emplace<std::wstring>(
      &v46,
      &v53,
      &Src);
    std::wstring::~wstring(&Src);
    v4 += 9;
  }
  v10 = (_QWORD *)((char *)this + 40);
  v11 = *((_QWORD *)this + 7);
  if ( *((_QWORD *)this + 8) > 7u )
    v10 = (_QWORD *)*v10;
  v60 = 0;
  v61 = 0;
  v62 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v60, v10, v11);
  v12 = v2 | 0x18;
  std::filesystem::directory_iterator::directory_iterator(
    (std::filesystem::directory_iterator *)v43,
    (const struct std::filesystem::path *)&v60);
  std::wstring::~wstring(&v60);
  v13 = (volatile signed __int32 *)v43[1];
  if ( v43[1] )
  {
    _InterlockedAdd((volatile signed __int32 *)v43[1] + 2, 1u);
    v13 = (volatile signed __int32 *)v43[1];
  }
  *(_OWORD *)v45 = *(_OWORD *)v43;
  if ( v13 )
  {
    _InterlockedAdd(v13 + 2, 1u);
    v13 = (volatile signed __int32 *)v43[1];
  }
  v53 = 0;
  if ( v13 )
  {
    if ( _InterlockedExchangeAdd(v13 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
      if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
    }
  }
  while ( 1 )
  {
    v14 = v45[0];
    if ( !v45[0] )
      break;
    Src = 0;
    v56 = 0;
    v57 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&Src, L".json", 5);
    v15 = v12 | 0x61;
    LODWORD(v44) = v15;
    v16 = (char *)v14 + 32;
    v17 = std::filesystem::path::extension((char *)v14 + 32, v58);
    v18 = v15 | 2;
    LODWORD(v44) = v18;
    if ( (unsigned int)std::filesystem::path::compare(v17, &Src)
      || (v19 = !std::filesystem::directory_entry::is_regular_file(v14), v20 = 0, v19) )
    {
      v20 = 1;
    }
    LOBYTE(v42) = v20;
    wil::details::in1diag3::Throw_HrIfMsg(
      retaddr,
      (void *)0x6A,
      (unsigned int)"onecore\\base\\usageandqualityinsights\\service\\lib\\configuration\\configstore.cpp",
      (const char *)0x80070057LL,
      v42,
      (bool)"Config file is not a JSON file",
      v43[0]);
    v21 = v18 & 0xFFFFFFFD;
    std::wstring::~wstring(v58);
    if ( (v21 & 1) != 0 )
    {
      v21 &= ~1u;
      std::wstring::~wstring(&Src);
    }
    v22 = std::filesystem::path::filename((char *)v14 + 32, v58);
    std::wstring::wstring(&Src, v22);
    v23 = v21 | 0x80;
    p_Src = &Src;
    if ( v57 > 7 )
      p_Src = (__int128 *)Src;
    v25 = 0xCBF29CE484222325uLL;
    for ( i = 0; i < 2 * v56; ++i )
      v25 = 0x100000001B3LL * (*((unsigned __int8 *)p_Src + i) ^ (unsigned __int64)v25);
    v27 = *(_QWORD *)(std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Find_last<std::wstring>(
                        &v46,
                        v54,
                        &Src,
                        v25)
                    + 8) == 0;
    std::wstring::~wstring(&Src);
    std::wstring::~wstring(v58);
    if ( v27 )
    {
      v37 = (volatile signed __int32 *)v45[1];
      if ( v45[1] )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v45[1] + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v37)(v37);
          if ( _InterlockedExchangeAdd(v37 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v37 + 8LL))(v37);
        }
      }
      v38 = (volatile signed __int32 *)v43[1];
      if ( v43[1] )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v43[1] + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v38)(v38);
          if ( _InterlockedExchangeAdd(v38 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v38 + 8LL))(v38);
        }
      }
      goto LABEL_61;
    }
    v28 = std::filesystem::path::filename(v16, v58);
    std::wstring::wstring(v63, v28);
    v12 = v23 | 0x100;
    v29 = v63;
    if ( v65 > 7 )
      v29 = (_QWORD *)v63[0];
    v30 = 0xCBF29CE484222325uLL;
    for ( j = 0; j < 2 * v64; ++j )
      v30 = 0x100000001B3LL * (*((unsigned __int8 *)v29 + j) ^ (unsigned __int64)v30);
    v32 = *(_QWORD **)(std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Find_last<std::wstring>(
                         &v46,
                         &v60,
                         v63,
                         v30)
                     + 8);
    if ( v32 )
    {
      v33 = 2 * (v30 & v51);
      v34 = v49;
      if ( *(_QWORD **)(v49 + 16 * (v30 & v51) + 8) == v32 )
      {
        if ( *(_QWORD **)(v49 + 16 * (v30 & v51)) == v32 )
        {
          v35 = v47;
          *(_QWORD *)(v49 + 16 * (v30 & v51)) = v47;
        }
        else
        {
          v35 = (_QWORD *)v32[1];
        }
        *(_QWORD *)(v34 + 8 * v33 + 8) = v35;
      }
      else if ( *(_QWORD **)(v49 + 16 * (v30 & v51)) == v32 )
      {
        *(_QWORD *)(v49 + 16 * (v30 & v51)) = *v32;
      }
      v36 = *v32;
      --v48;
      *(_QWORD *)v32[1] = v36;
      *(_QWORD *)(v36 + 8) = v32[1];
      std::wstring::~wstring(v32 + 2);
      operator delete(v32, 0x30u);
    }
    std::wstring::~wstring(v63);
    std::wstring::~wstring(v58);
    std::filesystem::directory_iterator::operator++(v45);
  }
  v39 = (volatile signed __int32 *)v45[1];
  if ( v45[1] )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v45[1] + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v39)(v39);
      if ( _InterlockedExchangeAdd(v39 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v39 + 8LL))(v39);
    }
  }
  v40 = (volatile signed __int32 *)v43[1];
  if ( v43[1] )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v43[1] + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v40)(v40);
      if ( _InterlockedExchangeAdd(v40 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v40 + 8LL))(v40);
    }
  }
  v6 = v48 != 0;
LABEL_61:
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<UsageAndQualityInsights::Database::FactTableName const,UsageAndQualityInsights::Facts::FactView>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<UsageAndQualityInsights::Database::FactTableName const,UsageAndQualityInsights::Facts::FactView>>>>>>(&v49);
  std::list<std::wstring>::~list<std::wstring>(&v47);
  return v6;
}

```

## disassembly

```asm
0x1800e65d4  push    rbp
0x1800e65d6  push    rbx
0x1800e65d7  push    rsi
0x1800e65d8  push    rdi
0x1800e65d9  push    r12
0x1800e65db  push    r13
0x1800e65dd  push    r14
0x1800e65df  push    r15
0x1800e65e1  lea     rbp, [rsp-58h]
0x1800e65e6  sub     rsp, 158h
0x1800e65ed  mov     rax, cs:__security_cookie
0x1800e65f4  xor     rax, rsp
0x1800e65f7  mov     [rbp+90h+var_48], rax
0x1800e65fb  mov     r13, rcx
0x1800e65fe  xor     ebx, ebx
0x1800e6600  mov     edi, ebx
0x1800e6602  mov     dword ptr [rsp+190h+var_150], ebx
0x1800e6606  mov     [rsp+190h+var_130], ebx
0x1800e660a  mov     [rsp+190h+var_128], rbx
0x1800e660f  mov     [rsp+190h+var_120], rbx
0x1800e6614  lea     ecx, [rbx+30h]; Size
0x1800e6617  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800e661c  mov     [rax], rax
0x1800e661f  mov     [rax+8], rax
0x1800e6623  mov     [rsp+190h+var_128], rax
0x1800e6628  mov     [rsp+190h+var_118], rbx
0x1800e662d  xorps   xmm0, xmm0
0x1800e6630  movdqa  [rbp+90h+var_110], xmm0
0x1800e6635  mov     [rbp+90h+var_100], 7
0x1800e663d  mov     [rbp+90h+var_F8], 8
0x1800e6645  mov     [rsp+190h+var_130], 3F800000h
0x1800e664d  mov     r8, rax
0x1800e6650  lea     edx, [rbx+10h]
0x1800e6653  lea     rcx, [rsp+190h+var_118]
0x1800e6658  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>)
0x1800e665d  nop
0x1800e665e  mov     rbx, [r13+0A8h]
0x1800e6665  mov     r12, [r13+0B0h]
0x1800e666c  mov     esi, 1
0x1800e6671  jmp     loc_1800E6736
0x1800e6676  lea     r14, [rbp+90h+var_B0]
0x1800e667a  mov     r15d, 2
0x1800e6680  mov     rcx, r14; this
0x1800e6683  call    ??0_Format_arg_index@std@@QEAA@XZ; std::_Format_arg_index::_Format_arg_index(void)
0x1800e6688  add     r14, 8
0x1800e668c  sub     r15, rsi
0x1800e668f  jnz     short loc_1800E6680
0x1800e6691  cmp     qword ptr [rbx+18h], 7
0x1800e6696  jbe     short loc_1800E669D
0x1800e6698  mov     rax, [rbx]
0x1800e669b  jmp     short loc_1800E66A0
0x1800e669d  mov     rax, rbx
0x1800e66a0  mov     [rbp+90h+var_A0], rax
0x1800e66a4  mov     rax, [rbx+10h]
0x1800e66a8  mov     [rbp+90h+var_98], rax
0x1800e66ac  mov     rax, 0C000000000000000h
0x1800e66b6  mov     [rbp+90h+var_B0], rax
0x1800e66ba  mov     eax, [rbx+20h]
0x1800e66bd  mov     [rbp+90h+var_90], eax
0x1800e66c0  mov     rax, 2000000000000010h
0x1800e66ca  mov     [rbp+90h+var_A8], rax
0x1800e66ce  lea     rax, aVJson; "{}_V{}.json"
0x1800e66d5  mov     [rsp+190h+var_140], rax
0x1800e66da  mov     [rsp+190h+var_140+8], 0Bh
0x1800e66e3  mov     [rsp+190h+var_160], 2; char *
0x1800e66ec  lea     rax, [rbp+90h+var_B0]
0x1800e66f0  mov     [rsp+190h+var_160+8], rax
0x1800e66f5  movaps  xmm0, xmmword ptr [rsp+190h+var_140]
0x1800e66fa  movdqa  [rsp+190h+var_150], xmm0
0x1800e6700  lea     r8, [rsp+190h+var_160]
0x1800e6705  lea     rdx, [rsp+190h+var_150]
0x1800e670a  lea     rcx, [rbp+90h+Src]; Src
0x1800e670e  call    ??$vformat@$0A@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@V?$basic_string_view@_WU?$char_traits@_W@std@@@0@V?$basic_format_args@V?$basic_format_context@V?$back_insert_iterator@V?$_Fmt_buffer@_W@std@@@std@@_W@std@@@0@@Z; std::vformat<0>(std::wstring_view,std::basic_format_args<std::basic_format_context<std::back_insert_iterator<std::_Fmt_buffer<wchar_t>>,wchar_t>>)
0x1800e6713  or      edi, 4
0x1800e6716  lea     r8, [rbp+90h+Src]
0x1800e671a  lea     rdx, [rbp+90h+var_F0]
0x1800e671e  lea     rcx, [rsp+190h+var_130]
0x1800e6723  call    ??$emplace@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Hash@V?$_Uset_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@@std@@_N@1@$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::emplace<std::wstring>(std::wstring &&)
0x1800e6728  nop
0x1800e6729  lea     rcx, [rbp+90h+Src]; void *
0x1800e672d  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800e6732  add     rbx, 48h ; 'H'
0x1800e6736  cmp     rbx, r12
0x1800e6739  jnz     loc_1800E6676
0x1800e673f  lea     rdx, [r13+28h]
0x1800e6743  mov     r8, [rdx+10h]
0x1800e6747  cmp     qword ptr [rdx+18h], 7
0x1800e674c  jbe     short loc_1800E6751
0x1800e674e  mov     rdx, [rdx]
0x1800e6751  xorps   xmm0, xmm0
0x1800e6754  movups  [rbp+90h+var_88], xmm0
0x1800e6758  xor     r12d, r12d
0x1800e675b  mov     [rbp+90h+var_78], r12
0x1800e675f  mov     [rbp+90h+var_70], r12
0x1800e6763  lea     rcx, [rbp+90h+var_88]
0x1800e6767  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800e676c  or      edi, 18h
0x1800e676f  lea     rdx, [rbp+90h+var_88]; struct std::filesystem::path *
0x1800e6773  lea     rcx, [rsp+190h+var_160]; this
0x1800e6778  call    ??0directory_iterator@filesystem@std@@QEAA@AEBVpath@12@@Z; std::filesystem::directory_iterator::directory_iterator(std::filesystem::path const &)
0x1800e677d  nop
0x1800e677e  lea     rcx, [rbp+90h+var_88]; void *
0x1800e6782  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800e6787  mov     rbx, [rsp+190h+var_160+8]
0x1800e678c  test    rbx, rbx
0x1800e678f  jz      short loc_1800E679A
0x1800e6791  lock add [rbx+8], esi
0x1800e6795  mov     rbx, [rsp+190h+var_160+8]
0x1800e679a  movaps  xmm0, xmmword ptr [rsp+190h+var_160]
0x1800e679f  movdqa  xmmword ptr [rsp+190h+var_140], xmm0
0x1800e67a5  test    rbx, rbx
0x1800e67a8  jz      short loc_1800E67B3
0x1800e67aa  lock add [rbx+8], esi
0x1800e67ae  mov     rbx, [rsp+190h+var_160+8]
0x1800e67b3  xorps   xmm1, xmm1
0x1800e67b6  movdqu  [rbp+90h+var_F0], xmm1
0x1800e67bb  or      r15d, 0FFFFFFFFh
0x1800e67bf  test    rbx, rbx
0x1800e67c2  jz      short loc_1800E67FC
0x1800e67c4  mov     eax, r15d
0x1800e67c7  lock xadd [rbx+8], eax
0x1800e67cc  add     eax, r15d
0x1800e67cf  jnz     short loc_1800E67FC
0x1800e67d1  mov     rax, [rbx]
0x1800e67d4  mov     rcx, rbx
0x1800e67d7  mov     rax, [rax]
0x1800e67da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e67df  mov     eax, r15d
0x1800e67e2  lock xadd [rbx+0Ch], eax
0x1800e67e7  add     eax, r15d
0x1800e67ea  jnz     short loc_1800E67FC
0x1800e67ec  mov     rax, [rbx]
0x1800e67ef  mov     rcx, rbx
0x1800e67f2  mov     rax, [rax+8]
0x1800e67f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e67fb  nop
0x1800e67fc  mov     r13, 100000001B3h
0x1800e6806  mov     rbx, [rsp+190h+var_140]
0x1800e680b  test    rbx, rbx
0x1800e680e  jz      loc_1800E6AED
0x1800e6814  xorps   xmm0, xmm0
0x1800e6817  movups  [rbp+90h+Src], xmm0
0x1800e681b  mov     [rbp+90h+var_C0], r12
0x1800e681f  mov     [rbp+90h+var_B8], r12
0x1800e6823  mov     r8d, 5
0x1800e6829  lea     rdx, aJson_0; ".json"
0x1800e6830  lea     rcx, [rbp+90h+Src]
0x1800e6834  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800e6839  or      edi, 60h
0x1800e683c  or      edi, esi
0x1800e683e  mov     dword ptr [rsp+190h+var_150], edi
0x1800e6842  lea     r14, [rbx+20h]
0x1800e6846  lea     rdx, [rbp+90h+var_B0]
0x1800e684a  mov     rcx, r14
0x1800e684d  call    ?extension@path@filesystem@std@@QEBA?AV123@XZ; std::filesystem::path::extension(void)
0x1800e6852  nop
0x1800e6853  or      edi, 2
0x1800e6856  mov     dword ptr [rsp+190h+var_150], edi
0x1800e685a  lea     rdx, [rbp+90h+Src]
0x1800e685e  mov     rcx, rax
0x1800e6861  call    ?compare@path@filesystem@std@@QEBAHAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@3@@Z; std::filesystem::path::compare(std::wstring const &)
0x1800e6866  test    eax, eax
0x1800e6868  jnz     short loc_1800E6879
0x1800e686a  mov     rcx, rbx; this
0x1800e686d  call    ?is_regular_file@directory_entry@filesystem@std@@QEBA_NXZ; std::filesystem::directory_entry::is_regular_file(void)
0x1800e6872  test    al, al
0x1800e6874  mov     al, r12b
0x1800e6877  jnz     short loc_1800E687C
0x1800e6879  mov     al, sil
0x1800e687c  mov     rcx, [rbp+98h]; this
0x1800e6883  lea     rdx, aConfigFileIsNo; "Config file is not a JSON file"
0x1800e688a  mov     qword ptr [rsp+190h+var_168], rdx; bool
0x1800e688f  mov     byte ptr [rsp+190h+var_170], al; int
0x1800e6893  mov     r9d, 80070057h; char *
0x1800e6899  lea     r8, aOnecoreBaseUsa_17; "onecore\\base\\usageandqualityinsights"...
0x1800e68a0  mov     edx, 6Ah ; 'j'; void *
0x1800e68a5  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1800e68aa  nop
0x1800e68ab  and     edi, 0FFFFFFFDh
0x1800e68ae  lea     rcx, [rbp+90h+var_B0]; void *
0x1800e68b2  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800e68b7  nop
0x1800e68b8  test    sil, dil
0x1800e68bb  jz      short loc_1800E68C9
0x1800e68bd  and     edi, 0FFFFFFFEh
0x1800e68c0  lea     rcx, [rbp+90h+Src]; void *
0x1800e68c4  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800e68c9  lea     rdx, [rbp+90h+var_B0]
0x1800e68cd  mov     rcx, r14
0x1800e68d0  call    ?filename@path@filesystem@std@@QEBA?AV123@XZ; std::filesystem::path::filename(void)
0x1800e68d5  nop
0x1800e68d6  mov     rdx, rax
0x1800e68d9  lea     rcx, [rbp+90h+Src]
0x1800e68dd  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800e68e2  bts     edi, 7
0x1800e68e6  mov     rax, [rbp+90h+var_C0]
0x1800e68ea  lea     rdx, [rbp+90h+Src]
0x1800e68ee  cmp     [rbp+90h+var_B8], 7
0x1800e68f3  cmova   rdx, qword ptr [rbp+90h+Src]
0x1800e68f8  mov     r9, 0CBF29CE484222325h
0x1800e6902  lea     r8, [rax+rax]
0x1800e6906  mov     rcx, r12
0x1800e6909  test    r8, r8
0x1800e690c  jz      short loc_1800E6921
0x1800e690e  movzx   eax, byte ptr [rcx+rdx]
0x1800e6912  xor     r9, rax
0x1800e6915  imul    r9, r13
0x1800e6919  add     rcx, rsi
0x1800e691c  cmp     rcx, r8
0x1800e691f  jb      short loc_1800E690E
0x1800e6921  lea     r8, [rbp+90h+Src]
0x1800e6925  lea     rdx, [rbp+90h+var_E0]
0x1800e6929  lea     rcx, [rsp+190h+var_130]
0x1800e692e  call    ??$_Find_last@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Hash@V?$_Uset_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAX@std@@@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@_K@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x1800e6933  cmp     [rax+8], r12
0x1800e6937  setz    bl
0x1800e693a  lea     rcx, [rbp+90h+Src]; void *
0x1800e693e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800e6943  nop
0x1800e6944  lea     rcx, [rbp+90h+var_B0]; void *
0x1800e6948  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800e694d  test    bl, bl
0x1800e694f  jnz     loc_1800E6A59
0x1800e6955  lea     rdx, [rbp+90h+var_B0]
0x1800e6959  mov     rcx, r14
0x1800e695c  call    ?filename@path@filesystem@std@@QEBA?AV123@XZ; std::filesystem::path::filename(void)
0x1800e6961  nop
0x1800e6962  mov     rdx, rax
0x1800e6965  lea     rcx, [rbp+90h+var_68]
0x1800e6969  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800e696e  bts     edi, 8
0x1800e6972  mov     rax, [rbp+90h+var_58]
0x1800e6976  lea     rdx, [rbp+90h+var_68]
0x1800e697a  cmp     [rbp+90h+var_50], 7
0x1800e697f  cmova   rdx, [rbp+90h+var_68]
0x1800e6984  mov     r14, 0CBF29CE484222325h
0x1800e698e  lea     r8, [rax+rax]
0x1800e6992  mov     rcx, r12
0x1800e6995  test    r8, r8
0x1800e6998  jz      short loc_1800E69AD
0x1800e699a  movzx   eax, byte ptr [rcx+rdx]
0x1800e699e  xor     r14, rax
0x1800e69a1  imul    r14, r13
0x1800e69a5  add     rcx, rsi
0x1800e69a8  cmp     rcx, r8
0x1800e69ab  jb      short loc_1800E699A
0x1800e69ad  mov     r9, r14
0x1800e69b0  lea     r8, [rbp+90h+var_68]
0x1800e69b4  lea     rdx, [rbp+90h+var_88]
0x1800e69b8  lea     rcx, [rsp+190h+var_130]
0x1800e69bd  call    ??$_Find_last@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Hash@V?$_Uset_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAX@std@@@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@_K@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x1800e69c2  mov     rbx, [rax+8]
0x1800e69c6  test    rbx, rbx
0x1800e69c9  jz      short loc_1800E6A37
0x1800e69cb  mov     rcx, [rbp+90h+var_100]
0x1800e69cf  and     rcx, r14
0x1800e69d2  add     rcx, rcx
0x1800e69d5  mov     rdx, [rsp+190h+var_118]
0x1800e69da  cmp     [rdx+rcx*8+8], rbx
0x1800e69df  jnz     short loc_1800E69FD
0x1800e69e1  cmp     [rdx+rcx*8], rbx
0x1800e69e5  jnz     short loc_1800E69F2
0x1800e69e7  mov     rax, [rsp+190h+var_128]
0x1800e69ec  mov     [rdx+rcx*8], rax
0x1800e69f0  jmp     short loc_1800E69F6
0x1800e69f2  mov     rax, [rbx+8]
0x1800e69f6  mov     [rdx+rcx*8+8], rax
0x1800e69fb  jmp     short loc_1800E6A0A
0x1800e69fd  cmp     [rdx+rcx*8], rbx
0x1800e6a01  jnz     short loc_1800E6A0A
0x1800e6a03  mov     rax, [rbx]
0x1800e6a06  mov     [rdx+rcx*8], rax
0x1800e6a0a  mov     rdx, [rbx]
0x1800e6a0d  sub     [rsp+190h+var_120], rsi
0x1800e6a12  mov     rax, [rbx+8]
0x1800e6a16  mov     [rax], rdx
0x1800e6a19  mov     rax, [rbx+8]
0x1800e6a1d  mov     [rdx+8], rax
0x1800e6a21  lea     rcx, [rbx+10h]; void *
0x1800e6a25  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800e6a2a  mov     edx, 30h ; '0'; unsigned __int64
0x1800e6a2f  mov     rcx, rbx; void *
0x1800e6a32  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800e6a37  lea     rcx, [rbp+90h+var_68]; void *
0x1800e6a3b  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800e6a40  nop
0x1800e6a41  lea     rcx, [rbp+90h+var_B0]; void *
0x1800e6a45  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800e6a4a  lea     rcx, [rsp+190h+var_140]
0x1800e6a4f  call    ??Edirectory_iterator@filesystem@std@@QEAAAEAV012@XZ; std::filesystem::directory_iterator::operator++(void)
0x1800e6a54  jmp     loc_1800E6806
0x1800e6a59  mov     rbx, [rsp+190h+var_140+8]
0x1800e6a5e  test    rbx, rbx
0x1800e6a61  jz      short loc_1800E6A9B
0x1800e6a63  mov     eax, r15d
0x1800e6a66  lock xadd [rbx+8], eax
0x1800e6a6b  add     eax, r15d
0x1800e6a6e  jnz     short loc_1800E6A9B
0x1800e6a70  mov     rax, [rbx]
0x1800e6a73  mov     rcx, rbx
  ... truncated ...
```
