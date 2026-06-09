# std::_Hash<std::_Umap_traits<winrt::hstring,winrt::guid,std::_Uhash_compare<winrt::hstring,std::hash<winrt::hstring>,std::equal_to<winrt::hstring>>,std::allocator<std::pair<winrt::hstring const,winrt::guid>>,0>>::_Forced_rehash(unsigned __int64)

- ea: `0x180029f00`
- end: `0x18002a1a3`
- name: `?_Forced_rehash@?$_Hash@V?$_Umap_traits@Uhstring@winrt@@Uguid@2@V?$_Uhash_compare@Uhstring@winrt@@U?$hash@Uhstring@winrt@@@std@@U?$equal_to@Uhstring@winrt@@@4@@std@@V?$allocator@U?$pair@$$CBUhstring@winrt@@Uguid@2@@std@@@5@$0A@@std@@@std@@IEAAX_K@Z`
- size: `675`
- prototype: `unsigned __int64 __fastcall(_QWORD *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800273b0`

## callees

- `0x180015250`
- `0x1800299b0`
- `0x180029f00`
- `0x1800323a4`

## pseudocode

```c
unsigned __int64 __fastcall std::_Hash<std::_Umap_traits<winrt::hstring,winrt::guid,std::_Uhash_compare<winrt::hstring,std::hash<winrt::hstring>,std::equal_to<winrt::hstring>>,std::allocator<std::pair<winrt::hstring const,winrt::guid>>,0>>::_Forced_rehash(
        _QWORD *a1,
        unsigned __int64 a2)
{
  unsigned __int64 v3; // rcx
  _QWORD *v4; // rbp
  unsigned __int64 v5; // rcx
  __int64 v6; // rbx
  unsigned __int64 result; // rax
  _QWORD *v8; // rdi
  _QWORD *i; // rsi
  __int64 v10; // r9
  __int64 v11; // rcx
  unsigned __int64 v12; // rdx
  unsigned __int64 v13; // r8
  __int64 v14; // rax
  _QWORD *v15; // r14
  _QWORD *v16; // rbx
  __int64 v17; // rax
  __int64 v18; // rcx
  const wchar_t *v19; // rdx
  size_t v20; // r8
  const wchar_t *v21; // rax
  bool v22; // cl
  _QWORD *v23; // r8
  _QWORD *v24; // rdx
  _QWORD *v25; // rcx
  _QWORD *v26; // rax
  __int64 v27; // rcx
  __int64 v28; // rdx
  const wchar_t *v29; // r9
  __int64 v30; // rax
  size_t v31; // r8
  const wchar_t *v32; // rcx
  _QWORD *v34; // rdx
  _QWORD *v35; // rcx
  _QWORD *v36; // rax
  _QWORD *v37; // r8
  _QWORD *v38; // rdx
  _QWORD *v39; // rcx
  _QWORD *v40; // rax

  _BitScanReverse64(&v3, 0xFFFFFFFFFFFFFFFuLL);
  if ( a2 > 1LL << v3 )
    std::_Xlength_error("invalid hash bucket count");
  v4 = (_QWORD *)a1[1];
  _BitScanReverse64(&v5, (a2 - 1) | 1);
  v6 = 1LL << ((unsigned __int8)v5 + 1);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<winrt::hstring const,winrt::guid>>>>>>::_Assign_grow(
    a1 + 3,
    2 * v6,
    v4);
  a1[7] = v6;
  result = v6 - 1;
  a1[6] = v6 - 1;
  v8 = *(_QWORD **)a1[1];
  for ( i = v8; i != v4; result = 0xCBF29CE484222325uLL )
  {
    v10 = v8[2];
    v11 = 0xCBF29CE484222325uLL;
    i = (_QWORD *)*i;
    if ( v10 )
    {
      v12 = 0;
      v13 = 2LL * *(unsigned int *)(v10 + 4);
      if ( v13 )
      {
        do
        {
          v14 = *(unsigned __int8 *)(*(_QWORD *)(v10 + 16) + v12++);
          v11 = 0x100000001B3LL * (v14 ^ v11);
        }
        while ( v12 < v13 );
      }
    }
    v15 = (_QWORD *)(16 * (a1[6] & v11) + a1[3]);
    if ( (_QWORD *)*v15 == v4 )
    {
      *v15 = v8;
      v15[1] = v8;
    }
    else
    {
      v16 = (_QWORD *)v15[1];
      v17 = v16[2];
      if ( v17 )
      {
        v18 = *(unsigned int *)(v17 + 4);
        v19 = *(const wchar_t **)(v17 + 16);
      }
      else
      {
        v18 = 0;
        v19 = &Src;
      }
      if ( v10 )
      {
        v20 = *(unsigned int *)(v10 + 4);
        v21 = *(const wchar_t **)(v10 + 16);
      }
      else
      {
        v20 = 0;
        v21 = &Src;
      }
      if ( v20 == v18 )
      {
        if ( v20 )
          v22 = wmemcmp(v21, v19, v20) != 0;
        else
          v22 = 0;
      }
      else
      {
        v22 = 1;
      }
      if ( v22 )
      {
        if ( (_QWORD *)*v15 == v16 )
        {
LABEL_37:
          v34 = (_QWORD *)v8[1];
          *v34 = i;
          v35 = (_QWORD *)i[1];
          *v35 = v16;
          v36 = (_QWORD *)v16[1];
          *v36 = v8;
          v16[1] = v35;
          i[1] = v34;
          v8[1] = v36;
          *v15 = v8;
        }
        else
        {
          while ( 1 )
          {
            v16 = (_QWORD *)v16[1];
            v27 = v16[2];
            if ( v27 )
            {
              v28 = *(unsigned int *)(v27 + 4);
              v29 = *(const wchar_t **)(v27 + 16);
            }
            else
            {
              v28 = 0;
              v29 = &Src;
            }
            v30 = v8[2];
            if ( v30 )
            {
              v31 = *(unsigned int *)(v30 + 4);
              v32 = *(const wchar_t **)(v30 + 16);
            }
            else
            {
              v31 = 0;
              v32 = &Src;
            }
            if ( v31 == v28 && (!v31 || wmemcmp(v32, v29, v31) == 0) )
              break;
            if ( (_QWORD *)*v15 == v16 )
              goto LABEL_37;
          }
          v37 = (_QWORD *)*v16;
          v38 = (_QWORD *)v8[1];
          *v38 = i;
          v39 = (_QWORD *)i[1];
          *v39 = v37;
          v40 = (_QWORD *)v37[1];
          *v40 = v8;
          v37[1] = v39;
          i[1] = v38;
          v8[1] = v40;
        }
      }
      else
      {
        v23 = (_QWORD *)*v16;
        if ( (_QWORD *)*v16 != v8 )
        {
          v24 = (_QWORD *)v8[1];
          *v24 = i;
          v25 = (_QWORD *)i[1];
          *v25 = v23;
          v26 = (_QWORD *)v23[1];
          *v26 = v8;
          v23[1] = v25;
          i[1] = v24;
          v8[1] = v26;
        }
        v15[1] = v8;
      }
    }
    v8 = i;
  }
  return result;
}

```

## disassembly

```asm
0x180029f00  push    r15
0x180029f02  sub     rsp, 50h
0x180029f06  mov     rax, 0FFFFFFFFFFFFFFFh
0x180029f10  mov     r15, rcx
0x180029f13  bsr     rcx, rax
0x180029f17  mov     eax, 1
0x180029f1c  shl     rax, cl
0x180029f1f  cmp     rdx, rax
0x180029f22  ja      loc_18002A196
0x180029f28  mov     [rsp+58h+arg_10], rbx
0x180029f2d  lea     rax, [rdx-1]
0x180029f31  mov     [rsp+58h+var_10], rbp
0x180029f36  or      rax, 1
0x180029f3a  mov     rbp, [r15+8]
0x180029f3e  mov     ebx, 1
0x180029f43  bsr     rcx, rax
0x180029f47  mov     [rsp+58h+var_18], rsi
0x180029f4c  mov     r8, rbp
0x180029f4f  inc     ecx
0x180029f51  mov     [rsp+58h+var_20], rdi
0x180029f56  shl     rbx, cl
0x180029f59  lea     rcx, [r15+18h]
0x180029f5d  mov     [rsp+58h+var_28], r12
0x180029f62  lea     rdx, [rbx+rbx]
0x180029f66  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUhstring@winrt@@Uguid@2@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUhstring@winrt@@Uguid@2@@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<winrt::hstring const,winrt::guid>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<winrt::hstring const,winrt::guid>>>>)
0x180029f6b  mov     [r15+38h], rbx
0x180029f6f  lea     rax, [rbx-1]
0x180029f73  mov     [r15+30h], rax
0x180029f77  mov     rdi, [r15+8]
0x180029f7b  mov     rdi, [rdi]
0x180029f7e  mov     rsi, rdi
0x180029f81  cmp     rdi, rbp
0x180029f84  jz      loc_18002A150
0x180029f8a  mov     [rsp+58h+var_30], r13
0x180029f8f  mov     rax, 0CBF29CE484222325h
0x180029f99  mov     [rsp+58h+var_38], r14
0x180029f9e  mov     r13, 100000001B3h
0x180029fa8  nop     dword ptr [rax+rax+00000000h]
0x180029fb0  mov     r9, [rdi+10h]
0x180029fb4  mov     rcx, rax
0x180029fb7  mov     rsi, [rsi]
0x180029fba  test    r9, r9
0x180029fbd  jz      short loc_180029FE5
0x180029fbf  mov     r8d, [r9+4]
0x180029fc3  mov     edx, 0
0x180029fc8  mov     r10, [r9+10h]
0x180029fcc  add     r8, r8
0x180029fcf  jz      short loc_180029FE5
0x180029fd1  movzx   eax, byte ptr [r10+rdx]
0x180029fd6  inc     rdx
0x180029fd9  xor     rcx, rax
0x180029fdc  imul    rcx, r13
0x180029fe0  cmp     rdx, r8
0x180029fe3  jb      short loc_180029FD1
0x180029fe5  and     rcx, [r15+30h]
0x180029fe9  mov     r14, [r15+18h]
0x180029fed  shl     rcx, 4
0x180029ff1  add     r14, rcx
0x180029ff4  cmp     [r14], rbp
0x180029ff7  jnz     short loc_18002A005
0x180029ff9  mov     [r14], rdi
0x180029ffc  mov     [r14+8], rdi
0x18002a000  jmp     loc_18002A130
0x18002a005  mov     rbx, [r14+8]
0x18002a009  mov     rax, [rbx+10h]
0x18002a00d  test    rax, rax
0x18002a010  jz      short loc_18002A01B
0x18002a012  mov     ecx, [rax+4]
0x18002a015  mov     rdx, [rax+10h]
0x18002a019  jmp     short loc_18002A024
0x18002a01b  xor     ecx, ecx
0x18002a01d  lea     rdx, Src; S2
0x18002a024  test    r9, r9
0x18002a027  jz      short loc_18002A033
0x18002a029  mov     r8d, [r9+4]
0x18002a02d  mov     rax, [r9+10h]
0x18002a031  jmp     short loc_18002A03D
0x18002a033  xor     r8d, r8d; N
0x18002a036  lea     rax, Src
0x18002a03d  cmp     r8, rcx
0x18002a040  jz      short loc_18002A049
0x18002a042  mov     ecx, 1
0x18002a047  jmp     short loc_18002A05F
0x18002a049  test    r8, r8
0x18002a04c  jnz     short loc_18002A052
0x18002a04e  xor     ecx, ecx
0x18002a050  jmp     short loc_18002A05F
0x18002a052  mov     rcx, rax; S1
0x18002a055  call    wmemcmp
0x18002a05a  test    eax, eax
0x18002a05c  setnz   cl
0x18002a05f  test    cl, cl
0x18002a061  jnz     short loc_18002A095
0x18002a063  mov     r8, [rbx]
0x18002a066  cmp     r8, rdi
0x18002a069  jz      short loc_18002A08C
0x18002a06b  mov     rdx, [rdi+8]
0x18002a06f  mov     [rdx], rsi
0x18002a072  mov     rcx, [rsi+8]
0x18002a076  mov     [rcx], r8
0x18002a079  mov     rax, [r8+8]
0x18002a07d  mov     [rax], rdi
0x18002a080  mov     [r8+8], rcx
0x18002a084  mov     [rsi+8], rdx
0x18002a088  mov     [rdi+8], rax
0x18002a08c  mov     [r14+8], rdi
0x18002a090  jmp     loc_18002A130
0x18002a095  cmp     [r14], rbx
0x18002a098  jz      short loc_18002A10C
0x18002a09a  nop     word ptr [rax+rax+00h]
0x18002a0a0  mov     rax, [rbx+8]
0x18002a0a4  mov     rbx, rax
0x18002a0a7  mov     rcx, [rax+10h]
0x18002a0ab  test    rcx, rcx
0x18002a0ae  jz      short loc_18002A0B9
0x18002a0b0  mov     edx, [rcx+4]
0x18002a0b3  mov     r9, [rcx+10h]
0x18002a0b7  jmp     short loc_18002A0C2
0x18002a0b9  xor     edx, edx
0x18002a0bb  lea     r9, Src
0x18002a0c2  mov     rax, [rdi+10h]
0x18002a0c6  test    rax, rax
0x18002a0c9  jz      short loc_18002A0D5
0x18002a0cb  mov     r8d, [rax+4]
0x18002a0cf  mov     rcx, [rax+10h]
0x18002a0d3  jmp     short loc_18002A0DF
0x18002a0d5  xor     r8d, r8d; N
0x18002a0d8  lea     rcx, Src; S1
0x18002a0df  cmp     r8, rdx
0x18002a0e2  jz      short loc_18002A0EB
0x18002a0e4  mov     eax, 1
0x18002a0e9  jmp     short loc_18002A103
0x18002a0eb  test    r8, r8
0x18002a0ee  jnz     short loc_18002A0F4
0x18002a0f0  xor     eax, eax
0x18002a0f2  jmp     short loc_18002A103
0x18002a0f4  mov     rdx, r9; S2
0x18002a0f7  call    wmemcmp
0x18002a0fc  test    eax, eax
0x18002a0fe  mov     ecx, eax
0x18002a100  setnz   al
0x18002a103  test    al, al
0x18002a105  jz      short loc_18002A170
0x18002a107  cmp     [r14], rbx
0x18002a10a  jnz     short loc_18002A0A0
0x18002a10c  mov     rdx, [rdi+8]
0x18002a110  mov     [rdx], rsi
0x18002a113  mov     rcx, [rsi+8]
0x18002a117  mov     [rcx], rbx
0x18002a11a  mov     rax, [rbx+8]
0x18002a11e  mov     [rax], rdi
0x18002a121  mov     [rbx+8], rcx
0x18002a125  mov     [rsi+8], rdx
0x18002a129  mov     [rdi+8], rax
0x18002a12d  mov     [r14], rdi
0x18002a130  mov     rdi, rsi
0x18002a133  mov     rax, 0CBF29CE484222325h
0x18002a13d  cmp     rsi, rbp
0x18002a140  jnz     loc_180029FB0
0x18002a146  mov     r14, [rsp+58h+var_38]
0x18002a14b  mov     r13, [rsp+58h+var_30]
0x18002a150  mov     rdi, [rsp+58h+var_20]
0x18002a155  mov     rsi, [rsp+58h+var_18]
0x18002a15a  mov     rbp, [rsp+58h+var_10]
0x18002a15f  mov     rbx, [rsp+58h+arg_10]
0x18002a164  mov     r12, [rsp+58h+var_28]
0x18002a169  add     rsp, 50h
0x18002a16d  pop     r15
0x18002a16f  retn
0x18002a170  mov     r8, [rbx]
0x18002a173  mov     rdx, [rdi+8]
0x18002a177  mov     [rdx], rsi
0x18002a17a  mov     rcx, [rsi+8]
0x18002a17e  mov     [rcx], r8
0x18002a181  mov     rax, [r8+8]
0x18002a185  mov     [rax], rdi
0x18002a188  mov     [r8+8], rcx
0x18002a18c  mov     [rsi+8], rdx
0x18002a190  mov     [rdi+8], rax
0x18002a194  jmp     short loc_18002A130
0x18002a196  lea     rcx, aInvalidHashBuc; "invalid hash bucket count"
0x18002a19d  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
