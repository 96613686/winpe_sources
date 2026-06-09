# FilterAgentArrayFactory::CreateFilterAgentArray(ushort,std::unordered_map<FilterType,std::unique_ptr<std::vector<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>,std::allocator<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>>>,std::default_delete<std::vector<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>,std::allocator<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>>>>>,std::hash<FilterType>,std::equal_to<FilterType>,std::allocator<std::pair<FilterType const,std::unique_ptr<std::vector<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>,std::allocator<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>>>,std::default_delete<std::vector<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>,std::allocator<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>>>>>>>> &)

- ea: `0x1800104e4`
- end: `0x180010944`
- name: `?CreateFilterAgentArray@FilterAgentArrayFactory@@SAJGAEAV?$unordered_map@W4FilterType@@V?$unique_ptr@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@U?$default_delete@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@@2@@std@@U?$hash@W4FilterType@@@3@U?$equal_to@W4FilterType@@@3@V?$allocator@U?$pair@$$CBW4FilterType@@V?$unique_ptr@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@U?$default_delete@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@@2@@std@@@std@@@3@@std@@@Z`
- size: `1120`
- prototype: `__int64 __fastcall(unsigned __int16, __int64 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18000e0a8`

## callees

- `0x180001a30`
- `0x180005ca4`
- `0x18000c794`
- `0x18000dc0c`
- `0x18000eeb8`
- `0x18000ef28`
- `0x18000fe3c`
- `0x1800103ac`
- `0x18001046c`
- `0x1800104e4`
- `0x18001094c`
- `0x1800114c8`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001052e`
- `msvcrt!??3@YAXPEAX@Z` at `0x180010537`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001063c`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800106ae`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001071d`
- `msvcrt!??3@YAXPEAX@Z` at `0x180010734`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001074b`
- `msvcrt!??3@YAXPEAX@Z` at `0x180010762`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001091d`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001052e`
- `msvcrt!??3@YAXPEAX@Z` at `0x180010537`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001063c`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800106ae`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001071d`
- `msvcrt!??3@YAXPEAX@Z` at `0x180010734`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001074b`
- `msvcrt!??3@YAXPEAX@Z` at `0x180010762`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001091d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FilterAgentArrayFactory::CreateFilterAgentArray(unsigned __int16 a1, __int64 *a2)
{
  _QWORD *v4; // rbx
  _QWORD *v5; // rsi
  void *v6; // rdi
  int v7; // eax
  __int64 v8; // r9
  unsigned int v9; // ebx
  const char *v10; // r9
  __int64 result; // rax
  _QWORD *v12; // r14
  _QWORD *v13; // rsi
  _QWORD *v14; // rdi
  FilterAgent **i; // rbx
  __int64 v16; // rdx
  __int64 v17; // rax
  void *v18; // rbx
  __int64 v19; // rdx
  __int64 v20; // rax
  void *v21; // rbx
  __int64 v22; // rdx
  __int64 v23; // rax
  void *v24; // rbx
  char v25; // cl
  _QWORD *v26; // rax
  void *v27; // rax
  FilterAgent *v28; // rcx
  FilterAgent *v29; // rax
  FilterAgent *v30; // r12
  _QWORD *v31; // rax
  void *v32; // rax
  FilterAgent *v33; // rcx
  FilterAgent *v34; // rax
  _QWORD *v35; // rax
  void *v36; // rax
  FilterAgent *v37; // rcx
  FilterAgent *v38; // rax
  int v39; // [rsp+20h] [rbp-78h]
  _QWORD *v40; // [rsp+20h] [rbp-78h]
  char v41[8]; // [rsp+28h] [rbp-70h] BYREF
  void *v42; // [rsp+30h] [rbp-68h]
  _BYTE v43[16]; // [rsp+38h] [rbp-60h] BYREF
  __int128 v44; // [rsp+48h] [rbp-50h] BYREF
  __int64 v45; // [rsp+58h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]
  FilterAgent *v47; // [rsp+B0h] [rbp+18h] BYREF
  _QWORD *v48; // [rsp+B8h] [rbp+20h]

  v4 = *(_QWORD **)*a2;
  *(_QWORD *)*a2 = *a2;
  *(_QWORD *)(*a2 + 8) = *a2;
  a2[1] = 0;
  if ( v4 != (_QWORD *)*a2 )
  {
    do
    {
      v5 = (_QWORD *)*v4;
      v6 = (void *)v4[3];
      if ( v6 )
      {
        std::vector<std::unique_ptr<FilterAgent>>::~vector<std::unique_ptr<FilterAgent>>(v4[3]);
        operator delete(v6);
      }
      operator delete(v4);
      v4 = v5;
    }
    while ( v5 != (_QWORD *)*a2 );
  }
  try
  {
    std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Init(
      a2,
      8);
    v44 = 0;
    v45 = 0;
    v7 = FilterParameterFactory::CreateFilterParameters(a1, &v44);
    v9 = v7;
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA3,
        (unsigned int)"mincore\\textinput\\dev\\mtf\\datasources\\filterds\\lib\\filterfactory.cpp",
        (const char *)(unsigned int)v7,
        v39);
      std::vector<std::unique_ptr<FilterBasicParameter>>::~vector<std::unique_ptr<FilterBasicParameter>>((__int64)&v44);
      return v9;
    }
    v12 = 0;
    v13 = 0;
    v48 = 0;
    v14 = 0;
    v40 = 0;
    for ( i = (FilterAgent **)v44; ; ++i )
    {
      if ( i == *((FilterAgent ***)&v44 + 1) )
      {
        if ( v12 )
        {
          v16 = v12[1];
          if ( *v12 != v16 )
          {
            LOBYTE(v8) = 0;
            std::_Sort_std::unique_ptr_FilterAgent_std::default_delete_FilterAgent________int64__lambda_4e00c4f2fc8604fa547e688629cc8b0c___(
              *v12,
              v16,
              (v16 - *v12) >> 3,
              v8,
              v40);
            v17 = (__int64)v12;
            v12 = 0;
            v41[0] = 1;
            v47 = 0;
            v42 = (void *)v17;
            std::_Hash<std::_Umap_traits<enum FilterType,std::unique_ptr<std::vector<std::unique_ptr<FilterAgent>>>,std::_Uhash_compare<enum FilterType,std::hash<enum FilterType>,std::equal_to<enum FilterType>>,std::allocator<std::pair<enum FilterType const,std::unique_ptr<std::vector<std::unique_ptr<FilterAgent>>>>>,0>>::insert<std::pair<enum FilterType,std::unique_ptr<std::vector<std::unique_ptr<FilterAgent>>>>>(
              (__int64 **)a2,
              (__int64)v43,
              (__int64)v41);
            v18 = v42;
            if ( v42 )
            {
              std::vector<std::unique_ptr<FilterAgent>>::~vector<std::unique_ptr<FilterAgent>>((__int64)v42);
              operator delete(v18);
            }
          }
        }
        if ( v13 )
        {
          v19 = v13[1];
          if ( *v13 != v19 )
          {
            LOBYTE(v8) = 0;
            std::_Sort_std::unique_ptr_FilterAgent_std::default_delete_FilterAgent________int64__lambda_4e00c4f2fc8604fa547e688629cc8b0c___(
              *v13,
              v19,
              (v19 - *v13) >> 3,
              v8,
              v40);
            v20 = (__int64)v13;
            v13 = 0;
            v48 = 0;
            v41[0] = 3;
            v47 = 0;
            v42 = (void *)v20;
            std::_Hash<std::_Umap_traits<enum FilterType,std::unique_ptr<std::vector<std::unique_ptr<FilterAgent>>>,std::_Uhash_compare<enum FilterType,std::hash<enum FilterType>,std::equal_to<enum FilterType>>,std::allocator<std::pair<enum FilterType const,std::unique_ptr<std::vector<std::unique_ptr<FilterAgent>>>>>,0>>::insert<std::pair<enum FilterType,std::unique_ptr<std::vector<std::unique_ptr<FilterAgent>>>>>(
              (__int64 **)a2,
              (__int64)v43,
              (__int64)v41);
            v21 = v42;
            if ( v42 )
            {
              std::vector<std::unique_ptr<FilterAgent>>::~vector<std::unique_ptr<FilterAgent>>((__int64)v42);
              operator delete(v21);
            }
          }
        }
        if ( v14 )
        {
          v22 = v14[1];
          if ( *v14 != v22 )
          {
            LOBYTE(v8) = 0;
            std::_Sort_std::unique_ptr_FilterAgent_std::default_delete_FilterAgent________int64__lambda_4e00c4f2fc8604fa547e688629cc8b0c___(
              *v14,
              v22,
              (v22 - *v14) >> 3,
              v8,
              v40);
            v23 = (__int64)v14;
            v14 = 0;
            v41[0] = 2;
            v47 = 0;
            v42 = (void *)v23;
            std::_Hash<std::_Umap_traits<enum FilterType,std::unique_ptr<std::vector<std::unique_ptr<FilterAgent>>>,std::_Uhash_compare<enum FilterType,std::hash<enum FilterType>,std::equal_to<enum FilterType>>,std::allocator<std::pair<enum FilterType const,std::unique_ptr<std::vector<std::unique_ptr<FilterAgent>>>>>,0>>::insert<std::pair<enum FilterType,std::unique_ptr<std::vector<std::unique_ptr<FilterAgent>>>>>(
              (__int64 **)a2,
              (__int64)v43,
              (__int64)v41);
            v24 = v42;
            if ( v42 )
            {
              std::vector<std::unique_ptr<FilterAgent>>::~vector<std::unique_ptr<FilterAgent>>((__int64)v42);
              operator delete(v24);
            }
          }
        }
        if ( v14 )
        {
          std::vector<std::unique_ptr<FilterAgent>>::~vector<std::unique_ptr<FilterAgent>>((__int64)v14);
          operator delete(v14);
        }
        if ( v13 )
        {
          std::vector<std::unique_ptr<FilterAgent>>::~vector<std::unique_ptr<FilterAgent>>((__int64)v13);
          operator delete(v13);
        }
        if ( v12 )
        {
          std::vector<std::unique_ptr<FilterAgent>>::~vector<std::unique_ptr<FilterAgent>>((__int64)v12);
          operator delete(v12);
        }
        std::vector<std::unique_ptr<FilterBasicParameter>>::~vector<std::unique_ptr<FilterBasicParameter>>((__int64)&v44);
        return 0;
      }
      v25 = *((_BYTE *)*i + 12);
      if ( v25 == 1 )
        break;
      if ( v25 == 3 )
      {
        if ( !v13 )
        {
          v31 = operator new(0x18u);
          if ( v31 )
          {
            *v31 = 0;
            v31[1] = 0;
            v31[2] = 0;
            v13 = v31;
            v48 = v31;
          }
        }
        v32 = operator new(0x18u);
        if ( v32 )
        {
          v33 = *i;
          *i = 0;
          v47 = v33;
          v34 = (FilterAgent *)FilterAgent::FilterAgent((__int64)v32, &v47);
        }
        else
        {
          v34 = 0;
        }
        v47 = v34;
        std::vector<std::unique_ptr<FilterAgent>>::push_back(v13, &v47);
        goto LABEL_37;
      }
      if ( v25 == 2 )
      {
        if ( !v14 )
        {
          v35 = operator new(0x18u);
          if ( v35 )
          {
            *v35 = 0;
            v35[1] = 0;
            v35[2] = 0;
            v14 = v35;
            v40 = v35;
          }
        }
        v36 = operator new(0x18u);
        if ( v36 )
        {
          v37 = *i;
          *i = 0;
          v47 = v37;
          v38 = (FilterAgent *)FilterAgent::FilterAgent((__int64)v36, &v47);
        }
        else
        {
          v38 = 0;
        }
        v47 = v38;
        std::vector<std::unique_ptr<FilterAgent>>::push_back(v14, &v47);
        v30 = v47;
        if ( v47 )
          goto LABEL_54;
      }
LABEL_56:
      ;
    }
    if ( !v12 )
    {
      v26 = operator new(0x18u);
      if ( v26 )
      {
        *v26 = 0;
        v26[1] = 0;
        v26[2] = 0;
        v12 = v26;
      }
    }
    v27 = operator new(0x18u);
    if ( v27 )
    {
      v28 = *i;
      *i = 0;
      v47 = v28;
      v29 = (FilterAgent *)FilterAgent::FilterAgent((__int64)v27, &v47);
    }
    else
    {
      v29 = 0;
    }
    v47 = v29;
    std::vector<std::unique_ptr<FilterAgent>>::push_back(v12, &v47);
LABEL_37:
    v30 = v47;
LABEL_54:
    if ( v30 )
    {
      FilterAgent::~FilterAgent(v30);
      operator delete(v30);
    }
    goto LABEL_56;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xD9,
                           (unsigned int)"mincore\\textinput\\dev\\mtf\\datasources\\filterds\\lib\\filterfactory.cpp",
                           v10);
  }
  return result;
}

```

## disassembly

```asm
0x1800104e4  push    rbx
0x1800104e6  push    rsi
0x1800104e7  push    rdi
0x1800104e8  push    r12
0x1800104ea  push    r13
0x1800104ec  push    r14
0x1800104ee  push    r15
0x1800104f0  sub     rsp, 60h
0x1800104f4  mov     r15, rdx
0x1800104f7  movzx   r14d, cx
0x1800104fb  mov     rax, [rdx]
0x1800104fe  mov     rbx, [rax]
0x180010501  mov     [rax], rax
0x180010504  mov     rax, [rdx]
0x180010507  mov     [rax+8], rax
0x18001050b  xor     r13d, r13d
0x18001050e  mov     [rdx+8], r13
0x180010512  cmp     rbx, [rdx]
0x180010515  jz      short loc_180010545
0x180010517  mov     rsi, [rbx]
0x18001051a  mov     rdi, [rbx+18h]
0x18001051e  test    rdi, rdi
0x180010521  jz      short loc_180010534
0x180010523  mov     rcx, rdi
0x180010526  call    ??1?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<FilterAgent>>::~vector<std::unique_ptr<FilterAgent>>(void)
0x18001052b  mov     rcx, rdi
0x18001052e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180010534  mov     rcx, rbx
0x180010537  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001053d  mov     rbx, rsi
0x180010540  cmp     rsi, [r15]
0x180010543  jnz     short loc_180010517
0x180010545  mov     edx, 8
0x18001054a  mov     rcx, r15
0x18001054d  call    ?_Init@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEAAX_K@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Init(unsigned __int64)
0x180010552  nop
0x180010553  xorps   xmm0, xmm0
0x180010556  movdqu  [rsp+98h+var_50], xmm0
0x18001055c  mov     [rsp+98h+var_40], r13
0x180010561  lea     rdx, [rsp+98h+var_50]
0x180010566  movzx   ecx, r14w
0x18001056a  call    ?CreateFilterParameters@FilterParameterFactory@@SAJGAEAV?$vector@V?$unique_ptr@VFilterBasicParameter@@U?$default_delete@VFilterBasicParameter@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterBasicParameter@@U?$default_delete@VFilterBasicParameter@@@std@@@std@@@2@@std@@@Z; FilterParameterFactory::CreateFilterParameters(ushort,std::vector<std::unique_ptr<FilterBasicParameter>> &)
0x18001056f  mov     ebx, eax
0x180010571  test    eax, eax
0x180010573  jns     short loc_1800105A3
0x180010575  mov     rcx, [rsp+98h]; this
0x18001057d  mov     r9d, eax; char *
0x180010580  lea     r8, aMincoreTextinp_14; "mincore\\textinput\\dev\\mtf\\datasourc"...
0x180010587  mov     edx, 0A3h; void *
0x18001058c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010591  nop
0x180010592  lea     rcx, [rsp+98h+var_50]
0x180010597  call    ??1?$vector@V?$unique_ptr@VFilterBasicParameter@@U?$default_delete@VFilterBasicParameter@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterBasicParameter@@U?$default_delete@VFilterBasicParameter@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<FilterBasicParameter>>::~vector<std::unique_ptr<FilterBasicParameter>>(void)
0x18001059c  mov     eax, ebx
0x18001059e  jmp     loc_180010933
0x1800105a3  mov     r14, r13
0x1800105a6  mov     [rsp+98h+arg_8], r13
0x1800105ae  mov     rsi, r13
0x1800105b1  mov     [rsp+98h+arg_18], r13
0x1800105b9  mov     rdi, r13
0x1800105bc  mov     [rsp+98h+var_78], r13
0x1800105c1  mov     rbx, qword ptr [rsp+98h+var_50]
0x1800105c6  cmp     rbx, qword ptr [rsp+98h+var_50+8]
0x1800105cb  jnz     loc_18001077A
0x1800105d1  test    r14, r14
0x1800105d4  jz      short loc_180010643
0x1800105d6  mov     rdx, [r14+8]
0x1800105da  cmp     [r14], rdx
0x1800105dd  jz      short loc_180010643
0x1800105df  mov     r9b, r13b
0x1800105e2  mov     r8, rdx
0x1800105e5  sub     r8, [r14]
0x1800105e8  sar     r8, 3
0x1800105ec  mov     rcx, [r14]
0x1800105ef  call    std___Sort_std__unique_ptr_FilterAgent_std__default_delete_FilterAgent________int64__lambda_4e00c4f2fc8604fa547e688629cc8b0c___
0x1800105f4  mov     rax, r14
0x1800105f7  mov     r14, r13
0x1800105fa  mov     [rsp+98h+arg_8], r13
0x180010602  mov     [rsp+98h+var_70], 1
0x180010607  mov     [rsp+98h+arg_10], r13
0x18001060f  mov     [rsp+98h+var_68], rax
0x180010614  lea     r8, [rsp+98h+var_70]
0x180010619  lea     rdx, [rsp+98h+var_60]
0x18001061e  mov     rcx, r15
0x180010621  call    ??$insert@U?$pair@W4FilterType@@V?$unique_ptr@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@U?$default_delete@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@@2@@std@@@std@@@?$_Hash@V?$_Umap_traits@W4FilterType@@V?$unique_ptr@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@U?$default_delete@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@@2@@std@@V?$_Uhash_compare@W4FilterType@@U?$hash@W4FilterType@@@std@@U?$equal_to@W4FilterType@@@3@@3@V?$allocator@U?$pair@$$CBW4FilterType@@V?$unique_ptr@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@U?$default_delete@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@@2@@std@@@std@@@3@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBW4FilterType@@V?$unique_ptr@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@U?$default_delete@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@@2@@std@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@W4FilterType@@V?$unique_ptr@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@U?$default_delete@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@@2@@std@@@1@@Z
0x180010626  nop
0x180010627  mov     rbx, [rsp+98h+var_68]
0x18001062c  test    rbx, rbx
0x18001062f  jz      short loc_180010643
0x180010631  mov     rcx, rbx
0x180010634  call    ??1?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<FilterAgent>>::~vector<std::unique_ptr<FilterAgent>>(void)
0x180010639  mov     rcx, rbx
0x18001063c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180010642  nop
0x180010643  test    rsi, rsi
0x180010646  jz      short loc_1800106B5
0x180010648  mov     rdx, [rsi+8]
0x18001064c  cmp     [rsi], rdx
0x18001064f  jz      short loc_1800106B5
0x180010651  mov     r9b, r13b
0x180010654  mov     r8, rdx
0x180010657  sub     r8, [rsi]
0x18001065a  sar     r8, 3
0x18001065e  mov     rcx, [rsi]
0x180010661  call    std___Sort_std__unique_ptr_FilterAgent_std__default_delete_FilterAgent________int64__lambda_4e00c4f2fc8604fa547e688629cc8b0c___
0x180010666  mov     rax, rsi
0x180010669  mov     rsi, r13
0x18001066c  mov     [rsp+98h+arg_18], r13
0x180010674  mov     [rsp+98h+var_70], 3
0x180010679  mov     [rsp+98h+arg_10], r13
0x180010681  mov     [rsp+98h+var_68], rax
0x180010686  lea     r8, [rsp+98h+var_70]
0x18001068b  lea     rdx, [rsp+98h+var_60]
0x180010690  mov     rcx, r15
0x180010693  call    ??$insert@U?$pair@W4FilterType@@V?$unique_ptr@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@U?$default_delete@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@@2@@std@@@std@@@?$_Hash@V?$_Umap_traits@W4FilterType@@V?$unique_ptr@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@U?$default_delete@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@@2@@std@@V?$_Uhash_compare@W4FilterType@@U?$hash@W4FilterType@@@std@@U?$equal_to@W4FilterType@@@3@@3@V?$allocator@U?$pair@$$CBW4FilterType@@V?$unique_ptr@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@U?$default_delete@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@@2@@std@@@std@@@3@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBW4FilterType@@V?$unique_ptr@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@U?$default_delete@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@@2@@std@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@W4FilterType@@V?$unique_ptr@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@U?$default_delete@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@@2@@std@@@1@@Z
0x180010698  nop
0x180010699  mov     rbx, [rsp+98h+var_68]
0x18001069e  test    rbx, rbx
0x1800106a1  jz      short loc_1800106B5
0x1800106a3  mov     rcx, rbx
0x1800106a6  call    ??1?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<FilterAgent>>::~vector<std::unique_ptr<FilterAgent>>(void)
0x1800106ab  mov     rcx, rbx
0x1800106ae  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800106b4  nop
0x1800106b5  test    rdi, rdi
0x1800106b8  jz      short loc_180010724
0x1800106ba  mov     rdx, [rdi+8]
0x1800106be  cmp     [rdi], rdx
0x1800106c1  jz      short loc_180010724
0x1800106c3  mov     r9b, r13b
0x1800106c6  mov     r8, rdx
0x1800106c9  sub     r8, [rdi]
0x1800106cc  sar     r8, 3
0x1800106d0  mov     rcx, [rdi]
0x1800106d3  call    std___Sort_std__unique_ptr_FilterAgent_std__default_delete_FilterAgent________int64__lambda_4e00c4f2fc8604fa547e688629cc8b0c___
0x1800106d8  mov     rax, rdi
0x1800106db  mov     rdi, r13
0x1800106de  mov     [rsp+98h+var_78], r13
0x1800106e3  mov     [rsp+98h+var_70], 2
0x1800106e8  mov     [rsp+98h+arg_10], r13
0x1800106f0  mov     [rsp+98h+var_68], rax
0x1800106f5  lea     r8, [rsp+98h+var_70]
0x1800106fa  lea     rdx, [rsp+98h+var_60]
0x1800106ff  mov     rcx, r15
0x180010702  call    ??$insert@U?$pair@W4FilterType@@V?$unique_ptr@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@U?$default_delete@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@@2@@std@@@std@@@?$_Hash@V?$_Umap_traits@W4FilterType@@V?$unique_ptr@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@U?$default_delete@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@@2@@std@@V?$_Uhash_compare@W4FilterType@@U?$hash@W4FilterType@@@std@@U?$equal_to@W4FilterType@@@3@@3@V?$allocator@U?$pair@$$CBW4FilterType@@V?$unique_ptr@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@U?$default_delete@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@@2@@std@@@std@@@3@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBW4FilterType@@V?$unique_ptr@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@U?$default_delete@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@@2@@std@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@W4FilterType@@V?$unique_ptr@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@U?$default_delete@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@@2@@std@@@1@@Z
0x180010707  nop
0x180010708  mov     rbx, [rsp+98h+var_68]
0x18001070d  test    rbx, rbx
0x180010710  jz      short loc_180010724
0x180010712  mov     rcx, rbx
0x180010715  call    ??1?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<FilterAgent>>::~vector<std::unique_ptr<FilterAgent>>(void)
0x18001071a  mov     rcx, rbx
0x18001071d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180010723  nop
0x180010724  test    rdi, rdi
0x180010727  jz      short loc_18001073B
0x180010729  mov     rcx, rdi
0x18001072c  call    ??1?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<FilterAgent>>::~vector<std::unique_ptr<FilterAgent>>(void)
0x180010731  mov     rcx, rdi
0x180010734  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001073a  nop
0x18001073b  test    rsi, rsi
0x18001073e  jz      short loc_180010752
0x180010740  mov     rcx, rsi
0x180010743  call    ??1?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<FilterAgent>>::~vector<std::unique_ptr<FilterAgent>>(void)
0x180010748  mov     rcx, rsi
0x18001074b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180010751  nop
0x180010752  test    r14, r14
0x180010755  jz      short loc_180010769
0x180010757  mov     rcx, r14
0x18001075a  call    ??1?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<FilterAgent>>::~vector<std::unique_ptr<FilterAgent>>(void)
0x18001075f  mov     rcx, r14
0x180010762  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180010768  nop
0x180010769  lea     rcx, [rsp+98h+var_50]
0x18001076e  call    ??1?$vector@V?$unique_ptr@VFilterBasicParameter@@U?$default_delete@VFilterBasicParameter@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterBasicParameter@@U?$default_delete@VFilterBasicParameter@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<FilterBasicParameter>>::~vector<std::unique_ptr<FilterBasicParameter>>(void)
0x180010773  xor     eax, eax
0x180010775  jmp     loc_180010933
0x18001077a  mov     rax, [rbx]
0x18001077d  mov     cl, [rax+0Ch]
0x180010780  cmp     cl, 1
0x180010783  jnz     loc_18001080A
0x180010789  test    r14, r14
0x18001078c  jnz     short loc_1800107B2
0x18001078e  lea     ecx, [r14+18h]; Size
0x180010792  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010797  test    rax, rax
0x18001079a  jz      short loc_1800107B2
0x18001079c  mov     [rax], r13
0x18001079f  mov     [rax+8], r13
0x1800107a3  mov     [rax+10h], r13
0x1800107a7  mov     r14, rax
0x1800107aa  mov     [rsp+98h+arg_8], rax
0x1800107b2  mov     ecx, 18h; Size
0x1800107b7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800107bc  test    rax, rax
0x1800107bf  jz      short loc_1800107E1
0x1800107c1  mov     rcx, [rbx]
0x1800107c4  mov     [rbx], r13
0x1800107c7  mov     [rsp+98h+arg_10], rcx
0x1800107cf  lea     rdx, [rsp+98h+arg_10]
0x1800107d7  mov     rcx, rax
0x1800107da  call    ??0FilterAgent@@QEAA@V?$unique_ptr@VFilterBasicParameter@@U?$default_delete@VFilterBasicParameter@@@std@@@std@@@Z; FilterAgent::FilterAgent(std::unique_ptr<FilterBasicParameter>)
0x1800107df  jmp     short loc_1800107E4
0x1800107e1  mov     rax, r13
0x1800107e4  mov     [rsp+98h+arg_10], rax
0x1800107ec  lea     rdx, [rsp+98h+arg_10]
0x1800107f4  mov     rcx, r14
0x1800107f7  call    ?push_back@?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@QEAAX$$QEAV?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@2@@Z; std::vector<std::unique_ptr<FilterAgent>>::push_back(std::unique_ptr<FilterAgent> &&)
0x1800107fc  nop
0x1800107fd  mov     r12, [rsp+98h+arg_10]
0x180010805  jmp     loc_18001090D
0x18001080a  cmp     cl, 3
0x18001080d  jnz     short loc_180010887
0x18001080f  test    rsi, rsi
0x180010812  jnz     short loc_180010837
0x180010814  lea     ecx, [rsi+18h]; Size
0x180010817  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001081c  test    rax, rax
0x18001081f  jz      short loc_180010837
0x180010821  mov     [rax], r13
0x180010824  mov     [rax+8], r13
0x180010828  mov     [rax+10h], r13
0x18001082c  mov     rsi, rax
0x18001082f  mov     [rsp+98h+arg_18], rax
0x180010837  mov     ecx, 18h; Size
0x18001083c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010841  test    rax, rax
0x180010844  jz      short loc_180010866
0x180010846  mov     rcx, [rbx]
0x180010849  mov     [rbx], r13
0x18001084c  mov     [rsp+98h+arg_10], rcx
0x180010854  lea     rdx, [rsp+98h+arg_10]
0x18001085c  mov     rcx, rax
0x18001085f  call    ??0FilterAgent@@QEAA@V?$unique_ptr@VFilterBasicParameter@@U?$default_delete@VFilterBasicParameter@@@std@@@std@@@Z; FilterAgent::FilterAgent(std::unique_ptr<FilterBasicParameter>)
0x180010864  jmp     short loc_180010869
0x180010866  mov     rax, r13
0x180010869  mov     [rsp+98h+arg_10], rax
0x180010871  lea     rdx, [rsp+98h+arg_10]
0x180010879  mov     rcx, rsi
0x18001087c  call    ?push_back@?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@QEAAX$$QEAV?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@2@@Z; std::vector<std::unique_ptr<FilterAgent>>::push_back(std::unique_ptr<FilterAgent> &&)
0x180010881  nop
0x180010882  jmp     loc_1800107FD
0x180010887  cmp     cl, 2
0x18001088a  jnz     loc_180010923
0x180010890  test    rdi, rdi
0x180010893  jnz     short loc_1800108B5
0x180010895  lea     ecx, [rdi+18h]; Size
0x180010898  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001089d  test    rax, rax
0x1800108a0  jz      short loc_1800108B5
0x1800108a2  mov     [rax], r13
0x1800108a5  mov     [rax+8], r13
0x1800108a9  mov     [rax+10h], r13
0x1800108ad  mov     rdi, rax
0x1800108b0  mov     [rsp+98h+var_78], rax
0x1800108b5  mov     ecx, 18h; Size
0x1800108ba  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800108bf  test    rax, rax
0x1800108c2  jz      short loc_1800108E4
0x1800108c4  mov     rcx, [rbx]
0x1800108c7  mov     [rbx], r13
0x1800108ca  mov     [rsp+98h+arg_10], rcx
0x1800108d2  lea     rdx, [rsp+98h+arg_10]
0x1800108da  mov     rcx, rax
0x1800108dd  call    ??0FilterAgent@@QEAA@V?$unique_ptr@VFilterBasicParameter@@U?$default_delete@VFilterBasicParameter@@@std@@@std@@@Z; FilterAgent::FilterAgent(std::unique_ptr<FilterBasicParameter>)
0x1800108e2  jmp     short loc_1800108E7
0x1800108e4  mov     rax, r13
0x1800108e7  mov     [rsp+98h+arg_10], rax
0x1800108ef  lea     rdx, [rsp+98h+arg_10]
0x1800108f7  mov     rcx, rdi
0x1800108fa  call    ?push_back@?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@QEAAX$$QEAV?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@2@@Z; std::vector<std::unique_ptr<FilterAgent>>::push_back(std::unique_ptr<FilterAgent> &&)
0x1800108ff  nop
0x180010900  mov     r12, [rsp+98h+arg_10]
0x180010908  test    r12, r12
0x18001090b  jz      short loc_180010923
0x18001090d  test    r12, r12
0x180010910  jz      short loc_180010923
0x180010912  mov     rcx, r12; this
0x180010915  call    ??1FilterAgent@@QEAA@XZ; FilterAgent::~FilterAgent(void)
0x18001091a  mov     rcx, r12
0x18001091d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180010923  add     rbx, 8
0x180010927  jmp     loc_1800105C6
0x18001092c  mov     eax, dword ptr [rsp+98h+arg_8]
0x180010933  add     rsp, 60h
0x180010937  pop     r15
0x180010939  pop     r14
0x18001093b  pop     r13
0x18001093d  pop     r12
0x18001093f  pop     rdi
0x180010940  pop     rsi
0x180010941  pop     rbx
0x180010942  retn
```
