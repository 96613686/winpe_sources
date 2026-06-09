# std::_Hash<std::tr1::_Uset_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::_Hash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,0>>::_Insert(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::_List_const_iterator<std::_List_val<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>>)

- ea: `0x1800181f0`
- end: `0x18001833e`
- name: `?_Insert@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@tr1@std@@@std@@IEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@std@@_N@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@V?$_List_const_iterator@V?$_List_val@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@2@@Z`
- size: `334`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000b280`
- `0x180017dfc`

## callees

- `0x18000c15c`
- `0x180017dfc`
- `0x1800180d4`
- `0x1800181f0`
- `0x180018c94`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::tr1::_Uset_traits<std::wstring,std::_Hash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Insert(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD **a4)
{
  _QWORD *v7; // r12
  _QWORD *v8; // rbx
  __int64 v9; // rcx
  __int64 v10; // rsi
  __int64 v11; // rax
  _QWORD *v12; // rdx
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  _QWORD *v15; // rax
  _QWORD *v17; // rax
  _QWORD **v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // rcx
  _QWORD *iter; // rax
  __int64 v23; // [rsp+20h] [rbp-48h] BYREF
  __int64 v24; // [rsp+28h] [rbp-40h] BYREF
  __int64 v25; // [rsp+70h] [rbp+8h] BYREF
  __int64 v26; // [rsp+80h] [rbp+18h]
  _QWORD **v27; // [rsp+88h] [rbp+20h]

  v27 = a4;
  v26 = a3;
  v25 = a1;
  v7 = (_QWORD *)(a1 + 8);
  v8 = *(_QWORD **)(a1 + 8);
  v10 = 2
      * std::_Hash<std::tr1::_Uset_traits<std::wstring,std::_Hash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Hashval(
          a1,
          a3);
  v11 = *(_QWORD *)(a1 + 32);
  if ( *(_QWORD **)(v11 + 8 * v10) != v8 )
    v8 = **(_QWORD ***)(v11 + 8 * v10 + 8);
  while ( v8 != *(_QWORD **)(*(_QWORD *)(a1 + 32) + 8 * v10) )
  {
    v8 = (_QWORD *)v8[1];
    if ( !(unsigned __int8)std::_Hash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>::operator()(
                             v9,
                             v26,
                             v8 + 2) )
    {
      if ( !(unsigned __int8)std::_Hash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>::operator()(
                               v9,
                               v8 + 2,
                               v26) )
      {
        std::list<std::wstring>::erase(v7, &v25, a4);
        *(_QWORD *)a2 = v8;
        *(_BYTE *)(a2 + 8) = 0;
        return a2;
      }
      v8 = (_QWORD *)*v8;
      break;
    }
  }
  v12 = *a4;
  if ( v8 != *a4 )
  {
    *a4[1] = v12;
    *(_QWORD *)v12[1] = v8;
    *(_QWORD *)v8[1] = a4;
    v13 = (_QWORD *)v8[1];
    v8[1] = v12[1];
    v12[1] = a4[1];
    a4[1] = v13;
  }
  v14 = *(_QWORD *)(a1 + 32);
  v15 = *(_QWORD **)(v14 + 8 * v10);
  if ( v15 == (_QWORD *)*v7 )
  {
    *(_QWORD *)(v14 + 8 * v10) = a4;
    *(_QWORD *)(*(_QWORD *)(a1 + 32) + 8 * v10 + 8) = a4;
  }
  else if ( v15 == v8 )
  {
    *(_QWORD *)(v14 + 8 * v10) = a4;
  }
  else
  {
    v17 = *(_QWORD **)(v14 + 8 * v10 + 8);
    v18 = (_QWORD **)*v17;
    *(_QWORD *)(v14 + 8 * v10 + 8) = *v17;
    if ( v18 != a4 )
    {
      v19 = *(_QWORD *)(a1 + 32);
      v20 = *(_QWORD *)(*(_QWORD *)(v19 + 8 * v10 + 8) + 8LL);
      *(_QWORD *)(v19 + 8 * v10 + 8) = v20;
    }
  }
  try
  {
    std::_Hash<std::tr1::_Uset_traits<std::wstring,std::_Hash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Check_size(a1);
  }
  catch ( ... )
  {
    iter = (_QWORD *)std::list<std::wstring>::_Make_iter(v21, &v23, v27);
    std::_Hash<std::tr1::_Uset_traits<std::wstring,std::_Hash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::erase(
      v25,
      &v24,
      *iter);
    throw;
  }
  *(_QWORD *)a2 = a4;
  *(_BYTE *)(a2 + 8) = 1;
  return a2;
}

```

## disassembly

```asm
0x1800181f0  mov     [rsp+arg_18], r9
0x1800181f5  mov     [rsp+arg_10], r8
0x1800181fa  mov     [rsp+arg_0], rcx
0x1800181ff  push    rbx
0x180018200  push    rsi
0x180018201  push    rdi
0x180018202  push    r12
0x180018204  push    r13
0x180018206  push    r14
0x180018208  push    r15
0x18001820a  sub     rsp, 30h
0x18001820e  mov     rdi, r9
0x180018211  mov     r14, rdx
0x180018214  mov     r15, rcx
0x180018217  lea     r12, [rcx+8]
0x18001821b  mov     rbx, [r12]
0x18001821f  mov     rdx, r8
0x180018222  call    ?_Hashval@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@tr1@std@@@std@@IEBA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<std::tr1::_Uset_traits<std::wstring,std::_Hash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Hashval(std::wstring const &)
0x180018227  mov     rsi, rax
0x18001822a  add     rsi, rsi
0x18001822d  mov     rax, [r15+20h]
0x180018231  cmp     [rax+rsi*8], rbx
0x180018235  jz      short loc_18001823F
0x180018237  mov     rbx, [rax+rsi*8+8]
0x18001823c  mov     rbx, [rbx]
0x18001823f  mov     rax, [r15+20h]
0x180018243  cmp     rbx, [rax+rsi*8]
0x180018247  jz      short loc_18001827F
0x180018249  mov     rax, [rbx+8]
0x18001824d  mov     rbx, rax
0x180018250  lea     r13, [rax+10h]
0x180018254  mov     r8, r13
0x180018257  mov     rdx, [rsp+68h+arg_10]
0x18001825f  call    ??R?$_Hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEBA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@0@Z; std::_Hash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>::operator()(std::wstring const &,std::wstring const &)
0x180018264  test    al, al
0x180018266  jnz     short loc_18001823F
0x180018268  mov     r8, [rsp+68h+arg_10]
0x180018270  mov     rdx, r13
0x180018273  call    ??R?$_Hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEBA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@0@Z; std::_Hash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>::operator()(std::wstring const &,std::wstring const &)
0x180018278  test    al, al
0x18001827a  jz      short loc_1800182D1
0x18001827c  mov     rbx, [rbx]
0x18001827f  mov     rdx, [rdi]
0x180018282  cmp     rbx, rdx
0x180018285  jz      short loc_1800182B4
0x180018287  mov     rax, [rdi+8]
0x18001828b  mov     [rax], rdx
0x18001828e  mov     rax, [rdx+8]
0x180018292  mov     [rax], rbx
0x180018295  mov     rax, [rbx+8]
0x180018299  mov     [rax], rdi
0x18001829c  mov     rcx, [rbx+8]
0x1800182a0  mov     rax, [rdx+8]
0x1800182a4  mov     [rbx+8], rax
0x1800182a8  mov     rax, [rdi+8]
0x1800182ac  mov     [rdx+8], rax
0x1800182b0  mov     [rdi+8], rcx
0x1800182b4  mov     rdx, [r15+20h]
0x1800182b8  mov     rax, [rdx+rsi*8]
0x1800182bc  cmp     rax, [r12]
0x1800182c0  jnz     short loc_1800182FC
0x1800182c2  mov     [rdx+rsi*8], rdi
0x1800182c6  mov     rax, [r15+20h]
0x1800182ca  mov     [rax+rsi*8+8], rdi
0x1800182cf  jmp     short loc_18001832B
0x1800182d1  mov     r8, rdi
0x1800182d4  lea     rdx, [rsp+68h+arg_0]
0x1800182d9  mov     rcx, r12
0x1800182dc  call    ?erase@?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA?AV?$_List_iterator@V?$_List_val@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@2@V?$_List_const_iterator@V?$_List_val@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@2@@Z; std::list<std::wstring>::erase(std::_List_const_iterator<std::_List_val<std::wstring>>)
0x1800182e1  mov     [r14], rbx
0x1800182e4  mov     byte ptr [r14+8], 0
0x1800182e9  mov     rax, r14
0x1800182ec  add     rsp, 30h
0x1800182f0  pop     r15
0x1800182f2  pop     r14
0x1800182f4  pop     r13
0x1800182f6  pop     r12
0x1800182f8  pop     rdi
0x1800182f9  pop     rsi
0x1800182fa  pop     rbx
0x1800182fb  retn
0x1800182fc  cmp     rax, rbx
0x1800182ff  jnz     short loc_180018307
0x180018301  mov     [rdx+rsi*8], rdi
0x180018305  jmp     short loc_18001832B
0x180018307  mov     rax, [rdx+rsi*8+8]
0x18001830c  mov     rcx, [rax]
0x18001830f  mov     [rdx+rsi*8+8], rcx
0x180018314  cmp     rcx, rdi
0x180018317  jz      short loc_18001832B
0x180018319  mov     rdx, [r15+20h]
0x18001831d  mov     rax, [rdx+rsi*8+8]
0x180018322  mov     rcx, [rax+8]
0x180018326  mov     [rdx+rsi*8+8], rcx
0x18001832b  mov     rcx, r15
0x18001832e  call    ?_Check_size@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@tr1@std@@@std@@IEAAXXZ; std::_Hash<std::tr1::_Uset_traits<std::wstring,std::_Hash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Check_size(void)
0x180018333  nop
0x180018334  mov     [r14], rdi
0x180018337  mov     byte ptr [r14+8], 1
0x18001833c  jmp     short loc_1800182E9
```
