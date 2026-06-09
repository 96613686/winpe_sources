# std::_Hash<std::tr1::_Uset_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::_Hash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,0>>::_Check_size(void)

- ea: `0x180017dfc`
- end: `0x180017ecc`
- name: `?_Check_size@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@tr1@std@@@std@@IEAAXXZ`
- size: `208`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800181f0`

## callees

- `0x180017dfc`
- `0x18001818c`
- `0x1800181f0`

## pseudocode

```c
void __fastcall std::_Hash<std::tr1::_Uset_traits<std::wstring,std::_Hash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Check_size(
        __int64 a1)
{
  __int64 v1; // r8
  unsigned __int64 v3; // rdx
  float v4; // xmm0_4
  __int64 v5; // rax
  float v6; // xmm1_4
  int i; // eax
  _QWORD *v8; // rax
  _QWORD **v9; // rsi
  _QWORD **v10; // rbx
  _BYTE v11[24]; // [rsp+20h] [rbp-18h] BYREF

  v1 = *(_QWORD *)(a1 + 16);
  v3 = *(_QWORD *)(a1 + 72);
  if ( v1 < 0 )
  {
    v5 = *(_QWORD *)(a1 + 16) & 1LL | (*(_QWORD *)(a1 + 16) >> 1);
    v4 = (float)(int)v5 + (float)(int)v5;
  }
  else
  {
    v4 = (float)(int)v1;
  }
  if ( (v3 & 0x8000000000000000uLL) != 0LL )
    v6 = (float)(int)(*(_DWORD *)(a1 + 72) & 1 | (v3 >> 1)) + (float)(int)(*(_DWORD *)(a1 + 72) & 1 | (v3 >> 1));
  else
    v6 = (float)(int)v3;
  if ( (float)(v4 / v6) > *(float *)(a1 + 80) )
  {
    for ( i = 0; i < 3; ++i )
    {
      if ( v3 >= 0xFFFFFFFFFFFFFFFLL )
        break;
      v3 *= 2LL;
    }
    std::_Hash<std::tr1::_Uset_traits<std::wstring,std::_Hash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Init(
      a1,
      v3);
    v8 = *(_QWORD **)(a1 + 8);
    if ( (_QWORD *)*v8 != v8 )
    {
      v9 = (_QWORD **)v8[1];
      do
      {
        v10 = **(_QWORD ****)(a1 + 8);
        std::_Hash<std::tr1::_Uset_traits<std::wstring,std::_Hash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Insert(
          a1,
          (__int64)v11,
          (__int64)(v10 + 2),
          v10);
      }
      while ( v10 != v9 );
    }
  }
}

```

## disassembly

```asm
0x180017dfc  mov     [rsp+arg_0], rbx
0x180017e01  mov     [rsp+arg_8], rsi
0x180017e06  push    rdi
0x180017e07  sub     rsp, 30h
0x180017e0b  mov     r8, [rcx+10h]
0x180017e0f  mov     rdi, rcx
0x180017e12  mov     rdx, [rcx+48h]
0x180017e16  xorps   xmm0, xmm0
0x180017e19  test    r8, r8
0x180017e1c  js      short loc_180017E25
0x180017e1e  cvtsi2ss xmm0, r8
0x180017e23  jmp     short loc_180017E3B
0x180017e25  mov     rax, r8
0x180017e28  and     r8d, 1
0x180017e2c  shr     rax, 1
0x180017e2f  or      rax, r8
0x180017e32  cvtsi2ss xmm0, rax
0x180017e37  addss   xmm0, xmm0
0x180017e3b  xorps   xmm1, xmm1
0x180017e3e  test    rdx, rdx
0x180017e41  js      short loc_180017E4A
0x180017e43  cvtsi2ss xmm1, rdx
0x180017e48  jmp     short loc_180017E62
0x180017e4a  mov     rax, rdx
0x180017e4d  mov     rcx, rdx
0x180017e50  shr     rcx, 1
0x180017e53  and     eax, 1
0x180017e56  or      rcx, rax
0x180017e59  cvtsi2ss xmm1, rcx
0x180017e5e  addss   xmm1, xmm1
0x180017e62  divss   xmm0, xmm1
0x180017e66  comiss  xmm0, dword ptr [rdi+50h]
0x180017e6a  jbe     short loc_180017EBC
0x180017e6c  xor     eax, eax
0x180017e6e  mov     rcx, 0FFFFFFFFFFFFFFFh
0x180017e78  cmp     rdx, rcx
0x180017e7b  jnb     short loc_180017E87
0x180017e7d  add     rdx, rdx
0x180017e80  inc     eax
0x180017e82  cmp     eax, 3
0x180017e85  jl      short loc_180017E6E
0x180017e87  mov     rcx, rdi
0x180017e8a  call    ?_Init@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@tr1@std@@@std@@IEAAX_K@Z; std::_Hash<std::tr1::_Uset_traits<std::wstring,std::_Hash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Init(unsigned __int64)
0x180017e8f  mov     rax, [rdi+8]
0x180017e93  cmp     [rax], rax
0x180017e96  jz      short loc_180017EBC
0x180017e98  mov     rsi, [rax+8]
0x180017e9c  mov     rbx, [rdi+8]
0x180017ea0  lea     rdx, [rsp+38h+var_18]
0x180017ea5  mov     rcx, rdi
0x180017ea8  mov     rbx, [rbx]
0x180017eab  mov     r9, rbx
0x180017eae  lea     r8, [rbx+10h]
0x180017eb2  call    ?_Insert@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@tr1@std@@@std@@IEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@std@@_N@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@V?$_List_const_iterator@V?$_List_val@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@2@@Z; std::_Hash<std::tr1::_Uset_traits<std::wstring,std::_Hash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Insert(std::wstring const &,std::_List_const_iterator<std::_List_val<std::wstring>>)
0x180017eb7  cmp     rbx, rsi
0x180017eba  jnz     short loc_180017E9C
0x180017ebc  mov     rbx, [rsp+38h+arg_0]
0x180017ec1  mov     rsi, [rsp+38h+arg_8]
0x180017ec6  add     rsp, 30h
0x180017eca  pop     rdi
0x180017ecb  retn
```
