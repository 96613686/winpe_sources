# std::_Hash<std::_Umap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::shared_ptr<XinputHid::XInputHidDevice>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::shared_ptr<XinputHid::XInputHidDevice>>>,0>>::_Forced_rehash(unsigned __int64)

- ea: `0x180010f28`
- end: `0x180011142`
- name: `?_Forced_rehash@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UXInputHidDevice@XinputHid@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UXInputHidDevice@XinputHid@@@2@@std@@@2@$0A@@std@@@std@@IEAAX_K@Z`
- size: `538`
- prototype: `int __fastcall(_QWORD *, unsigned __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180011148`

## callees

- `0x18000babc`
- `0x180010d1c`
- `0x180010f28`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180010f66`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180010f66`

## pseudocode

```c
int __fastcall std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<XinputHid::XInputHidDevice>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<XinputHid::XInputHidDevice>>>,0>>::_Forced_rehash(
        _QWORD *a1,
        unsigned __int64 a2)
{
  unsigned __int64 v3; // rcx
  _QWORD *v4; // rbp
  unsigned __int64 v5; // rcx
  __int64 *v6; // rsi
  __int64 v7; // rbx
  unsigned __int64 v8; // rax
  _QWORD *v9; // rbx
  _QWORD *v10; // rdi
  const wchar_t **v11; // r15
  const wchar_t *v12; // r8
  _QWORD *v13; // r10
  unsigned __int64 v14; // rdx
  __int64 i; // rcx
  __int64 v16; // r12
  __int64 v17; // r14
  _QWORD *v18; // rsi
  const wchar_t *v19; // rdx
  const wchar_t *v20; // rcx
  _QWORD *v21; // r8
  _QWORD *v22; // rdx
  _QWORD *v23; // rcx
  unsigned __int64 *v24; // r8
  const wchar_t *v25; // rdx
  size_t v26; // r8
  const wchar_t *v27; // rcx
  _QWORD *v28; // r8
  _QWORD *v29; // rdx
  _QWORD *v30; // rcx
  _QWORD *v31; // rdx
  _QWORD *v32; // rcx

  _BitScanReverse64(&v3, 0xFFFFFFFFFFFFFFFuLL);
  if ( a2 > 1LL << v3 )
    std::_Xlength_error("invalid hash bucket count");
  v4 = (_QWORD *)a1[1];
  _BitScanReverse64(&v5, (a2 - 1) | 1);
  v6 = a1 + 3;
  v7 = 1LL << ((unsigned __int8)v5 + 1);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<XinputHid::XInputHidDevice>>>>>>>::_Assign_grow(
    a1 + 3,
    2 * v7,
    v4);
  LODWORD(v8) = v7 - 1;
  a1[7] = v7;
  a1[6] = v7 - 1;
  v9 = *(_QWORD **)a1[1];
  v10 = v9;
  while ( v9 != v4 )
  {
    v10 = (_QWORD *)*v10;
    v11 = (const wchar_t **)(v9 + 2);
    v12 = (const wchar_t *)(v9 + 2);
    v13 = (_QWORD *)v9[4];
    if ( v9[5] > 7u )
      v12 = *v11;
    v14 = 0;
    for ( i = 0xCBF29CE484222325uLL; v14 < 2 * (__int64)v13; i = 0x100000001B3LL * (v8 ^ i) )
      v8 = *((unsigned __int8 *)v12 + v14++);
    v16 = *v6;
    v17 = 2 * (i & a1[6]);
    if ( *(_QWORD **)(*v6 + 16 * (i & a1[6])) == v4 )
    {
      *(_QWORD *)(v16 + 16 * (i & a1[6])) = v9;
      *(_QWORD *)(v16 + 8 * v17 + 8) = v9;
    }
    else
    {
      v18 = *(_QWORD **)(v16 + 16 * (i & a1[6]) + 8);
      v19 = (const wchar_t *)(v18 + 2);
      v8 = v18[4];
      if ( v18[5] > 7u )
        v19 = *(const wchar_t **)v19;
      v20 = (const wchar_t *)(v9 + 2);
      if ( v9[5] > 7u )
        v20 = *v11;
      if ( v13 != (_QWORD *)v8 || v13 && (LODWORD(v8) = wmemcmp(v20, v19, v9[4]), (_DWORD)v8) )
      {
        while ( 1 )
        {
          v24 = v18 + 1;
          if ( *(_QWORD **)(v16 + 8 * v17) == v18 )
            break;
          v18 = (_QWORD *)*v24;
          v25 = (const wchar_t *)(*v24 + 16);
          if ( *(_QWORD *)(*v24 + 40) > 7u )
            v25 = *(const wchar_t **)v25;
          v26 = v9[4];
          if ( v9[5] <= 7u )
            v27 = (const wchar_t *)(v9 + 2);
          else
            v27 = *v11;
          if ( v26 == v18[4] && (!v26 || !wmemcmp(v27, v25, v26)) )
          {
            v28 = (_QWORD *)*v18;
            v29 = (_QWORD *)v9[1];
            *v29 = v10;
            v30 = (_QWORD *)v10[1];
            *v30 = v28;
            v8 = v28[1];
            *(_QWORD *)v8 = v9;
            v28[1] = v30;
            v10[1] = v29;
            v9[1] = v8;
            goto LABEL_32;
          }
        }
        v31 = (_QWORD *)v9[1];
        *v31 = v10;
        v8 = v10[1];
        *(_QWORD *)v8 = v18;
        v32 = (_QWORD *)*v24;
        *v32 = v9;
        *v24 = v8;
        v10[1] = v31;
        v9[1] = v32;
        *(_QWORD *)(v16 + 8 * v17) = v9;
      }
      else
      {
        v21 = (_QWORD *)*v18;
        if ( (_QWORD *)*v18 != v9 )
        {
          v22 = (_QWORD *)v9[1];
          *v22 = v10;
          v23 = (_QWORD *)v10[1];
          *v23 = v21;
          v8 = v21[1];
          *(_QWORD *)v8 = v9;
          v21[1] = v23;
          v10[1] = v22;
          v9[1] = v8;
        }
        *(_QWORD *)(v16 + 8 * v17 + 8) = v9;
      }
LABEL_32:
      v6 = a1 + 3;
    }
    v9 = v10;
  }
  return v8;
}

```

## disassembly

```asm
0x180010f28  push    rbx
0x180010f2a  push    rbp
0x180010f2b  push    rsi
0x180010f2c  push    rdi
0x180010f2d  push    r12
0x180010f2f  push    r13
0x180010f31  push    r14
0x180010f33  push    r15
0x180010f35  sub     rsp, 28h
0x180010f39  mov     rax, 0FFFFFFFFFFFFFFFh
0x180010f43  mov     [rsp+68h+arg_8], 0
0x180010f4b  mov     r13, rcx
0x180010f4e  bsr     rcx, rax
0x180010f52  mov     eax, 1
0x180010f57  shl     rax, cl
0x180010f5a  cmp     rdx, rax
0x180010f5d  jbe     short loc_180010F6D
0x180010f5f  lea     rcx, aInvalidHashBuc; "invalid hash bucket count"
0x180010f66  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180010f6d  mov     rbp, [r13+8]
0x180010f71  lea     rax, [rdx-1]
0x180010f75  or      rax, 1
0x180010f79  mov     [rsp+68h+arg_8], 0
0x180010f81  bsr     rcx, rax
0x180010f85  mov     ebx, 1
0x180010f8a  lea     rsi, [r13+18h]
0x180010f8e  inc     ecx
0x180010f90  mov     r8, rbp
0x180010f93  shl     rbx, cl
0x180010f96  mov     rcx, rsi
0x180010f99  lea     rdx, [rbx+rbx]
0x180010f9d  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UXInputHidDevice@XinputHid@@@2@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UXInputHidDevice@XinputHid@@@2@@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<XinputHid::XInputHidDevice>>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<XinputHid::XInputHidDevice>>>>>)
0x180010fa2  lea     rax, [rbx-1]
0x180010fa6  mov     [r13+38h], rbx
0x180010faa  mov     [r13+30h], rax
0x180010fae  mov     rbx, [r13+8]
0x180010fb2  mov     rbx, [rbx]
0x180010fb5  mov     rdi, rbx
0x180010fb8  cmp     rbx, rbp
0x180010fbb  jz      loc_180011131
0x180010fc1  mov     rdi, [rdi]
0x180010fc4  lea     r15, [rbx+10h]
0x180010fc8  cmp     qword ptr [r15+18h], 7
0x180010fcd  mov     r8, r15
0x180010fd0  mov     r10, [r15+10h]
0x180010fd4  jbe     short loc_180010FD9
0x180010fd6  mov     r8, [r15]
0x180010fd9  lea     r9, [r10+r10]
0x180010fdd  xor     edx, edx
0x180010fdf  mov     rcx, 0CBF29CE484222325h
0x180010fe9  test    r9, r9
0x180010fec  jz      short loc_18001100C
0x180010fee  movzx   eax, byte ptr [r8+rdx]
0x180010ff3  mov     r11, 100000001B3h
0x180010ffd  xor     rcx, rax
0x180011000  inc     rdx
0x180011003  imul    rcx, r11
0x180011007  cmp     rdx, r9
0x18001100a  jb      short loc_180010FEE
0x18001100c  mov     r14, [r13+30h]
0x180011010  mov     r12, [rsi]
0x180011013  and     r14, rcx
0x180011016  add     r14, r14
0x180011019  cmp     [r12+r14*8], rbp
0x18001101d  jnz     short loc_18001102D
0x18001101f  mov     [r12+r14*8], rbx
0x180011023  mov     [r12+r14*8+8], rbx
0x180011028  jmp     loc_180011129
0x18001102d  mov     rsi, [r12+r14*8+8]
0x180011032  lea     rdx, [rsi+10h]
0x180011036  cmp     qword ptr [rdx+18h], 7
0x18001103b  mov     rax, [rdx+10h]
0x18001103f  jbe     short loc_180011044
0x180011041  mov     rdx, [rdx]; S2
0x180011044  cmp     qword ptr [r15+18h], 7
0x180011049  mov     rcx, r15
0x18001104c  jbe     short loc_180011051
0x18001104e  mov     rcx, [r15]; S1
0x180011051  cmp     r10, rax
0x180011054  jnz     short loc_18001109A
0x180011056  test    r10, r10
0x180011059  jz      short loc_180011067
0x18001105b  mov     r8, r10; N
0x18001105e  call    wmemcmp
0x180011063  test    eax, eax
0x180011065  jnz     short loc_18001109A
0x180011067  mov     r8, [rsi]
0x18001106a  cmp     r8, rbx
0x18001106d  jz      short loc_180011090
0x18001106f  mov     rdx, [rbx+8]
0x180011073  mov     [rdx], rdi
0x180011076  mov     rcx, [rdi+8]
0x18001107a  mov     [rcx], r8
0x18001107d  mov     rax, [r8+8]
0x180011081  mov     [rax], rbx
0x180011084  mov     [r8+8], rcx
0x180011088  mov     [rdi+8], rdx
0x18001108c  mov     [rbx+8], rax
0x180011090  mov     [r12+r14*8+8], rbx
0x180011095  jmp     loc_180011125
0x18001109a  lea     r8, [rsi+8]
0x18001109e  cmp     [r12+r14*8], rsi
0x1800110a2  jz      short loc_180011102
0x1800110a4  mov     rsi, [r8]
0x1800110a7  cmp     qword ptr [rsi+28h], 7
0x1800110ac  lea     rdx, [rsi+10h]
0x1800110b0  jbe     short loc_1800110B5
0x1800110b2  mov     rdx, [rdx]; S2
0x1800110b5  cmp     qword ptr [r15+18h], 7
0x1800110ba  mov     r8, [r15+10h]; N
0x1800110be  jbe     short loc_1800110C5
0x1800110c0  mov     rcx, [r15]
0x1800110c3  jmp     short loc_1800110C8
0x1800110c5  mov     rcx, r15; S1
0x1800110c8  cmp     r8, [rsi+20h]
0x1800110cc  jnz     short loc_18001109A
0x1800110ce  test    r8, r8
0x1800110d1  jz      short loc_1800110DC
0x1800110d3  call    wmemcmp
0x1800110d8  test    eax, eax
0x1800110da  jnz     short loc_18001109A
0x1800110dc  mov     r8, [rsi]
0x1800110df  mov     rdx, [rbx+8]
0x1800110e3  mov     [rdx], rdi
0x1800110e6  mov     rcx, [rdi+8]
0x1800110ea  mov     [rcx], r8
0x1800110ed  mov     rax, [r8+8]
0x1800110f1  mov     [rax], rbx
0x1800110f4  mov     [r8+8], rcx
0x1800110f8  mov     [rdi+8], rdx
0x1800110fc  mov     [rbx+8], rax
0x180011100  jmp     short loc_180011125
0x180011102  mov     rdx, [rbx+8]
0x180011106  mov     [rdx], rdi
0x180011109  mov     rax, [rdi+8]
0x18001110d  mov     [rax], rsi
0x180011110  mov     rcx, [r8]
0x180011113  mov     [rcx], rbx
0x180011116  mov     [r8], rax
0x180011119  mov     [rdi+8], rdx
0x18001111d  mov     [rbx+8], rcx
0x180011121  mov     [r12+r14*8], rbx
0x180011125  lea     rsi, [r13+18h]
0x180011129  mov     rbx, rdi
0x18001112c  jmp     loc_180010FB8
0x180011131  add     rsp, 28h
0x180011135  pop     r15
0x180011137  pop     r14
0x180011139  pop     r13
0x18001113b  pop     r12
0x18001113d  pop     rdi
0x18001113e  pop     rsi
0x18001113f  pop     rbp
0x180011140  pop     rbx
0x180011141  retn
```
