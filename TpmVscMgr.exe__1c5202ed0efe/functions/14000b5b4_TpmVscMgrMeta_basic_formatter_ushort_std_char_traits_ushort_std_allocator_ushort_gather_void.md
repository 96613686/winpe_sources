# TpmVscMgrMeta::basic_formatter<ushort,std::char_traits<ushort>,std::allocator<ushort>>::gather(void)

- ea: `0x14000b5b4`
- end: `0x14000b7e7`
- name: `?gather@?$basic_formatter@GU?$char_traits@G@std@@V?$allocator@G@2@@TpmVscMgrMeta@@QEAAXXZ`
- size: `563`
- prototype: `void __fastcall(__int64)`
- caller_count: `5`
- callee_count: `14`
- tags: `file_ops`

## callers

- `0x14000641c`
- `0x140008784`
- `0x14000e510`
- `0x14000e62c`
- `0x14000f54c`

## callees

- `0x1400016a0`
- `0x140001934`
- `0x140001990`
- `0x140006c84`
- `0x140006d94`
- `0x140007b88`
- `0x1400080e0`
- `0x1400081fc`
- `0x140008278`
- `0x140008308`
- `0x14000859c`
- `0x140008688`
- `0x14000b5b4`
- `0x14000ce48`

## import_xrefs

- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x14000b7c1`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x14000b7c1`

## pseudocode

```c
void __fastcall TpmVscMgrMeta::basic_formatter<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::gather(
        __int64 a1)
{
  _QWORD *v2; // rdx
  void ***v3; // rsi
  _QWORD *v4; // rdi
  _QWORD *i; // rbx
  _QWORD *v6; // rdx
  __int64 v7; // rax
  _QWORD *v8; // r14
  _QWORD *v9; // r15
  char *v10; // r12
  char **v11; // rdi
  _QWORD *v12; // rax
  _QWORD *v13; // rcx
  __int64 v14; // rcx
  void **v15; // rcx
  char **v16; // rdi
  char *v17; // rbx
  void **v18; // rax
  void **v19; // rcx
  void **v20; // rax
  _QWORD *v21; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v22; // [rsp+28h] [rbp-D8h]
  void **v23; // [rsp+30h] [rbp-D0h] BYREF
  void **v24; // [rsp+38h] [rbp-C8h]
  __int64 v25[17]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v26[104]; // [rsp+C8h] [rbp-38h] BYREF
  char *v27[4]; // [rsp+130h] [rbp+30h] BYREF

  if ( *(_BYTE *)a1 )
  {
    *(_BYTE *)a1 = 0;
    std::basic_ostringstream<unsigned short>::basic_ostringstream<unsigned short>(v25);
    if ( !*(_QWORD *)(a1 + 16) && !*(_BYTE *)a1 )
    {
      v2 = (_QWORD *)(a1 + 40);
      if ( *(_QWORD *)(a1 + 64) > 7u )
        v2 = (_QWORD *)*v2;
      std::_Insert_string<unsigned short,std::char_traits<unsigned short>,unsigned __int64>(
        v25,
        (__int64)v2,
        *(_QWORD *)(a1 + 56));
    }
    v3 = (void ***)(a1 + 8);
    v4 = *(_QWORD **)(a1 + 8);
    for ( i = (_QWORD *)*v4; i != v4; i = (_QWORD *)*i )
    {
      v6 = i + 2;
      if ( i[5] > 7u )
        v6 = (_QWORD *)*v6;
      std::_Insert_string<unsigned short,std::char_traits<unsigned short>,unsigned __int64>(v25, (__int64)v6, i[4]);
    }
    v7 = std::basic_ostringstream<unsigned short>::str(v25, v27);
    std::wstring::operator=(a1 + 40, v7);
    std::wstring::~wstring(v27);
    v8 = (_QWORD *)(a1 + 24);
    v9 = (_QWORD *)*v8;
    v10 = *(char **)(*v8 + 8LL);
    while ( !v10[25] )
    {
      std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::vector<std::_List_iterator<std::_List_val<std::_List_simple_types<std::wstring>>>>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::vector<std::_List_iterator<std::_List_val<std::_List_simple_types<std::wstring>>>>>,void *>>>(
        (__int64)v8,
        (__int64)v8,
        *((char **)v10 + 2));
      v11 = (char **)v10;
      v10 = *(char **)v10;
      std::vector<std::_List_iterator<std::_List_val<std::_List_simple_types<std::wstring>>>>::~vector<std::_List_iterator<std::_List_val<std::_List_simple_types<std::wstring>>>>(v11 + 8);
      std::wstring::~wstring(v11 + 4);
      operator delete(v11);
    }
    v9[1] = v9;
    *v9 = v9;
    v9[2] = v9;
    v8[1] = 0;
    v22 = 0;
    v12 = operator new(0x58u);
    *v12 = v12;
    v12[1] = v12;
    v12[2] = v12;
    *((_WORD *)v12 + 12) = 257;
    v21 = v12;
    if ( v8 != &v21 )
    {
      v13 = (_QWORD *)*v8;
      *v8 = v12;
      v21 = v13;
      v14 = v8[1];
      v8[1] = v22;
      v22 = v14;
    }
    __1___Tree_V___Tmap_traits_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__vector_V___List_iterator_V___List_val_U___List_simple_types_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___std___std___std__V__allocator_V___List_iterator_V___List_val_U___List_simple_types_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___std___std___std___2__2_U__less_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__vector_V___List_iterator_V___List_val_U___List_simple_types_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___std___std___std__V__allocator_V___List_iterator_V___List_val_U___List_simple_types_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___std___std___std___2__2__std___2__0A__std___std__QEAA_XZ(&v21);
    v15 = *v3;
    *(_QWORD *)(*v3)[1] = 0;
    v16 = (char **)*v15;
    if ( *v15 )
    {
      do
      {
        v17 = *v16;
        std::wstring::~wstring(v16 + 2);
        operator delete(v16);
        v16 = (char **)v17;
      }
      while ( v17 );
    }
    **v3 = *v3;
    (*v3)[1] = *v3;
    v3[1] = 0;
    v24 = 0;
    v18 = (void **)operator new(0x30u);
    *v18 = v18;
    v18[1] = v18;
    v23 = v18;
    if ( v3 != &v23 )
    {
      v19 = *v3;
      *v3 = v18;
      v23 = v19;
      v20 = v3[1];
      v3[1] = 0;
      v24 = v20;
    }
    std::list<std::wstring>::~list<std::wstring>(&v23);
    std::basic_ostringstream<unsigned short>::~basic_ostringstream<unsigned short>((__int64)v26);
    std::basic_ios<unsigned short>::~basic_ios<unsigned short,std::char_traits<unsigned short>>(v26);
  }
}

```

## disassembly

```asm
0x14000b5b4  push    rbp
0x14000b5b6  push    rbx
0x14000b5b7  push    rsi
0x14000b5b8  push    rdi
0x14000b5b9  push    r12
0x14000b5bb  push    r13
0x14000b5bd  push    r14
0x14000b5bf  push    r15
0x14000b5c1  lea     rbp, [rsp-68h]
0x14000b5c6  sub     rsp, 168h
0x14000b5cd  mov     rax, cs:__security_cookie
0x14000b5d4  xor     rax, rsp
0x14000b5d7  mov     [rbp+0A0h+var_50], rax
0x14000b5db  mov     r14, rcx
0x14000b5de  xor     r13d, r13d
0x14000b5e1  cmp     [rcx], r13b
0x14000b5e4  jz      loc_14000B7C7
0x14000b5ea  mov     [rcx], r13b
0x14000b5ed  lea     rcx, [rsp+1A0h+var_160]
0x14000b5f2  call    ??0?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_ostringstream<ushort>::basic_ostringstream<ushort>(void)
0x14000b5f7  nop
0x14000b5f8  cmp     [r14+10h], r13
0x14000b5fc  jnz     short loc_14000B61F
0x14000b5fe  cmp     [r14], r13b
0x14000b601  jnz     short loc_14000B61F
0x14000b603  lea     rdx, [r14+28h]
0x14000b607  mov     r8, [rdx+10h]
0x14000b60b  cmp     qword ptr [rdx+18h], 7
0x14000b610  jbe     short loc_14000B615
0x14000b612  mov     rdx, [rdx]
0x14000b615  lea     rcx, [rsp+1A0h+var_160]
0x14000b61a  call    ??$_Insert_string@GU?$char_traits@G@std@@_K@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@QEBG_K@Z; std::_Insert_string<ushort,std::char_traits<ushort>,unsigned __int64>(std::basic_ostream<ushort> &,ushort const * const,unsigned __int64)
0x14000b61f  lea     rsi, [r14+8]
0x14000b623  mov     rdi, [rsi]
0x14000b626  mov     rbx, [rdi]
0x14000b629  cmp     rbx, rdi
0x14000b62c  jz      short loc_14000B64F
0x14000b62e  lea     rdx, [rbx+10h]
0x14000b632  mov     r8, [rdx+10h]
0x14000b636  cmp     qword ptr [rdx+18h], 7
0x14000b63b  jbe     short loc_14000B640
0x14000b63d  mov     rdx, [rdx]
0x14000b640  lea     rcx, [rsp+1A0h+var_160]
0x14000b645  call    ??$_Insert_string@GU?$char_traits@G@std@@_K@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@QEBG_K@Z; std::_Insert_string<ushort,std::char_traits<ushort>,unsigned __int64>(std::basic_ostream<ushort> &,ushort const * const,unsigned __int64)
0x14000b64a  mov     rbx, [rbx]
0x14000b64d  jmp     short loc_14000B629
0x14000b64f  lea     rdx, [rbp+0A0h+var_70]
0x14000b653  lea     rcx, [rsp+1A0h+var_160]
0x14000b658  call    ?str@?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_ostringstream<ushort>::str(void)
0x14000b65d  lea     rcx, [r14+28h]
0x14000b661  mov     rdx, rax
0x14000b664  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x14000b669  lea     rcx, [rbp+0A0h+var_70]
0x14000b66d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000b672  add     r14, 18h
0x14000b676  mov     r15, [r14]
0x14000b679  mov     r12, [r15+8]
0x14000b67d  jmp     short loc_14000B6B5
0x14000b67f  mov     r8, [r12+10h]
0x14000b684  mov     rdx, r14
0x14000b687  mov     rcx, r14
0x14000b68a  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@V?$allocator@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@@2@@2@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@V?$allocator@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@@2@@2@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@V?$allocator@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@@2@@2@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@V?$allocator@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@@2@@2@@std@@PEAX@1@@Z
0x14000b68f  mov     rdi, r12
0x14000b692  mov     r12, [r12]
0x14000b696  lea     rcx, [rdi+40h]
0x14000b69a  call    ??1?$vector@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@V?$allocator@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::_List_iterator<std::_List_val<std::_List_simple_types<std::wstring>>>>::~vector<std::_List_iterator<std::_List_val<std::_List_simple_types<std::wstring>>>>(void)
0x14000b69f  lea     rcx, [rdi+20h]
0x14000b6a3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000b6a8  mov     edx, 58h ; 'X'; unsigned __int64
0x14000b6ad  mov     rcx, rdi; void *
0x14000b6b0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000b6b5  cmp     [r12+19h], r13b
0x14000b6ba  jz      short loc_14000B67F
0x14000b6bc  mov     [r15+8], r15
0x14000b6c0  mov     [r15], r15
0x14000b6c3  mov     [r15+10h], r15
0x14000b6c7  mov     [r14+8], r13
0x14000b6cb  mov     [rsp+1A0h+var_180], r13
0x14000b6d0  mov     [rsp+1A0h+var_178], r13
0x14000b6d5  mov     ecx, 58h ; 'X'; Size
0x14000b6da  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000b6df  mov     [rax], rax
0x14000b6e2  mov     [rax+8], rax
0x14000b6e6  mov     [rax+10h], rax
0x14000b6ea  mov     word ptr [rax+18h], 101h
0x14000b6f0  mov     [rsp+1A0h+var_180], rax
0x14000b6f5  lea     rcx, [rsp+1A0h+var_180]
0x14000b6fa  cmp     r14, rcx
0x14000b6fd  jz      short loc_14000B71C
0x14000b6ff  mov     rcx, [r14]
0x14000b702  mov     [r14], rax
0x14000b705  mov     [rsp+1A0h+var_180], rcx
0x14000b70a  mov     rcx, [r14+8]
0x14000b70e  mov     rax, [rsp+1A0h+var_178]
0x14000b713  mov     [r14+8], rax
0x14000b717  mov     [rsp+1A0h+var_178], rcx
0x14000b71c  lea     rcx, [rsp+1A0h+var_180]
0x14000b721  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@V?$allocator@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@@2@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@V?$allocator@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@@2@@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ
0x14000b726  mov     rcx, [rsi]
0x14000b729  mov     rax, [rcx+8]
0x14000b72d  mov     [rax], r13
0x14000b730  mov     rdi, [rcx]
0x14000b733  mov     r14d, 30h ; '0'
0x14000b739  test    rdi, rdi
0x14000b73c  jz      short loc_14000B75D
0x14000b73e  mov     rbx, [rdi]
0x14000b741  lea     rcx, [rdi+10h]
0x14000b745  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000b74a  mov     rdx, r14; unsigned __int64
0x14000b74d  mov     rcx, rdi; void *
0x14000b750  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000b755  mov     rdi, rbx
0x14000b758  test    rbx, rbx
0x14000b75b  jnz     short loc_14000B73E
0x14000b75d  mov     rax, [rsi]
0x14000b760  mov     [rax], rax
0x14000b763  mov     rax, [rsi]
0x14000b766  mov     [rax+8], rax
0x14000b76a  mov     [rsi+8], r13
0x14000b76e  mov     [rsp+1A0h+var_168], r13
0x14000b773  mov     rcx, r14; Size
0x14000b776  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000b77b  mov     [rax], rax
0x14000b77e  mov     [rax+8], rax
0x14000b782  mov     [rsp+1A0h+var_170], rax
0x14000b787  lea     rcx, [rsp+1A0h+var_170]
0x14000b78c  cmp     rsi, rcx
0x14000b78f  jz      short loc_14000B7A9
0x14000b791  mov     rcx, [rsi]
0x14000b794  mov     [rsi], rax
0x14000b797  mov     [rsp+1A0h+var_170], rcx
0x14000b79c  mov     rax, [rsi+8]
0x14000b7a0  mov     [rsi+8], r13
0x14000b7a4  mov     [rsp+1A0h+var_168], rax
0x14000b7a9  lea     rcx, [rsp+1A0h+var_170]
0x14000b7ae  call    ??1?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::list<std::wstring>::~list<std::wstring>(void)
0x14000b7b3  nop
0x14000b7b4  lea     rcx, [rbp+0A0h+var_D8]
0x14000b7b8  call    ??1?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UEAA@XZ; std::basic_ostringstream<ushort>::~basic_ostringstream<ushort>(void)
0x14000b7bd  lea     rcx, [rbp+0A0h+var_D8]
0x14000b7c1  call    cs:__imp_??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_ios<ushort>::~basic_ios<ushort,std::char_traits<ushort>>(void)
0x14000b7c7  mov     rcx, [rbp+0A0h+var_50]
0x14000b7cb  xor     rcx, rsp; StackCookie
0x14000b7ce  call    __security_check_cookie
0x14000b7d3  add     rsp, 168h
0x14000b7da  pop     r15
0x14000b7dc  pop     r14
0x14000b7de  pop     r13
0x14000b7e0  pop     r12
0x14000b7e2  pop     rdi
0x14000b7e3  pop     rsi
0x14000b7e4  pop     rbx
0x14000b7e5  pop     rbp
0x14000b7e6  retn
```
