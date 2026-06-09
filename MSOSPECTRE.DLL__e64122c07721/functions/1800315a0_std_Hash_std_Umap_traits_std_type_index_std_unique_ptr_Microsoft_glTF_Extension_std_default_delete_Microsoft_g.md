# std::_Hash<std::_Umap_traits<std::type_index,std::unique_ptr<Microsoft::glTF::Extension,std::default_delete<Microsoft::glTF::Extension>>,std::_Uhash_compare<std::type_index,std::hash<std::type_index>,std::equal_to<std::type_index>>,std::allocator<std::pair<std::type_index const,std::unique_ptr<Microsoft::glTF::Extension,std::default_delete<Microsoft::glTF::Extension>>>>,0>>::_Forced_rehash(unsigned __int64)

- ea: `0x1800315a0`
- end: `0x180031754`
- name: `?_Forced_rehash@?$_Hash@V?$_Umap_traits@Vtype_index@std@@V?$unique_ptr@VExtension@glTF@Microsoft@@U?$default_delete@VExtension@glTF@Microsoft@@@std@@@2@V?$_Uhash_compare@Vtype_index@std@@U?$hash@Vtype_index@std@@@2@U?$equal_to@Vtype_index@std@@@2@@2@V?$allocator@U?$pair@$$CBVtype_index@std@@V?$unique_ptr@VExtension@glTF@Microsoft@@U?$default_delete@VExtension@glTF@Microsoft@@@std@@@2@@std@@@2@$0A@@std@@@std@@IEAAX_K@Z`
- size: `436`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800308c0`

## callees

- `0x180016af0`
- `0x1800315a0`

## import_xrefs

- `VCRUNTIME140!__std_type_info_compare` at `0x180031684`
- `VCRUNTIME140!__std_type_info_compare` at `0x1800316d0`
- `VCRUNTIME140!__std_type_info_compare` at `0x180031684`
- `VCRUNTIME140!__std_type_info_compare` at `0x1800316d0`
- `VCRUNTIME140!__std_type_info_hash` at `0x180031647`
- `VCRUNTIME140!__std_type_info_hash` at `0x180031647`
- `MSVCP140!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800315ea`
- `MSVCP140!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800315ea`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<std::type_index,std::unique_ptr<Microsoft::glTF::Extension>,std::_Uhash_compare<std::type_index,std::hash<std::type_index>,std::equal_to<std::type_index>>,std::allocator<std::pair<std::type_index const,std::unique_ptr<Microsoft::glTF::Extension>>>,0>>::_Forced_rehash(
        _QWORD *a1,
        unsigned __int64 a2)
{
  unsigned __int64 v3; // rcx
  _QWORD *v4; // rbp
  unsigned __int64 v5; // rcx
  __int64 v6; // rbx
  __int64 result; // rax
  _QWORD *v8; // rbx
  _QWORD *i; // rdi
  __int64 v10; // r15
  __int64 v11; // r14
  _QWORD *v12; // rsi
  _QWORD *v13; // r8
  _QWORD *v14; // rdx
  _QWORD *v15; // rcx
  _QWORD *v16; // rdx
  _QWORD *v17; // rcx
  _QWORD *v18; // r8
  _QWORD *v19; // rdx
  _QWORD *v20; // rcx

  _BitScanReverse64(&v3, 0xFFFFFFFFFFFFFFFuLL);
  if ( a2 > 1LL << v3 )
    std::_Xlength_error("invalid hash bucket count");
  v4 = (_QWORD *)a1[1];
  _BitScanReverse64(&v5, (a2 - 1) | 1);
  v6 = 1LL << ((unsigned __int8)v5 + 1);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::type_index const,std::unique_ptr<Microsoft::glTF::Extension>>>>>>>::_Assign_grow(
    a1 + 3,
    2 * v6,
    v4);
  result = v6 - 1;
  a1[7] = v6;
  a1[6] = v6 - 1;
  v8 = *(_QWORD **)a1[1];
  for ( i = v8; i != v4; v8 = i )
  {
    i = (_QWORD *)*i;
    result = __std_type_info_hash(v8[2] + 8LL);
    v10 = a1[3];
    v11 = 2 * (result & a1[6]);
    if ( *(_QWORD **)(v10 + 16 * (result & a1[6])) == v4 )
    {
      *(_QWORD *)(v10 + 16 * (result & a1[6])) = v8;
    }
    else
    {
      v12 = *(_QWORD **)(v10 + 16 * (result & a1[6]) + 8);
      result = __std_type_info_compare(v8[2] + 8LL, v12[2] + 8LL);
      if ( (_DWORD)result )
      {
        do
        {
          if ( *(_QWORD **)(v10 + 8 * v11) == v12 )
          {
            v16 = (_QWORD *)v8[1];
            *v16 = i;
            v17 = (_QWORD *)i[1];
            *v17 = v12;
            result = v12[1];
            *(_QWORD *)result = v8;
            v12[1] = v17;
            i[1] = v16;
            v8[1] = result;
            *(_QWORD *)(v10 + 8 * v11) = v8;
            goto LABEL_13;
          }
          v12 = (_QWORD *)v12[1];
        }
        while ( (unsigned int)__std_type_info_compare(v8[2] + 8LL, v12[2] + 8LL) );
        v18 = (_QWORD *)*v12;
        v19 = (_QWORD *)v8[1];
        *v19 = i;
        v20 = (_QWORD *)i[1];
        *v20 = v18;
        result = v18[1];
        *(_QWORD *)result = v8;
        v18[1] = v20;
        i[1] = v19;
        v8[1] = result;
        continue;
      }
      v13 = (_QWORD *)*v12;
      if ( (_QWORD *)*v12 != v8 )
      {
        v14 = (_QWORD *)v8[1];
        *v14 = i;
        v15 = (_QWORD *)i[1];
        *v15 = v13;
        result = v13[1];
        *(_QWORD *)result = v8;
        v13[1] = v15;
        i[1] = v14;
        v8[1] = result;
      }
    }
    *(_QWORD *)(v10 + 8 * v11 + 8) = v8;
LABEL_13:
    ;
  }
  return result;
}

```

## disassembly

```asm
0x1800315a0  mov     rax, rsp
0x1800315a3  mov     [rax+8], rbx
0x1800315a7  mov     [rax+18h], rbp
0x1800315ab  mov     [rax+20h], rsi
0x1800315af  push    rdi
0x1800315b0  push    r12
0x1800315b2  push    r13
0x1800315b4  push    r14
0x1800315b6  push    r15
0x1800315b8  sub     rsp, 20h
0x1800315bc  mov     dword ptr [rax+10h], 0
0x1800315c3  mov     r13, rcx
0x1800315c6  mov     rax, 0FFFFFFFFFFFFFFFh
0x1800315d0  mov     ebx, 1
0x1800315d5  bsr     rcx, rax
0x1800315d9  mov     eax, ebx
0x1800315db  shl     rax, cl
0x1800315de  cmp     rdx, rax
0x1800315e1  jbe     short loc_1800315F1
0x1800315e3  lea     rcx, aInvalidHashBuc; "invalid hash bucket count"
0x1800315ea  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x1800315f1  mov     rbp, [r13+8]
0x1800315f5  lea     rax, [rdx-1]
0x1800315f9  or      rax, rbx
0x1800315fc  mov     [rsp+48h+arg_8], 0
0x180031604  bsr     rcx, rax
0x180031608  mov     r8, rbp
0x18003160b  inc     ecx
0x18003160d  shl     rbx, cl
0x180031610  lea     rcx, [r13+18h]
0x180031614  lea     rdx, [rbx+rbx]
0x180031618  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBVtype_index@std@@V?$unique_ptr@VExtension@glTF@Microsoft@@U?$default_delete@VExtension@glTF@Microsoft@@@std@@@2@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBVtype_index@std@@V?$unique_ptr@VExtension@glTF@Microsoft@@U?$default_delete@VExtension@glTF@Microsoft@@@std@@@2@@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::type_index const,std::unique_ptr<Microsoft::glTF::Extension>>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::type_index const,std::unique_ptr<Microsoft::glTF::Extension>>>>>)
0x18003161d  lea     rax, [rbx-1]
0x180031621  mov     [r13+38h], rbx
0x180031625  mov     [r13+30h], rax
0x180031629  mov     rbx, [r13+8]
0x18003162d  mov     rbx, [rbx]
0x180031630  mov     rdi, rbx
0x180031633  cmp     rbx, rbp
0x180031636  jz      loc_180031711
0x18003163c  mov     rcx, [rbx+10h]
0x180031640  mov     rdi, [rdi]
0x180031643  add     rcx, 8
0x180031647  call    cs:__imp___std_type_info_hash
0x18003164d  mov     r14, [r13+30h]
0x180031651  mov     r15, [r13+18h]
0x180031655  and     r14, rax
0x180031658  add     r14, r14
0x18003165b  cmp     [r15+r14*8], rbp
0x18003165f  jnz     short loc_18003166F
0x180031661  mov     [r15+r14*8], rbx
0x180031665  mov     [r15+r14*8+8], rbx
0x18003166a  jmp     loc_180031705
0x18003166f  mov     rsi, [r15+r14*8+8]
0x180031674  mov     rcx, [rbx+10h]
0x180031678  add     rcx, 8
0x18003167c  mov     rdx, [rsi+10h]
0x180031680  add     rdx, 8
0x180031684  call    cs:__imp___std_type_info_compare
0x18003168a  test    eax, eax
0x18003168c  jnz     short loc_1800316DA
0x18003168e  mov     r8, [rsi]
0x180031691  cmp     r8, rbx
0x180031694  jz      short loc_180031665
0x180031696  mov     rdx, [rbx+8]
0x18003169a  mov     [rdx], rdi
0x18003169d  mov     rcx, [rdi+8]
0x1800316a1  mov     [rcx], r8
0x1800316a4  mov     rax, [r8+8]
0x1800316a8  mov     [rax], rbx
0x1800316ab  mov     [r8+8], rcx
0x1800316af  mov     [rdi+8], rdx
0x1800316b3  mov     [rbx+8], rax
0x1800316b7  jmp     short loc_180031665
0x1800316b9  mov     rdx, [rsi+8]
0x1800316bd  mov     rcx, [rbx+10h]
0x1800316c1  mov     rsi, rdx
0x1800316c4  add     rcx, 8
0x1800316c8  mov     rdx, [rdx+10h]
0x1800316cc  add     rdx, 8
0x1800316d0  call    cs:__imp___std_type_info_compare
0x1800316d6  test    eax, eax
0x1800316d8  jz      short loc_18003172E
0x1800316da  cmp     [r15+r14*8], rsi
0x1800316de  jnz     short loc_1800316B9
0x1800316e0  mov     rdx, [rbx+8]
0x1800316e4  mov     [rdx], rdi
0x1800316e7  mov     rcx, [rdi+8]
0x1800316eb  mov     [rcx], rsi
0x1800316ee  mov     rax, [rsi+8]
0x1800316f2  mov     [rax], rbx
0x1800316f5  mov     [rsi+8], rcx
0x1800316f9  mov     [rdi+8], rdx
0x1800316fd  mov     [rbx+8], rax
0x180031701  mov     [r15+r14*8], rbx
0x180031705  mov     rbx, rdi
0x180031708  cmp     rdi, rbp
0x18003170b  jnz     loc_18003163C
0x180031711  mov     rbx, [rsp+48h+arg_0]
0x180031716  mov     rbp, [rsp+48h+arg_10]
0x18003171b  mov     rsi, [rsp+48h+arg_18]
0x180031720  add     rsp, 20h
0x180031724  pop     r15
0x180031726  pop     r14
0x180031728  pop     r13
0x18003172a  pop     r12
0x18003172c  pop     rdi
0x18003172d  retn
0x18003172e  mov     r8, [rsi]
0x180031731  mov     rdx, [rbx+8]
0x180031735  mov     [rdx], rdi
0x180031738  mov     rcx, [rdi+8]
0x18003173c  mov     [rcx], r8
0x18003173f  mov     rax, [r8+8]
0x180031743  mov     [rax], rbx
0x180031746  mov     [r8+8], rcx
0x18003174a  mov     [rdi+8], rdx
0x18003174e  mov     [rbx+8], rax
0x180031752  jmp     short loc_180031705
```
